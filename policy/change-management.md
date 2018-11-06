|Corda Network Foundation|[Document history]({{ site.github.repository_url }}/blame/master/{{page.path}})|

Change Management
=================

1 Proposed policy
===================

The Foundation and its Operator(s) shall apply controlled processes to the creation and modification of all 
infrastructure and applications supporting Corda Network.

In the context of this document, 'change' describes any modification to the scope or configuration or hardware and/or 
software components supporting  Corda Network. This includes:

* Creation of a new Corda Network environment (see )
* Deployment of new hardware or software components (see ) into a  Corda Network environment
* Deployment of updates and patches (see ) to  Corda Network components

Not included under this policy are:

* Changes to any component not controlled by the Foundation.
* Changes to Corda nodes, operated by the Foundation or its Operator(s)on behalf of the Foundation or other 
Participants, which do not themselves constitute Corda Network components (e.g. notary nodes).
* Changes to stateful data held by services and components which does not affect the operation of  Corda Network 
services - e.g. revocation of participant node certificates not relating to  Corda Network components. 

2 Governance
============

The Operator(s) is accountable for ensuring suitable change procedures, compliant with this policy, are in place and 
maintained on an on-going basis.

3 Testing
=========

Any intended change to a production environment must be tested in a non-production environment prior to execution. 
Testing should follow standard the Foundation testing practices.

The Operator(s) are accountable for:

* Maintaining suitable test environment(s) for the purpose of testing changes prior to production release.
* Ensuring all related testing activity takes place.
* Ensuring testing outcomes are captured and documented.
* Identifying any issues arising from testing which imply a risk if deployed to the production environment.
* Where a deployment risk has been identified, proposing amendments to the CR to mitigate or negate this risk prior 
to execution.

4 Change requests
=================

A **Change Request (CR)** must be raised for any intended change to a Production environment prior to its 
execution.

Prior to submission for review, each CR must include an unambiguous description of:

* Which environment(s) the change applies to.
* The change to be undertaken, detailing all components to be added/removed/updated and the nature of the change for 
each.
* Evidence of testing activities undertaken to validate the change.
* The envisaged impact to other components and  Corda Network services.
* External stakeholder groups which may be impacted by the change.
* The business rationale for the change, including requirements to be satisfied by the change, where relevant.

A CR may capture changes to multiple components, but should reflect a single logical package of changes with a common 
business rationale. Multiple changes to achieve different business objectives should be presented under separate CRs and 
reviewed independently.

CRs should be captured and maintained using a suitable workflow management tool (e.g. JIRA) which facilitates review and 
approval (see below) and allows subsequent audit and reporting of CRs. DevOps are accountable for management and 
accessibility of CR records, regardless of whether JIRA or another mechanism is used. 

CRs may also be raised for non-production environments where the level of operational exposure justifies formal 
change management. The requirement to raise CRs in these cases depends on the environment-specific policy.

5 Review and approval
=====================

At a minimum, all CRs must be reviewed and approved by one representative from each of the following groups with the 
Operator(s), prior to execution:

1. Head of Delivery and Strategy, COO, CTO, Chief Engineer or equivalent.
2. DevOps.
3. Security.

Additional reviewers may be appointed on an ad-hoc basis, depending on the context of the change. The Operator(s) is 
accountable for ensuring suitable reviewers are nominated and engaged as needed. This may include (e.g.) lead developers 
from feature teams, DevOps Technical Service Owners (TSOs), Support team members etc.

Simultaneous discussion between all reviewers (e.g. in a live meeting) is not required, but meetings to achieve 
consensus may be convened when needed.

Where any non-trivial (spelling, grammar etc.) change is made to the content of a CR prior to its execution, existing 
approvals to that CR are invalidated and the CR must be re-reviewed by all reviewers.

All review outcomes (approved/rejected, per reviewer) must be captured, documented and made visible to viewers of the 
CR. The overall status of the CR (approved/rejected) should also be presented in a reportable form.

DevOps are accountable for providing a suitable mechanism and establishing standard practice for this (e.g. comments on 
a JIRA, JIRA status)

6 Prioritisation
================

Each CR should be assigned one of three priority levels, prior to review:

1.  Standard: No impact of non-immediate execution to external stakeholders or the Foundation operations. 
Includes routine changes in line with general maintenance of the environment, e.g. security patches, upgrades.
2.  Urgent: External stakeholders or the Foundation's operations likely to be impacted by a delay in execution. 
Includes fixes/upgrades to key components required.
3.  Emergency: Critical operational or reputational risk to the Foundation from non-execution, sufficient to justify 
bypassing the normal review process (see Emergency changes, below). May include response to cyber-attacks, rollback of 
changes causing severe network disruption, etc. 

Operator(s) are responsible for assigning priority levels to each CR. The priority level should be approved in 
line with approval of the CR.

7 Execution
===========

Operator(s) are responsible for determining the appropriate method(s) to execute any CR. Following the immutable 
infrastructure principle, changes should generally take the form of (re-)deployment of resources to the relevant 
environment(s).

By exception, other methods (e.g. manual re-configuration) may be used. Operator(s) are accountable for ensuring all such 
methods are carried out in a controlled way and for capturing evidence of correct execution.

7.1 Scheduling
--------------
Execution of CRs should be scheduled in advance. Operator(s) are accountable for scheduling of CR activity and ensuring 
changes are carried out according to the schedule.

Scheduling should follow the agreed prioritisation of CRs (see Prioritisation, above).

Scheduling of CR executions should seek to minimize disruption to Corda Network services.

To the maximum extent possible, scheduling of CR executions should ensure compliance with  Corda Network Service Level 
Agreements (SLAs) provided to business network operators and other participants. These SLAs generally define operational 
'working hours' for  Corda Network services; CR execution should, in principle, always be scheduled outside these times.

Operator(s) must keep the Foundation informed of the CR execution schedule.

7.2 Communications
------------------
External stakeholders to be impacted by the change, identified within the CR, should be advised in advance of scheduled 
changes. The Platform Head of Delivery and Strategy is accountable for ensuring suitable communications are produced and 
distributed to relevant stakeholders on a timely basis.

8 Emergency changes
===================

Exceptional circumstances may necessitate bypassing the normal review process in order to address critical operational 
or reputational risks to the Foundation. This may include response to cyber-attacks, rollback of changes causing severe 
network disruption, etc. 

Emergency changes may be executed by DevOps without raising a CR in advance or securing formal prior approval according 
to the standard process outlined above. 

Operator(s) are accountable and responsible for identifying and executing Emergency changes, and may do so at their 
discretion, subject to the following conditions:

* Approval must be obtained from one of the Operator(s) CTO, Chief Engineer, or equivalent, on a verbal or written 
basis, prior to execution.  
* The Operator(s) is responsible for implementing a (e.g. rota) mechanism for ensuring that one of the named 
approvers is contactable at any point in time.
* Testing in a non-production environment should still be carried out in advance where feasible.
* Conventional procedures to access relevant resources should be used wherever possible, with break-glass procedures 
invoked by exception only. 
* Immediately following execution:
    * An operational incident must be raised and progressed according to the the Foundation incident management policy
    * A retrospective CR must be raised, detailing the rationale for the emergency change and requesting retrospective 
    approval from relevant reviewers.