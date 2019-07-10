---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-29"

keywords: hybrid, solutions, features, benefits, port speed, cross-connect, use cases, latency, routing, options, colocation

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Sobre o IBM Cloud Direct Link
{: #about-ibm-cloud-direct-link}

Esta seção permite procurar mais detalhes sobre os recursos-chave e os benefícios de cada uma das quatro soluções
do {{site.data.keyword.cloud}} Direct Link.
  * [**IBM Cloud Direct Link Exchange**](#direct-link-exchange-solution)
  * [**IBM Cloud Direct Link Connect**](#direct-link-connect-solution)
  * [**IBM Cloud Direct Link Dedicated**](#direct-link-dedicated-solution)
  * [**IBM Cloud Direct Link Dedicated Hosting**](#direct-link-dedicated-hosting-solution)

## A solução IBM Cloud Direct Link Exchange
{: #direct-link-exchange-solution}

A solução do IBM Cloud Direct Link Exchange permite que os clientes utilizem um provedor do Cloud Exchange para entregar conectividade para os locais do {{site.data.keyword.cloud_notm}}. Essa oferta geralmente fornece conectividade a um custo reduzido, porque a conectividade física do {{site.data.keyword.cloud_notm}} para o Cloud Exchange Provider já está em vigor, compartilhada entre outros clientes.

**Casos de uso comuns:** _melhor para cargas de trabalho híbridas, cargas de trabalho de
provedor cruzado, transferências de dados grandes ou frequentes com largura da banda de alto egresso, cargas de
trabalho privadas e administração do ambiente.  Essa opção geralmente é selecionada quando o local de PoP desejado já tem o provedor IBM Cloud Direct Link Exchange desejado._

![Figura 1](/images/Direct-Link-Exchange.png)

 * **Local de terminação:** ponto de presença (PoP) do {{site.data.keyword.cloud_notm}}.

 * **Tempo de implementação típico:** para provedores Equinix, o tempo de implementação típico será em horas. Para outros provedores, 5 a 10 dias após o circuito atingir a troca. Em geral, o tempo de implementação pode possivelmente ser de 30 a 60 dias, dependendo de sua localização e requisitos ao pedir um circuito de um NSP ou de uma transportadora.

 * **Detalhes de conexão cruzada:** as conexões cruzadas físicas para a interconexão segura do Cloud Exchange são mantidas entre o {{site.data.keyword.cloud_notm}} e o provedor Cloud Exchange. Os clientes solicitam um "Circuito virtual" do Cloud Exchange Provider, que estabelece conectividade lógica para o {{site.data.keyword.cloud_notm}}, uma vez que o cliente está interconectado ao Cloud Exchange Provider.

 * **Opções de velocidade da porta:** selecione 50 Mbps, 100 Mbps, 200 Mbps, 500 Mbps, 1 Gbps, 2 Gbps ou
5 Gbps.

 * **Latência aproximada:** a Latência é de aproximadamente 1,5 m dentro da área local (data centers com o mesmo prefixo de três letras, como DAL, AMS, MEL). Consulte http://lg.softlayer.com/ para ver as medidas de latência de localização de PoP-to-PoP (P2P) em tempo real.

 * **Serviços de colocação IBM:** nenhum.

 * **Redundância:** o {{site.data.keyword.cloud_notm}} fornece conexões para 2 (dois) roteadores de conexão cruzada (XCRs) diversos como parte do produto. Para estabelecer uma conectividade redundante, os clientes devem configurar o BGP em cada conexão do Direct Link conforme preferirem. Exemplos incluem opções como estas: _preferem MED mais baixa_, _preferem preferência local mais alta_ ou _preferem caminhos de AS mais curtos_.

 * **Opções de roteamento local/global:** Roteamento local é a opção de roteamento padrão. Fornece acesso a datacenters no mesmo Mercado que o PoP do link direto (denotado, por exemplo, como DAL, AMS ou MEL). A opção Roteamento global é necessária como um complemento para conectar seus recursos do IBM Cloud a outros recursos do IBM Cloud em data centers fora do mercado local. Ela fornece uma maneira de compartilhar cargas de trabalho entre os recursos do IBM Cloud (por exemplo, Dallas para Ashburn ou Dallas para Frankfurt).
 
## A solução IBM Cloud Direct Link Connect
{: #direct-link-connect-solution}

**Casos de uso comum** _A solução do IBM Cloud Direct Link Connect permite que os clientes alavanquem um provedor de serviços de rede (NSP) para entregar conectividade para os locais do {{site.data.keyword.cloud_notm}}. Esta oferta geralmente fornece conectividade a um custo reduzido, porque a conectividade física do {{site.data.keyword.cloud_notm}} para o Provedor de serviços de rede já está em vigor, compartilhada entre outros clientes._

![Figura 2](/images/Direct-Link-Connect.png)

* **Local de terminação:** ponto de presença (PoP) do {{site.data.keyword.cloud_notm}}.

* **Tempo de implementação típica:** 5 a 10 dias após o circuito atingir a troca. Em geral, o tempo de implementação pode possivelmente ser de 30 a 60 dias, dependendo de sua localização e requisitos ao pedir um circuito de um NSP ou de uma transportadora.

* **Detalhes de conexão cruzada:** conexões cruzadas físicas para a interconexão segura do Direct Link Connect são mantidas entre o {{site.data.keyword.cloud_notm}} e o provedor Connect. Os clientes solicitam um "Circuito virtual" por meio do provedor do Cloud Connect, que estabelece conectividade lógica para o {{site.data.keyword.cloud_notm}}, uma vez que o cliente está interconectado ao provedor do Cloud Connect.

* **Opções de velocidade da porta:** selecione 50 Mbps, 100 Mbps, 200 Mbps, 500 Mbps, 1 Gbps, 2 Gbps ou
5 Gbps.

* **Latência aproximada:** a Latência é de aproximadamente 1,5 m dentro da área local (data centers com o mesmo prefixo de três letras, como DAL, AMS, MEL). Consulte http://lg.softlayer.com/ para ver as medidas de latência de localização de PoP-to-PoP (P2P) em tempo real.

* **Serviços de colocação IBM:** nenhum.

* **Redundância:** o {{site.data.keyword.cloud_notm}} fornece conexões para 2 (dois) roteadores de conexão cruzada (XCRs) diversos como parte do produto. Para estabelecer uma conectividade redundante, os clientes devem configurar o BGP em cada conexão do Direct Link conforme preferirem. Exemplos incluem opções como estas: _preferem MED mais baixa_, _preferem preferência local mais alta_ ou _preferem caminhos de AS mais curtos_.

* **Opções de roteamento local/global:** Roteamento local é a opção de roteamento padrão. Ela fornece acesso a data centers dentro do mesmo mercado que o PoP do Direct Link (indicado, por exemplo, como DAL, AMS ou MEL). A opção Roteamento global é necessária como um complemento para conectar seus recursos do IBM Cloud a outros recursos do IBM Cloud em data centers fora do mercado local. É usado para compartilhar cargas de trabalho entre recursos IBM Cloud (por exemplo, Dallas para Ashburn ou Dallas para Frankfurt).

## A solução IBM Cloud Direct Link Dedicated
{: #direct-link-dedicated-solution}

A solução do IBM Cloud Direct Link Dedicated permite que os clientes finalizem uma conexão cruzada baseada em fibra de locatário único em sua própria conexão de rede privada do {{site.data.keyword.cloud_notm}}. Essa oferta pode ser usada por clientes com recursos de co-locação adjacentes aos PoPs e data centers do IBM Cloud, bem como por provedores de serviços de rede que entregam circuitos para instalações do cliente ou para outros data centers.

 **Casos de uso comuns:** _melhor para trabalhar com cargas de trabalho híbridas,
cargas de trabalho entre provedores, transferências de dados grandes ou frequentes, cargas de trabalho privadas e
administração do ambiente. Essa opção geralmente é selecionada: (1) quando o PoP desejado não tem o provedor de serviços Exchange ou de rede desejado, (2) para cargas de trabalho de alto desempenho que requerem alto rendimento ou (3) para requisitos de conformidade que não podem ser satisfeitos pelo modelo de implementação do IBM Cloud Direct Link Exchange ou do Connect._
 
 **Caso de uso 1: instalação do cliente para o IBM Cloud.**

![Figura 3](/images/Direct-link-Dedicated.png)

**Caso de uso 2: colocação do cliente no IBM Cloud.**

![Figura 3B](/images/dedicated-model-colo.png)

 * **Local de finalização:** {{site.data.keyword.cloud_notm}} ponto de presença (PoP) ou Data center (DC).

 * **Tempo de implementação típica:** 10 a 15 dias úteis após o novo circuito atingir o POP. O tempo de implementação pode possivelmente ser de 30 a 60 dias em geral, dependendo do local e dos requisitos ao pedir um circuito de um NSP ou de uma transportadora.

 * **Detalhes de conexão cruzada:** {{site.data.keyword.cloud_notm}} fornece uma Carta de autorização (LOA) que um cliente usa para pedir fibra Ethernet (Fibra de modo único apenas, óptica de 1Gig-LX ou de 10Gig-LR) que é executada por meio de um compartimento do cliente ou compartimento do provedor para o ponto de terminação {{site.data.keyword.cloud_notm}} CFA, que será amarrado à infraestrutura do roteador de conexão cruzada (XCR). A mídia deve ser uma ótica de comprimento de onda de 1310 nm.

 * **Opções de velocidade da porta:** selecione 1 Gbps, 2 Gbps, 5 Gbps ou 10 Gbps.

 * ** Latência aproximada:** a latência é de aproximadamente 1,5 ms dentro da área local (data centers com o mesmo prefixo de três letras, como DAL, AMS, MEL).  Consulte http://lg.softlayer.com/ para ver as medidas de latência de localização de PoP-to-PoP (P2P) em tempo real.

 * **Serviços de colocação IBM:** nenhum.

 * **Redundância:** o {{site.data.keyword.cloud_notm}} fornece conexões para 2 (dois) roteadores de conexão cruzada (XCRs) diversos como parte do produto. Para estabelecer uma conectividade redundante, os clientes devem configurar o BGP em cada conexão do Direct Link conforme preferirem. Exemplos incluem opções como estas: _preferem MED mais baixa_, _preferem preferência local mais alta_ ou _preferem caminhos de AS mais curtos_.

 * **Opções de roteamento local/global:** Roteamento local é a opção de roteamento padrão. Ela fornece acesso a data centers dentro do mesmo mercado que o PoP do Direct Link (indicado, por exemplo, como DAL, AMS ou MEL). A opção Roteamento global é necessária como um complemento para conectar seus recursos do IBM Cloud a outros recursos do IBM Cloud em data centers fora do mercado local. Ela fornece uma maneira de compartilhar cargas de trabalho entre os recursos do IBM Cloud (por exemplo, Dallas para Ashburn ou Dallas para Frankfurt).

## A solução IBM Cloud Direct Link Dedicated Hosting
{: #direct-link-dedicated-hosting-solution}

A solução do IBM Cloud Direct Link Dedicated Hosting fornece conectividade semelhante ao IBM Cloud Direct Link Dedicated, mas o ponto de conexão é adjacente a um data center do {{site.data.keyword.cloud_notm}}, que melhora a latência para casos de uso de desempenho mais altos. O IBM Cloud oferece uma variedade de serviços de colocação customizáveis com essa solução, com precificação simples.

**Casos de uso comuns:** _melhor para trabalhar com tecnologias de computação
não padrão, para os requisitos de armazenamento dedicado ou para alavancar investimentos de
TI existentes._

![Figura 4](/images/Direct-Link-Dedicated-Hosting.png)

* **Localização da rescisão:** {{site.data.keyword.cloud_notm}} Data Center (DC).

 * **Tempo de implementação típico:** varia de 30 a 60 dias após todos os requisitos
serem finalizados e os contratos executados.

 * **Detalhes de conexão cruzada:** o {{site.data.keyword.cloud_notm}} fornece conexões de fibra 1G ou 10G da infraestrutura do roteador de conexão cruzada (XCR) do {{site.data.keyword.cloud_notm}} para o ambiente de colocação do cliente como parte da implementação. Se os serviços de colocação não forem
solicitados (se os ambientes existentes já estiverem conectados),
o {{site.data.keyword.cloud_notm}}
fornecerá uma Carta de Autorização (LOA) que um cliente usa para solicitar a fibra Ethernet (somente Single-Mode
Fiber, com as óticas de 1 Gig-LX ou 10 Gig-LR) que é executada do compartimento do cliente ao
ponto de rescisão CFA do {{site.data.keyword.cloud_notm}}, que será
ligado à infraestrutura do roteador de conexão cruzada (XCR). A mídia deve ser uma ótica de comprimento de onda de 1310 nm.

 * **Opções de velocidade da porta:** selecione 1 Gbps, 2 Gbps, 5 Gbps ou 10 Gbps.

 * **Latência aproximada:** a latência é de aproximadamente 0,5 ms dentro do data center local.

 * **Serviços de colocação IBM:** sim.

 * **Redundância:** o {{site.data.keyword.cloud_notm}} fornece conexões para 2 (dois) roteadores de conexão cruzada (XCRs) diversos como parte do produto. Para estabelecer uma conectividade redundante, os clientes devem configurar o BGP em cada conexão do Direct Link conforme preferirem. Exemplos incluem opções como estas: _preferem MED mais baixa_, _preferem preferência local mais alta_ ou _preferem caminhos de AS mais curtos_.

 * **Opções de roteamento local/global:** Roteamento local é a opção de roteamento padrão. Fornece acesso a datacenters no mesmo Mercado que o PoP do link direto (denotado, por exemplo, como DAL, AMS ou MEL). A opção Roteamento global é necessária como um complemento para conectar seus recursos do IBM Cloud a outros recursos do IBM Cloud em data centers fora do mercado local. É usado para compartilhar cargas de trabalho entre recursos IBM Cloud (por exemplo, Dallas para Ashburn ou Dallas para Frankfurt).
