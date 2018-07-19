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

# ステップバイステップ: IBM Cloud Direct Link Exchange の注文

このページでは、IBM Cloud Direct Link Exchange サービスの注文方法を説明します。 Equinix Cloud Exchange 用に IBM Cloud Direct Link を注文する場合、サービス・プロビジョニングは完全に自動化されており、IBM サポート・チケットを開かずに IBM Cloud Direct Link 接続 (Equinix) を注文できます。

**(注: 自動化の機能は現在 Equinix Cloud Exchange に限定されています。 今後のリリースで、他のプロバイダーに対しての自動化も有効になる予定です。)。**

## 前提条件

自動化機能を使用するには、プライベート VLAN が IBM クラウド・プライベート・ネットワークの VRF に関連付けられている必要があります。 この要件が満たされていない場合、カスタマー・ポータルを使用して注文を行うと、IBM サポート・チケットが生成されます。

 * [Cloud Exchange の注文方法](#how-to-order-cloud-exchange)
 * [Equinix 用の Cloud Exchange の注文方法](#how-to-order-cloud-exchange-for-equinix)

## Cloud Exchange の注文方法

IBM Cloud Direct Link Exchange 接続をプロビジョンするには、以下のステップを実行します。

**ステップ 1:**

[カスタマー・ポータル ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://control.softlayer.com/)でお客様のアカウントにログインします。

**ステップ 2:**

**「ネットワーク」**タブで、**「Direct Link」 -> 「Exchange」**を選択して、既存の IBM Cloud Direct Link 接続を示すページを開きます (存在する場合)。

![ステップ 2](/images/Equinix-Step2.png)

**ステップ 3:**

ページ上部の**「Direct Link Exchange の注文 (Order Direct Link Exchange」**ボタンをクリックすると注文フォームが表示され、このフォームに IBM Cloud Direct Link Exchange 接続の構成パラメーターを入力できます。

![ステップ 3](/images/Equinix-Step3.png)

**ステップ 3A:**

オプションとして、Diverse ポートにアクセス可能であり、最初のバーチャル・サーキットを既にプロビジョンしている場合、以下のような画面が表示され、2 つのポートが示されます。そのポートから 2 つ目のバーチャル・サーキットを選択できます。

![2 つのポートのイメージ](/images/exchange-2-ports-image.png)

**ステップ 4:**

注文フォームに以下のパラメーターを入力して Direct Link を構成します。
  * IBM Cloud Direct Link 接続名を入力します。
  * リストから、IBM Cloud Direct Link 接続を確立する PoP の場所を選択します。
  * リストから、希望する Cloud Exchange プロバイダーの名前を選択します。
  * 接続に必要な「リンク速度 (Link Speed)」を選択します。
  * 接続に必要なルーティング・オプションを選択します。
  * BGP 交換の情報ボックスに示された範囲から ASN 番号を入力します。

**ステップ 5:**

これらの値を選択または入力すると、左側のパネルにおおよその月額料金が表示されます。

![ステップ 4-5](/images/Equinix-Step4-5.png)

**ステップ 6:**

入力値を指定すると、次の UI 画面に、選択したオプションに基づいて実際の月額料金が表示されます。

**ステップ 7:**

IBM Cloud Direct Link の注文を行う前に、「使用条件」に**同意**する必要があります。 「使用条件」には注文の前に理解しなければならない重要な技術情報が含まれているため、注意深くお読みください。 **(注: 使用条件に同意されない場合は、注文時に IBM サポート・チケットが生成されます。)** 次の図は、このステップで選択した内容に基づいて、表示される可能性のある画面を示しています。

次の図は「使用条件」画面を示しています。

![ステップ 7](images/Equinix-Step7.png)

次の図は、「使用条件」に同意しない場合に注文時に表示される画面を示しています。 画面には、生成されたチケット番号が表示されています。

![ステップ 7、同意](/images/Equinix-Step7-NoAgree.png)

次の図は、開かれているチケットの例を示しています。

![ステップ 7、チケット](/images/Equinix-Step7-NoAgree-Ticket.png)

**ステップ 8:**

使用条件に同意した後、注文を行うと、続けてサービスのプロビジョニングを行うための IBM サポート・チケットが生成されます。 注文を行うと、チケット番号が UI に表示されます。 

![ステップ NE1](/images/Non-Equinix-Step1.png)

**ステップ 9:**

メッセージの中のチケット番号をクリックすると、チケットの詳細が表示されます。

![ステップ NE2](/images/Non-Equinix-Step2.png)

## Equinix 用の Cloud Exchange の注文方法

**ステップ 1:**

上記の Cloud Exchange の注文のステップ 1 から 7 に従います。

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

