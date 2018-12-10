|Corda Network Foundation|[Document history]({{ site.github.repository_url }}/blame/master/{{page.path}})|

Introduction to Corda Network
=============================

Welcome to Corda Network's website.

![image](https://github.com/corda-network/corda-network.github.io/blob/master/Screen%20Shot%202018-12-04%20at%2012.15.27.png)

Corda Network consists of Corda nodes operated by network participants, in which business transactions are created and 
validated via Corda Distributed Applications (CorDapps) running on these nodes. Each node is identified by means of a 
certificate issued by the Network's doorman, and will also be identifiable on a network map. 

Corda Network enables interoperability – the exchange of data or assets via a secure, efficient internet layer – in a way 
that isn't possible with competing permissioned distributed ledger technologies or legacy systems.

As of December 2018, Corda Network is live with its new [certificate hierarchy](https://docs.corda.net/head/permissioning.html). 

Initially, it will be governed by R3, but an independent, not-for-profit Foundation has been set-up which will govern the Network from early/mid 2019, after a transition period when control moves entirely to the Foundation. See the [governance model](../governance/index.md) for more detail.

The Network will comprise many sub-groups of participants running particular CorDapps (sometimes but not 
always referred to as 'business networks'), and such groups will often have a co-ordinating party (the 'Business 
Network Operator') who manages the distribution of the app and rules (including around membership) for its use. 

Corda Network will support the operation of business networks by industry-specific operators within the Network. There 
will be a clear separation between areas of governance for the Network and for individual business networks. For example, 
rules around membership of business networks will be controlled by its Business Network Operators. 

Key services 
============

Identity Issuance Service
-------------------------
The Service receives Certificate Signing Requests (CSRs) from prospective Network Participants (sometimes via a Business Network Operator) and reviews the information submitted. A digitally signed Participation Certificate is returned if:

* The prospective Corda Network Participant meets the requirements specified in the documentation;
* Evidence is provided by the Participant or Business Network Operator of agreement to the Corda Network Participant Terms 
of Use.

The Corda Network Participant can then use the Participation Certificate to register itself with the R3 Network Map Service.

Network Map
----------- 
The Network Map Service accepts digitally signed documents describing network routing and identifying information from 
Participants, based on the Participation Certificates signed by the Doorman, and makes this information available to all 
Corda Network Participants.

Notary 
------
Corda design separates correctness consensus from uniqueness consensus, and the latter is provided by one or more Notary 
services. The Notary will digitally sign a transaction presented to it - provided no transaction referring to 
any of the same inputs has been previously signed by the Notary, and the transaction timestamp is within bounds. 

Business Network Operators and Network Participants may choose to enter into legal agreements which rely on the presence 
of such digital signatures when determining whether a transaction to which they are party, or upon the details of which they 
otherwise rely, is to be treated as 'confirmed' in accordance with the terms of the underlying agreement. 

Support 
-------
The Support Service is provided to Participants and Business Network Operators to manage / resolve inquiries and incidents 
relating to the Doorman, Network Map Service and Notary Service, and any other relevant services.


