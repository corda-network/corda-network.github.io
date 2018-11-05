The Corda Network Foundation
==============================

Incident Response
=================

[Document history]({{ site.github.repository_url }}/blame/master/{{page.path}})

1 Introduction
==============

1.1 Purpose
-----------
Computer security incident response is a part of the day to day business activities of the Foundation. This document 
defines the Foundation’s policy for reporting, prioritising and managing the response to such incidents.

1.2 Risks addressed
-------------------
Failure to comply with this policy may expose the Foundation to prolonged and uncontrolled impact from information 
security incidents.

Furthermore, failure to comply with this policy may constitute a breach of the Foundation’s legislative, regulatory 
and or contractual obligations.

1.3 Who does the policy apply to?
---------------------------------
This policy applies to employees and contractors, consultants, temporaries, and other workers at Corda Network 
Foundation, or its Operator(s), including all personnel affiliated with third parties – in short, it applies to everyone.

2 Scope
=======

All Foundation information, information assets and systems.

3 Policy Guidance
=================

3.1 Everyone has a role to play
-------------------------------
The biggest challenge to effectively responding to a computer security incident is its detection and assessment. Whilst 
some incidents may be readily indicated by automated system alerts or spotted by keen* eyed systems or network 
administrators, other indicators of potential incidents may not be so immediately visible.

For example, a staff member may have a personally owned computer that they use to access the Foundation systems which 
is subject to a malware infection. Systems and network administrators may be completely unaware of this as they have no 
administrative access to the device and it is not part of the Foundation’s antivirus protection.

Alternatively, a customer services team member may become aware through the grapevine that an external entity with 
whom Participants have a network connection is under attack by activists. Again, there is no guarantee that those 
responsible for incident response will also be privy to that information.

From these examples, it can be seen that incident detection is a complex problem. the Foundation’s ability to 
effectively detect and respond to incidents spreads beyond the bounds of the IT, DevOps and Support teams. Everyone 
in the organisation has a role to play.

3.2 How detect we detect security incidents? 
--------------------------------------------
A computer security incident is any real, suspected or imminent threat of compromise of the security of data or 
systems. Examples of incidents include:

* Malware infection of one or more systems.
* Defacement of the the Foundation website.
* Distributed denial of service attack against Internet facing systems.
* Extortion by threat to reveal trade secrets or client data.
* Compromise of remote access systems resulting in exposure and possibly breach of confidentiality of trade secrets.
* Violation of company security policy (e.g. emailing login credentials).

Some security incidents (such as the extortion example) will be obvious, but in the majority of cases identification 
of the incident will not be so straightforward. Often an incident may be detected only through one or more **events** 
 that are **indicators** of the incident.

An **event** is defined as any observable occurrence in a system or network. Routine events may include a server 
receiving a request for information, a user sending an email or a firewall blocking an undesired inbound connection. 
**Adverse** events are events that have undesirable consequences, such as a system crash, unauthorised access to 
controlled data or destruction of data by malware.

Although it may be possible that an event is easily recognisable as an indicator of an incident (for example, 
notification of malware detection by antivirus software), other events may be less obvious. Some examples of 
indicators of an incident include:

* A systems administrator noticing an unplanned configuration change.
* Unexpected processes running on a host.
* A network administrator noticing deviation from typical network traffic patterns.
* Apparently legitimate email containing unexpected or unusual content.

Incident detection and analysis is complicated by the fact that indicators may be vague or even incorrect. Complaints of 
system unavailability may be as a result of the user suffering local system or network issues, unusual emails may be as a 
result of a contact acquiring a new smartphone or company domain name changes.

Given this uncertainty, and the potential for “false positives”, it is sensible to adopt a prudent approach to 
investigating adverse events. We must assume that such events may be indicators of an incident until they are shown 
to be otherwise after investigation by experts.

3.3 Your obligations
--------------------
All employees and associates are required to:

* Be continually vigilant regarding events that might be indicators of security incidents.
* Comply with the mandatory controls in this policy, in particular you must ensure that suspicious events and 
suspected incidents are promptly reported.

4 Mandatory Controls
====================

4.1 The Response Team and Response Plans
----------------------------------------
The Foundation will maintain a computer security incident response team (CSIRT). 

The CSIRT extended team will include members of the DevOps, support, IT support and development teams. 

The Foundation will maintain a computer security incident response plan that implements this policy. The CISO (or 
individual performing that role) is responsible for the development and maintenance of the plan and may delegate day 
to day activities to the Information Security Program Manager.

4.2 Reporting and Response
--------------------------
All suspicious events and suspected incidents must be reported to the CSIRT. Initial reporting must be via telephone to 
the CSIRT response line on +44 (0)207 1131478.

On receipt of an incident report, the responding CSIRT team member will ensure that the computer security incident 
response plan is activated.

Every incident will be allocated an individual to act as Incident Handler. This individual will be the point of 
contact for the duration of the incident response activities.

The Incident Handler’s primary responsibility is to ensure the integrity of the incident handling process. They may 
be able to handle simple low* impact incidents (such as isolated malware infections) alone. Higher impact incidents 
may require a larger handling team to be assembled from the wider incident response team.

The Incident Handler will ensure that comprehensive records of the incident from reporting to closure and any actions 
taken in response are maintained.

4.3 Incident Classification and Prioritisation
----------------------------------------------
Incident handling must be prioritised based on relevant factors, rather than on a first-come, first-served basis. The 
Foundation computer security incident response plan includes a classification scheme that includes functional and 
information impact (combined as the business impact) and the level and type of resources required to recover from the 
incident. All incidents must be assessed according to this scheme as part of the triage phase the incident response 
activity.

4.4 Maintenance of Production Services
--------------------------------------
Where there is a conflict between containment of a security incident and preservation of evidence, and maintenance of
production services, the Foundation will usually prioritise the maintenance of production services wherever possible. 
If the steps to contain of an incident or preserve evidence are likely to result in medium or above functional impact 
to the production service, approval to implement must be sought from the Operator COO, Chief Engineer or CTO.

4.5 Incident Notification and Communications
--------------------------------------------
The following individuals of the Operator must be notified as a matter of course for incidents of for low and above 
functional impact (one or more critical services operating at a reduced but tolerable level of performance). They 
may also be notified in the event of a breach of information classified as internal or above:

* CISO.
* Information Security Manager.
* Support Engineering Manager (for production systems
 only).
* Head of Delivery (for production systems only).
* Lead developer for involved subsystem (production systems only).
* Head of DevOps.
* Head of HR (for incidents involving employees).
* Legal Counsel (for incidents with legal ramifications).
* Other individuals may be notified at the discretion of
 the incident handler.

The following additional individuals must be notified in the event of medium or above functional impact (one or more 
critical services are operating at an unacceptably reduced level or performance), or in the event of breach of 
information classified as confidential or above breach:

* CFO
* CEO

The Incident Handler must continue to provide status updates to the notified parties during the course of the incident 
response. Status report intervals must be communicated to the relevant parties at notification time and may be via 
email or telephone conference.

External communications must be handled with regard to the sensitivity of the information concerned, the relationship 
with the external entity and any liability that the Foundation might have. The incident response team may communicate 
directly with service providers and product vendors for the purposes of investigation and analysis, but all other 
communication should be handled by the relevant relationship manager with input from Legal Counsel as dictated by the 
incident impact.

4.6 Interaction with Law Enforcement
------------------------------------
The Foundation may take the decision to involve law enforcement to handle a security breach. Any decision to involve 
law enforcement must be taken in the light of any regulatory obligations to which the company is subject. Incident 
handlers or other staff members must not independently initiate any conversation with law enforcement. Any decision 
should weigh regulatory and client obligations against loss of control of the incident investigation and potential 
public disclosure of the incident. Decisions to involve law enforcement rest at COO and CEO level and must involve HR
and legal counsel.

4.7 Evidence Gathering and Handling
-----------------------------------
The incident handler must clearly document how all evidence gathered during the incident handling process has been 
preserved.

Evidence should be accounted for at all times. Where evidence is transferred from one person to another, chain of 
custody forms should detail the transfer and include each person’s signature.

5 Compliance
============
Regular assessments are carried out for compliance against this policy. Any violation of this policy will be 
investigated and if the cause is found due to wilful disregard or negligence, it will be treated as a disciplinary 
offence. All disciplinary proceedings are coordinated through the Operator(s) Human Resources Departments.

The Foundation reserves the right to amend this policy at any time and will publish updated versions to all Operator(s).


