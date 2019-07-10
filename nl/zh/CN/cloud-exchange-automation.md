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

# 供应 IBM Cloud Direct Link Exchange
{: #provisioning-ibm-cloud-direct-link-exchange}

此页面为您介绍如何订购 {{site.data.keyword.cloud}} Direct Link Exchange 服务。如果 {{site.data.keyword.cloud_notm}} Direct Link 订单是针对 Equinix Cloud Exchange 的，那么该服务就是完全自动供应的，也就是说，您可以[订购 IBM Cloud Direct Link 连接 (Equinix) 而无需开具 IBM 支持凭单](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix)，如相关文档中所述。

自动化功能当前仅限于 Equinix Cloud Exchange。在后续发行版中，将为其他提供商启用自动化。
{:note}

## 先决条件
{: #cloud-exchange-prerequisites}

要使用自动化功能，您的专用 VLAN 必须与 {{site.data.keyword.cloud_notm}} 专用网络中的 VRF 相关联。如果不满足此要求，那么当您在客户门户网站下订单时，将生成支持凭单。

 * [如何订购 Cloud Exchange](#how-to-order-cloud-exchange-no-equinix)
 * [如何订购 Cloud Exchange for Equinix](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix)

## 如何订购 Cloud Exchange
{: #how-to-order-cloud-exchange-no-equinix}

要供应 IBM Cloud Direct Link Exchange 连接，请完成下列步骤：

**步骤 1：**

在[客户门户网站 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://cloud.ibm.com/) 登录客户帐户。

**步骤 2：**

在**网络**选项卡下，选择 **Direct Link -> Exchange** 以打开显示现有 IBM Cloud Direct Link 连接（如果有）的页面。

![步骤 2](/images/pup_exchange_list.png)

**步骤 3：**

单击页面顶部的**订购 Direct Link Exchange** 按钮，就会看到订购表单，可以在该表单中输入 IBM Cloud Direct Link Exchange 连接的配置参数。

![步骤 3](/images/pup_exchange_create_default.png)

**步骤 3A：**

（可选）如果可以访问多种端口，并且先前已供应第一个虚拟电路，那么您将看到类似于下图的屏幕，其中显示有两个端口，您可以从中选择第二个虚拟电路。

![有 2 个端口的图像](/images/pup_exchange_create_ports.png)

**步骤 4：**

在订购表单中，输入用于配置 Direct Link 的下列参数：
  * 输入 IBM Cloud Direct Link 连接名称。
  * 在列表中，选择要建立 IBM Cloud Direct Link 连接的位置。
  * 在列表中，选择首选的 Cloud Exchange 提供商名称。
  * 选择连接所需的“链路速度”。
  * 选择连接所需的路由选项。
  * 输入在 BGP 交换的信息框中给定范围内的 ASN 编号。

**步骤 5：**

在选择或输入这些值时，您会在右侧面板中看到大致的每月费用。

![步骤 4-5](/images/pup_exchange_create_prices.png)

**步骤 6：**

在您提供输入时将验证表单字段。
要启用“创建”按钮，您必须**同意**“条款和条件”。

**步骤 7：**

在您同意了条款和条件后，在下订单时，下完订单就会生成 IBM 支持凭单以继续供应服务。在您下订单之后，该凭单编号会显示在 UI 中。 

![步骤 NE1](/images/pup_exchange_ticket_notification.png)

**步骤 8：**

通过单击消息中的凭单编号，可以查看凭单的详细信息。

![步骤 NE2](/images/pup_exchange_ticket_details.png)
