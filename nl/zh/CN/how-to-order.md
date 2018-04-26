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

# 订购 IBM Cloud Direct Link

如果您准备订购最能满足您需求的 IBM Cloud Direct Link 类型，请跟随下面的链接（或者滚动浏览此文档）来查看订购流程概述。如果您已准备好下订单，那么可以在我们的“分步骤”系列文档中找到可引导您完成整个订购流程的分步骤指示信息。

* [如何订购 IBM Cloud Direct Link Exchange](how-to-order.html#how-to-order-ibm-cloud-direct-link-exchange)
* [如何订购 IBM Cloud Direct Link Connect](how-to-order.html#how-to-order-ibm-cloud-direct-link-connect)
* [如何订购 IBM Cloud Direct Link Dedicated](how-to-order.html#how-to-order-ibm-cloud-direct-link-dedicated)
* [如何订购 IBM Cloud Direct Link Dedicated Hosting](how-to-order.html#how-to-order-ibm-cloud-direct-link-dedicated-hosting)

## 如何订购 IBM Cloud Direct Link Exchange

 * 验证您的网络提供商是否有能力将适当的 PoP 和交叉连接延伸到相关联云交换供应商。
 * 使用[客户门户网站 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://control.softlayer.com/) 打开 IBM Cloud Direct Link Exchange 请求并完成请求的信息。（可以请求 IBM 销售工程师的帮助。）如果使用 Equinix 提供商，那么订购和供应流程将[全部自动完成](cloud-exchange-automation.html)。
 * 联系 Exchange 提供商并协调与交换的连接。
 * 订购网络提供商与 Exchange 提供商之间的连接。
 * 通过 Exchange 提供商订购“虚拟电路”，将 {{site.data.keyword.BluSoftlayer_notm}} IBM Cloud Direct Link 请求的凭单标识引用为“请求标识”或“授权标识”。
 * {{site.data.keyword.BluSoftlayer_notm}} 网络基础架构上的 IP 分配将在虚拟线路请求完成后的 3 个工作日内完成。

## 如何订购 IBM Cloud Direct Link Connect

 * 验证您的网络提供商是否有能力将适当的 PoP 和交叉连接延伸到相关联的 Connect 提供商。
 * 使用[客户门户网站 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://control.softlayer.com/) 打开 IBM Cloud Direct Link Connect 请求并完成请求的信息。（可以请求 IBM 销售工程师的帮助。） 
 * 联系 Connect 提供商并协调与交换的连接。
 * 订购网络提供商与 Connect 提供商之间的连接。
 * 通过 Connect 提供商订购“虚拟电路”，将 {{site.data.keyword.BluSoftlayer_notm}} IBM Cloud Direct Link 请求的凭单标识引用为“请求标识”或“授权标识”。
 * {{site.data.keyword.BluSoftlayer_notm}} 网络基础架构上的 IP 分配将在虚拟线路请求完成后的 3 个工作日内完成。

## 如何订购 IBM Cloud Direct Link Dedicated

 * 验证您的网络提供商是否有能力将适当的 PoP 和交叉连接延伸到 {{site.data.keyword.BluSoftlayer_notm}} 环境。
 * 打开 IBM Cloud Direct Link Dedicated 请求并完成所请求的信息。（可以请求 IBM 销售工程师的帮助。）
 * {{site.data.keyword.BluSoftlayer_notm}} 为连接提供授权证 (LOA)。
 * 确认您的线路已经到达 PoP 且已由承运方完成。
 * 使用 LOA 中的 {{site.data.keyword.BluSoftlayer_notm}} CFA（客户设施分配）信息，订购交叉连接，通常需要2 到 10 个工作日即可完成。（此时间范围取决于设施供应商和客户下达订单时的订单优先级类型。）此过程包括设置 {{site.data.keyword.BluSoftlayer_notm}} 终止端口的补丁。
 * 在 {{site.data.keyword.BluSoftlayer_notm}} 门户网站凭单中，从设施提供商向 {{site.data.keyword.BluSoftlayer_notm}} 提供交叉连接完成通知。
 * {{site.data.keyword.BluSoftlayer_notm}} 将验证完成通知的效力，并通过 LOA/CFA 订购要对交叉连接路由器 (XCR) 和其他设备所做的补丁。
 * {{site.data.keyword.BluSoftlayer_notm}} 网络基础架构上的 IP 分配将在完成交叉连接后的 3 个工作日内完成。

## 如何订购 IBM Cloud Direct Link Dedicated Hosting

 * 识别您的并置和连接需求，并与 IBM 销售团队一起合作，最终确定并执行合同和技术附录。
 * {{site.data.keyword.BluSoftlayer_notm}} 针对所请求的环境和服务，与并置提供商执行构建订单。部署通常在下达构建订单后的 30 天内完成。
 * 当并置框架的构建完成时，并置框架与 {{site.data.keyword.BluSoftlayer_notm}} POD 环境的 XCR 设备之间的互连过程将遵循之前显示的 IBM Cloud Direct Link Dedicated 订购流程，从步骤 3 开始。
