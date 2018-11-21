|Corda Network Foundation|[Document history]({{ site.github.repository_url }}/blame/master/{{page.path}})|

Information Classification Policy
=================================

1 Purpose
---------
The purpose of this policy is to ensure that all sensitive Corda Network Foundation information and systems are
appropriately classified, based on their importance to the Foundation.  
This classification must accurately reflect the
impact that might result from any information or system loss, corruption, misappropriation or unavailability.

2 Risks Addressed
-----------------
Inappropriately restrictive information classification may result in excessive costs for the protection of low value
information or systems, or loss of productivity as a result of an overly complex security regime.  Alternatively, absent
or inappropriately permissive information classification may expose the Foundation to unavailability, disclosure,
modification or loss of high-value information. Access controls will therefore be applied in a manner that con-siders
the Foundation’s contractual, legal and regulatory obligations and is appropriate to the sensitivity of the information
and systems under consideration.

3 Control Objectives
--------------------
The objectives of the controls mandated by this policy is to en-sure that:

* Information owners are aware of their responsibilities with regards to the classification, labelling, cataloguing and
protection of information and systems for which they are responsible.
* Foundation employees and associates are aware of their responsibilities with regards to the protection of information
and systems which they may create or to which they may be granted access.

4 Who Does This Policy Apply To?
--------------------------------
This policy applies to employees and contractors, consultants, temporaries, and other workers at the Foundation. This
group is referred to as “employees and associates” throughout this policy.

5 Scope
-------
The scope of this policy includes all information and systems used, developed or operated by, or on behalf of, the
Foundation.

6 Roles and responsibilities
----------------------------
### All Foundation employees and associates
All Foundation and its Operator's employees and associates must understand and abide by this policy. Some individuals 
have additional responsibilities as listed below.

### Information owners
Information or systems must be treated as information assets if the Foundation is sensitive to their loss,
unauthorised modification or disclosure.

All information assets must be under the care of a designated information owner. Where there is any confusion
regarding the ownership of an information asset, ownership will reside with the relevant departmental head.

Information owners are also responsible for maintaining the information asset catalogue (or more simply, “the
catalogue”) entries for all significant information assets under their ownership. The catalogue is a record of
information assets or groups of like information assets, along with important attributes such as their classification,
distribution list and retention periods.

All information owners are responsible for defining and maintaining the correct classification of information
assets under their care, recording that classification in the catalogue, and for communicating that classification to
users of those assets.

### Information Custodians
Information Owners may delegate day to day responsibilities for the protection of information assets to one or more
custodians. A custodian may also have delegated responsibilities for the definition and maintenance of the catalogue and
implementation of controls to protect assets according to their classification.

### Head of Compliance
The Head of Compliance will identify any specific classification requirements for assets maintained by the Foundation resulting from
specific legislation or regulation.

### Information Security Manager
The Information Security Manager is responsible for ensuring that any technical solutions to the protection of
classified assets meet the requirements of this policy, the Information Owner and the Head of Compliance.

The information Security Manager will define the classification of data retained for logging and incident response
purposes.

7 Mandatory Classification
--------------------------
### Confidentiality
All information assets must be classified according to their confidentiality. Confidentiality reflects the need to
restrict access to the information asset under consideration. The Foundation will use the following classifications for
confidentiality: public, internal, confidential and secret.

Care should be taken to avoid over-classification of assets. Information owners should think carefully before they
classify assets using the higher classification levels of “confidential” or “secret”.

### Public
Information assets must be classified as public if they have been approved for general external distribution.
Public information may include the Foundation website, blogs, or Open Source software and documentation.

### Internal
Information assets must be classified as internal if they should not be disclosed outside the Foundation but when
there is no requirement to restrict their distribution within the business. Internal is a classification generally used
for assets which would inconvenience or cause limited financial loss or reputational damage to the Foundation or its
clients if disclosed.

Internal assets include (but are not restricted to) intellectual property such as policies, procedures, designs or
source code.

Internal assets may be freely distributed within the Foundation.

Internal assets may be distributed to external organisations, subject to the approval of their information owner,
so long as appropriate confidentiality or non-disclosure agreements are in place with the recipient organisation.

### Confidential
Information assets must be classified as confidential where there is a need to restrict their distribution to a
limited group of Foundation employees and associates. Confidential is a classification signifying that loss, or
disclosure outside a restricted group, could result in significant harm to the Foundation.

The information owner is responsible for approving access on an individual basis for confidential assets.

Confidential assets must include a distribution list to ensure that their confidentiality is preserved. The
distribution list should be embedded as part of the asset (for example, a paragraph or table in a word document). If
this is not possible, the distribution list must be included in the asset’s catalogue entry or the catalogue entry for
the group to which the asset belongs.

Confidential assets may include (but are not restricted to) business plans, details of impending mergers or
acquisitions, accounting information and systems, payroll and compensation information, and sensitive customer
information.

Confidential assets may be distributed to named recipients in external organisations, subject to the approval of
the Information Owner. Appropriate confidentiality or non-disclosure agreements must be in place between the Foundation
and the recipient organisation before this may happen.

### Secret
Information assets must be classified as secret, where their confidentiality must be preserved under all
circumstances. Secret, as a classification, is used to restrict access to an information asset to a single individual,
or very small group of explicitly named individuals.

Secret is a classification most often reserved for assets, such as passwords, that are used to authenticate
parties in the context of privileged access to resources.

The information owner is responsible for approving access on an individual basis for confidential assets.

Secret assets must include a distribution list to ensure that their confidentiality may be preserved. The
distribution list should be embedded as part of the asset (for example, a paragraph in a word document). If this is not
possible the distribution list must be included in the asset’s catalogue entry.

Secret may be extended to describe assets that should not be made visible under any circumstances. Examples
include cryptographic key material such as certificate authority signing keys.

Secret information must not be distributed outside the Foundation.

8 Optional Classification
-------------------------
### Integrity
Information assets may be classified in terms of their integrity requirements. Integrity relates to the need to
protect an information asset against improper loss or modification.

Integrity classifications are defined as follows:

|Level|Category|General definition|
|-----|--------|------------------|
|1|No requirement/no impact|No business impact from loss|
|2|Significant/limited impact|Activities can be recovered from loss with zero or minimal business impact|
|3|Important/serious impact|Activities can be recovered from loss with short term impact|
|4|Critical/severe impact|Loss is unacceptable under all circumstances|

 
### Availability
Information assets may be classified in terms of their availability requirements. Availability relates to the need
to ensure that an information asset may be reliably accessed in a timely manner.

Availability classifications are defined as follows:

|Level|Category|General definition|
|-----|--------|------------------|
|1|No requirement / no impact|Maximum downtime 1 week. 1 day per month expected|
|2|Business hours / limited impact|Maximum downtime 1 day. 8 hours per month expected|
|3|Available / serious impact|Maximum downtime 1 hour, 1 hour per month expected|
|4|Highly available / severe impact|Maximum downtime 1 hour, 30 minutes per year expected|

### Classification modifiers
Classification modifiers may be used to add context to, and to elaborate upon, the three fundamental information
classifications of confidentiality, integrity or availability. They are principally used to provide further clarity on
confidentiality issues but can also supplement availability and integrity classifications. Classification modifiers
should be used only where appropriate.

Information assets must be tested against any classification modifiers that may apply to them in order to ensure
that use of the modifier is appropriate. Classification modifiers will generally apply to information assets such as
client information or personally identifiable information which have specific customer, legal or regulatory status. All
relevant classification modifiers should be applied; in the case of any conflict between modifiers, the highest
classification is held to apply.

Classification modifiers applying to Foundation information assets will change from time to time. Information on
currently applicable modifiers is maintained in the information security management pages in the Foundation wiki.

Classification modifiers are associated with a minimum confidentiality classification. For example, all
information that has a modifier of “PII” must be classified as “confidential”.

9 Guidelines for Cataloguing Information Assets
-----------------------------------------------
It may not be reasonably possible for an information owner to individually catalogue all information assets under
their control. Practical techniques, such as classifying and cataloguing groups of similar assets (such as shared
directories containing finance information, or password manager databases or groups of signing keys) may be used where
appropriate.

10 Guidelines for Labelling Information Assets
----------------------------------------------
All information assets should, where reasonably possible, be labelled with their confidentiality classification.
Where labelling is not practical, appropriate compensating controls must be put in place.

Information assets that are stored in a way that prevents their individual labelling (such as attributes of a
system or as database rows) must have a data catalogue entry that includes their classification.

Information assets are not required to be labelled with their integrity and availability classifications.

11 Guidelines for Handling Unclassified Information and Systems
---------------------------------------------------------------
Information or systems not defined as assets cannot be considered as classified.

Information assets that are not classified must be treated as confidential until they may be properly classified.

12 Compliance
-------------
Assessments may be carried out for compliance against this policy. Any violation of this policy will be investigated and
if the cause is found due to wilful disregard or negligence, it will be treated as a disciplinary offence. All
disciplinary proceedings are coordinated through the Human Resources Department. The Foundation reserves the right to
amend this policy at any time and will publish updated versions to all staff.