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

# 단계별: IBM Cloud Direct Link 교환 주문

이 페이지에서는 IBM Cloud Direct Link 교환 서비스를 주문하는 방법에 대해 설명합니다. IBM Cloud Direct Link 주문이 Equinix 클라우드 교환에 대한 주문인 경우 서비스 프로비저닝이 완전히 자동화되며, 이는 IBM 지원 티켓을 열지 않고도 IBM Cloud Direct Link 연결(Equinix)을 주문할 수 있음을 의미합니다.

**(참고: 자동화 기능은 현재 Equinix 클라우드 교환으로 제한되어 있습니다. 후속 릴리스에서는 다른 제공자의 경우에도 자동화가 사용 가능합니다.)**

## 전제조건

자동화 기능을 사용하려면 사설 VLAN을 IBM Cloud 사설 네트워크의 VRF와 연관시켜야 합니다. 이 요구사항이 충족되지 않으면 고객 포털을 통해 주문할 때 IBM 지원 티켓이 생성됩니다.

 * [클라우드 교환 주문 방법](#how-to-order-cloud-exchange)
 * [Equinix의 클라우드 교환 주문 방법](#how-to-order-cloud-exchange-for-equinix)

## 클라우드 교환 주문 방법

IBM Cloud Direct Link 교환 연결을 프로비저닝하려면 다음 단계를 완료하십시오.

**단계 1:**

[고객 포털 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://control.softlayer.com/)의 고객 계정에 로그인하십시오.

**단계 2:**

**네트워크** 탭에서 **Direct Link -> 교환**을 선택하여 기존 IBM Cloud Direct Link 연결(있는 경우)을 표시하는 페이지를 여십시오.

![단계 2](/images/Equinix-Step2.png)

**단계 3:**

페이지의 맨 위에 있는 **Direct Link 교환 주문** 단추를 클릭하면 IBM Cloud Direct Link 교환 연결에 대한 구성 매개변수를 입력할 수 있는 주문서가 표시됩니다.

![단계 3](/images/Equinix-Step3.png)

**단계 4:**

주문서에 다음 매개변수를 입력하여 Direct Link를 구성하십시오.
  * IBM Cloud Direct Link 연결 이름을 입력하십시오.
  * 목록에서 IBM Cloud Direct Link 연결을 설정할 PoP 위치를 선택하십시오.
  * 목록에서 선호하는 클라우드 교환 제공자의 이름을 선택하십시오.
  * 연결에 필요한 링크 속도를 선택하십시오.
  * 연결에 필요한 라우팅 옵션을 선택하십시오.
  * BGP 교환에 대한 정보 상자에 제공된 범위의 ASN 번호를 입력하십시오.

**단계 5:**

이러한 값을 선택하거나 입력하면 왼쪽 패널에서 대략적인 월별 요금을 볼 수 있습니다.

![단계 4 - 5](/images/Equinix-Step4-5.png)

**단계 6.**

입력 값을 제공하면 그 다음 UI 화면에 선택한 옵션에 따른 실제 월별 가격 책정이 표시됩니다.

**단계 7:**

IBM Cloud Direct Link를 주문하려면 먼저 이용 약관에 **동의**해야 합니다. 진행하기 전에 이해해야 하는 중요한 기술 정보가 포함되어 있으므로 이용 약관을 주의 깊게 읽으십시오. **(참고: 이용 약관에 동의하지 않으면 주문 시 IBM 지원 티켓이 생성됩니다.)** 다음 그림에는 이 단계의 선택사항에 따라 볼 수 있는 화면이 표시됩니다.

다음 그림에는 이용 약관 화면이 표시됩니다.

![단계 7](images/Equinix-Step7.png)

다음 그림에는 주문 시 이용 약관에 동의하지 않는 경우 볼 수 있는 화면이 표시됩니다. 생성된 티켓 번호가 화면에 표시됩니다.

![단계 7 동의](/images/Equinix-Step7-NoAgree.png)

다음 그림에는 열린 티켓에 대한 예제가 표시됩니다.

![단계 7 티켓](/images/Equinix-Step7-NoAgree-Ticket.png)

**단계 8:**

이용 약관에 동의한 후 주문 시, 서비스 프로비저닝을 계속하기 위해 주문 후 IBM 지원 티켓이 생성됩니다. 주문 후 티켓 번호가 UI에 표시됩니다. 

![단계 NE1](/images/Non-Equinix-Step1.png)

**단계 9:**

메시지에서 티켓 번호를 클릭하여 티켓 세부사항을 볼 수 있습니다.

![단계 NE2](/images/Non-Equinix-Step2.png)

## Equinix의 클라우드 교환 주문 방법

**단계 1:**

위의 클라우드 교환 주문 단계에서 1 - 7단계를 수행하십시오.

**단계 2:**

주문 후 IBM Cloud Direct Link 프로비저닝이 시작됩니다.

![단계 8](/images/Equinix-Step8.png)

**단계 3:**

주문 후 연결 상태를 볼 수 있습니다. IBM 측에서 구성이 완료되면 상태가 **프로비저닝됨**으로 표시됩니다. 구성이 완료되지 않으면 상태가 **진행 중**으로 표시됩니다. 구성이 실패하면 상태가 **작성 실패**로 표시됩니다. 구성이 완료되었고 BGP 연결이 작동되면 상태가 **UP**으로 표시됩니다.

![단계 9 진행 중](/images/Equinix-Step9-InProgress.png)

다음 그림에는 주문 후의 다양한 연결 상태가 표시됩니다.

![단계 9 작동됨](/images/Equinix-Step9-UP.png)

**단계 4:**

연결이 **프로비저닝됨** 상태인 경우 연결 **이름**의 앞에 있는 **>**를 클릭하여 연결을 확장하십시오. 그런 다음 **고객 IP 주소** 및 **서비스 키** 정보를 기록하십시오. 고객 IP 주소는 고객 에지 라우터를 구성하는 데 필요하며 서비스 키는 클라우드 제공자 측(Equinix) 구성을 위한 권한 키로 필요합니다.

![단계 10](/images/Equinix-Step10-Provisioned.png)

**단계 5:**

**프로비저닝됨** 상태의 연결의 경우 연결 앞에 있는 **>**를 클릭하여 연결을 확장한 후 피어 링크 속도에 불일치가 나타나면 오류 메시지가 표시됩니다. 속도가 IBM 측과 Equinix 측에서 동일하면 이 오류 알림이 더 이상 표시되지 않습니다.

![단계 11](/images/Equinix-Step11-PortMismatch.png)

**단계 6:**

**작성 실패** 상태의 연결의 경우에는 IBM 지원 티켓이 생성되고 추가 세부사항이 지원 티켓을 통해 전달됩니다. 연결을 확장하면 지원 티켓 세부사항을 볼 수 있습니다.

![단계 12](/images/Equinix-Step12-CreateFailed.png)

**단계 7:**

**프로비저닝됨**, **UP** 또는 **DOWN** 상태의 연결에서는 연결 다음에 있는 **조치** 열을 클릭하여 연결을 **삭제**할 수 있습니다.

![단계 13](/images/Equinix-Step13-Delete.png)

**단계 8:**

**작성 실패** 상태의 연결에서는 연결 다음에 있는 **조치** 열을 클릭하여 연결을 **취소**할 수 있습니다.

