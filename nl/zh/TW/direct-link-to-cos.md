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

# 使用 IBM Cloud Direct Link 連接至 IBM Cloud Object Storage

本文件說明如何配置 IBM Cloud Direct Link，讓您能夠存取 IBM Cloud Object Storage (COS)。雖然這裡說明的方法是搭配 COS 來進行設計及測試，但它們可能適用於某些其他 IBM Cloud 服務。

依現行原則，IBM Cloud Direct Link 會拒絕對 IBM Cloud 專用服務端點的存取，包括 IBM Cloud Object Storage (COS) 使用的那些服務端點。本文件所說明的技術仰賴透過客戶的 IBM Cloud 帳戶所管理的伺服器，來對 COS 進行間接存取。設定之後，每個客戶的伺服器都可以在 IBM Cloud 專用服務端點與其透過 Direct Link 連接的遠端網路之間，雙向轉遞資料流量。

## 何謂 IBM Cloud Object Storage (COS)？

IBM Cloud Object Storage (COS) 是一種可儲存非結構化資料的 Web 規模平台。它提供可靠性、安全、可用性及災難回復，而不進行手動抄寫。

儲存在 IBM Cloud Object Storage 內的資訊已加密，並分散在多個地理位置。可透過 S3 API 的實作來存取它。本服務利用 IBM Cloud Object Storage 服務所提供之分散式儲存技術。

IBM COS 提供三種配置：**跨區域**、**區域**及**單一網站**。

 * 「跨區域」服務提供的延續性和可用性比使用單一區域更高，但代價是延遲稍高。目前美國和歐盟有提供此服務。（請注意，使用 Virtual Router Appliance (VRA)，您也可能使用 Direct Link 連接至亞太地區的 COS。）
 
 * 「區域」服務剛好相反：它在單一地區內的多個可用性區域之間分散物件。如果給定的區域或可用性區域無法存取，物件儲存庫會繼續順利運作。當無法存取的資料中心重新連線時，會套用任何遺漏的變更。
  
 * 「單一網站」服務在所選取的資料中心提供可負擔得起的 Cloud Object Storage 存取。

### COS 專用和公用端點
端點是應用程式用來發出 COS 指令並與 COS 交換資料的 URL。每個端點使用相同的「應用程式設計介面 (API)」來與 COS 互動。

在 IBM Cloud 內佈建的伺服器會使用專用 API 端點來提供服務，包括 COS。專用端點為客戶的 IBM Cloud 伺服器提供高速直接連線來連接服務，而不增加頻寬成本。

COS 公用端點讓 IBM Cloud 客戶能夠存取可從 IBM Cloud 內存取的相同 COS 資料，但公用端點允許從任何有配備網際網路的位置存取。

有兩個警示適用於 COS 公用端點：
 * 使用公用端點可能會針對超出 COS 服務需收取的使用收費的頻寬產生計量成本。 
 * 即使所有資料在傳輸中已加密，但客戶可能對透過網際網路傳輸的資料有相關的隱私權問題或法規限制。

## 何謂 IBM Cloud Direct Link？
IBM Cloud Direct Link 是一個產品組合，可讓客戶在他們的遠端網路環境與其 IBM Cloud 部署之間建立安全的專用連線。由 Direct Link 交換的資料絕不會公開在網際網路上。

## 透過 IBM Cloud Direct Link 使用 Cloud Object Storage (COS)
IBM 工程師已開發一種方法，可讓購買 COS 及 Direct Link 的 IBM Cloud 客戶建立與 COS 專用端點的遠端連線。這種類型的連線延伸了專用服務端點的優點，讓 IBM Cloud 設施以外的用戶端系統可以使用它們。
 
下列幾節將繪圖並說明此解決方案。

### 反向 Proxy

**基本前提：遠端用戶端透過 COS 的專用伺服器來傳遞要求，包括安全的認證**

![reverse=proxy](images/reverse-proxy.png)

HTTPS（安全的 HTTP）COS 要求是從遠端網站的用戶端起始。它們透過 IBM Cloud Direct Link 進行安全傳輸，以客戶的 IBM Cloud 帳戶中部署的_反向 Proxy 伺服器_的其中一個叢集為目標。從這裡，要求會傳遞至 COS 專用端點進行處理，然後其結果會傳回至遠端呼叫用戶端。

任何與 COS 搭配使用的範例用戶端程式碼，也應該可以透過_反向 Proxy_ 伺服器運作。唯一需要的調整是，用戶端不是以 IBM 所發佈的其中一個 COS 專用端點 URL 為目標，而是以反向 Proxy 伺服器的 IP 位址或 URL 為目標。

#### 安裝 Nginx 反向 Proxy
**NginX** 是一個成熟、精簡及快速開放程式碼 Web 伺服器，擅長特殊化作業，包括先前提及的_反向 Proxy_ 伺服器角色。

以下的指示及配置資訊--用於設定 NginX 反向 Proxy 伺服器--可在您調整至適合您環境之後適用。如果您卡住或需要其他資訊，請參閱 [Nginx 文件](https://docs.nginx.com/nginx/admin-guide/web-server/reverse-proxy/)的反向 Proxy 部分，或搜尋 [stackoverflow](http://stackoverflow.com) 以取得範例。

1. 以最低的 **RHEL** 或 **CentOS** Linux 建置來佈建您的 VSI 或裸機伺服器（建議）
2. 對於每一個 VSI，在公用介面上啟用下列安全群組規則：`allow_http`、`allow_https`、`allow_outbound`、`allow_ssh`
3. 對於每一個 VSI，在專用介面上啟用 `allow_all` 和 `allow_outbound` 規則；選取**儲存**
4. 在 Windows 或桌面的終端機程式中使用 **PuTTY**，以 root 身分使用 `ssh` 進入新的伺服器
5. 升級作業系統 OS (`yum update`)
6. 安裝 EPEL 儲存庫 (`yum install epel-release`)
7. 安裝 NginX (`yum install nginx`)
8. 啟動 NginX (`nginx`)，並在瀏覽器中開啟伺服器的 IP 位址。
9. `nginx.conf` 的預設位置為 `/etc/nginx`。建立安全備份。
10. 將下面的範例 `nginx.conf` 配置檔移至 `/etc/nginx`
11. 透過 IBM Cloud 入口網站購買 SSL 憑證，或執行 `yum install easy-rsa` 指令，並查閱您最愛的線上文件，以取得建立自簽憑證的相關提示。
12. 將您的憑證資訊新增至配置檔 `nginx.conf`
13. 使用 `nginx -t` 指令來測試已修改的 NginX 配置
14. 如果您的測試通過，請使用 `nginx -s quit; sleep 3; nginx` 指令重新啟動 `nginx`
15. 用戶端現在應能夠提交 COS 要求給 NginX (Proxy) 伺服器的 IP 或 URL

#### 附註：

* 此解決方案假設已訂購並適當地部署 Direct Link，不過，也可以在沒有它的情況下進行測試。
* 選用的記憶體或磁碟快取可與 `proxy_cache` 搭配使用
* 較大的檔案傳送可能需要較長的 `proxy_read_timeout` 值。
* 針對高可用性（自動失效接手）使用 `keepalive` 或 Pacemaker

#### 配置檔：`nginx.conf`

範例配置檔顯示在下列區段中。您可以複製並貼上它。

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

如需可使用於上述 `proxy_pass` 項目的專用端點清單，請參閱 [COS 端點](https://console.bluemix.net/docs/infrastructure/cloud-object-storage-infrastructure/endpoints.html#select-regions-and-endpoints)。

#### 提示：

 * 若要提高規模與備援，可部署與不同端點相關聯的多個 Proxy 伺服器。
 * 在用戶端使用循環式 DNS，以提供初步失效接手和負載平衡功能。
 * Proxy 伺服器可以放在 Virtual Router Appliance (VRA) 後面，以便保護和集中化記載。

## 管理及佈建 IBM Cloud 功能

本節提供您可以使用 IBM Cloud Direct Link 連接的一些 IBM Cloud PaaS 及 SaaS 供應項目之文件的快速鏈結。

### 如何佈建裸機伺服器

如需如何佈建裸機伺服器的詳細指示，請參閱[裸機伺服器手冊](https://console.bluemix.net/docs/bare-metal/about.html#getting-started-with-bare-metal-servers)。

### 如何佈建 Virtual Router Appliance (VRA)

如需如何佈建 VRA 的詳細指示，請參閱 [VRA 入門手冊](https://console.bluemix.net/docs/infrastructure/virtual-router-appliance/getting-started.html#getting-started)。

### 如何佈建 IBM Cloud Object Storage (COS)

 * 如需如何佈建 COS 的詳細指示，請參閱 [Cloud Object Storage 手冊](https://console.bluemix.net/catalog/services/cloud-object-storage)。

 * 使用其中一個專用端點（先前所列出），與您佈建的 COS 帳戶中的儲存區或任何物件之間建立一個介面。
