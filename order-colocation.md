---

copyright:
  years: 2017, 2023
lastupdated: "2023-03-23"

keywords:

subcollection: direct-link

---

{{site.data.keyword.attribute-definition-list}}

# Ordering Direct Link Dedicated Hosting on Classic
{: #how-to-order-ibm-cloud-direct-link-dedicated-hosting}
{: help}
{: support}

As you prepare to order Direct Link on Classic, review the general process that your organization follows for obtaining the Dedicated Hosting service, including the locations where each service is available, globally. When you're ready to place your order, follow the step-by-step instructions.  
{: shortdesc}

To determine which Direct Link solution is best for your networking environment, see
[How do I know which Direct Link solution to order?](/docs/direct-link?topic=direct-link-get-started-with-ibm-cloud-direct-link#get-started-solution-to-order)
{: tip}

## Direct Link ordering process overview
{: #ordering-process-overview-dh}

Here is the general process to order a Direct Link Dedicated Hosting service:

1. Identify your colocation and connectivity requirements, and work with the {{site.data.keyword.cloud}} sales team to finalize and execute a contract and technical addendum.
1. {{site.data.keyword.cloud_notm}} runs a build order with the colocation provider for the requested environment and services. Deployment typically is completed within 30 days from when the build order is placed.
1. When the build of your colocation cage is complete, use the [IBM Cloud console ![External link icon](../../icons/launch-glyph.svg "External link icon")](/login) to order Direct Link Dedicated Hosting on Classic and complete the requested information. You can request assistance from IBM Cloud Sales engineers. When you are ready to create your order, you are prompted to read and agree to the [Direct Link Dedicated Hosting prerequisites](/docs/direct-link?topic=direct-link-ibm-cloud-dl-dedicated-hosting-prerequisites).
1. {{site.data.keyword.cloud_notm}} provides Letters of Authorization (LOA) for connections that use IBM Cloud. When you have the LOA, supply it to your colocation provider, then have them order a cross connect (and any required inter-campus connectivity) by using the {{site.data.keyword.cloud_notm}} CFA (Customer Facility Assignment) information in the LOA.

   This process usually takes 2 - 10 business days to complete, depending on the facility vendor and the order priority you specify. It includes the setup of the patch for the {{site.data.keyword.cloud_notm}} termination port.
   {: note}

1. Provide {{site.data.keyword.cloud_notm}} with the cross-connect completion notice from the facility provider in the IBM Support case.
1. {{site.data.keyword.cloud_notm}} verifies the completion notice's efficacy and orders the patch to be made from the LOA/CFA to the cross-connect router (XCR) and other gear.

Your IP assignment on the {{site.data.keyword.cloud_notm}} networking infrastructure is completed within three business days after the cross-connect is complete.

## Ordering instructions
{: #steps-to-order-direct-link-dedicated-hosting}

To provision a Direct Link Dedicated Hosting order, complete the following steps:

1. Log in to your [IBM Cloud](/login){: external} account.
1. Select the **Navigation Menu** icon ![Navigation Menu icon](images/menu_icon.png) on the upper left, then click **Classic Infrastructure** > **Direct Link**.

   The Direct Link on Classic page opens, listing existing Direct Link connections provisioned for this account.    

1. Click **Order Direct Link** in the upper right of the page. The Choose Direct Link option page is displayed.
1. Select the **Direct Link Dedicated Hosting** tile to open the order form.
1. Complete the following information to configure Direct Link Dedicated Hosting on Classic:

   - Enter a Direct Link instance name.
   - Select the location in which you want to establish the {{site.data.keyword.cloud_notm}} Direct Link connection.
   - Select the name of your network provider.
   - Select the link speed required for the connection.
   - Select the routing option required for the connection: **Local routing (free)** or **Global routing**.
   - Enter a valid BGP ASN number from the range given in the information box for the BGP exchanges.

   As you select or enter these values, you can see an approximate monthly charge in the right pane.

1. Read and agree to the [Direct Link Dedicated Hosting prerequisites](/docs/direct-link?topic=direct-link-ibm-cloud-dl-dedicated-hosting-prerequisites). Then, click **Create** to complete your order.

      After you place your order, an IBM Support case number is generated. You can click the case number to view case details

1. After you provision your direct link, see [Configuring Direct Link on Classic](/docs/direct-link?topic=direct-link-configure-ibm-cloud-direct-link) to configure your subnet to interact with IBM Cloud.

## Locations
{: #dedicated-hosting-locations}

This table shows which {{site.data.keyword.cloud_notm}} data centers are able to accept customers for Dedicated Hosting:

| Region | Site ID | City | Site Type | Site Partner |  
|-------|-------|-------|-------|-------|
| Americas | DAL09 | Richardson | DC | Digital Realty  |
| Americas | DAL12 | Richardson |	DC (AZ2) | Digital Realty  |
| Americas | DAL13 | Carrollton | DC (AZ3) | CyrusOne |
| Americas | MON01 | Drummond  | DC | Cologix  |
| Americas | SJC3 | San Jose | DC | Digital Realty  |
| Americas | SAO01 | São Paulo | DC | Ascenty  |
| Americas | SJC03 | Santa Clara | DC | Digital Realty  |
| Americas | TORO5 | Toronto | DC (AZ3) | Digital Realty |
| Americas | WDC04 | Ashburn | DC (AZ1) | Digital Realty  |
| Americas | WDC06 | Ashburn | DC (AZ3) | NTT |
| Americas | WDC07 | Ashburn | DC (AZ2) | Sabey |
|  |  |  |  |  |
| APAC | OSA21 | Osaka 21 | PoP | Digital Realty |
| APAC | SYD04 | Sydney |	DC (AZ2) |	Digital Realty  |
| APAC | SYD05 | Sydney |	DC (AZ3) |	Equinix |
| APAC | TOK02  | Koto-ku | DC (AZ1) | AT Tokyo  |
| APAC | TOK05  | Kawasaki Kangagawa  | DC (AZ3) | NTT |
|  |  |  |  |  |
| EMEA | FRA04  | Frankfurt | DC (AZ2) | NTT |
| EMEA | FRA05  | Frankfurt | DC (AZ3) | Digital Realty |
| EMEA | LON02  | Chessington | DC | Digital Realty  |
| EMEA | MIL01 | Milan | DC |	Data4 |
{: caption="Table 1: Dedicated Hosting locations" caption-side="bottom"}
