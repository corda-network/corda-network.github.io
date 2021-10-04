# Network Options & Other Considerations 

- [1. What are the Network options currently offered?](#1-what-are-the-network-options-currently-offered)
- [2. What are the Pros and Cons of joining each of these Networks?](#2-what-are-the-pros-and-cons-of-joining-each-of-these-networks)
- [3. Who makes the decision about joining a Segregated Network or Mainnet?](#3-who-makes-the-decision-about-joining-a-segregated-network-or-mainnet)
- [4. If I have a node on a Segregated Network, can I transact with the Mainnet?](#4-if-i-have-a-node-on-a-segregated-network-can-i-transact-with-the-mainnet)
- [5. What does Corda Network check before I can join?](#5-what-does-corda-network-check-before-i-can-join)
- [6. If I have a Sponsored Node on the Network, but now want to join another Business Network, how do I change my membership type?](#6-if-i-have-a-sponsored-node-on-the-network-but-now-want-to-join-another-business-network-how-do-i-change-my-membership-type)
- [7. Can a Business Network have both Sponsored and Direct Participants?](#7-can-a-business-network-have-both-sponsored-and-direct-participants)
- [8. My legal entity wants to be a member of more than one Business Network. Should I use only one node (the same node) in each one Business Network?](#8-my-legal-entity-wants-to-be-a-member-of-more-than-one-business-network-should-i-use-only-one-node-the-same-node-in-each-one-business-network)
- [9. If I have a third party hosting a node on my behalf, do you provide a template legal agreement for that?](#9-if-i-have-a-third-party-hosting-a-node-on-my-behalf-do-you-provide-a-template-legal-agreement-for-that)



## 1. What are the Network options currently offered?

- Corda Network Mainnet - a service operated by R3, envisioned to have many business networks interoperating.

- Segregated Network - partitioned network off Corda Network Mainnet; uses the same Trust Root as the Mainnet, but in all other respects is separate (has separate notary, network map, network parameters).

- Standalone Network - network option where the client needs to set-up, deploy and run their own infrastructure (including the trust root) using Corda Enterprise Network Manager and Notary software. This option is not part of Corda Network.

## 2. What are the Pros and Cons of joining each of these Networks?

| **Network Choice**    	| **Pros**                                                                                                                                                                                                                	| **Cons**                                                                                                                                                           	|
|-----------------------	|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|--------------------------------------------------------------------------------------------------------------------------------------------------------------------	|
| Corda Network Mainnet 	| Interoperability – Inter-business network transactions; low effort & time to set-up; low cost to transact                                                                                                               	| Less control over policy and services are operated by a third party                                                                                                	|
| Segregated Network    	| Node identities not visible to Mainnet; control over network parameter upgrades; lower effort and time to set-up; transactions are free                                                                                 	| Less control than a standalone network; time, effort and cost to set-up and operate the private notary                                                             	|
| Standalone Network    	| Control the location of governance, rules and administration, notary operator(s) and shared services infrastructure and data, including the trust root; control over network parameters and notaries, Identity issuance 	| Less interoperability with other business networks (unless they join the standalone network); time, effort and cost for set-up and operation (depending on set-up) 	|

## 3. Who makes the decision about joining a Segregated Network, or Mainnet?

Typically this will be the Business Network Operator who decides, but usually in consultation with their end-participants.

## 4. If I have a node on a Segregated Network, can I transact with the Mainnet?

No, this is not possible today even though they share the same Trust Root.

## 5. What does Corda Network check before I can join?

To be admitted to Corda Network you need to satisfy the following requirements:

- Have signed any relevant legal agreements for participation including agreeing to pricing.
- Your organisation is registered with an official trade / company registry.
- Your organisation is not on any sanctions lists.

## 6. If I have a Sponsored Node on the Network, but now want to join another Business Network, how do I change my membership type?

There are two kinds of Corda Network Participants: Participants (who have legal contracts with R3) and Sponsored Participants (who have access to Corda Network via a Participant’s legal contract). Sponsored Participants' Corda nodes are sometimes referred to as Sponsored Nodes. If you wish to change your membership type please contact your R3 Account Manager.

## 7. Can a Business Network have both Sponsored and Direct Participants?

Yes.

## 8. My legal entity wants to be a member of more than one Business Network. Should I use only one node (the same node) in each one Business Network?

You can use the same node OR different nodes in each one. This should be a decision your business makes, but Corda allows for either.

## 9. If I have a third party hosting a node on my behalf, do you provide a template legal agreement for that?

No. This is strictly between your legal entity and that 3rd party, and is separate from any legal relationship you have with Corda Network. We are agnostic who hosts the node.
