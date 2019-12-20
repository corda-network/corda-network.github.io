# Deciding on the right Network choice

For anyone using Corda, there are 3 network choices available – Corda Network, a Segregated Network off Corda Network, which uses the same Trust Root, and a Private Network (using Corda Enterprise Network Manager, and with a separate Trust Root).

## Corda Network

A shared, permissioned, global network – which business networks may join and operate within. It’s sometimes called ‘an internet of Corda nodes,’ envisioned to have many business networks interoperating.

## Segregated Networks

A partitioned sub-network within Corda Network, which enables membership privacy (only members of the segregated network are visible to each other) and complete control over its own software upgrade schedule. It uses the same identity root as CN, but in all other respects is separate (has own notary, network map, network parameters).

## Private Networks

A business network operating and being governed entirely independently, using the Corda Enterprise Network Manager software. Can control location and operations of all its services and infrastructure.

[Link to paper - attached PDF](https://github.com/corda-network/corda-network.github.io/blob/master/assets/Corda_Networks_-_guiding_note_Final.pdf)
