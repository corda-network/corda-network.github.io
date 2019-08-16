|Corda Network|[Document history]({{ site.github.repository_url }}/blame/master/{{page.path}})|

Selecting the right Legal Entity for the "O" field in your X500 name
====================================================================

According to existing Corda Network guidelines, every node on Corda Network should represent a different legal entity to best enable interoperability for future operations. The legal entity name picked should be the owner of the assets which would be  transacted. 

The Legal Entity is found in the O field, of the node's [X500 name](https://corda.network/participation/distinguishedname.html) The Legal Entity should not be a high-level Corporate Group (for example, "HSBC") but the specific legal entity which owns the assets (for example: HSBC Asset Finance (UK) Limited) 

It should match the exact name in the government official trade list, in which it is registered.

Here is a few examples of filling out the whole X500 name, in practice. Take a careful look at the O field selected - this is the cause of most error!

Example 1:

| Field title | Real-life example |
|-----------------------------|---|
| **Organisation (O)**        | NatWest Markets PLC  |
| **City (L)**                | Edinburgh  |
| **Country (C)**             | UK  |
| State (US / Canada only)    |   |
| Organisation Unit (OU)      |   |
| Common Name (CN)            |   |
| Node Operator email address | admin@natwestmarkets.com (example - not actual email address)|

*This is the correct Legal Entity name, as evidenced in the UK government trade register, here:https://beta.companieshouse.gov.uk/company/SC090312*

Example 2:

| Field title | Real-life example |
|-----------------------------|---|
| **Organisation (O)**        | · BNP PARIBAS SA  |
| **City (L)**                | Serignan  |
| **Country (C)**             | France  |
| State (US / Canada only)    |   |
| Organisation Unit (OU)      |   |
| Common Name (CN)            |   |
| Node Operator email address | information@bnpp.fr (example - not actual email address) |

 
*This is the correct Legal Entity name, as evidenced in the French government trade register, here: http://www.sirene.fr/sirene/public/recherche*


Here are some examples of government trade registers (list is a work in progress):

Country | Link 
--- | --- 
Australia | https://connectonline.asic.gov.au/RegistrySearch/faces/landing/SearchRegisters.jspx?_adf.ctrl-state=jx0kwgy52_4
Chile | https://www.conservador.cl/portal/indice_comercio
Finland | https://virre.prh.fi/novus/home?execution=e1s1
Hungary | https://www.e-cegjegyzek.hu/?cegkereses
India | http://www.mca.gov.in/mcafoportal/viewCompanyMasterData.do
Philippines | https://www.bnrs.dti.gov.ph/web/guest/search
Singapore | https://www.bizfile.gov.sg/ngbbizfileinternet/faces/oracle/webcenter/portalapp/pages/BizfileHomepage.jspx
South Africa | https://eservices.cipc.co.za/Search.aspx
UK | https://beta.companieshouse.gov.uk/
US | https://www.sec.gov/edgar/searchedgar/companysearch.html


This page may also be helpful: https://en.wikipedia.org/wiki/List_of_company_registers#cite_note-194
