---

copyright:
  years: 2017, 2018
lastupdated: "2018-03-14"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# 기능의 개요

IBM Cloud Direct Link 오퍼링은 외부 소스에서 고객의 IBM Cloud 사설 네트워크로 연결을 제공합니다. Direct Link는 전통적인 사이트 간 VPN 솔루션에 대한 대안으로 볼 수 있으며, 원격 네트워크와 자신의 IBM 클라우드 환경 사이에 더욱 지속적이고, 처리량이 더 많은 연결을 필요로 하는 고객을 위해 디자인되었습니다. 다음 네 가지 유형의 연결이 사용 가능합니다.
 
 * **IBM Cloud Direct Link 교환**을 사용하면 고객이 교환 제공자를 활용하여 IBM Cloud에 연결할 수 있습니다. 교환 제공자는 다중 테넌트의 고용량 링크를 사용하여 IBM Cloud 네트워크에 이미 연결되어 있는 캐리어 또는 네트워크 제공자입니다. {{site.data.keyword.BluSoftlayer_notm}}에서 교환 제공자로 실제 연결이 이미 이루어져서 다른 고객들 간에 공유되고 있기 때문에 고객들은 일반적으로 이 제공자에서 가상 회선을 구매할 수 있으며 절감된 비용으로 연결할 수 있습니다.
 
 * **IBM Cloud Direct Link 연결**을 사용하면 고객이 설비 기반 네트워크를 소유하고 운영하는 파트너를 통한 연결을 활용할 수 있습니다. IBM Cloud Direct Link 연결에서는 IBM과 파트너가 듀얼 계층-2 10G NNI를 통해 계층 2와 3의 고객과 연결됩니다.
 
 * **IBM Cloud Direct Link 데디케이티드**를 사용하면 고객이 자신의 IBM Cloud 사설 네트워크에 대한 데디케이티드 단일 모드의 파이버 교차 연결을 종료할 수 있습니다.
 
 * **IBM Cloud Direct Link 데디케이티드 호스팅**은 IBM Cloud Direct Link 데디케이티드와 유사한 연결을 제공하지만, 연결 위치가 {{site.data.keyword.BluSoftlayer_notm}} 데이터 센터에 인접해 있어 고성능의 유스 케이스에 대한 대기 시간을 개선합니다. IBM 클라우드는 이 솔루션으로 사용자 정의할 수 있는 코로케이션 서비스를 다양하게 제공합니다.
  
IBM Cloud Direct Link 서비스는 라우팅된 OSI Layer-3 서비스입니다. 이 서비스는 낮은 대기 시간과 최대 10Gbps의 속도로 {{site.data.keyword.BluSoftlayer_notm}} 사설 네트워크 백본에 직접 연결을 제공합니다.
이 계층-3 연결 작성에서 유연성을 높이기 위해 IBM Cloud Direct Link에서는 고객이 다음을 이용할 수 있습니다.
 * 원격 호스트에 대한 이중 IP
 * NAT
 * BYOIP에 대한 터널링
