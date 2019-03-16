---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-02-19"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Direct Link オファリングの概要
{ #overview-of-direct-link-offerings}

{{site.data.keyword.cloud}} Direct Link オファリングは、外部ソースからお客様の IBM Cloud プライベート・ネットワークへの接続を提供します。 Direct Link は、リモート・ネットワークと IBM Cloud 環境の間に、より一貫性のある、高スループットの接続を必要とするお客様向けに設計されており、従来のサイト間 VPN ソリューションの代替と見なすことができます。 以下の 4 つのタイプの接続を利用することができます。
 
 * **IBM Cloud Direct Link Exchange** を使用すると、お客様は Exchange プロバイダーを利用して IBM Cloud への接続を実現できます。 Exchange プロバイダーは、IBM Cloud ネットワークに既に接続されている、マルチテナントの大容量リンクを使用するキャリアまたはネットワーク・プロバイダーです。 お客様は通常、このプロバイダーでバーチャル・サーキットを購入できます。{{site.data.keyword.BluSoftlayer_notm}} から Exchange プロバイダーへの物理的な接続は既に設置済みであり、他のお客様と共有できるため、低コストで接続が提供されます。
 
 * **IBM Cloud Direct Link Connect** を使用すると、お客様は、設備ベースのネットワークを所有して運用するパートナーを通じて接続を利用できます。 IBM Cloud Direct Link Connect を使用すると、IBM とパートナーが、レイヤー 2 およびレイヤー 3 で、レイヤー 2 の10 G デュアル NNI を介してお客様に接続します。
 
 * **IBM Cloud Direct Link Dedicated** を使用すると、お客様は、専用の単一モード・ファイバー相互接続を、独自の IBM Cloud プライベート・ネットワークに終端させることができます。
 
 * **IBM Cloud Direct Link Dedicated Hosting** は、IBM Cloud Direct Link Dedicated と同様の接続を提供しますが、接続ポイントが {{site.data.keyword.BluSoftlayer_notm}} データ・センターに隣接しているため、ハイパフォーマンスのユース・ケースの場合の待ち時間が改善されます。 IBM Cloud では、このソリューションを使用したカスタマイズ可能な各種のコロケーション・サービスを提供しています。
  
IBM Cloud  Direct Link サービスは、経路指定された OSI レイヤー 3 サービスです。 これは、{{site.data.keyword.BluSoftlayer_notm}} プライベート・ネットワーク・バックボーンへの直接接続を提供し、少ない待ち時間と 10 Gbps までの速度を実現します。
このレイヤー 3 接続を作成する際の柔軟性を高めるために、IBM Cloud Direct Link では、お客様は以下を利用できます。
 * リモート・ホストのデュアル IP
 * NAT
 * BYOIP のトンネリング
 
 各オファリングの詳細な説明については、[IBM Cloud Direct Link について](/docs/infrastructure/direct-link?topic=direct-link-about-ibm-cloud-direct-link)を参照してください。
