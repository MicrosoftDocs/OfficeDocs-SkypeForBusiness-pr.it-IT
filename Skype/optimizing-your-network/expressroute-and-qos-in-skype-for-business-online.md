---
title: "ExpressRoute e QoS in Skype for Business online"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/12/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 20c654da-30ee-4e4f-a764-8b7d8844431d
description: "Learn about using Azure ExpressRoute to have a network with bandwidth requirements and Quality of Service capability for a business class user experience. "
---

# ExpressRoute e QoS in Skype for Business online

Connettiti a Office 365 su una connessione di rete dedicata utilizzando Azure ExpressRoute per Office 365 e Skype for Business online. La tua connessione dedicata per le app Skype for Business ti offrirà privacy e prestazioni affidabili e prevedibili lontano dalla rete Internet pubblica. Ora puoi acquistare una connessione di rete migliore per Office 365 e Skype for Business online in grado di aggiungere prevedibilità e affidabilità di livello aziendale con un contratto di servizio (SLA) attivo.
  
> [!NOTE]
> È disponibile una nuova versione dello strumento Bandwidth Calculator: [Skype for Business, Bandwidth Calculator](http://go.microsoft.com/fwlink/?LinkId=715766) . Le istruzioni di questo documento, tuttavia, utilizzano Bandwidth Calculator di Lync 2010 e 2013.
  
## Skype for Business online ed ExpressRoute

Lavorando con un partner ExpressRoute di Microsoft, puoi connettere una vasta gamma di applicazioni Office 365, tra cui Skype for Business online, nel cloud su una connessione dedicata. Tuttavia, le funzionalità di comunicazione voce e video in tempo reale per Skype for Business richiedono servizi di rete specificamente configurati per supportare i carichi di lavoro di Office 365 in tempo reale. Ciò comprende una rete che abbia una larghezza di banda sufficiente per supportare il volume di traffico richiesto e che sia in grado di supportare la qualità del servizio (QoS, Quality of Service) per offrire agli utenti un'esperienza di livello aziendale.
  
Oltre a guidare l'utente nel processo di progettazione mediante un caso di studio, lo scopo del presente documento è quello di aiutare l'utente, gli amministratori e i progettisti di rete a comprendere le sfide richieste per supportare le comunicazioni in tempo reale, gli strumenti forniti da Microsoft per la progettazione di una rete che soddisfi tali requisiti.
  
Nella prima parte del documento viene presentato il caso di una progettazione di rete effettuata utilizzando [Bandwidth Calculator di Lync 2010 e 2013](http://go.microsoft.com/fwlink/?LinkId=690282) per calcolare i requisiti di rete in una distribuzione estesa e multisito di Skype for Business ExpressRoute. Nella seconda parte del documento, vengono descritti i concetti fondamentali della qualità del servizio (QoS, Quality of Service), un approfondimento dei dettagli tecnici specifici per supportare le comunicazioni Skype for Business in tempo reale e i tipi di servizi di rete specifici richiesti.
  
Tutte le informazioni fornite offriranno i dettagli tecnici e una panoramica di QoS ed ExpressRoute, una descrizione delle sfide specifiche correlate e una conoscenza operativa degli strumenti e delle tecniche per una distribuzione corretta di ExpressRoute sulla rete Skype for Business.
  
## Attività iniziali

Quando ci si prepara all'implementazione di ExpressRoute per Skype for Business, è consigliabile dare un'occhiata ai diversi modelli di connessione ExpressRoute e alla scelta dei partner e delle posizioni, quindi informarsi su come acquistare ed eseguire il provisioning di ExpressRoute all'interno dell'azienda. Ecco alcune risorse per iniziare:
  
- [Azure ExpressRoute]( http://go.microsoft.com/fwlink/?LinkId=690283)
    
- [Prezzi ExpressRoute](http://go.microsoft.com/fwlink/?LinkId=690284)
    
- [Documentazione ExpressRoute](http://go.microsoft.com/fwlink/?LinkId=690285)
    
## Parte 1: caso di studio - ExpressRoute per Dewey Law, LLC.

Questo caso di studio per Dewey Law, LLC. ti mostrerà come configurare una rete, ordinare i servizi di accesso e determinare i requisiti di larghezza di banda per supportare ExpressRoute per Skype for Business online.
  
 **Background** Dewy Law LLC. è una grande società legale nazionale con 790 avvocati e un totale di 5.580 dipendenti distribuiti in 78 sedi. L'azienda ha sede centrale a New York e dispone di tre uffici regionali a Chicago, San Francisco e Dallas, oltre a 24 filiali di grandi dimensioni e 50 di piccole dimensioni, sparse in tutto il paese. L'azienda gestisce casi complessi con un carico di lavoro generalmente diffuso su due o più uffici, con un notevole traffico di rete da un ufficio all'altro.
  
Dewy Law LLC. è un'azienda relativamente giovane con avvocati e dipendenti che utilizzano la tecnologia quotidianamente e con grande dimestichezza.
  
 **Distribuzione degli utenti per località e sedi**
  
||**Sede centrale (NY)**|**Uffici regionali (3)**|**Grandi filiali (24)**|**Piccole filiali (50)**|
|:-----|:-----|:-----|:-----|:-----|
|Dirigenti  <br/> |20  <br/> |10  <br/> |1  <br/> |1  <br/> |
|Partner  <br/> |150  <br/> |50  <br/> |10  <br/> |5  <br/> |
|Società collegate  <br/> |300  <br/> |100  <br/> |20  <br/> |10  <br/> |
|Assistenti legali  <br/> |400  <br/> |125  <br/> |30  <br/> |15  <br/> |
|Amministratori esecutivi  <br/> |100  <br/> |35  <br/> |6  <br/> |3  <br/> |
|Amministrazione generale e IT  <br/> |100  <br/> |25  <br/> |3  <br/> |2  <br/> |
|Totale per sito  <br/> |1.070  <br/> |345  <br/> |70  <br/> |36  <br/> |
|Totale per classe di sito  <br/> |1.070  <br/> |1.035  <br/> |1.680  <br/> |1.800  <br/> |
   
### Configurazione della rete

Per offrire servizi in tempo reale di alta qualità e coerenti per Dewey Law LLC., è necessario soddisfare alcuni requisiti di base:
  
- L'azienda ha l'esigenza di fornire servizi vocali durante le interruzioni della rete, pertanto gli switch e i router della distribuzione di rete devono poter fornire un PoE (Power over Ethernet) di tipo IEEE 802.3af o 802.3at.
    
- Gli switch e i router di rete devono inoltre utilizzare gruppi di continuità elettrica (UPS) in modo da continuare a funzionare durante le interruzioni dell'alimentazione.
    
    Poiché l'azienda dispone di connessioni Wi-Fi verso gli uffici LAN, è altamente consigliabile l'utilizzo di un partner di infrastruttura Wi-Fi Skype for Business certificato, appartenente alle [soluzioni Skype for Business](http://go.microsoft.com/fwlink/?LinkId=690281)
    
    > [!TIP]
    > Sono consigliati i punti di accesso wireless 802.11n e 802.11ac. 
  
- Inoltre, aspetto ancora più importante, tutte le reti LAN in tutti gli uffici devono essere configurate per fornire la qualità del servizio (QoS, Quality of Service). In questa operazione sono compresi PC, laptop e qualsiasi hardware di rete, come switch e router.
    
Una volta soddisfatti questi requisiti fondamentali, per fornire servizi vocali di livello aziendale per Dewey Law LLC., consigliamo l'utilizzo del servizio IP MPLS (Multi-Protocol Label Switching) da un partner di servizio di rete collegato al servizio Azure ExpressRoute. MPLS offre un servizio IP con prestazioni garantite in caso di ritardi, instabilità e perdite dei pacchetti. Tuttavia, se MPLS non è disponibile, è possibile utilizzare anche Ethernet connesso ai nostri partner di scambio dati ExpressRoute.
  
I provider MPLS offrono diversi livelli di classi di servizio ma ciascuno utilizza termini differenti per identificarli. È necessario lavorare a stretto contatto con il provider per avere la certezza che vengano recepiti i dati inseriti in [Bandwidth Calculator di Lync 2010 e 2013](http://go.microsoft.com/fwlink/?LinkID=690282), nonché le opzioni disponibili consigliate per le diverse applicazioni di carico di lavoro in tempo reale di Office 365.
  
Sono disponibili due opzioni per la mappatura dei dati delle applicazioni Skype for Business alle classi di servizio MPLS appropriate:
  
- Contrassegno endpoint del traffico mediante DSCP (DiffServ Control Point)
    
- Assegnazione basata sull'elenco di controllo di accesso (ACL, Access Control List) di rete
    
Per implementare il contrassegno endpoint, è necessario configurare tutte le macchine Windows aggiunte a un dominio per Dewey Law LLC. in modo da contrassegnare ciascun pacchetto con il contrassegno DSCP (DiffServ Control Point) appropriato e implementare la QoS su tutti gli switch e i router di rete in tutte le sedi degli uffici così da assicurarsi che i contrassegni QoS siano mantenuti e non rimossi. I contrassegni DSCP sui pacchetti di rete indicano al provider di servizi la priorità assegnata al pacchetto. **Ulteriori informazioni su DSCP sono disponibili nella sezione QoS nella Parte 2.**
  
Per l'assegnazione basata sull'ACL di rete, i contrassegni di priorità DSCP sono implementati su un router upstream e si basano sulla porta di origine UDP. Gli intervalli di porta consigliati per ciascuna applicazione sono elencati nella sezione 2.6.1.1 della guida [Network Planning, Monitoring, and Troubleshooting with Lync Server (Pianificazione della rete, monitoraggio e risoluzione dei problemi con Lync Server)](http://go.microsoft.com/fwlink/?LinkId=690286). È importante coordinare tali informazioni con l'implementazione e la progettazione generale di Dewey Law LLC, nonché essere a conoscenza dei diversi criteri QoS e delle possibili mancate corrispondenze tra i contrassegni dei pacchetti.
  
Ogni provider di servizi di rete ExpressRoute avrà una classe di servizio (CoS) appropriata per voce e video in tempo reale. Tale classe di servizio (CoS) è denominata "Expedited Forwarding" (EF) per la voce e "Assured Forwarding" (AF) per il video. È necessario prestare molta attenzione al dimensionamento della quantità di larghezza di banda acquistata per il traffico voce EF. Ciò è dovuto al fatto che la classe di servizio per la voce non lascia soluzioni in caso di invio di una quantità maggiore di traffico vocale di quella prevista.
  
> [!TIP]
> Tutto il traffico in eccesso inviato alla classe di servizio voce rispetto a quanto prestabilito dal provider di servizi viene immediatamente eliminato con effetti negativi sulla qualità vocale. 
  
Durante la progettazione globale di Dewey Law LLC. è estremamente importante stabilire in modo preciso la quantità di larghezza di banda di rete necessaria per supportare il traffico vocale sulle reti disponibili e contrassegnare ogni pacchetto vocale (e non solo) con l'impostazione DSCP per la voce (ad esempio, DSCP EF 46).
  
Per implementare QoS su tutta la rete aziendale, gli endpoint o i router devono contrassegnare ciascun pacchetto con l'indicatore di priorità di livello 3 appropriato (ad es. DSCP). Su tutto il percorso di rete, ogni switch e router deve avere l'opzione QoS attivata. Anche in presenza di un solo switch o router di rete non impostato su QoS, i contrassegni QoS per i pacchetti voce e video che attraversano tale switch o router potrebbero essere ignorati. Questa condizione disabilita di fatto la qualità del servizio (QoS) in tutti gli switch e i router downstream compromettendo il vantaggio di utilizzare ExpressRoute.
  
È necessario inoltre che l'associazione delle priorità QoS di livello 3 e 2 sia definita per ogni punto. I meccanismi di priorità di livello 2 sono definiti dallo standard IEEE 802.1p per le reti cablate e da 802.11e/WMM per le reti Wi-Fi. Ancora più importante, il router di rete che supporta la rete MPLS del provider dei servizi di rete deve mantenere le impostazioni DSCP su tutti i pacchetti in uscita in modo che essi abbiano la classe di servizio MPLS appropriata.
  
> [!TIP]
> Per i dettagli specifici relativi alla configurazione QoS, fai riferimento alla sezione 2.6 di [Network Planning, Monitoring, and Troubleshooting with Lync Server (Pianificazione della rete, monitoraggio e risoluzione dei problemi con Lync Server)]( http://go.microsoft.com/fwlink/?LinkId=760669). Puoi anche consultare [Pianificare i requisiti di rete per Skype for Business 2015](http://go.microsoft.com/fwlink/?LinkId=690287) per ulteriori requisiti relativi alla pianificazione di rete.
  
### Ordine dei servizi di accesso di rete

Una volta definiti i meccanismi e i prerequisiti di rete QoS per ExpressRoute, il passo successivo è l'invio di un ordine per i servizi di accesso di rete ExpressRoute. Per ordinare i servizi di accesso ExpressRoute per Dewey Law LLC dal partner provider dei servizi di rete Microsoft, devi specificare due parametri:
  
- La quantità di larghezza di banda totale richiesta per connettere ciascun sito a ExpressRoute e Office 365.
    
- La larghezza di banda totale necessaria per ciascuna classe di servizio richiesta per supportare le app Skype for Business utilizzate da Dewey Law LLC. Il requisito della larghezza di banda della classe di servizio si ottiene dal volume di traffico previsto per ciascuna applicazione Skype for Business, ad esempio applicazioni vocali, video, IM, di presenza e di condivisione dello schermo.
    
### Individuazione dei requisiti di larghezza di banda per le applicazioni Skype for Business

Per Dewey Law LLC., una volta stabilita la larghezza di banda totale richiesta, è necessario sapere in che modo essa verrà divisa tra le varie classi di servizio. Ad esempio, la quantità di larghezza di banda per ogni applicazione Skype for Business.
  
Per determinare tali requisiti per ciascun sito Dewey Law LLC., è necessario utilizzare [Bandwidth Calculator di Lync 2010 e 2013](http://go.microsoft.com/fwlink/?LinkID=690282). Questa calcolatrice è uno strumento basato su Excel che consente di specificare l'uso previsto delle diverse applicazioni Skype for Business, incluse quelle vocali, video, di conferenza e di condivisione dello schermo. La calcolatrice genera automaticamente una stima dei requisiti CoS e di larghezza di banda per ogni sito della rete. Quando si scarica Bandwidth Calculator di Lync 2010 e 2013, viene scaricata anche una guida per l'utente con informazioni dettagliate sull'uso.
  
Per semplificare la consultazione del foglio di calcolo, le varie celle sono codificate tramite colori:
  
- **Verde** Aree di input per dati generali.
    
- **Giallo** Aree di input per dati avanzati. È possibile modificare tali dati, ma con cautela.
    
- **Rosso** Aree di sola lettura con valori di input bloccati che non possono essere modificati.
    
- **Grigio** Aree di sola visualizzazione. Si tratta di risultati o dati delle aree di input generali.
    
Il processo di progettazione per Dewey Law LLC. inizia con una classificazione degli utenti in gruppi di "utenti tipo". Per ciascun "utente tipo" definito, è possibile specificare l'uso previsto delle varie applicazioni Skype for Business ("Nessuno", "Basso", "Medio", "Elevato" o una delle tre impostazioni "Personalizzato"). Tali selezioni sono disponibili nel foglio di lavoro "Utente tipo". Viene indicato l'utilizzo specifico per ogni scelta ("Basso", "Medio" o "Elevato"), ma i singoli valori predefiniti possono essere modificati. Identificando il numero di utenti per ogni "utente tipo" in ciascun sito, la calcolatrice è in grado di calcolare la larghezza di banda totale richiesta per ogni sede.
  
È anche possibile specificare i codec audio e video utilizzati, la possibilità di attivare la correzione degli errori di inoltro (FEC) e infine altri parametri di sistema che influiscono sui requisiti della larghezza di banda. È possibile utilizzare le impostazioni predefinite di Bandwidth Calculator di Lync 2010 e 2013 oppure selezionare codec differenti e altri parametri di sistema. Per la progettazione del sito Dewey Law LLC, è possibile utilizzare le impostazioni predefinite. Tuttavia, è disponibile un menu a discesa con tutte le scelte possibili per modificare tali impostazioni. Le larghezze di banda utilizzate per ciascuna scelta sono indicate nel foglio di lavoro "Codec". Quando si modifica un'impostazione, viene aggiornata la modifica della larghezza di banda e della classe di servizio (CoS) in ogni sito. Tale funzionalità permette di testare diverse configurazioni possibili e verificare l'impatto sui requisiti della larghezza di banda.
  
Abbiamo definito tre gruppi di utenti tipo per Dewey Law LLC., "Dirigenti/Partner", "Società collegate/Assistenti legali" e "Amministratori IT". Nella seguente tabella, viene illustrato in che modo sono stati definiti i profili di utilizzo per le applicazioni Skype for Business per ciascun utente tipo.
  
 **Utenti tipo e profili di utilizzo (Foglio di lavoro "Utente tipo" - Colonne A-P)**
  
|**Utente tipo**|**IM/Presenza**|**Audio P2P**|**Video P2P**|**Conferenze audio**|**Videoconferenze**|**Condivisione desktop**|**Conferenza telefonica con accesso esterno**|**Tipo RTV Lync 2010**|**Utenti remoti**|**Audio stereo Lync 2013**|**Qualità video Lync 2013**|**Comportamento degli utenti di Lync 2013 per la finestra video P2P**|**Utilizzo di MultiView in Lync 2013**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Dirigenti/ Partner  <br/> |Elevato  <br/> |Medio  <br/> |Basso  <br/> |Medio  <br/> |Medio  <br/> |Nessuno  <br/> |Medio  <br/> |CIF  <br/> |0%  <br/> |0%  <br/> |Ottimo  <br/> |Tipico  <br/> |Tipico  <br/> |
|Società collegate/ Assistenti legali  <br/> |Elevato  <br/> |Medio  <br/> |Basso  <br/> |Medio  <br/> |Elevato  <br/> |Elevato  <br/> |Medio  <br/> |CIF  <br/> |0%  <br/> |0%  <br/> |Medio  <br/> |Tipico  <br/> |Tipico  <br/> |
|Amministratori IT  <br/> |Elevato  <br/> |Medio  <br/> |Nessuno  <br/> |Basso  <br/> |Nessuno  <br/> |Nessuno  <br/> |Medio  <br/> |CIF  <br/> |0%  <br/> |0%  <br/> |Medio  <br/> |Tipico  <br/> |Tipico  <br/> |
   
È necessario immettere le informazioni nella tabella **Distribuzione degli utenti per località e sedi** precedente nel foglio di lavoro "Siti" di Bandwidth Calculator di Lync 2010 e 2013. Poiché il numero degli utenti negli uffici regionali è identico, essi sono stati definiti per un solo sito ed è stato indicato che vi sono tre istanze dello stesso. Analogamente è stato fatto per le filiali grandi e piccole, rispettivamente di 24 e 50 utenti.
  
Dopo aver specificato le impostazioni per ciascun utente tipo, è necessario immettere il numero di utenti di ogni gruppo di utenti tipo su ciascun sito nel foglio di lavoro "Siti". Il numero totale di utenti per tutti i siti viene aggiornato automaticamente. Dal momento che non sono presenti utenti nella posizione di Office 365, devono essere inseriti tutti nelle righe relative alle filiali del foglio di lavoro. A questo punto, Bandwidth Calculator di Lync 2010 e 2013 popola le colonne "Classe Best Effort", "Classe Traffico dati" e "Classe Traffico in tempo reale" della tabella "WAN BW per classe di traffico QoS". Ciò viene illustrato nei dati della tabella seguente.
  
> [!TIP]
> Il foglio di calcolo completo include anche il numero massimo di sessioni simultanee per ciascuna applicazione, ma tali colonne sono state eliminate per motivi di spazio. 
  
 **Utenti tipo per sito - (Foglio di lavoro "Siti" - Colonne A, D, I e AI fino a AX)**
  
|**Nome sito**|**Totale utenti nel sito**|**Totale siti analoghi**|**Profilo utente 1**|**Utente del profilo 1**|**Profilo utente 2**|**Utente del profilo 2**|**Profilo utente 3**|**Utente del profilo 3**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sede centrale  <br/> |1070  <br/> |1  <br/> |Dirigenti/Partner  <br/> |170  <br/> |Società collegate/Assistenti legali  <br/> |700  <br/> |Amministratori IT  <br/> |200  <br/> |
|Uffici regionali  <br/> |345  <br/> |3  <br/> |Dirigenti/Partner  <br/> |60  <br/> |Società collegate/Assistenti legali  <br/> |225  <br/> |Amministratori IT  <br/> |60  <br/> |
|Filiali grandi  <br/> |70  <br/> |24  <br/> |Dirigenti/Partner  <br/> |11  <br/> |Società collegate/Assistenti legali  <br/> |50  <br/> |Amministratori IT  <br/> |9  <br/> |
|Filiali piccole  <br/> |36  <br/> |50  <br/> |Dirigenti/Partner  <br/> |6  <br/> |Società collegate/Assistenti legali  <br/> |25  <br/> |Amministratori IT  <br/> |1  <br/> |
   
 **Larghezza di banda richiesta per applicazione per sito in Kbps (Foglio di lavoro "Siti" - Colonne A e BQ fino a LF)**
  
|**Sito**|**Larghezza di banda max IM/SIM**|**Larghezza di banda max peer audio intrasito**|**Larghezza di banda max peer video intrasito**|**Larghezza di banda max conf. audio**|**Larghezza di banda max videoconf.**|**Larghezza di banda max condivisioni WAN**|**Larghezza di banda max WAN per chiamate PSTN**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sede centrale  <br/> |1070  <br/> |525,30  <br/> |560,00  <br/> |739,50  <br/> |2640,00  <br/> |4224,00  <br/> |2688,30  <br/> |
|Uffici regionali  <br/> |345  <br/> |185,40  <br/> |560,00  <br/> |255,00  <br/> |1320,00  <br/> |1536,00  <br/> |896,10  <br/> |
|Filiali grandi  <br/> |70  <br/> |92,70  <br/> |560,00  <br/> |102,00  <br/> |600,00  <br/> |384,00  <br/> |216,30  <br/> |
|Filiali piccole  <br/> |36  <br/> |119,40  <br/> |560,00  <br/> |76,50  <br/> |600,00  <br/> |384,00  <br/> |123,60  <br/> |
   
Probabilmente le colonne più importanti del foglio di calcolo sono quelle che descrivono la larghezza di banda WAN per classe QoS. Ciò viene illustrato nella tabella seguente. Questi dati indicano le informazioni da fornire al provider dei servizi di rete per accedere alla connessione su ciascun sito. Quando si calcola la larghezza di banda totale, è importante ricordare di moltiplicare la larghezza di banda per ciascun tipo di sito di succursale per il numero di siti dello stesso tipo. Per connetterti con il partner dei servizi di rete ExpressRoute, consulta [Azure ExpressRoute]( http://go.microsoft.com/fwlink/?LinkId=690283).
  
È molto importante non superare la larghezza di banda per la voce o la classe di servizio "Expedited Forwarding" (EF). Un set casuale di pacchetti verrà ignorato, così che, invece di ridurre la qualità di una singola chiamata o di un gruppo di chiamate, tutte le chiamate in corso verranno compromesse. È importante inoltre che solo la voce sia contrassegnata con DSCP per EF (ad esempio, DSCP = 46), altrimenti la coda vocale potrebbe sovraccaricarsi quando viene aggiunto traffico non vocale.
  
> [!TIP]
> Anche in questo caso, mentre la classe EF del servizio offre la garanzia di prestazioni migliori, se si supera la larghezza di banda definita, tutti i pacchetti aggiuntivi verranno immediatamente ignorati. 
  
 **Larghezza di banda aggregata per sito per classe di traffico QoS - (Foglio di lavoro "Siti" - Colonne A e ML fino a MR) **
  
|**Nome sito**|**Classe Best Effort (DSCP 0)**|**Classe Traffico dati (DSCP personalizzato)**|**Classe Traffico in tempo reale (DSCP 34, AF41)**|**Classe Traffico prioritario (DSCP 46, EF)**|
|:-----|:-----|:-----|:-----|:-----|
|Sede centrale  <br/> |0,00  <br/> |5764,80  <br/> |3200,00  <br/> |3953,10  <br/> |
|Uffici regionali  <br/> |0,00  <br/> |2033,60  <br/> |1880,00  <br/> |1336,50  <br/> |
|Filiali grandi  <br/> |0,00  <br/> |486,40  <br/> |1160,00  <br/> |411,00  <br/> |
|Filiali piccole  <br/> |0,00  <br/> |438,40  <br/> |1160,00  <br/> |319,50  <br/> |
   
### Applicazione del piano

È possibile calcolare la larghezza di banda totale che attraversa la WAN e la quantità di larghezza di banda che attraversa ExpressRoute usando le stime di larghezza di banda della tabella **Per applicazione Per sito** sopra riportata. La parte di traffico che attraversa ExpressRoute esclude la larghezza di banda peer intrasito.
  
|**Sito**|**Larghezza di banda max IM/SIM**|**Larghezza di banda max conf. audio**|**Larghezza di banda max videoconf.**|**Larghezza di banda max condivisioni WAN**|**Larghezza di banda max WAN per chiamate PSTN**|**Traffico totale ExpressRoute classe di sito (ad esempio, tempo totale # dei siti)**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Sede centrale** <br/> |1.070  <br/> |739,50  <br/> |2640,00  <br/> |4224,00  <br/> |2688,30  <br/> |11361,80  <br/> |
|**Uffici regionali** <br/> |345  <br/> |255,00  <br/> |1320,00  <br/> |1536,00  <br/> |896,10  <br/> |8704,20  <br/> |
|**Filiali grandi** <br/> |70  <br/> |102,00  <br/> |600,00  <br/> |384,00  <br/> |216,30  <br/> |32935,20  <br/> |
|**Filiali piccole** <br/> |36  <br/> |76,50  <br/> |600,00  <br/> |384,00  <br/> |123,60  <br/> |61005,00  <br/> |
   
Questo significa che il traffico di Skype for Business online che attraversa il percorso rapido sarà di circa 114 Mbps, in modo che Dewey avrà bisogno almeno di un abbonamento da 200 Mbps per ExpressRoute. È possibile acquistare più circuiti ExpressRoute presso diverse posizioni di peering ExpressRoute. Questa operazione potrebbe essere consigliata se i siti di Dewey si trovano in aree geografiche diverse, o per garantire la resilienza nel caso in cui la connessione al circuito ExpressRoute abbia esito negativo. Se acquisti circuiti ExpressRoute in più aree geografiche Azure, il componente aggiuntivo ExpressRoute premium verrà richiesto per ricevere la connettività globale in ExpressRoute.
  
Ora che hai i dati della quantità totale di larghezza di banda richiesta e i numeri di larghezza di banda della classe di servizio (CoS), è possibile inviare gli ordini ai provider dei servizi di rete selezionati. Non dimenticare di includere le stime di traffico per altre applicazioni e servizi. Sono disponibili indicazioni relative alla pianificazione di rete per altri servizi di Office 365, tra cui Bandwidth Calculator per Exchange e OneDrive. L'abbonamento della larghezza di banda per i provider dei servizi di rete sarà superiore perché il traffico intrasito dovrà essere aggiunto di nuovo. Bandwidth Calculator di Lync 2010 e 2013 fornisce solo la stima del traffico previsto, si consiglia quindi di confermare la capacità della rete di supportare tale volume di traffico eseguendo un test di stress. 
  
> [!TIP]
> Il test di stress della rete è altamente consigliato quando si esegue una valutazione preliminare della rete. 
  
Un test di stress interessa la creazione e la configurazione dell'infrastruttura, quindi la relativa esecuzione con il volume previsto di traffico simulato e il monitoraggio delle prestazioni. Le stime di traffico possono essere imprecise in alcune aree, ma almeno garantiscono che sia supportato il volume di traffico previsto da Bandwidth Calculator di Lync 2010 e 2013. È opportuno eseguire il test di stress per almeno alcuni giorni, ma un'esecuzione più prolungata garantisce risultati migliori. Tuttavia, l'estensione del periodo del test di stress deve essere valutata tenendo conto del costo corrisposto per servizi di rete che non determinano un traffico di rete effettivo. Microsoft ha certificato un gruppo di fornitori nell'ambito del programma IT Pro Tools che forniscono strumenti operativi e di gestione di rete, compresi quelli di valutazione preliminare della rete. Skype for Business fornisce anche lo strumento Integrazione di sistemi (SI) che può eseguire il programma IT Pro Tools certificato e la valutazione della rete. Per ulteriori informazioni, consulta [Soluzioni Skype for Business: IT Pro Tools](http://go.microsoft.com/fwlink/?LinkID=690307).
  
Il test di stress offre la garanzia che la rete sia in grado di supportare il volume di traffico necessario, anche se in realtà i dati di Bandwidth Calculator di Lync 2010 e 2013 potrebbero non essere applicabili per diversi motivi. Si raccomanda inoltre di continuare a monitorare le reti dei siti mediante l'esecuzione di una valutazione di rete dopo la distribuzione, in modo da essere certi che la larghezza di banda sia sufficiente e che i meccanismi QoS funzionino correttamente. È importante continuare a monitorare le prestazioni di rete man mano che gli utenti effettivi online aumentano.
  
## Parte 2: QoS in ExpressRoute Skype for Business

Il servizio ExpressRoute di Microsoft fornisce una connessione dedicata al cloud Azure, mentre i servizi di comunicazione per i carichi di lavoro in tempo reale di Office 365 richiedono servizi di rete con larghezza di banda sufficiente per gestire il volume di traffico e supportano la qualità del servizio (QoS) per fornire un'esperienza utente di livello aziendale. Una connessione QoS deve essere configurata end-to-end (PC, switch e router di rete nel cloud) in quanto qualsiasi parte del percorso che presenta errori relativi alla qualità del servizio può compromettere la qualità dell'intera chiamata.
  
Lo scopo di questa sezione è di aiutare l'utente a comprendere le sfide correlate al traffico in tempo reale in una rete IP e a configurare e supportare una distribuzione ExpressRoute corretta dei carichi di lavoro in tempo reale di Office 365 utilizzando un partner provider dei servizi di rete o un provider ExpressRoute Exchange di Microsoft.
  
La QoS è accettata dalle proprie reti esclusivamente su circuiti di rete ExpressRoute e viene utilizzata all'interno della rete Microsoft per il traffico di Skype for Business. Attualmente, per parti di alcune connessioni in uscita da Microsoft mancano valori DSCP per Skype for Business. Finché il traffico in uscita non verrà contrassegnato completamente con valori DSCP, è consigliato di seguire le linee guida per l'aggiunta di contrassegni QoS al traffico presso il limite di rete come descritto nella sezione **Implementazione della QoS utilizzando l'elenco di controllo di accesso (ACL) di rete** del presente articolo.
  
### Il problema del tempo reale

L'offerta di servizi voce e video di qualità aziendale pone delle richieste specifiche su una rete IP. Il traffico in tempo reale utilizza il protocollo RTP (Real-time Transport Protocol), che è associato al protocollo UDP (User Datagram Protocol). Diversamente dal protocollo TCP (Transmission Control Protocol) che enumera e verifica ogni messaggio per la ricerca di eventuali errori e include altri meccanismi per rilevare e ritrasmettere i messaggi con errori o persi, UDP non fornisce questo tipo di affidabilità. Se i messaggi sono danneggiati a causa di errori o non arrivano per sovraccarico del buffer, essi vengono persi. Il protocollo UDP è stato scelto per l'uso insieme a quello RTP in quanto, nell'ambito del traffico in tempo reale, anche se i messaggi persi vengono reinviati, essi arrivano troppo tardi per aver un impatto positivo sul flusso del messaggio vocale.
  
Considerando l'impatto dei pacchetti vocali smarriti, i progettisti hanno definito due approcci per migliorare le prestazioni di voce e video su IP:
  
- Rendere la codifica/decodifica vocale più resiliente quando i pacchetti vengono persi. Ciò si ottiene utilizzando correzione degli errori di inoltro (FEC, Forward Error Correction) per correggere una percentuale di errori rilevati, ossia una funzionalità di Office 365 Real Time Transport, oppure designando i sistemi di decodifica vocale che tentano di mascherare l'effetto dei pacchetti smarriti, ossia una caratteristica dei codec Microsoft.
    
- Utilizzare servizi di trasporto che utilizzano a loro volta meccanismi QoS per garantire le prestazioni di rete in caso di ritardi, perdite di pacchetti, instabilità e variazioni nel ritardo tra pacchetti.
    
La codifica vocale resiliente risolve solo il problema della perdita dei pacchetti, pertanto è importante che una rete utilizzata per supportare voce e video in tempo reale sia dotata di meccanismi in grado di ridurre ritardi e l'instabilità. Anche con la codifica resiliente, se vengono smarriti troppi pacchetti, la stazione di ricezione non avrà informazioni sufficienti per ricostruire una versione riconoscibile del segnale vocale. La percentuale dei pacchetti smarriti che potrebbe portare a un evidente deterioramento della qualità vocale varia a seconda della tecnica di codifica usata. In tutti i casi, tuttavia, la perdita di stringhe di pacchetti successivi è molto problematica.
  
È importante ridurre al minimo il ritardo poiché un ritardo eccessivo può influire negativamente sul flusso della conversazione e disturbare gli interlocutori. Le procedure consigliate ci indicano che il ritardo end-to-end per la voce (denominato ritardo "bocca-orecchio") deve essere mantenuto al di sotto dei 150 millisecondi (msec). unidirezionali, non di tipo "round trip". Naturalmente, il ritardo aumenta per i collegamenti di trasmissione più lunghi, come quelli oltreoceano, considerato il ritardo di propagazione o il tempo che il segnale impiega a viaggiare fisicamente sul cavo.
  
Quando il ritardo supera i 150 msec unidirezionali, produce un effetto strano sull'interlocutore. Psicologicamente, nel cervello dell'interlocutore scatta un meccanismo per cui pensa che il destinatario non lo abbia sentito e ripete l'ultima parola pronunciata. Ciò collide con la risposta ritardata che proviene dall'altra estremità. Se ti è capitato di parlare su un canale satellitare, saprai riconoscere questo effetto. Su un canale satellitare, il ritardo unidirezionale è di circa 250 msec, che è di gran lunga superiore a quello consentito.
  
 **Parametri di rete consigliati per voce di livello aziendale**
  
|**Parametro**|**Valore consigliato**|
|:-----|:-----|
|Instabilità media tra arrivi di pacchetti (media)  <br/> |≤ 5 ms  <br/> |
|Instabilità media tra arrivi di pacchetti (massima)  <br/> |≤ 40 ms  <br/> |
|Percentuale perdita pacchetti (media)  <br/> |0% quasi raggiunto  <br/> |
|Latenza di rete unidirezionale  <br/> |≤ 100 ms (deve includere verifiche sul ritardo rispetto alla distanza geografica)  <br/> |
   
### ExpressRoute come parte di una rete voce di livello aziendale

ExpressRoute offre una connessione dedicata tramite un provider di servizi di rete (NSP) o un provider Exchange (EXP) in una delle 3 opzioni di connessione: 
  
- Housing nel cloud Exchange
    
- Connessione Ethernet Point-to-Point
    
- Connessione Any-to-Any (IPVPN)
    
In questo modo vengono offerti vantaggi come disponibilità elevata (contratto di servizio (SLA) con tempo di attività del 99,9%) e routing affidabile, sicuro (nessun transito Internet) e non interessato dalle variazioni del traffico Internet e vengono rispettati i contrassegni di Qualità del servizio (QoS) per assegnare priorità al traffico (il concetto di QoS è illustrato di seguito). ExpressRoute, insieme a una WAN ben pianificata, può fornire una rete voce di livello aziendale.
  
Puoi usare ExpressRoute per il transito dei dati da sedi o datacenter (se topologia ibrida) collegati al circuito. I dati per gli utenti fuori sede (ad esempio, da casa, in viaggio e così via) non sfruttano il circuito ExpressRoute, a meno che gli utenti sono connessi alla VPN e non devono essere inclusi nelle stime della larghezza di banda per dimensionare il circuito ExpressRoute. Se sei una multinazionale, puoi acquistare circuiti ExpressRoute in ogni area geografica e usare i tag della community BGP per informare le regole di routing in modo che il traffico venga diretto al circuito ExpressRoute preferito (in genere quello più vicino per ogni sito), mentre gli altri circuiti offrono ridondanza nel caso di un'interruzione che riguarda un unico circuito. 
  
### Se ExpressRoute non è un'opzione

Potrebbe non essere possibile connettere tutti i siti a ExpressRoute, a causa dei costi, dell'impossibilità di soddisfare i prerequisiti ExpressRoute o a causa di limitazioni del proprio NSP attuale. Se non riesci a utilizzare ExpressRoute, segui i suggerimenti riportati di seguito per contrassegnare QoS nella rete e per pianificare i contratti con l'NSP per assicurare la larghezza d banda e il supporto sufficienti per dare la priorità al traffico in base al QoS.
  
Inoltre, se hai uffici in più aree geografiche ma non disponi di circuiti ExpressRoute in tutte le aree geografiche, devi usare i contrassegni della community BGP quando configuri il routing da/a uffici satelliti in modo da evitare lunghe traiettorie. Ad esempio, pensa a una società che ha un'organizzazione Skype for Business online ospitata negli Stati Uniti, ma con succursali in Europa e con un singolo circuito ExpressRoute nella Silicon Valley. La maggior parte del traffico di Skype for Business online verrà instradata a un datacenter in cui è ospitata l'organizzazione (ad esempio, conferenze telefoniche con altri utenti all'interno della società), e per la maggior parte del traffico è preferibile utilizzare il circuito ExpressRoute. Tuttavia, se un utente in Europa dovesse partecipare a una conferenza telefonica ospitata da un'altra società la cui organizzazione si trova in Europa, la destinazione per i contenuti multimediali in quella chiamata sarebbe il datacenter europeo in cui si trova la seconda società. Il routing del traffico attraverso il circuito ExpressRoute nella Silicon Valley costituirebbe un instradamento meno diretto rispetto a quello possibile tramite Internet. In tal caso, potrebbe essere necessario configurare i router all'interno della rete (ad esempio, negli uffici europei) per analizzare i tag della community durante la creazione delle regole di routing e il routing via Internet anziché tramite il circuito ExpressRoute della Silicon Valley per il traffico con tag dell'area geografica europea.
  
### Concetti di base di QoS (Quality of Service)/CoS (Class of Service)

In IP, il termine qualità del servizio (QoS, Quality of Service) descrive qualsiasi meccanismo utilizzato per fornire una gestione prioritaria di alcuni pacchetti rispetto ad altri. In base alla definizione della ITU (International Telecommunications Union), QoS comprende tutti gli aspetti della qualità di una connessione, compresi ritardo, perdita, rapporto segnale-rumore, crosstalk, eco, interruzioni, risposta in frequenza, livelli di rumorosità e così via. Quello che chiamiamo QoS nella terminologia delle reti a pacchetti dovrebbe più correttamente definirsi CoS (Class of Service), ossia un fattore incentrato sul miglioramento delle prestazioni in caso di ritardi, instabilità e perdite, anche se continuiamo a utilizzare il termine più comune QoS.
  
L'offerta di QoS in una rete IP si basa su due componenti principali:
  
- Prenotazione di una quantità specifica di larghezza di banda su ciascun collegamento di traffico in tempo reale; se tale larghezza di banda non è richiesta per il traffico in tempo reale in qualsiasi momento, può essere utilizzata per altro traffico. In base alle istruzioni generali, non più del 30% della capacità di qualsiasi collegamento deve essere assegnata al traffico vocale.
    
- Contrassegno dei pacchetti con un indicatore di priorità nell'intestazione che indichi agli switch e ai router nel percorso la priorità per il pacchetto.
    
Quando un pacchetto viene ricevuto su uno switch o router, viene spostato in una coda di output per la coda o l'hop successivo. Esistono diverse code di output per i diversi livelli di priorità. Uno switch o router utilizza un algoritmo che serve la coda ad alta priorità più frequentemente delle code a priorità inferiore.
  
Il problema sta nel fatto che vi sono diverse tecniche QoS implementate al livello 2 (ad esempio, il livello Ethernet o Wi-Fi) e al livello 3 (ad esempio, il livello IP). Queste diverse implementazioni QoS possono richiedere la configurazione in ogni switch o router della rete, così come l'interfaccia tra la tua rete e la rete del provider dei servizi di rete.
  
Sono disponibili due opzioni per la mappatura dei dati delle varie applicazioni Skype for Business alle classi di servizio appropriate:
  
- Contrassegno endpoint del traffico mediante DSPC (Differentiated Services Control Point)
    
- Assegnazione basata sull'elenco di controllo di accesso (ACL, Access Control List) di rete
    
### Contrassegno del traffico endpoint - DSCP (Differentiated Services Control Point)

Quello dei servizi differenziati (DiffServ) viene considerato come un meccanismo a "granularità grossolana" per la classificazione e la gestione del traffico di rete nonché per l'applicazione della qualità del servizio (QoS) nelle reti IP. I router e gli altri dispositivi che implementano le funzioni del livello 3 utilizzano DSCP (DiffServ Control Point) per definire la priorità dei pacchetti. La qualità del servizio (QoS) viene implementata inserendo un valore DSCP a 6 bit nel campo Servizi differenziati (precedentemente "Tipo di servizio") dell'intestazione IP; 6 bit supporta 64 diversi livelli di priorità. I livelli di priorità sono in genere definiti come illustrato di seguito.
  
 **Impostazioni DSCP consigliate**
  
|**Classe di traffico**|**Trattamento (contrassegno DSCP)**|**Carichi di lavoro di Skype for Business**|
|:-----|:-----|:-----|
|**Voce** <br/> |EF (46)  <br/> |Skype for Business e Lync voce  <br/> |
|**Interattivi** <br/> |AF41 (34)  <br/> |Video  <br/> |
||AF21 (18)  <br/> |Condivisione applicazioni  <br/> |
|**Impostazione predefinita** <br/> |AF11 (10)  <br/> |Trasferimento di file  <br/> |
||CS0 (0)  <br/> |Qualsiasi altro valore  <br/> |
   
 ** Intestazione IP versione 4**
  
![Intestazione IPv4](../images/c8a6a714-2784-4328-8297-2e62706f302d.png)
  
### QoS livello 2: IEEE 802.1p/Wi-Fi Multi-Media (IEEE 802.11e)

Mentre DSCP costituisce il meccanismo standard per l'implementazione della QoS al livello 3, vi sono diversi meccanismi QoS di livello 2 per reti cablate (ad esempio, Ethernet) e wireless (ad esempio, Wi-Fi). Il meccanismo QoS per le reti cablate è definito dallo standard IEEE 802.1p; il meccanismo QoS WLAN è definito dallo standard IEEE 802.11e, che la Wi-Fi Alliance identifica come "certificazione Wi-Fi Multi-Media" (certificazione WMM).
  
Lo standard IEEE 802.1p utilizza un PCP (Priority Code Point) a 3 bit per identificare la priorità del messaggio; il PCP fa parte di un campo a 32 bit nell'intestazione Ethernet che trasporta anche l'identificativo VLAN. Le definizioni dei valori PCP sono riportate di seguito.
  
 ** Valori PCP IEEE 802.1p**
  
|**Valore PCP**|**Priorità**|**Acronimo**|**Tipi di traffico**|
|:-----|:-----|:-----|:-----|
|7  <br/> |7  <br/> |NC  <br/> |Network Control  <br/> |
|6  <br/> |6  <br/> |IC  <br/> |Internetwork Control  <br/> |
|5  <br/> |5  <br/> |VO  <br/> |Voce  <br/> |
|4  <br/> |4  <br/> |VI  <br/> |Video  <br/> |
|3  <br/> |3  <br/> |CA  <br/> |Critical Applications  <br/> |
|2  <br/> |2  <br/> |EE  <br/> |Excellent Effort  <br/> |
|0  <br/> |1  <br/> |BE  <br/> |Best Effort  <br/> |
|1  <br/> |0  <br/> |BK  <br/> |Sfondo  <br/> |
   
Laddove IEEE 802.1p è implementato nello stesso modo del DSCP con il traffico ordinato in diverse code di priorità per ciascun livello di priorità, ma la natura degli elementi multimediali condivisi delle WLAN richiama un approccio diverso. Mentre il punto di accesso e il client manterranno code di output separate per i diversi livelli di priorità, vi sono differenze anche nel modo in cui i frame vengono inviati sul canale radio.
  
In una rete Wi-Fi, tutti i client associati a un punto di accesso condividono un singolo canale half-duplex (ad esempio, solo una stazione client o il punto di accesso può eseguire l'invio in un determinato momento). Per ridurre al minimo la possibilità di collisioni sul canale radio, prima di inviare un frame, la stazione attende che il canale sia inattivo per un periodo di tempo specifico, denominato "intervallo tra frame"; se il canale è occupato quando una stazione inizia l'invio, si blocca per un periodo di tempo casuale. Una volta che il frame è stato inviato, se il mittente non riceve un messaggio di conferma dal destinatario, presuppone che sia avvenuta una collisione o un altro errore e torna a un intervallo casuale prima di tentare l'accesso al canale radio per un nuovo invio. L'intervallo di interruzione temporanea è casuale al fine di ridurre la probabilità che le stesse due stazioni collidano nuovamente.
  
Per dare priorità all'accesso al canale radio, IEEE 802.11e/WMM definisce diversi intervalli di attesa di pretrasmissione denominati "Arbitrated Inter-Frame Spacings" (AFIS) e diversi intervalli di interruzione temporanea per le diverse classi di traffico; sono definiti quattro livelli di priorità denominati "categorie di accesso".
  
La priorità viene conferita assegnando valori AFIS più brevi ai frame con priorità più alta. Pertanto, se una stazione è in attesa di inviare un frame voce e un'altra è in attesa di inviare un frame dati, il frame voce viene sempre inviato per primo. Tecnicamente, i frame voce e video sono assegnati allo stesso valore AFIS, ma la gamma degli intervalli di interruzione temporanea per i frame video è superiore. Quindi, mentre un frame voce e video può collidere al primo tentativo, il frame voce sarà sempre ritrasmesso prima possibile. La correlazione tra IEEE 802.1p e IEEE 802.11e viene illustrata di seguito:
  
 ** Mappatura da IEEE 802.11e/Wi-Fi Multi-Media (WMM) a 802.1P**
  
|**Categoria di accesso WMM**|**Descrizione WMM**|**Valore PCP 802.1P**|**Designazione 802.1P**|
|:-----|:-----|:-----|:-----|
|1 (AC_VO)  <br/> |Voce  <br/> |7 (111)  <br/> |NC  <br/> |
|6 (110)  <br/> |VO  <br/> |
|2 (AC_VI)  <br/> |Video  <br/> |5 (101)  <br/> |VI  <br/> |
|4 (100)  <br/> |CL  <br/> |
|3 (AC_BE)  <br/> |Best Effort Data  <br/> |3 (011)  <br/> |EE  <br/> |
|0 (000)  <br/> |BE  <br/> |
|4 (AC_BK)  <br/> |Background Data  <br/> |1 (001)  <br/> |BK  <br/> |
|2 (010)  <br/> |---  <br/> |
   
L'associazione consigliata delle priorità di livello 3 e livello 2 è illustrata di seguito:
  
 **Associazioni di priorità di livello 3 e livello 2 consigliate**
  
||**Contrassegni livello 3**|**Livello 2 (valore PCP)**|**Wi-Fi (categoria di accesso)**|
|:-----|:-----|:-----|:-----|
|Network Control  <br/> |Per Hop Behavior (PHB) - Class Selector (CS) 6  <br/> |6  <br/> |1 (AC_VO)  <br/> |
|Valore DSCP -48  <br/> |
|Voce  <br/> |Per Hop Behavior (PHB) - Expedited Forwarding (EF)  <br/> |5  <br/> |1 (AC_VO)  <br/> |
|Valore DSCP - 46  <br/> |
|Videoconferenze  <br/> |Per Hop Behavior (PHB) - Assured Forwarding (AF) 41  <br/> |4  <br/> |2 (AC_VI)  <br/> |
|Valore DSCP - 34  <br/> |
|Segnalazione chiamate  <br/> |Per Hop Behavior (PHB) - Class Selector (CS) 3  <br/> |3  <br/> |2 (AC_VI)  <br/> |
|Valore DSCP - 24  <br/> |
|Dati a bassa latenza  <br/> |Per Hop Behavior (PHB) -Assured Forwarding (AF) 21  <br/> |2  <br/> |3 (AC_BE)  <br/> |
|Valore DSCP -18  <br/> |
|Dati ad alta velocità  <br/> |Per Hop Behavior (PHB) - Assured Forwarding (AF) 11  <br/> |1  <br/> |3 (AC_BE)  <br/> |
|Valore DSCP - 10  <br/> |
|Best Effort  <br/> |Per Hop Behavior (PHB) - 0  <br/> |0  <br/> |4 (AC_BK)  <br/> |
|Valore DSCP - 0  <br/> |
   
È importante notare che vi è una discrepanza nella codifica di priorità per IEEE 802.1p e WMM. Il valore PCP 802.1p per la voce è 5; tuttavia, nella mappatura di equivalenza standard su WMM, PCP 5 viene convertito nella categoria di accesso 2, la categoria di accesso WMM per i video (AC_VI). Se possibile, consigliamo di sovrascrivere la mappatura in modo che PCP 5 venga convertito nella categoria di accesso 1 oppure di evitare semplicemente l'uso di voce e video sulla stessa rete Wi-Fi finché la Wi-Fi Alliance non risolverà tale problema. Per ulteriori informazioni su Wi-Fi, consulta [Wi-Fi Catalog Items (Elementi del catalogo Wi-Fi)]( http://go.microsoft.com/fwlink/?LinkId=690322)
  
### Implementazione della QoS utilizzando l'elenco di controllo di accesso (ACL) di rete

Il metodo alternativo per implementare la qualità del servizio (QoS) in una configurazione ExpressRoute consiste nell'utilizzare l'elenco di controllo di accesso (ACL) di rete. In tale approccio, anziché avere gli endpoint inseriti nel contrassegno DSCP appropriato nell'intestazione di ciascun pacchetto, il contrassegno può essere effettuato da un router upstream, in base alla porta di origine UDP. Tutti gli switch e i router devono comunque essere configurati in modo da supportare la QoS per garantire che le impostazioni DSCP siano mantenute. Soprattutto, il router connesso alla rete del provider di servizi deve mantenere il contrassegno DSCP nell'intestazione di ciascun pacchetto, in quanto tale impostazione DSCP è essenzialmente l'istruzione che indica al provider dei servizi di rete come trattare un determinato pacchetto.
  
Gli intervalli di porta consigliati per ogni applicazione Skype for Business sono elencati nella sezione 2.6.1.1 della guida [Network Planning, Monitoring, and Troubleshooting with Lync Server (Pianificazione della rete, monitoraggio e risoluzione dei problemi con Lync Server)](http://go.microsoft.com/fwlink/?LinkId=690286). È importante che tale operazione sia coordinata con l'approccio globale dell'organizzazione in materia di QoS; inoltre, occorre cercare continuamente criteri QoS diversi e potenziali discrepanze nel contrassegno dei pacchetti.
  
Mentre il motivo principale per cui sono utilizzati i servizi di rete MPLS e QoS è quello di garantire una buona esperienza utente per i servizi voce e video in tempo reale, le stesse funzionalità possono anche essere utilizzate per le applicazioni di dati. Anziché trattare tutte le applicazioni allo stesso modo, le reti MPLS possono consentire alle organizzazioni di assegnare la priorità ad alcune applicazioni di dati rispetto ad altre. Con il metodo MPLS, le applicazioni in tempo reale come le transazioni su carta di credito o la condivisione dello schermo possono avere la priorità rispetto al traffico sensibile al fattore temporale, ad esempio la posta elettronica.
  
### Descrizione dei tipi di servizi di rete IP: IP di base e MPLS

L'inoltro dei pacchetti IP originario si basava sul principio del "best effort". Ciò significava che i router che inoltravano tali pacchetti IP avrebbero fatto del loro meglio per distribuirli alle rispettive destinazioni, ma che non vi era alcuna garanzia rispetto ai tempi di arrivo o alla riuscita dell'invio. Questo è il modo in cui attualmente funzionano i servizi Internet di base, tra cui la connessione Internet domestica. L'idea era che, se per un'applicazione specifica era richiesta affidabilità, doveva essere fornita a un livello superiore nello stack del protocollo. Il meccanismo di consegna affidabile è il protocollo TCP (Transmission Control Protocol). L'UDP (User Datagram Protocol), utilizzato per voce e video in tempo reale, è il meccanismo di consegna non affidabile ("best effort").
  
La tecnica MPLS (Multi-Protocol Label Switching) è stata sviluppata in modo che i provider dei servizi di rete potessero offrire un servizio IP con garanzie di prestazioni in caso di ritardi, instabilità e perdite di pacchetti. Per la distribuzione con tali garanzie di prestazioni, MPLS elimina alcune delle imprevidibilità dell'IP tradizionale. Innanzitutto, anziché fare in modo che ogni pacchetto trovi il percorso di destinazione da router a router (per cui può accadere che ogni pacchetto prenda una route diversa dall'origine alla destinazione), MPLS instrada tutti i pacchetti su una connessione a "circuito virtuale" con una route fissa denominata LSP (Label Switched Path). Se uno dei collegamenti del percorso non funziona, tutti gli LSP che utilizzano tale collegamento vengono rapidamente reinstradati.
  
Quando un pacchetto viene inviato alla rete MPLS, il router perimetrale del provider dei servizi di rete aggiunge un'intestazione supplementare al pacchetto, che include un'etichetta usata per l'inoltro sull'LSP appropriato. L'etichetta viene eliminata dal router perimetrale all'altra estremità della rete MPLS.
  
Oltre a semplificare il processo di inoltro, l'altro vantaggio fornito dal metodo MPLS è che il sistema di gestione della rete è a conoscenza delle connessioni che si trovano su ciascun collegamento della rete. Controllando il modo in cui il traffico viene instradato sulla rete, l'operatore può assicurare la qualità del servizio fornita da ogni percorso. Pertanto, diversamente dalle prestazioni "best effort" dell'IP tradizionale o classico, gli operatori MPLS possono fornire un servizio IP con prestazioni prevedibili. Tale LSP rende inoltre MPLS intrinsecamente più sicuro rispetto ai servizi Internet tradizionali. Quindi, se con il servizio IP di base possiamo sperare che la rete funzionerà sufficientemente bene da fornire una buona qualità vocale e utilizzare tecniche come FEC e una codifica vocale più resiliente per migliorare tali probabilità, con il metodo MPLS ne abbiamo la certezza.
  
I provider MPLS offrono diversi gradienti di classi di servizio ma ciascuno utilizza termini differenti per identificarli. È necessario lavorare a stretto contatto con il provider per avere la certezza che vengano recepiti i risultati di [Bandwidth Calculator di Lync 2010 e 2013](http://go.microsoft.com/fwlink/?LinkID=690282) e le opzioni consigliate per le diverse applicazioni dei carichi di lavoro in tempo reale di Office 365.
  
## Conclusioni

Skype for Business migliora il modo in cui vengono condotte le comunicazioni aziendali. Anziché avere un telefono connesso a una centralina telefonica, un sistema di videconferenza autonomo, una piattaforma separata per l'e-mail, un servizio esterno per le conferenze audio e alcuni strumenti per IM e presenza, Skype for Business può accorpare tutte queste funzionalità in una singola interfaccia utente.
  
Una distribuzione uniforme dei servizi voce e video in tempo reale di livello aziendale richiede un'infrastruttura di rete end-to-end in grado di fornire la qualità del servizio (QoS). Ciò deve includere sia servizi LAN che WAN. Microsoft fornisce strumenti come [Bandwidth Calculator di Lync 2010 e 2013](http://go.microsoft.com/fwlink/?LinkID=690282) per calcolare la capacità di rete richiesta per i vari servizi. Inoltre, vi sono partner del programma IT Pro Tools[Soluzioni Skype for Business: IT Pro Tools](http://go.microsoft.com/fwlink/?LinkID=690307) che offrono strumenti per effettuare una valutazione preliminare dell'infrastruttura di rete e supportare il monitoraggio, la generazione di report e la risoluzione dei problemi. Senza un'infrastruttura di rete correttamente dimensionata e configurata, si corre il rischio di avere una distribuzione ExpressRoute Skype of Business che non soddisfa le aspettative dell'utente in materia di qualità e uniformità.
  
Strumenti aziendali efficaci devono funzionare in modo affidabile e coerente e offrire un'esperienza utente che ne favorisca l'adozione. Sotto il profilo della rete, ciò significa avere un'infrastruttura di rete, sia a livello locale che più ampio, fissa e mobile, in grado di supportare tali strumenti. Pianificare, progettare, implementare e gestire tale infrastruttura non è sempre facile. I servizi di rete, gli strumenti e l'hardware per ottenere questi risultati sono oggi disponibili, ma è responsabilità dell'IT Pro verificare se sono progettati, implementati e gestiti in modo da assicurare agli utenti una serie di servizi di collaborazione e comunicazione efficienti ed efficaci e che l'organizzazione possa trarre pieno beneficio dalle caratteristiche di tale tecnologia.
  
## Vedere anche

#### 

[Documentazione ExpressRoute](http://go.microsoft.com/fwlink/?LinkId=690285)

