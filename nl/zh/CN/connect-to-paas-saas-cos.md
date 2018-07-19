---

copyright:
  years: 2018
lastupdated: "2018-04-24"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# 联合使用：IBM Cloud Direct Link 和 IBM Cloud Object Storage

本文档描述了如何配置 IBM Cloud Direct Link，以便您有权访问 IBM Cloud Object Storage 和其他 IBM Cloud 服务。有多种方法可用于从专用 IBM Cloud IaaS 网络（有 IBM Cloud Direct Link）桥接到支持 IBM Cloud PaaS 和 SaaS 功能的“公用”网络，而实际上并未离开 IaaS 主干。

根据目前的策略，无法通过 IBM Cloud Direct Link 访问 IBM Cloud 专用服务端点。本文档中描述的方法依赖于通过 IBM Cloud 托管的系统进行间接访问。虽然无法通过 Direct Link 访问专用服务端点，但客户的专用服务器和设备可能会变为可访问。

## 什么是 IBM Cloud Object Storage (COS)？

IBM Cloud Object Storage 是一个用于存储非结构化数据的 Web 扩展平台。它提供了可靠性、安全性、可用性和灾难恢复功能，无需进行复制。 

使用 IBM Cloud Object Storage 存储的信息会进行加密并分散在多个地理位置。可通过实现 S3 API 对其进行访问。此服务利用的是 IBM Cloud Object Storage 服务提供的分布式存储技术。

IBM COS 有以下两种配置可用：**跨区域**和**区域**。“跨区域”服务提供的耐久性和可用性都要高于使用单个区域，但代价是等待时间略长。此服务目前在美国和欧盟可用。“区域”服务的做法则相反：它在单个区域内跨多个可用性专区分发对象。如果给定区域或可用性专区不可访问，对象存储也能继续顺利进行。当不可访问的数据中心重新联机时，将应用所有错过的更改。

## 什么是 IBM Cloud Direct Link？

IBM Cloud Direct Link 是一个产品套件，使客户能够在其远程网络环境与其 IBM Cloud 部署之间创建专用连接。 

## 通过 IBM Cloud Direct Link 使用 Cloud Object Storage (COS)

IBM Cloud Direct Link 系列连接解决方案是一种 IaaS 产品，旨在允许建立与我们的 IaaS 服务的专用 WAN 连接。大多数 IBM Cloud PaaS 和 SaaS 解决方案都是基于 IaaS 构建的。因此，您可以从 IBM Cloud 中发起这些类型的连接。

以下三种方法可帮助您使用 IBM Cloud Direct Link 连接到 IBM Cloud PaaS 和 SaaS。目前，建议使用方法 #3，因为该方法经过了最全面的测试。

## 通过 Direct Link 连接到 PaaS 和 SaaS 的三种方法


### 方法 1：使用虚拟路由器设备（VRA，有时称为 Vyatta）来创建“中继段到公用”
 
![vyatta-flow.png](images/vyatta-flow.png)



**基本前提：通过“公用中继段”连接到 IBM COS，从而连接到存储端点**
*此“公用中继段”从不离开 IBM Cloud IaaS 主干。*

* 客户在 IBM COS 客户支持和上线团队的帮助下选择公共端点，然后接收 API 密钥。
* 客户在其内部部署路由器上，添加特定子网的路径，从而确保使用 IBM Cloud Direct Link 顺利传输流量
* 客户在其 VRA 上创建一条路径，以遍历公用网络并访问 IBM COS 服务的公共端点
* 客户必须供应 VRA 硬件的 HA 对 (@x)
* 每个 VRA 成员会收到每月 20 TB 的自含带宽，以抵消公共云测量和计费的费用
* 在托管服务器之间使用带宽池以累计预付费带宽。


### 方法 2：云服务器传递（专用到专用）

![reverse=proxy](images/reverse-proxy.png)

**基本前提：使用 COS 凭证来信任云服务器**

 * 客户机在 IBM Cloud 中供应一个或多个服务器、VSI 或裸机
 * 每个服务器托管一个基于 Web 的应用程序或通过脚本编制（Java、Python、PHP 等）的应用程序，以仅在其专用接口上侦听连接和请求
 * 服务器应用程序使用自己的 API 或模拟（部分）S3
 * IBM Cloud 服务器专用接口相当安全。使用 VLAN、安全组、操作系统防火墙或 VRA 来隔离专用网络中的访问权
 * 用于验证调用者和限制 API 访问的措施是明智的
 * 客户内部部署网络中的客户机使用云传递服务器的专用 IP 地址作为请求的目标
 * 需要客户机路由和 DNS 更改
 * 服务器托管的应用程序通过向专用 COS 端点发出已认证的 API 调用来处理每个请求，然后将响应返回给调用者

### 方法 3：逆向代理（专用到专用）

这是目前建议采用的方法。

**基本前提：使用 COS 凭证来信任内部部署客户机调用者**

 

 * 此方法是在方法 2 的基础上进行的改动。此方法不是在云服务器上托管 Web 应用程序，而是托管针对逆向代理配置的 HTTPS 服务器（例如 NGINX）。
 * 每个服务器都会使用自签发证书侦听 HTTPS，并将请求直接传递给下面所引用文档中提供的专用 COS 端点：
 
 ![COS 端点](https://console.bluemix.net/docs/services/cloud-object-storage/basics/endpoints.html)
 
### 查看有关如何提高云可靠性和性能的示例（不特定于 COS）：`serverfault.com`

 * 为了提升规模和弹性，可以部署多个代理服务器。 
 * 在客户机端使用循环法 DNS，以实现基本的故障转移和负载均衡功能。
 * 代理服务器可以放在 VRA 后面以受到保护，也可用于集中日志记录。
 
 ## 管理和供应 IBM Cloud 功能 
 
本部分提供了可以使用 IBM Cloud Direct Link 连接到的某些 IBM Cloud PaaS 和 SaaS 服务产品的文档快速链接。

## 如何供应裸机服务器

有关如何供应裸机的详细指示信息，请参阅[此文档](https://console.bluemix.net/docs/bare-metal/about.html#getting-started-with-bare-metal-servers)。

## 如何供应虚拟路由器设备 (VRA)

有关如何供应 VRA 的详细指示信息，请参阅[此文档](https://console.bluemix.net/docs/infrastructure/virtual-router-appliance/getting-started.html#getting-started)。

## 如何供应 IBM Cloud Object Storage (COS)

 * 有关如何供应 COS 的详细指示信息，请参阅[此文档](https://console.bluemix.net/catalog/services/cloud-object-storage)。
 
 * 使用其中一个（先前列出的）专用端点与供应的 COS 帐户中的存储区或对象进行交互。
