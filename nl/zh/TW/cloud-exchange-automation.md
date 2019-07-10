---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-02"

keywords: provisioning, Exchange, order, support, ticket, diverse, virtual circuit, parameters, Terms and Conditions

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

# 佈建 IBM Cloud Direct Link Exchange
{: #provisioning-ibm-cloud-direct-link-exchange}

本頁面示範如何訂購 {{site.data.keyword.cloud}} Direct Link Exchange 服務。如果 {{site.data.keyword.cloud_notm}} Direct Link 訂單是針對 Equinix Cloud Exchange，則服務佈建會完全自動化，這表示您可以[訂購 IBM Cloud Direct Link 連線 (Equinix) 而不必開立 IBM 支援問題單](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix)，如相關文件中所述。

自動化功能目前僅限於 Equinix Cloud Exchange。在後續的版本中，將會為其他提供者啟用自動化。
{:note}

## 必要條件
{: #cloud-exchange-prerequisites}

若要使用自動化功能，您的專用 VLAN 必須與 {{site.data.keyword.cloud_notm}} 專用網路中的 VRF 相關聯。如果未符合此需求，當您透過客戶入口網站下訂單時，將會產生 IBM 支援問題單。

 * [如何訂購 Cloud Exchange](#how-to-order-cloud-exchange-no-equinix)
 * [如何訂購 Cloud Exchange for Equinix](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix)

## 如何訂購 Cloud Exchange
{: #how-to-order-cloud-exchange-no-equinix}

若要佈建 IBM Cloud Direct Link Exchange 連線，請完成下列步驟：

**步驟 1：**

在[客戶入口網站 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://cloud.ibm.com/) 上登入您的客戶帳戶。

**步驟 2：**

在**網路**標籤下，選取 **Direct Link -> Exchange**，這會開啟頁面顯示任何現有的 IBM Cloud Direct Link 連線。

![步驟 2](/images/pup_exchange_list.png)

**步驟 3：**

按一下頁面頂端的**訂購 Direct Link Exchange** 按鈕之後，您將會看到訂單表格，您可以在這裡輸入 IBM Cloud Direct Link Exchange 連線的配置參數。

![步驟 3](/images/pup_exchange_create_default.png)

**步驟 3A：**

如果可以存取多樣化埠，且您先前已佈建第一個「虛擬電路」，則會看到類似下列的畫面，其中顯示兩個埠，您可以選擇性地從中選取第二個「虛擬電路」。

![2-port-image](/images/pup_exchange_create_ports.png)

**步驟 4：**

在訂單表格中，輸入下列參數以配置 Direct Link：
  * 輸入 IBM Cloud Direct Link 連線名稱。
  * 從清單中，選取您要建立 IBM Cloud Direct Link 連線的位置。
  * 從清單中，選取您喜好的 Cloud Exchange 提供者名稱。
  * 選取連線所需的鏈結速度。
  * 選取連線所需的遞送選項。
  * 針對 BGP 交換，輸入來自資訊方框中所給定範圍的 ASN 號碼。

**步驟 5：**

當您選取或輸入這些值時，可以在右側的畫面看到約略的每月費用。

![步驟 4-5](/images/pup_exchange_create_prices.png)

**步驟 6.**

當您提供輸入時，會驗證表單欄位。您必須**同意**條款，才能啟用「建立」按鈕。

**步驟 7：**

同意條款之後，當您下訂單時，會在下訂單之後產生 IBM 支援問題單，以繼續服務佈建。在您下訂單之後，問題單號碼會顯示在使用者介面中。 

![步驟 NE1](/images/pup_exchange_ticket_notification.png)

**步驟 8：**

按一下訊息中的問題單號碼，便可以看到問題單詳細資料。

![步驟 NE2](/images/pup_exchange_ticket_details.png)
