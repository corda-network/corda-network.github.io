|Corda Network Foundation|[Document history]({{ site.github.repository_url }}/blame/master/{{page.path}})|

Access Control Policy
=====================

1 Introduction
--------------
The Operator shall control access to all privileged functionality supporting the delivery of Corda Network services. 
This document outlines provisions under which access is controlled.

2 Scope
-------
In the context of this document, access covers:

*   Operational management access: Ability to access privileged functions of the (physical or virtual) hardware, 
operating system and other processes.
*   Network user access: Ability to connect to Corda Network services from a client device, e.g. a remote node operated 
by a Corda Network Participant.

This policy covers all environments associated with the delivery of Corda Network services in both pre-production and 
production contexts. Access control policy may vary on a per-environment basis, wherein some (e.g. test, staging 
environments) may enjoy more relaxed access controls than for production environments. Per the [Environments Policy](environments.md), 
environment-specific access policies will be defined in Environment Specification documents and applied accordingly.

3 Governance
------------
This policy is pursuant to [Access Control Policy](access-control.md). Provisions in this policy should be considered 
additive to those provided in the corporate policy.

The Foundation owns this policy and are responsible for ensuring it remains consistent with all related Operator 
policies.

4 Change Management
-------------------
A change in access permissions, at either the individual user or policy level, requires a Change Request to be raised 
and approved prior to implementation, in accordance with the [Change Management Policy](change-management.md).

The Operator is responsible for ensuring access policies defined in Environment Specifications comply with the [Security Policy](security.md). 
The operations team is responsible for ensuring all such access policies are correctly implemented in accordance with 
the Environment Specification, and enforced on an on-going basis.

5 Operational Management (Administrative) Access
------------------------------------------------
Operational management access to all Corda Network resources will be controlled. The operations team is responsible for 
implementing appropriate controls in accordance with Environment specifications (see [Environments Policy](environments.md)).

The following basic principles shall apply to operational management (administrative) access for the production environment:

*   No users shall have SSH access to virtual machines with root access.
*   Members of the DevOps team may, as appropriate, have SSH access to virtual machines with sudo access via their named 
accounts.
*   Members of the DevOps team may, as appropriate, have access to credentials enabling access to other resources 
(Azure console access, Azure SQL database usernames/passwords, etc.).
*   No other personnel should have SSH access to virtual machines or credentials to access other resources, subject to 
exceptions defined in the [Emergency Access Policy](emergency-access.md).

6 Network User Access
---------------------
The Operator shall take reasonable measures to prevent unauthorised access to Corda Network core services. At a 
minimum, this will include controlling the provision of signed identity certificates which allow authenticated 
peer-to-peer messaging and transaction signing across the network. Additional measures (e.g. specific firewall 
configuration, VPNs) etc. may also be deployed on a per-environment basis. 

The Environment Specification should define appropriate network access control mechanisms to be implemented for each 
environment. DevOps are accountable for ensuring all such access control mechanisms are correctly implemented and 
enforced on an on-going basis.

Environments may, where appropriate, share a trust certificate root and make common use of non-environment-specific 
PKI infrastructure. The Environment Specification should specify which PKI assets should be used by which environments.