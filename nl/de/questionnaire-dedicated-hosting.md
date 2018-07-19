---

copyright:
  years: 2018
lastupdated: "2018-06-11"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Fragebogen für IBM Cloud Direct Link Dedicated

Danke für Ihre Anforderung von IBM Cloud Direct Link Dedicated Hosting. Für die Bearbeitung Ihrer Anforderung benötigen wir weitere Informationen von Ihnen. Beim Ausfüllen des Fragebogens können Sie jederzeit direkt mit einem Entwickler in Kontakt treten. Der von Ihnen ausgefüllte Fragebogen wird von unserem Entwicklungsteam für Cloud Design überprüft und zur Implementierung an die Abteilung für Network Engineering weitergeleitet.

## Bestätigungen

1. Die in diesem Fragebogen dargestellten Kosten beinhalten die Kosten für die Beendigung des Service in der IBM Cloud-Netzinfrastruktur. Im Rahmen der Zusammenstellungskosten, einschließlich Gehäuseschränke, Querverbindungen usw. fallen monatliche und einmalige Gebühren an, die im Rahmen einer Zusammenstellungsvereinbarung separat niedergelegt werden. 

2. IBM Cloud Direct Link Dedicated Hosting stellt Glasfaser-Querverbindungen mit 1 Gb/s oder 10 Gb/s zum privaten IBM Cloud-Netz bereit. Sie müssen einen Router oder einen Layer 3-Switch bereitstellen, der Einzelmodus-Glasfaser-Uplinks unterstützen kann. Die Bereitstellungszeit kann je nach Verbindungsprovider variieren. Die typische Implementierungszeit für diesen Service beträgt 30 bis 60 Tage.

3. Direct Link Dedicated Hosting erfordert die Verwendung einer VRF-Instanz (VRF = Virtual Routing and Forwarding). Dies ermöglicht dem Kunden das Definieren von eigenen fernen IP-Adressen für die Verwendung im eigenen fernen Netz. Beachten Sie jedoch, dass auch bei Verwendung des 10.x.x.x-Netzes keine Überschneidungen mit Ihren Hosts in IBM Cloud oder mit dem IBM Cloud-Servicenetz (10.0.0.0/14, 10.198.0.0/15 und 10.200.0.0/14) auftreten dürfen. Für den Übergang von Ihrem Konto auf eine VRF ist eine kurze Betriebsunterbrechung des privaten Netzes erforderlich, während jedes VLAN auf die neue Konfiguration migriert wird. Das Network Engineering-Team legt in Absprache mit Ihnen ein geeignetes Zeitfenster für diesen Vorgang fest.

4. VRF modifiziert das Verhalten von IBM Cloud SSL, PPTP und IPsec VPN. Diese Services können in der Regel genutzt werden, wenn eine VPN-Verbindung zu dem Rechenzentrum hergestellt wird, in dem die aufgerufenen Compute-Ressourcen ausgeführt werden. Der globale Zugriff ist hierbei jedoch nicht zulässig. Eine Alternative ist die Verwendung von Direct Link für die Verwaltung Ihrer Server oder die Ausführung einer eigenen VPN-Lösung (z. B. Vyatta), die mit unterschiedlichen VPN-Typen konfiguriert werden kann. 

5. Direct Link Dedicated Hosting erfordert BGP zum Implementieren der Routen zum fernen Netz eines Kunden. IBM Cloud implementiert keine Filter für die an IBM Cloud gesendeten Mitteilungen. IBM Cloud macht alle  privaten Teilnetze zugänglich, die Ihrem Konto zugeordnet sind. Die Kunden müssen von IBM Cloud empfangene Mitteilungen ordnungsgemäß verwalten.

6. IBM Cloud stellt auf jedem IBM Cloud-Router für Querverbindungen (XCR-Router) duale Uplinks bereit, damit die Kunden redundante Konnektivität einrichten können. Auf dem/den Routern des Kunden wird dies durch BGP-Sitzungen durch die Verwendung der ECMP-Funktionen erreicht oder einfach durch die Gewichtung der Verbindungen.

7. Das IBM Cloud-Servicenetz ist über Ihre Dedicated Hosting-Verbindngen oder Ihre fernen Netze nicht direkt zugänglich.

8. IBM Cloud ermöglicht Ihnen nicht die Rückübertragung des Datenverkehrs zwischen Ihren fernen Standorten über das IBM Cloud-Backbone. Der Direct Link-Service soll Ihren fernen Netzen die private Kommunikation mit Ihrer IBM Cloud-Infrastruktur ermöglichen.

9. IBM Cloud stellt Direct Link mit Local Routing oder Global Routing zur Verfügung. Bestätigen Sie bitte, welches Routing-Paket Sie benötigen, und stimmen Sie den zugehörigen Kostenplänen für die Bandbreite zu, die über den folgenden Link aufgerufen werden können: ibm.biz/DirectLink-Docs.

10. Geben Sie bitte an, welches Datenvolumen über Ihre Direct Link-Verbindung fließen soll und in welche IBM Cloud-Rechenzentren dieser Datenverkehr fließen soll.

11. Wenn Sie keine Zusammenstellungsservices über IBM Cloud erwerben, sind Sie selbst für die Bestellung und Bezahlung der Querverbindungen zwischen Ihrer Umgebung und IBM Cloud verantwortlich. Sobald die Verbindung eingerichtet ist, stellen wir ein Bevollmächtigungsschreiben bereit, aus dem unsere Genehmigung für Ihre Verbindung und der Zielstandort für die Verbindung hervorgehen.

12. Stimmen Sie den folgenden Preisen für Direct Link zu:
 * 1 Gb/s: _STANDORTABHÄNGIGE PREISE_ 
* 2 Gb/s: _STANDORTABHÄNGIGE PREISE_
* 5 Gb/s: _STANDORTABHÄNGIGE PREISE_
* 10 Gb/s: _STANDORTABHÄNGIGE PREISE_
* Global Routing (optional)
