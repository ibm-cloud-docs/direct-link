---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-02"

keywords: provisioning, Exchange, order, support, ticket, diverse, virtual circuit, parameters, Terms and Conditions

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
{:external: target="_blank" .external}

# Provisioning IBM Cloud Direct Link Exchange
{: #provisioning-ibm-cloud-direct-link-exchange}

This page tells you how to order the {{site.data.keyword.cloud}} Direct Link Exchange service. If the {{site.data.keyword.cloud_notm}} Direct Link order is for the Equinix Cloud Exchange, the service provisioning is fully automated, which means that you can [place an order for an IBM Cloud Direct Link connection (Equinix) without opening an IBM support ticket](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix) as described in a related document.

Automation capabilities currently are limited to the Equinix Cloud Exchange. In subsequent releases, automation will be enabled for other providers.
{:note}

## Prerequisites
{: #cloud-exchange-prerequisites}

To use the automation capability, your private VLANs must be associated with a VRF in the {{site.data.keyword.cloud_notm}} private network. If this requirement is not met, an IBM support ticket will be generated when you place the order through the Customer Portal.

 * [How to order Cloud Exchange](#how-to-order-cloud-exchange-no-equinix)
 * [How to order Cloud Exchange for Equinix](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix)

## How to order Cloud Exchange
{: #how-to-order-cloud-exchange-no-equinix}

To provision an IBM Cloud Direct Link Exchange connection, complete the following steps:

**Step 1:**

Log into your customer account on the [IBM Cloud console](https://cloud.ibm.com/){: external}.

**Step 2:**

Go to **Classic Infrastructure** > **Network** > **Direct Link** > **Exchange**, to open a page showing the existing IBM Cloud Direct Link connections, if any.

![Step 2](/images/pup_exchange_list.png)

**Step 3:**

After clicking the **Order Direct Link Exchange** button at the top of the page, you'll see the order form where you can enter the configuration parameters for the IBM Cloud Direct Link Exchange connection.

![Step 3](/images/pup_exchange_create_default.png)

**Step 3A:**

Optionally, if Diverse ports are accessible, and you've previously provisioned the first Virtual Circuit, you'll see a screen similar to the following one, showing two ports, from which you can select your second Virtual Circuit.

![2-port-image](/images/pup_exchange_create_ports.png)

**Step 4:**

In the order form, enter the following parameters to configure Direct Link:
  * Enter the IBM Cloud Direct Link connection name.
  * From the list, select the location in which you want to establish the IBM Cloud Direct Link connection.
  * From the list, select the name of the Cloud Exchange provider you prefer.
  * Select the Link Speed required for the connection.
  * Select the routing option required for the connection.
  * Enter an ASN number from the range given in the information box for the BGP exchanges.

**Step 5:**

As you select or enter these values, you can see an approximate monthly charge on the right-side panel.

![Step 4-5](/images/pup_exchange_create_prices.png)

**Step 6.**

The form fields are validated as you provide the inputs.
You must **AGREE** to the Terms and Conditions for the "Create" button to be enabled.

**Step 7:**

After agreeing to the terms and conditions, when you place the order, an IBM support ticket is generated after placing the order to continue with the service provisioning. The ticket number will be displayed in the UI after you place the order.

![Step NE1](/images/pup_exchange_ticket_notification.png)

**Step 8:**

By clicking on the ticket number in the message, you can see the ticket details.

![Step NE2](/images/pup_exchange_ticket_details.png)
