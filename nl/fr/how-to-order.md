---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-11"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Commander IBM Cloud Direct Link

Lorsque vous vous préparez à commander le type de solution IBM Cloud Direct Link qui correspond le mieux à vos besoins, cliquez sur les liens ci-dessous (ou faites simplement défiler ce document) pour afficher un aperçu général du processus. Une fois prêt à passer votre commande, vous trouverez des instructions qui vous guideront tout au long du processus de commande, étape par étape. 

* [Comment commander IBM Cloud Direct Link Exchange ?](how-to-order.html#how-to-order-ibm-cloud-direct-link-exchange)
* [Comment commander IBM Cloud Direct Link Connect ?](how-to-order.html#how-to-order-ibm-cloud-direct-link-connect)
* [Comment commander IBM Cloud Direct Link Dedicated ?](how-to-order.html#how-to-order-ibm-cloud-direct-link-dedicated)
* [Comment commander IBM Cloud Direct Link Dedicated Hosting ?](how-to-order.html#how-to-order-ibm-cloud-direct-link-dedicated-hosting)

## Comment commander IBM Cloud Direct Link Exchange ?

 * Vérifiez que votre fournisseur de réseau peut accéder au point de présence (PoP) approprié et établir une interconnexion avec le fournisseur Cloud Exchange associé.
 * Utilisez le [portail client![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/) pour ouvrir une demande pour IBM Cloud Direct Link Exchange et remplissez les informations demandées. (Vous pouvez faire appel à des ingénieurs commerciaux IBM pour vous aider). Si vous utilisez le fournisseur Equinix, le processus de commande et de mise à disposition est [entièrement automatisé](cloud-exchange-automation.html).
 * Contactez votre fournisseur Exchange et négociez la connectivité à votre échange.
 * Commandez la connectivité entre votre fournisseur de réseau et le fournisseur Exchange.
 * Commandez un "circuit virtuel" via le fournisseur Exchange et indiquez l'ID de ticket de la demande {{site.data.keyword.BluSoftlayer_notm}} IBM Direct Link comme "ID de la demande" ou "ID d'autorisation"
 * L'affectation d'une adresse IP sur l'infrastructure réseau {{site.data.keyword.BluSoftlayer_notm}} sera effective dans les trois jours ouvrables une fois la demande de circuit virtuel terminée.

## Comment commander IBM Cloud Direct Link Connect ?

 * Vérifiez que votre fournisseur de réseau peut accéder au point de présence (PoP) approprié et établir une interconnexion avec le fournisseur Connect associé.
 * Utilisez le [portail client![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/) pour ouvrir une demande pour IBM Cloud Direct Link Connect et remplissez les informations demandées. (Vous pouvez faire appel à des ingénieurs commerciaux IBM pour vous aider). 
 * Contactez votre fournisseur Connect et négociez la connectivité à votre échange.
 * Commandez la connectivité entre votre fournisseur de réseau et le fournisseur Connect.
 * Commandez un "circuit virtuel" via le fournisseur Connect et indiquez l'ID de ticket de la demande {{site.data.keyword.BluSoftlayer_notm}} IBM Direct Link comme "ID de la demande" ou "ID d'autorisation"
 * L'affectation d'une adresse IP sur l'infrastructure réseau {{site.data.keyword.BluSoftlayer_notm}} sera effective dans les trois jours ouvrables une fois la demande de circuit virtuel terminée.

## Comment commander IBM Cloud Direct Link Dedicated ?

 * Vérifiez que votre fournisseur de réseau peut accéder au point de présence (PoP) approprié et établir une interconnexion avec l'environnement {{site.data.keyword.BluSoftlayer_notm}}.
 * Ouvrez une demande IBM Cloud Direct Link Dedicated et indiquez les informations demandées. (Vous pouvez faire appel à des ingénieurs commerciaux IBM pour vous aider).
 * {{site.data.keyword.BluSoftlayer_notm}} fournit une lettre d'autorisation (LOA) pour la connexion.
 * Confirmez que votre circuit a atteint le PoP et a été finalisé par l'opérateur.
 * Commandez une interconnexion à l'aide des informations d'affectation de site client (CFA (Customer Facility Assignment)) {{site.data.keyword.BluSoftlayer_notm}} figurant dans la lettre d'autorisation, ce qui prend en principe de 2 à 10 jours ouvrables pour aboutir. (Ce délai dépend du fournisseur du site et du type de priorité de la commande défini par le client). Ce processus comprend la configuration du correctif pour le port de terminaison {{site.data.keyword.BluSoftlayer_notm}}.
 * Fournissez à {{site.data.keyword.BluSoftlayer_notm}} l'avis d'achèvement de l'interconnexion du fournisseur du site figurant dans le ticket du portail {{site.data.keyword.BluSoftlayer_notm}}.
 * {{site.data.keyword.BluSoftlayer_notm}} vérifiera l'efficacité de l'avis d'achèvement et commandera le correctif à appliquer à partir des informations LOA/CFA au routeur d'interconnexion (XCR) et à d'autres équipements.
 * L'affectation de votre adresse IP sur l'infrastructure réseau {{site.data.keyword.BluSoftlayer_notm}} sera effective dans les trois jours ouvrables une fois l'interconnexion terminée.

## Comment commander IBM Cloud Direct Link Dedicated Hosting ?

 * Identifiez vos besoins en matière de colocalisation et de connectivité, puis travaillez avec l'équipe commerciale IBM pour finaliser et exécuter un contrat et les additifs techniques.
 * {{site.data.keyword.BluSoftlayer_notm}} exécute une commande avec le fournisseur de colocalisation pour l'environnement et les services demandés. En principe, le déploiement est finalisé dans les 30 jours suivant la commande.
 * Lorsque la construction de votre cage de colocalisation est terminée, le processus d'interconnexion entre cette cage et l'équipement XCR de l'environnement POD {{site.data.keyword.BluSoftlayer_notm}} suivra le processus IBM Cloud Direct Link Dedicated indiqué précédemment, en commençant par l'étape 3.
