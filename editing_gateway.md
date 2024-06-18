---

copyright:
  years: 2022
lastupdated: "2024-06-18"

keywords:

subcollection: direct-link
---

{{site.data.keyword.attribute-definition-list}}

# Updating a direct link
{: #update-dl-gateway}
{: help}
{: support}

You can update a {{site.data.keyword.dl_short}} gateway either before or after the gateway moves to the **Provisioned** state. However, a gateway is restricted from editing during **In review**, **Configuring**, and some in-progress states.
{: shortdesc}

Your provider can also send you a request to create, delete, or edit a direct link. You are notified of these requests by a Notification icon ![Notification icon](/images/bell.png) and a request in the Status column. To respond to a pending request, select to accept or reject from the Actions menu ![Actions menu](/images/overflow.png), or use the **Actions** menu on the direct link's details page.
{: note}

To update a {{site.data.keyword.dl_short}} gateway, follow these steps:

1. Highlight the row of the gateway that you want to update, then click **Edit** from the Actions menu ![Actions menu](/images/overflow.png). Alternatively, you can click the Direct Link name in the table to show its details. Then, click the Edit icon ![Edit icon](/images/edit.png) in the upper right of the page.

   If you modify the speed or routing option, the pricing changes. Any updated charges take effect during the next billing cycle.
   {: note}

1. Read and agree to the {{site.data.keyword.dl_short}} prerequisites.
1. Click **Save** for your changes to take effect.

Configuration updates start automatically after you click **Save**. Notice that the gateway changes to **Configuring** state in the Direct Link table, followed by **Provisioned** when the update is completed.
