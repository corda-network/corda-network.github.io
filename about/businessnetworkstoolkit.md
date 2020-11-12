# Business Network Membership Management

This article assumes the reader's familiarity with the concept of Business Networks. For more information 
about Business Networks, please visit [Corda Solutions website](https://solutions.corda.net/business-networks/intro.html). 

Business Networks (BNs) are an abstraction layer on top of Corda Network, that allows multiple business applications to work 
and to interoperate within a single global shared environment.

Business Networks provide some of the benefits of separate, private networks, such as control over membership, while at the same time enabling cross Business Network transactions, all operating within the same zone: Corda Network. 

The launch of Corda 4.6 saw the introduction of a new CorDapp, Business Networks Extension. This  primitive app will help CorDapp developers represent membership attestations, membership lists, and, ultimately, Business Network abstractions. The CorDapp also introduces new APIs in the form of a CordaService with the purpose of managing memberships, driving entitlements, and setting granular privacy and permissioning within a business network.

This Corda platform extension allows Business Network Operators to enhance customer onboarding experience to a BN, map relationships to represent off ledger contractual agreements between parties within the BN, dynamically update membership information and delegate some membership management  to sub-group leaders by assigning roles & entitlements. 

With the introduction of native support for Business Network membership representation, the current open source Business Network Membership Service will be deprecated as the feature set will be included in Corda's official distribution. For more details on Business Network membership management, please visit the  [docs.corda](https://docs.corda.net/docs/corda-os/4.6/business-network-membership.html) site.
