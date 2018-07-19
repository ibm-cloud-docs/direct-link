---

copyright:
  years: 2017, 2018
lastupdated: "2018-05-11"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Perguntas mais frequentes

Esta seção contém respostas para algumas perguntas mais frequentes sobre o IBM Cloud Direct Link. 

## Como o IBM Cloud Direct Link funciona?
Para cada cliente do Direct Link, a equipe do IBM Cloud designa uma pequena sub-rede privada para
construir uma rede ponto a ponto entre o roteador de conexão
cruzada (XCR) do {{site.data.keyword.BluSoftlayer_notm}}
e o roteador de borda do cliente (CER). Em seguida, o {{site.data.keyword.BluSoftlayer_notm}} e o
cliente configuram o BGP para trocar rotas entre os ambientes. Finalmente,
o {{site.data.keyword.BluSoftlayer_notm}} coloca o cliente em um VRF para permitir a implementação de
rotas não exclusivas para o espaço de endereço privado da rede remota do cliente.

## O IBM Cloud mede a largura da banda de produtos do Direct Link?
Sim. O uso de largura da banda no serviço do Direct Link entre os Clientes e o IBM Cloud é grátis e sem medição, o IBM Cloud mede a largura da banda de saída dos serviços do IBM Cloud para a Internet pública.

## Quando o faturamento começa com o Direct Link?
As taxas para o Direct Link Connect cobrem o custo de rescisão do serviço na infraestrutura do IBM Cloud. 

Os Serviços de Infraestrutura são faturados antecipadamente e começam na aceitação do pedido de nosso cliente; no entanto, devido à natureza do IBM Cloud Direct Link, o faturamento do serviço do Direct Link começa quando uma sessão do Border Gateway Protocol (BGP) é estabelecida com o IBM Cloud, ou 30 dias após a chave de serviço ser fornecida para o cliente. 

O faturamento para depois que (1) um cliente solicita que um circuito seja excluído E (2) o Provedor Connect ou o Network Service Provider tenha desprovisionado o circuito.

## Que encargos adicionais incorrerão de outras partes com o Direct Link?
É possível que você tenha encargos adicionais do provedor de troca ou do provedor de serviços de rede. Consulte seu(s) provedor(es) para obter informações sobre taxas.

## Como posso atingir a redundância com o IBM Cloud Direct Link?
O Direct Link não fornece um serviço inerentemente redundante. O Direct Link pode fornecer conexões Diversas, que permitem que os clientes criem redundância via BGP. É possível obter a diversidade com o Direct Link conectando-se a mais de um provedor IBM Cloud Direct Link Dedicated ou provedor Exchange para {{site.data.keyword.BluSoftlayer_notm}}. Como alternativa, com o Exchange e o Connect, é possível alavancar diferentes NNIs com os provedores do IBM Cloud Direct Link.

## Qual é a diferença entre o roteamento "local" padrão e o complemento Global Routing?
Com a nossa oferta do Direct Link padrão, é possível enviar o tráfego entre os data centers
em sua região selecionada. Se você precisar de acesso a outros data centers fora da região especificada,
deverá solicitar o complemento Global Routing. Este modelo é baseado em ACLs (listas de controle de acesso)
que são colocadas em vigor no momento em que sua conexão do Direct Link é solicitada. 

## Como o excedente de largura da banda (egresso) de saída é cobrado para o complemento Global Routing?
Os excedentes são cobrados mensalmente quando sua cota de largura da banda é excedida, mas apenas
para a largura da banda de saída. A largura da banda de entrada é gratuita e não é medida. A largura
da banda de saída é cobrada com base na taxa que seja a maior das duas regiões que seus dados cruzam.  Por
exemplo, se seu Direct Link estiver configurado no DAL03 e o seu tráfego de dados passar pelo México, será
cobrada a taxa de largura da banda para o México.

## Por que um pacote de complemento Global Routing existe?
O complemento Global Routing foi incluído para impedir que os clientes tenham custos
de dados inesperados quando atravessar fora de sua região do data center. Ele mantém os custos reduzidos para a
maioria dos nossos clientes e permite que clientes com uma presença global atinjam
todas as regiões ao redor do mundo facilmente. Geralmente, no entanto, um cliente requer apenas um pacote de
largura da banda local.

## Quais são as opções de Roteamento Local e de Global Routing?
As opções de Local Routing e Global Routing são selecionadas por cada cliente ao solicitar o
serviço do Direct Link. Se os clientes precisam rotear o tráfego fora do POP na área em que eles solicitam
o Direct Link, eles devem incluir a opção Global Routing; caso contrário, o tráfego será restrito aos
serviços fornecidos pelo POP local.

Cada mês, todos os clientes que usam circuitos de 1 G recebem 10 TB de tráfego de egresso livre e
os que clientes que usam circuitos 10 G recebem 50 TB. Os excedentes são baseados na tabela a seguir, com a
maior taxa de mercado prevalecendo. Se você selecionar Roteamento Global, não será cobrado por nenhum tráfego local de egresso, somente pelo tráfego que se origina ou finaliza fora do PoP local.

|Dados de Mercado 1|Dados de Mercado 2|Dados de Mercado 3|
|---|---|---|
|<ul><li>DAL</li><li>WDC</li><li>SEA</li><li>SJC</li><li>NYC*</li><li>CHI*</li><li>DEN*</li><li>MIA*</li><li>ATL*</li><li>LAX*</li><li>TOR</li><li>MON</li><li>AMS</li><li>FRA</li></ul>|<ul><li>TOK</li><li>HKG</li><li>PAR</li><li>MIL</li><li>STK*</li><li>OSL</li><li>SNG</li></ul>|<ul><li>MEX</li><li>SAO</li><li>SYD</li><li>MEL</li><li>PER*</li><li>CHE</li><li>SEO</li></ul>|
**Tabela 1: Camadas de utilização**<br/>
As ofertas do Direct Link nos mercados marcados com um asterisco (*) DEVEM solicitar o Global Routing.

## Se eu estiver conectado a um Direct Link Dedicated, Direct Link Connect ou Direct Link Exchange em uma região como Dallas, eu terei acesso a outras regiões nos EUA por meio do Direct Link?
Sim, você é capaz de obter acesso a áreas fora de sua região se você escolher o complemento Global Routing. Se essa opção não for selecionada, o seu tráfego do Direct Link será limitado à região para o local do PoP que você selecionou. Consulte o [documento de precificação](pricing.html) para obter detalhes.

## Posso conectar a qualquer região disponível de um local do Direct Link fornecido?
Sim, desde que você solicite o Direct Link com o complemento Global Routing.

## Posso restringir as regiões que meu Direct Link pode atingir?
Não. O IBM Cloud oferece duas opções: (1) uma região única somente ou (2) todas as regiões, com o
complemento Global Routing.

## E se eu usei o processo de solicitação automatizado para o Equinix Cloud Exchange e me foi designada um sub-rede que
sobrepõe a minha rede interna?

Desde março de 2018, a melhor prática recomendada é cancelar seu pedido automatizado e enviar um novo chamado para preencher o
questionário do Direct Link. É necessário indicar se você prefere outra sub-rede no intervalo 10.254.x.x ou no intervalo
172.32.x.x.

## Qual é a diferença entre Direct Link Exchange e Direct Link Connect?

Esses dois serviços são semelhantes, têm custo relativamente baixo, são tolerantes a latência e têm pontos de entrada rápida
para os benefícios do IBM Cloud Direct Link. Em poucas palavras, o Exchange utiliza provedores de data center e o Connect utiliza
operadoras Telco. Aqui estão alguns detalhes adicionais:

O **Direct Link Exchange** é recomendado para clientes que preferem utilizar uma troca dentro de um data center. Com um serviço do Exchange, os clientes podem ativar a conectividade multinuvem para sua localização conjunta rapidamente, porque os circuitos subjacentes já são provisionados (esses outros provedores em nuvem já devem ter uma interconexão física presente dentro do recurso).

O Direct Link Exchange pode permitir um ambiente de uso multinuvem e compartilhado por meio de uma única porta de troca de nuvem, criada por uma conexão network-to-network (NNI) na Camada 2 entre o IBM Cloud e o Cloud Exchange Service Provider. As velocidades da porta estão disponíveis até 1 Gb.

O **Direct Link Connect** é para clientes que preferem utilizar a rede existente entre sua própria
implementação local e o IBM Cloud. Com um serviço do Direct Link Connect, os clientes podem usar redes de telecomunicações novas e
existentes (como MPLS) para ativar o IBM Cloud rapidamente, aproveitando os circuitos subjacentes fornecidos previamente.

Com o Direct Link Connect, os clientes podem se conectar ao IBM Cloud por meio do provedor Connect, por meio de uma conexão Network to Network (NNI), operada por parceiros da IBM em instalações no mundo todo. As
velocidades da porta estão disponíveis até 5 Gb.

## Podemos suportar o IPv6 sobre o Direct Link?

Não para a Sessão BGP. Temos que designar o nosso /30 do IPv4 e precisamos do mesmo no retorno do cliente.

## Podemos executar o Protocolo da Internet versão 6 na rede privada?

Não. O IPv6 é público apenas.

## Há algum requisito especial para o Verizon SCI? Prefixo / ASN / VLAN BGP / e assim por diante?

O Verizon SCI é um dos vários serviços baseados em MPLS da Camada 3 (VPN de IP). Ele requer que a IBM estabeleça o BGP com a Verizon em vez de diretamente com o cliente. A Verizon, então, estabelece o BGP com o cliente e anuncia rotas de acordo. Vários outros provedores de serviços baseados na Camada 3 participam do programa Direct Link Connect. Os clientes precisam estar cientes do que eles estão ordenando e como sua conta se comportará ao se conectar ao IBM Cloud.

## O Direct Link suporta qualquer tipo de QoS?

Não é possível suportar nenhuma garantia de QoS. O QoS requer o mapeamento do MPLS entre cada um de nossos fornecedores de serviço e o IBM Cloud. Os Provedores de Serviço de Nuvem geralmente não podem suportar o QoS neste momento, porque ele deve ter o alcance de ponta a ponta e envolver todos os dispositivos no meio. Não há solução alternativa disponível por "tunelamento" ou qualquer outro método.

## O Direct Link suporta quadros Jumbo?

Os quadros Jumbo (até 9214 bytes) são suportados no Dedicated e Dedicated Hosting.
O suporte no Connect e no Exchange é teoricamente possível, mas requer que o Provedor de Serviços trabalhe com a IBM e assegure que a conexão de ponta a ponta suporte Quadros Jumbo, incluindo a Network-to Network-Interface (NNI) subjacente.
Por padrão, o Exchange e o Connect são configurados com suporte de MTU de 1500 bytes.

## Com o Direct Link Connect, como um cliente assegura a diversidade do roteador por meio da mesma operadora (exemplo: Verizon em DAL03)?

Nós temos diversos XCRs criando links NNI diferentes para a operadora. Cabe à operadora manter a diversidade a partir desse ponto.

## Para o Direct Link Connect, um cliente precisa pedir 2 links para redundância ou o Direct Link Connect é inerentemente redundante?

Pedir 2 links para a diversidade. Nós não oferecemos redundância entre comutadores ou roteadores. Os clientes criam redundância com suas configurações de BGP em cada Direct Link.

## O quão fácil é fazer upgrade de minha largura da banda de conexão; por exemplo, de 1 GB para 5 GB?

Geralmente, nós instalamos velocidades de 1 G e abaixo em óticas de 1 G. Para velocidades de 2 G a 10 G, nós instalamos as óticas de 10 G. Assim, o upgrade de 1 G para 5 G exigiria que novas óticas fossem designadas ou inseridas. Seria um evento que afeta o serviço. Se você antecipar esse tipo de crescimento, é possível solicitar que fibras óticas de 10 G sejam instaladas no início de sua implementação do Direct Link, ou solicitar o 2 G inicialmente para que as óticas de 10 G existam.

## O ECMP é a maneira de ir para conexões redundantes? Quais alternativas existem?

Observe que o ECMP não se destina a conexões redundantes, mas ao balanceamento da carga sobre os dois links. Com o ECMP, ambas as conexões devem ser finalizadas para o mesmo IBM Cloud Cross-connect Router (XCR), o que o torna um ponto único de falha. (Em outras palavras, o ECMP pode ser provisionado apenas como duas sessões no mesmo IBM Cloud XCR.) 

ECMP é um recurso do BGP. Se você estiver procurando redundância, obtenha duas conexões do Direct Link, uma em cada XCR. Se desejar usar o ECMP e tiver redundância, serão necessárias duas conexões do Direct Link em cada XCR, para que seja possível ter duas sessões de ECMP simultaneamente.

Como alternativa, alguns de nossos clientes configuraram dois links em XCR diferente no mesmo data center, por exemplo, WDC02, em seguida, realizaram failover conforme necessário usando configurações de BGP. Essa configuração é menos redundante (menos segura) do que ter conexões do Direct Link em dois data centers separados, como WDC02 e WDC05.
