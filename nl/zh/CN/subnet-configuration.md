---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-30"

keywords: direct link, configure, connectivity, BGP, VRF, configuration, RFC1918, ASN, BYOIP, NAT, VLAN Spanning, 10.0.0.0/8, ECMP, redundancy, IP assignments, VMWare, Vyatta, IP limitations

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

# 配置 IBM Cloud Direct Link
{: #configure-ibm-cloud-direct-link}

建立 {{site.data.keyword.cloud}} Direct Link 连接后，您可以按照本文档中给定的步骤来配置子网，以与 {{site.data.keyword.cloud_notm}} 交互。

一般而言，要使 {{site.data.keyword.cloud_notm}} Direct Link 连接正常运作，您需要执行一些基本的网络配置步骤，然后您需要设置边界网关协议 (BGP)。在设置过程中，IBM 工程师将与您一起合作，以使您的网络能够使用所需的虚拟路由功能 (VRF)。

## 基本网络配置
{: #basic-network-configuration}

1. 使用标准 RFC1918 专用地址空间定义您的远程网络。 
 * 对于新环境而言，建议**不要**使用 10.0.0.0/8 空间。 
 * 对于利用 10.0.0.0/8 的现有环境而言，建议您获取更详细的评估，以确保与 {{site.data.keyword.cloud_notm}} 服务网络或与已经分配给您帐户的网络没有冲突。

2. {{site.data.keyword.cloud_notm}} 的员工为每个连接分配 /31 或 /30，并在 {{site.data.keyword.cloud_notm}} 交叉连接路由器 (XCR) 基础架构上配置界面 IP 地址。  

3. 使用我们提供的 IP 地址，配置客户边缘路由器 (CER) 上的界面：将 {{site.data.keyword.cloud_notm}}XCR IP 用作目标为 {{site.data.keyword.cloud_notm}} 的任何流量的下一个中继段。 

4. 对于返回流量，{{site.data.keyword.cloud_notm}} 将已分配的 CER IP 用作目标为远程网络的任何流量的下一个中继段，如通过 BGP 宣告的一样。

## 配置 BGP
{: #configuring-bgp}

要与您的环境交换路径信息，{{site.data.keyword.cloud_notm}} 需要配置 BGP。  

1. **ASN**：{{site.data.keyword.cloud_notm}} 为每个客户用量分配专用 ASN。或者，您可以利用自己的公共 ASN。当您下订单时，会请求您的首选项。在实施过程中，会向您提供已分配的专用 ASN。

2. **VRF**：使用 VRF，{{site.data.keyword.cloud_notm}} 会宣告分配给客户帐户的特定专用子网。您必须宣告您希望通过 {{site.data.keyword.cloud_notm}} 专用网络连接的远程网络。您作为客户负责管理 IBM Cloud 网络之间的宣告。（有关 VRF 的更多信息包含在下一节中。）

以下网络已过滤掉，不能接受：0.0.0.0、10.0.0.0/14、10.198.0.0/15、10.200.0.0/14、169.254.0.0/16、224.0.0.0/4。
{:note}

3. **ECMP**：对于选择在受支持位置构建冗余的客户来说，{{site.data.keyword.cloud_notm}} 支持实施等成本多路径 (ECMP) 以在两个链路之间提供负载均衡和冗余。此 ECMP 设置应该在订购时请求。

## IBM Cloud Direct Link 的 BGP 规范
{: #bgp-specifications-for-ibm-cloud-direct-link}

BGP 规范如下：

如上一节中所述，通过 Direct Link 管理路由必须遵循 BGP。订购 Direct Link 的帐户将迁移到 VRF 环境。

**针对 VLANS 和 VRF 的警告：**
 * 在 VRF 环境中，不允许使用帐户间 VLAN 生成。 
 * IPSEC VPN 服务受到限制。 
 
VRF 不会阻止 SSL 或 PPTP VPN 访问，但其行为会更改。不使用 VRF 时，一个 VPN 连接足以查看帐户上的所有服务器。使用 VRF 时，您只能访问市场中与 VPN 关联的资源。因此，如果连接到 DAL VPN，那么只能连接到 DAL 服务器。
{: note}

对于 Public 和 Private 服务，IBM Cloud ASN 为 **13884**。 
 * 订购时客户的缺省 ASN 为 **64999**，但缺省值可根据客户请求进行更改。 
 * （可选）可以支持 4201000000 到 4201064511 之间的 4 字节专用 ASN。
 * 如果要将 Direct Link Connect 与第 3 层服务（如 IP VPN）配合使用，那么 IBM Cloud 将通过 Direct Link Connect 提供者的 ASN 来建立 BGP。

**建议、缺省值和限制：**

 * 如果 IP 重叠成为问题，那么支持并建议使用隧道（即 GRE）。
 * BGP 计时器缺省值为 `Keepalive:30` 和 `Holdtime:60`。
 * 缺省情况下，未启用认证。
 * 缺省情况下，未启用 BGP BFD。
 * 每个 VRF 接收（来自客户或提供商）的最大前缀数限制为 200。
 
## 对 IP 分配的严格限制
{: #strict-limitations-on-ip-assignments}

 * 如果利用 10.x.x.x 网络，那么仍然无法创建与 IBM Cloud 中的主机以及占用 `10.0.0.0/14`、`10.198.0.0/15` 和 `10.200.0.0/14` 的 IBM Cloud 服务网络的重叠。  

 * 在联邦系统中不允许使用以下范围，并且 IBM 服务器将拒绝这些范围：`169.254.0.0/16` 和 `224.0.0.0/4`。

## 冗余和多样性
{: #redundancy-and-diversity}

{{site.data.keyword.cloud_notm}} Direct Link 提供多样性，而客户则负责通过其 BGP 模式实现冗余。

如果选择 ECMP 来提供冗余，那么两个 BGP 会话必须存在于同一个 XCR 上，因此您也就放弃了路由器多样性，一旦路由器发生故障就会暴露在风险中。您获得了第 3 层冗余，但却失去了路由器多样性。

## 使用 VRF 的更多信息
{: #more-about-using-vrf}

利用 {{site.data.keyword.cloud_notm}} Direct Link 解决方案的所有帐户必须迁移到 VRF。使用 VRF，客户将可用的路径宣告到其自定义远程网络。请注意，此配置不允许您利用 {{site.data.keyword.cloud_notm}} 网络上的自定义 IP 地址。

迁移到 VRF 在设置过程中完成。它需要一个简短的停机时间（对于具有多个 VLAN/位置的大型帐户，可达 30 分钟），在该期间，后端网络 VLAN 将在移动到 VRF 时失去彼此的连接。VRF 迁移由实施工程师计划。

请注意，VRF 会消除帐户的“VLAN 生成”选项，包括任何帐户到帐户 VLAN 生成能力，这是因为所有 VLAN 都可以进行通信，除非引入网关设备来管理流量。VRF 还会限制使用 {{site.data.keyword.cloud_notm}} VPN 服务的能力，因为它与 {{site.data.keyword.cloud_notm}} SSL、PPTP 和 IPSec VPN 服务不兼容。   

替代方法是使用 IBM Cloud Direct Link 产品本身来管理服务器，或者运行可以配置为不同类型 VPN 的自己的 VPN 解决方案（如 Vyatta）。迁移到 VRF 后，在对计算 VM 运行所在的相同数据中心位置进行 VPN 连接时，SSL VPN 通常会运作。

## 搭配使用 BYOIP 和 NAT 和 Direct Link
{: #using-byoip-and-nat-with-direct-link}

IBM Cloud Direct Link 在专用网络上不提供 BYOIP。因此，会舍弃具有未由 {{site.data.keyword.cloud_notm}} 分配的目标 IP 地址的流量。但是，客户可以使用 GRE、IPSec 或 VXLAN，封装远程网络及其 {{site.data.keyword.cloud_notm}} 之间的流量。  

最常见的是，BYOIP 环境在网关 (Vyatta) 或 VMWare NSX 部署的范围内实施。此配置使客户能够使用 {{site.data.keyword.cloud_notm}} 端的任何所需 IP 空间，跨隧道路由回远程网络。请注意，此配置必须由客户管理和支持，与 {{site.data.keyword.cloud_notm}} 无关。而且，如果客户为 {{site.data.keyword.cloud_notm}} 服务分配 {{site.data.keyword.cloud_notm}} 正在使用的 10.x.x.x 段，那么此配置还可以中断与服务网络的连接。 

此解决方案还要求每个需要与 {{site.data.keyword.cloud_notm}} 服务网络和远程网络连接的主机必须已分配 2 个 IP 地址：一个必须从 IBM 10.x.x.x 段分配，另一个从远程网络段分配。主机上必须设置静态路由，以确保正确路由流量。您无法在 {{site.data.keyword.cloud_notm}} 主机 (BYOIP) 上直接分配 IP 空间，让其在 {{site.data.keyword.cloud_notm}} 网络上天生就可路由。实现此能力的唯一方法如之前所述，但是 {{site.data.keyword.cloud_notm}} 并不支持此操作。

替代方法是客户频繁分配远程网络段，以在远程边缘路由器上配置的 NAT 表中使用。此配置允许客户限制这两个网络所需的更改，同时仍将流量转换为与这两个网络都兼容的网络地址空间。
