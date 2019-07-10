---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-01"

keywords: use case, alternatives, deployments, diverse, redundant, default, multi-cloud, other clouds, schematic

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# IBM Cloud Direct Link デプロイメントの代替方法
{: #alternatives-for-your-ibm-cloud-direct-link-deployment}

この資料では、お客様が {{site.data.keyword.cloud}} Direct Link デプロイメントのユース・ケースとして選択するいくつかの代替方法について説明します。

## Exchange および Connect のための多様なデプロイメント
{: #diverse-deployments-for-exchange-and-connect}

Direct Link Connect および Direct Link Exchange のデフォルトのデプロイメントに冗長構成は含まれませんが、個別のルーターにさまざまにデプロイすることはできます。

お客様の多くは、追加の Direct Link 接続を設定することによる冗長デプロイメントの作成を選択されます。 この資料では、代替の IBM Cloud Direct Link デプロイメントをいくつか図示します。

![多様な Exchange](/images/Direct-Link-Exchange-Diverse.png)

**図 1 (上の図): 多様な IBM Cloud Direct Link Exchange デプロイメント**

また、次の図に示すように、IBM Cloud Direct Link を使用すると、多様な Connect デプロイメントを容易に確立できます。

![多様な Connect](/images/Direct-Link-Connect-Diverse.png)


**図 2 (上の図): 冗長および多様な IBM Cloud Direct Link Connect デプロイメント**

## 他のクラウドと連携した Exchange および Connect の使用
{: #using-exchange-and-connect-in-conjunction-with-other-clouds}

一部のお客様は、AWS、Azure、Google Cloud などの他のクラウド・プロバイダーと連携した Direct Link Exchange の使用を希望されます。 次の図は、Cloud Exchange プロバイダーとの間でこのタイプの接続を確立する方法の概要を示しています。

![他のクラウド](/images/Direct-Link-Exchange-Other-Clouds.png)

**図 3 (上の図): 他のクラウドと連携した IBM Cloud Direct Link Exchange の使用**

一部のお客様は、AWS、Azure、Google Cloud などの他のクラウド・プロバイダーと連携した Direct Link Connect の使用を希望されます。 次の図は、通信事業者/ネットワーク・サービス・プロバイダーとの間でこのタイプの接続を確立する方法の概要を示しています。

![他のクラウド](/images/Direct-Link-Connect-other-clouds.png)

**図 4 (上の図): 他のクラウドと連携した IBM Cloud Direct Link Connect の使用**

