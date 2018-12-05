|Corda Network Foundation|[Document history]({{ site.github.repository_url }}/blame/master/{{page.path}})|

Joining Corda Network
=====================

The below gives a high-level guide on the steps required to join Corda Network. However, we have found that many of our users are joining Corda Network as part of a wider group or [business network](https://solutions.corda.net/business-networks/intro.html), so far - and the process can be modified where a group is joining together.

Firstly, Corda Network participation requires each node to possess a recognised Certificate Authority (CA) signed certificate 
(“Participation Certificate”), which is used to derive other digital certificates required (such as legal entity signing 
certificates and TLS certificates).

Identity certificates must be issued by the Corda Network Operator (Doorman / Network Map), which guarantees that the identity 
listed on the certificate is uniquely held by a single party within the network.

A high-level outline of steps to join the Network is listed below. This assumes that Participants wish to operate a node 
and already have access to at least one CorDapp which they wish to deploy. A more detailed step-by-step guide will soon 
be available.

Step 1. Obtain Corda software - either the Enterprise version, via a Corda sales representative, or the open source version
available through [github](https://github.com/corda) under an Apache 2 license. There is further guidance available on Corda Docs for [getting set up on Corda] (https://docs.corda.net/getting-set-up.html).

Step 2. Whitelist the IP address(es) associated with the Corda deployment, prior to raising Certificate Signing Requests (CSRs). Send to doorman@r3.com.

Step 3. For the time being, request the trust root certificate from Corda Network Doorman, by emailing doorman@r3.com, which 
will be sent back as a truststore.jks file. In future, the Corda Network trust root will be packaged in the software
distribution.

Step 4. [Start the node](https://docs.corda.net/deploying-a-node.html) - where applicable, with help from a Corda 
representative. 

Step 5. [Configure the node](https://docs.corda.net/corda-configuration-file.html) – a node.conf file must be included in the 
root directory of every Corda node. This includes: specifying an email address in relation to the certificate signing 
request as well as choosing a distinguished name.

*Specifying an email address* - this is only retained by the Operator for the purposes of contact in relation to identity checks and any administrative issues.

*Choosing a Distinguished Name* 

Step 6. Run the initial registration. 
Once the node.conf file is configured, the following should be typed to the command line "java -jar <corda jar file> --initial-registration". This will send a Certificate Signing Request (with the relevant name and email) to the 
Network Manager service (Doorman / Network Map).

Step 7. Sign Participant terms of use, either directly or indirectly:
* **Indirect model**: A Business Network Operator (BNO) may request approval for a certificate on behalf of Participants in its Business Network.
* **Direct model**: The Participant requesting a certificate for themselves.
Where relevant, a Terms of Use legal document will be sent from doorman@r3.com which will need to be signed by the Participant.

Step 8. Doorman verification checks – upon receipt of a CSR, a number of identity-related checks will be conducted, before issuing a certificate, including email and legal entity checks. 

Identity checks do not constitute formal Know Your Customer (KYC) or Enhanced Due Diligence (EDD) checks. Node operators and their users are responsible for carrying out appropriate due diligence on any participant in relation to transactions performed via Corda Network.

Step 9. Once identity checks have been completed, a signed node CA certificate will be released by the Operator to the node. A node in polling mode will automatically download and install the certificate in its local trust store. It will also automatically generate additional identity and TLS certificates from the node CA certificate, which are required for subsequent operation of the node. 

At this point, the node will terminate and will need to be restarted. Type "java -jar <corda jar file>" into the command line. Once restarted, the node will then proceed to download the network map and discover other nodes within Corda Network.
