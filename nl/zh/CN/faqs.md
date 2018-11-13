---

copyright:
  years: 2017, 2018
lastupdated: "2018-07-12"

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
是的。客户与 IBM Cloud 之间通过 Direct Link 服务使用的带宽是免费的，不按用量收费，但 IBM Cloud 会对 IBM Cloud 服务到公用因特网的出站带宽用量计费。

## 何时开始对 Direct Link 收费？
根据 IBM Cloud 基础架构上服务终止的成本来收取 Direct Link Connect 的费用。 

基础架构服务会提前收费，并在接受客户订单时开始计算；但是，由于 IBM Cloud Direct Link 的性质，在与 IBM Cloud 建立边界网关协议 (BGP) 会话时，即开始对 Direct Link 服务收费，或者在向客户提供服务密钥 30 天后开始收费。 

收费会在以下情况下停止：(1) 客户请求删除电路后，以及 (2) Connect 提供商或网络服务提供商已取消供应电路后。

## 使用 Direct Link 时会产生哪些额外的其他方费用？
交换提供商和网络服务提供商可能会向您收取额外费用。请咨询您的提供商以获取他们的收费信息。

## 如何利用 IBM Cloud Direct Link 实现冗余？
Direct Link 并不提供固有冗余的服务。Direct Link 可以提供多种连接，使客户能够通过 BGP 创建冗余。您可以通过连接到多个 IBM Cloud Direct Link Dedicated 提供商或 {{site.data.keyword.BluSoftlayer_notm}} 的 Exchange 提供商来实现 Direct Link 的多样化。或者，通过 Exchange 和 Connect，可以利用 IBM Cloud Direct Link 提供商的多种 NNI。

## 缺省“当地”路由与全球路由附加组件之间有何区别？
使用我们的标准 Direct Link 产品，您可以在所选区域的数据中心之间发送流量。如果您需要访问指定区域外部的其他数据中心，那么您必须订购全球路由附加组件。此模型基于 ACL（访问控制表），其在您订购 Direct Link 连接时即已就位。 

## 对于全球路由附加组件来说，如何收取出站（输出）带宽超额费用？
当超出所分配的带宽时会按月收取超额费用，但是仅限出站带宽。入站带宽是免费的，不按用量收费。出站带宽的收费以您数据所横跨的两个区域中的较高者为基础。例如，如果在 DAL03 中配置 Direct Link 且您的数据流量通过墨西哥，那么将根据墨西哥的带宽费率向您收取费用。

## 为什么存在全球路由附加组件包？
我们添加全球路由附加组件是为了防止客户在穿越数据中心区域外部时经历意外数据丢失。这可使我们的大部分客户保持较低的成本，并让跻身国际市场的客户能够轻松地到达全球所有区域。但是，通常来说，客户仅需要当地带宽包。

## 如果我连接到某个区域（如达拉斯）中的 Direct Link Dedicated、Direct Link Connect 或 Direct Link Exchange，我能够通过 Direct Link 访问美国的其他区域吗？
可以。如果您选择全球路由附加组件，那么您可以访问您所在区域外的区域。如果未选择此选项，那么您的 Direct Link 流量将限制在您所选的 PoP 位置的区域。请参阅[定价文档](pricing.html)了解详细信息。

## 我可以从给定 Direct Link 位置连接到任何可用的区域吗？
可以。只要您订购具有全球路由附加组件的 Direct Link 就可以。

## 我可以限制我的 Direct Link 能够到达的区域吗？
不可以。IBM Cloud 提供两个选项：(1) 仅限单个区域或者 (2) 所有区域（具有全球路由附加组件）。

## 如果我使用自动订购流程订购 Equinix Cloud Exchange，并为我分配了与我的内部网络重叠的子网，那怎么办？

自 2018 年 3 月起，建议的最佳做法是取消自动订购，并提交新的凭单以填写 Direct Link 调查表。您应该指明是否首选 10.254.x.x 范围或 172.32.x.x 范围内的其他子网。

## Direct Link Exchange 和 Direct Link Connect 有何区别？

这两种服务的相似之处在于，都具有 IBM Cloud Direct Link 相对成本较低、容许延迟、入口点速度快的优点。简而言之，Exchange 利用数据中心提供商，而 Connect 则利用 Telco 承运方。下面是其他一些详细信息：

建议将 **Direct Link Exchange** 用于更乐意利用数据中心内交换的客户。利用 Exchange 服务，客户可以支持快速建立与并置的多云连接，因为底层电路已供应（其他这些云提供商必须已经在设施中存在物理互连）。

Direct Link Exchange 可以允许通过单个云交换端口来访问多云共享使用环境，该环境是由网络到网络 (NNI) 连接在 IBM Cloud 和 Cloud Exchange 服务提供商之间的第 2 层创建的。端口速度最高可达 1Gb。

**Direct Link Connect** 适用于更乐意利用自己的内部部署与 IBM Cloud 之间现有网络的客户。利用 Direct Link Connect 服务，客户可以使用新的和现有的 Telco 网络（如 MPLS），通过预供应的底层电路来快速支持 IBM Cloud。

利用 Direct Link Connect，客户可以通过由 IBM 合作伙伴在世界各地设施运营的网络到网络 (NNI) 连接，经由 Connect 提供商连接到 IBM Cloud。端口速度最高可达 5Gb。

## Direct Link Connect 与 Direct Link Exchange 提供商相比较如何？

Connect 提供商是在数据中心外提供网络连接的 Telco。Exchange 提供商局限于其数据中心内。两者都可支持客户的多云体验。Exchange 提供商通常需要在其数据中心内进行主机托管，而 Connect 提供商可连接客户的内部部署站点和数据中心。

## 可以通过 Direct Link 支持 IPv6 吗？

不适用于 BGP 会话。我们必须从 IPv4 分配 /30，而我们也需要客户同样这么做。

## 可以在专用网络上执行 IPv6 吗？

不可以。IPv6 仅用于公用网络。

## Verizon SCI 有任何特殊需求吗？前缀/ASN/VLAN BGP 等？

Verizon SCI 是多种基于 MPLS 的第 3 层 (IP VPN) 服务之一。它要求 IBM 使用 Verizon 建立 BGP，而不是直接与客户建立 BGP。Verizon 与客户建立 BGP 后，会相应地公布路径。其他多个基于第 3 层的服务提供商参与了 Direct Link Connect 计划。客户需要了解自己的订购内容，以及其帐户在连接到 IBM Cloud 时的行为方式。

## Direct Link 支持任何类型的 QoS 吗？

我们无法保证支持任何 QoS。QoS 需要我们的每个服务供应商与 IBM Cloud 之间进行 MPLS 映射。目前，云服务供应商通常无法支持 QoS，因为它必须从端到端进行访问，并涉及端到端之间的每个设备。没有可通过“隧道”或其他任何方法使用的变通方法。

## Direct Link 支持巨型帧吗？

Dedicated 和 Dedicated Hosting 上支持巨型帧（最多 9214 字节）。理论上，可以支持 Connect 和 Exchange，但这要求您的服务提供商与 IBM 合作，并确保端到端连接支持巨型帧，包括底层的网络到网络接口 (NNI)。缺省情况下，Exchange 和 Connect 设置为支持 1500 字节的 MTU。

## 通过 Direct Link Connect，客户如何通过同一承运方（例如：DAL03 中的 Verizon）来确保路由器多样性？

我们有多种 XCR，可用于创建与承运方的多种 NNI 链路。从这方面来说，保持多样性取决于承运方。

## 对于 Direct Link Connect，客户是需要订购 2 个链路以实现冗余，还是 Direct Link Connect 具备固有冗余性？

订购 2 个链路来实现多样性。我们不提供交换机或路由器之间的冗余。客户可在每个 Direct Link 上使用其 BGP 配置创建冗余。

## 升级连接带宽有多简单（例如，从 1 GB 升级到 5 GB）？

通常，我们在 1G 光模块上安装的速度不高于 1G。对于 2 G 到 10G 的速度，我们安装 10G 光模块。因此，从 1G 升级到 5G 需要分配或插入新的光模块。这将是影响服务的事件。如果您预期会有该类型的增长，可以在 Direct Link 部署之初请求安装 10G 光纤，或者初始订购 2G 以便实施 10G 光模块。

## ECMP 是实现冗余连接的方法吗？有哪些替代方法？

请注意，ECMP 并不用于冗余连接，而是用于均衡两个链路上的负载。通过 ECMP，两个连接都必须终止接入同一个 IBM Cloud 交叉连接路由器 (XCR)，这会使其成为单一故障点。（换言之，ECMP 只能在同一个 IBM Cloud XCR 上作为两个会话供应。） 

ECMP 是 BGP 的一个功能。如果需要冗余，请获取两个 Direct Link 连接，每个 XCR 对应一个连接。如果要使用 ECMP 并具有冗余性，那么每个 XCR 上都需要两个 Direct Link 连接，以便可以同时进行 2 个 ECMP 会话。

或者，我们的一些客户在同一数据中心（例如 WDC02）中设置了两个接入不同 XCR 的链路，然后根据需要使用 BGP 配置进行故障转移。此配置的冗余性（安全性）不如建立与两个独立数据中心（例如 WDC02 和 WDC05）的 Direct Link 连接。

## XCR 连接上是否有 SLA 连接到帐户的 BCR？

目前，DirectLink 上没有 SLA。客户使用 BGP 正确配置 2 个或更多个 Direct Link 进行故障转移，可实现 99.999% 的有效性，但 IBM 无法控制这一点或在其上提供 SLA。
