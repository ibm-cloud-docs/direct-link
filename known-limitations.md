---

copyright:
  years: 2017, 2024
lastupdated: "2024-09-18"

keywords:

subcollection: direct-link

---

{{site.data.keyword.attribute-definition-list}}

# Known limitations
{: #known-limitations}

First, this section covers limitations that apply to all {{site.data.keyword.cloud}} Direct Link on Classic offerings, and then it details some limitations of each offering individually.

## General IBM Cloud Direct Link on Classic limitations
{: #general-ibm-cloud-direct-link-limitations}

* Each Direct Link on Classic connection requires a unique order. If you require multiple connections, open an IBM Cloud Direct Link order for each connection.
* The {{site.data.keyword.cloud_notm}} services network is not accessible directly from your remote networks.
* {{site.data.keyword.cloud_notm}} does not permit customers to back haul traffic between their remote sites across the {{site.data.keyword.cloud_notm}} backbone. The Direct Link on Classic product is meant to let your remote networks communicate privately with your {{site.data.keyword.cloud_notm}} infrastructure.
* Direct Link on Classic requires you to use a VRF (Virtual Routing and Forwarding) instance.
* VRF is not fully compatible with the {{site.data.keyword.cloud_notm}} SSL and IPsec VPN services.
* VRF is not compatible with {{site.data.keyword.cloud_notm}} account-to-account VLAN spanning.
* Direct Link on Classic requires BGP to establish the routes to a customer's remote network.

## Direct Link Connect on Classic limitations
{: #ibm-cloud-direct-link-connect-limitations}

* Customers are responsible for any fees that are associated with reaching the PoP from a remote network and any fees that are incurred with the Cloud Connect provider.
* {{site.data.keyword.cloud_notm}} does not colocate any customer equipment in our network PoPs. Customers must work with their provider to determine whether they need to colocate any equipment in the facility where the {{site.data.keyword.cloud_notm}} network PoP exists.
* Direct Link Connect availability varies between locations. Customers can contact their IBM Cloud account manager to confirm current or future availability.

## Direct Link Dedicated on Classic limitations
{: #ibm-cloud-direct-link-dedicated-limitations}

* The {{site.data.keyword.cloud_notm}} fees for Direct Link Dedicated cover the cost of port termination on the {{site.data.keyword.cloud_notm}} infrastructure. Customers are responsible for any fees that are associated with reaching the PoP from a remote network and any cross-connects needed within the PoP facility. {{site.data.keyword.cloud_notm}} does not order a cross-connect on any customer's behalf. 
* Direct Link Dedicated is a switchport in access mode. Currently, 802.1q is not supported.
* {{site.data.keyword.cloud_notm}} does not colocate any customer equipment in our network PoPs. Customers must work with their provider to determine whether they need to colocate any equipment in the facility where the {{site.data.keyword.cloud_notm}} network PoP exists.

## Direct Link Dedicated Hosting on Classic limitations
{: #ibm-cloud-direct-link-dedicated-hosting-limitations}

* Direct Link Dedicated Hosting requires a specific contract between {{site.data.keyword.cloud_notm}} and the customer. This contract outlines the terms and conditions for the product, the pricing for the colocation environment, and the term commitment for the services. A 6-, 9-, or 12-month contract is required.
* Provider connectivity is limited to the On-Net providers of the selected data center.

## Direct Link Exchange on Classic limitations
{: #ibm-cloud-direct-link-exchange-and-direct-link-connect-limitations}

* Customers are responsible for any fees that are associated with reaching the PoP from a remote network and any fees that are incurred with the Cloud Exchange provider.
* {{site.data.keyword.cloud_notm}} does not colocate any customer equipment in our network PoPs. Customers must work with their provider to determine whether they need to colocate any equipment in the facility where the {{site.data.keyword.cloud_notm}} network PoP exists.
* Direct Link Exchange availability varies between locations. Customers can contact their IBM Cloud account manager to confirm current or future availability.
