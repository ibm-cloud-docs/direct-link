---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-06-12"

keywords: provisioning, Exchange, order, support, ticket, diverse, virtual circuit, parameters, Terms and Conditions, legacy, customer, portal

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

# 透過舊式客戶入口網站佈建 IBM Cloud Direct Link Exchange
{: #provisioning-ibm-cloud-direct-link-exchange-legacy}

本頁面示範如何從 {{site.data.keyword.cloud_notm}} 舊式客戶入口網站訂購 {{site.data.keyword.cloud}} Direct Link Exchange 服務。
{: shortdesc}

如果 {{site.data.keyword.cloud_notm}} Direct Link 訂單是針對 Equinix Cloud Exchange，則服務佈建會完全自動化，這表示您可以[訂購 IBM Cloud Direct Link 連線 (Equinix) 而不必開立 IBM 支援問題單](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix-legacy)。

自動化功能目前僅限於 Equinix Cloud Exchange。在後續的版本中，將會為其他提供者啟用自動化。
{:note}

## 必要條件
{: #cloud-exchange-prerequisites-legacy}

若要使用自動化功能，您的專用 VLAN 必須與 {{site.data.keyword.cloud_notm}} 專用網路中的 VRF 相關聯。如果未符合此需求，當您透過客戶入口網站下訂單時，將會產生 IBM 支援問題單。

 * [如何訂購 Cloud Exchange](#how-to-order-cloud-exchange-no-equinix-legacy)
 * [如何訂購 Cloud Exchange for Equinix](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix-legacy)

## 如何訂購 Cloud Exchange
{: #how-to-order-cloud-exchange-no-equinix-legacy}

若要佈建 IBM Cloud Direct Link Exchange 連線，請完成下列步驟：

**步驟 1：**

在[客戶入口網站 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://control.softlayer.com/) 上登入您的客戶帳戶。

**步驟 2：**

在**網路**標籤下，選取 **Direct Link -> Exchange**，這會開啟頁面顯示任何現有的 IBM Cloud Direct Link 連線。

![步驟 2](/images/Equinix-Step2.png)

**步驟 3：**

按一下頁面頂端的**訂購 Direct Link Exchange** 按鈕之後，您將會看到訂單表格，您可以在這裡輸入 IBM Cloud Direct Link Exchange 連線的配置參數。

![步驟 3](/images/Equinix-Step3.png)

**步驟 3A：**

如果可以存取多樣化埠，且您先前已佈建第一個「虛擬電路」，則會看到類似下列的畫面，其中顯示兩個埠，您可以選擇性地從中選取第二個「虛擬電路」。

![2-port-image](/images/exchange-2-ports-image.png)

**步驟 4：**

在訂單表格中，輸入下列參數以配置 Direct Link：
  * 輸入 IBM Cloud Direct Link 連線名稱。
  * 從清單中，選取您要建立 IBM Cloud Direct Link 連線的 PoP 位置。
  * 從清單中，選取您喜好的 Cloud Exchange 提供者名稱。
  * 選取連線所需的鏈結速度。
  * 選取連線所需的遞送選項。
  * 針對 BGP 交換，輸入來自資訊方框中所給定範圍的 ASN 號碼。

**步驟 5：**

當您選取或輸入這些值時，可以在左邊的畫面看到約略的每月費用。

![步驟 4-5](/images/Equinix-Step4-5.png)

**步驟 6.**

提供輸入值之後，下一個使用者介面畫面會顯示根據您所選取選項的實際每月定價。

**步驟 7：**

您必須**同意**條款，然後才能訂購 IBM Cloud Direct Link。請仔細閱讀條款，因為它們包含您在繼續之前必須瞭解的重要技術資訊。 

如果不接受條款，則下訂單時會產生 IBM 支援問題單。
{:note}

接下來的圖顯示您可能會看到的畫面，視您在這個步驟選取的內容而定。

下圖顯示「條款」畫面：

![步驟 7](images/Equinix-Step7.png)

下圖顯示如果您下訂單時未同意條款，可能會看到的畫面。畫面上顯示產生的問題單號碼：

![步驟 7 同意](/images/Equinix-Step7-NoAgree.png)

下圖顯示正在開立問題單的範例：

![步驟 7 問題單](/images/Equinix-Step7-NoAgree-Ticket.png)

**步驟 8：**

同意條款之後，當您下訂單時，會在下訂單之後產生 IBM 支援問題單，以繼續服務佈建。在您下訂單之後，問題單號碼會顯示在使用者介面中。 

![步驟 NE1](/images/Non-Equinix-Step1.png)

**步驟 9：**

按一下訊息中的問題單號碼，便可以看到問題單詳細資料。

![步驟 NE2](/images/Non-Equinix-Step2.png)
