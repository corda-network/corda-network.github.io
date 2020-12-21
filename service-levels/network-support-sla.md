# Corda Network Support Service Handbook


## Contents

- [1. Introduction and Scope](#1-introduction-and-scope)
- [2. Support Schedule](#2-support-schedule)
- [3. Support Eligibility](#3-support-eligibility)
  - [3.1. Minimum Platform Version](#31-minimum-platform-version)
- [4. Accessing and Onboarding to Support](#4-accessing-and-onboarding-to-support)
  - [4.1. Support Portal and Participant Contacts](#41-support-portal-and-participant-contacts)
  - [4.2. Participant Data Stored by Corda Network](#42-participant-data-stored-by-corda-network)
  - [4.3. Network Operator Staff Access to Participant Support Data](#43-network-operator-staff-access-to-participant-support-data)
- [5. Incident Classifications and Response Targets](#5-incident-classifications-and-response-targets)
- [6. Exclusions](#6-exclusions)
  - [6.1. Support Exclusions](#61-support-exclusions)
  - [6.2. Excused Failures](#62-excused-failures)
- [7. Participant Obligations ](#7-participant-obligations)
  - [7.1. Access to Participant Source Code](#71-access-to-participant-source-code)
  - [7.2. Remedial and Diagnostic Actions Requested by Network Operator](#72-remedial-and-diagnostic-actions-requested-by-network-operator)
  - [7.3. Data Protection](#73-data-protection)
- [8. Final Disclaimers](#8-final-disclaimers)

## 1. Introduction and Scope

This Support Handbook contains information on the onboarding and operational support services (“Support”) provided in connection with the Services provided to you (“participant”, or “you”) by the Corda Network Operator ("Network Operator") pursuant to the terms of use (“Terms of Use”) entered into between you and the Corda Network Foundation. This handbook does not replace or amend in any way the contractual terms and conditions of the Terms of Use. Capitalized terms used herein but not otherwise defined shall have the meanings ascribed to them in the Terms of Use.

The Support consists of the following in connection with the Services:
1.	Corda Network onboarding 
2.	Operational Support Services when using the Services

## 2. Support Schedule

All time definitions are made in accordance with UTC+0.“Normal Business Hours” are from Sunday 23:00 (GMT) to Friday 23:00 (GMT). 
Corda Network Support uses a ‘follow-the-sun’ schedule with the Support team based in Network Operator’s offices in the following locations: London, New York and Singapore (each an “Office”).

“Business Day” means any day except (a) a Saturday or a Sunday, (b) any other day on which commercial banking institutions based in the affected Office’s city are authorized or directed by applicable law to close, or (c) any bank holiday in an Office.


## 3. Support Eligibility

Support is only provided for limited Corda Network onboarding assistance and for “Incidents” related to Services – on both Pre-Production Network and Production Network. “Testnet” is out of scope (other items out of scope are listed in Section 6: Exclusions). Please note that Support does not provide training, consultation or other professional services.

An “Incident” is where the Services do not operate in the manner as set forth in the General Maintenance and SLA Handbook. Determination of whether an “Incident” has occurred (rather than, for example, an issue that arose as a result of a Corda Network Node malfunction / CorDapp problem) shall be made by the Support team in its sole discretion. 

Network Operator is not in control of how a participant’s CorDapp manages workload on its and other CorDapp users’ hardware and operating systems, and so issues of performance or capacity overload caused by the CorDapp’s use of the Services are explicitly excluded from the definition of “Incident” (and are not eligible for Support).

Support is not provided for issues with your CorDapp(s), Corda Network Nodes or test environments (outside of the Pre-Production Network).
All of the Corda Software requirements set forth herein must be met in order for Support to be provided. 

## 3.1 Minimum Platform Version

Participant’s Corda Network Nodes should be running on a Corda Software version at least the same or more recent than the Minimum Platform Version (as defined in the minimumPlatformVersion among network parameters) of the Pre-Production Network and Production Network. 


## 4. Accessing and Onboarding to Support

To resolve a Support request in the most expedient way possible, the nominated individual should check the Service Dashboard. “Service Dashboard” means a dashboard where Corda Network infrastructure-related changes that impact participants will be communicated by Network Operator, currently located at StatusPage (and which may be moved from time to time), and access to which is provided to participants during their onboarding process.
If the issue cannot be resolved with information provided on the Service Dashboard , you could raise a ticket on the Support Portal for Support to look into the issue.

## 4.1 Support Portal and Participant Contacts

Network Operator uses Atlassian Jira Cloud to record all Support tickets and log all investigations. A web portal (“Support Portal”) provides an interface to the Jira Cloud for participants to raise Support tickets. Participant will be provided with a web link to the Support Portal which shall be the primary method for requesting Support.

**1. Requesting first user’s access**
- When onboarding to Corda Network, participants will be required to designate a Corda Network Node operator email address on the node configuration file (“node.conf”). Network Operator’s business operations team will contact the designated email address and ask for one (1) individual that should be granted to access the Support Portal. 
- Alternatively, you can request the first user in your organisation with access to Support Portal via the following means: If you are a Corda Enterprise customer or have an R3 Account Manager, contact your R3 account manager for access. 
**2. Registration Confirmation**
- Once access is granted, the registering individuals) will receive an email which will include a link to sign-up and create a password. Network Operator does not manage nor record Support Portal passwords outside the Jira Cloud System. If an individual loses their password they should recover access to their account by clicking on the ‘Forgot Password’ link when logging onto the Support Portal.
**3. Raising a Support ticket**
– You may raise a Support ticket via our Support Portal or via email (note: only emails sent from email addresses with access to the Support Portal will be able to email the Support team):
- Fill in the online form on the Support Portal (currently found at the following URL: https://r3-cev.atlassian.net/servicedesk/customer/portal/7; which may be moved from time to time), specify the Incident Severity (see Section 5: Incident Classifications and Response Targets for how to determine severity level) and attach any related documents on the dedicated web link to the Support Portal.
- Send an email to cordanetworksupport@r3-cev.atlassian.net. All Support tickets raised for “Incidents” are automatically classified as Severity 3 (S3). 
**4. Requesting access for different or additional users**
- Access is granted per individual email address basis. If you need to replace the email address originally assigned or request access for one (1) additional individual, a Support ticket for replacement/additional email address(es) will need to be raised.

The designated individual participant contact will be required to have the qualifications set forth in Section 7: Participant Obligations below. Support will only be provided to participant contacts. 

## 4.2 Participant Data Stored by Corda Network

Within Network Operator's Jira Cloud, participant contacts are stored as individuals grouped into organizations.

Only the organization name and data for each participant contact linked to that organization are stored in the Jira Cloud.

For participant contacts, only the full name and email address, as provided by the individual or the person who nominated that individual, are stored in the Jira Cloud. Once the participant contact registers with the Support Portal (accepts the invitation), the email address of that individual is no longer visible on the Jira Service Desk User Interface to the Support team.

Participant should note that, once registered, participant contacts can set up their own Jira profile which includes an avatar graphic and additional information about themselves. This is a feature of the Atlassian Jira Service Desk add-on, not a feature provided by Network Operator. If an individual chooses to customize their profile, the associated data will also be stored in Network Operator’s Jira Cloud. Please note, anything added to this profile is not within Network Operator’s control.

Support tickets and all information added to Support tickets, including attachments, are stored in Network Operator’s Jira Cloud system in perpetuity. Participant should therefore ensure that no personal data is included within such Support tickets or attachments submitted. participant must request specific deletion of Support ticket(s) if required.

## 4.3 Network Operator Staff Access to Participant Support Data

In an effort to expedite Support request resolution, the Support team has enabled any member of Network Operator team read-only visibility of all Support tickets raised by all participant contacts including all descriptions and comments on those Support tickets. This is so Support tickets can be quickly brought to the attention of different engineering teams, operations teams or even senior management teams during an investigation. However, only members of the Support team can view and modify user and organization data (e.g., add/delete users and organizations) and only the Support team can administer Support tickets and communicate directly with participant over the Support ticket.


## 5. Incident Classifications and Response Targets 

Incident severity level will first be proposed by participant, provided that Network Operator, in discussion with participant, will make the final determination as to the appropriate severity level in accordance with the following:

For the Production Network, Severity 1-4 may be raised.

For the Pre-Production Network, severity 2-4 may be raised.

Network Operator shall use commercially reasonable efforts to respond to all Incidents as provided below.

| **Incident Severity**                                     | **What is it?**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      | **How do we respond to the incident?**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                     **An Incident can be downgraded in the following situations**                                                                                                                                                                                                                                                                                                                                                                                             |
|-------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Severity 1:<br>Critical                               | Only applicable Service: Notary Service. <br><br>An emergency situation caused by an error in the Corda Network Notary Service which critically impairs a participant’s business.<br><br>Only issues related to Production Network can be raised as Severity 1 support ticket.<br><br>E.g.: the Corda Network Notary Service is not responding and participant’s business is critically impaired.<br><br>Fixes are not provided to fix issues with Participant’s Business Network, participants’ individual CorDapps and/or Corda Network Nodes.                 | Acknowledgement: Thirty (30) minutes from the time the incident was reported.<br><br>In addition, Network Operator shall, at Network Operator's expense (a) immediately assign an appropriate number of qualified resources to reasonably work towards correction of the Incident 24-hours a day, 7-days a week until Network Operator has provided a functional workaround or permanent fix or the issue is no longer defined as Severity 1.<br><br>Report status: Regularly report on the status of the corrections if the issue remains after four (4) hours at a schedule agreed with participant.<br><br>An appropriate number of participant resources must be made available in Severity 1 situations and reasonably cooperate to help resolve the issue. | A functional workaround has been implemented that has enabled the Notary Service to continue normal service;<br><br>During the course of the investigation it has been determined that the error is not in the Notary Service, as agreed by both parties;<br><br>Participant / a relevant third party fails to commit resources to work with Network Operator at any time;<br><br>Participant confirms the severity can be reduced for other reasons. |
| Severity 2:<br>Major Impact                           | Applicable Services: Notary Service, Identity Manager, Network Map Service.  <br><br>A detrimental situation caused by an error in the Notary Service, Identity Manager, and Network Map Service in which the CorDapp performance degrades substantially.<br><br>E.g.: Network Map Service is not acknowledging new participant entries. <br><br>Fixes are not provided to fix issues with Participant’s Business Network, Participants’ individual CorDapps, and/or Corda Network Nodes.                                                                        | Acknowledgement: Within two (2) Normal Business Hours from the time the Incident was reported.<br><br>In addition, Network Operator shall, at Network Operator’s expense, (a) promptly assign an appropriate number of qualified resources to work towards correction of the Incident until Network Operator has provided a functional workaround or fix; and (b) report on the status of the corrections not less than every Business Day.<br><br>Report status: No less than every Business Day.<br><br>A Severity 2 issue may be upgraded if the workaround no longer hides the impact of the issue, or if the workaround does not work.                                                                                                                      | During the course of the investigation it has been determined that the is not in the Notary Service, Identity Manger or Network Map, as applicable, as agreed by both parties; <br><br>Participant confirms that the severity can de reduced for other reasons.                                                                                                                                                                                       |
| Severity 3:<br>Moderate Impact                        | Applicable Corda Network Service: Notary Service, Identity Manager, Network Map Service. <br><br>The CorDapp is impaired caused by unexpected behaviour/error in the Notary Service, Identity Manager and Network Map Service), but the key functionalities are still maintained. The component impacted is not critical to the CorDapp, thereby causing little or no significant having limited impact on business operations.<br><br>Fixes are not provided to fix issues with Participant’s Business Network, individual CorDapps and/or Corda Network Nodes. | Acknowledgement: Within twelve (12) Normal Business Hours from the time the Incident was reported.<br><br>In addition, Network Operator shall, at Network Operator’s expense, then assign an appropriate number of qualified resources to work towards correction of the Incident until the issue is fixed.<br><br>Report status: Within a mutually agreed time if required<br><br>A Severity 3 issue may be upgraded if the impairment spreads to key functionalities of the CorDapp.                                                                                                                                                                                                                                                                           | During the course of the investigation it has been determined that the error is not in the Notary Service, Identity Manger or Network Map, as applicable, as agreed by both parties;<br><br>Participant confirms the severity can be reduced for other reasons.                                                                                                                                                                                       |
| Severity 4:<br>Minimal Impact or Information Requests | Applicable Service: Notary Service, Identity Manager, Network Map Service. <br><br>A noticeable situation, caused by an error in Notary Service, Identity Manager and Network Map), in which use of the CorDapp is affected in some cosmetic or ergonomic way and has a minimal impact on business operations. <br><br>Fixes are not provided to fix issues with Participant’s Business Network, Participants’ individual CorDapps and/or Corda Network Nodes.                                                                                                   | Acknowledgement: Within two (2) Business Days from the time the Incident was reported.<br><br>Report status: As soon as is practical, taking account of volumes of such queries and Incident in process at the time. Network Operator will take reasonable steps to provide an answer to the request.                                                                                                                                                                                                                                                                                                                                                                                                                                                            | During the course of the investigation it has been determined that the error is not in the Notary Service, Identity Manger or Network Map, as applicable, as agreed by both parties;<br><br>Participant confirms the ticket can be closed for other reasons.                                                                                                                                                                                          |



**Acknowledgement** = when the Support ticket is assigned to an Network Operator's Support engineer and such assignment has been communicated to participant.
**Report Status** = when subsequent updates are provided to participant by Network Operator's Support engineer(s).

When communicating with the Support team, participant contact should also mention the following items if they apply to your situation: 
- Participant is under business deadline pressure. 
- Participant contact and resources’ availability (i.e. when you will be able to work with Support). 
- Alternate ways to reach participant contact. 
- If Participant have other pending Incidents. 
- You are participating in an evaluation program. 
- Confirmation that participant researched this situation and have information or documentation in relation to the Incident. 

## 6. Exclusions

## 6.1 Support Exclusions
- This handbook does not cover fixes to issues with Business Networks, individual CorDapps, Corda Network Nodes or operating / test environments. 
- This handbook does not cover support of services or environments (e.g., “Testnet”).
- No on-site Support will be provided.
- Support will not include general training or consultation on the use of the Corda Network.  
- Support will not be provided with respect to Incidents caused by any reason external to the Services, including failure or fluctuation of electrical supplies, inadequate cooling, or equipment.

## 6.2 Excused Failures

Failure to meet any Incident service levels will be excused to the extent any of the following circumstances are present:
1.	The failure of, or problems resulting from, network services, connections, software, firmware or equipment not under the control of Network Operator; 
2.	Planned system downtime required for maintenance of either the Corda Network or Services components;
3.	Actions or inactions of participant, CorDapp user, or third-party vendor thereto (other than Network Operator and its subcontractors);
4.	Misuse of the Corda Software, or use or installation of the Corda Software other than as permitted in the relevant license to such Corda Software; 
5.	Failure of participant to meet any of its obligations set forth herein;
6.	Any action of any Governmental Authority which prevents Network Operator from providing Support; or
7.	Any Force Majeure Event (as defined in the Terms of Use), as long as Network Operator complies with reasonable disaster recovery procedures and provides to participant at least the same level of service during such Force Majeure Event as provided to other participants.

## 7. Participant Obligations 

Participant is responsible for the obligations set out below and acknowledges that the commitments provided by Network Operator are dependent on the performance of those obligations.
- Provide Network Operator with adequate and timely information and cooperation to facilitate the efficient provision of Support. 
- Provide Network Operator with one or more designated participant contact who will be responsible for engaging the support services by contacting Network Operator via designated methods using pre-authorized credentials. Where participant requires multiple participant contacts, please first open a dialogue with Network Operator to agree on a appropriate number of participant contacts. Individuals who are not designated participant contacts are not permitted to request Support.
- Ensure that participant contacts (and additional participant resources if requested) are suitably qualified and experienced, and are familiar with the Services, and provided further:
  - Enabled with enough access to their production operating environment to carry out Corda Software process diagnostics and retrieve Corda Software log and configuration files; 
  - Competent with the operating system running their Corda Network Nodes; 
  - Competent with running JVM based software and familiar with the way JVM based software executes;
  - Competent with any network and performance diagnostic tools considered standard for their operating system;
  - Comfortable with working through diagnostic procedures as described by the Support team.

- Provide access to required diagnostic information such as log files, configuration files, crash dumps etc.
- Provide Network Operator with a list of contacts for escalations and emergencies. It is recommended that this list includes email groups with more than one individual.
- Meet the minimum technical requirements to use the Corda Software and properly install the Corda Software, as set forth in the Corda Software documentation.
- Provide Network Operator with all reasonable co-operation to facilitate the efficient discharge of its obligations under this support handbook.
- Apply all patches and upgrades as required, after testing in a pre-production environment.

	  
## 7.1 Access to Participant Source Code

To the extent possible, and as requested by Network Operator, the participant may also be required to provide Network Operator or its authorized technical representative access to its source code in order to diagnose an Incident or otherwise provide Support. Participant acknowledges that if access is not provided as requested by Network Operator, response times, Incident determination and Incident resolution may be slower, impaired or impossible.

Network Operator will treat all source code as confidential and will not share it with anyone outside Network Operator. We will also take reasonable steps to only give access to engineers designated to investigate the Customer’s Incident or provide Support to Customer’s source code. Network Operator will not, under any circumstances, access or take action within participant’s own environments but may provide guidance, advice, or workaround suggestions to participant’s designated support contact who do have such access and rights. After an Incident has been closed, and upon participant’s request, Network Operator will destroy any copies of uploaded source code and, upon request, will certify to such destruction.

## 7.2 Remedial and Diagnostic Actions Requested by Network Operator

From time to time Network Operator may request that designated participant contacts and other resources carry out procedures or changes to source or configuration to establish a diagnosis or test a potential fix. These procedures and changes may be destructive in nature or have unexpected adverse effects, and while the Support team will take every reasonable effort to advise of any impact, it is the participant contact’s responsibility to apply due-diligence and ensure they are complying with their organisation’s change and backup policies.

## 7.3 Data Protection

Both parties acknowledge and agree that they will comply with all the provisions of Privacy Policy available at https://corda.network/policy/gdpr

## 8. Final disclaimers

Network Operator is not responsible for any participant Personal Data stored or otherwise used with any of Network Operator's proprietary software or on any network provided by Network Operator.

