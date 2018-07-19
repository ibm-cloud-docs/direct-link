---

copyright:
  years: 2018
lastupdated: "2018-04-24"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Juntos: IBM Cloud Direct Link e IBM Cloud Object Storage

Este documento descreve como configurar o IBM Cloud Direct Link para que você tenha acesso ao IBM Cloud Object Storage e a outros serviços do IBM Cloud. Existem vários métodos para a ligação da rede privada do IBM Cloud IaaS, sobre a qual o IBM Cloud Direct Link existe, para a rede "pública" que suporta os recursos do IBM Cloud PaaS e SaaS, sem de fato deixar o backbone do IaaS.

Por política atual, os terminais de serviço privado do IBM Cloud não são acessíveis por meio do IBM Cloud Direct Link. As técnicas descritas neste documento contam com acesso indireto por meio de sistemas hospedados pelo IBM Cloud. Embora os terminais de serviço privado não sejam acessíveis por meio do Direct Link, os servidores e dispositivos privados do cliente podem se tornar acessíveis.

## O que é o IBM Cloud Object Storage (COS)?

O IBM Cloud Object Storage é uma plataforma de escala da web que armazena dados não estruturados. Ele fornece confiabilidade, segurança, disponibilidade e recuperação de desastre sem replicação. 

As informações armazenadas com o IBM Cloud Object Storage são criptografadas e dispersas em várias localizações geográficas. Ele é acessível por meio de uma implementação da API do S3. Esse serviço faz uso das tecnologias de armazenamento distribuído fornecidas pelo serviço IBM Cloud Object Storage.

O IBM COS está disponível em duas configurações: **Região Cruzada** e **Regional**. O serviço de região cruzada fornece durabilidade e disponibilidade mais altas do que usar uma única região, mas ao custo da latência um pouco mais alta. Esse serviço está disponível atualmente nos EUA e na União Europeia. O serviço regional fornece o inverso: ele distribui objetos em várias zonas de disponibilidade dentro de uma única região. Se uma determinada região ou zona de disponibilidade estiver inacessível, o armazenamento de objeto continuará a funcionar normalmente. Qualquer mudança ausente será aplicada quando o data center inacessível voltar a ficar on-line.

## O que é IBM Cloud Direct Link?

O IBM Cloud Direct Link é um conjunto de produtos que fornece aos clientes a capacidade de criar conexões privadas entre seus ambientes de rede remota e suas implementações do IBM Cloud. 

## Usando o Cloud Object Storage (COS) sobre o IBM Cloud Direct Link

A família de soluções de conectividade do IBM Cloud Direct Link é uma oferta IaaS, que visa a permitir conectividade de WAN privada aos nossos serviços IaaS. A maioria das soluções IBM Cloud PaaS e SaaS é construída sobre o nosso IaaS. Portanto, é possível iniciar esses tipos de conexões de dentro do IBM Cloud.

Essas três abordagens podem ajudá-lo a se conectar ao IBM Cloud PaaS e SaaS usando o IBM Cloud Direct Link. Atualmente, o Método Nº 3 é a abordagem recomendada, porque ele foi testado de forma mais completa.

## Três métodos para conexão com o PaaS e o SaaS com o Direct Link


### Método 1: usar um Virtual Router Appliance (VRA, às vezes chamado de Vyatta) para criar um "hop para público"
 
![vyatta-flow.png](images/vyatta-flow.png)



**Premissa básica: conectar-se ao IBM COS com um "hop público" para conectar-se aos terminais de armazenamento**
*Esse "hop público" nunca deixa o backbone do IBM Cloud IaaS.*

* O cliente escolhe um terminal Público com assistência do suporte ao cliente do IBM COS e da equipe de onboarding e recebe uma chave API.
* Em seu roteador no local, o cliente inclui rotas para sub-redes específicas, para assegurar fluxos de tráfego adequados usando o IBM Cloud Direct Link
* Em seu VRA, o cliente cria uma rota para atravessar a rede pública e atingir o terminal público para serviços do IBM COS
* O cliente deve provisionar um par de HA do hardware VRA (@x)
* Cada membro do VRA recebe 20 TB por mês de largura de banda incluída, para compensar os encargos de medição e faturamento de sua nuvem Pública
* Use o conjunto de largura da banda em seus servidores hospedados para acumular a largura da banda paga antecipadamente.


### Método 2: Passagem do servidor em nuvem (privada para particular)

![reverse=proxy](images/reverse-proxy.png)

**Premissa básica: servidores em nuvem de confiança com credenciais do COS**

 * O cliente provisiona um ou mais servidores, VSI ou Bare Metal, no IBM Cloud
 * Cada servidor hospeda um aplicativo baseado na web ou em script (Java, Python, PHP, etc.) para receber conexões e solicitações apenas em sua interface privada
 * O app do servidor usa sua própria API ou imita (porções de) S3
 * As interfaces privadas do servidor IBM Cloud são bastante seguras. Separe o acesso dentro da rede privada usando VLANs, Grupos de Segurança, firewall do S.O. ou VRA
 * Medidas para validar o responsável pela chamada e limitar o alcance da API são prudentes
 * Os clientes na rede no local do cliente usam endereços IP privados dos servidores de passagem de nuvem como destinos para solicitações
 * Requer roteamento do cliente e mudanças de DNS
 * O aplicativo hospedado pelo servidor manipula cada solicitação emitindo uma chamada API autenticada para um terminal COS privado, retornando a resposta ao responsável pela chamada

### Método 3: Proxy reverso (privado para privado)

Esse método é a abordagem recomendada atualmente.

**Premissa básica: confiar em responsáveis pela chamada de cliente no local com credenciais do COS**

 

 * Como uma adaptação do Método 2, em vez de hospedar apps da web em servidores em nuvem, hospede servidores HTTPS (por exemplo, NGINX) configurados para proxy reverso.
 * Cada servidor atende no HTTPS, com certificado autoemitido, e transmite solicitações diretamente para os terminais COS privados que são fornecidos no documento referenciado abaixo:
 
 ![Terminais COS](https://console.bluemix.net/docs/services/cloud-object-storage/basics/endpoints.html)
 
### Visualize um exemplo de como melhorar a confiabilidade e o desempenho de sua nuvem (não específico ao COS): `serverfault.com`

 * Para impulsionar a escala e a resiliência, múltiplos servidores proxy podem ser implementados. 
 * Use o DNS round-robin no lado do cliente para failover rudimentar e recursos de balanceamento de carga.
 * Os servidores proxy podem ser colocados atrás do VRA para proteção e para criação de log centralizada.
 
 ## Gerenciando e Provisionando recursos do IBM Cloud 
 
Esta seção fornece links rápidos para a documentação para algumas ofertas do IBM Cloud PaaS e do SaaS que você pode conectar usando o IBM Cloud Direct Link.

## Como provisionar servidores bare metal

Para obter instruções detalhadas sobre como provisionar bare metal, consulte [este documento](https://console.bluemix.net/docs/bare-metal/about.html#getting-started-with-bare-metal-servers).

## Como provisionar um Virtual Router Appliance (VRA)

Para obter instruções detalhadas sobre como provisionar um VRA, consulte [este documento](https://console.bluemix.net/docs/infrastructure/virtual-router-appliance/getting-started.html#getting-started).

## Como provisionar o IBM Cloud Object Storage (COS)

 * Para obter instruções detalhadas sobre como provisionar o COS, consulte [este documento](https://console.bluemix.net/catalog/services/cloud-object-storage).
 
 * Use um dos terminais privados (listados anteriormente) para a interface com seu depósito ou objeto em sua conta do COS provisionada.
