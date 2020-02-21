# Environments Policy

## 1 Introduction

Corda Network is intended to serve transaction processing needs of major financial institutions with complex 
technical requirements. In particular,

*   The use of test data is expected to be prevalent throughout exploratory and testing activities; such data must be 
clearly segregated from authoritative (production) transactions.
*   There will be frequent requirements to test both participant node components and core network service components 
without operationally impacting production systems.
*   Participants conducting testing activities require clarity over the configuration and versioning of other 
participants and network services they are connecting to.

In line with standard practice, the Foundation seeks to address these requirements by implementing a series of 
controlled Network environments for both internal and external use. This document outlines the constraints within which 
environments are to be defined, implemented and managed on an on-going basis.

## 2 Usage Restrictions

The Foundation is accountable for ensuring that participants to specific environments are 
made aware of usage restrictions (e.g. no business transactions outside of production) in line with each environment's 
defined context.

It is acknowledged that, due to the distributed nature of the Corda Network, external participants cannot be forced to 
respect usage limitations by technical means. The legal team is accountable for implementing appropriate contractual 
mechanisms to enforce compliance with usage restrictions.

## 3 Environment Names

Each environment shall have an explicit name which distinguishes it from all other environments. The name shall follow 
a consistent convention which allows its context to be easily identified, e.g. a namespace-oriented convention.

Environment names are primarily for internal use; separate names may be used for external publication purposes but 
should be avoided where there is no explicit business need to do so. The Foundation is accountable for ensuring 
environments are named appropriately and managing any variance in internal vs. external naming to avoid confusion.

## 4 Governance

The Foundation holds accountability for ensuring Corda Network environments are defined, implemented and managed in an 
appropriate manner. Beyond this, responsibility for defining and monitoring specific aspects of environments rests with 
the Operator's DevOps, Operations, Testing, Information Security and Platform architecture teams.

In addition, each environment shall have an assigned Operator Environment Owner with accountability for initial 
delivery and subsequent management of that environment. The Operator is accountable for the appropriate assignment of 
Environment Owners.

## 5 Environment Specification

The parameters for each environment shall be specified in an Environment Specification, detailing the following:

*   Environment name.
*   Designated environment owner.
*   Environment context.
*   SLA, where applicable.
*   Access control restrictions, where applicable.
*   Specific on-boarding requirements.
*   Use of common PKI infrastructure, where applicable.
*   Core network services to be provided (Doorman, Network Map, Notaries by type and cluster).
*   Geographical focus of usage, where known (to inform deployment approach for minimal latency).
*   Applicable restrictions on cross-border data transfer and residence for core network services.
*   Support arrangements, where applicable.
*   Change management requirements (see below).

The specification of and subsequent changes to these parameters shall be subject to formal change control (see below).

The Operator is responsible for reviewing and approving all environment specifications for compliance with Foundation policies 
and strategic priorities, in consultation with the Operator's Operations, Legal, DevOps, Testing, Information Security 
and Platform Architecture teams.

## 6 Change Management

Creation of a new environment, modifications to existing environments, or termination of an environment, constitute 
changes subject to the [Change Management Policy](/policy/change-management). Formal change management is required for all 
production environments, and non-production environments where external stakeholders and/or the Operator would 
otherwise be exposed to operational and/or reputational risks from un-managed changes. The Operator is responsible for 
ensuring suitable change management is in place for all environments, including the timing and expedience for which a 
change can be implemented.

## 7 Asset Management

The Operator shall manage all assets associated with Corda Network environments. General management of assets is 
described in the [Inventory Management Policy](/policy/inventory-management).

Assets may be either environment-specific or non-environment-specific. Environment-specific assets may only be 
associated with one environment at any given time. Additionally, non-environment-specific assets may (but are not 
required to) be explicitly associated with a context grouping (see above) and be made available for use only by 
environments within that context; e.g. an HSM may be restricted for use in non-production, Operator internal environments.

DevOps are accountable for allocating assets to each environment according to the agreed environment specification, and 
ensuring environment-specific assets are managed and tracked appropriately.

## 8 Access Control

Access to environment-specific assets is controlled according to the [Access Control Policy](/policy/access-control).

Access controls may be varied on a per-environment basis; where environment-specific access policies apply, these must 
be defined in the Environment Specification in advance of the implementation of any environment.

## 9 Network User Access

The Operator shall take reasonable measures to prevent unauthorised access to Corda Network services. At a minimum, this will 
include controlling the provision of signed identity certificates which allow authenticated peer-to-peer messaging and 
transaction signing across the network. Additional measures (e.g. specific firewall configuration, VPN) etc. may also 
be deployed on a per-environment basis.

The Operator's architecture team is responsible for defining the appropriate network access control mechanisms to be implemented 
for each environment, in consultation with the Operator's operations team. The operations team is are accountable for 
ensuring all such access control mechanisms are correctly implemented and enforced on an on-going basis.

Environments may, where appropriate, share a trust certificate root and make common use of non-environment-specific PKI 
infrastructure. Platform Architecture are responsible for specifying which PKI assets should be used by which 
environments.

## 10 Administrative access

The Operator shall ensure that privileged access to all components running Corda Network services is controlled in 
accordance with relevant information policies, including the [Information Security Policy](/policy/security) and Corda Network
[Emergency Access Policy](/policy/emergency-access).

User access policies shall be defined on a per-environment basis as part of the Environment Specification (see above).
DevOps are accountable for ensuring that user access controls are implemented in accordance with the Environment 
Specification and maintained on an ongoing basis.

The following basic principles shall apply to administrative user access policies:

*   Access to all environments shall be limited to Operator personnel and external agents with whom appropriate logistical 
and contractual arrangements are in place to limit security risks.
*   Access to Production environments (see Environment contexts, above) shall be restricted to Operator operations 
personnel only, subject to exceptions defined in the [Emergency Access Policy](/policy/emergency-access).

# Incident management

The Operator shall manage all operational and security incidents in relation to environments in a controlled manner. 
The Operator is accountable for ensuring suitable procedures are in place.