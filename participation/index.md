|Corda Network Foundation|[Document history]({{ site.github.repository_url }}/blame/master/{{page.path}})|

Joining Corda Network
=====================

A summary of steps to join the Network (either the Pre-Production or Production network) is listed below. More details are given on each of these steps, further down this page. This assumes that participants wish to operate a node and already have access to at least one CorDapp which they wish to deploy, as well as other considerations listed. 

**Step 1: Terms of Use Agreement**
----------------------------------

**1.1 Direct Model**

*Pre-Production Network*

The Terms of Use for direct signing are available as a click-through agreement which will provide direct confirmation of acceptance to the Corda Network Operator. Available here: [Terms of Use](https://fs22.formsite.com/r3cev/CordaUATAgreement2019/index.html)

*Production Network* 

Terms of Use for direct signing [available here](https://corda.network/participation/terms-of-use.html) 

**1.2 Sponsored Model**

Business Network Operators acting as Sponsors need to ensure their participants have signed the Terms of Use before they can receive a participation certificate. If BNOs prefer to organise acceptance themselves, then they must forward appropriate documentary evidence for each participant (either a signed hard copy with wet signature or a scan of such hard copy). You must specify the precise Distinguished Names in order to confirm that the correct entity has signed and an accurate certificate can be issued. They must also sign a Sponsored Terms of Use Agreement (available both for Pre-Production and Production), which can be requested through an r3 representative, or via cordanetwork@r3.com.

**Step 2: Pre-approval of CSR information**
-------------------------------------------

To expedite your certificate signing request (CSR) to join CN, please follow these steps in order. 
Steps i-iv are pre-approval steps, to ensure when the CSR is submitted (below, in Step 6), all values are populated correctly.
 
i.	The node operator fills out fields in bold in the table below, for every node to be onboarded (you may submit as many nodes as you like). Send this email of nodes to cordanetwork@r3.com. Useful tip: If you reply from the ‘node operator email address’ (listed below), you’ll also have completed step 3.
ii.	CNF performs legal identity and sanctions checks on Organisation field (O) for each node. For guidance on which legal entity name to pick for your node, see [here](https://corda.network/participation/legalentity.html).
iii.	CNF needs to verify the person submitting this CSR has access to the associated email inbox and will do so by sending an email to the ‘node operator email address’ and waiting for a confirmation reply.
iv.	The network operator will give the all clear to node operator to submit their CSR.
 
*Before you begin...*
* If you are setting up a notary, there are additional considerations you need to keep in mind, please see the guidance you have received for setting up a notary.
* Fields in orange are optional, except for State (S), which is required only for legal entities registered in the USA. 
* The email address used below should be an actively monitored mailbox. We will use this email address for all communications with the node, including those involved in identity verification. We recommend this is an ‘admin@’ or ‘info@’ generic email associated with the legal entity, to avoid key man risk.
* The combination of O and OU are checked for uniqueness. If a CSR is submitted (or a certificate exists) with these two fields already in Corda Network, it will be rejected.
* If you are unsure of how to populate any fields, please see the guidance at the end of the email or reply to this email with your specific questions.

 Node 1 
 
| Node Operator email address |   |
|-----------------------------|---|
| **Organisation (O)**        |   |
| **City (L)**                |   |
| **Country (C)**             |   |
| State (US / Canada only)    |   |
| Organisation Unit (OU)      |   |
| Common Name (CN)            |   |
 
 
**Step 3: Trust Root** 
----------------------

Please put the trust root file for the correct environment in your certificates folder.

[Pre-production](assets/trustroots/preproduction/network-root-truststore.jks)
[Production](assets/trustroots/production/network-root-truststore.jks)


**Step 4: [Deploy the node](https://docs.corda.net/deploying-a-node.html)**
---------------------------------------------------------------------------

Where applicable, with help from a Corda representative.  

**Step 5: [Configure the node](https://docs.corda.net/corda-configuration-file.html)**
---------------------------------------------------------------------------

A node.conf file must be included in the root directory of every Corda node.

**Step 5.1: Specifying URLs For Initial Registration**


<span style="color:red"> **!!!WARNING!!!** </span> 

Please note if you are joining a SSZ, you need to request your unique **networkMapURL** from uatdoorman@r3.com for pre-production or doorman@r3.com for the production network. The below networkmapurls are for the public zones, so if you start up your node and connect with this url, you will join the public zone. This is a problem that can easily be corrected if you do it accidentally, but your node's identity will appear on the network map for a period of time, and if you want to keep your node's identity 100% private, you need to take care not to accidentally join a public zone.


*Pre-Production Network*

```
networkServices {
    doormanURL="https://doorman.uat.corda.network/3FCF6CEB-20BD-4B4F-9C72-1EFE7689D85B"
    networkMapURL="https://uat-sub1-netmap-01.uat.corda.network/SUB1CEP8-32UX-6ZXK-9C82-1FLR6268D75Z"    
}
devMode = false
tlsCertCrlDistPoint : "http://crl.uat.corda.network/nodetls.crl"
tlsCertCrlIssuer : "CN=Corda TLS CRL Authority,OU=Corda UAT,O=R3 HoldCo LLC,L=New York,C=US"
```

*Production Network*

The settings below must be added to the node.conf at the end of the file:

```
networkServices {
doormanURL = "https://doorman.corda.network/ED5D077E-F970-428B-8091-F7FCBDA06F8C"
networkMapURL = "https://prod-sub0-netmap-01.corda.network/SUB0CHKQ-8GCO-HS3S-KLZC-BINKKAGIMDRS"
}
tlsCertCrlDistPoint : "http://crl.corda.network/nodetls.crl"
tlsCertCrlIssuer : "CN=Corda TLS CRL Authority,OU=Corda Network,O=R3 HoldCo LLC,L=New York,C=US"
```

**Step 6: Run the initial registration** 
----------------------------------------

Once the node.conf file is configured, the following should be typed to the command line:

```
java -jar corda.jar --initial-registration
``` 

This will send a Certificate Signing Request (with the relevant name and email) to the Identity Service.

A message similar to the below will be printed to the console:

```
Legal Name: O=ABC LIMITED, L=New York, C=US
Email: john.smith@abc.com

Public Key: EC Public Key
            X: d14bc17e650f2a317cbcb95e554f1e26808ca80f67ab804bbc911ec16673abbd
            Y: 1978b02a8e693ecd534ceef835091c376cfc4e506decc69b91a872fc13ad1aeb

-----BEGIN CERTIFICATE REQUEST-----
MIIBLTCBywIBADBMMQswCQYDVQQGEwJVUzERMA8GA1UEBwwITmV3IFlvcmsxFjAU
BgNVBAoMDVIzIEhvbGRDbyBMTEMxEjAQBgNVBAsMCUM4MTUyOTE2NzBZMBMGByqG
SM49AgEGCCqGSM49AwEHA0IABNFLwX5lDyoxfLy5XlVPHiaAjKgPZ6uAS7yRHsFm
c6u9GXiwKo5pPs1TTO74NQkcN2z8TlBt7Mabkahy/BOtGuugHTAbBgkqhkiG9w0B
CQExDgwMYWRtaW5AcjMuY29tMBQGCCqGSM49BAMCBggqhkjOPQMBBwNHADBEAiBA
KLF4NLrleNZPKMoxBrr/80fE3kVbFnYtkB2h0JhX1gIgPcV0X0xZQug+njKCyKgf
DkNUdQJPqhkBBEpgVqyZmE8=
-----END CERTIFICATE REQUEST-----
Submitting certificate signing request to Corda certificate signing server.
Successfully submitted request to Corda certificate signing server, request ID: 6CBB63558B4B2D9C94F8C14AB713432F60AF692EB30F2E12E628B089C517F3CF.
Start polling server for certificate signing approval.
```

Important: the Request ID given in the above should be noted and kept safe for future reference. 


**Step 7: Confirmation**
------------------------

Once approved, a signed node CA certificate will be released by the Operator to the node. A node in polling mode will automatically download and install the certificate in its local trust store. It will also automatically generate additional identity and TLS certificates from the node CA certificate, which are required for subsequent operation of the node.

At this point, the node will terminate and will need to be restarted. Type “java -jar " into the command line. Once restarted, the node will then proceed to download the network map and discover other nodes within Corda Network. By the end of this process, joiners will be a participant in Corda Network and Corda Network Foundation.

Confirming your implementation - Installation and configuration of your Corda applications must be undertaken by the node operator. Instructions to install CorDapps can be found on https://docs.corda.net. Specifics on application usage or installation should be available from your CorDapp provider.

Business Network Operators should co-ordinate any post-install tests that may involve a small number of low value transactions on the business network to assure themselves of the correct setup of their node. Node operators should co-ordinate with their Business Network Operator in this regard. All node-initiated activity on the network from the point of connection is the responsibility of the node operator.

Participation fee 
------------------

Billing details will be gathered, for a participation fee invoice, during this process. This will depend on if they are part of the **indirect** or **direct model**.

For further questions on this process, please [contact us](../about/contact.html) - preferably on the [mailing list](https://groups.io/g/corda-network).
