---

copyright:
  years: 2018
lastupdated: "2018-04-24"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# IBM Cloud Direct Link 및 IBM Cloud Object Storage 함께 사용

이 문서에서는 IBM Cloud Object Storage 및 기타 IBM Cloud 서비스에 액세스할 수 있도록 IBM Cloud Direct Link를 구성하는 방법에 대해 설명합니다. 실제로 IaaS 백본을 나가지 않고 IBM Cloud Direct Link가 있는 사설 IBM Cloud IaaS 네트워크에서 IBM Cloud PaaS 및 SaaS 기능을 지원하는 "공용" 네트워크로 브릿지하는 몇 가지 방법이 있습니다. 

현재 정책에 따라 IBM Cloud Direct Link를 통해 IBM Cloud 개인 서비스 엔드포인트에 액세스할 수 없습니다. 이 문서에 설명된 기술은 IBM Cloud에서 호스팅되는 시스템을 통한 간접 액세스에 의존합니다. Direct Link를 사용하여 개인 서비스 엔드포인트에 연결할 수 없지만 고객의 개인용 서버 및 어플라이언스는 연결 가능하게 될 수 있습니다.

## IBM Cloud Object Storage(COS)란 무엇입니까?

IBM Cloud Object Storage는 구조화되지 않은 데이터를 저장하는 웹 확장 플랫폼이며 복제 없이 신뢰성, 보안, 가용성 및 재해 복구를 제공합니다. 

IBM Cloud Object Storage를 사용하여 저장된 정보는 암호화되어 여러 지리적 위치에 분산됩니다. S3 API의 구현을 통해 이러한 정보에 액세스할 수 있습니다. 이 서비스는 IBM Cloud Object Storage 서비스에서 제공되는 분산 스토리지 기술을 사용합니다.

IBM COS는 **교차 지역** 및 **지역별**의 두 가지 구성으로 사용할 수 있습니다. 교차 지역 서비스는 단일 지역을 사용하는 것보다 더 높은 내구성과 가용성을 제공하지만 대기 시간이 다소 높습니다. 이 서비스는 현재 미국 및 유럽에서 사용 가능합니다. 지역별 서비스는 그 반대를 제공합니다. 이 서비스는 단일 지역 내의 여러 가용성 구역에 오브젝트를 분산시킵니다. 지정된 지역 또는 가용성 구역에 액세스할 수 없는 경우 오브젝트 저장소가 계속 원활하게 작동합니다. 액세스 불가능한 데이터 센터가 다시 온라인 상태가 되면 누락된 모든 변경사항이 적용됩니다.

## IBM Cloud Direct Link란 무엇입니까?

IBM Cloud Direct Link는 고객에게 해당 원격 네트워크 환경과 IBM Cloud 배치 간의 개인용 연결을 작성할 수 있는 기능을 제공하는 제품 스위트입니다. 

## IBM Cloud Direct Link를 통해 Cloud Object Storage(COS) 사용

IBM Cloud Direct Link의 연결 솔루션 제품군은 IaaS 서비스에 대한 사설 WAN 연결을 허용하기 위한 IaaS 오퍼링입니다. 대부분의 IBM Cloud PaaS 및 SaaS 솔루션이 IaaS 위에 빌드됩니다. 따라서 IBM Cloud 내에서 이러한 유형의 연결을 시작할 수 있습니다.

다음과 같은 세 가지 접근 방식을 통해 IBM Cloud Direct Link를 사용하여 IBM Cloud PaaS 및 SaaS에 연결할 수 있습니다. 현재 방법 #3이 가장 철저히 테스트되었으므로 권장되는 접근 방식입니다. 

## Direct Link를 사용하여 PaaS 및 SaaS에 연결하는 세 가지 방법


### 방법 1: 가상 라우터 어플라이언스(VRA, 경우에 따라 Vyatta라고도 함)를 사용하여 "공용에 대한 홉" 작성
 
![vyatta-flow.png](images/vyatta-flow.png)



**기본 전제: "공용 홉"을 사용하여 IBM COS에 연결하여 스토리지 엔드포인트에 연결**
*이 "공용 홉"은 IBM Cloud IaaS 백본에서 나가지 않습니다.*

* 고객이 IBM COS 고객 지원 및 온보딩 팀의 지원을 받아 공용 엔드포인트를 선택하고 API 키를 수신합니다.
* 해당 온프레미스 라우터에서 고객이 특정 서브넷에 라우트를 추가함으로써 IBM Cloud Direct Link를 사용하여 원활한 트래픽 플로우를 보장합니다.
* 해당 VRA에서 고객이 공용 네트워크를 순회하고 IBM COS 서비스용 공용 엔드포인트에 도달하기 위한 라우트를 작성합니다.
* 고객이 VRA 하드웨어(@x)의 HA 쌍을 프로비저닝해야 합니다.
* 각 VRA 멤버가 월별 20TB의 포함된 대역폭을 수신하여 퍼블릭 클라우드 측정 및 청구에 대한 비용을 오프셋합니다.
* 호스팅된 서버에서 대역폭 풀을 사용하여 선불 대역폭을 누적합니다.


### 방법 2: 클라우드 서버 경유(사설-사설)

![역방향 프록시](images/reverse-proxy.png)

**기본 전제: COS 신임 정보로 클라우드 서버 보안**

 * 클라이언트가 IBM Cloud에 하나 이상의 서버, VSI 또는 Bare Metal을 프로비저닝합니다.
 * 각 서버가 해당 개인용 인터페이스에서만 연결 및 요청을 청취하도록 웹 기반 또는 스크립트(Java, Python, PHP 등) 애플리케이션을 호스팅합니다.
 * 서버 앱이 자체 API를 사용하거나 S3(일부)와 비슷하게 만듭니다.
 * IBM Cloud 서버 개인용 인터페이스는 매우 안전합니다. VLAN, 보안 그룹, OS 방화벽 또는 VRA를 사용하여 사설 네트워크 내의 액세스를 분리합니다.
 * 호출자의 유효성을 검증하고 API 범위를 제한하기 위한 조치가 현명합니다.
 * 고객 온프레미스 네트워크의 클라이언트가 클라우드 경유 서버의 사설 IP 주소를 요청의 대상으로 사용합니다.
 * 클라이언트 라우팅 및 DNS 변경이 필요합니다.
 * 서버에서 호스팅되는 애플리케이션은 사설 COS 엔드포인트에 대한 인증된 API 호출을 발행하여 각 요청을 처리하고 호출자에게 응답을 리턴합니다.

### 방법 3: 역방향 프록시(사설-사설)

이 방법이 현재 권장되는 접근 방식입니다.

**기본 전제: COS 신임 정보로 온프레미스 클라이언트 호출자 보안**

 

 * 방법 2를 적응하여 클라우드 서버에서 웹 앱을 호스팅하는 대신 역방향 프록시로 구성된 HTTPS 서버(예: NGINX)를 호스팅합니다.
 * 각 서버가 자체 발행된 인증서를 사용하여 HTTPS에서 청취하고 아래에서 참조된 문서에 지정된 사설 COS 엔드포인트에 직접 요청을 전달합니다.
 
 ![COS 엔드포인트](https://console.bluemix.net/docs/services/cloud-object-storage/basics/endpoints.html)
 
### 클라우드의 안정성과 성능을 향상시키는 방법에 대한 예제 보기(COS에 특정하지 않음): `serverfault.com`

 * 스케일과 복원성을 증대시키기 위해 여러 프록시 서버를 배치할 수 있습니다. 
 * 기본적인 장애 복구 및 로드 밸런싱 기능을 위해 클라이언트 측에서 라운드 로빈 DNS를 사용하십시오.
 * 보호 및 중앙 집중식 로깅을 위해 프록시 서버를 VRA 뒤에 배치할 수 있습니다.
 
 ## IBM Cloud 기능 관리 및 프로비저닝 
 
이 섹션에서는 IBM Cloud Direct Link를 사용하여 연결할 수 있는 일부 IBM Cloud PaaS 및 SaaS 오퍼링에 대한 문서에 대한 빠른 링크를 제공합니다.

## 베어메탈 서버를 프로비저닝하는 방법

베어메탈을 프로비저닝하는 방법에 대한 자세한 자시사항은 [이 문서](https://console.bluemix.net/docs/bare-metal/about.html#getting-started-with-bare-metal-servers)를 참조하십시오.

## 가상 라우터 어플라이언스(VRA)를 프로비저닝하는 방법

VRA를 프로비저닝하는 방법에 대한 자세한 지시사항은 [이 문서](https://console.bluemix.net/docs/infrastructure/virtual-router-appliance/getting-started.html#getting-started)를 참조하십시오.

## IBM COS(Cloud Object Storage)를 프로비저닝하는 방법

 * COS를 프로비저닝하는 방법에 대한 자세한 지시사항은 [이 문서](https://console.bluemix.net/catalog/services/cloud-object-storage)를 참조하십시오.
 
 * 이전에 나열된 개인용 엔드포인트 중 하나를 사용하여 프로비저닝된 COS 계정의 버킷 또는 오브젝트와 인터페이스하십시오.
