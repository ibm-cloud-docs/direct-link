---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-29"

keywords: hybrid, solutions, features, benefits, port speed, cross-connect, use cases, latency, routing, options, colocation

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Informationen zu IBM Cloud Direct Link
{: #about-ibm-cloud-direct-link}

Dieser Abschnitt enthält weitere Details zu den Hauptmerkmalen und Vorteilen der vier {{site.data.keyword.cloud}}
Direct Link-Lösungen.
  * [**IBM Cloud Direct Link Exchange**](#direct-link-exchange-solution)
  * [**IBM Cloud Direct Link Connect**](#direct-link-connect-solution)
  * [**IBM Cloud Direct Link Dedicated**](#direct-link-dedicated-solution)
  * [**IBM Cloud Direct Link Dedicated Hosting**](#direct-link-dedicated-hosting-solution)

## Die Lösung IBM Cloud Direct Link Exchange
{: #direct-link-exchange-solution}

Mit der Lösung IBM Cloud Direct Link Exchange können Kunden einen Cloud Exchange-Provider nutzen, um Konnektivität zu {{site.data.keyword.cloud_notm}}-Standorten bereitzustellen. Dieses Angebot bietet in der Regel Konnektivität zu geringeren Kosten, da die physische Verbindung zwischen {{site.data.keyword.cloud_notm}} und dem Cloud Exchange-Provider bereits vorhanden ist und von anderen Kunden gemeinsam genutzt wird.

**Übliche Anwendungsfälle:** _Optimal für hybride Workloads, providerübergreifende Workloads, umfangreiche oder häufige Datenübertragungen mit großer ausgehender Bandbreite, private Workloads und die Umgebungsverwaltung.  Diese Option wird in der Regel gewählt, wenn der gewünschte Bereitstellungspunkt bereits über den gewünschten IBM Cloud Direct Link Exchange-Provider verfügt._

![Abbildung 1](/images/Direct-Link-Exchange.png)

 * **Abschlussort:** {{site.data.keyword.cloud_notm}}-Bereitstellungspunkt (PoP).

 * **Typische Bereitstellungszeit:** Bei Equinix-Providern beträgt die Bereitstellungszeit meist mehrere Stunden. Bei anderen Providern beträgt sie 5 bis 10 Tage, nachdem die Verbindung den Austausch erreicht hat. Die gesamte Bereitstellungszeit kann je nach Standort und Anforderungen zwischen 30 und 60 Tagen betragen, wenn eine Verbindung bei einem Netzserviceanbieter oder Netzbetreiber bestellt wird.

 * **Details zu Querverbindungen:** Für die Cloud Exchange-Verbindung werden physische Querverbindungen zwischen {{site.data.keyword.cloud_notm}} und dem Cloud Exchange-Provider verwaltet. Kunden fordern eine "virtuelle Verbindung" beim Cloud Exchange-Provider an, mit der die logische Konnektivität zu {{site.data.keyword.cloud_notm}} eingerichtet wird, sobald der Kunde mit dem Cloud Exchange-Provider vernetzt ist.

 * **Optionen für Portgeschwindigkeiten:** Sie können zwischen 50 Mb/s, 100 Mb/s, 200 Mb/s, 500 Mb/s, 1 Gb/s, 2 Gb/s oder 5 Gb/s auswählen.

 * **Ungefähre Latenz:** Die Latenz beträgt ungefähr 1,5 ms im Nahbereich (Rechenzentren mit demselben Präfix aus drei Buchstaben wie DAL, AMS, MEL). Unter http://lg.softlayer.com/ finden Sie Latenzmessungen für aktive PoP/PoP-Verbindungen (P2P-Verbindungen).

 * **IBM Colocation-Services:** Keine.

 * **Redundanz:** {{site.data.keyword.cloud_notm}} bietet Verbindungen zu zwei (2) verschiedenen Routern für Querverbindungen (XCR) als Teil des Produkts. Zum Einrichten der redundanten Konnektivität müssen die Kunden für jede Direct Link-Verbindung entsprechend ihren Präferenzen BGP konfigurieren. Als Beispiele können Optionen wie die folgenden angegeben werden: _prefer Lowest MED_, _prefer highest local-preference_ oder _prefer shorter AS paths_.

 * **Optionen für Local/Global Routing:** Die Option 'Local Routing' ist die Standardoption für die Routenwahl. Sie bietet Zugriff auf Rechenzentren in demselben Markt wie der Direct Link-Bereitstellungspunkt oder -PoP (z. B. als DAL, AMS oder MEL bezeichnet). Die Option 'Global Routing' ist als Add-on erforderlich, um Ihre IBM Cloud-Ressourcen mit anderen IBM Cloud-Ressourcen in Rechenzentren außerhalb des lokalen Marktes zu verbinden. Sie stellt eine Möglichkeit bereit, Workloads durch mehrere IBM Cloud-Ressourcen gemeinsam zu nutzen (zum Beispiel durch Dallas und Ashburn oder durch Dallas und Frankfurt).
 
## Die Lösung IBM Cloud Direct Link Connect
{: #direct-link-connect-solution}

**Übliche Anwendungsfälle** _Mit der Lösung IBM Cloud Direct Link Connect können Kunden einen Netzserviceanbieter nutzen, um Konnektivität zu {{site.data.keyword.cloud_notm}}-Standorten bereitzustellen. Dieses Angebot bietet in der Regel Konnektivität zu geringeren Kosten, da die physische Verbindung zwischen {{site.data.keyword.cloud_notm}} und dem Netzserviceanbieter bereits vorhanden ist und von anderen Kunden gemeinsam genutzt wird._

![Abbildung 2](/images/Direct-Link-Connect.png)

* **Abschlussort:** {{site.data.keyword.cloud_notm}}-Bereitstellungspunkt (PoP).

* **Typische Bereitstellungszeit:** 5 bis 10 Tage, nachdem die Verbindung den Austausch erreicht hat. Die gesamte Bereitstellungszeit kann je nach Standort und Anforderungen zwischen 30 und 60 Tagen betragen, wenn eine Verbindung bei einem Netzserviceanbieter oder Netzbetreiber bestellt wird.

* **Details zu Querverbindungen:** Für die sichere Direct Link Connect-Verbindung werden physische Querverbindungen zwischen {{site.data.keyword.cloud_notm}} und dem Connect-Provider verwaltet. Kunden fordern eine "virtuelle Verbindung" vom Cloud Connect-Provider an, mit der die logische Konnektivität zu {{site.data.keyword.cloud_notm}} eingerichtet wird, sobald der Kunde mit dem Cloud Connect-Provider vernetzt ist.

* **Optionen für Portgeschwindigkeiten:** Sie können zwischen 50 Mb/s, 100 Mb/s, 200 Mb/s, 500 Mb/s, 1 Gb/s, 2 Gb/s oder 5 Gb/s auswählen.

* **Ungefähre Latenz:** Die Latenz beträgt ungefähr 1,5 ms im Nahbereich (Rechenzentren mit demselben Präfix aus drei Buchstaben wie DAL, AMS, MEL). Unter http://lg.softlayer.com/ finden Sie Latenzmessungen für aktive PoP/PoP-Verbindungen (P2P-Verbindungen).

* **IBM Colocation-Services:** Keine.

* **Redundanz:** {{site.data.keyword.cloud_notm}} bietet Verbindungen zu zwei (2) verschiedenen Routern für Querverbindungen (XCR) als Teil des Produkts. Zum Einrichten der redundanten Konnektivität müssen die Kunden für jede Direct Link-Verbindung entsprechend ihren Präferenzen BGP konfigurieren. Als Beispiele können Optionen wie die folgenden angegeben werden: _prefer Lowest MED_, _prefer highest local-preference_ oder _prefer shorter AS paths_.

* **Optionen für Local/Global Routing:** Die Option 'Local Routing' ist die Standardoption für die Routenwahl. Sie bietet Zugriff auf Rechenzentren in demselben Markt wie der Direct Link-Bereitstellungspunkt (z. B. als DAL, AMS oder MEL bezeichnet). Die Option 'Global Routing' ist als Add-on erforderlich, um Ihre IBM Cloud-Ressourcen mit anderen IBM Cloud-Ressourcen in Rechenzentren außerhalb des lokalen Marktes zu verbinden. Sie wird verwendet, um Workloads durch mehrere IBM Cloud-Ressourcen gemeinsam zu nutzen (zum Beispiel durch Dallas und Ashburn oder durch Dallas und Frankfurt).

## Die Lösung IBM Cloud Direct Link Dedicated
{: #direct-link-dedicated-solution}

Mit der Lösung IBM Cloud Direct Link Dedicated können Kunden eine glasfaserbasierte Single-Tenant-Querverbindung zu ihrer eigenen privaten {{site.data.keyword.cloud_notm}}-Netzverbindung herstellen. Dieses Angebot kann von Kunden mit Colocation-Einrichtungen, die an IBM Cloud-Bereitstellungspunkte und -Rechenzentren grenzen, sowie von Netzserviceanbietern, die Verbindungen zum Kundenstandort oder zu anderen Rechenzentren bereitstellen, genutzt werden.

 **Übliche Anwendungsfälle:** _Optimal für hybride Workloads, Provider-übergreifende Workloads, umfangreiche oder häufige Datenübertragungen, private Workloads und die Umgebungsverwaltung. Diese Option wird meist in folgenden Fällen ausgewählt: 1. Der gewünschte Bereitstellungspunkt verfügt nicht über den gewünschten Exchange-Provider oder Netzserviceanbieter, 2. Hochleistungs-Workloads erfordern einen hohen Durchsatz oder 3. Es bestehen Compliance-Anforderungen, die von den Implementierungsmodellen IBM Cloud Direct Link Exchange und Connect nicht erfüllt werden können._
 
 **Anwendungsfall 1: Kundeneinrichtung zu IBM Cloud.**

![Abbildung 3](/images/Direct-link-Dedicated.png)

**Anwendungsfall 2: Kundencolocation zu IBM Cloud.**

![Abbildung 3B](/images/dedicated-model-colo.png)

 * **Abschlussort:** {{site.data.keyword.cloud_notm}}-Bereitstellungspunkt oder -Rechenzentrum.

 * **Typische Bereitstellungszeit:** 10 bis 15 Werktage, nachdem die neue Verbindung den Bereitstellungspunkt erreicht hat. Die gesamte Bereitstellungszeit kann je nach Standort und Anforderungen zwischen 30 und 60 Tagen liegen, wenn eine Verbindung bei einem NSP oder einem Netzbetreiber bestellt wird.

 * **Details zu Querverbindungen:** {{site.data.keyword.cloud_notm}} stellt ein Bevollmächtigungsschreiben (LOA, Letter of Authorization) bereit, mit dem ein Kunde Ethernet-Glasfaserverbindungen (nur Monomode-Glasfaser, entweder 1Gig-LX oder 10Gig-LR) bestellen kann, die vom Kunden oder Provider zum {{site.data.keyword.cloud_notm}}-CFA-Abschlusspunkt verlaufen, der an die Infrastruktur des Routers für Querverbindungen (XCR) angebunden ist. Die Wellenlänge hierbei muss 1310 nm betragen.

 * **Optionen für Portgeschwindigkeiten:** Sie können zwischen 1 Gb/s, 2 Gb/s, 5 Gb/s oder 10 Gb/s auswählen.

 * **Ungefähre Latenz:** Die Latenz beträgt ungefähr 1,5 ms im Nahbereich (Rechenzentren mit demselben Präfix aus drei Buchstaben wie DAL, AMS, MEL).  Unter http://lg.softlayer.com/ finden Sie Latenzmessungen für aktive PoP/PoP-Verbindungen (P2P-Verbindungen).

 * **IBM Colocation-Services:** Keine.

 * **Redundanz:** {{site.data.keyword.cloud_notm}} bietet Verbindungen zu zwei (2) verschiedenen Routern für Querverbindungen (XCR) als Teil des Produkts. Zum Einrichten der redundanten Konnektivität müssen die Kunden für jede Direct Link-Verbindung entsprechend ihren Präferenzen BGP konfigurieren. Als Beispiele können Optionen wie die folgenden angegeben werden: _prefer Lowest MED_, _prefer highest local-preference_ oder _prefer shorter AS paths_.

 * **Optionen für Local/Global Routing:** Die Option 'Local Routing' ist die Standardoption für die Routenwahl. Sie bietet Zugriff auf Rechenzentren in demselben Markt wie der Direct Link-Bereitstellungspunkt (z. B. als DAL, AMS oder MEL bezeichnet). Die Option 'Global Routing' ist als Add-on erforderlich, um Ihre IBM Cloud-Ressourcen mit anderen IBM Cloud-Ressourcen in Rechenzentren außerhalb des lokalen Marktes zu verbinden. Sie stellt eine Möglichkeit bereit, Workloads durch mehrere IBM Cloud-Ressourcen gemeinsam zu nutzen (zum Beispiel durch Dallas und Ashburn oder durch Dallas und Frankfurt).

## Die Lösung IBM Cloud Direct Link Dedicated Hosting
{: #direct-link-dedicated-hosting-solution}

Die Lösung IBM Cloud Direct Link Dedicated Hosting bietet eine ähnliche Konnektivität wie IBM Cloud Direct Link Dedicated, aber der Verbindungspunkt grenzt an ein {{site.data.keyword.cloud_notm}}-Rechenzentrum, was die Latenz für Anwendungsfälle mit höherer Leistung verbessert. IBM Cloud bietet im Rahmen dieser Lösung eine Reihe anpassbarer Colocation-Services mit einfacher Preisgestaltung.

**Übliche Anwendungsfälle:** _Optimal für die Arbeit mit vom Standard abweichenden Computing-Technologien, dediziertem Speicherbedarf oder für die Nutzung vorhandener IT-Investitionen._

![Abbildung 4](/images/Direct-Link-Dedicated-Hosting.png)

* **Abschlussort:** {{site.data.keyword.cloud_notm}}-Rechenzentrum (Data Center, DC).

 * **Typische Bereitstellungszeit:** 30 bis 60 Tage nach Klärung aller Anforderungen und Durchsetzung der Verträge.

 * **Details zu Querverbindungen:** {{site.data.keyword.cloud_notm}} bietet 1-G- oder 10-G-Glasfaserverbindungen von der Infrastruktur des {{site.data.keyword.cloud_notm}}-Routers für Querverbindungen (XCR) hin zur Colocation-Umgebung des Kunden als Teil der Bereitstellung.  Wenn keine Colocation-Services angefordert werden (wenn vorhandene Umgebungen bereits verbunden sind), stellt {{site.data.keyword.cloud_notm}} ein Bevollmächtigungsschreiben (LOA, Letter of Authorization) bereit, mit dem ein Kunde Ethernet-Glasfaserverbindungen (nur Einzelmodus-Glasfaserverbindungen, entweder 1Gig-LX oder 10Gig-LR) bestellen kann, die von einen Kunden oder Provider zu einem {{site.data.keyword.cloud_notm}} CFA-Abschlusspunkt verlaufen, der an die Infrastruktur des XCR-Routers angebunden ist. Die Wellenlänge hierbei muss 1310 nm betragen.

 * **Optionen für Portgeschwindigkeiten:** Sie können zwischen 1 Gb/s, 2 Gb/s, 5 Gb/s oder 10 Gb/s auswählen.

 * **Ungefähre Latenz:** Die Latenz beträgt ungefähr 0,5 ms im lokalen Rechenzentrum.

 * **IBM Colocation-Services:** Ja.

 * **Redundanz:** {{site.data.keyword.cloud_notm}} bietet Verbindungen zu zwei (2) verschiedenen Routern für Querverbindungen (XCR) als Teil des Produkts. Zum Einrichten der redundanten Konnektivität müssen die Kunden für jede Direct Link-Verbindung entsprechend ihren Präferenzen BGP konfigurieren. Als Beispiele können Optionen wie die folgenden angegeben werden: _prefer Lowest MED_, _prefer highest local-preference_ oder _prefer shorter AS paths_.

 * **Optionen für Local/Global Routing:** Die Option 'Local Routing' ist die Standardoption für die Routenwahl. Sie bietet Zugriff auf Rechenzentren in demselben Markt wie der Direct Link-Bereitstellungspunkt oder -PoP (z. B. als DAL, AMS oder MEL bezeichnet). Die Option 'Global Routing' ist als Add-on erforderlich, um Ihre IBM Cloud-Ressourcen mit anderen IBM Cloud-Ressourcen in Rechenzentren außerhalb des lokalen Marktes zu verbinden. Sie wird verwendet, um Workloads durch mehrere IBM Cloud-Ressourcen gemeinsam zu nutzen (zum Beispiel durch Dallas und Ashburn oder durch Dallas und Frankfurt).
