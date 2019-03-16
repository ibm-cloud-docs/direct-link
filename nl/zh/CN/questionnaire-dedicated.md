---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-19"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# IBM Cloud Direct Link Dedicated 调查表
{: #ibm-cloud-direct-link-dedicated-questionnaire}

感谢您开具 {{site.data.keyword.cloud}} Direct Link Dedicated 请求。为了最终完成您的请求，我们希望向您收集一些额外的信息。在填写调查表过程中，您可以随时与工程师交谈。完成调查表后，我们的云设计工程团队将对其进行复查，并将其上报到特殊网络服务以进行实施。

## 您是否确认并同意以下内容？

1. 每个 Direct Link 连接都需要唯一的订单。如果您需要多个连接，请为每个连接开具单独的 Direct Link 订单。

2. Direct Link Connect 服务的费用将包含 IBM Cloud 基础架构上服务终止的成本。 

 * 基础架构服务会提前收费，并在接受您的订单时开始计算；但是，由于 IBM Cloud Direct Link 的性质，在启动与 IBM Cloud 的边界网关协议 (BGP) 会话时，即开始对 Direct Link 服务收费，或者在向客户提供服务密钥 30 天后开始收费。 

 * 发生以下情况时，计费即停止：
   * 客户请求删除电路，**以及** 
   * Exchange 提供商或网络服务提供商已取消供应电路。
  * 有关更多信息，请参阅位于以下链接的“云服务协议”中的**第 5 节 - 费用**：[https://www.ibm.com/support/customer/zz/en/selectcountrylang.html](https://www.ibm.com/support/customer/zz/en/selectcountrylang.html)。例如，美国的客户将看到[此云服务合同文档](https://www.ibm.com/support/customer/csol/contractexplorer/cloud/csa/us-en)。

3. 通过订购 Direct Link 服务，您将负责支付与从远程网络访问存在点 (PoP) 相关联的任何费用，以及与 PoP 设施中所需任何交叉连接相关联的任何费用。如果您的提供商需要路由器或其他设备实际位于 PoP 中，那么与并置该设备相关联的成本也由您负责支付。

4. IBM Cloud 不会代表客户订购交叉连接。

5. IBM Cloud 不会在我们的网络 POP 中并置任何客户设备。我们只接受“交叉连接”，即您的框架或提供商运行的光纤以太网（仅限单模光纤：1Gig-LX 或 10Gig-LR 1310 纳米光模块）。我们不接受 T1、DS3、ISDN、POT 线路等。您需要与提供商合作，以确定是否需要将任何设备并置到 IBM Cloud 网络 PoP 所在的设施中。

6. 提供 Direct Link 服务时要确保您的链路及其终止接入的 IBM Cloud 路由器都是单一故障点 (SPOF)。如果要通过 Direct Link 服务实现冗余，您需要订购两个接入具有辅助路由器的 Direct Link 位置的连接，或者将链路终止接入两个单独的 IBM Cloud PoP。

7. 无法直接从远程网络访问 IBM Cloud 服务网络。如果此功能未来发生更改，我们将通知您。

8. IBM Cloud 不允许客户跨 IBM Cloud 主干在其远程站点之间回送流量。Direct Link 产品旨在使远程网络能够与 IBM Cloud 基础架构以专用方式进行通信。

9. 确认电路已到达 PoP 并已由承运方完成之后，您需要订购与 IBM Cloud XCR（交叉连接路由器）的交叉连接，通常需要 2 到 10 个工作日才能完成。这包括向下一直到 SoftLayer 终止端口的补丁。完成后，您需要向 IBM Cloud 提供设施提供商的交叉连接完成通知。IBM Cloud 网络基础架构上的 IP 发现将在交叉连接完成后的 3 个工作日内完成。

10. IBM Cloud Direct Link Dedicated 需要利用 VRF（虚拟路由和转发）实例。此功能允许客户定义自己的远程 IP 地址以用于远程网络；但是，您必须知道的是，如果利用 10.x.x.x 网络，您仍然不能与 IBM Cloud 中的主机或与 IBM Cloud 服务网络（10.0.0.0/14、10.198.0.0/15 和 10.200.0.0/14）重叠。在将帐户转换到 VRF 的过程中，在每个 VLAN 迁移到新配置时，都需要短暂的专用网络中断。特殊网络服务团队将与您合作来为此活动定义一个时段。特殊网络服务团队在周一到周五的 8-5 CST（美国中央标准时间）提供服务。任何此时段之外的激活活动都必须通过凭单提出请求，并且在工程师在线时先由其批准。

11. VRF 与 IBM Cloud（原先的 SoftLayer）SSL、PPTP 和 IPSEC VPN 服务不兼容。替代方法是使用 Direct Link 本身来管理服务器，或者运行您自己的可以配置为使用不同类型 VPN 的 VPN 解决方案（如 Vyatta）。迁移到 VRF 之后，SSL VPN 通常会在与正在访问但不允许全球访问的计算所在的 DC 位置建立 VPN 连接时生效。

12. IBM Cloud Direct Link Dedicated 需要 BGP 才能实现到客户远程网络的路径。部署了 Direct Link 服务后，IBM Cloud 将宣告分配给您帐户的所有专用子网。IBM Cloud 不会对向客户的远程 BGP 同级进行的宣告实施定制过滤器、AS 路径前置和定制 local-preference。IBM Cloud 也不会对收到的向 IBM Cloud 进行的宣告实施过滤器。客户需要从自己的边缘路由器来正确管理与 IBM Cloud 之间的宣告。

## 其他问题

* **您希望 Direct Link 终止接入哪个 PoP？**

* **您需要的链路速度是多少（1、2、5 或 10 Gbps）？**

* **您需要配置使用 ECMP 的 BGP 多路径以用于设置与 IBM Cloud 的冗余连接吗？** 

    _如果需要，请包含冗余连接的凭单标识。凭单编号 ____________（请注意，ECMP 只能在同一个 IBM Cloud XCR 的两个会话上供应。如果需要 ECMP，请知悉，这两个 Direct Link 都必须位于同一路由器上。）_

* **是需要当地还是全球路由访问？**

    _如果客户选择当地路由，那么只能在通过订购 Direct Link 所在的 PoP 来提供服务的数据中心之间传递流量。如果客户希望在订购 Direct Link 所在的 PoP 外部传递流量，那么需要在全球路由选项上进行添加。_

* **您是否同意全球路由的费用，包括_您的位置_的每月费用和下面概述的超额费用？**

    _当地路由包括对直接连接到 PoP 的所有数据中心的访问权，并提供无限制的输入/输出流量。全球路由扩展了访问权，以包含 IBM Cloud 在全球的所有数据中心。服务可以对流量计量时，即会开始对带宽计量。进行带宽计量时，将根据市场价格按月向您收费，如下表所示。_


### 全球路由定价

|全球路由输入|全球路由输出|
|---|---|
|免费|1、2 或 5 Gbps 电路 - 10 TB 免费带宽|
|免费|10 Gbps 电路 - 50 TB 免费带宽|


|带宽超额费用|
|---|
|市场 1：0.05 美元/GB|
|市场 2：0.10 美元/GB|
|市场 3：0.15 美元/GB|
