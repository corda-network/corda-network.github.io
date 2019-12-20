# Port Ranges Policy

## 1 Policy

Outbound connectivity for Corda nodes must support all possible ports allowed by the TCP specification. This does not 
imply opening all ports on the inbound path – node operators may select a single port for their node and open only that 
port on network-level firewalls.
 
We recommend but do not require that nodes advertise port 31337 in the network map, if node operators have no other 
preference.
 
## 2 Rationale

It is common for firewall operators to dislike the idea of opening more ports than the minimum. Therefore picking a 
single port on which Corda nodes may establish outbound connections may make it slightly easier to get through firewall 
bureaucracies at large institutions.
 
However there are two reasons for allowing outbound connections to any port:

* Although we are working on upgrading the Corda protocol to support [TLS SNI] (https://en.wikipedia.org/wiki/Server_Name_Indication), old nodes will not know how to use it. 
Until the minPlatformVersion for the Corda network is raised to a level that makes SNI support mandatory the only way 
to disambiguate a connection to an IP address that may host multiple identities is by port number.
* CorDapps may wish to make non-P2P connections, for instance, an app providing oracle services may want to connect to a 
web server via TLS to download data from an external provider.
 
If we picked a static port like 31337 - [a favourite](https://www.urbandictionary.com/define.php?term=31337) - then we’d lose the ability to host multiple identities on 
a single IP address pre-SNI, and installing apps would become harder, because they’d often start out blocked.
 

## 3 Possible Future Evolutions

Whilst non-P2P connections made by apps may be restricted in future to reduce the trust needed in app developers, this 
would be a feature of a node implementation and not something that affects network level policy.
 
If CorDapps become sand-boxed (either by the node or by HTTP reverse proxies) such that they never need to make outbound 
connections on their own, and when minPlatformVersion is bumped high enough to eliminate non-SNI supporting 
implementations, both justifications for allowing the entire port range are gone. In this case the network may migrate 
to a single port number for all nodes, hence the recommendation. However this is a possible evolution and not a policy 
commitment.
