---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-02-19"

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

As empresas escolhem usar a interconexão de nuvem privada, como o {{site.data.keyword.cloud}} Direct Link, o
AWS Direct Connect, o Google Cloud Interconnect e o Microsoft Azure ExpressRoute por várias razões, incluindo requisitos
superiores de desempenho de rede, de segurança e de privacidade e a redução de custos de largura da banda. Embora sua
empresa possa adotar uma arquitetura de rede de interconexão de nuvem privada devido às vantagens de desempenho e
de segurança, a redução associada de custos de rede é uma métrica que claramente favorece o IBM Cloud Direct Link em muitos
cenários de uso. 

## Por que escolher o IBM Direct Link?
{: #why-choose-ibm-cloud-direct-link}

As taxas padrão da IBM para o Direct Link refletem um valor significativo para os clientes que usam recursos em nuvem ativamente. Esse fato é confirmado no cálculo do TCO para um Direct Link com relação à sua concorrência.

Uma conexão Direct Link dedicada de 10 Gbps atualmente é precificada em US$ 4.999 na América do Norte. Essa oferta
concede ingresso e egresso ilimitados para os recursos do IBM Cloud em toda a conexão. O Direct Link não tem uma
opção medida.

As comparações a seguir refletem o ponto de mudança com relação à maior concorrência. A tabela no final deste artigo
mostra um resumo detalhado dessa comparação de preço por região geográfica.

## AWS
{ #aws}

A AWS (como o Google e a Microsoft) apresenta uma oferta medida que proporciona ingresso barato, mas
uma precificação significativamente variável no egresso.
* A precificação da AWS de 10 Gbps é composta de horas da porta com encargo contínuo mensal de US$ 1.620 (MRC) mais uma taxa
de transferência de US$ 0,02/GB no egresso (na América do Norte).
* Para uma perspectiva equivalente para o IBM Cloud Direct Link Dedicated, uma conexão AWS Direct Connect
de 10 Gbps a 5% de uso (ou 170 TB) egresso em um mês, custaria ao cliente US$ 5.020, versus US$ 4.999 para uma conexão Direct
Link de 10 Gbps. Qualquer egresso de dados acima de 5% (ou 170 TB) em um mês, favoreceria o modelo de precificação de
taxa fixa do Direct Link.
* Para uma comparação mais clara, supondo que um cliente da AWS tenha 50% de uso (ou 1,7 PB) egresso em um mês,
isso custaria US$ 35.620 versus US$ 4.999 para uma conexão Direct Link de 10 Gbps.

## Google
{: #google}

O Google (como o AWS e a Microsoft) apresenta uma oferta medida que proporciona ingresso barato, mas uma
precificação significantemente variável no egresso.

* A precificação do Google de 10 Gbps é configurada em US$ 1.750 MRC mais uma taxa de transferência de US$ 0,02/GB no
egresso (na América do Norte).
* Para uma perspectiva equivalente para o IBM Cloud Direct Link Dedicated, uma porta do Google Cloud (GCP) de
10 Gbps com 5% de uso (170 TB) egresso em um mês, custaria ao cliente US$ 5.172 versus
US$ 4.999 para a conexão Direct Link de 10 Gbps. 
* Qualquer egresso de dados acima de 5% (ou 170 TB) em um mês, favoreceria o modelo de precificação de taxa fixa do Direct
Link.
* Para uma comparação mais clara, supondo que um cliente do Google tenha 50% de uso (ou 1,7 PB) egresso em um
mês, isso custaria US$ 35.772 versus US$ 4.999 para uma conexão Direct Link de 10 Gbps.

## Microsoft
{ #microsoft}

A Microsoft (como o Google e o AWS) apresenta uma oferta medida que proporciona ingresso barato, mas
precificação significativamente variável no egresso. A Microsoft também oferece uma tabela de precificação ilimitada. As
duas opções são comparadas nas próximas seções.

### Medido
{: #metered}

* A precificação do Microsoft Azure de 10 Gbps consiste em uma taxa de porta (US$ 5.000 MRC) mais uma taxa de
transferência de US$ 0,02/GB no egresso (na América do Norte). Para começar, QUALQUER dado transferido será
mais caro do que o IBM Cloud Direct Link.
* Para uma perspectiva equivalente para o IBM Cloud Direct Link Dedicated, uma porta de 10 Gbps do Microsoft Azure Express
Route a 5% de uso (ou 170 TB) egresso em um mês, custaria ao cliente US$ 8.400 versus US$ 4.999 para uma conexão Direct Link
de 10 Gbps. 
* Qualquer egresso de dados acima de 1 TB em um mês favoreceria o modelo de precificação simples do Direct Link.
* Para uma comparação mais clara, supondo que um cliente do Microsoft Azure tenha 50% de uso (ou 1,7 PB)
egresso em um mês, isso custaria US$ 47.500 versus US$ 4.999 para uma conexão Direct Link de 10 Gbps.


### Não medido 
{: #unmetered}

* A precificação do Microsoft Azure de 10 Gbps consiste em uma taxa de porta de US$ 51.000 MRC para ingresso e egresso
ilimitados.

* Para uma perspectiva equivalente para o IBM Cloud Direct Link Dedicated, esse custo mensal é de US$ 51.000
versus US$ 4.999 para uma conexão Direct Link de 10 Gbps. 

## Tabela de resumo
{: #summary-table}

Conforme necessário, role horizontalmente para visualizar todas as cinco colunas de comparação.

**Notas:**
* **As informações na tabela a seguir foram obtidas de websites públicos dessas empresas.**
* **O tamanho de conexão de 10 Gbps é usado para comparação de preço.**
* **O uso é baseado em 5 Gbps sustentados ou 1,7 PB de transferência de dados por mês.**


| Região | IBM Ilimitado | Azure Ilimitado | Azure Medido | AWS Medido (intrarregião) |
|-----|-----|-----|-----|-----|
| EUA | US$ 4.999 | US$ 51.300 | US$ 47.500 | US$ 35.620 |
| TOR/MON/AMS | US$ 5.149 | US$ 51.300 | US$ 47.500 | US$ 35.620 |
| LON/OSL/STO/MEX | US$ 5.349 | US$ 51.300 | US$ 47.500 | US$ 35.620 |
| PAR/FRA/MIL | US$ 5.499 | US$ 51.300 | US$ 47.500 | US$ 35.620 |
| SEO | US$ 5.499 | US$ 51.300 | US$ 90.000 | US$ 73.020 |
| SNG/HKG | US$ 5.699 | US$ 82.000 | US$ 90.000 | US$ 73.020 |
| TOK | US$ 5.999 |US$ 82.000 | US$ 90.000 | US$ 73.020 |
| MEL/SYD | US$ 5.999 |US$ 82.000 | US$ 90.000 | US$ 73.020 |
| CHE | US$ 5.999 |US$ 82.000 | US$ 90.000 | US$ 78.120 |
| SAO | US$ 5.999 |US$ 82.000 | US$ 242.350 | US$ 188.620 |


