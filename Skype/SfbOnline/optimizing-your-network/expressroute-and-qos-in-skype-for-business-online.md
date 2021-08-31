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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: "Informazioni sull'uso di Azure ExpressRoute per avere una rete con requisiti di larghezza di banda e funzionalità di qualità del servizio per un'esperienza utente di business class. "
ms.openlocfilehash: 32d9a3f6be35077f274f0a8ab9facc462a3fe6b4
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729785"
---
# <a name="expressroute-and-qos-in-skype-for-business-online"></a>ExpressRoute e QoS in Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Connessione a Microsoft 365 o Office 365 tramite una connessione di rete dedicata usando Azure ExpressRoute per Microsoft 365 o Office 365 e Skype for Business Online. La connessione dedicata per le app Skype for Business ti offrirà prestazioni affidabili e prevedibili, oltre che privacy lontano da Internet pubblico. Ora è possibile acquistare una connessione di rete migliore a Microsoft 365 o Office 365 e Skype for Business Online, che aggiunge prevedibilità, affidabilità in classe aziendale e viene fornito con un contratto di servizio per i tempi di attività.
  
> [!NOTE]
> È disponibile una nuova versione della calcolatrice della larghezza di banda: [Skype for Business, Bandwidth Calculator](https://go.microsoft.com/fwlink/?LinkId=715766). Tuttavia, le istruzioni in questo documento usano la calcolatrice della larghezza di banda di Lync 2010 e 2013. 
  
## <a name="skype-for-business-online-and-expressroute"></a>Skype for Business Online ed ExpressRoute

Lavorando con un partner ExpressRoute di Microsoft, è possibile connettere un'ampia gamma di applicazioni Microsoft 365 e Office 365, tra cui Skype for Business Online nel cloud tramite una connessione dedicata. Tuttavia, le funzionalità di comunicazione vocale e video in tempo reale per Skype for Business richiedono servizi di rete specificamente configurati per supportare questi carichi di lavoro Microsoft 365 o Office 365 in tempo reale. Ciò comprende una rete che abbia una larghezza di banda sufficiente per supportare il volume di traffico richiesto e che sia in grado di supportare la qualità del servizio (QoS, Quality of Service) per offrire agli utenti un'esperienza di livello aziendale.
  
Questo documento è progettato per aiutare gli amministratori e i progettisti di rete a comprendere le sfide speciali necessarie per supportare le comunicazioni in tempo reale, gli strumenti forniti da Microsoft per agevolare la progettazione di una rete in grado di supportare tali requisiti e per illustrare il processo di progettazione usando un case study. 
  
La prima parte di questo documento illustra un case study che illustra come progettare la rete usando la calcolatrice della larghezza di banda di [Lync 2010 e 2013](https://go.microsoft.com/fwlink/?LinkId=690282) per stimare i requisiti di rete per una distribuzione di Skype for Business ExpressRoute multisociestra di grandi dimensioni. La seconda parte di questo documento offre i concetti fondamentali di Qualità del servizio (QoS), un approfondimento sui dettagli tecnici specifici per il supporto delle comunicazioni Skype for Business tempo reale e sui tipi specifici di servizi di rete necessari.
  
Tutte le informazioni qui fornite forniscono i dettagli tecnici e la comprensione per QoS ed ExpressRoute, una comprensione delle sfide specifiche che si affronteranno e una conoscenza funzionante degli strumenti e delle tecniche che consentono di distribuire correttamente expressRoute nella rete Skype for Business. 
  
## <a name="getting-started"></a>Introduzione

Quando si è pronti per ExpressRoute per Skype for Business, è buona norma esaminare i diversi modelli di connessione ExpressRoute e le varie opzioni di partner e località e leggere come acquistare ed eseguire il provisioning di ExpressRoute all'interno dell'azienda. Ecco alcune risorse per iniziare: 
  
- [Azure ExpressRoute]( https://go.microsoft.com/fwlink/?LinkId=690283)
    
- [Prezzi expressroute](https://go.microsoft.com/fwlink/?LinkId=690284)
    
- [Documentazione di ExpressRoute](/azure/expressroute/)
    
## <a name="part-1-case-study---expressroute-for-dewey-law-llc"></a>Parte 1: Case study - ExpressRoute per Dewey Law, LLC.

Questo case study per Dewey Law, LLC. mostrerà come configurare una rete, ordinare i servizi di accesso alla rete e determinare i requisiti di larghezza di banda per supportare ExpressRoute per Skype for Business Online.
  
 **Sfondo** Dewy Law LLC. è un grande studio legale nazionale con 790 avvocati e un totale di 5.580 dipendenti distribuiti in 78 sedi. L'azienda ha una sede centrale a New York, tre uffici regionali a Chicago, San Francisco e Dallas, oltre a 24 filiali grandi e 50 piccole sparsi in tutto il paese. L'azienda gestisce casi complessi e di grandi dimensioni con il carico di lavoro in genere distribuito tra due o più uffici. Questa progettazione di rete comporta un notevole traffico di rete tra gli uffici.
  
Dewy Law LLC. è un'azienda relativamente giovane e gli avvocati e gli altri membri del personale sono molto a proprio agio con la tecnologia e dipendono molto da essa per il loro lavoro quotidiano. 
  
 **Distribuzione degli utenti in base a posizioni e posizioni**
  
|Personale |**Sede centrale (NY)**|**Uffici locali (3)**|**Filiali di grandi dimensioni (24)**|**Filiali di piccole dimensioni (50)**|
|:-----|:-----|:-----|:-----|:-----|
|Dirigenti  <br/> |20  <br/> |10  <br/> |1  <br/> |1  <br/> |
|Partner  <br/> |150  <br/> |50  <br/> |10  <br/> |5  <br/> |
|Associati  <br/> |300  <br/> |100  <br/> |20  <br/> |10  <br/> |
|Paralegale  <br/> |400  <br/> |125  <br/> |30  <br/> |15  <br/> |
|Amministratori dirigenti  <br/> |100  <br/> |35  <br/> |6  <br/> |3  <br/> |
|IT e amministrazione generale  <br/> |100  <br/> |25  <br/> |3  <br/> |2  <br/> |
|Totale per sito  <br/> |1,070  <br/> |345  <br/> |70  <br/> |36  <br/> |
|Totale per classe del sito  <br/> |1,070  <br/> |1,035  <br/> |1,680  <br/> |1,800  <br/> |
   
### <a name="setting-up-the-network"></a>Configurazione della rete

Per offrire servizi in tempo reale coerenti e di alta qualità per Dewey Law LLC., è necessario soddisfare un paio di requisiti di base:
  
- Vogliono fornire servizi vocali durante l'interruzione dell'alimentazione, quindi i router e gli switch di distribuzione di rete devono fornire alimentazione tramite Ethernet (PoE) IEEE 802.3af o 802.3at.
    
- Gli switch e i router di rete devono anche usare fonti di alimentazione ininterrotta (UPS) in modo che possano continuare a operare durante un'interruzione dell'alimentazione.
    
    Hanno una connessione Wi-Fi con i loro uffici LAN, quindi è consigliabile usare un partner certificato per l'infrastruttura di Skype for Business Wi-Fi di [Skype for Business Solutions.](https://go.microsoft.com/fwlink/?LinkId=690281)
    
    > [!TIP]
    >  Sono consigliati i punti di accesso wireless 802.11n e 802.11ac.
  
- E, cosa più importante, tutte le reti LAN in tutti gli uffici devono essere impostate per fornire la qualità del servizio (QoS). Sono inclusi PC, portatili e qualsiasi hardware di rete, ad esempio switch e router.
    
Ora che sono state trattate le nozioni di base, per fornire servizi vocali di livello aziendale per Dewey Law LLC., è consigliabile usare il servizio IP MPLS (Multi-Protocol Label Switching) da un partner del servizio di rete che si connetterà al servizio Azure ExpressRoute. MPLS fornisce un servizio IP con garanzie di prestazioni per ritardi, instabilità e perdita di pacchetti. Tuttavia, se MPLS non è disponibile, è possibile usare anche Ethernet connesso a uno dei partner di scambio dati ExpressRoute.
  
I provider MPLS offrono diverse classi di livelli di servizio, ma ognuno usa termini diversi per identificarli. È necessario collaborare a stretto contatto con il provider per assicurarsi che comprenda i dati immessi nella Calcolatrice larghezza di banda di [Lync 2010 e 2013](https://go.microsoft.com/fwlink/?LinkID=690282) e le opzioni disponibili e consigliate per le diverse applicazioni di carico di lavoro Microsoft 365 e Office 365 in tempo reale.
  
Esistono due opzioni per il mapping dei dati Skype for Business applicazioni alle classi di servizio MPLS appropriate:
  
- Contrassegno endpoint del traffico con DiffServ Control Point (DSCP)
    
- Elenco di controllo di accesso di rete (ACL) basato
    
Per implementare il contrassegno endpoint, è necessario configurare tutti i computer Windows dominio per Dewey Law LLC. per contrassegnare ogni pacchetto con il contrassegno DSCP (DiffServ Control Point) appropriato e quindi implementare la QoS su tutti gli switch e i router di rete in tutti i siti dell'ufficio per assicurarsi che i contrassegni QoS siano mantenuti e non rimossi. I contrassegni DSCP nei pacchetti di rete indicano al provider di servizi la priorità del pacchetto di rete. **Altre informazioni su DSCP sono disponibili nella sezione QoS della parte 2.**
  
Per l'assegnazione basata su ACL di rete, i contrassegni di priorità DSCP vengono implementati presso un router upstream e si basano sulla porta di origine UDP. Gli intervalli di porte consigliati per ogni applicazione sono elencati nella Sezione 2.6.1.1 di Pianificazione della rete, monitoraggio e risoluzione dei problemi [con Lync Server.](https://go.microsoft.com/fwlink/?LinkId=690286) È importante coordinare questa operazione con l'implementazione e la progettazione QoS generale di Dewey Law LLC e tenere presente i diversi criteri QoS e il potenziale di mancata corrispondenza dei contrassegni dei pacchetti.
  
Ogni provider di servizi di rete ExpressRoute avrà una classe di servizio (QoS) appropriata per voce e video in tempo reale. Questo COS è chiamato "Inoltro accelerato" (EF) per la voce e "Inoltro sicuro" (AF) per il video. È necessario prestare particolare attenzione nel ridimensionare la quantità di larghezza di banda acquistata per il traffico EF vocale. Il motivo è che la classe di servizio vocale è molto imperdonante nel caso in cui si invii più traffico vocale di quello per cui viene eseguito il provisioning della classe di servizio.
  
> [!TIP]
>  Qualsiasi traffico inviato nella classe di servizio vocale che supera l'impegno del provider di servizi viene immediatamente eliminato, in modo da effetto diretto sulla qualità vocale.
  
Quando si esamina la progettazione generale di Dewey Law LLC. è estremamente importante determinare con precisione la quantità di larghezza di banda di rete necessaria per supportare il traffico vocale attraverso la propria rete e contrassegnare ogni pacchetto vocale (e solo i pacchetti vocali) con l'impostazione DSCP per la voce (ad esempio DSCP EF 46).
  
Per implementare la QoS nella rete aziendale, gli endpoint o i router devono contrassegnare ogni pacchetto con l'indicatore di priorità di livello 3 appropriato, ad esempio DSCP. Lungo l'intero percorso di rete, ogni switch e router deve avere l'opzione QoS attivata. Avendo anche un solo interruttore di rete o router che non ha QoS attivato, i contrassegni QoS sui pacchetti vocali o video che passano attraverso quell'interruttore o router potrebbero essere spogliati. In questo modo la QoS viene disabilitata in modo efficace in tutti gli switch e i router downstream, con una riduzione del valore di ExpressRoute.
  
A questo scopo è necessario definire l'associazione delle priorità QoS di livello 3 e livello 2 in ogni punto. I meccanismi di priorità di livello 2 sono definiti in IEEE 802.1p per le reti cablate e 802.11e/WMM per le reti Wi-Fi rete. Ancora più importante, il router di rete rivolto alla rete MPLS del provider di servizi di rete deve mantenere le impostazioni DSCP in tutti i pacchetti in uscita in modo che mantengano la classe di servizio MPLS appropriata. 
  
> [!TIP]
>  Per informazioni dettagliate sulla configurazione di QoS, vedere la sezione 2.6 Pianificazione, monitoraggio e risoluzione dei problemi di rete [con Lync Server.]( https://go.microsoft.com/fwlink/?LinkId=760669) È anche possibile vedere [Pianificare i requisiti di rete per Skype for Business 2015](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md) per altri requisiti di pianificazione della rete.
  
### <a name="ordering-network-access-services"></a>Ordinare le Access Services

Dopo aver creato i prerequisiti e i meccanismi di rete QoS per supportare ExpressRoute, il passaggio successivo consiste nell'eseguire un ordine per i servizi di accesso alla rete ExpressRoute. Quando si ordinano i servizi di accesso ExpressRoute per Dewey Law LLC dal partner del provider di servizi di rete Microsoft, è necessario fornire due aspetti:
  
- La quantità totale di larghezza di banda necessaria per connettere ogni sito a ExpressRoute e Microsoft 365 o Office 365.
    
- Larghezza di banda totale necessaria per ogni classe di servizio necessaria per supportare Skype for Business app usate in Dewey Law LLC. Il requisito della larghezza di banda del servizio è basato sul volume di traffico previsto da ognuna delle varie applicazioni di Skype for Business come voce, video, messaggistica istantanea, presenza e condivisione dello schermo.
    
### <a name="determining-bandwidth-requirements-for-skype-for-business-applications"></a>Determinazione dei requisiti di larghezza di banda per Skype for Business applicazioni

Per Dewey Law LLC., dopo aver determinato la larghezza di banda totale richiesta, è ora necessario sapere come dividere la quantità totale di larghezza di banda tra le varie classi di servizio. Ad esempio, la quantità di larghezza di banda per ogni Skype for Business applicazione.
  
Per determinare questi requisiti in ogni dewey Law LLC. si userà la calcolatrice della larghezza di banda di [Lync 2010 e 2013.](https://go.microsoft.com/fwlink/?LinkID=690282) Questa calcolatrice è uno strumento Excel che consente di specificare l'uso previsto delle varie applicazioni di Skype for Business, tra cui voce, video, conferenze e condivisione dello schermo. La calcolatrice genererà automaticamente una stima della larghezza di banda e dei requisiti cos per ogni sito della rete. Quando si scarica La calcolatrice della larghezza di banda di Lync 2010 e 2013, viene scaricata anche la guida dell'utente che fornisce dettagli sull'uso. 
  
Per facilitare l'esecuzione del foglio di calcolo, le varie celle del foglio di calcolo sono codificate a colori:
  
- **Verde** Si tratta di aree generali di input dei dati.
    
- **Giallo** Si tratta di aree avanzate di input dei dati. È possibile modificarli, ma procedere con attenzione.
    
- **Rosso** Si tratta di aree di sola lettura e sono valori di input bloccati e non possono essere modificati.
    
- **Grigio** Si tratta di aree di sola visualizzazione. Si tratta dei risultati o dei dati provenienti dalle aree di input generali.
    
Processo di progettazione per Dewey Law LLC. inizia caratterizzando gli utenti in diversi "Persona". Per ogni persona definita, è possibile specificare l'uso previsto delle varie applicazioni Skype for Business ('Nessuno', 'Basso', 'Medio', 'Alto' o una delle tre impostazioni "Personalizzate" definite). Queste selezioni si trovano nel foglio di lavoro "Persona". Viene fornito l'utilizzo specifico per ogni scelta ('Bassa', 'Media' o 'Alta'), ma è possibile modificare le impostazioni predefinite per ogni scelta. Identificando il numero di utenti per ogni persona che si trova in ogni sito, la calcolatrice può calcolare la larghezza di banda totale necessaria per ogni posizione.
  
È anche possibile specificare i codec audio e video usati, se viene usata la correzione degli errori di inoltro e altri parametri di sistema che influiranno sui requisiti di larghezza di banda. È possibile usare le impostazioni predefinite in Bandwidth Calculator di Lync 2010 e 2013 oppure selezionare codec e altri parametri di sistema diversi. Per la progettazione del sito di Dewey Law LLC, è possibile usare le impostazioni predefinite. Tuttavia, per passare da una delle impostazioni predefinite è disponibile un menu a discesa con tutte le opzioni disponibili. Le larghezze di banda usate per ogni scelta sono incluse nel foglio di lavoro "Codec". Quando si modifica qualsiasi impostazione, la modifica della larghezza di banda e della combinazione di classe di servizio (CoS) in ogni sito viene aggiornata. Questa funzionalità consente di testare diverse configurazioni potenziali e di verificare l'impatto delle modifiche sui requisiti di larghezza di banda.
  
Abbiamo definito tre persone per Dewey Law LLC., 'Executive/Partner', 'Associate/Paralegal' e 'IT admins'. La tabella seguente mostra come sono stati impostati i profili di utilizzo per le varie app Skype for Business per ogni persona.
  
 **Persona e profili di utilizzo (foglio di lavoro 'Persona' - Colonne da A a P)**
  
|**Persona**|**Messaggistica istantanea/Presenza**|**Audio P2P**|**Video P2P**|**Audio dei servizi di conferenza**|**Video di conferenza**|**Condivisione desktop**|**Audioconferenza**|**Lync 2010 RTV_Type**|**Utenti remoti**|**Audio stereo di Lync 2013**|**Qualità video di Lync 2013**|**Comportamento degli utenti di Lync 2013 per la finestra video P2P**|**Uso multi visualizzazione di Lync 2013**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Executive/Partner  <br/> |Alta  <br/> |Media.  <br/> |Bassa  <br/> |Media.  <br/> |Media.  <br/> |Nessuno  <br/> |Media.  <br/> |CIF  <br/> |0%  <br/> |0%  <br/> |Migliore  <br/> |Tipico  <br/> |Tipico  <br/> |
|Associate/Paralegal  <br/> |Alta  <br/> |Media.  <br/> |Bassa  <br/> |Media.  <br/> |Alta  <br/> |Alta  <br/> |Media.  <br/> |CIF  <br/> |0%  <br/> |0%  <br/> |Media.  <br/> |Tipico  <br/> |Tipico  <br/> |
|Amministratori IT  <br/> |Alta  <br/> |Media.  <br/> |Nessuno  <br/> |Bassa  <br/> |Nessuno  <br/> |Nessuno  <br/> |Media.  <br/> |CIF  <br/> |0%  <br/> |0%  <br/> |Media.  <br/> |Tipico  <br/> |Tipico  <br/> |
   
È necessario immettere le informazioni  nella tabella Distribuzione degli utenti per posizioni e posizioni riportata sopra nel foglio di lavoro "Siti" della calcolatrice della larghezza di banda di Lync 2010 e 2013. Poiché il numero di utenti negli uffici locali è identico, vengono definiti per un 'sito' e vengono specificate tre istanze. Lo stesso è stato fatto per le filiali grandi e piccole in cui nei siti c'erano rispettivamente 24 e 50 utenti.
  
Dopo aver specificato le impostazioni per ogni persona, è necessario immettere il numero di utenti in ogni persona in ogni sito nel foglio di lavoro "Siti". Il totale degli utenti per tutti i siti viene aggiornato automaticamente. Poiché non ci sono utenti nella posizione Microsoft 365 o Office 365, devono essere immessi tutti nelle righe "Rami" del foglio di lavoro. La calcolatrice della larghezza di banda di Lync 2010 e 2013 popola quindi le colonne "Classe di traffico dati", "Classe di traffico dati" e "Classe di traffico in tempo reale" nella tabella "WAN BW per classe di traffico QoS". Questa opzione è illustrata nei dati della tabella seguente.
  
> [!TIP]
>  Il foglio di calcolo completo include anche il numero massimo di sessioni simultanee per ogni applicazione, ma le colonne sono state eliminate per risparmiare spazio.
  
 **Personas by site - ('Sites' Worksheet- Columns A, D, I and AI through AX)**
  
|**Nome sito**|**Totale utenti nel sito**|**Totale siti come questo**|**Profilo utente 1**|**Utente del profilo 1**|**Profilo utente 2**|**Utente del profilo 2**|**Profilo utente 3**|**Utente del profilo 3**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sede centrale  <br/> |1070  <br/> |1  <br/> |Executive/Partner  <br/> |170  <br/> |Associate/Paralegal  <br/> |700  <br/> |Amministratori IT  <br/> |200  <br/> |
|Uffici locali  <br/> |345  <br/> |3  <br/> |Executive/Partner  <br/> |60  <br/> |Associate/Paralegal  <br/> |225  <br/> |Amministratore IT  <br/> |60  <br/> |
|Filiali di grandi dimensioni  <br/> |70  <br/> |24  <br/> |Executive/Partner  <br/> |11  <br/> |Associate/Paralegal  <br/> |50  <br/> |Amministratore IT  <br/> |9  <br/> |
|Filiali di piccole dimensioni  <br/> |36  <br/> |50  <br/> |Executive/Partner  <br/> |6  <br/> |Associate/Paralegal  <br/> |25  <br/> |Amministratore IT  <br/> |1  <br/> |
   
 **Larghezza di banda richiesta per ogni applicazione per sito in Kbps ('Foglio di lavoro Siti'- Colonne da A a BQ a LF)**
  
|**Sito**|**Picco di larghezza di banda SIP/messaggistica istantanea**|**Larghezza di banda Peer Audio tra siti di punta**|**Larghezza di banda video peer tra siti di punta**|**Larghezza di banda dei servizi di audioconferenza di punta**|**Larghezza di banda delle videoconferenze di punta**|**Larghezza di banda della condivisione WAN di punta**|**Larghezza di banda WAN di punta per le chiamate PSTN**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sede centrale  <br/> |1070  <br/> |525.30  <br/> |560.00  <br/> |739.50  <br/> |2640.00  <br/> |4224.00  <br/> |2688.30  <br/> |
|Uffici regionali  <br/> |345  <br/> |185.40  <br/> |560.00  <br/> |255.00  <br/> |1320.00  <br/> |1536.00  <br/> |896.10  <br/> |
|Diramazioni di grandi dimensioni  <br/> |70  <br/> |92.70  <br/> |560.00  <br/> |102.00  <br/> |600.00  <br/> |384.00  <br/> |216.30  <br/> |
|Diramazioni di piccole dimensioni  <br/> |36  <br/> |119.40  <br/> |560.00  <br/> |76.50  <br/> |600.00  <br/> |384.00  <br/> |123.60  <br/> |
   
Probabilmente le colonne più importanti del foglio di calcolo sono quelle che descrivono la larghezza di banda WAN in base alla classe QoS. Questa opzione è illustrata nella tabella seguente. Questi dati riepilogano le informazioni che è necessario fornire al provider di servizi di rete per ordinare la connessione di accesso in ogni sito. Quando si calcola la larghezza di banda totale, ricordarsi di moltiplicare la larghezza di banda per ogni tipo di sito di succursale per il numero di siti dello stesso tipo. Per connettersi con il partner dei servizi di rete ExpressRoute, è possibile vedere [Azure ExpressRoute.]( https://go.microsoft.com/fwlink/?LinkId=690283)
  
È molto importante non superare la larghezza di banda nella classe di servizio "Inoltro accelerato" (EF). Un set casuale di pacchetti verrà eliminato, quindi, invece di ridurre la qualità di una singola chiamata o di un gruppo di chiamate, tutte le chiamate in corso possono essere influenzate. È anche importante che solo la voce sia contrassegnata con DSCP per EF (ad esempio DSCP = 46) o che la coda vocale possa traboccare quando viene aggiunto traffico non vocale.
  
> [!TIP]
>  Anche in questo caso, mentre la classe di servizio EF offre la migliore garanzia delle prestazioni, se si supera la larghezza di banda definita, eventuali pacchetti aggiuntivi verranno immediatamente eliminati.
  
 **Larghezza di banda aggregata per sito in base alla classe di traffico QoS ( Foglio di lavoro dei siti - Colonne A e ML tramite MR)**
  
|**Nome sito**|**Classe best effort (DSCP 0)**|**Classe di traffico dati (personalizzata DSCP)**|**Classe di traffico in tempo reale (DSCP 34, AF41)**|**Classe di traffico prioritario (DSCP 46, EF)**|
|:-----|:-----|:-----|:-----|:-----|
|Sede centrale  <br/> |0.00  <br/> |5764.80  <br/> |3200.00  <br/> |3953.10  <br/> |
|Uffici regionali  <br/> |0.00  <br/> |2033.60  <br/> |1880.00  <br/> |1336.50  <br/> |
|Diramazioni di grandi dimensioni  <br/> |0.00  <br/> |486.40  <br/> |1160.00  <br/> |411.00  <br/> |
|Diramazioni di piccole dimensioni  <br/> |0.00  <br/> |438.40  <br/> |1160.00  <br/> |319.50  <br/> |
   
### <a name="putting-your-plan-into-action"></a>Mettere in azione il piano

È possibile calcolare la larghezza di banda totale che attraverserà la WAN e la quantità di larghezza di banda che attraverserà ExpressRoute, usando le stime della larghezza di banda della **tabella Per applicazione per** sito riportata sopra. La parte di traffico che attraversa ExpressRoute esclude la larghezza di banda peer tra siti.

 
|**Sito**|**Picco di larghezza di banda SIP/messaggistica istantanea**|**Larghezza di banda dei servizi di audioconferenza di punta**|**Larghezza di banda delle videoconferenze di punta**|**Larghezza di banda della condivisione WAN di punta**|**Larghezza di banda WAN di punta per le chiamate PSTN**|**Traffico ExpressRoute <br/> totale per classe di siti <br/> (ad esempio, tempo <br/> totale # di siti)**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Sede centrale** <br/> |1,070  <br/> |739.50  <br/> |2640.00  <br/> |4224.00  <br/> |2688.30  <br/> |11361.80  <br/> |
|**Uffici regionali** <br/> |345  <br/> |255.00  <br/> |1320.00  <br/> |1536.00  <br/> |896.10  <br/> |8704.20  <br/> |
|**Diramazioni di grandi dimensioni** <br/> |70  <br/> |102.00  <br/> |600.00  <br/> |384.00  <br/> |216.30  <br/> |32935.20  <br/> |
|**Diramazioni di piccole dimensioni** <br/> |36  <br/> |76.50  <br/> |600.00  <br/> |384.00  <br/> |123.60  <br/> |61005.00  <br/> |
   
Questo significa che Skype for Business online che attraverserà il percorso rapido sarà di circa 114 Mbps, quindi Dewey avrà bisogno di almeno l'abbonamento a 200 Mbps per ExpressRoute. È possibile acquistare più circuiti ExpressRoute in posizioni di peering ExpressRoute diverse. Questa opzione può essere consigliata se i siti di Dewey si verificano in aree geografiche diverse o per garantire la resilienza nel caso in cui la connessione al circuito ExpressRoute non riesca. Se si acquistano circuiti ExpressRoute in più aree geografiche di Azure, il componente aggiuntivo ExpressRoute Premium sarà necessario per ricevere la connettività globale tramite ExpressRoute.
  
Ora che si ha la quantità totale di larghezza di banda richiesta e i numeri di larghezza di banda della classe di servizio (CoS) è possibile eseguire gli ordini con i provider di servizi di rete selezionati. Non dimenticare di includere le stime per il traffico per altre applicazioni e servizi. Sono disponibili indicazioni per la pianificazione della rete per altri Microsoft 365 e Office 365, inclusi i calcolatori della larghezza di banda per Exchange e OneDrive. L'abbonamento alla larghezza di banda per il provider di servizi di rete sarà più alto perché sarà necessario aggiungere di nuovo il traffico all'interno del sito. La calcolatrice della larghezza di banda di Lync 2010 e 2013 fornisce solo una stima del traffico previsto, pertanto è consigliabile confermare la capacità della rete di supportare quel volume di traffico che esegue un test di stress. 
  
> [!TIP]
> I test di stress per la rete sono consigliati quando si esegue una prevalutazione della rete. 
  
Un test di stress implica la creazione e la configurazione dell'infrastruttura e quindi l'esecuzione con il volume previsto di traffico simulato durante il monitoraggio delle prestazioni. Le stime del traffico potrebbero non essere accurate in alcune aree, ma almeno si può essere certi che sia in grado di supportare il volume di traffico previsto dalla calcolatrice della larghezza di banda di Lync 2010 e 2013. È consigliabile eseguire il test di stress per un minimo di alcuni giorni, ma eseguirlo per periodi di tempo più lunghi può essere utile per perfezionare i numeri. Tuttavia, l'estensione del periodo di stress test deve essere valutata in base al costo dei servizi di rete che si stanno pagando che non trasportano traffico di rete degli utenti reali. Microsoft ha certificato diversi fornitori nell'ambito del programma IT Pro Tools per la gestione della rete e gli strumenti per le operazioni, inclusi gli strumenti di stress pre-valutazione della rete. Skype for Business fornisce anche un System Integrators (SI) che può usare gli strumenti di Pro IT certificati e che può eseguire la valutazione della rete. Per altre informazioni, vedere [Skype for Business Solutions: IT Pro Tools](https://go.microsoft.com/fwlink/?LinkID=690307).
  
I test di stress assicurano che la rete sia in grado di supportare il volume di traffico necessario, ma in realtà i dati di Bandwidth Calculator di Lync 2010 e 2013 possono essere disattivati per diversi motivi. È anche consigliabile continuare a monitorare le reti dei siti eseguendo una valutazione continua della rete dopo la distribuzione per assicurarsi che la larghezza di banda sia sufficiente e che i meccanismi QoS funzionino correttamente. È importante continuare a monitorare le prestazioni di rete con l'applicazione di un numero sempre maggiore di utenti reali.
  
## <a name="part-2-expressroute-skype-for-business-qos"></a>Parte 2: ExpressRoute Skype for Business QoS

Il servizio ExpressRoute di Microsoft fornisce una connessione dedicata al cloud Azure, ma i servizi di comunicazione dei carichi di lavoro in tempo reale di Office 365 richiederanno servizi di rete con larghezza di banda sufficiente per supportare il volume di traffico e sono in grado di supportare la qualità del servizio (QoS) per offrire un'esperienza utente di livello aziendale. Una connessione che supporta la QoS deve essere configurata end-to-end (PC, switch di rete e router nel cloud) in quanto qualsiasi parte del percorso che non supporta QoS potrebbe compromettere la qualità dell'intera chiamata.
  
Lo scopo di questa sezione è aiutare a comprendere le sfide che si verificano quando si supporta il traffico in tempo reale in una rete IP e si configura e si supporta una distribuzione ExpressRoute di carichi di lavoro Microsoft 365 o Office 365 in tempo reale usando un partner microsoft expressroute Exchange Provider o provider di servizi di rete.
  
La QoS viene accettata dalle reti esclusivamente su circuiti di rete ExpressRoute e viene usata all'interno della rete Microsoft per Skype for Business traffico. Attualmente, alcune connessioni in uscita da Microsoft non hanno valori DSCP per Skype for Business. Finché il traffico in uscita non viene completamente contrassegnato con i valori DSCP, è consigliato seguire le linee guida per l'aggiunta di contrassegni QoS al traffico al confine di rete, come descritto nella sezione Implementazione di **QoS** con l'elenco di controllo di accesso di rete di questo articolo.
  
### <a name="the-real-time-problem"></a>Il problema in tempo reale

La fornitura di servizi vocali e video di qualità aziendale pone esigenze speciali in una rete IP. Il traffico in tempo reale usa il protocollo RTP (Real-time Transport Protocol) che viene trasportato tramite UDP (User Datagram Protocol). A differenza del protocollo TCP (Transmission Control Protocol), che numeri e verifica la presenza di errori in ogni messaggio e include altri meccanismi per rilevare e ritrasmettere messaggi persi o con errori, UDP non fornisce l'affidabilità di questo tipo. Se i messaggi sono danneggiati da errori o vengono persi a causa dell'overflow del buffer, vengono persi. UDP è stato scelto per l'uso con RTP perché la natura del traffico in tempo reale è che, anche se i messaggi persi erano risentiti, sarebbero arrivati troppo tardi per avere un impatto positivo sul flusso dei messaggi vocali.
  
Conoscendo l'impatto dei pacchetti vocali persi, i progettisti hanno evoluta due approcci per migliorare le prestazioni di voce e video su IP:
  
- Rendere la codifica/decodifica vocale più resiliente quando i pacchetti vengono persi. Questa operazione può essere eseguita usando la correzione degli errori in avanti (FEC) per correggere una percentuale degli errori rilevati, una funzionalità disponibile in Microsoft 365 o Office 365 Real Time Transport, oppure progettando sistemi di decodifica vocale che tentano di mascherare l'effetto dei pacchetti persi, caratteristica dei codec Microsoft. 
    
- Usare i servizi di trasporto che usano meccanismi di qualità del servizio per garantire le prestazioni della rete per quanto riguarda il ritardo, la perdita e l'instabilità dei pacchetti e la variazione del ritardo tra i pacchetti.
    
La codifica vocale resiliente risolve solo il problema della perdita di pacchetti, quindi è importante che una rete usata per portare voce e video in tempo reale abbia meccanismi che riducono al minimo il ritardo e l'instabilità. Anche con la codifica resiliente, se si perdono troppi pacchetti, la stazione ricevente non ha informazioni sufficienti per ricostruire una versione riconoscibile del segnale vocale. Percentuale di pacchetti persi che causano una notevole riduzione della qualità vocale, che varia a seconda della tecnica di codifica vocale usata. In tutti i casi, tuttavia, la perdita di stringhe di pacchetti successivi è molto problematica.
  
Ridurre al minimo il ritardo è importante perché un ritardo eccessivo può influire sul flusso della conversazione e creare fastidio per gli altoparlanti. Le procedure consigliate ci dicono che il ritardo end-to-end per la voce (quello che viene definito ritardo "bocca a orecchio") deve essere mantenuto al di sotto di 150 millisecondi (msec). unidiresfera, non un ritardo di "andata e ritorno". Naturalmente il ritardo aumenterà sui collegamenti di trasmissione più lunghi, come quelli che attraversano gli oceani, in base al ritardo di propagazione o al tempo necessario per il viaggio fisico del segnale sul cavo.
  
Quando il ritardo è superiore a 150 msec. unidirettivo, ha un effetto strano sull'altoparlante. Dal punto di vista psicologico, nel cervello dell'altoparlante si spegne un orologio che fa pensare che il destinatario non li abbia sentiti e che ripeta l'ultima cosa che ha detto. Questo conflitto con la risposta ritardata proveniente dall'estremo. Se hai mai parlato su un canale satellitare, riconoscerai questo effetto. Su un canale satellitare il ritardo unidireale è di circa 250 msec, che è ben oltre il ritardo consentito.
  
 **Parametri di rete consigliati per la voce di livello aziendale**
  
|**Parametro**|**Valore consigliato**|
|:-----|:-----|
|Instabilità tra pacchetti in arrivo (media)  <br/> |≤ 5 ms  <br/> |
|Instabilità pacchetti tra arrivi (massimo)  <br/> |≤ 40 ms  <br/> |
|Tasso di perdita pacchetti (media)  <br/> |0% in avvicinamento  <br/> |
|Latenza di rete unidiret  <br/> |≤ 100ms (dovrebbe includere i controlli sul ritardo rispetto alla distanza geografica)  <br/> |
   
### <a name="expressroute-as-part-of-a-business-grade-voice-network"></a>ExpressRoute come parte di una rete vocale di livello aziendale

ExpressRoute offre una connessione dedicata tramite un provider di servizi di rete (NSP) o un provider di Exchange (EXP) in una delle tre opzioni di connessione seguenti: 
  
- Colocation Exchange cloud
    
- Connessione Ethernet point-to-point
    
- Connessione Any-to-Any (IPVPN)
    
Questo offre i vantaggi della disponibilità elevata (contratto di servizio per il tempo di attività del 99,9%) e del routing affidabile sicuro (senza transito Internet), inalterato dalle variazioni del traffico Internet e rispetta i contrassegni qualità del servizio per assegnare priorità al traffico (la QoS è illustrata di seguito). ExpressRoute, insieme a una WAN ben pianificata, può fornire una rete vocale di livello aziendale.
  
È possibile usare ExpressRoute per il transito dei dati da uffici o data center (se topologia ibrida) connessi al circuito. I dati per gli utenti fuori sede ,ad esempio da uffici privati o in viaggio e così via, non sfruttano il circuito ExpressRoute a meno che gli utenti non siano connessi tramite VPN e non siano inclusi nelle stime della larghezza di banda per il dimensionamento del circuito ExpressRoute. Se si è un cliente multi-nazionale, è possibile acquistare circuiti ExpressRoute in ogni area geografica e usare i tag della community BGP per informare le regole di routing in modo che il traffico venga indirizzato al circuito ExpressRoute preferito (in genere quello più vicino per ogni sito), mentre gli altri circuiti offrono ridondanza in caso di interruzione che interessa un singolo circuito. 
  
### <a name="if-expressroute-isnt-an-option"></a>Se ExpressRoute non è un'opzione

Potrebbe non essere possibile connettere tutti i siti a ExpressRoute, a causa dei costi, dell'impossibilità di soddisfare i prerequisiti di ExpressRoute o delle limitazioni del provider di servizi di rete corrente. Se non si può usare ExpressRoute, è comunque consigliabile seguire le indicazioni seguenti per contrassegnare QoS all'interno della rete e pianificare i contratti con il provider di servizi di rete per garantire larghezza di banda e supporto sufficienti per la definizione delle priorità del traffico in base a QoS.
  
Inoltre, se si hanno uffici in più aree geografiche, ma non si hanno circuiti ExpressRoute in tutte le aree geografiche, è consigliabile usare i tag della community BGP dell'area quando si configura il routing per il traffico da/verso gli uffici satellitari in modo da evitare inutili transiti a lungo raggio. Si consideri ad esempio una società che ha un'organizzazione di Skype for Business Online ospitata negli Stati Uniti, ma con filiali in Europa e che ha un solo circuito ExpressRoute nella Silicon Valley. La maggior parte del traffico di Skype for Business Online verrà instradato a un data center in cui è ospitata l'organizzazione (ad esempio, conferenze telefoniche con altri utenti all'interno dell'azienda), l'uso del circuito ExpressRoute può essere preferito per la maggior parte del traffico. Tuttavia, se un utente in Europa partecipasse a una conferenza telefonica ospitata da un'altra società la cui organizzazione si trova in Europa, la destinazione per i media in quella chiamata sarebbe il data center europeo in cui si trova la seconda società. Il routing del traffico attraverso il circuito ExpressRoute nella Silicon Valley sarebbe un percorso meno diretto di quanto sarebbe possibile tramite Internet. In questo caso, è possibile configurare i router all'interno della rete,ad esempio presso gli uffici europei, in modo da controllare i tag della community quando si effettuano le regole di routing e il routing tramite Internet anziché tramite il circuito ExpressRoute della Silicon Valley per il traffico con tag dell'area geografica europea.
  
### <a name="basic-concepts-of-quality-of-service-qosclass-of-service-cos"></a>Concetti di base di QoS (Quality of Service)/Class of Service (CoS)

In IP, quality of service (QoS) descrive qualsiasi meccanismo usato per fornire la gestione prioritaria di alcuni pacchetti rispetto ad altri. In base alla definizione ITU (International Telecommunications Union), la QoS comprende tutti gli aspetti qualitativi di una connessione, tra cui ritardo, perdita, rapporto segnale-rumore, crosstalk, eco, interrupt, risposta di frequenza, livelli di rumorosità e così via. Ciò che viene chiamato QoS nelle reti di pacchetti è più correttamente chiamato Classe di servizio (CoS) che si concentra sul miglioramento delle prestazioni per ritardi, instabilità e perdita di pacchetti, ma continueremo a usare il termine QoS in quanto viene usato più comunemente.
  
La fornitura di QoS in una rete IP richiede due componenti principali:
  
- Prenotazione di una quantità definita di larghezza di banda in ogni collegamento per il traffico in tempo reale; se la larghezza di banda non è necessaria per il traffico in tempo reale in qualsiasi momento, può essere usata per altro traffico. La guida generale indica che per il traffico vocale non deve essere assegnato più del 30% della capacità di qualsiasi collegamento.
    
- Contrassegno dei pacchetti con un indicatore di priorità nell'intestazione che indica agli switch e ai router nel percorso la priorità del pacchetto da assegnare.
    
Quando un pacchetto viene ricevuto presso uno switch o un router, viene spostato in una coda di output per il passaggio o l'hop successivo. Esistono code di output diverse per i diversi livelli di priorità. Un commutatore o un router usa un algoritmo che consente di utilizzare la coda con priorità alta più frequentemente rispetto alle code con priorità inferiore.
  
La sfida consiste nel fatto che esistono diverse tecniche di QoS implementate a livello 2 (ad esempio il livello Ethernet o Wi-Fi) e livello 3 (ad esempio il livello IP). Queste diverse implementazioni QoS possono essere configurate in ogni switch e router della rete, oltre che nell'interfaccia tra la rete e la rete del provider di servizi di rete.
  
Esistono due opzioni per il mapping dei dati delle varie applicazioni Skype for Business alle classi di servizio appropriate:
  
- Contrassegno del punto finale del traffico tramite DSCP (Differentiated Services Control Point) 
    
- Basato sull'elenco di controllo di accesso di rete (ACL)
    
### <a name="end-point-traffic-marking--differentiated-services-control-point-dscp"></a>Contrassegno traffico punto finale- Punto di controllo servizi differenziati (DSCP)

I servizi differenziati (DiffServ) sono definiti meccanismi a grana grosso modo per classificare e gestire il traffico di rete e fornire QoS nelle reti IP. I router e altri dispositivi che implementano le funzioni di livello 3 usano il DSCP (DiffServ Control Point) per definire la priorità del pacchetto. La QoS viene implementata inserendo un valore DSCP a 6 bit nel campo Differentiated Services (in precedenza il campo "Type of Service") nell'intestazione IP; I 6 bit consentono 64 livelli di priorità diversi. I livelli di priorità sono in genere definiti come illustrato di seguito.
  
 **Impostazioni DSCP consigliate**
  
|**Classe di traffico**|**Trattamento (contrassegno DSCP)**|**Skype for Business di lavoro**|
|:-----|:-----|:-----|
|**Opzioni vocali** <br/> |EF (46)  <br/> |Skype for Business e voce di Lync  <br/> |
|**Interattivo** <br/> |AF41 (34)  <br/> |Video  <br/> |
||AF21 (18)  <br/> |Condivisione applicazioni  <br/> |
|**Impostazione predefinita** <br/> |AF11 (10)  <br/> |Trasferimento di file  <br/> |
||CS0 (0)  <br/> |Qualsiasi altra cosa  <br/> |
   
 **Intestazione IP versione 4**
  
![Intestazione IPv4.](../images/c8a6a714-2784-4328-8297-2e62706f302d.png)
  
### <a name="layer-2-qos-ieee-8021pwi-fi-multi-media-ieee-80211e"></a>QoS di livello 2: IEEE 802.1p/Wi-Fi Multi-Media (IEEE 802.11e)

Anche se DSCP è il meccanismo standard per l'implementazione di QoS al livello 3, esistono diversi meccanismi di QoS di livello 2 per reti cablate (ad esempio Ethernet) e wireless (ad esempio reti Wi-Fi). Il meccanismo QoS per le reti cablate è definito nello standard IEEE 802.1p; il meccanismo QoS WLAN è definito in IEEE 802.11e, che la Wi-Fi Alliance identifica come "Certificato Multi-Media Wi-Fi" (certificato WMM).
  
IEEE 802.1p usa un priority code point (PCP) a 3 bit per identificare la priorità del messaggio. il PCP fa parte di un campo a 32 bit nell'intestazione Ethernet che contiene anche l'identificatore VLAN. Le definizioni per i valori PCP sono incluse di seguito.
  
 **Valori PCP IEEE 802.1p**
  
|**Valore PCP**|**Priority**|**Acronimo**|**Tipi di traffico**|
|:-----|:-----|:-----|:-----|
|7  <br/> |7  <br/> |NC  <br/> |Controllo della rete  <br/> |
|6  <br/> |6  <br/> |IC  <br/> |Controllo Internetwork  <br/> |
|5  <br/> |5  <br/> |VO  <br/> |Opzioni vocali  <br/> |
|4  <br/> |4  <br/> |VI  <br/> |Video  <br/> |
|3  <br/> |3  <br/> |CA  <br/> |Applicazioni critiche  <br/> |
|2  <br/> |2  <br/> |EE  <br/> |Ottimo lavoro  <br/> |
|0  <br/> |1  <br/> |BE  <br/> |Attività ottimali  <br/> |
|1  <br/> |0  <br/> |BK  <br/> |Sfondo  <br/> |
   
Dove IEEE 802.1p viene implementato in modo molto diverso rispetto a DSCP con il traffico ordinato in code di priorità diverse per ogni livello di priorità, ma la natura multimediale condivisa delle reti WLAN richiede un approccio diverso. Mentre il punto di accesso e il client mantengono code di output separate per i diversi livelli di priorità, esistono anche differenze nel modo in cui i frame vengono inviati nel canale radio.
  
In una rete Wi-Fi, tutti i client associati a un punto di accesso condividono un unico canale half-duplex, ad esempio solo una stazione client o un punto di accesso alla volta. Per ridurre al minimo il potenziale di collisioni sul canale radio, prima di inviare un fotogramma la stazione attende che il canale sia inattivo per un periodo di tempo definito denominato "Inter-Frame Spacing", se il canale è occupato quando una stazione va a inviare, viene riattivato da un periodo di tempo casuale. Dopo l'invio del frame, se il mittente non riceve un messaggio di riconoscimento dal destinatario, presuppone che si sia verificato un conflitto o un altro errore e che venga eseguito un intervallo casuale prima di tentare di accedere al canale radio per inviarlo di nuovo. L'intervallo di back-off è casuale per ridurre la probabilità che le stesse due stazioni si scontrano di nuovo.
  
Per assegnare priorità all'accesso al canale radio, IEEE 802.11e/WMM definisce diversi intervalli di attesa pre-trasmissione denominati "Spaziature Inter-Frame arbitrate" (AFIS) e intervalli di back-off diversi per le diverse classi di traffico; Sono definiti quattro livelli di priorità denominati "Categorie di accesso".
  
La priorità viene assegnata assegnando valori AFIS più brevi ai frame con priorità più alta. Quindi, se una stazione è in attesa di inviare una cornice vocale e un'altra è in attesa di inviare un frame di dati, la cornice vocale verrà sempre inviata per prima. Tecnicamente, ai fotogrammi vocali e video viene assegnato lo stesso valore AFIS, ma l'intervallo di intervalli di back-off per i fotogrammi video è maggiore. Quindi, mentre un fotogramma vocale e video può collidere al primo tentativo, il fotogramma vocale verrà sempre ritrasmesso prima. La correlazione tra IEEE 802.1p e IEEE 802.11e è illustrata di seguito:
  
 **Mapping da IEEE 802.11e/Wi-Fi Multi-Media (WMM) a 802.1P**
  
|**Categoria di accesso WMM**|**Descrizione WMM**|**Valore PCP 802.1P**|**Designazione 802.1P**|
|:-----|:-----|:-----|:-----|
|1 (AC_VO)  <br/> |Opzioni vocali  <br/> |7 (111)  <br/> |NC  <br/> |
|6 (110)  <br/> |VO  <br/> |
|2 (AC_VI)  <br/> |Video  <br/> |5 (101)  <br/> |VI  <br/> |
|4 (100)  <br/> |CL  <br/> |
|3 (AC_BE)  <br/> |Dati delle migliori risorse  <br/> |3 (011)  <br/> |EE  <br/> |
|0 (000)  <br/> |BE  <br/> |
|4 (AC_BK)  <br/> |Dati di sfondo  <br/> |1 (001)  <br/> |BK  <br/> |
|2 (010)  <br/> |---  <br/> |
   
L'associazione consigliata delle priorità di livello 3 a livello 2 è illustrata di seguito:
  
 **Associazioni di priorità consigliate dal livello 3 al livello 2**
  
|&nbsp; |**Contrassegni di livello 3**|**Livello 2 (valore PCP)**|**Wi-Fi (categoria di accesso)**|
|:-----|:-----|:-----|:-----|
|Controllo della rete  <br/> |Per Hop Behavior (PHB) - Class Selector (CS) 6  <br/> |6  <br/> |1 (AC_VO)  <br/> |
|Valore DSCP -48  <br/> |
|Opzioni vocali  <br/> |Comportamento per hop (PHB) -Expedited Forwarding (EF)  <br/> |5  <br/> |1 (AC_VO)  <br/> |
|Valore DSCP - 46  <br/> |
|Videoconferenze  <br/> |Comportamento per hop (PHB) - Assured Forwarding (AF) 41  <br/> |4  <br/> |2 (AC_VI)  <br/> |
|Valore DSCP - 34  <br/> |
|Segnalazione chiamata  <br/> |Per Hop Behavior (PHB) - Class Selector (CS) 3  <br/> |3  <br/> |2 (AC_VI)  <br/> |
|Valore DSCP - 24  <br/> |
|Dati a bassa latenza  <br/> |Comportamento per hop (PHB) -Assured Forwarding (AF) 21  <br/> |2  <br/> |3 (AC_BE)  <br/> |
|Valore DSCP -18  <br/> |
|Dati ad alta velocità effettiva  <br/> |Comportamento per hop (PHB) - Assured Forwarding (AF) 11  <br/> |1  <br/> |3 (AC_BE)  <br/> |
|Valore DSCP - 10  <br/> |
|Attività ottimali  <br/> |Comportamento per hop (PHB) - 0  <br/> |0  <br/> |4 (AC_BK)  <br/> |
|Valore DSCP - 0  <br/> |
   
È importante notare che la codifica prioritaria per IEEE 802.1p e WMM non corrisponde. Il valore PCP 802.1p per la voce è 5, tuttavia, nel mapping di equivalenza standard a WMM, PCP 5 viene convertito in Access Category 2, la categoria di accesso WMM per il video (AC_VI). Se possibile, è consigliabile ignorare il mapping in modo che PCP 5 si traduca nella categoria 1 di Access o semplicemente evitare di usare voce e video nella stessa rete Wi-Fi finché Wi-Fi Alliance non risolve il problema. Per altre informazioni su Wi-Fi, vedere [Elementi del catalogo Wi-Fi.]( https://go.microsoft.com/fwlink/?LinkId=690322)
  
### <a name="implementing-qos-using-network-access-control-list-acl"></a>Implementazione di QoS con l'elenco di controllo di accesso di rete (ACL)

Il metodo alternativo per l'implementazione di QoS in una configurazione ExpressRoute consiste nell'usare l'elenco di controllo di accesso di rete (ACL). In questo approccio, invece di inserire il contrassegno DSCP appropriato nell'intestazione di ogni pacchetto, il contrassegno può essere eseguito da un router upstream, in base alla porta di origine UDP. Tutti gli switch e i router devono comunque essere configurati per supportare QoS per assicurarsi che le impostazioni DSCP siano mantenute. Ancora più importante, il router connesso alla rete del provider di servizi deve mantenere il DSCP nell'intestazione di ogni pacchetto, in quanto l'impostazione DSCP è essenzialmente l'istruzione al provider di servizi di rete su come deve essere trattato il pacchetto.
  
Gli intervalli di porte consigliati per ogni applicazione Skype for Business sono elencati nella sezione 2.6.1.1 della guida Pianificazione, monitoraggio e risoluzione dei problemi di rete con [Lync Server.](https://go.microsoft.com/fwlink/?LinkId=690286) È importante che questo approccio sia coordinato con l'approccio generale dell'organizzazione al QoS e che sia necessario essere alla ricerca di criteri QoS diversi e potenziali mancanze di commenti sui pacchetti.
  
Anche se il motivo principale per cui vengono usati i servizi di rete QoS e MPLS è garantire un'esperienza utente ottimale per voce e video in tempo reale, queste stesse funzionalità possono essere applicate anche alle applicazioni dati. Invece di trattare tutte le applicazioni allo stesso modo, le reti MPLS possono consentire alle organizzazioni di assegnare priorità ad alcune applicazioni di dati rispetto ad altre. Con MPLS, le applicazioni in tempo reale come le transazioni con carta di credito o la condivisione dello schermo possono avere la priorità su un traffico meno sensibile nel tempo, come la posta elettronica.
  
### <a name="understanding-the-types-of-ip-network-services--basic-ip-and-mpls"></a>Informazioni sui tipi di servizi di rete IP- IP di base e MPLS

L'inoltro di pacchetti IP originale ha funzionato in base al principio del "miglior sforzo". Questo significava che i router che inoltravano i pacchetti IP avrebbero fatto del loro meglio per recapitarli alle loro destinazioni, ma non c'era alcuna garanzia riguardo a quando o se sarebbero arrivati alle loro destinazioni. Ecco come funzionano oggi i servizi Internet di base, inclusa la connessione Internet domestica. L'idea era che, se fosse necessaria l'affidabilità per una particolare applicazione, sarebbe stata fornita a un livello superiore nello stack di protocolli. Il meccanismo di recapito affidabile è il protocollo TCP (Transmission Control Protocol). Il protocollo UDP (User Datagram Protocol), che viene usato per la voce e il video in tempo reale, è il meccanismo di distribuzione inaffidabile (ad esempio, "best effort"). 
  
Multi-Protocol Label Switching (MPLS) è stato sviluppato come mezzo per i provider di servizi di rete per offrire un servizio IP con garanzie di prestazioni per ritardi, instabilità e perdita di pacchetti. Per garantire queste garanzie di prestazioni, MPLS toglie parte dell'imprevedibilità dall'IP tradizionale. Prima di tutto, invece di fare in modo che ogni pacchetto trovi il suo percorso router-to-router verso la destinazione (il cui risultato potrebbe essere che ogni pacchetto prende una route diversa dall'origine alla destinazione), MPLS instrada tutti i pacchetti su una connessione "circuito virtuale" con un percorso fisso denominato percorso LSP (Label Switched Path). Se uno dei collegamenti in tale percorso non riesce, tutti i file LSP che usano tale collegamento vengono reindirizzati rapidamente.
  
Quando un pacchetto viene inviato nella rete MPLS, il router perimetrale del provider di servizi di rete aggiunge un'intestazione aggiuntiva al pacchetto che include un'etichetta usata per inoltrarlo sull'LSP appropriato. L'etichetta viene spogliata dal router perimetrale all'altra estremità della rete MPLS.
  
Oltre a semplificare il processo di inoltro, l'altro vantaggio offerto da MPLS è che il sistema di gestione della rete saprà quali connessioni vengono effettuate su ogni collegamento della rete. Controllando il modo in cui il traffico viene instradato attraverso la rete, l'operatore può garantire il QoS fornito da ogni percorso. Pertanto, a differenza delle prestazioni ottimali dell'IP tradizionale o di base, gli operatori MPLS possono fornire a un servizio IP prestazioni prevedibili. Questo LSP rende anche MPLS intrinsecamente più sicuro dei servizi Internet tradizionali. Quindi, con il servizio IP di base possiamo sperare che la rete funzioni abbastanza bene da fornire una buona qualità vocale e usare tecniche come FEC e una codifica vocale più resiliente per migliorare le probabilità, ma usando MPLS possiamo essere certi di questo.
  
I provider MPLS offrono diverse sfumature di classe di servizio che purtroppo usa termini diversi per identificarli. È necessario collaborare a stretto contatto con il provider per assicurarsi che comprenda gli output della calcolatrice della larghezza di banda di [Lync 2010 e 2013](https://go.microsoft.com/fwlink/?LinkID=690282) e le opzioni consigliate per diverse applicazioni Microsoft 365 o carichi di lavoro in tempo reale Office 365.
  
## <a name="conclusion"></a>Conclusione

Skype for Business migliora il modo in cui vengono condotte le comunicazioni aziendali. Invece di avere un telefono connesso a un PBX, un sistema di videoconferenza autonomo, una piattaforma separata per la posta elettronica, un servizio esterno per le audioconferenze e alcuni strumenti per la messaggistica istantanea e la presenza, Skype for Business può riunire tutte queste funzionalità in un'unica interfaccia utente.
  
La distribuzione coerente di servizi vocali e video in tempo reale richiede un'infrastruttura di rete end-to-end in grado di fornire QoS. Sono inclusi sia i servizi LAN che WAN. Microsoft fornisce strumenti come La calcolatrice della larghezza di banda di [Lync 2010 e 2013](https://go.microsoft.com/fwlink/?LinkID=690282) per stimare la capacità di rete necessaria per i vari servizi. Inoltre, ci sono partner nel programma IT Pro [Tools Skype for Business Solutions: IT Pro Tools](https://go.microsoft.com/fwlink/?LinkID=690307) che offrono strumenti per valutare in modo preliminare l'infrastruttura di rete e supportare il monitoraggio, la creazione di report e la risoluzione dei problemi. Senza un'infrastruttura di rete configurata correttamente, si rischia di avere una distribuzione di ExpressRoute Skype of Business che non soddisfi le aspettative degli utenti in fatto di qualità e coerenza.
  
Gli strumenti aziendali efficaci devono offrire prestazioni affidabili, coerenti e offrire un'esperienza utente che favorisca l'adozione degli utenti. Da un punto di vista di rete, questo significa avere un'infrastruttura di rete, sia locale che larga, fissa e mobile, che può consentire che ciò accada. Pianificare, progettare, implementare e mantenere tale infrastruttura non è sempre un'impresa facile. L'hardware, gli strumenti e i servizi di rete da realizzare oggi sono disponibili, ma è responsabilità del Pro IT vedere che sono progettati, implementati e gestiti in modo da garantire agli utenti un set di servizi di comunicazione e collaborazione che consentano loro di lavorare in modo efficiente ed efficace e che l'organizzazione possa trarre il massimo vantaggio da questa tecnologia. 
  
## <a name="related-topics"></a>Argomenti correlati

[Documentazione di ExpressRoute](/azure/expressroute/)

  
