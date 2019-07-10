---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-01"

keywords: pricing, competition, AWS, Microsoft, Azure, Google, metered, Dedicated, performance, bandwidth, ingress, egress, charges, unmetered, flat rate, apples-to-apples, enterprise, private cloud, costs

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Visão geral de precificação competitiva
{: #competitive-pricing-overview}

As empresas escolhem usar a interconexão de nuvem privada, como o {{site.data.keyword.cloud}} Direct Link por muitas razões, incluindo desempenho de rede superior, requisitos de segurança e privacidade e redução de custos de largura da banda. Embora sua
empresa possa adotar uma arquitetura de rede de interconexão de nuvem privada devido às vantagens de desempenho e
de segurança, a redução associada de custos de rede é uma métrica que claramente favorece o IBM Cloud Direct Link em muitos
cenários de uso. 

## Por que escolher o IBM Cloud Direct Link?
{: #why-choose-ibm-cloud-direct-link}

As taxas padrão da IBM para o Direct Link refletem um valor significativo para os clientes que usam recursos em nuvem ativamente. Esse fato é confirmado no cálculo do TCO para um Direct Link com relação à sua concorrência.

Uma conexão Direct Link dedicada de 10 Gbps atualmente é precificada em US$ 4.999 na América do Norte. Essa oferta
concede ingresso e egresso ilimitados para os recursos do IBM Cloud em toda a conexão. O Direct Link não tem uma
opção medida.

As comparações a seguir refletem o ponto de mudança com relação a exemplos hipotéticos. A tabela no final deste artigo
mostra um resumo detalhado dessa comparação de preço por região geográfica.

## Empresa A
{: #company-a}

A Empresa "A" oferece uma oferta medida que se presta a Ingress barato, mas precificação variável significativa no Egress.
* A precificação de 10 Gbps da Empresa “A” é composta de horas de porta a um encargo contínuo mensal (MRC) de US$ 1.620 mais uma taxa de transferência de US$ 0,02/GB no egresso (na América do Norte).
* Para uma perspectiva de apples-to-apples para o IBM Cloud Direct Link Dedicated, uma conexão de 10 Gbps equivalente do Direct Link da Empresa “A” a um uso de 5% (ou 170 TB) com egresso me um mês custaria a um cliente US$ 5.020, versus US$ 4.999 para uma conexão de 10 Gbps do Direct Link. Qualquer egresso de dados acima de 5% (ou 170 TB) em um mês, favoreceria o modelo de precificação de
taxa fixa do Direct Link.
* Para uma comparação mais dura, supondo 20% de uso (ou 680 TB) de egresso em um mês custaria a um cliente da Empresa “A” US$ 15.220 em um mês determinado vs. US$ 4.999 para uma conexão do Direct Link de 10 Gbps.

## Empresa G
{: #company-g}

A Empresa G oferece uma oferta medida que se presta a Ingress barato, mas precificação variável significativa no Egress.

* A precificação de 10 Gbps da Empresa G é configurada em US$ 1.750 MRC mais uma taxa de transferência de US$ 0,02/GB sobre o egresso (na América do Norte).
* Para uma perspectiva de apples-to-apples para o IBM Cloud Direct Link Dedicated, uma porta de 10 Gbps equivalente do Direct Link da Empresa "G" a 5% de uso, (170TB) de egresso em um mês custaria a um cliente US$ 5.172 versus US$ 4.999 para conexão de 10 Gbps do Direct Link. 
* Qualquer egresso de dados acima de 5% (ou 170 TB) em um mês, favoreceria o modelo de precificação de
taxa fixa do Direct Link.
* Para uma comparação mais dura, supondo 20% de uso (ou 680 TB) de egresso em um mês custaria a um cliente da Empresa “G” US$ 15.330 em um determinado mês vs. US$ 4.999 para uma conexão de 10Gbps do Direct Link.

## Empresa M
{: #company-m}

A Empresa "M" (como a Empresa "A" e a Empresa "G") apresenta uma oferta medida que se empresta ao ingresso barato, mas com precificação significativamente variável no egresso. A Empresa "M" também oferece uma tabela de precificação ilimitada. As
duas opções são comparadas nas próximas seções.

### Medido
{: #metered}

* A precificação de 10 Gbps da Empresa "M" consiste em uma taxa de porta (US$ 5.000 MRC) mais uma taxa de transferência de US$ 0,02/GB no egresso (na América do Norte). Para começar, QUALQUER dado transferido será
mais caro do que o IBM Cloud Direct Link.
* Para uma perspectiva de apples-to-apples para o IBM Cloud Direct Link Dedicated, uma porta de 10 Gbps equivalente do Direct Link da Empresa "M" a um uso de 5% (ou 170TB) com egresso em um mês custaria a um cliente US$ 8.400 versus US$ 4.999 para uma conexão de 10 Gbps do Direct Link. 
* Qualquer egresso de dados acima de 1 TB em um mês favoreceria o modelo de precificação simples do Direct Link.
* Para uma comparação mais dura, supondo 20% de uso (ou 680 TB) com egresso em um mês custaria um cliente da Empresa "M" US$ 22.000 em um mês determinado vs. US$ 4.999 para uma conexão de 10 Gbps do Direct Link.


### Não medido 
{: #unmetered}

* A precificação de 10 Gbps equivalente do Direct Link da Empresa “M” consiste em uma taxa de porta de US$ 51.000 MRC para ingresso e egresso ilimitados.

* Para uma perspectiva equivalente para o IBM Cloud Direct Link Dedicated, esse custo mensal é de US$ 51.000
versus US$ 4.999 para uma conexão Direct Link de 10 Gbps. 

## Tabela de resumo
{: #summary-table}

Conforme necessário, role horizontalmente para visualizar todas as cinco colunas de comparação.

**Notas:**

* **O tamanho de conexão de 10 Gbps é usado para comparação de preço.**
* **O uso é baseado em 2 Gbps sustentados ou 680 TB de transferência de dados por mês.**


| Região | IBM Ilimitado | Empresa “M” Ilimitada | Empresa “M” Medida | Empresa “A” Medida (intra-região) |
|-----|-----|-----|-----|-----|
| EUA | US$ 4.999 | US$ 51.300 | US$ 22.000 | US$ 15.220 |
| TOR/MON/AMS | US$ 5.149 | US$ 51.300 | US$ 22.000 | US$ 15.220 |
| LON/OSL/STO/MEX | US$ 5.349 | US$ 51.300 | US$ 22.000 | US$ 15.220 |
| PAR/FRA/MIL | US$ 5.499 | US$ 51.300 |US$ 22.000 | US$ 15.220 |
| SEO | US$ 5.499 | US$ 51.300 | US$ 39.000 | US$ 30.180 |
| SNG/HKG | US$ 5.699 | US$ 82.000 | US$ 39.000 | US$ 30.180 |
| TÓQ/MEL/SYD | US$ 5.999 |US$ 82.000 | US$ 39.000 | US$ 30.180 |
| CHE | US$ 5.999 |US$ 82.000 | US$ 39.000 | US$ 32.220 | 
| SAO | US$ 5.999 |US$ 82.000 | US$ 99.500 | US$ 76.420 |

## Artigo relacionado
{: #related-article}

[_As informações_, Empresas surpreendidas por contas de nuvem....![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.theinformation.com/articles/as-aws-use-soars-companies-surprised-by-cloud-bills?utm_medium=email&utm_source=cio)
