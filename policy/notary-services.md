|Corda Network Foundation|[Document history]({{ site.github.repository_url }}/blame/master/{{page.path}})|

Notary Services Policy
======================

This document defines required arrangements for the operation of Notary Services within the Corda Network.

1 Introduction
--------------
### 1.1 Definitions
The following definitions apply in the context of this document:

* **Notarisation** : Assertion, via cryptographic signature, that a given Corda transaction may be considered a final, 
immutable record within a Corda distributed ledger.
* **Notary Service** : A set of resources which, collectively and homogeneously, provide a mechanism for the 
notarisation of Corda transactions, and are authorised by the Foundation to do so. Generally composed of one or more 
Notaries (see below).
* **Notary** : A Corda node which, individually or in collaboration with other Corda nodes, provides a Notary Service
* **Notary Operator** : An entity which bears accountability for the operation of a Notary
* **Applicant** : An entity undertaking the process to become recognised as a Notary Operator
* **Participant** : A recognised operator of one or more Corda nodes on the network.
* **User** : Any Participant with a real or potential interest in the operation of a Notary Service, who would not be 
precluded from access under the conditions of service (see 2.4)

### 1.2 Motivation
Transaction notarisation is recognised as a core requirement for the operation of the Corda Network. By providing a 
basis for establishing the settlement finality of a transaction, notarisation enables business workflows including the 
exchange of assets cross the network; this, in turn, supports the mission of the Network to allow seamless communication 
between business partners.

The use of notarisation to enable the secure transfer of assets from one party to another is recognised as fundamental 
to many applications of the Corda Network. The design of Corda fundamentally ties the transferability of assets (as 
contract states), and thereby their economic value within the network, to the correct and reliable operation of the 
Notary Services to which they are linked.

The Foundation regards the long-term success of the Corda Network to be critically dependent upon the health, 
reliability and performance of the notary ecosystem. We believe the best way to achieve this is to encourage an open 
and competitive market in Notary Services, whilst applying sufficient governance to ensure Notary Services adhere to 
minimum standards. This document sets out the key elements of this governance.

### 1.3 Principles
This policy applies the following general principles:

1. Notary Operators must meet minimum criteria defined by the Foundation in order to provide a Notary Service.
2. Notary Operators must ensure Users are clearly informed of all limitations and implicit risks of using a given Notary 
Service, and any changes of these over time.
3. Participants must be conscious of the terms under which any Notary Service is provided before becoming Users of that 
Notary Service.

2 Policy Detail
---------------
### 2.1 Finality
In providing any judgment or opinion, the Foundation shall apply a general principle that notarised transactions (that 
is, cryptographically signed by a recognised Notary) shall be considered final, whereas un-notarised transactions shall 
be considered non-final.

Where there is a need for a Corda transaction to be considered final, it is incumbent on parties to that transaction to 
ensure it is submitted to an appropriate Notary Service for notarisation.

### 2.2 Organisation of Notary Services
A Notary Service may be operated either by a single Notary Operator, or by multiple Notary Operators operating 
collectively (e.g. via a collection of Notaries running a Byzantine Fault-Tolerant consensus algorithm).

Where a Notary Service is operated collectively by multiple Notary Operators, it is incumbent upon all those Notary 
Operators to:

* Ensure requests for notarisation return consistent, deterministic outcomes to Users, regardless of which Notary 
receives a notarisation request
* Define and maintain consistent Terms of Service (see 2.3) for all Notaries operating as part of the Notary Service
* Define and maintain appropriate mechanisms for collective governance (e.g. admission and removal of members, 
allocation of liability, fees, etc.)

### 2.3 Basic Standards
The Foundation shall provide a dedicated policy document setting out minimum criteria for Applicants, and the Notary 
Services they propose. These criteria form basic standards for the operation of Notary Services, covering areas such as:

* Financial and legal standing of Notary Operators
* Technical requirements for the proposed Notary Service, including provisions for data resilience
* Data protection and retention requirements
* Operational infrastructure and governance

The Foundation may change these criteria over time. Existing Notary Services may, as a result, be required by the 
Foundation to apply changes in order to comply with revised basic standards.

### 2.4 Terms of Service
Notary Operators shall define Terms of Service for any Notary Service(s) they operate.

At a minimum, Terms of Service shall include clear, explicit statements to cover the following:

* **Identification of Notary Operator(s)** including relevant contact information, trade registry reference numbers, 
legal status and regulated status for each Operator.
* **Type(s) of notarisation** (e.g. validating vs. non-validating) offered by the service.
* **Conditions of service** to be satisfied by both the User and any transaction(s) proposed in order for the service 
to be provided. These may include:
  * Applicable hours of operation.
  * Specific conditions under which service may be withheld (e.g. legal, regulatory constraints etc.).
  * **Data restrictions** : Data which Users are prohibited from sending to the Notary Service.
* Commitments to deliver a specific level of **performance**, specifying relevant metrics (e.g. throughput, notarisation 
latency etc.), and how they are measured.
* Commitments to ensure a specific level of **availability** (uptime) including provisions for planned and unplanned 
outages.
* **Charges** due to the Notary Operator(s) in exchange for notarisation services, and mechanisms for payment.
* **Acceptance of liability** for improper service, and division of liability between joint Notary Operators where 
applicable.
* **Dispute resolution** procedures, including means to contact the Notary Operator(s).
* **Compensation scheme(s)** applicable in the event of financial losses by a Participant due to improper service, and 
procedures for accessing scheme(s).
* **Disclosures** arrangements (see 2.5).
* **Data handling** : Treatment and arrangements for secure management of data provided to the Notary Service by Users.
* **Data retention** : Policy on the retention and deletion of data provided to the Notary Service by Users.
* **Geographical location**  of all resources (databases, servers etc.) making up the Notary Service, naming specific 
countries in which resources may reside. Where resources are distributed over more than one country, the division of 
resources across countries shall be unambiguously described.
* **Governing law** : Which set(s) of legislation shall be considered to govern the Terms of Service.
* Process for **changes to the Terms of Service**, including notice given to Participants and notification procedures.
* Process for **termination** of the Notary Service, including requirements for advance notice and migration, where 
relevant.

Where any of the above do not apply to a Notary Service, the Terms of Service shall include explicit statements to 
this effect.

A Notary Service may be provided to different Users under different Terms of Service, provided that Notary Operator(s) 
are able to demonstrate, without ambiguity, which Terms of Service apply to any given User at any point in time.

Notary Operators shall ensure Terms of Service are visible to any Participant who is a User of the Service, or may 
become so in future.

#### 2.4.1 User obligations
In providing any judgment or opinion, the Foundation shall consider usage of a Notary Service by a User to imply that 
acceptance by that User to the Terms of Service in effect at the time of usage. It is therefore incumbent on 
Participants to review and accept the Terms of Service prior to:

* Requesting notarisation from a Notary Service
* Entering into any transaction (via cryptographic signature) which would give rise to a dependency upon a Notary 
Service by that Participant

Participants may, through their use of a given CorDapp, delegate authority to that CorDapp to select Notary Services on 
their behalf. It is incumbent on Participants to determine the Notary Service selection behaviour of any CorDapp they 
use. Where a potential exists for a CorDapp to select one or more Notary Services on a behalf of a User, it is incumbent 
on the User to review and accept the Terms of Service for those Notary Services prior to using that CorDapp.

### 2.5 Creation of new Notary Services
The Foundation welcomes interest by all parties in the creation of new Notary Services as part of the Corda Network.

Creation of a new Notary Service shall be subject to review and approval by the Foundation. In principle, all 
applications to create a new Notary Service shall be reviewed without prejudice and approved subject to meeting the 
basic standards (see 2.3).

#### 2.5.1Application process
The Foundation shall provide a structured process for the processing of all applications to create a new Notary Service, 
wherein:

* Applicants shall be required to propose the Terms of Service under which the Notary Service is to be offered
* Applicants shall be required to demonstrate their ability to operate a Notary Service (a) in compliance with basic 
standards (see 2.4.1); (b) according to the proposed Terms of Service. This may require:
  * Submission of documentary evidence for review by the Foundation.
  * A technical audit of infrastructure provided by Notary Operators.
  * A business audit of Notary Operator organisations.
* Final decisions on the approval of an application shall be taken by the Foundation Board.
* Assuming approval of the application, a launch time for the new Notary Service shall be agreed between the Network 
Operator and Notary Operator(s).

Where one or more audits are deemed to be required as part of the application process, Applicants shall be required to 
engage an auditor approved by the Foundation. The cost of all such audits shall be borne by the Applicant(s).

### 2.6 Disclosures
Notary Operators are required to maintain transparency of changes in their status to their Users, such that Users may 
make informed decisions regarding their operational exposure to a Notary Service. The minimum set of required 
disclosures are described below.

#### 2.6.1 Advance disclosures
Notary Operators shall disclose the following to Users in advance of the fact:

* Any change to the Terms of Service applicable to those Users
* Intent to transfer operation of the Notary Service to another Notary Operator, or otherwise change the composition of 
Notary Operators operating the Notary Service
* Intent to discontinue the Notary Service
* Any other action with significant risk of impairing operation under the current Terms of Service

#### 2.6.2 Other disclosures
Notary Operators shall disclose the following to all Users:

* Any financial, legal or operational dependencies existing between joint Notary Operators, such that inability of a 
given Notary Operator to operate may affect the ability of another Notary Operator to maintain operation of their 
Notary(ies)
* Any change in the legal status of one or more Notary Operators
* Any change in the financial standing of one or more Notary Operators, including insolvency and/or bankruptcy
* Any event with significant risk of impairing operation of the Notary Service under the current Terms of Service
* Any breach of the data handling policy defined in the Terms of Service

Disclosures shall be made at the earliest practical opportunity. Where possible, all such disclosures shall be made in 
advance, and no later than 7 days after the event to be disclosed.

#### 2.6.3 Avoidance of disclosure conflicts
A Notary Operator shall avoid any action by which it may become unable to fulfill its disclosure obligations to Users, 
e.g. due to legal non-disclosure obligations.

### 2.7 Service monitoring
The Foundation may, at any time, require Notary Operators to provide evidence of:

* The accuracy of disclosures made to Users (or absence thereof; see 2.5)
* On-going ability to operate the Notary Service according to basic standards (see 2.4.1) and defined Terms of Service 
(see 2.4). This may require:
  * Submission of documentary evidence for review by the Foundation
  * A technical audit of infrastructure provided by Notary Operators
  * A business audit of Notary Operator organisations

Where one or more audits are deemed to be required in order to assemble such evidence, Notary Operators shall be 
required to engage an auditor approved by the Foundation. The cost of all such audits shall be borne by the Notary 
Operator(s).

### 2.8 Complaints
Participants may raise complaints to the Foundation at any time if they have reasonable cause to believe a Notary 
Service is not being operated in compliance with basic standards and/or Terms of Service.

The Foundation shall apply a structured process to the handling of complaints, wherein:

* All complaints received shall be reviewed without prejudice
* Complaints deemed of sufficient evidence and severity shall be subject to investigation
* Investigations may result in Notary Operators being required to demonstrate handling and on-going compliance

The Foundation shall make details of its complaints handling process available upon request.

### 2.9 Termination of Notary Services
Notary Operators may elect to discontinue provision of Notary Services where provision for such termination is given in 
the Terms of Service.

Subject to a Mandatory Governance Event (see the Corda Network Foundation Constitution), the Foundation may also, at any 
time, require Notary Operators to discontinue operation of the Notary Service. Such termination shall follow a review 
process in which justification for the Termination shall be provided to Notary Operators.

Except where otherwise stipulated by the Foundation, discontinuation of a Notary Service shall follow the process 
defined in the Terms of Service.