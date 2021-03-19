### 27 January 2021

**Update to Corda Network CRL** 


As of 8 February 2021 the Corda Network’s CRL will be served from an Azure CDN endpoint in order to continue to improve both resiliency and availability of Corda Network. Note that Corda Network’s CRL will only be available from the published CRL endpoint i.e. **crl.corda.network**

Please ensure that your Corda nodes are able to connect to Azure CDN endpoints or that connectivity to Azure CDN is not blocked by your Network Administrator by 8 February 2021.

1.  About Azure CDN:
  - Azure CDN endpoints are everywhere around the globe (Point of Presence/POP). It’s not a unique IP, rather a list of IPs.
  - Azure CDN uses the following FQDNs in order to retrieve the final destination IP (DNS A Record).
      - *.azureedge.net
      - *.trafficmanager.net
      - *.msedge.net
  - Ensure the destinations above are not blocked to access the CRL in the destination IP (DNS A Record)
  
2.  Your connection to CRL should not be disrupted if outbound connectivity to TCP port 80 in not blocked. Check that the node can reach the DNS “crl.corda.network“, or whitelist the DNS entry for “crl.corda.network” in your firewall.

3.  Ensure you have not IP whitelisted the current CRL endpoint (i.e. Doorman).
 

For more information please email info@corda.network.



### 18 August 2020

**Corda Network Statuspage is moving** 


As of 2 September 2020, all Corda Network infrastructure maintenance and incident related announcements will be communicated via a new password-protected site at https://corda-network.statuspage.io/. Current Statuspage at https://cordanetwork.statuspage.io/ will be decommissioned as part of this development. 

We are making these changes in order to deliver enhanced and more private communications around Corda Network infrastructure.

All participants on Corda Pre-Production and Production Networks will receive a prompt from Statuspage to their node operator email address, asking to complete registration and create log in details to access the portal and receive automatic updates.

Failure to complete registration means that you will no longer receive maintenance & incident-related updates.

Please contact info@corda.network by Friday 28 August 2020 if you wish to register any additional subscribers from your (or your sponsee’s) organisation to use the new Statuspage.

For more information please email info@corda.network.



### 6 July 2020

**Corda Network Foundation announces a new Board of Directors** 


The Participants of Corda Network have voted in a new board of directors for Corda Network Foundation, replacing the 15-month Transition Board which has been in place since March 2019. We are delighted to announce the nine directors who will steer the future of Corda Network:

- Nicholas Barnes, Manager, Marco Polo Business Network, TradeIX

- Richard Crook, Director, Cordite Society Limited 

- Robert Crozier, Chief Architect Customer Platforms & Head of Global Blockchain Centre of Competence, Allianz Technology

- Hans Huber, DLT Trade Finance Innovation Project Manager, Commerzbank

- Richard Phipps, Senior Project & Delivery Lead, Underwriting, Swiss Re

- Olivier Relandeau, DLT Product Manager, Standard Chartered Bank 

- Aaron Seabrook, Chief Operating Officer, Contour

- Alessandro Spadoni, Chief Architect & Platform Fluidity Product Owner, B3i

- Yong Xia, China Chief Architect, HSBC

The 9 new directors bring a wealth of expertise to help steer the next phase of Corda Network’s growth, as well as to drive the Network to enable seamless transactions between businesses across a wide and diverse network. They join James Carlyle and Carolyne Quinn who represent the Corda software developer R3.  

Current Chairman James Carlyle stated: “_I am extremely pleased to welcome the new directors to the board of the Corda Network Foundation. The number of business networks using Corda Network is growing, and new participants are joining those groups all the time, so the need for effective governance in order to uphold the Corda promise of interoperability across business applications is greater than ever. Governance of distributed ledger networks is new, and the board members will get a real chance to shape it for the entire industry.”_

These new directors replace the outgoing Transition Board. We are grateful for the significant contribution made by the Foundation's Transition Board who helped steer the Network from its inception.

**About Corda Network** 

Corda Network Foundation is a non-profit organisation that governs the Corda Network. Corda Network allows for the transfer of data and digital assets between communities of nodes (business networks) and different CorDapps. Participants can therefore create private ecosystems within their organisation, or with trusted commercial partners, while remaining interoperable with the wider Corda community where appropriate. Relevant information can be shared between applications and organisations  without the need for intermediaries, creating efficiencies and avoiding duplication. Corda Network also includes identity verification and privacy services to ensure that participants can operate on the network safely.

For more information please contact info@corda.network. 




### 22 April 2020
**The election for the new Corda Network Foundation Board is taking place on 30th June 2020**

Any legal entity who is live on the Production Network is eligible to vote for, or nominate an individual from their organization to stand for, the Board. Detailed rules below - from Section 3 of the Foundation's By-Laws.

For any questions, please contact info@corda.network.

Thank you!


**Application Process**

Individuals considering to stand for the Board should send a short application by 10th May 2020 - 7 weeks in advance of the vote. The vote is intended to take place on 30 June 2020 (further details to follow).
As detailed in Section 3.3.4 of the Foundation's By-Laws, the application should contain an updated CV, personal statement and short biography of the nominee
The list will be circulated to the Board and Participant Community by 17th May

**Eligibility**

A legal entity must have 1 node (Open Source / Enterprise) on the Production Network, by Tues 23 June 2020, to 1) vote for or 2) stand for, the Board
The legal entity is that found in the x500 cert. The node operator or Sponsor, if applicable, are not relevant.
All eligible legal entities get to vote for 3 Directors out of 9. If a legal entity has 2 nodes, it will have 2 opportunities to vote.
Any live legal entities may nominate up to 3 individuals for the Board, however in the end its likely only one will get through, according to the diversity criteria in the By-Laws (see Section 4).
If you are not live yet by the application deadline, you can still send in the application. However, the application will not be considered eligible until the node is live - on or before 23rd June.
Existing Foundation Transition Board directors are eligible to stand again.

**Staggered Board Design**

The 3 Directors with the most votes will get 3-year terms (July 2020 - July 2023)
The 3 Directors with the middle amount of votes will get 2-year terms (July 2020 - July 2022)
The 3 Directors with the lowest amount of votes will get 1-year terms (July 2020 - July 2021)
This is by design, to enable a staggered board. As such, from July 2021 onwards, on an annual basis, 3 directors' seats will become available on an ongoing basis

**Notes**

All of these rules are in the By-Laws of the Foundation. See Section 3.3 at https://corda.network/governance/bylaws
There is a small chance this will be delayed slightly, if a long list of candidates are proposed.
++++++++++++

For general updates on the Foundation, including decisions made, you may refer to the latest minutes from our Board Meetings.

 
