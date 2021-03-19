# Updates and Patching Policy

## 1 Introduction

This policy applies to the Operator for updating software components which have already been deployed onto Corda Network 
infrastructure.

## 2 Triggers For Updates

The Operator's operations team is responsible for monitoring the release of updates to third-party components, including operating 
systems, middleware and monitoring applications. No stipulation is provided on how to perform this monitoring, although 
relevant (e.g. vulnerability management) tools may be used for this purpose. Once an applicable update release is 
identified, the operations team should raise a CR for the update, following the same approval and scheduling workflow 
as for other CRs.

Updates to Corda components should be requested (via CR) to the relevant software vendor Product Owner following 
deployment of a confirmed milestone release of that component.

The operations team is also responsible for monitoring the performance of hardware infrastructure and determining where 
any changes (e.g. to scale up a virtual machine's cores / memory) are required to deliver optimum performance of the 
network. Where a hardware change is recommended, the operations team should raise a CR for the update, following the 
same approval and scheduling workflow as for other CRs.

Updates may also be triggered by the identification of vulnerabilities in Corda, it's dependencies, or the underlying 
infrastructure platform. These could come from:

*   Vendor or CERT email bulletins.
*   Identification of dependency vulnerabilities during CI activities.
*   Identification of dependency vulnerabilities during workload or virtual machine image creation.
*   Identification of infrastructure vulnerabilities during routine internal or external vulnerability assessments 
against running infrastructure.
*   Incident response activities.

## 3 Principles

Update activity is subject to the following general principles:

*   **Immutable infrastructure**: To the extent possible, components will be effectively re-deployed rather than 
subject to updates and changes within the production environment. Re-deployment should be the default practice for all 
cloud-based infrastructure, with in-situ updates/configuration changes performed by exception only (and for 
physically-hosted resources).
*   **Consistency**: Except where constrained by specific versioning requirements, updates should be applied to ensure 
version consistency of all instances of a given component within each environment, and between environments as 
appropriate.
*   **Operational continuity**: In the context of production environments and test environments with specific agreements 
in place, software updates should avoid loss of business continuity for users to the maximum extent possible. Planning 
of the deployment process may seek, for example, to progressively update workers within a clustered service whilst 
avoiding a situation where all members of the cluster are simultaneously down. This principle also reflects the 
requirement to retain continuity of user data through the course of the update process (see migration, below).
*   **Non-automatic**: All update operations should, in principle, be consciously instigated by a member of the 
operations team. Any automatic update features provided by software components should be disabled from the point of 
installation onwards.

## 4 Vulnerability (Security Patch) Management

Vulnerabilities will be managed according to the following schedule:

*   Critical vulnerabilities (CVSS score > 9.0) will be patched within 7 days.
*   High vulnerabilities (CVSS score 7.0 - 8.9) will be patched within 14 days.
*   Low to medium vulnerabilities (CVSS score 0.1 - 6.9) will be patched within 30 days.

Where there is information that a vulnerability is being actively exploited "in the wild" (for example, when exploits 
are available in exploitDB or notification from vendor or vulnerability management software), mitigating action 
(patching or compensating control) should be taken immediately.

Where a patch is not deployed (or available) within the timescales above, then there must be alternative mitigating 
action or compensating controls applied.

### Change management

All updates and patches must follow the same change management process as for new deployments, including the 
requirements for CR approval, scheduling and testing. See the [Change Management Policy](/policy/change-management) for more 
information.

### Execution

The operations team are responsible for determining the appropriate method to apply an update in each case. Following the 
immutable infrastructure principle, component updates should take the form of re-deployment of the relevant resources, 
with in-situ patching performed by exception only. See the [Deployment Policy](/policy/deployment) for more information.

### Data migration

With respect to production environments and test environments with specific continuity agreements in place, all 
deployment procedures used to perform component updates must put specific measures in place to ensure continuity of 
operationally significant data (see [Backup Policy](/policy/backup-restore)) before and after deployment. In the 
majority of cases, is expected that, by design, relevant user data will be persisted in a separate component (database, static file stores etc.) such that 
frequent functional updates do not automatically require complex data migration.

Prior to designing and/or executing a deployment procedure, the operations team is responsible for confirming all 
implied data migration requirements in consultation with the software vendor. Where a requirement to migrate data is 
confirmed to exist, the deployment procedure must document how the migration of data will be performed and validated to 
remove all risk of irretrievable data loss or disruption of services.

Prior to commencing (or as part of) an update deployment procedure, all operationally significant data associated with 
the component to be updated should be backed up (see the [Backup Policy](/policy/backup-restore)).