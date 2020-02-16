# Production Environment Service Level Agreement

This document is correct as of 25th November 2019.

Please note that the terms of this Service Level Agreement (SLA) are subject to change. Participants will be notified of any material changes via the contact contained in the Certificate Signing Request for each node unless alternative contact details are advised.

## Contents

- [1. Definitions](#1-definitions)
- [2. Introduction](#2-introduction)
  - [2.1. Scope](#21-scope)
  - [2.2. Assumptions](#22-assumptions)
  - [2.3. Support](#23-support)
- [3. Service Levels](#3-service-levels)
  - [3.1. Availability](#31-availability)
  - [3.2. Identity Operator](#32-identity-operator)
  - [3.3. Network Map Service](#33-network-map-service)
  - [3.4. Notary](#34-notary)
- [4. Change Management](#4-change-management)
  - [4.1. Ongoing Maintenance](#41-ongoing-maintenance)
  - [4.2. Network Infrastructure Patching](#42-network-infrastructure-patching)
  - [4.3. Emergency Maintenance](#43-emergency-maintenance)
  - [4.4. Platform Upgrades](#44-platform-upgrades)
  - [4.5. Network Parameter Updates](#45-network-parameter-updates)
  - [4.6. Scheduled Downtime](#46-scheduled-downtime)
  - [4.7. Unscheduled Downtime](#47-unscheduled-downtime)
  - [4.8. Change Freezes](#48-change-freezes)
- [5. Business Continuity](#5-business-continuity)
  - [5.1. Backups](#51-backups)
  - [5.2. Data Retention](#52-data-retention)
  - [5.3. Recovery Time Objective](#53-recovery-time-objective)
  - [5.4. Recovery Point Objective](#54-recovery-point-objective)
- [6. Reporting and Service Credits](#6-reporting-and-service-credits)
  - [6.1. Reporting](#61-reporting)
  - [6.2. Service Credits](#62-service-credits)

## 1. Definitions

| Term                      | Description                                                                                                                                                                                                                                                                                                                                            |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Business Network Operator | A Business Network Operator may set-up and operate its own business network for groups or companies that wish to transact together on the Corda Network. Depending on their size, Business Network Operators may also wish to on-board, off-board their members.                                                                                       |
| Corda Network Foundation  | A not-for-profit legal entity type known as a Stichting residing in the Netherlands. The Foundation governs the Corda Network and enables Network participants to be involved with, and also understand, how decisions are made (including around issues of identity and permission), building trust and engagement from a wide range of stakeholders. |
| CorDapp                   | Applications designed to interact with the Corda Network, built on the Corda platform.                                                                                                                                                                                                                                                                 |
| Network Operator          | The network operator appointed by the Corda Foundation who undertakes all day-to-day activities associated with delivering the network services outlined within Section 2 of this document.                                                                                                                                                            |
| Participant               | A legal entity participating in Corda Network and using one or more of the services provided by the Foundation.                                                                                                                                                                                                                                        |
| Production network        | The network operated by the Corda Foundation for participants to transact using ‘Live’, real world information and data. This environment is not for development/sandboxing purposes.                                                                                                                                                                  |

## 2. Introduction

This document defines standard Service Levels offered by the Corda Network Foundation (the ‘Foundation’) for organisations operating on the Corda Production Network.

The Corda Network operates under a single set of rules and policies set by the Foundation’s Board of Directors, which is comprised of its earliest customers. Further details are available at on the Corda Network website. The Foundation appoints a Network Operator, who undertakes all day-to-day activities associated with delivering the network services described in Section 2 of this document.

Users of CorDapps in any jurisdiction will need to ensure that their usage of the Corda Network complies with any local rules and legislation to which they are subject. Corda Network will support real-world assets, real-world identities and legally enforceable contracts between counterparties. Data will be long-lived and immutable. As such, the security model for Corda Network is consistent with the high value (and risk) of the activities being undertaken by its Participants.

This document defines:

- Services included in the Corda Network.
- The appropriate service levels for each service.
- Actions on non-performance/remediation.

Corda Network Participants accept the service levels contained within this document upon signing of the Corda Network Terms of Use, unless otherwise stipulated in such Terms of Use.

### 2.1. Scope

This document applies only to the Production Network and its constituent services as described in this document, and not to any other environments operated by the Foundation or the Network Operator.

### 2.2. Assumptions

- This agreement is available to all Participants of Corda Network – as defined on the [Corda Network website](https://corda.network).
- Expected Participant and transaction volumes for the period of use have been previously communicated to the Foundation and agreed as suitable for this standard SLA.
- A start date for usage of the Production Network services has been agreed at least four (4) weeks in advance.
- Direct Participants, or Business Network Operators may operate more than one application within Corda Network and the Service Levels described here apply to each.
- This Service Level Agreement excludes details of support processes and incident severity levels which can be found within the Corda Network Support Handbook on the [Corda Network website](https://corda.network).

### 2.3. Support

- The Network Operator supports Corda Network Services according to the service levels documented in the Support Handbook found on the [Corda Network website](https://corda.network).

## 3. Service Levels

The service levels contained within this section will apply during the term of Participants’ membership agreement of Corda Network.

The most up to date, detailed information about the services which Corda Network Foundation provides can be found [here](/about/concepts).

Please note that some services are guaranteed on a business hours basis. Business hours is defined as Monday to Friday from 00:30 UTC+0 to 21:30 UTC+0, excluding weekends and public holidays, in the territories of the United Kingdom, United States and Singapore.

### 3.1. Availability

The following services will operate with >99% availability on a business hours basis during each calendar month. Definitions of availability for each service are included below.

- **Identity Operator**

  > The Identity Operator service is considered available if it is able to successfully receive requests for new certificates submitted for the Corda Network.
  > _This is measured by monitoring the service endpoint to ensure a valid status code is returned, and checking that the underlying worker process is running._

- **Network Map**

  > The Network Map service is considered available if it is able to provide a network map upon request.
  > _This is measured by monitoring the service endpoint to ensure a valid status code is returned, and checking that the underlying worker process is running._

The following services will operate with >99% availability on a 24/7/365 basis during each calendar month. Definitions of availability for each service are included below.

- **Notary**

  > The Notary service is considered available if it is able to successfully receive, process and notarise transactions.
  > _This is measured by monitoring test transactions to ensure they are being received and processed as expected by the notary._

The following exclusions apply for service availability:

- Network connectivity problems or hardware/software failure outside of the Foundation’s control affecting the connectivity of Participant nodes or any other Participant hardware/software to the Network services i.e. Participant node, network or system failures.
- Planned system downtime required for essential maintenance of Corda Network service components.

### 3.2. Identity Operator

The completion of a Certificate Signing Request (CSR) is measured from the time of receipt of a correctly formatted signing request by the Foundation Identity Manager to the time at which a response is submitted to the requesting node. The Identity Manager process can handle multiple certificate signing requests in parallel.

> 95% of valid CSRs will be completed within 2 business working days each calendar month, excluding wait time for responses to confirmation or clarification requests from the Participant or Business Network Operator. Guidelines for submitting a CSR request can be found on the Foundation website [here](/trust-root/certificate-practices.html).
> Unless the Participant is being sponsored onto the Corda Production Network, the Identity Manager process requires the Participant to respond to a confirmation request. Service levels quoted here for turnaround time specifically exclude the duration of such Participant response.

The Identity Manager may reject the certificate signing request if the data is not constructed according to the standards set out in the User Guide. Amended CSRs will be subject to the same SLAs as new certificate signing requests.

Participants requesting re-certification, either to generate new keys, or to amend information on an existing and valid certificate, will start a new node and request a new certificate in exactly the same way as the original certificate and this will be subject to the same service levels. The Distinguished Name of the new identity must be unique (not the same as the previous identity). Details such as the IP address of the node can be changed without re-certification by sending a new configuration file directly to the Network Map server.

### 3.3. Network Map Service

Completion of Network Map updates as a result of successful certification of a new node is measured from the time a certificate is issued from the Identity Manager, to the time at which the updated Network Map is placed upon the distribution site(s). Participants are responsible for updating their own nodes with the revised information.

> 95% of Network Map updates for new nodes will be completed within 1 hour of the CSR being approved by the Identity Operator each calendar month.

### 3.4. Notary

The completion time for transaction notarisation requests is measured from the time the inbound request is received on a Production Network notary to the point at which the outbound reply leaves a Production Network notary. This metric assumes that correctly formatted and structured notarisation requests are received only.

Notarisation requests are treated individually, in sequence of receipt, by the notary working from an inbound queue.

> The average time taken to process notarisation requests as measured over a five (5)-minute* interval will be <240 seconds for 99% of each calendar month.
> *\*Each five-minute interval for measuring notarisation requests is approximate. Each interval is distinct, with a new five-minute measurement interval beginning once the previous one ends. Measurements are not taken as a five-minute rolling average. This means there are approximately 12 measured intervals per hour.\*

## 4. Change Management

All changes to Corda Network infrastructure are communicated via the Network Operator’s [service dashboard](https://cordanetwork.statuspage.io/), which will automatically send notifications for the scheduling and progress of each change to node operators via the contact contained in the CSR for each node unless alternative contact details are advised.

### 4.1. Ongoing Maintenance

Regular system maintenance is required to ensure the ongoing performance, stability and security of the Corda Network. To maintain continual service improvement at velocity, the Network Operator adopts an Agile framework for the identification, development and deployment of changes. This means that small, low-risk platform changes that are non-service impacting are deployed as often as required. These types of changes do not require a maintenance window and will not be communicated via the Operator’s service dashboard.

Larger changes with additional complexity, such as platform upgrades, will be subject to the process outlined in the [‘Platform Upgrades’](#44-platform-upgrades) section within this document.

Any changes that require service impacting system downtime will be subject to the process outlined in the [‘Scheduled Downtime’](#46-scheduled-downtime) section within this document.

### 4.2. Network Infrastructure Patching

Infrastructure patches are applied on a recurring monthly schedule. These activities are usually low risk and non-service impacting. Details of the change, including the relevant change windows, will be communicated a **minimum of five (5) business days in advance** via the Network Operator’s service dashboard.

### 4.3. Emergency Maintenance

On occasion, emergency maintenance may be required in response to a real or perceived vulnerability, security threat or unexpected service disruption. Emergency maintenance will be communicated as soon as practicably possible via the Network Operator’s service dashboard.

### 4.4. Platform Upgrades

It is important that Corda Network is able to take advantage of new releases without undue delay and so the normal mode of operation is for services to be regularly upgraded to the latest Corda platform version. Corda Network platform version upgrades will not normally require customer nodes to upgrade and in the majority of cases will be non-service impacting for node operators.

Planned platform upgrades that do not require action from node operators will be communicated a **minimum of five (5) business days in advance**.

However, there may be certain upgrade scenarios that do require action from Participants:

- Corda Network upgrades that require action from Corda Network Participants to accept new network parameters are subject to the change process and timelines defined for the Network Parameter Updates process [below](#45-network-parameter-updates).
- In the event that an upgrade does require customer nodes to upgrade, the Network Operator will post intention to upgrade Corda Network services a **minimum of three (3) calendar months in advance of the event** and will conduct its own testing in a separate environment before making the upgrade. Customers will be invited to support such testing by operating test nodes in such an environment. It may not be possible to test with every CorDapp, nor should it be necessary.

In the rare event of issues arising, any issue will be treated as an incident and managed according to the service levels defined in the Corda Network Support Handbook.

### 4.5. Network Parameter Updates

All Corda Network Participants have agreed to operate with a common set of network-wide parameters that each node using the Corda Network downloads alongside the Network Map. From time to time these network parameters need updating to ensure the continued smooth operation of the network.

Updates will be required whenever the following scenarios occur:

- A new notary is added to the environment.
- A Participant whitelists a new contract.
- The minimum platform version is upgraded.
- The maximum message and / or transaction sizes are increased.
- The network epoch value is increased.
- The event horizon is changed (the amount of time a node can be un-contactable before being retired from the network).

Many types of update processes will be entirely transparent to users and can be executed during normal working hours. Updates will be advertised at least **ten (10) business days in advance**.

The update process incorporates a node polling activity that ensures all node operators see the requested changes in advance and can choose to accept/not accept. The Foundation will consult with customers should there be disagreement over the proposed changes but reserves the right to progress if the majority of Participants are in agreement that it should go ahead, and reasonable attempts have been made to address any concerns of Participants rejecting the change.

Further details can be found on the Corda Network website [here](/policy/network-params-update) and within the Corda documentation [here](https://docs.corda.net/network-map.html#network-parameters).

Where the update may require significant Participant action, for example where the minimum platform version is increased and certain Participants need to upgrade to meet the new minimum, a minimum of three (3) months notice will be given. Full instructions will be communicated to node operators via the Network Operator’s service dashboard.

### 4.6. Scheduled Downtime

In the event that any platform maintenance or upgrades require a period of service impacting scheduled downtime, Participants will be notified by the Operator a **minimum of one (1) calendar month in advance** of the planned change window.

### 4.7. Unscheduled Downtime

All reasonable attempts will be made to avoid such unscheduled downtime, however on occasion emergency system maintenance may be required. For example, this could be to mitigate real or perceived security threats requiring immediate action, or in order to prevent more severe disruption to services as the result of a service incident. Emergency maintenance will be communicated as soon as practicably possible via the Network Operator’s service dashboard.

Any unavailability of services during normal business hours will be treated as an incident and managed according to the service levels defined in the Corda Network Support Handbook.

### 4.8. Change Freezes

To ensure the continued stability and performance of the Corda Network during periods where there are a number of public holidays worldwide, an annual change freeze will be implemented on the Corda Network. This change freeze will be in effect for **no more than one (1) month**, starting in December and ending in January the following year. Best endeavours will be made by the Network Operator to minimise the length of any change freezes, and these events will be announced via the Network Operator’s service dashboard.

Change freezes do not apply to an incident of [unscheduled downtime](#47-unscheduled-downtime) or [emergency maintenance](#43-emergency-maintenance).

## 5. Business Continuity

The Corda Network has a disaster recovery policy which is reviewed and tested semi-annually. This is in addition to a comprehensive security policy incorporating specific security incident management procedures to ensure business continuity in the event of an unexpected incident or system failure.

### 5.1. Backups

Regular backups are taken at a one (1) hour interval for the following Corda Network services:

- Identity Operator
- Network Map

Daily database backups are taken at a regular twenty-four (24) hour interval for the following Corda Network services:

- Notary

### 5.2. Data Retention

The data retention policy for the Corda Network is as follows:

- Business data created in the Corda Network environment as a result of customer activities under this agreement will be held by customer nodes and the Corda Network databases supporting the Identity Operator, Network Map and Notary services.
- At the end of the term of Corda Network membership for a Participant, the Foundation shall remove such data held in its own databases, unless customer requires otherwise at least thirty (30) days in advance of the end of the membership period. Any extended period of retention of data shall be at Foundation’s sole discretion and subject to a separate commercial agreement clarifying applicable storage costs and resulting fees payable by customer.

### 5.3. Recovery Time Objective

The recovery time objective is defined as the point at which the affected network service is either:

- Fully operational and able to interact with the rest of the Corda Network as it did before the incident or;
- A temporary workaround has been applied to restore the affected service, although further changes may be required to implement a permanent resolution.

The recovery time objective excludes any time required for Participants to complete required actions as a part of any incident resolution steps i.e. if a Network Parameter Update is required as a part of service recovery, and Participants are required to accept these updates on their nodes to restore connectivity to the Corda Network. During any such incident, regular updates will be posted by the Network Operator to its service dashboard.

In the event of a failure of the following Corda Network services, the recovery time objective will be four (4) hours (within normal business hours) from the point of detection:

- Identity Operator
- Network Map

### 5.4. Recovery Point Objective

In the event of a failure of the following Corda Network services, the recovery point objective will be one (1) hour from the point of failure:

- Identity Operator
- Network Map

In the event of a failure of the following Corda Network services, the recovery point objective will be twenty-four (24) hours from the point of failure:

- Notary

## 6. Reporting and Service Credits

### 6.1. Reporting

Performance against SLAs defined in this document will be reported on the Corda Network Foundation website **within five (5) business working days** of the end of each calendar month. Reporting will not be Participant specific and will not include any identifiable customer details.

### 6.2. Service Credits

In the event of SLA breaches impacting individual customers they will be entitled to repatriation of fees for the specific service affected.

A breach is defined as an instance where an individual service target is not met within the measurement intervals specified within this document. Multiple breaches cannot be claimed against a single service target within the same measurement interval.

| Number of breaches                 | Service Credit                    |
| ---------------------------------- | --------------------------------- |
| >9 and <20 within a calendar year  | 25% of fees for affected service  |
| >19 and <40 within a calendar year | 50% of fees for affected service  |
| >39 within a calendar year         | 100% of fees for affected service |

Any Participant requesting service credits should report details of each breach with reasonable evidence in writing. Requests can be submitted via email to <info@corda.network>.
