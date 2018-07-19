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

# 結合：IBM Cloud Direct Link 與 IBM Cloud Object Storage

本文件說明如何配置 IBM Cloud Direct Link，以存取 IBM Cloud Object Storage 及其他 IBM Cloud 服務。有幾種方法可從 IBM Cloud Direct Link 所在的專用 IBM Cloud IaaS 網路橋接到支援 IBM Cloud PaaS 及 SaaS 功能的「公用」網路，而不需要真的離開 IaaS 骨幹。

依現行原則，IBM Cloud 專用服務端點無法透過 IBM Cloud Direct Link 存取。本文件中所述的技術仰賴透過 IBM Cloud 所管理之系統的間接存取。雖然專用服務端點無法透過 Direct Link 呼叫到，但客戶的專用伺服器和軟體驅動裝置可以呼叫到。

## 何謂 IBM Cloud Object Storage (COS)？

IBM Cloud Object Storage 是一種可儲存非結構化資料的 Web 規模平台。它提供可靠性、安全、可用性及災難回復，而不進行抄寫。 

隨 IBM Cloud Object Storage 儲存的資訊已加密，並分散在多個地理位置。可透過 S3 API 的實作來存取它。本服務利用 IBM Cloud Object Storage 服務所提供之分散式儲存技術。

IBM COS 提供兩種配置：**跨區域**和**區域**。「跨區域」服務提供的延續性和可用性比使用單一區域更高，但代價是延遲稍高。目前美國和歐盟有提供此服務。「區域」服務剛好相反：它在單一地區內的多個可用性區域之間分散物件。如果給定的區域或可用性區域無法存取，物件儲存庫會繼續順利運作。當無法存取的資料中心重新連線時，會套用任何遺漏的變更。

## 何謂 IBM Cloud Direct Link？

IBM Cloud Direct Link 是一個產品組合，可讓客戶在他們的遠端網路環境與其 IBM Cloud 部署之間建立專用連線。 

## 透過 IBM Cloud Direct Link 使用 Cloud Object Storage (COS)

連線功能解決方案的 IBM Cloud Direct Link 系列是 IaaS 供應項目，旨在容許專用 WAN 連線至我們的 IaaS 服務。大部分 IBM Cloud PaaS 和 SaaS 解決方案都建置在我們的 IaaS 之上。因此，您可以從 IBM Cloud 中起始這些類型的連線。

這三種方法可協助您使用 IBM Cloud Direct Link 來連接至 IBM Cloud PaaS 及 SaaS。目前，方法 #3 是建議的方法，因為它已經過充分測試。

## 透過 Direct Link 連線到 PaaS 和 SaaS 的三個方法


### 方法 1：使用 Virtual Router Appliance（VRA，有時稱為 Vyatta）來建立「躍點至公用」
 
![vyatta-flow.png](images/vyatta-flow.png)



**基本前提：連接至具有「公用躍點」的 IBM COS 來連接至儲存空間端點**
*此「公用躍點」絕不離開 IBM Cloud IaaS 骨幹。*

* 客戶選擇「公用」端點，由 IBM COS 客戶支援中心及上線小組協助，並接收 API 金鑰。
* 在其內部部署路由器上，客戶會將路徑新增至特定子網路，從而確保使用 IBM Cloud Direct Link 的資料傳輸流順暢
* 在其 VRA 上，客戶會建立路徑來遍訪公用網路及連上 IBM COS 服務的公用端點
* 客戶必須佈建 VRA 硬體 HA 配對 (@x)
* 每一個 VRA 成員每月接收 20TB 併入頻寬，以抵銷您的「公用」雲端計量及計費
* 在受管理伺服器上使用頻寬儲存區，以累計預付頻寬。


### 方法 2：雲端伺服器透通（專用到專用）

![reverse=proxy](images/reverse-proxy.png)

**基本前提：具有 COS 認證的 Trust Cloud 伺服器**

 * 用戶端在 IBM Cloud 佈建一個以上的伺服器、VSI 或裸機伺服器
 * 每個伺服器管理一個 Web 型或 Script 化（Java、Python、PHP 等）應用程式，僅在其專用介面上接聽連線及要求
 * 伺服器應用程式使用自己的 API 或模擬（部分的）S3
 * IBM Cloud 伺服器專用介面非常安全。使用 VLAN、安全群組、OS 防火牆或 VRA，在專用網路中進行隔離存取
 * 驗證呼叫者及限制 API 呼叫的措施很聰明
 * 客戶內部部署網路上的用戶端使用雲端透通伺服器的專用 IP 位址作為要求的目標
 * 需要用戶端遞送和 DNS 變更
 * 伺服器管理的應用程式處理每一個要求的方法是對專用 COS 端點發出已鑑別的 API 呼叫，將回應傳回給呼叫者

### 方法 3：反向 Proxy（專用對專用）

這個方法是目前建議的方法。

**基本前提：具有 COS 認證的 Trust 內部部署用戶端呼叫者**

 

 * 這改寫方法 2，它不管理雲端伺服器上的 Web 應用程式，而是管理為反向 Proxy 配置的 HTTP 伺服器（例如，NGINX）。
 * 每個伺服器在具有自發憑證的情況下接聽 HTTPS，並直接將要求傳遞給專用 COS 端點（下列參照的文件中所提供）：
 
 ![COS 端點](https://console.bluemix.net/docs/services/cloud-object-storage/basics/endpoints.html)
 
### 檢視如何改進雲端的可靠性和效能的範例（非特定於 COS）：`serverfault.com`

 * 若要提高規模與備援，可部署多個 Proxy 伺服器。 
 * 在用戶端使用循環式 DNS，以提供初步失效接手和負載平衡功能。
 * Proxy 伺服器可以放在 VRA 後面，以便保護和集中化記載。
 
 ## 管理及佈建 IBM Cloud 功能 
 
本節提供您可以使用 IBM Cloud Direct Link 連接的一些 IBM Cloud PaaS 及 SaaS 供應項目之文件的快速鏈結。

## 如何佈建裸機伺服器

如需如何佈建裸機伺服器的詳細指示，請參閱[此文件](https://console.bluemix.net/docs/bare-metal/about.html#getting-started-with-bare-metal-servers)。

## 如何佈建 Virtual Router Appliance (VRA)

如需如何佈建 VRA 的詳細指示，請參閱[此文件](https://console.bluemix.net/docs/infrastructure/virtual-router-appliance/getting-started.html#getting-started)。

## 如何佈建 IBM Cloud Object Storage (COS)

 * 如需如何佈建 COS 的詳細指示，請參閱[此文件](https://console.bluemix.net/catalog/services/cloud-object-storage)。
 
 * 使用其中一個專用端點（先前所列出）與您佈建的 COS 帳戶中的儲存區或物件連接。
