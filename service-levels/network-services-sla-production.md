# Corda Network Maintenance and Service Level Handbook

This document is correct as of 17th December 2020.

Please note that the terms of this Maintenance and SLA Handbook are subject to change. 
Customers will be notified of any material changes via the contact contained in the Certificate Signing Request for each node unless alternative contact details are advised.


## Contents

- [1. Definitions](#1-definitions)
- [2. Introduction](#2-introduction)
  - [2.1. Scope](#21-scope)
  - [2.2. Assumptions](#22-assumptions)
- [3. Service Levels](#3-service-levels)
  - [3.1. Availability](#31-availability)
    - [3.1.1. Identity Manager](#311-identity-manager)
    - [3.1.2. Network Map](#312-network-map)
    - [3.1.3. Notary](#313-notary)
  - [3.2. Performance](#32-performance)
    - [3.2.1. Identity Manager](#321-identity-manager)
    - [3.2.2. Network Map Service](#322-network-map-service)
    - [3.2.3. Notary](#323-notary)
  - [3.3. Exclusions](#33-exclusions)
- [4. Change Management](#4-change-management)
  - [4.1. Ongoing Maintenance](#41-ongoing-maintenance)
  - [4.2. Emergency Maintenance](#42-emergency-maintenance)
  - [4.3. Network Parameter Updates](#43-network-parameter-updates)
    - [4.3.1. Updating Minimum Platform Version](#431-updating-minimum-platform-version)
    - [4.3.2. Customer Initiated Network Parameter Change](#432-customer-initiated-network-parameter-change)
  - [4.4. Scheduled Downtime](#44-scheduled-downtime)
  - [4.5. Unscheduled Downtime](#45-unscheduled-downtime)
- [5. Business Continuity](#5-business-continuity)
  - [5.1. Backups](#51-backups)
  - [5.2. Data Retention](#52-data-retention)
  - [5.3. Recovery Time Objective](#53-recovery-time-objective)
  - [5.4. Recovery Point Objective](#54-recovery-point-objective)
- [6. Service Credits](#6-service-credits)
  - [6.1. Production Services](#61-production-services)
  - [6.2. Pre-Production Services](#62-pre-production-services)
- [7. Change Communication](#7-change-communication)
  - [7.1. Network Operator Initiated Change Communication Table](#71-network-operator-initiated-change-communication-table)
  - [7.2. Customer Initiated Change Communication Table](#72-customer-initiated-change-communication-table)

## 1. Definitions

| Term | Description |
| --- | --- |
| Business Network Operator | A Business Network Operator is a company responsible for operating a shared CorDapp for companies that wish to transact together, which may be on Corda Network. |
| Business Days | Business Days are from Monday to Friday, excluding public holidays in the United Kingdom, United States and Singapore. |
| Business Hours | Business Hours are from Monday 00:30 UTC+0 to Friday 21:30 UTC+0, excluding public holidays in the territories of the United Kingdom, United States and Singapore. “UK Business Hours” are on 08:30 UTC+0 to 17:30 UTC+0. |
| Corda Network Foundation | A not-for-profit legal entity known as a Stichting residing in the Netherlands. The Foundation governs Corda Network’s public key infrastructure, sets policies and standards related to it, and enables Network participants to be involved with, and also understand, how decisions on these areas are made. |
| Corda Network Rulebook | The rules, standards and policies governing activity within the Corda Network that are mandatory for all Corda Network participants, as adopted by Certificate Authority from time to time and provided to Participants. These rules include Allowable Identity names, Admissions Criteria and Revocation Criteria. Some of these rule derive from Corda Network Foundation. |
| CorDapp | Software applications built on the Corda platform that may be used on the Corda Network. |
| Customer | A Customer is a legal entity who has signed a Terms of Use with Corda Network Foundation, for access to network and notary services. |
| Network Operator | The network operator appointed by the Corda Foundation who undertakes all day-to-day activities associated with delivering the network services outlined within Section 2 of this document. |
| Node Operator Email | When onboarding to Corda Network, Customers will be required to designate a node operator email address on the node configuration file (“node.conf”). Network Operator  will use the designated email address for change management communications. |
| Production Network | The Production Network is a network and notary service operated by the Corda Network Foundation for Participants to perform live business transactions with other legal entities. It uses the Trust Root / PKI owned by the Corda Network Foundation. |
| Pre-Production Network| The Pre-Production Network is provided by the Corda Network Foundation for owners of tested CorDapps with a firm plan to launch them on the Production network. This environment is designed to enable testing of CorDapps in the network configuration they will experience on the Production environment, utilising relevant network services. |
| Service Dashboard| All Corda Network infrastructure-related changes that impact Customers will be communicated via a Service Dashboard, (currently [StatusPage](https://corda-network.statuspage.io/), link may change from time to time), access to which is provided to Customers during their onboarding process. |
| Support Portal| The primary method for Customers to request support. Customers will be provided with access to the Support Portal during their onboarding process. Current [link](https://r3-cev.atlassian.net/servicedesk/customer/portal/7); may change from time to time. |



## 2. Introduction

This Maintenance and Service Level Handbook defines service levels offered by the Foundation to Customers for Corda Network Network Services on both the Pre-Production Network and the Production Network. Corda Network Network Services covered are: Identity Manager, Network Map and a shared Notary. Once any customer signs the Terms of Use with the Foundation (the “Agreement”) for Corda Network, they accept the service levels contained within this handbook.

As such, this handbook defines:
-	Network services included on both the Pre-Production and the Production Corda Network.
-	SLAs for all network services
-	Actions taken by Corda Network to remediate potential / actual non-performance of services. 


Corda Network operates under a single set of rules, standards and best practices related to PKI as set by the Corda Network Foundation’s Board of Directors. Further details are available on the Corda Network website.


### 2.1. Scope

This Maintenance and Service Level Handbook applies to the Pre-Production Network and Production Network, and its constituent Corda Network Services as described in this handbook, and not to any other environments operated by Network Operator.

### 2.2. Assumptions

This Maintenance and Service Level Handbook is available to all customers using the Pre-Production Network and Production Network. Customers may operate more than one CorDapp within both the Pre-Production and Production Network.

A note on the Pre-Production Network:

-	The Pre-Production Network is not intended for customers’ full test cycles, as it is expected that the majority of CorDapp testing will occur in simpler network configurations run by the CorDapp provider, or operating within Corda Testnet, but is available for testing of functionally complete and tested CorDapps in realistic network settings.
-	Realistic test data is expected to be used representing real world entities and business activities, however the Pre-Production Network is not designed for processing real, legally binding business transactions. It will be the responsibility of customers to ensure test data is compliant with relevant data protection legislation and that the terms and conditions under which Pre-Production Network processes such data is suitable for their needs.
-	Network Operator reserves the right to delete test data from the Pre-Production Network on the completion of testing. 


## 3. Service Levels

The service levels contained within this section will apply during the term of the Ageement – as outlined in the Terms of Use it has signed with the Foundation. There are two sections: 3.1 Availability; and 3.2 Performance.


### 3.1. Availability

Definitions of availability for each service are included below.

#### 3.1.1. Identity Manager

The Identity Manager service is considered available if it can successfully receive requests for new certificates submitted for the Corda Network. This is measured by monitoring the service endpoint to ensure a valid status code is returned and checking that the underlying worker process is running.

**Production Network:** The Identity Manager service will operate with >99% availability during business hours during each calendar month.

**Pre-Production Network:** The Identity Manager service will operate with at least 99% availability during UK business hours during each calendar month.


#### 3.1.2. Network Map

The Network Map service is considered available if it is able to provide a network map upon request. This is measured by monitoring the service endpoint to return a valid status code, and checking that the underlying worker process is running.

**Production Corda Network:** The Network Map service will operate with >99% availability during business hours during each calendar month.

**Pre-Production Corda Network:** The Network Map service will operate with at least 99% availability during UK business hours during each calendar month.



#### 3.1.3. Notary

The Notary service is considered available if it can successfully receive, process and notarise transactions. This is measured by monitoring test transactions to ensure they are being received and processed as expected by the notary.

**Production Network:** The Notary service will operate with >99% availability on a 24/7 basis during each calendar month.

**Pre-Production Network:** The Notary service will operate with at least 99% availability during UK business hours during each calendar month.


### 3.2. Performance

#### 3.2.1. Identity Manager

The completion of a Certificate Signing Request (CSR) is measured from the time of receipt of a correctly formatted signing request by the Identity Manager to the time at which a response is submitted to the requesting node. The Identity Manager process can handle multiple certificate signing requests in parallel.

95% of valid CSRs will be completed within 2 business days each calendar month, excluding wait time for responses to confirmation or clarification requests from Customer. This applies both for the Production and the Pre-Production Corda Network. 

The Identity Manager may reject the CSR if the data is not constructed according to the standards set out in Corda Network Rulebook. Amended CSRs will be subject to the same service levels as new CSRs. 

Requests for re-certification, either to generate new keys, or to amend information on an existing and valid certificate, will start a new Corda Network Node and request a new certificate in exactly the same way as the original certificate and this will be subject to the same service levels. The X.500 Name of the new identity must be unique (not the same as the previous identity). Details such as the IP address of the node can be changed without re-certification by sending a new configuration file directly to the Network Map server.

#### 3.2.2. Network Map Service

The network map  service regularly signs the network map to reflect the latest updates on the Production and the Pre-Production Corda Network; for example, the registration of a new participant node on a zone, or a node changing its IP address. As such, Network Map Service performance is measured by how frequently network maps are signed successfully.

At least 95% of Network Map signing events on both the Production and the Pre-Production Corda Network will be completed successfully each calendar month.

#### 3.2.3. Notary

The completion time for transaction notarisation requests is measured from the time the inbound request is received on the notary to the point at which the outbound reply leaves the notary. This metric assumes that correctly formatted and structured notarisation requests are received only.

Notarisation requests are treated individually, in sequence of receipt, by the notary working from an inbound queue.

**Production Network:** The average time taken to process notarisation requests as measured over a five (5)-minute interval will be <240 seconds for at least 99% of each calendar month.
**Pre-Production Network:** The average time taken to process notarisation requests as measured over a five (5)-minute  interval will be <240 seconds for at least 95% of each calendar month.


*\*Each five-minute interval for measuring notarisation requests is approximate. Each interval is distinct, with a new five-minute measurement interval beginning once the previous one ends. Measurements are not taken as a five-minute rolling average. This means there are approximately 12 measured intervals per hour.*

### 3.3. Exclusions

The following exclusions for availability and performance service levels include but are not limited to:

- Network connectivity problems or hardware/software failure outside of the Foundation’s control affecting the connectivity of Customer nodes or any other Customer hardware/software to the Network services i.e. Customer node, network or system failures.
- Planned system downtime required for essential maintenance of Corda Network service components.
-	Issues or faults arising as a result of errors/bugs in Customer developed software or services.
-	Security incidents outside of the Foundation's control, such as a result of Customer actions, zero-day software or hardware vulnerabilities or service downtime / degradation as a result of security testing.
-	Any service unavailability or degradation as a result of the Foundation suspending Customer’s use of the service in accordance with the Agreement.  
-	Failed transactions as a result of Customer misconfigurations, such as incorrectly specified identities, addresses and hostnames for either Customer nodes or the nodes of transacting counter-parties.


## 4. Change Management

Any necessary maintenance to the infrastructure of both the Pre-Production and Production Network is communicated via Service Dashboard, [StatusPage](https://corda-network.statuspage.io/), which will automatically send notifications for the scheduling and progress of each change to Customer via the node operator email address unless alternative contact details are provided.

In addition, Network Operator also oversees network parameter updates for both the Pre-Production and the Production Network.  Where it is necessary to update underlying infrastructure, which in turn would require action from Customer, Network Operator will provide advance notice via the same service dashboard as early as possible. Minimum notice periods for network parameter updates on Corda Network are summarised in the ['Change Communication Table'](#7-change-communication-table). Any changes that impact system downtime will be subject to the process outlined in the [‘Scheduled Downtime’](#44-scheduled-downtime) section within this handbook.

### 4.1. Ongoing Maintenance

Regular system maintenance is required to ensure the ongoing performance, stability and security of Corda Network. Small, low-risk platform changes to network services that are non-service impacting are deployed as often as required. These changes do not require a maintenance window and will not be communicated via the Network Operator’s Service Dashboard.


### 4.2. Emergency Maintenance

On occasion, emergency maintenance may be required in response to a real or perceived vulnerability, security threat or unexpected service disruption. Emergency maintenance will be communicated as soon as practicably possible via the Network Operator’s Service Dashboard.


### 4.3. Network Parameter Updates

The Corda Networks use a common set of network-wide parameters that each Corda Network Node adheres to. On occasion these network parameters need updating to ensure the continued smooth operation of the Corda Network. 


Network parameter updates will be required whenever the following scenarios occur:

- A new notary is added to the environment, changing the allowed notaries.
- The maxTransactionSize and / or maxMessageSize are increased.
- The network epoch value is increased.
- The eventHorizonis changed (the amount of time a node can be un-contactable before being retired from the network).
- Where whitelistedContractImplementations are changed
- The minimumPlatformVersion is upgraded (subject to 3-month notice, as detailed below).

In the event that a Network Parameter Update is necessary, a restart of the service will be required during a specified time window, which will be defined on the Network Operator's service dashboard, to ensure the continued operation of the service using the new network parameters.

Network Parameter Updates are scheduled for the Pre-Production Network and Production Network once per quarter. These update windows are scheduled a quarter in advance, and their contents will be advertised at least **ten (10) business days in advance** via the Network Operator's Service Dashboard.

The update process incorporates a node polling activity that ensures all node operators see the requested changes in advance and can choose to accept/not accept. The Foundation will consult with the customer that raised the request should there be disagreement over the proposed changes but reserves the right to progress if the majority of Customers are in agreement that it should go ahead, and reasonable attempts have been made to address any concerns of Customers rejecting the change.

### 4.3.1. Updating Minimum Platform Version

Where the recommended update requires significant customer action, for example where the minimum platform version is increased and certain customers need to upgrade to meet the new minimum:
- Network Operator will communicate intention a minimum of **three (3) calendar months in advance** of the event via the Network Operator's Service Dashboard and will conduct its own testing in a separate environment before making the update. Customers will be invited to support such testing by operating test nodes in such an environment. It may not be possible to test with every CorDapp, nor should it be necessary.
- In the rare event of issues arising in connection with customer’s upgrade of its node, any issue will be treated as an incident and managed according to the support processes and incident severity levels defined in a separate handbook which you should have received during onboarding, the Corda Network Support Handbook. Please contact info@corda.network if you do not have access to this.

### 4.3.2. Customer-Initiated Network Parameter Change

Customers may request Network Parameter Updates, provided such request should be made no less than **twenty (20) business days in advance** of the scheduled quarterly window via the Support Portal. 


### 4.4. Scheduled Downtime

Any scheduled maintenance of the Corda Network Services shall be notified by the Network Operator a minimum of **one (1) calendar month in advance** of the planned maintenance via Service Dashboard. Any scheduled maintenance shall be excluded from the calculation of service levels pursuant to this handbook.

### 4.5. Unscheduled Downtime

All reasonable attempts will be made to avoid such unscheduled downtime, however on occasion emergency system maintenance may be required. For example, this could be to mitigate real or perceived security threats requiring immediate action, or in order to prevent more severe disruption to services as the result of a service incident. Emergency maintenance will be communicated as soon as practicably possible via the Network Operator’s Service Dashboard.

Any unavailability of services during normal business hours will be treated as an incident and managed according to the support processes and incident severity levels defined in the Corda Network Support Handbook.


## 5. Business Continuity

The Production Corda Network and Pre-Production Corda Network has a disaster recovery policy which is reviewed and tested regularly. This is in addition to a comprehensive security policy incorporating specific security incident management procedures to ensure business continuity in the event of an unexpected incident or system failure.

The Network Operator will not be responsible for matching business continuity responsibilities that a customer has committed to as part of their own business requirement. If business continuity targets outlined in this section are not sufficient, customers should contact the Foundation to discuss any special arrangements that could be made. 


### 5.1. Backups

Regular backups are taken in line with our Disaster Recovery targets for the Corda Network Services.


### 5.2. Data Retention

The data retention policy for the Corda Production Network is as follows:

- Customer Data in the Production Network will be held by Customer Corda Network Nodes and the Production Network databases supporting the Corda Network Services.
- At the end of the term of the Agreement, the Foundation shall remove such data held in its own databases; provided if Customer would like the Foundation to retain such data, Customer shall provide the Foundation notice at least thirty (30) days prior to expiration of the Term, subject to additional fees and a separate agreement to be entered into at the time. Any extended period of retention of data shall be at the Foundation’s sole discretion.

### 5.3. Recovery Time Objective

The Recovery Time Objective applies when a disaster is declared by the Network Operator's Operations Team and these services are not available to be operated.

The Recovery Time Objective is defined as the point at which the affected network service is either:

- Fully operational and able to interact with the rest of the Production Network and Pre-Production Network as it did before the incident or;
- A temporary workaround has been applied to restore the affected service, although further changes may be required to implement a permanent resolution.

Recovery Time Objective is measured from the time the Network Operator confirms that service recovery is required, until the service is restored. 
In the event of a failure of the following network services, the recovery time objective from the point of detection (within normal business hours) will be four (4) hours in the Production Network and eight (8) hours in the Pre-Production Network:
-	Identity Manager
-	Network Map

The Identity Manager service’s primary function is to issue and revoke node certificates, and does not usually interact with nodes that have already been accepted onto the network. In addition, each live node on the network retains a cached version of the network map and can continue to interact with other active nodes during any service recovery operations. 

The recovery time objective excludes any time required for customers to complete required actions as a part of any incident resolution steps i.e. if a Network Parameter Update is required as a part of service recovery, and customers are required to accept these updates on their nodes to restore connectivity to the Corda Network. During any such incident, regular updates will be posted by the Network Operator to its Service Dashboard.

### 5.4. Recovery Point Objective

Recovery Point Objective applies only once a disaster is declared by the Network Operator's Operations Team.

Recovery Point Objective is defined as the maximum point-in-time that services will be recovered to, measured from the time that the failure occurred. Recovery Point Objective is measured as the time delta between the point-in-time that data is recovered to and the time the Network Operator identified a service failure as occurring.

In the event of a failure of the following network services on either the Production Network or Pre-Production Network, the Recovery Point Objective will be one (1) hour from the point of failure:

- Identity Manager
- Network Map

In the event of a failure of the following Corda Network services on either the Production Network or Pre-Production Network, the recovery point objective will be twenty-four (24) hours from the point of failure:

- Notary

## 6. Service Credits

### 6.1. Production Services

In the event of SLA breaches impacting individual Participants they will be entitled to repatriation of fees for the specific service affected.

A breach is defined as an instance where an individual service target is not met within the measurement intervals specified within this document. Multiple breaches cannot be claimed against a single service target within the same measurement interval.

| Number of breaches                 | Service Credit                    |
| ---------------------------------- | --------------------------------- |
| >9 and <20 within a calendar year  | 25% of fees for affected service  |
| >19 and <40 within a calendar year | 50% of fees for affected service  |
| >39 within a calendar year         | 100% of fees for affected service |


**How are service credits recorded and distributed?**

The Foundation aims to provide monthly SLA reporting to customers of Corda Network via email to registered node operator email address unless specified otherwise. Reporting will not be customer specific and will not include any identifiable customer details.

To request a service credit, customers must raise a service credit request via email to info@corda.network providing reasonable evidence of a breach in writing. Requests must be submitted within two (2) calendar months after a suspected breach to be eligible for a service credit. 

### 6.2. Pre-Production Services

Service credits will not apply for Pre-Production services.
The Foundation will not provide monthly SLA reporting for the Pre-Production Network.

## 7. Change Communication 


### 7.1. Network Operator Initiated Change Communication Table



| CLAUSE                          | DESCRIPTION                                                                                                                       |    NOTICE & CHANNEL                                                                                                                   |
|---------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| Emergency Maintenance (4.2)     | Response to a real or perceived vulnerability, security threat or unexpected service disruption                                   | **ASAP** via Service Dashboard                                                                                                            |
| Network Parameter Updates (4.3) | 1. Non-service impacting changes <br>2. Significant customer action required                                                          | 1. Min **10 business days**; quarterly schedule via Service Dashboard   <br>2. Min **3 calendar months** via Service Dashboard |
| Scheduled Downtime (4.4)        | Upgrades require a period of service impacting scheduled downtime                                                                 | Min **1 calendar month** via Service Dashboard                                                                                            |
| Unscheduled Downtime (4.5)      | To mitigate real or perceived security threats; to prevent more severe disruption to services as the result of a service incident | **ASAP** via Service Dashboard                                                                                                            |


 ### 7.2. Customer Initiated Change Communication Table  
 
                                                                                                    
| CLAUSE                          | DESCRIPTION                                                                                                                       |    NOTICE & CHANNEL                                                                                                                   |
|---------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| Network Parameter Updates (4.3.)  | Customers can request network parameter updates whenever the scenarios described in 4.3. occur                                                                   | Min **20 business days** via Support Portal                                                                             |
| Data Retention (5.2)              | Requests for the Foundation to retain any customer data held in its databases after the end of the Agreement period.              | **30 days** notice from Customer                                                                                                                       |



