---

copyright:
  years: 2017, 2018
lastupdated: "2018-05-22"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# 使用 IBM Cloud Direct Link 连接到 IBM Cloud Object Storage

本文档描述了如何配置 IBM Cloud Direct Link，以便您有权访问 IBM Cloud Object Storage (COS)。虽然此处描述的方法是针对 COS 设计并测试的，但也可能适用于某些其他 IBM Cloud 服务。

根据目前的策略，IBM Cloud Direct Link 会拒绝对 IBM Cloud 专用服务端点的访问，包括 IBM Cloud Object Storage (COS) 使用的端点。本文档中所述的方法依赖于通过客户的 IBM Cloud 帐户中托管的服务器对 COS 进行间接访问。设置之后，每个客户的服务器都可以在 IBM Cloud 专用服务端点及其通过 Direct Link 连接的远程网络之间双向转发流量。

## 什么是 IBM Cloud Object Storage (COS)？

IBM Cloud Object Storage (COS) 是一个用于存储非结构化数据的 Web 扩展平台。它提供了可靠性、安全性、可用性和灾难恢复功能，无需手动进行复制。

存储在 IBM Cloud Object Storage 中的信息会进行加密并分散在多个地理位置。可通过实现 S3 API 对其进行访问。此服务利用的是 IBM Cloud Object Storage 服务提供的分布式存储技术。

IBM COS 有以下三种配置可用：**跨区域**、**区域**和**单站点**。

 * “跨区域”服务提供的耐久性和可用性都要高于使用单个区域，但代价是等待时间略长。此服务目前在美国和欧盟可用。
 
 * “区域”服务的做法则相反：它在单个区域内跨多个可用性专区分发对象。如果给定区域或可用性专区不可访问，对象存储也能继续顺利进行。当不可访问的数据中心重新联机时，将应用所有错过的更改。
  
 * “单站点”服务提供对所选数据中心内 Cloud Object Storage 的经济实惠的访问。

### COS 专用和公共端点
端点是应用程序用于发出 COS 命令以及与 COS 交换数据的 URL。每个端点都使用相同的应用程序编程接口 (API) 与 COS 进行交互。

在 IBM Cloud 中供应的服务器将使用专用 API 端点来提供服务，包括 COS。通过专用端点，客户的 IBM Cloud 服务器可高速、直接连接到服务，无需额外的带宽成本。

COS 公共端点向 IBM Cloud 客户提供了对可从 IBM Cloud 中访问的 COS 数据的访问权，但公共端点允许从任何配备了因特网的位置进行访问。

下面两个警告适用于 COS 公共端点：
 * 使用公共端点发生的计量带宽成本可能会超出 COS 服务所收取的使用费。 
 * 尽管所有数据在传输过程中都已加密，但对于通过因特网传输的数据，客户仍可能有隐私方面的顾虑或有相关监管限制。

## 什么是 IBM Cloud Direct Link？
IBM Cloud Direct Link 是一个产品套件，使客户能够在其远程网络环境与其 IBM Cloud 部署之间创建安全的专用连接。Direct Link 交换的数据绝不会向因特网公开。

## 通过 IBM Cloud Direct Link 使用 Cloud Object Storage (COS)
IBM 工程师开发了一种方法，允许购买 COS 和 Direct Link 的 IBM Cloud 客户与 COS 专用端点建立远程连接。此类型的连接扩大了专用服务端点的优点，使得 IBM Cloud 设施外部的客户机系统也可以使用这些端点。
 
此解决方案在随后的各部分中以图和文字方式进行了描述。

### 逆向代理

**基本前提：远程客户机通过专用服务器将请求（包括安全凭证）传递给 COS**

![reverse=proxy](images/reverse-proxy.png)

远程站点的客户机发起了 HTTPS（安全 HTTP）COS 请求。这些请求通过 IBM Cloud Direct Link 安全地传输，并将部署在客户 IBM Cloud 帐户中的_逆向代理服务器_集群中的一个服务器设为目标。从该服务器中，会将请求传递到 COS 专用端点，经过处理后，结果会返回到远程调用客户机。

任何使用 COS 的样本客户机代码也应该通过_逆向代理_服务器运行。唯一需要的调整是客户机要将逆向代理服务器的 IP 地址或 URL 设为目标，而不是将 IBM 发布的其中一个 COS 专用端点 URL 设为目标。

#### 安装 Nginx 逆向代理
**NginX** 是一个成熟、紧凑、快速的开放式源代码 Web 服务器，擅长处理专项任务，包括先前提到的_逆向代理_服务器角色。

下面用于设置 NginX 逆向代理服务器的指示信息和配置信息在您根据环境对其进行调整后即可应用。如果遇到困难或需要更多信息，请查阅 [Nginx 文档](https://docs.nginx.com/nginx/admin-guide/web-server/reverse-proxy/)的逆向代理部分，或搜索相关站点，例如 [stackoverflow](http://stackoverflow.com)。

1. 通过最低 **RHEL** 或 **CentOS** Linux 构建（建议）来供应 VSI 或裸机服务器
2. 对于每个 VSI，在公共接口上启用以下安全组规则：`allow_http`、`allow_https`、`allow_outbound` 和 `allow_ssh`
3. 对于每个 VSI，在专用接口上启用 `allow_all` 和 `allow_outbound` 规则；选择**保存**
4. 使用 Windows 中的 **PuTTY** 或使用桌面的终端程序，通过 `ssh` 以 root 用户身份登录到新服务器
5. 升级操作系统 (`yum update`)
6. 安装 EPEL 存储库 (`yum install epel-release`)
7. 安装 NginX (`yum install nginx`)
8. 启动 NginX (`nginx`) 并在浏览器中打开服务器的 IP 地址。
9. `nginx.conf` 的缺省位置为 `/etc/nginx`。创建安全副本。
10. 将以下样本 `nginx.conf` 配置文件移至 `/etc/nginx` 中
11. 通过 IBM Cloud 门户网站购买 SSL 证书，或运行 `yum install easy-rsa` 命令并查阅您最喜欢的联机文档，以获取有关创建自签名证书的提示。
12. 将证书信息添加到配置文件 `nginx.conf`
13. 使用 `nginx -t` 命令测试已修改的 NginX 配置
14. 如果测试通过，请使用 `nginx -s quit; sleep 3; nginx` 命令重新启动 `nginx`
15. 现在，客户机应该能够向 NginX（代理）服务器的 IP 或 URL 提交 COS 请求

#### 注：

* 该解决方案假定已订购并正确部署了 Direct Link，尽管可以在不使用 Direct Link 的情况下对解决方案进行测试。
* 可选的内存或磁盘高速缓存可与 `proxy_cache` 配合使用。
* 较大的文件传输可能需要更大的 `proxy_read_timeout` 值。
* 使用 `keepalive` 或 Pacemaker 实现高可用性（自动故障转移）。

#### 配置文件：`nginx.conf`

以下部分中显示了样本配置文件。您可以复制并粘贴该文件。

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

请参阅 [COS 端点](https://console.bluemix.net/docs/infrastructure/cloud-object-storage-infrastructure/endpoints.html#select-regions-and-endpoints)，以获取用于上面的 `proxy_pass` 条目的专用端点的列表。

#### 提示：

 * 要提升规模和弹性，请部署多个与不同端点关联的代理服务器。
 * 在客户机端使用循环法 DNS，以实现基本的故障转移和负载均衡功能。
 * 代理服务器可以放在虚拟路由器设备 (VRA) 后面以受到保护，也可用于集中日志记录。

## 管理和供应 IBM Cloud 功能

本部分提供了可以使用 IBM Cloud Direct Link 连接到的某些 IBM Cloud PaaS 和 SaaS 服务产品的文档快速链接。

### 如何供应裸机服务器

有关如何供应裸机服务器的详细指示信息，请参阅[裸机服务器指南](https://console.bluemix.net/docs/bare-metal/about.html#getting-started-with-bare-metal-servers)。

### 如何供应虚拟路由器设备 (VRA)

有关如何供应 VRA 的详细指示信息，请参阅 [VRA 入门指南](https://console.bluemix.net/docs/infrastructure/virtual-router-appliance/getting-started.html#getting-started)。

### 如何供应 IBM Cloud Object Storage (COS)

 * 有关如何供应 COS 的详细指示信息，请参阅 [Cloud Object Storage 指南](https://console.bluemix.net/catalog/services/cloud-object-storage)。

 * 使用其中一个（先前列出的）专用端点创建与供应的 COS 帐户中的存储区或任何对象的接口。
