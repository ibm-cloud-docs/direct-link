---

copyright:
 years: 2017, 2018
lastupdated: "2018-04-05"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# 常见问题及解答

本节包含一些有关 IBM Cloud Direct Link 常见问题的解答。 

## IBM Cloud Direct Link 如何运作？
对于每个 Direct Link 客户，IBM Cloud 团队会分配一个小型的专用子网，以在 {{site.data.keyword.BluSoftlayer_notm}} 交叉连接路由器 (XCR) 和客户的边缘路由器 (CER) 之间构建点到点网络。然后，{{site.data.keyword.BluSoftlayer_notm}} 和客户会配置 BGP 以便在环境之间交换路径。最后，{{site.data.keyword.BluSoftlayer_notm}} 会将客户置于 VRF 中，以允许实施客户远程网络专用地址空间的非唯一路径。

## IBM Cloud 按照 Direct Link 产品的带宽用量计费吗？
是的。IBM Cloud 会按照 Direct Link 产品的所有出站带宽用量计费。入站带宽是免费的，不按用量收费。

## 使用 Direct Link 时会产生哪些额外的其他方费用？
交换提供商和网络服务提供商可能会向您收取额外费用。请咨询您的提供商以获取他们的收费信息。

## 如何利用 IBM Cloud Direct Link 实现冗余？
您可以通过连接到多个 IBM Cloud Direct Link Dedicated 提供商或 Exchange 提供商 {{site.data.keyword.BluSoftlayer_notm}} 来实现 Direct Link 的冗余。也可以利用其中一个为您的服务添加冗余的 IBM Cloud Direct Link 提供商。

## 缺省“当地”路由与全球路由附加组件之间有何区别？
使用我们的标准 Direct Link 产品，您可以在所选区域的数据中心之间发送流量。如果您需要访问指定区域外部的其他数据中心，那么您必须订购全球路由附加组件。此模型基于 ACL（访问控制表），其在您订购 Direct Link 连接时即已就位。 

## 对于全球路由附加组件来说，如何收取出站（输出）带宽超额费用？
当超出所分配的带宽时会按月收取超额费用，但是仅限出站带宽。入站带宽是免费的，不按用量收费。出站带宽的收费以您数据所横跨的两个区域中的较高者为基础。例如，如果在 DAL03 中配置 Direct Link 且您的数据流量通过墨西哥，那么将根据墨西哥的带宽费率向您收取费用。

## 为什么存在全球路由附加组件包？
我们添加全球路由附加组件是为了防止客户在穿越数据中心区域外部时经历意外数据丢失。这可使我们的大部分客户保持较低的成本，并让跻身国际市场的客户能够轻松地到达全球所有区域。但是，通常来说，客户仅需要当地带宽包。

## 什么是当地路由和全球路由选项？
每个客户在订购 Direct Link 服务时，都会选择当地路由和全球路由选项。如果客户需要将流量路由到他们订购 Direct Link 区域中的 POP 的外部，那么他们必须添加全球路由选项；否则，他们的流量会限制在当地 POP 所提供的服务。

每个月，使用 1G 线路的所有客户会分配 10TB 的免费输出流量；使用 10G 线路的客户会分配 50TB。超额基于下表，采用较高的市场费率。如果您选择全球路由，那么不会对任何当地输出流量向您收费，仅会对源自或终止在当地 POP 外部的流量进行收费。

|数据市场 1|数据市场 2|数据市场 3|
|---|---|---|
|<ul><li>DAL</li><li>WDC</li><li>SEA</li><li>SJC</li><li>NYC*</li><li>CHI*</li><li>DEN*</li><li>MIA*</li><li>ATL*</li><li>LAX*</li><li>TOR</li><li>MON</li><li>AMS</li><li>FRA</li></ul>|<ul><li>TOK</li><li>HKG</li><li>PAR</li><li>MIL</li><li>STK*</li><li>OSL</li></ul>|<ul><li>MEX</li><li>SAO</li><li>SYD</li><li>MEL</li><li>PER*</li><li>CHE</li><li>SEO</li></ul>|
**表 1：利用层**<br/>
以星号 (*) 标记的市场中的 Direct Link 产品必须订购全球路由。



## 如果我连接到某个区域（如达拉斯）中的 Direct Link NSP 或 Direct Link 云交换，我能够通过 Direct Link 访问美国的其他区域吗？
可以。如果您选择全球路由附加组件，那么您可以访问您所在区域外的区域。如果未选择此选项，那么您的 Direct Link 流量将限制在您所选的 POP 的区域。

## 我可以从给定 Direct Link 位置连接到任何可用的区域吗？
可以。只要您订购具有全球路由附加组件的 Direct Link 就可以。

## 我可以限制我的 Direct Link 能够到达的区域吗？
不可以。IBM Cloud 提供两个选项：(1) 仅限单个区域或者 (2) 所有区域（具有全球路由附加组件）。

## 如果我使用自动订购流程订购 Equinix Cloud Exchange，并为我分配了与我的内部网络重叠的子网，那怎么办？

自 2018 年 3 月起，建议的最佳做法是取消自动订购，并提交新的凭单以填写 Direct Link 调查表。您应该指明是否首选 10.254.x.x 范围或 172.32.x.x 范围内的其他子网。

## Direct Link Exchange 和 Direct Link Connect 有何区别？

这两种服务的相似之处在于，都具有 IBM Cloud Direct Link 相对成本较低、容许延迟、入口点速度快的优点。简而言之，Exchange 利用数据中心提供商，而 Connect 则利用 Telco 承运方。下面是其他一些详细信息：

**Direct Link Exchange** 适用于更乐意利用数据中心内交换的客户。利用 Exchange 服务，客户可以支持快速建立与并置的多个云连接，因为底层电路已供应（其他这些云提供商的设施中必须已经存在物理互联）。

Direct Link Exchange 可以允许通过单个云交换端口的多个云共享使用环境，该环境是由 NNI 连接在第 2 层在 IBM Cloud 和 Cloud Exchange 服务提供商之间创建的。端口速度最高可达 1Gb。

**Direct Link Connect** 适用于更乐意利用自己的内部部署与 IBM Cloud 之间现有网络的客户。利用 Direct Link Connect 服务，客户可以使用新的和现有的 Telco 网络（如 MPLS），通过预供应的底层电路来快速支持 IBM Cloud。

利用 Direct Link Connect，IBM 以及合作伙伴都会通过由 IBM 合作伙伴在世界各地运营的第 2 层 10G 网络到网络双接口 (NNI)，在第 2 层和第 3 层与客户连接。端口速度最高可达 5Gb。

