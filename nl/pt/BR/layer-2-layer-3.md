---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-30"

keywords: layer 2, layer 3, interconnect, partner, multi-cloud, other clouds, BGP, XCR

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Comparando conexões de camada 2 e camada 3 para o Direct Link
{: #comparing-layer-2-layer-3}

O {{site.data.keyword.cloud}} Direct Link aceita as interconexões de parceiro do OSI Camada 2 e Camada 3 por meio de provedores de serviços de rede (NSPs). Alguns provedores de serviços de rede oferecem serviços para ambas as camadas em redes diferentes. No entanto, alguns provedores podem ter escolhido **não** interconectar todas as suas redes no {{site.data.keyword.cloud_notm}}. 

Ao planejar a sua implementação do {{site.data.keyword.cloud_notm}} Direct Link, considere as características associadas às conexões de Camada 2 e Camada 3, para que seja possível criar uma implementação que melhor se adeque às suas necessidades.

## Considerações para conexões de Camada 2
{: #layer-2-networks}

Para cada Circuito virtual baseado na VLAN, que você criará com uma interconexão de parceiro de Camada 2, deve-se configurar e estabelecer uma sessão do BGP entre os seus roteadores no local e o XCR do IBM Cloud. O IBM Cloud fornecerá a você uma designação de IPv4 `/31` para estabelecer uma sessão do BGP com o seu roteador.

* As redes da Camada 2 oferecem opções para conexões simples e únicas entre empresas e o {{site.data.keyword.cloud_notm}}. 
* Os serviços da Camada 2 dependem de VLANs em vez de endereços IP. 
* Os serviços da Camada 2 podem ser de menores custos e latência inferior e eles podem consumir menos sobrecarga do que os serviços da Camada 3. 
* As redes da Camada 2 não impõem restrições nos recursos da Camada 3 que uma empresa pode ativar.

## Considerações para conexões da Camada 3
{: #layer-3-networks}

Para conexões da Camada 3, para cada Circuito virtual, o seu provedor de serviços estabelece uma sessão do BGP entre os XCRs do IBM Cloud e os roteadores de borda do provedor. Você não precisará configurar o BGP com o IBM Cloud para o seu roteador no local, pois o seu provedor de serviços gerenciará a configuração do BGP para o IBM Cloud.

* As redes IP VPN ou AVPN da Camada 3 permitem a conectividade "qualquer uma-para-qualquer uma". 
* As redes da Camada 3 requerem que o provedor de serviços de rede mantenha uma sessão do BGP entre a empresa e o {{site.data.keyword.cloud_notm}}. 
* Determinados provedores de serviços de rede podem restringir determinadas funcionalidades em sua rede ao usar conexões de Camada 3, como pré-anexação de ASN, tunelamento de GRE e assim por diante. Certifique-se de verificar com o seu provedor sobre possíveis restrições.

## Tabela de interconexão de parceiro
{: #partner-interconnection-table}

A tabela a seguir resume o tipo de conexões que cada parceiro do {{site.data.keyword.cloud_notm}} fornece. 

| Parceiros | Tipo de interconexão |  
|-------|-------|
| AT&T NetBond® for Cloud | Camada 3 |
| AT&T Cloud Gateway (anteriormente conhecido como RedFringe)| Camada 3 |
| Bell Canada | Camada 3 | 
| British Telecom | Camada 3  | 
| CenturyLink IP VPN | Camada 3 | 
| Conexões Dinâmicas CenturyLink | Camada 2 | 
| Chefe Telecomm | Camada 2 |
| Colt | Camada 2  | 
| Conectar Console por PCCW | Camada 2 |
| Digital Realty Service Exchange | Camada 2 | 
| Epsilon | Camada 2 | 
| IBM BlueFringe | Camada 3 | 
| Intercloud | Camada 3 |
| Megaport | Camada 2 |
| MWS GNPP | Camada 3 |
| Neutrona | Camada 2 |
| NTT | Camada 3 |
| PacketFabric | Camada 2  |
| Softbank | Camada 3 |
| Redes SES | Camada 2  |
| Tata IZO™ Private Connect  | Camada 3 | 
| Telia | Camada 3 |
| Telstra | Camada 3 |
| Tokai | Camada 2 | 
| Verizon SCI| Camada 3 |
| Link do Zayo Cloud | Camada 2 |
