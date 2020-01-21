# Deciding on the right Network choice

For anyone using Corda, there are 3 network choices available – Corda Network, a Segregated Network - off Corda Network, but which uses the same Trust Root; and a Private Network - using Corda Enterprise Network Manager, with a *separate* Trust Root.

## Corda Network

A shared, permissioned, global network – which business networks may join and operate within. Part of the original design of Corda, its envisioned as an internet of Corda nodes,’ with nodes transacting seamlessly across many CorDapps and business networks. Although 3rd party notaries will be on the network in late 2020, at the moment only the main Corda Network notary is available on the mainnet.

## Segregated Network

A partitioned sub-network off the Corda Network mainnet, which enables membership privacy (only members of the segregated network are visible to each other) and complete control over its own software upgrade schedule. It uses the same Trust Root as Corda Network, but in all other respects is separate (has own notary, network map, network parameters). Participants using a Segregated Network must run their own notary. The annual cost for a Segregated Network (including either or both Pre-Production and Production networks) will be $10,000 per year. 

## Private Networks

A business network operating and being governed entirely independently, using the Corda Enterprise Network Manager software. Can control location and operations of all its services and infrastructure, as well as running its own Service Level Agreements. Would need a separate Trust Root.

For more information on how to choose between these options, please reference this 12-page paper:

[Link to paper - attached PDF](https://github.com/corda-network/corda-network.github.io/blob/change/site-handover/assets/Corda%20Networks%20-%20guiding%20note_Final.pdf)
