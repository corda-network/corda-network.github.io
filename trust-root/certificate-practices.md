# The Corda Network Certification Practice Statement

5th October 2018

Corda Network Certification Practice Statement 0.9

## Document Classification

In current state, this document is classified PUBLIC.

## External Distribution

This document is made available for public examination and dissemination. 

## 1 Introduction


### 1.1 Overview

The Corda Network Public Key Infrastructure (Corda Network PKI) has been established by the 
Corda Network Foundation to enable reliable and secure identity authentication of nodes in 
the Corda Network, and to facilitate the preservation of confidentiality and integrity of data in 
electronic transactions within that network. This document is issued by Corda Network Foundation to identify the practices 
and procedures that the Operator employs in its role as Corda Network Certification 
Authority, issuing certificates on behalf of the Corda Network Foundation.

### 1.2 Name and Identification

This document is the Corda Network Certification Practice Statement (CPS). It has been published 
in response to the Corda Network Certificate Policy (CP).

#### 1.2.1 Revisions

See Appendix C

### 1.3 PKI Participants


#### 1.3.1 Certification Authority

The term Certification Authority (CA) refers to the collection of hardware, software and operating 
personnel that create, sign, and issue public key certificates to subscribers.

This CPS covers all certificates issued and signed by R3 in its capacity of operator of the Corda 
Network Root CA, the Corda Network Subordinate CAs and the Corda Network Doorman CA. 
Collectively, these may be referred to as the ‘Corda Network CA’, or more simply the ‘CA’.

Root CAs

```
* Corda Network Root Certificate 
 Key: ECC 256, SHA- 256 
 Serial#: 10:e5:ff:3e:a9:be:d0: 
 SHA-1 Fingerprint: 23:01:21:0E:B9:99:37:D4:A4:AA:3A:15:9C:57:D7:8B:68:6A:07:5B
 Valid until: Jan 18, 2038
```

Corda Network Subordinate CAs

```
* Corda Network Authority CNA1
 Key: ECC-256, SHA-256 
 Serial: 34:6C:58:95:DC:68:30:70
 SHA-1 Fingerprint: 76:6E:BD:9B:55:CD:DB:FA:4A:9F:9F:EE:5F:0F:52:63:D7:C9:1B:C2
 Valid until: Jan 18, 2038

* Corda Network Authority CNA2 
 Key: ECC-256, SHA-256 
 Serial: 50:FE:91:B8:74:F0:0C:1E 
 SHA-1 Fingerprint: E9:84:7D:C9:F0:C4:71:47:DB:9B:C7:63:74:A9:EB:C8:7F:01:E4:3D
 Valid until: Jan 18, 2038

* Corda Network Authority CNA3 
 Key: ECC-256, SHA-256 
 Serial#: 63:FD:94:55:41:A4:41:D1
 SHA-1 Fingerprint: 27:5E:93:CA:81:B4:EB:14:75:61:06:AB:90:00:79:92:50:89:6D:D2
 Valid until: Jan 18 00:00:00 2038 GMT

* Corda Network Authority CNA4
 Key: ECC-256, SHA-256 
 Serial#: 2C:CB:A5:F7:BC:5D:F2:25 
 SHA-1 Fingerprint: 9B:5B:FA:D0:D1:9C:B1:25:76:D3:C9:A5:0D:29:73:1A:7E:E4:E3:0C
 Valid until: Jan 18, 2038

* Corda Network Authority CNA5
 Key: ECC-256, SHA-256 
 Serial#: 2F:9A: 24 :CA:C7:EB:8E:ED 
 SHA-1 Fingerprint: 45:25:AE:77:48:F0:62:AE:6D:B3:2D:86:BD:37:A8:4A:16:40:AF:79
 Valid until: Jan 18, 203 8

* Corda Network Authority CNA6
 Key: ECC-256, SHA-256 
 Serial: 12 :AF:2F:30:ED:1F:19:5D 
 SHA-1 Fingerprint: 82:7D:9D:FA:D0:D4:E3:F3:38:4F:F1:F7:40:DD:57:8B:C6:B8:86:6C
 Valid until: Jan 18, 2038

* Corda Network Authority CNA7
 Key: ECC-256, SHA-256 
 Serial#: 4E:B8:8B:4C:C7:4C:57:3E 
 SHA-1 Fingerprint=FE:ED:02:45:9E:7D:D5:D6:D0:E7:C0:F5:12:3E:0A:A5:16:97:4D:D7
 Valid until: Jan 18, 2038

* Corda Network Authority CNA8
 Key: ECC-256, SHA-256 
 Serial#: 59:A9:0F:AC:9F:27:3D:A0
 SHA-1 Fingerprint: 3A:C3:20:7A:75:C0:77:6F:68:F1:0C:5D:89:32:09:FF:00:7F:DD:FC
 Valid until: Jan 18, 2038
```

Corda Network Doorman CA

```
* Corda Doorman CA
 Key: ECC-256, SHA-256 
 Serial#: 4C:BF:B4:D5:12:4C:72:65
 SHA-1 Fingerprint: F2:C6:54:EC:4D:99:4F:3A:9C:FF:38:E2:6E:1A:72:6C:20:C9:5E:1B
 Valid until: Jan 18, 2038
```

#### 1.3.2 Registration Authorities

A Registration Authorities (RA) collects and verifies each subscriber’s identity and information that 
is to be entered into the subscriber’s public key certificate

RA functions for the Corda Network may be provided by the CA or by Corda Network Sponsors.

The CA will accept assertion of identity from Sponsors and issue certificates to relevant sponsored 
subscribers under defined conditions and where a Sponsor agreement is in place.

#### 1.3.3 Trusted Agents

A Trusted Agent is an entity who satisfies all the appointment requirements for an RA and who 
performs identity proofing as a proxy for the RA. The Trusted Agent records information from, and 
verifies presented credentials for, an applicant’s identity on behalf of the RA. Future versions of this 
CPS may identify the parties responsible for providing such services, and the mechanisms for determining their 
trustworthiness.

#### 1.3.4 Subscribers

In the Corda Network PKI, a subscriber is an individual or organization that is capable of using - 
and is authorized to use - the private key corresponding to the public key listed in a Corda Network 
certificate, and that: (1) is named in a certificate’s “subject” field; (2) has agreed to the terms of 
a subscriber agreement with the Corda Network Foundation; and (3) asserts the use of the 
key and certificate in accordance with any certificate policy asserted in the certificate.

In the Corda Network, certificates issued to subscribers will also grant those subscribers the ability 
to further issue certificates that can be used in a specific, constrained way within the Corda Network. These 
certificates will be used for the purpose of establishing TLS connections with other 
entities and to support verification of subscriber signatures by such entities. These certificates can 
be used to represent that entity only and therefore, for the purposes of this policy, are not considered to confer 
CA status upon the subscriber for any purposes other than the generation of subordinate certificates, bound to its own 
identity.

#### 1.3.5 Relying Parties

A Relying Party is an entity that relies on the validity of the binding of the Subscriber’s name to a 
public key. The Relying Party uses a Subscriber’s certificate to verify or establish the identity and 
status of a system or device. A Relying Party is responsible for deciding whether or how to check 
the validity of the certificate by checking the appropriate certificate status information. A Relying 
Party may use information in the certificate to determine the suitability of the certificate for a particular use.

#### 1.3.6 Network Participants

As all entities in the Corda Network other than CAs or RAs will be both subscribers and relying 
parties, this policy often uses the term “network participant”, or more simply, “participant” to refer 
to those entities.

### 1.4 Certificate Usage


#### 1.4.1 Appropriate Certificate Uses


Certificates issued by the Doorman CA will be used by Subscribers to further generate certificates 
for authenticated peer-to-peer messaging across The Corda Network by Corda Nodes, in addition 
to certificates for use in individual transactions (as described in 1.3.4).

#### 1.4.2 Prohibited Certificate Uses

Certificates issued by the CA are not proof of the trustworthiness of the Network Participant, nor 
do they indicate the Participants compliance with any law. By issuing a certificate, the CA merely 
confirms that it has used reasonable means to verify the information in the certificate before it was 
issued.

Certificates issued under this CPS are not intended for use outside of the Corda Network.

### 1.5 Policy Administration

#### 1.5.1 Organization Administering the Document

The Corda Network Security Team is responsible for the drafting, maintenance and interpretation 
of this CPS.

#### 1.5.2 Contact Person

Corda Network Security Team 
security@r3.com

#### 1.5.3 Person Determining CPS Suitability for the Policy

The Policy Authority of the Corda Network Foundation determines the suitability and applicability of this CPS.

#### 1.5.4 CPS Approval Procedures

The CA may change this CPS as deemed necessary. Changes that, in the judgement of the CA, 
will have no or minimal effect on the participants in the Corda Network may be made without 
consultation or notification.

Changes that, in the judgement of the CA will have significant impact on Participants in the Corda 
Network will only be made subject to the approval of Policy Authority of the Corda Network Foundation, and with 
prior notice to network participants.

Changes to the CPS will be published at https://trust.corda.network/.

### 1.6 Definitions and Acronyms

See appendix A

## 2 Publication and Repository Responsibilities

The CAs listed in this CPS are operated by:

R3 LLC (Corda Network Operator)
11 West 42nd Street 
Floor 8 
New York 
New York, 10036

### 2.1 Repositories

The CA maintains a repository which comprises its root and non-constrained subordinate certificates, Doorman 
certificate, current CP and CPS, and the most recent revocation information for 
certificates that it has issued.

The repository can be accessed at https://trust.corda.network/.

### 2.2 Publication of Certification Information

#### 2.2.1 Publication of Certificates and Certificate Status

The repository system shall be designed and implemented so as to provide 99% availability overall 
and limit scheduled down-time to 0.5% annually. Where applicable, the certificate status server 
(CSS) shall be designed and implemented so as to provide 99% availability overall and limit scheduled down-time to 
0.5% annually.

#### 2.2.2 Publication of CPS Information

The CPS shall be made freely available to network participants.

### 2.3 Time or Frequency of Publication

An updated version of the CPS will be made available to network participants within thirty days of 
the incorporation of changes.

### 2.4 Access Controls on Repositories

The repository is available to all network participants. The CA operates appropriate security controls to protect the 
repository from unauthorised modification or deletion.

## 3 Identification and Authentication

### 3.1 Naming

#### 3.1.1 Types of Names

The CA shall assign an X.50 1 Distinguished Name (DN) to each subscriber, which will be contained 
in the Subject name field of Corda Network node certificates.
Names must conform to the Corda Network [Allowable Entity Names policy](/policy/allowable-names) [1].


#### 3.1.2 Need for Names to Be Meaningful

Names used in certificates must represent an unambiguous identifier for the subscriber. Names 
should be meaningful enough for a human to identify the named entity.

#### 3.1.3 Anonymity or Pseudonymity of Subscribers

The CA shall not issue anonymous or pseudonymous certificates.

#### 3.1.4 Rules for Interpreting Various Name Forms

No stipulation.

#### 3.1.5 Uniqueness of Names

The CA must ensure that each of its subscribers is identifiable by a unique name. This is accomplished using the X.50 1 
DN which is assigned to the subscriber by the CA and recorded in the 
Subject name field of the issued certificate.

#### 3.1.6 Recognition, Authentication, and Role of Trademarks

The Corda Network is currently targeted at organisational applications, and therefore subscribers 
will therefore, at least in the initial life of the network, be associated with an organization, legal 
entity name, trade name or trademark.

The CA will ensure that the X.501 DN of any subscriber certificate issued accurately reflects the 
legal entity name of the subscriber as recorded in the applicable local registry.

### 3.2 Initial Identity Validation

#### 3.2.1 Method to Prove Possession of Private Key

The CA will only accept certificate signing requests from Corda nodes. Nodes will always format 
signing requests according to PKCS#10. All requests will include a digital signature on the request, 
created using the private key that corresponds to the public key in the Certificate Signing Request 
(CSR).

#### 3.2.2 Authentication of Organization Identity

Requests for subscriber certificates shall include the subscriber name, address, and documentation of the existence of 
the subscriber.

Direct Applications

Before issuing subscriber certificates, an authority for the CA shall verify the information, the authenticity of the 
requesting representative (‘the applicant’) and the representative’s authorization 
to act in the name of the subscriber.

The CA shall verify the existence of the subscriber organization by verifying the identity and address of the 
organization and that the address is the subscriber’s address of existence or operation. 
In the course of the above, the CA shall use documentation provided by, or through communication with, at least one of 
the following:

* Official communication with the organization (authenticated email or signed letter with 
 official company letterhead) which names the applicant and their position within the subscriber;
* A third-party database that is periodically updated and considered a reliable data source; 
 _or_
* A site visit by the CA or a third party who is acting as an agent for the CA.

The CA may use the same documentation or communication described in above to verify both 
the subscriber’s identity and address.

Sponsored Applications

Where authorised sponsors are involved, the CA shall undertake:

1. Validation of the format and source of the CSR sent by the sponsor and that the request 
 is from an authorised sponsor at the time of receipt of CSR.
2. Uniqueness checking against all previously issued subscriber certificates. Any CSRs with 
 identical information to existing subscriber certificates will be rejected.

#### 3.2.3 Authentication of Individual Identity

The Corda Network is currently targeted at organisational applications, and no applications from 
individual subscribers will be accepted.

#### 3.2.4 Non-Verified Subscriber Information

Information that is not verified shall not be included in certificates.

#### 3.2.5 Validation of Authority

Before issuing a certificate, the CA shall validate the applicant’s authority to act in the name of 
the organization.

This check will be performed by ensuring that the applicant named on the CSR is also:

1. Listed as a named contact in the contract signed by a sponsor organisation where such 
 sponsor exists (also known as a ‘Business Network Operator’ or BNO); _and_

2. Is verified by the HR department or senior manager at the subscriber organisation as a 
 current employee with role relevant to the application (this can be achieved by confirmation of email cc’d by 
 applicant to an HR representative or senior manager at the subscriber organisation). The CA shall also undertake 
 reasonable checks to ensure that the 
 endorsing contact at the subscriber is a current employee with relevant role.

#### 3.2.6 Criteria for Interoperation

No stipulation

### 3.3 Identification and Authentication for Re-key Requests

#### 3.3.1 Identification and Authentication for Routine Requests

Subscriber certificates, as defined by their unique elements (subject DN and public key) can only 
be issued once. If a subscriber for any reason needs a new certificate they will need to revoke the 
existing certificate and re-apply for a replacement in the normal way (see section 4.9). The subject 
DN and existing key pair may be retained in specified circumstances (See Section X). In this way, 
the CA ensures that there is only ever one certificate for the subscriber in operation at any one 
time (ignoring subordinate subscriber certificates such as TLS and Identity certificates).

#### 3.3.2 Identification and Authentication for Re-key after Revocation

In the event of certificate revocation, issuance of a new certificate shall always require that the 
party complete the initial registration process per Section 3.2 above.

### 3.4 Identification and Authentication for Revocation Request

Revocation requests must be authenticated in the same manner as the original Certificate Signing Request. Once a 
certificate is revoked, it cannot be reinstated.

## 4 Certificate Life-Cycle Operational Requirements

### 4.1 Certificate Application

The certificate application process must provide sufficient information to:

* Establish the applicant’s authorization (by the subscriber or sponsoring organization) to obtain a certificate. (per 
Section 3.2.3);
* Establish and record identity of the applicant. (per Section 3.2.3);
* Obtain the subscriber’s Corda node public key from the applicant and verify the applicant’s possession of the private 
key for each certificate required. (per Section 3.2.1); _and_
* Verify any other information requested for inclusion in the certificate.

These steps may be performed in any order that is convenient for the CA and applicant that does 
not compromise security, but all must be completed before the CA can issue the certificate.

4.1.1 Who can Submit a Certificate Application?
-----------------------------------------------
A certificate application may be submitted to the CA by the subscriber authorised organisational 
representative (AOR), or a sponsor/RA on behalf of the subscriber.

4.1.2 Enrolment Process and Responsibilities
--------------------------------------------
The CA retains ultimate discretion over the admission of any subscriber to the network, operating 
on behalf of the Corda Network Foundation and according to its rules as published at the 
time.

The CA is responsible for ensuring that subscriber identities are verified according to the strictures 
of this CPS, the CA holds no accountability for the consequences of misrepresentation by subscriber applicants.

The CA is responsible for ensuring that sponsored applications are only accepted from sponsors 
with whom a valid and current contractual relationship exists with the CA or Corda Network Foundation.

### 4.2 Certificate Application Processing

Information in certificate applications must be verified as accurate before certificates are issued.

#### 4.2.1 Performing Identification and Authentication Functions

The identification and authentication of the subscriber must meet the requirements specified for 
subscriber authentication as specified in Sections 3.2 and 3.3.

#### 4.2.2 Approval or Rejection of Certificate Applications

Any certificate application that is received by a CA for which the identity and authorization of the 
applicant has been validated, will be duly processed. However, the CA will reject any application 
for which such validation cannot be completed, or when the CA has cause to lack confidence 
in the application or certification process.

#### 4.2.3 Time to Process Certificate Applications

Certificate applications will be processed as soon as practicable and in accordance with the 
performance criteria set out in the published service level agreement.

### 4.3 Certificate Issuance

#### 4.3.1 CA Actions during Certificate Issuance

Upon receiving the request, the CA or RA will:

* Verify the identity of the subscriber as specified in Section 3.2;
* Verify the authority of the applicant and the integrity of the information in the certificate 
 request as specified in Section 4.1;
* Build and sign a certificate if all certificate requirements have been met (in the case of an 
 CA); _and_
* Make the certificate available to the subscriber after confirming that the subscriber has 
 formally acknowledged their obligations as described in Section 9.6.3.

The certificate will not be signed until all verifications and modifications, if any, have been completed to the CA’s 
satisfaction.

All authorization and other attribute information received from a prospective subscriber shall be 
verified by the CA or RA before inclusion in a certificate.

#### 4.3.2 Notification to Subscriber by the CA of Issuance of Certificate

The CA shall inform the subscriber (or other certificate subject) of the creation of a certificate and 
make the certificate available to the subscriber. Such notification is achieved by the CA node 
(‘the Doorman node’) responding to the subscriber node with a signed subscriber certificate 
when polled with the unique CSR identifying number by the subscriber node. It is the responsibility 
of the subscriber node operator to regularly poll the Doorman for such signed certificate.

In the event of CSRs failing automated validation checks at the Doorman (incorrectly formatted, 
non-unique or containing invalid data) the latter will respond with an appropriate error message 
when polled with the CSR identifying number by the subscriber node.

For CSRs passing automated validation checks but which nevertheless fail other checks undertaken by the CA (such as 
authorisation checks), the CA staff will contact the named contact on 
the CSR (which will be a sponsor contact in the case of sponsored nodes) to update them with 
the status of the request.

### 4.4 Certificate Acceptance

Subscriber nodes will authenticate the received CA certificate by validating that the CA signature 
resolves back to the Trust Root published by the Corda Network Foundation. It is the responsibility of the subscriber 
to ensure this check is carried out and not use any certificate which fails 
this check.

#### 4.4.1 Conduct Constituting Certificate Acceptance

Failure to object to the certificate or its contents shall constitute acceptance of the certificate.

#### 4.4.2 Publication of the Certificate by the CA

As specified in Section 2.1, all CA certificates shall be published in repositories.

This policy makes no stipulation regarding publication of subscriber certificates.

#### 4.4.3 Notification of Certificate Issuance by the CA to Other Entities

The Policy Authority must be notified whenever a CA operating under this policy issues a CA or 
subscriber certificate.

### 4.5 Key Pair and Certificate Usage


#### 4.5.1 Subscriber Private Key and Certificate Usage

The intended scope of usage for a private key is specified though certificate extensions, including 
the key usage extensions, in the associated certificate.

The private key is used by the subscriber to sign:

1. TLS certificates created by the subscriber node for the purpose of securing communications with the nodes of other 
authorised Corda Network subscribers. Such TLS certificates 
 may be revoked and reissued from time to time by the subscriber node; _and_
2. Identity certificates which are used by the subscriber node to sign transactions on the 
 ledger on behalf of the subscriber entity. Such signatures allow third party authentication 
 of the acceptance of the signed transaction by the subscriber entity. The exact legal sta tus of such signatures shall 
 be determined by the surrounding legal framework governing 
 business between respective entities on the ledger, including any commercial contracts 
 in place and relevant jurisdictional laws and regulations.

#### 4.5.2 Relying Party Public Key and Certificate Usage

Relying parties use subscriber certificates and associated public keys to secure connections and 
authenticate messages from other Corda Network subscribers. Certificates may specify restrictions 
on use though critical certificate extensions, including the basic constraints and key usage extensions.

The CA shall issue CRLs specifying the current status of all unexpired certificates issued under this 
PKI scheme. It is a condition of use of Corda Network that relying parties process and comply with 
this information whenever using certificates in a transaction.

### 4.6 Certificate Renewal

Certificate renewal will result in the creation of a new certificate with the same name, key, and 
other information as the old one, but with a new, extended validity period and a new serial number.

#### 4.6.1 Circumstance for Certificate Renewal

Corda Network subscriber certificates are intended to be long-lasting, in line with the identities on 
the ledger they are representing. Renewals will be processed as for the original certificate, with 
verification of the identity details as per the original application and initiated by a CSR.

It expected that other events will have led to the revocation of a certificate (see section 4.9) 
before its validity period expires.

#### 4.6.2 Who May Request Renewal

Any subscriber whose certificate is close to expiry or has expired may request renewal.

#### 4.6.3 Processing Certificate Renewal Requests

Certificate renewal requests will be processed in the same way as original certificate signing requests.

#### 4.6.4 Notification of New Certificate Issuance to Subscriber

New certificate issuance notification will take place as per issuance of the original certificate.

#### 4.6.5 Conduct Constituting Acceptance of a Renewal Certificate

As per acceptance of the original certificate.

#### 4.6.6 Publication of the Renewal Certificate by the CA

As per publication of the original certificate.

#### 4.6.7 Notification of Certificate Issuance by the CA to Other Entities

As per notification of the original certificate issuance to other entities.

### 4.7 Certificate Re-key

Re-keying a certificate consists of creating replacement certificate, containing an updated public key and serial number 
while retaining the remaining contents of the old certificate that describe 
the subject. The new certificate may be assigned a different validity period, key identifiers, specify 
a different CRL distribution point, and may be signed with a different key.

Because the public key is included in the uniqueness checks a Corda Network certificate, a re-key 
is equivalent to a revocation and reissue (See section 4.9). Original certificates must always be 
revoked to ensure that subscribers are only ever represented by a single subscriber certificate and 
key pair.

### 4.8 Certificate Modification

As per re-key requests, any modification to a subscriber certificate requires revocation of the original (see section 4.9) 
and reissue of a new subscriber certificate.

### 4.9 Certificate Revocation and Suspension

Certificate Revocation in the Corda Network is still being finalised, and aspects could change in 
the future. In particular it is likely that revocation of Corda certificates could be implemented by 
an entirely separate mechanism to the CRL facility provided by X.509 certificates.

The CA will issue CRLs covering all unexpired certificates issued except for OCSP responder (if one 
exists).

The CA will make available to network participants a description of how to obtain revocation 
information for the certificates they publish, and an explanation of the consequences of using 
dated revocation information. This information shall be given to subscribers during certificate request or issuance and 
shall be readily available to any potential relying party.

Revocation requests must be authenticated. See Section 3.2 for more details.

Certificate suspension is not supported by this CPS.

#### 4.9.1 Circumstances for Revocation

Corda Network subscriber certificates are intended to be long-lived, and revocation only used in 
specific circumstances:

1. The subscriber entity wishes to leave the Corda Network, and has either redeemed all 
 ledger assets from the network or transferred them to other parties;
2. The subscriber can be shown to have violated the stipulations of its subscriber agreement to the extent that the 
Corda Network Foundation requires that the entity 
 leave the Corda Network;
3. There is reason to believe that the private key has been compromised and a new key 
 pair is needed (key rotation); _or_
4. Attributes of the subscriber entity have changed such that the current certificate is no 
 longer applicable, or the certificate renewal period is up, and a new certificate for 
 the same entity is needed utilising the same key pair.

It should be noted that orderly departure from the Corda Network (1) will be the case in the majority of corporate 
transactions which change the fundamental nature of the legal identity, such 
as mergers, splits, acquisitions, name changes etc. In general, the action will result in a new legal 
identity or identities and a transfer of assets from the old to the new.

In the case of revocation due to key compromise ( 3 ), it will be the subject of legal agreement at 
the time as to what action applies to assets effectively frozen at the time of revocation. This situation is expected 
to only occur in extremis, as a revoked certificate cannot be reinstated, and so 
in the normal course of events either any cause of dispute is remedied between the parties effected and/or assets are 
transferred before revocation takes place.

Attribute changes ( 4 ) are expected to be rare, and only needed in instances where privileges assigned to the identity 
through the certificate need to be adjusted.

In all of the cases above, if a new subscriber certificate is needed (with the same or new identity) 
it will be requested and communicated in the same way as for new entrants to the network and 
under the conditions detailed in section 3.2 through to 4.4.

The transfer of assets held on the ledger under a certificate and key pair pending revocation to 
different legal identities or to the same legal identity with a new certificate (same or new key pair) 
is not the subject of this Certificate Practice Statement. Processes and procedures to achieve this 
same are described elsewhere in the Corda Network documentation.

Whenever any of the above circumstances occur, the associated certificate shall be revoked 
and placed on the CRL. Revoked certificates shall be included on all new publications of the 
certificate status information until the certificates expire.

#### 4.9.2 Who Can Request Revocation

Within the Corda Network, certificate revocation can be requested either by the CA, the Corda 
Network Governing Body, a subscriber or its sponsor.

#### 4.9.3 Procedure for Revocation Request

Due to the impact of revocation on the assets held under the certificate being revoked, the conditions under which such 
revocations can occur will be precisely defined in contractual agreements between the parties concerned. This CPS 
assumes that the relevant conditions have been 
observed before revocation occurs and describes the process of revocation, rather than the legal 
conditions under which it can occur. It is therefore a key assumption of this document that all 
business activities within the Corda Network are carried out under an appropriate legal and contractual framework which 
is outside the scope of this document.

Where the CA is revoking a certificate on request from the subscriber, adequate steps will be 
taken to authenticate the request, including verifying that the requester is suitably authorised 
within the subscriber entity to make the request.

#### 4.9.4 Procedure for Revocation Request

Requests to revoke a certificate must be made via the published channel of the CA and shall:

1. Identify the certificate to be revoked;
2. Detail the reason for revocation;
3. Only be accepted either from the named contacts in the original certificate request or 
 from subsequent names provided by the subscriber entity and approved by a relevant 
 officer of that entity in a separate communication prior to revocation; _and_
4. Be separately endorsed as genuine by an officer of the subscriber entity via secure email 
 or hard copy with signature.

Revocation requests must be endorsed by at least two officers of the company and provenance 
be provided to demonstrate the grounds for revocation including satisfaction of all relevant contractual conditions, 
proof that all procedures to remedy have completed their course and to ensure legal validity of the action.

#### 4.9.5 Revocation Request Grace Period

There is no grace period for revocation under this policy.

#### 4.9.6 Time within which CA must Process the Revocation Request

CAs will revoke certificates as quickly as practical upon receipt of a proper revocation request. 
Revocation requests shall be processed before the next CRL is published, excepting those requests 
received within two hours of CRL issuance.

#### 4.9.7 Revocation Checking Requirements for Relying Parties

It is the responsibility of relying parties to ensure that they regularly download and check the CRL, 
and any activity conducted by them with parties appearing on the list is at their own risk.

#### 4.9.8 CRL Issuance Frequency

CRLs shall be issued periodically by the CA. Certificate status information may be issued more 
frequently than the issuance frequency described below. Certificate status information shall be 
published no later than the next scheduled update, this will facilitate the local caching of certificate status 
information.

For the status of Doorman-issued Node Certificates: the CRL is updated and reissued at least once every seven (7) days, and the value of the nextUpdate field is not more than ten (10) days beyond the value of the thisUpdate field.

For the status of node TLS certificates: the CRL is updated and reissued at least once every seven (7) days, and the value of the nextUpdate field is not more than ten (10) days beyond the value of the thisUpdate field.

For the status of all other certificates issued by the Corda Network Operator: the CRL will be issued at least (i) once every twelve (12) months and (ii) within 24 hours after revoking a certificate. The value of the nextUpdate field is not more than twelve months beyond the value of the thisUpdate field. Circumstances related to emergency CRL issuance are specified in section 4.9.12.

#### 4.9.9 Maximum Latency for CRLs

Following certificate revocation, the Certificate Revocation List will be updated according to the 
SLAs published at the time.

Irrespective of the above each CRL shall be published no later than the time specified in the _nextUpdate_ field of the 
previously issued CRL for same scope.

#### 4.9.10 On-Line Revocation/Status Checking Availability

On-line certificate status protocol (OCSP) is not currently supported.

#### 4.9.11 On-line Revocation Checking Requirements

No stipulation.

#### 4.9.12 Other Forms of revocation Advertisements Available

The CA may also use other methods to publicize the certificates it has revoked. Details of alternative forms of 
revocation advertisement will be provided through updates to this CPS.

#### 4.9.13 Special Requirements Related to Key Compromise

Due to the significance of private keys in the Corda Network, holders of such keys are expected 
to take measures, appropriate to the value of assets that the keys control, to ensure their confidentiality. Should a 
party suspect that a private key has been subject to unauthorised disclosure , 
they will seek to lock down the assets at risk whilst a new key pair is generated. However, subscribers must also be 
able to control the assets secured by the compromised key during and after key 
regeneration. In the absence of any separate arrangement for off-ledger recreation or reissue of 
ledger assets, the compromised key must be retained in order to take any action with respect to 
such assets on the ledger.

It is therefore expected that either:

1. Separate contingency arrangements are put in place by subscribers to cover the risk of 
 key loss such that revocation can be used to prevent the assets on ledger in original form 
 being transacted at any point in the future. In this case, the subscriber will have arrangements in place to recreate 
 the assets and ownership records on an entirely separate in stance (either in the Corda Network or outside)
2. Provided the key alone has been compromised (and the integrity of the node and its vault 
 is not in question), the subscriber may be able to transfer the assets with the existing key to 
 a separately commissioned node under a new key and certificate. This also assumes that 
 integrity of the new node is similarly assured.

Aside from the above, there are no special requirements relating to key compromise. Revocation 
of the certificate, at the discretion of the subscriber and at a time of their choosing may be accomplished according 
to the previous sections of this document.

#### 4.9.14 Circumstances for Suspension

Suspension of certificates is not currently supported.

#### 4.9.15 Who Can Request Suspension

Not applicable.

#### 4.9.16 Procedure for Suspension Request

Not applicable.

#### 4.9.17 Limits on Suspension Period

Not applicable.

#### 4.9.18 Circumstances for Restoration

Not applicable.

#### 4.9.19 Who Can Request Restoration

Not applicable.

#### 4.9.20 Procedure for Restoration Request

Not applicable.

### 4.10 Certificate Status Services

Certificate status is provided by the CA via published CRLs.

### 4.11 End of Subscription

Subscriber certificates are either renewed at the end of their life or allowed to expire as all assets 
under their control have been transferred. In each case, the action to be taken is at the discretion 
of the subscriber, provided relevant contractual arrangements are continued.

### 4.12 Key Escrow and Recovery

Escrow of private keys is not supported. Subscribers are responsible for the custody and security of 
their private keys at all times.

#### 4.12.1 Key Escrow and Recovery Policy and Practices

Not supported.

#### 4.12.2 Session Key Encapsulation and Recovery Policy and Practices

Session key encapsulation and recovery is not supported.

## 5 Facility, Management, and Operational Controls


### 5.1 Physical Controls

The CA infrastructure is located in a secure facility within the Interxion London Campus and in 
Microsoft’s Azure data centres. Critical CA functions (such as certificate signing activities) are carried out on 
dedicated infrastructure. Detailed security procedures have been put in place and 
are followed the CA and by supplier organisations, that prohibit unauthorized access and entry 
into the areas of the facilities in which the CA systems reside.

#### 5.1.1 Site Location and Construction

Site locations that contain dedicated CA infrastructure have been assessed by the CA for their 
physical security. All buildings are solidly constructed to prevent unauthorised entry.

#### 5.1.2 Physical Access

The CA has in place appropriate physical security controls to restrict access to facilities providing 
CA services.

Access to critical hardware and software that used to issue certificates is limited to those performing a trusted 
role as described in section 5.2. Two-person access is enforced for these systems and 
they are locked inside dedicated cabinets within an Interxion data centre. All CA private keys are 
stored in hardware security modules that are validated to FIPS 140-2 Level 3 or higher and that are 
physically tamper-evident and tamper resistant.

Physical access to hardware and software that provides a supporting capability to the CA will be 
controlled according to the information security control environment documented by the infrastructure provider 
(Microsoft Azure).

#### 5.1.3 Power and Air Conditioning

The CA facilities are connected to UPS and emergency power generator and are equipped with 
cooling systems.

#### 5.1.4 Water Exposures

The CA facilities are equipped with controls which protect CA systems from damage resulting from 
water leakage.

#### 5.1.5 Fire Prevention and Protection

The CA facilities are equipped with fire detection alarms and protection equipment.

#### 5.1.6 Media Storage

No stipulation.

#### 5.1.7 Waste Disposal

The CA takes reasonable steps to ensure that all media used for the storage of sensitive information such as keys, 
activation data or configuration information is appropriately purged or destroyed according to a defined data 
destruction standard before being released for disposal

#### 5.1.8 Off-Site Backup

The CA will maintain a backup facility for its CA infrastructure, which will also hold copies of the 
CA private keys for redundancy. The backup facilities will have security controls which are equivalent to those 
operated at the primary.

The CA maintains sharded, encrypted backups of the CA private keys at multiple secure, geographically separate, 
storage facilities. Access to multiple facilities is required to recover key material and the backups can survive total 
loss of 33% of the storage facilities.

### 5.2 Procedural Controls


#### 5.2.1 Trusted Roles

All personnel who have access to, or control over cryptographic operations of the CA that affect 
the issuance, use, and management of certificates are considered as serving in a trusted role. 
Such personnel include, but are not limited to, members of the Corda Network

#### 5.2.2 Number of Persons Required per Task

Where multi-party control is required, all participants shall hold a trusted role. Multi-party control 
shall not be achieved using personnel that serve in a Security Auditor role with the exception of 
audit functions. The following tasks shall require two or more persons:

* Generation, and backup of CA keys;
* Activation of intermediate CA keys (note that operational CA keys, such as the doorman 
 key may be activated by a single person with multi-factor authentication);
* Performance of CA administration or maintenance tasks;
* Archiving or deleting CA audit logs; _or_
* Physical access to CA equipment.

#### 5.2.3 Identification and Authentication for Each Role

Individuals holding trusted roles shall identify themselves and be authenticated by the CA before 
being permitted to perform any actions set forth above for that role or identity. CA Operations 
Staff shall authenticate using a credential that is distinct from any credential they use to perform 
non-trusted role functions. This credential shall be generated and stored in a system that is protected to the same 
level as the CA system.

CA shall require, at a minimum, strong authenticated access control for remote access using multifactor authentication. 
Examples of multi factor authentication include use of a password or PIN 
along with a time-based token, digital certificate on a hardware token or other device that enforce a policy of what a 
user has and what a user knows.

CA equipment shall require, at a minimum, authenticated access control (e.g., strong passwords) 
for local multi-party access.

Individuals holding trusted roles shall be appointed in a manner that conforms to the CA’s Access 
Control and User Access Management policy.

Users shall authenticate themselves to all aspects of the network (servers, operating systems, applications, databases, 
processes, and so on) before they can access that resource.

Any role that requires the activation of CA private keys, whether local or remote requires multifactor authentication to 
activate those keys. The authenticator token used to identify the user 
must be dedicated to the activation of that cryptographic material only.

Where more than one person is required to carry out a task, all persons are required to provide 
multi-factor authentication.

Authentication: Passwords and Accounts

When the authentication mechanism uses operator selectable passwords, strong passwords shall 
be employed. Passwords for CA authentication shall be different from non-CA systems.

The CA shall have the minimum number of accounts that are necessary to its operation. Account 
access shall be locked after an appropriate number of unsuccessful login attempts. Restoration 
of access shall be performed by a different person who holds a trusted role.

#### 5.2.4 Roles requiring separation of duties

Doorman CA roles

Day to day operations of the Corda Network Doorman CA requires three trusted roles to be segregated. Persons holding 
any one of these roles, may not perform of hold the role of any other 
within this group:

* Checker - carries out identity proofing for the network participant;
* “Four-Eyes” Checker – caries out a 10% random sample check on the checkers work; _or_
* Certificate Signer – activates the Doorman key to complete the signing procedure for the 
 participant’s CSR.

Subordinate CA roles

Subordinate CA keys may only be only be activated by dual control by individuals holding the 
Crypto Officer trusted roles. Individuals assuming the Crypto Officer role may not hold any other 
roles within the CA.

Common roles

HSM Administrators may carry out limited HMS admin activities alone. HSM Administrators may not 
perform or hold the role of HSM Oversight.

The presence of a personal holding the HSM Oversight role is required to enforce dual control for 
critical HSM Administrative functions, HSM Oversight users may not hold the role of HSM Administrator.

Individuals serving as Security Auditors shall not perform or hold any other trusted role.

Only an individual serving in a Security Auditor role may perform internal auditing functions, with 
the exception of those security audit functions (e.g., configuring, archiving, deleting) that require 
multi-person control.

An individual that performs any trusted role shall only have one identity when accessing CA equipment.

### 5.3 Personnel Controls


#### 5.3.1 Qualifications, Experience, and Clearance Requirements

The CA has implemented policies for verifying the identity and trustworthiness of its personnel. Furthermore, the CA 
evaluates the performance of its staff to ensure that they perform their duties in 
a satisfactory manner.

All individuals appointed to any trusted role must meet the following requirements:

* Be employees of or contractor/vendor of the CA and bound by terms of employment or 
 contract;
* Be appointed in writing;
* Have successfully completed an appropriate training program;
* Have demonstrated the ability to perform their duties;
* Have no other duties that would interfere or conflict with their responsibilities as defined in 
 section 5.2.1; _and_
* Have not been previously relieved of trusted role duties for reasons of negligence or non performance of duties.

#### 5.3.2 Background Check Procedures

**Note to reviewer:** Background checks have not historically been conducted to this level for CA 
personnel. This will be changed in the near future and background checks for all CA personnel 
will be brought into line with this, and retrospective background checks will be carried out for all 
persons fulfilling trusted roles. Should any person fail to pass a retrospective background check, 
the Corda Network Policy Authority must be notes, and a security incident raised. The Policy Authority will decide such 
remedial action as is necessary to preserve the integrity of the network CA.

Prior to personnel assuming a Trusted Role, the CA shall conduct background checks (in accordance with local privacy 
laws) which will include a reasonable subset of the following:

* Confirmation of previous employment;
* Check of professional reference;
* Confirmation of the highest or most relevant educational degree obtained;
* Search of criminal records (local, state or provincial, and national); and
* Check of credit/financial records; _and_
* Identity verification

#### 5.3.3 Training Requirements

All personnel performing duties with respect to the operation of the CA personnel shall receive 
comprehensive training. Training shall be conducted in the following areas:

* CA security principles and mechanisms;
* All PKI software versions in use on within the CA system;
* All PKI duties they are expected to perform;
* Disaster recovery and business continuity procedures; _and_
* Stipulations of these practices and any specific policies to which the role is subject.

#### 5.3.4 Retraining Frequency and Requirements

All personnel in trusted roles are required to maintain skill levels consistent with the tasks assigned 
to them. As such, the CA requires those personnel to undergo retraining at least annually and also

when the systems they operate, or the security control environment, is subject to significant 
change.

#### 5.3.5 Job Rotation Frequency and Sequence

No stipulation.

#### 5.3.6 Sanctions for Unauthorized Actions

The CA will impose sanctions on personnel if they perform unauthorized acts, abuse their authority 
or for other appropriate reasons, at the discretion of the CA management.

#### 5.3.7 Independent Contractor Requirements

Independent contractors assuming trusted roles shall be subject to all requirements stipulated in 
this document.

Independent contractors who have not completed or passed the background check procedures 
specified above must be escorted and directly supervised by a person holding trusted role at all 
times when present at CA facilities.

#### 5.3.8 Documentation Supplied to Personnel

Documentation sufficient to define duties and procedures for each role shall be provided to the 
personnel filling that role.

### 5.4 Audit Logging Procedures


#### 5.4.1 Types of Events Recorded

The following events are recorded:

* CA key lifecycle management events 
 o Key generation, backup, storage, recovery, archival and destruction 
 o Cryptographic device lifecycle events
* Participant events 
 o Request to create a certificate 
 o Request to revoke a certificate
* CA and Participant Certificate lifecycle events 
 o Verification activities stipulated in the CP and this CPS 
 o Acceptance and rejection of certificate requests 
 o Key generation 
 o Key compromise notification 
 o Creation of a certificate 
 o Delivery of a certificate 
 o Revocation of a certificate 
 o Generation of a Certificate Revocation List
* Actions by Trusted Personnel 
 o Login events and use of identification and authentication mechanisms 
 o Changes to CA policies 
 o Changes to CA keys 
 o Configuration changes to the CA

* Security Events 
 o Successful and unsuccessful PKI system access attempts 
 o PKI and security system actions performed 
 o Security profile changes; 
 o System crashes, hardware failures, and other anomalies 
 o Firewall and router activities 
 o Entries to and exits from the CA facility

Log entries include the following elements:

1. Date and time of entry;
2. Identity of the person making the journal entry; _and_
3. Description of the entry.

Logging is automated wherever possible. Where necessary, manual logging and record keeping 
methods may be used.

#### 5.4.2 Frequency of Processing Log

Audit logs are reviewed on an as-required basis.

#### 5.4.3 Retention Period for Audit Logs

The CA retains audit logs for a period of seven years, or longer, if required by law.

#### 5.4.4 Protection of Audit Log

Multiple copies of audit logs are stored in geographically separate locations, protected by appropriate physical and 
logical access controls.

#### 5.4.5 Audit Log Backup Procedures

Audit logs and audit summaries are be backed up on a defined schedule.

#### 5.4.6 Audit Collection System (Internal vs. External)

No stipulation.

#### 5.4.7 Notification to Event-Causing Subject

There is no requirement to notify a subject that an event was audited. Events that are deemed 
security critical will be escalated to the CA’s incident response team.

#### 5.4.8 Vulnerability Assessments

The CA operates a vulnerability assessment program that combines regular in-house testing using 
commercial vulnerability assessment tools, internal security code reviews and external vulnerability 
and penetration testing.

### 5.5 Records Archival


#### 5.5.1 Types of Events Archived

Records that should be archived are specified in section 5.4.1.

#### 5.5.2 Retention Period for Archive

Archive records must be retained for the lifetime of the Corda Network at the CA’s discretion. The 
CA retains audit logs for a period of seven years, or longer, if required by law.

#### 5.5.3 Protection of Archive

A backup of archive information is retained in a geographically separate location with similar 
security and availability protection as the primary environment.

#### 5.5.4 Archive Backup Procedures

Backup and recovery procedures exist to recover systems in the event of loss or destruction of the 
primary archives.

#### 5.5.5 Requirements for Time-Stamping of records

Archive records are automatically time-stamped as they are created. Where practical, accuracy of timestamps will be 
ensured by synchronizing the hosts to a network time source.

#### 5.5.6 Archive Collection System (Internal or External)

Archive data may be collected in any expedient manner.

#### 5.5.7 Procedures to Obtain and Verify Archive Information

No stipulation.

### 5.6 Key Changeover

The Corda Network Subordinate CAs and the Corda Network Doorman CA will only be rotated in 
extremis. Changeover of intermediate certificates will involve a re-enactment of the initial key 
generation ceremony, in which the Corda Network Foundation’s root key will be required to 
sign the Subordinate CA’s Certificate Signing Requests.

Changeover of Network Participant keys can be accomplished by the same procedure as was 
originally used to provide the operational certificate.

CA’s signing key shall have a validity period as described in section 6.3.2.

### 5.7 Compromise and Disaster Recovery


#### 5.7.1 Incident and Compromise Handling Procedures

If a disaster causes the CA to become inoperative, the CA will re-initiate its operations on replacement hardware at a 
similarly secure facility after verifying the integrity and confidentiality of the 
CA systems.

The CA maintains a security incident response plan.

If compromise of a CA is suspected, an independent, third-party investigation shall be performed 
in order to determine the nature and the degree of damage. Certificates issued by that CA shall 
be stopped immediately upon detection of a compromise. If a CA private signing key is suspected 
of compromise, the procedures outlined in Section 5.7.3 shall be followed. Otherwise, the scope 
of potential damage shall be assessed in order to determine if the CA needs to be rebuilt, only 
some certificates need to be revoked, and/or the CA private key needs to be declared compromised. The independent, 
third-party investigating party shall make the determination that a CA 
private key has been compromised.

The CA shall notify the Corda Network Foundation if any of the following occur:

* Suspected or detected compromise of any CA system or subsystem
* Physical or electronic penetration of any CA system or subsystem
* Successful denial of service attacks on any CA system or subsystem
* Any incident preventing a CA from issuing and publishing a CRL prior to the time indicated 
 in the _nextUpdate_ field in the currently published CRL suspected or detected compromise 
 of a certificate status server (CSS) if: 
 o the CSS certificate has a lifetime of more than <72> hours; and 
 o the CSS certificate cannot be revoked

#### 5.7.2 Computing Resources, Software, and/or Data Are Corrupted

When computing resources, software, and/or data are corrupted, the CA shall respond as follows:

* Notify Corda Network Foundation as soon as possible.
* Ensure that the system’s integrity has been restored prior to returning to operation and 
 determine the extent of loss of data since the last point of backup.
* If the CA signing keys are not destroyed, the integrity of the system has been restored, and 
 the risk is deemed negligible, re-establish CA operations, giving priority to the ability to 
 generate certificate status information within the CRL issuance schedule.
* If the CA signing keys are destroyed, the integrity of the system cannot be restored, or the 
 risk is deemed substantial, re-establish CA operations as quickly as possible, giving priority 
 to the generation of a new CA signing key pair.

#### 5.7.3 Entity (CA) Private Key Compromise Procedures

In the event that the private key of a CA is compromised, the CA will:

* Notify the Corda Network Foundation;
* Immediately cease using the compromised key material;
* Revoke all certificates signed with the compromised key;
* Take commercially reasonable steps to notify all network participants of the revocation; 
 _and_
* Take commercially reasonable steps to cause all participants to cease using any such certificates.

Once the compromised key material has been replaced, and secure operation of the CA in question has been established, 
the CA may issue replacement certificates, following the procedure for 
initially providing the certificates.

#### 5.7.4 Business Continuity Capabilities after a Disaster

The CA maintains a Facility Specific Disaster Recovery Plan for its facilities.

In the case of a disaster in which the CA equipment is damaged and inoperative, the CA operations shall be 
re-established as quickly as possible. If the CA cannot re-establish revocation capabilities within an acceptable time 
(prior to date and time specified in the _nextUpdate_ field in the 
currently published CRL issued by the CA), then the inoperative status of the CA shall be reported 
to the Corda Network Foundation. The Corda Network Foundation shall decide whether 
to declare the CA private signing key as compromised and re-establish the CA keys and certificates or allow additional 
time for reestablishment of the CA’s revocation capability.

In the case of a disaster whereby all copies of a CA signature key are destroyed, the CA shall 
revoke the certificate associated with that key. The CA installation shall then be completely rebuilt 
by re-establishing the CA equipment, generating new private and public keys and being re-certified. Finally, all 
Participant certificates will be re-issued.

### 5.8 CA or RA Termination

If it becomes necessary to terminate operations of a CA before all certificates have expired, the 
CA will:

* Provide practicable and reasonable prior notice to all network participants.
* Issue a CRL revoking all unexpired certificates prior to termination. This CRL shall be available until all 
certificates issued by the CA expire;
* Archive all audit logs and other records prior to termination and transfer those records to 
 the Corda Network Foundation;
* Assist with the orderly transfer of service and operational records to a successor CA, if any; 
 _and_
* If a Root CA is terminated, the Root CA shall use secure means to notify the subscribers to 
 delete all trust anchors representing the terminated CA.

## 6 Technical controls

### 6.1 Key Pair Generation and Installation


#### 6.1.1 Key Pair Generation

Key pairs for CAs are generated in \[FIPS 140\] Level 3 validated Hardware Security Modules (HSM). 
Formal key generation procedures are observed during the creation of all key material. Private 
keys cannot be exported from the HSM in plaintext. Multi-party control is required for CA key pair 
generation, as specified in section 6.2.2.

Key pairs for intermediate (subordinate or Doorman) CAs are generated in accordance with the 
requirements set forth by the Corda Network Foundation in the Corda Network Certificate 
Policy and with any contractual obligations that exist between the CA and that body.

A key pair generation must create a verifiable audit trail demonstrating that the security requirements for procedures 
were followed. The documentation of the procedure must be detailed 
enough to show that appropriate role separation was used. The CA has engaged an independent 
third party to validate the execution of the key generation procedures by witnessing the key generation ceremony for 
the root and subordinate keys and certificates.

#### 6.1.2 Private Key Delivery to Subscriber

Not applicable.

#### 6.1.3 Public Key Delivery to Certificate Issuer

Network participants provide their public key to the CA through a PKCS#10 CSR, transferred 
over TLS

#### 6.1.4 CA Public Key Delivery to Relying Parties

The public keys of Corda Network Subordinate CAs are signed by the Corda Network Root CA. 
Both Subordinate and Root are included in the Corda Node software distribution. In addition, CA 
public keys are made available from the online repository at: [http://trust.corda.network/](http://trust.corda.network/)

#### 6.1.5 Key Sizes

CAs use key sizes and cryptographic protocols which adhere to NIST recommendations and to the applicable provisions of 
the CP.

#### 6.1.6 Public Key Parameters Generation and Quality Checking

Elliptic Curve public key parameters shall always be selected from the set specified in section 7.1.3.

#### 6.1.7 Key Usage Purposes (as per X.509 v3 Key Usage Field)

No stipulation.

### 6.2 Private Key Protection and Cryptographic Module Engineering Controls


#### 6.2.1 Cryptographic Module Standards and Controls

The CA shall use a \[FIPS 140\] Level 3 or higher validated hardware cryptographic module for signing operations.

CA private keys are kept in physically secure locations and are never stored unencrypted outside 
of their Hardware Security Modules.

#### 6.2.2 Private Key (N of M) Multi-Person Control

A single person shall not be permitted to activate or access any cryptographic module that contains the complete CA 
signing key. CA signing keys may be backed up only under two-person 
control. Access to CA signing keys backed up for disaster recovery shall be under at least two-person control. The 
names of the parties used for two-person control shall be maintained on a list 
that shall be made available for inspection during compliance audits.

All CA key pairs are generated in pre-planned key generation ceremonies. Upon finalisation of 
the ceremony, all individuals sign off on the successful completion of the script and thoroughly 
describe any exceptions that may have been applied in the process.

#### 6.2.3 Private Key Escrow

CA private keys are never escrowed.

#### 6.2.4 Private Key Backup

The CA private signature keys are backed up under the same multiparty control as the original 
signature key. Encrypted copies of the private signature keys are store offsite. All copies of the CA 
private signature key are accounted for and protected in the same manner as the original.

Backup procedures form part of the CAs cryptographic material handling procedures.

#### 6.2.5 Private Key Archival

Private keys belonging to CAs are not archived by parties other than the CA.

#### 6.2.6 Private Key Transfer into or from a Cryptographic Module

CA private keys are exported from the cryptographic module only as a result of CA key backup 
procedures as described in Section 6.2.4.1. At no time shall the CA private key exist in plaintext 
outside the cryptographic module.

All transfers of private keys to and from an HSM are performed in accordance with the procedures 
specified by the HSM vendor and by the CA’s cryptographic material handling procedures.

#### 6.2.7 Private Key Storage on Cryptographic Module

Private keys are store in accordance with the applicable instruction specified by the HSM vendor.

#### 6.2.8 Method of Activating Private Key

All CA private keys are activated in accordance with the HSM vendor instructions.

Multi-factor authentication is required for all private key activation.

Subordinate or Issuing CA private keys require (N of M) multi person control as described in section 
6.2.2.

#### 6.2.9 Method of Deactivating Private Key

All CA private keys are deactivated in accordance with the HSM vendor instructions.

#### 6.2.10 Method of Destroying Private Key

Private keys are destroyed in accordance with applicable instructions specified by the HSM manufacturer. In addition, 
the CA’s data destruction procedures must be followed.

#### 6.2.11 Cryptographic Module Rating

See section 6.2.1.

### 6.3 Other Aspects of Key Pair Management


#### 6.3.1 Public Key Archival

No stipulation.

#### 6.3.2 Certificate Operational Periods and Key Usage Periods

Certificates are valid starting at the moment of signing, unless otherwise specified in the certificate 
validity structure, until the ned noted in the certificate expiration time.

The usage period for Subordinate or Issuing and Doorman CA certificates is a maximum of 20 years

The usage period for the Network Operator subject certificates is a maximum of 20 years.

The usage period for Network Participant certificates is a maximum of 20 years.

### 6.4 Activation Data


#### 6.4.1 Activation Data Generation and Installation

No stipulation

#### 6.4.2 Activation Data Protection

HSM keys (the HSM master backup keys) are stores in the HSM and can only be used by authorised 
CA administrators upon presentation of two factor authentication (smartcard and PIN). Multi-party 
(M of N) authentication is required to activate private keys. Physical tokens should be protected 
and secured, local tokens (PINs, passwords etc.) must be memorised or stored in an encrypted 
form.

#### 6.4.3 Other Aspects of Activation Data

No stipulation.

### 6.5 Computer Security Controls


#### 6.5.1 Specific Computer Security Technical Requirements

CA systems are protected from unauthorised access through a combination of physical, logical 
and technical security controls, which are documented in the CA’s Information Security Management System (”ISMS”).

#### 6.5.2 Computer Security Rating

No stipulation.

### 6.6 Life Cycle Technical Controls

#### 6.6.1 System Development Controls

System development controls address various aspects related to the development and change 
of the CA system through aspects of its life-cycle.

The CA system shall be implemented and tested in a non-production environment prior to implementation in a production 
environment. No change shall be made to the production environment 
unless the change has gone through the change control process as defined for the system baseline.

In order to prevent incorrect or improper changes to the CA system, the CA system shall require 
multi-party control for access to the CA system when changes are made.

#### 6.6.2 Security Management Controls

The CA has established an Information Security Organisation, which operates physical, logical and 
technical security controls, to protect the integrity, confidentiality of CA systems. The internal security control 
environment for the CA is documented in the CA’s ISMS.

#### 6.6.3 Life Cycle Security Controls

The CA has a set of lifecycle security controls for its systems that together make up and integrated 
security assurance plan.

Significant components of the security assurance plan include vulnerability identification, tracking, mitigation and 
remediation, remediation and review.

Vulnerability identification is achieved by a combination of threat modelling, code review, manual and automated 
vulnerability assessment and external penetration testing.

Vulnerabilities are recorded, assessed in terms of their impact and likelihood, and recorded in the 
CA’s issue tracking system.

A triage process examines identified vulnerabilities and remedial actions, which may include the 
application of vendor updates, in-house code changes, compensating controls or other mitigating actions. The Security 
Operations Group (a component of the CA ISMS) will then track the identified threats or vulnerabilities until they are 
appropriately resolved or mitigated.

Automated vulnerability assessment is carried out on a frequent (no less than monthly) basis. Manual vulnerability 
assessment and penetration testing is carried out not less than yearly. Threat modelling and code review activities are 
carried out whenever systems are subject to significant 
change and are reviewed on a yearly basis to ensure that they are current.

### 6.7 Network Security Controls

The networked components of the CA are located behind firewall devices that logically segregate the components of a 
system into zones, isolating those components according to their value 
and the need to provide access to those services to network participants and administrators. The 
principle of least privilege is used throughout.

### 6.8 Time-Stamping

All logs contain synchronized time stamps.

## 7 Certificate, CRL, and OCSP Profiles


### 7.1 Certificate Profile

**Note to reviewer:** The certificate, CRL and OCSP profiles used by Corda nodes and supporting 
infrastructure has not been finalised. At present, the PKI in which the nodes operate runs a uniform 
version of the Corda code and therefore the interoperability requirements satisfied by these profiles do not exist. It 
is recognised that this will not always be the case and that said profiles will be 
required in the future to facilitate interoperability between heterogeneous nodes and supporting 
infrastructure. Appropriate profiles will be included in this certificate policy at that time.

#### 7.1.1 Version Number (s)

Certificates MUST be of type X.509 v3.

#### 7.1.2 Serial Numbers

CAs SHALL generate non-sequential Certificate serial numbers greater than zero (0) containing at 
least 64 bits of output from a CSPRNG.

#### 7.1.3 Certificate Cipher Suite and Algorithms

The Corda Root CA and Subordinate CA Certificates shall sign with the following algorithms:

 Certificate Algorithm Parameters Lifetime
 

 Root CA ECDSA, SHA- 256 ECDSA_P 256 20 years
 

 Subordinate CA ECDSA, SHA- 256 ECDSA_P 256 20 years
 

TLS certificates must follow the TLSv1.2 standard.

#### 7.1.4 Certificate Role Extension

Corda certificates have a custom X.509 v3 extension that specifies the role the certificate relates 
to. This extension has the OID 1.3.6.1.4.1.50530.1.1 and is non-critical, so implementations outside 
of Corda nodes can safely ignore it. The extension contains a single ASN.1 integer identifying the 
identity type the certificate is for:

 Role Value
 

 Doorman CA 1
 

 Network Map 2
 

 Service Identity 3
 Node CA 4
 

 TLS 5
 

 Legal Identity 6
 

 Confidential Identity 7
 

#### 7.1.5 Root CA Certificate

 Extension Status Constraints
 

 Basic Constraints CRITICAL
 

 This extension MUST appear as a critical extension.
 The cA field MUST be set true.
 The pathLenConstraint field SHOULD NOT be present
 

 Key Usage CRITICAL
 

 This extension MUST be present, and MUST be marked critical.
 

 Bit positions for keyCertSign and cRLSign MUST be set.
 If the Root CA Private Key is used for signing OCSP responses, then the digitalSignature bit MUST be set.
 

 Certificate Policies NOT PRESENT This extension SHOULD NOT be present
 

 Extended Key Usage NOT PRESENT This extension MUST NOT be present
 

#### 7.1.6 Subordinate “Issuing” CA Certificate

 Field Status Constraint
 

 Certificate Policies REQUIRED
 

 This extension MUST be present and SHOULD NOT be
 marked as critical
 REQUIRED:
 certificatePolicies:policyIdentifier
 

#### OPTIONAL:

 certificatePolicies:policyQualifiers:
 policyQualifierId
 

#### OPTIONAL:

 certificatePolicies:policyQualifiers:
 qualifier:cPSuri
 

 CRL Distribution Points REQUIRED^
 

 This extension MUST be present and SHOULD NOT be
 marked as critical
 

 It MUST contain the HTTP URL of the CA's CRL service
 

 Authority Information
 Access
 

#### REQUIRED

 With the exception of stapling, which is noted below, this
 extension MUST be present.
 It MUST NOT be marked as critical
 It MAY contain the URL of the issuing CA's OCSP responder (access method = 1.3.6.1.5.5.7.48.1).
 It SHOULD also contain the HTTP URL of the Issuing CA’s
 certificate (accessMethod = 1.3.6.1.5.5.7.48.2)
 

 The HTTP URL of the Issuing CA’s OCSP responder MAY
 be omitted, provided that the Subscriber
 “staples” the OCSP response for the Certificate in its TLS
 handshakes [RFC4366]
 

 Basic Constraints CRITICAL
 

 This extension MUST appear as a critical extension.
 Bit positions for keyCertSign and cRLSign MUST be set.
 The cA field MUST be set true.
 

 The pathLenConstraint field SHOULD NOT be present
 

 Key Usage CRITICAL
 

 This extension MUST be present, and MUST be marked
 critical.
 

 Bit positions for keyCertSign and cRLSign MUST be set.
 If the Issuing CA Private Key is used for signing OCSP responses, then the digitalSignature bit MUST be set.
 

 Name Constraints OPTIONAL If present, this extension SHOULD be marked critical
 

 Extended Key Usage OPTIONAL
 

 For Subordinate CA Certificates to be Technically constrained in line with section 7.1.5, then either the value
 id-kp-serverAuth [RFC5280] or id-kp-clientAuth
 [RFC5280] or both values MUST be present**
 

#### 7.1.7 Certificate Policy Object Identifier

A Root CA Certificate SHOULD NOT contain the certificatePolicies extension

A Subordinate CA SHALL represent, in its CP and/or CPS, that all Certificates containing a policy 
identifier indicating compliance with these Requirements are issued and managed in accordance with these Requirements.

A certificate issued to a Subscriber MUST contain one or more policy identifier(s), defined by the 
Issuing CA, in the Certificate’s certificatePolicies extension that indicates adherence to and compliance with these 
Requirements. CAs complying with these Requirements MAY also assert one of 
the reserved policy OIDs in such Certificates. The issuing CA SHALL document in its Certificate Policy or Certification 
Practice Statement that the Certificates it issues containing the specified policy 
identifier(s) are managed in accordance with these Requirements

#### 7.1.8 Usage of Policy Constraints Extension

No stipulation.

#### 7.1.9 Policy Qualifiers Syntax and Semantics

No stipulation.

#### 7.1.10 Processing Semantics for the Critical Certificate Policies

No stipulation.

### 7.2 CRL Profile

Certificate Revocation in the Corda Network is still being finalised and aspects could change in 
the future. In particular it is likely that revocation of Corda certificates could be implemented by 
an entirely separate mechanism to the CRL facility provided by X.509 certificates. Corda certificates will still define 
CRL endpoints in case it is required in the future.

The Root CA SHOULD NOT contain a CRL Distribution Point.

The Subordinate CA SHOULD contain a CRL Distribution Point. The CRL SHOULD be signed by the 
Root CA, or a revocation certificate issued by the Root CA.

An entry in the CRL MUST NOT be removed until the expiration date of the certificate being revoked has passed. In other 
words, once revoked, the certificate must remain in the CRL during its 
validity period.

### 7.2.1 Version Number(s)

No stipulation.

#### 7.2.2 CRL and CRL Entry Extensions

No stipulation.

### 7.3 OCSP Profile

Certificate Revocation in the Corda Network is still being finalised and aspects could change in 
the future. In particular it is likely that revocation of Corda Nodes could be implemented by an 
entirely separate mechanism to the OCSP facility provided by X.509 certificates. Corda Network 
certificates may still define an OCSP responder in case it is required in the future.

The Root CA SHOULD NOT contain the Authority Information Access extension.

The Subordinate CA MAY contain an Authority Information Access extension. The Access Method 
MAY be set to On-line Certificate Status Protocol. The Authority Key Identifier MAY identity a revocation key issued by 
the Root CA.

#### 7.3.1 Version Number(s)

No stipulation.

#### 7.3.2 OCSP Extensions

No stipulation.

## 8 Compliance, Audit and Other Assessments

### 8.1 Frequency or Circumstances of Assessment

The CA will undertake compliance audits of its security control environment at least annually.

### 8.2 Qualifications of Assessor

Compliance audits of the CA will be performed by a public accounting firm that possesses the 
following qualifications and skills

1. Independence from the subject of audit;
2. Employs individuals who have proficiencies in examining public key infrastructure technology, information security 
tools and techniques, information technology and security audit ing and the third-party attestation function; and
3. Bound by law, government regulation, or a professional code of ethics.

### 8.3 Assessor’s Relationship to Assessed Entity

Compliance audits of the CA are performed by a public accounting firm that is independent of 
the subject of audit.

### 8.4 Topics Covered by Assessment

Compliance audits of the CA cover a validation of controls relevant to the proper operation of 
the CA.

The purpose of a compliance audit shall be to verify that the CA is complying with the requirements of the Corda Network 
Certificate Policy.

The compliance audits will provide an assessment of the design and effectiveness the CA’s security control environment 
and will include validation of “agreed upon procedures”, based on selected controls from a standard such as SOC 2 or ISO 27001.

### 8.5 Actions Taken as a Result of Deficiency

Significant deficiencies identified during a compliance audit will result in a determination of actions to be taken by 
the CA management. These decisions are made with input from the auditor 
and implemented within a commercially reasonable period of time.

### 8.6 Communication of Results

A copy of the service auditor’s statement will be provided to Corda Network participants when 
requested by them to support trust in the CA.

## 9 Other Business and Legal Matters


### 9.1 Fees


#### 9.1.1 Certificate Issuance or Renewal Fees

Certificate issuance and renewal fees will be decided by the Corda Network Foundation 
(CNF) and may be included in a single network access fee. Such fee schedules to be published 
by the CNF from time to time.

#### 9.1.2 Certificate Access Fees

Certificate access fees will be decided by the CNF and may be included in a single network 
access fee. Such fee schedules to be published by the CNF from time to time.

#### 9.1.3 Revocation or Status Information Access Fees

Revocation or status information access fees will be decided by the CNF and may be included 
in a single network access fee. Such fee schedules to be published by the CNF from time to 
time.

#### 9.1.4 Fees for other Services

Other service fees are not envisioned at this time but may be introduced by the CNF in the future 
and may or may not be included in a single network access fee. Such fee schedules to be published by the CNF from time 
to time.

#### 9.1.5 Refund Policy

Refund policy will be determined and published by the CNF.

### 9.2 Financial Responsibility


#### 9.2.1 Insurance Coverage

The CA maintains general liability insurance proportionate to the specific risks of the service being 
offered.

#### 9.2.2 Other Assets

No stipulation.

#### 9.2.3 Insurance or Warranty Coverage for End-Entities

No stipulation.

### 9.3 Confidentiality of Business Information


#### 9.3.1 Scope of Confidential Information

Information, including names of business entities and routing information, is procured for the express purpose of 
making such information available to other subscribers and relying parties within 
the Corda Network and is not considered confidential.

#### 9.3.2 Information not within the Scope of Confidential Information

No stipulation.

#### 9.3.3 Responsibility to Protect Confidential Information

No stipulation.

### 9.4 Privacy of Personal Information


#### 9.4.1 Privacy Plan

The CA will comply with all relevant data protection legislation in the jurisdictions within which it 
operates.

#### 9.4.2 Information Treated as Private

Any personally identifiable information (PII) relating to subscribers, relying parties or Registration 
Authorities and their employees to which the CA has access or control must be treated as private.

#### 9.4.3 Information not Deemed Private

IP addresses of Corda nodes are not considered private information relating to individual persons 
unless the node is operated by, and certificated to, a named individual rather than a corporate 
entity will not be deemed private.

#### 9.4.4 Responsibility to Protect Private Information

The CA will comply with all relevant data protection legislation in the jurisdictions within which they 
operate.

#### 9.4.5 Notice and Consent to Use Private Information

The CA will comply with all relevant data protection legislation in the jurisdictions within which it 
operates.

#### 9.4.6 Disclosure Pursuant to Judicial or Administrative Process

No stipulation.

#### 9.4.7 Other Information Disclosure Circumstances

No stipulation.

### 9.5 Intellectual Property Rights

The CA will not knowingly violate intellectual property rights held by others.

### 9.6 Representations and Warranties

No stipulation.

#### 9.6.1 Representations and Warranties

The CA makes the below warranties to subscribers and relying parties (‘network participants’) 
making valid use of such certificates as defined in the Participant Agreement of the Corda Network:

The CA represents and warrants to network participants that, during the validity period of the Certificate, the CA has 
complied with these requirements and its own Certification Practice Statement in issuing and managing the Certificate.

The Certificate Warranties specifically include, but are not limited to, the following:

1. The CA warrants that they accurately described the procedure for verifying certificate 
 details in their Certification Practice Statement and followed such procedure in the issuance of the Certificate;
2. The CA warrants that they, at the time of issuance, implemented a procedure for verifying 
 that the Certificate Requester either had the right to use, or had control of, the organisation or person name 
 supplied as Distinguished Name for the X509 certificate or was delegated such right or control by someone who had 
 such right to use or control;
3. The CA warrants that they implemented a procedure for verifying that the named organisation or individual 
authorised the submission of the Certificate Signing Request and that 
 the Certificate Requester was in a suitable position to request the Certificate on behalf of 
 the named organisation or individual;
4. The CA warrants that, at the time of issuance, they implemented a commercially reason able procedure for ensuring 
that the information contained in the Certificate would not 
 be misleading to relying parties;
5. The CA warrants that, if the CA and Subscriber are not Affiliated, the Subscriber and CA 
 are parties to a legally valid and enforceable Subscriber Agreement that satisfies these 
 Requirements, or, if the CA and Subscriber are Affiliated, the Certificate Requester 
 acknowledged and accepted the Terms of Use;
6. The CA warrants that they maintain a 24 x 7 publicly-accessible Repository with current 
 information regarding the status (valid or revoked) of all unexpired Certificates;
7. The CA warrants that they will revoke the Certificate for any of the reasons specified in this 
 policy or separately described by the Corda Network Foundation in its rules and/or 
 Participant Agreements; _and_
8. The CA warrants that, if they delegate tasks covered in this policy to a third party (Subordinate CA), they shall 
be responsible for the performance and warranties of the Subordinate CA, their compliance with this policy, and for 
all liabilities and indemnities of the Sub ordinate CA under this policy.

#### 9.6.2 RA Representations and Warranties

No stipulation.

#### 9.6.3 Subscriber Representations and Warranties

Prior to the issuance of any Certificate, the CA shall ensure that the subscriber requesting the Certificate has 
accepted the Terms of Use of the Corda Network as in force at the time of request

and either enshrined in the Participant Agreement or any other such document as decreed by 
the Corda Network Foundation.

The CA will implement a process to ensure that the Participant Agreement is legally enforceable 
against the subscriber and applies to the particular Certificate to be issued as a result of the particular Certificate 
request. The CA may use an electronic or “click-through” Agreement provided 
that the CA has determined that such agreements are legally enforceable.

For reference, the Participant Agreement will contain provisions imposing on the subscriber (or 
subscriber’s agent) requesting the certificate the following obligations and warranties:

1. To provide accurate and complete information at all times to the CA, both in the Certificate Signing Request and as 
otherwise requested by the CA in connection with the issuance of the Certificate(s) to be supplied by the CA;
2. To take all reasonable measures to maintain sole control of, keep confidential, and 
 properly protect at all times the Private Key that corresponds to the Public Key to be included in the requested 
 Certificate(s) (and any associated activation data or device, e.g. 
 password or token);
3. To review and verify the Certificate contents for accuracy before accepting and using it;
4. To install the Certificate only on servers that are accessible at the IP addresses supplied at 
 the time of application, and to use the Certificate solely in compliance with all applicable 
 laws and solely in accordance with the Participant or other relevant agreement;
5. To promptly cease using a Certificate and its associated Private Key, and promptly request 
 the CA to revoke the Certificate, in the event that any information in the Certificate is, or 
 becomes, incorrect or inaccurate, or there is any actual or suspected misuse or compromise of the Subscriber’s 
 Private Key associated with the Public Key included in the Certificate;
6. To promptly cease all use of the Private Key corresponding to the Public Key included in 
 the Certificate upon revocation of that Certificate for reasons of Key compromise;
7. To respond to the CA’s instructions concerning Key compromise or Certificate misuse within 
 a specified time period; _and_
8. To acknowledge and accept that the CA is entitled to revoke the Certificate immediately 
 if the Applicant were to violate the terms of the Participant of other agreement or if the 
 CA discovers that the Certificate is being used to enable criminal activities such as phishing 
 attacks, fraud, or the distribution of malware.

#### 9.6.4 Relying Parties Representations and Warranties

No stipulation.

#### 9.6.5 Representations and Warranties of Other Subscribers

No stipulation.

### 9.7 Disclaimers of Warranties

No stipulation.

### 9.8 Limitations of Liability

For delegated tasks, the CA and any third party may divide liability between themselves contractually, but the CA will 
remain fully responsible for the performance of all parties in accordance 
with this Policy, as if the tasks had not been delegated.

If the CA has issued and managed the Certificate in compliance with this Policy and its Certification Practice 
Statement, the CA may disclaim liability to relying parties or any other third parties 
for any losses suffered as a result of use or reliance on such Certificate beyond those specified in 
this CPS.

If the CA has not issued or managed the Certificate in compliance with applicable requirements 
and its Certification Practice Statement, the CA may seek to limit its liability to network participants, regardless of 
the cause of action or legal theory involved, for any and all claims, losses or 
damages suffered as a result of the use or reliance on such Certificate by any appropriate means 
that the CA desires.

### 9.9 Indemnities

No stipulation.

### 9.10 Term and Termination


#### 9.10.1 Term

No Stipulation

#### 9.10.2 Termination

No stipulation

#### 9.10.3 Effect of Termination and Survival

No stipulation

### 9.11 Individual Notices and Communications with Subscribers

The CA shall establish appropriate procedures for communications with the Corda Network Foundation to ensure that 
this CPS complies with the Governing Body’s CP via contracts or memoranda of agreement as applicable.

For all other communications, there is no stipulation.

### 9.12 Amendments


#### 9.12.1 Procedure for Amendment

The CA shall review this CPS at least once every year. Corrections, updates, or changes to this CPS 
shall be publicly available. Suggested changes to this CPS shall be communicated to the contact 
in section 1.5.2; such communication must include a description of the change, a change justification, and contact 
information for the person requesting the change.

#### 9.12.2 Notification Mechanism and Period

No stipulation.

#### 9.12.3 Circumstances under which OID must be Changed

No stipulation

### 9.13 Dispute Resolution Provisions

A dispute resolution mechanism may be operated by the Corda Network Foundation.

### 9.14 Governing Law

No stipulation.

### 9.15 Compliance with Applicable Law

No stipulation.

### 9.16 Miscellaneous Provisions


#### 9.16.1 Entire Agreement

No stipulation.

#### 9.16.2 Assignment

No stipulation.

#### 9.16.3 Severability

No stipulation

#### 9.16.4 Enforcement (Attorneys’ Fees and Waiver of Rights)

No stipulation.

#### 9.16.5 Force Majeure

No stipulation.

### 9.17 Other Provisions

No stipulation.

## Appendix A: Acronyms

Selected acronyms and abbreviations that may be used in the guide are defined below.

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

HTTP Hypertext Transfer Protocol

IEC International Electrotechnical Commission

IETF Internet Engineering Task Force

IS Information System

ISMS Information Security Management System

LAN Local Area Network

ISO International Organization for Standardization

ITU-T International Telecommunications Union – Telecommunications Sector

NIST National Institute of Standards and Technology

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

UPS Uninterrupted Power Supply

URL Uniform Resource Locator

UUID Universal Unique Identifier

VPN Virtual Private Network

## Appendix B: References

1. [Allowable Identity Names] (/policy/allowable-names) (Corda Network technical policies): 

Appendix C: Document History

 Version Date Author Change Details
 

 Draft 0.1 27th August 2017 Jonathan Sartin Initial fork from Corda Network CP
 

 Draft 0.2 9th September Jonathan Sartin Draft 0.2
 Draft 0.3 24th September 2018 Jonathan Sartin Completed section 1 and up to 2.2
 

 Draft 0.4 1st October 2018 Jonathan Sartin Updated some aspects of the certificate profile (in particular,
 changed curve parameters from 384 to 256).
 

 Draft 0.5 2nd October 2018 Jonathan Sartin Updated most sections. Ready to
 merge with section 3 and 4 updates.
 

 Draft 0.6 3rd October 2018 Jonathan Sartin
 / James Brown
 

 Updated certificate profile (section
 7)
 

 Draft 0.7 3rd October 20 18 Jonathan Sartin
 / Nigel King
 

 Updated certificate lifecycle operational requirements (section 4)
 

 Draft 0.8 4th October 2018 Jonathan Sartin Simplified explanation of physical
 security requirements.
 Grammar / style corrections
 

 Draft 0.9 5th October 2018 Jonathan Sartin Prepared for Review – further grammar / style corrections.