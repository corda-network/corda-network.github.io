|Corda Network Foundation|[Document history]({{ site.github.repository_url }}/blame/master/{{page.path}})|

Network Services Policy
======================

1	Introduction
--------------

**1.1	Definitions**
The following definitions apply in the context of this document:
-	Network Service: A resource, or collection of resources, providing functionality which is generally required by all Corda Network participants, and which is addressable via a single URI.
- Service Operator: An organisation responsible for the provision of a Network Service. Includes the Network Operator, where the Network Operator provides Network Services directly (see 2.3)
- User: A prospective or current Network participant, who may access a Network Service. 
- Corda Reference Implementation: Official open source reference node implementation for the Corda protocol, uniquely recognised as such by the Foundation.

**1.2	Motivation**
Network Services are essential to the operation of the Network, realising fundamental concepts such identity and interoperability within the context of Corda. The Foundation regards it as essential to the success of the network that the required services are reliably provided, and are operated in a secure and controlled manner which engenders trust by all Participants. This policy sets out key requirements for Service Operators (including the Network Operator) to ensure this.

**1.3	Principles**
This policy applies the following general principles:
1.	Security: Network Services must be engineered and operated in a manner which appropriately reflects the significance of their role in safeguarding the security and resilience of the network.
2.	Backward compatibility: Wherever permissible, changes to Network Services should avoid breaking compatibility with previously-supported clients. 
3.	Transparency: Users must be informed of the terms and conditions under which a Network Service is operated, and made aware of any limitations in the Service. 

2	Policy detail
---------------

**2.1	Network Service functions**
Subject to access and usage restrictions, Network Services shall collectively satisfy all required Network Service functions.
Required Network Service functions are implied by the functional architecture of the Corda Reference Implementation. The current set of required functions is given in Appendix: Required Network Service functions.
Over and above the above requirements, Service Operators may choose to package additional functionality within the provision of Network Services.

**2.2	Interface requirements**
Interface requirements for Network Services may vary between implementations of the Corda software. At a minimum, Network Services shall collectively satisfy interface requirements implied by the Corda Reference Implementation, for all released versions over and above the mininumPlatformVersion specified in the network parameters.
Service Operators may choose to provide additional interface support for other Corda implementations and non-Corda client software.

**2.3	Accountability and delegation**
The Network Operator shall ensure provision of Network Services which collectively satisfy all functions (see 2.1) and interface requirements (see 2.2).
Subject to Foundation approval via a Mandatory Governance Event (see the Corda Network Foundation Constitution), the Network Operator may elect to delegate responsibility for providing some or all functions to one or more third party Service Operators, whilst remaining ultimately accountable to the Foundation for provision of all Network Services. Such responsibilities may be selectively delegated by function and/or segmentation of Users; e.g. a specific Service Operator may be responsible for certificate issuance for a specific group of Users.

**2.4	Implementations**
Service Operators (including the Network Operator) may employ any technical implementation which satisfies their required functions and interface requirements. Accordingly, Service Operators may determine any distribution of functions across one or more discrete Network Services, provided that this collectively provides Users with all required functions and meet all interface requirements.
A Service Operator may provide different versions or instances of a Network Service to different Users, provided these provide Users with all required functions and meet all interface requirements.

**2.5	Terms of Service**
Service Operators shall define Terms of Service for all Network Services they provide. 
At a minimum, Terms of Service shall include clear, explicit statements to cover the following:
- Identification of Service Operator including relevant contact information, trade registry reference number, legal status and regulated status.
- Description of the Network Service offered, including technical detail where relevant to its access and operation.
- Conditions of service, which may include:
- Any requirements for the User to enter into prior agreements with the Service Operator
- Applicable hours of operation 
- Specific conditions under which service may be withheld (e.g. legal, regulatory constraints etc.)
- Data restrictions: Data which Users are prohibited from sending to the Network Service
- Commitments to deliver a specific level of performance, specifying relevant metrics (e.g. throughput, latency etc.), and how they are measured
- Commitments to ensure a specific level of availability (uptime) including provisions for planned and unplanned outages
- Charges due to the Service Operator in relation to the Network Service, and how these are to be paid
- Acceptance of liability for improper service
- Dispute resolution procedures, including means to contact the Service Operator
- Compensation scheme(s) applicable in the event of financial losses by a User due to improper service, and procedures for accessing scheme(s)
- Disclosures arrangements (see 2.6)
- Data handling: Treatment and arrangements for secure management of data provided to the Network Service by Users 
- Data retention: Policy on the retention and deletion of data provided to the Network Service by Users
- Geographical location of all resources (databases, servers etc.) making up the Network Service, naming specific countries in which resources may reside. Where resources are distributed over more than one country, the division of resources across countries shall be unambiguously described.
- Governing law: Which set(s) of legislation shall be considered to govern the Terms of Service
- Process for changes to the Terms of Service, including notice given to Participants and notification procedures
- Process for termination of the Network Service, including requirements for advance notice and migration, where relevant
Where any of the above do not apply to a Network Service, the Terms of Service shall include explicit statements to this effect.

**2.6	Disclosures**
Service Operators are required to maintain transparency of changes in status to Users, such that Users may make informed decisions regarding their operational exposure to a Network Service. The minimum set of required disclosures are described below. 

*2.6.1	Advance disclosures*
Service Operators shall disclose the following to Users in advance of the fact:
- Any planned major change or upgrade to the Network Service (and whether the change impacts backward compatibility, see 2.8.1)
- Any change to the network location (URL etc.) at which a Network Service is accessible to those Users (see 2.8.2)
- Any change to the Terms of Service applicable to those Users
- Intent to delegate or transfer operation of the Network Service to another Operator
- Intent to discontinue the Network Service
- Any other action with significant risk of impairing operation under the current Terms of Service

*2.6.2	Other disclosures*
Service Operators shall disclose the following to all Users:
- Any financial, legal or operational dependencies existing between joint Service Operators, such that inability of a given Service Operator to operate may affect the ability of another Service Operator to maintain operation of their Network Services
- Any change in the legal status of the Service Operator
- Any change in the financial standing of the Service Operator, including insolvency and/or bankruptcy
- Any event with significant risk of impairing operation of the Network Service under the current Terms of Service
- Any breach of the data handling policy defined in the Terms of Service
Disclosures shall be made at the earliest practical opportunity. Where possible, all such disclosures shall be made in advance, and no later than 7 days after the event to be disclosed.

*2.6.3	Avoidance of disclosure conflicts*
A Service Operator shall avoid any action by which it may become unable to fulfill its disclosure obligations to Users, e.g. due to legal non-disclosure obligations.

**2.7	Security**
Service Operators shall maintain an appropriate control environment for all components of Network Services, such that:
- Measures are in place to restrict access to critical information assets (for example, cryptographic signing keys)
- All data provided to the Network Service by Users is handled in a secure manner, in line with policies described in the Terms of Service (see 2.5)

**2.8	Changes to Network Services**
The Foundation shall determine required changes to Network Services in line with changes to the Corda Reference Implementation. 

*2.8.1	Breaking changes*
Service Operators shall seek prior approval from the Foundation prior to implementing any changes which would violate the backward compatibility principle (see 1.3).
All such approvals shall be subject to a Mandatory Governance Event (see Corda Network Foundation Constitution).

*2.8.2	Relocations*
Subject to advance disclosure (see 2.6.1), Service Operators may alter the network location (e.g. URL) at which a given Network Service is accessible to users. Where permissible, Service Operators should seek to ensure Network Services remain available at the old network location (e.g. via HTTP redirects) even when deprecating in favour of a new location.

*2.8.3	Change deployment*
Service Operators shall maintain appropriate change control procedures in order to minimise risk to Participants.
At a minimum:
- All proposed changes shall be subject to prior regression testing to establish backward compatibility and identify any potential breaking changes (see 2.8.1)
- Each deployments shall be scheduled for a specific time window which shall be disclosed to Users (see 2.6.1)
- Procedures shall allow for rollback in the event of major issues

**2.9	Audit obligations**
The Foundation may at times require a Service Provider to provide evidence of compliance with the terms of this policy.
Where the Foundation deems necessary, a third party audit may be required to establish this evidence on an independent basis. In such cases, the Service Operator shall be required to engage a third party auditor approved by the Foundation. 
All costs of such audits shall be borne by the Service Provider.
