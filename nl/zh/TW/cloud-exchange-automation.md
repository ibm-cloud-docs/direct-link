---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-11"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# 逐步：訂購 IBM Cloud Direct Link Exchange

本頁面示範如何訂購 IBM Cloud Direct Link Exchange 服務。如果 IBM Cloud Direct Link 訂單是針對 Equinix Cloud Exchange，服務佈建會完全自動化，這表示您可以訂購 IBM Cloud Direct Link 連線 (Equinix) 而不必開立 IBM 支援問題單。

**（附註：自動化功能目前僅限於 Equinix Cloud Exchange。在後續的版本中，將會為其他提供者啟用自動化。）**

## 必要條件

若要使用自動化功能，您的專用 VLAN 必須與 IBM Cloud 專用網路中的 VRF 相關聯。如果未符合此需求，當您透過客戶入口網站下訂單時，將會產生 IBM 支援問題單。

 * [如何訂購 Cloud Exchange](#how-to-order-cloud-exchange)
 * [如何訂購 Cloud Exchange for Equinix](#how-to-order-cloud-exchange-for-equinix)

## 如何訂購 Cloud Exchange

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

您必須**同意**條款，然後才能訂購 IBM Cloud Direct Link。請仔細閱讀條款，因為它們包含您在繼續之前必須瞭解的重要技術資訊。**（附註：如果未接受條款，下訂單時將會產生 IBM 支援問題單。）**接下來的圖顯示您可能會看到的畫面，視您在這個步驟選取的內容而定。

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

## 如何訂購 Cloud Exchange for Equinix

**步驟 1：**

遵循上述 Cloud Exchange 訂購步驟的步驟 1 到 7

**步驟 2：**

下訂單之後，IBM Cloud Direct Link 佈建便會開始。

![步驟 8](/images/Equinix-Step8.png)

**步驟 3：**

下訂單之後，您可以看到連線的狀態。如果 IBM 端的配置順利完成，您會看到狀態是**已佈建**。如果未完成配置，您會看到狀態是**進行中**。如果配置失敗，您會看到狀態是**建立失敗**。如果配置已順利完成，且 BGP 連線已啟動，您會看到狀態是**啟動**。

![步驟 9 進行中](/images/Equinix-Step9-InProgress.png)

下圖顯示下訂單之後，連線的各種狀態。

![步驟 9 啟動](/images/Equinix-Step9-UP.png)

**步驟 4：**

如果連線為**已佈建**狀態，請按一下連線**名稱**前面的 **>** 來展開連線。然後記下**客戶 IP 位址**及**服務金鑰**資訊。訂購客戶邊緣路由器時，以及作為雲端提供者端 (Equinix) 配置的授權金鑰時，將會分別需要這些。

![步驟 10](/images/Equinix-Step10-Provisioned.png)

**步驟 5：**

對於**已佈建**狀態的連線，按一下連線前面的 **>** 來展開連線之後，如果與對等節點鏈結速度不符，您將會看到錯誤訊息。IBM 端和 Equinix 端的速度相同之後，便不會再顯示此錯誤通知。

![步驟 11](/images/Equinix-Step11-PortMismatch.png)

**步驟 6：**

對於**建立失敗**狀態的連線，會產生 IBM 支援問題單，並且會透過支援問題單來溝通進一步的詳細資料。當您展開連線時，可以看到支援問題單詳細資料。

![步驟 12](/images/Equinix-Step12-CreateFailed.png)

**步驟 7：**

對於**已佈建**、**啟動**或**關閉**狀態的連線，您可以按一下連線旁邊的**動作**直欄來**刪除**連線。

![步驟 13](/images/Equinix-Step13-Delete.png)

**步驟 8：**

對於**建立失敗**狀態的連線，您可以按一下連線旁邊的**動作**直欄來**取消**連線。

