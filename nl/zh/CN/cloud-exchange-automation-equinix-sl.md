---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-06-12"

keywords: provisioning, order, Exchange, Equinix, automated, status, connection, legacy, customer, portal, Softlayer

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


# 通过旧的客户门户网站供应 IBM Cloud Direct Link Exchange for Equinix
{: #provisioning-ibm-cloud-direct-link-exchange-for-equinix-legacy}

此文档提供使用 IBM Cloud 旧的客户门户网站供应 Direct Link Exchange for Equinix 的分步指示信息。
{: shortdesc}

如果 {{site.data.keyword.cloud}} Direct Link 订单是针对 Equinix Cloud Exchange 的，那么该服务就是完全自动供应的，也就是说，您可以订购 {{site.data.keyword.cloud_notm}} Direct Link 连接 (Equinix) 而无需开具 IBM 支持凭单。

自动化功能当前仅限于 Equinix Cloud Exchange。在后续发行版中，将为其他提供商启用自动化。
{:note}

## 先决条件
{: #cloud-exchange-equinix-prerequisites-legacy}

要使用自动订购功能，您的专用 VLAN 必须与 {{site.data.keyword.cloud_notm}} 专用网络中的 VRF 相关联。如果不满足此要求，那么当您在客户门户网站下订单时，将生成支持凭单。

## 订购和供应步骤
{: #cloud-exchange-steps-for-ordering-and-provisioning-legacy}

**步骤 1：**

执行正常 [Cloud Exchange 订购步骤](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-legacy)中的步骤 1 到步骤 7。

**步骤 2：**

只要下完订单，IBM Cloud Direct Link 供应就会开始。

![步骤 8](/images/Equinix-Step8.png)

**步骤 3：**

在下订单之后，可以查看连接的状态。如果在 IBM 端成功完成了配置，您将看到状态为**已供应**。如果配置尚未完成，您将看到状态为**进行中**。如果配置已失败，您将看到状态为**创建失败**。如果配置已成功完成并且 BGP 连接处于开启状态，您将看到状态为**开启**。

![步骤 9 进行中](/images/Equinix-Step9-InProgress.png)

下图显示了下订单后的各种状态：

![步骤 9 开启](/images/Equinix-Step9-UP.png)

**步骤 4：**

如果连接处于**已供应**状态，请单击连接**名称**前边的 **>** 以展开连接。然后记下**客户 IP 地址**和**服务密钥**信息。在配置客户端路由器时需要这些信息，另外，这些信息也会分别作为云提供商端 (Equinix) 配置的授权密钥。

![步骤 10](/images/Equinix-Step10-Provisioned.png)

**步骤 5：**

对于状态为**已供应**的连接，在通过单击连接前边的 **>** 展开连接之后，如果“对等链路速度”不匹配，您就会看到错误消息。只要 IBM 端与 Equinix 端的速度相同，就不会再显示此错误通知。

![步骤 11](/images/Equinix-Step11-PortMismatch.png)

**步骤 6：**

对于状态为**创建失败**的连接，会生成 IBM 支持凭单，并通过支持凭单来传递进一步的详细信息。在展开连接时，您会看到支持凭单详细信息。

![步骤 12](/images/Equinix-Step12-CreateFailed.png)

**步骤 7：**

对于状态为**已供应**、**开启**或**关闭**的连接，您可以**删除**该连接，方法是单击连接旁边的**操作**列。

![步骤 13](/images/Equinix-Step13-Delete.png)

**步骤 8：**

对于状态为**创建失败**的连接，您可以**取消**该连接，方法是单击连接旁边的**操作**列。
