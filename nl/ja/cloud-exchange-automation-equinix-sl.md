---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-06-12"

keywords: provisioning, order, Exchange, Equinix, automated, status, connection, legacy, customer, portal, Softlayer

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


# レガシー・カスタマー・ポータルを使用した Equinix 用の IBM Cloud Direct Link Exchange のプロビジョン
{: #provisioning-ibm-cloud-direct-link-exchange-for-equinix-legacy}

この資料では、IBM Cloud レガシー・カスタマー・ポータルを使用して Equinix 用の Direct Link Exchange をプロビジョンするための手順を段階的に説明します。
{: shortdesc}

Equinix Cloud Exchange 用に {{site.data.keyword.cloud}} Direct Link を注文する場合、サービス・プロビジョニングは完全に自動化されており、IBM サポート・チケットを開かずに {{site.data.keyword.cloud_notm}} Direct Link 接続 (Equinix) を注文できます。

自動化の機能は現在 Equinix Cloud Exchange に限定されています。 今後のリリースで、他のプロバイダーに対しての自動化も有効になる予定です。
{:note}

## 前提条件
{: #cloud-exchange-equinix-prerequisites-legacy}

自動注文機能を使用するには、プライベート VLAN が {{site.data.keyword.cloud_notm}} プライベート・ネットワークの VRF に関連付けられている必要があります。この要件が満たされていない場合、カスタマー・ポータルを使用して注文を行うと、IBM サポート・チケットが生成されます。

## 注文およびプロビジョニングのステップ
{: #cloud-exchange-steps-for-ordering-and-provisioning-legacy}

**ステップ 1:**

通常の [Cloud Exchange 注文ステップ](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-legacy)の 1 から 7 までのステップに従います。

**ステップ 2:**

注文を完了すると、IBM Cloud Direct Link のプロビジョニングが開始されます。

![ステップ 8](/images/Equinix-Step8.png)

**ステップ 3:**

注文後に接続の状況を確認できます。 IBM 側で構成が正常に完了すると、状況が**「プロビジョン済み」**と表示されます。 構成が完了していない場合は、状況が**「進行中」**と表示されます。 構成が失敗した場合は、状況が**「作成失敗」**と表示されます。 構成が正常に完了し、BGP 接続が確立されている場合は、状況が**「アップ」**と表示されます。

![ステップ 9、進行中](/images/Equinix-Step9-InProgress.png)

次の図は、注文が行われた後の接続のさまざまな状態を示しています。

![ステップ 9、アップ](/images/Equinix-Step9-UP.png)

**ステップ 4:**

接続が**「プロビジョン済み」**状況の場合は、接続の**「名前」**の前にある**「>」**をクリックして接続を展開します。 次に、**お客様の IP アドレス**と**サービス・キー**の情報を書き留めます。 この情報は、それぞれ、お客様のエッジ・ルーターの構成と、クラウド・プロバイダー側 (Equinix) の構成の許可キーとして必要になります。

![ステップ 10](/images/Equinix-Step10-Provisioned.png)

**ステップ 5:**

接続が**「プロビジョン済み」**状況で、接続の前にある**「>」**をクリックして接続を展開した時に、ピア・リンク速度との不一致があると、エラー・メッセージが表示されます。 IBM 側と Equinix 側で速度が同じになると、このエラー通知は表示されなくなります。

![ステップ 11](/images/Equinix-Step11-PortMismatch.png)

**ステップ 6:**

接続が**「作成失敗」**状況では、IBM サポート・チケットが生成され、サポート・チケットを通じて詳細が通知されます。 接続を展開すると、サポート・チケットの詳細が表示されます。

![ステップ 12](/images/Equinix-Step12-CreateFailed.png)

**ステップ 7:**

接続が**「プロビジョン済み」**、**「アップ」**、または**「ダウン」**の状況の場合、接続名の隣の**「アクション」**列をクリックして、接続を**「削除」**できます。

![ステップ 13](/images/Equinix-Step13-Delete.png)

**ステップ 8:**

接続が**「作成失敗」**状況の場合、接続名の隣の**「アクション」**列をクリックして、接続を**「キャンセル」**できます。
