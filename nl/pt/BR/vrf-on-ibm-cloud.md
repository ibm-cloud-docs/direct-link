---

copyright:
  years: 2017, 2018
lastupdated: "2018-07-25"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Visão geral do Virtual Routing and Forwarding (VRF) no IBM Cloud

Por definição, Virtual Routing and Forwarding (VRF) é uma tecnologia incluída nos roteadores de rede do Protocolo da Internet (IP). Ele é entregue como um serviço backbone inerente.

## Opções de Conectividade para o IBM Cloud

**Recursos de nuvem dispersos** são recursos em mais de um local ou mesmo em mais de uma sub-rede ou VLAN. Esses recursos requerem uma função de roteamento para se comunicar entre si, mesmo em um contexto de rede privada. Este documento descreve uma opção de comunicação de ocupação de "múltiplo isolamento", que geralmente é chamada de _VRF do cliente_. Ela é implementada como uma VPN MPLS de Camada 3 (RFC 4364) no backbone global do IBM Cloud.

Em geral, o IBM Cloud Platform oferece duas opções para roteamento em nossa rede privada, fornecendo conectividade entre pods e data centers: 

1. **Ocupação compartilhada:** uma rede lógica comum, compartilhada por todos os locatários que usam esse modelo, com separação fornecida pelas Listas de controle de acesso (ACLs) automatizadas e ativada com a ampliação da VLAN. (Essa opção não é descrita neste documento.)

2. **Múltiplo isolamento:** uma rede lógica dedicada por locatário, que não permite interação com as redes lógicas de outros locatários.  

Este documento usa o termo **VRF do cliente** para descrever a conectividade de rede de _múltiplo isolamento_.

## Visão geral do VRF do cliente

O Virtual Routing and Forwarding (VRF) permite que várias instâncias de uma tabela de roteamento existam em um roteador e que funcionem simultaneamente. Com o Virtual Routing and Forwarding (VRF), cada rede VRF do cliente é segmentada em sua tabela de roteamento. Essa segmentação permite sobreposições de endereço IP e não cria nenhuma interação ou interferência com outros VRFs do cliente. O IBM Cloud utiliza uma grande maioria da rede `10.0.0.0/8`, que pode ser sobreposta por muitas redes remotas do cliente. 

Usando o Virtual Routing and Forwarding (VRF), os clientes têm permissão para usar endereços IP remotos que normalmente não teriam permissão de sobreposição na tabela Global. A IBM ainda reserva a RFC 1918, os endereços locais de link e os endereços multicast a seguir, que não são roteáveis por meio desse serviço VRF:

* ` 10.0.0.0/ 14 ` 
* ` 10.200.0.0/ 14 ` 
* ` 10.198.0.0/ 15 ` 
* ` 169.254.0.0/ 16 ` 
* ` 224.0.0.0/4 ` 
* `166.9.0.0/16` (usado pelo serviço de terminal privado)
* Quaisquer intervalos de IP designados às suas VLANs na plataforma IBM.

A IBM está avançando com uma implementação na nuvem de última geração para ativar a Nuvem Particular Virtual (VPC) em nossas Zonas de disponibilidade (AZs). Esse novo recurso VPC permite que os clientes usem o recurso Bring Your own IP (BYoIP) nas AZs ativadas para VPC, que estão localizadas em Dallas, Washington DC, Londres, Frankfurt, Tóquio e Sydney. 

Cada locatário no backbone que utiliza o Virtual Routing and Forwarding (VRF) pode ter um (e apenas um) _VRF do cliente_ por Direct Link, que fornece conectividade entre todos os servidores do locatário, independentemente do local. No entanto, um cliente pode ter mais de uma conta do Direct Link que é alimentada em um único roteador de conexão cruzada.  

* Os servidores de um locatário em qualquer VLAN, em qualquer pod, em qualquer data center no mundo todo podem atingir todos os outros servidores desse locatário globalmente. 

* O VRF do cliente de cada locatário está conectado à rede de serviços compartilhados comuns para fornecer alcance privado para esses servidores usarem o DNS, o armazenamento compartilhado, o monitoramento, a correção e assim por diante.

* O VRF do cliente é um serviço de conectividade que fornece isolamento entre os locatários. Quaisquer controles adicionais necessários em uma ocupação devem ser provisionados separadamente, usando um gateway, grupos de segurança ou controles baseados em host.

## Benefícios da movimentação para um VRF do cliente

**Os principais benefícios de um VRF do cliente incluem:**

* Tecnologia de separação de _múltiplo isolamento_ comprovada pela indústria e amplamente aceita. Muitos clientes acham a abordagem VPN de Nível 3 mais palatável (do que ACLs) para seus auditores e executivos de conformidade.   

* Os clientes podem ampliar ou migrar o alcance de sua rede de forma significativa, devido à inclusão de novos sites ou aplicativos em toda a rede IBM. 

* As tabelas de roteamento específicas do locatário limitam a abertura para a sobreposição de endereço IP, sem o risco de sobreposição pelas sub-redes de outros locatários ou outras partes da rede que não são aplicáveis. 

**Algumas trocas menores vêm com o VRF do cliente, em comparação com o modelo de ACL mais antigo:**  

* A conversão para um VRF do cliente requer uma janela de manutenção, o que causa uma breve interrupção de fluxos de tráfego de backbone.

* O acesso remoto por meio dos serviços VPN gerenciados (SSL, IPSec) é limitado ao data center local, no entanto, o backbone da ACL compartilhada permite acesso global de qualquer ponto de entrada.

* A ampliação da VLAN em uma ocupação de _múltiplo isolamento_ do cliente não está disponível.

## O que acontece durante o processo de conversão de conta

Muitos clientes estão operando atualmente em um modelo de ocupação compartilhada na rede do IBM Cloud. Durante a conversão, a ocupação é convertida para usar um VRF do cliente, mais comumente com uma nova assinatura do Direct Link ou conforme necessário ou solicitado.  

O processo de conversão envolve uma interrupção na rede, enquanto as VLANs e suas sub-redes são removidas do backbone da ACL e, em seguida, conectadas ao VRF do cliente. Esse processo resulta em alguns momentos de perda de pacote para o tráfego que está entrando ou saindo das VLANs. Os pacotes na VLAN continuam a fluir. Nos casos em que um gateway de rede, como um FortiGate Security Appliance ou um Virtual Router Appliance está envolvido, não ocorre nenhuma interrupção entre as VLANs conectadas a esse gateway. Os próprios servidores não veem nenhuma indisponibilidade de rede e a maioria das cargas de trabalho se recupera automaticamente quando o fluxo de tráfego continua. A duração total da interrupção depende da extensão da topologia do locatário, ou seja, do número de sub-redes, das VLANs e dos pods incluídos pela ocupação.

![The conversion process](/images/vrf-on-ibm-cloud.png)

Durante a migração, as VLANs do cliente são desconectadas do backbone e reconectadas ao VRF do cliente.  A duração da interrupção varia, dependendo da quantidade de VLANs, de PODs e de data centers envolvidos. O tráfego entre as VLANs é interrompido e, mesmo assim, os servidores permanecem conectados à rede. O aplicativo pode ou não ser afetado, dependendo de sua sensibilidade à perda de pacote.

## Como é possível iniciar a conversão

Nossos clientes podem abrir um chamado de suporte por meio de sua conta do [IBM Cloud Console ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")]( https://control.bluemix.net/support/unifiedConsole/tickets/add), solicitando que seja migrada para um VRF. O chamado deve afirmar: "Pergunta da rede privada" e incluir o texto a seguir no chamado de suporte: 

"Estamos solicitando que a conta _preencha o número da sua conta_ seja movida para seu próprio VRF. Entendemos os riscos e aprovamos a mudança.  Responda novamente com as janelas de tempo planejadas em que essa mudança será feita para que possamos nos preparar para a migração". 

A migração foi concluída pela equipe do IBM Cloud Network Engineering. Nenhuma outra informação é necessária do cliente, exceto um planejamento acordado. Geralmente, a perda de pacote pode durar de 15 a 30 minutos, dependendo da complexidade da conta. (Poderá demorar mais se um cliente tiver conexões anteriores do Direct Link). O processo é altamente automatizado. Ele envolve interação mínima da equipe da IBM e deve ser transparente para um cliente.
