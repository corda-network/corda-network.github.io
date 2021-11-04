# Segregated Network Operations Guide

## Purpose

This guide serves as an introduction to segregated networks and may be updated by R3 from time to time. R3 (“Network Operator”) runs the infrastructure of Corda Network - both the Mainnet and segregated networks. For the purposes of this document, “Participant” is any legal entity that has a node on a segregated network. “Customer” is the legal entity which signs a legal agreement with R3 for, and helps operate, a segregated network.

All time definitions are made in accordance with UTC+0. “Normal Business Hours” refer to Monday 00:30 UTC+0 to Friday 21:30 UTC+0, excluding public holidays in the territories of the United Kingdom, United States and Singapore. “Business Days” refer to Monday to Friday, excluding weekends and public holidays in the of the United Kingdom, United States and Singapore.

## 1.	Introduction 
Segregated networks (SNs) are partitioned sub-networks off the Corda Network Mainnet, which enable dedicated notaries, membership privacy (i.e. only participants of the segregated network are visible to each other) and complete control over the network parameter upgrade schedule. While the segregated network uses the same Trust Root and the Identity Operator (joining and leaving process) is shared with the Corda Network Mainnet, in all other respects it is separate (i.e. has its own notary, network map, and network parameters).

### 1.1. Requesting a segregated network 
The prerequisite for a segregated network to be created is a signed Participant Terms of Use agreement between R3 and Customer. Once the legal contract is in place, the Customer can request their Pre-Production and Production environments to be built by filling in a [Segregated Network Requirements Form](https://github.com/corda-network/corda-network.github.io/blob/master/assets/R3_Segregated%20Network%20Requirements%20Form_2021.docx). The form captures necessary technical details for the environment to be created as each segregated network is custom-built according to the Customer’s specifications. 

Delivery dates for Pre-Production and Production segregated networks must be agreed with R3 Support team. While every effort is made to meet expectations regarding preferred timelines, building an environment may take up to 6 weeks to complete. 

### 1.2. Segregated network delivery 

The segregated network delivery process follows the steps outlined below.

**Step 1: Customer requests SN** 

Customer fills in the SN requirements form and submits it as a Task ticket in [Corda Network Support Portal](https://r3-cev.atlassian.net/servicedesk/customer/portal/7). 

**Step 2: Delivery of Network Map URL** 

Once the SN is built, Customer will be sent a file containing dedicated Network Map URL and other relevant details about the environment. Details of delivery will be agreed with R3 Support team over the ticket raised in Step 1.

**Step 3: Customer registers Notary service identity**

Information sent by R3 Support (including Customer’s unique Network Map URL) allows Customer to configure their notary service identity and notary worker nodes. Consult [this](https://docs.r3.com/en/platform/corda/4.8/enterprise/corda-network/setup-segregated-notary.html) page for a technical overview and [this](https://corda.network/joining-corda-network/onboarding-workflow/) page for step-by step business process.

Please note that while the Doorman details will be the same as in the [onboarding workflow](https://corda.network/joining-corda-network/onboarding-workflow/), the Network Map URL is unique to each SN environment.

To ensure that the CSR requests for notary service identity and notary worker nodes will not have any errors, it is advised that Customer submits proposed X509 name for pre-approval over the same ticket raised in Step 1. Instructions on how to fill in the fields of an X509 certificate can be found in the Corda Network [Rulebook](https://corda.network/corda-network-rulebook/allowable-identity-names-on-corda-network/).

At the end of the node registration process a nodeInfo-xxx file should automatically be generated. This file contains details needed for R3 to update the network parameters with.

**Step 4: Customer submits nodeInfo-xxx file to Support**

NodeInfo-xxx file containing notary service identity should be submitted within a week after receiving the Network Map URL in the Support ticket raised in Step 1. 

**Step 5: R3 updates network parameters**

R3 needs to update network parameters with Customer’s notary details as it is running the Network Map service on behalf of the Customer. After the network parameters have been updated, Customer can [start the notary worker nodes](https://docs.r3.com/en/platform/corda/4.8/enterprise/node/deploy/starting-components.html#starting-a-corda-node). This will be coordinated via a support ticket between Customer and R3 Support.

## 2. Network parameters

Network parameters are a set of values that every node participating in the segregated network needs to use so as to interoperate with other nodes. 
When a segregated network is first set up, the Network Operator signs a data structure that contains the values and they are distributed along with the Network Map as network parameters. Segregated network nodes using this Network Map download the signed network parameters at first start-up, cache it in a network-parameters file and apply them on the node. A full list of network parameters can be found in the following table.

| **Network parameter**              	| **Description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              	| **Default values in the Customer’s segregated network (unless specified otherwise)** 	|
|------------------------------------	|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|--------------------------------------------------------------------------------------	|
| epoch                              	| Version number of the network parameters. Starting from 1, this will always increment whenever any of the parameters change.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 	| "epoch":1                                                                            	|
| eventHorizon                       	| Time after which nodes are considered to be unresponsive and removed from network map. Nodes republish their NodeInfo on a regular interval, which the network map treats as an indication from the node that it is online.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  	| "eventHorizon":"720:00:00"                                                           	|
| maxMessageSize                     	| Maximum allowed size (in bytes) of an individual message sent between nodes. Note that attachments are a special case and may be fragmented for streaming transfer, however, an individual transaction or flow message may not be larger than this value.                                                                                                                                                                                                                                                                                                                                                                                                                                                                    	| "maxMessageSize":20971520                                                            	|
| maxTransactionSize                 	| Maximum allowed size (in bytes) of a transaction (includes attachments).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     	| "maxTransactionSize":10485760                                                        	|
| minimumPlatformVersion             	| The minimum platform version of Corda that nodes must be running. Any node running a version of Corda below this version will not start.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     	| "minimumPlatformVersion":{}                                                          	|
| modifiedTime                       	| The time when the network parameters were last modified by the Network Operator.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             	| "modifiedTime":{}                                                                    	|
| notaries                           	| List of identity and validation type (either validating or non-validating) of the notaries which are permitted in the compatibility zone.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    	| "Notaries":{}                                                                        	|
| packageOwnership                   	| List of the network-wide java packages that were successfully claimed by their owners. Any CorDapp JAR that offers contracts and states in any of these packages must be signed by the owner so that when a node encounters an owned contract it can uniquely identify it and knows that all other nodes can do the same. Encountering an owned contract in a JAR that is not signed by the rightful owner is most likely a sign of malicious behavior, and should be reported. The transaction verification logic will throw an exception when this happens. Read more about Package namespace ownership [here](https://docs.r3.com/en/platform/corda/4.8/enterprise/node/deploy/env-dev.html#package-namespace-ownership). 	| "packageOwnership":{}                                                                	|
| whitelistedContractImplementations 	| List of whitelisted versions of contract code. For each contract class there is a list of SHA-256 hashes of the approved CorDapp jar versions containing that contract. CorDapps using signature constraints instead of hash constraints will not need this parameter.                                                                                                                                                                                                                                                                                                                                                                                                                                                       	| "whitelistedContracts":{}                                                            	|
| parametersUpdate                   	| Details of an upcoming, or previous, update to the above parameters, further details are below.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              	| No value, since these have not changed yet                                           	|

### ParametersUpdate
parametersUpdate is a network parameter that contains information on the point after which new updates to parameters can be made, and a description of those changes. Below is an example and further description:

![image](https://user-images.githubusercontent.com/61778485/140306410-7daf2fc4-a52b-4952-8245-f98fa279f6a6.png)


| **parametersUpdate** 	| **Description**                                                                                                                                                                                 	|
|----------------------	|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|
| description          	| A summary of any updates to the network   parameters                                                                                                                                            	|
| updateDeadline       	| An ISO 8601 format DateTime before which the proposed updates will not be applied to the Network. This value is the first moment they could be applied, not when they actually will be applied. 	|
 

## 3. Changes in network parameters 

Setting initial network parameters is straightforward as there are as yet no network Participants onboarded. When a node first starts up it has no network parameters file and therefore implicitly accepts whatever the network is currently using. 

From time to time, the above listed network parameters would likely need to be updated to provide for the continued operation of the segregated network. Any changes to network parameters require the Network Operator to run an explicit update process called a Network Parameter Update. 

Customer is expected to plan its own Network Parameter Update schedule, and wherever possible, share with R3 Support team to facilitate forward planning. 

Network Parameter Updates will be required whenever the following scenarios occur:

- A new notary is added to the environment.
- Customer whitelists a new contract.
- The minimum platform version is upgraded.
- The maximum message and/or transaction sizes are increased.
- The network epoch value is increased.
- The event horizon is changed (the amount of time a node can be un-contactable before being retired from the network).

Change management is covered in greater detail in the Corda Network [Maintenance and Service Level Handbook](https://corda.network/trust-centre/sla-&-maintenance-handbook).

## 4. Tasks

### 4.1	Requesting network parameter change

To request a Network Parameters Update,  Customer should raise a ticket via the [Corda Network Support Portal](https://r3-cev.atlassian.net/servicedesk/customer/portal/7), outlining new network parameters, giving at least **3-weeks' notice i.e. 15 business days**. 

To streamline the process, this ticket should also include a selection of preferred dates for the Network Parameters Update. Corda Network Support team will then respond via Support Portal and confirm one of the suggested dates. 

The update process incorporates a node polling activity that provides that all node operators see the requested changes in advance and can choose to accept/not accept. 

Certain upgrade scenarios requested by the Customer may require Participant nodes to upgrade. The Customer and any segregated network Participants are encouraged to conduct their own testing in a separate environment before making the upgrade. 

In the rare event of issues arising, any issue will be treated as an incident and managed according to the service levels defined in Corda Network Support Service Handbook.  

### 4.2  Network Parameter Update process

Network Parameter Updates take place in two main phases:

- After Customer has proposed new parameters, the update is broadcast to Participants with an acceptance deadline.
- Once the update deadline has passed and Participants have accepted, Network Operator will run the network parameter update 

Network Parameter Update process follows steps outlined below.

**Step 1: Agree Changes**

Proposed changes are agreed upon between Network Operator and Customer. This means both parties have seen the same proposed new *network-parameters.conf*. 

**Step 2: Network Parameter Update**

Network Operator uploads the updated *network-parameters.conf* to the target Network Map server, stops the Network Map Service, and loads the *netmap.jar* with java using the *-set-network-parameters* flag.

After the update step is completed the java process will terminate. Network Operator restarts the Network Map service to continue to serve the old parameters and map until the Network Parameter Update. Meanwhile, the new network parameters are broadcast to Participants with an acceptance deadline.

**Step 3: Update Deadline**

Until this *DateTime* is passed the old network parameters are still in effect. This means that the contents of *network-parameters.conf* is not the same as the broadcast parameters.

Network Operator cannot run a Network Parameter Update until this point in time elapses.

**Step 4: Flag Day**

Once the *DateTime* set in the *updateDeadline* property of the *parametersUpdate* has been passed, the Network Operator can run a Network Parameter Update, also referred to as Flag Day. First the Network Map service will need to be stopped, then the *netmap.jar* is loaded with java using the *-flag-day* flag.

After the Flag Day step is completed the java process will terminate, and the Network Map service will need to be restarted to serve the new Network Parameters.

At this point nodes that have not accepted the updates will begin to drop from the segregated network.

Completing this step will change the status of a parameter update to *APPLIED*.

### 4.3 Network parameter changes: Process flow & customer requirements

Updates to some network parameters can be configured to be auto acceptable i.e. the new parameters will be accepted without user input. Auto acceptable parameters include *epoch*, *whitelistedContractImplementations*, m*odifiedTime* and *packageOwnership*.

If the auto-acceptance behaviour is turned off via the configuration or the network parameters change involves parameters that are not auto-acceptable then manual approval from each node operator is required. In this case the node administrator can review the change and decide if they are going to accept it. The approval should be done before the update deadline. 

To send back parameters approval to Network Operator, each node accepts the parameters by running the `run acceptNewNetworkParameters parametersHash: <HASH>` shell command.

Once all Participants have accepted and the update deadline has passed the Network Operator issues a flag day. When the Network Map is next built and signed the parameters will roll over to the proposed update. 

**Network parameter rollover**

When the network rolls over its parameters after a flag day, all nodes will automatically shut down, regardless of whether they have accepted new parameters or not.

Nodes that have accepted can be restarted and will automatically start using the new parameters. Nodes that have not will fail to start. They will have to purge their current network parameters to be able to re-join the network.

More information on Network Parameter Update process is available [online](https://docs.r3.com/en/platform/corda/4.8/open-source.html).

### 4.4 Requesting Certificate Revocation

To request any Participant certificate to be revoked Customer should raise a ticket via [Corda Network Support Portal](https://r3-cev.atlassian.net/servicedesk/customer/portal/7), providing the following information:

- A sound business reason to justify permanent removal of the X.509 certificate from the segregated network, such as a change of the company legal name, compromised private key, or the Participant decides to permanently withdraw from the Network.
- Attach email approval from at least two officers (in general, Director or above employee) of the legal owner (“O” field) of the node.
- Specify the X.509 name of the certificate to be revoked.

Certificate Revocation requests will be prioritised based on the business reason for such revocation.

There are also exceptional scenarios where R3 may initiate a Certificate Revocation, as set forth in the agreement entered into between R3 and Customer.

More information can be found [here](https://corda.network/joining-corda-network/offboarding-workflow)


## 5. Testing

### 5.1 Health Survey tool

The Corda Health Survey tool is a command line utility designed to help Corda Enterprise node operators with initial setup of a Node; it is not meant to be used as an ongoing monitoring tool. Customer should be using the same version of the Health Survey tool as the version of Corda Enterprise node that they are running.
In the context of a network parameter change, the purpose of running the Corda Health Survey tool is to confirm connectivity to the Identity Manager and Network Map, and to ping the Notary to confirm it is available.

Furthermore, the Health Survey tool can be used to collect information about a node, which can be used by R3 Support team as an aid to diagnose support issues. It works by scanning a provided node base directory and archiving some of the important files. It also conducts a deployment status check by connecting to the node and probing it and the firewall (if deployed externally) for information on configuration, service status, connection map and more.

Materials on how to set up and run the health survey tool can be found [here](https://docs.r3.com/en/platform/corda/4.8/enterprise/health-survey.html#health-survey-tool). Further information on node monitoring and logging is available [here](https://docs.r3.com/en/platform/corda/4.8/enterprise/node/operating/monitoring-and-logging/overview.html#node-monitoring).


For more information, please contact your R3 Account Manager.
