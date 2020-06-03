---

copyright:
  years: 2018, 2020
lastupdated: "2020-05-19"

keywords: order, provider, capabilities, Connect, cross-connect, locations, PoP, datacenter, data, center, pricing, virtual circuit, Request ID, Authorization ID

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

# Ordering Direct Link Connect on Classic
{: #how-to-order-ibm-cloud-direct-link-connect-classic}
{: help}
{: support}

As you prepare to order Direct Link on Classic, review the general process your organization will follow for obtaining the Connect service, including the locations where each service is available, globally. When you're ready to place your order, follow the step-by-step instructions.  
{:shortdesc}

To determine which Direct Link solution is best for your networking environment, see [How do I know which Direct Link solution to order?](/docs/direct-link?topic=direct-link-get-started-with-ibm-cloud-direct-link#get-started-solution-to-order)
{: tip}

## Direct Link ordering process overview
{: #ordering-process-overview-connect}

Here is the general process to order a Direct Link service:

 1. Verify your network provider's capabilities to reach the appropriate IBM Cloud PoP.
 2. Use the [IBM Cloud console ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://cloud.ibm.com) to order Direct Link Connect on Classic and complete the requested information. You can request assistance from IBM Cloud Sales engineers. When you are ready to create your order, you are prompted to read and agree to the Master Service Agreement.
 3. Contact your Connect provider and negotiate connectivity to your premise or colocation.
 4. Order a virtual circuit through the Connect provider, and reference the case ID of the Direct Link Connect request as your Request ID or Authorization ID.

The IP assignment on the {{site.data.keyword.cloud_notm}} networking infrastructure is completed within three business days after the virtual circuit request is complete.

## Steps to order Direct Link Connect on Classic
{: #steps-to-order-direct-link-connect}

To provision a Direct Link Connect order, complete the following steps:

1. Log in to your [IBM Cloud](https://cloud.ibm.com/){: external} account and open the **Catalog**.
2. Select the **Navigation Menu** icon ![Navigation Menu icon](images/menu_icon.png) on the upper left, then click **Classic Infrastructure**.
2. Select **Network > Direct Link > Connect** to open a page that shows the existing Direct Link connections, if any.
3. Click **Order Direct Link Connect +** in the upper right of the page. The "Create an IBM Cloud Direct Link Connect Connection" page is displayed.
4. In the order form, complete the following information to configure Direct Link Connect:
   - Enter the Direct Link instance name.
   - From the list, select the location in which you want to establish the {{site.data.keyword.cloud_notm}} Direct Link connection.
   - From the list, select the name of the network provider that you prefer.
   - Select the link speed required for the connection.
   - Select the routing option required for the connection.
   - Enter a valid ASN number from the range given in the information box for the BGP exchanges.

   As you select or enter these values, you can see an approximate monthly charge in the right panel.

6. You must agree to the [Master Service Agreement](https://cloud.ibm.com/classic/account/masterserviceagreement/getagreement){: external} before you can place the IBM Cloud Direct Link order.  

      After you place your order, an IBM Support case number is generated. You can click the case number to view case details.

7. You’ll be asked to complete a customer questionnaire, which you can review at [Direct Link Connect questionnaire](/docs/direct-link?topic=direct-link-ibm-cloud-direct-link-connect-classic-questionnaire).

8. After you provision the direct link and complete the questionnaire, see [Configuring Direct Link on Classic](/docs/direct-link?topic=direct-link-configure-ibm-cloud-direct-link) to configure your subnet to interact with IBM Cloud.


## Locations
{: #connect-classic-locations}

Our Direct Link Connect providers include these locations:

| Partners | Available Markets |
|--------------|--------------|
| AT&T NetBond® for Cloud |  **Americas:** Dallas 3, San Jose 2 (no diversity: on same XCR),  Washington DC 2 (no diversity: on same XCR)<br /> **EU:** Frankfurt 1, London 1 |
| AT&T Cloud Gateway (formerly known as RedFringe)| Dallas 3, Washington DC 2 |
| Bell Canada | Montreal 2, Toronto 2 |
| British Telecom |   Frankfurt 1, London 1, Sao Paulo 2, Washington DC 2|
| CenturyLink IP VPN | Dallas 3, Miami 1, Sao Paulo 2 |
| CenturyLink Dynamic Connections |  **Americas:** San Jose 2, Toronto 2, Washington DC 2 <br />**EU:** Frankfurt 1, London 3, Paris 2
| Chief Telecomm | Hong Kong 1 |
| China Unicom | Hong Kong 3 |
| Colt | **APAC:** Tokyo 1, Singapore 2 <br />**EU:** Amsterdam 2, Frankfurt 1, London 1, Paris 2 |
| Console Connect by PCCW | **Americas:** San Jose 2<br />**APAC:** Hong Kong 1, Singapore 2, Tokyo 1<br />**EU:** London 1, Frankfurt 3  |
| Digital Realty Service Exchange |	Supported by Megaport in <br />**Americas:** Dallas 3, San Jose 2, Toronto 2, Washington DC 2<br />**EU:** Amsterdam 2, Frankfurt 1, London 3, Stockholm 1 |
| Epsilon | **APAC:**  Singapore 2<br />**EU:** Frankfurt 1  |
| EU Networks | Frankfurt 1 |
| IBM BlueFringe | Chennai 1 , Dallas 3, Washington DC 2 |
| IBM Power Virtual Server | **Americas:** Toronto 1, Washington DC 4<br />**EU:** Frankfurt 4, Frankurt 5, London 6  |
| Intercloud | Amsterdam 2, Frankfurt 1, Frankfurt 3 |
| IXReach | **Americas:** Washington DC 2 <br />**EU:** London 1 (no diversity), London 3 (no diversity) |
| Megaport | **Americas:** Chicago 1, Dallas 4, San Jose 2 (no diversity),  Toronto 2 (no diversity), Washington DC 2<br />**APAC:** Tokyo 2, Tokyo 3, Melbourne 2, Singapore 2, Sydney 2,Hong Kong 1 (no diversity)<br />**EU:** Amsterdam 2 (no diversity), Frankfurt 1 (no diversity), London 3 (no diversity), Paris 2,  Stockholm 1 (no diversity) |
| MWS GNPP |  **Americas:** Dallas 3, Washington DC 2<br />**EU:** Amsterdam 2 (no diversity), Frankfurt 3 |
| Neutrona |  Dallas 3, Sao Paulo 2, Washington DC 2 |
| NTT | Tokyo 5 |
| Orange Business Services | Paris 02|
| PacketFabric | Dallas 4, San Jose 2, Washington DC 2 |
| Softbank | Tokyo 4 |
| SES Networks | Washington DC 2 |
| Tata | Chennai 1, Hong Kong 1 |
| Telia | Stockholm 1 |
| Telstra | Melbourne 2, Sydney 2 |
| Tokai | Tokyo 3, Osaka 1 |
| Verizon SCI |  **Americas:** Dallas 3, San Jose 2, Washington DC 2<br />**APAC:**  Sydney 2 , Tokyo 1  <br />**EU:** Amsterdam 2, Frankfurt 1 |
| Vodafone | Frankfurt 1 (no Diversity), London 1 (no Diversity), London 3 (no Diversity)  |
| Zayo | Dallas 3,  Toronto 2, Washington DC 2 |


## Pricing
{: #connect-pricing}

For more information, refer to the **Connect on Classic** tab in the [pricing table](/docs/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link).
