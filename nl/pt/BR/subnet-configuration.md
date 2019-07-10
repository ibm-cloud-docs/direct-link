---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-30"

keywords: direct link, configure, connectivity, BGP, VRF, configuration, RFC1918, ASN, BYOIP, NAT, VLAN Spanning, 10.0.0.0/8, ECMP, redundancy, IP assignments, VMWare, Vyatta, IP limitations

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:note: .note}
{:download: .download}

# Configure o IBM Cloud Direct Link
{: #configure-ibm-cloud-direct-link}

Logo que a sua conectividade do {{site.data.keyword.cloud}} Direct Link tiver sido estabelecida, será possível seguir as etapas fornecidas neste documento para configurar a sua sub-rede para interagir com o {{site.data.keyword.cloud_notm}}.

Em geral, para ter a sua conexão do {{site.data.keyword.cloud_notm}} Direct Link funcionando, você precisará fazer algumas etapas básicas de configuração de rede e, em seguida, será necessário configurar o Border Gateway Protocol (BGP). Durante o processo de configuração, um engenheiro IBM trabalhará com você para ativar sua rede para uso do
recurso Virtual Routing Function (VRF), que é necessário.

## Configuração básica de rede
{: #basic-network-configuration}

1. Defina sua rede remota usando o espaço de endereço privado RFC1918 padrão. 
 * Para novos ambientes, recomenda-se **NÃO** usar o espaço 10.0.0.0/8. 
 * Para ambientes existentes que utilizam 10.0.0.0/8, recomendamos que você obtenha uma avaliação mais
detalhada, para assegurar que não haja conflito com a rede de serviços do
{{site.data.keyword.cloud_notm}}
ou com as redes já designadas à sua conta.

2. Nossa equipe no {{site.data.keyword.cloud_notm}} designa um /31 ou /30 para cada
conexão e configura um endereço IP da interface na infraestrutura de roteador de conexão cruzada (XCR) do
{{site.data.keyword.cloud_notm}}.  

3. Configure a interface no seu roteador de borda do cliente (CER) usando o endereço IP fornecido:
utilize o IP XCR do {{site.data.keyword.cloud_notm}} como um próximo hop para
qualquer tráfego destinado ao {{site.data.keyword.cloud_notm}}. 

4. Para o tráfego de retorno, o {{site.data.keyword.cloud_notm}} utiliza o IP do CER
designado como o próximo hop para qualquer tráfego destinado à rede remota, conforme anunciado via BGP.

## Configurando o BGP
{: #configuring-bgp}

Para trocar informações de rota com seu ambiente, o {{site.data.keyword.cloud_notm}} requer
que o BGP seja configurado.  

1. **ASN**: o {{site.data.keyword.cloud_notm}} designa um
ASN privado para cada uso do cliente. Como alternativa, é possível utilizar seu próprio ASN público. Sua preferência é
solicitada no momento em que faz seu pedido. Seu ASN privado designado é fornecido para você durante o processo
de implementação.

2. **VRF**: usando o VRF, o {{site.data.keyword.cloud_notm}} anuncia
as sub-redes privadas específicas designadas à sua conta do cliente. Deve-se anunciar as redes remotas que
você deseja que fiquem acessíveis por meio da rede privada do {{site.data.keyword.cloud_notm}}. Como um cliente, é sua responsabilidade gerenciar os anúncios
que o IBM Cloud envia e recebe. (Mais detalhes sobre o VRF estão incluídos na próxima seção).

As seguintes redes são filtradas e não podem ser aceitas: 0.0.0.0, 10.0.0.0/14, 10.198.0.0/15, 10.200.0.0/14,
169.254.0.0/16, 224.0.0.0/4.
{:note}

3. **ECMP**: para clientes que optam por construir redundância em um local
suportado, o {{site.data.keyword.cloud_notm}} suporta a implementação de caminhos múltiplos
de custo igual (ECMP) para fornecer balanceamento de carga e redundância entre os dois links. Esta
configuração ECMP deve ser solicitada no momento do pedido.

## Especificações do BGP para o IBM Cloud Direct Link
{: #bgp-specifications-for-ibm-cloud-direct-link}

As especificações do BGP são as seguintes:

Conforme indicado na seção anterior, o BGP é obrigatório para gerenciar seu roteamento por meio do Direct Link. Uma conta que pede o Direct Link será migrada para o ambiente VRF.

**Avisos para VLANS e VRF:**
 * A ampliação da VLAN interconta não é permitida no ambiente VRF. 
 * O serviço IPSEC VPN é limitado. 
 
O VRF não evita o acesso à VPN do SSL ou do PPTP, mas o comportamento muda. Sem o VRF, uma conexão VPN é suficiente para ver todos os servidores em sua conta. Com o VRF, é possível acessar somente recursos no mercado associados à sua VPN. Portanto, se você se conectar à VPN do DAL, será possível apenas se conectar a servidores do DAL.
{: note}

O ASN do IBM Cloud é **13884**, para serviços Públicos e Privados. 
 * O ASN padrão para um cliente ao pedir é **64999**, mas o padrão pode ser mudado por solicitação do cliente. 
 * Opcionalmente, um ASN privado de 4 bytes entre 4201000000 e 4201064511 pode ser suportado.
 * Se você estiver usando o Direct Link Connect com um serviço de camada 3, como VPN de IP, o IBM Cloud estabelecerá o BGP com o ASN do provedor do Direct Link Connect

** Recomendações, Padrões e Limites: **

 * O tunelamento (ou seja, GRE) será suportado e recomendado se a sobreposição de IP se tornar um problema.
 * Os padrões de cronômetro BGP são  ` Keepalive: 30 `,  ` Holdtime: 60. `
 * A autenticação não é ativada por padrão.
 * O BFD do BGP não é ativado por padrão.
 * O limite máximo de prefixo recebido (do cliente ou provedor) é 200 por VRF.
 
## Limitações estritas em designações de IP
{: #strict-limitations-on-ip-assignments}

 * Se você utilizar a rede 10.x.x.x,, ainda não poderá criar sobreposição com seus hosts dentro do IBM Cloud nem com a rede de serviços do IBM Cloud, que ocupa `10.0.0.0/14`, `10.198.0.0/15` e `10.200.0.0/14`.  

 * Os intervalos a seguir não são permitidos no sistema Federal e eles serão rejeitados pelos servidores IBM: `169.254.0.0/16`, `224.0.0.0/4`.

## Redundância e diversidade
{: #redundancy-and-diversity}

O {{site.data.keyword.cloud_notm}} Direct Link fornece diversidade e os clientes são responsáveis por implementar a redundância por meio de seus esquemas do BGP.

Se você selecionar o ECMP para redundância, ambas as sessões do BGP deverão existir no mesmo XCR; portanto, você desiste da diversidade do roteador e será exposto ao risco se o roteador falhar. Você ganha redundância de Camada 3, mas perde a diversidade do roteador.

## Mais sobre o uso do VRF
{: #more-about-using-vrf}

Todas as contas que utilizam uma solução do {{site.data.keyword.cloud_notm}} Direct Link devem migrar para um VRF. Usando o VRF, os
clientes anunciam a rotas disponíveis para suas redes remotas autodefinidas. Observe que essa
configuração não permite o uso de endereços IP autodefinidos
na rede do {{site.data.keyword.cloud_notm}}.

A migração para um VRF é feita durante o processo de configuração. Ela requer uma janela de
indisponibilidade curta (até 30 minutos para contas grandes com múltiplas VLANs/locais),
durante a qual as VLANs de rede de backend perdem a conectividade mútua enquanto são movidas para o VRF. A migração
do VRF é planejada marcada com o engenheiro de implementação.

Observe que o VRF elimina a opção "VLAN Spanning" para sua conta, incluindo quaisquer
recursos de ampliação de VLAN conta a conta, já que todas as VLANs são capazes de se comunicar, a menos que um
Dispositivo de Gateway seja introduzido para gerenciar o tráfego. O VRF também limita a capacidade de uso dos
serviços de VPN do {{site.data.keyword.cloud_notm}}, já que
ele não é compatível com os serviços de VPN SSL, PPTP e IPSec
do {{site.data.keyword.cloud_notm}}.   

Uma alternativa é usar a própria oferta do IBM Cloud Direct Link para gerenciar os seus servidores ou executar a sua própria
solução de VPN (como um Vyatta) que pode ser configurado com diferentes tipos de VPN. Após migrar para um VRF, a VPN SSL geralmente funciona quando uma conexão VPN é estabelecida no mesmo
local do data center no qual uma VM de cálculo está em execução, mas não permite acesso
globalmente.

## Usando BYOIP e NAT com o Direct Link
{: #using-byoip-and-nat-with-direct-link}

O IBM Cloud Direct Link não oferece BYOIP na rede privada. Portanto, o
tráfego com um endereço IP de destino que não foi designado pelo
{{site.data.keyword.cloud_notm}} será eliminado. No entanto, os clientes podem encapsular o
tráfego entre a rede remota e sua rede do {{site.data.keyword.cloud_notm}} usando GRE,
IPSec ou VXLAN.  

Mais comumente, o ambiente BYOIP é implementado dentro do escopo de uma implementação do Network Gateway
(Vyatta) ou NSX do VMWare. Essa configuração permite que os clientes usem qualquer espaço de IP desejado no
lado do {{site.data.keyword.cloud_notm}} e roteiem de volta através do túnel para a
rede remota. Observe que esta configuração deve ser gerenciada e suportada pelo cliente, independentemente do
{{site.data.keyword.cloud_notm}}. Além disso, essa configuração poderá quebrar a conectividade
com a rede de serviços do {{site.data.keyword.cloud_notm}} se o cliente designar um
bloco 10.x.x.x que o {{site.data.keyword.cloud_notm}} utiliza para serviços. 

Essa solução também requer que cada host que precisa de conectividade com a rede de serviços do {{site.data.keyword.cloud_notm}}
e a rede remota tenha 2 endereços IP designados: um deve ser designado do bloco IBM 10.x.x.x e outro do bloco de
rede remota. Rotas estáticas devem ser configuradas no host, para assegurar que o tráfego seja roteado de forma
apropriada. Não será possível designar um espaço de IP diretamente nos hosts do
{{site.data.keyword.cloud_notm}} (BYOIP) e torná-lo roteável na rede do
{{site.data.keyword.cloud_notm}} inerentemente. A única maneira de implementar essa capacidade
é conforme descrito anteriormente, mas esse processo não é suportado pelo
{{site.data.keyword.cloud_notm}}.

Como alternativa, os clientes normalmente designam um bloco de rede remota para uso em uma
tabela NAT configurada em seu roteador de borda remoto. Essa configuração
permite que os clientes limitem as mudanças necessárias para ambas as redes, enquanto ainda converte o
tráfego em um espaço de endereço de rede que seja compatível com ambas as redes.
