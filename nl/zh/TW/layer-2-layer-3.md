---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-30"

keywords: layer 2, layer 3, interconnect, partner, multi-cloud, other clouds, BGP, XCR

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# 比較 Direct Link 的第 2 層及第 3 層連線
{: #comparing-layer-2-layer-3}

{{site.data.keyword.cloud}} Direct Link 接受來自網路服務提供者 (NSP) 的 OSI 第 2 層及第 3 層合作夥伴交互連接。部分網路服務提供者在不同網路上提供這兩層的服務，不過，部分提供者可能已選擇**不要**將其所有網路交互連接至 {{site.data.keyword.cloud_notm}}。 

規劃 {{site.data.keyword.cloud_notm}} Direct Link 部署時，請考量與第 2 層及第 3 層連線相關聯的特徵，因此您可以建立最符合需求的部署。

## 第 2 層連線的考量
{: #layer-2-networks}

對於您將使用第 2 層合作夥伴交互連接所建立的每個 VLAN 型虛擬電路，必須在內部部署路由器與 IBM Cloud XCR 之間配置並建立 BGP 階段作業。IBM Cloud 將提供 `/31` IPv4 指派，以與路由器建立 BGP 階段作業。

* 第 2 層網路提供的選項，讓企業與 {{site.data.keyword.cloud_notm}} 之間具有簡單的一對一連線。 
* 第 2 層服務依據 VLAN 而非 IP 位址。 
* 第 2 層服務的成本可能較低、延遲較少，且其額外負擔可能比第 3 層服務少。 
* 第 2 層網路不會對企業可啟用的第 3 層特性強加限制。

## 第 3 層連線的考量
{: #layer-3-networks}

若為第 3 層連線，對於每個「虛擬電路」，您的服務提供者會在 IBM Cloud XCR 與提供者的邊緣路由器之間建立 BGP 階段作業。您不需要為內部部署路由器配置 BGP 與 IBM Cloud，因為服務提供者將會管理與 IBM Cloud 的 BGP 配置。

* 第 3 層 IP VPN 或 AVPN 網路可啟用「任意對任意」連線功能。 
* 第 3 層網路需要網路服務提供者，才能在企業與 {{site.data.keyword.cloud_notm}} 之間維護 BGP 階段作業。 
* 特定網路服務提供者在使用第 3 層連線（例如 ASN prepend、GRE 通道作業等）時，可能會限制其整個網路中的特定功能。請務必向您的提供者洽詢可能的限制。

## 合作夥伴交互連接表格
{: #partner-interconnection-table}

下表彙總每個 {{site.data.keyword.cloud_notm}} 合作夥伴所提供的連線類型。 

|合作夥伴|交互連接類型|  
|-------|-------|
|AT&T NetBond® for Cloud|第 3 層|
| AT&T Cloud Gateway（以前稱為 RedFringe）|第 3 層|
|Bell Canada |第 3 層| 
|British Telecom |第 3 層| 
|CenturyLink IP VPN|第 3 層| 
|CenturyLink Dynamic Connections|第 2 層| 
| Chief Telecomm |第 2 層|
|Colt |第 2 層| 
| Console Connect by PCCW |第 2 層|
| Digital Realty Service Exchange |第 2 層| 
| Epsilon |第 2 層| 
| IBM BlueFringe |第 3 層| 
| Intercloud |第 3 層|
|Megaport |第 2 層|
| MWS GNPP |第 3 層|
| Neutrona |第 2 層|
| NTT |第 3 層|
|PacketFabric |第 2 層|
| Softbank |第 3 層|
| SES Networks |第 2 層|
| Tata IZO™ Private Connect  |第 3 層| 
|Telia |第 3 層|
|Telstra |第 3 層|
| Tokai |第 2 層| 
| Verizon SCI|第 3 層|
| Zayo Cloud Link |第 2 層|
