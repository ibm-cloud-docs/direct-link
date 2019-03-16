---
copyright:
  years: 1994, 2017, 2018, 2019
lastupdated: "2019-02-19"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Informationen zur Latenz
{: #understanding-latency}

_Hybridumgebung mit {{site.data.keyword.cloud}} Direct Link: Schnellere Verarbeitung Ihrer Workloads weltweit_

IBM Cloud stellt Rechenzentren mit Direct Link-Funktionen auf der ganzen Welt bereit. Dies bedeutet für Sie minimale Latenzzeiten, wenn Sie beim Erstellen einer eigenen Hybrid-Cloud-Lösung mithilfe von Direct Link Ihre IBM Cloud mit Ihrer bestehenden Infrastruktur verbinden.

Ganz egal, ob Sie ein Onlinegeschäft betreiben, Lösungen für Big Data einsetzen oder Ihre Mitarbeiter über das Netz auf Dateien in der ganzen Welt zugreifen. In jedem dieser Anwendungsfälle sind lange Ladezeiten beim Seitenaufbau im Web oder lange Wartezeiten bei der Datenübertragung aus einer Datenbank unerwünscht, da sie die Verkaufsaktivitäten ausbremsen bzw. die Produktivität Ihrer Mitarbeiter beeinträchtigen. Leistungsminderungen können durch die Netzlatenz (das ist der Messwert für die Datenübertragung zwischen zwei verbundenen Punkten im Internet) verursacht werden. Die Latenz ist der Zeitraum, der für die Übertragung eines Datenpakets von einem Ort an einen anderen benötigt wird.

Die Latenz im globalen Internet kann stark variieren, abhängig von der zurückzulegenden Strecke, der Anzahl der Datenübergänge (Hops) zwischen verschiedenen Servicedprovidern, der verfügbaren Bandbreite auf dem Übertragungsweg, dem Datenvolumen auf dem gewählten Übertragungsweg und von anderen Variablen. IBM Cloud Direct Link bietet deterministische Latenz mit erhöhter Sicherheit im Vergleich zum Internet - und damit eine vorhersehbare Leistung.


## Informationen zur Netzlatenz

Die Best Practice jedes Netzbetreibers zielt darauf ab, eine möglichst geringe Netzlatenz für möglichst viele Kunden bereitzustellen, und jeder Kunde wünscht sich möglichst kurze Latenzzeiten. Das ist der gemeinsame Wunsch aller Beteiligten.

In der Theorie können Glasfaserkabel Daten mit Lichtgeschwindigkeit übertragen, doch in der Praxis werden aus den oben genannten Gründen wesentlich niedrigere Übertragungsgeschwindigkeiten erzielt. Angenommen, die Bandbreitenkapazität für eine bestimmte Netzverbindung ist ausgeschöpft. In diesem Fall werden Datenpakete vorübergehend in eine Warteschlange eingereiht, bis der Übertragungsweg wieder frei ist. Ein weiteres Beispiel: Wenn im Netz eines Serviceproviders eine nicht optimale Netzroute ausgewählt wird, weichen Datenpakete möglicherweise mehrere hunderttausend Kilometer von der idealen Route zum Ziel ab. Solche Verzögerungen und Umwege führen zu einer höheren Netzlatenz und bremsen die Datenübertragung aus.

Die Netzlatenz wird in Millisekunden gemessen (eine Sekunde besteht aus 1.000 Millisekunden). Ein paar Tausendstelsekunden sind keine wirklich lange Zeit, aber im täglichen Alltagsgeschäft können Millisekunden beim Aufrufen von Webseiten oder bei Geschäftstransaktionen zu einem entscheidenden Faktor werden. Im Finanzsektor können Millisekunden beispielsweise bei alltäglichen Handelstransaktionen Verluste oder Gewinne in Milliardenhöhe verursachen.

## Allgemeine Ansätze zur Minimierung der Netzlatenz

Wenn das gemeinsame Ziel die Minimierung der Latenz ist, macht es Sinn, die Anzahl der potenziellen Variablen zu begrenzen, die sich auf die Geschwindigkeit der Datenübertragung auswirken können. Kein Provider kann den Übertragungsweg von Daten im Internet lückenlos steuern, doch mit den folgenden bewährten Verfahren kann die Netzlatenz minimiert werden:

 * Globale Verteilung der Daten: Kunden an verschiedenen Standorten können Daten jeweils von dem nächstgelegenen geografischen Standort abrufen. Durch die relative Nähe des Speicherorts wird die Zahl der erforderlichen Zwischenschritte bei der Datenübertragung reduziert. Je kürzer die zu überwindende Distanz, umso geringer die Beeinträchtigung der Übertragungsleistung durch die Routenwahl.

 * Bereitstellung von Serverports mit hoher Kapazität: Der Server kann hohe Datenvolumen pro Sekunde übertragen. Wenn Datenpakete durch voll ausgelastete Ports verzögert werden, gehen Millisekunden verloren, Seiten werden langsamer aufgebaut, die Downloadgeschwindigkeiten nehmen ab und die Benutzer werden ungeduldig.

 * Die vom Provider festgelegte Routenwahl für die Datenübertragung verstehen: Wer gut einschätzen kann, wie die eigenen Daten den Weg zu Kunden in der ganzen Welt finden, der kann fundierte Entscheidungen über geeignete Standorte für das Hosting der Daten treffen.

## Wie geht IBM Cloud beim Minimieren der Netzlatenz vor?

Zur Minimierung der Latenzzeiten wurde in IBM Cloud ein einzigartiges Konzept für den Netzaufbau gewählt. Alle unsere Rechenzentren sind mit Netzbereitstellungspunkten (Points of Presence, PoPs) verbunden und alle Netzbereitstellungspunkte sind über unser globales Backbone-Netz miteinander verbunden. Durch die Pflege eines eigenen globalen Backbone-Netzes können unsere Netzoperationen die Netzpfade und die Datenübertragungen genauer steuern als beim länderübergreifenden Datenverkehr mit Beteiligung anderer Provider.
 
Beispiel: Ein IBM Cloud-Kunde in Berlin möchte ein Video über Katzen sehen, das auf einem IBM Cloud-Server in Dallas gehostet wird. Die Datenpakete für dieses Katzenvideo werden in unserem Backbone-Netz (das nur für den IBM Cloud-Datenverkehr genutzt wird) nach Frankfurt übertragen. Von dort werden die Pakete an einen unserer Serviceprovider für Netzpeering oder für die Datenübertragung in öffentlichen Netzen gesendet und erreichen schließlich den Benutzer in Berlin. Noch besser ist es, wenn der Kunde die CDN-Funktionalität von IBM Cloud nutzt. In diesem Fall werden die Pakete von einem Edge-Server in der Nähe des Kundenstandorts weitergeleitet, d. h. sie müssen nicht von Dallas aus versendet werden.

Ohne ein globales Babkbone-Netz werden Videodatenpakete an einen Serviceprovider für Netzpeering oder für die Datenübertragung in öffentlichen Netzen in Dallas gesendet und im Netz dieses Providers weitergeleitet oder über einen Netzhop an einen anderen Provider weitergeleitet, bis sie schließlich über viele Stationen ihr Ziel in Deutschland erreichen. Es kann durchaus vorkommen, dass die Pakete den Weg von Dallas nach Berlin mit der gleichen Netzlatenz zurücklegen wie bei der Übertragung im globalen Backbone-Netz. Doch ohne das globale Backbone-Netz kommen mehr Variablen ins Spiel. Dabei unterliegt die Gesamtlatenz stärkeren Schwankungen und ist schwerer vorherzusagen.

Neben der Nutzung des eigenen globalen Backbone-Netzes teilt IBM Cloud den Datenverkehr in Segmente für öffentliche, private und Managementdaten auf, die über verschiedene Netzports geleitet werden. Auf diese Weise können unterschiedliche Arten von Datenverkehr unabhängig voneinander übertragen werden.

## Zusammenfassung: Netzlatenz

Ihre Kunden möchten so schnell wie möglich auf die gewünschten Daten aus Ihrem Datenbestand zugreifen. Der Zeitraum bis zum Empfang der Daten über das Internet wird als Netzlatenz bezeichnet. Je genauer Sie den Netzpfad für Ihre Daten steuern können, umso konsistenter (und kürzer) kann die Netzlatenz sein.

* Mit Direct Link können Sie den Pfad steuern, den Ihre Daten im Netz zurücklegen, um Unterbrechungen oder Blockaden durch anderen Datenverkehr zu vermeiden.

* IBM Cloud arbeitet mit führenden Serviceprovidern der Branche zusammen und bietet einen hohen Standard in Bezug auf Leistung, Datenschutz und Ausfallsicherheit.

* In IBM Cloud wird das globale Netz der Bereitstellungspunkte ständig erweitert, um den Weg der Daten zum Kunden zu verkürzen, die Latenzzeiten zu minimieren und die Gesamtleistung an die Anforderungen Ihrer Hybrid-Cloud-Workloads anzupassen.

