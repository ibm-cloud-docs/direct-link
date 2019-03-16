---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-19"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Modelle für Diversität und Redundanz in Direct Link
{: #models-for-diversity-and-redundancy-in-direct-link}

Dieses Dokument enthält eine Reihe schematischer Darstellungen im Zusammenhang mit Redundanz und Diversität, die Sie beim Auswählen eines Modells für die Erstellung der besten {{site.data.keyword.cloud}} Direct Link-Bereitstellung für Ihre Anforderungen unterstützen. Die schematischen Darstellungen sind nach zunehmender Komplexität und nach dem dargestellten Direct Link-Angebot geordnet. Direct Link ist kein Service mit inhärenter Redundanz am Router für Querverbindungen (XCR-Router); die Kunden sind für die Bereitstellung von Redundanz über ihre BGP-Schemas (Border Gateway Protocol) verantwortlich.  

## Abschnitt 1: Einfache Konfigurationen, die Diversität ermöglichen

Die Konfigurationen in dieser Gruppe setzen voraus, dass sich alle Assets am selben Bereitstellungspunkt und im selben globalen Markt befinden.

**Abbildung 1: Direct Link Exchange mit Diversität am selben Bereitstellungspunkt (ohne Verfügbarkeitszone)**

![Exchange mit Diversität am selben Bereitstellungspunkt](/images/exchange-diversity-same-pop.png)

**Abbildung 2: Direct Link Connect mit Diversität am selben Bereitstellungspunkt (ohne Verfügbarkeitszone)**

![Connect mit Diversität am selben Bereitstellungspunkt](/images/connect-diversity-same-pop.png)

**Abbildung 3: Direct Link Dedicated mit Diversität am selben Bereitstellungspunkt (ohne Verfügbarkeitszone)**

![Dedicated mit Diversität am selben Bereitstellungspunkt](/images/dedicated-diversity-same-pop.png)

## Abschnitt 2: Diversität mit Verfügbarkeitszonen und Global Routing-Optionen

Die Konfigurationen in dieser Gruppe bieten Verbindungsoptionen zwischen lokalen Verfügbarkeitszonen und Märkten

### Teil A: Diversität in einer lokalen Verfügbarkeitszone

**Abbildung 4: Direct Link Exchange mit Diversität in einer lokalen Verfügbarkeitszone (WDC, DAL, FRA, LON)**

![Exchange mit Diversität in der lokalen Verfügbarkeitszone](/images/exchange-diversity-local-az.png)

**Abbildung 5: Direct Link Connect mit Diversität in einer lokalen Verfügbarkeitszone (WDC, DAL, FRA, LON)**

![Connect mit Diversität in der lokalen Verfügbarkeitszone](/images/connect-diversity-local-az.png)

**Abbildung 6: Direct Link Dedicated mit Diversität in einer lokalen Verfügbarkeitszone (WDC, DAL, FRA, LON)**

![Dedicated mit Diversität in der lokalen Verfügbarkeitszone](/images/dedicated-diversity-local-az.png)

### Teil B: Diversität in verschiedenen lokalen Märkten mit Global Routing

**Abbildung 7: Direct Link Connect mit Diversität und Global Routing**

![Connect mit Diversität und Global Routing](/images/connect-diversity-global.png)

**Abbildung 8: Direct Link Exchange mit Diversität und Global Routing**

![Exchange mit Diversity und Global Routing](/images/exchange-diversity-global.png)

**Abbildung 9: Direct Link Dedicated mit Diversität und Global Routing**

![Dedicated mit Diversität und Global Routing](/images/dedicated-diversity-global.png)

## Weitere Informationen zu ECMP

ECMP ist eine Funktion von BGP. Einige Kunden haben den Wunsch geäußert, Redundanz mithilfe von ECMP bereitzustellen. ECMP allein reicht für diesen Zweck jedoch nicht aus. In diesem Abschnitt werden die Gründe dafür erläutert.

**F: Ist ECMP eine geeignete Methode für redundante Verbindungen? Welche Alternativen gibt es?**

ECMP wurde nicht zum Herstellen redundanter Verbindungen entwickelt, sondern für den Lastausgleich über zwei Links. Bei Verwendung von ECMP unter IBM Cloud müssen beide Verbindungen auf demselben Router für Querverbindungen (IBM Cloud-XCR) enden, der dadurch zu einem Single Point of Failure wird. (Mit anderen Worten: ECMP kann nur in zwei Sitzungen auf demselben IBM Cloud-XCR-Router bereitgestellt werden.)

**Abbildung 10: ECMP bereitstellen**

![ECMP-Modell für Dedicated](/images/ecmp-without-diversity.png)

### Vorgehensweise zum Bereitstellen von Diversität und Redundanz

Wenn Sie Hochverfügbarkeit (High Availability, HA) oder vollständige Redundanz erreichen möchten, richten Sie zwei Links zu verschiedenen XCR-Routern im selben Rechenzentrum (z. B. DAL03) ein. Anschließend können Sie die Funktionsübernahme nach Bedarf mithilfe von BGP-Konfigurationen bereitstellen.

**Abbildung 11: ECMP mit zwei XCR-Routern**

![ECMP-Modell mit zwei XCR-Routern](/images/ecmp-with-diversity.png)
