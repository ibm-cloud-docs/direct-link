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

# Utilizzo di IBM Cloud Direct Link per il collegamento a IBM Cloud Object Storage
{: #using-ibm-cloud-direct-link-to-connect-to-ibm-cloud-object-storage}

Questo documento descrive come configurare {{site.data.keyword.cloud}} Direct Link in modo da avere accesso a IBM Cloud Object Storage (COS). Anche se i metodi qui descritti sono stati progettati e verificati con COS, possono funzionare per alcuni altri servizi IBM Cloud.

Con la politica corrente, IBM Cloud Direct Link nega l'accesso agli endpoint del servizio privato IBM Cloud, inclusi quelli utilizzati da IBM Cloud Object Storage (COS). La tecnica descritta in questo documento si basa sull'accesso indiretto a COS tramite i server ospitati in account IBM Cloud del cliente. Dopo la configurazione, ogni server del cliente può inoltrare il traffico in modo bidirezionale tra gli endpoint del servizio privato IBM Cloud e le loro reti remote collegate da Direct Link.

## Che cos'è IBM Cloud Object Storage (COS)?

IBM Cloud Object Storage (COS) è una piattaforma su scala web che archivia i dati non strutturati. Fornisce affidabilità, sicurezza, disponibilità e ripristino di emergenza senza replica manuale.

Le informazioni archiviate in IBM Cloud Object Storage vengono crittografate e distribuite in più ubicazioni geografiche. Sono accessibili tramite un'implementazione dell'API S3. Questo servizio utilizza le tecnologie di archiviazione distribuita fornite dal servizio IBM Cloud Object Storage.

IBM COS è disponibile in tre configurazioni: **Cross Region**, **Regional** e **Single Site**.

 * Il servizio Cross Region fornisce una disponibilità e una durata maggiori rispetto all'utilizzo di una sola regione, ma al costo di una leggermente maggiore latenza. Questo servizio è disponibile oggi negli Stati Uniti e in Europa. (Nota che, utilizzando una VRA (Virtual Router Appliance), potresti anche utilizzare Direct Link per stabilire una connessione a COS nella regione Asia Pacifico).

 * Il servizio Regional fornisce il contrario: distribuisce gli oggetti in più zone di disponibilità all'interno di una sola regione. Se una zona di disponibilità o una regione non è disponibile, l'archiviazione oggetti continua a funzionare correttamente. Tutte le modifiche mancanti vengono applicate quando il data center non accessibile torna online.

 * Il servizio Single Site offre un accesso conveniente a Cloud Object Storage in un data center selezionato.

### Endpoint pubblico e privato COS
Gli endpoint sono URL che le applicazioni utilizzano per immettere i comandi COS e scambiare i dati con COS. Ogni endpoint utilizza la stessa API (Application Programming Interface) per interagire con COS.

I server di cui è stato eseguito il provisioning all'interno di IBM Cloud utilizzano gli endpoint API privati per i servizi, incluso COS. Gli endpoint privati forniscono ai server IBM Cloud dei clienti elevata velocità, connessioni dirette ai servizi senza ulteriori costi per la larghezza di banda.

Gli endpoint pubblici COS forniscono ai clienti IBM Cloud l'accesso agli stessi dati COS che sono accessibili dall'interno di IBM Cloud, ma gli endpoint pubblici consentono l'accesso da qualsiasi ubicazione che dispone di internet.

Si applicano due avvertimenti agli endpoint pubblici COS:
 * L'utilizzo degli endpoint pubblici può comportare dei costi misurati per larghezza di banda oltre agli addebiti di utilizzo imposti dal servizio COS.
 * Anche se tutti i dati sono codificati in transito, i clienti potrebbero avere preoccupazioni relative alla privacy o limitazioni normative correlate ai dati trasmessi tramite internet.

## Che cos'è IBM Cloud Direct Link?
IBM Cloud Direct Link è una suite di prodotti che fornisce ai clienti la capacità di creare connessioni private e sicure tra i loro ambienti di rete remoti e le loro distribuzioni IBM Cloud. I dati scambiati da Direct Link non vengono mai esposti su internet.

## Utilizzo di Cloud Object Storage (COS) su IBM Cloud Direct Link
Gli ingegneri di IBM hanno sviluppato un metodo che consente a un cliente IBM Cloud che acquista COS e Direct Link di effettuare connessioni remote agli endpoint privati COS. Questo tipo di connessione estende i vantaggi degli endpoint del servizio privato, in modo che possono essere utilizzati dai sistemi client al di fuori delle funzioni di IBM Cloud.

Questa soluzione viene schematizzata e descritta nelle seguenti sezioni.

### Proxy inverso

**Premessa di base: i client remoti passano le richieste, incluse le credenziali sicure, tramite un server privato a COS**

![reverse=proxy](images/reverse-proxy.png)

Le richieste COS HTTPS (HTTP sicuro) sono avviate da un client in un sito remoto. Vengono trasmesse in modo sicuro tramite IBM Cloud Direct Link, con destinazione uno dei cluster dei _server proxi inversi_ distribuiti in un account IBM Cloud del cliente. Da lì, le richieste vengono passate a un endpoint privato COS, vengono elaborate e i risultati vengono poi restituiti al client di chiamata remoto.

Ogni codice client di esempio che funziona con COS dovrebbe funzionare anche tramite un server _proxy inverso_. L'unica modifica richiesta è che, invece di avere come destinazione uno degli URL dell'endpoint privato COS pubblicato da IBM, il client utilizza l'indirizzo IP o l'URL del server proxy inverso.

#### Installazione del tuo proxy inverso Nginx
**NginX** è un server web open source veloce compatto e completo che eccelle in attività specializzate, incluso il precedentemente menzionato ruolo del server _proxy inverso_.

Le seguenti istruzioni e le informazioni sulla configurazione--per la configurazione di un server proxy inverso NginX--possono funzionare dopo che le hai adattate al tuo ambiente. Se non sai come procedere o hai bisogno di ulteriori informazioni, consulta la parte riguardante il proxy inverso della [documentazione Nginx ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://docs.nginx.com/nginx/admin-guide/web-server/reverse-proxy/) o cerca [stackoverflow ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")]](http://stackoverflow.com) per degli esempi.

1. Esegui il provisioning dei tuoi server VSI o bare metal con almeno la build Linux **RHEL** o **CentOS** (consigliato)
2. Per ogni VSI, abilita le seguenti regole del gruppo di sicurezza nell'interfaccia pubblica: `allow_http`, `allow_https`, `allow_outbound`, `allow_ssh`
3. Per ogni VSI, abilita le regole `allow_all` e `allow_outbound` nell'interfaccia privata; seleziona **Save**
4. Utilizzando **PuTTY** in Windows o il programma del terminale del tuo desktop, esegui `ssh` nel tuo nuovo server come root
5. Aggiorna il tuo sistema operativo SO (`yum update`)
6. Installa il repository EPEL (`yum install epel-release`)
7. Installa NginX (`yum install nginx`)
8. Avvia NginX (`nginx`) e apri l'indirizzo IP del tuo server in un browser.
9. L'ubicazione predefinita di `nginx.conf` è `/etc/nginx`. Crea una copia sicura.
10. Sposta il file di configurazione `nginx.conf` di esempio, sotto, in `/etc/nginx`
11. Acquista i certificati SSL tramite il portale IBM Cloud o esegui il comando `yum install easy-rsa` e consulta la tua documentazione offline preferita per dei suggerimenti sulla creazione dei certificati autofirmati.
12. Aggiungi le informazioni del tuo certificato al file di configurazione, `nginx.conf`
13. Verifica la configurazione NginX modificata utilizzando il comando `nginx -t`
14. Se la verifica ha esito positivo, riavvia `nginx` con il comando `nginx -s quit; sleep 3; nginx`
15. Il tuo client dovrebbe ora essere abilitato ad inviare le richieste COS agli IP o URL del server (proxy) NginX

#### Note:

* La soluzione presuppone che sia stato ordinato e distribuito correttamente Direct Link, anche se può essere verificata senza di esso.
* Può essere utilizzata memoria facoltativa o cache disco con `proxy_cache`
* Potrebbe essere necessario un valore `proxy_read_timeout` più lungo per trasferimenti file più grandi.
* Utilizza `keepalive` o Pacemaker per l'alta disponibilità (failover automatico)

#### File di configurazione: `nginx.conf`

Viene mostrato il file di configurazione di esempio nella seguente sezione. Puoi copiarlo e incollarlo.

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

Consulta [COS Endpoints](https://{DomainName}/docs/infrastructure/cloud-object-storage-infrastructure/endpoints.html#select-regions-and-endpoints) per un elenco di endpoint privati da utilizzare nelle precedenti voci `proxy_pass`.

#### Suggerimenti:

 * Per rafforzare la resilienza e il ridimensionamento, distribuisci più server proxy associati a endpoint differenti.
 * Utilizza il DNS round robin nel lato del client per le funzionalità di bilanciamento del carico e di failover elementari.
 * I server proxy possono essere posizionati dietro il VRA (Virtual Router Appliance) per la protezione e la registrazione centralizzata.

## Gestione e provisioning delle funzionalità IBM Cloud

Questa sezione fornisce link rapidi alla documentazione per alcune offerte di IBM Cloud PaaS e SaaS che potresti collegare per utilizzare IBM Cloud Direct Link.

### Come eseguire il provisioning dei server bare metal

Per istruzioni dettagliate su come eseguire il provisioning del server bare metal, fai riferimento a [Guide to Bare Metal Servers](https://{DomainName}/docs/bare-metal?topic=bare-metal-about#about).

### Come eseguire il provisioning di un VRA (Virtual Router Appliance)

Per istruzioni dettagliate su come eseguire il provisioning di un VRA, fai riferimento a
[VRA Getting Started Guide](https://{DomainName}/docs/infrastructure/virtual-router-appliance/getting-started.html#getting-started).

### Come eseguire il provisioning di IBM Cloud Object Storage (COS)

 * Per istruzioni dettagliate su come eseguire il provisioning di COS, fai riferimento alla [Guida Cloud Object Storage](https://{DomainName}/catalog/services/cloud-object-storage).

 * Utilizza uno degli endpoint privati (elencati precedentemente) per creare un'interfaccia con il tuo bucket o con ogni
 oggetto nel tuo account COS fornito.
