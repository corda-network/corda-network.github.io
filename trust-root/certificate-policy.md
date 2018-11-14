|Corda Network Foundation|[Document history]({{ site.github.repository_url }}/blame/master/{{page.path}})|

# Corda Network Certificate Policy

20th September 2018

# Document Classification

In current state, this document is classified PUBLIC.

# External Distribution

This document is made available for public examination and dissemination.

# 1 Introduction

This document is the Corda Network Certificate Policy. It is provided for internal R3 review purposes and for other 
stakeholders to assess the potential level of assurance provided by the Corda Network Certificate Authority.

As with all draft documents, this document is subject to change. In particular, clauses marked “no stipulation” are 
likely to be subject to frequent change as the document progresses from draft to release version.

For R3 employees, the document author should be your first point of contact for information or clarification regarding 
the contents of this document. For external organisations to whom this document has been released, you should contact 
your R3 representative if you have any questions.

This document does not modify existing agreements or obligations between R3 and other entities in any way.

## 1.1 Overview

The Corda Network is a distributed population of Corda nodes operated by autonomous network participants. Participants 
conduct various types of business through Corda Distributed Applications (CorDapps) running on those nodes. Such nodes 
(instances of the Corda software) conduct bilateral sessions authenticated via TLS and using standard PKIX technology. 
Each node is identified by means of an X509 certificate issued by an appointed Certificate Authority CA) for the 
network. CAs are appointed by the governing body of the Corda Network^1.

This document (‘the Corda Network Certificate Policy’) describes the policy for issue, management and revocation of 
X.509 certificates for participants of the Corda Network. Such certificates provide the basis of identity within the 
Corda Network and assert the uniqueness of individual nodes and the ownership of records those nodes contain. Each node 
is constrained to a single signing certificate and public/private key pair at the time of writing (sub-certificates are 
used for TLS and some other activities). It is important to note that CAs in the Corda Network are not the same as 
general internet CAs and should not be thought of as such. Corda has a much more constrained usage profile for 
certificates than a general internet certificate and also has specific protections built into its logic that work off 
the contents of the certificates.

This document has been derived from the NIST Draft Reference Certificate Policy NISTIR 7924 with modifications relevant 
to the specialised nature of the Corda Network Certificate Authority.

To ease review, we have maintained a standard structure and terminology for this document based on NIST publications. 
Corda Network Participants (node operators) are equivalent to both ‘subscribers’ and ‘relying parties’ in NIST 
terminology.

The Corda Network will comprise many sub-groups or ‘business networks’ of participants running particular CorDapps for 
particular use cases and such groups will often have a co-ordinating party (the ‘Business Network Operator’) who 
manages the distribution of the app and rules for its use. Such Business Network Operators may fulfil the role of 
‘Registration Authority’ in the Corda Network.

This Certificate Policy is owned and maintained by the Policy Authority of the Corda Network Foundation.

## 1.2 Name and Identification

This document is the Corda Network Certificate Policy (CP). It is the principal statement of policy governing the Corda 
Network PKI. The Corda Network PKI’s primary function is to support identity assurance between subscribers engaging in 
transactions of legal and financial significance within the Corda Network.

An enterprise number for R3 has been requested from IANA. Future versions of this document will include the R3 OID used 
for the purposes of identifying this CP.

(^1) The Corda Network is currently governed and operated by R3, but governance activities will be handed over to an 
independent and representative Foundation once the network has reached a threshold size.

## 1.3 PKI Participants

The following categories of PKI participants are defined in the sections that follow:

* Certificate Authorities
* Registration Authorities
* Subscribers – Corda network participants issued with a certificate by the Corda Network Operator.
* Relying Parties – Corda network participants that act in reliance on a Corda Network Operator issued certificate to 
verify a digital signature and or decrypt an encrypted document or message from other participants.

This section identifies roles that are relevant to the administration and operation of CAs under this policy.

### 1.3.1 Certificate Authority

The CA is the collection of hardware, software and operating personnel that create, sign, and issue public key 
certificates to subscribers. The CA is responsible for issuing and managing certificates including:

* Approving the issuance of all certificates, including those issued to subordinate CAs and RAs;
* Publication of certificates;
* Revocation of certificates;
* Generation and destruction of CA signing keys;
* Establishing and maintaining the CA system;
* Establishing and maintaining the Certificate Policy (CP) & Certification Practice Statement (CPS); _and_
* Ensuring that all aspects of the CA services, operations, and infrastructure related to certificates issued under the 
CP are performed in accordance with the requirements, representations, and warranties of the CP.

### 1.3.2 Registration Authorities

The registration authorities (RAs) collect and verify each subscriber’s identity and information that is to be entered 
into the subscriber’s public key certificate. The RA performs its function in accordance with a CPS approved by the 
Policy Authority. The RA is responsible for:

* The registration process; and
* The identification and authentication process.

### 1.3.3 Trusted Agents

The trusted agent is a person who satisfies all the appointment requirements for an RA and who performs identity 
proofing as a proxy for the RA. The trusted agent records information from and verifies presented credentials for an 
applicant’s identity on behalf of the RA. The CPS will identify the parties responsible for providing such services, 
and the mechanisms for determining their trustworthiness.

### 1.3.4 Subscribers

In the Corda Network PKI, a subscriber is an individual or organization that is capable of using and authorized to use 
the private key corresponding to the public key listed in a Corda Network certificate, and that: (1) is named in a 
certificate’s “subject” field and (2) has agreed to the terms of a subscriber agreement with the Corda Network 
Foundation and: (3) asserts the use of the key and certificate in accordance with any certificate policy asserted in 
the certificate.

In a Corda network, certificates issued to subscribers will also grant those subscribers the ability to further issue 
certificates that can be used in a specific, constrained way within that Corda network. These certificates can be used 
to represent that entity only and therefore, for the purposes of this policy, do not confer CA status upon the subscriber.

### 1.3.5 Relying Parties

A Relying Party is an entity that relies on the validity of the binding of the Subscriber’s name to a public key. The 
Relying Party uses a Subscriber’s certificate to verify or establish the identity and status of a system or device. A 
Relying Party is responsible for deciding whether or how to check the validity of the certificate by checking the 
appropriate certificate status information. A Relying Party may use information in the certificate to determine the 
suitability of the certificate for a particular use.

### Network Participants

As all entities in the Corda Network other than CAs or RAs will be both subscribers and relying parties, this policy 
often uses the term “network participant”, or more simply, “participant” to refer to those entities. Where a 
distinction is required, this policy will return to the more standard nomenclature present in the NIST reference CP 
(on which it is based).

## 1.4 Certificate Usage

### 1.4.1 Appropriate Certificate Uses

Certificates issued by the Corda Network CA will be used to further generate certificates for authenticated peer-to-peer 
messaging across The Corda Network, in addition to certificates for use in individual transactions.

### 1.4.2 Prohibited Certificate Uses

No stipulation.

## 1.5 Policy Administration

### 1.5.1 Organization Administering the Document

The Policy Authority of the Corda Network Foundation (the “Policy Authority”) is responsible for all aspects of this CP.

### 1.5.2 Contact Person

The Policy Authority can be contacted at: Information Security Team security@r3.com

### 1.5.3 Person Determining CPS Suitability for the Policy

The Policy Authority shall approve the CPS for each CA that issues certificates under the policy.

### 1.5.4 CPS Approval Procedures

CAs issuing under the policy are required to meet all facets of the policy. The Policy Authority shall work with a CA 
to minimize the use of waivers.

The Policy Authority shall make the determination that a CPS complies with the policy. The CA and RA must meet all 
requirements of an approved CPS before commencing operations. The Policy Authority will make this determination based 
on the nature of the system function, the type of communications, or the operating environment.

In each case, the determination of suitability shall be based on an independent compliance auditor’s results and 
recommendations. See section 8 for further details.

## 1.6 Definitions and Acronyms

See appendix A

# 2 Publication and Repository Responsibilities

## 2.1 Repositories
All CAs that issue certificates under this policy are obliged to post all CA certificates issued by or to the CA and 
CRLs issued by the CA in a repository that is accessible to Corda Network participants.

CAs are **not** required to post all certificates issued to Corda Network participants to a central repository.

## 2.2 Publication of Certification Information

### 2.2.1 Publication of Certificates and Certificate Status

The repository system shall be designed and implemented so as to provide 99% availability overall and limit scheduled 
down-time to 0.5% annually. Where applicable, the certificate status server (CSS) shall be designed and implemented so 
as to provide 99% availability overall and limit scheduled down-time to 0.5% annually.

### 2.2.2 Publication of CA Information

The CP shall be available to subscribers. The CPS of the CA may also be published; a CPS summary shall either be 
publicly available or available upon request.

## 2.3 Time or Frequency of Publication

An updated version of the CP will be made publicly available within thirty days of the incorporation of changes.

## 2.4 Access Controls on Repositories

The CA shall protect information not intended for public dissemination or modification. CA certificates and CRLs in the 
repository shall be available to Corda Network participants. Direct and/or remote access to other information in the CA 
repositories shall be determined by Policy Authority. The CPS shall detail what information in the repository shall be 
exempt from automatic availability and to whom, and under which conditions the restricted information may be made 
available.

# 3 Identification and Authentication

## 3.1 Naming

### 3.1.1 Types of Names

The CA shall assign an X.50 0 Distinguished Name (DN) to each subscriber.

### 3.1.2 Need for Names to Be Meaningful

Names used in certificates must represent an unambiguous identifier for the subject. Names should be meaningful enough 
for a human to identify the named entity, irrespective of whether the entity is a person, machine, or process. 
Interpreting the name semantic may require a reference database (e.g. human resources directory or inventory catalogue) 
external to the PKI.

### 3.1.3 Anonymity or Pseudonymity of Subscribers

The CA shall not issue anonymous or pseudonymous certificates.

### 3.1.4 Rules for Interpreting Various Name Forms

No stipulation.

### 3.1.5 Uniqueness of Names

The CA must ensure that each of its subscribers is identifiable by a unique name. Each X.500 DN assigned to a subscriber 
by a CA (i.e., in that CA's namespace) must identify that subscriber uniquely.

The CPS shall identify the method for the assignment of unique subject names.

### 3.1.6 Recognition, Authentication, and Role of Trademarks

The Corda Network is currently targeted at organisational applications, and therefore subscribers will therefore, at 
least in the initial life of the network, be associated with an organization, legal entity name, trade name or trademark.

For organizational subscribers, the CA must ensure that the X.500 DN of any subscriber certificate issued accurately 
reflects the legal entity name of the subscriber as recorded in the applicable local registry.

## 3.2 Initial Identity Validation

### 3.2.1 Method to Prove Possession of Private Key

In all cases where the party named in a certificate generates its own keys, that party shall be required to prove 
possession of the private key, which corresponds to the public key in the certificate request.

### 3.2.2 Authentication of Organization Identity

Requests for CA certificates shall include the CA name, address, and documentation of the existence of the CA. Before 
issuing CA certificates, an authority for the issuing CA shall verify the information, in addition to the authenticity 
of the requesting representative and the representative’s authorization to act in the name of the CA.

For subscriber certificates, the CA shall verify the existence of the organization by verifying the identity and address 
of the organization and that the address is the subscriber’s address of existence or operation. The CA shall verify the 
identity and address of the subscriber using documentation provided by, or through communication with, at least one of 
the following:

* Official communication with the organization;
* A third-party database that is periodically updated and considered a reliable data source; _or_
* A site visit by the CA or a third party who is acting as an agent for the CA.

The CA may use the same documentation or communication described in above to verify both the subscriber’s identity and 
address.

### 3.2.3 Authentication of Individual Identity

The Corda Network is currently targeted at organisational applications, and as such this policy does not currently 
stipulate requirements to authenticate individual identities. It is recognised that this may change in the future and 
that use cases involving individual identities will result in revisions to this policy.

#### 3.2.3.1 Authentication of Human Subscribers

No stipulation

#### 3.2.3.2 Authentication of Devices

No stipulation

#### 3.2.3.3 Authentication of Applications or Services

No stipulation

#### 3.2.3.4 Authentication for Role Certificates

No stipulation.

#### 3.2.3.5 Authentication for Code Signing Certificates

No stipulation

### 3.2.4 Non-Verified Subscriber Information

Information that is not verified shall not be included in certificates.

### 3.2.5 Validation of Authority

Before issuing CA certificates or signature certificates that assert organizational authority, including certificates 
for Corda Network participants, the CA shall validate the subscriber’s authority to act in the name of the organization.

The most prevalent certificates that assert organizational authority within the Corda Network are Corda node 
certificates.

### 3.2.6 Criteria for Interoperation

No stipulation

## 3.3 Identification and Authentication for Re-key Requests

### 3.3.1 Identification and Authentication for Routine Requests

In the event of a routine re-key, issuance of a new certificate shall always require that the party go through the 
initial registration process per Section 3.2 above.

### 3.3.2 Identification and Authentication for Re-key after Revocation

In the event of certificate revocation, issuance of a new certificate shall always require that the party go through 
the initial registration process per Section 3.2 above.

## 3.4 Identification and Authentication for Revocation Request

Revocation requests must be authenticated.

# 4 Certificate Life-Cycle Operational Requirements

## 4.1 Certificate Application

The Certificate application process must provide sufficient information to:

* Establish the applicant’s authorization (by the subscriber or sponsoring organization) to obtain a certificate. (per 
Section 3.2.3);
* Establish and record identity of the applicant. (per Section 3.2.3);
* Obtain the subscriber’s Corda node public key from the applicant and verify the applicant’s possession of the private 
key for each certificate required. (per Section 3.2.1); _and_
* Verify any other information requested for inclusion in the certificate.

These steps may be performed in any order that is convenient for the CA and applicants that does not compromise 
security, but all must be completed before certificate issuance.

### 4.1.1 Who can Submit a Certificate Application?

A certificate application may be submitted to the CA by the Subscriber authorised organisational representative (AOR), 
or an RA on behalf of the Subscriber.

### 4.1.2 Enrolment Process and Responsibilities

All communications among PKI Authorities supporting the certificate application and issuance process shall be 
authenticated and protected from modification; any electronic transmission of shared secrets and personally 
identifiable information shall be protected. Communications may be electronic or out-of-band.

Where electronic communications are used, cryptographic mechanisms commensurate with the strength of the public/private 
key pair shall be used. Out-of-band communications shall protect the confidentiality and integrity of the data.

Subscribers are responsible for providing accurate information on their certificate applications.

## 4.2 Certificate Application Processing

Information in certificate applications must be verified as accurate before certificates are issued.
Procedures to verify information in certificate applications shall be specified in the CPS.

### 4.2.1 Performing Identification and Authentication Functions

The identification and authentication of the subscriber must meet the requirements specified for subscriber 
authentication as specified in Sections 3.2 and 3.3. The components of the PKI (e.g., CA or RA) that are responsible for 
authenticating the subscriber’s identity in each case must be identified in the CPS.

### 4.2.2 Approval or Rejection of Certificate Applications

Any certificate application that is received by a CA under this policy, for which the identity and authorization of the 
applicant has been validated, will be duly processed. However, the CA must reject any application for which such 
validation cannot be completed, or when the CA has cause to lack confidence in the application or certification process.

### 4.2.3 Time to Process Certificate Applications

No stipulation.

## 4.3 Certificate Issuance


### 4.3.1 CA Actions during Certificate Issuance

Upon receiving the request, the CAs/RAs will:

* Verify the identity of the requester as specified in Section 3.2;
* Verify the authority of the requester and the integrity of the information in the certificate request as specified in 
Section 4.1;
* Build and sign a certificate if all certificate requirements have been met (in the case of an RA, arrange for the CA 
to sign the certificate); _and_
* Make the certificate available to the subscriber after confirming that the subscriber has formally acknowledged their 
obligations as described in Section 9.6.3.

The certificate request may already contain a certificate built by either the RA or the subscriber. This certificate 
will not be signed until all verifications and modifications, if any, have been completed to the CA’s satisfaction.

All authorization and other attribute information received from a prospective subscriber shall be verified before 
inclusion in a certificate. The responsibility for verifying prospective subscriber data shall be described in a CA’s 
CPS.

### 4.3.2 Notification to Subscriber by the CA of Issuance of Certificate

CAs operating under this policy shall inform the subscriber (or other certificate subject) of the creation of a 
certificate and make the certificate available to the subscriber. For Corda nodes, the CA shall issue the certificate 
according to the certificate requesting protocol used by the node (this may be automated) and, if the protocol does not 
provide inherent notification, also notify the AOR of the issuance (this may be in batch).

## 4.4 Certificate Acceptance

Before a subscriber can make effective use of its private key, the CA shall explain to the subscriber its 
responsibilities and obtain the subscriber’s acknowledgement, as defined in Section 9.6.3.

### Conduct Constituting Certificate Acceptance

Failure to object to the certificate or its contents shall constitute acceptance of the certificate.

###4.4.2 Publication of the Certificate by the CA

As specified in Section 2.1, all CA certificates shall be published in repositories.

This policy makes no stipulation regarding publication of subscriber certificates.

### 4.4.3 Notification of Certificate Issuance by the CA to Other Entities

The Policy Authority must be notified whenever a CA operating under this policy issues a CA certificate.

## 4.5 Key Pair and Certificate Usage

### 4.5.1 Subscriber Private Key and Certificate Usage

The intended scope of usage for a private key is specified though certificate extensions, including the key usage 
extensions, in the associated certificate.

### 4.5.2 Relying Party Public Key and Certificate Usage

Certificates may specify restrictions on use though critical certificate extensions, including the basic constraints and 
key usage extensions. All CAs operating under this policy shall issue CRLs specifying the current status of all unexpired 
certificates except for OCSP responder certificates. It is recommended that relying parties process and comply with this 
information whenever using certificates in a transaction.

### 4.6 Certificate Renewal

Renewing a certificate means creating a new certificate with the same name, key, and other information as the old one, 
but with a new, extended validity period and a new serial number.

### 4.6.1 Circumstance for Certificate Renewal

No stipulation.

### 4.6.2 Who May Request Renewal

No stipulation.

### 4.6.3 Processing Certificate Renewal Requests

No stipulation

### 4.6.4 Notification of New Certificate Issuance to Subscriber

No stipulation

### 4.6.5 Conduct Constituting Acceptance of a Renewal Certificate

No stipulation

### 4.6.6 Publication of the Renewal Certificate by the CA

No Stipulation.

### 4.6.7 Notification of Certificate Issuance by the CA to Other Entities

No stipulation.

### 4.7 Certificate Re-key

Re-keying a certificate consists of creating new certificates with a different public key (and serial number) while 
retaining the remaining contents of the old certificate that describe the subject. The new certificate may be assigned 
a different validity period, key identifiers, specify a different CRL distribution point, and/or be signed with a 
different key. Re-key of a certificate does not require a change to the _subjectName_ and does not violate the 
requirement for name uniqueness. The old certificate may or may not be revoked, but must not be further re-keyed, 
renewed, or modified.

Certificate re-keying is not supported. Any re-key request will be treated as a new certificate issuance request.

### 4.7.1 Circumstance for Certificate Re-Key

No stipulation

### 4.7.2 Who May Request Certification of a New Public Key

No stipulation

### 4.7.3 Processing Certificate Re-Keying Requests

No stipulation

### 4.7.4 Notification of New Certificate Issuance to Subscriber

No stipulation.

### 4.7.5 Conduct Constituting Acceptance of a Re-Keyed Certificate

No stipulation.

### 4.7.6 Publication of the Re-Keyed Certificate by the CA

No stipulation.

### 4.7.7 Notification of Certificate Issuance by the CA to Other Entities

No stipulation.

## 4.8 Certificate Modification

Modifying a certificate means creating a new certificate that has the same or a different key and a different serial number, and that differs in one or more other fields from the old certificate. The old certificate may or may not be revoked, but must not be further re-keyed, renewed, or modified.

Modification of previously issued certificates is not supported. Any request for modification will be treated as a new certificate issuance request.

### 4.8.1 Circumstance for Certificate Modification

No stipulation.

### 4.8.2 Who May Request Certificate Modification

No stipulation.

### 4.8.3 Processing Certificate Modification Requests

No stipulation.

### 4.8.4 Notification of New Certificate Issuance to Subscriber

No stipulation.

### 4.8.5 Conduct Constituting Acceptance of Modified Certificate

No stipulation.

### 4.8.6 Publication of the Modified Certificate by the CA

No stipulation.

### 4.8.7 Notification of Certificate Issuance by the CA to Other Entities

No stipulation.

## 4.9 Certificate Revocation and Suspension

Certificate Revocation in the Corda Network is still being finalised and aspects could change in the future. In particular it is likely that revocation of Corda Nodes could be implemented by an entirely separate mechanism to the Certificate Revocation List (CRL) facility provided by X. certificates.

CAs operating under this policy shall issue CRLs covering all unexpired certificates issued under this policy except for OCSP responder.

CAs operating under this policy shall make public a description of how to obtain revocation information for the certificates they publish, and an explanation of the consequences of using dated revocation information. This information shall be given to subscribers during certificate request or issuance and shall be readily available to any potential relying party.

Revocation requests must be authenticated. See Section 3.2 for more details.

Certificate suspension is not allowed by this policy.

### 4.9.1 Circumstances for Revocation

A certificate shall be revoked when the binding between the subject and the subject’s public key defined within the certificate is no longer considered valid. Examples of circumstances that invalidate the binding are:

* Identifying information or affiliation components of any names in the certificate becomes invalid:
* Privilege attributes asserted in the subscriber’s certificate are reduced;
* The subscriber can be shown to have violated the stipulations of its subscriber agreement;
* There is reason to believe the private key has been compromised; _or_
* The subscriber or other authorized party (as defined in the CPS) asks for his/her certificate to be revoked.

Whenever any of the above circumstances occur, the associated certificate shall be revoked and placed on the CRL. Revoked certificates shall be included on all new publications of the certificate status information until the certificates expire.

### 4.9.2 Who Can Request Revocation

Within the the Corda Network, a CA may summarily revoke certificates within its domain. A written notice and brief explanation for the revocation shall subsequently be provided to the subscriber. The RA can request the revocation of a subscriber’s certificate on behalf of any authorized party as specified in the CPS.

A subscriber may request that its own certificate be revoked. The AOR of the organization that owns or controls a device can request the revocation of the device’s certificate. Other authorized individuals of the organization may request revocation as described in the CPS.

### 4.9.3 Procedure for Revocation Request

A request to revoke a certificate shall identify the certificate to be revoked, explain the reason for revocation, and allow the request to be authenticated (e.g., digitally or manually signed). The steps involved in the process of requesting a certification revocation are detailed in the CPS.

### 4.9.4 Revocation Request Grace Period

There is no grace period for revocation under this policy.

### 4.9.5 Time within which CA must Process the Revocation Request

CAs will revoke certificates as quickly as practical upon receipt of a proper revocation request. Revocation requests shall be processed before the next CRL is published, excepting those requests received within two hours of CRL issuance.

### 4.9.6 Revocation Checking Requirements for Relying Parties

No stipulation.

### 4.9.7 CRL Issuance Frequency

CRLs shall be issued periodically per the CPS. Certificate status information may be issued more frequently than the issuance frequency described below. Certificate status information shall be published no later than the next scheduled update. This will facilitate the local caching of certificate status information for off-line or remote (laptop) operation.

CAs that issue certificates to subscribers or operate on-line must issue on a defined cycle.

Circumstances related to emergency CRL issuance are specified in section 4.9.12.

### 4.9.8 Maximum Latency for CRLs

CRLs shall be published within 4 hours of generation. Furthermore, each CRL shall be published no later than the time specified in the _nextUpdate_ field of the previously issued CRL for same scope.

### 4.9.9 On-Line Revocation/Status Checking Availability

Where on-line status is supported, status information must be updated and available to relying parties within a defined period after CRL publication.

### 4.9.10 On-line Revocation Checking Requirements

Relying party client software may optionally support on-line status checking. Client software using on-line status checking need not obtain or process CRLs.

### 4.9.11 Other Forms of revocation Advertisements Available

A CA may also use other methods to publicize the certificates it has revoked. Any alternative method must meet the following requirements:

* The alternative method must be described in the CA’s approved CPS;
* The alternative method must provide authentication and integrity services commensurate
 with the assurance level of the certificate being verified;
* The alternative method must meet the issuance and latency requirements for CRLs stated in Sections 4.9.7 and 4.9.8; _and_
* Components involved in creation of revocation information including providing authentication and integrity services must meet the security requirements for CSS as stated in this CP.

### 4.9.12 Special Requirements Related to Key Compromise

Certificate revocation for reason of key compromise must appear in a published CRL (or OCSP
response) within an agreed time period of the decisions to revoke.

### 4.9.13 Circumstances for Suspension

Suspension of certificates is not supported.

#### 4.9.13.1 Circumstances for Suspension

No stipulation.

#### 4.9.13.2 Who Can Request Suspension

No stipulation.

#### 4.9.13.3 Procedure for Suspension Request

No stipulation.

#### 4.9.13.4 Limits on Suspension Period

No stipulation.

#### 4.9.13.5 Circumstances for Restoration

No stipulation.

#### 4.9.13.6 Who Can Request Restoration

No stipulation.

#### 4.9.13.7 Procedure for Restoration Request

No stipulation.

## 4.10 Certificate Status Services

A CRL repository may be provided which can be leveraged to validate revocation of a certificate.

## 4.11 End of Subscription

No stipulation

## 4.12 Key Escrow and Recovery

Escrow of private keys is not supported.

### 4.12.1 Key Escrow and Recovery Policy and Practices

No stipulation

### 4.12.2 Session Key Encapsulation and Recovery Policy and Practices

Session key encapsulation and recovery is not supported

# 5 Facility, Management, and Operational Controls

**Note to reviewer:** This section is adopted mostly unchanged from NISTIR 7924, and it intended to apply to all current and future Corda Network Operators.

## 5.1 Physical Controls

All CA and RA equipment, including cryptographic modules, shall be protected from theft, loss, and unauthorized access at all times. Unauthorized use of CA and RA equipment is prohibited. CA equipment shall be dedicated to performing CA functions. RA equipment shall be operated to ensure that the equipment meets all physical controls at all times.

### 5.1.1 Site Location and Construction

The location and construction of the facility housing the CA equipment, as well as sites housing remote workstations used to administer the CAs, shall be consistent with facilities used to house high-value, sensitive information. The site location and construction, when combined with other physical security protection mechanisms such as guards, high security locks, and intrusion sensors, shall provide robust protection against unauthorized access to the CA equipment and records.

### 5.1.2 Physical Access

##### 5.1.2.1 Physical Access for CA Equipment

Physical access to CA equipment shall be limited to CA Operations Staff and Security Auditors. The security mechanisms shall be commensurate with the level of threat in the equipment environment.

At a minimum, physical access controls for CA equipment and all copies of the CA cryptographic module shall meet the following requirements:

* Ensure that no unauthorized access to the hardware is permitted;
* Be manually or electronically monitored for unauthorized intrusion at all times;
* Ensure an access log is maintained and inspected periodically;
* Mandate at least two-person access requirements. At least one individual shall be a mem ber of the CA Operations Staff. Technical or mechanical mechanisms (e.g., dual locks) should be used to enforce the two-person physical access control; _and_
* Other individuals shall be escorted by CA operations staff. This includes maintenance personnel. All individuals shall be recorded in the access log.

When not in use, removable CA cryptographic modules, removable media, and any activation information used to access or enable CA cryptographic modules or CA equipment, or paper containing sensitive plain-text information, shall be placed in locked containers sufficient for housing equipment and information commensurate with the sensitivity, or value, of the information being protected by the certificates issued by the CA. Access to the contents of the locked containers shall be restricted to individuals holding CA trusted roles as defined in Section 5.2.1, utilizing two-person access controls, and two-person integrity while the container is unlocked.

CA cryptographic modules held within the work area for intermittent use throughout the day may be kept under one lock, as long as they are stored in an area where there are at least two persons physically present at all times. Knowledge of the combination or access to the key used to secure the lock shall be restricted to authorized individuals only. When in active use, the cryptographic module shall be locked into the system or container (rack, reader, server, etc.) using a physical lock under the control of the CA Operations Staff to prevent unauthorized removal.

Any activation information used to access or enable the cryptographic modules or CA equipment shall be stored separately from the associated modules and equipment. Such information shall either be memorized or recorded and stored in a manner commensurate with the security afforded the associated cryptographic module or equipment. Where activation information is split across multiple materials in the custody of separate, named individuals, single person access controls and integrity provision per storage location is sufficient.

A security check of the room/rack housing CA equipment shall occur prior to leaving the room/rack unattended by the CA Operations Staff. The check shall verify the following:

* The equipment is in a state appropriate to the current mode of operation (e.g., that cryptographic modules are in
place when “open”, and secured when “closed”);
* Any security containers are properly secured;
* Physical security systems (e.g., door locks, vent covers) are functioning properly; _and_
* The area is secured against unauthorized access.

If unattended, the facility housing CA equipment should be protected by an intrusion detection system (IDS).

If a facility is not continuously attended and does not include an IDS, regular checks must be made to ensure that no attempts to defeat the physical security mechanisms have been made. A person or group of persons shall be made explicitly responsible for making such checks. When a group of persons are responsible, a log identifying the person performing a check at each instance shall be maintained. The last person to depart shall initial a sign-out sheet that indicates the date and time, and asserts that all necessary physical protection mechanisms are in place and activated.

#### 5.1.2.2 Physical Access for RA Equipment

RA equipment shall be protected from unauthorized access.

Any activation information used to access or enable the RA equipment shall be stored separately from the associated modules and equipment. Such information shall either be memorized or recorded and stored in a manner commensurate with the security afforded any associated cryptographic module or equipment.

#### 5.1.2.3 Physical Access for CSS Equipment

Physical access control requirements for CSS equipment (if implemented), shall meet the CA physical access requirements specified in Section 5.1.2.1.

### 5.1.3 Power and Air Conditioning

The CA shall have backup power capability sufficient to lock out input, finish any pending actions, and record the state of the equipment automatically before lack of power or air conditioning causes a shutdown. The repositories (containing CA certificates and CRLs) shall be provided with uninterrupted power sufficient a defined period of operation in the absence of commercial power, to maintain availability and avoid denial of service.

### 5.1.4 Water Exposures

CA equipment shall be installed such that it is not in danger of exposure to water (e.g., on tables, or elevated floors).

Potential water damage from fire prevention and protection measures (e.g., sprinkler systems) excluded from this requirement.

### 5.1.5 Fire Prevention and Protection

No stipulation.

### 5.1.6 Media Storage

Media shall be stored so as to protect it from accidental damage (water, fire, electromagnetic) and unauthorized physical access. Media not required for daily operation or not required by policy to remain with the CA or RA, that contains security audit, archive, or backup information shall be stored securely in a location separate from the CA or RA equipment.

Media containing private key material shall be handled, packaged, and stored in a manner compliant with the requirements for the sensitivity level of the information it protects or provides access. Storage protection of CA and RA private key material shall be consistent with stipulations in Section 5.1.2.

### 5.1.7 Waste Disposal

CA and RA Operations Staff shall remove and destroy normal office waste in accordance with local policy. Media used to collect or transmit privacy information shall be destroyed, such that the information is unrecoverable, prior to disposal. Sensitive media and paper shall be destroyed in accordance with the applicable policy for destruction of such material.

Appropriate procedures for the secure destruction of media and documentation containing sensitive information, such as private key material, must be developed and included in the CA or RA CSP.

### 5.1.8 Off-Site Backup

A system backup shall be made when a CA system is activated. If the CA system is operational for more than a week, backups shall be made at least once per week **or whenever changes are made to the CA system**. Backups shall be stored offsite. Only the latest backup needs to be retained. The backup shall be stored at a site with physical and procedural controls commensurate to that of the operational CA system.

## 5.2 Procedural Controls

### 5.2.1 Trusted Roles

A trusted role is one whose incumbent performs functions that can introduce security problems if not carried out properly, whether accidentally or maliciously. It is essential that the people selected to fill these roles shall be held accountable to perform designated actions correctly or the integrity of the CA is weakened. The functions performed in these roles form the basis trust in the CA. Two approaches are taken to increase the likelihood that these roles can be successfully carried out.

The first approach is to minimize the number of trusted roles and ensure that the people filling those roles are trustworthy and properly trained. The second is to enforce the concept of least privilege and distribute the functions of the roles among several people, so that any malicious activity requires collusion.

Trusted role operations include:

* The validation, authentication, and handling of information in Certificate Applications;
* The acceptance, rejection, or other processing of Certificate Applications, revocation re quests, renewal requests, or enrolment information;
* The issuance, or revocation of Certificates, including personnel having access to restricted portions of its repository;
* Access to safe combinations and/or keys to security containers that contain materials sup porting portions of its
repository;
* Access to hardware security modules (HSMs), their associated key material, and the secret share splits of the PINS that protect access to the HSMs;
* Providing enterprise customer support;
* Access to any source code for the digital certificate applications or systems;
* Access to restricted portions of the certificate repository;
* The ability to grant physical and/or logical access to the CA equipment; _or_
* The ability to administer the background investigation policy processes.

The only mandatory trusted roles defined by this policy are the Administrators, CA Operations Staff, the RA Operations Staff and Security Auditors. Multiple people may hold the same trusted role, with collective privileges sufficient to fill the role. Other trusted roles may be defined in other documents, which describe or impose requirements on the CA operation.

The CA shall maintain lists, including names, organizations, contact information, and organizational affiliation for those who act in Administrator, CA Operations Staff, RAs, and Security Auditor trusted roles, and shall make them available during compliance audits. The RA shall maintain lists, including names, organizations, and contact information of those who act in RA Operations Staff, RA Administrators, and RA Security Auditor roles for that RA.

#### 5.2.1.1 Administrator

The administrator role shall be responsible for:

* Installation, configuration, and maintenance of the CA and CSS (where applicable);
* Establishing and maintaining CA and CSS system accounts;
* Configuring certificate profiles or templates;
* Configuring CA, RA, and CSS audit parameters;
* Configuring CSS response profiles;
* Generating and backing up CA and CSS keys;
* Controlling and managing CA cryptographic modules;
* System backups and recovery; _and_
* Changing recording media.

Administrators do not issue certificates to subscribers.

#### 5.2.1.2 CA Operation Staff

The CA Operation Staff role shall be responsible for issuing certificates, that is:

* Registering new subscribers and requesting the issuance of certificates;
* Verifying the identity of subscribers and accuracy of information included in certificates;
* Approving and executing the issuance of certificates;
* Requesting, approving and executing the revocation of certificates;
* Approving infrastructure certificates issued to support the operations of the CA;
* Approving revocation of certificates issued to CAs or to support the operations of the CA;
* Approving certificates issued to RAs;
* Authorizing RAs;
* Approving revocation of certificates issued to RAs;
* Providing Certificate revocation and suspension status information as part of a CSS (if implemented); _and_
* Posting Certificates and CRLs.

#### 5.2.1.3 Auditor

Security Auditors are responsible for auditing CAs and RAs. This sensitive role cannot be combined with any other sensitive role, e.g. the Security Auditor cannot also be part of the CA Operations Staff.

Security Auditors are responsible for reviewing, maintaining, and archiving audit logs, and for performing or overseeing internal audits (independent of formal compliance audits) to ensure that CAs and RAs are operating in accordance with the associated CPSs.

#### 5.2.1.4 RA Staff

RA Staff are the individuals holding trusted roles that operate and manage RA components. RA Staff is responsible for the following:

* Installation, configuration, and maintenance of the RA;
* Establishing and maintaining RA operating system and application accounts;
* Routine operation of the RA equipment such as system backup and recovery or changing
 recording media;
* Registering new Subscriber and requesting the issuance of certificates;
* Verifying the identity of Subscribers;
* Verifying the accuracy of information included in certificates;
* Approving and executing the issuance of certificates; _and_
* Requesting, approving, and executing the suspension, restoration, and revocation of certificates.

### 5.2.2 Number of Persons Required per Task
Where multi-party control is required, all participants shall hold a trusted role. Multi-party control shall not be achieved using personnel that serve in a Security Auditor role with the exception of audit functions. The following tasks shall require two or more persons:

* Generation, and backup of CA keys;
* Activation of root and intermediate CA keys (note that operational CA keys, such as the doorman key may be activated by a single person with multi-factor authentication).
* Performance of CA administration or maintenance tasks;
* Archiving or deleting CA audit logs. At least one of the participants shall serve in a Security Auditor role;
* Physical access to CA equipment; _or_
* Access to any copy of the CA cryptographic module.

### 5.2.3 Identification and Authentication for Each Role

Individuals holding trusted roles shall identify themselves and be authenticated by the CA and RA before being permitted to perform any actions set forth above for that role or identity. CA Operations Staff and RA Staff shall authenticate using a credential that is distinct from any credential they use to perform non-trusted role functions. This credential shall be generated and stored in a system that is protected to the same level as the CA system.

CA and RA equipment shall require, at a minimum, strong authenticated access control for remote access using multi-factor authentication. Examples of multi factor authentication include use of a password or PIN along with a time-based token, digital certificate on a hardware token or other device that enforce a policy of what a user has and what a user knows.

CA and RA equipment shall require, at a minimum, authenticated access control (e.g., strong passwords) for local multi-party access.

Individuals holding trusted roles shall be appointed to the trusted role by an appropriate approving authority. The approval shall be recorded in a secure and auditable fashion. Individuals holding trusted roles shall accept the responsibilities of the trusted role, and this acceptance shall be recorded in a secure and auditable fashion.

Identity proofing of the RA shall be performed by a member of the CA Operations Staff.

Users shall authenticate themselves to all aspects of the network (servers, operating systems, applications, databases, processes, and so on) before they can access that resource.

#### 5.2.3.1 Authentication: Passwords and Accounts

When the authentication mechanism uses operator selectable passwords, strong passwords shall be employed. Passwords for CA authentication shall be different from non-CA systems.

The CA shall have the minimum number of accounts that are necessary to its operation. Account access shall be locked after an appropriate number of unsuccessful login attempts. Restoration of access shall be performed by a different person who holds a trusted role.

### 5.2.4 Roles requiring separation of duties

Individuals serving as Security Auditors shall not perform or hold any other trusted role.

An individual that holds any CA Operations Staff role shall not be an RA excerpt that CA Operations Staff may perform RA functions when issuing CA Certificates or issuing certificates to RA.

Only an individual serving in a Security Auditor role may perform internal auditing functions, with the exception of those security audit functions (e.g., configuring, archiving, deleting) that require multi-person control.

An individual that performs any trusted role shall only have one identity when accessing CA equipment.

## 5.3 Personnel Controls

Personnel Security plays a critical role in the CA facility’s overall security system. Personnel Security shall be designed to prevent both unauthorized access to the CA facility and CA systems and compromise of sensitive CA operations by CA personnel.

Inadequate personnel security procedures or negligent enforcement of personnel security policies can pose potentially devastating threats to security. These threats can include unauthorized access, data loss and corruption, denial of service, and even facility sabotage and terrorism. Such events can erode or destroy customer confidence in the CA.

### 5.3.1 Qualifications, Experience, and Clearance Requirements

Personnel seeking to become Trusted Persons shall present proof of the requisite background, qualifications and experience needed to perform their prospective job responsibilities competently and satisfactorily.

Individuals appointed to any trusted role shall meet the following:

* Be employees of or contractor/vendor of the CA and bound by terms of employment or contract
* Be appointed in writing
* Have successfully completed an appropriate training program
* Have demonstrated the ability to perform their duties
* Have no other duties that would interfere or conflict with their responsibilities as defined in section 5.2.1
* Have not been previously relieved of trusted role duties for reasons of negligence or non performance of duties.

### 5.3.2 Background Check Procedures

**Note to reviewer:** Background checks are not currently undertaken for R3 personnel. This will be changed in the near future and background checks for all CA personnel will be brought into line with this, and retrospective background checks will be carried out for all persons fulfilling trusted roles. Should any person fail to pass a retrospective background check, the Corda Network Policy Authority must be notes, and a security incident raised. The Policy Authority will decide such remedial action as is necessary to preserve the integrity of the network CA.

Persons fulfilling Trusted Roles shall pass a comprehensive background check.

Prior to commencement of employment in a Trusted Role, the CA shall conduct background checks (in accordance with local privacy laws) which will include a reasonable subset of the following:

* Confirmation of previous employment;
* Check of professional reference;
* Confirmation of the highest or most relevant educational degree obtained;
* Search of criminal records (local, state or provincial, and national);
* Check of credit/financial records;
* Search of driver’s license records; _and_
* Identification verification via National Identity Check (e.g., Social Security Administration records as applicable.

Factors revealed in a background check that should be considered grounds for rejecting candidates for Trusted Roles or for taking action against an existing Trusted Person generally include (but are not limited to) the following:

* Misrepresentations made by the candidate or Trusted Person;
* Highly unfavourable or unreliable professional references;
* Certain criminal convictions; _and_
* Indications of a lack of financial or personal responsibility.

### 5.3.3 Training Requirements

All personnel performing duties with respect to the operation of the CA, CSS or RA shall receive comprehensive training. Training shall be conducted in the following areas:

* CA/CSS/RA security principles and mechanisms;
* All PKI software versions in use on the CA/CSS/RA system;
* All PKI duties they are expected to perform;
* Disaster recovery and business continuity procedures; _and_
* Stipulations of this policy.

### 5.3.4 Retraining Frequency and Requirements

All individuals responsible for PKI Trusted Roles shall be made aware of changes in the CA, CSS, RA operation. Any significant change to the operations shall have a training (awareness) plan, and the execution of such plan shall be documented. Examples of such changes are CA software or hardware upgrade, changes in automated security systems, and relocation of equipment.

Documentation shall be maintained identifying all personnel who received training and the level of training completed.

### 5.3.5 Job Rotation Frequency and Sequence

No stipulation.

### 5.3.6 Sanctions for Unauthorized Actions

Appropriate administrative and disciplinary actions as documented in organization policy shall be taken against personnel who perform unauthorized actions (i.e., not permitted by this CPS or other policies) involving the CA’s systems, the certificate status verification systems, and the repository. Disciplinary actions shall be commensurate with the frequency and severity of the unauthorized actions.

### 5.3.7 Independent Contractor Requirements

Contractor personnel filling trusted roles shall be subject to all requirements stipulated in this document.

Independent contractors who have not completed or passed the background check procedures specified above shall be permitted access to the CA’s secure facilities only to the extent they are escorted and directly supervised by a person holding trusted role at all times.

### 5.3.8 Documentation Supplied to Personnel

Documentation sufficient to define duties and procedures for each role shall be provided to the personnel filling that role.

## 5.4 Audit Logging Procedures

Audit log files shall be generated for all events relating to the security of the CAs, CSS, and RAs. Where possible, the security audit logs shall be automatically collected. Where this is not possible, a logbook, paper form, or other physical mechanism shall be used. All security audit logs, both electronic and non- electronic, shall be retained and made available during compliance audits.

### 5.4.1 Types of Events Recorded

All security auditing capabilities of CA, CSS, and RA operating system and applications shall be enabled during installation. At a minimum, each audit record shall include the following (either recorded automatically or manually for each auditable event):

* The type of event;
* The date and time the event occurred;
* Success or failure where appropriate, _and_
* The identity of the entity and/or operator that caused the event.

A message from any source requesting an action by the CA, CSS or RA is an auditable event; the corresponding audit record must also include message date and time, source, destination, and contents.

Further details of types of events recorded are included in the relevant CSP.

### 5.4.2 Frequency of Processing Log

The audit log shall be reviewed at regular intervals. All significant events shall be explained in an audit log summary. Actions taken as a result of these reviews shall be documented.

Such reviews involve verifying that the log has not been tampered with and then briefly inspecting all log entries, with a more thorough investigation of any alerts or irregularities in the logs. A statistically significant portion of the security audit data generated by the CA, CSS and RA since the last review shall be examined. This amount will be described in the CPS.

Real-time automated analysis tools should be used. All alerts generated by such a system shall be analysed.

### 5.4.3 Retention Period for Audit Logs

Audit logs shall be retained on-site for a period defined in the relevant CSP, in addition to being archived as described in section 5.5. The individual who removes audit logs from the CA system shall be an official different from the individuals who, in combination, command the CA signature key. For the CSS and RA, a System Administrator other than the CSS operator or RA shall be responsible for managing the audit log.

### 5.4.4 Protection of Audit Log

The security audit data shall not be open for reading or modification by any human, or by any automated process, other than those that perform security audit processing.

Physical logbooks shall implement controls to allow for the detection of the removal of pages or deletion of entries.

CA/CSS/RA system configuration and procedures must be implemented together to ensure that only authorized people archive or delete security audit data. Procedures must be implemented to protect archived data from deletion or destruction before the end of the security audit data retention period (note that deletion requires modification access).

### 5.4.5 Audit Log Backup Procedures

Audit logs and audit summaries shall be backed up on a defined schedule.

### 5.4.6 Audit Collection System (Internal vs. External)

The audit log collection system may or may not be external to the CA/CSS/RA system. Automated audit processes shall be invoked at system or application start-up, and cease only at system or application shutdown. Audit collection systems shall be configured such that security audit data is protected against loss (e.g., overwriting or overflow of automated log files). Should it become apparent that an automated audit system has failed; CA/CSS/RA operations shall be suspended until the security audit capability can be restored

### 5.4.7 Notification to Event-Causing Subject

There is no requirement to notify a subject that an event was audited. Real-time alerts are neither required nor prohibited by this policy.

### 5.4.8 Vulnerability Assessments

The CA shall perform routine self-assessments of security controls.

## 5.5 Records Archival

### 5.5.1 Types of Events Archived

CA/CSS/RA archive records shall be sufficiently detailed to determine the proper operation of the CA/CSS/RA and the validity of any certificate (including those revoked or expired) issued by the CA. Further details of data archived will be included in the CPS.

### 5.5.2 Retention Period for Archive

Archive records must be retained for the lifetime of the Corda Network without any loss of data.

### 5.5.3 Protection of Archive

No unauthorized user shall be permitted to write to, modify, or delete the archive. For the CA and CSS, the authorized individuals are Security Auditors. For the RA, authorized individuals are someone other than the RA.

For the CA/CSS/RA, archived records may be moved to another medium. The contents of the archive shall not be released except in accordance with sections 9.3and 9.4. Records of individual transactions may be released upon request of any subscribers involved in the transaction or their legally recognized agents.

Archive media shall be stored in a safe, secure storage facility separate from the CA/CSS/RA with physical and procedural security controls equivalent to or better than those of the CA/CSS/RA. If the original media cannot retain the data for the required period, a mechanism to periodically transfer the archived data to new media shall be defined by the archive site.

### 5.5.4 Archive Backup Procedures

The CPS or a referenced document shall describe how archive records are backed up, and how the archive backups are managed.

### 5.5.5 Requirements for Time-Stamping of records

CA/CSS/RA archive records shall be automatically time-stamped as they are created. The CPS shall describe how system clocks used for time-stamping are maintained in synchrony with an authoritative time standard.

### 5.5.6 Archive Collection System (Internal or External)

Archive data may be collected in any expedient manner.

### 5.5.7 Procedures to Obtain and Verify Archive Information

Procedures, detailing how to create, verify, package, transmit, and store the CA archive information, shall be published in the CPS.

## 5.6 Key Changeover

To minimize risk from compromise of a CA’s private signing key, that key may be changed often. From that time on, only the new key will be used to sign CA and subscriber certificates. If the old private key is used to sign OCSP responder certificates or CRLs that cover certificates signed with that key, the old key must be retained and protected.

The CA’s signing key shall have a validity period as described in section 6.3.2.

When a CA updates its private signature key and thus generates a new public key, the CA shall notify all CAs, RAs, and subscribers that rely on the CA’s certificate that it has been changed. When a CA that distributes self-signed certificates updates its private signature key, the CA shall generate key rollover certificates, where the new public key is signed by the old private key, and vice versa. This permits acceptance of newly issued certificates and CRLs without distribution of the new self-signed certificate to current users. Key rollover certificates are optional for CAs that do not distribute self-signed certificates.

## 5.7 Compromise and Disaster Recovery

### 5.7.1 Incident and Compromise Handling Procedures

CA organizations shall have an Incident Response Plan and a Disaster Recovery Plan.

If compromise of a CA is suspected, an independent, third-party investigation shall be performed in order to determine the nature and the degree of damage. Certificates issued off that CA shall be stopped immediately upon detection of a compromise. If a CA private signing key is suspected of compromise, the procedures outlined in Section 5.7.3 shall be followed. Otherwise, the scope of potential damage shall be assessed in order to determine if the CA needs to be rebuilt, only some certificates need to be revoked, and/or the CA private key needs to be declared compromised. The independent, third-party investigating party shall make the determination that a CA private key has been compromised.

In case of a CSS key compromise, all certificates issued to the CSS shall be revoked and the revocation information shall be published immediately in the most expeditious manner. Subsequently, the CSS shall be re-keyed.

The vendor shall notify the Corda Network Foundation in the case of a root CA or Network Operator CA or notify the superior CA in the case of a subordinate CA if any of the following occur:

* Suspected or detected compromise of any CA system or subsystem
* Physical or electronic penetration of any CA system or subsystem
* Successful denial of service attacks on any CA system or subsystem
* Any incident preventing a CA from issuing and publishing a CRL or OCSP prior to the time indicated in the _nextUpdate_ field in the currently published CRL or OCSP suspected or detected compromise of a certificate status server (CSS) if:
** the CSS certificate has a lifetime of more than <72> hours; and
** the CSS certificate cannot be revoked (e.g., an OCSP responder certificate with the _id-pkix-ocsp-nocheck_ extension)

### 5.7.2 Computing Resources, Software, and/or Data Are Corrupted

When computing resources, software, and/or data are corrupted, CAs operating under this policy shall respond as follows:

* Notify Corda Network Foundation or the superior CA as soon as possible.
* Ensure that the system’s integrity has been restored prior to returning to operation and determine the extent of loss of data since the last point of backup.
* If the CA signing keys are not destroyed, the integrity of the system has been restored, and the risk is deemed negligible, re-establish CA operations, giving priority to the ability to generate certificate status information within the CRL issuance schedule.
* If the CA signing keys are destroyed, the integrity of the system cannot be restored, or the risk is deemed substantial, re-establish CA operations as quickly as possible, giving priority to the generation of a new CA signing key pair.

### 5.7.3 Entity (CA) Private Key Compromise Procedures

#### 5.7.3.1 Root CA Compromise Procedures

In the case of the Root CA compromise, the vendor shall notify the Corda Network Governing Body and relying parties via public announcement of the Root CA compromise so that they can revoke any cross certificates issued to the Root CA or any Subordinate CAs and notify all Subscribers and Relying Parties to remove the trusted self-signed certificate from their trust stores. Notification shall be made in an authenticated and trusted manner. Initiation of notification to the Corda Network Governing Body and any cross-certified PKIs shall be made at the earliest feasible time. Initiation of notification to relying parties and subscribers may be made after mediations are in place to ensure continued operation of applications and services. If the cause of the compromise can be adequately addressed and it is determined that the PKI can be securely re-established the vendors shall then generate a new Root CA certificate, solicit requests and issue new Subordinate CA certificates and securely distribute the new Root CA certificate.

#### 5.7.3.2 Intermediate or Subordinate CA

In the event of an Intermediate or Subordinate CA key compromise, the CA vendor shall notify the Corda Network Foundation and Superior CA. The superior CA shall revoke that CA’s certificate, and the revocation information shall be published immediately in the most expedient, authenticated, and trusted manner but within a period defined by the applicable CSP after the notification. The Compromised CA vendor shall also investigate and report to the Corda Network Governing Body and Superior CA what caused the compromise or loss, and what measures have been taken to preclude recurrence. If the cause of the compromise can be adequately addressed and it is determined that the CA can be securely re-established, then, the CA shall be re- established. Upon re-establishment of the CA, new Subscriber certificates shall be requested and issued.

For Subordinate CAs, when a Subscriber certificate is revoked because of compromise, suspected compromise, or loss of the private key, a CRL shall be published at the earliest feasible time by the supporting CA, but in no case more than 6 hours after notification.

#### 5.7.3.3 CSS Compromise Procedures

In case of a CSS key compromise, the CA that issued the CSS a certificate shall revoke that certificate, and the
revocation information shall be published immediately in the most expedient, authenticated, and trusted manner. The CSS
shall subsequently be re-keyed. If the CSS is self-signed
and the CSS certificate expiration is more than a period defined by the applicable CSP days
away, the vendor shall immediately notify the Corda Network Foundation, relying parties,
and any cross-certified PKIs of the CSS compromise so that they can notify all Subscribers and
Relying Parties to remove trust in the CSS certificate from each Relying Party application, and
install the re-keyed certificate.

#### 5.7.3.4 RA Compromise Procedures

In case of an RA compromise, the CA shall disable the RA. In the case that an RA’s key is compromised, the CA that issued the RA certificate shall revoke it, and the revocation information shall be published within a period defined by the applicable CSP in the most expedient, authenticated, and trusted manner. The compromise shall be investigated by the CA in order to determine the actual or potential date and scope of the RA compromise. All certificates approved by that RA since the date of actual or potential RA compromise shall be revoked. In the event that the scope is indeterminate, then the CA compromise procedures in Section 5.7.3.2 shall be followed.

### 5.7.4 Business Continuity Capabilities after a Disaster

CAs shall be required to maintain a Disaster Recovery Plan.

In the case of a disaster in which the CA equipment is damaged and inoperative, the CA operations shall be re-established as quickly as possible, giving priority to the ability to revoke Subscriber’s certificates. If the CA cannot re-establish revocation capabilities prior to date and time specified in the _nextUpdate_ field in the currently published CRL issued by the CA, then the inoperative status of the CA shall be reported to the Corda Network Foundation and Superior CA. The Corda Network Governing Body and Superior CA shall decide whether to declare the CA private signing key as compromised and re-establish the CA keys and certificates, or allow additional time for reestablishment of the CA’s revocation capability.

In the case of a disaster whereby a CA installation is physically damaged, and all copies of the CA signature key are destroyed as a result, the CA shall request that its certificates be revoked. The CA installation shall then be completely rebuilt by re-establishing the CA equipment, generating new private and public keys, being re-certified, and re-issuing all cross certificates. Finally, all Subscriber certificates will be re-issued. In such events, any Relying Parties who continue to use certificates signed with the destroyed private key do so at their own risk, and the risk of others to whom the data is forwarded, as no revocation information will be available (if the CRL signing key was destroyed).

## 5.8 CA or RA Termination

When a CA operating under this policy terminates operations before all certificates have expired, Entities will be given as much advance notice as circumstances permit.

Prior to CA termination, notice shall be provided to all cross-certified CAs requesting revocation of all certificates issued to it. In addition:

* The CA shall issue a CRL revoking all unexpired certificates prior to termination. This CRL shall be available until all certificates issued by the CA expire.
* The CA, CSS, and RA shall archive all audit logs and other records prior to termination
* The CA, CSS, and RA shall destroy all its private keys upon termination
* The CA, CSS, and RA archive records shall be transferred to an appropriate authority specified in the CPS.
* If a Root CA is terminated, the Root CA shall use secure means to notify the subscribers to delete all trust anchors representing the terminated CA.

# 6 Technical controls

## 6.1 Key Pair Generation and Installation

### 6.1.1 Key Pair Generation

#### 6.1.1.1 CA Key Pair Generation

Cryptographic keying material used by CAs to sign certificates, CRLs or status information shall be generated in \[FIPS 140\] Level 3 validated cryptographic modules. Multi-party control is required for CA key pair generation, as specified in section 6.2.2.

CA key pair generation must create a verifiable audit trail demonstrating that the security requirements for procedures were followed. The documentation of the procedure must be detailed enough to show that appropriate role separation was used. An independent third party shall validate the execution of the key generation procedures either by witnessing the key generation or by examining the signed and documented record of the key generation.

#### 6.1.1.2 RA Key Pair Generation

No stipulation.

#### 6.1.1.3 Subscriber Key Pair Generation

Subscriber key pair generation will be performed by the subscriber only.

#### 6.1.1.4 CSS Key Pair Generation

No stipulation.

### 6.1.2 Private Key Delivery to Subscriber

Not applicable.

### 6.1.3 Public Key Delivery to Certificate Issuer

Where key pairs are generated by the subscriber, the public key and the subscriber’s identity must be delivered securely to the CA for certificate issuance. The delivery mechanism shall bind the subscriber’s verified identity to the public key. If cryptography is used to achieve this binding, it must be at least as strong as the CA keys used to sign the certificate.

### 6.1.4 CA Public Key Delivery to Relying Parties

The public key of a root CA shall be provided to the subscribers acting as relying parties in a secure manner so that it is not vulnerable to modification or substitution. Examples of acceptable methods for delivery of the public key include:

* Secure distribution of self-signed certificates through secure out-of-band mechanisms;
* Comparison of the hash of the self-signed certificate against a hash value made available via authenticated out-of-band sources (note that hashes posted in-band along with the certificate are not acceptable as an authentication mechanism);

When a CA updates its signature key pair, the key rollover certificates may be signed with the CA’s current private key; in this case secure distribution is not required.

### 6.1.5 Key Sizes

Note to reviewer – Key sizes are described in separate documents. Contact R3 for details.

All CA certificates issued under this policy shall contain elliptic curve keys of at least 384 bits and be signed with the corresponding private key.

All Corda node certificates issued under this policy shall contain elliptic curve keys of at least 256 bits and be signed with the corresponding private key.

CAs that generate certificates and CRLs under this policy should use SHA-384 hash algorithm when generating digital signatures. ECDSA signatures on certificates and CRLs shall be generated using SHA-256 or SHA-384, as appropriate for the key length.

### 6.1.6 Public Key Parameters Generation and Quality Checking

Elliptic Curve public key parameters shall always be selected from the set specified in section 7.1.3.

### 6.1.7 Key Usage Purposes (as per X.509 v3 Key Usage Field)

No stipulation.

## 6.2 Private Key Protection and Cryptographic Module Engineering Controls

### 6.2.1 Cryptographic Module Standards and Controls

The CA shall use a \[FIPS 140\] Level 3 or higher validated hardware cryptographic module for signing operations.

No stipulation with regards cryptographic module standards for RAs.

No stipulation with regards cryptographic module standards for CSSes.

No stipulation with regards cryptographic module standards for subscribers.

### 6.2.2 Private Key (N of M) Multi-Person Control

A single person shall not be permitted to activate or access any cryptographic module that contains the complete CA signing key. CA signing keys may be backed up only under two-person control. Access to CA signing keys backed up for disaster recovery shall be under at least two person control. The names of the parties used for two-person control shall be maintained on a list that shall be made available for inspection during compliance audits.

### 6.2.3 Private Key Escrow

Private keys are never escrowed.

### 6.2.4 Private Key Backup

#### 6.2.4.1 Backup of CA Private Signature Key

The CA private signature keys shall be backed up under the same multiparty control as the original signature key. At least one copy of the private signature key shall be stored off-site. All copies of the CA private signature key shall be accounted for and protected in the same manner as the original. Backup procedures shall be included in the CA’s CPS.

#### 6.2.4.2 Backup of Human Subscriber Private Keys

No stipulation.

#### 6.2.4.3 Backup of CSS Private Key

CSS private keys may be backed up. If backed up, all copies shall be accounted for and protected in the same manner as the original.

#### 6.2.4.4 Backup of Device Private Keys

No stipulation.

### 6.2.5 Private Key Archival

CA private signature keys and subscriber private signature keys shall not be archived. CAs that retain subscriber private encryption keys for business continuity purposes shall archive such subscriber private keys in accordance with section 5.5.

### 6.2.6 Private Key Transfer into or from a Cryptographic Module

CA private keys may be exported from the cryptographic module only to perform CA key backup procedures as described in Section 6.2.4.1. At no time shall the CA private key exist in plaintext outside the cryptographic module.

All other keys shall be generated by a cryptographic module. In the event that a private key is to be transported from one cryptographic module to another, the private key must be encrypted during transport; private keys must never exist in plaintext form outside the cryptographic module boundary.

Symmetric keys used to encrypt other private keys for transport must be protected from disclosure.

### 6.2.7 Private Key Storage on Cryptographic Module

No stipulation.

### 6.2.8 Method of Activating Private Key

The subscriber must be authenticated to the cryptographic token before the activation of the associated private key(s). Acceptable means of authentication include but are not limited to passphrases, PINs or biometrics. Entry of activation data shall be protected from disclosure (i.e., the data should not be displayed while it is entered).

A device may be configured to activate its private key without requiring activation data, provided that appropriate physical and logical access controls are implemented for the device and its cryptographic token. The AOR is responsible for ensuring that the system has security controls commensurate with the level of threat in the device’s environment. These controls shall protect the device’s hardware, software, and the cryptographic token and its activation data from compromise

### 6.2.9 Method of Deactivating Private Key

Cryptographic modules that have been activated shall not be available to unauthorized access. After use, the cryptographic module shall be deactivated, e.g., via a manual logout procedure or automatically after a period of inactivity as defined in the applicable CPS. CA cryptographic modules shall be removed and stored in a secure container when not in use.

### 6.2.10 Method of Destroying Private Key

Individuals in trusted roles shall destroy CA, RA, and CSS (e.g., OCSP server) private signature keys when they are no longer needed. Subscribers shall either surrender their cryptographic module to CA/RA personnel for destruction or destroy their private signature keys, when they are no longer needed or when the certificates to which they correspond expire or are revoked. Physical destruction of hardware is not required.

### 6.2.11 Cryptographic Module Rating

See section 6.2.1.

## 6.3 Other Aspects of Key Pair Management

### 6.3.1 Public Key Archival

The public key is archived as part of the certificate archival.

### 6.3.2 Certificate Operational Periods and Key Usage Periods
The usage period for the Root CA key pair is a maximum of 20 years.

The usage period for the Network Operator subordinate CA key pairs is a maximum of 20 years

The usage period for the Network Operator subject key pairs is a maximum of 20 years.

The usage period for subscriber key pairs is a maximum of 20 years.

## 6.4 Activation Data

### 6.4.1 Activation Data Generation and Installation

CA activation data may be user-selected (by each of the multiple parties holding that activation data). If the activation data must be transmitted, it shall be via an appropriately protected channel, and distinct in time and place from the associated cryptographic module.

RA and subscriber activation data may be user-selected. The strength of the activation data shall meet or exceed the requirements for authentication mechanisms stipulated for Level 2 in \[FIPS 140\]. If the activation data must be transmitted, it shall be via an appropriately protected channel, and distinct in time and place from the associated cryptographic module.

### 6.4.2 Activation Data Protection

Data used to unlock private keys shall be protected from disclosure by a combination of cryptographic and physical
access control mechanisms. Activation data shall be either:

* Memorized;
* Biometric in nature; or
* Recorded and secured at the level of assurance associated with the activation of the
 cryptographic module and shall not be stored with the cryptographic module.

### 6.4.3 Other Aspects of Activation Data
No stipulation.

## 6.5 Computer Security Controls

### 6.5.1 Specific Computer Security Technical Requirements
#### 6.5.1.1 Access Control

Access to information such as sensitive details about customer accounts, passwords, and ultimately, CA-related private
keys should be carefully guarded, along with the machines housing
such information.

#### 6.5.1.2 Access Control Policy and Procedures

The CA shall create and document roles and responsibilities for each employee job function in
the CPS.

The CA shall create and maintain a mapping of these roles and their associated responsibilities to
specific employees and their accounts on CA systems.

#### 6.5.1.3 Account Management

Information system account management features shall ensure that users access only that functionality permitted by
their role or function. All account types with access to information systems
shall be documented along with the conditions and procedures to follow in creating new accounts. Groups and roles shall
have a documented relationship to the business or mission roles
involved in operating the CA.

Section 5.2.1 of this document defines roles and job functions for personnel that the CA will use
when defining access control mechanisms. The CA shall employ the principle of least privilege
when creating users and assigning them to groups and roles; membership to a group or role is
granted shall be justified based upon business need. The CA shall take appropriate action when
a user no longer requires an account, their business role changes, or the user is terminated or
transferred. Periodically, the CA shall review all active accounts to match active authorized users
with accounts, and disable any accounts no longer associated with an active authorized user.

To assist with the management of the information system accounts, automated systems shall assist
in maintaining access for only those users who are still authorized to use the information system.
After an extended period of inactivity, an account shall be automatically disabled and attempts
to access any deactivated account shall be logged.

All account administration activities shall be logged and made available for inspection by appropriate security
personnel. Account administration activities that shall be audited include account
creation, modification, enabling, disabling, group or role changes, and removal actions.

The use of shared/group and guest/anonymous accounts for logon to information systems shall
be prohibited.

#### 6.5.1.4 Least Privilege

In granting rights to accounts and groups, the CA shall employ the principle of least privilege,
allowing only authorized access for users (and processes acting on behalf of users) which are
necessary to accomplish assigned tasks in accordance with organizational missions and business
functions. The CA shall explicitly authorize access to accounts and groups for controlling security
functions and security-relevant information. The CA shall authorize access to privileged commands and features of
information systems only for specific, organization-defined compelling operational needs and documents the
rationale for such access. The CA shall require that users of information systems with access to
administrative privileges to utilize non-privileged accounts or roles when accessing non-privileged
functions (such as reading email).

#### 6.5.1.5 Access Control Best Practices

No stipulation.

#### 6.5.1.6 Permitted Actions without Identification or Authentication

No stipulation.

#### 6.5.1.7 System Integrity

**System Isolation and Partitioning**

CA systems shall be configured, operated, and maintained so as to ensure the continuous logical
separation of processes and their assigned resources. This separation shall be enforced by:

* physical and/or logical isolation mechanisms, such as dedicated systems or virtualization
* protecting an active process and any assigned resources from access by or interference
 from another process.
* protecting an inactive process and any assigned resources from access by or interference
 from an active process.
* ensuring that any exception condition raised by one process will have no lasting detrimental effect on the operation
or assigned resources of another process.

All trusted components should be logically separated from each other, and shall be logically separated from any
untrusted components of the CA system. The CPS shall document how it this
logical isolation of components is accomplished.

Security critical processes shall be isolated from processes that have external interfaces. For example, the CA signing
processes shall be isolated from registration processes. The CPS shall outline
how security critical processes are protected from interference by externally facing processes.

If there are system resources shared amongst trusted and/or untrusted processes, the underlying
system(s)shall prevent any unauthorized and unintended information transfer between processes
via those shared system resources.

**Malicious Code Protection**

The CA system shall employ malicious code protection mechanisms to mitigate the risk of malicious code on CA system
components. Malicious code on trusted CA components could allow
an attacker to issue fraudulent certificates, create a rouge intermediate or signing CA server, or
compromise the availability of the system.

**Software and Firmware Integrity**

The CA shall employ technical and procedural controls to prevent and detect unauthorized
changes to firmware and software on CA systems. Access control mechanisms and configuration
management processes (see Section 6.5.1.1 and 6.6.2) shall ensure that only authorized system
administrators are capable of installing or modifying firmware and software on CA systems.

**Information Protection**

The CA shall protect the confidentiality and integrity of sensitive information stored or processed
on CA systems that could lead to abuse or fraud. For example, the CA shall protect customer data
that could allow an attacker to impersonate a customer. The CA shall employ technical mechanisms to prevent unauthorized
changes or accesses to this information, such as access control
mechanisms that limit which users are authorized to view or modify files. Sensitive information
stored on devices that are not physically protected from potential attackers shall be stored in an
encrypted format, using a NIST-approved encryption algorithm and mode of operation.

### 6.5.2 Computer Security Rating
No stipulation.

## 6.6 Life Cycle Technical Controls

## 6.6.1 System Development Controls

The system development controls address various aspects related to the development and change of the CA system through aspects of its life-cycle.

The CA system shall be implemented and tested in a non-production environment prior to implementation in a production environment. No change shall be made to the production environment unless the change has gone through the change control process as defined for the system baseline.

In order to prevent incorrect or improper changes to the CA system, the CA system shall require multi-party control for access to the CA system when changes are made.

## 6.6.2 Security Management Controls

A list of acceptable products and their versions for each individual CA system component shall be maintained and kept up-to-date within a configuration management system. Mechanisms and/or procedures shall be in operation designed to prevent the installation and execution of unauthorized software.

To reduce the available attack surface of a CA system, only those ports, protocols, and services that are necessary to the CA system architecture are permitted to be installed or operating. The CA system shall maintain a list of ports, protocols, and services that are necessary for the correct function of each component within the CA system. There shall be automated mechanisms to monitor the running processes and open ports against the permitted list.

### 6.6.3 Life Cycle Security Controls

For flaw remediation, the CA shall scan all CA systems for vulnerabilities using at least one vulnerability scanner at regular intervals. The use of multiple scanners on the most sensitive systems is strongly encouraged.

Vulnerabilities identified will be recorded and tracked to resolution using the CA’s issue tracking system. Time to remediation will be linked to the CVSS base score, temporal and environmental metrics.

The CA shall monitor relevant notification channels on a regular basis for updates to packages installed on CA systems (including networking hardware). CAs shall have a plan for receiving notification of software and firmware updates, for obtaining and testing those updates, for deciding when to install them, and finally for installing them without undue disruption. For critical vulnerabilities, the CA shall evaluate and install the update within a period to be established. For less critical vulnerabilities, the CA shall evaluate each package to determine whether an update is required, and if so, that update shall be applied to all affected CA systems within a period to be established A log shall be kept of the notifications, the decision to apply/not apply including reason, and the application of relevant updates/patches.

From time to time, the CA may discover errors in configuration files, either because of human error, source data error, or changes in the environment which have made an entry erroneous. The CA shall correct such errors within a period to be established of discovery, and shall document the reason for the error, and the associated correction within the CA’s issue tracking system.

In no case should remediation cause unavailability of revocation information.

## 6.7 Network Security Controls

The components of the Corda Network Certificate Authority are located behind firewall devices that logically segregate the components of a system into zones, isolating those components according to their value and the need to provide access to those services to network subscribers (network participants, in Corda parlance). The principle of least privilege is used throughout.

Appropriate technical controls will be provided to ensure that services are afforded the availability appropriate to the criticality of the services provided. For example, the availability of any revocation services is seen to be more critical that of certificate request and issuance services.

Technical controls will be implemented to ensure the confidentiality and integrity of communications between CA components, CA to RA communications and CA and RA to subscriber communications.

Network, host and application monitoring will be in place to track network and host resource thresholds, unauthorized network services, certificate request and access control thresholds.

For operational reasons, there may be a need to perform remote management of some CA resources. The CA will implement such controls as to allow remote management while maintaining the desired security posture.

The CA System shall conduct regular external and internal penetration tests to identify vulnerabilities and attack vectors that can be used to exploit enterprise systems. Results of these tests will be integrated into the vulnerability remediation process.

The CA System shall conduct regular external and internal penetration tests to identify vulnerabilities and attack vectors that can be used to exploit enterprise systems.

## 6.8 Time-Stamping

Asserted times shall be accurate to within three minutes. Electronic or manual procedures may be used to maintain system time. Clock adjustments are auditable events (see section 5.4.1).

# 7 Certificate, CRL, and OCSP Profiles

## 7.1 Certificate Profile

**Note to reviewer:** The certificate, CRL and OCSP profiles used by Corda nodes and supporting infrastructure has not been finalised. At present, for the purposes of the R3 Testnet, the PKI in which the nodes operate runs a uniform version of the Corda code and therefore the interoperability requirements satisfied by these profiles do not exist. It is recognised that this will not always be the case and that said profiles will be required in the future to facilitate interoperability between heterogeneous nodes and supporting infrastructure. Appropriate profiles will be included in this certificate policy at that time.

### 7.1.1 Version Number (s)

Certificates MUST be of type X.509 v3.

### 7.1.2 Serial Numbers

CAs SHALL generate non-sequential Certificate serial numbers greater than zero (0) containing at least 64 bits of output from a CSPRNG.

### 7.1.3 Certificate Cipher Suite and Algorithms
The Corda Root CA and Subordinate CA Certificates shall sign with the following algorithms:

|Certificate|Algorithm|Parameters|Lifetime|
|-----------|---------|----------|--------|
|Root CA    |ECDSA, SHA-256|ECDSA_P 256|20 years|
|Subordinate CA|ECDSA, SHA- 256|ECDSA_P 256|20 years|


TLS certificates must follow the TLSv1.2 standard.

### 7.1.4 Certificate Role Extension
Corda certificates have a custom X.509 v3 extension that specifies the role the certificate relates to. This extension has the OID 1.3.6.1.4.1.50530.1.1 and is non-critical, so implementations outside of Corda nodes can safely ignore it. The extension contains a single ASN.1 integer identifying the identity type the certificate is for:

|Role|Value|
|----|-----|
|Doorman CA|1|
|Network Map|2|
|Service Identity|3|
|Node CA|4|
|TLS|5|
|Legal Identity|6|
|Confidential Identity|7|


### 7.1.5 Root CA Certificate
|Extension|Status|Constraints|
|---------|------|-----------|
|Basic Constraints|CRITICAL|This extension MUST appear as a critical extension. The CA field MUST be set true. The pathLenConstraint field SHOULD NOT be present|
|Key Usage|CRITICAL|This extension MUST be present and MUST be marked critical. Bit positions for keyCertSign and cRLSign MUST be set. If the Root CA Private Key is used for signing OCSP responses, then the digitalSignature bit MUST be set.|
|Certificate Policies|NOT PRESENT|This extension SHOULD NOT be present|
|Extended Key Usage|NOT PRESENT|This extension MUST NOT be present|

### 7.1.6 Subordinate “Issuing” CA Certificate

|Field|Status|Constraint|
|-----|------|----------|
|Certificate Policies|REQUIRED|This extension MUST be present and SHOULD NOT be marked as critical. REQUIRED: certificatePolicies:policyIdentifier OPTIONAL: certificatePolicies:policyQualifiers:policyQualifierId OPTIONAL: certificatePolicies:policyQualifiers:qualifier:cPSuri|
|CRL Distribution Points|REQUIRED| This extension MUST be present and SHOULD NOT be marked as critical It MUST contain the HTTP URL of the CA's CRL service|
|Authority Information Access|REQUIRED|With the exception of stapling, which is noted below, this extension MUST be present. It MUST NOT be marked as critical It MUST contain the URL of the issuing CA's OCSP responder (access method = 1.3.6.1.5.5.7.48.1). It SHOULD also contain the HTTP URL of the Issuing CA’s certificate (access method = 1.3.6.1.5.5.7.48.2). The HTTP URL of the Issuing CA’s OCSP responder MAY be omitted, provided that the Subscriber “staples” the OCSP response for the Certificate in its TLS handshakes [RFC4366]|
|Basic Constraints|CRITICAL|This extension MUST appear as a critical extension. Bit positions for keyCertSign and cRLSign MUST be set. The cA field MUST be set true. The pathLenConstraint field SHOULD NOT be present|
|Key Usage|CRITICAL| This extension MUST be present and MUST be marked critical. Bit positions for keyCertSign and cRLSign MUST be set. If the Issuing CA Private Key is used for signing OCSP responses, then the digitalSignature bit MUST be set.|
|Name Constraints|OPTIONAL|If present, this extension SHOULD be marked critical|
|Extended Key Usage|OPTIONAL|For Subordinate CA Certificates to be Technically con- strained in line with section 7.1.5, then either the value id-kp-serverAuth [RFC5280] or id-kp-clientAuth [RFC5280] or both values MUST be present**|

### 7.1.7 Certificate Policy Object Identifier

A Root CA Certificate SHOULD NOT contain the certificatePolicies extension.

A Subordinate CA SHALL represent, in its Certificate Policy and/or Certification Practice Statement, that all Certificates containing a policy identifier indicating compliance with these Requirements are issued and managed in accordance with these Requirements.

Subscriber Certificates A Certificate issued to a Subscriber MUST contain one or more policy identifier(s), defined by the Issuing CA, in the Certificate’s certificatePolicies extension that indicates adherence to and compliance with these Requirements. CAs complying with these Requirements MAY also assert one of the reserved policy OIDs in such Certificates. The issuing CA SHALL document in its Certificate Policy or Certification Practice Statement that the Certificates it issues containing the specified policy identifier(s) are managed in accordance with these Requirements

### 7.1.8 Usage of Policy Constraints Extension

No stipulation.

### 7.1.9 Policy Qualifiers Syntax and Semantics

No stipulation.

### 7.1.10 Processing Semantics for the Critical Certificate Policies

No stipulation.

## 7.2 CRL Profile

Certificate Revocation in the Corda Network is still being finalised and aspects could change in the future. In particular it is likely that revocation of Corda Nodes could be implemented by an entirely separate mechanism to the CRL facility provided by X.509 certificates. Corda Certificates will still define CRL endpoints in case it is required in the future.

The Root CA SHOULD NOT contain a CRL Distribution Points

The Subordinate CA SHOULD contain a CRL Distribution Point. The CRL SHOULD be signed by a revocation certificate issued by the Root CA.

An entry in the CRL MUST NOT be removed until the expiration date of the certificate being revoked has passed. In other words, once revoked, the certificate must remain in the CRL during its validity period.

### 7.2.1 Version Number(s)

No stipulation.

### 7.2.2 CRL and CRL Entry Extensions

No stipulation.

## 7.3 OCSP Profile

Certificate Revocation in the Corda Network is still being finalised and aspects could change in the future. In 
particular it is likely that revocation of Corda Nodes could be implemented by an entirely separate mechanism to the 
OCSP facility provided by X.509 certificates. Corda Certificates will still define an OCSP responder in case it is 
required in the future.

The Root CA SHOULD NOT contain the Authority Information Access extension.

The Subordinate CA MAY contain an Authority Information Access extension. The Access Method SHOULD be set to On-line 
Certificate Status Protocol. The Authority Key Identifier SHOULD identity a revocation key issued by the Root CA.

### 7.3.1 Version Number(s)

No stipulation.

### 7.3.2 OCSP Extensions

No stipulation.

# 8 Compliance, Audit and Other Assessments

The CAs shall have a compliance audit mechanism in place to ensure that:

* They comply with requirements outlined within this policy and the audit requirements set forth in this section are 
met; _and_
* The requirements of their CPS are implemented and enforced.

This specification does not impose a requirement for any particular assessment methodology.

## 8.1 Frequency or Circumstances of Assessment

CAs and RAs shall be subject to a periodic compliance audit at least once per year.

## 8.2 Qualifications of Assessor

The auditor must demonstrate competence in the field of compliance audits, and must be thoroughly familiar with the CA’s 
CPS and this CP. The compliance auditor must perform such compliance audits as a regular ongoing business activity. In 
addition to the previous requirements, the auditor must be a certified information system auditor (CISA) or IT security 
specialist, and a PKI subject matter specialist who can offer input regarding acceptable risks, mitigation strategies, 
and industry best practices.

## 8.3 Assessor’s Relationship to Assessed Entity

The compliance auditor either shall be a private firm that is independent from the entities (CA and RAs) being audited, 
or it shall be sufficiently organizationally separated from those entities to provide an unbiased, independent 
evaluation. To insure independence and objectivity, the compliance auditor may not have served the entity in developing 
or maintaining the entity’s CA Facility or certificate practices statement. The Policy Authority shall determine whether 
a compliance auditor meets this requirement.

## 8.4 Topics Covered by Assessment

The purpose of a compliance audit shall be to verify that the CA and its recognized RAs comply with all the requirements 
of the current versions of this CP and the CA’s CPS. All aspects of the CA/RA operation shall be subject to compliance 
audit inspections.

## 8.5 Actions Taken as a Result of Deficiency

When the compliance auditor finds a discrepancy between the requirements of this CP or the stipulations in the CPS and 
the design, operation, or maintenance of the PKI Authorities, the following actions shall be performed:

* The compliance auditor shall note the discrepancy;
* The compliance auditor shall notify the parties identified in section 8.6 of the discrepancy; _and_
* The party responsible for correcting the discrepancy will propose a remedy, including expected time for completion, 
to the Policy Authority.

Depending upon the nature and severity of the discrepancy, and how quickly it can be corrected, the Policy Authority 
may decide to temporarily halt operation of the CA or RA, to revoke a certificate issued to the CA or RA, or take other 
actions it deems appropriate. The Policy Authority will develop procedures for making and implementing such 
determinations.

## 8.6 Communication of Results

An Audit Compliance Report shall be provided to the entity responsible for CA operations. The Audit Compliance Report 
and identification of corrective measures shall be provided to Policy Authority within defined period of completion. A 
special compliance audit may be required to confirm the implementation and effectiveness of the remedy.

# 9 Other Business and Legal Matters

## 9.1 Fees

### 9.1.1 Certificate Issuance or Renewal Fees

Certificate issuance and renewal fees will be decided by the Corda Network Foundation (CNF) and may be included in a 
single network access fee. Such fee schedules to be published by the CNF from time to time.

### 9.1.2 Certificate Access Fees

Certificate access fees will be decided by the CNF and may be included in a single network access fee. Such fee 
schedules to be published by the CNF from time to time.

### 9.1.3 Revocation or Status Information Access Fees

Revocation or Status Information Access fees will be decided by the CNF and may be included in a single network access 
fee. Such fee schedules to be published by the CNF from time to time.

### 9.1.4 Fees for other Services

Other Service fees are not envisioned at this time but may be introduced by the CNF in the future and may or may not be 
included in a single network access fee. Such fee schedules to be published by the CNF from time to time.

### 9.1.5 Refund Policy

Refund Policy will be determined and published by the CNF.

## 9.2 Financial Responsibility

### 9.2.1 Insurance Coverage

CAs will be required to maintain general liability insurance proportionate to the specific risks of the service being 
offered.

### 9.2.2 Other Assets

No stipulation.

### 9.2.3 Insurance or Warranty Coverage for End-Entities

No stipulation.

## 9.3 Confidentiality of Business Information

### 9.3.1 Scope of Confidential Information

Information, including names of business entities and routing information, is procured for the express purpose of 
making such information available to other subscribers and relying parties within the Corda Network and is not 
considered confidential.

### 9.3.2 Information not within the Scope of Confidential Information

No stipulation.

### 9.3.3 Responsibility to Protect Confidential Information

No stipulation.

## 9.4 Privacy of Personal Information

### 9.4.1 Privacy Plan

CAs will comply with all relevant Data Protection legislation in the jurisdictions within which they operate.

### 9.4.2 Information Treated as Private

Any personally identifiable information (PII) relating to subscribers, relying parties or Registration Authorities and 
their employees to which the CA has access or control must be treated as private.

### 9.4.3 Information not Deemed Private

IP addresses of Corda nodes are not considered private information relating to individual persons unless the node is 
operated by, and certificated to, a named individual rather than a corporate entity will not be deemed private.

### 9.4.4 Responsibility to Protect Private Information

The CA will comply with all relevant Data Protection legislation in the jurisdictions within which they
operate.

### 9.4.5 Notice and Consent to Use Private Information

The CA will comply with all relevant Data Protection legislation in the jurisdictions within which they operate.

### 9.4.6 Disclosure Pursuant to Judicial or Administrative Process

No stipulation.

### 9.4.7 Other Information Disclosure Circumstances

No stipulation.

## 9.5 Intellectual Property Rights

The CA will not knowingly violate intellectual property rights held by others.

## 9.6 Representations and Warranties

No stipulation.

### 9.6.1 Representations and Warranties

The CA makes the below warranties to subscribers and relying parties (‘Certificate Users’) making valid use of such 
certificates as defined in the Participant Agreement of the Corda Network:

The CA represents and warrants to Certificate Users that, during the validity period of the Certificate, the CA has
complied with these requirements and its own Certification Practice Statement
in issuing and managing the Certificate.

The Certificate Warranties specifically include, but are not limited to, the following:

1. The CA warrants that they accurately described the procedure for verifying certificate details in their Certification 
Practice Statement and followed such procedure in the issuance of the Certificate;
2. The CA warrants that they, at the time of issuance, implemented a procedure for verifying that the Certificate 
Requester either had the right to use, or had control of, the organisation or person name supplied as Distinguished
Name for the X.509 certificate or was delegated such right or control by someone who had such right to use or control;
3. The CA warrants that they implemented a procedure for verifying that the named organisation or individual authorised 
the submission of the Certificate Signing Request and that the Certificate Requester was in a suitable position to 
request the Certificate on behalf of the named organisation or individual;
4. The CA warrants that, at the time of issuance, they implemented a commercially reason able procedure for ensuring 
that the information contained in the Certificate would not be misleading to relying parties;
5. The CA warrants that, if the CA and Subscriber are not Affiliated, the Subscriber and CA are parties to a legally 
valid and enforceable Subscriber Agreement that satisfies these Requirements, or, if the CA and Subscriber are 
Affiliated, the Certificate Requester acknowledged and accepted the Terms of Use;
6. The CA warrants that they maintain a 24 x 7 publicly-accessible Repository with current information regarding the 
status (valid or revoked) of all unexpired Certificates;
7. The CA warrants that they will revoke the Certificate for any of the reasons specified in this policy or separately 
described by the Corda Network Foundation in its rules and/or Participant Agreements; _and_
8. The CA warrants that, if they delegate tasks covered in this policy to a third party (Subordinate CA), they shall be 
responsible for the performance and warranties of the Subordinate CA, their compliance with this policy, and for all 
liabilities and indemnities of the Sub ordinate CA under this policy.

### 9.6.2 RA Representations and Warranties

No stipulation.

### 9.6.3 Subscriber Representations and Warranties

Prior to the issuance of any Certificate, the CA shall ensure that the subscriber requesting the Certificate has 
accepted the Terms of Use of the Corda Network as in force at the time of request and either enshrined in the 
Participant Agreement or any other such document as decreed by the Corda Network Foundation.

The CA will implement a process to ensure that the Participant Agreement is legally enforceable against the subscriber 
and applies to the particular Certificate to be issued as a result of the particular Certificate request. The CA may 
use an electronic or “click-through” Agreement provided that the CA has determined that such agreements are legally 
enforceable.

For reference, the Participant Agreement will contain provisions imposing on the subscriber (or subscriber’s agent) 
requesting the certificate the following obligations and warranties:

1. To provide accurate and complete information at all times to the CA, both in the Certificate Signing Request and as 
otherwise requested by the CA in connection with the issuance of the Certificate(s) to be supplied by the CA;
2. To take all reasonable measures to maintain sole control of, keep confidential, and properly protect at all times 
the Private Key that corresponds to the Public Key to be included in the requested Certificate(s) (and any associated 
activation data or device, e.g. password or token);
3. To review and verify the Certificate contents for accuracy before accepting and using it;
4. To install the Certificate only on servers that are accessible at the IP addresses supplied at the time of 
application, and to use the Certificate solely in compliance with all applicable laws and solely in accordance with the 
Participant or other relevant agreement;
5. To promptly cease using a Certificate and its associated Private Key, and promptly request the CA to revoke the 
Certificate, in the event that any information in the Certificate is, or becomes, incorrect or inaccurate, or there is 
any actual or suspected misuse or compromise of the Subscriber’s Private Key associated with the Public Key included in 
the Certificate;
6. To promptly cease all use of the Private Key corresponding to the Public Key included in the Certificate upon 
revocation of that Certificate for reasons of Key compromise;
7. To respond to the CA’s instructions concerning Key compromise or Certificate misuse within a specified time period; 
_and_
8. To acknowledge and accept that the CA is entitled to revoke the Certificate immediately if the Applicant were to 
violate the terms of the Participant of other agreement or if the CA discovers that the Certificate is being used to 
enable criminal activities such as phishing attacks, fraud, or the distribution of malware.

### 9.6.4 Relying Parties Representations and Warranties

No stipulation.

### 9.6.5 Representations and Warranties of Other Subscribers

No stipulation.

## 9.7 Disclaimers of Warranties

No stipulation.

## 9.8 Limitations of Liability

For delegated tasks, the CA and any third party may divide liability between themselves contractually, but the CA will 
remain fully responsible for the performance of all parties in accordance with this Policy, as if the tasks had not 
been delegated.

If the CA has issued and managed the Certificate in compliance with this Policy and its Certification Practice 
Statement, the CA may disclaim liability to relying parties or any other third parties for any losses suffered as a 
result of use or reliance on such Certificate beyond those specified in the CA’s Certification Practice Statement.

If the CA has not issued or managed the Certificate in compliance with applicable requirements and its Certification 
Practice Statement, the CA may seek to limit its liability to the Subscriber and to Relying Parties, regardless of the 
cause of action or legal theory involved, for any and all claims, losses or damages suffered as a result of the use or 
reliance on such Certificate by any appropriate means that the CA desires. If the CA chooses to so limit its liability, 
then the CA will include the limitations on liability in its Certification Practice Statement.

## 9.9 Indemnities

No stipulation.

## 9.10 Term and Termination

### 9.10.1 Term

No Stipulation

### 9.10.2 Termination

No stipulation

### 9.10.3 Effect of Termination and Survival

No stipulation

## 9.11 Individual Notices and Communications with Subscribers

The Policy Authority shall establish appropriate procedures for communications with CAs operating under this policy via
contracts or memoranda of agreement as applicable.

For all other communications, there is no stipulation.

## 9.12 Amendments

### 9.12.1 Procedure for Amendment

The Policy Authority shall review this CP at least once every year. Corrections, updates, or changes to this CP shall 
be publicly available. Suggested changes to this CP shall be communicated to the contact in section 1.5.2; such 
communication must include a description of the change, a change justification, and contact information for the person 
requesting the change.

### 9.12.2 Notification Mechanism and Period

No stipulation.

### 9.12.3 Circumstances under which OID must be Changed

No stipulation

## 9.13 Dispute Resolution Provisions

A dispute resolution mechanism may be operated by the Corda Network Foundation.

## 9.14 Governing Law

No stipulation.

## 9.15 Compliance with Applicable Law

No stipulation.

## 9.16 Miscellaneous Provisions

### 9.16.1 Entire Agreement

No stipulation.

### 9.16.2 Assignment

No stipulation.

### 9.16.3 Severability

No stipulation

### 9.16.4 Enforcement (Attorneys’ Fees and Waiver of Rights)

No stipulation.

### 9.16.5 Force Majeure

No stipulation.

## 9.17 Other Provisions

No stipulation.

# Appendix A – Acronyms

Selected acronyms and abbreviations that may be used in the guide are defined below.

AIA Authority Information Access

AOR Authorized Organizational Representative

CA Certification Authority

CNF Corda Network Foundation

COMSEC Communications Security

CP Certificate Policy

CPS Certification Practice Statement

CRL Certificate Revocation List

CSOR Computer Security Objects Registry

CSR Certificate Signing Request

CSS Certificate Status Server

DN Distinguished Name

ECDSA Elliptic Curve Digital Signature Algorithm

FIPS PUB (US) Federal Information Processing Standards Publication

FPKI Federal Public Key Infrastructure

HTTP Hypertext Transfer Protocol

IEC International Electrotechnical Commission

IETF Internet Engineering Task Force

IS Information System

LAN Local Area Network

ISO International Organization for Standardization

ITU-T International Telecommunications Union – Telecommunications Sector

NIST National Institute of Standards and Technology

NSTISSI National Security Telecommunications and Information Systems Security Instruction

OCSP Online Certificate Status Protocol

OID Object Identifier

PIN Personal Identification Number

PIV Personal Identity Verification

PKCS Public Key Cryptography Standards

PKI Public Key Infrastructure

PKIX Public Key Infrastructure X.509

PSS Probabilistic Signature Scheme

PZ Public Zone

RA Registration Authority

RZ Restricted Zone

RFC Request For Comments

RSA Rivest-Shamir-Adleman (encryption algorithm)

RSASSA RSA Signature Scheme with Appendix

SHA Secure Hash Algorithm

SP Special Publication

SSP-REP Shared Service Provider Repository Service Requirements

UPS Uninterrupted Power Supply

URL Uniform Resource Locator

UUID Universal Unique Identifier

VPN Virtual Private Network

WAP Wireless Access Point

# Appendix B – Document history

|Version|Date|Author|Change Details|
|-------|----|------|--------------|
|Draft 0.1|18th August 2017|Jonathan Sartin|Initial draft|
|Draft 0.2|21st August 2017|Jonathan Sartin|Spelling and grammar| corrections. Minor format changes. Limit level of table of contents. Clarify distribution of CPS.|
|Draft 0.3|21st August 2017|Jonathan Sartin|Further minor corrections, make references to X.500 consistent in section 3.1.|
|Draft 0.4|24th August 2017|Prepared for certificate profile changes from James Brown in section 7.|
|Draft 0.5|27th August 2018|Jonathan Sartin|Update policy in line with new Corda Network Foundation and certificate hierarchy.|
|Draft 0.6|27th August 2018|Jonathan Sartin / Nigel King|Further updates to align with separation of Corda Network Operator and Foundation. Updated section 9.|
|Draft 0.7|28th August 2018|Jonathan Sartin|Proof reading and correction – added some comments|
|Draft 0.8|29th August 2018|James Brown|Added certificate revocation information|
|Draft 0.9|4th September 2018|Jonathan Sartin|Further changes to reflect separation of Corda Network Governing Body and Corda Network Operator|
|Draft 0.10|5th September 2018|Jonathan Sartin|More technical detail, key sizes, usage periods uniqueness of names, recognition of trademarks.|
|Draft 0.11|20th September 2018|Jonathan Sartin|Incorporating proposed changed from Schellman.|
|Draft 0.12|2nd October 2018|Jonathan Sartin|Moved Document history to appendix. Added Wells Fargo as stakeholders|
