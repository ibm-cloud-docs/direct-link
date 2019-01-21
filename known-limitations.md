---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-01-18"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Known Limitations

First, this section covers limitations that apply to all three {{site.data.keyword.cloud}} Direct Link offerings, and then it details some limitations of each offering individually.

## General IBM Cloud Direct Link Limitations
 * Each IBM Cloud Direct Link connection requires a unique order. If you require multiple connections, please open an IBM Cloud Direct Link order for each connection.
 * The {{site.data.keyword.BluSoftlayer_notm}} services network is not accessible directly from your remote networks.
 * {{site.data.keyword.BluSoftlayer_notm}} will not permit customers to back haul traffic between their remote sites across the {{site.data.keyword.BluSoftlayer_notm}} backbone. The IBM Cloud Direct Link product is meant to let your remote networks communicate privately with your {{site.data.keyword.BluSoftlayer_notm}} infrastructure.
 * IBM Cloud Direct Link requires you to use a VRF (Virtual Routing and Forwarding) instance.
 * VRF is not fully compatible with the {{site.data.keyword.BluSoftlayer_notm}} SSL, PPTP, and IPSec VPN services.
 * VRF is not compatible with {{site.data.keyword.BluSoftlayer_notm}} account-to-account VLAN spanning.
 * IBM Cloud Direct Link requires BGP in order to establish the routes to a customer's remote network.
 * Changes to the IBM Cloud Direct Link infrastructure must be made between 8AM and 5PM, U.S. Central time zone.
 
## IBM Cloud Direct Link Exchange and Direct Link Connect Limitations
 * Customers are responsible for any fees associated with reaching the POP from a remote network and any fees incurred with the Cloud Exchange provider.
 * {{site.data.keyword.BluSoftlayer_notm}} will not co-locate any customer equipment in our network POPs. Customers must work with their provider to determine whether they need to co-locate any equipment in the facility where the {{site.data.keyword.BluSoftlayer_notm}} network PoP exists.
 * Direct Link Cloud Exchange availability varies between locations. Customers can contact their IBM Cloud account manager to confirm current or future availability.
 
## IBM Cloud Direct Link Dedicated Limitations
 * The {{site.data.keyword.BluSoftlayer_notm}} fees for IBM Cloud Direct Link dedicated cover the cost of port termination on the {{site.data.keyword.BluSoftlayer_notm}} infrastructure. Customers are responsible for any fees associated with reaching the PoP from a remote network and any cross-connects needed within the PoP facility.  {{site.data.keyword.BluSoftlayer_notm}} will not order a cross-connect on any customer's behalf.
 * {{site.data.keyword.BluSoftlayer_notm}} will not co-locate any customer equipment in our network PoPs. Customers must work with their provider to determine whether they need to co-locate any equipment in the facility where the {{site.data.keyword.BluSoftlayer_notm}} network PoP exists.

## IBM Cloud Direct Link Dedicated Hosting Limitations
 * IBM Cloud Direct Link Dedicated Hosting requires a specific contract between {{site.data.keyword.BluSoftlayer_notm}} and the customer. This contract outlines the terms and conditions for the product, the pricing for the colocation environment, and the term commitment for the services. A 6-, 9-, or 12-month contract is required.
 * Provider connectivity is limited to the On-Net providers of the selected data center.
