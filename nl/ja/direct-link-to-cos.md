---

copyright:
  years: 2017, 2018
lastupdated: "2018-10-30"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# IBM Cloud Direct Link を使用した IBM Cloud オブジェクト・ストレージへの接続

この資料では、IBM Cloud Direct Link を構成して、IBM Cloud オブジェクト・ストレージ (COS) にアクセスできるようにする方法について説明します。 ここで説明されている方法は COS で設計およびテストされていますが、他の特定の IBM Cloud サービスでも機能する可能性があります。

現在のポリシーでは、IBM Cloud Direct Link は、IBM Cloud オブジェクト・ストレージ (COS) が使用するものを含む、IBM Cloud プライベート・サービス・エンドポイントへのアクセスを拒否します。 この資料で説明する技法では、お客様の IBM Cloud アカウントでホストされているサーバーを介して、COS への間接アクセスを利用します。 セットアップ後、お客様の各サーバーは、Direct Link によって接続された IBM Cloud プライベート・サービス・エンドポイントとリモート・ネットワークとの間で双方向にトラフィックを転送できます。

## IBM Cloud オブジェクト・ストレージ (COS) とは

IBM Cloud オブジェクト・ストレージ (COS) は、非構造化データを保管する Web スケール・プラットフォームです。 手動による複製なしで、信頼性、セキュリティー、可用性、および災害復旧が提供されます。

IBM Cloud オブジェクト・ストレージに保管された情報は暗号化され、複数の地理的位置に分散されます。 これは、S3 API の実装を介してアクセス可能です。 このサービスは、IBM Cloud オブジェクト・ストレージ・サービスによって提供されている分散ストレージ・テクノロジーを利用します。

IBM COS は、**クロス地域**、**地域**、および**単一サイト**という 3 つの構成で利用可能です。

 * クロス地域サービスでは、単一地域を使用した場合よりも高い耐久性および可用性が得られますが、待ち時間が若干長くなるという代償を伴います。 現在、このサービスは、米国および EU で使用可能です。(Virtual Router Appliance (VRA) を使用することにより、アジア太平洋地域の COS に接続するために Direct Link も使用できることに注意してください。)
 
 * 地域サービスは、その逆となります。つまり、単一地域内の複数のアベイラビリティー・ゾーンにオブジェクトを分散します。 特定の地域またはアベイラビリティー・ゾーンがアクセス不能な場合でも、オブジェクト・ストアは引き続きスムーズに機能します。 適用されていない変更は、アクセス不能なデータ・センターがオンラインに戻ったときに適用されます。
  
 * 単一サイト・サービスは、選択されたデータ・センター内のクラウド・オブジェクト・ストレージへの手頃な料金でのアクセスを提供します。

### COS のプライベート・エンドポイントおよびパブリック・エンドポイント
エンドポイントは、アプリケーションが COS コマンドを発行し、COS とデータを交換するために使用する URL です。 各エンドポイントは、同じアプリケーション・プログラミング・インターフェース (API) を使用して COS と対話します。

IBM Cloud 内でプロビジョンされたサーバーは、COS を含むサービスのプライベート API エンドポイントを使用します。 プライベート・エンドポイントにより、帯域幅コストを追加することなく、お客様の IBM Cloud サーバーでサービスへの直接高速接続が提供されます。

COS パブリック・エンドポイントは、IBM Cloud のお客様に IBM Cloud 内からアクセスできるのと同じ COS データへのアクセスを提供しますが、パブリック・エンドポイントは、インターネットが利用できる任意の場所からのアクセスを許可します。

以下の 2 つの注意点が COS パブリック・エンドポイントに適用されます。
 * パブリック・エンドポイントを使用した場合、COS サービスによって課される使用料金以外に、帯域幅に対して課金される可能性があります。 
 * 転送中のデータはすべて暗号化されますが、お客様には、インターネットを介して送信されるデータに関連してプライバシーの懸念や規制による制限が生じることがあります。

## IBM Cloud Direct Link とは
IBM Cloud Direct Link は、お客様がリモート・ネットワーク環境と IBM Cloud デプロイメントの間のセキュアなプライベート接続を作成できるようにする製品スイートです。 Direct Link によって交換されるデータは、インターネットに公開されることはありません。

## IBM Cloud Direct Link を介したクラウド・オブジェクト・ストレージ (COS) の使用
IBM エンジニアは、COS および Direct Link を購入した IBM Cloud のお客様が COS プライベート・エンドポイントにリモート接続できるようにする方法を開発してきました。 このタイプの接続は、プライベート・サービス・エンドポイントの利点を拡張するものであり、IBM Cloud 施設外のクライアント・システムで使用できます。
 
後続のセクションでは、このソリューションについて図示および説明します。

### リバース・プロキシー

**基本的な前提: リモート・クライアントは、プライベート・サーバーを介して、要求 (セキュアな資格情報を含む) を COS に渡します。**

![リバース・プロキシー](images/reverse-proxy.png)

HTTPS (セキュア HTTP) COS 要求は、リモート・サイトのクライアントから開始されます。 要求は IBM Cloud Direct Link を介してセキュアに送信され、お客様の IBM Cloud アカウントにデプロイされた_リバース・プロキシー・サーバー_ のクラスターのいずれかを宛先とします。 そこから、要求は COS プライベート・エンドポイントに渡され、処理されてから、結果が呼び出し元のリモート・クライアントに返されます。

COS で機能するサンプル・クライアント・コードはすべて、_リバース・プロキシー_・サーバーでも機能します。 唯一必要な調整として、IBM によって公開されている COS プライベート・エンドポイント URL のいずれかを宛先にするのではなく、リバース・プロキシー・サーバーの IP アドレスまたは URL をクライアントの宛先にしてください。

#### Nginx リバース・プロキシーのインストール
**NginX** は、前述の_リバース・プロキシー_・サーバーの役割を含む、特化したタスクに優れた、成熟したコンパクトな高速オープン・ソース Web サーバーです。

後続の説明および構成情報 (NginX リバース・プロキシー・サーバーをセットアップするためのもの) は、環境に適合させた後に機能します。 行き詰まった場合や追加情報が必要な場合は、[Nginx 資料](https://docs.nginx.com/nginx/admin-guide/web-server/reverse-proxy/)のリバース・プロキシーの部分を参照するか、[スタック・オーバーフロー](http://stackoverflow.com)で例を検索してください。

1. 最小限の **RHEL** または **CentOS** Linux ビルド (推奨) で、VSI またはベアメタル・サーバーをプロビジョンします。
2. VSI ごとに、パブリック・インターフェースに関するセキュリティー・グループ・ルール `allow_http`、`allow_https`、`allow_outbound`、`allow_ssh` を有効にします。
3. VSI ごとに、プライベート・インターフェースに関する `allow_all` および `allow_outbound` ルールを有効にします。**「保存 (Save)」**を選択します。
4. Windows の **PuTTY** またはご使用のデスクトップの端末プログラムを使用して、`ssh` で新規サーバーに root として接続します。
5. オペレーティング・システム OS をアップグレードします (`yum update`)。
6. EPEL リポジトリーをインストールします (`yum install epel-release`)。
7. NginX をインストールします (`yum install nginx`)。
8. NginX を開始し (`nginx`)、サーバーの IP アドレスをブラウザーで開きます。
9. `nginx.conf` のデフォルトの場所は `/etc/nginx` です。 安全なコピーを作成します。
10. 下記のサンプル `nginx.conf` 構成ファイルを `/etc/nginx` に移動します。
11. IBM Cloud ポータルで SSL 証明書を購入するか、コマンド `yum install easy-rsa` を実行し、自己署名証明書の作成に関するヒントについて任意のオンライン資料を参照します。
12. 証明書情報を構成ファイル `nginx.conf` に追加します。
13. コマンド `nginx -t` を使用して、変更した NginX 構成をテストします。
14. テストに合格した場合は、コマンド `nginx -s quit; sleep 3; nginx` を使用して `nginx` を再始動します。
15. これで、クライアントは NginX (プロキシー) サーバーの IP または URL に COS 要求を送信できるようになっています。

#### 注:

* このソリューションでは、Direct Link が購入済みで適切にデプロイされていることを前提としています。ただし、Direct Link がなくても、テスト可能です。
* `proxy_cache` を使用して、オプションのメモリーまたはディスク・キャッシュを使用できます。
* 大規模なファイルの転送の場合、`proxy_read_timeout` 値を大きくする必要が生じることがあります。
* 高可用性 (自動フェイルオーバー) には、`keepalive` または Pacemaker を使用してください。

#### 構成ファイル: `nginx.conf`

以下のセクションでは、サンプル構成ファイルを示します。 コピー・アンド・ペーストできます。

```
user nginx;
worker_processes auto;
error_log /var/log/nginx/error.log;
pid /run/nginx.pid;

events {
    worker_connections 1024;
}

http {
    log_format  main  '$remote_addr - $remote_user [$time_local] "$request" '
                      '$status $body_bytes_sent "$http_referer" '
                      '"$http_user_agent" "$http_x_forwarded_for"';

    access_log  /var/log/nginx/access.log  main;

    sendfile            on;
    tcp_nopush          on;
    tcp_nodelay         on;
    keepalive_timeout   5;
    types_hash_max_size 2048;

    include             /etc/nginx/mime.types;
    default_type        application/octet-stream;
    ssl_session_cache shared:SSL:1m;
    ssl_session_timeout  10m;
    ssl_ciphers HIGH:!aNULL:!MD5;
    ssl_prefer_server_ciphers on;
    proxy_http_version 1.1;
    proxy_buffering off;
    proxy_intercept_errors on;

    # IBM COS Endpoints
    # https://console.bluemix.net/docs/infrastructure/cloud-object-storage-infrastructure/endpoints.html#select-regions-and-endpoints
    # US
    server {
        listen       443 ssl http2;
        server_name  us-cos.myibmcloud.com;
        ssl_certificate "/etc/pki/tls/certs/star.myibmcloud.com.pem";
        ssl_certificate_key "/etc/pki/tls/private/star.myibmcloud.com.key";
        location / {
            proxy_set_header Host $server_name;
            proxy_pass https://s3-api.us-geo.objectstorage.service.networklayer.com;
        }
    }

    # Dallas
    server {
        listen       443 ssl http2;
        server_name  dal-cos.myibmcloud.com;
        ssl_certificate "/etc/pki/tls/certs/star.myibmcloud.com.pem";
        ssl_certificate_key "/etc/pki/tls/private/star.myibmcloud.com.key";
        location / {
            proxy_set_header Host $server_name;
            proxy_pass https://s3-api.dal-us-geo.objectstorage.service.networklayer.com;
        }
    }
}
```

上記の `proxy_pass` 項目で使用するプライベート・エンドポイントのリストについては、[COS エンドポイント](https://console.bluemix.net/docs/infrastructure/cloud-object-storage-infrastructure/endpoints.html#select-regions-and-endpoints)を参照してください。

#### ヒント:

 * スケーリングおよび回復力を向上させるには、各種エンドポイントに関連付けられた複数のプロキシー・サーバーをデプロイします。
 * 基本的なフェイルオーバーおよびロード・バランシング機能には、クライアント・サイドでラウンドロビン DNS を使用します。
 * 保護および中央集中ロギングのために、仮想ルーター・アプライアンス (VRA) の背後にプロキシー・サーバーを配置できます。

## IBM Cloud の機能の管理とプロビジョン

このセクションでは、IBM Cloud Direct Link を使用して接続できる一部の IBM Cloud PaaS および SaaS オファリングの資料へのクイック・リンクを提供します。

### ベアメタル・サーバーのプロビジョン方法

ベアメタル・サーバーのプロビジョン方法について詳しくは、[ベアメタル・サーバーのガイド](https://console.bluemix.net/docs/bare-metal/about.html#getting-started-with-bare-metal-servers)を参照してください。

### 仮想ルーター・アプライアンス (VRA) のプロビジョン方法

VRA のプロビジョン方法について詳しくは、
[VRA の入門ガイド](https://console.bluemix.net/docs/infrastructure/virtual-router-appliance/getting-started.html#getting-started)を参照してください。

### IBM Cloud オブジェクト・ストレージ (COS) のプロビジョン方法

 * COS のプロビジョン方法について詳しくは、[クラウド・オブジェクト・ストレージ・ガイド](https://console.bluemix.net/catalog/services/cloud-object-storage)を参照してください。

 * プライベート・エンドポイント (前述) のいずれかを使用して、
バケットまたはプロビジョン済み COS アカウントの任意のオブジェクトとのインターフェースを作成します。
