|Corda Network|[Document history]({{ site.github.repository_url }}/blame/master/{{page.path}})|

Filling in the right legal entity name for your node's x500 name, "O" field
==========================================================================

According to existing Corda Network guidelines, every node on Corda Network should represent a different legal entity to best enable interoperability for future operations. The legal entity name picked should be the owner of the assets which would be  transacted.

However, strictly speaking, for the nodes to function, it’s only imperative that each name is unique. Despite this, if you may join other business networks in the future, it would be better overall to pick different legal entity names for each node. 

The legal entity name should match the name in the government official trade list, in which it is registered.

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


Here is a few examples of this in practice:

Example 1:

| Node Operator email address | admin@natwestmarkets.com (example - not actual email address) |
|-----------------------------|---|
| **Organisation (O)**        | NatWest Markets PLC  |
| **City (L)**                | Edinburgh  |
| **Country (C)**             | UK  |
| State (US / Canada only)    |   |
| Organisation Unit (OU)      |   |
| Common Name (CN)            |   |

*This is the correct Legal Entity name, as evidenced in the UK government trade register, here:https://beta.companieshouse.gov.uk/company/SC090312*

Example 2:

| Node Operator email address | information@bnpp.fr (example - not actual email address) |
|-----------------------------|---|
| **Organisation (O)**        | · BNP PARIBAS SA  |
| **City (L)**                | Serignan  |
| **Country (C)**             | France  |
| State (US / Canada only)    |   |
| Organisation Unit (OU)      |   |
| Common Name (CN)            |   |

 

*This is the correct Legal Entity name, as evidenced in the French government trade register, here: http://www.sirene.fr/sirene/public/recherche*


This page may also be helpful: https://en.wikipedia.org/wiki/List_of_company_registers#cite_note-194
