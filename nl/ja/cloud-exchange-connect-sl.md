---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-06-12"

keywords: provision, Connect, console, order, support, ticket, legacy, customer, portal

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


# IBM Cloud レガシー・カスタマー・ポータルからの IBM Cloud Direct Link Connect のプロビジョン
{: #provision-ibm-cloud-direct-link-connect-legacy}

このページでは、{{site.data.keyword.cloud_notm}} レガシー・カスタマー・ポータルから {{site.data.keyword.cloud}} Direct Link Connect サービスを注文する方法について説明します。
{: shortdesc}

注文を行った後、IBM サポート・チケットが生成されます。
{:note}

## Direct Link Connect を注文するためのステップ
{: #steps-to-order-direct-link-connect-legacy}

{{site.data.keyword.cloud_notm}} Direct Link Connect の注文をプロビジョンするには、以下のステップをすべて行います。

**ステップ 1:**

[カスタマー・ポータル ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://control.softlayer.com/)でお客様のアカウントにログインします。
  
**ステップ 2:**

**「ネットワーク」**タブで、**「Direct Link」 -> 「Connect」**を選択すると、既存の {{site.data.keyword.cloud_notm}} Direct Link 接続を示すページが開きます (存在する場合)。

![ステップ 2](images/Step2-Connect-Offering-Tab.png)
![ステップ 2a](images/Step2-Connect-List-Page.png)

**ステップ 3:**

ページ上部の**「Direct Link Connect の注文 (Order Direct Link Connect)」**ボタンをクリックすると注文フォームが表示され、このフォームに IBM Cloud Direct Link Connect の注文の構成パラメーターを入力できます。

![ステップ 3](images/Step3-Connect-Order-Page.png)

**ステップ 4:**

注文フォームに以下のパラメーターを入力して Direct Link を構成します。

  - IBM Cloud Direct Link 接続名を入力します。
  - リストから、{{site.data.keyword.cloud_notm}} Direct Link 接続を確立する PoP の場所を選択します。
  - リストから、希望する Cloud Exchange プロバイダーの名前を選択します。
  - 接続に必要な「リンク速度 (Link Speed)」を選択します。
  - 接続に必要なルーティング・オプションを選択します。
  - BGP 交換の情報ボックスに示された範囲から ASN 番号を入力します。
  - 接続の VRF を選択します。

**ステップ 5:**

これらの値を選択または入力すると、左側のパネルにおおよその月額料金が表示されます。

![ステップ 5](images/Step5-Connect-Link-Speeds.png)

**ステップ 6:**

入力値を指定すると、次の UI 画面に、選択したオプションに基づいて実際の月額料金が表示されます。

**ステップ 7:**

IBM Cloud Direct Link の注文を行う前に、「使用条件」に同意する必要があります。 _「使用条件」_には注文の前に理解しなければならない重要な技術情報が含まれているため、注意深くお読みください。 次の図は、注文を行った後に表示される画面を示しています。

次の図は「使用条件」画面を示しています。

![ステップ 7](images/Step7-Connect-Summary-Page.png)

次の図は、注文を行った後に表示される画面を示しています。 画面には、生成されたチケット番号が表示されています。

![ステップ 7a](images/Step7-Connect-Ticket-Generated.png)

次の図は、開かれているチケットの例を示しています。

![ステップ 7b](images/Step7-Connect-Ticket-Details.png)
