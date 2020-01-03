---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-25"

keywords: colocation, connectivity, provider, Dedicated, Hosting, locations, PoP, datacenter, data, center, contract, addendum

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

# Ordering Direct Link Dedicated Hosting on Classic
{: #how-to-order-ibm-cloud-direct-link-dedicated-hosting}

As you prepare to order IBM Cloud Direct Link, review the general process your organization will follow for obtaining the Direct Link Connect service, including the locations where each service is available, globally. When you're ready to place your order, follow the step-by-step instructions.  
{:shortdesc}

To determine which Direct Link solution is best for your networking environment, see
[How do I know which type of IBM Cloud Direct Link I need?](/docs/direct-link?topic=direct-link-get-started-with-ibm-cloud-direct-link#how-do-i-know-which-type-of-ibm-cloud-direct-link-i-need-)
{: tip}

## Direct Link ordering process overview
{: # ordering-process-overview-dh}

Here is the general process to order a Direct Link Dedicated Hosting service:

1. Identify your colocation and connectivity requirements, and work with the {{site.data.keyword.cloud}} sales team to finalize and execute a contract and technical addendum.
2. {{site.data.keyword.cloud_notm}} runs a build order with the colocation provider for the requested environment and services. Deployment typically is completed within 30 days from when the build order is placed.
3. When the build of your colocation cage is complete, use the [IBM Cloud console ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://cloud.ibm.com) to order Direct Link Dedicated Hosting on Classic and complete the requested information. You can request assistance from IBM Cloud Sales engineers. When you are ready to create your order, you are prompted to read and agree to the Master Service Agreement.
4. {{site.data.keyword.cloud_notm}} provides Letters of Authorization (LOA) for connections that use IBM Cloud. When you have the LOA, supply it to your colocation provider, then have them order a cross connect (and any required inter-campus connectivity) by using the {{site.data.keyword.cloud_notm}} CFA (Customer Facility Assignment) information in the LOA.

  This process usually takes 2 to 10 business days to complete, depending on the facility vendor and the order priority you specify. It includes the setup of the patch for the {{site.data.keyword.cloud_notm}} termination port.

5. Provide {{site.data.keyword.cloud_notm}} with the cross-connect completion notice from the facility provider in the IBM Support case.
6. {{site.data.keyword.cloud_notm}} verifies the completion notice's efficacy and orders the patch to be made from the LOA/CFA to the cross-connect router (XCR) and other gear.

Your IP assignment on the {{site.data.keyword.cloud_notm}} networking infrastructure is completed within three business days after the cross-connect is complete.

## Steps to order Direct Link Dedicated Hosting on Classic
{: #steps-to-order-direct-link-dedicated-hosting}

To provision a Direct Link Connect Hosting order, omplete the following steps:

1. Log in to your [IBM Cloud](https://cloud.ibm.com/){: external} account and open the **Catalog**.
2. Select the **Navigation Menu** icon ![Navigation Menu icon](images/menu_icon.png) on the upper left, then click **on Classic Infrastructure**.
2. Select **Network > Direct Link > Dedicated Hosting** to open a page that shows the existing Direct Link connections, if any.
3. Click **Order Direct Link Dedicated Hosting +** in the upper right of the page. The "Create an IBM Cloud Direct Link Dedicated Hosting Connection" page is displayed.
4. In the order form, complete the following information to configure Direct Link Dedicated Hosting on Classic:
   - Enter the Direct Link instance name.
   - From the list, select the location in which you want to establish the {{site.data.keyword.cloud_notm}} Direct Link connection.
   - From the list, select the name of the network provider that you prefer.
   - Select the link speed required for the connection.
   - Select the routing option required for the connection.
   - Enter a valid ASN number from the range given in the information box for the BGP exchanges.

   As you select or enter these values, you can see an approximate monthly charge in the right panel.
6. You must agree to the [Master Service Agreement](https://cloud.ibm.com/classic/account/masterserviceagreement/getagreement){: external} before you can place the IBM Cloud Direct Link order.  

      After you place your order, an IBM Support case number is generated. You can click the case number to view case details

7. You’ll be asked to complete a customer questionnaire, which you can review at [Direct Link Dedicated Hosting questionnaire](/docs/direct-link?topic=direct-link-ibm-cloud-direct-link-dedicated-hosting-questionnaire).

8. After you provision the direct link and complete the questionnaire, see [Configuring Direct Link on Classic]{/docs/direct-link?topic=direct-link-configure-ibm-cloud-direct-link) to configure your subnet to interact with IBM Cloud.


## Locations
{: #dedicated-hosting-locations}

This table shows which {{site.data.keyword.cloud_notm}} data centers are able to accept customers for Dedicated Hosting:


| Region | Site<br />ID | City | Site<br />Type | Site<br />Partner | Site<br />Address |
|-------|-------|-------|-------|-------|-------|
| Americas | DAL09 | Richardson | DC | Digital Realty  | 900 Quality Way |
| Americas | DAL10 | Irving | DC (AZ1) | QTS | 6431 Longhorn Dr. |
| Americas | DAL12 | Richardson |	DC (AZ2) | Digital Realty  | 1210 Integrity Dr.  |
| Americas | DAL13 | Carrollton | DC (AZ3) | CyrusOne | 1649 Frankford Rd. |
| Americas | MON01 | Drummond  | DC | Colo-D  | 2525 Rue Canadien |
| Americas | SAO01 | Sao Paulo | DC | Digital Realty (Ascenty) | Rua Presbitero Plinio Alves de Souza, 757 J. Ermida II, Jundial |
| Americas | SJC03 | Santa Clara | DC | Digital Realty  | 1100 Space Park Drive |
| Americas | WDC04 | Ashburn | DC (AZ1) | Digital Realty  | 44060 Digital Loudoun Plaza (Bldg K)
| Americas | WDC06 | Ashburn | DC (AZ3) | Raging Wire | 44610 Guilford Drive |
| Americas | WDC07 | Ashburn | DC (AZ2) | Sabey | 21741 Red Rum Dr |
|  |  |  |  |  |  |
| APAC |  SYD01 |  Sydney | DC (AZ1) | Global Switch  |  400 Harris Street aka 273 Pyrmont St. Ultimo |
| APAC |	SYD04 |	 Sydney |	DC (AZ2) |	Digital Realty  |	4 Eden Park Drive |
| APAC |	SYD05 |	 Sydney |	DC (AZ3) |	Equinix |	200 Bourke Rd |
| APAC |  SNG01 |  Jurong East | DC | Digital Realty  |  29a International Business Park, S180 |
| APAC | TOK02  |  Koto-ku | DC (AZ1) | AT Tokyo  |  Koto-ku |
| APAC | TOK05  | Kawasaki Kangagawa  | DC (AZ3) | NTT | Kawasaki Kangagawa |
|  |  |  |  |  |  |
| EMEA | FRA02  | Frankfurt |  DC (AZ1) | Cyrus One (Zenium)   | Leonhard - Heisswolf Str. 4 |
| EMEA | FRA04  | Frankfurt |  DC (AZ2) | E-shelter | Eschborner Landstrasse 100, Building H |
| EMEA | LON02  | Chessington | DC  | Digital Realty  |  Fountain Court |
| EMEA | LON06 | London |	DC (AZ3) |	Cyrus One (Zenium) |	12 Liverpool Rd |

## Pricing
{: #dedicated-pricing}

For more information, refer to the [pricing document](/docs/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#pricing-for-direct-link-dedicated-hosting).
