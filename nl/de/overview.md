---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-04-02"

keywords: overview, connectivity, private network, site-to-site, Exchange, Connect, Dedicated, Hosting, OSI, Layer-3, partners, NNI, latency, backbone

subcollection: direct-link

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Übersicht über die Direct Link-Angebote
{: #overview-of-direct-link-offerings}

Die {{site.data.keyword.cloud}} Direct Link-Angebote stellen Konnektivität von einer externen Quelle in das private IBM Cloud-Netz eines Kunden bereit. Direct Link kann als Alternative zur traditionelle Site-to-Site-VPN-Lösung angesehen werden, die für Kunden konzipiert ist, die eine konsistentere Konnektivität mit höherem Durchsatz zwischen einem fernen Netz und ihren IBM Cloud-Umgebungen benötigen. Es stehen vier Verbindungstypen zur Verfügung:
 
 * Mit **IBM Cloud Direct Link Exchange** können Kunden einen Exchange-Provider für die Konnektivität zu ihrer IBM Cloud nutzen. Ein Exchange-Provider ist ein Colocation- oder Rechenzentrumsprovider, der bereits mit dem {{site.data.keyword.cloud_notm}}-Netz verbunden ist, und zwar über Multi-Tenant-Verbindungen mit hoher Kapazität (auch bekannt als _Network-to-Network Interface_ oder NNI). Kunden können meist eine virtuelle Verbindung bei diesem Provider erwerben, der Konnektivität zu reduzierten Kosten ermöglicht, da die physische Verbindung von {{site.data.keyword.cloud_notm}} zum Exchange-Provider bereits vorhanden ist und mit anderen Kunden gemeinsam genutzt wird.
 
 * Mit **IBM Cloud Direct Link Connect** können Kunden eine Verbindung über unsere Netzbetreiberpartner nutzen, die ein Facility-basiertes Netz besitzen und betreiben. Ein Connect-Provider ist ein Netzserviceanbieter, der bereits mit dem {{site.data.keyword.cloud_notm}}-Netz über Multi-Tenant-Verbindungen mit hoher Kapazität (auch bekannt als _Network-to-Network Interface_ oder NNI) verbunden ist. Kunden können meist eine virtuelle Verbindung bei diesem Provider erwerben, der Konnektivität zu reduzierten Kosten ermöglicht, da die physische Verbindung von {{site.data.keyword.cloud_notm}} zum Connect-Provider bereits vorhanden ist und mit anderen Kunden gemeinsam genutzt wird.
 
 * Mit **IBM Cloud Direct Link Dedicated** können Kunden eine glasfaserbasierte Single-Tenant-Querverbindung zum {{site.data.keyword.cloud_notm}}-Netz herstellen. Dieses Angebot kann von Kunden mit Colocation-Räumlichkeiten, die an IBM Cloud-Bereitstellungspunkte und -Rechenzentren grenzen, sowie von Netzserviceanbietern, die Verbindungen zum Kundenstandort oder zu anderen Rechenzentren bereitstellen, genutzt werden.
 
 * **IBM Cloud Direct Link Dedicated Hosting** bietet eine ähnliche Konnektivität wie {{site.data.keyword.cloud_notm}} Direct Link Dedicated, aber der Verbindungspunkt grenzt an ein {{site.data.keyword.cloud_notm}}-Rechenzentrum, was die Latenz bei Anwendungsfällen mit höheren Leistungsanforderungen verbessert. {{site.data.keyword.cloud_notm}} bietet im Rahmen dieser Lösung eine Reihe anpassbarer Colocation-Services an.
  
Der Service {{site.data.keyword.cloud_notm}} Direct Link ist ein auf OSI-Layer-3 basierender Routing-Service. Er bietet bei einer niedrigen Latenz und Geschwindigkeiten von bis zu 10 Gb/s eine direkte Verbindung zum Backbone des privaten {{site.data.keyword.cloud_notm}}-Netzes.
Für mehr Flexibilität bei der Erstellung dieser Layer-3-Konnektivität ermöglicht {{site.data.keyword.cloud_notm}} Direct Link den Kunden die Nutzung folgender Möglichkeiten:
 * Dual IP für ferne Hosts
 * NAT
 * Tunnelung für BYOIP
 
 Eine detaillierte Beschreibung der einzelnen Angebote finden Sie unter [Informationen zu IBM Cloud Direct Link](/docs/infrastructure/direct-link?topic=direct-link-about-ibm-cloud-direct-link).
