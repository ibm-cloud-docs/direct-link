---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-12"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Sobre o IBM Cloud Direct Link

Esta seção permite pesquisar mais detalhes sobre os principais recursos e benefícios de cada uma das quatro soluções do IBM Cloud Direct Link.
  * [**IBM Cloud Direct Link Exchange**](#the-ibm-cloud-direct-link-exchange-solution)
  * [**IBM Cloud Direct Link Connect**](#the-ibm-cloud-direct-link-connect-solution)
  * [**IBM Cloud Direct Link Dedicated**](#the-ibm-cloud-direct-link-dedicated-solution)
  * [**IBM Cloud Direct Link Dedicated Hosting**](#the-ibm-cloud-direct-link-dedicated-hosting-solution)

## A solução IBM Cloud Direct Link Exchange

A solução IBM Cloud Direct Link Exchange permite que os clientes alavanquem um provedor Cloud Exchange para fornecer conectividade com os locais do {{site.data.keyword.BluSoftlayer_notm}}. Esta oferta
geralmente fornece conectividade a um custo reduzido, já que a conectividade física do
{{site.data.keyword.BluSoftlayer_notm}} com o provedor Cloud Exchange já está em vigor e
compartilhada entre outros clientes.

**Casos de uso comuns:** _melhor para cargas de trabalho híbridas, cargas de trabalho de provedor cruzado, transferências de dados grandes ou frequentes com largura da banda de alto egresso, cargas de trabalho privadas e administração do ambiente. Essa opção geralmente é selecionada quando o local de PoP desejado já tem o provedor IBM Cloud Direct Link Exchange desejado._

![Figura 1](/images/Direct-Link-Exchange.png)

 * **Localização de rescisão:** ponto de presença (PoP) do {{site.data.keyword.BluSoftlayer_notm}}.

 * **Tempo de implementação típico:** para provedores Equinix, o tempo de implementação típico será em horas. Para outros provedores, 5 a 10 dias após o circuito atingir a troca. O tempo de implementação pode possivelmente ser de 30 a 60 dias em geral, dependendo do local e dos requisitos ao pedir um circuito de um NSP ou de uma transportadora.

 * **Detalhes de conexão cruzada:** as conexões cruzadas físicas para a interconexão segura do Cloud Exchange são mantidas entre o {{site.data.keyword.BluSoftlayer_notm}} e o provedor Cloud Exchange. Os clientes solicitam um "Circuito Virtual" do provedor Cloud Exchange, que estabelece uma conectividade
lógica com o {{site.data.keyword.BluSoftlayer_notm}}, uma vez que eles são interconectados com o
provedor Cloud Exchange.

 * **Opções de velocidade da porta:** selecione 50 Mbps, 100 Mbps, 200 Mbps, 500 Mbps ou 1 Gbps.

 * **Latência aproximada:** a Latência é de aproximadamente 1,5 m dentro da área local (data centers com o mesmo prefixo de três letras, como DAL, AMS, MEL). Consulte http://lg.softlayer.com/ para ver as medidas de latência de localização de PoP-to-PoP (P2P) em tempo real.

 * **Serviços de colocação:** nenhum.

 * **Redundância:** para estabelecer redundância para o IBM Cloud Direct Link Exchange, a conectividade em
mais 2 locais é necessária ou a seleção de um local com um XCR secundário disponível que possa ser utilizado pelo provedor
Cloud Exchange.

 * **Opções de roteamento local/global:** a opção de roteamento local fornece acesso a data centers com o mesmo prefixo de três letras que o local do PoP (como DAL, AMS, MEL). A opção Roteamento global é necessária como um complemento para atingir os data centers fora desses locais.
 
## A solução IBM Cloud Direct Link Connect

**Casos de uso comuns** Semelhante à solução Direct Link Exchange. Oferece mais opções de velocidade. A solução do Direct Link Cloud Connect fornece um ponto de entrada de custo mais baixo para os clientes de rede do IBM Cloud.

![Figura 2](/images/Direct-Link-Connect.png)

* **Localização de rescisão:** ponto de presença (PoP) do {{site.data.keyword.BluSoftlayer_notm}}.

* **Tempo de implementação típico:** varia de 5 a 10 dias depois que o circuito
atinge a troca. O tempo de implementação pode possivelmente ser de 30 a 60 dias em geral, dependendo do local e dos requisitos ao pedir um circuito de um NSP ou de uma transportadora.

* **Detalhes de conexão cruzada:** conexões cruzadas físicas para a interconexão segura do Direct Link Connect são mantidas entre o {{site.data.keyword.BluSoftlayer_notm}} e o provedor Connect. Os clientes solicitam um "circuito
virtual" do provedor Cloud Connect, que estabelece uma conectividade lógica com o {{site.data.keyword.BluSoftlayer_notm}}, uma
vez que eles são interconectados com o provedor Cloud Connect.

* **Opções de velocidade da porta:** selecione 50 Mbps, 100 Mbps, 200 Mbps, 500 Mbps, 1 Gbps, 2 Gbps ou
5 Gbps.

* **Latência aproximada:** a Latência é de aproximadamente 1,5 m dentro da área local (data centers com o mesmo prefixo de três letras, como DAL, AMS, MEL). Consulte http://lg.softlayer.com/ para ver as medidas de latência de localização de PoP-to-PoP (P2P) em tempo real.

* **Serviços de colocação:** nenhum.

* **Redundância:** para estabelecer redundância para o IBM Cloud Direct Link Connect, é necessária a conectividade em mais de dois locais, ou a seleção de um local com um XCR secundário disponível que pode ser alavancado pelo provedor IBM Cloud Connect.

* **Opções de roteamento local/global:** a opção de roteamento local fornece acesso a data centers com o mesmo prefixo de três letras que o local do PoP (como DAL, AMS, MEL). A opção Roteamento global é necessária como um complemento para atingir os data centers fora desses locais.

## A solução IBM Cloud Direct Link Dedicated

A solução IBM Cloud Direct Link Dedicated permite que os clientes finalizem uma conexão cruzada de fibra dedicada em modo
único em sua própria rede privada {{site.data.keyword.BluSoftlayer_notm}}.

 **Casos de uso comuns:** _melhor para trabalhar com cargas de trabalho híbridas,
cargas de trabalho entre provedores, transferências de dados grandes ou frequentes, cargas de trabalho privadas e
administração do ambiente.  Essa opção geralmente é selecionada: (1) quando o PoP desejado não tem o provedor do IBM Cloud Direct
Link Exchange desejado, (2) para cargas de trabalho de alto desempenho que requerem alto rendimento ou (3) para requisitos de
conformidade que não podem ser satisfeitos pelo modelo de implementação do IBM Cloud Direct Link Exchange._

![Figura 3](/images/Direct-link-Dedicated.png)

 * **Localização de rescisão:** ponto de presença (PoP) do {{site.data.keyword.BluSoftlayer_notm}}.

 * **Tempo de implementação típico:** varia de 10 a 15 dias úteis depois que o novo
circuito atinge o POP. O tempo de implementação pode possivelmente ser de 30 a 60 dias em geral, dependendo do local e dos requisitos ao pedir um circuito de um NSP ou de uma transportadora.

 * **Detalhes da conexão cruzada:** o {{site.data.keyword.BluSoftlayer_notm}}
fornece uma Carta de Autorização (LOA) que um cliente usa para solicitar a fibra Ethernet (somente Single-Mode
Fiber, com as óticas de 1 Gig-LX ou 10 Gig-LR) que é executada de um compartimento ou provedor do cliente para o ponto
de rescisão CFA do
{{site.data.keyword.BluSoftlayer_notm}}, que será ligado à infraestrutura do roteador de conexão
cruzada (XCR). A mídia deve ser uma ótica de comprimento de onda de 1310 nm.

 * **Opções de velocidade da porta:** selecione 1 Gbps, 2 Gbps, 5 Gbps ou 10 Gbps.

 * ** Latência aproximada:** a latência é de aproximadamente 1,5 ms dentro da área local (data centers com o mesmo prefixo de três letras, como DAL, AMS, MEL). Consulte http://lg.softlayer.com/ para ver as medidas de latência de localização de PoP-to-PoP (P2P) em tempo real.

 * **Serviços de colocação:** nenhum.

 * **Redundância:** para estabelecer redundância requer a conectividade do IBM Cloud Direct Link
em mais 2 locais ou a seleção de um local com um XCR secundário disponível e uma segunda solicitação de conexão do IBM Cloud Direct
Link.

 * **Opções de roteamento local/global:** a opção de Roteamento Local fornece acesso a data centers com o mesmo prefixo de três letras que o PoP (como DAL, AMS, MEL). A opção Roteamento global é necessária como um complemento para atingir os data centers fora desses locais.

## A solução IBM Cloud Direct Link Dedicated Hosting

A solução IBM Cloud Direct Link Dedicated Hosting fornece conectividade similar ao IBM Cloud Direct Link Dedicated,
mas o ponto de conexão é adjacente a um {{site.data.keyword.BluSoftlayer_notm}} Data Center, que melhora a latência para casos de
uso de maior desempenho. O IBM Cloud oferece uma variedade de serviços de colocação customizáveis com essa solução, com precificação simples.

**Casos de uso comuns:** _melhor para trabalhar com tecnologias de computação
não padrão, para os requisitos de armazenamento dedicado ou para alavancar investimentos de
TI existentes._

![Figura 4](/images/Direct-Link-Dedicated-Hosting.png)

* **Localização da rescisão:** {{site.data.keyword.BluSoftlayer_notm}} Data Center (DC).

 * **Tempo de implementação típico:** varia de 30 a 60 dias após todos os requisitos
serem finalizados e os contratos executados.

 * **Detalhes da conexão cruzada:** o {{site.data.keyword.BluSoftlayer_notm}} fornece conexões de
fibra de 1 G ou 10 G da infraestrutura do roteador de conexão cruzada (XCR) do {{site.data.keyword.BluSoftlayer_notm}}
para o ambiente de colocação do cliente como parte da implementação.  Se os serviços de colocação não forem
solicitados (se os ambientes existentes já estiverem conectados),
o {{site.data.keyword.BluSoftlayer_notm}}
fornecerá uma Carta de Autorização (LOA) que um cliente usa para solicitar a fibra Ethernet (somente Single-Mode
Fiber, com as óticas de 1 Gig-LX ou 10 Gig-LR) que é executada do compartimento do cliente ao
ponto de rescisão CFA do {{site.data.keyword.BluSoftlayer_notm}}, que será
ligado à infraestrutura do roteador de conexão cruzada (XCR). A mídia deve ser uma ótica de comprimento de onda de 1310 nm.

 * **Opções de velocidade da porta:** selecione 1 Gbps, 2 Gbps, 5 Gbps ou 10 Gbps.

 * **Latência aproximada:** a latência é de aproximadamente 0,5 ms dentro do data center local.

 * **Serviços de colocação:** sim.

 * **Redundância:** o {{site.data.keyword.BluSoftlayer_notm}} fornece conexões com dois roteadores
de conexão cruzada (XCRs) como parte do produto. Para estabelecer a conectividade redundante, os clientes devem configurar o BGP em cada conexão do Direct Link conforme eles se ajustem para obter redundância. Exemplos incluem opções como estas: _preferem MED mais baixa_, _preferem preferência local mais alta_ ou _preferem caminhos de AS mais curtos_.

 * **Opções de roteamento local/global:** a opção de Roteamento Local fornece acesso a data centers com o mesmo prefixo de três letras que o PoP (como DAL, AMS, MEL). A opção Roteamento global é necessária como um complemento para atingir os data centers fora desses locais.
