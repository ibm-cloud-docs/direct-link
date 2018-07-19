---

copyright:
  years: 2018
lastupdated: "2018-06-11"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# IBM Cloud Direct Link Dedicated 질문지

IBM Cloud Direct Link Dedicated Hosting에 대한 요청을 열어 주셔서 감사합니다. 요청을 완료하기 위해 귀하에게 몇 가지 추가 정보를 수집하려고 합니다. 질문지 프로세스 중에 언제든지 엔지니어에게 문의할 수 있습니다. 귀하가 질문지를 완료하면 클라우드 디자인 엔지니어링 팀에서 검토하여 구현을 위해 네트워크 엔지니어링에 에스컬레이션합니다.

## 확인사항

1. 이 질문지에 설명된 요금에는 IBM Cloud 네트워크 인프라에 대한 서비스 종료 비용이 포함됩니다. 캐비닛, 교차 연결 등을 포함한 코로케이션 비용에는 코로케이션 계약의 일부로서 별도로 설명된 월별 및 비반복적 요금이 포함됩니다.

2. IBM Cloud Direct Link Dedicated Hosting은 IBM Cloud 사설 네트워크에 대한 1Gbps 또는 10Gbps 파이버 교차 연결을 제공합니다. 단일 모드 파이버(SMF) 업링크를 지원할 수 있는 라우터 또는 계층 3 스위치를 제공해야 합니다. 배치 시간은 회선 제공자에 따라 다를 수 있으며 이 서비스의 일반 배치 시간은 30 - 60일입니다.

3. Direct Link Dedicated Hosting에서는 VRF(Virtual Routing and Forwarding) 인스턴스를 활용해야 합니다. 이를 통해 고객은 원격 네트워크에서 사용할 고유 원격 IP 주소를 정의할수 있습니다. 그러나 10.x.x.x 네트워크를 활용하는 경우에는 여전히 IBM Cloud 내의 호스트 및 SIBM Cloud 서비스 네트워크(10.0.0.0/14, 10.198.0.0/15 및 10.200.0.0/14)와 겹치지 않아야 한다는 점에 유의해야 합니다. 사용자 계정을 VRF로 전환하려면 각각의 VLAN이 새 구성으로 마이그레이션될 때 사설 네트워크의 가동이 잠시 중단되어야 합니다. 네트워크 엔지니어링 팀에서 사용자와 함께 작업하여 이 활동에 대한 기간을 정의합니다.

4. VRF는 IBM Cloud SSL, PPTP 및 IPsec VPN의 동작을 변경합니다. 이는 일반적으로 액세스되는 컴퓨팅 리소스와 동일한 데이터 센터에 대한 VPN 연결이 설정될 때 작동하지만 글로벌하게 액세스를 허용하지 않습니다. 대안은 Direct Link 자체를 사용하여 서버를 관리하거나 여러 유형의 VPN으로 구성할 수 있는 사용자 고유의 VPN 솔루션(예: Vyatta)을 실행하는 것입니다.  

5. 고객의 원격 네트워크에 대한 라우트를 구현하려면 Direct Link Dedicated Hosting에 호스팅에 BGP가 필요합니다. IBM Cloud는 IBM Cloud에 작성된 광고에 대한 필터를 구현하지 않습니다. IBM Cloud에서 계정에 지정된 모든 사설 서브넷을 광고합니다. 고객이 IBM Cloud에 수신된 광고를 적절히 관리해야 합니다.

6. IBM Cloud는 고객이 중복 연결을 설정할 수 있도록 IBM Cloud의 교차 연결 라우터마다 하나씩 이중 업링크를 제공합니다. 이는 ECMP 기능을 활용하거나 단순히 연결에 가중치를 지정하여 BGP 세션을 통해 고객의 라우터에서 수행됩니다.

7. IBM Cloud 서비스 네트워크는 사용자의 Dedicated Hosting 또는 원격 네트워크에서 직접 액세스할 수 없습니다. 

8. IBM Cloud는 사용자가 IBM Cloud 백본에서 원격 사이트 간에 트래픽을 백홀(back-haul)하도록 허용하지 않습니다. Direct Link 서비스는 원격 네트워크에서 IBM Cloud 인프라와 개인적으로 통신할 수 있도록 디자인되었습니다.

9. IBM Cloud는 로컬 또는 글로벌 라우팅을 사용하는 Direct Link를 제공합니다. 필요한 라우팅 패키지를 확인하고 ibm.biz/DirectLink-Docs 링크에 나열된 해당 패키지와 연관된 대역폭 플랜에 동의하는지 확인하십시오.

10. Direct Link에서 푸시할 트래픽의 양과 이 트래픽을 푸시할 IBM Cloud 데이터 센터를 지정하십시오.

11. IBM Cloud를 통해 코로케이션 서비스를 구매하지 않을 경우 사용자 환경과 IBM Cloud 간의 교차 연결을 주문하고 비용을 지불하는 것은 사용자의 책임입니다. 연결되면 연결 승인과 연결될 위치에 대해 자세히 설명하는 LOA(Letter of Authorization)를 제공합니다.

12. Direct Link에 대한 다음의 가격 책정에 동의하는지 확인하십시오.
 * 1Gbps: _위치 기반 가격 책정_ 
* 2Gbps: _위치 기반 가격 책정_
* 5Gbps: _위치 기반 가격 책정_
* 10Gbps: _위치 기반 가격 책정_
* 선택적 글로벌 라우팅
