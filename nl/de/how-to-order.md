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

# Bestellung von IBM Cloud Direct Link

Bei der Vorbereitung für die Bestellung des Typs von IBM Cloud Direct Link, der sich am besten für Ihren Bedarf eignet, können Sie den nachstehenden Links folgen (oder einfach durch dieses Dokument blättern), um eine allgemeine Übersicht über den Prozess zu erhalten. Wenn Sie für die Bestellung bereit sind, können Sie in unserer "Schritt für Schritt"-Serie von Dokumenten eine schrittweise Anleitung finden, die Sie durch den Bestellablauf führt.

* [Vorgehensweise zur Bestellung von IBM Cloud Direct Link Exchange](how-to-order.html#how-to-order-ibm-cloud-direct-link-exchange)
* [Vorgehensweise zu Bestellung von IBM Cloud Direct Link Connect](how-to-order.html#how-to-order-ibm-cloud-direct-link-connect)
* [Vorgehensweise zur Bestellung von IBM Cloud Direct Link Dedicated](how-to-order.html#how-to-order-ibm-cloud-direct-link-dedicated)
* [Vorgehensweise zur Bestellung von IBM Cloud Direct Link Dedicated Hosting](how-to-order.html#how-to-order-ibm-cloud-direct-link-dedicated-hosting)

## Vorgehensweise zur Bestellung von IBM Cloud Direct Link Exchange

 * Überprüfen Sie die Möglichkeiten Ihres Netzproviders, den entsprechenden Bereitstellungspunkt zu erreichen und die Querverbindung zum zugehörigen Cloud-Provider für den Datenaustausch einzurichten.
 * Verwenden Sie das [Kundenportal ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://control.softlayer.com/), um eine Anforderung für IBM Cloud Direct Link Exchange zu öffnen und die angeforderten Informationen auszufüllen. (Unterstützung von IBM Sales Engineers kann angefordert werden.) Wenn Sie den Equinix-Provider verwenden, ist der Bestell- und Bereitstellungsprozess [voll automatisiert](cloud-exchange-automation.html).
 * Wenden Sie sich an Ihren Exchange-Provider und vereinbaren Sie Konnektivität für Ihren Datenaustausch.
 * Bestellen Sie Konnektivität zwischen Ihrem Netzbetreiber und dem Exchange-Provider.
 * Bestellen Sie eine "virtuelle Verbindung" durch den Exchange-Provider und verweisen Sie auf die Ticket-ID der {{site.data.keyword.BluSoftlayer_notm}} IBM Cloud Direct Link-Anforderung als Ihre "Anforderungs-ID".
 * Die IP-Zuordnung für die Netzinfrastruktur von {{site.data.keyword.BluSoftlayer_notm}} erfolgt innerhalb von drei Werktagen nach erfolgreicher Abwicklung der Anforderung für eine virtuelle Verbindung.

## Vorgehensweise zur Bestellung von IBM Cloud Direct Link Connect

 * Überprüfen Sie die Funktionalität Ihres Netzbetreibers zum Erreichen des geeigneten Bereitstellungspunkts und zur Querverbindung mit dem zugehörigen Connect-Provider.
 * Verwenden Sie das [Kundenportal ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://control.softlayer.com/), um eine IBM Cloud Direct Link Connect-Anforderung zu öffnen und die angeforderten Informationen auszufüllen. (Unterstützung von IBM Sales Engineers kann angefordert werden.) 
 * Wenden Sie sich an Ihren Connect-Provider und vereinbaren Sie Konnektivität für Ihren Datenaustausch.
 * Bestellen Sie Konnektivität zwischen Ihrem Netzbetreiber und dem Connect-Provider.
 * Bestellen Sie eine "virtuelle Verbindung" durch den Connect-Provider und verweisen Sie auf die Ticket-ID der {{site.data.keyword.BluSoftlayer_notm}} IBM Cloud Direct Link-Anforderung als Ihre "Anforderungs-ID" oder "Berechtigungs-ID".
 * Die IP-Zuordnung für die Netzinfrastruktur von {{site.data.keyword.BluSoftlayer_notm}} erfolgt innerhalb von drei Werktagen nach erfolgreicher Abwicklung der Anforderung für eine virtuelle Verbindung.

## Vorgehensweise zur Bestellung von IBM Cloud Direct Link Dedicated

 * Überprüfen Sie die Möglichkeiten Ihres Netzproviders, den entsprechenden Bereitstellungspunkt zu erreichen und die Querverbindung in die {{site.data.keyword.BluSoftlayer_notm}}-Umgebung einzurichten.
 * Öffnen Sie eine IBM Cloud Direct Link Dedicated-Anforderung und füllen Sie die angeforderten Informationen aus. (Unterstützung von IBM Sales Engineers kann angefordert werden.)
 * {{site.data.keyword.BluSoftlayer_notm}} stellt das Bevollmächtigungsschreiben (LOA, Letter of Authorization) für die Verbindung bereit.
 * Stellen Sie sicher, dass die Verbindung den Bereitstellungspunkt erreicht hat und vom Netzbetreiber eingerichtet wurde.
 * Bestellen Sie die Querverbindung anhand der CFA-Informationen (CFA, Customer Facility Assignment) von {{site.data.keyword.BluSoftlayer_notm}} aus dem Berechtigungsschreiben. Dieser Vorgang ist in der Regel nach 2 bis 10 Werktagen abgeschlossen. (Dieser Zeitrahmen hängt vom entsprechenden Facility-Anbieter und der Art der vom Kunden angegebenen Auftragspriorität ab.) Dieser Prozess umfasst die Einrichtung des Patches für den Abschlussport von {{site.data.keyword.BluSoftlayer_notm}}.
 * Stellen Sie für {{site.data.keyword.BluSoftlayer_notm}} den Fertigstellungshinweis für die Querverbindung vom Facility-Provider im Ticket des {{site.data.keyword.BluSoftlayer_notm}}-Portals bereit.
 * {{site.data.keyword.BluSoftlayer_notm}} überprüft den Fertigstellungshinweis auf dessen Wirksamkeit und bestellt den Patch vom LOA/CFA zum Router für Querverbindungen (XCR) und zu anderen Geräten.
 * Die IP-Zuordnung für die Netzinfrastruktur von {{site.data.keyword.BluSoftlayer_notm}} wird innerhalb von drei Werktagen nach erfolgreicher Einrichtung der Querverbindung abgeschlossen.

## Vorgehensweise zur Bestellung von IBM Cloud Direct Link Dedicated Hosting

 * Ermitteln Sie Ihre Colocation- und Konnektivitätsanforderungen und arbeiten Sie gemeinsam mit dem IBM Vertriebsteam am Abschluss und an der Durchführung eines Vertrags und technischen Anhangs.
 * {{site.data.keyword.BluSoftlayer_notm}} führt gemeinsam mit dem Colocation-Provider einen Erstellungsauftrag für die angeforderte Umgebung und die entsprechenden Services durch. Die Bereitstellung wird in der Regel innerhalb von 30 Tagen nach Erteilung des Erstellungsauftrags abgeschlossen.
 * Wenn die Erstellung Ihres Colocation-Käfigs abgeschlossen ist, folgt der Prozess der Verbindung zwischen Ihrem Colocation-Käfig und dem Router für Querverbindungen (XCR) der {{site.data.keyword.BluSoftlayer_notm}}-Pod-Umgebung dem zuvor beschriebenen Prozess für IBM Cloud Direct Link Dedicated, der mit Schritt 3 beginnt.
