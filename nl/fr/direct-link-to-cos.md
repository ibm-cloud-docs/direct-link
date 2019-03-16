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

# Utilisation d'IBM Cloud Direct Link pour se connecter à IBM Cloud Object Storage
{: #using-ibm-cloud-direct-link-to-connect-to-ibm-cloud-object-storage}

Le présent document explique comment configurer {{site.data.keyword.cloud}} Direct Link de manière à pouvoir accéder à IBM Cloud Object Storage (COS). Bien que les méthodes décrites ici ont été conçues et testées avec COS, elles peuvent fonctionner pour certains autres services IBM Cloud.

Selon la règle en cours, IBM Cloud Direct Link rejette l'accès aux noeuds finaux de service privés IBM Cloud, y compris à ceux utilisés par IBM Cloud Object Storage (COS). La technique décrite dans le présent document s'appuie sur un accès indirect à COS via les serveurs hébergés dans le compte IBM Cloud d'un client. Après l'installation et la configuration, chaque serveur de client peut acheminer le trafic de façon bidirectionnelle entre les noeuds finaux de service privés IBM Cloud et leurs réseaux distants connectés par Direct Link.

## Qu'est-ce qu'IBM Cloud Object Storage (COS) ?

IBM Cloud Object Storage (COS) est une plateforme basée sur le Web qui stocke des données non structurées. Elle fournit fiabilité, sécurité, disponibilité et reprise après incident sans réplication manuelle.

Les informations stockées dans IBM Cloud Object Storage sont chiffrées et réparties dans plusieurs emplacements géographiques. Elles sont accessibles via une implémentation de l'API S3. Ce service utilise les technologies de stockage réparti fournies par le service IBM Cloud Object Storage.

IBM COS est disponible dans trois types de configuration : **Inter-régional**, **Régional** et **Site unique**.

 * Le service de type Inter-régional fournit une plus grande durabilité et une meilleure disponibilité que lorsqu'une seule région est utilisée, mais au détriment de temps d'attente légèrement plus élevés. Ce service est disponible aujourd'hui aux Etats-Unis et dans l'UE. (L'utilisation d'un dispositif de routeur virtuel vous permet également d'utiliser Direct Link pour vous connecter à COS dans la région Asie-Pacifique.)

 * Le service de type Régional fournit le contraire : il distribue des objets sur plusieurs zones de disponibilité dans une seule région. Si une région ou une zone de disponibilité donnée est inaccessible, le conteneur d'objets continue de fonctionner sans problèmes. Les éventuelles modifications manquées sont appliquées lorsque le centre de données inaccessible est à nouveau en ligne.

 * Le service de type Site unique offre un accès abordable à Cloud Object Storage dans un centre de données sélectionné.

### Noeuds finaux publics et privés COS
Les noeuds finaux sont des URL que les applications utilisent pour exécuter des commandes COS et échanger des données avec COS. Chaque noeud final utilise la même API pour interagir avec COS.

Les serveurs mis à disposition dans IBM Cloud utilisent les noeuds finaux d'API privés des services, y compris COS. Les noeuds finaux privés fournissent aux serveurs IBM Cloud des clients des connexions directes très rapides avec les services, sans coût supplémentaire lié à la bande passante.

Les noeuds finaux publics COS permettent aux clients IBM Cloud d'accéder aux mêmes données COS que celles qui sont accessibles à partir d'IBM Cloud, mais à partir de n'importe quel emplacement équipé d'Internet.

Deux avertissements s'appliquent aux noeuds finaux publics COS :
 * L'utilisation de noeuds finaux publics peut engendrer des coûts mesurés liés à la bande de passante qui dépassent les frais d'utilisation imposés par le service COS.
 * Bien que toutes les données soient chiffrées pendant leur transfert, les clients peuvent être confrontés à des problèmes de confidentialité ou de restriction réglementaire concernant les données transmises via Internet.

## Qu'est-ce qu'IBM Cloud Direct Link ?
IBM Cloud Direct Link est une suite de produits qui permet aux clients de créer des connexions privées sécurisées entre leurs environnements de réseau distant et leurs déploiements IBM Cloud. Les données échangées par Direct Link ne sont jamais exposées sur Internet.

## Utilisation de Cloud Object Storage (COS) sur IBM Cloud Direct Link
Les ingénieurs IBM ont mis au point une méthode permettant à un client IBM Cloud qui acquiert les services COS et Direct Link d'établir des connexions distantes à des noeuds finaux privés COS. Ce type de connexion étend les avantages des noeuds finaux de service privés, ce qui les rend utilisables par des systèmes client en dehors des installations IBM Cloud.

Cette solution est présentée sous forme de diagramme et décrite dans les sections qui suivent.

### Proxy inverse

**Principe de base : les clients distants transmettent des demandes, y compris des données d'identification sécurisées, via un serveur privé vers COS**

![reverse=proxy](images/reverse-proxy.png)

Les demandes COS HTTPS sont initiées à partir d'un client au niveau d'un site distant. Elles sont transmises de manière sécurisée via IBM Cloud Direct Link, en ciblant l'un des clusters de _serveurs proxy inverses_ déployés dans le compte BM Cloud d'un client. A partir de là, les demandes sont transmises à un noeud final privé COS, elles sont traitées, puis les résultats sont renvoyés au client appelant distant.

Tout exemple de code client qui fonctionne avec COS doit également fonctionner via un serveur _proxy inverse_. Le seul ajustement requise est que, au lieu de cibler l'une des URL de noeud final privé COS publiées par IBM, le client cible l'adresse IP ou l'URL du serveur proxy inverse.

#### Installation de votre proxy inverse Nginx
**NginX** est un serveur Web open source mature, compact et rapide qui excelle dans l'exécution de tâches spécialisées, y compris le rôle de serveur _proxy inverse_ mentionné précédemment.

Les instructions et les informations de configuration indiquées ci-après, relatives à l'installation et la configuration d'un serveur proxy inverse NginX, peuvent fonctionner une fois que vous avez adapté ce dernier à votre environnement. Si vous êtes coincé ou si vous avez besoin d'informations supplémentaires, consultez la partie sur le proxy inverse dans la [documentation Nginx ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://docs.nginx.com/nginx/admin-guide/web-server/reverse-proxy/) ou recherchez des exemples dans [stackoverflow ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")]](http://stackoverflow.com). 

1. Mettez à disposition vos serveurs VSI ou bare avec une version Linux **RHEL** ou **CentOS** minimale (recommandée).
2. Pour chaque VSI, activez les règles de groupe de sécurité suivantes sur l'interface publique : `allow_http`, `allow_https`, `allow_outbound`, `allow_ssh`.
3. Pour chaque VSI, activez les règles `allow_all` et `allow_outbound` sur l'interface privée ; sélectionnez **Sauvegarder**.
4. A l'aide de **PuTTY** dans Windows ou du programme terminal de votre bureau, connectez-vous en tant qu'utilisateur root à votre nouveau serveur via `ssh`.
5. Mettez à niveau votre système d'exploitation (`yum update`).
6. Installez le référentiel EPEL (`yum install epel-release`).
7. Installez NginX (`yum install nginx`).
8. Démarrez NginX (`nginx`) et ouvrez l'adresse IP de votre serveur dans un navigateur.
9. L'emplacement par défaut de `nginx.conf` est `/etc/nginx`. Créez une copie limitée.
10. Déplacez l'exemple de fichier de configuration `nginx.conf` ci-dessous dans `/etc/nginx`.
11. Achetez des certificats SSL via le portail IBM Cloud ou exécutez la commande `yum install easy-rsa` et consultez vos documents en ligne préférés pour obtenir des astuces relatives à la création de certificats autosignés.
12. Ajoutez vos informations de certificat au fichier de configuration `nginx.conf`.
13. Testez la configuration NginX modifiée à l'aide de la commande `nginx -t`.
14. Si le test aboutit, redémarrez `nginx` à l'aide de la commande `nginx -s quit; sleep 3; nginx`.
15. Votre client devrait à présent être en mesure de soumettre des demandes COS aux adresses IP ou aux URL du serveur NginX (proxy).

#### Remarques :

* La solution part du principe que Direct Link a été commandé et correctement déployé, même si elle peut être testée sans ce service.
* La mémoire ou le cache-disque facultatifs peuvent être utilisés avec `proxy_cache`.
* Une valeur `proxy_read_timeout` plus élevée peut s'avérer nécessaire pour des transferts de fichiers plus importants.
* Utilisez `keepalive` ou Pacemaker pour une haute disponibilité (reprise en ligne automatique).

#### Fichier de configuration : `nginx.conf`

L'exemple de fichier de configuration est présenté dans la section suivante. Vous pouvez le copier et le coller.

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

Pour obtenir une liste de points finaux privés à utiliser dans les entrées `proxy_pass` ci-dessus, voir la rubrique en ligne sur les [noeuds finaux COS](https://{DomainName}/docs/infrastructure/cloud-object-storage-infrastructure/endpoints.html#select-regions-and-endpoints).

#### Astuces :

 * Pour accélérer la mise à l'échelle et la résilience, déployez plusieurs serveurs proxy associés à différents points finaux.
 * Utilisez DNS de façon circulaire côté client pour des fonctions de basculement et d'équilibrage de charge rudimentaires.
 * Les serveurs proxy peuvent être placés derrière un dispositif de routeur virtuel à des fins de protection et de journalisation centralisée.

## Gestion et mise à disposition de fonctions IBM Cloud

Cette section contient des liens rapides vers la documentation de certaines offres IBM Cloud PaaS et SaaS auxquelles vous pouvez vous connecter à l'aide d'IBM Cloud Direct Link.

### Comment mettre à disposition des serveurs bare metal

Pour obtenir des instructions détaillées sur la mise à disposition de serveurs bare metal, voir la [documentation sur les serveurs bare metal](https://{DomainName}/docs/bare-metal?topic=bare-metal-about#about).

### Comment mettre à disposition un dispositif de routeur virtuel (VRA)

Pour obtenir des instructions détaillées sur la mise à disposition d'un dispositif de routeur virtuel, voir le [guide d'initiation sur IBM Virtual Router Appliance](https://{DomainName}/docs/infrastructure/virtual-router-appliance/getting-started.html#getting-started).

### Comment mettre à disposition IBM Cloud Object Storage (COS)

 * Pour obtenir des instructions détaillées sur la mise à disposition de COS, voir la [documentation sur Cloud Object Storage](https://{DomainName}/catalog/services/cloud-object-storage).

 * Utilisez l'un des noeuds finaux privés (indiqués précédemment) pour créer une interface avec votre compartiment ou n'importe quel objet dans votre compte COS mis à disposition.
