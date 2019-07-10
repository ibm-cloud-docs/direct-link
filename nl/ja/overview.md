---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-02"

keywords: overview, connectivity, private network, site-to-site, Exchange, Connect, Dedicated, Hosting, OSI, Layer-3, partners, NNI, latency, backbone

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Direct Link オファリングの概要
{: #overview-of-direct-link-offerings}

{{site.data.keyword.cloud}} Direct Link オファリングは、外部ソースからお客様の IBM Cloud プライベート・ネットワークへの接続を提供します。 Direct Link は、リモート・ネットワークと IBM Cloud 環境の間に、より一貫性のある、高スループットの接続を必要とするお客様向けに設計されており、従来のサイト間 VPN ソリューションの代替と見なすことができます。 以下の 4 つのタイプの接続を利用することができます。
 
 * **IBM Cloud Direct Link Exchange** を使用すると、お客様は Exchange プロバイダーを利用して IBM Cloud への接続を実現できます。Exchange プロバイダーは、{{site.data.keyword.cloud_notm}} ネットワークに既に接続されている、マルチテナントの大容量リンク (別名: _ネットワーク間インターフェース_つまり NNI) を使用するコロケーションまたはデータ・センターのプロバイダーです。お客様は通常、このプロバイダーでバーチャル・サーキットを購入できます。{{site.data.keyword.cloud_notm}} から Exchange プロバイダーへの物理的な接続は既に設置済みであり、他のお客様と共有できるため、低コストで接続が提供されます。
 
 * **IBM Cloud Direct Link Connect** を使用すると、お客様は、ファシリティー・ベースのネットワークを所有して運用するキャリア・パートナーを介して接続を利用できます。Connect プロバイダーは、{{site.data.keyword.cloud_notm}} ネットワークに既に接続されている、マルチテナントの大容量リンク (別名: _ネットワーク間インターフェース_つまり NNI) を使用するネットワーク・サービス・プロバイダー (NSP) です。お客様は通常、このプロバイダーでバーチャル・サーキットを購入できます。{{site.data.keyword.cloud_notm}} から Connect プロバイダーへの物理的な接続が既に設置済みで、他のお客様と共有されるので、低コストで接続が提供されます。
 
 * **IBM Cloud Direct Link Dedicated** を使用すると、お客様はシングル・テナントのファイバー・ベースの相互接続を {{site.data.keyword.cloud_notm}} ネットワークの中に終端させることができます。IBM Cloud PoP およびデータ・センターに隣接するコロケーション・プレミスを持つお客様、さらにオンプレミスまたは他のデータ・センターへの回線を提供するネットワーク・サービス・プロバイダーが、このオファリングを利用できます。
 
 * **IBM Cloud Direct Link Dedicated Hosting** は、{{site.data.keyword.cloud_notm}} Direct Link Dedicated と同様の接続を提供しますが、接続ポイントが {{site.data.keyword.cloud_notm}} データ・センターに隣接しているため、ハイパフォーマンスのユース・ケースの場合の待ち時間が改善されます。{{site.data.keyword.cloud_notm}} には、このソリューションを使用したカスタマイズ可能な各種のコロケーション・サービスが備わっています。
  
{{site.data.keyword.cloud_notm}} Direct Link サービスは、経路指定された OSI レイヤー 3 サービスです。これは、{{site.data.keyword.cloud_notm}} プライベート・ネットワーク・バックボーンへの直接接続を提供し、少ない待ち時間と 10 Gbps までの速度を実現します。
このレイヤー 3 接続を作成する際の柔軟性を高めるために、お客様は {{site.data.keyword.cloud_notm}} Direct Link で以下を利用できます。
 * リモート・ホストのデュアル IP
 * NAT
 * BYOIP のトンネリング
 
 各オファリングの詳細な説明については、[IBM Cloud Direct Link について](/docs/infrastructure/direct-link?topic=direct-link-about-ibm-cloud-direct-link)を参照してください。
