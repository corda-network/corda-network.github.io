The Corda Network Foundation
============================

Allowable Identity Names
========================

[Document history]({{ site.github.repository_url }}/blame/master/{{page.path}})

1 Proposed policy
===================

Legal names registered with the Corda network must be submitted in the form of an X.500 name with at least the 
organisation, locality and country attributes present. They must be sorted in the order specified in the Corda protocol. 
The zone operator will ensure each component meets the following requirements:

* The organisation, locality and country attributes are present. The state, organisational-unit and common name attributes 
are optional.
* The fields of the name have the following maximum character lengths:
    * Common name: 64
    * Organisation: 128
    * Organisation unit: 64
    * Locality: 64
    * State: 64
* The country attribute is a valid ISO 3166-1 two letter code in upper-case
* The free text fields of the name obey the following constraints
* Consist only of characters from the following Unicode code blocks: Basic Latin, Latin-1 Supplement, Latin Extended A, 
Latin Extended B
* Control characters are not allowed.
* Must have at least two characters.
* Must be normalized to Unicode NKFC form.
* The following characters are forbidden:  , = $ " ' \ /
* There may not be any trailing or leading whitespace.
* They must be encoded using UTF-8

The following rules may cause rejection if sufficient justification is not provided. The definition of "sufficient 
justification" is up to the zone operator and may be changed without notice:

* A stopword sequence is present.
* The name is not capitalised.

Stopwords are character sequences that may be the result of mistaken applications or intent to confuse. The zone 
operator may adjust the list of stopwords at any time. The Foundation may request a list of current or prior 
stopwords at any time.

Examples of likely stopwords:
* Corda
* R3
* Node
* Server
* Oracle (obviously this one is particularly special)
* Ã
* Â

The first 5 are intended to avoid confusing node names or people creating names like "MegaCorp Corda Node" which would 
not be a valid legal name. The last two are intended to catch encoding mismatch errors. Cases where company names 
legitimately include stopwords will be handled via manual review.

The Corda Network uses Unicode version 6.2

2 Rationale
===========
English benefits from a very simple alphabet. Many languages have more complex writing systems and this frequently 
leads to a cascade of bugs and security holes when working with so-called "international text". Despite the decades of 
excellent work done by the Unicode Consortium on creating a global system for computerized text, it is still a complex 
area.

The rules above are designed to simplify Corda development for both R3 and app developers. Here is a subset of the 
problems we hope to avoid:

* Names that cannot be pronounced over the phone by support staff.
* Confusible character attacks, e.g. submitting an application for a name that already exists with letters like "o" 
swapped for their Cyrillic equivalents, thus creating what appears to a computer to be a unique name.
* Confusion attacks based on flipping text direction half way through a script that doesn't benefit from it, for 
instance try copying the following word out of this email and into a text editor or terminal:  Mega‮proC‏
You will find that it isn't quite what you expected.
* Varying Unicode canonicalization, for instance is the letter ü represented as a single character or as a u followed 
by the ¨ combining character? NFKC form provides an answer.
* Some common software is critically buggy when faced with characters outside the Basic Multilingual Plane. MySQL in 
particular does not support the full range of Unicode inside UTF-8 fields. You have to specify the column type as 
utf8mb4 instead. If you don't the non-BMP character and anything after it is silently truncated. This is not considered 
a bug by the MySQL developers and therefore does not get fixed.Facebook got hacked in this way.

It would imply a need to fully support complex scripts in end user apps, which may need to interop with legacy mainframe 
based applications that do not handle Unicode properly.

The restriction on only supporting the extended Latin alphabet may be considered restrictive in some locales, as it 
effectively forbids the use of Arabic, Thai, Chinese, Hebrew etc in legal entity names. Even worse it restricts the use 
of emoji 💔😢.

The owners of names that lie outside the extended Latin alphabet must select a canonical transliteration before they 
apply for an identity in the main zone. Future versions of this policy may relax the naming requirements, probably in 
concert with new platform features to make it easier to work with such names (e.g. integrated transliteration facilities).
The X.500 standard is used to disambiguate legal names using locality information, as company names are not globally 
unique (see https://stripe.ian.sh for an example of this).

Control characters are forbidden for obvious reasons.

The comma is forbidden because it is used to separate X.500 components when serialised to text. This rule is restrictive 
and it may need to be removed, as commas are commonly found in legitimate legal names. The X.500 text format can escape 
commas by wrapping a component with double quotes, which is why " is also forbidden. Note that X.500 names are natively 
binary and thus do not suffer such escaping issues, but the prevalence of web apps and the entirely textual nature of 
the web protocol stack implies names should be easily worked with in textual forms too.

The = \ / and $ characters are forbidden due to the number of systems in which they are interpreted as having special 
meaning, and the low probability of them appearing in legitimate legal entity names.

Stopwords are implemented to catch the case where someone tries to give their node a name that isn't a legal entity name 
but rather, specifies what it is (e.g. "MegaCorp Corda Node"). 

The first-letter-capitalized rule is to stop lazy admins submitting names like "hsbc corp". We want names that look 
good in user interfaces!

The selected Unicode version is the one supported by Java 8.

3 Developer notes
=================

Handling international text is a remarkably difficult task, filled with pitfalls for new and experienced engineers 
alike. For best results follow these recommendations:
* Do not be tempted to perform "looks alike" conversion into ASCII when attempting to interop with legacy systems. If you 
absolutely cannot upgrade a target system to be Unicode aware, use ? as a replacement character. Mapping extended 
Latin characters to characters that English speakers think look the same has caused people to kill each other by 
accident (the linked article is not a joke).
* Names on the Corda network should not be prepared for comparison using methods like toLowerCase() or toUpperCase() 
because some supported characters do not survive case roundtripping. For example the German letter ß converts to "SS" 
when uppercased but, of course, "SS" converts to "ss" when lowercased. Whilst making two pieces of text "human compares 
equal" by simply lowercasing or uppercasing is valid in English, in other languages some visual differences may be 
considered irrelevant yet not be removed by re-casing. A better approach is to use a java.text.Collator object, then 
call the setStrength method to determine how lax the match should be, and then check if the compare method returns zero.
* A Collator object should also be used to sort Corda names, for example if you wish to create an alphabetically sorted 
list of target names. Note that sorting (collation) rules change depending on the native language of the user. For 
example in Germany Ü sorts directly after U however in Swedish it is considered a separate letter and Ü will sort after 
Z. Therefore if you want to sort things alphabetically you should have some understanding of where your user is from. 
The HTTP Accept-Language header may seem tempting for this but it is common for users who aren't native English 
speakers to put English first in their preference list, due to the abundance of poorly localized apps. So you may wish 
to obtain this information in different ways, or to pay attention to the first non-English language specified.
* When allowing the user to input free text for identities, use the CordaRPCOps.partiesFromName RPC to do lookups and 
set exactMatch to false. Don't attempt to download the network map or a BNO membership list and do your own matching - 
do the query first against the network map, then filter out members that are not in the BNO list. 

Corda will do fuzzy matching of names for you. This matching is likely to improve over time, at least in some 
implementations, e.g. by introducing Soundex matching, Jaro-Winkler or Levenshtein distance computation, automatic NFKC 
canonicalisation, Thai word breaking, spelling correction and so on. These tasks are extremely hard to do well in 
JavaScript so web app authors should pay particular attention to this point.

Future versions of the platform will probably include new APIs for guiding developers towards the right tools and 
behaviours here.

Please note that these guidelines are not exhaustive. R3 employees can find a tech talk that explores Unicode security 
further on our wiki.

4 Potential future evolutions
=============================

* Support for more alphabets like Chinese and its variants, Japanese, Thai, Arabic, Hebrew. This implies allowing 
right-to-left text in names and consequent policies designed to detect abuse.
* Allowing commas and quote characters for e.g. Irish names, name of law firms etc.
* Policy constraints on acceptable state, country names.
* Relaxation or removal of stopwords. Alternatively, addition of more stopwords e.g. swear words.
* Integration of Unicode confusible character detection algorithms.