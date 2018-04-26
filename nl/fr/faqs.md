---

copyright:
 years: 2017, 2018
lastupdated: "2018-04-05"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Foire aux questions

Cette section contient les réponses aux questions les plus fréquentes sur IBM Cloud Direct Link. 

## Comment fonctionne IBM Cloud Direct Link ?
Pour chaque client Direct Link, l'équipe IBM Cloud affecte un petit sous-réseau privé pour construire un réseau point à point entre le routeur d'interconnexion (XCR) {{site.data.keyword.BluSoftlayer_notm}} et le routeur edge du client (CER). Puis, {{site.data.keyword.BluSoftlayer_notm}} et le client configurent BGP pour échanger les routes entre les environnements. Et enfin, {{site.data.keyword.BluSoftlayer_notm}} met le client dans une instance VRF pour permettre l'implémentation de routes non uniques vers l'espace d'adresse privé du réseau distant de ce client.

## Est-ce qu'IBM Cloud mesure la bande passante pour les produits Direct Link ?
Oui. IBM Cloud mesure toute la bande passante sortante sur les produits Direct Link. La bande passante entrante est gratuite et ne fait pas l'objet de mesures.

## Quels sont les frais supplémentaires encourus pour les parties prenantes avec Direct Link ?
Vous pourrez avoir des frais supplémentaires facturés par votre fournisseur d'échange ou votre fournisseur de services réseau. Consultez votre ou vos fournisseurs pour obtenir les informations concernant leurs tarifs.

## Comment peut-on établir la redondance avec IBM Cloud Direct Link ?
Vous pouvez établir la redondance avec Direct Link en connectant plusieurs fournisseurs IBM Cloud Direct Link Dedicated ou Exchange à {{site.data.keyword.BluSoftlayer_notm}}. Vous pouvez également tirer parti de l'un des fournisseurs IBM Cloud Direct Link qui ajoute de la redondance à votre service.

## Quelle est la différence entre un routage "local" par défaut et le module complémentaire de routage mondial Global Routing ?
Avec notre offre Direct Link standard, vous pouvez envoyer du trafic entre les centres de données de votre région sélectionnée. Si vous devez accéder à d'autres centres de données situés hors de la région spécifiée, vous devez commander le module complémentaire Global Routing. Ce modèle est basé sur des listes de contrôle d'accès (ACL) mises en place lors de votre commande de connexion Direct Link. 

## Comment les dépassements de bande passante sortante sont-ils facturés pour le module complémentaire Global Routing ?
Les dépassements sont facturés par mois si vous dépassez la bande passante qui vous est allouée, mais uniquement pour la bande passante sortante. La bande passante entrante est gratuite et ne fait pas l'objet de mesures. La bande passante sortante est facturée en fonction du taux le plus élevé des deux régions parcourues par vos données.  Par exemple, si votre solution Direct Link est configurée dans DAL03 et que vos données circulent via Mexico, le débit de bande passante vous sera facturé au tarif de Mexico.

## Pourquoi un module complémentaire Global Routing ?
Nous avons ajouté le module complémentaire Global Routing pour éviter à nos clients de faire l'expérience de coûts de données imprévus lorsqu'ils franchissent la région de leur centre de données. Cela permet de réduire les coûts pour la majorité de nos clients tout en leur donnant la possibilité d'être présents au niveau international pour atteindre facilement toutes les régions du monde. En règle générale, un client ne nécessite qu'un module de bande passante local.

## Que sont les options de routage local et de routage mondial ?
Les options de routage local et de routage mondial sont sélectionnées par tous les clients lorsqu'ils commandent le service Direct Link. Si les clients ont besoin de router leur trafic hors du point de présence (POP) dans la zone dans laquelle ils commandent Direct Link, ils doivent ajouter l'option de routage mondial, autrement leur trafic sera limité aux services fournis par le POP local.

Chaque mois, tous les clients utilisant des circuits 1G obtiennent 10 To de trafic sortant gratuit, les clients utilisant des circuits 10G en obtiennent 50 To. Les dépassements sont basés sur le tableau suivant avec le taux en vigueur le plus élevé du marché. Si vous sélectionnez le routage mondial, vous n'êtes pas facturé pour le trafic sortant local, mais uniquement pour le trafic en provenance ou à destination d'un emplacement qui ne figure pas dans le POP local.

|Marché de données 1|Marché de données 2|Marché de données 3|
|---|---|---|
|<ul><li>DAL</li><li>WDC</li><li>SEA</li><li>SJC</li><li>NYC*</li><li>CHI*</li><li>DEN*</li><li>MIA*</li><li>ATL*</li><li>LAX*</li><li>TOR</li><li>MON</li><li>AMS</li><li>FRA</li></ul>|<ul><li>TOK</li><li>HKG</li><li>PAR</li><li>MIL</li><li>STK*</li><li>OSL</li></ul>|<ul><li>MEX</li><li>SAO</li><li>SYD</li><li>MEL</li><li>PER*</li><li>CHE</li><li>SEO</li></ul>|
**Tableau 1 : Niveaux d'utilisation**<br/>
Les offres Direct Link sur les marchés marqués d'un astérisque (*) DOIVENT commander le module complémentaire de routage mondial Global Routing.

## Si je suis connecté à Direct Link NSP ou Direct Link Cloud Exchange dans une région telle que Dallas, ai-je accès à d'autres régions aux États-Unis via Direct Link ?
Oui, vous pouvez accéder à des zones situées hors de votre région si vous choisissez le module complémentaire Global Routing. Si cette option n'est pas sélectionnée, votre trafic Direct Link sera limité à la région du POP que vous avez sélectionné.

## Puis-je me connecter à une région disponible à partir d'un emplacement Direct Link donné ?
Oui, à condition de commander Direct Link avec le module complémentaire Global Routing.

## Puis-je limiter les régions auxquelles Direct Link peut accéder ?
Non. IBM Cloud offre deux options : (1) une seule région uniquement ou (2) toutes les régions avec le module complémentaire Global Routing.

## Que se passe-t-il si j'ai utilisé le processus de commande automatisé pour Equinix Cloud Exchange et qu'on m'a attribué un sous-réseau qui chevauche mon réseau interne ?

A compter de mars 2018, il est recommandé d'annuler votre commande automatisée et de soumettre un nouveau ticket pour remplir le questionnaire Direct Link. Vous devez indiquer si vous préférez un autre sous-réseau dans la plage 10.254.x.x ou 172.32.x.x.

## Quelle est la différence entre Direct Link Exchange et Direct Link Connect ?

Ces deux services sont relativement peu coûteux, tolérants aux temps de latence et offrent un accès rapide aux avantages d'IBM Cloud Direct Link similaire. En bref, Exchange fait appel à des fournisseurs de centres de données et Connect fait appel à des opérateurs télécoms. Voici quelques détails supplémentaires : 

**Direct Link Exchange** s'adresse aux clients qui préfèrent utiliser un échange à l'intérieur d'un centre de données. Avec un service Exchange, les clients peuvent activer rapidement la connectivité multi-cloud à leur colocation, car les circuits sous-jacents sont déjà mis à disposition (ces autres fournisseurs de cloud doivent déjà avoir une interconnexion physique présente dans l'installation).

Direct Link Exchange peut permettre un environnement d'utilisation partagée et multi-cloud grâce à un seul port d'échange cloud, créé par une connexion NNI à la couche 2 entre IBM Cloud et le fournisseur de services Cloud Exchange. Les vitesses de port disponibles vont jusqu'à 1 Gb.  

**Direct Link Connect** s'adresse aux clients qui préfèrent utiliser leur réseau existant entre leur propre déploiement sur site et IBM Cloud. Avec le service Direct Link Connect, les clients peuvent utiliser les réseaux de télécommunication nouveaux et existants (tels que MPLS) pour activer rapidement IBM Cloud, en tirant parti des circuits sous-jacents déjà mis à disposition.

Avec Direct Link Connect, IBM et le partenaire se connecteront au client aux couches 2 et 3 par le biais d'interfaces réseau à réseau (NNI) 10G doubles de couche 2, exploitées par des partenaires IBM dans des installations dans le monde entier. Les vitesses de port disponibles vont jusqu'à 5 Gbps.

