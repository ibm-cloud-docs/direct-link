---

copyright:
  years: 2018, 2019
lastupdated: "2019-03-29"


keywords: Dedicated, Hosting, finalize, questionnaire, Network Engineering, billing, fees, VRF, BGP, ticket, cross-connects, datacenters, data, center, backhaul, single mode, single-mode, fiber, Letter of Authorization, LOA, contract

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Limitations d'IBM Cloud Direct Link Dedicated Hosting
{: #ibm-cloud-direct-link-dedicated-hosting-questionnaire}

Merci d'avoir ouvert une demande pour {{site.data.keyword.cloud}} Direct Link Dedicated Hosting. Afin de pouvoir finaliser votre demande, nous aurions besoin d'informations supplémentaires. Vous pouvez parler avec un ingénieur à tout moment durant le questionnaire. Une fois le questionnaire rempli, il sera examiné par notre équipe d'ingénieurs spécialisés dans la conception de cloud et transmis à l'équipe d'ingénieurs spécialistes des réseaux pour implémentation.

## Confirmations
{: #dedicated-hosting-acknowledgements}

1. Les frais indiqués dans ce questionnaire couvrent le coût lié à la résiliation du service dans l'infrastructure réseau IBM Cloud. Les coûts de colocalisation, y compris les meubles, les interconnexions, etc., incluent des frais mensuels et ponctuels indiqués séparément dans le cadre d'un contrat de colocalisation.

2. IBM Cloud Direct Link Dedicated Hosting fournit des interconnexions 1 Gbit/s ou 10 Gbit/s par fibre dans le réseau privé IBM Cloud. Vous devez fournir un routeur ou un commutateur de couche 3 pouvant prendre en charge des liaisons montantes SMF (Single Mode Fiber). La délai de déploiement peut varier en fonction de votre fournisseur de circuit. Le déploiement de ce service prend généralement 30 à 60 jours.

3. Direct Link Dedicated Hosting requiert l'utilisation d'une instance VRF (Virtual Routing and Forwarding). Cela permet au client de définir ses propres adresses IP distantes pour les utiliser dans son réseau distant ; cependant, sachez que si vous utilisez le réseau 10.x.x.x, vous ne pouvez toujours pas créer un chevauchement avec vos hôtes dans IBM Cloud ni avec le réseau des services IBM Cloud (10.0.0.0/14, 10.198.0.0/15 et 10.200.0.0/14). La transition de votre compte vers une instance VRF requiert une brève indisponibilité du réseau privé lorsque chaque VLAN est migré dans la nouveau configuration. L'équipe d'ingénieurs spécialistes des réseaux travaillera avec vous afin de définir une fenêtre pour cette activité.

4. VRF modifie le comportement d'IBM Cloud SSL, PPTP et IPsec VPN. En principe, ces réseaux fonctionnent lorsqu'une connexion VPN est établie avec le même emplacement de centre de données que celui où résident les ressources de calcul qui font l'objet d'un accès, mais ils n'autorisent pas l'accès mondial.  En guise d'alternative, vous pouvez utiliser Direct Link à proprement parler pour gérer vos serveurs ou pour exécuter votre propre solution VPN (par exemple Vyatta) pouvant être configurée avec différents types de VPN. 

5. Direct Link Dedicated Hosting requiert BGP afin d'implémenter des routes vers le réseau distant d'un client. IBM Cloud n'implémente pas de filtres sur les annonces émises vers IBM Cloud.  IBM Cloud prévient tous les sous-réseaux privés affectés à votre compte. Les clients doivent gérer correctement les annonces émises vers IBM Cloud.

6. IBM Cloud fournit des liaisons montantes doubles, une pour chacun des routeurs d'interconnexion d'IBM Cloud, afin de permettre aux clients d'établir une connectivité redondante. Cette opération est effectuée sur le(s) routeur(s) du client via des sessions BGP en optimisant les fonctions ECMP ou en pondérant simplement les connexions.

7. Le réseau de services IBM Cloud n'est pas directement accessible depuis votre réseau Dedicated Hosting ou vos réseaux distants.

8. IBM Cloud ne vous autorise pas à renvoyer le trafic entre vos sites distants via le réseau principal IBM Cloud. Le service Direct Link a été conçu pour permettre à vos réseaux distants de communiquer en privé avec votre infrastructure IBM Cloud.

9. IBM Cloud offre Direct Link avec l'option Routage local ou Routage mondial. Précisez le module de routage dont vous avez besoin et confirmez que vous acceptez les plans de bande passante associés aux modules consultables dans la documentation suivante : ibm.biz/DirectLink-Docs.

10. Indiquez la quantité de trafic que vous prévoyez de faire transiter par votre Direct Link et vers quels centres de données IBM Cloud vous prévoyez d'envoyer ce trafic.

11. Si vous n'achetez pas de services de colocalisation via IBM Cloud, il vous incombe de commander et de payer les interconnexions entre votre environnement et IBM Cloud. Une fois que vous serez connecté, nous vous fournirons une lettre d'autorisation détaillant notre approbation de votre connexion et de l'emplacement auquel vous devez vous connecter.

12. Confirmez que vous acceptez la tarification suivante pour Direct Link :
 * 1 Gbit/s : _TARIFICATION BASEE SUR L'EMPLACEMENT_ 
 * 2 Gbit/s : _TARIFICATION BASEE SUR L'EMPLACEMENT_
 * 5 Gbit/s : _TARIFICATION BASEE SUR L'EMPLACEMENT_
 * 10 Gbit/s : _TARIFICATION BASEE SUR L'EMPLACEMENT_
 * Option Routage mondial facultative
