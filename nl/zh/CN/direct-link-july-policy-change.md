---
copyright:
  years: 2018, 2019
lastupdated: "2019-04-02"

keywords: Intercloud, Frankfurt, PoPs, Connect, Exchange, Chennai, Equinix, Megaport, Kinx, diversity, Bluefringe, CenturyLink, BT, Sao Paulo, Tokyo, Japan, PCCW, Colt, blog, service provider, partner, Telia, Internexion, Packet Fabric, Global Routing, expanded, market

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:important: .important}

# 声明：全球路由策略变更将于 7 月 1 日开始

2019 年 7 月 1 日生效 - IBM Direct Link 全球路由策略变更
{: important}

为了改进客户体验并提供更大的价值，我们将增强 IBM Direct Link 全球路由服务。主要改进包括：

* **扩展的本地市场：**我们正在确保客户可以在其本地市场中连接的站点的一致性。我们正在调整 IBM Cloud 网络中的每个 PoP 站点，以使连接到我们 PoP 站点中 IBM Cloud 的客户能够连接到全球范围内一个或多个数据中心内的资源。

* **新的定价模型：**为了更好地使定价与所选连接速度协调一致，我们正在更改 IBM Direct Link 全球路由服务的定价模型。

* **无限制的 Direct Link 流量：**对于在 IBM Cloud PoP 与全球数据中心之间有 Direct Link 专用网络流量的本地或全球路由的客户，我们将除去网络流量超额费用。

## IBM Cloud Direct Link 全球路由概述
{: #ibm-cloud-direct-link-global-routing-overview}

所有当前 Direct Link 产品都包含本地路由，无需额外付费。此服务包括对 Direct Link 连接所在本地市场中的数据中心的访问权。它通过 Direct Link 专用连接提供针对客户帐户中的 IBM Cloud 资源的输入和输出流量。对于“本地路由”选项，Direct Link 流量仅限于此本地市场提供的服务。

要路由 Direct Link 所连接的本地市场外部的网络流量（PoP 或数据中心），您必须添加“全球路由”选项，该选项扩展访问权以包括全球所有 IBM Cloud 数据中心。

全球路由应用于单个 Direct Link 服务。全球路由不通过聚集来应用。它必须在需要给定市场之外的连接的每个 Direct Link 服务上进行指定。

## 扩展的 IBM Direct Link 本地市场
{: #announce-expanded-ibm-direct-link-local-markets}

我们正在扩展 Direct Link 本地市场，以向全球客户提供更多本地路由选项。下面列出了新的本地市场分配：

* 达拉斯本地市场现在将包括丹佛、休斯顿和芝加哥 PoP。
* 华盛顿特区本地市场现在将包括纽约、亚特兰大和迈阿密 PoP。
* 圣何塞本地市场现在将包括洛杉矶 PoP。
* 奥斯陆本地市场现在将包括斯德哥尔摩 PoP。
* 悉尼本地市场现在将包含珀斯 PoP。
* 香港本地市场将包括台北 PoP（推出后）。
* 东京本地市场将包括大坂 PoP（推出后）。
* 金奈本地市场将包括孟买 PoP（推出后）。

以下网址中的各个表中概述了这些更改：https://cloud.ibm.com/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#expanded-ibm-direct-link-local-markets

## IBM Cloud Direct Link 全球路由定价模型
{: #announce-ibm-cloud-direct-link-global-routing-pricing-model}

有了所有 IBM Cloud Direct Link 产品，本地市场中的网络路由是标准的。从 2019 年 7 月 1 日起，“全球路由”选项的定价将与 Direct Link 连接的连接速度协调一致。此协调将通过可用于 Direct Link 产品的所有连接速度为客户提供更好的价值。

定价位于 https://cloud.ibm.com/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#pricing-for-global-routing-add-on

## IBM Cloud Direct Link 全球路由网络传输超额费用
{: #announce-ibm-cloud-direct-link-global-routing-network-transit-overage-charges}

在此声明中，我们还撤销了使用“全球路由”选项的客户的网络传输限制和超额费用。先前的定价包括客户本地市场外的输出流量的网络传输限额和超额费用。新的定价将取消这些网络流量费用。与此声明同时生效的是，Direct Link 连接中的输入和输出流量不会产生超额费用。

## 生效日期
{: #announce-effective-date}

这些变更将于 2019 年 7 月 1 日（星期一）生效，将适用于此日期之后的下一个计费周期的所有新订单。

请务必注意，通过此更新的自动化，任何需要全球路由的 Direct Link 电路都应该在此日期之前进行相应更新。Direct Link 服务的任何升级或降级都将生成用于验证全球路由是否存在的自动化操作。如果全球路由不存在，那么 Direct Link 电路中的任何流量都将仅限于本地市场。

我们强烈推荐客户在 Direct Link 服务上查看其 IBM Cloud 路由，并开具凭单以修复现有 Direct Link 服务上的路由。
