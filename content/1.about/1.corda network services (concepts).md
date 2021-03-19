# Corda Network Services 

Corda Network has it's own [Trust Root](/trust-root/index) -- the single, long-term cryptographic key which all the certificates on the Network root back to, and is the basis of trust in the provenance of data, recognised by  participants. For Corda Network, this is offline and secured in custody by the Corda Network Foundation.


## Identity Manager

The Identity Manager admits new participants onto Corda Network. The service receives certificate signing requests (CSRs) from prospective network participants (sometimes via a [Intergroup Sponsor](/participation/join-directly-or-as-sponsor)) and reviews the information submitted. 

A digitally signed participation certificate (based on the Corda Network Trust Root) is returned if:

* The participant meets the requirements specified in the bylaws and policies of the Foundation (broadly speaking, limited to 
sanction screening only);
* The participant agrees to Corda Network participant terms of use.

The Corda Network node can then use the participation certificate to register itself with the Network Map.


## Network Map

The Network Map accepts digitally signed documents describing network routing and identifying information from 
nodes, based on the participation certificates signed by the Identity Manager, and makes this information available to all 
Corda Network nodes.


## Notary

Corda design separates correctness consensus from uniqueness consensus, and the latter is provided by one or more Notaries. The Notary will digitally sign a transaction presented to it, provided no transaction referring to 
any of the same inputs has been previously signed by the Notary, and the transaction timestamp is within bounds. 

Business network operators and network participants may choose to enter into legal agreements which rely on the presence 
of such digital signatures when determining whether a transaction to which they are party, or upon the details of which they 
otherwise rely, is to be treated as 'confirmed' in accordance with the terms of the underlying agreement. 


## Support 

Support is provided to participants and business network operators to manage and resolve inquiries and incidents 
relating to the Identity Manager, Network Map and Notary.

If you have questions about any of the above, and can't find your answer on this site, [contact us](/about/contact)!

`DISCLAIMER: ANY ENTITY OPERATING A BUSINESS NETWORK (“BUSINESS NETWORK OPERATOR”) ON THE CORDA NETWORK ACKNOWLEDGES AND AGREES THAT THE SERVICES PROVIDED BY THE FOUNDATION ARE PROVIDED TO CORDA NETWORK PARTICIPANTS SUBJECT TO THE TERMS AND CONDITIONS OF ANY AGREEMENT ENTERED INTO BETWEEN SUCH PARTICIPANTS AND THE FOUNDATION, AND ARE NOT PROVIDED TO OR ON BEHALF OF SUCH BUSINESS NETWORK OPERATOR. THE BUSINESS NETWORK OPERATOR FURTHER ACKNOWLEDGES AND AGREES THAT IN NO EVENT DOES THE FOUNDATION PROVIDE ANY REPRESENTATIONS OR WARRANTIES REGARDING THE SERVICES (INCLUDING BUT NOT LIMITED TO AVAILABILITY AND ACCURACY THEREOF) TO BUSINESS NETWORK OPERATOR AND THAT THE OPERATION OF A BUSINESS NETWORK ON THE CORDA NETWORK AND RELIANCE THEREON IS AT A BUSINESS NETWORK OPERATOR’S OWN RISK.`
