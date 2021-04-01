Corda design separates correctness consensus from uniqueness consensus, and the latter is provided by one or more Notaries. The Notary will digitally sign a transaction presented to it, provided no transaction referring to any of the same inputs has been previously signed by the Notary, and the transaction timestamp is within bounds.

Business network operators and network participants may choose to enter into legal agreements which rely on the presence of such digital signatures when determining whether a transaction to which they are party, or upon the details of which they otherwise rely, is to be treated as ‘confirmed’ in accordance with the terms of the underlying agreement. 

Participants may also operate their own notary, but only (for now) within a Segregated Network.
