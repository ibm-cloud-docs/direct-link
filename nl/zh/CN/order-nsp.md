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

# 如何订购 IBM Cloud Direct Link Dedicated

1. 验证您的网络提供商是否有能力将适当的 PoP 和交叉连接延伸到 {{site.data.keyword.BluSoftlayer_notm}} 环境。
2. 打开 IBM Cloud Direct Link Dedicated 请求并完成所请求的信息。（可以请求 IBM 销售工程师的帮助。）
3. {{site.data.keyword.BluSoftlayer_notm}} 为连接提供授权证 (LOA)。
4. 确认您的线路已经到达 PoP 且已由承运方完成。
5. 使用 LOA 中的 {{site.data.keyword.BluSoftlayer_notm}} CFA（客户设施分配）信息，订购交叉连接，通常需要2 到 10 个工作日即可完成。（此时间范围取决于设施供应商和客户下达订单时的订单优先级类型。）此过程包括设置 {{site.data.keyword.BluSoftlayer_notm}} 终止端口的补丁。
6. 在 {{site.data.keyword.BluSoftlayer_notm}} 门户网站凭单中，从设施提供商向 {{site.data.keyword.BluSoftlayer_notm}} 提供交叉连接完成通知。
7. {{site.data.keyword.BluSoftlayer_notm}} 将验证完成通知的效力，并通过 LOA/CFA 订购要对交叉连接路由器 (XCR) 和其他设备所做的补丁。
8. {{site.data.keyword.BluSoftlayer_notm}} 网络基础架构上的 IP 分配将在完成交叉连接后的 3 个工作日内完成。
