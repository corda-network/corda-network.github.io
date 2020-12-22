# Corda Network Rulebook

## Introduction

This Corda Network Rulebook defines the rules, standards and policies governing activity within the Corda Network that are mandatory for all Corda Network participants, as adopted by Certificate Authority from time to time and provided to Participants. Some of these rules derive from Corda Network Foundation. 
This document defines:

- Admissions criteria for Corda Network. 
- Allowable identity names on Corda Network and how to correctly fill in the fields in X.500 name certificates. 
- Revocation criteria for Corda Network Participants. 

Corda Network Participants accept the rules and policies contained within this document upon signing Corda Network participant Terms of Use.


## Definitions

| Term | Description |
| --- | --- |
| Business Network Operator | A Business Network Operator may set-up and operate its own business network for groups or companies that wish to transact together on the Corda Network. Depending on their size, Business Network Operators may also wish to on-board, off-board their members. |
| Corda Network Foundation | A not-for-profit legal entity known as a Stichting residing in the Netherlands. The Foundation governs Corda Network’s public key infrastructure, sets policies and standards related to it, and enables Network participants to be involved with, and also understand, how decisions on these areas are made. |
| Corda Network Participant | A Legal Entity that has a Node on Corda Production or Pre-Production Network.  |
| Corda Network Rulebook | The rules, standards and policies governing activity within the Corda Network that are mandatory for all Corda Network participants, as adopted by Certificate Authority from time to time and provided to Participants. These rules include Allowable Identity names, Admissions Criteria and Revocation Criteria. Some of these rule derive from Corda Network Foundation. |
| Corda Network Services | Services delivered by Certificate Authority, including Identity Manager, Network Map and Notary services. |
| CorDapp | Software applications built on the Corda platform that may be used on the Corda Network. |
| Customer | A customer is a legal entity who has signed a Terms of Use with the Certificate Authority, for access to network and notary services. |
| Node Operator Email | When onboarding to Corda Network, customers will be required to designate a node operator email address on the node configuration file (“node.conf”). The Certificate Authority will use the designated email address for change management communications. |
| Production Corda Network | The Production Corda Network is a network and notary service operated by the Certificate Authority for Participants to perform live business transactions with other legal entities. It uses the Trust Root / PKI owned by the Corda Network Foundation. |
| Pre-Production Corda Network | The rules, standards and policies governing activity within the Corda Network that are mandatory for all Corda Network participants, as adopted by Certificate Authority from time to time and provided to Participants. These rules include Allowable Identity names, Admissions Criteria and Revocation Criteria. Some of these rule derive from Corda Network Foundation. |
| Sponsee | Any legal entity that is allowed to access the Corda Network and the Services as a Corda Network Participant but has not signed Terms of Use directly with the Certificate Authority. |

## Contents

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
- [3. Revocation Policy](#3-revocation-policy)
  - [3.1. Introduction](#31-introduction)
- [4. Amendments to Corda Network Rulebook](#4-amendments-to-corda-network-rulebook)
  

## 1. Admissions Criteria

## 1.1. Introduction

Participants, including Business Network Operators, must request a certificate from the Certificate Authority to gain access to and join Corda Network. 
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

Note: additional details may be required for Participation billing, but these requirements do not form part of this Policy.

The Certificate Authority has established a sanction review commensurate with jurisdictional laws and regulations on all entities. Positive matches will not receive a certificate for the network. Business Network Operators must perform their own KYC check and should not rely on the Certificate Authority's identification or sanction review. Business Network Operators are responsible for obtaining further documentation such as articles of incorporation, ultimate beneficial owners, etc. to verify identity and conduct appropriate due diligence checks (high risk industry analysis, high risk geographies, negative news checks) to ensure entities meet acceptable risk tolerance standards designed by the business network.

Certifications will be issued based on the information provided in the certification request. Any changes to information contained in the Participation Certificate, including updating the entity name or contact information, will require the certificate to be revoked and re-issued by the Certificate Authority.

## 1.3. Rationale

The Certificate Authority should obtain minimum information required for billing purposes and to confirm identity on the Corda Network. See below membership requirements for other foundations.

* SWIFT: The country risk (e.g. FATF versus non-FATF countries), affiliation of SWIFT Users to current member base, 
intended use of SWIFT products and services (e.g. the use by the (applicant) SWIFT User of the SWIFT financial messaging 
services for necessary and legitimate business purposes), applicable sanctions regulations, and credit worthiness of the 
applicant SWIFT User. Other requests: A certificate of incorporation, a tax certificate, an operating license, a 
declaration of ownership, a list of shareholders, a list of authorised signatures, the composition of the board and/or 
executives and audited accounts. * These requirements are too onerous for the Corda network. SWIFT is similar to a business network operator and all 
    SWIFT members have a common interest in a specific type of service. Corda users have vastly different interests and 
    uses so membership criteria should not be so stringent. It is worth noting that individual Business Network 
    Operators could choose to implement more stringent requirements, such as seen by SWIFT, if it so chooses.

* OPEC: Any country with a substantial net export of crude petroleum, which has fundamentally similar interests to 
those of Member Countries, may become a Full Member of the Organization, if accepted by a majority constituting 
three-fourths of Full Members, including the concurring votes of all Founder Members. * Centralized approval process not feasible for Corda Network design.

* ISO: When joining ISO, documents confirming the entity’s status as the organization most representative of 
standardization in the entity’s respective country, and that said country is recognized by the United Nations. * Corda network should only do business with UN recognized countries.

* ICANN: The name and contact information (including email address, physical address and contact phone number) for the 
domain's registrant, administrative and billing contacts. * This is practical for the Corda Network.  
    
 ## 1.4. Addendum

The Certificate Authority must use the following lists for all Participants joining the Corda Network: 

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

Any node on Corda Network must have a Distinguished Name (DN) or X.500 name in its [participation certificate](https://docs.corda.net/corda-network/index.html#identity-service). Legal names registered with the Corda Network Certificate Authority are to be submitted in the form of an X.500 name that must include 4 fields:

- Organisation (O)
- Organisation Unit (OU)
- Locality (L)
- Country (C)

X.500 names may include up to 6 fields (optional additional fields are State (S) and Common Name(CN)), explained in greater detail in section 1.2 below. Data fields in the X.500 name must be sorted in the order specified in the Corda protocol.

The entire X.500 name is used for the uniqueness check. For now, the maximum number of characters in the whole X.500 name (across all 6 fields) is **128 characters**.

## 2.2. Choosing X500 Name for your Node

The Certificate Authority must ensure all X.500 names meet the following requirements:

- Mandatory Organisation, Organisational-Unit, Locality and Country attributes are present.
- Organisation attribute represents a legal entity name, which is the beneficial owner of states on the ledger.
- The Country attribute is a valid ISO 3166-1 two letter code in upper-case.

Overall, the DN is one of the most common points of error in joining Corda Network, so take care to fill this out correctly. As part of standard onboarding checks for Corda Network, the Certificate Authority may verify that these details have been accurately populated and reject requests where the population of these fields does not appear to be correct.

For guidance on writing a legal entity name please see the table below:





| Field                      | Mandatory | Length (chars) | Validation                                                                                       | Purpose                                                                                                                                                                                                                                                                                                                                              |
|----------------------------|:---------:|---------------:|--------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Organisation (O)**       |     Y     |            110 | As per above, and additionally: No double-spacing. May not contain  stopwords like "node" or "server". | The O field for the legal entity defines the beneficial owner of states on the ledger. This should be set to the **legal name** of the organisation, as it appears on the official trade register within the jurisdiction in which the entity is registered. This is used to define the owning organisation of the node / certificate. More details provided in section 2.2.1.               |
| **Organisation Unit (OU)** |     Y     |             64 | As per above                                                                                     | This field is generally used to denote sub-divisions or units in the organisation (legal entity). It may be used by node operators for internal purposes to separate nodes used for different purposes by the same legal entity.                                                                                                                     |
| **Locality (L)**          |     Y     |             64 | As per above                                                                                     | The city or town in which the registered head-office of the legal entity is located. If the company operates from New York City but is registered in Wilmington, Delaware then please use Wilmington.                                                                                                                                                 |
| **Country (C)**            |     Y     |              2 | [2-digit ISO code](https://en.wikipedia.org/wiki/ISO_3166-2)                                                                                 | The country in which the registered head-office of the legal entity is located.                                                                                                                                                                                                                                                                      |
| **State (S)**              |     N     |             64 | As per above                                                                                     | If your country operates a State or Province system (e.g. USA and Canada) please add the State in which the registered head-office of the legal entity is located. Do not abbreviate. For example, "CA" is not a valid state name. "California" is correct. If the company operates from New York but is registered in Delaware, please use Delaware. |
| **Common Name (CN)**       |     N     |             64 | As per above                                                                                     | Available for use by the node operator for their own internal purposes. Often used for home website urls in www.                                                                                                                                                                                                                                     |

### 2.2.1. Selecting the Right Legal Entity for the Organisation Field

The Certificate Authority must ensure all X.500 names meet the following requirements:

According to Corda Network policy, the Legal Entity in the “O” field of the node’s X.500 name should be the owner of the assets to be transacted.

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

The free text fields in the X.500 name must obey the following constraints:

- Consist only of characters from the following Unicode code blocks: Basic Latin, Latin-1 Supplement, Latin Extended A, Latin Extended B. 
- Start with upper-case first letter. 
- May not not contain the null character.
- May not contain control characters.  
- Must have at least two characters. 
- Must be normalized to Unicode NFKC form. 
- May not include the following forbidden characters: , , = , $ , " , ' , \
- May not include trailing or leading whitespace. 
- Must be encoded using UTF-8. 

The following rules may cause rejection if sufficient justification is not provided. The definition of "sufficient justification" is up to the Certificate Authority and may be changed without notice:

- A stopword sequence is present.
- The name is not capitalised.

### 2.2.3. Stopwords

Stopwords are character sequences that may be the result of mistaken applications or intent to confuse. The  Certificate Authority may adjust the list of stopwords at any time. The Foundation may request a list of current or prior stopwords at any time.

Examples of likely stopwords:
1.	Corda
2.	R3
3.	Node
4.	Server
5.	Oracle (obviously this one is particularly special)
6.	Ã
7.	Â
8.	test (in Corda Network Production environment)

The first five are intended to avoid confusing node names or people creating names like "MegaCorp Corda Node" which would not be a valid legal name. The last two are intended to catch encoding mismatch errors. Cases where company names legitimately include stopwords will be handled via manual review.
The Corda Network uses Unicode version 6.2.

### 2.2.4. E-mail Contained in the *NodeConf* File

Before a node can be onboarded to Corda Network, the Certificate Authority needs a response from authenticated email address contained in the CSR to confirm that: 
- the email domain used in the node.conf is associated with the legal entity requesting the certificate; and
- the person submitting the CSR has access to the email inbox listed in the node.conf file. 

**Requirements for the e-mail address**

The email address used in the node.conf file will be used for communications with the node operator, including those involved in identity verification and for all future communication related to Corda Network. This is why it must be associated with the legal entity submitting the request, and be an actively monitored mailbox such as ‘admin@, ‘info@’ or ‘support’.

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
* Confusion attacks based on flipping text direction half way through a script that doesn't benefit from it, for 
instance try copying the following word out of this email and into a text editor or terminal:  Mega‮proC‏
You will find that it isn't quite what you expected.
* Varying Unicode canonicalization, for instance is the letter ü represented as a single character or as a u followed 
by the ¨ combining character? NFKC form provides an answer.
* Some common software is critically buggy when faced with characters outside the Basic Multilingual Plane. MySQL in 
particular does not support the full range of Unicode inside UTF-8 fields. You have to specify the column type as 
utf8mb4 instead. If you don't the non-BMP character and anything after it is silently truncated. This is not considered 
a bug by the MySQL developers and therefore does not get fixed.Facebook got hacked in this way.

It would imply a need to fully support complex scripts in end user apps, which may need to inter-operate with legacy mainframe 
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

## 2.4. Developer Notes

Handling international text is a remarkably difficult task, filled with pitfalls for new and experienced engineers 
alike. For best results follow these recommendations:
* Do not be tempted to perform "looks alike" conversion into ASCII when attempting to inter-operate with legacy systems. If you 
absolutely cannot upgrade a target system to be Unicode aware, use ? as a replacement character. Mapping extended 
Latin characters to characters that English speakers think look the same has caused people to kill each other by 
accident (the linked article is not a joke).
* Names on the Corda network should not be prepared for comparison using methods like toLowerCase() or toUpperCase() 
because some supported characters do not survive case round-tripping. For example the German letter ß converts to "SS" 
when upper-cased but, of course, "SS" converts to "ss" when lower-cased. Whilst making two pieces of text "human compares 
equal" by simply lower-casing or upper-casing is valid in English, in other languages some visual differences may be 
considered irrelevant yet not be removed by re-casing. A better approach is to use a java.text.Collator object, then 
call the setStrength method to determine how lax the match should be, and then check if the compare method returns zero.
* A Collator object should also be used to sort Corda names, for example if you wish to create an alphabetically sorted 
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

## 3. Revocation Policy

## 3.1. Introduction

Certificate Authority shall always seek to resolve any issues with regards to Participant’s Participation Certificate through negotiations and Certificate Revocation is considered as a measure of last resort.

Certificate Authority shall have the right at any time with immediate effect and without notice to: 

(i) suspend Participant’s access to the Corda Network and/or the Corda Network Services; 
(ii) terminate Participant’s access to to the Corda Network and/or the Corda Network Services; 
(iii) revoke Participant’s Participation Certificate if the Certificate Authority, acting reasonably, determines that:

1.	Participant has failed to pay any Fees specified in Terms of Use for a period of ninety (90) days following their due date;
2.	Participant is in material breach of Terms of Use and such breach is with reasonable efforts capable of being cured within thirty (30) days but has not been cured by Participant within thirty (30) days following notice from Certificate Authority of such breach;
3.	There is a threat or attack (including a denial of service attack) on, or a security risk to the Corda Network Services or Certificate Authority's IT Systems or other event that may create a risk to the Corda Network Services, Certificate Authority’s or any other party’s IT Systems, the Corda Network or Corda Network Participants (provided that Certificate Authority may only revoke Participant’s Participation Certificate if Certificate Authority reasonably suspects that such threat or attack eminates from Participant’s IT Systems);
4.	The Foundation or Certificate Authority reasonably suspects that Participant is 
4.1.	preparing to use, is using, or permitting the use of Corda Network or Corda Network Services for fraudulent or illegal activities, 
4.2.	is committing malicious behaviour;
4.3.	is distributing unlawful, harmful or threatening materials on the Network;
4.4.	or Participant is otherwise in violation of Applicable Law or its Terms of Use;
5.	Certificate Authority can no longer provide Corda Network Services to Participant or to the Corda Network Participants in general due to a change in Applicable Law or a request or requirement by a Governmental Authority that makes it unlawful for Certificate Authority to continue to perform its obligations under the Terms of Use (each, an “llegality”), and such Illegality is not mitigable through commercially reasonable steps;
6.	Foundation or Certificate Authority reasonably suspects that Participant has in any way, intentionally or unintentionally, misrepresented its, and/or its sponsee(s) identity;
7.	Participant has filed a voluntary petition in bankruptcy or other insolvency proceeding, (ii) an order for relief by any court in bankruptcy or other insolvency proceeding has been granted with respect to Participant, (iii) Participant has made a general assignment for the benefit of creditors, (iv) a receiver, trustee, liquidator, custodian or similar official has been appointed for Participant or its assets, or (v) an involuntary petition in bankruptcy or other insolvency proceeding has been filed against Participant;
8.	Participant is (i) unable to perform any material portion of its obligations under the Terms of Use due to a Force Majeure Event and (ii) unable to resume its performance of such obligations within 30 calendar days of such Force Majeure Event.
9.	The binding between the Participant and the Participant’s public key defined within the certificate is no longer considered valid. Examples of circumstances that invalidate the binding are:
9.1.	Identifying information or affiliation components of any names in the certificate becomes invalid;
9.2.	Privilege attributes asserted in the Participant’s certificate are reduced;
9.3.	There is reason to believe the Participant’s private key has been compromised; or
9.4.	The Participant or other authorised party (as defined in the CPS) asks for their certificate to be revoked.
10.	The Foundation or the Certificate Authority obtains evidence that the Participant’s certificate was misused;
11.	Participant has been listed on any of the sanctions list outlined in the Admission Criteria in Corda Network Rulebook;
12.	The Certificate Authority has terminated its legal agreement with the Participant;
13.	The Certificate Authority is made aware that the Participant’s certificate was not issued in accordance with the Foundation’s Certificate Policy or Certificate Authority’s Certification Practice Statement;
14.	The Certificate Authority's right to issue Participant certificates expires or is revoked or terminated by the Foundation, unless the Certificate Authority has made other arrangements
15.	Revocation is required by the Foundation’s Certificate Policy or Certificate Authority’s Certification Practice Statement;
16.	The Certificate Authority is made aware of a demonstrated or proven method that exposes the Participant’s Private Key to compromise, methods have been developed that can easily calculate it based on the Public Key (such as a [Debian weak key](http://wiki.debian.org/SSLkeys).
17.	Whenever any of the above circumstances occur, the associated certificate shall be revoked by the Certificate Authority and placed on the CRL. Revoked certificates shall be included on all new publications of the certificate status information until the certificates expire.
If Participant’s access to the Corda Network is terminated or Participant’s Participation Certificate is revoked, Participant shall be solely responsible for the transition of its assets, transactions and data from the Corda Network.  
Participant acknowledges and agrees that Certificate Authority may amend the terms outlined in Corda Network Rulebook.  Participant’s continued use of Corda Network Services after receipt of such a notice shall constitute Participant’s agreement to such amendment.

## 4. Amendments to Corda Network Rulebook

Please note that the content of this Corda Network Rulebook is subject to change.

