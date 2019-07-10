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

# IBM Cloud Direct Link Exchange のプロビジョニング
{: #provisioning-ibm-cloud-direct-link-exchange}

このページでは、{{site.data.keyword.cloud}} Direct Link Exchange サービスの注文方法を説明します。 Equinix Cloud Exchange 用に {{site.data.keyword.cloud_notm}} Direct Link を注文する場合、サービス・プロビジョニングは完全に自動化されており、関連する資料で取り上げられているように、[IBM サポート・チケットを開かずに IBM Cloud Direct Link 接続 (Equinix) を注文できます](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix)。

自動化の機能は現在 Equinix Cloud Exchange に限定されています。 今後のリリースで、他のプロバイダーに対しての自動化も有効になる予定です。
{:note}

## 前提条件
{: #cloud-exchange-prerequisites}

自動化機能を使用するには、プライベート VLAN が {{site.data.keyword.cloud_notm}} プライベート・ネットワークの VRF に関連付けられている必要があります。この要件が満たされていない場合、カスタマー・ポータルを使用して注文を行うと、IBM サポート・チケットが生成されます。

 * [Cloud Exchange の注文方法](#how-to-order-cloud-exchange-no-equinix)
 * [Equinix 用の Cloud Exchange の注文方法](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix)

## Cloud Exchange の注文方法
{: #how-to-order-cloud-exchange-no-equinix}

IBM Cloud Direct Link Exchange 接続をプロビジョンするには、以下のステップを実行します。

**ステップ 1:**

[カスタマー・ポータル ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://cloud.ibm.com/)でお客様のアカウントにログインします。

**ステップ 2:**

**「ネットワーク」**タブで、**「Direct Link」 -> 「Exchange」**を選択して、既存の IBM Cloud Direct Link 接続を示すページを開きます (存在する場合)。

![ステップ 2](/images/pup_exchange_list.png)

**ステップ 3:**

ページ上部の**「Direct Link Exchange の注文 (Order Direct Link Exchange」**ボタンをクリックすると注文フォームが表示され、このフォームに IBM Cloud Direct Link Exchange 接続の構成パラメーターを入力できます。

![ステップ 3](/images/pup_exchange_create_default.png)

**ステップ 3A:**

オプションとして、Diverse ポートにアクセス可能であり、最初のバーチャル・サーキットを既にプロビジョンしている場合、以下のような画面が表示され、2 つのポートが示されます。そのポートから 2 つ目のバーチャル・サーキットを選択できます。

![2 つのポートのイメージ](/images/pup_exchange_create_ports.png)

**ステップ 4:**

注文フォームに以下のパラメーターを入力して Direct Link を構成します。
  * IBM Cloud Direct Link 接続名を入力します。
  * リストから、IBM Cloud Direct Link 接続を確立する場所を選択します。
  * リストから、希望する Cloud Exchange プロバイダーの名前を選択します。
  * 接続に必要な「リンク速度 (Link Speed)」を選択します。
  * 接続に必要なルーティング・オプションを選択します。
  * BGP 交換の情報ボックスに示された範囲から ASN 番号を入力します。

**ステップ 5:**

これらの値を選択または入力すると、右側のパネルにおおよその月額料金が表示されます。

![ステップ 4-5](/images/pup_exchange_create_prices.png)

**ステップ 6:**

入力すると、フォーム・フィールドが検証されます。
「作成」ボタンを有効にするには、ご利用条件に**同意**する必要があります。

**ステップ 7:**

使用条件に同意した後、注文を行うと、続けてサービスのプロビジョニングを行うための IBM サポート・チケットが生成されます。 注文を行うと、チケット番号が UI に表示されます。 

![ステップ NE1](/images/pup_exchange_ticket_notification.png)

**ステップ 8:**

メッセージの中のチケット番号をクリックすると、チケットの詳細が表示されます。

![ステップ NE2](/images/pup_exchange_ticket_details.png)
