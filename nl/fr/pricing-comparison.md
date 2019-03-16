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

# Vue d'ensemble des prix de la concurrence
{: #competitive-pricing-overview}

Les entreprises choisissent d'utiliser une interconnexion de cloud privé comme {{site.data.keyword.cloud}} Direct Link, AWS Direct Connect, Google Cloud Interconnect et Microsoft Azure ExpressRoute pour de nombreuses raisons, notamment l'augmentation des
performances réseau, les exigences de sécurité et de confidentialité, ainsi que la réduction des coûts de bande passante. Bien que votre société puisse adopter une architecture de réseau d'interconnexion de cloud privé en raison des avantages qu'elle procure en termes de performance et de sécurité, la réduction connexe des coûts réseau est un paramètre qui favorise clairement IBM Cloud Direct Link dans de nombreux scénarios d'utilisation.  

## Pourquoi choisir IBM Direct Link ? 
{: #why-choose-ibm-cloud-direct-link}

Les tarifs standard d'IBM pour Direct Link reflètent un avantage significatif pour les clients qui utilisent activement des ressources de cloud. Ce fait est confirmé par le calcul du coût total de possession pour un service Direct Link par rapport à la concurrence. 

Une connexion Direct Link dédiée de 10 Gbit/s est actuellement évaluée à 4 999 $ en Amérique du Nord. Cette offre accorde un accès illimité en entrée et en sortie aux ressources IBM Cloud via la connexion. Direct Link ne comporte pas d'option au compteur. 

Les comparaisons suivantes reflètent le point d'inflexion par rapport à l'option la plus large de la concurrence. Le tableau à la fin de cet article présente un récapitulatif détaillé de cette comparaison de prix, par région géographique. 

## AWS
{ #aws}

AWS (comme Google et Microsoft) présente une offre au compteur qui propose une tarification en entrée bon marché mais considérablement variable en sortie. 
* La tarification AWS 10 Gbit/s se compose d'heures de port à 1 620 $ de frais périodiques mensuels (MRC) plus des frais de transfert de 0,02 $/Go à la sortie (en Amérique du Nord). 
* Pour une comparaison à l'identique avec IBM Cloud Direct Link Dedicated, une connexion AWS Direct Connect 10 Gbit/s utilisée à 5 % (ou 170 To) en sortie sur un mois coûterait 5 020 $ à un client, contre 4 999 $ pour une connexion Direct Link 10 Gbit/s. Toute sortie de données au delà de 5 % (ou 170 To) sur un mois favoriserait un modèle de tarification Direct Link au forfait. 
* Pour une comparaison plus parlante, supposons qu'un client AWS utilise 50 % (ou 1,7 Po) de sorties sur un mois, cela lui coûterait 35 620 $, contre le tarif de 4 999 $ pour une connexion Direct Link 10 Gbit/s. 

## Google
{: #google}

Google (comme AWS et Microsoft) présente une offre au compteur qui propose une tarification en entrée bon marché mais considérablement variable en sortie. 

* La tarification Google 10 Gbit/s est définie à 1 750 $ de frais périodiques mensuels (MRC) plus des frais de transfert de 0,02 $/Go à la sortie (en Amérique du Nord). 
* Pour une comparaison à l'identique avec IBM Cloud Direct Link Dedicated, un port Google Cloud (GCP) 10 Gbit/s utilisé à 5 % (170 To) en sortie sur un mois coûterait 5 172 $ à un client, contre 4 999 $ pour une connexion Direct Link 10 Gbit/s.  
* Toute sortie de données au delà de 5 % (ou 170 To) sur un mois favoriserait un modèle de tarification Direct Link au forfait. 
* Pour une comparaison plus parlante, supposons qu'un client Google utilise 50 % (ou 1,7 Po) de sorties sur un mois, cela lui coûterait 35 772 $, contre le tarif de 4 999 $ pour une connexion Direct Link 10 Gbit/s. 

## Microsoft
{ #microsoft}

Microsoft (comme Google et AWS) présente une offre au compteur qui propose une tarification en entrée bon marché mais considérablement variable en sortie. Microsoft offre également un tableau de tarification illimitée. Les deux options sont comparées dans les sections suivantes. 

### Au compteur
{: #metered}

* La tarification Microsoft Azure 10 Gbit/s se compose de frais pour le port (5 000 $ MRC) plus des frais de transfert de 0,02 $/Go à la sortie (en Amérique du Nord). Dès le début, TOUTE donnée transférée à l'extérieur coûtera plus cher qu'IBM Cloud Direct Link !
* Pour une comparaison à l'identique avec IBM Cloud Direct Link Dedicated, un port Microsoft Azure Express Route 10 Gbit/s utilisé à 5 % (ou 170 To) en sortie sur un mois coûterait 8 400 $ à un client, contre 4 999 $ pour une connexion Direct Link 10 Gbit/s.  
* Toute sortie de données au delà de 1 To sur un mois favoriserait un modèle de tarification Direct Link au forfait. 
* Pour une comparaison plus parlante, supposons qu'un client Microsoft Azure utilise 50 % (ou 1,7 Po) de sorties sur un mois, cela lui coûterait 47 500 $, contre le tarif de 4 999 $ pour une connexion Direct Link 10 Gbit/s. 


### En illimité 
{: #unmetered}

* La tarification Microsoft Azure 10 Gbit/s se compose de frais pour le port (51 000 $ MRC) pour des entrées et sorties illimitées. 

* Pour une comparaison à l'identique avec IBM Cloud Direct Link Dedicated, ce coût mensuel s'élève à 51 000 $, contre 4 999 $ pour une connexion Direct Link 10 Gbit/s.  

## Tableau récapitulatif
{: #summary-table}

Faites défiler le tableau horizontalement si nécessaire pour afficher les 5 colonnes de comparaison. 

**Remarques :**
* **Les informations du tableau suivant ont été obtenues à partir des sites Web publics de ces sociétés.**
* **La taille de la connexion 10 Gbit/s est utilisée pour la comparaison de prix.**
* **L'utilisation se base sur un transfert de données soutenu de 5 Gbit/s ou 1,7 Po par mois.**


| Région | IBM illimité | Azure illimité | Azure au compteur | AWS au compteur (intra-région) |
|-----|-----|-----|-----|-----|
| USA | 4 999 $ | 51 300 $ | 47 500 $ | 35 620 $ |
| TOR/MON/AMS | 5 149 $ | 51 300 $ | 47 500 $ | 35 620 $ |
| LON/OSL/STO/MEX | 5 349 $ | 51 300 $ | 47 500 $ | 35 620 $ |
| PAR/FRA/MIL | 5 499 $ | 51 300 $ | 47 500 $ | 35 620 $ |
| SEO | 5 499 $ | 51 300 $ | 90 000 $ | 73 020 $ |
| SNG/HKG | 5 699 $ | 82 000 $ | 90 000 $ | 73 020 $ |
| TOK | 5 999 $ | 82 000 $ | 90 000 $ | 73 020 $ |
| MEL/SYD | 5 999 $ | 82 000 $ | 90 000 $ | 73 020 $ |
| CHE | 5 999 $ | 82 000 $ | 90 000 $ | 78 120 $ |
| SAO | 5 999 $ | 82 000 $ | 242 350 $ | 188 620 $ |


