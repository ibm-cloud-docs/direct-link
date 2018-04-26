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

# 配置 IBM Cloud Direct Link

建立 IBM Cloud Direct Link 连接后，您可以按照本文档中指定的步骤来配置子网，以便与 IBM Cloud 交互。

一般而言，要使 IBM Cloud Direct Link 连接运作，您需要执行一些基本的网络配置步骤，然后还需要设置边界网关协议 (BGP)。在设置过程中，IBM 工程师将与您一起合作，以使您的网络能够使用所需的虚拟路由功能 (VRF)。

## 基本网络配置

1. 使用标准 RFC1918 专用地址空间定义您的远程网络。 
 * 对于新环境而言，建议**不要**使用 10.0.0.0/8 空间。 
 * 对于利用 10.0.0.0/8 的现有环境而言，建议您获取更详细的评估，以确保与 {{site.data.keyword.BluSoftlayer_notm}} 服务网络或与已经分配给您帐户的网络没有冲突。

2. {{site.data.keyword.BluSoftlayer_notm}} 的员工为每个连接分配 /31 或 /30，并在 {{site.data.keyword.BluSoftlayer_notm}} 交叉连接路由器 (XCR) 基础架构上配置界面 IP 地址。  

3. 使用我们提供的 IP 地址，配置客户边缘路由器 (CER) 上的界面：将 {{site.data.keyword.BluSoftlayer_notm}}XCR IP 用作目标为 {{site.data.keyword.BluSoftlayer_notm}} 的任何流量的下一个中继段。 

4. 对于返回流量，{{site.data.keyword.BluSoftlayer_notm}} 将已分配的 CER IP 用作目标为远程网络的任何流量的下一个中继段，如通过 BGP 宣告的一样。

## 配置 BGP

要与您的环境交换路径信息，{{site.data.keyword.BluSoftlayer_notm}} 需要配置 BGP。  

1. **ASN**：{{site.data.keyword.BluSoftlayer_notm}} 为每个客户用量分配专用 ASN。或者，您可以利用自己的公共 ASN。当您下订单时，会请求您的首选项。在实施过程中，会向您提供已分配的专用 ASN。

2. **VRF**：使用 VRF，{{site.data.keyword.BluSoftlayer_notm}} 会宣告分配给客户帐户的特定专用子网。您必须宣告您希望通过 {{site.data.keyword.BluSoftlayer_notm}} 专用网络连接的远程网络。以下网络已过滤掉，不能接受：0.0.0.0、10.0.0.0/14、10.198.0.0/15、10.200.0.0/14、169.254.0.0/16、224.0.0.0/4。您作为客户负责管理 IBM Cloud 网络之间的宣告。（有关 VRF 的更多信息包含在下一节中。）

3. **ECMP**：对于选择在受支持位置构建冗余的客户来说，{{site.data.keyword.BluSoftlayer_notm}} 支持实施等成本多路径 (ECMP) 以跨两个链接提供负载均衡和冗余。此 ECMP 设置应该在订购时请求。

## 冗余和多样性

IBM Cloud Direct Link 提供多样性，而客户则负责通过 BGP 模式实现冗余。

如果选择 ECMP 来提供冗余，那么两个 BGP 会话必须存在于同一个 XCR 上，因此您也就放弃了路由器多样性，一旦路由器发生故障就会暴露在风险中。您获得了第 3 层冗余，但却失去了第 2 层冗余。

## 使用 VRF 的更多信息

利用 IBM Cloud Direct Link 解决方案的所有帐户必须迁移到 VRF。使用 VRF，客户将可用的路径宣告到其自定义远程网络。请注意，此配置不允许您利用 {{site.data.keyword.BluSoftlayer_notm}} 网络上的自定义 IP 地址。

迁移到 VRF 在设置过程中完成。它需要一个简短的停机时间（对于具有多个 VLAN/位置的大型帐户，可达 30 分钟），在该期间，后端网络 VLAN 将在移动到 VRF 时失去彼此的连接。VRF 迁移由实施工程师计划。

请注意，VRF 会消除帐户的“VLAN 生成”选项，包括任何帐户到帐户 VLAN 生成能力，这是因为所有 VLAN 都可以进行通信，除非引入网关设备来管理流量。VRF 还会限制使用 {{site.data.keyword.BluSoftlayer_notm}} VPN 服务的能力，因为它与 {{site.data.keyword.BluSoftlayer_notm}} SSL、PPTP 和 IPSec VPN 服务不兼容。   

替代方法是使用 IBM Cloud Direct Link 产品本身来管理服务器，或者运行可以配置为不同类型 VPN 的自己的 VPN 解决方案（如 Vyatta）。迁移到 VRF 后，在对计算 VM 运行所在的相同数据中心位置进行 VPN 连接时，SSL VPN 通常会运作。

## 搭配使用 BYOIP 和 NAT 和 Direct Link
IBM Cloud Direct Link 在专用网络（在[定制专用定址](#custom-private-addressing)一节中所涵盖的特殊环境中除外）上不提供 BYOIP。因此，会舍弃具有未由 {{site.data.keyword.BluSoftlayer_notm}} 分配的目标 IP 地址的流量。但是，客户可以使用 GRE、IPSec 或 VXLAN，封装远程网络及其 {{site.data.keyword.BluSoftlayer_notm}} 之间的流量。  

最常见的是，BYOIP 环境在网关 (Vyatta) 或 VMWare NSX 部署的范围内实施。此配置使客户能够使用 {{site.data.keyword.BluSoftlayer_notm}} 端的任何所需 IP 空间，跨隧道路由回远程网络。请注意，此配置必须由客户管理和支持，与 {{site.data.keyword.BluSoftlayer_notm}} 无关。而且，如果客户为 {{site.data.keyword.BluSoftlayer_notm}} 服务分配 {{site.data.keyword.BluSoftlayer_notm}} 正在使用的 10.x.x.x 段，那么此配置还可以中断与服务网络的连接。 

此解决方案还要求每个需要与 {{site.data.keyword.BluSoftlayer_notm}} 服务网络和远程网络连接的主机必须已分配 2 个 IP 地址：一个必须从 IBM 10.x.x.x 段分配，另一个从远程网络段分配。主机上必须设置静态路由，以确保正确路由流量。您无法在 {{site.data.keyword.BluSoftlayer_notm}} 主机 (BYOIP) 上直接分配 IP 空间，让其在 {{site.data.keyword.BluSoftlayer_notm}} 网络上天生就可路由。实现此能力的唯一方法如之前所述，但是 {{site.data.keyword.BluSoftlayer_notm}} 并不支持此操作。

替代方法是客户频繁分配远程网络段，以在远程边缘路由器上配置的 NAT 表中使用。此配置允许客户限制这两个网络所需的更改，同时仍将流量转换为与这两个网络都兼容的网络地址空间。

## 关于定制专用定址

有时，在 IBM Cloud Direct Link 加载期间，客户使用之前说明的方法，无法解决内部部署和 {{site.data.keyword.BluSoftlayer_notm}} 专用网络之间的 IP 定址冲突。如果发生此情况，{{site.data.keyword.BluSoftlayer_notm}} 工程或销售代表可能会建议您使用_定制专用定址_ (CPA)。CPA 没有相关联的额外费用；但是，此功能有独特的需求和限制，您应该在同意使用之前对其进行彻底地了解。这些详细信息在建议 CPA 的 IBM Cloud 代表向您提供的文档中有所说明。 

_关键需求_是定制专用定址仅可以在新的空 {{site.data.keyword.BluSoftlayer_notm}} 帐户和新的 Direct Link 连接上激活。无法将现有资源转换或迁移到 CPA。

定制专用定制可让您在所选择的有效专用 IPv4 地址范围（10.x.x.x、192.168.x.x 或 172.16.x.x）内托管 {{site.data.keyword.BluSoftlayer_notm}} 服务器。CPA 在特殊的内部路由地址范围 161.26.x.x 中提供一组常用 IBM Cloud 服务，该地址范围保留专用 IP 地址免费供客户使用。虽然 CPA 使您能够定义多达 5 个专用 IP 范围（称为 _CPA 网络_），但是每个 Direct Link 仅能与一个 CPA 网络连接。如果在帐户中存在其他 CPA 网络，那么将无法通过 Direct Link 连接这些网络。

定制专用地址利用 VRF 和 BGP。实施工程师将协助您详细了解 CPA 相关内容。
