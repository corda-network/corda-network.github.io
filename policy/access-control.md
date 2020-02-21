# Access Control and User Access Management Policy

## 1 Purpose

This policy documents the principles that govern the provision of access to sensitive Corda Network Foundation systems
and information, and the uses to which they may be put. Access will be granted in accordance with minimum necessary
required by the role of the individual or system requiring access. The purpose of this policy is to comply with legal
and regulatory requirements, to protect the Foundation’s reputation i, to ensure the effective delivery of services to
network participants and to meet contractual commitments by ensuring that access control requirements are appropriately
defined.

## 2 Risks Addressed

Inappropriately restrictive access controls may result in excessive costs for the protection of low value information or
systems, or loss of productivity as a result of an overly complex security regime. Alternatively, absent or
inappropriately permissive access controls may expose the Foundation to unavailability, disclosure, modification or loss
of high-value information. Access controls will therefore be applied in a manner that takes into account the
Foundation’s contractual, legal and regulatory obligations and is appropriate to the sensitivity of the information and
systems under consideration.

## 3 Control Objectives

The objectives of this policy are to ensure that the principle of least privilege is observed (and can be shown to be
observed) when granting access to all sensitive information and systems. This will be achieved by clear and unambiguous
definition of the rules under which access is granted.

## 4 Who Does This Policy Apply To?

This policy applies to employees and contractors, consultants, temporaries, and other workers at the Foundation. This
group is referred to as “users” throughout this policy.

## 5 Scope

All information and information systems developed, operated or used by or on behalf of the Foundation.

## 6 Mandatory Controls

Information or systems must be treated as information assets if the Foundation is sensitive to their loss,
unauthorised modification or disclosure.

Appropriate physical and logical access controls must be established for all Foundation information assets.

Information or systems not defined as information assets will not have any specific access control requirements.

All Information assets must have a corresponding owner. The information owner’s responsibilities include ensuring
that the asset is assigned an appropriate security classification, the asset is protected by appropriate controls and
access is granted to the asset only to those whose role requires it. The owner will also ensure that the asset’s
classification and protective controls are reviewed on an appropriate periodic basis.

Information owners are also responsible for maintaining the information asset catalogue (or more simply, “the
catalogue”) entries for all significant information assets under their ownership. The catalogue is a record of
information assets or groups of like information assets, along with important attributes such as their classification,
distribution list, retention period and the frequency at which user access rights to the asset should be reviewed.

### 6.1 Access Control Principles

The following policy statements describe mandatory controls for Foundation information assets.

Foundation production systems must be logically segregated from office and development systems.

All Foundation systems must implement an appropriate authentication scheme. An “appropriate” authentication scheme is
one that is aligned to the value of the services provided by the system in question. Multiple factor authentication
should be used where available. Authenticators (such as passwords or cryptographic tokens) must have appropriate
controls and tools in place to support revocation, replacement, lockout, expiry and other lifecycle management
activities.

The Foundation will maintain appropriate standards for the use of authenticators. These standards must be aligned to
the Foundation information classification policy. Deviations from these standards must be approved by the Information
Owner and the Information Security Manager.

Systems that cannot support appropriate authentication schemes must be protected by other “compensating” controls.
Such controls must be approved by the Information Owner and Information Security Manager.

All users must be allocated their own unique user ID for access to Foundation systems.

User IDs must, wherever possible, not reflect the nature of the role for which the account is used. Words such as
administrator, admin and manager should be avoided.

Shared user IDs may only be used where there is no alternative mechanism available. Use of shared user IDs must be
approved by the Information Owner and the Information Security Manager. Where shared user IDs are used, appropriate
compensating controls must be put in place.

User passwords or other authentication tokens must not be shared, written down or stored on information systems in
an unencrypted form.

Vendor default system passwords must be changed before system deployment.

All Foundation systems must, wherever reasonably practicable, present a login banner, warning of the consequences of
unauthorized access and that communications may be monitored and used in legal proceedings.

Any external network access to Foundation networks must be controlled by a firewall or similar traffic management
capability. External access must be limited to the minimum ports/protocols necessary to accomplish the required task.

The Chief Information Security Officer (CISO) or Information Security Manager may require a risk assessment
(according to the Foundation’s supplier risk assessment policy) to be carried out before providing external access to
Foundation information assets.

Depending on the result of the supplier risk assessment, the CISO or Information Security Manager may require the
deployment of additional technical or administrative security controls before external access may be permitted.

The Foundation operates a clear desk and screen policy. Sensitive information on hard copy or removable electronic
media must be locked away when not required, especially when the office is unoccupied.

All user, system and application sessions that are inactive for a predetermined amount of time must be
automatically terminated.  Systems and applications that cannot automatically terminate sessions should be protected by
compensating controls such as password protected screensavers or terminal locks.

The Foundation Management Team holds final responsibility for the protection of information assets.

### 6.2 User Access Management

The following policy statements apply equally to Foundation managed systems or to those operated on the Foundation's
behalf by external vendors. This policy may delegate to further operational policies and procedures for the details of
granting, modification, revocation and review of user access rights.

Access to Foundation information assets will be granted observing both the principle of Least Privilege (“Need to
Know”) and their classification. All user access should be limited to the minimum necessary for the user to fulfil their
business responsibilities.

Users must not seek to obtain elevated levels of access to an information asset without approval by the asset’s
owner. Any attempt, successful or otherwise, to obtain elevated levels of access without owner approval will be
considered a violation of this policy.

All user access to Foundation information assets must be approved by their owner or authorised deputy. For common
office automation systems (such as email, or new users home directories) which do not necessarily have a designated
owner, approval will be required from the user’s manager.

Formal user account management procedures must be in place for user registration, modification and deregistration on
all Foundation systems (on-boarding, access change requests and off-boarding).

Segregation of duties between user access request, approval and action must be maintained wherever possible. Such
segregation of duties is mandatory for Foundation maintained information systems, and highly recommended for third party
and outsourced systems. It must not be possible for users to approve and/or action their own access requests.

Users must only be provided with privileged or administrative accounts where required by their job function.
Authorization for administrative access to applications must be provided by the information or application owner.
Authorization for administrative access to infrastructure, or operating systems must be provided by the CISO or
Information Security Manager.

Information owners must ensure that user access permissions for information assets are maintained in line with the
user’s role and responsibilities. This requires the review of access permissions on a periodic basis as indicated by the
asset’s catalogue entry.

## 7 Compliance

Assessments may be carried out for compliance against this policy. Any violation of this policy will be investigated and
if the cause is found due to wilful disregard or negligence, it will be treated as a disciplinary offence. All
disciplinary proceedings are coordinated through the Human Resources Department. the Foundation reserves the right to
amend this policy at any time and will publish updated versions to all staff.