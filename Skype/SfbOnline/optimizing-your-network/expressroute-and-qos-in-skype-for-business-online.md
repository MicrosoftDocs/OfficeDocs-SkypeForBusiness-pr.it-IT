---
title: ExpressRoute e QoS in Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: 20c654da-30ee-4e4f-a764-8b7d8844431d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: "Informazioni sull'uso di Azure ExpressRoute per avere una rete con requisiti di larghezza di banda e funzionalità di qualità del servizio per un'esperienza utente di livello aziendale. "
ms.openlocfilehash: 7802217872d1f466fa1d855435f84e2ecc468830
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164345"
---
# <a name="expressroute-and-qos-in-skype-for-business-online"></a>ExpressRoute e QoS in Skype for Business Online

Connettersi a Microsoft 365 o Office 365 su una connessione di rete dedicata usando Azure ExpressRoute per Microsoft 365 o Office 365 e Skype for Business online. La tua connessione dedicata per le app Skype for Business ti offrirà prestazioni affidabili e prevedibili e privacy lontano dalla rete Internet pubblica. Ora è possibile acquistare una connessione di rete migliore a Microsoft 365 o Office 365 e Skype for Business Online, che aggiunge prevedibilità e affidabilità di livello aziendale e include un contratto di servizio con tempo di attività.
  
> [!NOTE]
> È disponibile una nuova versione di Bandwidth Calculator: [Skype for Business, Bandwidth Calculator.](https://go.microsoft.com/fwlink/?LinkId=715766) Tuttavia, le istruzioni fornite in questo documento utilizzano Bandwidth Calculator di Lync 2010 e 2013. 
  
## <a name="skype-for-business-online-and-expressroute"></a>Skype for Business online ed ExpressRoute

Collaborando con un partner ExpressRoute di Microsoft, puoi connettere un'ampia varietà di applicazioni Microsoft 365 e Office 365, tra cui Skype for Business online nel cloud su una connessione dedicata. Tuttavia, le funzionalità di comunicazione voce e video in tempo reale per Skype for Business richiedono servizi di rete specificamente configurati per supportare questi carichi di lavoro in tempo reale di Microsoft 365 o Office 365. Ciò comprende una rete che abbia una larghezza di banda sufficiente per supportare il volume di traffico richiesto e che sia in grado di supportare la qualità del servizio (QoS, Quality of Service) per offrire agli utenti un'esperienza di livello aziendale.
  
Questo documento è pensato per aiutare l'utente, gli amministratori e i progettisti di rete a comprendere le sfide speciali richieste per supportare le comunicazioni in tempo reale, gli strumenti forniti da Microsoft per la progettazione di una rete in grado di supportare tali requisiti e per supportare il processo di progettazione con un case study. 
  
Nella prima parte del documento viene descritto un case study per la progettazione della rete mediante Bandwidth Calculator di [Lync 2010 e 2013](https://go.microsoft.com/fwlink/?LinkId=690282) per stimare i requisiti di rete per una distribuzione ExpressRoute di Skype for Business su più siti. Nella seconda parte del documento vengono illustrati i concetti fondamentali della qualità del servizio (QoS, Quality of Service), un approfondimento sui dettagli tecnici specifici per supportare le comunicazioni Skype for Business in tempo reale e sui tipi specifici di servizi di rete necessari.
  
Tutte le informazioni fornite ti daranno i dettagli tecnici e la comprensione di QoS ed ExpressRoute, una comprensione delle sfide specifiche che dovrai affrontare e ti daranno una conoscenza funzionante degli strumenti e delle tecniche che ti consentiranno di distribuire correttamente un ExpressRoute sulla tua rete Skype for Business. 
  
## <a name="getting-started"></a>Introduzione

Quando ci si prepara per ExpressRoute per Skype for Business, è una buona idea esaminare i diversi modelli di connessione ExpressRoute e la scelta di partner e sedi e leggere come acquistare ed eseguire il provisioning di ExpressRoute all'interno dell'azienda. Ecco alcune risorse utili per iniziare: 
  
- [Azure ExpressRoute]( https://go.microsoft.com/fwlink/?LinkId=690283)
    
- [Prezzi ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690284)
    
- [Documentazione di ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690285)
    
## <a name="part-1-case-study---expressroute-for-dewey-law-llc"></a>Parte 1: case study - ExpressRoute per Dewey Law, LLC.

Questo case study per Dewey Law, LLC. ti mostrerà come configurare una rete, ordinare i servizi di accesso di rete e determinare i requisiti di larghezza di banda per supportare ExpressRoute per Skype for Business online.
  
 **Sfondo** Dewy Law LLC. è un grande studio legale nazionale con 790 legali e un totale di 5.580 dipendenti distribuiti in 78 sedi. L'azienda ha una sede centrale di New York, tre uffici regionali a Chicago, San Francisco e Dallas, oltre a 24 filiali di grandi dimensioni e 50 filiali sparse in tutto il paese. L'azienda gestisce casi complessi e di grandi dimensioni con il carico di lavoro in genere distribuito tra due o più uffici. La progettazione di questa rete comporta un traffico di rete considerevole tra gli uffici.
  
Dewy Law LLC. è un'azienda relativamente giovane e i legali e i membri del personale sono molto a proprio agio con la tecnologia e dipendono da questa tecnologia per il loro lavoro quotidiano. 
  
 **Distribuzione degli utenti per località e posizioni**
  
||**Sede centrale (NY)**|**Uffici regionali (3)**|**Filiali grandi (24)**|**Filiali piccole (50)**|
|:-----|:-----|:-----|:-----|:-----|
|Dirigenti  <br/> |20  <br/> |10  <br/> |1  <br/> |1  <br/> |
|Partner  <br/> |150  <br/> |50  <br/> |10  <br/> |5  <br/> |
|Società associate  <br/> |300  <br/> |100  <br/> |20  <br/> |10  <br/> |
|Paralegale  <br/> |400  <br/> |125  <br/> |30  <br/> |15  <br/> |
|Amministratori esecutivi  <br/> |100  <br/> |35  <br/> |6  <br/> |3  <br/> |
|Amministrazione generale e IT  <br/> |100  <br/> |25  <br/> |3  <br/> |2  <br/> |
|Totale per sito  <br/> |1,070  <br/> |345  <br/> |70  <br/> |36  <br/> |
|Totale per classe sito  <br/> |1,070  <br/> |1,035  <br/> |1,680  <br/> |1,800  <br/> |
   
### <a name="setting-up-the-network"></a>Configurazione della rete

Per offrire servizi coerenti e di alta qualità in tempo reale per Dewey Law LLC., è necessario soddisfare alcuni requisiti di base:
  
- L'utente desidera fornire servizi vocali durante le guasti di alimentazione, quindi gli switch e i router di distribuzione della rete devono fornire power over Ethernet (PoE) IEEE 802.3af o 802.3at.
    
- Gli switch e i router di rete devono inoltre utilizzare interruzioni di alimentazione (UPS) in modo che possano continuare a operare durante un'interruzione di corrente.
    
    Hanno una connessione Wi-Fi di rete ai loro uffici LAN, quindi consigliamo vivamente di usare un partner di infrastruttura Wi-Fi Skype for Business certificato da [Skype for Business Solutions.](https://go.microsoft.com/fwlink/?LinkId=690281)
    
    > [!TIP]
    >  Sono consigliati i punti di accesso wireless 802.11n e 802.11ac.
  
- E, soprattutto, tutte le reti LAN in tutti gli uffici devono essere impostate per fornire la qualità del servizio (QoS, Quality of Service). Sono inclusi PC, portatili e qualsiasi hardware di rete, ad esempio switch e router.
    
Una volta trattati i concetti di base, per fornire servizi vocali di livello aziendale per Dewey Law LLC., è consigliabile usare il servizio IP MPLS (Multi-Protocol Label Switching) da un partner di servizio di rete che si connetterà al servizio Azure ExpressRoute. MPLS fornisce un servizio IP con garanzie di prestazioni in caso di ritardi, instabilità e perdite di pacchetti. Tuttavia, se MPLS non è disponibile, è possibile utilizzare anche Ethernet connesso a uno dei nostri partner di scambio dati ExpressRoute.
  
I provider MPLS offrono diversi livelli di classe di servizio, ma ciascuno utilizza termini diversi per identificarli. Sarà necessario lavorare a stretto contatto con il provider per assicurarsi che comprenda i dati immessi in [Bandwidth Calculator di Lync 2010 e 2013](https://go.microsoft.com/fwlink/?LinkID=690282) e le opzioni disponibili e sono consigliate per le diverse applicazioni di carico di lavoro in tempo reale di Microsoft 365 e Office 365.
  
Esistono due opzioni per la mappatura dei dati delle applicazioni Skype for Business alle classi di servizio MPLS appropriate:
  
- Contrassegno endpoint del traffico tramite DSCP (DiffServ Control Point)
    
- Basato sull'elenco di controllo di accesso (ACL, Access Control List) di rete
    
Per implementare il contrassegno endpoint, è necessario configurare tutti i computer Windows aggiunti a un dominio per Dewey Law LLC. per contrassegnare ogni pacchetto con il contrassegno DSCP (DiffServ Control Point) appropriato e quindi implementare la QoS su tutti gli switch e i router di rete in tutte le sedi degli uffici per assicurarsi che i contrassegni QoS siano mantenuti e non rimossi. I contrassegni DSCP sui pacchetti di rete specificano al provider di servizi la priorità assegnata al pacchetto di rete. **Altre informazioni su DSCP sono disponibili nella sezione QoS della Parte 2.**
  
Per l'assegnazione basata su ACL di rete, i contrassegni di priorità DSCP sono implementati su un router upstream e si basano sulla porta di origine UDP. Gli intervalli di porta consigliati per ogni applicazione sono elencati nella Sezione 2.6.1.1 di Pianificazione della rete, monitoraggio e risoluzione dei problemi [con Lync Server.](https://go.microsoft.com/fwlink/?LinkId=690286) È importante coordinare queste informazioni con l'implementazione e la progettazione generale di Dewey Law LLC e tenere presenti i diversi criteri QoS e il potenziale mancata corrispondenza dei contrassegni dei pacchetti.
  
Ogni provider di servizi di rete ExpressRoute avrà una classe di servizio (QoS) appropriata per voce e video in tempo reale. Questa funzione di supporto è denominata "Expedited Forwarding" (EF) per la voce e "Assured Forwarding" (AF) per il video. È necessario prestare molta attenzione al dimensionamento della quantità di larghezza di banda acquistata per il traffico voce EF. Il motivo è che la classe di servizio voce non è molto lesa nel caso in cui si invii una maggiore traffico vocale di quello per cui è stato effettuato il provisioning della classe di servizio.
  
> [!TIP]
>  Tutto il traffico inviato alla classe di servizio vocale in eccesso da parte del provider di servizi viene immediatamente ignorato, con effetto diretto sulla qualità vocale.
  
Durante la progettazione generale di Dewey Law LLC. è estremamente importante determinare in modo accurato la quantità di larghezza di banda di rete necessaria per supportare il traffico vocale attraverso la propria rete e contrassegnare ogni pacchetto vocale (e solo i pacchetti vocali) con l'impostazione DSCP per la voce (ad esempio, DSCP EF 46).
  
Per implementare la QoS nella rete aziendale, gli endpoint o i router devono contrassegnare ogni pacchetto con l'indicatore di priorità di livello 3 appropriato (ad esempio, DSCP). Lungo l'intero percorso di rete, ogni switch e router deve avere l'opzione QoS attivata. Avendo anche un solo switch o router di rete che non dispone di QoS attivato, i contrassegni QoS sui pacchetti vocali o video che passano attraverso lo switch o il router potrebbero essere spogliati. Questo disabilita in modo efficace la QoS in tutti gli switch e i router a valle, abbassando il valore della presenza di ExpressRoute.
  
È anche necessario definire l'associazione delle priorità QoS di livello 3 e 2 in ogni punto. I meccanismi di priorità di livello 2 sono definiti nello standard IEEE 802.1p per le reti cablate e 802.11e/WMM per le reti Wi-Fi rete. E ancora più importante, il router di rete che si trova rivolto alla rete MPLS del provider dei servizi di rete deve mantenere le impostazioni DSCP su tutti i pacchetti in uscita, in modo che mantengano la classe di servizio MPLS appropriata. 
  
> [!TIP]
>  Per i dettagli specifici relativi alla configurazione QoS, fare riferimento alla sezione 2.6 Pianificazione della rete, monitoraggio e risoluzione dei problemi [con Lync Server.]( https://go.microsoft.com/fwlink/?LinkId=760669) Per ulteriori requisiti di pianificazione della rete, è anche possibile consultare Pianificare i requisiti di rete per [Skype for Business 2015.](https://go.microsoft.com/fwlink/?LinkId=690287)
  
### <a name="ordering-network-access-services"></a>Ordine dei servizi di Access Services

Una volta soddisfatti i meccanismi e i prerequisiti di rete QoS per ExpressRoute, il passaggio successivo consiste nell'inserire un ordine per i servizi di accesso di rete ExpressRoute. Quando si ordinano i servizi di accesso ExpressRoute per Dewey Law LLC dal partner provider dei servizi di rete Microsoft, è necessario specificare due aspetti:
  
- La quantità totale di larghezza di banda necessaria per connettere ogni sito a ExpressRoute e Microsoft 365 o Office 365.
    
- La larghezza di banda totale richiesta per ogni classe di servizio necessaria per supportare le app Skype for Business in uso presso Dewey Law LLC. Il requisito della larghezza di banda della classe di servizio è basato sul volume di traffico previsto da ognuna delle varie applicazioni Skype for Business, come applicazioni vocali, video, immediate, di presenza e di condivisione dello schermo.
    
### <a name="determining-bandwidth-requirements-for-skype-for-business-applications"></a>Determinazione dei requisiti di larghezza di banda per le applicazioni Skype for Business

Per Dewey Law LLC., dopo aver determinato la larghezza di banda totale richiesta, è necessario sapere in che modo dividere tale quantità totale di larghezza di banda tra le varie classi di servizio. Ad esempio, la quantità di larghezza di banda per ogni applicazione Skype for Business.
  
Per determinare tali requisiti presso ciascun Dewey Law LLC. si userà Bandwidth [Calculator di Lync 2010 e 2013.](https://go.microsoft.com/fwlink/?LinkID=690282) Questa calcolatrice è uno strumento basato su Excel che ti consente di specificare l'uso previsto delle varie applicazioni Skype for Business, tra cui voce, video, conferenze e condivisione dello schermo. La calcolatrice genererà automaticamente una stima della larghezza di banda e dei requisiti CoS per ogni sito della rete. Quando si scarica Bandwidth Calculator di Lync 2010 e 2013, viene scaricata anche la guida di un utente che fornisce dettagli sull'uso. 
  
Per facilitare la gestione del foglio di calcolo, le varie celle del foglio di calcolo sono codificate a colori:
  
- **Verde** Aree di input per dati generali.
    
- **Giallo** Aree di input per dati avanzati. Queste modifiche possono essere modificate con attenzione.
    
- **Rosso** Aree di sola lettura con valori di input bloccati che non possono essere modificati.
    
- **Grigio** Aree di sola visualizzazione. Si tratta dei risultati o dei dati delle aree di input generali.
    
Processo di progettazione per Dewey Law LLC. inizia caratterizzando gli utenti in diversi "Utenti tipo". Per ciascun utente tipo definito, è possibile specificare l'utilizzo previsto delle varie applicazioni Skype for Business ('Nessuno', 'Basso', 'Medio', 'Alto' o una delle tre impostazioni definite "Personalizzato"). Queste selezioni si trovano nel foglio di lavoro "Utente tipo". Viene fornito l'utilizzo specifico per ogni scelta ('Bassa', 'Media' o 'Alta'), ma i valori predefiniti per ogni scelta possono essere modificati. Identificando il numero di utenti per ogni utente tipo situato in ogni sito, la calcolatrice può calcolare la larghezza di banda totale necessaria per ogni posizione.
  
È anche possibile specificare i codec audio e video utilizzati, se viene usata la correzione degli errori di inoltro e anche altri parametri di sistema che influiranno sui requisiti della larghezza di banda. È possibile utilizzare le impostazioni predefinite di Bandwidth Calculator di Lync 2010 e 2013 oppure selezionare codec diversi e altri parametri di sistema. Per la progettazione del sito Dewey Law LLC, è possibile usare le impostazioni predefinite. Tuttavia, per modificare una delle impostazioni predefinite è disponibile un menu a discesa con tutte le opzioni disponibili. Le larghezze di banda utilizzate per ogni scelta sono incluse nel foglio di lavoro "Codec". Quando si modifica qualsiasi impostazione, la modifica della larghezza di banda e della classe di servizio (CoS) in ogni sito viene aggiornata. Questa funzionalità consente di testare diverse configurazioni possibili e verificare l'impatto delle modifiche sui requisiti di larghezza di banda.
  
Abbiamo definito tre utenti tipo per Dewey Law LLC., "Dirigenti/Partner", "Società associate/Legali" e "Amministratori IT". La tabella seguente mostra come sono stati impostati i profili di utilizzo per le varie app Skype for Business per ciascun utente tipo.
  
 **Utenti tipo e profili di utilizzo (foglio di lavoro "Utente tipo" - Colonne da A a P)**
  
|**Utente tipo**|**Messaggistica istantanea/Presenza**|**Audio P2P**|**Video P2P**|**Audioconferenza**|**Videoconferenze**|**Condivisione del desktop**|**Audioconferenza**|**Lync 2010 RTV_Type**|**Utenti remoti**|**Audio stereo lync 2013**|**Qualità video di Lync 2013**|**Comportamento degli utenti di Lync 2013 per la finestra video P2P**|**Utilizzo di più opzioni in Lync 2013**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Dirigenti/Partner  <br/> |Alta  <br/> |Media.  <br/> |Bassa  <br/> |Media.  <br/> |Media.  <br/> |Nessuno  <br/> |Media.  <br/> |CIF  <br/> |0%  <br/> |0%  <br/> |Migliore  <br/> |Tipico  <br/> |Tipico  <br/> |
|Società associate/Paralegal  <br/> |Alta  <br/> |Media.  <br/> |Bassa  <br/> |Media.  <br/> |Alta  <br/> |Alta  <br/> |Media.  <br/> |CIF  <br/> |0%  <br/> |0%  <br/> |Media.  <br/> |Tipico  <br/> |Tipico  <br/> |
|Amministratori IT  <br/> |Alta  <br/> |Media.  <br/> |Nessuno  <br/> |Bassa  <br/> |Nessuno  <br/> |Nessuno  <br/> |Media.  <br/> |CIF  <br/> |0%  <br/> |0%  <br/> |Media.  <br/> |Tipico  <br/> |Tipico  <br/> |
   
Sarà necessario immettere le informazioni  nella tabella Distribuzione degli utenti per località e posizioni riportata sopra nel foglio di lavoro "Siti" di Bandwidth Calculator di Lync 2010 e 2013. Poiché il numero di utenti negli uffici regionali è identico, essi sono definiti per un solo sito e hanno specificato che vi sono tre istanze del sito. Lo stesso vale per le filiali grandi e piccole, rispettivamente di 24 e 50 utenti.
  
Dopo aver specificato le impostazioni per ogni utente tipo, è necessario immettere il numero di utenti di ogni utente tipo in ogni sito nel foglio di lavoro "Siti". Il totale degli utenti per tutti i siti viene aggiornato automaticamente. Poiché non ci sono utenti nella posizione di Microsoft 365 o Office 365, tutti devono essere immessi nelle righe "Rami" del foglio di lavoro. Bandwidth Calculator di Lync 2010 e 2013 popola quindi le colonne "Classe Best Effort", "Classe traffico dati" e "Classe traffico in tempo reale" nella tabella "WAN BW per classe di traffico QoS". Questo valore viene visualizzato nei dati della tabella seguente.
  
> [!TIP]
>  Il foglio di calcolo completo include anche il numero massimo di sessioni simultanee per ogni applicazione, ma queste colonne sono state eliminate per risparmiare spazio.
  
 **Utenti tipo per sito - (Foglio di lavoro "Siti" - Colonne A, D, I e AI fino a AX)**
  
|**Nome sito**|**Totale utenti nel sito**|**Totale siti come questo**|**Profilo utente 1**|**Utente del profilo 1**|**Profilo utente 2**|**Utente del profilo 2**|**Profilo utente 3**|**Utente del profilo 3**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sede centrale  <br/> |1070  <br/> |1  <br/> |Dirigenti/Partner  <br/> |170  <br/> |Società associate/Paralegal  <br/> |700  <br/> |Amministratori IT  <br/> |200  <br/> |
|Uffici regionali  <br/> |345  <br/> |3  <br/> |Dirigenti/Partner  <br/> |60  <br/> |Società associate/Paralegal  <br/> |225  <br/> |Amministratore IT  <br/> |60  <br/> |
|Filiali di grandi dimensioni  <br/> |70  <br/> |24  <br/> |Dirigenti/Partner  <br/> |11  <br/> |Società associate/Paralegal  <br/> |50  <br/> |Amministratore IT  <br/> |9  <br/> |
|Filiali piccole  <br/> |36  <br/> |50  <br/> |Dirigenti/Partner  <br/> |6  <br/> |Società associate/Paralegal  <br/> |25  <br/> |Amministratore IT  <br/> |1  <br/> |
   
 **Larghezza di banda richiesta per applicazione per sito in Kbps (foglio di lavoro "Siti" - Colonne A e BQ fino a LF)**
  
|**Sito**|**Larghezza di banda di picco SIP/MESSAGGISTICA ISTANTANEA**|**Larghezza di banda picco peer audio intersito**|**Larghezza di banda picco peer video intersito**|**Larghezza di banda di picco per le audioconferenze**|**Larghezza di banda di picco per le videoconferenze**|**Larghezza di banda di picco della condivisione WAN**|**Larghezza di banda massima WAN per le chiamate PSTN**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sede centrale  <br/> |1070  <br/> |525.30  <br/> |560.00  <br/> |739.50  <br/> |2640.00  <br/> |4224.00  <br/> |2688.30  <br/> |
|Uffici regionali  <br/> |345  <br/> |185.40  <br/> |560.00  <br/> |255.00  <br/> |1320.00  <br/> |1536.00  <br/> |896.10  <br/> |
|Filiali grandi  <br/> |70  <br/> |92.70  <br/> |560.00  <br/> |102.00  <br/> |600.00  <br/> |384.00  <br/> |216.30  <br/> |
|Filiali piccole  <br/> |36  <br/> |119.40  <br/> |560.00  <br/> |76.50  <br/> |600.00  <br/> |384.00  <br/> |123.60  <br/> |
   
Probabilmente le colonne più importanti del foglio di calcolo sono quelle che descrivono la larghezza di banda WAN per classe QoS. Questa opzione è illustrata nella tabella seguente. Questi dati riepilogano le informazioni che sarà necessario fornire al provider dei servizi di rete per ordinare la connessione di accesso a ogni sito. Quando si calcola la larghezza di banda totale, ricordarsi di moltiplicare la larghezza di banda per ogni tipo di sito di succursale per il numero di siti dello stesso tipo. Per connettersi con il partner dei servizi di rete ExpressRoute, è possibile vedere [Azure ExpressRoute.]( https://go.microsoft.com/fwlink/?LinkId=690283)
  
È molto importante non superare la larghezza di banda per la voce o la classe di servizio "Expedited Forwarding" (EF). Un set casuale di pacchetti verrà ignorato, quindi, invece di ridurre la qualità di una singola chiamata o di un gruppo di chiamate, tutte le chiamate in corso possono essere influenzate. È anche importante che solo la voce sia contrassegnata con DSCP per EF (ad esempio, DSCP = 46) oppure che la coda vocale si riversi quando viene aggiunto traffico non vocale.
  
> [!TIP]
>  Anche in questo caso, mentre la classe del servizio EF offre la garanzia di prestazioni migliori, se si supera la larghezza di banda definita, eventuali pacchetti aggiuntivi verranno immediatamente ignorati.
  
 **Larghezza di banda aggregata per sito per classe di traffico QoS - (Foglio di lavoro "Siti" - Colonne A e ML fino a MR)**
  
|**Nome sito**|**Classe Best Effort (DSCP 0)**|**Classe traffico di dati (DSCP personalizzato)**|**Classe traffico in tempo reale (DSCP 34, AF41)**|**Classe traffico prioritario (DSCP 46, EF)**|
|:-----|:-----|:-----|:-----|:-----|
|Sede centrale  <br/> |0.00  <br/> |5764.80  <br/> |3200.00  <br/> |3953.10  <br/> |
|Uffici regionali  <br/> |0.00  <br/> |2033.60  <br/> |1880.00  <br/> |1336.50  <br/> |
|Filiali grandi  <br/> |0.00  <br/> |486.40  <br/> |1160.00  <br/> |411.00  <br/> |
|Filiali piccole  <br/> |0.00  <br/> |438.40  <br/> |1160.00  <br/> |319.50  <br/> |
   
### <a name="putting-your-plan-into-action"></a>Applicazione del piano

È possibile calcolare la larghezza di banda totale che attraversa la WAN e la quantità di larghezza di banda che attraversa ExpressRoute usando le stime di larghezza di banda della tabella Per applicazione **per** sito precedente. La parte di traffico che attraversa ExpressRoute esclude la larghezza di banda peer tra siti.

 
|**Sito**|**Larghezza di banda di picco SIP/MESSAGGISTICA ISTANTANEA**|**Larghezza di banda di picco per le audioconferenze**|**Larghezza di banda di picco per le videoconferenze**|**Larghezza di banda di picco della condivisione WAN**|**Larghezza di banda massima WAN per le chiamate PSTN**|**Traffico totale ExpressRoute <br/> per classe di sito <br/> (ad esempio, tempo <br/> totale # dei siti)**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Sede centrale** <br/> |1,070  <br/> |739.50  <br/> |2640.00  <br/> |4224.00  <br/> |2688.30  <br/> |11361.80  <br/> |
|**Uffici regionali** <br/> |345  <br/> |255.00  <br/> |1320.00  <br/> |1536.00  <br/> |896.10  <br/> |8704.20  <br/> |
|**Filiali grandi** <br/> |70  <br/> |102.00  <br/> |600.00  <br/> |384.00  <br/> |216.30  <br/> |32935.20  <br/> |
|**Filiali piccole** <br/> |36  <br/> |76.50  <br/> |600.00  <br/> |384.00  <br/> |123.60  <br/> |61005.00  <br/> |
   
Questo significa che il traffico di Skype for Business online che attraversa il percorso rapido sarà di circa 114 Mbps, quindi Dewey avrà bisogno di almeno l'abbonamento di 200 Mbps per ExpressRoute. È possibile acquistare più circuiti ExpressRoute in diverse posizioni di peering di ExpressRoute. Questa operazione potrebbe essere consigliata se i siti di Dewey si verificano in aree geografiche diverse o per garantire la resilienza in caso di errore di connessione al circuito ExpressRoute. Se si acquistano circuiti ExpressRoute in più aree geografiche Azure, sarà necessario il componente aggiuntivo Premium ExpressRoute per ricevere la connettività globale via ExpressRoute.
  
Ora che hai la quantità totale di larghezza di banda richiesta e i numeri di larghezza di banda della classe di servizio (CoS), puoi classe di servizio (CoS) inserire i tuoi ordini con i provider dei servizi di rete selezionati. Non dimenticare di includere le stime di traffico per altre applicazioni e servizi. Sono disponibili indicazioni per la pianificazione della rete per altri servizi di Microsoft 365 e Office 365, inclusi i calcolatori di larghezza di banda per Exchange e OneDrive. La sottoscrizione della larghezza di banda per il provider dei servizi di rete sarà superiore perché sarà necessario aggiungere di nuovo il traffico intrasodei siti. Bandwidth Calculator di Lync 2010 e 2013 fornisce solo una stima del traffico previsto, quindi è consigliabile confermare la capacità della rete di supportare quel volume di traffico che esegue un test di stress. 
  
> [!TIP]
> Il test di stress della rete è altamente consigliato quando si esegue una valutazione preliminare della rete. 
  
Un test di stress implica la creazione e la configurazione dell'infrastruttura e quindi la sua esecuzione con il volume previsto di traffico simulato, monitorando le prestazioni. Le stime di traffico potrebbero non essere accurate in alcune aree, ma almeno si può essere certi che sia in grado di supportare il volume di traffico previsto da Bandwidth Calculator di Lync 2010 e 2013. È consigliabile eseguire il test di stress per almeno alcuni giorni, ma l'esecuzione per periodi di tempo più lunghi consente di perfezionare i numeri. Tuttavia, l'estensione del periodo del test di stress deve essere valutata in base al costo dei servizi di rete che non trasportano un traffico di rete reale. Microsoft ha certificato diversi fornitori nell'ambito del programma IT Pro Tools, che forniscono strumenti per la gestione e le operazioni di rete, inclusi gli strumenti di verifica preliminare della rete. Skype for Business fornisce anche lo strumento Integrazione di sistemi (SI) che può eseguire la certificazione IT Pro Tools e la valutazione della rete. Ulteriori informazioni sono disponibili in [Skype for Business Solutions: IT Pro Tools.](https://go.microsoft.com/fwlink/?LinkID=690307)
  
Il test di stress garantisce che la rete sia in grado di supportare il volume di traffico necessario, ma in realtà i dati di Bandwidth Calculator di Lync 2010 e 2013 possono essere disattivati per diversi motivi. È anche consigliabile continuare a monitorare le reti dei siti eseguendo una valutazione continua di rete dopo la distribuzione per assicurarsi che la larghezza di banda sia sufficiente e che i meccanismi QoS funzionino correttamente. È importante continuare a monitorare le prestazioni di rete man via che un numero sempre maggiore di utenti reali viene messo in linea.
  
## <a name="part-2-expressroute-skype-for-business-qos"></a>Parte 2: QoS expressRoute Skype for Business

Il servizio ExpressRoute di Microsoft fornisce una connessione dedicata al cloud Azure, ma i servizi di comunicazione dei carichi di lavoro in tempo reale di Office 365 richiedono servizi di rete con larghezza di banda sufficiente per supportare il volume di traffico e sono in grado di supportare la qualità del servizio (QoS) per offrire un'esperienza utente di livello aziendale. Una connessione QoS deve essere configurata end-to-end (PC, switch e router di rete nel cloud) in quanto qualsiasi parte del percorso che non supporta la QoS potrebbe compromettere la qualità dell'intera chiamata.
  
Lo scopo di questa sezione è di aiutare l'utente a comprendere le sfide poste dal traffico in tempo reale in una rete IP e a configurare e supportare una distribuzione ExpressRoute corretta dei carichi di lavoro in tempo reale di Microsoft 365 o Office 365 usando un partner Microsoft ExpressRoute Exchange Provider o Un provider di servizi di rete.
  
La QoS viene accettata dalle tue reti esclusivamente su circuiti di rete ExpressRoute e viene utilizzata all'interno della rete Microsoft per il traffico di Skype for Business. Oggi, parti di alcune connessioni in uscita da Microsoft non hanno valori DSCP per Skype for Business. Finché il traffico in uscita non viene contrassegnato completamente con valori DSCP, è consigliato di seguire le linee guida per l'aggiunta di contrassegni QoS al traffico al confine di rete, come descritto nella sezione Implementazione della QoS mediante l'elenco di controllo di accesso **(ACL)** di rete di questo articolo.
  
### <a name="the-real-time-problem"></a>Il problema del tempo reale

L'offerta di servizi vocali e video di qualità aziendale pone specifiche richieste su una rete IP. Il traffico in tempo reale utilizza il protocollo RTP (Real-time Transport Protocol) che viene trasportato tramite UDP (User Datagram Protocol). A differenza del protocollo TCP (Transmission Control Protocol) che numeri e verifica la presenza di errori in ogni messaggio e include altri meccanismi per rilevare e ritrasmettere i messaggi persi o con errori, UDP non fornisce questo tipo di affidabilità. Se i messaggi sono danneggiati a causa di errori o persi a causa di sovraccarico del buffer, questi vengono persi. Il protocollo UDP è stato scelto per l'uso con RTP perché la natura del traffico in tempo reale è che, anche se i messaggi persi vengono inviati nuovamente, arrivano troppo tardi per avere un impatto positivo sul flusso dei messaggi vocali.
  
Conoscendo l'impatto dei pacchetti vocali smarriti, i progettisti hanno adottato due approcci per migliorare le prestazioni di voce e video su IP:
  
- Rendere la codifica/decodifica vocale più resiliente quando i pacchetti vengono persi. Questa operazione può essere eseguita usando correzione degli errori di inoltro (FEC, Forward Error Correction) per correggere una percentuale di errori rilevati, ovvero una funzionalità di Microsoft 365 o Office 365 Real Time Transport, oppure progettando sistemi di decodifica vocale che tentano di mascherare l'effetto dei pacchetti smarriti, ovvero una caratteristica dei codec Microsoft. 
    
- Usare servizi di trasporto che usano meccanismi di qualità del servizio per garantire le prestazioni della rete in relazione a ritardi, perdite di pacchetti e instabilità e alla variazione del ritardo tra i pacchetti.
    
La codifica vocale resiliente risolve solo il problema della perdita di pacchetti, quindi è importante che una rete usata per portare voce e video in tempo reale abbia meccanismi che ritienino ritardi e instabilità. Anche con la codifica resiliente, se vengono persi troppi pacchetti, la stazione di ricezione non dispone di informazioni sufficienti per ricostruire una versione riconoscibile del segnale vocale. La percentuale di pacchetti persi che causa un evidente degrado della qualità vocale varia a seconda della tecnica di codifica vocale usata. In tutti i casi, tuttavia, la perdita di stringhe di pacchetti successivi è molto problematica.
  
È importante ridurre al minimo il ritardo perché un ritardo eccessivo può influire sul flusso della conversazione e creare fastidi per gli altoparlanti. Le procedure consigliate ci dicono che il ritardo end-to-end per la voce (detto ritardo "bocca-auricolare") deve essere mantenuto al di sotto dei 150 millisecondi (msec). unidirede, non un ritardo di tipo "round trip". Naturalmente il ritardo aumenta per i collegamenti di trasmissione più lunghi, come quelli che attraversano gli oceani, in base al ritardo di propagazione o al tempo necessario al segnale per viaggiare fisicamente sul cavo.
  
Quando il ritardo è superiore a 150 msec. unidiretivo ha uno strano effetto sull'altoparlante. Dal punto di vista fisico, un orologio nel cervello dell'altoparlante fa pensare che il destinatario non li ha ascoltati e ripete l'ultima cosa che hanno detto. Questo problema si urta con la risposta ritardata proveniente dall'estrema estremità. Se si parla su un canale satellitare, si riconoscerà questo effetto. Su un canale satellitare il ritardo unidiretario è di circa 250 msec, molto oltre il ritardo consentito.
  
 **Parametri di rete consigliati per voce di livello aziendale**
  
|**Parametro**|**Valore consigliato**|
|:-----|:-----|
|Instabilità media tra arrivi di pacchetti (media)  <br/> |≤ 5 ms  <br/> |
|Instabilità tra arrivi di pacchetti (massima)  <br/> |≤ 40 ms  <br/> |
|Tasso di perdita pacchetti (media)  <br/> |Lo 0% si avvicina  <br/> |
|Latenza di rete unidiredirezia  <br/> |≤ 100 ms (deve includere i controlli sul ritardo rispetto alla distanza geografica)  <br/> |
   
### <a name="expressroute-as-part-of-a-business-grade-voice-network"></a>ExpressRoute come parte di una rete voce di livello aziendale

ExpressRoute offre una connessione dedicata tramite un provider di servizi di rete (NSP) o un provider Exchange (EXP) in una delle 3 opzioni di connessione: 
  
- Cloud Exchange Colocation
    
- Connessione Ethernet Point-to-Point
    
- Connessione Any-to-Any (IPVPN)
    
In questo modo vengono offerti vantaggi come disponibilità elevata (contratto di servizio (SLA) con tempo di attività del 99,9%) e routing affidabile, sicuro (nessun transito Internet), non interessato dalle variazioni del traffico Internet e vengono rispettati i contrassegni di qualità del servizio (QoS) per assegnare priorità al traffico (la QoS è illustrata di seguito). ExpressRoute, insieme a una WAN ben pianificata, può fornire una rete voce di livello aziendale.
  
È possibile usare ExpressRoute per il transito dei dati da uffici o data center (se topologia ibrida) connessi al circuito. I dati per gli utenti fuori sede (ad esempio, da casa, in viaggio e così via) non sfruttano il circuito ExpressRoute a meno che gli utenti non siano connessi alla VPN e non devono essere inclusi nelle stime della larghezza di banda per dimensionare il circuito ExpressRoute. Se si è un cliente internazionale, è possibile acquistare circuiti ExpressRoute in ogni area geografica e usare i tag della community BGP per informare le regole di routing in modo che il traffico venga diretto al circuito ExpressRoute preferito (in genere quello più vicino per ogni sito), mentre gli altri circuiti offrono ridondanza in caso di interruzione che interessa un singolo circuito. 
  
### <a name="if-expressroute-isnt-an-option"></a>Se ExpressRoute non è un'opzione

Potrebbe non essere possibile connettere tutti i siti a ExpressRoute, a causa dei costi, dell'impossibilità di soddisfare i prerequisiti ExpressRoute o a causa di limitazioni dell'attuale NSP. Se non riesci a usare ExpressRoute, segui comunque le indicazioni seguenti per contrassegnare QoS all'interno della rete e per pianificare i contratti con il tuo NSP in modo da assicurare larghezza di banda e supporto sufficienti per la definizione delle priorità del traffico in base al QoS.
  
Inoltre, se si hanno uffici in più aree geografiche, ma non si dispone di circuiti ExpressRoute in tutte le aree geografiche, è consigliabile usare i tag della community BGP dell'area quando si configura il routing da/verso uffici satellitari in modo da evitare il trasporto di lunghe fretta. Ad esempio, si consideri un'azienda che ha un'organizzazione Skype for Business online ospitata negli Stati Uniti, ma con succursali in Europa e che ha un solo circuito ExpressRoute nella Silicon Valley. La maggior parte del traffico di Skype for Business online verrà instradato a un data center in cui è ospitata l'organizzazione (ad esempio, conferenze telefoniche con altri utenti all'interno dell'azienda), per la maggior parte del traffico è preferibile usare il circuito ExpressRoute. Tuttavia, se un utente in Europa partecipasse a una conferenza telefonica ospitata da un'altra società la cui organizzazione si trova in Europa, la destinazione dei contenuti multimediali in quella chiamata sarebbe il data center europeo in cui si trova la seconda società. Il routing del traffico attraverso il circuito ExpressRoute nella Silicon Valley sarebbe un percorso meno diretto di quanto sarebbe possibile tramite Internet. In tal caso, può essere necessario configurare i router all'interno della rete (ad esempio, negli uffici europei) per analizzare i tag della community durante la creazione delle regole di routing e il routing tramite Internet invece che tramite il circuito ExpressRoute della Silicon Valley per il traffico con tag dell'area geografica europea.
  
### <a name="basic-concepts-of-quality-of-service-qosclass-of-service-cos"></a>Concetti di base di QoS (Quality of Service)/CoS (Class of Service)

In IP, la qualità del servizio (QoS, Quality of Service) descrive qualsiasi meccanismo utilizzato per fornire una gestione prioritaria di alcuni pacchetti rispetto ad altri. In base alla definizione dell'ITU (International Telecommunications Union), QoS comprende tutti gli aspetti di qualità di una connessione, tra cui ritardo, perdita, rapporto segnale-rumore, crosstalk, eco, interruzioni, risposta in frequenza, livelli di rumorosità e così via. Quello che si riferisce al termine QoS nelle reti a pacchetti è più correttamente noto come CoS (Class of Service), in particolare per migliorare le prestazioni in caso di ritardi, instabilità e perdite di pacchetti, ma continueremo a usare il termine QoS perché viene usato più comunemente.
  
L'offerta di QoS in una rete IP richiede due componenti principali:
  
- Prenotazione di una quantità definita di larghezza di banda su ciascun collegamento per il traffico in tempo reale; se tale larghezza di banda non è necessaria per il traffico in tempo reale in qualsiasi momento, può essere usata per altro traffico. In base alle indicazioni generali, al traffico vocale non deve essere assegnato più del 30% della capacità di qualsiasi collegamento.
    
- Contrassegno dei pacchetti con un indicatore di priorità nell'intestazione che indica agli switch e ai router nel percorso la priorità del pacchetto da assegnare.
    
Quando un pacchetto viene ricevuto da uno switch o router, viene spostato in una coda di output per la coda o l'hop successivo. Esistono diverse code di output per i diversi livelli di priorità. Uno switch o router utilizza un algoritmo che consente di ordinamento della coda ad alta priorità più frequentemente delle code con priorità inferiore.
  
Il problema sta nel fatto che esistono diverse tecniche QoS implementate al livello 2 (ad esempio, il livello Ethernet o Wi-Fi) e al livello 3 (ad esempio, il livello IP). Queste diverse implementazioni QoS possono richiedere la configurazione in ogni switch o router della rete, nonché l'interfaccia tra la rete dell'utente e la rete del provider dei servizi di rete.
  
Esistono due opzioni per la mappatura dei dati delle varie applicazioni Skype for Business alle classi di servizio appropriate:
  
- Contrassegno del punto finale del traffico con DSCP (Differentiated Services Control Point) 
    
- Basato sull'elenco di controllo di accesso (ACL, Access Control List) di rete
    
### <a name="end-point-traffic-marking--differentiated-services-control-point-dscp"></a>Contrassegno del traffico end point - DSCP (Differentiated Services Control Point)

I servizi differenziati (DiffServ) sono chiamati meccanismi a "granularità grossosa" per classificare e gestire il traffico di rete e fornire la qualità del servizio (QoS) nelle reti IP. I router e altri dispositivi che implementano funzioni di livello 3 usano il DSCP (DiffServ Control Point) per definire la priorità del pacchetto. La qualità del servizio (QoS) viene implementata inserendo un valore DSCP a 6 bit nel campo Servizi differenziati (in precedenza il campo "Tipo di servizio") nell'intestazione IP; La versione a 6 bit consente di creare 64 diversi livelli di priorità. I livelli di priorità sono in genere definiti come illustrato di seguito.
  
 **Impostazioni DSCP consigliate**
  
|**Classe traffico**|**Trattamento (contrassegno DSCP)**|**Carichi di lavoro di Skype for Business**|
|:-----|:-----|:-----|
|**Opzioni vocali** <br/> |EF (46)  <br/> |Chiamate vocali di Skype for Business e Lync  <br/> |
|**Interattivo** <br/> |AF41 (34)  <br/> |Video  <br/> |
||AF21 (18)  <br/> |Condivisione applicazioni  <br/> |
|**Impostazione predefinita** <br/> |AF11 (10)  <br/> |Trasferimento di file  <br/> |
||CS0 (0)  <br/> |Qualsiasi altra cosa  <br/> |
   
 **Intestazione IP versione 4**
  
![Intestazione IPv4](../images/c8a6a714-2784-4328-8297-2e62706f302d.png)
  
### <a name="layer-2-qos-ieee-8021pwi-fi-multi-media-ieee-80211e"></a>QoS livello 2: IEEE 802.1p/Wi-Fi Multi-Media (IEEE 802.11e)

Anche se DSCP è il meccanismo standard per l'implementazione della QoS al livello 3, esistono diversi meccanismi QoS di livello 2 per reti cablate (ad esempio Ethernet) e wireless (ad esempio Wi-Fi). Il meccanismo QoS per le reti cablate è definito nello standard IEEE 802.1p; il meccanismo QoS WLAN è definito nello standard IEEE 802.11e, che la Wi-Fi Alliance identifica come "Certificato Wi-Fi Multi-Media" (certificato WMM).
  
Lo IEEE 802.1p usa un PCP (Priority Code Point) a 3 bit per identificare la priorità del messaggio; Il PCP fa parte di un campo a 32 bit nell'intestazione Ethernet che trasporta anche l'identificatore VLAN. Le definizioni dei valori PCP sono riportate di seguito.
  
 **Valori PCP IEEE 802.1p**
  
|**Valore PCP**|**Priorità**|**Acronimo**|**Tipi di traffico**|
|:-----|:-----|:-----|:-----|
|7  <br/> |7  <br/> |NC  <br/> |Network Control  <br/> |
|6  <br/> |6  <br/> |IC  <br/> |Internetwork Control  <br/> |
|5  <br/> |5  <br/> |VO  <br/> |Opzioni vocali  <br/> |
|4  <br/> |4  <br/> |VI  <br/> |Video  <br/> |
|3  <br/> |3  <br/> |CA  <br/> |Applicazioni critiche  <br/> |
|2  <br/> |2  <br/> |EE  <br/> |Excellent Effort  <br/> |
|0  <br/> |1  <br/> |BE  <br/> |Best Effort  <br/> |
|1  <br/> |0  <br/> |BK  <br/> |Sfondo  <br/> |
   
Laddove IEEE 802.1p è implementato in modo molto identico al DSCP con il traffico ordinato in diverse code di priorità per ogni livello di priorità, ma la natura degli elementi multimediali condivisi delle WLAN richiama un approccio diverso. Mentre il punto di accesso e il client manterranno code di output separate per i diversi livelli di priorità, vi sono differenze anche nel modo in cui i frame vengono inviati sul canale radio.
  
In una rete Wi-Fi tutti i client associati a un punto di accesso condividono un unico canale half-duplex (ad esempio, solo una stazione client o il punto di accesso può inviare postazione per volta). Per ridurre al minimo la possibilità di collisioni sul canale radio, prima di inviare un frame, la stazione attende che il canale sia inattivo per un determinato periodo di tempo, detto "Spaziatura tra frame", se il canale è occupato quando una stazione va in invio, si riattiva per un periodo di tempo casuale. Una volta inviato il frame, se il mittente non riceve un messaggio di conferma dal destinatario, presuppone che sia avvenuta una collisione o un altro errore e torna a un intervallo casuale prima di tentare di accedere al canale radio per l'invio di nuovo. L'intervallo di back-off è casuale per ridurre la probabilità che le stesse due stazioni collideranno nuovamente.
  
Per dare priorità all'accesso al canale radio, IEEE 802.11e/WMM definisce diversi intervalli di attesa di pre-trasmissione denominati "Spaziature Inter-Frame arbitrate" (AFIS) e diversi intervalli di back-off per le diverse classi di traffico; Sono definiti quattro livelli di priorità denominati "categorie di Access".
  
La priorità viene assegnata assegnando valori AFIS più brevi ai frame con priorità più alta. Quindi, se una stazione è in attesa di inviare un frame vocale e un'altra è in attesa di inviare un frame dati, il frame voce verrà sempre inviato per primo. Tecnicamente, ai frame voce e video viene assegnato lo stesso valore AFIS, ma la gamma di intervalli di back-off per i fotogrammi video è superiore. Quindi, mentre un frame voce e video può collidere al primo tentativo, il fotogramma voce sarà sempre ritrasmesso prima. La correlazione tra IEEE 802.1p e IEEE 802.11e è illustrata di seguito:
  
 **Mapping da IEEE 802.11e/Wi-Fi Multi-Media (WMM) a 802.1P**
  
|**Categoria di accesso WMM**|**Descrizione WMM**|**Valore PCP 802.1P**|**Designazione 802.1P**|
|:-----|:-----|:-----|:-----|
|1 (AC_VO)  <br/> |Opzioni vocali  <br/> |7 (111)  <br/> |NC  <br/> |
|6 (110)  <br/> |VO  <br/> |
|2 (AC_VI)  <br/> |Video  <br/> |5 (101)  <br/> |VI  <br/> |
|4 (100)  <br/> |CL  <br/> |
|3 (AC_BE)  <br/> |Dati Best Effort  <br/> |3 (011)  <br/> |EE  <br/> |
|0 (000)  <br/> |BE  <br/> |
|4 (AC_BK)  <br/> |Dati in background  <br/> |1 (001)  <br/> |BK  <br/> |
|2 (010)  <br/> |---  <br/> |
   
L'associazione consigliata delle priorità di livello 3 a livello 2 è illustrata di seguito:
  
 **Associazioni di priorità di livello 3 e livello 2 consigliate**
  
||**Contrassegni livello 3**|**Livello 2 (valore PCP)**|**Wi-Fi (categoria di accesso)**|
|:-----|:-----|:-----|:-----|
|Network Control  <br/> |Per Hop Behavior (PHB) - Class Selector (CS) 6  <br/> |6  <br/> |1 (AC_VO)  <br/> |
|Valore DSCP -48  <br/> |
|Opzioni vocali  <br/> |Per Hop Behavior (PHB) - Expedited Forwarding (EF)  <br/> |5  <br/> |1 (AC_VO)  <br/> |
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
   
È importante notare che la codifica di priorità per IEEE 802.1p e WMM non corrisponde. Il valore PCP 802.1p per la voce è 5, tuttavia, nella mappatura di equivalenza standard su WMM, PCP 5 viene convertito nella categoria di accesso 2, la categoria di accesso WMM per i video (AC_VI). Se possibile, è consigliabile ignorare tale mappatura in modo che PCP 5 si traduca nella categoria 1 di Access o semplicemente evitare di usare voce e video sulla stessa rete Wi-Fi finché Wi-Fi Alliance non risolve il problema. Per altre informazioni sulla rete Wi-Fi, vedere [gli elementi del catalogo Wi-Fi.]( https://go.microsoft.com/fwlink/?LinkId=690322)
  
### <a name="implementing-qos-using-network-access-control-list-acl"></a>Implementazione della QoS utilizzando l'elenco di controllo di accesso (ACL) di rete

Il metodo alternativo per implementare la QoS in una configurazione ExpressRoute consiste nell'usare l'elenco di controllo di accesso (ACL, Access Control List) di rete. In questo approccio, invece di avere gli end point, inserire il contrassegno DSCP appropriato nell'intestazione di ogni pacchetto, il contrassegno può essere eseguito da un router upstream, in base alla porta di origine UDP. Tutti gli switch e i router devono comunque essere configurati per supportare la QoS per garantire che le impostazioni DSCP siano mantenute. E ancora più importante, il router connesso alla rete del provider di servizi deve mantenere il DSCP nell'intestazione di ogni pacchetto, in quanto tale impostazione DSCP è essenzialmente l'istruzione al provider dei servizi di rete su come deve essere considerato tale pacchetto.
  
Gli intervalli di porta consigliati per ogni applicazione Skype for Business sono elencati nella Sezione 2.6.1.1 della guida Pianificazione di rete, monitoraggio e risoluzione dei problemi con [Lync Server.](https://go.microsoft.com/fwlink/?LinkId=690286) È importante che tale operazione sia coordinata con l'approccio generale dell'organizzazione in fatto di QoS e che si debbano cercare diversi criteri QoS e potenziali mancati contrassegni dei pacchetti.
  
Anche se il motivo principale per cui vengono utilizzati i servizi di rete QoS e MPLS è quello di garantire una buona esperienza utente per voce e video in tempo reale, le stesse funzionalità possono essere applicate anche alle applicazioni di dati. Invece di trattare tutte le applicazioni allo stesso modo, le reti MPLS possono consentire alle organizzazioni di dare la priorità ad alcune applicazioni di dati rispetto ad altre. Con MPLS, le applicazioni in tempo reale come le transazioni con carta di credito o la condivisione dello schermo possono avere la priorità rispetto al traffico sensibile al tempo più basso, come la posta elettronica.
  
### <a name="understanding-the-types-of-ip-network-services--basic-ip-and-mpls"></a>Informazioni sui tipi di servizi di rete IP - IP di base e MPLS

L'inoltro dei pacchetti IP originale si baseva sul principio del "best effort". Questo significava che i router che inoltravano quei pacchetti IP avrebbero fatto del loro meglio per inviare i pacchetti alle loro destinazioni, ma che non vi era alcuna garanzia in merito a quando e se arrivano alle loro destinazioni. Ecco come funzionano oggi i servizi Internet di base, inclusa la connessione Internet domestica. L'idea era che, se per una particolare applicazione era richiesta affidabilità, verrebbe fornita a un livello superiore nello stack del protocollo. Il meccanismo di consegna affidabile è il protocollo TCP (Transmission Control Protocol). L'UDP (User Datagram Protocol), usato per voce e video in tempo reale, è il meccanismo di consegna non affidabile (ad esempio , "best effort"). 
  
Il protocollo MPLS (Multi-Protocol Label Switching) è stato sviluppato come mezzo per offrire ai provider dei servizi di rete un servizio IP con garanzie di prestazioni in caso di ritardi, instabilità e perdite di pacchetti. Per offrire tali garanzie di prestazioni, MPLS prende alcune delle inconsapevolmente dell'IP tradizionale. Prima di tutto, invece di fare in modo che ogni pacchetto trovi il percorso da router a router verso la destinazione (il risultato potrebbe essere che ogni pacchetto prende una route diversa dall'origine alla destinazione), MPLS instrada tutti i pacchetti su una connessione a "circuito virtuale" con una route fissa denominata LSP (Label Switched Path). Se uno dei collegamenti nel percorso non riesce, tutti gli LSP che usano quel collegamento vengono rapidamente reinstradati.
  
Quando un pacchetto viene inviato alla rete MPLS, il router perimetrale del provider dei servizi di rete aggiunge un'intestazione aggiuntiva al pacchetto che include un'etichetta usata per inoltrarlo sull'LSP appropriato. L'etichetta viene spogliata dal router perimetrale all'altra estremità della rete MPLS.
  
Oltre a semplificare il processo di inoltro, l'altro vantaggio fornito da MPLS è che il sistema di gestione della rete saprà quali connessioni vengono trasportate su ogni collegamento della rete. Controllando il modo in cui il traffico viene instradato attraverso la rete, l'operatore può garantire la QoS che ogni percorso fornirà. Quindi, a differenza delle prestazioni "best effort" dell'IP tradizionale o di base, gli operatori MPLS possono fornire un servizio IP con prestazioni prevedibili. Tale LSP rende inoltre MPLS intrinsecamente più sicuro dei servizi Internet tradizionali. Pertanto, con il servizio IP di base ci auguriamo che la rete funzioni abbastanza bene da fornire una buona qualità vocale e usare tecniche come FEC e una codifica vocale più resiliente per migliorare queste probabilità, ma con il metodo MPLS ne abbiamo la certezza.
  
I provider MPLS offrono diverse sfumature di classe di servizio che purtroppo utilizzano termini diversi per identificarli. Sarà necessario lavorare a stretto contatto con il provider per assicurarsi che comprenda gli output di [Bandwidth Calculator di Lync 2010 e 2013](https://go.microsoft.com/fwlink/?LinkID=690282) e le opzioni consigliate per diverse applicazioni di Microsoft 365 o Office 365 In tempo reale.
  
## <a name="conclusion"></a>Conclusione

Skype for Business migliora il modo in cui vengono condotte le comunicazioni aziendali. Invece di avere un telefono connesso a un PBX, un sistema di videoconferenza autonomo, una piattaforma separata per la posta elettronica, un servizio esterno per le audioconferenze e alcuni strumenti per la messaggistica istantanea e la presenza, Skype for Business può riunire tutte queste funzionalità in un'unica interfaccia utente.
  
Una distribuzione coerente dei servizi voce e video in tempo reale di livello aziendale richiede un'infrastruttura di rete end-to-end in grado di fornire QoS. Ciò includerebbe sia i servizi LAN che WAN. Microsoft fornisce strumenti come Bandwidth Calculator di [Lync 2010 e 2013](https://go.microsoft.com/fwlink/?LinkID=690282) per stimare la capacità di rete necessaria per i vari servizi. Inoltre, ci sono partner nel programma IT Pro [Tools Skype for Business Solutions: IT Pro Tools](https://go.microsoft.com/fwlink/?LinkID=690307) che offrono strumenti per valutare in modo preliminare l'infrastruttura di rete e supportare il monitoraggio, la creazione di report e la risoluzione dei problemi. Senza un'infrastruttura di rete correttamente dimensionata e configurata, si rischia di avere una distribuzione ExpressRoute Skype of Business che non soddisfa le aspettative degli utenti in fatto di qualità e coerenza.
  
Strumenti aziendali efficaci devono avere prestazioni affidabili e coerenti e offrire un'esperienza utente che incoraggi l'adozione da parte degli utenti. Da un punto di vista di rete, ciò significa avere un'infrastruttura di rete, sia locale che wide area, fissa e mobile, che può consentire questo. Pianificare, progettare, implementare e gestire tale infrastruttura non è sempre facile. L'hardware, gli strumenti e i servizi di rete per raggiungere questi obiettivi sono oggi disponibili, ma è responsabilità dei professionisti IT verificare che siano progettati, implementati e gestiti in modo da garantire agli utenti un set di servizi di collaborazione e comunicazione che consentano loro di lavorare in modo efficiente ed efficace e che l'organizzazione possa trarre pieno vantaggio da ciò che questa tecnologia offre. 
  
## <a name="related-topics"></a>Argomenti correlati

[Documentazione di ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690285)

  
 