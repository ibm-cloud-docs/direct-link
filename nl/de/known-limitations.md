---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-02-26"

keywords: limitations, VRF, account-to-account, VPN, BGP, fees, contract, Exchange, Connect, Dedicated, Hosting

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Bekannte Einschränkungen
{: #known-limitations}

Dieser Abschnitt befasst sich zunächst mit den Einschränkungen für alle {{site.data.keyword.cloud}} Direct Link-Angebote. Danach werden Details zu einigen der Einschränkungen der einzelnen Angebote aufgeführt.

## Allgemeine Einschränkungen für IBM Cloud Direct Link
{: #general-ibm-cloud-direct-link-limitations}

 * Jede IBM Cloud Direct Link-Verbindung erfordert eine eindeutige Bestellung. Wenn Sie mehrere Verbindungen benötigen, öffnen Sie für jede Verbindung eine IBM Cloud Direct Link-Bestellung.
 * Sie können aus Ihren fernen Netzen nicht direkt auf das Servicenetz von {{site.data.keyword.BluSoftlayer_notm}} zugreifen.
 * {{site.data.keyword.BluSoftlayer_notm}} ermöglicht Kunden keinen Rücktransport beim Datenverkehr zwischen ihren fernen Standorten im {{site.data.keyword.BluSoftlayer_notm}}-Backbone. Das IBM Cloud Direct Link-Produkt ist dafür vorgesehen, Ihre fernen Netze privat mit Ihrer {{site.data.keyword.BluSoftlayer_notm}}-Infrastruktur kommunizieren zu lassen.
 * IBM Cloud Direct Link erfordert die Verwendung einer VRF (Virtual Routing and Forwarding)-Instanz.
 * VRF ist nicht vollständig mit den SSL- und IPSec VPN-Services von {{site.data.keyword.BluSoftlayer_notm}} kompatibel.
 * VRF ist nicht mit dem kontoübergreifenden VLAN-Spanning von {{site.data.keyword.BluSoftlayer_notm}} kompatibel.
 * IBM Cloud Direct Link erfordert BGP, um die Routen zum fernen Netz eines Kunden herstellen zu können.
 * Änderungen an der IBM Cloud Direct Link-Infrastruktur müssen zwischen 08:00 Uhr und 17:00 Uhr der Zeitzone Central Time (MEZ -8) vorgenommen werden.
 
## Einschränkungen für IBM Cloud Direct Link Exchange und Direct Link Connect
{: #ibm-cloud-direct-link-exchange-and-direct-link-connect-limitations}

 * Kunden sind für alle Gebühren verantwortlich, die für das Erreichen des Bereitstellungspunkts über ein fernes Netz anfallen, sowie für alle Gebühren hinsichtlich des Cloud-Providers für den Datenaustausch.
 * {{site.data.keyword.BluSoftlayer_notm}} stellt keine Kundengeräte an unseren Netzbereitstellungspunkten zusammen. Kunden müssen gemeinsam mit ihrem Provider ermitteln, ob sie Geräte an der Stelle zusammenstellen, an der {{site.data.keyword.BluSoftlayer_notm}}-Netzbereitstellungspunkte vorhanden sind.
 * Die Verfügbarkeit von 'Direct Link Cloud Exchange' ist je nach Standort unterschiedlich. Kunden können sich an ihren IBM Cloud-Account-Manager wenden, um die aktuelle oder zukünftige Verfügbarkeit zu überprfen.
 
## Einschränkungen für IBM Cloud Direct Link Dedicated
{: #ibm-cloud-direct-link-dedicated-limitations}

 * Die {{site.data.keyword.BluSoftlayer_notm}}-Gebühren für IBM Cloud Direct Link Dedicated umfassen die Kosten für den Portabschluss an der {{site.data.keyword.BluSoftlayer_notm}}-Infrastruktur. Kunden sind für alle Gebühren verantwortlich, die für das Erreichen des Bereitstellungspunkts über ein fernes Netz anfallen, sowie für alle Querverbindungen, die innerhalb der PoP-Facility benötigt werden.  {{site.data.keyword.BluSoftlayer_notm}} bestellt keine Querverbindungen im Namen eines Kunden.
 * {{site.data.keyword.BluSoftlayer_notm}} stellt keine Kundengeräte an unseren Netzbereitstellungspunkten zusammen. Kunden müssen gemeinsam mit ihrem Provider ermitteln, ob sie Geräte an der Stelle zusammenstellen, an der {{site.data.keyword.BluSoftlayer_notm}}-Netzbereitstellungspunkte vorhanden sind.

## Einschränkungen für IBM Cloud Direct Link Dedicated Hosting
{: #ibm-cloud-direct-link-dedicated-hosting-limitations}

 * IBM Cloud Direct Link Dedicated Hosting erfordert einen speziellen Vertrag zwischen {{site.data.keyword.BluSoftlayer_notm}} und dem Kunden. Dieser Vertrag enthält die Bedingungen für das Produkt, die Preisstruktur für die Colocation-Umgebung und die verbindliche Zusage für die Bedingungen für die Services. Es ist ein Vertrag mit einer Laufzeit von 6, 9 oder 12 Monaten erforderlich.
 * Die Provider-Konnektivität ist auf die On-Net-Provider des ausgewählten Rechenzentrums beschränkt.
