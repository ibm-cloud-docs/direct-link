---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-02"

keywords: provisioning, order, Exchange, Equinix, automated, status, connection

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


# Provisioning IBM Cloud Direct Link Exchange for Equinix
{: #provisioning-ibm-cloud-direct-link-exchange-for-equinix}

If the {{site.data.keyword.cloud}} Direct Link order is for the Equinix Cloud Exchange, the service provisioning is fully automated, which means that you can place an order for an {{site.data.keyword.cloud_notm}} Direct Link connection (Equinix) without opening an IBM support ticket.

Automation capabilities currently are limited to the Equinix Cloud Exchange. In subsequent releases, automation will be enabled for other providers.
{:note}

## Prerequisites
{: #cloud-exchange-equinix-prerequisites}

To use the automated ordering capability, your private VLANs must be associated with a VRF in the {{site.data.keyword.cloud_notm}} private network. If this requirement is not met, an IBM support ticket will be generated when you place the order through the Customer Portal.

## Steps for ordering and provisioning
{: #cloud-exchange-steps-for-ordering-and-provisioning}

**Step 1:**

Follow the steps from 1 through 7 from the regular [Cloud Exchange ordering steps](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange).

**Step 2:**

Once you place the order, the IBM Cloud Direct Link provisioning begins.

You can see the status of your connection after you place the order. If the configuration completes on the IBM side successfully, you'll see the status as **Provisioned**. If the configuration is not finished, you'll see the status as **In-Progress**. If the configuration has failed, you'll see the status as **Create Failed**. If the configuration has completed successfully and the BGP connection is up, you'll see the status as **UP**.

![Step 9 in progress](/images/pup_exchange_equinix_inProgress.png)

**Step 3:**

If the connection is in **Provisioned** status, click on the connection Name by clicking the **<connection_name>** link.  It should navigate to details page.

![Step 10](/images/pup_exchange_equinix_provisioned.png)

The following figure shows various states of the connection after the order is placed:

![Step 9 up](/images/pup_exchange_equinix_up.png)

**Step 4:**

Note down the **Customer IP Address** and **Service Key** information. These will be needed for configuring the customer edge router and as the authorization key for the cloud-provider-side (Equinix) configuration, respectively.

![Step 9 up](/images/pup_exchange_equinix_provisioned_details.png)

**Step 5:**

For the connections in **Provisioned** status, after clicking on the connection Name by clicking the **<connection_name>**, you'll see an error message if there is a mismatch with Peer Link Speed. Once the Speed is the same on the IBM side and the Equinix Side, this Error notification is no longer displayed.

![Step 11](/images/pup_exchange_equinix_provisioned_details_portSpeedMismatch.png)

**Step 6:**

For the connections in the **Create Failed** status, an IBM support ticket is generated and further details are communicated through the support ticket. When you expand the connection, you can see the support ticket details.

![Step 12](/images/pup_exchange_equinix_list_createFailed.png)

**Step 7:**

For the connections in **Provisioned**, **UP** or **DOWN** status, you can **Delete** the connection by clicking on the overflow in **ACTIONS** column next to the connection.

![Step 13](/images/pup_exchange_equinix_list_delete.png)

**Step 8:**

For the connections in **Create Failed** status, you can **Cancel** the connection by clicking on the **ACTIONS** column next to the connection.

![Step 14](/images/pup_exchange_equinix_list_delete.png)