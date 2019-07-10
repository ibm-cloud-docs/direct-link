---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-02"

keywords: order, provider, capabilities, Exchange, cross-connect, locations, PoP, datacenter, data, center, pricing

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Comment commander IBM Cloud Direct Link Exchange ?
{: # how-to-order-ibm-cloud-direct-link-exchange}

1. Vérifiez que votre fournisseur de réseau peut accéder au point de présence (PoP) approprié et établir une interconnexion avec le fournisseur Exchange associé.
2. Utilisez le [portail client![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/) pour ouvrir une demande pour {{site.data.keyword.cloud}} Direct Link Exchange et remplissez les informations demandées. (Vous pouvez faire appel à des ingénieurs commerciaux IBM pour vous aider). Si vous utilisez le fournisseur Equinix, vous pouvez aussi utiliser le système de [commande automatisée](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix).
3. Contactez votre fournisseur Exchange et négociez la connectivité à votre échange.
4. Commandez la connectivité entre votre fournisseur de réseau et le fournisseur Exchange.
5. Commandez un "circuit virtuel" via le fournisseur Exchange et indiquez l'ID de ticket de la demande {{site.data.keyword.BluSoftlayer_notm}} Direct Link comme "ID de la demande" ou "ID d'autorisation"
6. L'affectation d'une adresse IP sur l'infrastructure réseau {{site.data.keyword.BluSoftlayer_notm}} sera effective dans les trois jours ouvrables une fois la demande de circuit virtuel terminée.
 
## Emplacements
{: #exchange-locations}
 
 Le tableau présente les centres de données IBM Cloud qui offrent la connectivité Direct Link Exchange :
 
| Fournisseur Exchange	| Code de centre de données IBM |
|-------------|-----------------------|
| AT Tokyo | Tokyo 2 |
| Ascenty | Sao Paulo 1* |
| Cologix | Montréal 2, Toronto 2 |
| Cyrus One | Dallas 13 |
| DE-CIX | Francfort 3 |
| Equinix | Hong Kong 1,Singapour 2, Sydney 2, Tokyo 1, Amsterdam 2, Paris 2, Chicago 1, Dallas 3, New York City 2, New York City 3, Sao Paulo 2, San José 2, Toronto 2, Washington DC 2, Londres 1, Francfort 3 |							
| InterXion | Francfort 1, Stockholm 1 |
| KINX	| Séoul 2 |
| NextDC | Melbourne 2, Sydney 3 |
| SK C&C | Séoul 1 |

* Bientôt disponible

## Tarification
{: #exchange-pricing}

Pour obtenir des informations de tarification, voir la [rubrique sur la tarification](/docs/infrastructure/direct-link?topic=direct-link-pricing-for-ibm-cloud-direct-link#pricing-for-direct-link-exchange).
