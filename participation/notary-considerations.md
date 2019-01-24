|Corda Network Foundation|[Document history]({{ site.github.repository_url }}/blame/master/{{page.path}})|

Notary Considerations
=====================

A notary is a network service that provides uniqueness consensus by attesting that, for a given transaction, it has not already signed other transactions that consumes any of the proposed transaction’s input states.

When joining Corda Network, participants *will need to decide* whether:
* to use the Corda Network notary for their transactions, or 
* to set-up and run their own notary.

In deploying a CorDapp, currently the default option is to use the Corda Network notary. For all participants using this service, [transaction fees](https://corda.network/participation/membership-tiers.html) will be charged.

However, Corda Network participants also have the option to set up their own, third-party notary. Detailed instructions are listed, how to do set-up a 'third party notary' [here](https://docs.corda.r3.com/running-a-notary-cluster/toctree.html). In this case, transaction fees will not apply. It is worth noting that setting up a notary will be a complex process; for advice, feel free to email our public mailing lists, [corda-network](https://groups.io/g/corda-network) or [corda-dev](https://groups.io/g/corda-dev) - or (if applicable) your R3 representative.

For an introduction to what is a notary, in Corda, take a look at the video and explanations uploaded [here](https://docs.corda.net/key-concepts-notaries.html). 
