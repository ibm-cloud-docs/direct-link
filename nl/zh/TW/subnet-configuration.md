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

建立 {{site.data.keyword.cloud}} Direct Link 連線功能之後，您可以遵循本文件提供的步驟，配置您的子網路以與 {{site.data.keyword.cloud_notm}} 互動。

一般而言，若要讓您的 {{site.data.keyword.cloud_notm}} Direct Link 連線運作，您需要進行一些基本網路配置步驟，然後設定「邊界閘道通訊協定 (BGP)」。在設定過程期間，IBM 工程師會與您合作，讓您的網路能使用「虛擬遞送功能 (VRF)」功能，此為必要項目。

## 基本網路配置
{: #basic-network-configuration}

1. 使用標準 RFC1918 專用位址空間定義您的遠端網路。 
 * 若為新的環境，建議**不要**使用 10.0.0.0/8 空間。 
 * 若為使用 10.0.0.0/8 的現有環境，我們建議您取得更詳細的評量，以確保不會與 {{site.data.keyword.cloud_notm}} 服務網路衝突，或與已經指派給您帳戶的網路衝突。

2. 我們的 {{site.data.keyword.cloud_notm}} 人員會指派 /31 或 /30 給每個連線，並在 {{site.data.keyword.cloud_notm}} 交叉連接路由器 (XCR) 基礎架構上配置介面 IP 位址。  

3. 在您的客戶邊緣路由器 (CER) 上使用我們提供的 IP 位址配置介面：利用 {{site.data.keyword.cloud_notm}} XCR IP 作為目的地為 {{site.data.keyword.cloud_notm}} 之任何資料流量的下個躍點。 

4. 對於返回資料流量，{{site.data.keyword.cloud_notm}} 會利用已指派的 CER IP，作為目的地為遠端網路之任何資料流量的下個躍點，如同 BGP 所通告。

## 配置 BGP
{: #configuring-bgp}

為了與您的環境交換路徑資訊，{{site.data.keyword.cloud_notm}} 需要配置 BGP。  

1. **ASN**：{{site.data.keyword.cloud_notm}} 指派專用 ASN 供每位客戶使用。或者，您也可以利用自己的公用 ASN。您的喜好設定會在您下單時要求。已指派的專用 ASN 會在實作過程期間提供給您。

2. **VRF**：{{site.data.keyword.cloud_notm}} 會使用 VRF 通告指派給您的客戶帳戶的特定專用子網路。您必須通告想要可以從 {{site.data.keyword.cloud_notm}} 專用網路聯繫的遠端網路。身為客戶的您必須負責管理與 IBM Cloud 網路之間的通告。（關於 VRF 的更多詳細資料包含於下一節。）

下列網路會被過濾掉，無法接受：0.0.0.0、10.0.0.0/14、10.198.0.0/15、10.200.0.0/14、169.254.0.0/16、224.0.0.0/4。
{:note}

3. **ECMP**：對於選擇在支援的位置建置備援的客戶，{{site.data.keyword.cloud_notm}} 支援實作等價多路徑 (ECMP) 以提供兩個鏈結之間的負載平衡和備援。這項 ECMP 設定應該在訂購時要求。

## IBM Cloud Direct Link 的 BGP 規格
{: #bgp-specifications-for-ibm-cloud-direct-link}

BGP 規格如下所示：

如前一節所述，BGP 是管理透過 Direct Link 的遞送時必要的項目。訂購 Direct Link 的帳戶將移轉至 VRF 環境。

**對於 VLANS 及 VRF 的警示：**
 * VRF 環境中不容許帳戶間的 VLAN 跨越。 
 * IPSEC VPN 服務受限制。 
 
VRF 不會阻止 SSL 或 PPTP VPN 存取，但行為會變更。沒有 VRF 的情況下，一個 VPN 連線就足以查看您帳戶上的所有伺服器。使用 VRF 時，您只能存取市場中與您的 VPN 相關聯的資源。因此，如果您連接至 DAL VPN，則只能連接至 DAL 伺服器。
{: note}

IBM Cloud ASN 是適用於「公用」和「專用」服務的 **13884**。 
 * 訂購時客戶的預設 ASN 為 **64999**，但可以應客戶要求變更此預設值。 
 * 選擇性地，可支援 4201000000 與 4201064511 之間的 4 位元組「專用 ASN」。
 * 如果您使用 Direct Link Connect 搭配第 3 層服務（例如 IP VPN），則 IBM Cloud 將透過 Direct Link Connect 提供者的 ASN 建立 BGP

**建議、預設值和限制：**

 * 通道作業（亦即 GRE）受到支援，如果 IP 重疊變成問題時建議使用通道作業。
 * BGP 計時器預設值為 `keepalive:30`、`holdtime:60`。
 * 依預設，不會啟用鑑別。
 * 依預設，不會啟用 BGP BFD。
 * 每 VRF 的最大接收（來自客戶或提供者）字首限制為 200。
 
## IP 指派的嚴格限制
{: #strict-limitations-on-ip-assignments}

 * 如果您使用 10.x.x.x 網路，您仍然無法與 IBM Cloud 內的主機或 IBM Cloud 服務網路（其佔用 `10.0.0.0/14`、`10.198.0.0/15` 及 `10.200.0.0/14`）建立重疊。  

 * 下列範圍在 Federal 系統中不被接受，將遭到 IBM 伺服器拒絕：`169.254.0.0/16`、`224.0.0.0/4`。

## 備援與多樣性
{: #redundancy-and-diversity}

{{site.data.keyword.cloud_notm}} Direct Link 提供多樣性，而客戶則負責透過他們的 BGP 綱目實作備援。

如果您選取 ECMP 來進行備援，兩個 BGP 階段作業都必須存在於相同的 XCR；因此您會放棄路由器多樣性，而冒著路由器萬一故障所致的風險。您得到第 3 層備援，但失去路由器多樣性。

## 使用 VRF 的詳細資訊
{: #more-about-using-vrf}

利用 {{site.data.keyword.cloud_notm}} Direct Link 解決方案的所有帳戶都必須移轉至 VRF。藉由使用 VRF，客戶會通告自行定義之遠端網路的可用路徑。請注意，此配置不允許您在 {{site.data.keyword.cloud_notm}} 網路上利用自行定義的 IP 位址。

移轉至 VRF 會在設定過程期間完成。它需要短暫的中斷時間範圍（對於具有多個 VLAN/位置的大型帳戶最多 30 分鐘），在這期間後端網路 VLAN 移動到 VRF 時會失去彼此的連線功能。VRF 移轉由實作的工程師排定。

請注意，VRF 刪除了您帳戶的「VLAN 跨距」選項，包括任何帳戶對帳戶的 VLAN 跨距功能，因為所有 VLAN 都能通訊，除非引入了「閘道應用裝置」來管理資料流量。VRF 限制了使用 {{site.data.keyword.cloud_notm}} VPN 服務的能力，因為它與 {{site.data.keyword.cloud_notm}} SSL、PPTP 及 IPSec VPN 服務並不完全相容。   

替代方案是使用 IBM Cloud Direct Link 供應項目本身來管理您的伺服器，或是自行執行可以配置為不同類型 VPN 的 VPN 解決方案（例如 Vyatta）。移轉至 VRF 之後，SSL VPN 通常會在對運算 VM 執行所在之相同資料中心位置建立 VPN 連線時運作，但它不允許廣域存取。

## 使用 BYOIP 及 NAT 搭配 Direct Link
{: #using-byoip-and-nat-with-direct-link}

IBM Cloud Direct Link 不在專用網路上提供 BYOIP。因此，將會捨棄目的地 IP 位址不是由 {{site.data.keyword.cloud_notm}} 指派的資料流量。不過，客戶可以使用 GRE、IPSec 或 VXLAN 封裝遠端網路與其 {{site.data.keyword.cloud_notm}} 網路之間的資料流量。  

最常見的情況是，BYOIP 環境是在網路閘道 (Vyatta) 或 VMWare NSX 部署的範圍內實作。此配置讓客戶能在 {{site.data.keyword.cloud_notm}} 端使用任何想要的 IP 空間，以及透過通道遞送回遠端網路。請注意，此配置必須由客戶管理及支援，與 {{site.data.keyword.cloud_notm}} 無關。再者，如果客戶指派了 {{site.data.keyword.cloud_notm}} 用於服務的 10.x.x.x 區塊，此配置可能會岔斷與 {{site.data.keyword.cloud_notm}} 服務網路的連線功能。 

此解決方案還要求，需要連接至 {{site.data.keyword.cloud_notm}} 服務網路及遠端網路的每台主機都必須被指派 2 個 IP 位址：一個必須從 IBM 10.x.x.x 區塊指派，另一個則從遠端網路區塊指派。主機上必須已設定靜態路徑，以確保適當地遞送資料流量。您無法直接在 {{site.data.keyword.cloud_notm}} 主機 (BYOIP) 上指派 IP 空間，也無法讓該資料流量可在 {{site.data.keyword.cloud_notm}} 網路上遞送。實作此功能的唯一方式就是執行上述方法，但 {{site.data.keyword.cloud_notm}} 並不支援。

或者，客戶可以經常指派遠端網路區塊，以在其遠端邊緣路由器上配置的 NAT 表格中使用。此配置讓客戶可以限制兩個網路所需的變更，同時仍將資料流量轉換成與兩個網路相容的網址空間。
