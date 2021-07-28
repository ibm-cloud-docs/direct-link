---

copyright:
  years: 2017, 2021
lastupdated: "2021-01-28"

keywords: provider, cross-connect, locations, PoP, data center
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

# Ordering Direct Link Exchange on Classic
{: #how-to-order-ibm-cloud-direct-link-exchange}
{: help}
{: support}

As you prepare to order Direct Link on Classic, review the general process that your organization follows for obtaining the Exchange service, including the locations where each service is available, globally. When you're ready to place your order, follow the step-by-step instructions.  
{:shortdesc}

To determine which Direct Link solution is best for your networking environment, see
[How do I know which type of IBM Cloud Direct Link I need?](/docs/direct-link?topic=direct-link-get-started-with-ibm-cloud-direct-link#get-started-solution-to-order)
{: tip}

## Direct Link ordering process overview
{: #ordering-process-overview-exchange}

Here is the general process to order a Direct Link service:

1. Verify your network provider's capabilities to reach the appropriate {{site.data.keyword.cloud_notm}} PoP.
2. Use the [IBM Cloud console ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://cloud.ibm.com) to open a Direct Link Exchange request and complete the requested information. You can request assistance from IBM Cloud Sales engineers. When you are ready to create your order, you are prompted to read and agree to the Master Service Agreement.

   If the Direct Link order is for the Equinix Cloud Exchange, the service provisioning is fully automated. This means that you can place an order for a Direct Link connection (Equinix) without opening an IBM Support case. Automation capabilities currently are limited to the Equinix Cloud Exchange.
{: note}

3. Contact your Exchange provider and negotiate connectivity to your colocation.
4. Order a virtual circuit through the Exchange provider, and refer the case ID of the {{site.data.keyword.cloud_notm}} Direct Link request as your Request ID or Authorization ID.

IP assignment on the {{site.data.keyword.cloud_notm}} networking infrastructure is completed within three business days after the virtual circuit request is complete.

## Steps to order Direct Link Exchange on Classic
{: #how-to-order-cloud-exchange-no-equinix}

To provision an IBM Cloud Direct Link Exchange connection, complete the following steps. To order Direct Link Exchange for Equinix, follow [steps to order Direct Link Exchange on Classic for Equinix](/docs/direct-link?topic=direct-link-how-to-order-ibm-cloud-direct-link-exchange#provisioning-ibm-cloud-direct-link-exchange-for-equinix).

1. Log in to your [IBM Cloud console](https://cloud.ibm.com/){: external} account and open the **Catalog.**
2. Select the **Navigation Menu** icon on the upper left, then click **Classic Infrastructure**.
3. Select **Network > Direct Link > Exchange** to open the IBM Cloud Direct Link Exchange dashboard, which shows existing direct links, if any.
4. Click **Order Direct Link Exchange** in the upper right of the page. The "Create an IBM Cloud Direct Link Exchange Connection" page is displayed.

   Optionally, if diverse ports are accessible, and you previously provisioned the first virtual circuit, you see a page similar to the following one, which shows two ports from which you can select your second virtual circuit. For example:<br />  
![Virtual circuit selection](/images/two_ports.png)
{: note}

5. In the order form, complete following information to configure Direct Link Exchange:

  * Enter a Direct Link instance name.
  * Choose the location in which you want to establish the IBM Cloud Direct Link connection.
  * Select the name of your network provider.
  * Choose a link speed for the connection. 
  * Select either Local or Global routing for the connection.
  * Enter an ASN number from the range given in the information box for the BGP exchanges.

   As you complete these values, you can see an approximate monthly charge in the right Summary pane.

6. Agree to the [Master Service Agreement](https://cloud.ibm.com/classic/account/masterserviceagreement/getagreement){: external} so that you can place your Direct Link Exchange order.  

   After you complete your order, an IBM Support case number is generated. Click the case number to view case details.

7. You’ll be asked to complete a customer questionnaire, which you can review at [Direct Link Exchange questionnaire](/docs/direct-link?topic=direct-link-ibm-cloud-direct-link-exchange-questionnaire).

8. After you provision the direct link, see [Configuring Direct Link on Classic](/docs/direct-link?topic=direct-link-configure-ibm-cloud-direct-link) to configure your subnet to interact with IBM Cloud.

## Steps to order Direct Link Exchange on Classic for Equinix
{: #provisioning-ibm-cloud-direct-link-exchange-for-equinix}

If the {{site.data.keyword.cloud}} Direct Link on Classic order is for the Equinix Cloud Exchange, the service provisioning is fully automated. This means that you can place an order for an {{site.data.keyword.cloud_notm}} Direct Link connection (Equinix) without opening an IBM Support case.
{:shortdesc} 

**PREREQUISITE**:
To use the automated ordering capability, your private VLANs must be associated with a VRF in the {{site.data.keyword.cloud_notm}} private network. If this requirement is not met, an IBM Support case is generated when you place the order.

To order Direct Link Exchange on Classic for Equinix, follow these steps:

1. Log in to the Equinix Cloud Exchange (ECX) Fabric portal.
   * Navigate to [https://ecxfabric.equinix.com](https://ecxfabric.equinix.com).
   * Enter your username and password.
   * Click **Sign In**.   
1. In the Frequent Connections section, click the **IBM Cloud** tile.
1. In the **IBM Cloud Direct Link Exchange** profile, click **Create Connection**.

   ![Equinix ordering](/images/equinix-ibm-cloud-2.png "Equinix ordering")
1. In the Origin section, click **Port**.

   ![Select a Port, Location, and Destination](/images/equinix-port.png "Select a Port, Location, and Destination")   
1. Select a **Location**, followed by a **Destination**. Then, click **Next**.  
1. On the Connection Details page, enter the connection information. For Account ID, enter the Classic Softlayer Account ID (for example, `114340xxx`) that was generated when you provisioned your direct link. This key can be found on the Direct Link details page. 
1. Select a **Connection Speed**, then click **Next**.   
1. Review and click **Submit Your Order**. 
1. Return to the [IBM Cloud Direct Link Exchange page](https://cloud.ibm.com/classic/network/directlink/exchange) in the IBM Cloud console. Notice that the connection status for your direct link connection states **Create Approval Pending**. 
1. Open the Actions ![Actions menu](/images/overflow.png) menu and click **Accept**.
    
      ![Equinix request approval pending](/images/equinix-request-pending.png)      
      The virtual connection shows as **Provisioned** in the Equinix Fabric portal.      
1. Review your order summary, agree to the [Master Service Agreement](https://cloud.ibm.com/classic/account/masterserviceagreement/getagreement){: external}, and then click **Create**.

      ![Equinix order summary pane](/images/equinix-order-summary.png)

The timeline for approval is within 24 hours. If the 24-hour Service Level Agreement (SLA) is not acceptable, you can [create an IBM Support case](https://cloud.ibm.com/unifiedsupport/cases/form) and request that it be routed to the SNS team. 
{: note}
  
## Ordering Direct Link Exchange on Classic when there is no VRF present
{: #how-to-order-exchange-when-there-is-no-vrf-present}

For the accounts with no Virtual Routing and Forwarding (VRF) present, the **Select VRF** field is not displayed in the order form. In this situation, an IBM Support case is generated after you place your order. The case number and details are shown in the IBM Cloud console after you place the order.
{:shortdesc}

## Locations
{: #exchange-locations}

 This table shows which {{site.data.keyword.cloud_notm}} data centers offer Direct Link Exchange connectivity:

| Exchange Provider	| IBM Data Center Code |
|-------------|-----------------------|
| AT Tokyo | Tokyo 2 |
| Ascenty | Sao Paulo 1* |
| Cologix | Montreal 2, Toronto 2 |
| Cyrus One | Dallas 13 |
| DE-CIX | Frankfurt 3 |
| Equinix | **APAC:** Hong Kong 1, Osaka 1, Singapore 2, Sydney 2, Tokyo 1, Tokyo 3<br />**EU:** Amsterdam 2, Frankfurt 3, London 1, London 3, Paris 2<br />**Americas:** Chicago 1, Dallas 3, New York City 2, New York City 3, Sao Paulo 2, San Jose 2, Toronto 2, Washington DC 2 |							
| InterXion | Frankfurt 1, Stockholm 1 |
| KINX	| Seoul 2 |
| NextDC | Melbourne 2, Sydney 3 |
| SK C&C | Seoul 1 |

## Pricing
{: #exchange-pricing}

For more information, see the **Exchange on Classic** tab in the [pricing table](/docs/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link).
