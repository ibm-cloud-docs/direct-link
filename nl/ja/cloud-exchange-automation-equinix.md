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


# Equinix 用の IBM Cloud Direct Link Exchange のプロビジョニング
{: #provisioning-ibm-cloud-direct-link-exchange-for-equinix}

Equinix Cloud Exchange 用に {{site.data.keyword.cloud}} Direct Link を注文する場合、サービス・プロビジョニングは完全に自動化されており、IBM サポート・チケットを開かずに {{site.data.keyword.cloud_notm}} Direct Link 接続 (Equinix) を注文できます。

自動化の機能は現在 Equinix Cloud Exchange に限定されています。 今後のリリースで、他のプロバイダーに対しての自動化も有効になる予定です。
{:note}

## 前提条件
{: #cloud-exchange-equinix-prerequisites}

自動注文機能を使用するには、プライベート VLAN が {{site.data.keyword.cloud_notm}} プライベート・ネットワークの VRF に関連付けられている必要があります。この要件が満たされていない場合、カスタマー・ポータルを使用して注文を行うと、IBM サポート・チケットが生成されます。

## 注文およびプロビジョニングのステップ
{: #cloud-exchange-steps-for-ordering-and-provisioning}

**ステップ 1:**

通常の [Cloud Exchange 注文ステップ](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange)の 1 から 7 までのステップに従います。

**ステップ 2:**

注文を完了すると、IBM Cloud Direct Link のプロビジョニングが開始されます。

注文後に接続の状況を確認できます。 IBM 側で構成が正常に完了すると、状況が**「プロビジョン済み」**と表示されます。 構成が完了していない場合は、状況が**「進行中」**と表示されます。 構成が失敗した場合は、状況が**「作成失敗」**と表示されます。 構成が正常に完了し、BGP 接続が確立されている場合は、状況が**「アップ」**と表示されます。

![ステップ 9、進行中](/images/pup_exchange_equinix_inProgress.png)

**ステップ 3:**

接続が**「プロビジョン済み」**状態である場合、**<connection_name>** リンクをクリックして接続名をクリックします。詳細ページが表示されます。

![ステップ 10](/images/pup_exchange_equinix_provisioned.png)

次の図は、注文が行われた後の接続のさまざまな状態を示しています。

![ステップ 9、アップ](/images/pup_exchange_equinix_up.png)

**ステップ 4:**

**お客様の IP アドレス**と**サービス・キー**の情報を書き留めます。この情報は、それぞれ、お客様のエッジ・ルーターの構成と、クラウド・プロバイダー側 (Equinix) の構成の許可キーとして必要になります。

![ステップ 9、アップ](/images/pup_exchange_equinix_provisioned_details.png)

**ステップ 5:**

**「プロビジョン済み」**状態の接続の場合、**<connection_name>**をクリックして接続名をクリックすると、ピア・リンク速度との不一致があるときにはエラー・メッセージが表示されます。IBM 側と Equinix 側で速度が同じになると、このエラー通知は表示されなくなります。

![ステップ 11](/images/pup_exchange_equinix_provisioned_details_portSpeedMismatch.png)

**ステップ 6:**

接続が**「作成失敗」**状況では、IBM サポート・チケットが生成され、サポート・チケットを通じて詳細が通知されます。 接続を展開すると、サポート・チケットの詳細が表示されます。

![ステップ 12](/images/pup_exchange_equinix_list_createFailed.png)

**ステップ 7:**

接続が**「プロビジョン済み」**、**「アップ」**、または**「ダウン」**状態である場合、接続名の隣の**「アクション」**列のオーバーフローをクリックして、接続を**「削除」**できます。

![ステップ 13](/images/pup_exchange_equinix_list_delete.png)

**ステップ 8:**

接続が**「作成失敗」**状況の場合、接続名の隣の**「アクション」**列をクリックして、接続を**「キャンセル」**できます。

![ステップ 14](/images/pup_exchange_equinix_list_delete.png)
