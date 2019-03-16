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

# Vue d'ensemble des offres Direct Link
{ #overview-of-direct-link-offerings}

Les offres {{site.data.keyword.cloud}} Direct Link fournissent la connectivité depuis une source externe vers le réseau privé IBM Cloud d'un client. Direct Link peut être envisagé comme une alternative à une solution de réseau privé virtuel (VPN) classique de site à site, conçue pour les clients ayant besoin d'une connectivité à plus haut débit plus cohérente entre un réseau privé et leurs environnements IBM Cloud. Il existe quatre types de connexion disponibles :
 
 * **IBM Cloud Direct Link Exchange** permet aux clients de tirer parti d'un fournisseur Exchange pour assurer la connectivité à leur réseau IBM Cloud. Un fournisseur Exchange est un opérateur ou un fournisseur réseau déjà connecté au réseau IBM Cloud via des liaisons à service partagé de grande capacité. Les clients peuvent généralement acheter un circuit virtuel auprès de ce fournisseur pour obtenir une connectivité à coût réduit, car la connectivité physique de {{site.data.keyword.BluSoftlayer_notm}} au fournisseur Exchange est déjà en place, partagée avec d'autres clients.
 
 * **IBM Cloud Direct Link Connect** permet aux clients de tirer parti d'une connexion via nos partenaires qui possèdent et exploitent un réseau basé sur des installations. Avec IBM Cloud Direct Link Connect, IBM et le partenaire se connectent aux clients au niveau des couches 2 et 3 via des interfaces réseau-réseau (NNI) 10G doubles de couche 2.
 
 * **IBM Cloud Direct Link Dedicated** permet aux clients de terminer une interconnexion fibre dédiée en mode unique dans leur propre réseau privé IBM Cloud.
 
 * **IBM Cloud Direct Link Dedicated Hosting** offre une connectivité similaire à IBM Cloud Direct Link Dedicated, mais le point de connexion est adjacent à un centre de données {{site.data.keyword.BluSoftlayer_notm}}, ce qui améliore le temps d'attente pour les cas d'utilisation à performance accrue. IBM Cloud offre une large gamme de services de colocalisation personnalisables avec cette solution.
  
Le service IBM Cloud Direct Link est un service OSI à trois couches routé. Il offre une connexion directe au réseau principal du réseau privé {{site.data.keyword.BluSoftlayer_notm}}, avec un faible temps d'attente et un débit accéléré jusqu'à 10 Gbit/s.
Pour plus de flexibilité dans la création de cette connectivité à trois couches, IBM Cloud Direct Link permet aux clients d'utiliser :
 * Une double adresse IP pour les hôtes distants
 * La conversion NAT
 * La tunnellisation pour BYOIP
 
 Pour des descriptions détaillées de chaque offre, voir [A propos d'IBM Cloud Direct Link](/docs/infrastructure/direct-link?topic=direct-link-about-ibm-cloud-direct-link). 
