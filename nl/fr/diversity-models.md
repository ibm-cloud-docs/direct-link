---

copyright:
  years: 2018
lastupdated: "2018-05-30"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Modèles de diversité et de redondance dans Direct Link

Le présent document contient une série de schémas relatifs à des questions de redondance et de diversité, destinés à vous aider à trouver un modèle à utiliser pour créer le déploiement Direct Link le plus adapté à vos besoins. Les schémas sont organisés par niveaux croissants de complexité et en fonction de l'offre Direct Link qu'ils illustrent. Direct Link n'est pas un service intrinsèquement redondant au niveau du routeur XCR, il incombe aux clients de créer de la redondance via leurs schémas BGP.  

## Section 1 : Remarques relativement simples pour obtenir de la diversité

Les configurations décrites dans ce groupe s'appuient sur le fait que tous les actifs se trouvent dans le même emplacement de point de présence et sur le même marché mondial. 

**Figure 1 : Direct Link Exchange avec diversité, dans le même emplacement de point de présence (hors zone de disponibilité)**

![Exchange avec diversité dans le même emplacement de point de présence](/images/exchange-diversity-same-pop.png)

**Figure 2 : Direct Link Connect avec diversité, dans le même emplacement de point de présence (hors zone de disponibilité)**

![Connect avec diversité dans le même emplacement de point de présence](/images/connect-diversity-same-pop.png)

**Figure 3 : Direct Link Dedicated avec diversité, dans le même emplacement de point de présence (hors zone de disponibilité)**

![Dedicated avec diversité dans le même emplacement de point de présence](/images/dedicated-diversity-same-pop.png)

## Section 2 : Diversité qui inclut des zones de disponibilité et les options Routage mondial

Les configurations décrites dans ce groupe offrent des options de connexion dans les zones de disponibilité et les marchés locaux.

### Partie A : Diversité dans une zone de disponibilité locale

**Figure 4 : Direct Link Exchange avec diversité dans une zone de disponibilité locale (WDC, DAL, FRA, LON)**

![Exchange avec diversité dans la zone de disponibilité locale](/images/exchange-diversity-local-az.png)

**Figure 5 : Direct Link Connect avec diversité dans une zone de disponibilité locale (WDC, DAL, FRA, LON)**

![Connect avec diversité dans la zone de disponibilité locale](/images/connect-diversity-local-az.png)

**Figure 6 : Direct Link Dedicated avec diversité dans une zone de disponibilité locale (WDC, DAL, FRA, LON)**

![Dedicated avec diversité dans la zone de disponibilité locale](/images/dedicated-diversity-local-az.png)

### Partie B : Diversité dans différents marchés locaux avec l'option Routage mondial

**Figure 7 : Direct Link Connect avec diversité et l'option Routage mondial**

![Connect avec diversité et l'option Routage mondial](/images/connect-diversity-global.png)

**Figure 8 : Direct Link Exchange avec diversité et l'option Routage mondial**

![Exchange avec diversité et l'option Routage mondial](/images/exchange-diversity-global.png)

**Figure 9 : Direct Link Dedicated avec diversité et l'option Routage mondial**

![Dedicated avec diversité et l'option Routage mondial](/images/dedicated-diversity-global.png)

## En savoir plus sur ECMP

ECMP est une fonction de BGP. Certains clients nous ont demandé s'il était possible d'utiliser ECMP pour obtenir de la redondance. Utilisé seul, ECMP n'est pas suffisant. Cette section explique pourquoi. 

**Q : ECMP doit-il être utilisé pour créer des connexions redondantes ? Existe-t-il d'autres méthodes ?**

ECMP n'a pas été conçu pour créer des connexions redondantes mais pour obtenir l'équilibrage de la charge sur deux liaisons. Avec ECMP on IBM Cloud, les deux connexions doivent aller jusqu'au même routeur d'interconnexion (XCR) IBM Cloud, ce qui en fait un point de défaillance unique. (En d'autres termes, ECMP peut être mis à disposition uniquement sous forme de deux sessions sur le même routeur XCR IBM Cloud.)

**Figure 10 : Mise à disposition d'ECMP**

![Modèle dédié pour ECMP](/images/ecmp-without-diversity.png)

### Comment obtenir diversité et redondance

Si vous recherchez une haute disponibilité ou une redondance totale, configurez deux liaisons dans des routeurs XCR différents dans le même centre de données (par exemple, DAL03). Ensuite, effectuez une reprise en ligne si nécessaire à l'aide des configurations BGP. 

**Figure 11 : ECMP avec des routeurs XCR doubles**

![Modèle XCR double pour ECMP](/images/ecmp-with-diversity.png)
