---

copyright:
  years: 2017, 2022
lastupdated: "2022-02-17"

keywords: 

subcollection: direct-link

---

{{site.data.keyword.attribute-definition-list}}

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
2. Use the [IBM Cloud console ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://cloud.ibm.com) to order Direct Link Dedicated on Classic and complete the requested information. You can request assistance from IBM Cloud Sales engineers. When you are ready to create your order, you are prompted to read and agree to the [Direct Link Dedicated prerequisites](/docs/direct-link?topic=direct-link-ibm-cloud-dl-dedicated-prerequisites).

3. {{site.data.keyword.cloud_notm}} provides Letters of Authorization (LOA) for connections that use IBM Cloud. When you have the LOA, supply it to your colocation provider, then have them order a cross connect (and any required inter-campus connectivity) by using the {{site.data.keyword.cloud_notm}} CFA (Customer Facility Assignment) information in the LOA.

   This process usually takes 2 - 10 business days to complete, depending on the facility vendor and the order priority you specify. It includes the setup of the patch for the {{site.data.keyword.cloud_notm}} termination port.

4. Provide {{site.data.keyword.cloud_notm}} with the cross-connect completion notice from the facility provider in the IBM Support case.
5. {{site.data.keyword.cloud_notm}} verifies the completion notice's efficacy and orders the patch to be made from the LOA/CFA to the cross-connect router (XCR) and other gear.

Your IP assignment on the {{site.data.keyword.cloud_notm}} networking infrastructure is completed within three business days after the cross-connect is complete.

## Option 2 - Using an NSP
{: #network-service-provider}

1. Verify your NSP's capabilities to reach the appropriate Meet Me Room in the {{site.data.keyword.cloud_notm}} PoP or data center and cross-connect into the {{site.data.keyword.cloud_notm}} environment.
2. Use the [IBM Cloud console ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://cloud.ibm.com) to order Direct Link Dedicated on Classic and complete the requested information. You can request assistance from IBM Cloud Sales engineers. When you are ready to create your order, you are prompted to read and agree to the [Direct Link Dedicated prerequisites](/docs/direct-link?topic=direct-link-ibm-cloud-dl-dedicated-prerequisites).
3. {{site.data.keyword.cloud_notm}} provides Letters of Authorization (LOA) for connections that use IBM Cloud. When you have the LOA, supply it to your network provider, and have them order a "third-party cross connect", as well as the circuit between your premises and the appropriate Meet Me Room by using the {{site.data.keyword.cloud_notm}} CFA (Customer Facility Assignment) information in the LOA.

   This third-party, cross-connect process usually takes 2 - 10 extra business days to complete, depending on the facility vendor and the order priority you specify. It includes the setup of the patch to the {{site.data.keyword.cloud_notm}} termination port.

4. Provide {{site.data.keyword.cloud_notm}} with the cross-connect completion notice from the facility provider in the IBM Support case.
5. {{site.data.keyword.cloud_notm}} verifies the completion notice's efficacy and orders the patch to be made from the LOA/CFA to the cross-connect router (XCR) and other gear.

Your IP assignment on the {{site.data.keyword.cloud_notm}} networking infrastructure is completed within three business days after the cross connect is complete.

## Ordering instructions
{: #steps-to-order-direct-link-dedicated}

To provision a Direct Link Dedicated order, complete the following steps:

1. Log in to your [IBM Cloud](https://cloud.ibm.com/){: external} account.
1. Select the **Navigation Menu** icon ![Navigation Menu icon](images/menu_icon.png) on the upper left, then click **Classic Infrastructure** > **Direct Link**.

   The Direct Link on Classic page opens, listing existing Direct Link connections provisioned for this account.    
   
1. Click **Order Direct Link** in the upper right of the page. The Choose Direct Link option page is displayed.

   ![Choose Direct Link option](/images/choose-direct-link-dedicated.png){: caption="Choose Direct Link option" caption-side="bottom"}    
   
1. Select the **Direct Link Dedicated** tile to open the order form.
1. Complete the following information to configure Direct Link Dedicated: 

   - Enter a Direct Link instance name.
   - Select the location in which you want to establish the {{site.data.keyword.cloud_notm}} Direct Link connection.
   - Select the name of your network provider.
   - Select the link speed required for the connection.
   - Select the routing option required for the connection: **Local routing (free)** or **Global routing**. 
   - Enter a valid BGP ASN number from the range given in the information box for the BGP exchanges.

   As you select or enter these values, you can see an approximate monthly charge in the right pane.
   
1. Read and agree to the [Direct Link Dedicated prerequisites](/docs/direct-link?topic=direct-link-ibm-cloud-dl-dedicated-prerequisites). Then, click **Create** to complete your order.

      After you place your order, an IBM Support case number is generated. You can click the case number to view case details.

1. After you provision your direct link, see [Configuring Direct Link on Classic](/docs/direct-link?topic=direct-link-configure-ibm-cloud-direct-link) to configure your subnet to interact with IBM Cloud.

## Locations
{: #dedicated-locations}

The table gives details about the {{site.data.keyword.cloud_notm}} data centers where Direct Link Dedicated is available:

|**IBM Location Code** | **Location Type** | **Meet Me Room Operator**| **Operator Site Code** | **Operator Address** |
|-----------------|-----------------|-----------------|--------------------|--------------------|
| **APAC** | | | | |
| Chennai 1 | DC | Tata | PH-01 | 226, Red Hills Road, Kallikuppam, Ambattur |
| Hong Kong 1 | PoP | Mega-I (via Telstra) | Mega-I (iAdvantage Hong Kong) |29F, 399 Chai Wan Road |
| Hong Kong 3 | PoP | Equinix | HKG3| 17/F Kerry Warehouse |
| Melbourne 2 | PoP |NextDC | M1 | 820 Lorimer Street, Port Melbourne |
| Osaka 1 | PoP | Equinix | OS1 | Nishi-Shinsaibashi Bldg., 1-26-1 Shin-machi, Osaka  |
| Osaka 21  | DC(AZ1)|  IDC Frontier (SoftBank) | OSA021 | 6-1 Saitoaokita Mino-shi |
| Osaka 22  | DC(AZ2) | IDC Frontier (SoftBank) | OSA022 | 6-1 Saitoaokita Mino-shi |
| Osaka 23  | DC(AZ3) | IDC Frontier (SoftBank) | OSA023 | 6-1 Saitoaokita Mino-shi |
| Perth 1 | PoP | Equinix (Metronode) | F1Z | 60 Randell St, Shenton Park, Western Australia |
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
| Mexico 1 | DC | Equinix (fAlestra) | Alestra Queretaro Datacenter | Lateral Carretera Estatal 431, Parque Tecnologico Inovacion Lote 79, El Marqués |
| Miami 1 | PoP | Equinix (fTerremark/Verizon) | NAP | 50 NE 9th Street |
| Montreal 1 | DC | Cologix (fCOLO-D) | Cologix MTL9-H | 2525 Rue Canadien |
| Montreal 2 | PoP | Cologix | MTL7 | 1155  Robert – Bourassa Boulevard (Formerly Known as University Street) |
| New York City 2* | PoP | Equinix | NY4 | 755 Secaucus Rd, Secaucus, NJ |
| New York City 3* | PoP | Equinix | NY5 | 800 Secaucus Rd, Secaucus, NJ |
| San Jose 2 | PoP | Equinix | SV1 | 11 Great Oaks Blvd |
| San Jose 3 | DC | Digital Realty | SJC31 | 1100 Space Park Drive |
| San Jose 4 | DC | Infomart | SJC1 | 2001 Fortune Drive |
| Sao Paulo 1 | DC | Digital Realty (Ascenty) | SP1 | Rua Presbitero Plinio Alves de Souza, 757 J. Ermida II,Jundiai |
| Sao Paulo 2 | PoP | Equinix | SP4 | Avenida Ceci, 1900, Tambore, Barueri, SP, 06460 120 BR, Brazil |
| Seattle 2 | PoP | Digital Realty (The Westin Building) | WBX | 2001 6th Avenue |
| Toronto 1 | DC | Digital Realty (via SunGard) | YYZ11 | 371 Gough Rd |
| Toronto 2 | PoP | Cologix | TOR1 | 151 Front Street |
| Washington DC 2 | PoP | Equinix | DC2 | 21715 Filigree Ct |
| Washington DC 4 | DC(AZ1) | Digital Realty | IAD38 | 44060 Digital Loudoun Plaza (Bldg K) |
| Washington DC 5 | PoP | Coresite | DC2 | 12098 Sunrise Valley Dr |
| Washington DC 6 | DC(AZ1) | Raging Wire | VA2 | 44610 Guilford Drive |
| Washington DC 7 | DC(AZ1) | Sabey | Sabey Intergate.Ashburn | 21741 Red Rum Dr|
{: caption="Table 1: Direct Link Dedicated locations" caption-side="bottom"}

* NYC02 and NYC03 connect to the IBM Cloud backbone through NYC1. The primary reason for these PoPs is to extend connectivity to different site providers from our NYC01 site. When planning your diversity strategy, keep in mind that traffic for NYC02 and NYC03 have a single, shared path to the IBM network.

## Pricing
{: #dedicated-pricing-classic}

For more information, refer to the **Dedicated on Classic** tab in the [pricing table](/docs/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link).

If you require the exact address for TOK01 or TOK02, contact your Direct Link offering management or sales team.
{: note}
