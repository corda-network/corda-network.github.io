# Preparing to Join

Before joining Corda Network, would-be Participants should:

* Be familiar with the objectives, policies and standards of the Corda Network as described on https://corda.network .

* Have conducted the appropriate project management and operational activities within their organisation to authorise the set up and operation of the Node for live business use and to to agree commercial terms and sign the Corda Network Terms of Use.

* Be familiar with Corda and key Corda concepts as described in the Corda documentation (https://docs.corda.net)

* Have agreed to license Corda under the appropriate licence (Corda, Corda Enterprise). 

* Have access to at least one CorDapp that they wish to deploy in Corda Network.

* Have a look at the Network's [Service Level Agreements](https://corda.network/service-levels/network-services-sla-production)

* Be able to supply a dedicated IP address for communications with their node - typical network configurations are described at Corda Firewall. 

## Pre-onboarding questionnaire

All on boarding projects MUST supply the below information before start date can be scheduled and certificates granted.

This information must be provided at least 8 weeks in advance of any go-live date, for the following reasons:

To allow time for:
* Customer review and completion of the Participant Terms of Use (PToU)
* Confirmation of which on-boarding model is being used (see below)
* Briefing on the relevant operations model
* Identification of support and operational contacts

If using the Corda Network notary, we must be able to ensure that capacity is added should the projected incremental load on the notary be out of the normal headroom we maintain

For Corda 3 environments, new projects will require a Network Parameter Update to implement their contract (zone) constraints. Production environment runs Network Parameter Updates on a pre-defined 2 monthly schedule - see here: https://corda.network/participation/networkparamsschedule

*The stipulations above do not apply to nodes on boarding to existing projects already live on the network.*

### On-boarding Information Required:

1. Is the client joining with a consortium of potential other participants, or a separate entity such as a bespoke network operator? If as part of a consortium...

2. Will the BNO be reselling Corda Network services to its participants?

3. Is the BNO hosting other participant nodes in the business network?

4. Is the BNO operating its own Corda node in the business network (signing its own transactions)?

6. What version of Corda would the BNO like to launch with (and use in UAT)? 
Incl: Corda Enterprise or Corda Open Source?

7. If a Corda 3.x version is being used, please supply zone constraints required in both UAT and Production environments (for details on this see here: https://docs.corda.net/head/api-contract-constraints.html). It is Corda Network policy for all projects to use zone constraints if using Corda 3 (link to CNF page to be added when created)

8. What plans do they have for Corda version upgrades during the first year of operations?

9. Will the BNO require any bespoke services outside of those delivered under the terms of the PToU? If so, what are they?

10. What 3rd parties are involved in day to day operations (such as regulators, oracles, 3P hosting providers, etc)?

11. How is the BNO intending to manage its own business network membership (entries and exits?)

12. How many participant nodes will be joining (estimate):
    * At launch
    * By the end of the first quarter 
    * By the end of the first year 

13. How many different legal entities will be joining (if different from nodes)
    * At launch
    * By the end of the first quarter 
    * By the end of the first year 

14. What notary will be used when issuing new assets onto the ledger?

15. What are the expected average and peak daily transaction volumes in the first three months?

16. Does the business network application (CorDapp) always explicitly select a defined and available notary for asset issuance?
