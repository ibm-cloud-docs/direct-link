---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-25"

keywords: order, provider, capabilities, Dedicated, cross-connect, locations, PoP, datacenter, data, center, pricing, Letter of Authorization, LOA,

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:note: .note}
{:download: .download}

# How to order IBM Cloud Direct Link Dedicated
{: #how-to-order-ibm-cloud-direct-link-dedicated}

To order IBM Cloud Direct Link Dedicated, perform one of the following procedures, depending on your requirements.

The colocation or Network Service Provider does not need to be an IBM Cloud Direct Link Partner to connect you to a Direct Link Dedicated service.
{: note}

## Co-located in an IBM Cloud PoP or data center

1. Verify your colocation provider's capabilities to reach the appropriate Meet Me Room and cross-connect into the {{site.data.keyword.BluSoftlayer_notm}} environment.

2. Open an {{site.data.keyword.cloud}} Direct Link Dedicated request and complete the requested information.

  IBM sales engineers can help you with this process.  
  {: tip}

3. {{site.data.keyword.BluSoftlayer_notm}} provides Letters of Authorization (LOA) for connections using the customer portal. When you have the LOA, supply it to your colocation provider, then have them order a cross connect (as well as any required inter-campus connectivity) using the {{site.data.keyword.BluSoftlayer_notm}} CFA (Customer Facility Assignment) information in the LOA.

  This process usually takes 2 two 10 business days to complete, depending on the facility vendor and the order priority you specify. It includes the set up of the patch for the {{site.data.keyword.BluSoftlayer_notm}} termination port.

5. Provide {{site.data.keyword.BluSoftlayer_notm}} with the cross-connect completion notice from the facility provider in the {{site.data.keyword.BluSoftlayer_notm}} portal ticket.

6. {{site.data.keyword.BluSoftlayer_notm}} verifies the completion notice's efficacy and orders the patch to be made from the LOA/CFA to the cross-connect router (XCR) and other gear.

  Your IP assignment on the {{site.data.keyword.BluSoftlayer_notm}} networking infrastructure will be completed within 3 business days after the cross-connect is complete.

## Using a Network Service Provider

1. Verify your Network Service Provider’s capabilities to reach the appropriate Meet Me Room in the IBM Cloud PoP or data center and cross-connect into the {{site.data.keyword.BluSoftlayer_notm}} environment.

2. Open an {{site.data.keyword.cloud}} Direct Link Dedicated request and complete the requested information.

  IBM sales engineers can help you with this process.  
  {: tip}

3. {{site.data.keyword.BluSoftlayer_notm}} provides Letters of Authorization (LOA) for connections using the customer portal. When you have the LOA, supply it to your network provider, and have them order a "third party cross connect", as well as the circuit between your premises and the appropriate Meet Me Room using the {{site.data.keyword.BluSoftlayer_notm}} CFA (Customer Facility Assignment) information in the LOA.

  This third party cross-connect process usually takes 2 to 10 additional business days to complete, depending on the facility vendor and the order priority you specify. It includes the set up of the patch to the IBM Cloud termination port.

5. Provide {{site.data.keyword.BluSoftlayer_notm}} with the cross-connect completion notice from the facility provider in the {{site.data.keyword.BluSoftlayer_notm}} portal ticket.
6. {{site.data.keyword.BluSoftlayer_notm}} verifies the completion notice's efficacy and orders the patch to be made from the LOA/CFA to the cross-connect router (XCR) and other gear.

Your IP assignment on the {{site.data.keyword.BluSoftlayer_notm}} networking infrastructure will be completed within 3 business days after the cross-connect is complete.

## Locations
{: #dedicated-locations}

The table gives details about the IBM Cloud datacenters where Direct Link Dedicated is available:

|**IBM Location Code** | **Meet Me Room Operator**| **Operator Site Code** | **Operator Address** |
|-----------------|-----------------|--------------------|--------------------|
| **APAC** | | | |
| Chennai 1 | Tata | PH-01 | 226, Red Hills Road,Kallikuppam, Ambattur |
| Hong Kong 1 | Mega-I (via Telstra) | Mega-I (iAdvantage Hong Kong) |29F, 399 Chai Wan Road |
| Hong Kong 2 | Digital Realty | HKG10 |33 Chun Choi Street, Yan Hing Industrial Building |
| Melbourne 1 | Digital Realty | MEL11 | 72 Radnor Drive, Deer Park |
| Melbourne 2 | NextDC | M2 | 820 Lorimer Street, Port Melbourne |
| Osaka 1 (PoP only)| Equinix | OS1 |  |
| Perth 1 (PoP only)| Metronode | F1Z | 60 Randell St, Shenton Park, Western Australia |
| Seoul 1 | C&C | Seoul01 | 46, Pangyo-ro 255beon-gil, Bundang-gu, Seongnam-si, Gyeonggi-do |
| Seoul 2 | KINX | KINX Bundang IDC | 3F Hostway IDC ,343-1 Yatap-dong , Gyeonggi-do |
| Singapore 1 | Digital Realty | SIN10 | 29A International Business Park, S180 |
| Singapore 2 | Equinix | SG1 | 20 Ayer Rajan Crescent Industrial Park |
| Sydney 1 | Global Switch | SYD01 | 400 Harris Street aka 273 Pyrmont St Ultimo  |
| Sydney 2 | Equinix | SY3 | 47 Bourke Rd |
| Sydney 3 | NextDC | S1 | 4 Eden Park Drive, Macquarie Park |
| Sydney 4 | Digital Realty | SYD10 | 1-11 Templar Rd, Erskine Park |
| Sydney 5 | Equinix | SY4 | 200 Bourke Rd |
| Tokyo 1 | Equinix | TY2 | |
| Tokyo 2 | At Tokyo | CC2 |  |
| Tokyo 3 | Equinix | TY4 | |
| Tokyo 4 | SoftBank | | |
| Tokyo 5 | NTT | | |
| **EMEA** |  |  |
| Amsterdam 2 | Equinix | AM1 / AM2 | Larrderhoogtweg 57 |
| Amsterdam 3 | KPN | Amsterdam 3 | Rondebeltweg 62 |
| Frankfurt 1 | InterXion | FRA01 | Hanauer Landstrasse 302 |
| Frankfurt 2 | Zenium | FRA1 | Leonhard - Heisswolf Str 4., Frankfurt am Main |
| Frankfurt 3 | Equinix| FRA6 | Larchenstrasse 110, Frankfurt Griesheim |
| Frankfurt 4 | E-Shelter | Frankfurt 1 | Eschborner Landstrasse 100, Building H |
| Frankfurt 5 | InterXion | FRA05 | Weismüllerstraße 40 |
| London 1 | Equinix (fTelecity) | LD8 | 6/7 Harbour Exchange  E14 9GE |
| London 2 | Digital Realty | LHR13 | Fountain Court, Cox Lane |
| London 3 | Equinix | LD5 | 8 Buckingham Ave |
| London 4 | ARK | A103 | A57 Cody Technology Park Old, Victor Way, Farnborough |
| London 6 | Zenium | LON1 | 12 Liverpool Rd, Trading Estate |
| Milan 1 | Data IV | | Via Monzoro 101-105 , 20010 Cornaredo (MI) |
| Milan 2 | Infracom Italia | Infracom 21 Via Caldera Way | Infracom Italia Spa, Building D, Caldera Business Park, Via Caldera, 21|
| Oslo 1 | EVRY | DigiPlex - Fetsund | 9,, Heiaveien, 1900 Fetsund |
| Oslo 2 | Verizon | Verizon Oslo | Hans Møller Gassmanssvei 9 |
| Paris 1 | Global Switch | PAR01 | Société par Actions Simplifiée Unipersonnelle, 7-9 rue Petit |
| Paris 2 | Equinix | PA2 | 114 Rue Ambroise Croizat, St Denis |
| Stockholm 1 (PoP only) | InterXion | STO01 | Esbogatan 11 |
|  |  |  |
| **IBM PoP / Data Center Code** | **Meet Me Room Operator** | **Operator Site Code** |
| **Americas** |  |  |
| Atlanta 1 (PoP only)| Digital Realty | ATL13 | 56 Marietta Street |
| Chicago 1 (PoP only)| Equinix | CH4 | 350 E. Cermak |
| Dallas 3 | Equinix | DA1 | 1950 N. Stemmons Freeway |
| Dallas 4 | Digital Realty | DFW14 | 2323 Bryan St |
| Dallas 9 | Digital Realty | DFW35 | 900 Quality Way |
| Dallas 10 | QTS | IRV | 6431 Longhorn Drive |
| Dallas 12 |Digital Realty | DFW18 | 907 Security Row |
| Dallas 13 | Cyrus One | Carrollton - Frankford | 1649 W. Frankford Rd |
| Denver 1 (PoP only) | Coresite | DE1 | 910 15th Street |
| Houston 2 (PoP only) | IBM | HOU02 | 855 Greens Parkway |
| Los Angeles 1 (PoP only) | Coresite | LA1 | 624 S. Grand Ave. AKA 1 Wilshire Blvd |
| Mexico 1 | Alestra | Alestra Queretaro Datacenter | Lateral Carretera Estatal 431,Parque Tecnologico Inovacion Lote 79, El Marqués |
| Miami 1 (PoP only) | Terremark / Verizon | NAP | 50 NE 9th Street |
| Montreal 1 | COLO-D | COLO-D1 | 2525 Rue Canadien |
| Montreal 2 | Cologix | MTL7 | 1155  Robert – Bourassa Boulevard (Formerly Known as University Street) |
| New York City 2 (PoP only) | Equinix | NY4 | 755 Secaucus Rd, Secaucus, NJ |
| New York City 3 (PoP only) | Equinix | NY5 | 800 Secaucus Rd, Secaucus, NJ |
| Sao Paulo 1 | Ascenty | SP1 | Rua Presbitero Plinio Alves de Souza, 757 J. Ermida II,Jundiai |
| Sao Paulo 2 | Equinix | SP2 | Alameda Araguaia, 3641 - Alphaville, Barueri |
| Seattle 2 | The Westin Building | WBX | 2001 6th Avenue |
| San Jose 2 | Equinix | SV1 | 11 Great Oaks Blvd |
| San Jose 3 | Digital Realty | SJC31 | 1100 Space Park Drive |
| San Jose 4 | Infomart | SJC1 | 2001 Fortune Drive |
| Toronto 1 | Digital Realty | YYZ11 | 371 Gough Rd |
| Toronto 2 | Cologix | TOR1 | 151 Front Street |
| Washington DC 2 | Equinix | DC2 | 21715 Filigree Ct |
| Washington DC 4 | Digital Realty | IAD38 | 44060 Digital Loudoun Plaza (Bldg K) |
| Washington DC 5 | Coresite | DC2 | 12098 Sunrise Valley Dr |
| Washington DC 6 | Raging Wire | VA2 | 44610 Guilford Drive |
| Washington DC 7 | Sabey | Sabey Intergate.Ashburn | 21741 Red Rum Dr|

## Pricing
{: #dedicated-pricing}

For pricing information, please refer to the [pricing document](/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#pricing-for-direct-link-dedicated).

If you require the exact address for TOK01 or TOK02, please contact your Direct Link offering management or sales team.
{:note}
