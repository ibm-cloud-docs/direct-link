---
copyright:
  years: 1994, 2017, 2018
lastupdated: "2018-05-07"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Informazioni sulla latenza

_Modalità ibrida con IBM Cloud Direct Link: rendi l'esecuzione dei tuoi carichi di lavoro più veloce, in tutto il mondo_

IBM Cloud offre dei data center con la funzionalità Direct Link in tutto il mondo. Pertanto, puoi contare sulla latenza minima quando utilizzi Direct Link per creare la tua soluzione cloud ibrida collegando il tuo IBM Cloud alla tua infrastruttura esistente.

Se disponi di un negozio online, esegui le soluzioni big data o configura i tuoi dipendenti su una rete con l'accesso ai file in tutto il mondo-non vuoi sentire per alcun motivo che il lento caricamento della pagina o il lento trasferimento dei dati da un database, ti impedisce una vendita o riduce la produttività dei tuoi dipendenti. I rallentamenti possono essere causati dalla latenza di rete, che è la misurazione di quanto velocemente i dati si spostano tra due punti collegati su internet. Puoi considerarla come la quantità di tempo che un pacchetto di dati impiega per passare da un posto all'altro.

Globalmente, la latenza complessiva di internet può variare in modo significativo—a seconda di quanto i dati devono essere trasmessi fisicamente, di quante volte i dati devono spostarsi tra i provider di servizi, di quanta larghezza di banda è disponibile lungo il percorso, di quali altri dati sono in movimento attraverso lo stesso percorso, in aggiunta ad altre variabili. IBM Cloud Direct Link offre una latenza deterministica con maggiore sicurezza, relativa a internet per prestazioni prevedibili.


## Informazioni sulla latenza di rete

Come procedura ottimale, ogni provider di rete desidera offrire la latenza di rete più bassa al numero maggiore di clienti e ogni cliente desidera ottenere la latenza più bassa possibile. È un risultato desiderabile e condiviso.

Teoricamente, i dati possono essere trasmessi alla velocità della luce attraverso i cavi di rete a fibra ottica, ma per tutti i motivi appena forniti, i dati normalmente viaggiano molto più lentamente. Ad esempio, se una connessione di rete specifica ha raggiunto la sua capacità di larghezza di banda, i pacchetti di dati potrebbe essere temporaneamente accodati in attesa del loro turno per spostarsi tramite tale percorso di comunicazione. Come altro esempio, se una particolare rete del provider di servizi seleziona una rotta di rete non ottimale, i pacchetti di dati possono essere inviati a centinaia o migliaia di miglia distanti dalla loro destinazione nel processo di raggiungerla! Questi tipi di ritardi e deviazioni sono le cause della latenza di rete più elevata—e di trasferimenti di dati più lenti.

Esprimiamo la latenza di rete in millisecondi (ovvero 1.000 millisecondi al secondo). Pochi millesimi di secondo non significano molto per noi mentre viviamo le nostre vite giornaliere, ma i millisecondi diventano spesso un fattore decisivo nella nostra esplorazione web o nelle nostre transazioni di business. Ad esempio, nel settore finanziario, i millisecondi possono significare miliardi di dollari di differenza tra i guadagni o le perdite dalle transazioni commerciali su base giornaliera.

## Approcci comuni che minimizzano la latenza di rete

Dato che il nostro obiettivo condiviso è di minimizzare la latenza, ha senso limitare il numero di variabili potenziali che possono influire sulla velocità dello spostamento dei dati. Nessun provider può ottenere il controllo completo su come i dati vengono trasmessi su internet, ma queste sono alcune procedure ottimali per ridurre al minimo la latenza di rete:

 * Distribuisci i dati in tutto il mondo: i clienti in diverse ubicazioni possono estrarre i dati da un'ubicazione geograficamente vicina a loro. Poiché i dati sono più vicini ai clienti, vengono trasmessi meno volte. Quando i dati hanno una distanza inferiore di trasmissione, l'instradamento è meno probabile che possa causare un impatto significativo sulle prestazioni.

 * Esegui il provisioning di server con porte di rete ad elevata capacità: elevati volumi di dati possono essere trasmessi attraverso un server ogni secondo. Se i pacchetti vengono ritardati a causa di porte completamente saturate, passano dei millisecondi, le pagine si caricano più lentamente, le velocità dei download scendono e gli utenti non sono soddisfatti.

 * Comprendi come il tuo provider instrada il traffico: quando conosci ulteriori dettagli su come i tuoi dati vengono trasferiti ai clienti in tutto il mondo, puoi prendere decisioni migliori su dove ospitare i tuoi dati.

## Come IBM Cloud minimizza la latenza di rete

Per minimizzare la latenza, IBM Cloud ha adottato un approccio unico per creare la nostra rete. Tutti i nostri data center sono collegati ai PoP (point of presence) di rete e tutti i nostri PoP di rete sono collegati tra loro tramite la nostra rete globale di backbone. Poiché manteniamo la nostra rete di backbone globale, il nostro team delle operazioni di rete può controllare i percorsi di rete e i trasferimenti di dati in modo più accurato rispetto a quando ci siamo affidati ad altri provider per spostare i dati tra le aree geografiche.
 
Ad esempio, se un cliente IBM Cloud a Berlino desidera guardare un video di un gatto ospitato su un server IBM Cloud a Dallas, i pacchetti di dati che compongono quel video del gatto saranno trasmessi tramite la nostra rete di backbone (che è utilizzata esclusivamente dal traffico IBM Cloud) a Francoforte, dove i pacchetti vengono inviati a uno dei nostri provider di servizi di rete pubblica di transito o di peer, per raggiungere infine l'utente in Berlino. Ancora meglio, se il nostro cliente utilizza la funzionalità CDN di IBM Cloud, i pacchetti verranno inviati da un server edge ubicato vicino al cliente e non dovranno per alcun motivo essere inviati da Dallas.

Senza una rete di backbone globale, i pacchetti video vengono inviati a un provider di rete pubblica di transito o di peer in Dallas, poi tale provider instrada i pacchetti attraverso la sua rete o li invia a un altro provider a un hop di rete e infine i pacchetti vengono recapitati sul loro percorso in Germania. È del tutto possibile che i pacchetti possano arrivare da Dallas a Berlino con la stessa latenza di rete senza utilizzare la rete di backbone globale, ma senza di essa esistono più variabili; la latenza totale è molto più difficile da garantire o da prevedere.

Insieme all'utilizzo della nostra rete di backbone globale, IBM Cloud segmenta anche il traffico pubblico, privato e di gestione nelle diverse porte di rete. Questo significa che tipi diversi di traffico vengono trasferiti senza interferire tra loro.

## Riepilogo: latenza di rete

I tuoi clienti vogliono i tuoi dati nel modo più veloce possibile in cui puoi offrirli loro. Il tempo impiegato dai tuoi dati per arrivare a essi attraverso internet è chiamato latenza di rete. Più controllo hai sul percorso di rete dei tuoi dati, più coerente (e minore) può essere la tua latenza di rete.

* Con Direct Link, ti diamo il controllo sul percorso dei tuoi trasferimenti di dati, per cui il tuo trasferimento di dati non sarà interrotto o bloccato da altro traffico.

* IBM Cloud offre provider di servizi leader del settore-- fornendo elevate prestazioni, sicurezza e resilienza.

* In IBM Cloud, continuiamo ad aggiungere PoP (Points of Presence) in tutto il mondo per portare i dati dei tuoi clienti più vicini a loro-- migliorando quindi la latenza e le prestazioni generali per soddisfare le esigenze dei tuoi carichi di lavoro cloud ibridi.

