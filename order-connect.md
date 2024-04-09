---

copyright:
  years: 2018, 2022
lastupdated: "2022-02-17"

keywords:

subcollection: direct-link

---

{{site.data.keyword.attribute-definition-list}}

# Ordering Direct Link Connect on Classic
{: #how-to-order-ibm-cloud-direct-link-connect-classic}
{: help}
{: support}

As you prepare to order Direct Link on Classic, review the general process that your organization follows for obtaining the Connect service, including the locations where each service is available, globally. When you're ready to place your order, follow the step-by-step instructions.
{: shortdesc}

To determine which Direct Link solution is best for your networking environment, see [How do I know which Direct Link solution to order?](/docs/direct-link?topic=direct-link-get-started-with-ibm-cloud-direct-link#get-started-solution-to-order)
{: tip}

## Direct Link ordering process overview
{: #ordering-process-overview-connect}

Here is the general process to order a Direct Link service:

 1. Verify your network provider's capabilities to reach the appropriate IBM Cloud PoP.
 2. Use the [IBM Cloud console ![External link icon](../../icons/launch-glyph.svg "External link icon")](/login) to order Direct Link Connect on Classic and complete the requested information. You can request assistance from IBM Cloud Sales engineers. When you are ready to create your order, you are prompted to read and agree to the [Direct Link Connect prerequisites](/docs/direct-link?topic=direct-link-ibm-cloud-dl-connect-prerequisites).
 3. Contact your Connect provider and negotiate connectivity to your premise or colocation.
 4. Order a virtual circuit through the Connect provider, and reference the case ID of the Direct Link Connect request as your Request ID or Authorization ID.

The IP assignment on the {{site.data.keyword.cloud_notm}} networking infrastructure is completed within three business days after the virtual circuit request is complete.

## Ordering instructions
{: #steps-to-order-direct-link-connect}

To provision a Direct Link Connect order, complete the following steps:

1. Log in to your [IBM Cloud](/login){: external} account.
1. Select the **Navigation Menu** icon ![Navigation Menu icon](images/menu_icon.png) on the upper left, then click **Classic Infrastructure** > **Direct Link**.

   The Direct Link on Classic page opens, listing existing Direct Link connections provisioned for this account.

1. Click **Order Direct Link** in the upper right of the page. The Choose Direct Link option page is displayed.
1. Select the **Direct Link Connect** tile to open the order form.
1. Complete the following information to configure Direct Link Connect:

   - Enter a Direct Link instance name.
   - Select the location in which you want to establish the Direct Link connection.
   - Select the name of your network provider.
   - Select the link speed required for the connection.
   - Select the routing option required for the connection: **Local routing (free)** or **Global routing**.
   - Enter a valid BGP ASN number from the range given in the information box for the BGP exchanges.

   As you select or enter these values, you can see an approximate monthly charge in the right pane.
   {: note}

1. Read and agree to the [Direct Link Connect prerequisites](/docs/direct-link?topic=direct-link-ibm-cloud-dl-connect-prerequisites). Then, click **Create** to complete your order.

      After you place your order, an IBM Support case number is generated. You can click the case number to view case details.

1. After you provision your direct link, see [Configuring Direct Link on Classic](/docs/direct-link?topic=direct-link-configure-ibm-cloud-direct-link) to configure your subnet to interact with IBM Cloud.

## Locations
{: #connect-classic-locations}

Our Direct Link Connect providers include these locations:

| Partners | Available Markets |
|--------------|--------------|
| Arelion | Americas: Washington DC 2 |
| Ascenty | Americas: Sao Paulo 1 |
| Bell Canada | Americas: Montreal 2, Toronto 2 |
| BNPP | EU: Paris 1 |
| British Telecom |  Americas: Washington DC 2  \n EU: Frankfurt 1, London 1, London 3 |
| CenturyLink Dynamic Connections |  Americas: San Jose 2, Toronto 2, Washington DC 2   \n EU: Frankfurt 1, London 3, Paris 2
| CenturyLink IP VPN | Americas: Dallas 3, Miami 1, Sao Paulo 2 |
| Chief Telecomm | APAC: Hong Kong 1, Taipei |
| China Unicom | APAC: Hong Kong 3 |
| Colt | APAC: Tokyo 1, Singapore 2  \n EU: Amsterdam 2, Frankfurt 1, London 1, Paris 2 |
| Cologix | Americas: Montreal 1 |
| Console Connect | Americas: Chicago 1, Miami 1, San Jose 2   \n APAC: Hong Kong 1, Osaka 1, Singapore 2, Sydney 3, Sydney 5, Tokyo 1  \n EU: London 1, Frankfurt 3, Frankfurt 5  |
| CyrusOne | Americas: Dallas 13 |
| Epsilon | APAC:  Singapore 2  \n EU: Frankfurt 1  |
| Equinix | EU: Paris 3 |
| EU Networks | EU: Frankfurt 1 |
| IBM BlueFringe | Americas: Dallas 3, Washington DC 2  \n APAC: Chennai 1  \n EU: Amsterdam 2, Frankfurt 3 |
| IBM Power Virtual Server | Americas: Dallas 12, Montreal 1, Sao Paulo 1, Toronto 1, Washington DC 4  \n APAC: Osaka 21, Sydney 4  \n EU: Frankfurt 4, Frankfurt 5, London 4, London 6  |
| Intercloud | EU: Amsterdam 2, Frankfurt 1, Frankfurt 3 |
| IXReach | Americas: Washington DC 2  \n EU: London 1 (no diversity), London 3 (no diversity) |
| Neutrona |  Americas: Dallas 3, Sao Paulo 2, Washington DC 2 |
| nextGen Global Network Peering Platform (GNPP) |  Americas: Dallas 3, Washington DC 2  \n EU: Amsterdam 2 (no diversity), Frankfurt 3, London 4 |
| NTT | APAC: Tokyo 5 |
| Orange Business Services | EU: Paris 02|
| PacketFabric | Americas: Dallas 4, San Jose 2, Washington DC 2 |
| SES Networks | Americas: Washington DC 2 |
| Softbank | APAC: Tokyo 4 |
| Tata | APAC: Chennai 1, Hong Kong 1 |
| Tokai | APAC: Osaka 1, Tokyo 3 |
| Vodafone | EU: Frankfurt 1 (no diversity), Frankfurt 3 (no diversity), London 1 (no diversity), London 3 (no diversity)  |
| Zayo | Americas: Dallas 3, Toronto 2, Washington DC 2 |
{: caption="Table 1: Direct Link Connect provider locations" caption-side="bottom"}
