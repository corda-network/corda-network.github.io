# Minutes and Governance Events of Board Meetings

## Minutes

Minutes of previous meetings are available:

1. [2019/12/06 - December](/minutes/20191206).
2. [2020/02/13 - February](/minutes/20200213).
3. 2020/05/13 - May (see below).
4. 2020/06/19 - June (see below).

## Minutes - Transition Board Meeting 6, 13th May 2020

 

### 1. General updates

JC gave an overview of last 3 months; 1) Corda Network has 12 Business Networks live; 2) a new R3 internal project has started, to make network onboarding streamlined and scalable for larger numbers of customers; and 3) team secured Directors and Officer’s Insurance for 2020, for all the Foundation Directors going forward (whilst lowering last year’s price)

 

### 2. Upcoming election – CNF Board 

CQ explained that 14 applications were received for 9 seats, so will need to have a vote on 30th June. Since only 8 of the 14 applicants have live nodes - there may be drop-outs, if 6 of the applying legal entities aren’t live by deadline of 23rd June.

 

Next steps (BC/CQ): Director applications to be circulated to all current Board members, via secure filesharing. Team to finalise voting software, upload applications and communicate process to all eligible voters in the Participant Community, in 1-2 weeks

 

### 3. Proposal around multiple Doormen certs

R3’s Office of the CTO, led by Richard Brown, has developed research report showing its technically possible to issue additional doormen certs off the Trust Root used by the Foundation currently. In its current format, the Foundation would have no, or very limited ability, to revoke the certificate.

 

The Foundation approved an investigation into both 

1) testing this ‘potential offering’ with existing / potential customers 

2) conducting legal analysis (with external counsel) to see what the risks and scope of this are, with an option to vote on this change formally, at our next meeting – aiming to have a final meeting in mid-June (depends on analysis being ready). 

 

AV raised whether there could be a conflict of interest if the new Board Directors might have a vested interest in this happening. However, its noted that only 1/14 Board applications received has been from a candidate who may be interested in this (SDX). In addition, the Board will have an opportunity to vote at a meeting in June on this topic.

 

AI raised whether we could be careful around offering clients a Doormen cert without the Foundation’s ability to revoke This is not something typical in PKI and we should be do detailed research if this is a sound idea. An ideal alternative would be for the Foundation still have the right to revoke the Doorman cert, but only in extremely rare and clearly well-defined circumstances (for legal to help us define). Action: CQ to set up Board meeting in mid-June 

 

### 4. Financials 

AS asked for an overview of cost / revenue projections and if we are on track. CQ to send out in next few days via secure filesharing

 

### 5. Liability

For legals, the Foundation now has a new change control process. All amendments to Corda Network legal agreements are now reviewed by external counsel / whether they are material / immaterial and if material, to escalate to the Foundation Board for approval. This process may not be scalable in the long run, but works currently.

**Escalation Event 1** - 3 requests from customer wishing to join the network on materially changing our standard liability clauses. On each request, the Board asked for additional information from external counsel – otherwise they will take a cautious approach and vote against.

 

### Actions

1. BC to issue all applications to Board by secure file-sharing, this week

2. Team to communicate voting process in next 1 week to Board; to members shortly thereafter

3. CQ/BC to set up Board meeting in mid-June

4. CQ to send financial pack around by secure file-sharing

5. CQ to liaise with external counsel for further info around the three liability clauses, and send to Board, before making a collective final decision on liability

  
## Minutes - Transition Board Meeting 7, 19th June 2020

### Attendance

Andrei Ilchenko - ING

Miyashyita Masayuki - SMBC

Yong Xia - HSBC

Alessandro Spadoni  - B3i

James Carlyle -  R3 

Carolyne Quinn -  R3

Blanche Crowe – R3 (Board Secretary)

**Apologies**

Alain Verschueren – BNP Paribas

Greg Crow - AXA XL

Chris Madsen - Aegon

**Absent**

Andrew Speers - Commonwealth Bank

Jordane Rollin – Standard Chartered

### Minutes 

1.	CQ mentions the antitrust guidelines.

2.	CQ asks the board for feedback on issues that they have found difficult to get through the legal team and onto the network.  Does the current onboarding model need tweaking?

3.	AV (sent apologies) emailed his legal team’s feedback. Liability was the main issue for his bank.  If a node on the network causes damage to some part of the network or to another participant. He has asked for a mutual cap (200% on the fees paid) on liability to be made. An example of harm being caused could be spamming another participant or causing the notary to stop working.   The legal team agree that the owner is responsible for their node’s actions if the circumstances are clearly defined.

4.	YX has spoken to his project team, and there have been no blockers.  They understand the process takes time.   JC adds it is important to recognise the difference between business as usual process and blockage.

5.	CQ suggests having a subcommittee, to review legal changes every month. AI and AS would like to nominate their legal counsel to review.  JC adds that the board would still need to ultimately decide on any changes made. 

6.	AI's outstanding concerns are on the service legal agreement.  On clause 3.6, they want a baseline agreed in the terms of use.  On clause 6.2 (monitoring an audit) they want an addition to that clause, providing reasonable grounds for data collection. On clause 11 (limitation of liability) they want to steer clear of being accountable for indirect loss.  Lastly, they want the participate to have the right to terminate agreement, under certain conditions. 

7.	CQ responds that the liability concerns would need to be discussed in more detail with external council.  Other concerns are not material changes but we would need to change our standard agreement going forward. 

8.	MM is concerned the documentation process is time consuming.  Could CNF reduce the need to sign multiple contacts with many parties. 

9.	JC agrees there needs to be improvements to the process.  Simple contracts with a small number of counterparties for a large organisation is important.  We do not want to rule out the possibility of direct contracts with the foundation if someone wants to.   Structure needs to be easy to explain and legally aligned. 

10.	MM wants to know if the CNF has the resources to go through all contracts.  CQ replies that they do not. 

11.	AI adds that being able to deal with CNF directly is appealing.  AS agrees helping to remove barriers in adoption, is core to our strategy.

12.	JC adds if we can think of CNF as a governance and standard setting organisation, which has control.  It is not set up to act contractually and negotiate contracts.  AS agrees. 

13.	CQ says that everyone would have received an email from Clifford Chance (our external counsel).  Within Dutch law, if any changes to Articles of Association and By-Laws are being made, we need remote attestation.   This involves a 10min video call done by Clifford Chance where you need to sign a draft resolution, which is to approve the changes already approved by email. 

14.	CQ explains there are 4/14 candidates running for election for the 9 board seats, who may not have a live node by 23rd June 2020.   We would like to vote on lifting this deadline.  This will only apply in this board election and not in future elections. CQ wanted to vote today on the criterion for Candidate Directors on the new Board needing to have a live node on the network – but the Board requires 8 for a quorum, while there are only 6 in attendance. JC suggests we take the vote offline, explaining the reason for the vote in detail, in an email. 


15.	AI mentions this is the last board meeting with this board.  JC thanks the board for their contribution for the last 15 months.   


### Actions

1.	CQ & JC to set up a monthly process of gathering feedback on legal documentation.  Working with external council and then publish an updated standard.
2.	CQ to contact Clifford Chance regarding email to YX. Name needs to be changed. 
3.	CQ to email the board on voting to lift the rule on all election candidates needing to have a live node by 23rd June 2020. 
 

## Governance Events

Details of the following governance events, with their voting status, are available:

1. [Advisory event 0001](/minutes/event-0001): Converge the UAT Network Governance.
2. [Mandatory event 0003](/minutes/event-0003): Revised participation pricing.
2. [Mandatory event 0004](/minutes/event-0004): Change X500 name length.
2. [Mandatory event 0005](/minutes/event-0005): Guidance on joining fees.
2. [Mandatory event 0007](/minutes/event-0007): Approve Segregated Sub-Zone Pricing.
3. [Mandatory event 0008](/minutes/event-0008): Approve 2019 Budget and 2020 Plan.
4. [Mandatory event 0009](/minutes/event-0009): Defer first open Director vote.

For more information about the intended governance of the network, please refer to the [Corda Network Foundation : 
Governance Guidelines](/governance/governance-guidelines) document.
