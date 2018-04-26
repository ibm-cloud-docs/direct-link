---

copyright:
  years: 2017, 2018
lastupdated: "2018-04-12"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Informationen zu IBM Cloud Direct Link

Dieser Abschnitt enthält weitere Details zu den Hauptmerkmalen und Vorteilen von jedem der vier Angebote für IBM Cloud Direct Link.
  * [**IBM Cloud Direct Link Exchange**](#the-ibm-cloud-direct-link-exchange-solution)
  * [**IBM Cloud Direct Link Connect**](#the-ibm-cloud-direct-link-connect-solution)
  * [**IBM Cloud Direct Link Dedicated**](#the-ibm-cloud-direct-link-dedicated-solution)
  * [**IBM Cloud Direct Link Dedicated Hosting**](#the-ibm-cloud-direct-link-dedicated-hosting-solution)

## Die Lösung IBM Cloud Direct Link Exchange

Mit der Lösung IBM Cloud Direct Link Exchange können Kunden einen Cloud-Provider für den Datenaustausch nutzen, um Konnektivität zu {{site.data.keyword.BluSoftlayer_notm}} bereitzustellen. Dieses Angebot bietet in der Regel Konnektivität zu geringeren Kosten, da die physische Verbindung zwischen {{site.data.keyword.BluSoftlayer_notm}} und dem Cloud-Provider für den Datenaustausch bereits vorhanden ist und von anderen Kunden gemeinsam genutzt wird.

**Übliche Anwendungsfälle:** _Optimal für hybride Workloads, Provider-übergreifende Workloads, umfangreiche oder häufige Datenübertragungen, private Workloads und die Umgebungsverwaltung.  Diese Option wird meist ausgewählt, wenn der gewünschte Bereitstellungspunkt bereits über den gewünschten IBM Cloud Direct Link Exchange-Provider verfügt._

![Abbildung 1](/images/Direct-Link-Exchange.PNG)

 * **Abschlussort:** {{site.data.keyword.BluSoftlayer_notm}}-Bereitstellungspunkt (PoP).

 * **Typische Bereitstellungszeit:** Bei Equinix-Providern beträgt die Bereitstellungszeit meist wenige Stunden. Bei anderen Providern beträgt sie 5 bis 10 Tage, nachdem die Verbindung den Austausch erreicht hat. Die Bereitstellungszeit kann u. U. 30 bis 60 Tage insgesamt in Anspruch nehmen, je nach Ihrem Standort und Ihren Anforderungen.

 * **Details zu Querverbindungen:** Für die Cloud Exchange-Verbindung werden physische Querverbindungen zwischen {{site.data.keyword.BluSoftlayer_notm}} und dem Cloud-Provider für den Datenaustausch verwaltet. Kunden fordern eine "virtuelle Verbindung" vom Cloud-Provider für den Datenaustausch an, womit die logische Konnektivität zu {{site.data.keyword.BluSoftlayer_notm}} eingerichtet wird, sobald sie mit dem Datenaustauschprovider vernetzt sind.

 * **Optionen für Portgeschwindigkeiten:** Sie können zwischen 50 Mb/s, 100 Mb/s, 200 Mb/s, 500 Mb/s oder 1 Gb/s auswählen.

 * **Ungefähre Latenz:** Die Latenz beträgt in etwa 1,5 ms im Nahbereich (Rechenzentren mit demselben Präfix, wie DAL, AMS, MEL usw.). Unter 'http://lg.softlayer.com/' finden Sie Live-Latenzmessungen für P2P-Verbindungen.

 * **Colocation-Services:** Keine.

 * **Redundanz:** Zur Schaffung von Redundanz für IBM Cloud Direct Link Exchange ist Konnektivität zu mindestens 2 Standorten erforderlich. Alternativ muss ein Standort mit einem verfügbaren sekundären Router für Querverbindungen (XCR) ausgewählt sein, der vom Cloud-Provider für den Datenaustausch genutzt werden kann.

 * **Optionen für Local/Global Routing:** Mit der Option 'Local Routing' erhalten Sie Zugriff auf Rechenzentren, die dasselbe Präfix aus drei Buchstaben aufweisen wie der Bereitstellungspunkt (DAL, AMS, MEL usw). Die Option 'Global Routing' ist ein erforderliches Add-on, um Rechenzentren außerhalb dieser Standorte zu erreichen.
 
## Die Lösung IBM Cloud Direct Link Connect

**Gängige Anwendungsfälle** Ähnlich wie für die Lösung Direct Link Exchange. Das Angebot enthält weitere Geschwindigkeitsoptionen. Es stellt einen kostengünstigeren Einstiegspunkt dar.

![Abbildung 2](/images/Direct-Link-Connect.PNG)

* **Abschlussort:** {{site.data.keyword.BluSoftlayer_notm}}-Bereitstellungspunkt (PoP).

* **Typische Bereitstellungszeit:** 5 bis 10 Tage, nachdem die Verbindung den Austauschprovider erreicht. Die Bereitstellungszeit kann je nach Standort und Anforderungen insgesamt zwischen 30 und 60 Tagen liegen.

* **Details zu Querverbindungen:** Physische Querverbindungen für Cloud Connect-Verbindungen werden zwischen {{site.data.keyword.BluSoftlayer_notm}} und dem Cloud-Provider für Verbindungen gepflegt. Kunden fordern eine "virtuelle Verbindung" vom Cloud-Provider für Verbindungen an, die die logische Konnektivität zu {{site.data.keyword.BluSoftlayer_notm}} herstellt, nachdem sie mit dem Cloud-Provider für Verbindungen verbunden wurden.

* **Optionen für Portgeschwindigkeiten:** Sie können zwischen 50 Mb/s, 100 Mb/s, 200 Mb/s, 500 Mb/s, 1 Gb/s, 2 Gb/s oder 5 Gb/s auswählen.

* **Ungefähre Latenz:** Die Latenz beträgt in etwa 1,5 ms im Nahbereich (Rechenzentren mit demselben Präfix, wie DAL, AMS, MEL usw.). Unter 'http://lg.softlayer.com/' finden Sie Live-Latenzmessungen für P2P-Verbindungen.

* **Colocation-Services:** Keine.

* **Redundanz:** Zur Schaffung von Redundanz für IBM Cloud Direct Link Connect ist Konnektivität zu mindestens 2 Standorten erforderlich. Alternativ muss ein Standort mit einem verfügbaren sekundären Router für Querverbindungen (XCR) ausgewählt sein, der vom Cloud-Provider für Verbindungen genutzt werden kann.

* **Optionen für Local/Global Routing:** Mit der Option 'Local Routing' erhalten Sie Zugriff auf Rechenzentren, die dasselbe Präfix aus drei Buchstaben aufweisen wie der Bereitstellungspunkt (DAL, AMS, MEL usw). Die Option 'Global Routing' ist ein erforderliches Add-on, um Rechenzentren außerhalb dieser Standorte zu erreichen.

## Die Lösung IBM Cloud Direct Link Dedicated

Mit der Lösung IBM Cloud Direct Link Dedicated können Kunden eine dedizierte Einzelmodus-Glasfaser-Querverbindung zu ihrem eigenen privaten {{site.data.keyword.BluSoftlayer_notm}}-Netz herstellen.

 **Übliche Anwendungsfälle:** _Optimal für hybride Workloads, Provider-übergreifende Workloads, umfangreiche oder häufige Datenübertragungen, private Workloads und die Umgebungsverwaltung.  Diese Option wird meist in folgenden Fällen ausgewählt: 1. Der gewünschte Bereitstellungspunkt verfügt nicht über den gewünschten IBM Cloud Direct Link Exchange-Provider, 2. Hochleistungs-Workloads erfordern einen hohen Durchsatz oder 3. Es bestehen Compliance-Anforderungen, die von dem Implementierungsmodell von IBM Cloud Direct Link Exchange nicht erfüllt werden können._

![Abbildung 3](/images/Direct-link-Dedicated.PNG)

 * **Abschlussort:** {{site.data.keyword.BluSoftlayer_notm}}-Bereitstellungspunkt (PoP).

 * **Typische Bereitstellungszeit:** 10 bis 15 Werktage, nachdem die neue Verbindung den Bereitstellungspunkt erreicht. Die Bereitstellungszeit kann je nach Standort und Anforderungen insgesamt zwischen 30 und 60 Tagen liegen.

 * **Details zu Querverbindungen:** {{site.data.keyword.BluSoftlayer_notm}} stellt ein Bevollmächtigungsschreiben (LOA, Letter of Authorization) bereit, mit dem ein Kunde Ethernet-Glasfaserverbindungen (nur Monomode-Glasfaserverbindungen, entweder 1Gig-LX oder 10Gig-LR) bestellen kann, die von einen Kunden oder Provider zu einem {{site.data.keyword.BluSoftlayer_notm}} CFA-Abschlusspunkt verlaufen, der an die Infrastruktur des XCR-Routers angebunden ist. Die Wellenlänge hierbei muss 1310 nm betragen.

 * **Optionen für Portgeschwindigkeiten:** Sie können zwischen 1 Gb/s, 2 Gb/s, 5 Gb/s oder 10 Gb/s auswählen.

 * **Ungefähre Latenz:** Die Latenz beträgt in etwa 1,5 ms im Nahbereich (Rechenzentren mit demselben Präfix, wie DAL, AMS, MEL usw.).  Unter 'http://lg.softlayer.com/' finden Sie Live-Latenzmessungen für P2P-Verbindungen.

 * **Colocation-Services:** Keine.

 * **Redundanz:** Zur Schaffung von Redundanz ist Konnektivität für IBM Cloud Direct Link zu mindestens 2 Standorten erforderlich. Alternativ müssen ein Standort mit einem verfügbaren sekundären Router für Querverbindungen (XCR) sowie eine zweite IBM Cloud Direct Link-Verbindungsanforderung ausgewählt sein.

 * **Optionen für Local/Global Routing:** Mit der Option 'Local Routing' erhalten Sie Zugriff auf Rechenzentren, die dasselbe Präfix aus drei Buchstaben aufweisen wie der Bereitstellungspunkt (DAL, AMS, MEL usw). Die Option 'Global Routing' ist ein erforderliches Add-on, um Rechenzentren außerhalb dieser Standorte zu erreichen.

## Die Lösung IBM Cloud Direct Link Dedicated Hosting

Die Lösung IBM Cloud Direct Link Dedicated Hosting bietet eine ähnliche Konnektivität wie IBM Cloud Direct Link Dedicated, aber der Verbindungspunkt grenzt an ein {{site.data.keyword.BluSoftlayer_notm}}-Rechenzentrum an, das die Latenz für Anwendungsfälle mit höherer Leistung verbessert. IBM Cloud bietet im Rahmen dieser Lösung eine Reihe anpassbarer Colocation-Services.

**Übliche Anwendungsfälle:** _Optimal für die Arbeit mit vom Standard abweichenden Computing-Technologien, dediziertem Speicherbedarf oder für die Nutzung vorhandener IT-Investitionen._

![Abbildung 4](/images/Direct-Link-Dedicated-Hosting.png)

* **Abschlussort:** {{site.data.keyword.BluSoftlayer_notm}}-Rechenzentrum (Data Center, DC).

 * **Typische Bereitstellungszeit:** 30 bis 60 Tage nach Klärung aller Anforderungen und Durchsetzung der Verträge.

 * **Details zu Querverbindungen:** {{site.data.keyword.BluSoftlayer_notm}} bietet 1-G- oder 10-G-Glasfaserverbindungen von der Infrastruktur des {{site.data.keyword.BluSoftlayer_notm}}-Routers für Querverbindungen (XCR) hin zur Colocation-Umgebung des Kunden als Teil der Bereitstellung. Wenn keine Colocation-Services angefordert werden (wenn vorhandene Umgebungen bereits verbunden sind), stellt {{site.data.keyword.BluSoftlayer_notm}} ein Bevollmächtigungsschreiben (LOA, Letter of Authorization) bereit, mit dem ein Kunde Ethernet-Glasfaserverbindungen (nur Monomode-Glasfaserverbindungen, entweder 1Gig-LX oder 10Gig-LR) bestellen kann, die von einen Kunden oder Provider zu einem {{site.data.keyword.BluSoftlayer_notm}} CFA-Abschlusspunkt verlaufen, der an die Infrastruktur des XCR-Routers angebunden ist. Die Wellenlänge hierbei muss 1310 nm betragen.

 * **Optionen für Portgeschwindigkeiten:** Sie können zwischen 1 Gb/s, 2 Gb/s, 5 Gb/s oder 10 Gb/s auswählen.

 * **Ungefähre Latenz:** Die Latenz beträgt etwa 0,5 ms im lokalen Rechenzentrum.

 * **Colocation-Services:** Ja.

 * **Redundanz:** {{site.data.keyword.BluSoftlayer_notm}} bietet Verbindungen zu zwei Routern für Querverbindungen (XCR) als Teil des Produkts. Um eine redundante Verbindung einzurichten, konfigurieren Kunden BCP mit Equal Cost Multipath (ECMP).

 * **Optionen für Local/Global Routing:** Mit der Option 'Local Routing' erhalten Sie Zugriff auf Rechenzentren, die dasselbe Präfix aus drei Buchstaben aufweisen wie der Bereitstellungspunkt (DAL, AMS, MEL usw). Die Option 'Global Routing' ist ein erforderliches Add-on, um Rechenzentren außerhalb dieser Standorte zu erreichen.
