# Joining Corda Network

A summary of steps to join the Network (either the Pre-Production or Production network) is listed below. More details are given on each of these steps, further down this page. This assumes that participants wish to operate a node and already have access to at least one CorDapp which they wish to deploy, as well as other considerations listed.

## Step 1: Terms of Use Agreement

### 1.1 Direct Model

#### Pre-Production Network

The Terms of Use for direct signing are available through contacting info@corda.network. Shortly, this will be available as a click-through.

#### Production Network

The Terms of Use for direct signing are available [here](https://github.com/corda-network/corda-network.github.io/blob/Update-Participant-Terms-of-Use-(Jul-2020)/assets/Corda%20Network%20-%20Participant%20Terms%20of%20Use%20-%20Direct%20-%2007-17-20.pdf). Shortly, this will be available as a click-through.

### 1.2 Intergroup Sponsor Model

An entity looking to onboard multiple entities within the same Group or parent company to the Corda Network may choose to sign a Intergroup Sponsor Participant Terms of Use with Corda Network Foundation. They must ensure the appropriate legal entity name is specified in the Distinguished Name of all its participants. The Sponsoring entity is responsible to communicate with Corda Network Foundation for registering, specifying the precise Distingished Names, submitting Certificate Signing Requests and handling customer support and billing for itself and other participating entities. They must also sign a Intergroup Sponsor Participant Terms of Use Agreement (available both for Pre-Production and Production), which can be requested through an r3 representative, or via info@corda.network. The Terms of Use to join Production are available [here](https://github.com/corda-network/corda-network.github.io/blob/Update-Participant-Terms-of-Use-(Jul-2020)/assets/Corda%20Network%20-%20Participant%20Terms%20of%20Use%20-%20Intergroup%20Sponsor%20-%2007-17-20.pdf).

## Step 2: Pre-approval of CSR information

To expedite your certificate signing request (CSR) to join Corda Network, please follow these steps in order.
Steps i-iv are pre-approval steps, to ensure when the CSR is submitted (below, in Step 6), all values are populated correctly.

i. The node operator fills out fields in bold in the table below, for every node to be onboarded (you may submit as many nodes as you like). Send this email of nodes to info@corda.network.

"O" - Organisation should usually be the same Legal Entity as what you have filled out in your Terms of Use (Step 1), which is also the owner of the assets being used on Corda Network. For guidance on which legal entity name to pick for your node, see [here](/participation/legalentity).

| Required x500 fields        | Value |
| --------------------------- | ----: |
| **Organisation (O)**        |     - |
| **City (L)**                |     - |
| **Country (C)**             |     - |
| **Organisation Unit (OU)**  |     - |
| State (US / Canada only)    |     - |
| Common Name (CN)            |     - |
| Node Operator email address |     - |


ii. CNF performs legal identity and sanctions checks on Organisation field (O) for each node.

iii. CNF needs to verify the person submitting this CSR has access to the associated email inbox and will do so by sending an email to the ‘node operator email address’ and waiting for a confirmation reply.

iv. The network operator will give the all clear to node operator to submit their CSR.

### Before you begin...

- Fields in non-bold are optional, except for State (S), which is required only for legal entities registered in the USA.

- The email address used below should be an actively monitored mailbox. We will use this email address for all communications with the node, including those involved in identity verification. We recommend this is an ‘admin@’ or ‘info@’ generic email associated with the legal entity, to avoid key man risk.

- If you are unsure of how to populate any fields, please see the guidance at the end of the email or reply to this email with your specific questions.

- If you are setting up a notary, there are additional considerations you need to keep in mind, please see the guidance you have received for setting up a notary.

## Step 3: Trust Root

Please put the trust root file for the correct environment in your certificates folder.

[Pre-production Network](https://github.com/corda-network/corda-network.github.io/blob/master/assets/trustroots/preproduction/network-root-truststore.jks)

[Production Network](https://github.com/corda-network/corda-network.github.io/blob/master/assets/trustroots/production/network-root-truststore.jks)

## Step 4: Deploy the node

Follow these instructions to [deploy the node](https://docs.corda.net/deploying-a-node.html). Where applicable, with help from a Corda representative.

## Step 5: Configure the node

Follow these instructions to [configure your node](https://docs.corda.net/corda-configuration-file.html). A node.conf file must be included in the root directory of every Corda node.

Use default passwords on the node configuration file to unlock the Trust Store file and Keystore file containing the Corda Network root certificate. This is a non-secret value required for your initial registration. 
trustStorePassword: trustpass

**Step 5.1: Specifying URLs For Initial Registration**

The below networkmapurls are for the Corda Network mainnet, so if you start up your node and connect with this url, you will join the mainnet. 

N.B.: If you are joining a **Segregated Network**, you need to request it according to the instructions on [this page](/participation/network-choice). To deploy your Segregated Network you will need to use your *unique* and *private* networkMapURL (for pre-production and/or production network). If you join the mainnet by accident, this is a problem that can easily be corrected, but your node's identity will appear on the network map for a period of time.

### Pre-Production Network

```
networkServices {
    doormanURL="https://doorman.uat.corda.network/3FCF6CEB-20BD-4B4F-9C72-1EFE7689D85B"
    networkMapURL="https://uat-sub1-netmap-01.uat.corda.network/SUB1CEP8-32UX-6ZXK-9C82-1FLR6268D75Z"
}
devMode = false
tlsCertCrlDistPoint : "http://crl.uat.corda.network/nodetls.crl"
tlsCertCrlIssuer : "CN=Corda TLS CRL Authority,OU=Corda UAT,O=R3 HoldCo LLC,L=New York,C=US"
```

### Production Network

The settings below must be added to the node.conf at the end of the file:

```
networkServices {
doormanURL = "https://doorman.corda.network/ED5D077E-F970-428B-8091-F7FCBDA06F8C"
networkMapURL = "https://prod-sub0-netmap-01.corda.network/SUB0CHKQ-8GCO-HS3S-KLZC-BINKKAGIMDRS"
}
tlsCertCrlDistPoint : "http://crl.corda.network/nodetls.crl"
tlsCertCrlIssuer : "CN=Corda TLS CRL Authority,OU=Corda Network,O=R3 HoldCo LLC,L=New York,C=US"
```

## Step 6: Run the initial registration

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

## Step 7: Confirmation

**Step 7.1: Certificate Released and Node Restart**

Once approved, a signed node CA certificate will be released by the Operator to the node. A node in polling mode will automatically download and install the certificate in its local trust store. It will also automatically generate additional identity and TLS certificates from the node CA certificate, which are required for subsequent operation of the node.

At this point, the node will terminate and will need to be restarted. Type “java -jar " into the command line. Once restarted, the node will then proceed to download the network map and discover other nodes within Corda Network. By the end of this process, joiners will be a participant in Corda Network and Corda Network Foundation.

Confirming your implementation - Installation and configuration of your Corda applications must be undertaken by the node operator. Instructions to install CorDapps can be found on https://docs.corda.net. Specifics on application usage or installation should be available from your CorDapp provider.

Business Network Operators should co-ordinate any post-install tests that may involve a small number of low value transactions on the business network to assure themselves of the correct setup of their node. Node operators should co-ordinate with their Business Network Operator in this regard. All node-initiated activity on the network from the point of connection is the responsibility of the node operator.

**Step 7.2: Subscribe to StatusPage**

We currently communicate system maintenance schedule, disruptions and other important operational announcements related to the Corda Network services on our [Statuspage](https://cordanetwork.statuspage.io/#). Please ensure all individuals and/or groups responosible for technical operation of your network / node have subscribed to these updates so that they will be automatically sent to the relevant email addresses. 

Please also ensure that the relevant lists are being subscribed - each subscriber can choose which service(s) (notary, network map and identity operator) and enviornement(s) (Pre-production and Production) to subscribe to. **We strongly recommend that at least the node operator email address should subscribe to all services in your operating environment. You should also ensure you update your subscription list when you onboard to a new environment - such as ensuring you subscribe to all Production updates of as you onboarded to the Production environment).**

## Participation fee

Billing details will be gathered, for a participation fee invoice, during this process. This will depend on if they are part of the **Intergroup Sponsor** or **Direct model**.

For further questions on this process, please [contact us](/about/contact) - preferably on the [mailing list](https://groups.io/g/corda-network).
