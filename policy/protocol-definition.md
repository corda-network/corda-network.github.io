|Corda Network Foundation|[Document history]({{ site.github.repository_url }}/blame/master/{{page.path}})|

Protocol Definition
===================

1 Proposed policy
=================

Zone members agree that their nodes will understand the Corda protocol as defined by the open source reference 
implementation, of at least the version specified in the network parameters' minPlatformVersion field or higher. Note 
that the "platform version" may not always be aligned with the major version number of the Corda open source release, 
although at the time of writing it is.

Nodes may additionally support and use extended versions of the protocol, however they must not reject traffic from 
nodes that are using the regular protocol.

2 Rationale
===========

There is currently no written specification of the Corda protocol. Therefore the Corda protocol is defined as whatever 
the Corda software itself does.

One day, if the project continues to be successful, there will be a need to write such a specification so other 
node implementations can be written (or more likely, less general programs that speak a subset of the protocol). At 
such a time the official definition of the protocol may be redefined to be whatever the specification says, and if the 
open source implementation doesn't do that, then the open source implementation is buggy.

The Corda protocol is designed to be specifiable - it's largely AMQP over TLS with extensions, and of course is heavily 
based on Java which is itself a standard with a formal specification. But it also sits on top of a very large pyramid of 
technologies, so any specification would run to hundreds of pages. So, writing a detailed enough specification for this 
to happen is a large undertaking which doesn't directly sell software, therefore it will have to wait until there is 
sufficient demand.

Until then, an implementation or modification to the open source implementation in incompatible ways will be deemed to 
have become incompatible with the Corda protocol and thus in violation of zone policy.