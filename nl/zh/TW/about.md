---

copyright:
  years: 2017, 2018
lastupdated: "2018-08-09"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# 關於 IBM Cloud Direct Link

本章節可讓您瀏覽關於四個 IBM Cloud Direct Link 解決方案每一個的主要功能及好處的更多詳細資料。
  * [**IBM Cloud Direct Link Exchange**](#the-ibm-cloud-direct-link-exchange-solution)
  * [**IBM Cloud Direct Link Connect**](#the-ibm-cloud-direct-link-connect-solution)
  * [**IBM Cloud Direct Link Dedicated**](#the-ibm-cloud-direct-link-dedicated-solution)
  * [**IBM Cloud Direct Link Dedicated Hosting**](#the-ibm-cloud-direct-link-dedicated-hosting-solution)

## IBM Cloud Direct Link Exchange 解決方案

IBM Cloud Direct Link Exchange 解決方案可讓客戶運用 Cloud Exchange 提供者，提供對 {{site.data.keyword.BluSoftlayer_notm}} 位置的連線功能。此供應項目一般提供成本較低的連線功能，因為從 {{site.data.keyword.BluSoftlayer_notm}} 到 Cloud Exchange 提供者的實體連線功能已經就緒，並與其他客戶共用。

**一般使用案例：**_最適合混合式工作負載、跨提供者的工作負載、具有高輸出頻寬的大量或頻繁資料傳送、專用工作負載，以及環境管理。當所要的 PoP 位置已經具有所需 IBM Cloud Direct Link Exchange 提供者時，通常會選取此選項。_

![圖 1](/images/Direct-Link-Exchange.png)

 * **終止位置：**{{site.data.keyword.BluSoftlayer_notm}} 連接點 (PoP)。

 * **一般部署時間：**對於 Equinix 提供者，一般部署時間將以小時為單位。若為其他提供者，則為電路到達交換之後 5-10 天。向 NSP 或通訊業者訂購電路時，部署時間可能整體為 30-60 天，視您的位置及需求而定。

 * **交叉連接詳細資料：**{{site.data.keyword.BluSoftlayer_notm}} 與 Cloud Exchange 提供者之間會維護安全的 Cloud Exchange 交互連接的實體交叉連接。客戶向 Cloud Exchange 提供者要求虛擬電路，這樣會在交互連接至 Cloud Exchange 提供者之後建立對 {{site.data.keyword.BluSoftlayer_notm}} 的邏輯連線功能。

 * **埠速度選項：**選取 50Mbps、100Mbps、200Mbps、500Mbps 或 1Gbps。

 * **約略延遲：**本端區域（具有相同三個字母字首，例如 DAL、AMS、MEL 資料中心）內的延遲大約為 1.5ms。有關即時 PoP 至 PoP (P2P) 位置延遲測量，請參閱 http://lg.softlayer.com/

 * **主機託管服務：**無。

 * **備援：**若要建立 IBM Cloud Direct Link Exchange 的備援，需要 2+ 位置的連線功能，或選擇具有 Cloud Exchange 提供者可用之次要 XCR 的位置。

 * **本端/廣域遞送選項：**本端遞送選項是預設的遞送選項。它提供對與 Direct Link PoP 相同市場內的資料中心存取（以例如 DAL、AMS 或 MEL 表示）。需要「廣域遞送」選項作為附加程式，以便將市場內的 IBM Cloud 資源連接到本端市場外資料中心的其他 IBM Cloud 資源。它用來在 IBM Cloud 資源之間共用工作負載（例如達拉斯對阿什本，或達拉斯對法蘭克福）。
 
## IBM Cloud Direct Link Connect 解決方案

**一般使用案例：**類似於 Direct Link Exchange 解決方案。提供更多速度選項。Direct Link Cloud Connect 解決方案提供 IBM Cloud 網路客戶的較低成本進入點。

![圖 2](/images/Direct-Link-Connect.png)

* **終止位置：**{{site.data.keyword.BluSoftlayer_notm}} 連接點 (PoP)。

* **一般部署時間：**電路聯繫交換之後 5-10 天。向 NSP 或通訊業者訂購電路時，部署時間可能整體為 30-60 天，視您的位置及需求而定。

* **交叉連接詳細資料：**{{site.data.keyword.BluSoftlayer_notm}} 與 Connect 提供者之間會維護安全的 Direct Link Connect 交互連接的實體交叉連接。客戶向 Cloud Connect 提供者要求虛擬電路，這樣會在交互連接至 Cloud Connect 提供者之後建立對 {{site.data.keyword.BluSoftlayer_notm}} 的邏輯連線功能。

* **埠速度選項：**選取 50Mbps、100Mbps、200Mbps、500Mbps、1Gbps、2Gbps 或 5Gbps。

* **約略延遲：**本端區域（具有相同三個字母字首的資料中心，例如 DAL、AMS、MEL）內的延遲大約為 1.5ms。有關即時 PoP 至 PoP (P2P) 位置延遲測量，請參閱 http://lg.softlayer.com/

* **主機託管服務：**無。

* **備援：**若要建立 IBM Cloud Direct Link Connect 的備援，需要 2+ 位置的連線功能，或選擇具有 IBM Cloud Connect 提供者可用之次要 XCR 的位置。

* **本端/廣域遞送選項：**本端遞送選項是預設的遞送選項。它提供對與 Direct Link PoP 相同市場內的資料中心存取（以例如 DAL、AMS 或 MEL 表示）。需要「廣域遞送」選項作為附加程式，以便將市場內的 IBM Cloud 資源連接到本端市場外資料中心的其他 IBM Cloud 資源。它用來在 IBM Cloud 資源之間共用工作負載（例如達拉斯對阿什本，或達拉斯對法蘭克福）。

## IBM Cloud Direct Link Dedicated 解決方案

IBM Cloud Direct Link Dedicated 讓客戶將專用、單一模式的光纖交叉連接連入到他們自己的 {{site.data.keyword.BluSoftlayer_notm}} 專用網路。

 **一般使用案例：**_最適合使用混合式工作負載、跨提供者的工作負載、大量或頻繁的資料傳送、專用工作負載，以及環境管理。這個選項的選取時機通常為：(1) 想要的 PoP 沒有想要的 IBM Cloud Direct Link Exchange 提供者時，(2) 需要高傳輸量的高效能工作負載，或 (3) IBM Cloud Direct Link Exchange 實作模型所無法滿足的法規遵循需求。_

![圖 3](/images/Direct-link-Dedicated.png)

 * **終止位置：**{{site.data.keyword.BluSoftlayer_notm}} 連接點 (PoP)。

 * **一般部署時間：**新的電路達到 POP 之後 10-15 個營業日。向 NSP 或通訊業者訂購電路時，部署時間可能整體為 30-60 天，視您的位置及需求而定。

 * **交叉連接詳細資料：**{{site.data.keyword.BluSoftlayer_notm}} 提供授權信 (LOA)，客戶用它來訂購從客戶機箱或提供者連到 {{site.data.keyword.BluSoftlayer_notm}}
CFA 終止點的光纖乙太網路（僅限單一模式光纖、1Gig-LX 或 10Gig-LR 光學設備）。CFA 終止點將限制在交叉連接路由器 (XCR) 基礎架構。媒介必須是 1310nm 波長的光學設備。

 * **埠速度選項：**選取 1Gbps、2Gbps、5Gbps 或 10Gbps。

 * **約略延遲：**本端區域（具有相同三個字母字首的資料中心，例如 DAL、AMS、MEL）內的延遲大約為 1.5ms。有關即時 PoP 至 PoP (P2P) 位置延遲測量，請參閱 http://lg.softlayer.com/

 * **主機託管服務：**無。

 * **備援：**若要建立備援，需要對 2+ 位置的 IBM Cloud Direct Link 連線功能，或選擇具有次要 XCR 可用的位置以及第二條 IBM Cloud Direct Link 連線的要求。

 * **本端/廣域遞送選項：**本端遞送選項是預設的遞送選項。它提供對與 Direct Link PoP 相同市場內的資料中心存取（以例如 DAL、AMS 或 MEL 表示）。需要「廣域遞送」選項作為附加程式，以便將市場內的 IBM Cloud 資源連接到本端市場外資料中心的其他 IBM Cloud 資源。它用來在 IBM Cloud 資源之間共用工作負載（例如達拉斯對阿什本，或達拉斯對法蘭克福）。

## IBM Cloud Direct Link Dedicated Hosting 解決方案

IBM Cloud Direct Link Dedicated Hosting 解決方案提供與 IBM Cloud Direct Link Dedicated 類似的連線功能，但連線點與 {{site.data.keyword.BluSoftlayer_notm}} 資料中心相鄰，這樣可改善較高效能使用案例的延遲。IBM Cloud 透過簡單計價，以此解決方案提供各種可自訂的主機託管服務。

**一般使用案例：**_最適合使用非標準的運算技術、專用儲存空間需求，或利用現有的 IT 投資。_

![圖 4](/images/Direct-Link-Dedicated-Hosting.png)

* **終止位置：**{{site.data.keyword.BluSoftlayer_notm}} 資料中心 (DC)。

 * **一般部署時間：**所有需求都確定且已執行合約之後 30-60 天。

 * **交叉連接詳細資料：**{{site.data.keyword.BluSoftlayer_notm}} 提供 1G 或 10G 光纖連線，從 {{site.data.keyword.BluSoftlayer_notm}} 交叉連接路由器 (XCR) 基礎架構到部署當中的客戶主機託管環境。如果未要求主機託管服務（如果現有環境已經連接的話），{{site.data.keyword.BluSoftlayer_notm}} 會提供授權信 (LOA)，客戶用它來訂購從客戶機箱連到 {{site.data.keyword.BluSoftlayer_notm}}
CFA 終止點的光纖乙太網路（僅限單一模式光纖、1Gig-LX 或 10Gig-LR 光學設備）。CFA 終止點將限制在交叉連接路由器 (XCR) 基礎架構。媒介必須是 1310nm 波長的光學設備。

 * **埠速度選項：**選取 1Gbps、2Gbps、5Gbps 或 10Gbps。

 * **約略延遲：**本端資料中心內的延遲大約為 0.5ms。

 * **主機託管服務：**是。

 * **備援：**{{site.data.keyword.BluSoftlayer_notm}} 在產品中提供對兩台交叉連接路由器 (XCR) 的連線。若要建立備援連線功能，客戶必須在每一個 Direct Link 連線上配置他們認為適合達到備援的 BGP。範例包括諸如這些選項：_偏好最低 MED_、_偏好最高的區域喜好設定_，或_偏好較短的 AS 路徑_。

 * **本端/廣域遞送選項：**本端遞送選項是預設的遞送選項。它提供對與 Direct Link PoP 相同市場內的資料中心存取（以例如 DAL、AMS 或 MEL 表示）。需要「廣域遞送」選項作為附加程式，以便將市場內的 IBM Cloud 資源連接到本端市場外資料中心的其他 IBM Cloud 資源。它用來在 IBM Cloud 資源之間共用工作負載（例如達拉斯對阿什本，或達拉斯對法蘭克福）。
