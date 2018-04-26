---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-11"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# 分步骤：订购 IBM Cloud Direct Link Exchange

此页面为您介绍如何订购 IBM Cloud Direct Link Exchange 服务。如果 IBM Cloud Direct Link 订单是针对 Equinix Cloud Exchange 的，那么该服务就是完全自动供应的，也就是说，您可以订购 IBM Cloud Direct Link 连接 (Equinix) 而无需开具 IBM 支持凭单。

**（注：自动化功能当前仅限于 Equinix Cloud Exchange。在后续发行版中，将为其他提供商启用自动化。）**

## 先决条件

要使用自动化功能，您的专用 VLAN 必须与 IBM Cloud 专用网络中的 VRF 相关联。如果不满足此要求，那么当您在客户门户网站下订单时，将生成支持凭单。

 * [如何订购 Cloud Exchange](#how-to-order-cloud-exchange)
 * [如何订购 Cloud Exchange for Equinix](#how-to-order-cloud-exchange-for-equinix)

## 如何订购 Cloud Exchange

要供应 IBM Cloud Direct Link Exchange 连接，请完成下列步骤：

**步骤 1：**

在[客户门户网站 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://control.softlayer.com/) 登录客户帐户。

**步骤 2：**

在**网络**选项卡下，选择 **Direct Link -> Exchange** 以打开显示现有 IBM Cloud Direct Link 连接（如果有）的页面。

![步骤 2](/images/Equinix-Step2.png)

**步骤 3：**

单击页面顶部的**订购 Direct Link Exchange** 按钮，就会看到订购表单，可以在该表单中输入 IBM Cloud Direct Link Exchange 连接的配置参数。

![步骤 3](/images/Equinix-Step3.png)

**步骤 4：**

在订购表单中，输入用于配置 Direct Link 的下列参数：
  * 输入 IBM Cloud Direct Link 连接名称。
  * 在列表中，选择要建立 IBM Cloud Direct Link 连接的 PoP 位置。
  * 在列表中，选择首选的 Cloud Exchange 提供商名称。
  * 选择连接所需的“链路速度”。
  * 选择连接所需的路由选项。
  * 输入在 BGP 交换的信息框中给定范围内的 ASN 编号。

**步骤 5：**

在选择或输入这些值时，您会在左侧面板中看到每月大约费用。

![步骤 4-5](/images/Equinix-Step4-5.png)

**步骤 6：**

在提供输入值之后，下一个 UI 屏幕中会显示根据您所选择的选项算出的实际每月定价。

**步骤 7：**

您必须**同意**条款和条件，才能下 IBM Cloud Direct Link 订单。请详细阅读“条款和条件”，因为其中包含重要的技术信息，必须先理解这些信息才能继续。**（注：如果不接受条款和条件，那么将生成有关下订单的 IBM 支持凭单。）**下图显示了根据您在此步骤中所做的选择您可能会看到的屏幕。

下图显示了“条款和条件”屏幕：

![步骤 7](images/Equinix-Step7.png)

下图显示了如果您在下订单时不同意“条款和条件”，可能会看到的屏幕。该屏幕中显示了生成的凭单编号：

![步骤 7 同意](/images/Equinix-Step7-NoAgree.png)

下图显示了开具的凭单的示例：

![步骤 7 凭单](/images/Equinix-Step7-NoAgree-Ticket.png)

**步骤 8：**

在您同意了条款和条件后，在下订单时，下完订单就会生成 IBM 支持凭单以继续供应服务。在您下订单之后，该凭单编号会显示在 UI 中。 

![步骤 NE1](/images/Non-Equinix-Step1.png)

**步骤 9：**

通过单击消息中的凭单编号，可以查看凭单的详细信息。

![步骤 NE2](/images/Non-Equinix-Step2.png)

## 如何订购 Cloud Exchange for Equinix

**步骤 1：**

按照上面的 Cloud Exchange 订购步骤来执行从步骤 1 到步骤 7

**步骤 2：**

只要下完订单，IBM Cloud Direct Link 供应就会开始。

![步骤 8](/images/Equinix-Step8.png)

**步骤 3：**

在下订单之后，可以查看连接的状态。如果在 IBM 端成功完成了配置，您将看到状态为**已供应**。如果配置尚未完成，您将看到状态为**进行中**。如果配置已失败，您将看到状态为**创建失败**。如果配置已成功完成并且 BGP 连接处于开启状态，您将看到状态为**开启**。

![步骤 9 进行中](/images/Equinix-Step9-InProgress.png)

下图显示了下订单后的各种状态：

![步骤 9 开启](/images/Equinix-Step9-UP.png)

**步骤 4：**

如果连接状态为**已供应**，请单击连接**名称**前边的 **>** 以展开连接。然后记下**客户 IP 地址**和**服务密钥**信息。在配置客户端路由器时需要这些信息，另外，这些信息也会分别作为云提供商端 (Equinix) 配置的授权密钥。

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

