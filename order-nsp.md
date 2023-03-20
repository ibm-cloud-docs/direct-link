---

copyright:
  years: 2017, 2023
lastupdated: "2023-02-08"

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
2. Use the [IBM Cloud console ![External link icon](../../icons/launch-glyph.svg "External link icon")](/login) to order Direct Link Dedicated on Classic and complete the requested information. You can request assistance from IBM Cloud Sales engineers. When you are ready to create your order, you are prompted to read and agree to the [Direct Link Dedicated prerequisites](/docs/direct-link?topic=direct-link-ibm-cloud-dl-dedicated-prerequisites).

3. {{site.data.keyword.cloud_notm}} provides Letters of Authorization (LOA) for connections that use IBM Cloud. When you have the LOA, supply it to your colocation provider, then have them order a cross connect (and any required inter-campus connectivity) by using the {{site.data.keyword.cloud_notm}} CFA (Customer Facility Assignment) information in the LOA.

   This process usually takes 2 - 10 business days to complete, depending on the facility vendor and the order priority you specify. It includes the setup of the patch for the {{site.data.keyword.cloud_notm}} termination port.

4. Provide {{site.data.keyword.cloud_notm}} with the cross-connect completion notice from the facility provider in the IBM Support case.
5. {{site.data.keyword.cloud_notm}} verifies the completion notice's efficacy and orders the patch to be made from the LOA/CFA to the cross-connect router (XCR) and other gear.

Your IP assignment on the {{site.data.keyword.cloud_notm}} networking infrastructure is completed within three business days after the cross-connect is complete.

## Option 2 - Using an NSP
{: #network-service-provider}

1. Verify your NSP's capabilities to reach the appropriate Meet Me Room in the {{site.data.keyword.cloud_notm}} PoP or data center and cross-connect into the {{site.data.keyword.cloud_notm}} environment.
2. Use the [IBM Cloud console ![External link icon](../../icons/launch-glyph.svg "External link icon")](/login) to order Direct Link Dedicated on Classic and complete the requested information. You can request assistance from IBM Cloud Sales engineers. When you are ready to create your order, you are prompted to read and agree to the [Direct Link Dedicated prerequisites](/docs/direct-link?topic=direct-link-ibm-cloud-dl-dedicated-prerequisites).
3. {{site.data.keyword.cloud_notm}} provides Letters of Authorization (LOA) for connections that use IBM Cloud. When you have the LOA, supply it to your network provider, and have them order a "third-party cross connect", as well as the circuit between your premises and the appropriate Meet Me Room by using the {{site.data.keyword.cloud_notm}} CFA (Customer Facility Assignment) information in the LOA.

   This third-party, cross-connect process usually takes 2 - 10 extra business days to complete, depending on the facility vendor and the order priority you specify. It includes the setup of the patch to the {{site.data.keyword.cloud_notm}} termination port.

4. Provide {{site.data.keyword.cloud_notm}} with the cross-connect completion notice from the facility provider in the IBM Support case.
5. {{site.data.keyword.cloud_notm}} verifies the completion notice's efficacy and orders the patch to be made from the LOA/CFA to the cross-connect router (XCR) and other gear.

Your IP assignment on the {{site.data.keyword.cloud_notm}} networking infrastructure is completed within three business days after the cross connect is complete.

## Ordering instructions
{: #steps-to-order-direct-link-dedicated}

To provision a Direct Link Dedicated order, complete the following steps:

1. Log in to your [IBM Cloud](/login){: external} account.
1. Select the **Navigation Menu** icon ![Navigation Menu icon](images/menu_icon.png) on the upper left, then click **Classic Infrastructure** > **Direct Link**.

   The Direct Link on Classic page opens, listing existing Direct Link connections provisioned for this account.    
   
1. Click **Order Direct Link** in the upper right of the page. The Choose Direct Link option page is displayed.   
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

|**IBM Location Code** | **Location Type** | **Meet Me Room Operator**| **Operator Site Code** |
|-----------------|-----------------|-----------------|--------------------|
| Chennai 1 | DC | Tata | PH-01 |
| Hong Kong 1 | PoP | Mega-I (via Telstra) | Mega-I (iAdvantage Hong Kong) |
| Hong Kong 3 | PoP | Equinix | HKG3|
| Melbourne 2 | PoP |NextDC | M1 |
| Osaka 1 | PoP | Equinix | OS1 |
| Osaka 21  | DC(AZ1)|  IDC Frontier (SoftBank) | OSA021 |
| Osaka 22  | DC(AZ2) | IDC Frontier (SoftBank) | OSA022 |
| Osaka 23  | DC(AZ3) | IDC Frontier (SoftBank) | OSA023 |
| Perth 1 | PoP | Equinix (Metronode) | F1Z |
| Seoul 2 | PoP | KINX | KINX Bundang IDC |
| Singapore 1 | DC | Digital Realty | SIN10 |
| Singapore 2 | PoP | Equinix | SG1 | 
| Sydney 1 | DC(AZ1) | Global Switch | SYD01 |
| Sydney 2 | PoP | Equinix | SY3 |
| Sydney 3 | PoP | NextDC | S1 | 
| Sydney 4 | DC(AZ2) | Digital Realty | SYD10 |
| Sydney 5 | DC(AZ3) | Equinix | SY4 |
| Tokyo 1 | PoP | Equinix | TY2 |
| Tokyo 2 | DC(AZ1) | At Tokyo | CC2 |
| Tokyo 3 | PoP | Equinix | TY4 |
| Tokyo 4 | DC(AZ2) | SoftBank | |
| Tokyo 5 | DC(AZ3) | NTT | |
| **EMEA** |  |  |  |
| Amsterdam 2 | PoP | Equinix | AM2 |
| Amsterdam 3 | DC | KPN | Amsterdam 3 |
| Frankfurt 1 | PoP | Digital Realty (fInterXion) | FRA6 |
| Frankfurt 2 | DC(AZ1) | Cyrus One (fZenium) | FRA1 |
| Frankfurt 3 | PoP | Equinix| FR6 |
| Frankfurt 4 | DC(AZ2) | E-Shelter | Frankfurt 1 |
| Frankfurt 5 | DC(AZ3) | InterXion | FRA11 |
| London 1 | PoP | Equinix (fTelecity) | LD8 |
| London 2 | DC | Digital Realty | LHR13 |
| London 3 | PoP | Equinix | LD5 |
| London 4 | DC(AZ1) | ARK | A103 |
| London 5 | DC(AZ2) | Gyron |  |
| London 6 | DC(AZ3) | Cyrus One (fZenium) | LON1 |
| Milan 1 |  DC | Data4 | |
| Milan 2 | PoP | Infracom Italia | Infracom 21 Via Caldera Way |
| Paris 1 | DC | Global Switch | PAR01 |
| Paris 2 | PoP | Equinix | PA2 |
| **Americas** |  |  |
| Atlanta 1 | PoP | Digital Realty | ATL13 |
| Chicago 1 | PoP | Equinix | CH4 |
| Dallas 3 | PoP | Equinix | DA1 |
| Dallas 4 | PoP | Digital Realty | DFW14 |
| Dallas 9 | DC | Digital Realty | DFW35 |
| Dallas 10 | DC(AZ1) | QTS | IRV |
| Dallas 12 | DC(AZ1) | Digital Realty | DFW18 |
| Dallas 13 | DC(AZ1) | Cyrus One | Carrollton - Frankford |
| Denver 1 | PoP | Coresite | DE1 |
| Miami 1 | PoP | Equinix (fTerremark/Verizon) | NAP |
| Montreal 1 | DC | Cologix (fCOLO-D) | Cologix MTL9-H |
| Montreal 2 | PoP | Cologix | MTL7 |
| New York City 2* | PoP | Equinix | NY4 |
| New York City 3* | PoP | Equinix | NY5 |
| San Jose 2 | PoP | Equinix | SV1 |
| San Jose 3 | DC | Digital Realty | SJC31 |
| San Jose 4 | DC | Infomart | SJC1 |
| Sao Paulo 1 | DC | Digital Realty (Ascenty) | SP1 |
| Sao Paulo 2 | PoP | Equinix | SP4 |
| Seattle 2 | PoP | Digital Realty (The Westin Building) | WBX |
| Toronto 1 | DC | Digital Realty (via SunGard) | YYZ11 |
| Toronto 2 | PoP | Cologix | TOR1 |
| Washington DC 2 | PoP | Equinix | DC2 |
| Washington DC 4 | DC(AZ1) | Digital Realty | IAD38 |
| Washington DC 5 | PoP | Coresite | DC2 |
| Washington DC 6 | DC(AZ1) | Raging Wire | VA2 |
| Washington DC 7 | DC(AZ1) | Sabey | Sabey Intergate.Ashburn |
{: caption="Table 1: Direct Link Dedicated locations" caption-side="bottom"}

\* NYC02 and NYC03 connect to the IBM Cloud backbone through NYC1. The primary reason for these PoPs is to extend connectivity to different site providers from our NYC01 site. When planning your diversity strategy, keep in mind that traffic for NYC02 and NYC03 have a single, shared path to the IBM network.

If you require the exact address for TOK01 or TOK02, contact your Direct Link offering management or sales team.
{: note}
