|Corda Network Foundation|[Document history]({{ site.github.repository_url }}/blame/master/{{page.path}})|

Backup and Restore Policy
=========================

1 Introduction
--------------
This document describes stipulations regarding backup and restore activity in support of providing operational 
continuity for Corda Network services.

In this context, 'backup' refers to the capture of point-in-time snapshots of the state of data within a component, 
whilst 'restore' refers to the reconstitution of the state of a component to be consistent to a backup snapshot. This 
section does not refer to active replication for the purposes of ensuring high availability of a given component, 
except to the extent that a replica of a component can be legitimately regarded as a backup from which a restore is 
possible. 

2 Scope
-------
Backups are required for all data which is operationally significant, such that irrecoverable loss of that data would 
impact the Operator's ability to deliver services on Corda Network. Sources for applicable data are expected to be 
databases and other file stores containing stateful information resulting from interaction by Corda Network 
participants. This may include, but is not limited to:

*   Certificate Signing Requests and accompanying registration data.
*   Transaction data for notarised transactions.
*   Persisted flows by notaries.
*   Network map data.
*   Messaging, business event and systems logs.

In principle, backups are **not** required for the state of any component resulting from its deployment according to a 
deterministic deployment procedure. Inherently stateless components are therefore exempt from backup requirements, as 
are snapshots of the operating system, middleware and functional components which may be definitively restored via 
redeployment (see immutable architecture principle, above).

The operations team is responsible for identifying all instances of operationally significant data within Corda Network 
components.

3 Frequency
-----------
The frequency of required backups for any component are determined by the defined Recovery Point Objective for that 
component. The operations team is responsible for ensuring the software vendor defines and documents an appropriate 
RPO for each component. The operations team is responsible for controlling the frequency of execution of backup 
procedures (see below) in accordance with specified RPOs. 

4 Database Replication
----------------------
In the context of databases containing operationally significant data, replication should be used wherever this 
approach delivers on the specified RPO within other operational constraints (performance etc.). Wherever replication is 
determined not to be appropriate, a custom backup procedure (see below) must be designed and implemented. The Operations 
team is responsible for defining, with the software vendor, where database replication is to be used vs. backup procedure.

5 Backup Procedures
-------------------
In the absence of database replication, all activity to backup operationally significant data must follow a documented 
backup procedure. This section specifies the requirements for creating and managing deployment procedures.

### Procedure Development
The operations team should maintain standard backup procedures for common component types (e.g. doorman, notaries etc.).
The operations team may develop new procedures on an ad-hoc basis where new backup requirements are identified; such 
ad-hoc procedures must still be documented prior to being executed.

In principle, backup procedures should always be developed in a scripted form which allows automatic execution of the 
procedure. Backup procedures should be annotated with suitable comments to facilitate review of the document and 
subsequent auditing by knowledgeable parties, including a clear definition of what data is being backed up. All backup 
procedures must include appropriate controls to validate that the backup has completed correctly, and define appropriate 
handling of any exceptions.

Where a backup procedure cannot be scripted, or includes any manual steps, those manual steps must still be documented 
in a suitable form which facilitates review and audit. 

### Procedure Inventory
All backup procedures, once documented, should be retained in a code repository and subject to git-based revision 
control. The operations team owns this code repository ('backup procedure library') and is responsible for maintaining 
the content in an organised manner which facilitates efficient identification, execution and review of procedures, as 
well as ensuring it complies with the Data Retention Policy. The operations team also administers access to this 
repository. In principle, access should be restricted to members of the operations team team; the operations team team 
may at its discretion provide temporary access to specific Operator personnel to assist with specific business tasks.

Introduction of new backup procedures, as well as revisions to existing procedures, must be subject to a four-eyes 
quality review by a suitably qualified individual (typically another member of the operations team) prior to being 
committed to the library for subsequent use; the standard git PR review mechanism should be used to enforce this.

### Procedure Testing
All backup procedures must be tested before use. This must include executing the backup procedure within each 
production environment.

### Procedure Execution
All backup procedures should be capable of being executed on both a manual and an automated periodic basis.

Periodic execution of backup procedures should be configured using an appropriate scheduling tool (e.g. cron job). The 
operations team is responsible for determining the appropriate scheduling mechanism and configuring it in accordance 
with backup frequency requirements (see above).

Auditable evidence of the execution of all backup procedures must be captured and retained (see Data Retention Policy).

Backup procedures should be executed from designated machines, as determined by the Operator.

### Procedure Deployment
Backup procedures themselves require deployment onto a suitable machine. The Operator is responsible for determining 
where backup procedures should be deployed and run.

Deployment of appropriate backup procedures should be incorporated into the deployment procedure for any components 
with which they may be co-located, and subject to stipulations around deployment procedure control (see Deployment, 
above).

6 Storage
---------
The Operator, working with the software vendor, is responsible for specifying storage arrangements for backup of each 
component. Arrangements for any component backup will primarily be determined on the basis of:

*   RTO/RPO objectives specified for that component.
*   Any specific legal or regulatory requirements, e.g. requirements to retain data on a durable medium.
*   Voluntary compliance with any recognised industry standards, e.g. PCI-DSS, ISO27001.
*   Guidance on best practice by Information Security (see below).
*   Cost optimisation, including effective cost of infrastructure management.

The operations team is responsible for the implementation of backup storage arrangements specified by the Operator, and 
ensuring those arrangements are maintained on an on-going basis.

7 Security
----------
The operations team is responsible for specifying appropriate security measures to be implemented around the generation, 
shipping and storage of backups, in consultation with the Operator's Information Security team. In principle, security 
measures over backups are expected to be equal or greater than those applied to the sources being backed up. Relevant 
security measures may include, for example:

*   Requirement that backups are stored in an encrypted form.
*   Requirement that backup data is shipped over a secure connection with appropriate authentication mechanisms in place.
*   Restricting access to backup data with user authentication and formal access control administration.

Where the execution of a backup procedure requires access credentials to be provisioned to a particular component (e.g. 
an automated backup server), appropriate measures must be put in place to protect those credentials from unauthorised 
access.

The operations team is responsible for the implementation of all security measures as specified by the Operator, and 
ensuring the integrity of those measures is maintained on an on-going basis.

8 Retention
-----------
The Operator is responsible for specifying appropriate retention periods for different backups, in accordance with:

*   The Data Retention Policy.
*   Defined RPO objectives for each component.

Backups which exceed any limits specified in the Data Retention Policy must be deleted. 

The operations team is responsible for ensuring retention of files in compliance with specified retention periods on an 
on-going basis. Where a scripted procedure is used to automatically deleted backups which exceed the retention period, 
that procedure must comply with the same stipulations for documentation, retention, change control and testing applied 
to deployment procedures (See Deployment, above).

9 Restore Procedures
--------------------
Except in the case database replication, all activity to restore operationally significant data from backup must follow 
a documented backup procedure. Documented restore procedures must comply with the same stipulations for documentation, 
retention, change control, testing and verification applied to deployment procedures (See Deployment, above).

The operations team is responsible for the creation and management of all restore procedures in line with previous 
stipulations.

### Restore Point
In principle, the target of a restore procedure will be to restore to the most recent backup point captured.

The Operator, working with the software vendor, is responsible for identifying any exceptions to this, and ensuring 
such exceptions are recorded in this policy and noted by the operations team ahead of the execution of any restore 
procedure.

### Procedure Execution
The operations team is responsible for the execution of all restore procedures, and are accountable for ensuring timely 
execution in compliance with the defined RTO for each component. 

All restore procedures should, in principle, be consciously initiated by a member of the operations team team.

Auditable evidence of the execution of all restore procedures must be captured and retained (see Data Retention Policy).