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
f1keywords: None
ms.custom:
- Optimization
description: "Informazioni sull'uso di Azure ExpressRoute per avere una rete con requisiti di larghezza di banda e qualità della funzionalità di servizio per un'esperienza utente di business class. "
ms.openlocfilehash: e42cf42caafbb5ecd43b3660608a23d20cf8814e
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221248"
---
# <a name="expressroute-and-qos-in-skype-for-business-online"></a>ExpressRoute e QoS in Skype for Business Online

Connettersi a Office 365 tramite una connessione di rete dedicata con Azure ExpressRoute per Office 365 e Skype for business online. La connessione dedicata per le app Skype for Business ti offrirà prestazioni affidabili e prevedibili, oltre alla privacy, lontano da Internet pubblico. Ora è possibile acquistare una connessione di rete migliore a Office 365 e Skype for business online, che aggiunge prevedibilità, affidabilità della classe business e offre un contratto di lavoro di uptime.
  
> [!NOTE]
> È disponibile una nuova versione del calcolatore della larghezza di banda: [Skype for business, Bandwidth Calculator](https://go.microsoft.com/fwlink/?LinkId=715766). Le istruzioni in questo documento usano tuttavia la calcolatrice della larghezza di banda Lync 2010 e 2013. 
  
## <a name="skype-for-business-online-and-expressroute"></a>Skype for business online e ExpressRoute

Per collaborare con un partner di ExpressRoute di Microsoft, è possibile connettere una vasta gamma di applicazioni di Office 365, tra cui Skype for business online nel cloud tramite una connessione dedicata. Tuttavia, le funzionalità di comunicazione vocale e video in tempo reale per Skype for business richiedono servizi di rete configurati in modo specifico per supportare questi carichi di lavoro in tempo reale di Office 365. Ciò comprende una rete che abbia una larghezza di banda sufficiente per supportare il volume di traffico richiesto e che sia in grado di supportare la qualità del servizio (QoS, Quality of Service) per offrire agli utenti un'esperienza di livello aziendale.
  
Questo documento è progettato per aiutare gli amministratori e i progettisti di rete a comprendere le sfide specifiche necessarie per supportare le comunicazioni in tempo reale, gli strumenti forniti da Microsoft per facilitare la progettazione di una rete in grado di supportare questi requisiti e per illustrare il processo di progettazione con un caso di studio. 
  
Nella prima parte di questo documento viene illustrata una procedura per facilitare la progettazione della rete usando il calcolatore della [larghezza di banda Lync 2010 e 2013](https://go.microsoft.com/fwlink/?LinkId=690282) per stimare i requisiti di rete per una distribuzione di ExpressRoute Skype for business di grandi dimensioni e multisito. La seconda parte di questo documento offre i concetti fondamentali di qualità del servizio (QoS), una profonda immersione sui dettagli tecnici specifici per il supporto delle comunicazioni in tempo reale di Skype for business e i tipi specifici di servizi di rete che sono necessario.
  
Tutte le informazioni qui forniranno i dettagli tecnici e la comprensione per QoS e ExpressRoute, una comprensione delle sfide specifiche che dovrai affrontare e ti daranno una conoscenza efficace degli strumenti e delle tecniche che ti consentiranno di eseguire correttamente le operazioni distribuire un ExpressRoute attraverso la rete Skype for business. 
  
## <a name="getting-started"></a>Introduzione

Quando ti stai preparando per ExpressRoute per Skype for business, è una buona idea esaminare i diversi modelli di connessione ExpressRoute e la scelta di diversi partner e posizioni e leggere come acquistare e provisionare ExpressRoute all'interno della tua azienda. Ecco alcune risorse per iniziare: 
  
- [Azure ExpressRoute]( https://go.microsoft.com/fwlink/?LinkId=690283)
    
- [Prezzi ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690284)
    
- [Documentazione di ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690285)
    
## <a name="part-1-case-study---expressroute-for-dewey-law-llc"></a>Parte 1: case study-ExpressRoute per Dewey Law, LLC.

Questo caso di studio per Dewey Law, LLC. verrà illustrato come configurare una rete, ordinare servizi di accesso alla rete e determinare i requisiti di larghezza di banda per il supporto di ExpressRoute per Skype for business online.
  
 **Sfondo** Diritto di rugiada LLC. è un grande studio legale nazionale con 790 avvocati e un totale di 5.580 dipendenti distribuiti in 78 posizioni. Lo studio ha una sede centrale a New York, tre uffici regionali a Chicago, San Francisco e Dallas, insieme a 24 grandi e 50 piccole filiali sparse in tutto il paese. La società gestisce casi di grandi dimensioni e complessi con il carico di lavoro in genere distribuito tra due o più uffici. La progettazione della rete comporta un considerevole traffico di rete tra gli uffici.
  
Diritto di rugiada LLC. è una società relativamente giovane e gli avvocati e gli altri membri del personale sono molto comodi con la tecnologia e dipendono molto da essa per il lavoro quotidiano. 
  
 **Distribuzione degli utenti per località e posizioni**
  
||**Sede centrale (NY)**|**Uffici regionali (3)**|**Filiali grandi (24)**|**Piccole filiali (50)**|
|:-----|:-----|:-----|:-----|:-----|
|Esecutivo  <br/> |20  <br/> |10  <br/> |1  <br/> |1  <br/> |
|Partner  <br/> |150  <br/> |50  <br/> |10  <br/> |5  <br/> |
|Associates  <br/> |300  <br/> |100  <br/> |20  <br/> |10  <br/> |
|Paralegal  <br/> |400  <br/> |125  <br/> |30  <br/> |15  <br/> |
|Amministratori esecutivi  <br/> |100  <br/> |35  <br/> |6  <br/> |3  <br/> |
|IT e amministrazione generale  <br/> |100  <br/> |25  <br/> |3  <br/> |2  <br/> |
|Totale per sito  <br/> |1.070  <br/> |345  <br/> |70  <br/> |36  <br/> |
|Totale per classe sito  <br/> |1.070  <br/> |1.035  <br/> |1.680  <br/> |1.800  <br/> |
   
### <a name="setting-up-the-network"></a>Configurazione della rete

Per offrire servizi in tempo reale coerenti e di alta qualità per Dewey Law LLC, è necessario soddisfare un paio di requisiti di base:
  
- Desiderano prestare servizi vocali durante l'interruzione di corrente in modo che i relativi switch e router di distribuzione della rete debbano implementare PoE (Power over Ethernet) IEEE 802.3 AF o 802.3 at.
    
- Gli switch e i router di rete devono usare anche le fonti di energia ininterrotte (UPS) in modo che possano continuare a funzionare durante un errore di alimentazione.
    
    Hanno connessioni Wi-Fi agli uffici LAN, quindi consigliamo vivamente di usare un partner di infrastruttura Wi-Fi di Skype for business certificato da [Skype for Business Solutions](https://go.microsoft.com/fwlink/?LinkId=690281).
    
    > [!TIP]
    >  sono consigliati i punti di accesso wireless 802.11 n e 802.11 AC.
  
- E, cosa più importante, tutte le reti LAN in tutti gli uffici devono essere configurate per ottenere qualità del servizio (QoS). Questo include PC, laptop e qualsiasi hardware di rete, ad esempio switch e router.
    
Ora che le nozioni di base sono coperte, per offrire servizi vocali di qualità aziendale per Dewey Law LLC., è consigliabile usare il servizio IP MPLS (Multi-Protocol Label Switching) da un partner di servizio di rete che si connette al servizio Azure ExpressRoute. MPLS offre un servizio IP con garanzie sulle prestazioni per il ritardo, il jitter e la perdita di pacchetti. Tuttavia, se MPLS non è disponibile, è possibile usare Ethernet connessa a uno dei nostri partner di scambio dati di ExpressRoute.
  
I provider MPLS offrono diverse classi di livelli di servizio, ma ognuno usa termini diversi per identificarli. Sarà necessario collaborare in stretta collaborazione con il provider per verificare che siano in grado di comprendere i dati di input nella calcolatrice della [larghezza di banda di Lync 2010 e 2013](https://go.microsoft.com/fwlink/?LinkID=690282) e le opzioni disponibili e consigliate per i diversi carichi di lavoro in tempo reale di Office 365 applicazioni.
  
Sono disponibili due opzioni per il mapping dei dati delle applicazioni Skype for business alle classi di servizio MPLS appropriate:
  
- Contrassegno endpoint del traffico tramite il punto di controllo DiffServ (DSCP)
    
- Elenco di controllo di accesso (ACL) di rete basato
    
Per implementare la marcatura dell'endpoint, è necessario configurare tutti i computer di Windows Uniti per Dewey Law LLC. per contrassegnare ogni pacchetto con il contrassegno del punto di controllo DiffServ (DSCP) appropriato e quindi implementare QoS in tutti gli switch e i router di rete in tutti i siti di Office per assicurarsi che i contrassegni QoS vengano mantenuti e non vengano rimossi. I contrassegni DSCP nei pacchetti di rete indicano al provider di servizi la priorità del pacchetto di rete. **Sono disponibili altre informazioni su DSCP nella sezione QoS della parte 2.**
  
Per le assegnazioni basate su ACL di rete, i contrassegni di priorità DSCP vengono implementati in un router a Monte e sono basati sulla porta di origine UDP. Gli intervalli di porte consigliati per ogni applicazione sono elencati nella sezione 2.6.1.1 della [pianificazione della rete, del monitoraggio e della risoluzione dei problemi con Lync Server](https://go.microsoft.com/fwlink/?LinkId=690286). È importante coordinare questa operazione con l'implementazione e la progettazione QoS complessiva di Dewey Law LLC e tenere presente i diversi criteri QoS e il potenziale per le mancate corrispondenze del contrassegno dei pacchetti.
  
Ogni provider di servizi di rete ExpressRoute avrà una classe di servizio (QoS) appropriata per la voce e il video in tempo reale. Questo COS si chiama "inoltro accelerato" (EF) per la voce e "Inoltro assicurato" (AF) per il video. È necessario prestare particolare attenzione a ridimensionare la quantità di larghezza di banda acquistata per il traffico Voice EF. Il motivo è che la classe vocale del servizio è molto spietata in caso di invio di più traffico vocale rispetto a cui viene effettuato il provisioning della classe di servizio.
  
> [!TIP]
>  Qualsiasi traffico inviato alla classe di servizio vocale superiore all'impegno del provider di servizi viene immediatamente scartato, che consentirà di avere una qualità vocale effettiva.
  
Quando si esamina il progetto generale per Dewey Law LLC. è estremamente importante determinare in modo accurato la quantità di larghezza di banda di rete necessaria per supportare il traffico vocale nella propria rete e contrassegnare ogni pacchetto vocale (e solo i pacchetti vocali) con l'impostazione DSCP per la voce (ad esempio DSCP EF 46).
  
Per implementare il QoS attraverso la rete aziendale, gli endpoint o i router devono contrassegnare ogni pacchetto con l'indicatore di priorità Layer 3 appropriato (ad esempio, DSCP). Lungo l'intero percorso di rete, ogni switch e router deve avere l'opzione QoS attivata. Avendo anche solo uno switch di rete o un router che non ha QoS attivato, i contrassegni QoS su pacchetti vocali o video che passano attraverso l'interruttore o il router potrebbero essere rimossi. Questo disabilita efficacemente il QoS in tutti gli interruttori downstream e nei router che decrementano il valore di ExpressRoute.
  
Questo richiede inoltre che l'associazione delle priorità QoS Layer 3 e Layer 2 sia definita in ogni punto. I meccanismi di priorità layer 2 sono definiti in IEEE 802.1 p per reti cablate e 802.11 e/WMM per reti Wi-Fi. Più importante, il router di rete che si affaccia sulla rete MPLS del provider di servizi di rete deve mantenere le impostazioni di DSCP in tutti i pacchetti in uscita in modo che mantengano la classe di servizio MPLS appropriata. 
  
> [!TIP]
>  Per i dettagli specifici relativi alla configurazione QoS, vedere la sezione pianificazione della [rete di 2,6, monitoraggio e risoluzione dei problemi con Lync Server]( https://go.microsoft.com/fwlink/?LinkId=760669). È anche possibile visualizzare i [requisiti di rete per pianificare Skype for Business 2015](https://go.microsoft.com/fwlink/?LinkId=690287) per altri requisiti per la pianificazione della rete.
  
### <a name="ordering-network-access-services"></a>Ordinamento dei servizi di accesso alla rete

Dopo aver installato i prerequisiti e i requisiti di rete QoS per supportare ExpressRoute, il passaggio successivo consiste nell'effettuare un ordine per i servizi di accesso alla rete ExpressRoute. Quando si ordina ExpressRoute Access Services per Dewey Law LLC dal partner del provider di servizi di rete Microsoft, sarà necessario fornirne due informazioni:
  
- La quantità totale di larghezza di banda necessaria per connettere ogni sito a ExpressRoute e Office 365.
    
- La larghezza di banda totale necessaria per ogni classe di servizio necessaria per supportare le app Skype for business usate in Dewey Law LLC. La classe del requisito della larghezza di banda del servizio è determinata dal volume di traffico previsto da ognuna delle varie applicazioni Skype for business, ad esempio Voice, video, messaggistica istantanea, presenza e condivisione dello schermo.
    
### <a name="determining-bandwidth-requirements-for-skype-for-business-applications"></a>Determinazione dei requisiti di larghezza di banda per le applicazioni Skype for business

Per Dewey Law LLC., dopo aver determinato la larghezza di banda totale necessaria, è ora necessario sapere in che modo la larghezza di banda totale deve essere divisa tra le varie classi di servizio. Ad esempio, la quantità di larghezza di banda per ogni applicazione Skype for business.
  
Per determinare questi requisiti in ognuno dei Dewey Law LLC. i siti utilizzeranno il [calcolatore di larghezza di banda Lync 2010 e 2013](https://go.microsoft.com/fwlink/?LinkID=690282). Questa calcolatrice è uno strumento basato su Excel che consente di specificare l'uso previsto delle varie applicazioni Skype for business, tra cui Voice, video, conferenza e condivisione dello schermo. La calcolatrice genererà automaticamente una stima dei requisiti di larghezza di banda e CoS per ogni sito nella propria rete. Quando si Scarica il calcolatore di larghezza di banda Lync 2010 e 2013, verrà scaricato anche un manuale dell'utente che fornirà dettagli sull'uso. 
  
Per facilitare il foglio di calcolo, le varie celle del foglio di calcolo sono contraddistinte da colori:
  
- **Verde** Queste sono le aree di input dati generali.
    
- **Giallo** Queste sono aree avanzate per l'immissione di dati. Puoi cambiarle, ma fallo con attenzione.
    
- **Colore rosso** Queste sono aree di sola lettura e sono valori di input bloccati e non possono essere modificate.
    
- **Grigio** Queste sono aree di sola visualizzazione. Sono i risultati o i dati provenienti dalle aree di input generali.
    
Processo di progettazione per Dewey Law LLC. inizia con la caratterizzazione dei loro utenti in diversi "Personas". Per ogni persona che Definisci, puoi specificare l'uso previsto delle varie applicazioni Skype for business (' nessuno ',' low ',' medium ',' High ' o una delle tre impostazioni ' personalizzate ' definite). Queste selezioni si trovano nel foglio di lavoro "persona". Viene fornito l'utilizzo specifico di ogni scelta ("basso", "medio" o "alto"), ma le impostazioni predefinite per ogni scelta possono essere modificate. Identificando il numero di utenti per ogni persona che si trova in ogni sito, la calcolatrice può calcolare la larghezza di banda totale necessaria per ogni posizione.
  
È anche possibile specificare i codec audio e video usati, se si usa la correzione degli errori in avanti e anche altri parametri di sistema che influiranno sui requisiti di larghezza di banda. È possibile usare le impostazioni predefinite nel calcolatore di larghezza di banda Lync 2010 e 2013 o selezionare codec diversi e altri parametri di sistema. Per la progettazione del sito di Dewey Law LLC, è possibile usare le impostazioni predefinite. Tuttavia, per passare da una qualsiasi delle impostazioni predefinite, c'è un menu a discesa con tutte le opzioni disponibili. Le larghezze di banda usate per ogni scelta sono incluse nel foglio di lavoro "codec". Quando si modifica un'impostazione, la modifica della larghezza di banda e della combinazione di classi di servizi (CoS) in ogni sito viene aggiornata. Questa funzionalità consente di testare diverse configurazioni potenziali e di verificare l'impatto che le modifiche avranno sui requisiti di larghezza di banda.
  
Abbiamo definito tre persone per Dewey Law LLC., "Executive/Partner", "associate/paralegal" e "IT Admins". La tabella seguente mostra come sono stati impostati i profili di utilizzo per le varie app Skype for business per ogni persona.
  
 **Utenti e profili di utilizzo (foglio di lavoro "persona"-colonne da A A P)**
  
|**Utente tipo**|**Messaggistica istantanea/presenza**|**Audio P2P**|**Video P2P**|**Audio per conferenze**|**Video per conferenze**|**Condivisione desktop**|**Audioconferenza**|**Lync 2010 RTV_Type**|**Utenti remoti**|**Audio stereo di Lync 2013**|**Qualità video di Lync 2013**|**Comportamento degli utenti di Lync 2013 per la finestra video P2P**|**Utilizzo della visualizzazione multipla di Lync 2013**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Executive/Partner  <br/> |Alta  <br/> |Media  <br/> |Bassa  <br/> |Media  <br/> |Media  <br/> |Nessuno  <br/> |Media  <br/> |CIF  <br/> |0  <br/> |0  <br/> |Procedure  <br/> |Tipico  <br/> |Tipico  <br/> |
|Associato/paralegal  <br/> |Alta  <br/> |Media  <br/> |Bassa  <br/> |Media  <br/> |Alta  <br/> |Alta  <br/> |Media  <br/> |CIF  <br/> |0  <br/> |0  <br/> |Media  <br/> |Tipico  <br/> |Tipico  <br/> |
|Amministratori IT  <br/> |Alta  <br/> |Media  <br/> |Nessuno  <br/> |Bassa  <br/> |Nessuno  <br/> |Nessuno  <br/> |Media  <br/> |CIF  <br/> |0  <br/> |0  <br/> |Media  <br/> |Tipico  <br/> |Tipico  <br/> |
   
Sarà necessario immettere le informazioni nella **distribuzione degli utenti per posizione e posizione** sopra la tabella nel foglio di lavoro "siti" della calcolatrice della larghezza di banda di Lync 2010 e 2013. Dato che il numero di utenti negli uffici regionali è identico, questi sono definiti per un "sito" e sono stati specificati tre istanze. Lo stesso è stato fatto per i rami grandi e piccoli, in cui erano rispettivamente presenti 24 e 50 utenti in siti.
  
Dopo aver specificato le impostazioni per ogni persona, è necessario immettere il numero di utenti in ogni persona in ogni sito nel foglio di lavoro "siti". Gli utenti totali per tutti i siti vengono aggiornati automaticamente. Poiché non ci sono utenti nella posizione di Office 365, devono essere tutti immessi nelle righe ' Branchs ' del foglio di lavoro. La calcolatrice della larghezza di banda di Lync 2010 e 2013 quindi popola le colonne "classe di lavoro migliore", "classe traffico dati" e "classe di traffico in tempo reale" nella tabella "WAN BW per la classe di traffico QoS". Questa operazione viene visualizzata nei dati della tabella seguente.
  
> [!TIP]
>  Il foglio di calcolo completo include anche il numero massimo di sessioni simultanee per ogni applicazione, ma le colonne sono state eliminate per risparmiare spazio.
  
 **Utenti tipo per sito-(foglio di lavoro "siti"-colonne A, D, I e AI tramite AX)**
  
|**Nome sito**|**Totale utenti nel sito**|**Totale siti come questo**|**Profilo utente 1**|**Utente del profilo 1**|**Profilo utente 2**|**Utente del profilo 2**|**Profilo utente 3**|**Utente del profilo 3**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sede  <br/> |1070  <br/> |1  <br/> |Executive/Partner  <br/> |170  <br/> |Associato/paralegal  <br/> |700  <br/> |Amministratori IT  <br/> |200  <br/> |
|Uffici regionali  <br/> |345  <br/> |3  <br/> |Executive/Partner  <br/> |60  <br/> |Associato/paralegal  <br/> |225  <br/> |Amministratore IT  <br/> |60  <br/> |
|Filiali grandi  <br/> |70  <br/> |24  <br/> |Executive/Partner  <br/> |11  <br/> |Associato/paralegal  <br/> |50  <br/> |Amministratore IT  <br/> |9  <br/> |
|Filiali piccole  <br/> |36  <br/> |50  <br/> |Executive/Partner  <br/> |6  <br/> |Associato/paralegal  <br/> |25  <br/> |Amministratore IT  <br/> |1  <br/> |
   
 **Larghezza di banda necessaria per ogni applicazione per sito in kbps (' foglio di lavoro siti '-colonne A e BQ-LF)**
  
|**Sito**|**Larghezza di banda massima SIP/messaggistica istantanea**|**Larghezza di banda audio peer intersito picco**|**Larghezza di banda massima del peer video intersito**|**Larghezza di banda di conferenza audio di picco**|**Larghezza di banda massima di conferenza video**|**Larghezza di banda massima della condivisione WAN**|**Larghezza di banda WAN di picco per chiamate PSTN**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sede  <br/> |1070  <br/> |525,30  <br/> |560,00  <br/> |739,50  <br/> |2640,00  <br/> |4224,00  <br/> |2688,30  <br/> |
|Uffici regionali  <br/> |345  <br/> |185,40  <br/> |560,00  <br/> |255,00  <br/> |1320,00  <br/> |1536,00  <br/> |896,10  <br/> |
|Rami di grandi dimensioni  <br/> |70  <br/> |92,70  <br/> |560,00  <br/> |102,00  <br/> |600,00  <br/> |384,00  <br/> |216,30  <br/> |
|Piccole branche  <br/> |36  <br/> |119,40  <br/> |560,00  <br/> |76,50  <br/> |600,00  <br/> |384,00  <br/> |123,60  <br/> |
   
Probabilmente le colonne più importanti del foglio di calcolo sono quelle che descrivono la larghezza di banda WAN per la classe QoS. Questa operazione è illustrata nella tabella seguente. Questi dati riepilogano le informazioni che devono essere fornite al provider di servizi di rete per ordinare la connessione di Access in ogni sito. Quando si calcola la larghezza di banda totale, ricordarsi di moltiplicare la larghezza di banda per ogni tipo di sito di succursale in base al numero di siti dello stesso tipo. Per connettersi con il partner di servizi di rete ExpressRoute, è possibile visualizzare [Azure ExpressRoute]( https://go.microsoft.com/fwlink/?LinkId=690283).
  
È molto importante non superare la larghezza di banda nella classe di servizio Voice o "Accelerated forwarding" (EF). Un set di pacchetti casuale verrà scartato, quindi invece di ridurre la qualità di una singola chiamata o di un gruppo di chiamate, tutte le chiamate in corso possono essere interessate. È inoltre importante che solo la voce sia contrassegnata con il DSCP per EF (ad esempio DSCP = 46) oppure che la coda vocale potrebbe riversarsi quando viene aggiunto il traffico non vocale.
  
> [!TIP]
>  Anche in questo caso, mentre la classe EF del servizio offre la garanzia di prestazioni migliori, se si supera la larghezza di banda definita, tutti i pacchetti aggiuntivi verranno immediatamente eliminati.
  
 **Larghezza di banda aggregata per sito per classe di traffico QoS-(foglio di lavoro "siti"-colonne A e ML fino a MR)**
  
|**Nome sito**|**Classe effort migliore (DSCP 0)**|**Classe traffico dati (DSCP Custom)**|**Classe di traffico in tempo reale (DSCP 34, AF41)**|**Classe di traffico prioritario (DSCP 46, EF)**|
|:-----|:-----|:-----|:-----|:-----|
|Sede  <br/> |0,00  <br/> |5764,80  <br/> |3200,00  <br/> |3953,10  <br/> |
|Uffici regionali  <br/> |0,00  <br/> |2033,60  <br/> |1880,00  <br/> |1336,50  <br/> |
|Rami di grandi dimensioni  <br/> |0,00  <br/> |486,40  <br/> |1160,00  <br/> |411,00  <br/> |
|Piccole branche  <br/> |0,00  <br/> |438,40  <br/> |1160,00  <br/> |319,50  <br/> |
   
### <a name="putting-your-plan-into-action"></a>Mettere in atto il piano

Possiamo calcolare la larghezza di banda totale che percorrerà la WAN e la quantità di larghezza di banda che attraverserà ExpressRoute, usando le stime della larghezza di banda della tabella **per ogni applicazione per ogni sito** precedente. La parte di traffico che attraversa ExpressRoute esclude la larghezza di banda peer tra siti.

 
|**Sito**|**Larghezza di banda massima SIP/messaggistica istantanea**|**Larghezza di banda di conferenza audio di picco**|**Larghezza di banda massima di conferenza video**|**Larghezza di banda massima della condivisione WAN**|**Larghezza di banda WAN di picco per chiamate PSTN**|**Traffico ExpressRoute<br/>totale per classe<br/>di sito (ad esempio,<br/>tempo totale # dei siti)**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Sede** <br/> |1.070  <br/> |739,50  <br/> |2640,00  <br/> |4224,00  <br/> |2688,30  <br/> |11361,80  <br/> |
|**Uffici regionali** <br/> |345  <br/> |255,00  <br/> |1320,00  <br/> |1536,00  <br/> |896,10  <br/> |8704,20  <br/> |
|**Rami di grandi dimensioni** <br/> |70  <br/> |102,00  <br/> |600,00  <br/> |384,00  <br/> |216,30  <br/> |32935,20  <br/> |
|**Piccole branche** <br/> |36  <br/> |76,50  <br/> |600,00  <br/> |384,00  <br/> |123,60  <br/> |61005,00  <br/> |
   
Questo significa che il traffico di Skype for business online che attraverserà l'itinerario espresso sarà di circa 114 Mbps, quindi Dewey avrà bisogno almeno dell'abbonamento a 200 Mbps per ExpressRoute. Più circuiti ExpressRoute possono essere acquistati in diversi punti di peering di ExpressRoute. Questo può essere raccomandato se i siti di Dewey si trovano in aree geografiche diverse o per ottenere una resilienza se il collegamento al circuito ExpressRoute non riesce. Se si acquistano circuiti ExpressRoute in più aree di Azure, il componente aggiuntivo Premium ExpressRoute sarà necessario per ricevere la connettività globale tramite ExpressRoute.
  
Ora che si ha la quantità totale di larghezza di banda necessaria e i numeri di larghezza di banda per la classe di servizio (CoS), è possibile inserire gli ordini con i provider di servizi di rete selezionati. Non dimenticare di includere stime per il traffico per altre applicazioni e servizi. Offriamo indicazioni per la pianificazione della rete per altri servizi di Office 365, incluse le calcolatrici della larghezza di banda per Exchange e OneDrive. L'abbonamento alla larghezza di banda per il provider di servizi di rete sarà più elevato perché il traffico intra-sito deve essere aggiunto di nuovo. Il calcolatore della larghezza di banda di Lync 2010 e 2013 fornisce solo una stima del traffico previsto, pertanto è consigliabile confermare la capacità della rete di supportare il volume di traffico che conduce a un test di stress. 
  
> [!TIP]
> Test di stress la rete è altamente consigliata quando si esegue una prevalutazione della rete. 
  
Un test di stress prevede la creazione e la configurazione dell'infrastruttura e l'esecuzione con il volume previsto di traffico simulato durante il monitoraggio delle prestazioni. Le stime del traffico potrebbero essere imprecise in alcune aree, ma almeno puoi essere certo che possa supportare il volume del traffico previsto dal calcolatore della larghezza di banda di Lync 2010 e 2013. È consigliabile eseguire il test di stress per un minimo di pochi giorni, ma eseguirlo per un periodo di tempo più lungo può aiutare a perfezionare i numeri. Tuttavia, l'estensione del periodo di prova di stress deve essere valutata rispetto al costo dei servizi di rete pagati che non trasportano il traffico di rete utente reale. Microsoft ha certificato un certo numero di fornitori nell'ambito del programma IT Pro Tools che offre strumenti di gestione della rete e operazioni, inclusi gli strumenti di Prevalutazione della rete. Skype for business offre anche un System Integrator (SI) che può prendere gli strumenti Pro IT certificati e che può eseguire la valutazione della rete. Per altre informazioni, vedere [soluzioni per Skype for business: it Pro Tools](https://go.microsoft.com/fwlink/?LinkID=690307).
  
Il test di stress garantisce che la rete possa supportare il volume di traffico che sarà necessario, ma in realtà i dati di calcolo della larghezza di banda di Lync 2010 e 2013 possono essere spenti per qualsiasi numero di motivi. È anche consigliabile continuare a monitorare le reti dei siti eseguendo una valutazione della rete in corso dopo la distribuzione per garantire che la larghezza di banda sia sufficiente e che i meccanismi QoS funzionino correttamente. È importante continuare a monitorare le prestazioni della rete man mano che sempre più utenti reali vengono portati in linea.
  
## <a name="part-2-expressroute-skype-for-business-qos"></a>Parte 2: ExpressRoute Skype for business QoS

Il servizio ExpressRoute di Microsoft offre una connessione dedicata a Azure cloud, ma i servizi di comunicazione dei workload in tempo reale di Office 365 richiedono servizi di rete con larghezza di banda sufficiente per trasportare il volume del traffico e sono in grado di supportare Qualità del servizio (QoS) per offrire un'esperienza utente di livello aziendale. Una connessione in grado QoS deve essere configurata da end-to-end (PC, switch di rete e router nel cloud), poiché qualsiasi parte del percorso che non supporta QoS può degradare la qualità dell'intera chiamata.
  
Lo scopo di questa sezione è aiutare a comprendere le sfide quando si supporta il traffico in tempo reale in una rete IP e la configurazione e il supporto di una distribuzione ExpressRoute efficace dei workload di Office 365 in tempo reale con Microsoft Exchange ExpressRoute Provider o partner del provider di servizi di rete.
  
La QoS viene accettata dalle reti esclusivamente su circuiti di rete ExpressRoute e viene usata all'interno della rete Microsoft per il traffico Skype for business. Oggi parti di alcune connessioni in uscita da Microsoft presentano valori DSCP mancanti per Skype for business. Fino a quando il traffico in uscita è completamente contrassegnato con i valori DSCP, si consiglia di seguire le linee guida per l'aggiunta di contrassegni QoS al traffico al limite di rete, come descritto in **implementazione QoS con l'elenco di controllo di accesso di rete (ACL)** di questa sezione articolo.
  
### <a name="the-real-time-problem"></a>Problema in tempo reale

L'offerta di servizi per la qualità aziendale e il servizio video richiede particolari esigenze in una rete IP. Il traffico in tempo reale usa il protocollo RTP (Real-Time Transport Protocol) che viene eseguito tramite UDP (User Datagram Protocol). A differenza dei protocolli TCP (Transmission Control Protocol) che numerano e testano ogni messaggio per gli errori e includono altri meccanismi per rilevare e ritrasmettere messaggi persi o con errori, UDP non offre questo tipo di affidabilità. Se i messaggi sono danneggiati da errori o persi a causa di overflow del buffer, questi vengono persi. UDP è stato scelto per l'uso con la RTP perché la natura del traffico in tempo reale è che anche se i messaggi smarriti sono stati rimandati, arrivano troppo tardi per avere un impatto positivo sul flusso del messaggio vocale.
  
Conoscendo l'impatto dei pacchetti vocali persi, i progettisti hanno creato due approcci per migliorare le prestazioni della voce e del video tramite IP:
  
- Rendere la codifica vocale/decodifica più resiliente quando i pacchetti andranno perduti. Questa operazione può essere eseguita usando la correzione degli errori in avanti (FEC) per correggere una percentuale di errore riscontrato che è una funzionalità trovata nel trasporto in tempo reale di Office 365 oppure progettando sistemi di decodifica vocale che tentano di mascherare l'effetto di pacchetti persi che è una caratteristica dei codec Microsoft. 
    
- Usare i servizi di trasporto che usano i meccanismi di qualità dei servizi per garantire le prestazioni della rete in termini di ritardo, perdita di pacchetti e jitter e variazione di ritardo tra i pacchetti.
    
La codifica vocale resiliente risolve solo il problema della perdita di pacchetti, quindi è importante che una rete usata per il trasporto di voce e video in tempo reale abbia meccanismi che riducono al minimo ritardo e jitter. Anche con la codifica resiliente, se vengono persi troppi pacchetti, la stazione ricevente non avrà sufficienti informazioni per ricostruire una versione riconoscibile del segnale vocale. Percentuale di pacchetti persi che causano un deterioramento evidente della qualità vocale che varia a seconda della tecnica di codifica vocale usata. In tutti i casi, tuttavia, la perdita di stringhe di pacchetti successivi è molto problematica.
  
Il ritardo ridotto è importante perché un ritardo eccessivo può influire sul flusso della conversazione e creare un fastidio per gli altoparlanti. Le procedure consigliate indicano che il ritardo end-to-end per la voce (quello che chiamiamo "ritardo da bocca a orecchio") deve essere mantenuto al di sotto di 150 millisecondi (msec). ritardo di andata e ritorno. Naturalmente, il ritardo aumenterà sui collegamenti di trasmissione più lunghi, come quelli che attraversano gli oceani, in base al ritardo di propagazione o al tempo necessario per il segnale di spostamento fisicamente sul cavo.
  
Quando il ritardo supera i 150 msec. unidirezionale, ha uno strano effetto sull'altoparlante. Psicologicamente, un orologio si spegne nel cervello dell'oratore che li fa pensare che il destinatario non li abbia sentiti e ripetono l'ultima cosa che hanno detto. Questo si scontra con la risposta ritardata che arriva dall'estrema fine. Se hai mai parlato su un canale satellitare, riconosci questo effetto. Su un canale satellitare il ritardo unidirezionale è approssimativamente di 250 msec., che è ben oltre il ritardo ammissibile.
  
 **Parametri di rete consigliati per la voce business Grade**
  
|**Parametro**|**Valore consigliato**|
|:-----|:-----|
|Jitter in arrivo tra pacchetti (media)  <br/> |≤ 5ms  <br/> |
|Jitter del pacchetto di arrivo Inter (massimo)  <br/> |≤ 40ms  <br/> |
|Tasso di perdita di pacchetti (media)  <br/> |avvicinamento dello 0%  <br/> |
|Latenza della rete in un modo  <br/> |≤ 100ms (dovrebbe includere controlli sul ritardo rispetto alla distanza geografica)  <br/> |
   
### <a name="expressroute-as-part-of-a-business-grade-voice-network"></a>ExpressRoute come parte di una rete telefonica di qualità aziendale

ExpressRoute offre una connessione dedicata tramite un provider di servizi di rete (NSP) o un provider di Exchange (EXP) in una delle tre opzioni di connessione: 
  
- Colocation di Exchange cloud
    
- Connessione Ethernet Point-to-Point
    
- Connessione any-to-any (IPVPN)
    
In questo modo vengono forniti i vantaggi della disponibilità elevata (SLA uptime di 99,9%) e un routing affidabile (senza transito Internet), non influenzato dalle variazioni del traffico Internet e rispetta la qualità dei segni di servizio per la priorità del traffico (il QoS è spiegato di seguito) . ExpressRoute, insieme a una WAN ben pianificata, può offrirti una rete vocale di livello aziendale.
  
È possibile usare ExpressRoute per il transito di dati da uffici o Datacenter (se topologia ibrida) collegati al circuito. I dati per gli utenti fuori sede (ad esempio, da uffici privati o in viaggio e così via) non sfruttano il circuito ExpressRoute, a meno che gli utenti non siano connessi alla rete VPN e non debbano essere inclusi nelle stime della larghezza di banda per il dimensionamento del circuito di ExpressRoute. Se si è un cliente multinazionale, è possibile acquistare circuiti ExpressRoute in ogni area geografica e usare i tag della community BGP per informare le regole di routing in modo che il traffico venga indirizzato al circuito di ExpressRoute preferito (in genere quello più vicino per ogni sito), mentre l'altro i circuiti offrono ridondanza in caso di interruzioni che interessano un singolo circuito. 
  
### <a name="if-expressroute-isnt-an-option"></a>Se ExpressRoute non è un'opzione

Potrebbe non essere possibile connettere tutti i siti a ExpressRoute, a causa di costi, impossibilità di soddisfare i prerequisiti di ExpressRoute o limitazioni dell'attuale NSP. Se non si riesce a usare ExpressRoute, è comunque consigliabile seguire le indicazioni seguenti per contrassegnare il QoS all'interno della rete e pianificare i contratti con il proprio NSP per garantire una larghezza di banda e un supporto sufficienti per la priorità del traffico in base al QoS.
  
Inoltre, se si hanno uffici in più aree geografiche, ma non sono presenti circuiti ExpressRoute in tutte le aree geografiche, è consigliabile usare i tag della community di Region BGP quando si configura il routing per il traffico da/verso gli uffici satellitari, in modo da evitare il transito a lungo raggio. Ad esempio, considera una società che ha un'organizzazione di Skype for business online ospitata negli Stati Uniti, ma con succursali in Europa, e la società ha solo un singolo circuito ExpressRoute in Silicon Valley. La maggior parte del traffico Skype for business online verrà indirizzato a un Data Center in cui è ospitata l'organizzazione (ad esempio, conferenze telefoniche con altri utenti all'interno della società), l'uso del circuito ExpressRoute può essere preferito per la maggior parte del traffico. Tuttavia, se un utente in Europa dovesse partecipare a una conferenza telefonica ospitata da un'altra società la cui organizzazione si trova in Europa, la destinazione per il contenuto multimediale in quella chiamata sarebbe il data center europeo in cui si trova la seconda società. Instradare il traffico attraverso il circuito di ExpressRoute nella Silicon Valley sarebbe un percorso meno diretto di quello che sarebbe possibile tramite Internet. In questo caso, è consigliabile configurare i router all'interno della rete (ad esempio, presso gli uffici europei) per esaminare i tag della community quando si impostano le regole di routing e il routing via Internet invece del circuito di Silicon Valley ExpressRoute per il traffico che ha Tag Region europei.
  
### <a name="basic-concepts-of-quality-of-service-qosclass-of-service-cos"></a>Concetti di base sulla qualità del servizio (QoS)/Class of Service (CoS)

In IP la qualità del servizio (QoS) descrive qualsiasi meccanismo usato per offrire la gestione prioritaria di alcuni pacchetti rispetto ad altri. Secondo la definizione ITU (International Telecommunications Union), QoS include tutti gli aspetti qualitativi di una connessione, tra cui ritardo, perdita, rapporto segnale/rumore, area interattiva, eco, interrupt, risposta in frequenza, livelli di Loudness e così via. Ciò che chiamiamo QoS in network di pacchetti è più correttamente denominato Class of Service (CoS), che si basa sul miglioramento delle prestazioni per il ritardo, il jitter e la perdita di pacchetti, ma continueremo a usare il termine QoS dato che viene usato più comunemente.
  
La fornitura di QoS in una rete IP richiede due componenti principali:
  
- La prenotazione di una quantità definita di larghezza di banda su ogni collegamento per il traffico in tempo reale; Se la larghezza di banda non è necessaria per il traffico in tempo reale in qualsiasi momento, può essere usata per altri traffici. La guida generale prevede che per il traffico vocale non venga assegnato più del 30% della capacità di un collegamento.
    
- Contrassegnare i pacchetti con un indicatore di priorità nell'intestazione che indica agli switch e ai router nel percorso la priorità del pacchetto che deve essere assegnato.
    
Quando si riceve un pacchetto a un interruttore o a un router, viene spostato in una coda di output per la prossima tappa o hop. Esistono code di output diverse per i diversi livelli di priorità. Un switch o un router usa un algoritmo che assiste la coda con priorità alta più frequentemente delle code con priorità inferiore.
  
La sfida è che ci sono tecniche di QoS diverse implementate in layer 2 (cioè Ethernet o Wi-Fi Layer) e Layer 3 (cioè il livello IP). Le diverse implementazioni QoS possono essere configurate in ogni switch e router della rete, nonché nell'interfaccia tra la rete e la rete del provider di servizi di rete.
  
Sono disponibili due opzioni per il mapping dei dati delle varie applicazioni Skype for business alle classi di servizio appropriate:
  
- Contrassegno del punto finale del traffico tramite il punto di controllo dei servizi differenziati (DSCP) 
    
- Basato su elenchi di controllo di accesso (ACL) di rete
    
### <a name="end-point-traffic-marking--differentiated-services-control-point-dscp"></a>Contrassegno del traffico del punto finale-punto di controllo dei servizi differenziati (DSCP)

I servizi differenziati (DiffServ) si riferiscono a un meccanismo "a grana grossa" per classificare e gestire il traffico di rete e fornire QoS nelle reti IP. I router e altri dispositivi che implementano le funzioni Layer 3 usano il punto di controllo DiffServ (DSCP) per definire la priorità del pacchetto. Il QoS viene implementato inserendo un valore DSCP a 6 bit nel campo servizi differenziati (in precedenza il campo "tipo di servizio") nell'intestazione IP; 6 bit consente di 64 livelli di priorità diversi. I livelli di priorità sono in genere definiti come illustrato di seguito.
  
 **Impostazioni DSCP consigliate**
  
|**Classe traffico**|**Trattamento (contrassegno DSCP)**|**Carichi di lavoro Skype for business**|
|:-----|:-----|:-----|
|**Segreteria telefonica** <br/> |EF (46)  <br/> |Skype for business e Lync Voice  <br/> |
|**Interattiva** <br/> |AF41 (34)  <br/> |Video  <br/> |
||AF21 (18)  <br/> |Condivisione applicazioni  <br/> |
|**Predefinita** <br/> |AF11 (10)  <br/> |Trasferimento di file  <br/> |
||CS0 (0)  <br/> |Qualsiasi altra cosa  <br/> |
   
 **Intestazione IP versione 4**
  
![Intestazione IPv4](../images/c8a6a714-2784-4328-8297-2e62706f302d.png)
  
### <a name="layer-2-qos-ieee-8021pwi-fi-multi-media-ieee-80211e"></a>QoS di livello 2: IEEE 802.1 p/Wi-Fi multi-media (IEEE 802.11 e)

Mentre DSCP è il meccanismo standard per l'implementazione del QoS nel layer 3, esistono diversi meccanismi QoS Layer 2 per Wired (Ethernet) e wireless (ad esempio reti Wi-Fi). Il meccanismo QoS per le reti cablate è definito nello standard IEEE 802.1 p; il meccanismo QoS WLAN è definito in IEEE 802.11 e, che l'Alleanza Wi-Fi identifica come "Certified multi-media Wi-Fi" (WMM Certified).
  
Lo standard IEEE 802.1 p usa un PCP (3 bit Priority Code Point) per identificare la priorità del messaggio; il PCP fa parte di un campo a 32 bit nell'intestazione Ethernet che trasporta anche l'identificatore VLAN. Di seguito sono elencate le definizioni per i valori PCP.
  
 **Valori PCP IEEE 802.1 p**
  
|**Valore PCP**|**Priorità**|**Acronimo**|**Tipi di traffico**|
|:-----|:-----|:-----|:-----|
|7  <br/> |7  <br/> |NC  <br/> |Controllo di rete  <br/> |
|6  <br/> |6  <br/> |IC  <br/> |Controllo Internetwork  <br/> |
|5  <br/> |5  <br/> |VO  <br/> |Segreteria telefonica  <br/> |
|4  <br/> |4  <br/> |VI  <br/> |Video  <br/> |
|3  <br/> |3  <br/> |CA  <br/> |Applicazioni critiche  <br/> |
|2  <br/> |2  <br/> |EE  <br/> |Eccellente sforzo  <br/> |
|0  <br/> |1  <br/> |ESSERE  <br/> |Sforzo migliore  <br/> |
|1  <br/> |0  <br/> |BK  <br/> |Sfondo  <br/> |
   
Dove IEEE 802.1 p è implementato più o meno allo stesso modo di DSCP con il traffico ordinato in code prioritarie diverse per ogni livello di priorità, ma la natura media condivisa delle reti WLAN richiede un approccio diverso. Mentre il punto di accesso e il client manterranno le code di output separate per i diversi livelli di priorità, esistono anche differenze nel modo in cui i fotogrammi vengono inviati sul canale radio.
  
In una rete Wi-Fi tutti i client associati a un punto di accesso condividono un singolo canale half-duplex (ad esempio, è possibile inviare una sola stazione client o il punto di accesso alla volta). Per ridurre al minimo il potenziale di collisioni sul canale radio, prima di inviare un fotogramma la stazione attende che il canale sia inattivo per un determinato periodo di tempo denominato "spaziatura inter-frame", se il canale è occupato quando una stazione passa a inviare, viene eseguito il backup di un tempo casuale peri od. Dopo aver inviato il fotogramma, se il mittente non riceve un messaggio di riconoscimento da parte del destinatario, presuppone che si verifichi una collisione o un altro errore e che passi di nuovo a un intervallo casuale prima di provare ad accedere al canale radio per rinviarlo. L'intervallo di back-off è casuale per ridurre la probabilità che le stesse due stazioni si scontrano di nuovo.
  
Per dare priorità all'accesso al canale radio, IEEE 802.11 e/WMM definisce diversi intervalli di attesa di pre-trasmissione denominati "spazi inter-frame arbitrato" (AFIS) e diversi intervalli di back-off per le diverse classi di traffico; vengono definiti quattro livelli di priorità denominati "categorie di accesso".
  
La priorità viene data assegnando valori AFIS più brevi ai fotogrammi con priorità più alta. Quindi, se una stazione è in attesa di inviare un fotogramma vocale e un altro è in attesa di inviare un fotogramma dati, il fotogramma vocale verrà sempre inviato per primo. Tecnicamente, per i fotogrammi vocali e video viene assegnato lo stesso valore AFIS, ma l'intervallo di intervalli di back-off per i fotogrammi video è più elevato. Quindi, mentre un fotogramma vocale e video può collidere al primo tentativo, il fotogramma vocale verrà sempre ritrasmesso prima. Di seguito è illustrata la correlazione tra IEEE 802.1 p e IEEE 802.11 e:
  
 **IEEE 802.11 e/Wi-Fi multi-media (WMM) alla mappatura 802.1 P**
  
|**Categoria di accesso WMM**|**Descrizione di WMM**|**valore PCP 802.1 p**|**designazione 802.1 p**|
|:-----|:-----|:-----|:-----|
|1 (AC_VO)  <br/> |Segreteria telefonica  <br/> |7 (111)  <br/> |NC  <br/> |
|6 (110)  <br/> |VO  <br/> |
|2 (AC_VI)  <br/> |Video  <br/> |5 (101)  <br/> |VI  <br/> |
|4 (100)  <br/> |CL  <br/> |
|3 (AC_BE)  <br/> |Dati sugli sforzi migliori  <br/> |3 (011)  <br/> |EE  <br/> |
|0 (000)  <br/> |ESSERE  <br/> |
|4 (AC_BK)  <br/> |Dati in background  <br/> |1 (001)  <br/> |BK  <br/> |
|2 (010)  <br/> |---  <br/> |
   
Di seguito è illustrata l'associazione consigliata delle priorità di livello 3 e livello 2:
  
 **Consigliato livello 3 alle associazioni prioritarie Layer 2**
  
||**Marcature Layer 3**|**Layer 2 (valore PCP)**|**Wi-Fi (categoria Access)**|
|:-----|:-----|:-----|:-----|
|Controllo di rete  <br/> |Comportamento per hop (PHB)-selettore di classe (CS) 6  <br/> |6  <br/> |1 (AC_VO)  <br/> |
|Valore DSCP-48  <br/> |
|Segreteria telefonica  <br/> |Comportamento per hop (PHB)-inoltro accelerato (EF)  <br/> |5  <br/> |1 (AC_VO)  <br/> |
|Valore DSCP-46  <br/> |
|Video conferenza  <br/> |Comportamento per hop (PHB)-inoltro assicurato (AF) 41  <br/> |4  <br/> |2 (AC_VI)  <br/> |
|Valore DSCP-34  <br/> |
|Segnalazione chiamata  <br/> |Comportamento per hop (PHB)-selettore di classe (CS) 3  <br/> |3  <br/> |2 (AC_VI)  <br/> |
|Valore DSCP-24  <br/> |
|Dati a bassa latenza  <br/> |Comportamento per hop (PHB)-inoltro assicurato (AF) 21  <br/> |2  <br/> |3 (AC_BE)  <br/> |
|Valore DSCP-18  <br/> |
|Dati a velocità elevata  <br/> |Comportamento per hop (PHB)-inoltro assicurato (AF) 11  <br/> |1  <br/> |3 (AC_BE)  <br/> |
|Valore DSCP-10  <br/> |
|Sforzo migliore  <br/> |Comportamento per hop (PHB)-0  <br/> |0  <br/> |4 (AC_BK)  <br/> |
|Valore DSCP-0  <br/> |
   
È importante notare che c'è una mancata corrispondenza nella codifica prioritaria per IEEE 802.1 p e WMM. L'802.1 p il valore PCP per la voce è 5, tuttavia, nella mappatura dell'equivalenza standard a WMM, PCP 5 viene tradotto in Access Category 2, la categoria di accesso WMM per il video (AC_VI). Se possibile, devi eseguire l'override di tale mapping in modo che PCP 5 venga convertita nella categoria 1 di Access o semplicemente evitare di usare la voce e il video nella stessa rete Wi-Fi finché l'Alleanza Wi-Fi non risolve questo problema. Per altre informazioni su Wi-Fi, vedere [elementi del catalogo Wi-Fi]( https://go.microsoft.com/fwlink/?LinkId=690322).
  
### <a name="implementing-qos-using-network-access-control-list-acl"></a>Implementazione di QoS tramite l'elenco di controllo di accesso (ACL) di rete

Il metodo alternativo per l'implementazione di QoS in una configurazione ExpressRoute consiste nell'usare l'elenco di controllo di accesso (ACL) di rete. In questo approccio, invece di inserire i punti finali nel contrassegno di DSCP appropriato nell'intestazione di ogni pacchetto, la marcatura può essere eseguita da un router a Monte, in base alla porta di origine UDP. Tutti gli switch e i router devono essere ancora configurati per supportare QoS per verificare che le impostazioni di DSCP vengano mantenute. Cosa più importante, il router connesso alla rete del provider di servizi deve mantenere il DSCP nell'intestazione di ogni pacchetto, dato che l'impostazione DSCP è essenzialmente l'istruzione per il provider di servizi di rete per il modo in cui il pacchetto deve essere trattato.
  
Gli intervalli di porte consigliati per ogni applicazione Skype for business sono elencati nella sezione 2.6.1.1 della Guida alla [pianificazione della rete, al monitoraggio e alla risoluzione dei problemi con Lync Server](https://go.microsoft.com/fwlink/?LinkId=690286) guide. È importante che sia coordinata con l'approccio globale dell'organizzazione alla QoS e che tu debba essere alla ricerca di diversi criteri QoS e di potenziali mancate corrispondenze del pacchetto.
  
Mentre i servizi di rete QoS e MPLS principali vengono usati per garantire una buona esperienza utente per la voce e il video in tempo reale, le stesse funzionalità possono essere applicate anche alle applicazioni dati. Invece di trattare equamente tutte le applicazioni, le reti MPLS possono consentire alle organizzazioni di dare priorità ad alcune applicazioni di dati rispetto ad altre. Con MPLS, le applicazioni in tempo reale, come le transazioni tramite carta di credito o la condivisione dello schermo, possono avere priorità su traffico meno sensibile al tempo, come la posta elettronica.
  
### <a name="understanding-the-types-of-ip-network-services--basic-ip-and-mpls"></a>Informazioni sui tipi di servizi di rete IP-IP di base e MPLS

L'inoltro originale del pacchetto IP è stato usato per il principio "migliore sforzo". Ciò significava che i router che inoltrano tali pacchetti IP farebbero del loro meglio per consegnarli alle loro destinazioni, ma non c'era alcuna garanzia riguardo a quando o se potessero arrivare alle loro destinazioni. Questo è il modo in cui i servizi Internet di base, inclusa la connessione Internet domestica, funzionano oggi. L'idea era che se fosse necessaria l'affidabilità per una particolare applicazione, sarebbe stata fornita a un livello più alto nello stack del protocollo. Il meccanismo di recapito affidabile è il protocollo TCP (Transmission Control Protocol). Il protocollo UDP (User Datagram Protocol), usato per la voce e il video in tempo reale, è il meccanismo di recapito non attendibile (ad esempio "migliore sforzo"). 
  
Il cambio di etichetta Multi-Protocol (MPLS) è stato sviluppato come mezzo per i provider di servizi di rete per offrire un servizio IP con garanzie di prestazioni per ritardo, jitter e perdita di pacchetti. Per offrire queste garanzie di prestazioni, MPLS richiede parte dell'imprevedibilità dell'IP tradizionale. Prima di tutto, invece di avere ogni pacchetto trovare la sua strada router-to-router alla sua destinazione (il cui risultato potrebbe essere che ogni pacchetto prende una route diversa dalla fonte alla destinazione), MPLS instrada tutti i pacchetti in una connessione "circuito virtuale" con un Route fissa denominata LSP (Switched Path) etichetta. Se uno dei collegamenti nel percorso non riesce, tutti i LSP che usano il collegamento vengono rapidamente reinstradati.
  
Quando viene inviato un pacchetto nella rete MPLS, il router Edge del provider di servizi di rete aggiunge un'intestazione aggiuntiva al pacchetto che include un'etichetta che viene usata per inoltrarla tramite il LSP appropriato. L'etichetta viene spogliata dal router Edge all'altra estremità della rete MPLS.
  
Oltre a semplificare il processo di inoltro, l'altro vantaggio disponibile in MPLS consiste nel fatto che il sistema di gestione della rete saprà quali connessioni vengono trasportate su ogni collegamento della rete. Controllando il modo in cui il traffico viene instradato attraverso la rete, l'operatore può garantire il QoS che ogni percorso fornirà. A differenza delle prestazioni ottimali degli IP tradizionali o di base, gli operatori MPLS possono ottenere un servizio IP con prestazioni prevedibili. Questo LSP rende anche i MPLS più sicuri dei servizi Internet tradizionali. Quindi, con il servizio IP di base possiamo sperare che la rete si svolga abbastanza bene per garantire una buona qualità della voce e usare tecniche come FEC e la codifica vocale più resiliente per migliorare le probabilità, ma usando MPLS, possiamo essere sicuri.
  
I provider MPLS offrono diverse classi di gradienti di servizio che usano purtroppo termini diversi per identificarle. Sarà necessario collaborare in stretta collaborazione con il provider per verificare che siano in contatto con gli output della calcolatrice della [larghezza di banda Lync 2010 e 2013](https://go.microsoft.com/fwlink/?LinkID=690282) e le opzioni consigliate per le diverse applicazioni di carichi di lavoro in tempo reale di Office 365.
  
## <a name="conclusion"></a>Conclusione

Skype for business migliora il modo in cui vengono svolte le comunicazioni commerciali. Invece di avere un telefono connesso a un PBX, un sistema di videoconferenza autonomo, una piattaforma separata per la posta elettronica, un servizio esterno per i servizi di audioconferenza e un veicolo per la messaggistica istantanea e la presenza, Skype for business può riunire tutte queste funzionalità in una singola interfaccia utente.
  
La distribuzione coerente dei servizi vocali e video in tempo reale per le aziende richiede un'infrastruttura di rete end-to-end in grado di fornire QoS. Che includerebbe sia LAN che i servizi WAN. Microsoft offre strumenti come il [calcolatore della larghezza di banda Lync 2010 e 2013](https://go.microsoft.com/fwlink/?LinkID=690282) per stimare la capacità di rete necessaria per i vari servizi. Ci sono inoltre partner nel programma IT Pro Tools [per Skype for Business Solutions: strumenti IT Pro](https://go.microsoft.com/fwlink/?LinkID=690307) che offrono strumenti per valutare preventivamente l'infrastruttura di rete e supportare il monitoraggio, la creazione di report e la risoluzione dei problemi. Senza un'infrastruttura di rete correttamente dimensionata e configurata, si rischia di avere una distribuzione di ExpressRoute Skype of business che non soddisfi le aspettative dell'utente per qualità e coerenza.
  
Gli strumenti aziendali effettivi devono eseguire in modo affidabile, coerente e offrire un'esperienza utente che incoraggi l'adozione degli utenti. Dal punto di vista della rete, che significa avere un'infrastruttura di rete, sia locale che wide area, fissa e mobile, che può consentire che ciò accada. La pianificazione, la progettazione, l'implementazione e la manutenzione di tali infrastrutture non è sempre un'impresa facile. L'hardware, gli strumenti e i servizi di rete da realizzare oggi disponibili, ma è responsabilità di IT Pro verificare che siano progettati, implementati e gestiti in modo da garantire agli utenti un set di servizi di comunicazione e collaborazione che consentire loro di lavorare in modo efficiente ed efficace e che l'organizzazione possa trarre il massimo vantaggio da ciò che questa tecnologia può offrire. 
  
## <a name="related-topics"></a>Argomenti correlati

[Documentazione di ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690285)

  
 