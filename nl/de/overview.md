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

# Übersicht über die Direct Link-Angebote
{ #overview-of-direct-link-offerings}

Die {{site.data.keyword.cloud}} Direct Link-Angebote stellen Konnektivität von einer externen Quelle in das private IBM Cloud-Netz eines Kunden bereit. Direct Link kann als Alternative zur traditionelle Site-to-Site-VPN-Lösung angesehen werden, die für Kunden konzipiert ist, die eine konsistentere Konnektivität mit höherem Durchsatz zwischen einem fernen Netz und ihren IBM Cloud-Umgebungen benötigen. Es stehen vier Verbindungstypen zur Verfügung:
 
 * Mit **IBM Cloud Direct Link Exchange** können Kunden einen Exchange-Provider für die Konnektivität zu ihrer IBM Cloud nutzen. Ein Exchange-Provider ist ein Netzbetreiber oder Netz-Provider, der bereits mit dem IBM Cloud-Netz über Multi-Tenant-Links mit hoher Kapazität verbunden ist. Kunden können meist eine virtuelle Verbindung bei diesem Provider erhalten, der Konnektivität zu reduzierten Kosten ermöglicht, da die physische Konnektivität von {{site.data.keyword.BluSoftlayer_notm}} zum Exchange-Provider bereits vorhanden ist und mit anderen Kunden gemeinsam genutzt wird.
 
 * Mit **IBM Cloud Direct Link Connect** können Kunden eine Verbindung durch unsere Partner nutzen, die ein Facility-basiertes Netz besitzen und betreiben. Mit IBM Cloud Direct Link Connect stellen IBM und der Partner Verbindungen zu Kunden auf Layer 2 und 3 über duale Layer-2-NNIs mit 10 G her.
 
 * Mit **IBM Cloud Direct Link Dedicated** können Kunden eine dedizierte Einzelmodus-Glasfaser-Querverbindung zu ihrem eigenen privaten IBM Cloud-Netz führen.
 
 * **IBM Cloud Direct Link Dedicated Hosting** bietet eine ähnliche Konnektivität wie IBM Cloud Direct Link Dedicated, aber der Verbindungspunkt grenzt an ein {{site.data.keyword.BluSoftlayer_notm}}Rechenzentrum an, das die Latenz für Anwendungsfälle mit höherer Leistung verbessert. IBM Cloud bietet im Rahmen dieser Lösung eine Reihe anpassbarer Colocation-Services.
  
Der Service 'Direct Link' von IBM Cloud ist ein auf OSI Layer-3 basierender Routing-Service. Er bietet bei einer niedrigen Latenz und Geschwindigkeiten von bis zu 10 Gb/s eine direkte Verbindung zum Backbone des privaten {{site.data.keyword.BluSoftlayer_notm}}-Netzes.
Für mehr Flexibilität bei der Erstellung dieser Layer-3-Konnektivität ermöglicht IBM Cloud Direct Link den Kunden die Nutzung folgender Möglichkeiten:
 * Dual IP für ferne Hosts
 * NAT
 * Tunnelung für BYOIP
 
 Eine detaillierte Beschreibung der einzelnen Angebote finden Sie unter [Informationen zu IBM Cloud Direct Link](/docs/infrastructure/direct-link?topic=direct-link-about-ibm-cloud-direct-link). 
