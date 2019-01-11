|Corda Network Foundation|[Document history]({{ site.github.repository_url }}/blame/master/{{page.path}})|

Business Networks Toolkit
========================

This article assumes the reader's familiarity with the concept of Business Networks. For more information 
about Business Networks please visit [Corda Solutions website](https://solutions.corda.net/business-networks/intro.html). 

Business Networks (BNs) is an abstraction layer on top of a Corda Network that allows multiple business applications to work 
and to interoperate withing a single global shared environment.

Business Networks provide the benefits of private networks, such as control over memberships in the same time allowing 
to seamlessly build cross Business Network transactions within the same Compatibility Zone. 

Business Networks functionality can be implemented at the CorDapp level and it's not a part of the Corda core itself. A
particular implementation can be chosen by a Business Network Operator (BNO) at their own discretion. 

Business Networks Toolkit is an Open Source project maintained by R3. It contains a set of utilities that aim to help
Business Network Operators to run their Business Networks. Business Networks Toolkit contains the following tools: 
* [Business Network Membership Service (BNMS)](https://github.com/corda/corda-solutions/tree/master/bn-apps/memberships-management). 
BNMS is an extensible service that allows BNOs to manage memberships on their Business Networks. It provides APIs to 
on-board new and to suspend the existing members, to associate a custom metadata with a node's identity and 
distribute it to the Business Network. BNMS can be used by multiple CorDapps simultaneously and allows a single node to 
participate in multiple Business Networks while managing all memberships within a single application. BNMS distributes
any changes to the memberships in nearly real-time and provides instant membership revocations (which might take a while 
in the case of CRLs).
* [CorDapp Distribution Service (CDS)](https://github.com/corda/corda-solutions/tree/master/bn-apps/cordapp-updates-distribution).
CDS aims to tackle the problem of CorDapp updates distribution. It allows Business Network members to subscribe to one 
or multiple distribution channels and to automatically download CorDapp updates whenever they get released.  CDS heavily 
utilises Maven infrastructure and can be easily integrated into an existing enterprise deployment, without requiring any changes 
to allow an extra ingress traffic. 
* [Ledger Sync Service](https://github.com/corda/corda-solutions/tree/master/bn-apps/ledger-sync). Ledger Sync Service allows 
Business Network participants to verify their ledgers consistency and to recover the ledger from their counterparts 
in the case of a data loss.

Business Network Toolkit can be easily integrated into your solution. For more details please visit the repositories
referenced above.