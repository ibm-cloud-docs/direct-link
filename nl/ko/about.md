---

copyright:
  years: 2017, 2018
lastupdated: "2018-08-09"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# IBM Cloud Direct Link 정보

이 섹션에서는 네 가지 IBM Cloud Direct Link 솔루션 각각의 이점 및 주요 기능에 대한 세부사항을 찾아볼 수 있습니다.
  * [**IBM Cloud Direct Link Exchange**](#the-ibm-cloud-direct-link-exchange-solution)
  * [**IBM Cloud Direct Link Connect**](#the-ibm-cloud-direct-link-connect-solution)
  * [**IBM Cloud Direct Link Dedicated**](#the-ibm-cloud-direct-link-dedicated-solution)
  * [**IBM Cloud Direct Link Dedicated Hosting**](#the-ibm-cloud-direct-link-dedicated-hosting-solution)

## IBM Cloud Direct Link Exchange 솔루션

IBM Cloud Direct Link Exchange 솔루션을 사용하면 고객이 Cloud Exchange 제공자를 활용하여 {{site.data.keyword.BluSoftlayer_notm}} 위치에 대한 연결을 제공할 수 있습니다. {{site.data.keyword.BluSoftlayer_notm}}에서 Cloud Exchange 제공자로의 실제 연결이 이미 이루어져서, 다른 고객들 간에 공유되고 있기 때문에 이 오퍼링은 일반적으로 절감된 비용으로 연결을 제공합니다.

**공통 유스 케이스:** _하이브리드 워크로드, 교차 제공자 워크로드, 높은 발신 대역폭을 통한 대형 또는 빈번한 데이터 전송, 개인용 워크로드 및 환경 관리에 가장 적합합니다.  일반적으로 이 옵션은 원하는 PoP 위치에 원하는 IBM Cloud Direct Link Exchange 제공자가 이미 있는 경우에 선택됩니다._

![그림 1](/images/Direct-Link-Exchange.png)

 * **종료 위치:** {{site.data.keyword.BluSoftlayer_notm}} PoP(Point of Presence)입니다.

 * **일반 배치 시간:** Equinix 제공자의 경우 일반 배치 시간은 몇 시간이 걸립니다. 다른 제공자의 경우 회선에 교환에 도달하고 5 - 10일 이후입니다. 배치 시간은 NSP 또는 캐리어에서 회선을 주문할 때 사용자의 위치와 요구사항에 따라 전체 30 - 60일이 걸릴 수도 있습니다.

 * **교차 연결 세부사항:** 보안 Cloud Exchange 상호 연결을 위한 실제 교차 연결은 {{site.data.keyword.BluSoftlayer_notm}}와 Cloud Exchange 제공자 사이에서 유지보수됩니다. 고객이 Cloud Exchange 제공자에 상호 연결되면 Cloud Exchange 제공자로부터 "가상 회선"을 요청하고, {{site.data.keyword.BluSoftlayer_notm}}에 논리 연결을 설정합니다.

 * **포트 속도 옵션:** 50Mbps, 100Mbps, 200Mbps, 500Mbps 또는 1Gbps를 선택하십시오.

 * **대략적인 대기 시간:** 로컬 영역(DAL, AMS, MEL와 같이 동일한 세 개의 문자로 된 접두부가 있는 데이터 센터) 내에서 대기 시간은 대략적으로 1.5밀리초입니다. 실시간 P2P(PoP-to-PoP) 위치 대기 시간 측정에 대해서는 http://lg.softlayer.com/을 참조하십시오.

 * **코로케이션 서비스:** 없음.

 * **중복성:** IBM Cloud Direct Link Exchange에 대한 중복성을 설정하려면 둘 이상의 위치에 연결이 필요하거나, Cloud Exchange 제공자가 활용할 수 있는 보조 XCR이 사용 가능한 위치를 선택해야 합니다.

 * **로컬/글로벌 라우팅 옵션:** 로컬 라우팅 옵션이 기본 라우팅 옵션입니다. Direct Link PoP(예를 들어, DAL, AMS 또는 MEL로 표기됨)과 동일한 마켓 내의 데이터 센터에 액세스할 수 있습니다. 인마켓 IBM Cloud 리소스를 로컬 마켓 외부의 데이터 센터에 있는 다른 IBM Cloud 리소스에 연결하기 위한 추가 기능으로 글로벌 라우팅 옵션이 필요합니다. IBM Cloud 리소스 간의 워크로드를 공유하는 데 사용됩니다(예: 댈러스와 애슈번 또는 댈러스와 프랑크푸르트).
 
## IBM Cloud Direct Link Connect 솔루션

**공통 유스 케이스** Direct Link Exchange 솔루션과 유사합니다. 추가 속도 옵션을 제공합니다. Direct Link Cloud Connect 솔루션은 IBM Cloud 네트워크 고객에 대한 낮은 비용의 시작점을 제공합니다.

![그림 2](/images/Direct-Link-Connect.png)

* **종료 위치:** {{site.data.keyword.BluSoftlayer_notm}} PoP(Point of Presence)입니다.

* **일반적인 배치 시간:** 회선이 교환에 도달하고 5-10일 이후입니다. 배치 시간은 NSP 또는 캐리어에서 회선을 주문할 때 사용자의 위치와 요구사항에 따라 전체 30 - 60일이 걸릴 수도 있습니다.

* **교차 연결 세부사항:** 보안  Direct Link Connect의 상호 연결을 위한 실제 교차 연결은 {{site.data.keyword.BluSoftlayer_notm}}와 Connect 제공자 사이에서 유지보수됩니다. 고객이 클라우드 연결 제공자에 상호 연결되면 Cloud Connect Provider로부터 "가상 회선"을 요청하고 {{site.data.keyword.BluSoftlayer_notm}}에 논리 연결을 설정합니다.

* **포트 속도 옵션:** 50Mbps, 100Mbps, 200Mbps, 500Mbps, 1Gbps, 2Gbps 또는 5Gbps를 선택하십시오.

* **대략적인 대기 시간:** 로컬 영역(DAL, AMS, MEL와 같이 동일한 세 개의 문자로 된 접두부가 있는 데이터 센터) 내에서 대기 시간은 대략적으로 1.5밀리초입니다. 실시간 P2P(PoP-to-PoP) 위치 대기 시간 측정에 대해서는 http://lg.softlayer.com/을 참조하십시오.

* **코로케이션 서비스:** 없음.

* **중복성:** IBM Cloud Direct Link 연결에 대한 중복성을 설정하려면 둘 이상의 위치에 대한 연결이 필요하거나 IBM Cloud Connect 제공자가 활용할 수 있는 보조 XCR이 사용 가능한 위치를 선택해야 합니다.

* **로컬/글로벌 라우팅 옵션:** 로컬 라우팅 옵션이 기본 라우팅 옵션입니다. Direct Link PoP(예를 들어, DAL, AMS 또는 MEL로 표기됨)과 동일한 마켓 내의 데이터 센터에 액세스할 수 있습니다. 인마켓 IBM Cloud 리소스를 로컬 마켓 외부의 데이터 센터에 있는 다른 IBM Cloud 리소스에 연결하기 위한 추가 기능으로 글로벌 라우팅 옵션이 필요합니다. IBM Cloud 리소스 간의 워크로드를 공유하는 데 사용됩니다(예: 댈러스와 애슈번 또는 댈러스와 프랑크푸르트).

## IBM Cloud Direct Link Dedicated 솔루션

IBM Cloud Direct Link Dedicated 솔루션을 사용하면 고객이 자신의 {{site.data.keyword.BluSoftlayer_notm}} 사설 네트워크에 대한 데디케이티드 단일 모드의 파이버 교차 연결을 종료할 수 있습니다.

 **공통 유스 케이스:** _하이브리드 워크로드, 교차 제공자 워크로드, 대형 또는 빈번한 데이터 전송, 개인용 워크로드 및 환경 관리에 대한 작업에 가장 적합합니다.  이 옵션은 일반적으로 다음과 같은 경우에 선택됩니다. (1) 원하는 PoP에 원하는 IBM Cloud Direct Link Exchange 제공자가 없는 경우, (2) 많은 처리량을 필요로 하는 고성능 워크로드를 위한 경우, (3) IBM Cloud Direct Link Exchange 구현 모델로 충족되지 않는 정부 규제 준수를 위한 경우._

![그림 3](/images/Direct-link-Dedicated.png)

 * **종료 위치:** {{site.data.keyword.BluSoftlayer_notm}} PoP(Point of Presence)입니다.

 * **일반적인 배치 시간:** 새 회선이 POP에 도달하고 10-15 영업일 이후입니다. 배치 시간은 NSP 또는 캐리어에서 회선을 주문할 때 사용자의 위치와 요구사항에 따라 전체 30 - 60일이 걸릴 수도 있습니다.

 * **교차 연결 세부사항:** {{site.data.keyword.BluSoftlayer_notm}}는 고객 케이지 또는 제공자에서 {{site.data.keyword.BluSoftlayer_notm}} CFA 종료 지점으로 실행되는 파이버 이더넷(단일 모드 파이버 전용, 1Gig-LX 또는 10Gig-LR 광학 중 하나)을 주문하기 위해 고객이 사용하는 LOA(Letter of Authorization)를 제공하며, 이는 교차 연결 라우터(XCR) 인프라에 연결됩니다. 매체는 1310nm 주파수 광학이어야 합니다.

 * **포트 속도 옵션:** 1Gbps, 2Gbps, 5Gbps 또는 10Gbps를 선택하십시오.

 * **대략적인 대기 시간:** 로컬 영역(DAL, AMS, MEL와 같이 동일한 세 개의 문자로 된 접두부가 있는 데이터 센터) 내에서 대기 시간은 대략적으로 1.5밀리초입니다.  실시간 P2P(PoP-to-PoP) 위치 대기 시간 측정에 대해서는 http://lg.softlayer.com/을 참조하십시오.

 * **코로케이션 서비스:** 없음.

 * **중복성:** 중복성 설정을 위해 둘 이상의 위치로 IBM Cloud Direct Link 연결이 필요하거나, 보조 XCR이 사용 가능하고 보조 IBM Cloud Direct Link 연결 요청이 있는 위치를 선택해야 합니다.

 * **로컬/글로벌 라우팅 옵션:** 로컬 라우팅 옵션이 기본 라우팅 옵션입니다. Direct Link PoP(예를 들어, DAL, AMS 또는 MEL로 표기됨)과 동일한 마켓 내의 데이터 센터에 액세스할 수 있습니다. 인마켓 IBM Cloud 리소스를 로컬 마켓 외부의 데이터 센터에 있는 다른 IBM Cloud 리소스에 연결하기 위한 추가 기능으로 글로벌 라우팅 옵션이 필요합니다. IBM Cloud 리소스 간의 워크로드를 공유하는 데 사용됩니다(예: 댈러스와 애슈번 또는 댈러스와 프랑크푸르트).

## IBM Cloud Direct Link Dedicated Hosting 솔루션

IBM Cloud Direct Link Dedicated Hosting 솔루션은 IBM Cloud Direct Link Dedicated와 유사한 연결을 제공하지만, 연결 위치가 {{site.data.keyword.BluSoftlayer_notm}} 데이터 센터에 인접해 있어 고성능의 유스 케이스에 대한 대기 시간을 개선합니다. IBM Cloud는 단순 가격으로 이 솔루션을 통해 사용자 정의할 수 있는 다양한 코로케이션 서비스를 제공합니다.

**공통 유스 케이스:** _비표준 컴퓨팅 기술에 대한 작업, 전용 스토리지 요구사항 또는 기존 IT 투자 활용에 가장 적합합니다._

![그림 4](/images/Direct-Link-Dedicated-Hosting.png)

* **종료 위치:** {{site.data.keyword.BluSoftlayer_notm}} 데이터 센터(DC)입니다.

 * **일반적인 배치 시간:** 모든 요구사항이 완료되어 계약이 실행되고 30-60일 이후입니다.

 * **교차 연결 세부사항:** {{site.data.keyword.BluSoftlayer_notm}}는 {{site.data.keyword.BluSoftlayer_notm}} 교차 연결 라우터(XCR) 인프라에서 고객의 코로케이션 환경에 배치의 일부로 1G 또는 10G 파이버 연결을 제공합니다.  코로케이션 서비스가 요청되지 않은 경우(기존 환경이 이미 연결된 경우), {{site.data.keyword.BluSoftlayer_notm}}는 고객 케이지에서 {{site.data.keyword.BluSoftlayer_notm}} CFA 종료 지점으로 실행되는 파이버 이더넷(단일 모드 파이버 전용, 1Gig-LX 또는 10Gig-LR 광학 중 하나)을 주문하기 위해 고객이 사용하는 LOA(Letter of Authorization)를 제공하며, 이는 교차 연결 라우터(XCR) 인프라에 연결됩니다. 매체는 1310nm 주파수 광학이어야 합니다.

 * **포트 속도 옵션:** 1Gbps, 2Gbps, 5Gbps 또는 10Gbps를 선택하십시오.

 * **대략적인 대기 시간:** 로컬 데이터 센터 내에서 대기 시간은 대략 0.5밀리초입니다.

 * **코로케이션 서비스:** 예.

 * **중복성:** {{site.data.keyword.BluSoftlayer_notm}}는 제품의 일부로 두 개의 교차 연결 라우터(XCR)에 대한 연결을 제공합니다. 중복 연결을 설정하려면 고객이 중복성을 획득하기에 적절하다고 생각하는 대로 각 Direct Link 연결에 BGP를 구성해야 합니다. 예에는 _가장 낮은 MED 선호_, _가장 높은 로컬 환경 설정 선호_ 또는 _더 짧은 AS 경로 선호_와 같은 옵션이 포함됩니다.

 * **로컬/글로벌 라우팅 옵션:** 로컬 라우팅 옵션이 기본 라우팅 옵션입니다. Direct Link PoP(예를 들어, DAL, AMS 또는 MEL로 표기됨)과 동일한 마켓 내의 데이터 센터에 액세스할 수 있습니다. 인마켓 IBM Cloud 리소스를 로컬 마켓 외부의 데이터 센터에 있는 다른 IBM Cloud 리소스에 연결하기 위한 추가 기능으로 글로벌 라우팅 옵션이 필요합니다. IBM Cloud 리소스 간의 워크로드를 공유하는 데 사용됩니다(예: 댈러스와 애슈번 또는 댈러스와 프랑크푸르트).
