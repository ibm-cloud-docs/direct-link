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

# Direct Link 오퍼링 개요
{: #overview-of-direct-link-offerings}

{{site.data.keyword.cloud}} Direct Link 오퍼링은 외부 소스에서 고객의 IBM Cloud 사설 네트워크로 연결을 제공합니다. Direct Link는 전통적인 사이트 간 VPN 솔루션에 대한 대안으로 볼 수 있으며, 원격 네트워크와 자신의 IBM Cloud 환경 사이에 더욱 지속적이고, 처리량이 더 많은 연결을 필요로 하는 고객을 위해 디자인되었습니다. 다음 네 가지 유형의 연결이 사용 가능합니다.
 
 * **IBM Cloud Direct Link Exchange**를 사용하면 고객이 Exchange 제공자를 활용하여 IBM Cloud에 연결할 수 있습니다. Exchange 제공자는 멀티 테넌트의 고용량 링크(_NNI(Network-to-Network Interfaces)_라고도 함)를 사용하여 {{site.data.keyword.cloud_notm}} 네트워크에 이미 연결되어 있는 코로케이션 또는 데이터 센터 제공자입니다. {{site.data.keyword.cloud_notm}}에서 Exchange 제공자로 실제 연결이 이미 이루어져서 다른 고객들 간에 공유되고 있기 때문에 고객들은 일반적으로 이 제공자에서 가상 회선을 구매할 수 있으며 절감된 비용으로 연결할 수 있습니다.
 
 * **IBM Cloud Direct Link Connect**를 사용하면 고객이 설비 기반 네트워크를 소유하고 운영하는 캐리어 파트너를 통해 연결을 활용할 수 있습니다. Connect 제공자는 멀티 테넌트의 고용량 링크(_NNI(Network-to-Network Interfaces)_라고도 함)를 사용하여 {{site.data.keyword.cloud_notm}} 네트워크에 이미 연결되어 있는 네트워크 서비스 제공자(NSP)입니다. {{site.data.keyword.cloud_notm}}에서 Connect 제공자로 실제 연결이 이미 이루어져서 다른 고객들 간에 공유되고 있기 때문에 고객들은 일반적으로 이 제공자에서 가상 회선을 구매할 수 있으며 절감된 비용으로 연결할 수 있습니다.
 
 * **IBM Cloud Direct Link Dedicated**를 사용하면 고객이 {{site.data.keyword.cloud_notm}} 네트워크에 대한 싱글 테넌트의 파이버 기반 교차 연결을 종료할 수 있습니다. IBM Cloud PoPs 및 데이터 센터와 인접한 코로케이션 프레미스가 있는 고객과 고객 프레미스 또는 다른 데이터 센터에 회선을 제공하는 네트워크 서비스 제공자가 이 오퍼링을 활용할 수 있습니다.
 
 * **IBM Cloud Direct Link Dedicated Hosting**은 {{site.data.keyword.cloud_notm}} Direct Link Dedicated와 유사한 연결을 제공하지만, 연결 위치가 {{site.data.keyword.cloud_notm}} 데이터 센터에 인접해 있어 고성능 유스 케이스에 대한 대기 시간을 개선합니다. {{site.data.keyword.cloud_notm}}는 이 솔루션으로 사용자 정의할 수 있는 다양한 코로케이션 서비스를 제공합니다.
  
{{site.data.keyword.cloud_notm}} Direct Link 서비스는 라우팅된 OSI Layer-3 서비스입니다. 이 서비스는 낮은 대기 시간과 최대 10Gbps의 속도로 {{site.data.keyword.cloud_notm}} 사설 네트워크 백본에 직접 연결을 제공합니다.
이 계층 3 연결을 작성할 때 유연성을 향상시키기 위해 고객이 {{site.data.keyword.cloud_notm}} Direct Link를 통해 다음을 활용할 수 있습니다.
 * 원격 호스트에 대한 이중 IP
 * NAT
 * BYOIP에 대한 터널링
 
 각 오퍼링에 대한 자세한 설명은 [IBM Cloud Direct Link 정보](/docs/infrastructure/direct-link?topic=direct-link-about-ibm-cloud-direct-link)를 참조하십시오.
