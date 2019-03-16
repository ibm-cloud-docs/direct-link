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

# Limitations connues
{: #known-limitations}

Cette section commence avec une présentation des limitations qui s'appliquent à l'ensemble des trois offres {{site.data.keyword.cloud}} Direct Link, puis indique les détails relatifs à certaines limitations de chaque offre individuellement.

## Limitations générales d'IBM Cloud Direct Link
 * Chaque connexion IBM Cloud Direct Link nécessite une commande unique. Si vous avez besoin de plusieurs connexions, créez une commande IBM Cloud Direct Link pour chaque connexion.
 * Le réseau de services {{site.data.keyword.BluSoftlayer_notm}} n'est pas accessible directement depuis vos réseaux distants.
 * {{site.data.keyword.BluSoftlayer_notm}} n'autorise pas les clients à renvoyer le trafic entre leurs sites distants via le réseau principal {{site.data.keyword.BluSoftlayer_notm}}. Le produit IBM Cloud Direct Link est censé laisser vos réseaux distants communiquer en privé avec votre infrastructure {{site.data.keyword.BluSoftlayer_notm}}.
 * IBM Cloud Direct Link nécessite que vous utilisiez une instance VRF (Virtual Routing and Forwarding).
 * VRF n'est pas entièrement compatible avec les services VPN SSL, PPTP et IPSec de {{site.data.keyword.BluSoftlayer_notm}}.
 * VRF n'est pas compatible avec la fonction Spanning VLAN de compte à compte {{site.data.keyword.BluSoftlayer_notm}}.
 * IBM Cloud Direct Link nécessite BGP afin d'établir les routes vers le réseau distant d'un client.
 * Les modifications apportées à l'infrastructure IBM Cloud Direct Link doivent être effectuées entre 8h00 et 17h00, heure du centre des États-Unis.
 
## Limitations d'IBM Cloud Direct Link Exchange et Direct Link Connect
 * Les clients sont redevables de tous les frais associés à l'accessibilité du POP depuis un réseau distant et de tous les frais encourus avec le fournisseur Cloud Exchange.
 * {{site.data.keyword.BluSoftlayer_notm}} ne colocalisera pas d'équipement du client dans les POP de notre réseau. Les clients doivent travailler avec leur fournisseur pour déterminer s'ils ont besoin de colocaliser des équipements sur le site où se trouve le PoP du réseau {{site.data.keyword.BluSoftlayer_notm}}.
 * La disponibilité de Direct Link Cloud Exchange varie suivant les emplacements. Les clients peuvent contacter leur chargé de clientèle IBM Cloud pour confirmer la disponibilité actuelle ou à venir.
 
## Limitations d'IBM Cloud Direct Link Dedicated
 * Les frais {{site.data.keyword.BluSoftlayer_notm}} pour la solution IBM Cloud Direct Link Dedicated couvrent le coût du port de terminaison sur l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}. Les clients sont redevables de tous les frais associés à l'accessibilité du PoP depuis un réseau distant et toutes les interconnexions nécessaires sur le site du PoP.  {{site.data.keyword.BluSoftlayer_notm}} ne commandera pas d'interconnexion pour le compte d'un client.
 * {{site.data.keyword.BluSoftlayer_notm}} ne colocalisera pas d'équipement du client dans les PoP de notre réseau. Les clients doivent travailler avec leur fournisseur pour déterminer s'ils ont besoin de colocaliser des équipements sur le site où se trouve le PoP du réseau {{site.data.keyword.BluSoftlayer_notm}}.

## Limitations d'IBM Cloud Direct Link Dedicated Hosting
 * La solution IBM Cloud Direct Link Dedicated Hosting nécessite un contrat spécifique entre {{site.data.keyword.BluSoftlayer_notm}} et le client. Ce contrat précise les dispositions du produit, la tarification de l'environnement de colocalisation et la période d'engagement pour les services. Un contrat de 6, 9 ou 12 mois est requis.
 * La connectivité du fournisseur est limitée aux fournisseurs en réseau du centre de données sélectionné.
