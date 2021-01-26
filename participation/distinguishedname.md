# Corda Network Rulebook

- [1. Admissions Criteria](#1-admissions-criteria)
  - [1.1. Introduction](#11-introduction)
  - [1.2. Policy](#12-policy)
  - [1.3. Rationale](#13-rationale)
  - [1.4. Addendum](#14-addendum)
- [2. Allowable Identity Names](#2-allowable-identity-names)
  - [2.1. Introduction](#21-introduction)
  - [2.2. Choosing X500 Name for your Node](#22-choosing-x500-name-for-your-node)
    - [2.2.1. Selecting the Right Legal Entity for the Organisation Field](#221-selecting-the-right-legal-entity-for-the-organisation-field)
    - [2.2.2. Constraints on Characters and Unicode](#222-constraints-on-characters-and-unicode)
    - [2.2.3 Stopwords](#223-stopwords)
    - [2.2.4 E-mail Contained in the *NodeConf* File](#224-e-mail-contained-in-the-nodeconf-file)
  - [2.3. Rationale](#23-rationale)
  - [2.4. Developer Notes](#24-developer-notes)
  - [2.5. Potential Future Evolutions](#25-potential-future-evolutions)

  

## 1. Admissions Criteria

## 1.1. Introduction

Participants, including Business Network Operators, must request a certificate from the Corda Network Certificate Authority (Certificate Authority) to gain access to and join Corda Network. 
The Certificate Authority’s validation and approval to the network should not be considered, nor treated as, a substitute for required “Know Your Customer” processes. All Corda Network Participants, Customers and Business Network Operators are obligated to escalate inappropriate business conduct or fraudulent identities to the Certificate Authority and relevant regulatory bodies or authorities.


## 1.2. Policy

The Certificate Authority provides a certificate to non-natural persons, i.e. organisations that are an incorporated legal entity. The following information must be provided by all Participants upon request:
- Entity name
- Entity Address
- Contact Name
- Contact Email Address
- Contact Phone Number
- Unique ID – (GLEIF ID, EIN, CRN, etc.)
- Website Domain (Optional)

Note: additional details may be required for Participant billing, but these requirements do not form part of this Rulebook.

The Certificate Authority has established a sanction review commensurate with jurisdictional laws and regulations on all entities. Positive matches will not be allowed to receive a certificate for the Corda Network. Business Network Operators must perform their own KYC check and should not rely on the Certificate Authority's identification or sanction review. Business Network Operators are responsible for obtaining further documentation such as articles of incorporation, evidence of ultimate beneficial ownership, and any other evidence needed to verify identity and conduct appropriate due diligence checks (high risk industry analysis, high risk geographies, negative news checks) to ensure entities meet acceptable risk tolerance standards designed by the business network.

Certifications will be issued based on the information provided in the certification request. Any changes to information contained in the Participant certificate, including updating the entity name or contact information, will require the certificate to be revoked and re-issued by the Certificate Authority.

## 1.3. Rationale

The Certificate Authority requires certain minimum information for billing purposes and to confirm identities on the Corda Network. See below membership requirements for other foundations.

* SWIFT: The country risk (e.g. FATF versus non-FATF countries), affiliation of SWIFT users to current member base, 
intended use of SWIFT products and services (e.g. the use by the (applicant) SWIFT user of the SWIFT financial messaging 
services for necessary and legitimate business purposes), applicable sanctions regulations, and credit worthiness of the 
applicant SWIFT user. Other requests: A certificate of incorporation, a tax certificate, an operating license, a 
declaration of ownership, a list of shareholders, a list of authorised signatures, the composition of the board and/or 
executives and audited accounts. * These requirements are too onerous for the Corda Network. SWIFT is similar to a business network operator and all 
    SWIFT members have a common interest in a specific type of service. Corda Network Participants have vastly different interests and 
    uses so membership criteria should not be so stringent. It is worth noting that individual Business Network 
    Operators could choose to implement more stringent requirements, such as seen by SWIFT, if they so choose.

* OPEC: Any country with a substantial net export of crude petroleum, which has fundamentally similar interests to those of certain specified member countries, may become a full member of the OPEC organization, if accepted by a majority constituting three-fourths of full members, including the concurring votes of all founding members. * A centralized approval process is not feasible for Corda Network design.

* ISO: When joining ISO, documents confirming the entity’s status as the organization most representative of 
standardization in the entity’s respective country, and that said country is recognized by the United Nations. * Corda network should only do business with UN recognized countries.

* ICANN: The name and contact information (including email address, physical address and contact phone number) for the 
domain's registrant, administrative and billing contacts. * This is practical for the Corda Network.  
    
## 1.4. Addendum

The Certificate Authority must screen potential participants against the following lists for all before allowing to become a Participant: 

* United Kingdom Her Majesty’s Treasury Sanctions    
* Office of Foreign Assets Control Non-Specially Designated National Entities
* Office of Foreign Assets Control Sanctions         
* Office of Foreign Assets Control Specially Designated Nationals
* United Nations Consolidated List
* Bureau of Industry and Security
* Excluded Parties List System
* FATF Financial Action Task Force         
* Office of the Superintendent of Financial Institutions Consolidated List—Canada
* Consolidated list of Persons, Groups and Entities subject to EU Financial Sanctions
* [Section 311 of the USA Patriot Act](https://home.treasury.gov/policy-issues/terrorism-and-illicit-finance/311-actions)
* [Office of the Comptroller of the Currency (OCC) Unauthorized Banking List](https://www.occ.treas.gov/news-issuances/alerts/2010/alert-2010-12.html)

## 2. Allowable Identity Names

## 2.1. Introduction

Any Node must have a unique Distinguished Name (DN) or X.500 name in its [participation certificate](https://docs.corda.net/corda-network/index.html#identity-service). Legal names registered with the Corda Network Certificate Authority are to be submitted in the form of an X.500 name that must include 4 fields:

- Organisation (O)
- Organisation Unit (OU)
- Locality (L)
- Country (C)

X.500 names may include up to 6 fields (optional additional fields are State (S) and Common Name(CN)), explained in greater detail in section 1.2 below. Data fields in the X.500 name must be sorted in the order specified in the Corda protocol.

The entire X.500 name is used for the uniqueness check. For now, the maximum number of characters of your X.500 name (including field names, such as "O=", "OU=", "L=" are is **128 characters**.

## 2.2. Choosing X500 Name for your Node

The Certificate Authority must ensure all X.500 names meet the following requirements:

- Mandatory Organisation, Organisational-Unit, Locality and Country attributes are present.
- Organisation attribute represents a legal entity name, which is the beneficial owner of states on the ledger.
- The Country attribute is a valid ISO 3166-1 two letter code in upper-case.

Overall, the DN is one of the most common points of error in joining Corda Network, so take care to fill this out correctly. As part of standard onboarding checks for Corda Network, the Certificate Authority may verify that these details have been accurately populated and reject requests where the population of these fields does not appear to be correct.

For guidance on writing a legal entity name please see the table below:





| Field                      | Mandatory | Length (chars) | Validation                                                                                       | Purpose                                                                                                                                                                                                                                                                                                                                              |
|----------------------------|:---------:|---------------:|--------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Organisation (O)**       |     Y     |            110 | As per above, and additionally: No double-spacing. May not contain  stopwords like "node" or "server". | The O field for the legal entity defines the beneficial owner of states on the ledger. This should be set to the **legal name** of the organisation, as it appears on the official trade register within the jurisdiction in which the entity is registered. This is used to define the owning organisation of the Node / certificate. More details provided in section 2.2.1.               |
| **Organisation Unit (OU)** |     Y     |             64 | As per above                                                                                     | This field is generally used to denote sub-divisions or units in the organisation (legal entity). It may be used by Node operators for internal purposes to separate Nodes used for different purposes by the same legal entity.                                                                                                                     |
| **Locality (L)**          |     Y     |             64 | As per above                                                                                     | The city or town in which the registered head-office of the legal entity is located. If the company operates from New York City but is registered in Wilmington, Delaware then please use Wilmington.                                                                                                                                                 |
| **Country (C)**            |     Y     |              2 | [2-digit ISO code](https://en.wikipedia.org/wiki/ISO_3166-2)                                                                                 | The country in which the registered head-office of the legal entity is located.                                                                                                                                                                                                                                                                      |
| **State (S)**              |     N     |             64 | As per above                                                                                     | If your country operates a State or Province system (e.g. USA and Canada) please add the State in which the registered head-office of the legal entity is located. Do not abbreviate. For example, "CA" is not a valid state name. "California" is correct. If the company operates from New York but is registered in Delaware, please use Delaware. |
| **Common Name (CN)**       |     N     |             64 | As per above                                                                                     | Available for use by the Node operator for their own internal purposes. Often used for home website urls in www.                                                                                                                                                                                                                                     |

### 2.2.1. Selecting the Right Legal Entity for the Organisation Field

The Certificate Authority must ensure all X.500 names meet the following requirements:

According to Corda Network policy, the Legal Entity in the “O” field of the Node’s X.500 name should be the owner of the assets to be transacted.

The Legal Entity should not be a high-level Corporate Group (for example, "HSBC") but the specific legal entity which owns the assets (for example: HSBC Asset Finance (UK) Limited).

It should match the exact name in the government official trade list, in which it is registered.

Here are a few examples of filling out the whole X500 name, in practice. Take a careful look at the O field selected - this is the cause of most errors!


**Example 1:**

| Field title | Example |
|---------------------------------|---|
| **Organisation (O)**            | NatWest Markets PLC  |
| **City (L)**                    | Edinburgh  |
| **Country (C)**                 | UK  |
| **Organisation Unit (OU)**      | FI  |
| State (US / Canada only)        |   |
| Organisation Unit (OU)          |   |
| Common Name (CN)                |   |
| **Node Operator email address** | admin@natwestmarkets.com (example - not actual email address)|

*This is the correct Legal Entity name, as evidenced in the UK government trade register, here:https://beta.companieshouse.gov.uk/company/SC090312*


**Example 2:**

| Field title | Example |
|---------------------------------|---|
| **Organisation (O)**            | BNP PARIBAS SA  |
| **City (L)**                    | Serignan  |
| **Country (C)**                 | France  |
| **Organisation Unit (OU)**      | Agent1  |
| State (US / Canada only)        |   |
| Common Name (CN)                |   |
| **Node Operator email address** | information@bnpp.fr (example - not actual email address) |

 
*This is the correct Legal Entity name, as evidenced in the French government trade register, here: http://www.sirene.fr/sirene/public/recherche*


**Here are some examples of government trade registers (list is a work in progress):**

|Country | Link |
|--- | --- |
|Australia | https://connectonline.asic.gov.au/RegistrySearch/faces/landing/SearchRegisters.jspx?_adf.ctrl-state=jx0kwgy52_4|
|Chile | https://www.conservador.cl/portal/indice_comercio|
|France | http://www.sirene.fr/sirene/public/accueil?sirene_locale=en|
|Finland | https://virre.prh.fi/novus/home?execution=e1s1|
|Hungary | https://www.e-cegjegyzek.hu/?cegkereses|
|India | http://www.mca.gov.in/mcafoportal/viewCompanyMasterData.do|
|Philippines | https://www.bnrs.dti.gov.ph/web/guest/search|
|Singapore | https://www.bizfile.gov.sg/ngbbizfileinternet/faces/oracle/webcenter/portalapp/pages/BizfileHomepage.jspx|
|South Africa | https://eservices.cipc.co.za/Search.aspx|
|UK | https://beta.companieshouse.gov.uk/|
|US | https://www.sec.gov/edgar/searchedgar/companysearch.html|


Please also refer to this page for a list of company registers: https://en.wikipedia.org/wiki/List_of_company_registers#cite_note-194

### 2.2.2. Constraints on Characters and Unicode

Your identity name (including field names such as "O=", "OU=", "L=" are included in the 128 characters limit.

The free text fields in the X.500 name must obey the following constraints:

- Consist only of characters from the following Unicode code blocks: Basic Latin, Latin-1 Supplement, Latin Extended A, Latin Extended B. 
- Start with upper-case first letter. 
- May not not contain the null character.
- May not contain control characters.  
- Must have at least two characters. 
- Must be normalized to Unicode NFKC form. 
- May not include the following forbidden characters: , , = , $ , " , ' , \, +
- May not include trailing or leading whitespace. 
- Must be encoded using UTF-8. 

The following rules may cause rejection if sufficient justification is not provided. The definition of "sufficient justification" is up to the Certificate Authority and may be changed without notice:

- A stopword sequence is present.
- The name is not capitalised.

### 2.2.3. Stopwords

Stopwords are character sequences that may be the result of mistaken applications or intent to confuse. The  Certificate Authority may adjust the list of stopwords at any time. The Foundation may request a list of current or prior stopwords at any time.

Examples of likely stopwords:
- Corda
- R3
- Node
- Server
- Oracle
- Ã
- Â
- test (in Corda Network Production environment)

The first five are intended to avoid confusing Node names or people creating names like "MegaCorp Corda Node" which would not be a valid legal name. The last two are intended to catch encoding mismatch errors. Cases where company names legitimately include stopwords will be handled via manual review.
The Corda Network uses Unicode version 6.2.

### 2.2.4. E-mail Contained in the *NodeConf* File

Before a Node can be onboarded to Corda Network, the Certificate Authority needs a response from authenticated email address contained in the CSR to confirm that: 
- the email domain used in the node.conf is associated with the legal entity requesting the certificate; and
- the person submitting the CSR has access to the email inbox listed in the node.conf file. 

**Requirements for the e-mail address**

The email address used in the node.conf file will be used for communications with the Node operator, including those involved in identity verification and for all future communication related to Corda Network. This is why it must be associated with the legal entity submitting the request, and be an actively monitored mailbox such as ‘admin@, ‘info@’ or ‘support’.

## 2.3. Rationale

English benefits from a very simple alphabet. Many languages have more complex writing systems and this frequently 
leads to a cascade of bugs and security holes when working with so-called "international text". Despite the decades of 
excellent work done by the Unicode Consortium on creating a global system for computerized text, it is still a complex 
area.

The rules above are designed to simplify Corda development for both R3 and app developers. Here is a subset of the 
problems we hope to avoid:

* Names that cannot be pronounced over the phone by support staff.
* Confusable character attacks, e.g. submitting an application for a name that already exists with letters like "o" 
swapped for their Cyrillic equivalents, thus creating what appears to a computer to be a unique name.
* Confusion attacks based on flipping text direction half way through a script that doesn't benefit from it. For 
instance, try copying the following word out of this email and into a text editor or terminal: "MegaproC".
You will find that it isn't quite what you expected.
* Varying Unicode canonicalization, for instance is the letter ü represented as a single character or as a u followed 
by the ¨ combining character? NFKC form provides an answer.
* Some common software is critically buggy when faced with characters outside the Basic Multilingual Plane. MySQL in 
particular does not support the full range of Unicode inside UTF-8 fields. You have to specify the column type as 
utf8mb4 instead. If you don't, the non-BMP character and anything after it is silently truncated. This is not considered 
a bug by the MySQL developers and therefore does not get fixed. Facebook got hacked in this way.

It would imply a need to fully support complex scripts in end user apps, which may need to inter-operate with legacy mainframe 
based applications that do not handle Unicode properly.

The restriction on only supporting the extended Latin alphabet may be considered restrictive in some locales, as it 
effectively forbids the use of Arabic, Thai, Chinese, Hebrew etc in legal entity names. Even worse, it restricts the use 
of emoji 💔😢.

The owners of names that lie outside the extended Latin alphabet must select a canonical transliteration before they 
apply for an identity in the main zone. Future versions of this policy may relax the naming requirements, probably in 
concert with new platform features to make it easier to work with such names (e.g. integrated transliteration facilities).
The X.500 standard is used to disambiguate legal names using locality information, as company names are not globally 
unique (see https://stripe.ian.sh for an example of this).

Control characters are forbidden for obvious reasons.

The comma is forbidden because it is used to separate X.500 components when serialised to text. This rule is restrictive, 
and it may need to be removed, as commas are commonly found in legitimate legal names. The X.500 text format can escape 
commas by wrapping a component with double quotes, which is why " is also forbidden. Note that X.500 names are natively 
binary and thus do not suffer such escaping issues, but the prevalence of web apps and the entirely textual nature of 
the web protocol stack implies names should be easily worked with in textual forms too.

The = \ / and $ characters are forbidden due to the number of systems in which they are interpreted as having special 
meaning, and the low probability of them appearing in legitimate legal entity names.

Stopwords are implemented to catch the case where someone tries to give their Node a name that isn't a legal entity name 
but rather, specifies what it is (e.g. "MegaCorp Corda Node"). 

The first-letter-capitalized rule is to stop lazy admins submitting names like "hsbc corp". We want names that look 
good in user interfaces!

The selected Unicode version is the one supported by Java 8.

## 2.4. Developer Notes

Handling international text is a remarkably difficult task, filled with pitfalls for new and experienced engineers 
alike. For best results follow these recommendations:

* Do not be tempted to perform "looks alike" conversion into ASCII when attempting to inter-operate with legacy systems. If you 
absolutely cannot upgrade a target system to be Unicode aware, use ? as a replacement character. Mapping extended 
Latin characters to characters that English speakers think look the same has caused people to kill each other by 
accident (the linked article is not a joke).

* Names on the Corda Network should not be prepared for comparison using methods like toLowerCase() or toUpperCase() 
because some supported characters do not survive case round-tripping. For example the German letter ß converts to "SS" 
when upper-cased but, of course, "SS" converts to "ss" when lower-cased. Whilst making two pieces of text "human compares 
equal" by simply lower-casing or upper-casing is valid in English, in other languages some visual differences may be 
considered irrelevant yet not be removed by re-casing. A better approach is to use a java.text.Collator object, then 
call the setStrength method to determine how lax the match should be, and then check if the compare method returns zero.

* A Collator object should also be used to sort Corda Network names, for example if you wish to create an alphabetically sorted 
list of target names. Note that sorting (collation) rules change depending on the native language of the user. For 
example in Germany Ü sorts directly after U however in Swedish it is considered a separate letter and Ü will sort after 
Z. Therefore if you want to sort things alphabetically you should have some understanding of where your user is from. 
The HTTP Accept-Language header may seem tempting for this but it is common for users who are not native English 
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

## 2.5. Potential Future Evolutions

* Support for more alphabets like Chinese and its variants, Japanese, Thai, Arabic, Hebrew. This implies allowing 
right-to-left text in names and consequent policies designed to detect abuse.
* Allowing commas and quote characters for e.g. Irish names, name of law firms etc.
* Policy constraints on acceptable state, country names.
* Relaxation or removal of stopwords. Alternatively, addition of more stopwords e.g. swear words.
* Integration of Unicode confusable character detection algorithms.
