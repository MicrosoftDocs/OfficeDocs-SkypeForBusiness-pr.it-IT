---
title: ExpressRoute e QoS in Skype for Business in linea
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 20c654da-30ee-4e4f-a764-8b7d8844431d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "Informazioni sull'utilizzo di Azure ExpressRoute disporre di una rete con larghezza di banda e funzionalità di qualità del servizio per un'esperienza utente di classe business. "
ms.openlocfilehash: 7073840031013d41013762b190ccdc568840cceb
ms.sourcegitcommit: 61127a5723fe58545b0b19edb2e2d4260965eb4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2017
---
# <a name="expressroute-and-qos-in-skype-for-business-online"></a>ExpressRoute e QoS in Skype for Business in linea

Connettersi a Office 365 tramite una connessione di rete dedicata utilizzando ExpressRoute Azure per Office 365 e Skype Business online. La connessione dedicata per la Skype per le applicazioni aziendali per ottenere prestazioni affidabile e prevedibile nonché privacy internet pubblico. È ora possibile acquistare una connessione di rete migliore per Office 365 e Skype Business online che aggiunge la prevedibilità, affidabilità di livello aziendale e viene fornito con un SLA uptime.
  
> [!NOTE]
> È disponibile una nuova versione del calcolo della larghezza di banda: [Skype per le aziende, strumento di calcolo della larghezza di banda](https://go.microsoft.com/fwlink/?LinkId=715766). Tuttavia, le istruzioni contenute in questo documento utilizzano Lync 2010 e strumento di calcolo della larghezza di banda 2013. 
  
## <a name="skype-for-business-online-and-expressroute"></a>Skype per le aziende Online ed ExpressRoute

Utilizzo dei partner ExpressRoute di Microsoft, è possibile connettere diversi di applicazioni di Office 365 inclusi Skype Business online nel cloud tramite una connessione dedicata. Tuttavia, la voce in tempo reale e funzionalità di comunicazione video per Skype per le aziende richiedono servizi di rete che sono configurati in modo specifico per il supporto di questi carichi di lavoro in tempo reale di Office 365. Sono incluse una rete con larghezza di banda sufficiente per eseguire il volume del traffico necessario ed essere in grado di supportare qualità del servizio (QoS) per offrire un'esperienza di classe aziendali per gli utenti.
  
In questo documento è progettato per è, gli amministratori e progettisti di rete comprendere le problematiche necessarie per supportare le comunicazioni in tempo reale, gli strumenti forniti da Microsoft per agevolare la progettazione di una rete in grado di supportare quelle requisiti e per esaminare il processo di progettazione utilizzando un case study. 
  
La prima parte del presente documento si illustra un case study di aiutarti con la struttura della rete con [Lync 2010 e strumento di calcolo della larghezza di banda 2013](https://go.microsoft.com/fwlink/?LinkId=690282) per stimare i requisiti di rete per un Skype più siti e di grandi dimensioni per la distribuzione ExpressRoute Business. La seconda parte del presente documento permette di utilizzare con i concetti fondamentali della qualità del servizio (QoS), un approfondimento le attività specifiche tecniche per il supporto Skype per le comunicazioni in tempo reale Business e i tipi di servizi di rete che sono specifici necessarie.
  
Tutte le informazioni di seguito vengono fornite informazioni tecniche e informazioni per QoS ed ExpressRoute, una conoscenza di verifiche specifiche verrà affiancate e fornire una conoscenza degli strumenti e le tecniche che consentono di correttamente distribuire un ExpressRoute tra i Skype per la rete aziendale. 
  
## <a name="getting-started"></a>Guida introduttiva

Durante la preparazione per ExpressRoute per Skype per le aziende, è consigliabile esaminare i diversi modelli di connessione ExpressRoute e la scelta dei partner e posizioni diverse e informazioni su come acquistare ed eseguire il provisioning ExpressRoute all'interno dell'azienda. Di seguito sono riportate alcune risorse introduttive: 
  
- [Azure ExpressRoute]( https://go.microsoft.com/fwlink/?LinkId=690283)
    
- [Prezzo ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690284)
    
- [Documentazione ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690285)
    
## <a name="part-1-case-study---expressroute-for-dewey-law-llc"></a>Parte 1: Case study - ExpressRoute per Dewey Law, LLC.

In questo case study per Dewey Law, LLC. verrà illustrato come installare una rete, servizi di accesso di rete ordine e determinare i requisiti di larghezza di banda per supportare ExpressRoute Skype Business online.
  
 **Sfondo** Legge dewy LLC. è un'azienda di grandi dimensioni diritto con 790 legali e un totale di 5,580 dipendenti dislocata in 78 posizioni. L'azienda ha una sede New York, tre uffici in Chicago, San Francisco e Dallas, insieme a 24 grandi e 50 succursali distribuiti in tutto il paese. L'azienda gestisce i casi complesse di grandi dimensioni con il carico di lavoro in genere distribuito tra due o più degli uffici. Con questo risultati di progettazione di rete una notevole del traffico di rete tra uffici.
  
Legge dewy LLC. è una società relativamente giovane e i legali e gli altri membri dello staff molto ha familiarità con la tecnologia e notevolmente utilizzabili per il lavoro giornaliero. 
  
 **Distribuzione degli utenti da posizioni e le posizioni**
  
||**Headquarters (NY)**|**Uffici (3)**|**Filiali di grandi dimensioni (24)**|**Succursali (50)**|
|:-----|:-----|:-----|:-----|:-----|
|Executive  <br/> |20  <br/> |10  <br/> |1  <br/> |1  <br/> |
|Partner  <br/> |150  <br/> |50  <br/> |10  <br/> |5  <br/> |
|Consente di associare  <br/> |300  <br/> |100  <br/> |20  <br/> |10  <br/> |
|Paralegal  <br/> |400  <br/> |125  <br/> |30  <br/> |15  <br/> |
|Amministratori Executive  <br/> |100  <br/> |35  <br/> |6  <br/> |3  <br/> |
|IT e amministrativi generali  <br/> |100  <br/> |25  <br/> |3  <br/> |2  <br/> |
|Totali per sito.  <br/> |1,070  <br/> |345  <br/> |70  <br/> |36  <br/> |
|Totale per ogni classe di sito  <br/> |1,070  <br/> |1,035  <br/> |1,680  <br/> |1.800  <br/> |
   
### <a name="setting-up-the-network"></a>Configurazione di rete

Per fornire servizi in tempo reale coerente di alta qualità per Dewey Law LLC., esistono alcuni requisiti nozioni di base che devono essere soddisfatti:
  
- Desiderano offrire servizi vocali durante l'interruzione dell'alimentazione in modo che le opzioni di distribuzione di rete e i router deve fornire power over Ethernet (PoE) IEEE 802.3 AF o 802.3at.
    
- Gli switch di rete e i router necessario utilizzare anche fonti di alimentazione continuità (UPS) in modo che possano continuare operativo durante un'interruzione dell'alimentazione.
    
    Hanno una connessioni Wi-Fi nelle rispettive sedi LAN, pertanto è consigliabile che utilizzano un Skype certified partner infrastruttura aziendale Wi-Fi da [Skype per soluzioni aziendali](https://go.microsoft.com/fwlink/?LinkId=690281).
    
    > [!TIP]
    >  è consigliabile utilizzare 802.11 n e 802.11ac punti di accesso wireless.
  
- E, in particolare, tutte le reti LAN negli uffici di tutto necessario da impostare per offrire qualità del servizio (QoS). Sono incluse PC, portatili e hardware, ad esempio router e switch di rete.
    
Dopo aver creato le nozioni fondamentali trattate, per fornire servizi di segreteria livello business per Dewey Law LLC., è consigliabile utilizzare servizio IP commutazione etichetta Multi-Protocol (MPLS) da un partner di servizio di rete che si connetterà al servizio ExpressRoute Azure. MPLS fornisce un servizio IP con prestazioni garanzie di ritardo, dall'instabilità e perdita di pacchetti. Se MPLS non è disponibile, una scheda Ethernet connessa a uno dei nostri ExpressRoute può essere utilizzato anche dati exchange partner.
  
MPLS provider offrono diverse classi di livelli di servizio, ma ogni diversi termini utilizzare per identificare in modo sicuro. È necessario lavorare a stretto contatto con il provider per garantire che acquisire familiarità con i dati che hanno voce in [Lync 2010 e strumento di calcolo della larghezza di banda 2013](https://go.microsoft.com/fwlink/?LinkID=690282) e le opzioni disponibili e consigliati per i diverso Office 365 in tempo reale del carico di lavoro applicazioni.
  
Sono disponibili due opzioni per la modalità dati da Skype per le applicazioni aziendali possono essere associati alle classi MPLS appropriate del servizio:
  
- Contrassegno di endpoint del traffico utilizzando DiffServ controllo Point (DSCP)
    
- Rete controllo elenco accesso (ACL) basati su
    
Per implementare il contrassegno Endpoint, è necessario configurare tutti i computer Windows aggiunto al dominio per evitare il diritto LLC. Per contrassegnare ogni pacchetto con il contrassegno DiffServ controllo Point (DSCP) appropriato e quindi implementare QoS in tutti i commutatori di rete e i router tra tutti i siti di office per verificare il QoS contrassegni vengono gestiti e non vengono rimossi. Contrassegni DSCP sui pacchetti di rete indicano al provider di servizio come una priorità corrispondente di pacchetti di rete. **Non vi sono ulteriori informazioni su DSCP nella sezione QoS nella parte 2.**
  
Per ACL all'assegnazione basata sulla rete, le indicazioni di priorità DSCP vengono implementate in un router monte e basate su porta di origine UDP. Gli intervalli di porte consigliato per ogni applicazione sono elencati nella sezione 2.6.1.1 della [Pianificazione della rete, monitoraggio e risoluzione dei problemi con Lync Server](https://go.microsoft.com/fwlink/?LinkId=690286). È importante questo coordinarsi con evitare legge LLC complessiva QoS progettazione e implementazione e tenere in considerazione la possibilità di contrassegnare le incongruenze di pacchetti e diversi criteri QoS.
  
Ogni provider di servizi di rete ExpressRoute avrà una classe di servizio (QoS) appropriato per audio e video in tempo reale. Questo COS viene chiamato 'Expedited inoltro' (EF) per audio e 'Assured inoltro' (AF) per il video. È necessario prestare particolare attenzione di ridimensionamento della larghezza di banda che acquisto di Enterprise voice traffico EF. Il motivo è che la classe vocale del servizio è molto grossi nel caso in cui si invia più il traffico vocale di provisioning per la classe di servizio.
  
> [!TIP]
>  Tutto il traffico inviato all'identificatore di classe vocale del servizio che superano impegno del provider di servizi viene rimosso immediatamente che fornirà qualità vocale effetto.
  
Quando si visualizza la struttura globale per evitare il diritto LLC. è estremamente importante stabilire in modo preciso la quantità di larghezza di banda necessaria per supportare il traffico vocale tra la rete e da contrassegnare ogni pacchetto vocale (e solo i pacchetti vocali) con l'impostazione DSCP di Enterprise voice (vale a dire il contrassegno DSCP EF 46).
  
Per implementare QoS all'interno dell'azienda, rete, l'endpoint o router necessario contrassegnare ogni pacchetto con l'indicatore di priorità livello 3 appropriato (ad esempio, il contrassegno DSCP). Lungo il percorso di rete intera ogni opzione e il router deve hanno la possibilità di QoS attivata. Disporre anche solo un commutatore di rete o di router priva di QoS attivata, QoS indicazioni sui pacchetti audio o video tramite tale opzione o un router potrebbero essere rimosse. In modo efficace, ciò consente di disabilitare QoS in tutti i commutatori downstream e router in grado di ridurre il valore di avere ExpressRoute.
  
Inoltre è necessario definire l'associazione delle priorità livello 3 e livello 2 QoS in ogni punto. In IEEE 802.1p per le reti cablate e 802.11 e vengono definiti i meccanismi di priorità livello 2 / WMM per reti Wi-Fi. Più importante, il router della rete con connessione di rete MPLS del provider di servizi di rete deve mantenere le impostazioni di DSCP su tutti i pacchetti in uscita in modo che mantiene la classe MPLS appropriata del servizio. 
  
> [!TIP]
>  Per dettagli specifici relativi alla configurazione di QoS, vedere 2.6 sezione [Pianificazione della rete, monitoraggio e risoluzione dei problemi con Lync Server]( https://go.microsoft.com/fwlink/?LinkId=760669). Puoi anche vedere [pianificare i requisiti di rete per Skype per 2015 aziendali](https://go.microsoft.com/fwlink/?LinkId=690287) per la rete ulteriori requisiti di pianificazione.
  
### <a name="ordering-network-access-services"></a>Ordinamento dei servizi di accesso di rete

Dopo avere creato i prerequisiti di rete QoS e meccanismi per il supporto ExpressRoute, il passaggio successivo è per effettuare un ordine per i servizi di accesso di rete ExpressRoute. Quando ordinano ExpressRoute access services per evitare il diritto LLC dal partner Microsoft network services provider, è necessario fornire due operazioni:
  
- La quantità totale di larghezza di banda necessaria per connettere ogni sito ExpressRoute e Office 365.
    
- Larghezza di banda totale necessario per ogni classe di servizio necessari per supportare Skype per le applicazioni aziendali utilizzati in evitare legge LLC. Si basa la classe dei requisiti di larghezza di banda del servizio per il volume del traffico si prevede di ciascuna di Skype diversi per le applicazioni di Business come voce, video, messaggistica immediata, presenza e condivisione dello schermo.
    
### <a name="determining-bandwidth-requirements-for-skype-for-business-applications"></a>Determinazione dei requisiti di larghezza di banda per Skype per le applicazioni aziendali

Per Dewey Law LLC., dopo avere stabilito la larghezza di banda totale necessario è ora necessario conoscere come tale quantità totale di larghezza di banda deve essere suddivisi tra le diverse classi di servizio. Ad esempio, la quantità della larghezza di banda per ogni Skype per applicazioni aziendali.
  
Determinare i requisiti in ogni LLC la legge evitare. i siti, si utilizzeranno [Lync 2010 e strumento di calcolo della larghezza di banda 2013](https://go.microsoft.com/fwlink/?LinkID=690282). Questo strumento di calcolo è uno strumento basato su Excel che consente di specificare l'utilizzo previsto del Skype diversi per le applicazioni aziendali incluse audio, video, conferenza e condivisione dello schermo. La calcolatrice genera automaticamente una stima della larghezza di banda e CoS requisiti per ogni sito all'interno della rete. Quando si scarica Lync 2010 e strumento di calcolo della larghezza di banda 2013, manuale dell'utente verrà inoltre scaricato che per ottenere informazioni dettagliate sull'utilizzo. 
  
Per facilitare il foglio di calcolo, le celle del foglio di calcolo vari sono a colori:
  
- **Verde** Queste sono le aree di immissione dati generali.
    
- **Giallo** Queste avanzate aree di input dei dati. È possibile modificare tali impostazioni, ma a questo scopo con attenzione.
    
- **Rosso** Queste sono le aree di sola lettura e sono valori di input bloccati e non può essere modificate.
    
- **Grigio** Queste sono le aree di sola visualizzazione. Sono i risultati o dati dalle aree inpue generale.
    
Il processo di progettazione per evitare il diritto LLC. inizia definendo agli utenti in diverse "persone". Per ogni utente tipo definite, è possibile specificare loro utilizzo previsto del Skype diversi per le applicazioni aziendali ("None", "Bassa", 'Medie', 'High' o uno dei tre impostazioni definite 'Custom'). Tali opzioni sono disponibili nel foglio di lavoro "Utente". Viene fornita l'utilizzo specifico per ogni scelta ("Bassa", "Media" o "Alta"), ma i valori predefiniti per ogni opzione possono essere modificati. Per identificare il numero di utenti per ogni persona che si trova in ogni sito, la calcolatrice può calcolare la larghezza di banda totale necessario per ogni località.
  
È inoltre possibile specificare l'audio e codec video utilizzati, se viene utilizzata la correzione degli errori di inoltro e anche altri parametri di sistema che incideranno i requisiti di larghezza di banda. È possibile utilizzare le impostazioni predefinite in Lync 2010 e strumento di calcolo della larghezza di banda 2013 o selezionare diversi codec e altri parametri del sistema. Per la progettazione del evitare legge LLC sito, è possono utilizzare le impostazioni predefinite. Tuttavia, per passare da uno del valore predefinito impostazioni vi è un menu a discesa contenente tutte le opzioni disponibili. Le larghezze di banda che vengono utilizzati per ciascuna scelta sono inclusi nel foglio di lavoro 'Codec'. Quando si modifica qualsiasi impostazione, modifica la larghezza di banda e la classe del servizio (CoS) combinazione in ogni sito viene aggiornato. Con questa funzionalità consente di configurazioni di test diverse possibili per essi e visualizzare l'impatto le modifiche sulla larghezza di banda per essi.
  
Tre persone abbiamo definito per Dewey Law LLC. ' Executive/Partner', ' Associa/Paralegal' e "Gli amministratori IT". Nella tabella seguente viene illustrato come è stata impostata i profili di dati di utilizzo per Skype diversi per le applicazioni di Business per ogni utente.
  
 **Persone e profili di utilizzo ("Utente" del foglio di lavoro - colonne da A P)**
  
|**Utente**|**Messaggistica Istantanea e presenza**|**P2P audio**|**Video P2P**|**Audio conferenze**|**Conferenze video**|**La condivisione del desktop**|**Audioconferenza**|**Lync 2010 RTV_Type**|**Utenti remoti**|**Audio stereo Lync 2013**|**Qualità video di Lync 2013**|**Comportamento degli utenti di Lync 2013 per P2P finestra video**|**Utilizzo di Lync 2013 MultiView**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Executive / Partner  <br/> |Elevata  <br/> |Medie dimensioni  <br/> |Bassa  <br/> |Medie dimensioni  <br/> |Medie dimensioni  <br/> |Nessuno  <br/> |Medie dimensioni  <br/> |CIF  <br/> |0%  <br/> |0%  <br/> |Procedure  <br/> |Tipico  <br/> |Tipico  <br/> |
|Associare / Paralegal  <br/> |Elevata  <br/> |Medie dimensioni  <br/> |Bassa  <br/> |Medie dimensioni  <br/> |Elevata  <br/> |Elevata  <br/> |Medie dimensioni  <br/> |CIF  <br/> |0%  <br/> |0%  <br/> |Medie dimensioni  <br/> |Tipico  <br/> |Tipico  <br/> |
|Amministratori IT  <br/> |Elevata  <br/> |Medie dimensioni  <br/> |Nessuno  <br/> |Bassa  <br/> |Nessuno  <br/> |Nessuno  <br/> |Medie dimensioni  <br/> |CIF  <br/> |0%  <br/> |0%  <br/> |Medie dimensioni  <br/> |Tipico  <br/> |Tipico  <br/> |
   
È necessario immettere le informazioni nella tabella di **distribuzione degli utenti da posizioni e le posizioni** di sopra del foglio di lavoro 'Siti' di Lync 2010 e strumento di calcolo della larghezza di banda 2013. Il numero di utenti negli uffici regionali è identico, sono definiti per un sito di' +' e specificati che non vi sono tre le relative istanze. La stessa operazione è stata eseguita per le filiali di grandi e piccole in cui si sono rispettivamente 24 e 50 utenti nei siti.
  
Dopo aver specificato le impostazioni per ogni utente, è necessario immettere il numero di utenti in ogni utente in ogni sito nel foglio di lavoro 'Siti'. Totale utenti per tutti i siti viene aggiornato automaticamente. Poiché non vi sono utenti in corrispondenza della posizione di Office 365, devono tutti essere immessi nelle righe "Rami" del foglio di lavoro. Lync 2010 e strumento di calcolo della larghezza di banda 2013 popola la 'Classe sforzo maggiore', 'Dati traffico classe' e 'il traffico in tempo reale classe' colonne nella tabella 'BW WAN per ogni classe di traffico QoS'. Come illustrato nei dati nella tabella seguente.
  
> [!TIP]
>  Foglio di calcolo completo include anche il numero massimo di sessioni simultanee per ogni applicazione, ma sono state eliminate le colonne per risparmiare spazio.
  
 **Persone dal sito - ('Siti' foglio di lavoro - colonne A, D, è possibile e AI tramite AX)**
  
|**Nome del sito**|**Totale utenti nel sito**|**Totali siti simile al seguente**|**Profili utente 1**|**Utente del profilo 1**|**Profili utente 2**|**Utente del profilo 2**|**Profili utente 3**|**Utente del profilo 3**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Headquarters  <br/> |1070  <br/> |1  <br/> |Executive/Partner  <br/> |170  <br/> |Associare/Paralegal  <br/> |700  <br/> |Amministratori IT  <br/> |200  <br/> |
|Uffici  <br/> |345  <br/> |3  <br/> |Executive/Partner  <br/> |60  <br/> |Associare/Paralegal  <br/> |225  <br/> |Amministratore IT  <br/> |60  <br/> |
|Filiali di grandi dimensioni  <br/> |70  <br/> |24  <br/> |Executive/Partner  <br/> |11  <br/> |Associare/Paralegal  <br/> |50  <br/> |Amministratore IT  <br/> |9  <br/> |
|Succursali  <br/> |36  <br/> |50  <br/> |Executive/Partner  <br/> |6  <br/> |Associare/Paralegal  <br/> |25  <br/> |Amministratore IT  <br/> |1  <br/> |
   
 **Larghezza di banda necessaria per ogni applicazione dal sito in Kbps ('Siti foglio di lavoro'-colonne A e BQ tramite LF)**
  
|**Sito**|**Picco SIP / della larghezza di banda di messaggistica immediata**|**Larghezza di banda di picco tra siti Peer Audio**|**Larghezza di banda tra siti Peer Video massima**|**Larghezza di banda di picco audioconferenze**|**Larghezza di banda di picco conferenze Video**|**Larghezza di banda di picco condivisione WAN**|**Larghezza di banda WAN massima per le chiamate PSTN**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Headquarters  <br/> |1070  <br/> |525.30  <br/> |560.00  <br/> |739.50  <br/> |2640.00  <br/> |4224.00  <br/> |2688.30  <br/> |
|Uffici  <br/> |345  <br/> |185.40  <br/> |560.00  <br/> |255.00  <br/> |1320.00  <br/> |1536.00  <br/> |896.10  <br/> |
|Rami di grandi dimensioni  <br/> |70  <br/> |92.70  <br/> |560.00  <br/> |102.00  <br/> |600,00  <br/> |384.00  <br/> |216.30  <br/> |
|Filiali di piccole dimensioni  <br/> |36  <br/> |119.40  <br/> |560.00  <br/> |76.50  <br/> |600,00  <br/> |384.00  <br/> |123.60  <br/> |
   
Probabilmente più importanti colonne del foglio di calcolo sono quelli che descrivono la larghezza di banda WAN dalla classe QoS. Come illustrato nella tabella seguente. Questi dati vengono riepilogate le informazioni che necessarie per fornire al provider di servizi di rete per ordinare la connessione di accesso a singoli siti. Durante il calcolo della larghezza di banda totale, ricordare moltiplicare la larghezza di banda per ogni tipo di siti di succursale per il numero di siti dello stesso tipo. Per la connessione con i partner di servizi di rete ExpressRoute, è possibile visualizzare [ExpressRoute Azure]( https://go.microsoft.com/fwlink/?LinkId=690283).
  
È molto importante che non superano la larghezza di banda nella vocale o 'Expedited inoltro' (EF) classe di servizio. Un insieme casuale di pacchetti verrà eliminato in modo anziché riducendo la qualità di una singola chiamata o un gruppo di chiamate, tutte le chiamate in corso può essere influenzate. È inoltre importante che solo VoIP contrassegnato con il DSCP per EF (vale a dire il contrassegno DSCP = 46) o la coda voice potrebbe verificarsi un overflow quando del traffico vocale non viene aggiunto.
  
> [!TIP]
>  Nuovamente, mentre la classe EF del servizio offre la garanzia prestazioni migliore, se si supera la larghezza di banda definito, tutti i pacchetti aggiuntivi immediatamente essere eliminati.
  
 **Aggregata della larghezza di banda per ogni sito dalla classe di traffico QoS - ('Siti' foglio di lavoro - colonne A e ML tramite MR)**
  
|**Nome del sito**|**Classe sforzo maggiore (DSCP 0)**|**Classe di traffico di dati (DSCP personalizzato)**|**Classe di traffico in tempo reale (34 il contrassegno DSCP, AF41)**|**Classe di traffico priorità (46 il contrassegno DSCP, EF)**|
|:-----|:-----|:-----|:-----|:-----|
|Headquarters  <br/> |0,00  <br/> |5764.80  <br/> |3200.00  <br/> |3953.10  <br/> |
|Uffici  <br/> |0,00  <br/> |2033.60  <br/> |1880.00  <br/> |1336.50  <br/> |
|Rami di grandi dimensioni  <br/> |0,00  <br/> |486.40  <br/> |1160.00  <br/> |411.00  <br/> |
|Filiali di piccole dimensioni  <br/> |0,00  <br/> |438.40  <br/> |1160.00  <br/> |319.50  <br/> |
   
### <a name="putting-your-plan-into-action"></a>Inserire il piano in azione

È possibile calcolare la larghezza di banda totale attraversato WAN e la quantità di larghezza di banda attraversato ExpressRoute, utilizzando la larghezza di banda stime **per ogni applicazione per ogni sito** nella tabella precedente. La parte del traffico che attraversa ExpressRoute esclude la larghezza di banda tra siti peer.

 
|**Sito**|**Picco SIP / della larghezza di banda di messaggistica immediata**|**Larghezza di banda di picco audioconferenze**|**Larghezza di banda di picco conferenze Video**|**Larghezza di banda di picco condivisione WAN**|**Larghezza di banda WAN massima per le chiamate PSTN**|**Totale ExpressRoute<br/>il traffico per ogni classe di sito<br/>(ad esempio, in totale<br/>ora # dei siti)**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Headquarters** <br/> |1,070  <br/> |739.50  <br/> |2640.00  <br/> |4224.00  <br/> |2688.30  <br/> |11361.80  <br/> |
|**Uffici** <br/> |345  <br/> |255.00  <br/> |1320.00  <br/> |1536.00  <br/> |896.10  <br/> |8704.20  <br/> |
|**Rami di grandi dimensioni** <br/> |70  <br/> |102.00  <br/> |600,00  <br/> |384.00  <br/> |216.30  <br/> |32935.20  <br/> |
|**Filiali di piccole dimensioni** <br/> |36  <br/> |76.50  <br/> |600,00  <br/> |384.00  <br/> |123.60  <br/> |61005.00  <br/> |
   
Ciò significa che Skype per il traffico in linea aziendale che attraversato route express sarà circa 114 Mbps, in modo evitare, sarà necessario almeno 200 sottoscrizione Mbps per ExpressRoute. Più circuiti ExpressRoute possono essere acquistati dislocati ExpressRoute peering. Potrebbe essere consigliabile per siti di evitare in aree geografiche diverse o per garantire la resilienza nel caso in cui la connessione a commutazione di circuito ExpressRoute non riesce. Se si acquistano circuiti ExpressRoute in più aree di Azure, il componente aggiuntivo premium ExpressRoute deve ricevere connettività globale su ExpressRoute.
  
Dopo aver creato la quantità totale di larghezza di banda necessaria e classe di servizio (CoS) numeri della larghezza di banda è possibile inserire gli ordini con la rete selezionata uno o più provider di servizi. Non dimenticare di includere le stime per il traffico per altri servizi e applicazioni. Offriamo rete istruzioni per altri servizi di Office 365, tra cui calcolatori di larghezza di banda per Exchange e OneDrive per la pianificazione. Sottoscrizione di larghezza di banda per il provider di servizi di rete è superiore perché il traffico all'interno del sito, sarà necessario per l'aggiunta di nuovo. Lync 2010 e strumento di calcolo della larghezza di banda 2013 fornisce solo una stima del traffico previsto, si consiglia di confermare la capacità di rete per supportare il volume di traffico si esegue un test di stress. 
  
> [!TIP]
> La rete di test di stress è vivamente consigliato quando si esegue una valutazione iniziale di rete. 
  
Un test di stress prevede la creazione e configurazione dell'infrastruttura e quindi eseguirlo con il numero previsto di traffico simulato durante il monitoraggio delle prestazioni. Una stima il traffico potrebbe non essere precisi in alcuni settori, ma almeno avere la certezza che può supportare il volume del traffico Lync 2010 e strumento di calcolo della larghezza di banda 2013 previsti. È consigliabile che si esegue il test di stress per un periodo minimo di pochi giorni, ma esegue per periodi di tempo più consentono di ottimizzare i numeri. Tuttavia, estendere il periodo del test di stress necessario valutare i con i costi dei servizi di rete si paga che non sono trasporto di traffico di rete utente reale. Microsoft ha certificato numerosi fornitori come parte del programma di strumenti di professionisti IT per fornire strumenti di gestione e operazioni di rete tra gli strumenti di valutazione preliminare stress di rete. Skype per le aziende include inoltre un sistema integratori (SI) che può richiedere certificati IT Pro Tools e che può eseguire la valutazione della rete automaticamente. È possibile visualizzare ulteriori [Skype per soluzioni aziendali: IT Pro Tools](https://go.microsoft.com/fwlink/?LinkID=690307).
  
Test di stress fornisce certezza che la rete può supportare il volume di traffico che sarà necessari, ma in realtà Lync 2010 e 2013 dati calcolo della larghezza di banda possono essere disattivata per vari motivi. È inoltre consigliabile continuare monitorare le reti siti eseguendo una valutazione della rete in corso una volta che viene distribuita per verificare che la larghezza di banda è sufficiente e che i meccanismi di QoS funzionino correttamente. È importante continuare il monitoraggio delle prestazioni della rete come utenti più reali vengono introdotti in linea.
  
## <a name="part-2-expressroute-skype-for-business-qos"></a>Parte 2: ExpressRoute Skype per QoS Business

ExpressRoute il servizio fornisce una connessione al cloud Azure dedicata, ma servizi di comunicazione degli Office 365 in tempo reale dei carichi di lavoro richiederanno servizi di rete con larghezza di banda sufficiente per eseguire il volume del traffico e sono in grado di supportare Esperienza di qualità del servizio (QoS) per fornire un utente di livello aziendale. Un QoS grado connessione deve essere configurata end-to-end (PC, switch di rete e router nel cloud) come qualsiasi parte del percorso che si verifica un errore per il supporto QoS peggiorare la qualità della chiamata intero.
  
Lo scopo di questa sezione è utili per comprendere le problematiche quando il traffico in tempo reale in una rete IP e configurazione di supporto e una corretta distribuzione di Office 365 in tempo reale dei carichi di lavoro utilizzando ExpressRoute Exchange di Microsoft ExpressRoute Partner provider o Provider di servizi di rete.
  
QoS viene accettata da reti esclusivamente su circuiti rete ExpressRoute e viene utilizzata all'interno della rete Microsoft Skype per il traffico di Business. Parti di alcune connessioni in uscita da Microsoft oggi sono valori DSCP mancanti per Skype per le aziende. Fino a quando il traffico in uscita completamente è contrassegnato con valori DSCP, vengono fornite informazioni utili per seguire le linee guida per l'aggiunta di contrassegni QoS per il traffico in corrispondenza del limite rete come descritto nella sezione **QoS implementazione utilizzando l'elenco di controllo accesso (ACL) di rete** dell'oggetto articolo.
  
### <a name="the-real-time-problem"></a>Problema in tempo reale

Fornitura dei servizi vocali e video di qualità business effettua le richieste speciali in una rete IP. Il traffico in tempo reale utilizza Real-time Transport Protocol (RTP), viene eseguita tramite protocollo UDP (User Datagram). A differenza di protocollo TCP (Transmission Control) in cui i numeri e verificato ogni messaggio di errori, nonché altri meccanismi per rilevare e ritrasmettere perduti o errore relativo ai messaggi, UDP non fornisce l'affidabilità questo tipo. Se i messaggi vengono danneggiati dall'errori o vengono persi a causa di overflow del buffer, queste vengono eliminate. UDP è stato scelto per l'utilizzo con RTP perché la natura del traffico in tempo reale anche se sono stati inviati messaggi persi, in cui verrebbe arrivano troppo ritardo per ha effetto positivo per il flusso del messaggio vocale.
  
Si conosce l'impatto dei pacchetti vocali persi, i progettisti emerse con due approcci per migliorare le prestazioni di audio e video IP:
  
- Effettuare la voce di codifica/decodifica più resiliente quando i pacchetti vanno persi. Questa operazione può essere eseguita da uno con correzione degli errori di inoltro (FEC) per correggere una percentuale di errori riscontrati è una funzionalità disponibili in Office 365 in tempo reale trasporto o da Progettazione voice decodifica sistemi che tentano di nascondere gli effetti della perdita di pacchetti che è una caratteristica di codec Microsoft. 
    
- Utilizzare i servizi di trasporto che utilizzano qualità dei meccanismi di servizio per garantire prestazioni di rete rispetto al sistema ritardo, la perdita di pacchetti e instabilità e la variante in ritardo tra i pacchetti.
    
Scrittura di codice voice resiliente solo risolve il problema della perdita di pacchetti, pertanto è importante che una rete utilizzati per eseguire in tempo reale vocali e video sono meccanismi di ridurre al minimo il ritardo e l'instabilità. Anche con la codifica resiliente, in caso di perdita, troppi pacchetti station ricevente non disporrà di informazioni sufficienti per ricostruire una versione riconoscibile del segnale vocale. Percentuale di perdita di pacchetti che potrebbe causare un peggioramento significativo della qualità vocale che varia a seconda della voce tecnica che viene utilizzata la codifica. In tutti i casi, tuttavia, la perdita dei pacchetti successivi stringhe è molto problematica.
  
Ridurre al minimo ritardo è importante in quanto eccessive può influire il flusso della conversazione e creare un fastidio per gli altoparlanti. Procedure consigliate comunicano che ritardo end-to-end di Enterprise voice (che cos'è fare riferimento a come ritardo 'afta-auricolari') deve essere conservato di sotto di 150 millisecondi (msec). ritardo di non 'round trip' unidirezionale. Ovviamente il ritardo aumenterà su più collegamenti di trasmissione analoghi a quelli che attraversano i oceani, dato il tempo che necessario per il segnale di viaggiare fisicamente via cavo o il ritardo di propagazione.
  
Quando il ritardo passa maggiore di 150 millisecondi. unidirezionale, ha un effetto strano dell'altoparlante. Psychologically, un orologio scompare in cervello del relatore che li rende ritiene che il destinatario non ha ascoltare li e ripetono l'ultima operazione che hanno risposto. Si è in conflitto con la risposta ritardata provenienti da estremità di destinazione. Se sarà mai letto attraverso un canale satellitari riconoscibile effetto. Attraverso un canale satellitari ritardo unidirezionale è approssimativamente 250 msec., ovvero oltrepassare il tempo massimo consentito.
  
 **Parametri di rete consigliato per VoIP di livello aziendale**
  
|**Parametro**|**Valore consigliato**|
|:-----|:-----|
|Tra le instabilità pacchetti in arrivo (Media)  <br/> |≤ 5 MS DA  <br/> |
|Tra le instabilità pacchetti in arrivo (al massimo)  <br/> |≤ 40MS  <br/> |
|Frequenza di perdita di pacchetti (Media)  <br/> |0% raggiungendo  <br/> |
|Un modo latenza di rete  <br/> |≤ 100 ms (deve includere controlli in ritardo rispetto alla distanza geografica)  <br/> |
   
### <a name="expressroute-as-part-of-a-business-grade-voice-network"></a>ExpressRoute come parte di una rete vocale di livello aziendale

ExpressRoute offre una connessione dedicata tramite un Provider di servizi di rete (NSP) o un Provider di Exchange (EXP) in una delle opzioni di connessione di 3: 
  
- Installazione di Exchange cloud
    
- Tipo di connessione Ethernet
    
- Tutti a qualsiasi connessione (IPVPN)
    
In tal modo vantaggi della disponibilità elevata (SLA uptime 99,9%) e la protezione di routing affidabile vale a dire (nessun transito internet) non modifica le varianti in traffico Internet e gli aspetti indicazioni di qualità del servizio per definire le priorità traffico (QoS vengono illustrati di seguito) . ExpressRoute, insieme a una rete WAN pianificate può fornire una rete vocale di livello aziendale.
  
È possibile utilizzare ExpressRoute per la trasmissione di dati da uffici o Datacenter (se topologia ibrida) connessi al circuito. Dati per gli utenti fuori sede (ad esempio, da casa, o in viaggio e così via) non sfruttano a commutazione di circuito ExpressRoute solo se gli utenti siano connessi VPN e non devono essere incluse nel stime di larghezza di banda per il ridimensionamento a commutazione di circuito ExpressRoute. Se sei un cliente multinazionale, è possibile acquistare circuiti ExpressRoute in ogni area e utilizzare BGP community tag per informare le regole di routing in modo che il traffico diretto a preferito ExpressRoute circuito (in genere quello più vicino per ogni sito), mentre l'altra circuiti offrono ridondanza in caso di interruzione incidere sull'elenco in un singolo a commutazione di circuito. 
  
### <a name="if-expressroute-isnt-an-option"></a>Se non è un'opzione ExpressRoute

Potrebbe non essere realizzabile a cui connettersi tutti i siti ExpressRoute uno a causa dei costi, impossibilità per soddisfare i prerequisiti ExpressRoute o limitazioni del NSP corrente. Se si che non possono utilizzare ExpressRoute sono comunque consigliato per seguire le istruzioni di sotto di contrassegno QoS all'interno della rete e pianificare i contratti con il NSP per garantire la larghezza di banda e supporto per la definizione delle priorità traffico basato su QoS sufficienti.
  
Inoltre, se si dispongono di uffici in più aree, ma non dispongono di circuiti ExpressRoute in tutte le regioni devono utilizzare i tag di community BGP area durante la configurazione di routing per il traffico in una filiale remota in modo che è possibile evitare transito distanza long non necessarie. Si consideri ad esempio una società con Skype per le organizzazioni aziendali Online ospitate negli Stati Uniti, ma con succursali in Europa e l'azienda dispone solo di un singolo ExpressRoute a commutazione di circuito in silicio valle. La maggior parte del Skype per il traffico Business Online verrà instradato a un centro dati di cui è ospitato l'organizzazione (ad esempio, conferenze telefoniche con altri utenti all'interno della società), utilizzando a commutazione di circuito ExpressRoute potrebbe essere preferito per la maggior parte del traffico. Tuttavia, se un utente in Europa per partecipare a una conferenza telefonica ospitata da un'altra società in cui organizzazione si trova in Europa, la destinazione per i supporti di chiamata è datacenter European seconda società in cui si trova. Routing del traffico attraverso il ExpressRoute a commutazione di circuito in silicio valle è una route meno diretta rispetto tramite Internet. In tal caso, è possibile configurare i router all'interno della rete (ad esempio in uffici europei) per analizzare i tag di community in cui effettuare il routing regole e il routing tramite Internet anziché valle silicio ExpressRoute circuito per il traffico con Tag area Comunità.
  
### <a name="basic-concepts-of-quality-of-service-qosclass-of-service-cos"></a>Concetti di base della qualità del servizio (QoS) / classe di servizio (CoS)

In IP, qualità del servizio (QoS) viene descritto un meccanismo che consente di assegnare priorità gestione per alcuni pacchetti rispetto ad altri. In base alla definizione International Telecommunications Union (ITU), QoS comprende tutti gli aspetti di qualità di una connessione inclusi ritardo, la perdita, rapporto segnale-rumore, crosstalk, eco, interrupt, risposta di frequenza, livelli sonorità e così via. Che cos'è fare riferimento a QoS nelle reti di pacchetti è più correttamente denominata classe di servizio (CoS) che è destinata a migliorare le prestazioni di ritardo, dall'instabilità e perdita di pacchetti, ma continua a utilizzare il termine QoS più comunemente utilizzate.
  
Fornitura di QoS in un indirizzo IP rete chiama i due componenti principali:
  
- La prenotazione di una quantità di larghezza di banda sui collegamenti per il traffico in tempo reale. Se non è necessario che la larghezza di banda per il traffico in tempo reale in qualsiasi momento, può essere utilizzato per il traffico. Le indicazioni generali sono che devono essere assegnati non più di 30% della capacità di qualsiasi collegamento per il traffico vocale.
    
- Contrassegno dei pacchetti con un indicatore di priorità nell'intestazione che indica le opzioni e i router nel percorso la priorità del pacchetto che deve essere assegnato.
    
Quando si riceve un pacchetto in uno switch o router, viene spostato a una coda di output per il segmento successivo o hop. Sono disponibili le code di output diverso per i diversi livelli di priorità. Uno switch o router usa un algoritmo che fornisce servizi di coda ad alta priorità maggiore frequenza rispetto le code di priorità inferiore.
  
La richiesta è che sono disponibili diverse tecniche QoS implementate al livello 2 (vale a dire il livello di una scheda Ethernet o Wi-Fi) e livello 3 (vale a dire il livello IP). Tali implementazioni diverse QoS potrebbero essere necessario configurare in ogni opzione e il router della rete, nonché l'interfaccia tra la rete e di rete del provider di servizi di rete.
  
Sono disponibili due opzioni per come dati da diverse Skype per le applicazioni aziendali possono essere associati alle classi appropriate del servizio:
  
- Contrassegno punto finale del traffico utilizzando controllo scegliere DSCP (Differentiated Services) 
    
- Elenco di controllo di accesso (ACL) di rete-base
    
### <a name="end-point-traffic-marking--differentiated-services-control-point-dscp"></a>Punto finale del traffico contrassegno - Differentiated Services controllo Point (DSCP)

Servizi differenziati (DiffServ) è denominato "meno importanti" meccanismo per la classificazione e la gestione del traffico di rete e fornire QoS nelle reti IP. Router e ad altri dispositivi che implementano funzioni di livello 3 utilizzano DiffServ controllo Point (DSCP) per definire la priorità del pacchetto. QoS viene implementato inserendo un valore DSCP a 6 bit nel campo servizi differenziati (noto in precedenza il campo "Type of Service") nell'intestazione IP. 6 bit consente di 64 diversi livelli di priorità. I livelli di priorità in genere vengono definiti come indicato di seguito.
  
 **Impostazioni consigliate DSCP**
  
|**Classe di traffico**|**Trattamento (il contrassegno DSCP)**|**Skype per carichi di lavoro Business**|
|:-----|:-----|:-----|
|**VoIP** <br/> |EF (46)  <br/> |Skype per VoIP aziendale e Lync  <br/> |
|**Interactive** <br/> |AF41 (34)  <br/> |Video  <br/> |
||AF21 (18)  <br/> |Condivisione applicazioni  <br/> |
|**Impostazione predefinita** <br/> |AF11 (10)  <br/> |Trasferimento di file  <br/> |
||CS0 (0)  <br/> |Qualsiasi altra cosa  <br/> |
   
 **Intestazione IP versione 4**
  
![Intestazione IPv4](../images/c8a6a714-2784-4328-8297-2e62706f302d.png)
  
### <a name="layer-2-qos-ieee-8021pwi-fi-multi-media-ieee-80211e"></a>QoS di livello 2: IEEE 802.1 p/Wi-Fi Multimedia (IEEE 802.11 e)

Mentre il contrassegno DSCP è il meccanismo standard per l'implementazione di QoS al livello 3, sono disponibili diversi meccanismi di livello 2 QoS per cablata (vale a dire Ethernet) e wireless (vale a dire reti Wi-Fi). Il meccanismo di QoS per le reti cablate è definito in standard IEEE 802.1p; il meccanismo di QoS WLAN è definito in IEEE 802.11, e cosa Wi-Fi Alliance identifica come "Certificati Wi-Fi Multimedia" (WMM certificato).
  
IEEE 802.1p utilizza un punto di codice priorità bit 3 (PCP) per identificare la priorità del messaggio. la PCP fa parte di un campo a 32 bit nell'intestazione Ethernet che esegue inoltre l'identificatore VLAN. Di seguito sono riportate le definizioni per i valori PCP.
  
 **Valori di IEEE 802.1p PCP**
  
|**Valore PCP**|**Priorità**|**Acronimo**|**Tipi di traffico**|
|:-----|:-----|:-----|:-----|
|7  <br/> |7  <br/> |CONTESTO DEI NOMI  <br/> |Controllo di rete  <br/> |
|6  <br/> |6  <br/> |IC  <br/> |Controllo del sistema di reti  <br/> |
|5  <br/> |5  <br/> |ARMENO  <br/> |VoIP  <br/> |
|4  <br/> |4  <br/> |VI  <br/> |Video  <br/> |
|3  <br/> |3  <br/> |AUTORITÀ DI CERTIFICAZIONE  <br/> |Applicazioni più importanti  <br/> |
|2  <br/> |2  <br/> |EE  <br/> |Impegno eccellente  <br/> |
|0  <br/> |1  <br/> |ESSERE  <br/> |Massimo sforzo  <br/> |
|1  <br/> |0  <br/> |BK  <br/> |Sfondo  <br/> |
   
Dove IEEE 802.1p è implementato in modo come il contrassegno DSCP con traffico ordinati nelle code priorità diverse per ogni livello di priorità, ma la natura condivisa media delle chiamate di questo tipo di rete per un approccio diverso. Mentre il punto di accesso e il client mantiene le code di output separati per i diversi livelli di priorità, vi sono inoltre differenze nelle modalità fotogrammi vengono inviati sul canale radio.
  
In una rete Wi-Fi, tutti i client associati a un punto di accesso condividono un canale singolo e half-duplex (vale a dire un solo client station o il punto di accesso può inviare contemporaneamente). Per ridurre al minimo la possibilità di collisioni sul canale radio, prima di inviare una cornice che la station attende il canale di essere inattivo per un periodo di tempo definito un "spaziatura inter-Frame," se il canale è occupato quando si passa da una workstation di inviare, per il ripristino disattivata peri un tempo casuale od. Dopo la cornice viene inviata, se il mittente non riceve un messaggio di conferma del destinatario, si presuppone un conflitto o si è verificato un errore e viene eseguita nuovamente intervalli casuali prima di tentare di accedere a canale radio per inviare di nuovo. L'intervallo di interruzione temporanea è casuale per ridurre la probabilità che stesse due stazioni caratteristica è in conflitto nuovamente.
  
Per impostare la priorità di accesso per l'opzione di canale, IEEE 802.11 e / WMM definisce intervalli diversi in attesa di pre-trasmissione denominati "Arbitrated inter-Frame spaziature avanzamento" (AFIS) e intervalli di interruzione temporanea diversi per le classi di traffico diversi, sono definiti quattro livelli di priorità denominati 'Accesso categorie'.
  
Prioritaria assegnando brevi AFIS valori per i frame priorità superiori. Così se uno station è in attesa di inviare una cornice VoIP e un altro in attesa di invio di una cornice di dati, la cornice voice verrà sempre inviata prima. Tecnicamente, audio e video con frame vengono assegnati lo stesso valore AFIS, ma l'intervallo di interruzione temporanea intervalli per i frame video è superiore. In modo mentre il primo tentativo potrebbe sono in conflitto una voce e video frame, la cornice voice verrà sempre trasmesso più rapidamente. La correlazione tra IEEE 802.1p e IEEE 802.11 e viene illustrata di seguito:
  
 **IEEE 802.11 e / Wi-Fi Multimedia (WMM) per lo standard 802.1 P mapping**
  
|**Categoria di accesso WMM**|**Descrizione WMM**|**Valore 802.1P PCP**|**Designazione 802.1P**|
|:-----|:-----|:-----|:-----|
|1 (AC_VO)  <br/> |VoIP  <br/> |7 (111)  <br/> |CONTESTO DEI NOMI  <br/> |
|6 (110)  <br/> |ARMENO  <br/> |
|2 (AC_VI)  <br/> |Video  <br/> |5 (101)  <br/> |VI  <br/> |
|4 (100)  <br/> |CL  <br/> |
|3 (AC_BE)  <br/> |Dati sforzo maggiore  <br/> |3 (011)  <br/> |EE  <br/> |
|0 (000)  <br/> |ESSERE  <br/> |
|4 (AC_BK)  <br/> |Dati di base  <br/> |1 (001)  <br/> |BK  <br/> |
|2 (010)  <br/> |---  <br/> |
   
L'associazione consigliato di livello 3 alle priorità di livello 2 è illustrata di seguito:
  
 **Livello 3 è consigliabile associazioni priorità livello 2**
  
||**Indicazioni di livello 3**|**Livello 2 (PCP valore)**|**Wi-Fi (accesso categoria)**|
|:-----|:-----|:-----|:-----|
|Controllo di rete  <br/> |Per ogni comportamento Hop (PHB) - selettore di classe (CS) 6  <br/> |6  <br/> |1 (AC_VO)  <br/> |
|Valore DSCP-48  <br/> |
|VoIP  <br/> |Per ogni comportamento Hop (PHB)-Expedited inoltro (EF)  <br/> |5  <br/> |1 (AC_VO)  <br/> |
|Valore DSCP - 46  <br/> |
|Servizi di videoconferenza  <br/> |Per ogni comportamento Hop (PHB) - Assured inoltro (AF) 41  <br/> |4  <br/> |2 (AC_VI)  <br/> |
|Valore DSCP - 34  <br/> |
|Segnalazione delle chiamate  <br/> |Per ogni comportamento Hop (PHB) - selettore di classe (CS) 3  <br/> |3  <br/> |2 (AC_VI)  <br/> |
|Valore DSCP - 24  <br/> |
|Dati a bassa latenza  <br/> |Per ogni comportamento Hop (PHB)-Assured inoltro (AF) 21  <br/> |2  <br/> |3 (AC_BE)  <br/> |
|Valore DSCP -18  <br/> |
|Alta velocità effettiva  <br/> |Per ogni comportamento Hop (PHB) - Assured inoltro (AF) 11  <br/> |1  <br/> |3 (AC_BE)  <br/> |
|Valore DSCP - 10  <br/> |
|Massimo sforzo  <br/> |Per ogni comportamento Hop (PHB) - 0  <br/> |0  <br/> |4 (AC_BK)  <br/> |
|Valore DSCP - 0  <br/> |
   
È importante notare che vi sia una mancata corrispondenza nella priorità di codifica per IEEE 802.1p e WMM. Protocollo 802.1p PCP il valore di Enterprise voice è 5, tuttavia, nel mapping di equivalenza standard a WMM PCP 5 viene convertito in Access categoria 2, la categoria di accesso WMM per il video (AC_VI). Se possibile deve ignorare tale mapping in modo che PCP 5 viene convertita in Access categoria 1 o semplicemente evitare l'utilizzo di audio e video della stessa rete Wi-Fi fino a quando non Wi-Fi Alliance consente di risolvere il problema. Per ulteriori informazioni su Wi-Fi, vedere [Gli elementi del catalogo Wi-Fi]( https://go.microsoft.com/fwlink/?LinkId=690322).
  
### <a name="implementing-qos-using-network-access-control-list-acl"></a>L'implementazione di QoS utilizzando l'elenco di controllo accesso (ACL) di rete

Il metodo alternativo per l'implementazione di QoS in una configurazione ExpressRoute consiste nell'utilizzare l'elenco di controllo accesso (ACL) di rete. In quanto approccio, anziché i punti finali inserisce il contrassegno DSCP appropriato nell'intestazione di ogni pacchetto, il contrassegno può essere eseguito tramite un router monte, basato su porta di origine UDP. Tutti i commutatori e router ancora deve essere configurati per supportare QoS per mantenere le impostazioni di DSCP. Più importante, il router connesso alla rete del provider di servizi deve mantenere il contrassegno DSCP nell'intestazione di ogni pacchetto, come tale impostazione DSCP essenzialmente le istruzioni per il provider di servizi di rete per la modalità di pacchetti devono essere considerato.
  
Gli intervalli di porte consigliato per ogni Skype per applicazioni aziendali sono elencati nella sezione 2.6.1.1 della Guida alla [Pianificazione della rete, monitoraggio e risoluzione dei problemi con Lync Server](https://go.microsoft.com/fwlink/?LinkId=690286) . È importante che questo essere coordinati con approccio globale dell'organizzazione per QoS e deve prestare attenzione per diversi criteri QoS e potenziali pacchetti della nota le incongruenze di.
  
Mentre il motivo principale vengono utilizzati QoS e MPLS servizi di rete per garantire un'esperienza utente ottimale per in tempo reale audio e video, è inoltre possibile applicare a tali funzionalità stessa alle applicazioni di dati. Invece di considerare ugualmente tutte le applicazioni, reti MPLS possono consentire alle organizzazioni di dare priorità al alcune applicazioni di dati rispetto ad altri. Con MPLS, applicazioni in tempo reale, ad esempio le transazioni di carta di credito o condivisione dello schermo è possibile assegnare priorità su meno traffico riservati ora come messaggio di posta elettronica.
  
### <a name="understanding-the-types-of-ip-network-services--basic-ip-and-mpls"></a>Informazioni sui tipi di IP rete servizi di base IP e MPLS

L'inoltro dei pacchetti IP originale utilizzati in base al principio dei "massimo sforzo". Ciò significa che i router inoltro i pacchetti IP eseguire le procedure per soddisfare tali alle relative destinazioni, ma si è non verificato assolutamente alcuna garanzia in relazione alla quando oppure se arrivano contemporaneamente le rispettive destinazioni. È come base servizi Internet, tra cui la connessione a Internet, lavoro oggi home page. L'idea che se l'affidabilità è obbligatorio per una determinata applicazione, potrebbe essere fornito un livello superiore nello stack di protocolli. Il meccanismo di recapito affidabile è il protocollo TCP (Transmission Control). Il protocollo UDP (User Datagram), che viene utilizzato per in tempo reale audio e video, è il recapito inaffidabile (ad esempio "ottimo sforzo") meccanismo. 
  
Passaggio etichetta Multi-Protocol (MPLS) sviluppato come mezzo per provider di servizi di rete offrono un indirizzo IP del servizio con prestazioni garanzie per ritardo, instabilità e perdita di pacchetti. Per la consegna in tali garanzie prestazioni, MPLS accetta alcuni dei potenziali da IP tradizionale. Per prima cosa, anziché con ogni pacchetto di acquisire informazioni to router alla destinazione (il risultato delle quali può essere che ogni pacchetto accetta una route diversa dall'origine alla destinazione), MPLS instrada tutti i pacchetti di una connessione "circuito virtuale" con un route fissi definita un'etichetta a commutazione di percorso (Layered Service Provider). Se uno dei collegamenti in tale percorso non riesce, vengono reindirizzati rapidamente tutti LSP utilizzando tale collegamento.
  
Quando viene inviato alla rete MPLS router edge del provider di servizi di rete aggiunge un'intestazione aggiuntiva per il pacchetto che include un'etichetta che viene utilizzata per inoltrare su LSP appropriato. L'etichetta viene rimossa dal router edge alla fine della rete MPLS.
  
Accanto a semplificare il processo di inoltro, l'altro vantaggio che MPLS fornisce è che il sistema di gestione di rete verrà conoscere le connessioni a cui si effettuano su ogni collegamento nella rete. Per controllare il modo in cui viene eseguito il routing traffico attraverso la rete, l'operatore può garantire QoS fornirà ogni percorso. Così a differenza di ottenere prestazioni ottimali sforzo dell'indirizzo IP tradizionale o di base, operatori MPLS possono fornire un servizio IP prestazioni prevedibile. LSP che rende implicitamente MPLS maggiore protezione rispetto a tradizionali servizi Internet. Pertanto con servizi di base IP è possibile una sorpresa che la rete verrà eseguiti anche sufficiente fornire una buona qualità telefonica e utilizzare le tecniche come FEC e ulteriori voice resiliente la scrittura di codice per migliorare la probabilità, ma con MPLS, possiamo essere certi di esso.
  
MPLS provider offrono diverse classe di sfumature di servizio che purtroppo vengono utilizzati termini diversi per identificare in modo sicuro. È necessario lavorare a stretto contatto con il provider per assicurarsi che compreso l'output da [Lync 2010 e strumento di calcolo della larghezza di banda 2013](https://go.microsoft.com/fwlink/?LinkID=690282) e le opzioni consigliate per diverse applicazioni dei carichi di lavoro di Office 365 in tempo reale.
  
## <a name="conclusion"></a>Conclusione

Skype per le aziende consente di migliorare il modo in cui vengono condotte comunicazioni aziendali. Anziché con un telefono collegato a un PBX, un sistema autonomo di videoconferenza, una piattaforma separata per la posta elettronica, un servizio esterno per le conferenze audio e alcuni veicolo per messaggistica immediata e presenza, Skype per le aziende può riunire tutte queste funzionalità in un'unica interfaccia utente.
  
Ottimizzazione in modo coerente servizi video e vocali in tempo reale di livello aziendale richiede un'infrastruttura di rete end-to-end che è in grado di fornire QoS. Che potrebbe includere sia LAN e i servizi WAN. Microsoft offre alcuni strumenti come il [calcolo della larghezza di banda 2013 e Lync 2010](https://go.microsoft.com/fwlink/?LinkID=690282) per calcolare la capacità di rete che è necessario per i diversi servizi. Esistono inoltre partner nel programma di IT Pro Tools [Skype per soluzioni aziendali: IT Pro Tools](https://go.microsoft.com/fwlink/?LinkID=690307) che sono disponibili gli strumenti di pre-valutare l'infrastruttura di rete e supportare monitoring, reporting e risoluzione dei problemi. Senza un'infrastruttura di rete di dimensioni e configurato correttamente, si corre il rischio di avere un Skype ExpressRoute di distribuzione aziendale che non soddisferà le aspettative dell'utente per la qualità e coerenza.
  
Strumenti aziendali efficaci devono essere eseguite in modo affidabile, costantemente e offrire un'esperienza utente che favorisce l'adozione di utente. Dal punto di vista della rete che si intende per avere un'infrastruttura di rete, locale e wide area fisso e mobile, che può consentire che si verifichi. Pianificazione, progettazione, l'implementazione e manutenzione di tale infrastruttura non è sempre un semplice feat. Hardware, strumenti e servizi di rete per eseguire questa operazione oggi sono disponibili, ma è responsabilità per professionisti IT per verificare che siano progettati, implementare e gestiti in modo da garantire che gli utenti ricevono un set di servizi di collaborazione e le comunicazioni consentire loro di lavorare in modo efficiente ed efficace e che l'organizzazione può trarre il massimo vantaggio dalle quali questa tecnologia disponibili in. 
  
## <a name="related-topics"></a>Argomenti correlati

[Documentazione ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690285)

