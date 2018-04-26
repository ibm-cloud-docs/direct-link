---

copyright:
 years: 2017, 2018
lastupdated: "2018-04-05"

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
Sim. O IBM Cloud mede toda a largura da banda de saída dos produtos do Direct Link. A largura de banda de
entrada é livre e ilimitada.

## Que encargos adicionais incorrerão de outras partes com o Direct Link?
É possível que você tenha encargos adicionais do provedor de troca ou do provedor de serviços de rede. Consulte seu(s) provedor(es) para obter informações sobre taxas.

## Como posso atingir a redundância com o IBM Cloud Direct Link?
É possível obter redundância com o Direct Link conectando-se a mais de um provedor IBM Cloud Direct Link Dedicated ou
provedor Exchange {{site.data.keyword.BluSoftlayer_notm}}. Como alternativa, é possível utilizar um dos provedores
IBM Cloud Direct Link que inclui redundância ao seu serviço.

## Qual é a diferença entre o roteamento "local" padrão e o complemento Global Routing?
Com a nossa oferta do Direct Link padrão, é possível enviar o tráfego entre os datacenters
em sua região selecionada. Se você precisar de acesso a outros datacenters fora da região especificada,
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
de dados inesperados quando atravessar fora de sua região do datacenter. Ele mantém os custos reduzidos para a
maioria dos nossos clientes e permite que clientes com uma presença global atinjam
todas as regiões ao redor do mundo facilmente. Geralmente, no entanto, um cliente requer apenas um pacote de
largura da banda local.

## Quais são as opções de Roteamento Local e de Global Routing?
As opções de Local Routing e Global Routing são selecionadas por cada cliente ao solicitar o
serviço do Direct Link. Se os clientes precisam rotear o tráfego fora do POP na área em que eles solicitam
o Direct Link, eles devem incluir a opção Global Routing; caso contrário, o tráfego será restrito aos
serviços fornecidos pelo POP local.

Cada mês, todos os clientes que usam circuitos de 1G recebem 10 TB de tráfego de egresso livre e
os que clientes que usam circuitos 10G recebem 50 TB. Os excedentes são baseados na tabela a seguir, com a
maior taxa de mercado prevalecendo. Se você selecionar Global Routing, não será cobrado nenhum tráfego de
egresso local, apenas o tráfego que se origina ou que termina fora do POP local.

|Dados de Mercado 1|Dados de Mercado 2|Dados de Mercado 3|
|---|---|---|
|<ul><li>DAL</li><li>WDC</li><li>SEA</li><li>SJC</li><li>NYC*</li><li>CHI*</li><li>DEN*</li><li>MIA*</li><li>ATL*</li><li>LAX*</li><li>TOR</li><li>MON</li><li>AMS</li><li>FRA</li></ul>|<ul><li>TOK</li><li>HKG</li><li>PAR</li><li>MIL</li><li>STK*</li><li>OSL</li></ul>|<ul><li>MEX</li><li>SAO</li><li>SYD</li><li>MEL</li><li>PER*</li><li>CHE</li><li>SEO</li></ul>|
**Tabela 1: Camadas de utilização**<br/>
As ofertas do Direct Link nos mercados marcados com um asterisco (*) DEVEM solicitar o Global Routing.

## Se eu estou conectado a um NSP do Direct Link ou Direct Link Cloud Exchange em uma região como Dallas,
eu tenho acesso a outras regiões nos Estados Unidos por meio do Direct Link?
Sim, você é capaz de obter acesso a áreas fora de sua região se você escolher o complemento Global Routing. Se essa opção não for selecionada, o tráfego do Direct Link será limitado à região para o POP que você
selecionou.

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

O **Direct Link Exchange** é para clientes que preferem utilizar uma troca dentro de um data center. Com um
serviço do Exchange, os clientes podem ativar a conectividade em múltiplas nuvens para sua colocação rapidamente porque os
circuitos subjacentes já estão fornecidos (esses outros provedores em nuvem já devem ter uma interconexão física presente
dentro do recurso).

O Direct Link Exchange pode permitir um ambiente de múltiplas nuvens, de ambiente de uso compartilhado por meio de uma única
porta de troca de nuvem, criado por uma conexão do NNI na camada 2 entre o IBM Cloud e o provedor de serviços de troca de nuvem. 
As velocidades da porta estão disponíveis até 1 Gb.

O **Direct Link Connect** é para clientes que preferem utilizar a rede existente entre sua própria
implementação local e o IBM Cloud. Com um serviço do Direct Link Connect, os clientes podem usar redes de telecomunicações novas e
existentes (como MPLS) para ativar o IBM Cloud rapidamente, aproveitando os circuitos subjacentes fornecidos previamente.

Com o Direct Link Connect, a IBM e o parceiro se conectarão ao cliente na camada 2 e 3 por meio das
Network-to-Network Interfaces (NNIs) duais de camada 2 com 10 G, operadas por parceiros IBM em instalações no mundo todo. As
velocidades da porta estão disponíveis até 5 Gb.

