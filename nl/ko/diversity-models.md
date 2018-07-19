---

copyright:
  years: 2018
lastupdated: "2018-05-30"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Direct Link의 다양성 및 중복성에 대한 모델

이 문서는 중복성 및 다양성 문제와 관련된 일련의 Schematic을 제공하므로 사용자의 요구사항을 충족하기 위한 가장 성공적인 Direct Link 배치를 작성하는 모델을 찾는 데 도움이 될 수 있습니다. Schematic은 복잡도의 증가 레벨 및 각 레벨이 나타내는 Direct Link 오퍼링에 따라 배열됩니다. Direct Link는 본질적으로 XCR의 중복 서비스가 아니며 해당 BGP 스키마를 통해 중복성을 작성하는 것은 고객의 책임입니다. 

## 섹션 1: 다양성을 확보하는 비교적 단순한 구성

이 그룹에 표시된 구성은 모든 자산이 동일한 PoP 및 동일한 글로벌 시장에 있다는 사실에 의존합니다.

**그림 1: 동일한 PoP(AZ가 아님)에 다양성이 있는 Direct Link Exchange**

![동일한 PoP에 다양성이 있는 교환](/images/exchange-diversity-same-pop.png)

**그림 2: 동일한 PoP(AZ가 아님)에 다양성이 있는 Direct Link Connect**

![동일한 PoP에 다양성이 있는 연결](/images/connect-diversity-same-pop.png)

**그림 3: 동일한 PoP(AZ가 아님)에 다양성이 있는 Direct Link Dedicated**

![동일한 PoP에 다양성이 있는 데디케이티드](/images/dedicated-diversity-same-pop.png)

## 섹션 2: AZ 및 글로벌 라우팅 옵션을 포함하는 다양성

이 그룹에 표시된 구성은 로컬 가용성 구역 및 마켓에서 연결하기 위한 옵션을 제공합니다.

### 파트 A: 로컬 가용성 구역(AZ)의 다양성

**그림 4: 로컬 AZ(WDC, DAL, FRA, LON)에 다양성이 있는 Direct Link Exchange**

![로컬 AZ에 다양성이 있는 교환](/images/exchange-diversity-local-az.png)

**그림 5: 로컬 AZ(WDC, DAL, FRA, LON)에 다양성이 있는 Direct Link Connect**

![로컬 AZ에 다양성이 있는 연결](/images/connect-diversity-local-az.png)

**그림 6: 로컬 AZ(WDC, DAL, FRA, LON)에 다양성이 있는 Direct Link Dedicated**

![로컬 AZ에 다양성이 있는 데디케이티드](/images/dedicated-diversity-local-az.png)

### 파트 B: 글로벌 라우팅을 포함하는 여러 로컬 마켓의 다양성

**그림 7: 다양성 및 글로벌 라우팅을 포함하는 Direct Link Connect**

![다양성 및 글로벌 라우팅을 포함하는 연결](/images/connect-diversity-global.png)

**그림 8: 다양성 및 글로벌 라우팅을 포함하는 Direct Link Exchange**

![다양성 및 글로벌 라우팅을 포함하는 교환](/images/exchange-diversity-global.png)

**그림 9: 다양성 및 글로벌 라우팅을 포함하는 Direct Link Dedicated**

![다양성 및 글로벌 라우팅을 포함하는 데디케이티드](/images/dedicated-diversity-global.png)

## ECMP에 대한 자세한 정보

ECMP는 BGP의 기능입니다. 일부 고객이 중복성을 확보하는 방법으로 ECMP를 사용하는 것에 대해 문의했습니다. 그러나 ECMP만으로는 충분하지 않습니다. 이 섹션에서 이유를 설명합니다.

**Q: ECMP가 중복 연결을 얻을 수 있는 방법입니까? 어떤 대안이 있습니까?**

ECMP는 중복 연결을 작성하기 위해서가 아니라 두 개의 링크 간 로드를 밸런싱하도록 디자인되었습니다. IBM Cloud에서 ECMP를 사용하면 두 개의 연결이 모두 동일한 IBM Cloud 교차 연결 라우터(XCR)로 종료되어야 하므로 단일 장애 지점이 됩니다. (즉, ECMP는 동일한 IBM Cloud XCR의 두 개 세션으로만 프로비저닝할 수 있습니다.)

**그림 10: ECMP 프로비저닝**

![ECMP Dedicated 모델](/images/ecmp-without-diversity.png)

### 다양성 및 중복성을 획득하는 방법

고가용성(HA) 또는 전체 중복성을 원하는 경우 동일한 데이터 센터(예: DAL03)의 서로 다른 XCR에 대한 두 개의 링크를 설정하십시오. 그런 다음 필요에 따라 BGP 구성을 사용하여 장애 복구하십시오.

**그림 11: 이중 XCR이 있는 ECMP**

![ECMP 이중 XCR 모델](/images/ecmp-with-diversity.png)
