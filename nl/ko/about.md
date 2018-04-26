---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-12"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# IBM Cloud Direct Link 정보

이 섹션에서는 네 가지 IBM Cloud Direct Link 오퍼링 각각의 이점 및 주요 기능에 대한 세부사항을 제공합니다.
  * [**IBM Cloud Direct Link 교환**](#the-ibm-cloud-direct-link-exchange-solution)
  * [**IBM Cloud Direct Link 연결**](#the-ibm-cloud-direct-link-connect-solution)
  * [**IBM Cloud Direct Link 데디케이티드**](#the-ibm-cloud-direct-link-dedicated-solution)
  * [**IBM Cloud Direct Link 데디케이티드 호스팅**](#the-ibm-cloud-direct-link-dedicated-hosting-solution)

## IBM Cloud Direct Link 교환 솔루션

IBM Cloud Direct Link 교환 솔루션을 사용하면 고객이 클라우드 교환 제공자를 활용하여 {{site.data.keyword.BluSoftlayer_notm}}에 연결할 수 있습니다. {{site.data.keyword.BluSoftlayer_notm}}에서 클라우드 교환 제공자로의 실제 연결이 이미 이루어져서, 다른 고객들 간에 공유되고 있기 때문에 이 오퍼링은 일반적으로 절감된 비용으로 연결을 제공합니다.

**공통 유스 케이스:** _하이브리드 워크로드, 교차 제공자 워크로드, 대형 또는 빈번한 데이터 전송, 개인용 워크로드 및 환경 관리에 가장 적합합니다.  일반적으로 이 옵션은 원하는 PoP에 이미 원하는 IBM Cloud Direct Link 교환 제공자가 있는 경우에 선택됩니다._

![그림 1](/images/Direct-Link-Exchange.PNG)

 * **종료 위치:** {{site.data.keyword.BluSoftlayer_notm}} PoP(Point of Presence)입니다.

 * **일반 배치 시간:** Equinix 제공자의 경우 일반 배치 시간은 수 시간이 걸립니다. 다른 제공자의 경우에는 회선이 교환에 도달하고 5 - 10일 후이며 사용자의 위치와 요구사항에 따라 전체적으로 30 - 60일이 걸릴 수도 있습니다.

 * **교차 연결 세부사항:** 클라우드 교환 상호 연결을 위한 실제 교차 연결은 {{site.data.keyword.BluSoftlayer_notm}}와 클라우드 교환 제공자 사이에서 유지보수됩니다. 고객이 클라우드 교환 제공자에 상호 연결되면 클라우드 교환 제공자로부터 "가상 회선"을 요청하고, {{site.data.keyword.BluSoftlayer_notm}}에 논리 연결을 설정합니다.

 * **포트 속도 옵션:** 50Mbps, 100Mbps, 200Mbps, 500Mbps 또는 1Gbps를 선택하십시오.

 * **대략적인 대기 시간:** 로컬 영역(DAL, AMS, MEL 등과 같은 세 개의 문자로 된 접두부가 있는 데이터 센터) 내에서 대기 시간은 대략 1.5밀리초입니다. 라이브 P2P(PoP-to-PoP) 대기 시간 측정에 대해서는 http://lg.softlayer.com/ 을 참조하십시오.

 * **코로케이션 서비스:** 없음.

 * **중복성:** IBM Cloud Direct Link 교환에 대한 중복성을 설정하려면 둘 이상의 위치에 연결이 필요하거나, 클라우드 교환 제공자가 활용할 수 있는 보조 XCR이 사용 가능한 위치를 선택해야 합니다.

 * **로컬/글로벌 라우팅 옵션:** 로컬 라우팅 옵션은 PoP(DAL, AMS, MEL 등)와 같은 세 개의 문자로 된 접두부가 있는 데이터 센터에 대한 액세스를 제공합니다. 해당 위치 외부의 데이터 센터에 연결하기 위한 추가 기능으로 글로벌 라우팅 옵션이 필요합니다.
 
## IBM Cloud Direct Link 연결 솔루션

**공통 유스 케이스** Direct Link 교환 솔루션과 유사합니다. 추가 속도 옵션을 제공합니다. 저비용의 시작점입니다.

![그림 2](/images/Direct-Link-Connect.PNG)

* **종료 위치:** {{site.data.keyword.BluSoftlayer_notm}} PoP(Point of Presence)입니다.

* **일반적인 배치 시간:** 회선이 교환에 도달하고 5-10일 이후입니다. 배치 시간은 사용자의 위치와 요구사항에 따라 전체 30-60일이 걸릴 수도 있습니다.

* **교차 연결 세부사항:** 클라우드 연결의 상호 연결을 위한 실제 교차 연결은 {{site.data.keyword.BluSoftlayer_notm}}와 클라우드 연결 제공자 사이에서 유지보수됩니다. 고객이 클라우드 연결 제공자에 상호 연결되면 클라우드 연결 제공자로부터 "가상 회선"을 요청하고 {{site.data.keyword.BluSoftlayer_notm}}에 논리 연결을 설정합니다.

* **포트 속도 옵션:** 50Mbps, 100Mbps, 200Mbps, 500Mbps, 1Gbps, 2Gbps 또는 5Gbps를 선택하십시오.

* **대략적인 대기 시간:** 로컬 영역(DAL, AMS, MEL 등과 같은 세 개의 문자로 된 접두부가 있는 데이터 센터) 내에서 대기 시간은 대략 1.5밀리초입니다. 라이브 P2P(PoP-to-PoP) 대기 시간 측정에 대해서는 http://lg.softlayer.com/ 을 참조하십시오.

* **코로케이션 서비스:** 없음.

* **중복성:** IBM Cloud Direct Link 연결에 대한 중복성을 설정하려면 둘 이상의 위치에 연결이 필요하거나 클라우드 연결 제공자가 활용할 수 있는 보조 XCR이 사용 가능한 위치를 선택해야 합니다.

* **로컬/글로벌 라우팅 옵션:** 로컬 라우팅 옵션은 PoP(DAL, AMS, MEL 등)와 같은 세 개의 문자로 된 접두부가 있는 데이터 센터에 대한 액세스를 제공합니다. 해당 위치 외부의 데이터 센터에 연결하기 위한 추가 기능으로 글로벌 라우팅 옵션이 필요합니다.

## IBM Cloud Direct Link 데디케이티드 솔루션

IBM Cloud Direct Link 데디케이티드 솔루션을 사용하면 고객이 자신의 {{site.data.keyword.BluSoftlayer_notm}} 사설 네트워크에 대한 데디케이티드 단일 모드의 파이버 교차 연결을 종료할 수 있습니다.

 **공통 유스 케이스:** _하이브리드 워크로드, 교차 제공자 워크로드, 대형 또는 빈번한 데이터 전송, 개인용 워크로드 및 환경 관리에 대한 작업에 가장 적합합니다.  이 옵션은 일반적으로 다음과 같은 경우에 선택됩니다. (1) 원하는 PoP에 원하는 IBM Cloud Direct Link 교환 제공자가 없는 경우, (2) 많은 처리량을 필요로 하는 고성능 워크로드를 위한 경우, (3) IBM Cloud Direct Link 교환 구현 모델로 충족되지 않는 정부 규제 준수를 위한 경우._

![그림 3](/images/Direct-link-Dedicated.PNG)

 * **종료 위치:** {{site.data.keyword.BluSoftlayer_notm}} PoP(Point of Presence)입니다.

 * **일반적인 배치 시간:** 새 회선이 POP에 도달하고 10-15 영업일 이후입니다. 배치 시간은 사용자의 위치와 요구사항에 따라 전체 30-60일이 걸릴 수도 있습니다.

 * **교차 연결 세부사항:** {{site.data.keyword.BluSoftlayer_notm}}는 고객 케이지 또는 제공자에서 {{site.data.keyword.BluSoftlayer_notm}} CFA 종료 지점으로 실행되는 파이버 이더넷(단일 모드 파이버 전용, 1Gig-LX 또는 10Gig-LR 광학 중 하나)을 주문하기 위해 고객이 사용하는 LOA(Letter of Authorization)를 제공하며, 이는 교차 연결 라우터(XCR) 인프라에 연결됩니다. 매체는 1310nm 주파수 광학이어야 합니다.

 * **포트 속도 옵션:** 1Gbps, 2Gbps, 5Gbps 또는 10Gbps를 선택하십시오.

 * **대략적인 대기 시간:** 로컬 영역(DAL, AMS, MEL 등과 같은 세 개의 문자로 된 접두부가 있는 데이터 센터) 내에서 대기 시간은 대략 1.5밀리초입니다.  라이브 P2P(PoP-to-PoP) 대기 시간 측정에 대해서는 http://lg.softlayer.com/ 을 참조하십시오.

 * **코로케이션 서비스:** 없음.

 * **중복성:** 중복성 설정을 위해 둘 이상의 위치로 IBM Cloud Direct Link 연결이 필요하거나, 보조 XCR이 사용 가능하고 보조 IBM Cloud Direct Link 연결 요청이 있는 위치를 선택해야 합니다.

 * **로컬/글로벌 라우팅 옵션:** 로컬 라우팅 옵션은 PoP(DAL, AMS, MEL 등)와 같은 세 개의 문자로 된 접두부가 있는 데이터 센터에 대한 액세스를 제공합니다. 해당 위치 외부의 데이터 센터에 연결하기 위한 추가 기능으로 글로벌 라우팅 옵션이 필요합니다.

## IBM Cloud Direct Link 데디케이티드 호스팅 솔루션

IBM Cloud Direct Link 데디케이티드 호스팅 솔루션은 IBM Cloud Direct Link 데디케이티드와 유사한 연결을 제공하지만, 연결 위치가 {{site.data.keyword.BluSoftlayer_notm}} 데이터 센터에 인접해 있어 고성능의 유스 케이스에 대한 대기 시간을 개선합니다. IBM 클라우드는 이 솔루션으로 사용자 정의할 수 있는 코로케이션 서비스를 다양하게 제공합니다.

**공통 유스 케이스:** _비표준 컴퓨팅 기술에 대한 작업, 전용 스토리지 요구사항 또는 기존 IT 투자 활용에 가장 적합합니다._

![그림 4](/images/Direct-Link-Dedicated-Hosting.png)

* **종료 위치:** {{site.data.keyword.BluSoftlayer_notm}} 데이터 센터(DC)입니다.

 * **일반적인 배치 시간:** 모든 요구사항이 완료되어 계약이 실행되고 30-60일 이후입니다.

 * **교차 연결 세부사항:** {{site.data.keyword.BluSoftlayer_notm}}는 {{site.data.keyword.BluSoftlayer_notm}} 교차 연결 라우터(XCR) 인프라에서 고객의 코로케이션 환경에 배치의 일부로 1G 또는 10G 파이버 연결을 제공합니다. 코로케이션 서비스가 요청되지 않은 경우(기존 환경이 이미 연결된 경우), {{site.data.keyword.BluSoftlayer_notm}}는 고객 케이지에서 {{site.data.keyword.BluSoftlayer_notm}} CFA 종료 지점으로 실행되는 파이버 이더넷(단일 모드 파이버 전용, 1Gig-LX 또는 10Gig-LR 광학 중 하나)을 주문하기 위해 고객이 사용하는 LOA(Letter of Authorization)를 제공하며, 이는 교차 연결 라우터(XCR) 인프라에 연결됩니다. 매체는 1310nm 주파수 광학이어야 합니다.

 * **포트 속도 옵션:** 1Gbps, 2Gbps, 5Gbps 또는 10Gbps를 선택하십시오.

 * **대략적인 대기 시간:** 로컬 데이터 센터 내에서 대기 시간은 대략 0.5밀리초입니다.

 * **코로케이션 서비스:** 예.

 * **중복성:** {{site.data.keyword.BluSoftlayer_notm}}는 제품의 일부로 두 개의 교차 연결 라우터(XCR)에 대한 연결을 제공합니다. 중복 연결을 설정하기 위해 고객은 동일 비용 다중 경로(ECMP)로 BGP를 구성합니다.

 * **로컬/글로벌 라우팅 옵션:** 로컬 라우팅 옵션은 PoP(DAL, AMS, MEL 등)와 같은 세 개의 문자로 된 접두부가 있는 데이터 센터에 대한 액세스를 제공합니다. 해당 위치 외부의 데이터 센터에 연결하기 위한 추가 기능으로 글로벌 라우팅 옵션이 필요합니다.
