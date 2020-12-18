# Frequently Asked Questions

## Contents

- [1. Network Choice](#1-network-choice)
- [2. Considerations When Joining Corda Network](#2-considerations-when-joining-corda-network)
- [3. Understanding Corda Network Services](#3-understanding-corda-network-services)
- [4. Other](#4-other)



## 1. Network Choice

### What are the Network options currently offered?

1. Corda Network Mainnet - an internet of Corda nodes, envisioned to have many business networks interoperating.

2. Segregated Network - partition off Corda Network Mainnet; uses the same Trust Root as the Mainnet, but in all other respects is separate (has separate notary, network map, network parameters).

3. Private network - uses Corda Enterprise Network Manager, with a separate Trust Root and is not part of Corda Network.

---
### What are the Pros and Cons of joining each of these Networks?

| NETWORK CHOICE        | PROS                                                                                                                                                                                                                          | CONS                                                                                                                                                                  |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Corda Network Mainnet | - Interoperability – Inter-business network transactions<br>- Low effort & time to set-up<br>- Low cost to transact                                                                                                           | - Participant identity is visible on public network map<br>- Less control over policy and services are operated by a third party                                      |
| Segregated Network    | - Node identities not visible to Mainnet<br>- Control over network parameter upgrades<br>- Lower effort and time to set-up; transaction is free <br>     | - Less control than a private network<br>- Time, effort and cost to set-up and operate the private notary                                                             |
| Private Network       | - Control the location of governance, rules and administration, notary operator(s) and shared services infrastructure and data, including the trust root<br>- Control over network parameters and notaries, Identity issuance | - Less interoperability with other business networks (unless they join the private network)<br>- Time, effort and cost for set-up and operation (depending on set-up) |

---

### Who makes the decision about joining a Segregated Network, or Mainnet?

Typically this will be the Business Network Operator who decides, but usually in consultation with their end-participants.

---

### If I have a node on a Segregated Network, can I transact with the Mainnet?

No, this is not possible today even though they share the same Trust Root.

---

## 2. Considerations When Joining Corda Network

### What does Corda Network check before I can join?

To be admitted to Corda Network you need to satisfy the following requirements:

- Have signed any relevant legal agreements for participation
- Your organisation is registered with an official trade / company registry
- Your organisation is not on any sanctions lists

---

### What are the main differences between Sponsor and Direct Model models?

Sponsor model is aimed at Business Network Operators who intend to onboard a significant number of nodes.



|                                            | **Direct Model (DEFAULT)**           | **Sponsor Model**                                                    |                     |
|--------------------------------------------|--------------------------------------|----------------------------------------------------------------------|---------------------|
|                                            | Direct Participant                   | Sponsor                                                  | Sponsee Participant |
| Signs legal agreement with the Foundation? | Yes                                  | Yes, and for their Sponsees _but accessing the Sponsor CorDapp only_ | No                  |
| Covers billing?                            | Yes                                  | Yes, and for their Sponsees                                          | No                  |
| Provides support?                          | Gets it directly from the Foundation | Yes, and for their Sponsees                                          | No                  |
| Can be part of more > 1 BN?                | Yes                                  | No                                                                   | No                  |

---

### If I have a Sponsored Node on the Network, but now want to join another Business Network, how do I change my membership type?

Email info@corda.network. 

---

### Can a Business Network have both sponsored and direct participants ?

Yes.

---

### My legal entity wants to be a member of more than one Business Network. Should I use only one node (the same node) in each one Business Network?

You can use the same node OR different nodes in each one. This should be a decision your business makes, but Corda allows for either.

---

### If I have a third party hosting a node on my behalf, do you provide a template legal agreement for that?

No. This is strictly between your legal entity and that 3rd party, and is separate from any legal relationship you have with Corda Network. We are agnostic who hosts the node.

---

### Do you negotiate on the legal agreements provided in this website?

No. These are standard agreements. The Foundation is a not for profit, which doesn’t have the resources to negotiate.

---

## 3. Understanding Corda Network Services

## Notary

### What kind of notary does the network have?

It is a highly-available, non-validating notary cluster. It consists of multiple worker nodes that are geographically distributed across different locations in Western Europe. For more information about what a notary is, see this website.

---

### Can the Foundation run a notary for me, on Corda Network?

Today, all participants on the Corda Network Mainnet share a public notary and those who want to run their own notary can do so on a Segregated Network. If you are interested in having a dedicated notary run on your behalf on the Mainnet, please contact info@corda.network

---

### Is there a plan to introduce more notaries to Corda Network?

Yes. Corda supports more than one notary. There is currently only one notary, but we do want to introduce more notaries in the future.

---

### Do I have to specify which notary I want to use?

Yes, if your CorDapp is using the public Corda Network notary, you must ensure it obtains the preferred notary service X.500 name from the CorDapp config file.

CorDapp code should not assume there is only one notary cluster (e.g. not use “notaries.single”) nor should it select a notary at random (e.g. not use “notaries.first”).

The functionality of CorDapps using outdated syntax will be impaired in a multi-notary environment, which is why selecting a notary using the notary’s X.500 name is important for future-proofing CorDapps.

More information about selecting a notary is available at https://corda.network/participation/notary-considerations/.

---

### What information do notaries have access to? 

Non-validating notaries see all of the transaction. They don’t run the verify function, just check that inputs have not been previously consumed, and that all input states were under its control. In principle this means that they could record the details of all transactions, although Corda Network notary implementation does not do such recording. 

Below is a summary of what specific transaction components have to be revealed to a non-validating notary:

| TRANSACTION COMPONENTS            | WHAT IS REVEALED |
|-----------------------------------|------------------|
| Input states                      | References only  |
| Output states                     | Hidden           |
| Commands (with signer identities) | Hidden           |
| Attachments                       | Hidden           |
| Time window                       | Visible          |
| Notary identity                   | Visible          |
| Signatures                        | Hidden           |
| Network parameters                | Visible          |

Notaries record the calling party’s identity: the public key and the X.500 Distinguished Name.

---

### Do notaries have access to all transactions?

Not exactly. Each transaction is governed by a notary, but a notary doesn’t necessarily see every transaction on the network. If there is more than one notary on a network, then the transactions can be split among them, for example. 

---

## Network Maps

### What is the function of the Network Map Server?

The Network Map is a collection of signed NodeInfo objects. Each NodeInfo is signed by the node it represents and thus cannot be tampered with. It forms the set of reachable nodes in a compatibility zone. 

The network map server also distributes the parameters file that define values for various settings that all nodes need to agree on to remain in sync.

---

### Who communicates with the Network Map and how?

Each node periodically polls the network map for deltas/changes that may have occurred. Of course, we don’t want the network map to be a single point of failure, so all of the nodes have a local copy of the NodeInfo objects that they reference in in order to communicate with other nodes.

---

### What data is collected by Network Map and is it stored in a database?

NodeInfo objects contain:

- Platform Version that the node is referencing. 

- Node Identity (legal name + node issued certificate). 

- Node IP Address. 

NodeInfo objects are stored in the database that is determined at the time the node is installed and configured.

---

## 4. Other

### Does it make a difference if I use Corda Enterprise or Corda Open Source, on Corda Network?

No

---

### I’m not an Enterprise customer. Am I still entitled to Support?

Yes, we have some support available for customers on network-related issues. We will be publishing the Handbook soon, but for now, please email info@corda.network.

---

### At which point am I entitled to Corda Network Support?

As soon as a Corda Network node has onboarded, its registered email address is entitled to access Corda Network support portal and receive updates on the state of Corda Network infrastructure via Statuspage.

---

### Is there any formal trust attestation available for the Corda Network’s Certificate Authority?

The entirety of the material that can be provided to network participants with regards to  where our certificate and trust attestation comes from is available at https://trust.corda.network/. 

It is the responsibility of each network participant to determine from the documentation at the URL above, whether the assurance levels provided by the network trust root are sufficient.

---

### Can I whitelist Corda Network Infrastructure?

Corda Network infrastructure can be whitelisted using FQDN names but not IP addresses. As Corda Network infrastructure is deployed on Cloud we don’t have 100% ownership of the Public IPs. 

In the future, Corda Network improvements will likely result in our Public IPs changing and that would negatively impact participants who would have to update their IP whitelisting rules. To avoid this we recommend using FQDN addresses of Network Map, Notary and Identity Manager services instead.

For more information on whitelisting please contact info@corda.network
