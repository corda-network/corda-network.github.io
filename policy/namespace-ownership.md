|Corda Network Foundation|[Document history]({{ site.github.repository_url }}/blame/master/{{page.path}})|

Namespace Ownership Policy
==========================

1 Introduction
--------------
Corda implements a decentralised database that can be unilaterally extended with new data types and logic by its users, 
without any involvement by the closest equivalent we have to administrators (the “Operator”). 
Even informing them is not required.

This design minimises the power the Operator has and ensures deploying new apps can be fast and cheap - it’s limited 
only by the speed with which the users themselves can move. But it introduces problematic levels of namespace 
complexity which can make programming securely harder than in regular non-decentralised programming.

2 Policy
--------
Any organization will be able to claim a Java package name in the next network parameters refresh, by either:
 
* Sending a DKIM protected email with an attached self-signed certificate to claim@corda-network (when set up)from an 
email address that matches the requested top level domain.
* Presenting a key that is either equal to or which chains to their identity key, if they have gone through ID 
verification with an EV SSL cert.
 
If the Network Operator fully automates this process, they are expected to filter out emails coming from large 
webmail domains using e.g. [this list](https://webmail.wiki/list-of-webmail-domains/).
 
The start date for this policy will be later in 2019.
 
3 Rationale
-----------
[Package namespace ownership](https://docs.corda.net/head/design/data-model-upgrades/package-namespace-ownership.html) 
is a new optional feature arriving in Corda 4. You can read the design document to learn 
the details but briefly, links between Java package namespaces and public keys in the 
network parameters will be published. For example:
 
* com.r3.* -> secp256k1:12345….7890
* net.corda.* -> secp256k1:9876….54321
* com.megacorp.foobarapp.* -> rsa:123456789abcdef00
 
This has two purposes:
 
Eliminate some surprising degrees of freedom in Corda’s design, to more closely align developers’ mental model of the 
ledger with reality.
Allow a migration away from hash constraints to signature constraints for apps that have gone live already with 
accidental usage of hash constraints.
 
For the feature to work, Java package namespaces should be usable only by developers working for the organisations they 
(appear to) reflect. Corda 4 will reject unsigned transaction attachment JARs defining classes in claimed namespaces. 
JARs can define classes in namespaces only if they are signed by the appropriate code signing key.
 
We must therefore verify that the signing key that is registered for com.megacorp.* is actually controlled by employees 
of that organization.
 
DomainKeys Identified Mail (DKIM) is an email security standard designed to block phishing attacks. It now protects 
virtually all email (97% of non-spam arriving at Gmail). When a domain supports DKIM, all outbound mail claiming to be 
from that domain must be signed using keys published in DNS. The keys are held and signatures checked entirely on the 
email relays, and thus DKIM is transparent to the end user. Receiving an email that passed DKIM authentication checks is 
proof that the email came from the user named in the From header (assuming that companies own infrastructure has not 
been compromised). Therefore, receiving a self-signed certificate from a DKIM protected domain is equivalent to 
asserting ownership of that key by an employee or user at that domain.
 
The second approach is useful for cases where the Network Operator chooses to allow ID verification using EV SSL certs, as 
these contain a verified domain name already.