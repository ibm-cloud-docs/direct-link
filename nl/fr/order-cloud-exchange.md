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

# Comment commander IBM Cloud Direct Link Exchange ?
{ # how-to-order-ibm-cloud-direct-link-exchange}

1. Vérifiez que votre fournisseur de réseau peut accéder au point de présence (PoP) approprié et établir une interconnexion avec le fournisseur Exchange associé.
2. Utilisez le [portail client![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/) pour ouvrir une demande pour {{site.data.keyword.cloud}} Direct Link Exchange et remplissez les informations demandées. (Vous pouvez faire appel à des ingénieurs commerciaux IBM pour vous aider). Si vous utilisez le fournisseur Equinix, vous pouvez aussi utiliser le système de [commande automatisée](/docs/infrastructure/direct-link?topic=direct-link-provisioning-ibm-cloud-direct-link-exchange-for-equinix).
3. Contactez votre fournisseur Exchange et négociez la connectivité à votre échange.
4. Commandez la connectivité entre votre fournisseur de réseau et le fournisseur Exchange.
5. Commandez un "circuit virtuel" via le fournisseur Exchange et indiquez l'ID de ticket de la demande {{site.data.keyword.BluSoftlayer_notm}} Direct Link comme "ID de la demande" ou "ID d'autorisation"
6. L'affectation d'une adresse IP sur l'infrastructure réseau {{site.data.keyword.BluSoftlayer_notm}} sera effective dans les trois jours ouvrables une fois la demande de circuit virtuel terminée.
 
## Emplacements
 
 Le tableau présente les centres de données IBM Cloud qui offrent la connectivité Direct Link Exchange :
 
| Fournisseur Exchange	| Code de centre de données IBM |
|-------------|-----------------------|
| AT Tokyo | TOK02 |
| Ascenty | SAO01* |
| Cologix | MON02, TOR02 |
| Cyrus One | DAL13 |
| DE-CIX | FRA01 |
| Equinix | HKG01,SNG02, SYD02, TOK01, AMS02, PAR02, CHI01, DAL03, NYC02, NYC03, SAO02, SJC02, TOR02, WDC02, LON01, FRA03 |							
| InterXion | FRA01, STO01 |
| KINX	| SEO02 |
| NextDC | MEL02, SYD03* |
| SK C&C | SEO01 |

* Bientôt disponible

## Tarification

Pour obtenir des informations de tarification, voir la [rubrique sur la tarification](/docs/infrastructure/direct-link/pricing.html).
