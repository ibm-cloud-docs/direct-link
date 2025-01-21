---

copyright:
  years: 2017, 2025
lastupdated: "2019-12-02"

keywords: 

subcollection: direct-link

---

{{site.data.keyword.attribute-definition-list}}

# Converting to virtual routing and forwarding
{: #what-happens-during-the-account-conversion-process}

Many {{site.data.keyword.cloud}} customers currently operate with a shared tenancy model on the {{site.data.keyword.cloud_notm}} network. During conversion, your shared tenancy is converted to use a customer VRF, most commonly with a new Direct Link on Classic subscription.
{: shortdesc}

A "customer VRF" refers to multiple isolation network connectivity. For more information, see [Virtual routing and forwarding on IBM Cloud](/docs/direct-link?topic=direct-link-overview-of-virtual-routing-and-forwarding-vrf-on-ibm-cloud).
{: note}

## The conversion process
{: #process-description}

The conversion process involves a network disruption, while the VLANs and their subnets are detached from the ACL backbone and then attached to the customer VRF. This process results in a few moments of packet loss for traffic entering or exiting the VLANs. Packets within the VLAN continue to flow. In the cases where a network gateway, such as a FortiGate Security Appliance or Virtual Router Appliance is involved, no disruption occurs among the VLANs attached to that gateway. The servers see no network outage themselves, and most workloads automatically recover when the traffic flow resumes. The total duration of the disruption depends on the extent of the tenant’s topology, that is, the number of subnets, VLANs, and pods that your tenancy includes.

During migration, the VLANs are disconnected from the backbone and reconnected to the customer VRF.  The duration of disruption varies, depending on the quantity of VLANs, pods, and data centers involved. Traffic among VLANs is disrupted, yet the servers stay connected to the network. The application might not be affected, depending on its sensitivity to packet loss.

## Initiating the conversion
{: #how-you-can-initiate-the-conversion}

Existing {{site.data.keyword.cloud_notm}} customers can [open an IBM Support case](/unifiedsupport/cases/add){: external} through the {{site.data.keyword.cloud_notm}} console, requesting to be migrated to a VRF. The IBM Support case should state: “Private Network Question” and include the following text:

"We are requesting that account _your account number_ is moved to its own VRF. We understand the risks and approve the change. Reply with the scheduled window(s) of time where this change will be made so we can prepare for the migration."

Migration is completed by the {{site.data.keyword.cloud_notm}} Network Engineering team. No other information is required from you, except an agreed-to schedule. Typically, packet loss might last 15 - 30 minutes, depending on the complexity of your account. It might be longer if your account has legacy Direct Link connections. The process is highly automated, requiring minimal interaction by the IBM team, and it should be transparent.

When you're opening the case, it's recommended to select the "Technical" support type option, with category **Networking > Direct Link**.
