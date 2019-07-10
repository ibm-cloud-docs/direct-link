---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-02"

keywords: provisioning, Exchange, order, support, ticket, diverse, virtual circuit, parameters, Terms and Conditions

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:note: .note}
{:download: .download}

# IBM Cloud Direct Link Exchange 프로비저닝
{: #provisioning-ibm-cloud-direct-link-exchange}

이 페이지에서는 {{site.data.keyword.cloud}} Direct Link Exchange 서비스를 주문하는 방법에 대해 설명합니다. {{site.data.keyword.cloud_notm}} Direct Link 주문이 Equinix Cloud Exchange에 대한 주문인 경우 서비스 프로비저닝이 완전히 자동화되며, 이는 관련 문서에 설명된 대로 [IBM 지원 티켓을 열지 않고도 IBM Cloud Direct Link 연결(Equinix)을 주문](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix)할 수 있음을 의미합니다.

자동화 기능은 현재 Equinix Cloud Exchange로 제한되어 있습니다. 후속 릴리스에서는 다른 제공자도 자동화를 사용할 수 있습니다.
{:note}

## 전제조건
{: #cloud-exchange-prerequisites}

자동화 기능을 사용하려면 사설 VLAN을 {{site.data.keyword.cloud_notm}} 사설 네트워크의 VRF와 연관시켜야 합니다. 이 요구사항이 충족되지 않으면 고객 포털을 통해 주문할 때 IBM 지원 티켓이 생성됩니다.

 * [Cloud Exchange 주문 방법](#how-to-order-cloud-exchange-no-equinix)
 * [Equinix의 Cloud Exchange 주문 방법](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix)

## Cloud Exchange 주문 방법
{: #how-to-order-cloud-exchange-no-equinix}

IBM Cloud Direct Link Exchange 연결을 프로비저닝하려면 다음 단계를 완료하십시오.

**단계 1:**

[고객 포털 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://cloud.ibm.com/)의 고객 계정에 로그인하십시오.

**단계 2:**

**네트워크** 탭에서 **Direct Link -> Exchange**를 선택하여 기존 IBM Cloud Direct Link 연결(있는 경우)을 표시하는 페이지를 여십시오.

![단계 2](/images/pup_exchange_list.png)

**단계 3:**

페이지의 맨 위에 있는 **Direct Link Exchange 주문** 단추를 클릭하면 IBM Cloud Direct Link Exchange 연결에 대한 구성 매개변수를 입력할 수 있는 주문서가 표시됩니다.

![단계 3](/images/pup_exchange_create_default.png)

**단계 3A:**

선택적으로, 다양한 포트에 액세스할 수 있고 이전에 첫 번째 가상 회선을 프로비저닝한 경우 두 번째 가상 회선을 선택할 수 있는 두 개의 포트를 표시하는 다음과 유사한 화면이 표시됩니다.

![2-port-image](/images/pup_exchange_create_ports.png)

**단계 4:**

주문서에 다음 매개변수를 입력하여 Direct Link를 구성하십시오.
  * IBM Cloud Direct Link 연결 이름을 입력하십시오.
  * 목록에서 IBM Cloud Direct Link 연결을 설정할 위치를 선택하십시오.
  * 목록에서 선호하는 Cloud Exchange 제공자의 이름을 선택하십시오.
  * 연결에 필요한 링크 속도를 선택하십시오.
  * 연결에 필요한 라우팅 옵션을 선택하십시오.
  * BGP 교환에 대한 정보 상자에 제공된 범위의 ASN 번호를 입력하십시오.

**단계 5:**

이러한 값을 선택하거나 입력하면 오른쪽 패널에서 대략적인 월별 요금을 볼 수 있습니다.

![단계 4 - 5](/images/pup_exchange_create_prices.png)

**단계 6.**

입력을 제공할 때 양식 필드의 유효성이 검증됩니다.
"작성" 단추가 사용으로 설정되려면 이용 약관에 **동의**해야 합니다.

**단계 7:**

이용 약관에 동의한 후 주문 시, 서비스 프로비저닝을 계속하기 위해 주문 후 IBM 지원 티켓이 생성됩니다. 주문 후 티켓 번호가 UI에 표시됩니다. 

![단계 NE1](/images/pup_exchange_ticket_notification.png)

**단계 8:**

메시지에서 티켓 번호를 클릭하여 티켓 세부사항을 볼 수 있습니다.

![단계 NE2](/images/pup_exchange_ticket_details.png)
