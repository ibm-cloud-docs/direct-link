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

# IBM Cloud Direct Link를 사용하여 IBM Cloud Object Storage에 연결

이 문서에서는 IBM Cloud Object Storage(COS)에 액세스할 수 있도록 IBM Cloud Direct Link를 구성하는 방법에 대해 설명합니다. 여기에 설명된 방법은 COS로 디자인되고 테스트되었지만 특정한 다른 IBM Cloud 서비스에 대해 작업할 수 있습니다.

현재 정책에 따라 IBM Cloud Direct Link는 IBM Cloud Object Storage(COS)에서 사용되는 것을 포함하여 IBM Cloud 개인 서비스 엔드포인트에 대한 액세스를 거부합니다. 이 문서에 설명된 기술은 고객의 IBM Cloud 계정에서 호스팅되는 서버를 통한 COS에 대한 간접 액세스에 의존합니다. 설정 후 각 고객의 서버는 IBM Cloud 개인 서비스 엔드포인트와 Direct Link에서 연결된 해당 원격 네트워크 간에 양방향으로 트래픽을 전달할 수 있습니다.

## IBM Cloud Object Storage(COS)란 무엇입니까?

IBM Cloud Object Storage(COS)는 구조화되지 않은 데이터를 저장하는 웹 확장 플랫폼이며 수동 복제 없이 신뢰성, 보안, 가용성 및 재해 복구를 제공합니다.

IBM Cloud Object Storage 내에 저장된 정보는 암호화되어 여러 지리적 위치에 분산됩니다. S3 API의 구현을 통해 이러한 정보에 액세스할 수 있습니다. 이 서비스는 IBM Cloud Object Storage 서비스에서 제공되는 분산 스토리지 기술을 사용합니다.

IBM COS는 **교차 지역**, **지역별** 및 **단일 사이트**의 세 가지 구성으로 사용할 수 있습니다.

 * 교차 지역 서비스는 단일 지역을 사용하는 것보다 더 높은 내구성과 가용성을 제공하지만 대기 시간이 다소 높습니다. 이 서비스는 현재 미국 및 유럽에서 사용 가능합니다.
 
 * 지역별 서비스는 그 반대를 제공합니다. 이 서비스는 단일 지역 내의 여러 가용성 구역에 오브젝트를 분산시킵니다. 지정된 지역 또는 가용성 구역에 액세스할 수 없는 경우 오브젝트 저장소가 계속 원활하게 작동합니다. 액세스 불가능한 데이터 센터가 다시 온라인 상태가 되면 누락된 모든 변경사항이 적용됩니다.
  
 * 단일 사이트 서비스는 선택한 데이터 센터의 Cloud Object Storage에 대한 경제적인 액세스를 제공합니다.

### COS 개인용 및 공용 엔드포인트
엔드포인트는 애플리케이션이 COS 명령을 실행하고 COS와 데이터를 교환하는 데 사용하는 URL입니다. 모든 엔드포인트는 동일한 API(Application Programming Interface)를 사용하여 COS와 상호작용합니다.

IBM Cloud 내에서 프로비저닝된 서버는 COS를 포함한 서비스에 개인용 API 엔드포인트를 사용합니다. 개인용 엔드포인트는 고객의 IBM Cloud 서버에 추가된 대역폭 비용 없이 서비스에 대한 고속의 직접 연결을 제공합니다.

COS 공용 엔드포인트는 IBM Cloud 고객에게 IBM Cloud 내에서 액세스할 수 있는 것과 동일한 COS 데이터에 대한 액세스를 제공하지만 공용 엔드포인트는 인터넷이 장착된 위치에서의 액세스를 허용합니다.

두 가지 제한사항이 COS 공용 엔드포인트에 적용됩니다.
 * 공용 엔드포인트를 사용하면 COS 서비스에서 부과되는 사용 요금을 초과하는 대역폭에 대해 측정된 비용이 발생할 수 있습니다. 
 * 모든 데이터가 전송 중에 암호화되지만 고객이 인터넷을 통해 전송되는 데이터와 관련된 개인정보처리방침 또는 규제 제한사항의 적용을 받을 수 있습니다.

## IBM Cloud Direct Link란 무엇입니까?
IBM Cloud Direct Link는 고객에게 해당 원격 네트워크 환경과 IBM Cloud 배치 간의 안전한 개인용 연결을 작성할 수 있는 기능을 제공하는 제품 스위트입니다. Direct Link에서 교환된 데이터는 인터넷에 노출되지 않습니다.

## IBM Cloud Direct Link를 통해 Cloud Object Storage(COS) 사용
IBM 엔지니어가 COS 및 Direct Link를 구매하는 IBM Cloud 고객이 COS 개인용 엔드포인트에 원격으로 연결할 수 있도록 방법을 개발했습니다. 이 유형의 연결은 개인 서비스 엔드포인트의 장점을 확장하므로 IBM Cloud 설비 외부의 클라이언트 시스템에서 사용될 수 있습니다.
 
이 솔루션은 다음 섹션에서 다이어그램으로 표시되고 설명됩니다.

### 역방향 프록시

**기본 전제: 원격 클라이언트가 개인용 서버를 통해 COS에 보안 인증 정보를 포함하는 요청 전달**

![역방향 프록시](images/reverse-proxy.png)

HTTPS(보안 HTTP) COS 요청은 원격 사이트의 클라이언트에서 시작됩니다. 고객의 IBM Cloud 계정에 배치된 _역방향 프록시 서버_의 클러스터 중 하나를 대상으로 하여 IBM Cloud Direct Link를 통해 안전하게 전송됩니다. 거기에서 요청이 COS 개인용 엔드포인트에 전달되고 처리된 후 원격 호출 클라이언트에 결과가 리턴됩니다.

COS에 대해 작업하는 모든 샘플 클라이언트 코드는 _역방향 프록시_ 서버를 통해 작동해야 합니다. 유일하게 필요한 조정은 클라이언트가 IBM에서 공개된 COS 개인용 엔드포인트 URL 중 하나를 대상으로 하는 대신 역방향 프록시 서버의 IP 주소 또는 URL을 대상으로 하는 것입니다.

#### Nginx 역방향 프록시 설치
**NginX**는 이전에 언급된 _역방향 프록시_ 서버 역할을 포함하여 전문화된 태스크에서 탁월한 성능을 나타내는 완성되고 간편하며 빠른 오픈 소스 웹 서버입니다.

다음에 나오는 NginX 역방향 프록시 서버 설정에 대한 지시사항 및 구성 정보를 사용자 맞게 조정한 후 작업할 수 있습니다. 중단되거나 추가 정보가 필요한 경우 [Nginx 문서](https://docs.nginx.com/nginx/admin-guide/web-server/reverse-proxy/)의 역방향 프록시 부분을 참조하거나 [stackoverflow](http://stackoverflow.com)에서 예제를 검색하십시오.

1. 최소 **RHEL** 또는 **CentOS** Linux 빌드로 VSI 또는 베어메탈 서버를 프로비저닝하십시오(권장).
2. 각 VSI에 대해 공용 인터페이스에서 `allow_http`, `allow_https`, `allow_outbound` 및 `allow_ssh` 보안 그룹 규칙을 사용으로 설정하십시오.
3. 각 VSI에 대해 개인용 인터페이스에 대한 `allow_all` 및 `allow_outbound` 규칙을 사용으로 설정하고 **저장**을 선택하십시오.
4. Windows의 **PuTTY** 또는 데스크탑의 터미널 프로그램을 사용하여 루트로 새 서버에 `ssh`하십시오.
5. 운영 체제 OS를 업그레이드하십시오(`yum update`).
6. EPEL 저장소를 설치하십시오(`yum install epel-release`).
7. NginX를 설치하십시오(`yum install nginx`).
8. NginX를 시작하고(`nginx`) 브라우저에서 서버의 IP 주소를 여십시오.
9. `nginx.conf`의 기본 위치는 `/etc/nginx`입니다. 안전한 사본을 작성하십시오.
10. 아래의 샘플 `nginx.conf` 구성 파일을 `/etc/nginx`로 이동하십시오.
11. IBM Cloud 포털을 통해 SSL 인증서를 구매하거나 `yum install easy-rsa` 명령을 실행하고 선호하는 온라인 문서에서 자체 서명된 인증서 작성에 대한 팁을 참조하십시오.
12. 구성 파일 `nginx.conf`에 인증서 정보를 추가하십시오.
13. `nginx -t` 명령을 사용하여 수정된 NginX 구성을 테스트하십시오.
14. 테스트에 통과하면 `nginx -s quit; sleep 3; nginx` 명령을 사용하여 `nginx`를 다시 시작하십시오.
15. 이제 클라이언트가 COS 요청을 NginX(프록시) 서버의 IP 또는 URL에 제출할 수 있습니다.

#### 참고사항:

* Direct Link 없이 테스트할 수 있지만 이 솔루션에서는 Direct Link가 주문되고 올바르게 배치되었다고 가정합니다.
* 선택적 메모리 또는 디스크 캐시를 `proxy_cache`와 함께 사용할 수 있습니다.
* 큰 파일의 전송을 위해 더 긴 `proxy_read_timeout` 값이 필요할 수 있습니다.
* 고가용성(자동 장애 복구)을 위해 `keepalive` 또는 Pacemaker를 사용하십시오.

#### 구성 파일: `nginx.conf`

샘플 구성 파일이 다음 섹션에 표시되어 있습니다. 복사하여 붙여넣을 수 있습니다.

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

위의 `proxy_pass` 항목에 사용할 개인용 엔드포인트 목록은 [COS 엔드포인트](https://console.bluemix.net/docs/infrastructure/cloud-object-storage-infrastructure/endpoints.html#select-regions-and-endpoints)를 참조하십시오.

#### 팁:

 * 스케일과 복원성을 증대시키려면 서로 다른 엔드포인트와 연관된 여러 프록시 서버를 배치하십시오.
 * 기본적인 장애 복구 및 로드 밸런싱 기능을 위해 클라이언트 측에서 라운드 로빈 DNS를 사용하십시오.
 * 보호 및 중앙 집중식 로깅을 위해 프록시 서버를 가상 라우터 어플라이언스(VRA) 뒤에 배치할 수 있습니다.

## IBM Cloud 기능 관리 및 프로비저닝

이 섹션에서는 IBM Cloud Direct Link를 사용하여 연결할 수 있는 일부 IBM Cloud PaaS 및 SaaS 오퍼링에 대한 문서에 대한 빠른 링크를 제공합니다.

### 베어메탈 서버를 프로비저닝하는 방법

베어메탈 서버를 프로비저닝하는 방법에 대한 자세한 지시사항은 [Bare Metal Servers 안내서](https://console.bluemix.net/docs/bare-metal/about.html#getting-started-with-bare-metal-servers)를 참조하십시오.

### 가상 라우터 어플라이언스(VRA)를 프로비저닝하는 방법

VRA를 프로비저닝하는 방법에 대한 자세한 지시사항은 [VRA 시작하기 안내서](https://console.bluemix.net/docs/infrastructure/virtual-router-appliance/getting-started.html#getting-started)를 참조하십시오.

### IBM COS(Cloud Object Storage)를 프로비저닝하는 방법

 * COS를 프로비저닝하는 방법에 대한 자세한 지시사항은 [Cloud Object Storage 안내서](https://console.bluemix.net/catalog/services/cloud-object-storage)를 참조하십시오.

 * 이전에 나열된 개인용 엔드포인트 중 하나를 사용하여 프로비저닝된 COS 계정의 버킷 또는 오브젝트와의 인터페이스를 작성하십시오.
