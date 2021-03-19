# Business Networks (Consortiums)

For Corda, Business Networks are groups of companies who wish to transact together - using either Corda Open Source or Enterprise, for a specific commercial purpose. 

**Governance**

Business Networks can have many different governance models. Business Networks using Corda can range from a consortium model, to a more centralized model with a Business Network Operator (which may be a separate legal entity). A BNO often sets-up and operates legal rules, organisation structure and business processes for its Business Network. They may also design and operate a shared CorDapp for the Business Network’s members to transact with, or this can also be set-up and run by a third party. In most circumstances, a BNO should ask its participants to sign legal agreements directly with the Foundation (prior to joining the Network), except when the BNO has established a sponsorship model with Corda Network Foundation.


**Business Network Membership Management**

Business Networks are an abstraction layer on top of Corda Network, that provide some of the benefits of separate, private networks, such as control over membership, while at the same time enabling cross Business Network transactions, all operating within the same zone: Corda Network.

Depending on their size, Business Networks may also wish to onboard, offboard and bill their members. 

The launch of Corda 4.6 saw the introduction of a new CorDapp, Business Networks Extension, which also includes new APIs in the form of a CordaService with the purpose of managing memberships within a Business Network. This Corda platform extension allows BNOs to enhance customer onboarding experience to a Business Network, map relationships to represent off ledger contractual agreements between parties within the Business Network, dynamically update membership information and delegate some membership management to sub-group leaders by assigning roles & entitlements.

With the introduction of native support for Business Network membership representation, the open source Business Network Membership Service has been deprecated as the feature set will be included in Corda's official distribution.

We continue to develop tools and features for Business Networks to work well. For more information on the options and flexibility which Business Networks can offer while using Corda please visit [Business networks and memberships](https://github.com/corda/bn-extension) and [Corda solutions site](https://solutions.corda.net/business-networks/intro.html).









