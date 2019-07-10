---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-02"

keywords: overview, connectivity, private network, site-to-site, Exchange, Connect, Dedicated, Hosting, OSI, Layer-3, partners, NNI, latency, backbone

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Vue d'ensemble des offres Direct Link
{: #overview-of-direct-link-offerings}

Les offres {{site.data.keyword.cloud}} Direct Link fournissent la connectivité depuis une source externe vers le réseau privé IBM Cloud d'un client. Direct Link peut être envisagé comme une alternative à une solution de réseau privé virtuel (VPN) classique de site à site, conçue pour les clients ayant besoin d'une connectivité à plus haut débit plus cohérente entre un réseau privé et leurs environnements IBM Cloud. Il existe quatre types de connexion disponibles :
 
 * **IBM Cloud Direct Link Exchange** permet aux clients d'utiliser un fournisseur Exchange pour assurer la connectivité à leur réseau IBM Cloud. Un fournisseur Exchange est un fournisseur de colocalisation ou de centre de données déjà connecté au réseau {{site.data.keyword.cloud_notm}} via des liaisons à service partagé de grande capacité (également appelées _interface réseau à réseau_ ou NNI). Les clients peuvent généralement acheter un circuit virtuel auprès de ce fournisseur pour obtenir une connectivité à coût réduit, car la connectivité physique de {{site.data.keyword.cloud_notm}} au fournisseur Exchange est déjà en place, partagée avec d'autres clients.
 
 * **IBM Cloud Direct Link Connect** permet aux clients d'utiliser une connexion via nos partenaires transporteurs qui possèdent et exploitent un réseau basé sur des installations. Un fournisseur Connect est un fournisseur de services réseau (NSP) déjà connecté au réseau {{site.data.keyword.cloud_notm}} via des liaisons à service partagé de grande capacité (également appelées _interface réseau à réseau_ ou NNI). Les clients peuvent généralement acheter un circuit virtuel auprès de ce fournisseur pour obtenir une connectivité à coût réduit, car la connectivité physique depuis {{site.data.keyword.cloud_notm}} jusqu'au fournisseur Connect est déjà en place, partagée avec d'autres clients.
 
 * **IBM Cloud Direct Link Dedicated** permet aux clients de terminer interconnexion fibre à service exclusif dans le réseau {{site.data.keyword.cloud_notm}}. Cette offre peut être utilisée par des clients disposant de locaux de colocalisation adjacents aux points de présence et centres de données IBM Cloud ; il en est de même pour les fournisseurs de services réseau délivrant des circuits dans les locaux ou les centres de données des clients.
 
 * **IBM Cloud Direct Link Dedicated Hosting** offre une connectivité similaire à {{site.data.keyword.cloud_notm}} Direct Link Dedicated, mais le point de connexion est adjacent à un centre de données {{site.data.keyword.cloud_notm}}, ce qui améliore le temps d'attente pour les cas d'utilisation à performance accrue. {{site.data.keyword.cloud_notm}} offre une large gamme de services de colocalisation personnalisables avec cette solution.
  
Le service {{site.data.keyword.cloud_notm}} Direct Link est un service OSI à trois couches routé. Il offre une connexion directe au réseau principal du réseau privé {{site.data.keyword.cloud_notm}}, avec un faible temps d'attente et un débit accéléré jusqu'à 10 Gbit/s.
Pour plus de flexibilité dans la création de cette connectivité à trois couches, {{site.data.keyword.cloud_notm}} Direct Link permet aux clients d'utiliser :
 * Une double adresse IP pour les hôtes distants
 * La conversion NAT
 * La tunnellisation pour BYOIP
 
 Pour des descriptions détaillées de chaque offre, voir [A propos d'IBM Cloud Direct Link](/docs/infrastructure/direct-link?topic=direct-link-about-ibm-cloud-direct-link).
