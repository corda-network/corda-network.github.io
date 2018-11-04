The Corda Network Foundation
==============================

Dispute Resolution
==================

1 Introduction
==============
Disputes between participants on the Corda Network shall be resolved in a hierarchical fashion, moving from the most 
cost- and time-effective through to the most expensive.

1. **Negotiation** – when a contract falls into dispute, or issues are observed with the unexpected behaviour of 
counterparties, the parties involved shall use negotiation as the implicit first step. 
For technical operational issues, Corda node operators may contact the operations team at a counterparty using the 
contact information in the NodeInfo file. This may be a team contact and not an individual one, and the counterparty 
may need to be obliged to monitor their contact point, for example the email address provided.
    1. For Corda data issues and contract constraint logic issues without an application provider: They shall discuss the terms 
of the agreement and attempt to understand what has caused the dispute and how it can be resolved to the satisfaction of 
both parties. 
    2.  For Corda application issues where the application is provided by a vendor: The counterparties to the trade shall engage 
the vendor, and the vendor support team would be expected to have a reference data database which they maintain with 
contact information for both sides. 
2. **Mediation** – on failure to reach a satisfactory agreement through negotiation, the parties may choose to mediate their 
dispute, or their agreement may specify that. Mediation is similar to negotiation but involves an independent third 
party, a mediator, to facilitate the process and assist the parties in reaching an agreement. The mediator does not 
make a decision and typically, agreements reached through mediation are not legally binding.
For Corda application issues where the application is provided by a vendor, or through a business network operator: The 
vendor or operator would be expected to provide a mediation process.
3. **Courts** – the courts of law are the ultimate recourse for dispute resolution but the courts and the laws to be used 
will vary depending on where a case is brought. Needless to say, a decision reached in a court of law is legally 
binding, although can be challenged in the appeal courts.

An additional step of Arbitration may be provided in due course, between steps 2 (Mediation) and 3 (Courts). When 
negotiation fails or the agreement specifies, parties may go to arbitration, involving an independent, decision-making 
third party, an arbitrator or arbitration panel. To make arbitration effective, it requires the arbitrator to be 
knowledgeable in the field in which the dispute is raised. The arbitrator reviews the evidence in the dispute, applies 
the applicable rules and law, and renders a decision that is legally binding on both sides and enforceable in the courts 
of law. 

2 Rationale
===========
Most agreements today, including common Master agreements, have clauses stating the dispute resolution approach to be 
used in the event of conflict. There is a split between those that use arbitration and those that use the courts of law 
(although Schedules to those Master agreements could override the default approach), but in both cases it does not 
specify that the arbitrators / judges should be specialists in the field.
We believe that to enable swift resolution of disputes arising from the use of distributed ledgers and smart contracts 
in some deployments of DLT a tailored dispute resolution approach would be beneficial.

2.1 Why is dispute resolution required?
---------------------------------------
In order to deliver certainty in contracts, we need to cater for the edge case of disputes. Although distributed ledger 
technology promises to increase reliability of transactions and reduce the frequency of disputes, those that remain may 
be bigger and more complicated. Furthermore, confidence in DLT and smart contracts is strongly dependent on knowing that 
someone is protecting the capital and the principles of business. Dispute Resolution provides the ability to formally 
resolve a contract that has fallen into dispute, and can be made up of several components including state-operated 
courts, arbitration, mediation and various ad hoc methods.

The DAO attack and the ensuing fallout around culpability re-confirms our belief of the need for a clear, agreed 
dispute resolution process - part of the challenge with resolving the impact from The DAO attack is the absence of a 
contractually agreed dispute resolution process which could opine on whether the attack was a criminal act, or just an 
unforeseen use of the code. An agreed dispute resolution process may have provided a more efficient channel through 
which those who have had Ether taken can initiate discussions to get their assets returned.

2.2 How can disputes arise?
---------------------------
All agreements are subject to conflict and smart agreements (contracts) are no exception. For the purposes of this 
policy the scope of dispute resolution is limited to disputes relating to, or arising from, the use of the Network and 
applications running on top of it. This would imply that disputes arising before the smart contract has been implemented 
on the Network would also fall under the jurisdiction of the dispute resolution process. We should consider that 
disputes may arise for a variety of reasons, including:

* Contract code can fail to perform – this is possible where there are defects in the code (that haven’t been identified 
by either party or vendor prior to implementation) resulting in errors.
* Inputs to the contract can be incorrect – the details of a trade can be incorrectly entered into the system 
(e.g. 'fat finger error') even if the code itself functions as agreed.
* Contract code can perform differently to expectations – code will always perform as it is programmed to, so this is 
more about the parties to the contract not understanding how the code will function.
* Contract code can be exploited - an actor (not necessarily a party to the agreement) can exploit aspects of the code 
to achieve unintended results. Once again, The DAO attack is a good example of this, where a third party exploited a 
code 'feature' for their own benefit.
* Performance can fail to meet the agreement – operational failures with the underlying system may result in the 
contract code being unable to perform as required.
* Contract code can perform at odds with the legal prose agreement – if sections of the contract are duplicated 
incorrectly in the legal prose and the contract code, and there is no clear precedence of prose or code, the parties 
may fall into dispute over which should represent the legal contract.
* Parties are unable to agree the contract code implementation to represent the agreement – even before the smart contract 
is deployed, disputes may arise in how the contract code should be written.

Disputes will also arise from relatively frequent events. For example, within collateral management disputes about the 
amount of collateral to be posted are commonplace (typically due to the difference in valuation models). While the 
introduction of CorDapps may minimise these disputes, a dispute resolution approach could be used for these more 
'everyday' conflicts. 

With all the potential errors, disputes will typically arise where one party (to the contract) stands to gain from the 
error and one stands to lose. However, disputes can also arise where one party is perceived to gain and the other 
perceived to lose – i.e. one party may believe that there is an error that is causing them to lose. Conversely, just 
because an error is identified, it does not necessarily mean that the contract will fall into dispute - the parties may 
agree to amicably resolve the error. However, the ability to ‘unwind’ a smart contract (as discussed later in this 
section) may still be required.

To a certain extent, we can ignore the causes of conflict and simply assert that conflicts will exist. This is to admit 
that even as we reduce ambiguity in agreements represented in smart contracts code, we can only reduce the number of 
conflicts, not eliminate them entirely. There will be complicated CorDapps and both parties may miss errors during the 
implementation of the code. Furthermore, it is plausible that a poorly designed or implemented mechanism may make for an 
increased number, and severity, of conflicts.

As such, the most important aspect is that the legal agreements should state clearly what the dispute resolution process 
is, i.e. what the jurisdiction will be for resolution of conflict. This may be in the User Agreement, or in one of the 
lower level trading agreements. This may become difficult to manage where a trade spans multiple CorDapps which may have 
different User Agreements and potentially different dispute resolution processes - the potential for discrepancy will 
need to be carefully assessed as inter-operating ledgers are implemented.

3 What options exist for dispute resolution?
============================================
With any contract, relying on litigation (e.g. courts of law) to resolve a dispute is typically a costly and 
time-consuming exercise for both parties to the contract. Therefore, having an agreed dispute resolution process in 
place for CorDapps, which does not involve immediate hand-off to litigation, could provide benefits by eliminating 
inefficient use of time and money.

While there are multiple methods of dispute resolution we have focused on the four of the most common which should be 
used a means of resolving disputes in a hierarchical fashion, moving from the (typically) most cost and time effective 
through to the most expensive.

When establishing a dispute resolution forum we will need to be aware of existing dispute resolution processes that 
either we a) can leverage or b) have to work with. For example, for Credit Default Swaps operating under ISDA rules, an 
agreement between two parties would need to state that dispute resolution is conducted via the ISDA Credit Derivatives 
Determination Committee. Using the hierarchy of agreements, a User Agreement may state that a newly-formed process is 
the primary dispute resolution process, but the relevant Master Agreement would override this and refer to the 
Determinations Committee. It may be possible for those existing forums to be adapted to include smart contract disputes 
into their scope – this would be a potentially simpler way of ‘launching’ a new dispute resolution process.

As mentioned above, negotiation, in one form or another, is always likely to occur between parties and should be 
considered as the first step. Given the non-legally binding nature of any decision from mediation, we believe this 
would not be palatable to the market participants as it leaves the option for challenging, or ignoring any decisions 
reached. We believe that, in some deployments of CorDapps in financial services, arbitration may a practical option. 
Appealing to the courts of law will always be available to parties if they wish to challenge the decision of an 
arbitrator, but, given the legal standing of arbitration, it is likely that the courts would respect the decision 
reached through that method.

In most countries a decision by an arbitrator is legally binding, therefore the main comparison we can make to other 
forms of dispute resolution is the benefits of using arbitration before resorting to the courts. We see four primary 
potential benefits to be considered:

Given that CorDapps will operate on a distributed, international network of nodes spanning different countries and 
jurisdictions it will be beneficial to have one body (i.e. one jurisdiction) that makes rulings on any dispute on the 
ledger. Many countries have an Arbitration Act aligned to the United Nations (UNCITRAL) Model Law on International 
Commercial Arbitration. In addition, it is our understanding that under the 1958 New York convention, a decision reached 
via arbitration in any signatory country is generally recognised as legally binding in all other signatory countries and 
virtually all significant commercial countries are signatories to the act.

Arbitration allows the participants choice in the selection of the arbitrator(s), which can be particularly beneficial 
in cases where a high degree of specialist knowledge is required. In the legal system, a judge may not have any 
knowledge of the domain and would rely on the testimony of expert witnesses. Expert witnesses are chosen by one or 
other party to support their argument and therefore the courts do not necessarily receive a completely unbiased view of 
the case. Expert arbitrators can have a full understanding of the issue and make an informed decision without being 
unduly influenced by either side. This will be particularly beneficial in cases where there is dispute over the contract 
code which will likely require specific technical knowledge.

The rules and procedures of the Arbitration forum can be designed specifically to function in line with the special 
nature of the disputes. For example, the rules could state "Any records signed by a Corda identity are acceptable 
evidence", thus bypassing any discussions about the legal standing of digital signatures. Similarly, the rules could 
specify: the time limits for dispute resolution; a single language to be used; how an arbitrator is chosen (e.g. from 
an independent bank from an independent country).

Arbitration is typically faster, and therefore cheaper, than resolving disputes through the courts. However, there are 
also challenges with implementing arbitration as the dispute resolution approach for distributed ledgers:

1. Certain industries may not be willing to accept arbitration – historically arbitration has been relatively unused 
within finance and has some negative connotations. However, we anticipate that firms will recognise the benefits of 
having expert arbitrators presiding over disputes for smart contracts. Additionally, there is increased acceptance and 
usage of arbitration within banking and finance in exactly the domains where we expect Corda to be implemented. For 
example, the ISDA Master Agreement and BAFT Master Participation Agreements now provides model clauses which can be used 
in the User Agreements between parties to specify the arbitration rules, seat and governing law for arbitration. And 
FMIs such as SWIFT, LCH and CME also make provisions for arbitration within their Terms and Conditions.
2. The requirement for expert arbitrators – while the benefits of expert arbitrators are very clear, actually finding 
the right candidates to be arbitrators will be challenging. Depending on the scope of the arbitration panel, the 
arbitrators may require a very broad knowledge of business and of the technical aspects of distributed ledgers and 
contract code. To begin with there will be very few candidates meeting those requirements, and they are likely to have 
other priorities. There may be potential to use existing arbitrators to provide a head start to the process. For 
example, PRIME Finance (Panel of Recognised International Market Experts in Finance) is an organisation of finance 
experts available to act as arbitrators for a range of purposes, and recognised by ISDA.
3. Scalability of the arbitration process - given the immaturity of the technology and knowledge around smart contracts 
it is conceivable that there will be far more disputes that can be handled by the available arbitrators. If the 
arbitration process is seen to be ‘failing’ by not processing disputes quickly enough this will result in participants 
quickly losing confidence in its authority.
4. Scope of arbitration – the potential applications of Corda in business are broad ranging and it is inconceivable that 
any one arbitrator could have expert-level knowledge across all businesses. The scope of arbitration will need to be 
carefully managed, with a balance needing to be found between having many small or a few large forums. Many small 
forums enable each to be specialised in their field and not have to handle too many cases. Conversely, having a few 
large forums enables each to have visibility across a large range of cases which would help to drive consistency of 
decisions. There may also be further challenge where disputes span multiple applications, and potentially cross 
jurisdictional boundaries.

I anticipate that arbitration will grow from the mediation step, but it will require time to develop and a mature 
understanding of the types of application, which is why I propose to exclude it from the Policy for now. 
Regardless, the clear, unambiguous documentation of the dispute resolution process (and its boundaries) in the 
agreements is critical to its success.