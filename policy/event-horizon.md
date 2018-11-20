|Corda Network Foundation|[Document history]({{ site.github.repository_url }}/blame/master/{{page.path}})|

Event Horizon Policy
====================

1 Policy
--------
The event horizon for the Corda network shall be defined as 2592000 seconds on the Corda/Java timeline. This is 
equivalent to 30 days excluding daylight savings transitions and leap seconds.

2 Rationale
-----------
Corda nodes are not required to be online continuously. Like email servers, transient outages are tolerated by peer 
nodes buffering outbound messages to disk and retrying from time to time. Thus nodes can be restarted, upgraded and so 
on without causing any user visible problems beyond increased latency.

Although this design is robust, it does imply that nodes which go offline permanently (e.g. due to bankruptcy, seizure, 
destruction) would cause permanent resource leaks throughout the network as flows hang and retry delivery forever. 
Therefore there should be an upper bound at which point the node is assumed to never be returning, enabling message 
queues to be flushed and in-flight flows to be killed.

The event horizon should be long. If it is too low then there is a risk that recoverable outages are turned into major 
user-visible disruption because the event horizon is crossed unnecessarily. If it is too high then disk space and CPU 
time may be wasted, however the cost of this is likely to be very low compared to the cost of business disruption and 
required human attention.

In addition, the Corda network may be extended in future to support nodes owned by small businesses and even sole 
traders, which may go offline for weeks due to trivial events like taking a holiday or sickness.
Therefore we propose that roughly one month provides a good balance of factors.
