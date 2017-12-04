---

copyright:
  years: 2017
lastupdated: "2017-12-04"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Order IBM Cloud Direct Link

To order the type of IBM Cloud Direct Link that best suits your needs, follow the link to see instructions.

* [How to order IBM Cloud Direct Link Exchange](how-to-order.html#how-to-order-ibm-cloud-direct-link-exchange)
* [How to order IBM Cloud Direct Link Dedicated](how-to-order.html#how-to-order-ibm-cloud-direct-link-dedicated)
* [How to order IBM Cloud Direct Link Dedicated Hosting](how-to-order.html#how-to-order-ibm-cloud-direct-link-dedicated-hosting)

## How to order IBM Cloud Direct Link Exchange

 * Verify your network provider's capabilities to reach the appropriate PoP and cross-connect into the associated Cloud Exchange provider.
<<<<<<< HEAD
 * Use the [Customer Portal ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/) to open an IBM Cloud Direct Link Exchange request and complete the requested information. (Assistance from IBM sales engineers can be requested.) If you use the Equinix provider, the ordering and provisioning process is [fully automated](https://github.ibm.com/Bluemix-Docs/direct-link/blob/staging/cloud-exchange-automation.md).
 * Contact your Exchange provider and negotiate connectivity to your exchange.
 * Order connectivity between your network provider and the  Exchange provider.
 * Order a "virtual circuit" through the Exchange provider, and refer the Ticket ID of the {{site.data.keyword.BluSoftlayer_notm}} IBM Cloud Direct Link request as your "Request ID" or "Authorization ID"
=======
 * Use the [Customer Portal ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/) to open a Direct Link Cloud Exchange request and complete the requested information. (Assistance from IBM sales engineers can be requested.) 
 * Contact the Cloud Exchange provider and negotiate connectivity to your exchange.
 * Order connectivity between your network provider and the Cloud Exchange provider.
 * Order a "virtual circuit" through the Cloud Exchange provider, and refer the Ticket ID of the {{site.data.keyword.BluSoftlayer_notm}} Direct Link request as your "Request ID" or "Authorization ID"
>>>>>>> 224d6c71057bf300385a74b93be36ff063e6db39
 * IP assignment on the {{site.data.keyword.BluSoftlayer_notm}} networking infrastructure will be completed within 3 business days after the virtual circuit request is complete.

## How to order IBM Cloud Direct Link Dedicated

 * Verify your network provider's capabilities to reach the appropriate PoP and cross-connect into the {{site.data.keyword.BluSoftlayer_notm}} environment.
 * Open a IBM Cloud Direct Link Dedicated request and complete the requested information. (Assistance from IBM sales engineers can be requested.)
 * {{site.data.keyword.BluSoftlayer_notm}} provides the Letter of Authorization (LOA) for the connection.
 * Confirm that your circuit has reached the PoP and has been completed by the carrier.
 * Order the cross-connect using the {{site.data.keyword.BluSoftlayer_notm}} CFA (Customer Facility Assignment) information in the LOA, which usually takes between 2 and 10 business days to complete. (This timeframe depends upon the facilty vendor and the type of order priority as it is placed by the customer.) This process includes setting up the patch to the {{site.data.keyword.BluSoftlayer_notm}} termination port.
 * Provide {{site.data.keyword.BluSoftlayer_notm}} with the cross-connect completion notice from the facility provider in the {{site.data.keyword.BluSoftlayer_notm}} portal ticket.
 * {{site.data.keyword.BluSoftlayer_notm}} will verify the completion notice's efficacy and order the patch to be made from the LOA/CFA to the cross-connect router (XCR) and other gear.
 * Your IP assignment on the {{site.data.keyword.BluSoftlayer_notm}} networking infrastructure will be completed within 3 business days after the cross-connect is complete.

## How to order IBM Cloud Direct Link Dedicated Hosting

 * Identify your colocation and connectivity requirements, and work with the IBM sales team to finalize and execute a contract and technical addendum.
 * {{site.data.keyword.BluSoftlayer_notm}} executes a build order with the colocation provider for the requested environment and services. Deployment typically is completed within 30 days from when the build order is placed.
 * When the build of your colocation cage is complete, the process to interconnect between your colocation cage and the {site.data.keyword.BluSoftlayer_notm}} POD environment's XCR gear will follow the previously-shown IBM Cloud Direct Link Dedicated process, starting at Step 3.
