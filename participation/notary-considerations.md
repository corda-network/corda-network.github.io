|Corda Network Foundation|[Document history]({{ site.github.repository_url }}/blame/master/{{page.path}})|

Notary Considerations
=====================

A notary is a network service that provides uniqueness consensus by attesting that, for a given transaction, it has not already signed other transactions that consumes any of the proposed transaction’s input states.

When joining Corda Network, participants *will need to decide* whether:
* to use the Corda Network notary for their transactions, or 
* to set-up and run their own notary.

In deploying a CorDapp, currently the default option is to use the Corda Network notary. For all participants using this service, [transaction fees](https://corda.network/participation/membership-tiers.html) will be charged.

However, Corda Network participants also have the option to set up their own, third-party notary. Detailed instructions are listed, how to do set-up a 'third party notary' [here](https://docs.corda.r3.com/running-a-notary-cluster/toctree.html). In this case, transaction fees will not apply. It is worth noting that setting up a notary will be a complex process; for advice, feel free to email our public mailing lists, [corda-network](https://groups.io/g/corda-network) or [corda-dev](https://groups.io/g/corda-dev) - or (if applicable) your R3 representative.

For an introduction to what is a notary, in Corda, take a look at the video and explanations uploaded [here](https://docs.corda.net/key-concepts-notaries.html). 

Guidance for application developers:
------------------------------------

**Explicit Selection of Notaries**
 
Corda Network allows for public and private notaries to operate. Both types of notary are currently advertised in the network parameters and application developers should ensure that their applications explicitly select their chosen notary when writing states that will be subject to notarized transactions (state issuance does not require notarization). Notary identities follow the same format in the network parameters as the X509 certificates issued to their nodes, and the full identity should be specified.
 
A list of current notaries will be maintained on this site (see below).
 
Sample code for selecting notaries in the application is included here, based on actual identity data for the first public notary to be offered in Corda Network:
 
// In the flow context.
serviceHub.networkMapCache.notaryIdentities.single { it.name == CordaX500Name.parse("CN=Non-validating Prod HA Notary, O=R3 HoldCo LLC, L=New York, C=US") }
 
// Via RPC, where rpc is CordaRPCOps.
rpc.notaryIdentities().single { it.name == CordaX500Name.parse("CN=Non-validating Prod HA Notary, O=R3 HoldCo LLC, L=New York, C=US") }

**Current Notary List**:
 
1. R3 High Availability Non- Validating Notary
   X500 Name: CN=Non-validating Prod HA Notary, O=R3 HoldCo LLC, L=New York, C=US
 
Setting of Contract Constraints (To Follow)
