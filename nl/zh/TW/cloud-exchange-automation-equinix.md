---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-02"

keywords: provisioning, order, Exchange, Equinix, automated, status, connection

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


# 佈建 IBM Cloud Direct Link Exchange for Equinix
{: #provisioning-ibm-cloud-direct-link-exchange-for-equinix}

如果 {{site.data.keyword.cloud}} Direct Link 訂單是針對 Equinix Cloud Exchange，則服務佈建會完全自動化，這表示您可以訂購 {{site.data.keyword.cloud_notm}} Direct Link 連線 (Equinix) 而不必開立 IBM 支援問題單。

自動化功能目前僅限於 Equinix Cloud Exchange。在後續的版本中，將會為其他提供者啟用自動化。
{:note}

## 必要條件
{: #cloud-exchange-equinix-prerequisites}

若要使用自動化訂購功能，您的專用 VLAN 必須與 {{site.data.keyword.cloud_notm}} 專用網路中的 VRF 相關聯。如果未符合此需求，當您透過客戶入口網站下訂單時，將會產生 IBM 支援問題單。

## 訂購及佈建步驟
{: #cloud-exchange-steps-for-ordering-and-provisioning}

**步驟 1：**

遵循一般 [Cloud Exchange 訂購步驟](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange)的步驟 1 到 7。

**步驟 2：**

下訂單之後，IBM Cloud Direct Link 佈建便會開始。

下訂單之後，您可以看到連線的狀態。如果 IBM 端的配置順利完成，您會看到狀態是**已佈建**。如果未完成配置，您會看到狀態是**進行中**。如果配置失敗，您會看到狀態是**建立失敗**。如果配置已順利完成，且 BGP 連線已啟動，您會看到狀態是**啟動**。

![步驟 9 進行中](/images/pup_exchange_equinix_inProgress.png)

**步驟 3：**

如果連線處於**已佈建**狀態，請藉由按一下 **<connection_name>** 鏈結來按一下連線名稱。這應該會導覽至詳細資料頁面。

![步驟 10](/images/pup_exchange_equinix_provisioned.png)

下圖顯示下訂單之後，連線的各種狀態。

![步驟 9 啟動](/images/pup_exchange_equinix_up.png)

**步驟 4：**

請記下**客戶 IP 位址**及**服務金鑰**資訊。訂購客戶邊緣路由器時，以及作為雲端提供者端 (Equinix) 配置的授權金鑰時，將會分別需要這些。

![步驟 9 啟動](/images/pup_exchange_equinix_provisioned_details.png)

**步驟 5：**

對於處於**已佈建**狀態的連線，藉由按一下 **<connection_name>** 來按一下連線名稱之後，如果與「對等節點鏈結速度」不符，您會看到一則錯誤訊息。IBM 端和 Equinix 端的速度相同之後，便不會再顯示此錯誤通知。

![步驟 11](/images/pup_exchange_equinix_provisioned_details_portSpeedMismatch.png)

**步驟 6：**

對於**建立失敗**狀態的連線，會產生 IBM 支援問題單，並且會透過支援問題單來溝通進一步的詳細資料。當您展開連線時，可以看到支援問題單詳細資料。

![步驟 12](/images/pup_exchange_equinix_list_createFailed.png)

**步驟 7：**

對於處於**已佈建**、**啟動**或**關閉**狀態的連線，您可以按一下連線旁邊的**動作**直欄中的溢位來**刪除**連線。

![步驟 13](/images/pup_exchange_equinix_list_delete.png)

**步驟 8：**

對於**建立失敗**狀態的連線，您可以按一下連線旁邊的**動作**直欄來**取消**連線。

![步驟 14](/images/pup_exchange_equinix_list_delete.png)
