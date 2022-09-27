---

copyright:
  years: 2017, 2022
lastupdated: "2022-02-17"

keywords: 

subcollection: direct-link

---

{{site.data.keyword.attribute-definition-list}}

# Ordering Direct Link Exchange on Classic
{: #how-to-order-ibm-cloud-direct-link-exchange}
{: help}
{: support}

As you prepare to order Direct Link on Classic, review the general process that your organization follows for obtaining the Exchange service, including the locations where each service is available, globally. When you're ready to place your order, follow the step-by-step instructions.  
{: shortdesc}

To determine which Direct Link solution is best for your networking environment, see
[How do I know which type of IBM Cloud Direct Link I need?](/docs/direct-link?topic=direct-link-get-started-with-ibm-cloud-direct-link#get-started-solution-to-order)
{: tip}

## Direct Link ordering process overview
{: #ordering-process-overview-exchange}

Here is the general process to order a Direct Link service:

1. Verify your network provider's capabilities to reach the appropriate {{site.data.keyword.cloud_notm}} PoP.
2. Use the [IBM Cloud console ![External link icon](../../icons/launch-glyph.svg "External link icon")](/login) to open a Direct Link Exchange request and complete the requested information. You can request assistance from IBM Cloud Sales engineers. When you are ready to create your order, you are prompted to read and agree to the [Direct Link Exchange prerequisites](/docs/direct-link?topic=direct-link-ibm-cloud-dl-exchange-prereqs).

   If the Direct Link order is for the Equinix Cloud Exchange, the service provisioning is fully automated. This means that you can place an order for a Direct Link connection (Equinix) without opening an IBM Support case. Automation capabilities currently are limited to the Equinix Cloud Exchange.
{: note}

3. Contact your Exchange provider and negotiate connectivity to your colocation.
4. Order a virtual circuit through the Exchange provider, and reference the case ID of the {{site.data.keyword.cloud_notm}} Direct Link request as your Request ID or Authorization ID.

IP assignment on the {{site.data.keyword.cloud_notm}} networking infrastructure is completed within three business days after the virtual circuit request is complete.

## Ordering instructions
{: #how-to-order-cloud-exchange-no-equinix}

To provision an IBM Cloud Direct Link Exchange connection, complete the following steps. To order Direct Link Exchange for Equinix, follow [Steps to order Direct Link Exchange on Classic for Equinix](/docs/direct-link?topic=direct-link-how-to-order-ibm-cloud-direct-link-exchange#provisioning-ibm-cloud-direct-link-exchange-for-equinix).

1. Log in to your [IBM Cloud console](/login){: external} account.
1. Select the **Navigation Menu** icon ![Navigation Menu icon](images/menu_icon.png) on the upper left, then click **Classic Infrastructure** > **Direct Link**.

   The Direct Link on Classic page opens, listing existing Direct Link connections provisioned for this account.    
   
1. Click **Order Direct Link** in the upper right of the page. The Choose Direct Link option page is displayed.

   ![Choose Direct Link option](/images/choose-direct-link-exchange.png){: caption="Choose Direct Link option" caption-side="bottom"}    
   
1. Select the **Direct Link Exchange** tile to open the order form. 

   Optionally, if diverse ports are accessible, and you previously provisioned the first virtual circuit, you see a page similar to the following one, which shows two ports from which you can select your second virtual circuit. For example:  /n
   ![Virtual circuit selection](/images/two_ports.png){: caption="Virtual circuit selection" caption-side="bottom"}
   {: note}

1. In the order form, complete following information to configure Direct Link Exchange:

   * Enter a Direct Link instance name.
   * Choose the location in which you want to establish the IBM Cloud Direct Link connection.
   * Select the name of your network provider.
   - Select the routing option required for the connection: **Local routing (free)** or **Global routing**. 
   * Enter a BGP ASN number from the range given in the information box for the BGP exchanges.

   As you complete these values, you can see an approximate monthly charge in the right Summary pane.

1. Read and agree to the [Direct Link Exchange prerequisites](/docs/direct-link?topic=direct-link-ibm-cloud-dl-exchange-prereqs). Then, click **Create** to complete your order.

   After you complete your order, an IBM Support case number is generated. Click the case number to view case details.

1. After you provision your direct link, see [Configuring Direct Link on Classic](/docs/direct-link?topic=direct-link-configure-ibm-cloud-direct-link) to configure your subnet to interact with IBM Cloud.

## Ordering instructions for the Equinix Cloud Exchange
{: #provisioning-ibm-cloud-direct-link-exchange-for-equinix}

If the {{site.data.keyword.cloud}} Direct Link on Classic order is for the Equinix Cloud Exchange, the service provisioning is fully automated. This means that you can place an order for an {{site.data.keyword.cloud_notm}} Direct Link connection (Equinix) without opening an IBM Support case.
{: shortdesc}

**PREREQUISITE**: To use the automated ordering capability, your private VLANs must be associated with a VRF in the {{site.data.keyword.cloud_notm}} private network. If this requirement is not met, an IBM Support case is generated when you place the order.

To order Direct Link Exchange on Classic for Equinix, follow these steps:

1. Log in to the Equinix Cloud Exchange (ECX) Fabric portal.
   * Navigate to [https://ecxfabric.equinix.com](https://ecxfabric.equinix.com).
   * Enter your username and password.
   * Click **Sign In**.   
1. In the Frequent Connections section, click the **IBM Cloud** tile.
1. In the **IBM Cloud Direct Link Exchange** profile, click **Create Connection**.

   ![Equinix ordering](/images/equinix-ibm-cloud-2.png "Equinix ordering"){: caption="Equinix ordering" caption-side="bottom"}

1. In the Origin section, click **Port**.

   ![Select a Port, Location, and Destination](/images/equinix-port.png "Select a Port, Location, and Destination"){: caption="Select a Port, Location, and Destination" caption-side="bottom"}   

1. Select a **Location**, followed by a **Destination**. Then, click **Next**.  
1. On the Connection Details page, enter the connection information. For Account ID, enter the Classic Softlayer Account ID (for example, `114340xxx`). This is the unique account ID that was initially created to start using IBM Cloud. 
1. Select a **Connection Speed**, then click **Next**.   
1. Review and click **Submit Your Order**.
1. Return to the [IBM Cloud Direct Link Exchange page](/classic/network/directlink/exchange) in the IBM Cloud console. Notice that the connection status for your direct link connection states **Create Approval Pending**.
1. Open the Actions ![Actions menu](/images/overflow.png) menu and click **Accept**.

      ![Equinix request approval pending](/images/equinix-request-pending.png){: caption="Equinix request approval pending" caption-side="bottom"}   

      The virtual connection shows as **Provisioned** in the Equinix Fabric portal.   

1. Review your order summary, agree to the [Direct Link Exchange prerequisites](/docs/direct-link?topic=direct-link-ibm-cloud-dl-exchange-prereqs), and then click **Create**.

      ![Equinix order summary pane](/images/equinix-order-summary.png){: caption="Equinix order summary pane" caption-side="bottom"}

The timeline for approval is within 24 hours. If the 24-hour Service Level Agreement (SLA) is not acceptable, you can [create an IBM Support case](/unifiedsupport/cases/form) and request that it be routed to the SNS team.
{: note}

## Ordering Direct Link Exchange on Classic when there is no VRF present
{: #how-to-order-exchange-when-there-is-no-vrf-present}

For the accounts with no Virtual Routing and Forwarding (VRF) present, the **Select VRF** field is not displayed in the order form. In this situation, an IBM Support case is generated after you place your order. The case number and details are shown in the IBM Cloud console after you place the order.
{: shortdesc}

## Locations
{: #exchange-locations}

 This table shows which {{site.data.keyword.cloud_notm}} data centers offer Direct Link Exchange connectivity:

| Exchange Provider	| IBM Data Center Code |
|-------------|-----------------------|
| AT Tokyo | Tokyo 2 |
| Ascenty | Sao Paulo 1 |
| Cologix | Montreal 2, Toronto 2 |
| Cyrus One | Dallas 13 |
| DE-CIX | Frankfurt 3 |
| Equinix | Americas: Chicago 1, Dallas 3, New York City 2*, New York City 3*, Sao Paulo 2, San Jose 2, Toronto 2, Toronto 3, Washington DC  \n APAC: Hong Kong 1, Osaka 1, Singapore 2, Sydney 2, Tokyo 1, Tokyo 3  \n  EU: Amsterdam 2, Frankfurt 3, London 1, London 3, Paris 2  |	
| InterXion | Frankfurt 1, Stockholm 1 |
| KINX	| Seoul 2 |
| NextDC | Melbourne 2, Sydney 3 |
{: caption="Table 1: Data centers that offer Direct Link Exchange connectivity" caption-side="bottom"}

* NYC02 and NYC03 connect to the IBM Cloud backbone through NYC1. The primary reason for these PoPs is to extend connectivity to different site providers from our NYC01 site. When planning your diversity strategy, keep in mind that traffic for NYC02 and NYC03 have a single, shared path to the IBM network.

## Pricing
{: #exchange-pricing}

For more information, see the **Exchange on Classic** tab in the [pricing table](/docs/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link).
