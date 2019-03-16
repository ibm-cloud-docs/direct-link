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
{:DomainName: data-hd-keyref="DomainName"}

# Usando o IBM Cloud Direct Link para se conectar ao IBM Cloud Object Storage
{: #using-ibm-cloud-direct-link-to-connect-to-ibm-cloud-object-storage}

Este documento descreve como configurar o {{site.data.keyword.cloud}} Direct Link para que você tenha acesso
ao IBM Cloud Object Storage (COS). Embora os métodos descritos aqui tenham sido projetados e testados com o COS, eles podem funcionar para outros serviços do IBM Cloud específicos.

Pela política atual, o IBM Cloud Direct Link nega acesso a terminais de serviço privado do IBM Cloud, incluindo aqueles usados pelo IBM Cloud Object Storage (COS). A técnica descrita neste documento depende do acesso indireto ao COS por meio de servidores hospedados na conta do IBM Cloud de um cliente. Após a configuração, cada servidor do cliente pode encaminhar o tráfego bidirecionalmente entre os terminais de serviço privado do IBM Cloud e suas redes remotas conectadas pelo Direct Link.

## O que é o IBM Cloud Object Storage (COS)?

O IBM Cloud Object Storage (COS) é uma plataforma de escala da web que armazena dados não estruturados. Ele fornece confiabilidade, segurança, disponibilidade e recuperação de desastre sem replicação manual.

As informações armazenadas no IBM Cloud Object Storage são criptografadas e dispersas em várias localizações geográficas. Ele é acessível por meio de uma implementação da API do S3. Esse serviço faz uso das tecnologias de armazenamento distribuído fornecidas pelo serviço IBM Cloud Object Storage.

O IBM COS está disponível em três configurações: **Região Cruzada**, **Regional** e **Site Único**.

 * O serviço de região cruzada fornece durabilidade e disponibilidade mais altas do que usar uma única região, mas ao custo da latência um pouco mais alta. Esse serviço está disponível hoje nos EUA e na União Europeia. (Observe que, ao usar um Virtual Router Appliance (VRA), você também poderá usar o Direct Link para se
conectar ao COS na região Ásia-Pacífico).

 * O serviço regional fornece o inverso: ele distribui objetos em várias zonas de disponibilidade dentro de uma única região. Se uma determinada região ou zona de disponibilidade estiver inacessível, o armazenamento de objeto continuará a funcionar normalmente. Qualquer mudança ausente será aplicada quando o data center inacessível voltar a ficar on-line.

 * O serviço de site único oferece acesso financeiramente suportável ao Cloud Object Storage em um data center selecionado.

### Terminais Privados e Públicos do COS
Terminais são URLs que os aplicativos usam para emitir comandos do COS e trocar dados com o COS. Cada terminal usa a mesma Interface de Programação de Aplicativos (API) para interagir com o COS.

Servidores provisionados no IBM Cloud usam terminais de API privados para serviços, incluindo o COS. Os terminais privados fornecem aos servidores IBM Cloud dos clientes conexões diretas de alta velocidade para serviços sem nenhum custo de largura da banda incluído.

Os terminais públicos do COS fornecem aos clientes do IBM Cloud acesso aos mesmos dados do COS que são acessíveis de dentro do IBM Cloud, mas os terminais públicos permitem acesso de qualquer local equipado com Internet.

Duas advertências se aplicam aos terminais públicos do COS:
 * O uso de terminais públicos pode incorrer em custos medidos para a largura da banda além dos encargos de uso impostos pelo serviço do COS.
 * Embora todos os dados sejam criptografados em trânsito, os clientes poderão ter questões de privacidade ou restrições regulamentares relacionadas aos dados transmitidos pela Internet.

## O que é IBM Cloud Direct Link?
O IBM Cloud Direct Link é um conjunto de produtos que fornece aos clientes a capacidade de criar conexões seguras e privadas entre seus ambientes de rede remota e suas implementações do IBM Cloud. Os dados trocados pelo Direct Link nunca são expostos na Internet.

## Usando o Cloud Object Storage (COS) sobre o IBM Cloud Direct Link
Os engenheiros da IBM desenvolveram um método que permite que um cliente do IBM Cloud que compra o COS e o Direct Link faça conexões remotas com os terminais privados do COS. Esse tipo de conexão estende as vantagens dos terminais de serviço privado, portanto, eles podem ser usados por sistemas do cliente fora dos recursos do IBM Cloud.

Essa solução é diagramada e descrita nas seções a seguir.

### Proxy reverso

**Premissa básica: os clientes remotos transmitem solicitações, incluindo credenciais seguras, por meio de um servidor privado para o COS**

![reverse=proxy](images/reverse-proxy.png)

As solicitações de COS HTTPS (HTTP seguro) são iniciadas em um cliente em um site remoto. Elas são transmitidas com segurança por meio do IBM Cloud Direct Link, atingindo um cluster de _servidores proxy reversos_ implementados na conta do IBM Cloud de um cliente. De lá, as solicitações são transmitidas para um terminal privado do COS, elas são processadas e, em seguida, os resultados retornados para o cliente de chamada remoto.

Qualquer código do cliente de amostra que funciona com COS também deve funcionar por meio de um servidor _proxy reverso_. O único ajuste necessário é que, em vez de atingir uma das URLs de terminal privado do COS publicadas pela IBM, o cliente é direcionado ao endereço IP ou à URL do servidor proxy reverso.

#### Instalando o seu Proxy Reverso Nginx
**NginX**  é um servidor da web de software livre maduro, compacto e rápido que se destaca em tarefas especializadas, incluindo a função do servidor _proxy reverso_ mencionada anteriormente.

As instruções e informações de configuração a seguir -- para configurar um servidor proxy reverso NginX -- podem funcionar depois de adaptá-las ao seu ambiente. Se
encontrar alguma dificuldade ou precisar de informações adicionais, consulte a parte de proxy reverso da
[documentação do Nginx
![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://docs.nginx.com/nginx/admin-guide/web-server/reverse-proxy/) ou
procure [stackoverflow ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")]](http://stackoverflow.com) para obter exemplos.

1. Provisione seus servidores VSI ou bare metal com a construção mínima do Linux **RHEL** ou **CentOS** (recomendado)
2. Para cada VSI, ative as regras do grupo de segurança a seguir na interface pública: `allow_http`, `allow_https`, `allow_outbound`, `allow_ssh`
3. Para cada VSI, ative as regras `allow_all` e `allow_outbound` na interface privada; selecione **Salvar**
4. Usando **PuTTY** no Windows ou o programa de terminal de sua área de trabalho, execute `ssh` em seu novo servidor como raiz
5. Faça upgrade de seu sistema operacional (`yum update`)
6. Instale o repositório EPEL (`yum install epel-release`)
7. Instale o NginX (`yum install nginx`)
8. Inicie o NginX (`nginx`) e abra o endereço IP do servidor em um navegador.
9. O local padrão de `nginx.conf` é `/etc/nginx`. Crie uma cópia segura.
10. Mova o arquivo de configuração de amostra `nginx.conf` abaixo para `/etc/nginx`
11. Compre certificados SSL por meio do portal do IBM Cloud ou execute o comando `yum install easy-rsa` e consulte seus documentos on-line favoritos para obter dicas sobre como criar certificados autoassinados.
12. Inclua as informações de certificado no arquivo de configuração, `nginx.conf`
13. Teste a configuração do NginX modificada usando o comando `nginx -t`
14. Se seu teste for aprovado, reinicie `nginx` com o comando `nginx -s quit; sleep 3; nginx`
15. Seu cliente agora deve ser capaz de enviar solicitações do COS para os IPs ou URLs do servidor NginX (proxy)

#### Notas:

* A solução assume que o Direct Link foi solicitado e implementado corretamente, embora ele possa ser testado sem ele.
* A memória ou o cache de disco opcional pode ser usado com `proxy_cache`
* Um valor mais longo `proxy_read_timeout` pode ser necessário para transferências de arquivos maiores.
* Use `keepalive` ou Pacemaker for High Availability (failover automático)

#### Arquivo de configuração: `nginx.conf`

O arquivo de configuração de amostra é apresentado na seção a seguir. É possível copiar e colá-lo.

```
user nginx;
worker_processes auto;
error_log /var/log/nginx/error.log;
pid /run/nginx.pid;

events {
    worker_connections 1024;
}

http {
    log_format  main  '$remote_addr - $remote_user [$time_local] "$request" '
                      '$status $body_bytes_sent "$http_referer" '
                      '"$http_user_agent" "$http_x_forwarded_for"';

    access_log  /var/log/nginx/access.log  main;

    sendfile            on;
    tcp_nopush          on;
    tcp_nodelay         on;
    keepalive_timeout   5;
    types_hash_max_size 2048;

    include             /etc/nginx/mime.types;
    default_type        application/octet-stream;
    ssl_session_cache shared:SSL:1m;
    ssl_session_timeout  10m;
    ssl_ciphers HIGH:!aNULL:!MD5;
    ssl_prefer_server_ciphers on;
    proxy_http_version 1.1;
    proxy_buffering off;
    proxy_intercept_errors on;

    # IBM COS Endpoints
    # https://cloud.ibm.com/docs/services/cloud-object-storage/basics?topic=cloud-object-storage-endpoints#select-regions-and-endpoints
    # US
    server {
        listen       443 ssl http2;
        server_name  us-cos.myibmcloud.com;
        ssl_certificate "/etc/pki/tls/certs/star.myibmcloud.com.pem";
        ssl_certificate_key "/etc/pki/tls/private/star.myibmcloud.com.key";
        location / {
            proxy_set_header Host $server_name;
            proxy_pass https://s3-api.us-geo.objectstorage.service.networklayer.com;
        }
    }

    # Dallas
    server {
        listen       443 ssl http2;
        server_name  dal-cos.myibmcloud.com;
        ssl_certificate "/etc/pki/tls/certs/star.myibmcloud.com.pem";
        ssl_certificate_key "/etc/pki/tls/private/star.myibmcloud.com.key";
        location / {
            proxy_set_header Host $server_name;
            proxy_pass https://s3-api.dal-us-geo.objectstorage.service.networklayer.com;
        }
    }
}
```

Consulte [Terminais COS](https://{DomainName}/docs/infrastructure/cloud-object-storage-infrastructure/endpoints.html#select-regions-and-endpoints) para obter uma lista de terminais privados para uso nas entradas `proxy_pass` acima.

#### Dicas:

 * Para impulsionar a escala e a resiliência, implemente múltiplos servidores proxy com diferentes terminais.
 * Use o DNS round-robin no lado do cliente para failover rudimentar e recursos de balanceamento de carga.
 * Os servidores proxy podem ser colocados atrás de um Virtual Router Appliance (VRA) para proteção e criação de log centralizada.

## Gerenciando e Provisionando recursos do IBM Cloud

Esta seção fornece links rápidos para a documentação para algumas ofertas do IBM Cloud PaaS e do SaaS que você pode conectar usando o IBM Cloud Direct Link.

### Como provisionar servidores bare metal

Para obter instruções detalhadas sobre como provisionar servidores bare metal, consulte o [Guia para Bare Metal Servers](https://{DomainName}/docs/bare-metal?topic=bare-metal-about#about).

### Como provisionar um Virtual Router Appliance (VRA)

Para obter instruções detalhadas sobre como provisionar um VRA, consulte o
[Guia de introdução ao VRA](https://{DomainName}/docs/infrastructure/virtual-router-appliance/getting-started.html#getting-started).

### Como provisionar o IBM Cloud Object Storage (COS)

 * Para obter instruções detalhadas sobre como provisionar COS, consulte o [Guia do Cloud Object Storage](https://{DomainName}/catalog/services/cloud-object-storage).

 * Use um dos terminais privados (listados anteriormente) para criar uma interface com seu depósito ou com qualquer
objeto em sua conta do COS provisionada.
