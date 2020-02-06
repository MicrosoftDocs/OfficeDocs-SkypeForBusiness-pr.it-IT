---
title: Novità di Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2017
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e62c9229-b738-45ef-b637-0b58ca8225a4
description: 'Riepilogo: leggere questo argomento per informazioni sulle nuove funzionalità di Skype for Business Server 2015. Per informazioni dettagliate sulla nuova esperienza client, vedere Lync è ora Skype for business-Ecco le novità.'
ms.openlocfilehash: 0a11c94f7c31b0140a256ab350f5dad6112bc71e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824080"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Novità di Skype for Business Server 2015

**Riepilogo:** Leggere questo argomento per informazioni sulle nuove funzionalità di Skype for Business Server 2015. Per informazioni dettagliate sulla nuova esperienza client, vedere [Lync è ora Skype for business-](https://go.microsoft.com/fwlink/p/?LinkId=529022)Ecco le novità.
  
Lync è ora Skype for business, una piattaforma di comunicazione e collaborazione che riunisce un'esperienza ispirata da Skype con la sicurezza, la conformità e il controllo a livello aziendale di Lync. Skype for business offre funzionalità che includono la presenza, la messaggistica istantanea, le chiamate vocali e video e le riunioni online. Skype for business offre una nuova esperienza client, una nuova versione del server e gli aggiornamenti del servizio in Office 365. Se gli utenti dell'organizzazione hanno già familiarità con Skype, apprezzeranno la potenza e la semplicità di Skype for business, dove è facile trovare e connettersi con i colleghi. Se gli utenti dell'organizzazione arrivano a Skype for business da Lync, riconoscono tutte le funzionalità che già usano, ma in una nuova interfaccia fresca con controlli semplificati e nuove aggiunte. Oltre alla nuova esperienza client, Skype for Business Server 2015 offre diverse nuove funzionalità per migliorare la gestibilità dei server locali e delle soluzioni ibride.
  
Le nuove funzionalità di Skype for Business Server 2015 includono miglioramenti per:
  
- Esperienza utente  
- Supporto per la voce e il video
- Supporto per dispositivi mobili
- Gestione dei server locali
- Distribuzione e gestione di soluzioni ibride
- Supporto per l'autenticazione a più fattori
    
## <a name="user-experience"></a>Esperienza utente

Il client Skype for business ha un aspetto molto simile alla versione consumer di Skype e usa gli stessi pulsanti e le stesse icone. Meno menu e una gerarchia di attività più piatta consentono agli utenti di trovare rapidamente i controlli e i comandi necessari. 
  
Skype for business include la nuova esperienza utente descritta sopra e l'esperienza utente di Lync 2013 rilasciata in precedenza. L'inclusione di entrambe le esperienze consente alle aziende di gestire le modifiche per gli utenti controllando il processo e la tempistica del nuovo roll-out del client. L'esperienza utente predefinita dipende dalla versione del server che si sta usando. Gli amministratori scelgono l'esperienza preferita usando il cmdlet **Set-CsClientPolicy** con il parametro EnableSkypeUI. Per altre informazioni sulla configurazione dell'esperienza client, vedere [configurare l'esperienza client con il](deploy/deploy-clients/configure-the-client-experience.md) confronto delle caratteristiche client Skype for business e [Desktop per Skype for business](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md).
  
> [!NOTE]
> L'esperienza client di Lync 2013 non è un'opzione per le versioni client di Skype for business 2016. Prima di provare a configurare l'ambiente client per l'utilizzo del client Lync 2013, verifica che la versione client non inizi con il numero 16; ad esempio: 16.x.x.x. 
  
## <a name="voice-and-video-improvements"></a>Miglioramenti vocali e video

Skype for Business Server 2015 include i miglioramenti apportati alle funzionalità vocali e video, tra cui la raccolta e l'analisi dei dati delle chiamate e l'interoperabilità migliorata con i sistemi di videoconferenza di terze parti.
  
### <a name="call-data-collection-and-analysis"></a>Raccolta e analisi dei dati delle chiamate

La caratteristica Vota la mia chiamata consente agli amministratori di Skype for Business Server 2015 di raccogliere i dati delle chiamate. Questa caratteristica è disponibile solo per le distribuzioni locali. Dopo aver completato una chiamata, agli utenti viene richiesto di eseguire un sondaggio. Per altre informazioni, Vedi [Vota la mia chiamata in Skype for Business Server 2015](manage/health-and-monitoring/rate-my-call.md).
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>Interoperabilità migliorata con i sistemi di teleconferenza video di terze parti

Il video Interop Server (VIS) funge da intermediario tra i sistemi Skype for Business Server e Cisco video teleconferenza (VTC). Quando si partecipa a una riunione, gli utenti possono ora selezionare un sistema Cisco VTC. Il server di interoperabilità video (VIS) viene implementato come ruolo autonomo del server per le distribuzioni locali. Per altre informazioni, vedere [pianificare il video Interop server in Skype for Business server 2015](plan-your-deployment/video-interop-server.md).
  
### <a name="call-via-work"></a>Chiamata tramite lavoro

La funzione chiamata tramite lavoro consente agli utenti aziendali di effettuare chiamate vocali dal client Skype for business. Quando un utente inserisce una chiamata vocale, viene instradata da Skype for business al telefono PBX o PSTN dell'originatore. Una volta che il mittente risponde al telefono, la chiamata viene quindi indirizzata al numero di destinazione. Il destinatario della chiamata risponde e la chiamata viene stabilita con Skype for business che funge da pannello di controllo. L'autore può gestire i controlli di presenza e chiamata da Skype for business. Gli amministratori del server abilitano e configurano la chiamata tramite lavoro per l'organizzazione. Per altre informazioni, vedere [pianificare la chiamata tramite lavoro in Skype for Business Server 2015](plan-your-deployment/enterprise-voice-solution/call-via-work.md). 
  
## <a name="mobile-device-support-improvements"></a>Miglioramenti del supporto per dispositivi mobili

I miglioramenti apportati al supporto dei dispositivi mobili includono funzionalità per migliorare l'esperienza di mobilità per gli utenti di Enterprise Edition, ad esempio l'accesso alla cronologia delle conversazioni e i dati di log, le esperienze di riunione mobili avanzate e il supporto Single Sign-on in Office. Ci sono inoltre miglioramenti al supporto per Android, ai miglioramenti delle prestazioni e alle funzionalità per semplificare l'integrazione tramite il Framework comune per le app. 
  
> [!NOTE]
> I server UCWA di Lync 2013 devono essere aggiornati a Skype for Business Server 2015 per supportare i client mobili. 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>La cronologia delle conversazioni sul lato server è ora disponibile nei dispositivi mobili

Per consentire l'accesso mobile alla cronologia delle conversazioni, ai messaggi istantanei persi e ai dati del log delle chiamate, l'archiviazione di queste informazioni viene ora elaborata tramite il server per tutti i client mobili. La caratteristica di accettazione automatica per la messaggistica istantanea migliora l'affidabilità impedendo i messaggi di timeout del server quando un utente mobile non risponde immediatamente a un messaggio ISTANTANEo. Per sfruttare l'integrazione delle cartelle di Exchange/Outlook basate sul server, è necessario Exchange Server 2013 o i client mobili più recenti e aggiornati. 
  
### <a name="enhanced-meeting-experiences"></a>Esperienze di riunione migliorate

La funzionalità riunione disponibile sul desktop è ora disponibile anche per gli utenti di dispositivi mobili. La nuova funzionalità include:
  
- Spostamento asincrono del contenuto di PowerPoint condiviso
- Capacità del relatore di assumere il controllo del contenuto di PowerPoint condiviso
- Gestione della sala di attesa per i relatori, che consente loro di ammettere o rifiutare i partecipanti
    
### <a name="skype-for-business-on-android-improvements"></a>Miglioramenti di Skype for business per Android

Skype for business su Android offre ora caratteristiche simili a quelle disponibili in Skype for business per iOS e Skype for business su Windows:
  
- Continuare o partecipare di nuovo alle conversazioni
- Abilitare il certificato e l'autenticazione passiva
- Invitare altri utenti a una conversazione
- Avviare facilmente le conversazioni di gruppo
- Partecipare a una riunione senza essere un utente Skype for business
- Abilitare l'interfaccia utente di smartphone nei tablet Android
- Gestire le riunioni aggiungendo o rimuovendo partecipanti
    
> [!NOTE]
> Queste funzionalità richiedono Android OS versione 4,0 o successive. 
  
## <a name="management-of-on-premises-servers"></a>Gestione dei server locali

Skype for Business Server 2015 offre diverse nuove funzionalità per migliorare la gestibilità dei server locali, tra cui l'aggiornamento sul posto, la configurazione intelligente, i processi di aggiornamento e di patch migliorati, la funzionalità di avvio a freddo del pool Front-End, SQL Server AlwaysOn supporto e registrazione centralizzata e risoluzione dei problemi.
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>Aggiornamento sul posto per i server locali

È ora possibile aggiornare i sistemi Lync Server 2013 a Skype for Business Server 2015 usando la nuova funzionalità di aggiornamento sul posto, che usa gli investimenti hardware e server esistenti di Lync Server 2013, riducendo così il costo complessivo per la distribuzione di Skype for Business Server 2015.
  
Esistono due scenari per l'aggiornamento sul posto: il metodo Move User, che non richiede tempi di inattività, e il metodo offline, che richiede tempi di inattività. Per altre informazioni sulla procedura di aggiornamento appropriata per l'azienda, vedere [pianificare l'aggiornamento a Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
> [!NOTE]
> L'opzione sul posto non è disponibile se si esegue l'aggiornamento da Lync Server 2010. Per altre informazioni sull'aggiornamento da Lync Server 2010, vedere [pianificare l'aggiornamento a Skype for Business server 2015](plan-your-deployment/upgrade.md). 
  
### <a name="smart-setup"></a>Configurazione intelligente

La caratteristica di configurazione intelligente, che rileva e Scarica automaticamente gli aggiornamenti, fa ora parte del programma di installazione. Durante il processo di installazione, viene chiesto all'utente se il processo di installazione deve verificare la disponibilità di aggiornamenti. Per altre informazioni, vedere [installare Skype for Business Server 2015](deploy/install/install.md).
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>Processo di aggiornamento e patch del server front-end migliorato

Skype for Business Server introduce due nuovi cmdlet che semplificano l'aggiornamento o la patch dei server front-end molto più facilmente rispetto alle versioni precedenti di Lync Server.
  
Quando è necessario applicare una patch o eseguire qualsiasi altra manutenzione, in un server front-end è sufficiente digitare **Invoke-CsComputerFailOver** e specificare il nome del server. Skype for Business Server sposta temporaneamente il carico di lavoro del server sugli altri server del pool. È quindi possibile eseguire la manutenzione e quindi usare il cmdlet **Invoke-CsComputerFailback** per riportare il server in servizio. Se è necessario applicare la patch a ogni server in un pool, seguire questa procedura per ogni server, uno alla volta. Questi nuovi cmdlet consentono di eseguire la patch dei server in modo molto più rapido rispetto alle versioni precedenti e con maggiore affidabilità e un flusso di lavoro più semplice.
  
### <a name="improved-front-end-pool-cold-start-capability"></a>Funzionalità di avvio a freddo del pool Front-End migliorata

Skype for Business Server introduce un nuovo cmdlet che semplifica e migliora il processo di avvio a freddo di un intero pool Front-end. Quando si usa il nuovo cmdlet **Start-CsPool** , vengono controllati i prerequisiti per tutti i server front-end del pool, quindi i tentativi di avviare ogni server. Se incontra problemi, li diagnostica e avvisa l'utente con dettagli e soluzioni alternative. In alcuni casi è possibile avviare il pool anche se alcuni dei singoli server non sono in grado di iniziare.
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>Supporto di SQL Server AlwaysOn per i server locali

Skype for Business Server 2015 aggiunge il supporto per i gruppi di disponibilità di SQL Server AlwaysOn e per le istanze del cluster di failover di SQL Server AlwaysOn. Oltre a queste funzionalità, Skype for Business Server continua il supporto per il mirroring del database e il clustering di SQL Server, come nelle versioni precedenti di Lync Server.
  
SQL Server AlwaysOn Availability Groups è una soluzione a elevata disponibilità e ripristino di emergenza in SQL Server 2012 e SQL Server 2014 che offre un'alternativa al mirroring del database. Un gruppo di disponibilità supporta un ambiente di failover per un set discreto di database (noti come database di disponibilità) che non rientrano insieme. Un gruppo di disponibilità supporta un set di database primari di lettura-scrittura e uno-quattro set di database secondari corrispondenti. Facoltativamente, i database secondari possono essere resi disponibili per l'accesso in sola lettura e per alcune operazioni di backup.
  
Le istanze del cluster di failover di SQL Server sfruttano la funzionalità WSFC (Windows Server Failover Clustering) per assicurare una disponibilità elevata locale tramite ridondanza a livello di istanza del server, ovvero un'istanza del cluster di failover (FCI). Una FCI è una singola istanza di SQL Server installata in nodi WSFC (Windows Server Failover Clustering) e, possibilmente, in più subnet.
  
Per altre informazioni, vedere [pianificare l'elevata disponibilità e il ripristino di emergenza in Skype for Business Server 2015](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>Miglioramenti centralizzati per la registrazione e la risoluzione dei problemi per i server locali

Il servizio di registrazione centralizzato è l'ambiente di registrazione preferito per Skype for Business Server 2015. Questa versione non contiene nuove funzionalità, ma l'affidabilità e le prestazioni sono state migliorate sia per il servizio che per l'agente del servizio di registrazione centralizzato (ClsAgent. exe): l'eseguibile del servizio che comunica con il controller e riceve i comandi rilasciato dall'amministratore.
  
Skype for Business Server 2015 USA i cmdlet di Windows PowerShell per gestire gli agenti del servizio di registrazione, avviare la traccia e generare report. Lync Server 2013 ha usato ClsController. exe per eseguire queste attività.
  
Il servizio di registrazione centralizzato può essere eseguito su qualsiasi Skype for Business Server 2015. Gli scenari predefiniti (tracce predefinite) rimangono invariati, così come la possibilità di creare scenari personalizzati. Esiste uno scenario speciale denominato AlwaysOn che è sempre in esecuzione e consente agli amministratori di individuare problemi comuni in tempo quasi reale.
  
Lo strumento di debug di Snooper è stato aggiornato anche per consentire il debug dei registri della mobilità e funziona con i dispositivi che si connettono a Lync 2013 o Skype for Business Server 2015. Lo strumento è disponibile come download Web dagli [strumenti di debug](https://go.microsoft.com/fwlink/?LinkId=285257).
  
## <a name="hybrid-deployment-and-management"></a>Distribuzione e gestione ibrida

Skype for Business Server 2015 consente funzionalità di amministrazione e gestione della distribuzione ibrida introducendo le caratteristiche seguenti:
  
- Consigli per le distribuzioni ibride in base allo stato degli asset locali del cliente, come determinato dallo strumento di assistenza automatica OnRamp per Office 365.
- Miglioramenti apportati al pannello di controllo di Skype for Business Server e all'interfaccia di amministrazione di Skype for Business Server in modo che gli amministratori possano usare questi strumenti per gestire una distribuzione ibrida.
- Miglioramenti al pannello di controllo che consentono agli amministratori di accedere a un tenant di Office 365 e configurare Hybrid con Skype for business online con la configurazione guidata ibrida.
- Supporto del pannello di controllo per spostare gli utenti locali in Skype for business online o per spostare gli utenti di Skype for business online di nuovo in locale.
- Caratteristiche del pannello di controllo per identificare e filtrare gli oggetti utente locali spostati in Skype for business online, ovvero gli utenti ibridi, dagli utenti locali.
- Funzionalità dell'interfaccia di amministrazione per identificare e filtrare gli utenti di cloud creati inizialmente in Skype for business online dagli utenti ibridi migrati da locale a online.
- Possibilità di gestire gli utenti ibridi tramite il pannello di controllo per le proprietà gestibili da locale e dall'interfaccia di amministrazione per le proprietà gestibili da Skype for business online.
- Uso della sincronizzazione delle password con DirSync, la possibilità di sincronizzare le password di Active Directory locale con il tenant online. Se configurata, questa funzionalità Elimina la necessità di distribuire ADFS per l'autenticazione federata, ma ADFS è comunque necessario per l'autenticazione a più fattori. 
- Supporto continuo per la coesistenza tra Skype for business online e Exchange locale.
    
> [!NOTE]
> L'esperienza di coesistenza e supporto di Lync Online 2013 e Exchange locale non è cambiata. 
  
## <a name="multi-factor-authentication"></a>Autenticazione a più fattori

L'autenticazione a più fattori è un metodo di autenticazione che richiede l'uso di più metodi di verifica e aggiunge un secondo livello critico di sicurezza agli accessi e alle transazioni degli utenti. Ad esempio, richiedendo un nome utente e una password e un certificato. Skype for Business Server 2015 continua a essere basato sulle funzionalità di autenticazione a più fattori disponibili negli aggiornamenti cumulativi di Lync Server 2013. Le modifiche significative nell'autenticazione a più fattori sono:
  
- Uso della libreria di autenticazione di Active Directory di Office 2013 SP1 per l'integrazione con Exchange e SharePoint
- Supporto della funzionalità di autenticazione a più fattori nel client di Skype for Business Web App
    
Con l'autenticazione a più fattori di Skype for business, ora è possibile specificare opzioni di autenticazione diverse in base alla geografia. Ad esempio, i clienti possono configurare il proprio ambiente in modo che l'autenticazione interna si basa sull'autenticazione integrata di Windows, mentre i dipendenti che eseguono l'autenticazione dall'esterno dell'organizzazione usano l'autenticazione a più fattori. 
  
L'esperienza di autenticazione a più fattori di Skype for business è perfetta indipendentemente da:
  
- Posizione geografica: se l'utente effettua l'accesso dall'interno o dall'esterno dell'organizzazione 
- Tipo di client/dispositivo: viene usato il client Skype for business e su quale dispositivo è in uso il client (PC, dispositivi mobili, iPad e così via)
- Posizione dell'account: se l'utente è ospitato in un Active Directory locale o in Azure Active Directory online (Office 365)
