# Node IP Connectivity Policy

## 1 IP Policy

1. Nodes may advertise IPv6 addresses, however all nodes in the main zone must advertise at least one IPv4 address.
2. IPv6 only nodes will not be allowed before at least 2022.
3. Node P2P ports must be globally reachable via the internet, from any part of the internet. By implication you may not 
use TCP/IP firewall rules to block who connects to your node. Instead, access control should be done cryptographically 
using TLS termination and membership rule checking at the start of flow logic (i.e. before any code other than session 
setup runs).

## 2 Rationale

The world has run out of IPv4 addresses. IPv6 is clearly the future. Unfortunately
[adoption is currently only at 25%](https://www.google.com/intl/en/ipv6/statistics.html) and whilst it’s growing, so 
too is the disparity between weekend and weekday IPv6 traffic. This is because workplaces are slower to adopt IPv6 than 
consumer ISPs.

Corda nodes are meant to run on servers. Some data centres do not currently support IPv6, although the big cloud 
operators all do. However data-centres have been allocated enough IPv4 addresses that realistically it is very unlikely 
that a node operator will be unable to obtain one in the near future.

Like all blockchain networks the Corda network is flat with direct inter-node connectivity. The Corda Network Foundation 
does not sit in the middle and route messages. Therefore, all nodes must be able to build TCP/IP connections to each 
other in order to exchange data.

TCP/IP level firewall rules are a traditional way to regulate inter-business communications, however, there are no good 
standard protocols for altering them from inside the firewall and many organisations have built elaborate bureaucracies 
around doing so. If Corda nodes were to be firewalled at the TCP/IP level, the network would rapidly ossify and new 
members of a business network would experience multi-month delays whilst all the firewalls on all the other nodes were 
reconfigured. This would make Corda essentially useless.

Therefore, nodes should be protected with cryptographic firewalls. This is more secure as it is resistant to BGP 
hijacks and other forms of IP address takeover. TLS handshaking is used to verify the peer identity. Access control can 
be enforced by node configuration and/or at the app level. This reflects the intended configuration of a node that 
supports multiple collaborating apps in dynamic business networks, each of which may have its own notion of which 
counterparties are members.