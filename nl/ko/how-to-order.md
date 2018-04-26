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

# IBM Cloud Direct Link 주문

사용자의 요구에 가장 적합한 IBM Cloud Direct Link의 유형을 주문하려고 준비할 때 다음 링크를 따라(또는 이 문서를 스크롤하여) 프로세스에 대한 일반 개요를 볼 수 있습니다. 주문 준비가 되면 일련의 "단계별" 문서에서 전체 주문 프로세스에 대한 단계별 지시사항을 알 수 있습니다.

* [IBM Cloud Direct Link 교환 주문 방법](how-to-order.html#how-to-order-ibm-cloud-direct-link-exchange)
* [IBM Cloud Direct Link 연결 주문 방법](how-to-order.html#how-to-order-ibm-cloud-direct-link-connect)
* [IBM Cloud Direct Link 데디케이티드 주문 방법](how-to-order.html#how-to-order-ibm-cloud-direct-link-dedicated)
* [IBM Cloud Direct Link 데디케이티드 호스팅 주문 방법](how-to-order.html#how-to-order-ibm-cloud-direct-link-dedicated-hosting)

## IBM Cloud Direct Link 교환 주문 방법

 * 적합한 PoP 및 교차 연결을 연관된 클라우드 교환 제공자에 연결하기 위해 네트워크 제공자의 기능을 확인하십시오.
 * [고객 포털 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://control.softlayer.com/)을 사용하여 IBM Cloud Direct Link 교환 요청을 열고 요청된 정보를 완료하십시오. (IBM 영업 엔지니어의 지원을 요청할 수 있습니다.) Equinix 제공자를 사용하는 경우 주문 및 프로비저닝 프로세스가 [완전히 자동화됩니다](cloud-exchange-automation.html).
 * 교환 제공자에게 문의하여 교환에 대한 연결을 조정하십시오.
 * 네트워크 제공자와 교환 제공자 간의 연결을 주문하십시오.
 * 교환 제공자를 통해 "가상 회선"을 주문하고 {{site.data.keyword.BluSoftlayer_notm}} IBM Cloud Direct Link 요청의 티켓 ID를 사용자의 "요청 ID" 또는 "권한 ID"로 참조하십시오.
 * {{site.data.keyword.BluSoftlayer_notm}} 네트워킹 인프라에서 IP 지정은 가상 회선 요청이 완료된 이후 3 영업일 이내에 완료됩니다.

## IBM Cloud Direct Link 연결 주문 방법

 * 적합한 PoP 및 교차 연결을 연관된 연결 제공자에 연결하기 위해 네트워크 제공자의 기능을 확인하십시오.
 * [고객 포털 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://control.softlayer.com/)을 사용하여 IBM Cloud Direct Link 연결 요청을 열고 요청된 정보를 완료하십시오. (IBM 영업 엔지니어의 지원을 요청할 수 있습니다.) 
 * 연결 제공자에게 문의하여 교환에 대한 연결을 조정하십시오.
 * 네트워크 제공자와 연결 제공자 간의 연결을 주문하십시오.
 * 연결 제공자를 통해 "가상 회선"을 주문하고 {{site.data.keyword.BluSoftlayer_notm}} IBM Cloud Direct Link 요청의 티켓 ID를 사용자의 "요청 ID" 또는 "권한 ID"로 참조하십시오.
 * {{site.data.keyword.BluSoftlayer_notm}} 네트워킹 인프라에서 IP 지정은 가상 회선 요청이 완료된 이후 3 영업일 이내에 완료됩니다.

## IBM Cloud Direct Link 데디케이티드 주문 방법

 * 적합한 PoP 및 교차 연결을 {{site.data.keyword.BluSoftlayer_notm}} 환경에 연결하기 위해 네트워크 제공자의 기능을 확인하십시오.
 * IBM Cloud Direct Link 데디케이티드 요청을 열고 요청된 정보를 완료하십시오. (IBM 영업 엔지니어의 지원을 요청할 수 있습니다.)
 * {{site.data.keyword.BluSoftlayer_notm}}는 연결을 위해 LOA(Letter of Authorization)를 제공합니다.
 * 사용자의 회선이 PoP에 연결되었으며 캐리어에 의해 완료되었음을 확인하십시오.
 * LOA에서 {{site.data.keyword.BluSoftlayer_notm}} CFA(Customer Facility Assignment) 정보를 사용하여 교차 연결을 주문하십시오. 완료되려면 일반적으로 2 -10 영업일이 소요됩니다. (이 시간 범위는 설비 벤더 및 고객이 주문을 배치할 때 주문 우선순위의 유형에 따라 달라집니다.) 이 프로세스에는 {{site.data.keyword.BluSoftlayer_notm}} 종료 포트에 패치 설정이 포함됩니다.
 * {{site.data.keyword.BluSoftlayer_notm}}에 {{site.data.keyword.BluSoftlayer_notm}} 포털 티켓의 설비 제공자로부터 교차 연결 완료 통지를 제공하십시오.
 * {{site.data.keyword.BluSoftlayer_notm}}는 완료 통지의 유효성을 확인하고 LOA/CFA에서 교차 연결 라우터(XCR) 및 기타 기어에 패치를 만들도록 주문합니다.
 * {{site.data.keyword.BluSoftlayer_notm}} 네트워킹 인프라에서 IP 지정은 교차 연결이 완료된 이후 3 영업일 이내에 완료됩니다.

## IBM Cloud Direct Link 데디케이티드 호스팅 주문 방법

 * 코로케이션 및 연결 요구사항을 확인하고, 계약 및 기술적인 추가사항을 완료하고 실행하기 위해 IBM 영업 팀과 작업하십시오.
 * {{site.data.keyword.BluSoftlayer_notm}}는 요청된 환경 및 서비스에 대한 코로케이션 제공자로 빌드 주문을 실행합니다. 배치는 일반적으로 빌드 주문이 배치되고 30일 이내에 완료됩니다.
 * 코로케이션 케이지의 빌드가 완료되면 코로케이션 케이지와 {{site.data.keyword.BluSoftlayer_notm}} POD 환경의 XCR 기어 간에 상호 연결하기 위한 프로세스는 3단계에서 시작하는, 이전에 표시된 IBM Cloud Direct Link 데디케이티드 프로세스를 따르게 됩니다.
