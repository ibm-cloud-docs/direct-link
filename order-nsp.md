---

copyright:
  years: 2017, 2021
lastupdated: "2021-07-15"

keywords: order, provider, capabilities, Dedicated, cross-connect, locations, PoP, datacenter, data, center, pricing, Letter of Authorization, LOA,

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:DomainName: data-hd-keyref="DomainName"}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}
{:external: target="_blank" .external}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:term: .term}  
{:generic: data-hd-programlang="generic"}
{:download: .download}  
{:help: data-hd-content-type='help'}
{:support: data-reuse='support'}

# Ordering Direct Link Dedicated on Classic
{: #how-to-order-ibm-cloud-direct-link-dedicated}
{: help}
{: support}

As you prepare to order Direct Link on Classic, review the general process that your organization follows for obtaining the Dedicated service, including the locations where each service is available, globally. When you're ready to place your order, follow the step-by-step instructions.  
{: shortdesc}

The colocation or Network Service Provider (NSP) does not need to be an IBM Cloud Direct Link Business Partner to connect you to a Direct Link Dedicated service.
{: note}

To determine which Direct Link solution is best for your networking environment, see [How do I know which Direct Link solution to order?](/docs/direct-link?topic=direct-link-get-started-with-ibm-cloud-direct-link#get-started-solution-to-order)
{: tip}

You can choose from the following two options.

## Option 1 - Colocated in an IBM Cloud PoP or data center
{: #colocated-in-ibm-cloud-pop}

1. Verify your colocation provider's capabilities to reach the appropriate Meet Me Room and cross-connect into the {{site.data.keyword.cloud_notm}} environment.
2. Use the [IBM Cloud console ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://cloud.ibm.com) to order Direct Link Dedicated on Classic and complete the requested information. You can request assistance from IBM Cloud Sales engineers. When you are ready to create your order, you are prompted to read and agree to the Master Service Agreement.
3. {{site.data.keyword.cloud_notm}} provides Letters of Authorization (LOA) for connections that use IBM Cloud. When you have the LOA, supply it to your colocation provider, then have them order a cross connect (and any required inter-campus connectivity) by using the {{site.data.keyword.cloud_notm}} CFA (Customer Facility Assignment) information in the LOA.

   This process usually takes 2 - 10 business days to complete, depending on the facility vendor and the order priority you specify. It includes the setup of the patch for the {{site.data.keyword.cloud_notm}} termination port.

4. Provide {{site.data.keyword.cloud_notm}} with the cross-connect completion notice from the facility provider in the IBM Support case.
5. {{site.data.keyword.cloud_notm}} verifies the completion notice's efficacy and orders the patch to be made from the LOA/CFA to the cross-connect router (XCR) and other gear.

Your IP assignment on the {{site.data.keyword.cloud_notm}} networking infrastructure is completed within three business days after the cross-connect is complete.

## Option 2 - Using an NSP
{: #network-service-provider}

1. Verify your NSP's capabilities to reach the appropriate Meet Me Room in the {{site.data.keyword.cloud_notm}} PoP or data center and cross-connect into the {{site.data.keyword.cloud_notm}} environment.
2. Use the [IBM Cloud console ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://cloud.ibm.com) to order Direct Link Dedicated on Classic and complete the requested information. You can request assistance from IBM Cloud Sales engineers. When you are ready to create your order, you are prompted to read and agree to the Master Service Agreement.
3. {{site.data.keyword.cloud_notm}} provides Letters of Authorization (LOA) for connections that use IBM Cloud. When you have the LOA, supply it to your network provider, and have them order a "third-party cross connect", as well as the circuit between your premises and the appropriate Meet Me Room by using the {{site.data.keyword.cloud_notm}} CFA (Customer Facility Assignment) information in the LOA.

   This third-party, cross-connect process usually takes 2 - 10 extra business days to complete, depending on the facility vendor and the order priority you specify. It includes the setup of the patch to the {{site.data.keyword.cloud_notm}} termination port.

4. Provide {{site.data.keyword.cloud_notm}} with the cross-connect completion notice from the facility provider in the IBM Support case.
5. {{site.data.keyword.cloud_notm}} verifies the completion notice's efficacy and orders the patch to be made from the LOA/CFA to the cross-connect router (XCR) and other gear.

Your IP assignment on the {{site.data.keyword.cloud_notm}} networking infrastructure is completed within three business days after the cross connect is complete.

## Steps to order Direct Link Dedicated on Classic
{: #steps-to-order-direct-link-dedicated}

To provision a Direct Link Connect order, complete the following steps:

1. Log in to your [IBM Cloud](https://cloud.ibm.com/){: external} account and open the **Catalog**.
2. Select the **Menu** icon ![Menu icon](images/menu_icon.png) on the upper left of the page, then click **Classic Infrastructure**.
2. Select **Network > Direct Link > Dedicated** to open a page that shows the existing Direct Link connections, if any.
3. Click **Order Direct Link Dedicated +** in the upper right of the page. The "Create an IBM Cloud Direct Link Dedicated Connection" page is displayed.
4. In the order form, complete the following information to configure Direct Link Dedicated on Classic:
   - Enter the Direct Link instance name.
   - From the list, select the location in which you want to establish the {{site.data.keyword.cloud_notm}} Direct Link connection.
   - From the list, select the name of the network provider that you prefer.
   - Select the link speed required for the connection.
   - Select the routing option required for the connection.
   - Enter a valid ASN number from the range given in the information box for the BGP exchanges.

   As you select or enter these values, you can see an approximate monthly charge in the right pane.
6. You must agree to the [Master Service Agreement](https://cloud.ibm.com/classic/account/masterserviceagreement/getagreement){: external} before you can place the IBM Cloud Direct Link order.  

      After you place your order, an IBM Support case number is generated. You can click the case number to view case details.

7. You’ll be asked to complete a customer questionnaire, which you can review at [Direct Link Dedicated questionnaire](/docs/direct-link?topic=direct-link-ibm-cloud-direct-link-dedicated-questionnaire).

8. After you provision the direct link and complete the questionnaire, see [Configuring Direct Link on Classic](/docs/direct-link?topic=direct-link-configure-ibm-cloud-direct-link) to configure your subnet to interact with IBM Cloud.


## Locations
{: #dedicated-locations}

The table gives details about the {{site.data.keyword.cloud_notm}} data centers where Direct Link Dedicated is available:

|**IBM Location Code** | **Location Type** | **Meet Me Room Operator**| **Operator Site Code** | **Operator Address** |
|-----------------|-----------------|-----------------|--------------------|--------------------|
| **APAC** | | | | |
| Chennai 1 | DC | Tata | PH-01 | 226, Red Hills Road, Kallikuppam, Ambattur |
| Hong Kong 1 | PoP | Mega-I (via Telstra) | Mega-I (iAdvantage Hong Kong) |29F, 399 Chai Wan Road |
| Hong Kong 2 | DC | Digital Realty | HKG10 |33 Chun Choi Street, Yan Hing Industrial Building |
| Hong Kong 3 | PoP | Equinix | HKG2 | 17/F Kerry Warehouse |
| Melbourne 2 | PoP |NextDC | M1 | 820 Lorimer Street, Port Melbourne |
| Osaka 1 | PoP | Equinix | OS1 | Nishi-Shinsaibashi Bldg., 1-26-1 Shin-machi, Osaka  |
| Perth 1 | PoP | Equinix (Metronode) | F1Z | 60 Randell St, Shenton Park, Western Australia |
| Seoul 1 | DC | C&C | Seoul01 | 46, Pangyo-ro 255beon-gil, Bundang-gu, Seongnam-si, Gyeonggi-do |
| Seoul 2 | PoP | KINX | KINX Bundang IDC | 3F Hostway IDC, 343-1 Yatap-dong, Gyeonggi-do |
| Singapore 1 | DC | Digital Realty | SIN10 | 29A International Business Park, S180 |
| Singapore 2 | PoP | Equinix | SG1 | 20 Ayer Rajan Crescent Industrial Park |
| Sydney 1 | DC(AZ1) | Global Switch | SYD01 | 400 Harris Street aka 273 Pyrmont St Ultimo  |
| Sydney 2 | PoP | Equinix | SY3 | 47 Bourke Rd |
| Sydney 3 | PoP | NextDC | S1 | 4 Eden Park Drive, Macquarie Park |
| Sydney 4 | DC(AZ2) | Digital Realty | SYD10 | 1-11 Templar Rd, Erskine Park |
| Sydney 5 | DC(AZ3) | Equinix | SY4 | 200 Bourke Rd |
| Tokyo 1 | PoP | Equinix | TY2 | |
| Tokyo 2 | DC(AZ1) | At Tokyo | CC2 |  |
| Tokyo 3 | PoP | Equinix | TY4 | |
| Tokyo 4 | DC(AZ2) | SoftBank | | |
| Tokyo 5 | DC(AZ3) | NTT | | |
| **EMEA** |  |  |  |
| Amsterdam 2 | PoP | Equinix | AM2 | Larrderhoogtweg 57 |
| Amsterdam 3 | DC | KPN | Amsterdam 3 | Rondebeltweg 62 |
| Frankfurt 1 | PoP | Digital Realty (fInterXion) | FRA6 | Hanauer Landstrasse 302 |
| Frankfurt 2 | DC(AZ1) | Cyrus One (fZenium) | FRA1 | Leonhard - Heisswolf Str 4., Frankfurt am Main |
| Frankfurt 3 | PoP | Equinix| FR6 | Larchenstrasse 110, Frankfurt Griesheim |
| Frankfurt 4 | DC(AZ2) | E-Shelter | Frankfurt 1 | Eschborner Landstrasse 100, Building H |
| Frankfurt 5 | DC(AZ3) | InterXion | FRA11 | Weismüllerstraße 40 |
| London 1 | PoP | Equinix (fTelecity) | LD8 | 6/7 Harbour Exchange E14 9GE |
| London 2 | DC | Digital Realty | LHR13 | Fountain Court, Cox Lane |
| London 3 | PoP | Equinix | LD5 | 8 Buckingham Ave |
| London 4 | DC(AZ1) | ARK | A103 | A57 Cody Technology Park Old, Victor Way, Farnborough |
| London 5 | DC(AZ2) | Gyron |  | Maxted Cl, Hemel Hempstead  |
| London 6 | DC(AZ3) | Cyrus One (fZenium) | LON1 | 12 Liverpool Rd, Trading Estate |
| Milan 1 |  DC | Data4 | | Via Monzoro 101-105, 20010 Cornaredo (MI) |
| Milan 2 | PoP | Infracom Italia | Infracom 21 Via Caldera Way | Infracom Italia Spa, Building D, Caldera Business Park, Via Caldera, 21|
| Oslo 1 | DC | DigiPlex | DigiPlex - Fetsund | 9,, Heiaveien, 1900 Fetsund |
| Oslo 2 | POP | Verizon | Verizon Oslo | Hans Møller Gassmanssvei 9 |
| Paris 1 | DC | Global Switch | PAR01 | Société par Actions Simplifiée Unipersonnelle, 7-9 rue Petit |
| Paris 2 | PoP | Equinix | PA2 | 114 Rue Ambroise Croizat, St Denis |
| Stockholm 1 | PoP | Digital Realty (fInterXion)  | STO01 | Esbogatan 11 |
| **Americas** |  |  |  |
| Atlanta 1 | PoP | Digital Realty | ATL13 | 56 Marietta Street |
| Chicago 1 | PoP | Equinix | CH4 | 350 E. Cermak |
| Dallas 3 | PoP | Equinix | DA1 | 1950 N. Stemmons Freeway |
| Dallas 4 | PoP | Digital Realty | DFW14 | 2323 Bryan St |
| Dallas 9 | DC | Digital Realty | DFW35 | 900 Quality Way |
| Dallas 10 | DC(AZ1) | QTS | IRV | 6431 Longhorn Drive |
| Dallas 12 | DC(AZ1) | Digital Realty | DFW18 | 907 Security Row |
| Dallas 13 | DC(AZ1) | Cyrus One | Carrollton - Frankford | 1649 W. Frankford Rd |
| Denver 1 | PoP | Coresite | DE1 | 910 15th Street |
| Los Angeles 1 | PoP | Coresite | LA1 | 624 S. Grand Ave. AKA 1 Wilshire Blvd |
| Mexico 1 | DC | Equinix (fAlestra) | Alestra Queretaro Datacenter | Lateral Carretera Estatal 431, Parque Tecnologico Inovacion Lote 79, El Marqués |
| Miami 1 | PoP | Equinix (fTerremark/Verizon) | NAP | 50 NE 9th Street |
| Montreal 1 | DC | Cologix (fCOLO-D) | Cologix MTL9-H | 2525 Rue Canadien |
| Montreal 2 | PoP | Cologix | MTL7 | 1155  Robert – Bourassa Boulevard (Formerly Known as University Street) |
| New York City 2 | PoP | Equinix | NY4 | 755 Secaucus Rd, Secaucus, NJ |
| New York City 3 | PoP | Equinix | NY5 | 800 Secaucus Rd, Secaucus, NJ |
| Sao Paulo 1 | DC | Digital Realty (Ascenty) | SP1 | Rua Presbitero Plinio Alves de Souza, 757 J. Ermida II,Jundiai |
| Sao Paulo 2 | PoP | Equinix | SP4 | Avenida Ceci, 1900, Tambore, Barueri, SP, 06460 120 BR, Brazil |
| Seattle 2 | PoP | Digital Realty (The Westin Building) | WBX | 2001 6th Avenue |
| San Jose 2 | PoP | Equinix | SV1 | 11 Great Oaks Blvd |
| San Jose 3 | DC | Digital Realty | SJC31 | 1100 Space Park Drive |
| San Jose 4 | DC | Infomart | SJC1 | 2001 Fortune Drive |
| Toronto 1 | DC | Digital Realty (via SunGard) | YYZ11 | 371 Gough Rd |
| Toronto 2 | PoP | Cologix | TOR1 | 151 Front Street |
| Washington DC 2 | PoP | Equinix | DC2 | 21715 Filigree Ct |
| Washington DC 4 | DC(AZ1) | Digital Realty | IAD38 | 44060 Digital Loudoun Plaza (Bldg K) |
| Washington DC 5 | PoP | Coresite | DC2 | 12098 Sunrise Valley Dr |
| Washington DC 6 | DC(AZ1) | Raging Wire | VA2 | 44610 Guilford Drive |
| Washington DC 7 | DC(AZ1) | Sabey | Sabey Intergate.Ashburn | 21741 Red Rum Dr|

## Pricing
{: #dedicated-pricing-classic}

For more information, refer to the **Dedicated on Classic** tab in the [pricing table](/docs/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link).

If you require the exact address for TOK01 or TOK02, contact your Direct Link offering management or sales team.
{: note}
