|Corda Network Foundation|[Document history]({{ site.github.repository_url }}/blame/master/{{page.path}})|

Configuration Policy
====================

1 Introduction
--------------
This document describes the policy for managing versioning of all technology resources employed in the delivery of 
Corda Network services.

2 Motivation
------------
The Corda Network comprises a complex technology stack which is likely to continue to grow in scale and complexity over 
time. Changes to Corda Network components (governed by the [Change Management Policy](change-management.md)) are likely 
to occur frequently, creating risk of 
disruption or otherwise inconsistent performance of Corda Network services over time. This policy seeks to mitigate 
these risks by ensuring that changes in configuration are co-ordinated over time.

3 Scope
-------
This policy covers all (physical & virtual) hardware and software components required to deliver Corda Network 
capabilities. This may include, but is not limited to:

*   Hardware provisioning.
*   Device firmware.
*   Operating systems.
*   Relevant middleware, e.g. Java Runtime Environments.
*   Corda-specific application components, e.g. certificate signing ('Doorman') services, network map services and 
notary services.

The following are out of scope for this policy:

*   Resources outside the Operator's direct control (business network operators and participant nodes).
*   Resources (e.g. Corda nodes) operated the Operator on behalf of external parties, which do not constitute core 
Corda Network services.
*   Corda node release management (except where this underpins a Corda Network service, e.g. Notary).

4 Principles
------------
Configuration management is subject to the following general principles:

*   **Immutable infrastructure**: To the extent possible, components will be effectively re-deployed rather than 
subject to updates and changes within the production environment. Re-deployment should be the default practice for all 
cloud-based infrastructure, with in-situ updates/configuration changes performed by exception only (and for 
physically-hosted resources). See the  for more information.
*   **Consistency**: Except where constrained by specific versioning requirements, updates should be applied to ensure 
version consistency of all instances of a given component within each environment, and between environments as 
appropriate.
*   **Operational continuity**: In the context of production environments and test environments with specific agreements 
in place, software updates should avoid loss of business continuity for users to the maximum extent possible. Planning 
of the deployment process may seek, for example, to progressively update workers within a clustered service whilst 
avoiding a situation where all members of the cluster are simultaneously down. This principle also reflects the 
requirement to retain continuity of user data through the course of the update process (see migration, below).
*   **Non-automatic**: All update operations should, in principle, be consciously instigated by a member of the 
operations team. Any automatic update features provided by software components should be disabled from the point of 
installation onwards.

5 Governance
------------
The operations team is collectively accountable for ensuring appropriate configuration management of all 
Corda Network services.

Within the operations team, a Technical Service Owner (TSO) shall be appointed for each Corda Network service.

In relation to that service, the TSO is responsible for:

*   Capturing and retaining up-to-date information on the configuration of all resources supporting that service.
*   Identifying the potential impact of any configuration change.
*   Ensuring such impacts are documented in each Change Request (CR) and considered in the CR review (see 
[Change Management Policy](change-management.md))).
*   Identifying which previous test outcomes are invalidated by the change, and ensuring these are re-tested prior to 
execution in a production environment.

TSOs for different services shall collaborate to ensure any inter-service impacts of changes are identified and managed.

6 Resource Naming
-----------------
The operations team is responsible for establishing and enforcing a fit-for-purpose convention for the naming of all 
Corda Network components. This naming convention should:

*   Relate resources to the environment(s) in which they are used.
*   Relate resources to the functions or services they support.
*   Be demonstrably consistent across each environment and between environments.

7 Resource Monitoring
---------------------
The operations team is responsible for maintaining up-to-date information on the configuration of all deployed 
resources, and should be able to share this information with internal parties upon request. Appropriate monitoring 
mechanisms should be implemented to facilitate this; where appropriate, such mechanisms should be implemented alongside 
operational monitoring tools to provide an integrate view of the Corda Network resource portfolio.

8 Asset Management
------------------
In addition to configuration management information, the operations team is accountable under the for tracking all 
physical and electronic assets of commercial value to the Operator.

Asset management and configuration management information should, where relevant, be closely integrated to ensure 
consistency and internal transparency for the purpose of informing financial decisions on the management of Corda 
Network resources.

9 Resource Deployment
---------------------
Deployment procedures (described in the [Deployment Policy](deployment.md)) must be appropriately designed and managed 
to facilitate effective configuration management, specifically to enable consistently repeatable deployment of 
configurations across instances and environments. 

10 External Disclosure
-------------------
The Operator shall enable external stakeholders (primarily Corda Network business network operators and participants) 
to obtain relevant, up-to-date configuration information in relation to the Corda Network environments and services to 
which they have access (see [Environments Policy](environments.md)).

The operations team is accountable for ensuring such information can be provided upon request. Where appropriate, 
mechanisms to publish this information on an automatic basis to external parties should be developed.

Forthcoming changes in configuration which impact external stakeholders must be scheduled in advance and communicated 
in accordance with the [Change Management Policy](change-management.md).

11 Corda Releases
-----------------
The configuration of Corda Network services is implicitly required to maintain compatibility with successive releases 
of the Corda software to be used by Corda Network participants. 

TSOs must maintain engagement with Corda release owners to ensure clear visibility of the pipeline of changes required 
to support each release. TSOs are accountable for raising CRs on a timely basis to ensure each environment is able to 
meet its requirements to support successive Corda versions. This should generally occur within the framework of a Corda 
release plan, management of which is outside the scope of this policy.