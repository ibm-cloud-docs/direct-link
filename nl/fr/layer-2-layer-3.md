---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-30"

keywords: layer 2, layer 3, interconnect, partner, multi-cloud, other clouds, BGP, XCR

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Comparaison des connexions de couche 2 et 3 pour Direct Link
{: #comparing-layer-2-layer-3}

{{site.data.keyword.cloud}} Direct Link accepte les interconnexions de partenaire de couche 2 et 3 OSI à partir des fournisseurs de services réseau (NSP). Certains de ces fournisseurs proposent des services pour ces deux couches sur des réseaux différents, même si certains fournisseurs peuvent avoir choisi de ne **pas** interconnecter l'ensemble de leurs réseaux dans {{site.data.keyword.cloud_notm}}. 

Lors de la planification de votre déploiement {{site.data.keyword.cloud_notm}} Direct Link, prenez en compte les caractéristiques associées connexions de couche 2 et 3 afin de pouvoir créer un déploiement qui répond au mieux à vos besoins.

## Considérations liées aux connexions de couche 2
{: #layer-2-networks}

Pour chaque circuit virtuel sur VLAN (que vous créez avec une interconnexion partenaire de couche 2), vous devez configurer et établir une session BGP entre vos routeurs sur site et me routeur XCR IBM Cloud. IBM Cloud fournit une affectation IPv4 `/31` pour l'établissement d'une session BGP avec votre routeur.

* Les réseaux de couche 2 offre des options pour les connexions un à un simples entre les entreprises et {{site.data.keyword.cloud_notm}}. 
* Les services de couche 2 reposent sur des réseaux locaux virtuels (VLAN) à la place d'adresses IP. 
* Les services de couche 2 peuvent présenter des coûts et des temps d'attente plus faibles, et peuvent entraîner moins de consommer moins de temps système que des services de couche 3. 
* Les réseaux de couche 2 n'imposent pas de restrictions sur les fonctions de couche 3 qu'une entreprise peut activer.

## Considérations liées aux connexions de couche 3
{: #layer-3-networks}

Pour les connexions de couche 3, pour chaque circuit virtuel, votre fournisseur de services établit une session BGP entre des routeurs XCR IBM Cloud et les routeurs de périphérie du fournisseur. Vous n'avez pas besoin de configurer BGP avec IBM Cloud pour votre routeur sur site car votre fournisseur de services s'occupe de gérer la configuration BGP vers IBM Cloud.

* Les réseaux VPN ou AVPN d'IP de couche 3 activent une connectivité "any-to-any" (de tout point à tout point). 
* Les réseaux de couche 3 nécessitent que le fournisseur de services réseau conserve une session BGP entre l'entreprise et {{site.data.keyword.cloud_notm}}. 
* Certains fournisseurs de services réseau peuvent restreindre certaines fonctionnalités sur leur réseau lors de l'utilisation de connexions de couche 3, comme l'ajout en préfixe du numéro ASN, la tunnellisation du routage mondial sortant (GRE) et ainsi de suite. Veillez à demander à votre fournisseur les éventuelles restrictions.

## Tableau des interconnexions partenaire
{: #partner-interconnection-table}

Le tableau suivant récapitule le type des connexions fournies par chaque partenaire {{site.data.keyword.cloud_notm}}. 

| Partenaires | Type d'interconnexion |  
|-------|-------|
| AT&T NetBond® for Cloud | Couche 3 |
| AT&T Cloud Gateway (anciennement appelé RedFringe)| Couche 3 |
| Bell Canada | Couche 3 | 
| British Telecom | Couche 3 | 
| CenturyLink IP VPN | Couche 3 | 
| CenturyLink Dynamic Connections | Couche 2 | 
| Chief Telecomm | Couche 2 |
| Colt | Couche 2 | 
| Console Connect by PCCW | Couche 2 |
| Digital Realty Service Exchange | Couche 2 | 
| Epsilon | Couche 2 | 
| IBM BlueFringe | Couche 3 | 
| Intercloud | Couche 3 |
| Megaport | Couche 2 |
| MWS GNPP | Couche 3 |
| Neutrona | Couche 2 |
| NTT | Couche 3 |
| PacketFabric | Couche 2 |
| Softbank | Couche 3 |
| SES Networks | Couche 2 |
| Tata IZO™ Private Connect  | Couche 3 | 
| Telia | Couche 3 |
| Telstra | Couche 3 |
| Tokai | Couche 2 | 
| Verizon SCI| Couche 3 |
| Zayo Cloud Link | Couche 2 |
