---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-02"

keywords: order, provider, capabilities, Exchange, cross-connect, locations, PoP, datacenter, data, center, pricing

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

# Ordering Direct Link Exchange on Classic
{: #how-to-order-ibm-cloud-direct-link-exchange}

As you prepare to order IBM Cloud Direct Link, review the general process your organization will follow for obtaining the Direct Link Exchange service, including the locations where each service is available, globally. When you're ready to place your order, follow the step-by-step instructions.  
{:shortdesc}

To determine which Direct Link solution is best for your networking environment, see
[How do I know which type of IBM Cloud Direct Link I need?](/docs/direct-link?topic=direct-link-get-started-with-ibm-cloud-direct-link#how-do-i-know-which-type-of-ibm-cloud-direct-link-i-need-)
{: tip}

## Direct Link ordering process overview
{: #ordering-process-overview-exchange}

Here is the general process to order a Direct Link service:

1. Verify your network provider's capabilities to reach the appropriate {{site.data.keyword.cloud_notm}} PoP.
2. Use the [IBM Cloud console ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://cloud.ibm.com) to open a Direct Link Exchange request and complete the requested information.You can request assistance from IBM Cloud Sales engineers. When you are ready to create your order, you are prompted to read and agree to the Master Service Agreement.

   If the Direct Link order is for the Equinix Cloud Exchange, the service provisioning is fully automated. This means that you can place an order for a Direct Link connection (Equinix) without opening an IBM Support case. Automation capabilities currently are limited to the Equinix Cloud Exchange.
{: note}

3. Contact your Exchange provider and negotiate connectivity to your colocation.
4. Order a virtual circuit through the Exchange provider, and refer the case ID of the {{site.data.keyword.cloud_notm}} Direct Link request as your "Request ID" or "Authorization ID".

IP assignment on the {{site.data.keyword.cloud_notm}} networking infrastructure is completed within three business days after the virtual circuit request is complete.

## Steps to order Direct Link Exchange on Classic
{: #how-to-order-cloud-exchange-no-equinix}

To provision an IBM Cloud Direct Link Exchange connection, complete the following steps. To order Direct Link Exchange for Equinix, follow [steps to order Direct Link Exchange on Classic for Equinix](/docs/direct-link?topic=direct-link-ordering-direct-link-exchange-classic#provisioning-ibm-cloud-direct-link-exchange-for-equinix).

1. Log in to your [IBM Cloud console](https://cloud.ibm.com/){: external} account and open the **Catalog.**
2. Select the **Navigation Menu** icon on the upper left, then click **on Classic Infrastructure**.
3. Select **Network > Direct Link > Exchange** to open a page that shows the existing Direct Link on Classic connections, if any.
4. Click **Order Direct Link Exchange** in the upper right of the page. The "Create an IBM Cloud Direct Link Exchange Connection" page is displayed.

   Optionally, if diverse ports are accessible, and you previously provisioned the first virtual circuit, you see a page similar to the following one, which shows two ports from which you can select your second virtual circuit. For example:<br />  
![Virtual circuit selection](/images/two_ports.png)
{: note}

5. In the order form, enter the following parameters to configure Direct Link Exchange:

  * Enter the Direct Link instance name.
  * From the list, select the location in which you want to establish the IBM Cloud Direct Link connection.
  * From the list, select the name of the network that provider you prefer.
  * Select the link speed required for the connection.
  * Select the routing option required for the connection.
  * Enter an ASN number from the range given in the information box for the BGP exchanges.

   As you select or enter these values, you can see an approximate monthly charge in the right panel.

6. You must agree to the [Master Service Agreement](https://cloud.ibm.com/classic/account/masterserviceagreement/getagreement){: external} before you can place the IBM Cloud Direct Link order.  

   After you place your order, an IBM Support case number is generated. You can click the case number to view case details.

7. You’ll be asked to complete a customer questionnaire, which you can review at [Direct Link Exchange questionnaire](/docs/direct-link?topic=direct-link-ibm-cloud-direct-link-exchange-questionnaire).

8. After you provision the direct link and complete the questionnaire, see [Configuring Direct Link on Classic](/docs/direct-link?topic=direct-link-configure-ibm-cloud-direct-link) to configure your subnet to interact with IBM Cloud.


## Steps to order Direct Link Exchange on Classic for Equinix
{: #provisioning-ibm-cloud-direct-link-exchange-for-equinix}

If the {{site.data.keyword.cloud}} Direct Link on Classic order is for the Equinix Cloud Exchange, the service provisioning is fully automated. This means that you can place an order for an {{site.data.keyword.cloud_notm}} Direct Link connection (Equinix) without opening an IBM Support case.
{:shortdesc}

Automation capabilities currently are limited to the Equinix Cloud Exchange. In subsequent releases, automation will be enabled for other providers.
{: note}

**PREREQUISITE**:
To use the automated ordering capability, your private VLANs must be associated with a VRF in the {{site.data.keyword.cloud_notm}} private network. If this requirement is not met, an IBM Support case is generated when you place the order.

1. Complete Steps 1 through 8 in [Steps to order Direct Link Exchange on Classic](/docs/direct-link?topic=direct-link-ordering-direct-link-exchange-classic#how-to-order-cloud-exchange-no-equinix).

   After you place the order, the IBM Cloud Direct Link provisioning begins. You can see the status of your connection after you place the order:

   * **Provisioned** indicates that the configuration completed on the IBM side successfully.
   * **In-Progress** indicates that the configuration is not finished.
   * **Create Failed** indicates that the configuration failed.
   * **UP** indicates that the configuration completed successfully and the BGP connection is up.

2. If the connection is in **Provisioned** status, click the name of the connection to show its details page and jot down the **Customer IP address** and **Service Key** information. This information is needed for configuring the customer edge router and as the authorization key for the cloud-provider-side (Equinix) configuration.

**Notes**:

   * For connections with **Provisioned** status, after you click the name of the connection, you'll see an error message if there is a mismatch with Peer Link Speed. When the speed is the same on the IBM side and the Equinix side, this error notification is no longer displayed.
   * For connections with **Create Failed** status, an IBM Support case is generated and further details are communicated through the case. When you expand the connection, you can see the case details.
   * For connections with **Provisioned**, **UP**, or **DOWN** status, you can **Delete** the connection by clicking the overflow in **ACTIONS** column next to the connection.
   * For connections with **Create Failed** status, you can **Cancel** the connection by clicking the **ACTIONS** column next to the connection.

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

For more information, refer to the [pricing document](/docs/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#pricing-for-direct-link-exchange).
