# Network Parameters Update Policy

This document outlines requirements for the handling of updates to network parameters.

## Introduction

Like all blockchain systems, as a precondition of exchanging information, nodes must agree on some technical “ground rules”, which for Corda Network we call “network parameters”. In other words, these are the minimum set of shared run-time settings which enable all Corda Network nodes to interoperate.

Network parameters specify things like Minimum  Platform Version and whitelisted notaries  which, although not expected to change frequently,  nevertheless will need to be updated over time. [Our docs site](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.corda.net%2Fnetwork-map.html%23network-parameters&data=02%7C01%7C%7C7b5adf5bd9674a65dc7708d697159e1a%7Ca4be1f2e2d10419587cd736aca9b672c%7C0%7C0%7C636862516429056071&sdata=nQfxg5VijKYmEXjmPdSoDH5HjGLtXTEDjIX0%2BAMFfJ8%3D&reserved=0) has more detail.

### Guiding Principles

This policy applies the following principles:

1.  **Control**: Changes to Network Parameters must take place via a controlled process which minimises operational 
risks to Participants during the update.
2.  **Backward compatibility**: Wherever possible, changes to Network Parameters should avoid breaking compatibility 
with applications based on previously-supported implementations of Corda.
3.  **Collective interest**: Network Parameters shall be adopted and updated based on what the Foundation judges to be 
the collective interest of all Participants to the network.


### Roles & Responsibilities

As outlined in the Foundation’s [by-laws](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fcorda.network%2Fgovernance%2Fbylaws.html&data=02%7C01%7C%7C7b5adf5bd9674a65dc7708d697159e1a%7Ca4be1f2e2d10419587cd736aca9b672c%7C0%7C0%7C636862516429066085&sdata=IpBxiEXL6zTrFt%2BMY8Q7gYldsYpViLi2gQOLnOWfzRI%3D&reserved=0), changes to technical parameters and  notary criteria are managed through a governance process: “Advisory Governance  Events” (clauses 8.1.1.c and 10.1). These are changes which can be implemented  by the Operator without Foundation approval, but the Foundation can ask to  provide an advisory vote. It’s important that the Operator can progress parameter update to a  regular schedule without encumbering the governance process of the Foundation with routine changes to keep in line  with the Corda Protocol.

### Changes to Network Parameters: Process

The Foundation shall apply a structured process to the creation of new Network Parameters, where:

1. Changes may be proposed by any Participant of the Network, or by the Network Operator.
2. All proposals for changes shall be reviewed by the Network Operator and the Foundation.
3. The Network Operator shall undertake testing to demonstrate in advance that proposed changes shall not have unforeseen negative effects on the operation of the Network.
4. The Network Operator will determine the appropriate implementation date, following the schedule below
5. The Network Operator will have the right to refuse or delay parameter updates at its discretion, but at all times acting in accordance with its brief and the terms and objectives of the Corda Network Charter
6. The Network Operator shall provide forward notice of planned parameters updates.


### Addition of new parameters and updates to existing  parameters

The schedueled Network Parameter Update window can be found on our [Network Parameters Update Schedule](https://corda.network/participation/networkparamsschedule.html) page.

If participants wish to change any network parameters, including a new public notary, they must give notice to the Operator (cordanetwork.ops@r3.com) *20 business days* in advance of the scheduled Network Parameter Update window, or else they will have to wait for the next window.

The planned annual dates will also be communicated by the Network Operator to all participants in advance on [https://corda.network/](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fcorda.network%2F&data=02%7C01%7C%7C7b5adf5bd9674a65dc7708d697159e1a%7Ca4be1f2e2d10419587cd736aca9b672c%7C0%7C0%7C636862516429066085&sdata=K6T%2Bxp7TvdYAwXtr5QQvIAnv2wUalGOkjzRSIvvtQ4A%3D&reserved=0), and if anything needs to change, reasonable advance notice to all participants will be uploaded onto this website.

If participants wish to update any network parameter, they must give notice to the Operator 20 business days in advance of the scheduled Network Parameter window.

This should be sent to: cordanetwork.ops@r3.com

### Please note:

Due to the importance of the new features in Corda 4 (in particular signature constraints), the Foundation will be aiming to complete the update to Minimum Platform Version v4 within 6 months of the release of the Corda Enterprise version.

Generally, the Minimum Platform Version will be updated within 15 months of the release of each major new release of the open source version of Corda.

### Re-scheduling:

The Network Operator may, at its discretion, alter the timing at which a proposed update to Network Parameters is scheduled to take place, subject to the following conditions:

*The revised timing must be disclosed to all Participants not less than 30 days in advance of the new implementation date*

### Cancellation:

The Network Operator may, subject to approval by the Foundation, cancel a planned update to the Network Parameter update Window. The following conditions apply:

- The cancellation must be disclosed to all Participants.
- The cancellation must be disclosed at the earliest possible opportunity.

The Foundation shall only approve a cancellation if it believes that doing so serves the collective interest of all Participants.

### Emergency reversion:

In the event of major issues resulting from enactment of a Network Parameters update, the Network Operator may, at its discretion, apply a further update with the effect of reverting the Network Parameters to their original state prior to the change. In this case, the following conditions apply:

- The balance of interest for all Participants of the Network must be clearly in favour of reversion.
- All parameters must be reverted to their collective state prior to the change.
- No new parameters may be added during the course of a reversion.
- No parameters may be otherwise changed except to their reverted values.
- Appropriate controls over the reversion process must be in place to minimise subsequent risk to the Network.
- The reversion must be completed within 48 hours of the Network Parameters update (otherwise, normal provisions for changes to Network Parameters apply).
- The Network Operator shall disclose the action taken and rationale to all Participants at the earliest opportunity.

### Removal of Network Parameters:

The Foundation shall apply a structured process to the removal of new Network Parameters, wherein:

- Removal of a parameter may be proposed by any Participant of the Foundation, or by the Network Operator.
- All proposals for parameter removals shall be reviewed by the Foundation and put to a governance vote if necessary.
- Following approval, the appropriate timing to remove a parameter shall be determined by the Network Operator.

No Network Parameter shall be removed where it is required for operation of nodes employing the Corda Reference Implementation, over and above the version indicated in the minimumPlatformVersion Network Parameter.
