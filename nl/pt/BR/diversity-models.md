---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-19"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Modelos para diversidade e redundância no Direct Link
{: #models-for-diversity-and-redundancy-in-direct-link}

Este documento fornece uma série de esquemas relacionados a problemas de redundância e diversidade, o que pode ajudar a
localizar um modelo para criar a implementação mais bem-sucedida do {{site.data.keyword.cloud}} Direct Link para atender às suas necessidades. Os esquemas são organizados em níveis crescentes de complexidade e também de acordo com a oferta do Direct Link que cada um estiver ilustrando. O
Direct Link não é um serviço inerentemente redundante no roteador de conexão cruzada (XCR). Os clientes têm a
responsabilidade de criar redundância por meio de seus esquemas de Protocolo de Roteamento de Borda (BGP). 

## Seção 1: configurações relativamente simples que atingem a diversidade

As configurações mostradas nesse grupo contam com o fato de que todos os ativos estão localizados no mesmo PoP e no mesmo mercado global.

**Figura 1: Direct Link Exchange com diversidade, no mesmo PoP (não AZ)**

![Exchange com diversidade no mesmo PoP](/images/exchange-diversity-same-pop.png)

**Figura 2: Direct Link Connect com diversidade no mesmo PoP (não AZ)**

![Connect com diversidade no mesmo PoP](/images/connect-diversity-same-pop.png)

**Figura 3: Direct Link Dedicated com diversidade no mesmo PoP (não AZ)**

![Dedicated com diversidade no mesmo PoP](/images/dedicated-diversity-same-pop.png)

## Seção 2: diversidade que inclui as opções de AZs e Roteamento Global

As configurações mostradas nesse grupo oferecem opções para conexão entre zonas de disponibilidade e mercados locais.

### Parte A: diversidade em uma zona de disponibilidade (AZ) local

**Figura 4: Direct Link Exchange com diversidade em uma AZ local (WDC, DAL, FRA, LON)**

![Exchange com diversidade na AZ local](/images/exchange-diversity-local-az.png)

**Figura 5: Direct Link Connect com diversidade em uma AZ local (WDC, DAL, FRA, LON)**

![Connect com diversidade na AZ local](/images/connect-diversity-local-az.png)

**Figura 6: Direct Link Dedicated com diversidade em uma AZ local (WDC, DAL, FRA, LON)**

![Dedicated com diversidade na AZ local](/images/dedicated-diversity-local-az.png)

### Parte B: diversidade em diferentes mercados locais, com o Roteamento Global

**Figura 7: Direct Link Connect com diversidade e Roteamento Global**

![Connect com diversidade e Roteamento Global](/images/connect-diversity-global.png)

**Figura 8: Direct Link Exchange com diversidade e Roteamento Global**

![Exchange com diversidade e Roteamento Global](/images/exchange-diversity-global.png)

**Figura 9: Direct Link Dedicated com diversidade e Roteamento Global**

![Dedicated com diversidade e Roteamento Global](/images/dedicated-diversity-global.png)

## Mais sobre ECMP

ECMP é um recurso do BGP. Alguns clientes nos perguntaram sobre o uso do ECMP como uma forma de obter redundância. No entanto, só o ECMP não é suficiente. Esta seção explica o motivo.

**P: O ECMP é a melhor solução para conexões redundantes? Quais alternativas existem? **

O ECMP não foi projetado para criar conexões redundantes, mas para balancear a carga sobre dois links. Com o ECMP no IBM Cloud, ambas as conexões devem ser finalizadas no mesmo IBM Cloud Cross-connect Router (XCR), o que o torna um ponto único de falha. (Em outras palavras, o ECMP pode ser provisionado apenas como duas sessões no mesmo IBM Cloud XCR.)

** Figura 10: Provisionamento ECMP **

![ECMP Dedicated model](/images/ecmp-without-diversity.png)

### Como alcançar a Diversidade e o Redundância

Se você estiver procurando alta disponibilidade (HA) ou redundância completa: configure dois links em diferentes XCRs no mesmo data center (por exemplo, DAL03). Em seguida, execute failover conforme necessário usando configurações de BGP.

** Figura 11: ECMP com XCRs Duplos **

![ECMP Dual XCR Model](/images/ecmp-with-diversity.png)
