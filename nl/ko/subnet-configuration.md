---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-24"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# IBM Cloud Direct Link 구성

IBM Cloud Direct Link 연결이 설정되었으면 이 문서에 제공된 단계를 따라서 IBM Cloud와 상호작용하기 위한 서브넷을 구성할 수 있습니다.

일반적으로 IBM Cloud Direct Link 연결이 작동하게 하려면 기본 네트워크 구성 단계를 수행한 후에 BGP(Border Gateway Protocol)를 설정해야 합니다. 설정 프로세스 중에는 사용자의 네트워크가 필수인 VRF(Virtual Routing Function) 기능을 사용할 수 있게 하기 위해 IBM 엔지니어가 사용자와 함께 작업합니다.

## 기본 네트워크 구성

1. 표준 RFC1918 사설 주소 공간을 사용하여 원격 네트워크를 정의하십시오. 
 * 새 환경의 경우, 10.0.0.0/8 공간을 사용하지 **않도록** 권장됩니다. 
 * 10.0.0.0/8을 이용하는 기존 환경의 경우, {{site.data.keyword.BluSoftlayer_notm}} 서비스 네트워크 또는 사용자의 계정에 이미 지정된 네트워크와 충돌이 없음을 확인하기 위해 더 세부적인 평가를 확보하기를 권장합니다.

2. {{site.data.keyword.BluSoftlayer_notm}}에서 우리 직원이 각 연결에 대해 /31 또는 /30을 지정하고 {{site.data.keyword.BluSoftlayer_notm}} 교차 연결 라우터(XCR) 인프라에서 인터페이스 IP 주소를 구성합니다.  

3. 우리가 제공한 IP 주소를 사용하여 고객 에지 라우터(CER)에서 인터페이스를 구성하고, {{site.data.keyword.BluSoftlayer_notm}}로 향하는 트래픽에 대한 다음 홉(hop)으로 {{site.data.keyword.BluSoftlayer_notm}} XCR IP를 이용하십시오. 

4. 리턴 트래픽의 경우, {{site.data.keyword.BluSoftlayer_notm}}는 지정된 CER IP를 원격 네트워크로 향하는 트래픽에 대한 다음 홉(hop)으로 BGP를 통해 광고된 대로 이용합니다.

## BGP 구성

사용자의 환경과 라우트 정보를 교환하려면 {{site.data.keyword.BluSoftlayer_notm}}에 BGP가 구성되어야 합니다.  

1. **ASN**: {{site.data.keyword.BluSoftlayer_notm}}는 각 고객이 사용하기 위한 사설 ASN을 지정합니다. 또는 사용자 고유의 공용 ASN을 이용할 수 있습니다. 주문이 배치될 때 참조가 요청됩니다. 지정된 사설 ASN이 구현 프로세스 중에 사용자에게 제공됩니다.

2. **VRF**: VRF를 사용하여 {{site.data.keyword.BluSoftlayer_notm}}는 사용자의 고객 계정에 지정된 특정 사설 서브넷을 광고합니다.  {{site.data.keyword.BluSoftlayer_notm}} 사설 네트워크에서 연결할 수 있기를 바라는 원격 네트워크를 광고해야 합니다. 다음 네트워크가 필터링되어 허용되지 않습니다. 0.0.0.0, 10.0.0.0/14, 10.198.0.0/15, 10.200.0.0/14, 169.254.0.0/16, 224.0.0.0/4. 고객으로서 IBM Cloud 네트워크를 오가는 광고를 관리하는 것이 사용자의 책임입니다. (VRF에 대한 추가 세부사항이 다음 섹션에 포함되어 있습니다.)

3. **ECMP**: 지원되는 위치에서 중복성을 빌드하도록 선출하는 고객의 경우, {{site.data.keyword.BluSoftlayer_notm}}는 두 개의 링크에서 로드 밸런싱 및 중복성을 제공하기 위한 동일 비용 다중 경로(ECMP)의 구현을 지원합니다. 이 ECMP 설정은 주문 시에 요청해야 합니다.

## IBM Cloud Direct Link에 대한 BGP 사양 

BGP 스펙은 다음과 같습니다.

이전 섹션에 설명된 대로 Direct Link를 통해 라우팅을 관리하려면 BGP가 반드시 필요합니다. Direct Link를 주문하는 계정이 VRF 환경으로 마이그레이션됩니다.

**VLANS 및 VRF에 대한 제한사항:**
 * VRF 환경에서는 계정 간 VLAN 스패닝이 허용되지 않습니다. 
 * IPSEC VPN 서비스가 제한됩니다. 
 
**참고:** VRF는 SSL 또는 PPTP VPN 액세스를 방지하지 않지만 해당 동작이 변경됩니다. VRF가 없으면 하나의 VPN 연결로 계정의 모든 서버를 볼 수 있습니다. VRF를 사용하는 경우 해당 VPN과 연관된 마켓의 리소스에만 액세스할 수 있습니다. 따라서 DAL VPN에 연결하는 경우 DAL 서버에만 연결할 수 있습니다.

고용 및 개인 서비스에 대한 IBM Cloud ASN은 **13884**입니다. 
 * 주문 시 고객용 기본 ASN은 **64999**이지만 고객 요청에 따라 기본값을 변경할 수 있습니다. 
 * 선택적으로 4201000000 - 4201064511 사이의 4바이트 사설 ASN이 지원될 수 있습니다.
 * IP VPN과 같은 계층 3 서비스와의 Direct Link Connect를 사용 중인 경우 IBM Cloud가 Direct Link Connect 제공자의 ASN을 사용하여 BGP를 설정합니다.
   
**IP 지정에 대한 엄격한 제한사항:**
 * 10.x.x.x 네트워크를 활용하는 경우에는 IBM Cloud 내의 호스트 및 IBM Cloud 서비스 네트워크(`10.0.0.0/14`, `10.198.0.0/15` 및 `10.200.0.0/14`를 차지함)와 겹치지 않아야 합니다.  

 * `169.254.0.0/16`, `224.0.0.0/4` 범위는 연방 시스템에서 허용되지 않으며 IBM 서버에서 거부됩니다.

**권장사항, 기본값 및 제한사항:**

 * IP 겹침이 문제가 되는 경우 터널링(즉, GRE)이 지원되고 권장됩니다.
 * BGP 타이머의 기본값은 `Keepalive:30`, `Holdtime:60`입니다.
 * 기본적으로 인증은 사용 안함으로 설정됩니다.
 * 기본적으로 BGP BFD는 사용 안함으로 설정됩니다.
 * 수신되는(고객 또는 제공자로부터) 최대 접두부 한계는 VRF당 200개입니다.

## 중복성 및 다양성

IBM Cloud Direct Link는 다양성을 제공하며 고객은 BGP 스키마를 통해 중복성을 구현해야 합니다.

중복성에 대해 ECMP를 선택하는 경우, 두 BGP 세션이 동일한 XCR에 있어야 하므로 다양한 라우터를 사용할 수 없게 되고 라우터에 장애가 발생하는 경우 위험에 노출됩니다. 계층 3의 중복성을 획득하지만 라우터 다양성은 잃게 됩니다.

## VRF 사용에 대한 자세한 정보

IBM Cloud Direct Link 솔루션을 이용하는 모든 계정이 VRF로 마이그레이션되어야 합니다. VRF를 사용하여 고객은 사용 가능한 라우트를 자신의 자체 정의한 원격 네트워크에 광고합니다. 이 구성은 {{site.data.keyword.BluSoftlayer_notm}} 네트워크에서 자체 정의한 IP 주소를 이용하도록 허용하지 않습니다.

설정 프로세스 중에 VRF로 마이그레이션이 완료되었습니다. 가동 중단 창(다중 VLAN/위치가 있는 대형 계정의 경우 최대 30분)이 필요하며, 그 동안에 백엔드 네트워크 VLAN이 VRF로 이동하면서 상호 연결을 잃게 됩니다. VRF 마이그레이션은 구현 엔지니어와 함께 스케줄링됩니다.

게이트웨이 어플라이언스가 트래픽 관리를 위해 도입되지 않으면 모든 VLAN이 통신할 수 있기 때문에 VRF가 계정 간 VLAN 스패닝 기능을 포함하는 사용자의 계정에 대한 "VLAN Spanning" 옵션을 제거한다는 점을 참고하십시오. 또한, VRF는 {{site.data.keyword.BluSoftlayer_notm}} VPN 서비스가 {{site.data.keyword.BluSoftlayer_notm}} SSL, PPTP 및 IPSec VPN 서비스와 호환 가능하지 않기 때문에 해당 서비스 사용 기능을 제한합니다.   

대안은 IBM Cloud Direct Link 오퍼링 자체를 사용하여 서버를 관리하거나 여러 유형의 VPN으로 구성할 수 있는 사용자 고유의 VPN 솔루션(예: Vyatta)을 실행하는 것입니다. VRF로 마이그레이션한 후에 SSL VPN은 일반적으로 VPN 연결이 컴퓨팅 VM이 실행 중인 같은 데이터 센터 위치에 작성될 때 작동하지만, 글로벌하게 액세스를 허용하지 않습니다.

## Direct Link와 함께 BYOIP 및 NAT 사용하기
IBM Cloud Direct Link는 [사용자 정의 사설 주소 지정](#custom-private-addressing)에 대한 섹션 아래에서 다루는 특수한 상황을 제외하고 사설 네트워크에서 BYOIP를 제공하지 않습니다. 따라서 {{site.data.keyword.BluSoftlayer_notm}}에서 지정되지 않은 대상 IP 주소가 있는 트래픽은 삭제됩니다. 그러나 고객은 원격 네트워크와 GRE, IPSec 또는 VXLAN을 사용하는 자신의 {{site.data.keyword.BluSoftlayer_notm}} 네트워트 사이의 트래픽을 캡슐화할 수 있습니다.  

일반적으로 BYOIP 환경은 네트워크 게이트웨이(Vyatta) 또는 VMWare NSX 배치의 범위 내에서 구현됩니다. 이 구성은 고객이 {{site.data.keyword.BluSoftlayer_notm}} 측에서 원하는 IP 공간을 사용하고, 터널에서 원격 네트워크로 다시 라우팅할 수 있게 합니다. 이 구성은 {{site.data.keyword.BluSoftlayer_notm}}와 별개로 고객이 관리하고 지원해야 합니다. 또한, 고객이 {{site.data.keyword.BluSoftlayer_notm}}가 서비스에 사용하고 있는 10.x.x.x 블록을 지정하는 경우,이 구성은 {{site.data.keyword.BluSoftlayer_notm}} 서비스 네트워크에 대한 연결을 중단할 수 있습니다. 

또한 이 솔루션을 위해서는 {{site.data.keyword.BluSoftlayer_notm}} 서비스 네트워크와 원격 네트워크에 연결해야 하는 각 호스트에 두 개의 IP 주소가 지정되어야 합니다. 하나는 IBM 10.x.x.x 블록에서 지정되어야 하고 다른 하나는 원격 네트워크 블록에서 지정되어야 합니다. 트래픽이 올바르게 라우트되도록 정적 라우트를 호스트에 설정해야 합니다. {{site.data.keyword.BluSoftlayer_notm}} 호스트(BYOIP)에서 직접 IP 주소를 지정할 수 없게 되며, 본질적으로 {{site.data.keyword.BluSoftlayer_notm}} 네트워크에서 라우트 가능하게 만듭니다. 이 기능을 구현하는 유일한 방법은 이전에 그 개요가 설명되었지만, {{site.data.keyword.BluSoftlayer_notm}}에서 지원되지 않습니다.

또는 고객이 자신의 원격 에지 라우터에 구성된 NAT 테이블에서 사용하기 위한 원격 네트워크 블록을 종종 지정합니다. 이 구성은 양쪽 네트워크와 호환 가능한 네트워크 주소 공간으로 트래픽을 변환하는 동안에 고객이 양쪽 네트워크에 필요한 변경을 제한하도록 허용합니다.

## 사용자 정의 사설 주소 지정

때때로, IBM Cloud Direct Link 온보딩 중에 고객은 이전에 설명한 방법을 사용하여 온프레미스와 {{site.data.keyword.BluSoftlayer_notm}} 사설 네트워크 사이의 IP 주소 지정 충돌을 해결할 수 없습니다. 이 상황이 발생하는 경우, {{site.data.keyword.BluSoftlayer_notm}} 엔지니어링 또는 영업 담당자는 _사용자 정의 사설 주소 지정_(CPA)을 사용하도록 권장할 수 있습니다. CPA와 연관된 추가 비용이 없습니다. 그러나 이 기능에는 사용에 동의하기 전에 사용자가 완전히 이해해야 하는 고유한 요구사항과 제한사항이 있습니다. 이러한 세부사항은 CPA를 권장하는 IBM Cloud 담당자가 사용자에게 제공할 문서에 설명되어 있습니다. 

_키 요구사항_은 사용자 정의 사설 주소 지정이 비어 있는 새 {{site.data.keyword.BluSoftlayer_notm}} 계정과 새 Direct Link 연결에서만 활성화될 수 있다는 것입니다. 기존 리소스를 CPA로 변환 또는 마이그레이션하는 것은 불가능합니다.

사용자 정의 사설 주소 지정은 유효한, 사용자가 선택한 사설 IPv4 주소 범위(10.x.x.x, 192.168.x.x 또는 172.16.x.x)에서 사용자가 {{site.data.keyword.BluSoftlayer_notm}} 서버를 호스트하게 합니다. CPA는 특수한 내부적으로 라우트된 주소 범위 161.26.x.x에서 공통 IBM Cloud 서비스의 서브세트를 제공하며, 사설 IP 주소를 고객이 무료로 사용할 수 있습니다. CPA가 최대 다섯 개의 사설 IP 범위(_CPA 네트워크_라고 함)를 정의할 수 있도록 하는 반면에, 각 Direct Link는 한 개의 CPA 네트워크로만 연결합니다. 추가적인 CPA 네트워크가 계정에 존재하는 경우, Direct Link를 통해 액세스할 수 없습니다.

사용자 정의 사설 주소 지정은 VRF 및 BGP를 활용합니다. 구현 엔지니어가 CPA 관련 세부사항으로 사용자를 지원합니다.
