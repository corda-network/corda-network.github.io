|Corda Network Foundation|[Document history]({{ site.github.repository_url }}/blame/master/{{page.path}})|

Network Parameters Upgrade Policy
=================================

This document outlines requirements for the handling of updates to Network Parameters.

Introduction
============

Definitions
-----------

The following definitions apply in the context of this document:

*   **Network Parameter**: A parameter with a single value at any point in time, on which the entire Network is taken 
to be in agreement
*   **Participant**: A user of the Corda Network. 
*   **Corda Reference Implementation**: Official open source reference node implementation for the Corda protocol, 
uniquely recognised as such by the Foundation.

Motivation
----------

Network Parameters provide a means to optimise compatibility between nodes on the Network. For several operating 
parameters, the possibility of different Participant nodes assuming different values may give rise to technical or 
operational issues between nodes attempting to transact with each other, or make it impossible for them to do so. The 
Foundation considers it vital to avoid these scenarios in line with its aim of realising frictionless interaction 
between Participants via the Corda Network.

Equally, it is recognised that a highly opinionated Network is not automatically in the interests of Participants. This 
places emphasis on structured governance to ensure that both the scope of Network Parameters, and their values, are 
appropriately chosen to reflect the collective interest.

Principles
----------

This policy applies the following general principles:

1.  **Control**: Changes to Network Parameters must take place via a controlled process which minimises operational 
risks to Participants.
2.  **Backward compatibility**: Wherever permissible, changes to Network Parameters should avoid breaking compatibility 
with previously-supported implementations of Corda. 
3.  **Collective interest**: Network Parameters shall be adopted and updated based on what the Foundation judges to be 
the collective interest of all Participants to the network. 

Policy Detail
=============

Roles & Responsibilities
------------------------

The Foundation shall determine the scope of Network Parameters and the value to be adopted for each Network Parameter.

The Network Operator is accountable for the distribution of Network Parameters to all Participants and ensuring these 
consistently reflect values agreed by the Foundation.

Addition of new Network Parameters
----------------------------------

The Foundation shall apply a structured process to the creation of new Network Parameters, wherein:

*   New parameters may be proposed by any Participant of the Foundation, or by the Network Operator.
*   All proposals for new parameters shall be reviewed without prejudice.
*   Following approval, the appropriate timing to introduce new parameters shall be determined by the Network Operator.

### Reference implementation alignment

At a minimum, the Foundation shall ensure that Network Parameters include all parameters assumed by the Corda Reference 
Implementation.

### Majority interest

Network Parameters shall only be provided for purposes which may be reasoned to be of potential relevance to the 
majority of Network Participants, both in the near term and for the foreseeable future. They shall not be employed as a 
mechanism for distributing information which is specific to a given business network or other group of users.

### Descriptive

Network parameter names shall use the English language, and be clearly descriptive of their intended use.

Updates to existing Network Parameters
--------------------------------------

The Foundation shall apply a structured process to any changes in the value of Network Parameters, wherein:

*   Changes may be proposed by any Member of the Foundation, or by the Network Operator.
*   All proposals for changes shall be reviewed by the Foundation without prejudice.
*   The Network Operator shall undertake structured testing to demonstrate in advance that proposed change shall not 
have unforeseen negative effects on the operation of the Network.
*   Following approval, the appropriate timing of parameters updates shall be determined by the Network Operator.
*   The Network Operator shall provide advanced disclosure of planned parameters updates.
*   The Network Operator shall apply a controlled process to the distribution and enactment of Network Parameters 
updates.

### Advance disclosure

The Network Operator shall ensure any proposed changes to Network Parameters are disclosed to all Participants in 
advance of their coming into effect.

In general, this shall be no less than 30 days prior to the proposed changes coming into effect. Any planned changes 
which allow less than 30 days notice to Participants shall be subject to prior approval by the Foundation via an 
Emergency Governance Event.

### Re-scheduling

The Network Operator may, at its discretion, alter the timing at which a proposed update to Network Parameters is 
scheduled to take place, subject to the following conditions:

*   The revised timing must be disclosed to all Participants.
*   The revised timing must be no less than 30 days in advance of disclosing the re-scheduled timing to Participants.

### Cancellation

The Network Operator may, subject to approval by the Foundation, cancel a planned update to Network Parameters. The 
following conditions apply:

*   The cancellation must be disclosed to all Participants.
*   The cancellation must be disclosed at the earliest possible opportunity.

The Foundation shall only approve a cancellation if it believes that doing so serves the collective interest of all 
Participants, and seeks to avoid any unnecessary cancellations.

### Emergency reversion

In the event of major issues resulting from enactment of a Network Parameters update, the Network Operator may, at its 
discretion, apply a further update with the effect of reverting the Network Parameters to their original state prior to 
the change. In this case, the following conditions apply:

*   The balance of interest for all Participants of the Network must be clearly in favour of reversion.
*   All parameters must be reverted to their collective state prior to the change.
*   No new parameters may be added during the course of a reversion.
*   No parameters may be otherwise changed except to their reverted values.
*   Appropriate controls over the reversion process must be in place to minimise subsequent risk to the Network.
*   The reversion must be completed within 48 hours of the Network Parameters update (otherwise, normal provisions for 
changes to Network Parameters apply).
*   The Network Operator shall disclose the action taken and rationale to all Participants at the earliest opportunity.

Removal of Network Parameters
-----------------------------

The Foundation shall apply a structured process to the removal of new Network Parameters, wherein:

*   Removal of a parameter may be proposed by any Member of the Foundation, or by the Network Operator.
*   All proposals for parameter removals shall be reviewed without prejudice.
*   Following approval, the appropriate timing to remove a parameter shall be determined by the Network Operator.

No Network Parameter shall be removed where it is required for operation of nodes employing the Corda Reference 
Implementation, over and above the version indicated in the `minimumPlatformVersion` Network Parameter.