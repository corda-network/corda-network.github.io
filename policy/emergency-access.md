|Corda Network Foundation|[Document history]({{ site.github.repository_url }}/blame/master/{{page.path}})|

Emergency Access Policy
=======================

1 Introduction
--------------
All Corda Network components associated with a production environment must have clearly stated and widely understood 
procedures for allowing access via alternate and/or manual methods in the event of an emergency. The Operator's operations 
team is responsible for development, documentation, implementation and testing of these procedures.

2 Triggers for emergency access
-------------------------------
Emergency access may be required in order to execute an emergency change as defined in the [Change Management Policy](change-management.md). 
Such scenarios imply immediate, critical operational or reputational risk to the Foundation, sufficient to justify 
bypassing normal procedures. This may include responding to cyber-attacks, rolling back changes causing severe network 
disruption, etc. 

Where possible, such emergency changes should still be performed using conventional access procedures. However, 
scenarios exist in which normal access procedures may not allow for timely execution, such as:

*   Account issues, wherein a privileged user (e.g. member of an operations team) is unable to gain required access due to 
lost/forgotten passwords, misplaced keys, unforeseen account expiry etc.
*   Authentication issues, e.g. due to damaged smart cards, card reader devices, or failure in authentication systems.
*   Authorisation issues, wherein a user is required to act in an unforeseen capacity where they lack suitable 
authorisation.

Under such scenarios, emergency access ('break glass') as defined in this policy may be invoked.

3 Governance
------------
All emergency access is subject to the [Access Control Policy](access-control.md), under which:

*   Distribution of emergency access credentials to authorised incident responders must be pre-approved by the 
Information System Owner.
*   If there are no staff approved for emergency access available to respond an incident, the Information System Owner 
or their deputy must approve access on a case-by-case basis. Access granted in this way must be revoked as part of the 
post-emergency maintenance unless the individual concerned is to be added to the standing list of pre-approved 
responders.
*   Information Systems Owner must review the list of users approved for emergency access on a yearly basis and whenever 
individuals join or leave the operations team.

4 Emergency Access Credentials
------------------------------
The operations team is responsible for definition and managing credentials appropriate for emergency usage. 
In principle, root system accounts should not be used by default. Instead, dedicated emergency user accounts should be 
pre-created which are:

*   Clearly recognisable as emergency accounts by name (e.g. "EMERGENCY01" etc.).
*   Protected by strong passwords.
*   Limited in access privileges to those that may reasonably be required under an emergency scenario.

Emergency access credentials must be made available for rapid distribution in the event of an emergency. The operations 
team is responsible for defining and managing secure arrangements for the storage of emergency access credentials.

5 Execution
-----------
The Operator operations team is accountable for ensuring correct execution of all emergency access procedures. 

A full audit trail must be captured of all emergency access procedures. Where automatic logging mechanisms do not fully 
capture all stages of the emergency access procedure, a manual audit trail must be captured by parties involved in 
executing the procedure. The operations team is accountable for ensuring that relevant audit trail records are 
captured and retained.

The [Change Management Policy](change-management.md) provides additional stipulations on subsequent handling of 
emergency changes.

6 Post-Emergency Maintenance
----------------------------
In principle, emergency access passwords must be changed as soon as possible following the emergency. Exceptions to 
this are permitted in cases where it can be demonstrated that emergency access passwords were not made accessible to 
any party who would not normally have access to that password (e.g. anyone outside the operations team).

Where the emergency procedure has resulted in any change to the configuration of a Corda Network component, the 
operations team must raise a CR to re-deploy that component (in accordance with the immutable architecture principle) 
and progress through to redeployment as possible following the emergency.