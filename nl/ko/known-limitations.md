---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-11"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# 알려진 제한사항

먼저 이 섹션에서는 세 개의 IBM Cloud Direct Link 오퍼링에 모두 적용되는 제한사항에 대해 다루며, 그 다음으로 각 오퍼링의 제한사항에 대한 세부사항을 개별적으로 상세히 설명합니다.

## 일반 IBM Cloud Direct Link 제한사항
 * 각 IBM Cloud Direct Link 연결에는 고유 주문이 필요합니다. 다중 연결이 필요한 경우, 각 연결에 대해 IBM Cloud Direct Link 주문을 여십시오.
 * {{site.data.keyword.BluSoftlayer_notm}} 서비스 네트워크는 사용자의 원격 네트워크에서 직접 액세스할 수 없습니다.
 * {{site.data.keyword.BluSoftlayer_notm}}는 고객이 {{site.data.keyword.BluSoftlayer_notm}} 백본에서 자신의 원격 사이트 간에 트래픽을 백홀(back haul)하는 것을 허용하지 않습니다. IBM Cloud Direct Link 제품은 사용자의 원격 네트워크가 {{site.data.keyword.BluSoftlayer_notm}} 인프라와 개인적으로 통신하도록 되어 있습니다.
 * IBM Cloud Direct Link에서는 VRF(Virtual Routing and Forwarding) 인스턴스를 사용해야 합니다.
 * VRF는 {{site.data.keyword.BluSoftlayer_notm}} SSL, PPTP 및 IPSec VPN 서비스와 완전하게 호환 가능하지 않습니다.
 * VRF는 {{site.data.keyword.BluSoftlayer_notm}} 계정 간 VLAN Spanning과 호환 가능하지 않습니다.
 * 고객의 원격 네트워크에 라우트를 설정하려면 IBM Cloud Direct Link에 BGP가 필요합니다.
 * IBM Cloud Direct Link 인프라에 대한 변경은 미국 중부 표준시 오전 8시와 오후 5시 사이에 이루어져야 합니다.
 
## IBM Cloud Direct Link Exchange 및 Direct Link Connect 제한사항
 * 고객은 원격 네트워크에서 POP 접속과 연관된 비용 및 Cloud Exchange 제공자에서 발생한 비용에 대한 책임이 있습니다.
 * {{site.data.keyword.BluSoftlayer_notm}}는 우리의 네트워크 POP에 고객 장비를 같은 위치에 배치하지 않습니다. 고객은 {{site.data.keyword.BluSoftlayer_notm}} 네트워크 PoP가 존재하는 설비에서 장비를 같은 위치에 배치해야 하는지 여부를 판별하려면 자신의 제공자와 함께 작업해야 합니다.
 * Direct Link Cloud Exchange 가용성은 위치에 따라 다양합니다. 고객은 IBM Cloud 계정 관리자에게 문의하여 현재 또는 향후 가용성을 확인할 수 있습니다.
 
## IBM Cloud Direct Link Dedicated 제한사항
 * IBM Cloud Direct Link Dedicated에 대한 {{site.data.keyword.BluSoftlayer_notm}} 요금은 {{site.data.keyword.BluSoftlayer_notm}} 인프라의 포트 종료 비용을 포함합니다. 고객은 원격 네트워크에서 PoP에 접속하기와 PoP 설비 내에서 필요한 교차 연결과 연관된 비용에 대한 책임이 있습니다.  {{site.data.keyword.BluSoftlayer_notm}}는 고객을 위해 교차 연결을 주문하지 않습니다.
 * {{site.data.keyword.BluSoftlayer_notm}}는 우리의 네트워크 POP에 고객 장비를 같은 위치에 배치하지 않습니다. 고객은 {{site.data.keyword.BluSoftlayer_notm}} 네트워크 PoP가 존재하는 설비에서 장비를 같은 위치에 배치해야 하는지 여부를 판별하려면 자신의 제공자와 함께 작업해야 합니다.

## IBM Cloud Direct Link Dedicated Hosting 제한사항
 * IBM Cloud Direct Link Dedicated Hosting에는 {{site.data.keyword.BluSoftlayer_notm}}와 고객 간의 특정 계약이 필요합니다. 이 계약은 제품, 코로케이션 환경의 가격 및 서비스의 기간 약정에 대한 이용 약관에 대해 설명합니다. 6, 9 또는 12개월 계약이 필요합니다.
 * 제공자 연결은 선택한 데이터 센터의 On-Net 제공자로 제한됩니다.
