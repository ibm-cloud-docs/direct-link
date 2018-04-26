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

Essa seção fornece mais detalhes sobre os principais recursos e benefícios de cada uma das quatro ofertas IBM Cloud Direct
Link.
  * [**IBM Cloud Direct Link Exchange**](#the-ibm-cloud-direct-link-exchange-solution)
  * [**IBM Cloud Direct Link Connect**](#the-ibm-cloud-direct-link-connect-solution)
  * [**IBM Cloud Direct Link Dedicated**](#the-ibm-cloud-direct-link-dedicated-solution)
  * [**IBM Cloud Direct Link Dedicated Hosting**](#the-ibm-cloud-direct-link-dedicated-hosting-solution)

## A solução IBM Cloud Direct Link Exchange

A solução IBM Cloud Direct Link Exchange permite que os clientes utilizem um provedor Cloud Exchange para fornecer
conectividade para {{site.data.keyword.BluSoftlayer_notm}}. Esta oferta
geralmente fornece conectividade a um custo reduzido, já que a conectividade física do
{{site.data.keyword.BluSoftlayer_notm}} com o provedor Cloud Exchange já está em vigor e
compartilhada entre outros clientes.

**Casos de uso comuns:** _melhor para cargas de trabalho híbridas, cargas
de trabalho entre provedores, transferências de dados grandes ou frequentes, cargas de trabalho privadas e
administração do ambiente.  Essa opção geralmente é selecionada quando o PoP desejado já tem o provedor IBM Cloud Direct Link Exchange desejado._

![Figura 1](/images/Direct-Link-Exchange.PNG)

 * **Localização de rescisão:** ponto de presença (PoP) do {{site.data.keyword.BluSoftlayer_notm}}.

 * **Tempo de implementação típico:** para provedor Equinix, o tempo de implementação típico será em
horas. Para outros provedores, 5 a 10 dias após o circuito atingir a troca, e o tempo de implementação pode ser de 30 a 60 dias em
geral, dependendo de sua localização e requisitos.

 * **Detalhes da conexão cruzada:** conexões cruzadas físicas para a interconexão do
Cloud Exchange são mantidas entre o {{site.data.keyword.BluSoftlayer_notm}} e o provedor Cloud Exchange. Os clientes solicitam um "Circuito Virtual" do provedor Cloud Exchange, que estabelece uma conectividade
lógica com o {{site.data.keyword.BluSoftlayer_notm}}, uma vez que eles são interconectados com o
provedor Cloud Exchange.

 * **Opções de velocidade da porta:** selecione 50 Mbps, 100 Mbps, 200 Mbps, 500 Mbps ou 1 Gbps.

 * **Latência aproximada:** a latência é de aproximadamente 1,5 ms dentro da área
local (datacenters com o mesmo prefixo de três letras, como DAL, AMS, MEL, etc.). Consulte http://lg.softlayer.com/ para obter as medidas de latência do PoP-to-PoP (P2P) em tempo real.

 * **Serviços de colocação:** nenhum.

 * **Redundância:** para estabelecer redundância para o IBM Cloud Direct Link Exchange, a conectividade em
mais 2 locais é necessária ou a seleção de um local com um XCR secundário disponível que possa ser utilizado pelo provedor
Cloud Exchange.

 * **Opções de roteamento global/local:** a opção Roteamento local fornece acesso aos data centers com o mesmo prefixo de três letras que o PoP (DAL, AMS, MEL, etc). A opção Roteamento global é necessária como um complemento para atingir os data centers fora desses locais.
 
## A solução IBM Cloud Direct Link Connect

**Casos de uso comuns** Semelhante à solução Direct Link Exchange. Oferece mais opções de velocidade. Um
ponto de entrada de custo mais baixo.

![Figura 2](/images/Direct-Link-Connect.PNG)

* **Localização de rescisão:** ponto de presença (PoP) do {{site.data.keyword.BluSoftlayer_notm}}.

* **Tempo de implementação típico:** varia de 5 a 10 dias depois que o circuito
atinge a troca. O tempo de implementação pode ser de 30 a 60 dias em geral, dependendo de sua localização e dos requisitos.

* **Detalhes da conexão cruzada:** conexões cruzadas físicas para a interconexão do Cloud Connect são
mantidas entre o {{site.data.keyword.BluSoftlayer_notm}} e o provedor Cloud Connect. Os clientes solicitam um "circuito
virtual" do provedor Cloud Connect, que estabelece uma conectividade lógica com o {{site.data.keyword.BluSoftlayer_notm}}, uma
vez que eles são interconectados com o provedor Cloud Connect.

* **Opções de velocidade da porta:** selecione 50 Mbps, 100 Mbps, 200 Mbps, 500 Mbps, 1 Gbps, 2 Gbps ou
5 Gbps.

* **Latência aproximada:** a latência é de aproximadamente 1,5 ms dentro da área
local (datacenters com o mesmo prefixo de três letras, como DAL, AMS, MEL, etc.). Consulte http://lg.softlayer.com/ para obter as medidas de latência do PoP-to-PoP (P2P) em tempo real.

* **Serviços de colocação:** nenhum.

* **Redundância:** para estabelecer redundância para o IBM Cloud Direct Link Connect, a conectividade em
mais 2 locais é necessária ou a seleção de um local com um XCR secundário disponível que possa ser utilizado pelo provedor
Cloud Connect.

* **Opções de roteamento global/local:** a opção Roteamento local fornece acesso aos data centers com o mesmo prefixo de três letras que o PoP (DAL, AMS, MEL, etc). A opção Roteamento global é necessária como um complemento para atingir os data centers fora desses locais.

## A solução IBM Cloud Direct Link Dedicated

A solução IBM Cloud Direct Link Dedicated permite que os clientes finalizem uma conexão cruzada de fibra dedicada em modo
único em sua própria rede privada {{site.data.keyword.BluSoftlayer_notm}}.

 **Casos de uso comuns:** _melhor para trabalhar com cargas de trabalho híbridas,
cargas de trabalho entre provedores, transferências de dados grandes ou frequentes, cargas de trabalho privadas e
administração do ambiente.  Essa opção geralmente é selecionada: (1) quando o PoP desejado não tem o provedor do IBM Cloud Direct
Link Exchange desejado, (2) para cargas de trabalho de alto desempenho que requerem alto rendimento ou (3) para requisitos de
conformidade que não podem ser satisfeitos pelo modelo de implementação do IBM Cloud Direct Link Exchange._

![Figura 3](/images/Direct-link-Dedicated.PNG)

 * **Localização de rescisão:** ponto de presença (PoP) do {{site.data.keyword.BluSoftlayer_notm}}.

 * **Tempo de implementação típico:** varia de 10 a 15 dias úteis depois que o novo
circuito atinge o POP. O tempo de implementação pode ser de 30 a 60 dias em geral, dependendo de sua localização e dos requisitos.

 * **Detalhes da conexão cruzada:** o {{site.data.keyword.BluSoftlayer_notm}}
fornece uma Carta de Autorização (LOA) que um cliente usa para solicitar a fibra Ethernet (somente Single-Mode
Fiber, com as óticas 1Gig-LX ou 10Gig-LR) que é executada de um compartimento ou provedor do cliente para o ponto
de rescisão CFA do
{{site.data.keyword.BluSoftlayer_notm}}, que será ligado à infraestrutura do roteador de conexão
cruzada (XCR). A mídia deve ser uma ótica de comprimento de onda de 1310 nm.

 * **Opções de velocidade da porta:** selecione 1 Gbps, 2 Gbps, 5 Gbps ou 10 Gbps.

 * **Latência aproximada:** a latência é de aproximadamente 1,5 ms dentro da área
local (datacenters com o mesmo prefixo de três letras, como DAL, AMS, MEL, etc.).  Consulte http://lg.softlayer.com/ para obter as medidas de latência do PoP-to-PoP (P2P) em tempo real.

 * **Serviços de colocação:** nenhum.

 * **Redundância:** para estabelecer redundância requer a conectividade do IBM Cloud Direct Link
em mais 2 locais ou a seleção de um local com um XCR secundário disponível e uma segunda solicitação de conexão do IBM Cloud Direct
Link.

 * **Opções de roteamento global/local:** a opção Roteamento local fornece acesso aos data centers com o mesmo prefixo de três letras que o PoP (DAL, AMS, MEL, etc). A opção Roteamento global é necessária como um complemento para atingir os data centers fora desses locais.

## A solução IBM Cloud Direct Link Dedicated Hosting

A solução IBM Cloud Direct Link Dedicated Hosting fornece conectividade similar ao IBM Cloud Direct Link Dedicated,
mas o ponto de conexão é adjacente a um {{site.data.keyword.BluSoftlayer_notm}} Data Center, que melhora a latência para casos de
uso de maior desempenho. O IBM Cloud oferece com esta solução uma variedade de serviços de colocação customizáveis.

**Casos de uso comuns:** _melhor para trabalhar com tecnologias de computação
não padrão, para os requisitos de armazenamento dedicado ou para alavancar investimentos de
TI existentes._

![Figura 4](/images/Direct-Link-Dedicated-Hosting.png)

* **Localização da rescisão:** {{site.data.keyword.BluSoftlayer_notm}} Data Center (DC).

 * **Tempo de implementação típico:** varia de 30 a 60 dias após todos os requisitos
serem finalizados e os contratos executados.

 * **Detalhes da conexão cruzada:** o {{site.data.keyword.BluSoftlayer_notm}} fornece conexões de
fibra de 1 G ou 10 G da infraestrutura do roteador de conexão cruzada (XCR) do {{site.data.keyword.BluSoftlayer_notm}}
para o ambiente de colocação do cliente como parte da implementação. Se os serviços de colocação não forem
solicitados (se os ambientes existentes já estiverem conectados),
o {{site.data.keyword.BluSoftlayer_notm}}
fornecerá uma Carta de Autorização (LOA) que um cliente usa para solicitar a fibra Ethernet (somente Single-Mode
Fiber, com as óticas 1Gig-LX ou 10Gig-LR) que é executada do compartimento do cliente ao
ponto de rescisão CFA do {{site.data.keyword.BluSoftlayer_notm}}, que será
ligado à infraestrutura do roteador de conexão cruzada (XCR). A mídia deve ser uma ótica de comprimento de onda de 1310 nm.

 * **Opções de velocidade da porta:** selecione 1 Gbps, 2 Gbps, 5 Gbps ou 10 Gbps.

 * **Latência aproximada:** a latência é de aproximadamente 0,5 ms dentro do
datacenter local.

 * **Serviços de colocação:** sim.

 * **Redundância:** o {{site.data.keyword.BluSoftlayer_notm}} fornece conexões com dois roteadores
de conexão cruzada (XCRs) como parte do produto. Para estabelecer a conectividade
redundante, os clientes configuram em BGP com caminhos múltiplos de custo igual (ECMP).

 * **Opções de roteamento global/local:** a opção Roteamento local fornece acesso aos data centers com o mesmo prefixo de três letras que o PoP (DAL, AMS, MEL, etc). A opção Roteamento global é necessária como um complemento para atingir os data centers fora desses locais.
