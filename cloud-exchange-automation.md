---

copyright:
  years: 2017
lastupdated: "2017-12-01"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Order an IBM Cloud Direct Link Exchange using automation (for Equinix users)

This page tells you how to order the IBM Cloud Direct Link Exchange service. If the IBM Cloud Direct Link order is for the Equinix Cloud Exchange, the service provisioning is fully automated.

Using IBM Cloud Direct Link Exchange automation, you can place an order for an IBM Cloud Direct Link connection (Equinix) without opening an IBM support ticket.

**(Note: Automation capabilities currently are limited to the Equinix Cloud Exchange. In subsequent releases, automation will be enabled for other cloud exchange providers.)**

The automation for IBM Cloud Direct Link Exchange is supported only for accounts that do not use custom private addressing (CPA). If the IBM Cloud Direct Link connectivity is needed for a CPA account, please open an IBM support ticket.

To use the automation capability, your private VLANs must be associated with a VRF in the IBM Cloud private network. If this requirement is not met, an IBM support ticket will be generated when you place the order through the portal.

To provision an IBM Cloud Direct Link Exchange connection automatically, complete the following steps:

1. Log into your customer account on the [Customer Portal ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/).

2. Under the **Network** tab, select **Direct Link -> Exchange**, to open a page showing the existing IBM Cloud Direct Link connections, if any.

3. After clicking the **Order Direct Link Exchange** button at the top of the page, you'll see the order form where you can enter the configuration parameters for the IBM Cloud Direct Link Exchange connection.

4. In the order form, enter the following parameters to configure Direct Link:
  * Enter the IBM Cloud Direct Link connection name.
  * From the list, select the PoP location in which you want to establish the IBM Cloud Direct Link connection.
  * From the list, select the name of the Cloud Exchange provider you prefer.
  * Select the Link Speed required for the connection.
  * Select the routing option required for the connection.
  * Enter an ASN number from the range given in the information box for the BGP exchanges.
5.	As you select or enter these values, you can see an approximate monthly charge on the left-side panel.

6. After you provide the input values, the next UI screen shows the actual monthly pricing based on the options you've selected.

7. You must **AGREE** to the Terms and Conditions before you can place the IBM Cloud Direct Link order. Please read the Terms and Conditions carefully, because they contain important technical information that you must understand before proceeding. **(Note: If the terms and conditions are not accepted, an IBM support ticket will be generated upon placing the order.)**

8. Once you place the order, the IBM Cloud Direct Link provisioning begins.
9. You can see the status of your connection after you place the order. If the configuration completes on the IBM side successfully, you'll see the status as **Provisioned**. If the configuration is not finished, you'll see the status as **In-Progress**. If the configuration has failed, you'll see the status as **Failed**. If the configuration has completed successfully and the BGP connection is up, you'll see the status as **UP**.

10. If the connection is in **Provisioned** status, expand the connection by clicking the **>** in front of the connection **Name**. Then note down the **Customer IP Address**, **IBM IP Address** and **Service Key** information, which you will need for configuring the provider side (Equinix) connection.

11.	For the connections in the **Failed** status, an IBM support ticket is generated and further details will be communicated through the support ticket. When you expand the connection, you can see the support ticket details.

12. For the connections in **Provisioned**, **UP** or **DOWN** status, you can **Delete** the connection by clicking on the **ACTIONS** column next to the connection.

13. For the connections in **Failed** status, you can **Cancel** the connection by clicking on the **ACTIONS** column next to the connection.

14. If the IBM Cloud Direct Link Exchange order was placed for another provider than Equinix, an IBM support ticket is generated to continue with the service provisioning. The ticket details are displayed in the UI after you place the order. By clicking on the ticket number in the message, you can see the ticket details.

15. For the accounts with no-VRF present, the **Select VRF** field is not displayed in the order form. After placing an order in this case, an IBM support ticket is generated. The ticket number and details are shown in the UI screen after you place the order.
