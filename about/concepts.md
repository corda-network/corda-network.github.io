Key services 
============

Identity Issuance Service
-------------------------
The Identity Service admits new participants onto Corda Network. The service receives certificate signing requests (CSRs) from prospective network participants (sometimes via a business network operator) and reviews the 
information submitted. A digitally signed participation certificate is returned if:

* The participant meets the requirements specified in the bylaws and policies of the foundation (broadly speaking, limited to 
sanction screening only);
* The participant agrees to Corda Network participant terms of use.

The Corda Network node can then use the participation certificate to register itself with the Network Map Service.


Network Map Service
------------------- 
The Network Map Service accepts digitally signed documents describing network routing and identifying information from 
nodes, based on the participation certificates signed by the Identity Service, and makes this information available to all 
Corda Network nodes.


Notary Service
--------------
Corda design separates correctness consensus from uniqueness consensus, and the latter is provided by one or more Notary 
Services. The Notary will digitally sign a transaction presented to it, provided no transaction referring to 
any of the same inputs has been previously signed by the Notary, and the transaction timestamp is within bounds. 

Business network operators and network participants may choose to enter into legal agreements which rely on the presence 
of such digital signatures when determining whether a transaction to which they are party, or upon the details of which they 
otherwise rely, is to be treated as 'confirmed' in accordance with the terms of the underlying agreement. 


Support Service 
---------------
The Support Service is provided to participants and business network operators to manage and resolve inquiries and incidents 
relating to the Identity Service, Network Map Service and Notary Services.

If you have questions about any of the above, and can't find your answer on this site, [contact us](../about/contact.html)!
