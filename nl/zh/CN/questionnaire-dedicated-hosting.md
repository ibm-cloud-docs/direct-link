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

# IBM Cloud Direct Link Dedicated Hosting 调查表
{: #ibm-cloud-direct-link-dedicated-hosting-questionnaire}

感谢您开具 {{site.data.keyword.cloud}} Direct Link Dedicated Hosting 请求。为了最终完成您的请求，我们希望向您收集一些额外的信息。在填写调查表过程中，您可以随时与工程师交谈。完成调查表后，我们的云设计工程团队将对其进行复查，并将其上报到网络工程部以进行实施。

## 声明

1. 本调查表中概述的费用将包含服务终止接入 IBM Cloud 基础架构的成本。并置成本（包括机柜、交叉连接等）包含每月费用和非经常性费用，这些费用会作为并置合同的一部分单独概述。

2. IBM Cloud Direct Link Dedicated Hosting 提供接入 IBM Cloud 专用网络的 1 Gbps 或 10 Gbps 光纤交叉连接。您需要提供可支持单模光纤 (SMF) 上行链路的路由器或第 3 层交换机。部署时间可能因电路提供商而异，此服务的典型部署时间为 30-60 天。

3. Direct Link Dedicated Hosting 需要利用 VRF（虚拟路由和转发）实例。这允许客户定义自己的远程 IP 地址以用于远程网络；但是，您必须知道的是，如果利用 10.x.x.x 网络，您仍然不能与 IBM Cloud 中的主机或与 IBM Cloud 服务网络（(10.0.0.0/14、10.198.0.0/15 和 10.200.0.0/14）重叠。在将帐户转换到 VRF 的过程中，在每个 VLAN 迁移到新配置时，都需要短暂的专用网络中断。网络工程团队将与您合作为此活动定义一个时段。

4. VRF 会改变 IBM Cloud SSL、PPTP 和 IPsec VPN 的行为。通常，这些变化在与正在访问但不允许全球访问的计算资源所在的数据中心位置建立 VPN 连接时生效。替代方法是使用 Direct Link 本身来管理服务器，或者运行您自己的可以配置为使用不同类型 VPN 的 VPN 解决方案（如 Vyatta）。 

5. Direct Link Dedicated Hosting 需要 BGP 才能实现到客户远程网络的路径。IBM Cloud 不会对向 IBM Cloud 进行的宣告实施过滤器。IBM Cloud 将宣告分配给您帐户的所有专用子网。客户需要正确管理收到的向 IBM Cloud 进行的宣告。

6. IBM Cloud 提供双上行链路，每个 IBM Cloud 交叉连接路由器对应一个链路，以允许客户建立冗余连接。这可以通过 BGP 会话在客户的路由器上利用 ECMP 功能或仅仅对连接加权来实现。

7. 无法直接从 Dedicated Hosting 或远程网络访问 IBM Cloud 服务网络。

8. IBM Cloud 不允许您跨 IBM Cloud 主干在您的远程站点之间回送流量。Direct Link 服务旨在使远程网络能够与 IBM Cloud 基础架构以专用方式进行通信。

9. IBM Cloud 提供使用当地路由或全球路由的 Direct Link。请确认您需要的路由包，并确认是否同意与以下链接中列出的包相关联的带宽套餐：ibm.biz/DirectLink-Docs。

10. 请指定计划在 Direct Link 上推送多少流量，以及计划将此流量推送到的 IBM Cloud 数据中心。

11. 如果您不是通过 IBM Cloud 购买的并置服务，那么您将负责订购环境与 IBM Cloud 之间的交叉连接并支付相关费用。连接后，我们将提供一份授权书 (LOA)，详细说明我们已批准您的连接以及要连接到的位置。

12. 请确认您是否同意以下 Direct Link 定价：
 * 1 Gbps：_基于位置定价_ 
* 2 Gbps：_基于位置定价_
* 5 Gbps：_基于位置定价_
* 10 Gbps：_基于位置定价_
* 可选全球路由
