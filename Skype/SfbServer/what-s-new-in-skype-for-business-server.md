---
title: Novità di Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: "Riepilogo: leggere questo argomento per informazioni sulle nuove funzionalità in Skype for Business Server 2015. Per informazioni dettagliate sulla nuova esperienza client, vedere Lync è ora Skype for Business--vedere What ' s New."
ms.openlocfilehash: 09774f722020ef750ae16ad01a29873d43d25e76
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827586"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Novità di Skype for Business Server 2015

**Riepilogo:** Leggere questo argomento per informazioni sulle nuove funzionalità in Skype for Business Server 2015. Per informazioni dettagliate sulla nuova esperienza client, vedere [Lync è ora Skype for Business--vedere What ' s New](https://go.microsoft.com/fwlink/p/?LinkId=529022).
  
Lync è ora Skype for business, una piattaforma di comunicazione e collaborazione che unisce un'esperienza ispirata a Skype con la sicurezza, la conformità e il controllo di Lync di livello aziendale. Skype for business offre funzionalità quali la presenza, la messaggistica istantanea, le chiamate vocali e video e le riunioni online. Skype for business offre una nuova esperienza client, una nuova versione del server e gli aggiornamenti del servizio in Microsoft 365 o Office 365. Se gli utenti dell'organizzazione hanno già familiarità con Skype, apprezzeranno la potenza e la semplicità di Skype for business in cui è facile trovare e connettersi con i colleghi. Se gli utenti dell'organizzazione vengono a Skype for business da Lync, riconoscono tutte le funzionalità che già utilizzano, ma in una nuova interfaccia fresca con controlli semplificati e nuove aggiunte. Oltre alla nuova esperienza client, in Skype for Business Server 2015 sono disponibili diverse nuove funzionalità per migliorare la gestibilità dei server locali e delle soluzioni ibride.
  
Le nuove funzionalità di Skype for Business Server 2015 includono miglioramenti per:
  
- Esperienza utente  
- Supporto per la voce e il video
- Supporto versioni mobili
- Gestione dei server locali
- Distribuzione e gestione di soluzioni ibride
- Supporto per l'autenticazione a più fattori
    
## <a name="user-experience"></a>Esperienza utente

Il client Skype for business ha un aspetto molto simile alla versione consumer di Skype e utilizza gli stessi pulsanti e le stesse icone. Meno menu e una gerarchia di attività semplificano gli utenti a trovare rapidamente i controlli e i comandi necessari. 
  
Skype for business include la nuova esperienza utente descritta sopra e l'esperienza utente di Lync 2013 rilasciata in precedenza. L'inclusione di entrambe le esperienze consente alle aziende di gestire le modifiche per i propri utenti controllando il processo e la tempistica del nuovo roll-out del client. L'esperienza utente predefinita dipende dalla versione del server che si sta utilizzando. Gli amministratori scelgono l'esperienza preferita utilizzando il cmdlet **Set-CsClientPolicy** con il parametro EnableSkypeUI. Per ulteriori informazioni sulla configurazione dell'esperienza client, vedere [Configure the client experience with Skype for business](deploy/deploy-clients/configure-the-client-experience.md) and [desktop client Feature Comparison for Skype for business](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md).
  
> [!NOTE]
> L'esperienza client di Lync 2013 non è un'opzione per le versioni client di Skype for business 2016. Prima di tentare di configurare l'ambiente client per l'utilizzo del client Lync 2013, controllare la versione client per verificare che non venga avviata con il numero 16. ad esempio: 16. x.x.x. 
  
## <a name="voice-and-video-improvements"></a>Miglioramenti di voce e video

Skype for Business Server 2015 include miglioramenti alla funzionalità di audio e video, tra cui la raccolta e l'analisi dei dati di chiamata e l'interoperabilità migliorata con i sistemi di teleconferenza di terze parti.
  
### <a name="call-data-collection-and-analysis"></a>Raccolta e analisi dei dati delle chiamate

La caratteristica Rate My Call consente agli amministratori di Skype for Business Server 2015 di raccogliere i dati delle chiamate. Questa funzionalità è disponibile solo per le distribuzioni locali. Dopo aver completato una chiamata, agli utenti viene richiesto di eseguire un sondaggio. Per ulteriori informazioni, vedere [Rate My Call in Skype for Business Server 2015](manage/health-and-monitoring/rate-my-call.md).
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>Maggiore interoperabilità con sistemi di teleconferenza video di terze parti

Il video Interop Server (VIS) funge da intermediario tra i sistemi Skype for Business Server e Cisco video teleconferenza (videoconferenza). Quando si partecipa a una riunione, gli utenti possono ora selezionare un sistema Cisco videoconferenza. Il video Interop Server (VIS) è implementato come ruolo del server autonomo per le distribuzioni locali. Per ulteriori informazioni, vedere [Plan for video Interop server in Skype for Business server 2015](plan-your-deployment/video-interop-server.md).
  
### <a name="call-via-work"></a>Chiamata tramite lavoro

La funzionalità di chiamata tramite lavoro consente agli utenti dell'organizzazione di effettuare chiamate vocali dal client Skype for business. Quando un utente inserisce una chiamata vocale, viene instradata da Skype for business al telefono PBX o PSTN del mittente. Una volta che il mittente risponde al telefono, la chiamata viene quindi indirizzata al numero di destinazione. Il destinatario della chiamata risponde e la chiamata viene stabilita con Skype for business che funge da pannello di controllo. L'autore può gestire la propria presenza e i controlli di chiamata da Skype for business. Gli amministratori del server abilitano e configurano la chiamata tramite lavoro per l'organizzazione. Per ulteriori informazioni, vedere [pianificare la chiamata tramite lavoro in Skype for Business Server 2015](plan-your-deployment/enterprise-voice-solution/call-via-work.md). 
  
## <a name="mobile-device-support-improvements"></a>Miglioramenti del supporto per i dispositivi mobili

I miglioramenti apportati al supporto dei dispositivi mobili includono funzionalità che migliorano l'esperienza di telefonia mobile per gli utenti di Enterprise Edition, ad esempio l'accesso alla cronologia delle conversazioni e i dati di log, le esperienze di riunioni mobili migliorate e il supporto Single Sign-on Inoltre, ci sono miglioramenti al supporto Android, ai miglioramenti delle prestazioni e alle funzionalità per semplificare l'integrazione tramite Common App Framework. 
  
> [!NOTE]
> I server Lync 2013 UCWA devono essere aggiornati a Skype for Business Server 2015 per supportare i client mobili. 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>La cronologia delle conversazioni sul fianco del server è ora disponibile nei dispositivi mobili

Per abilitare l'accesso mobile alla cronologia delle conversazioni, ai dati di messaggistica istantanea e ai log delle chiamate, l'archiviazione di queste informazioni viene ora elaborata tramite il server per tutti i client mobili. La funzionalità di accettazione automatica per la messaggistica istantanea migliora l'affidabilità impedendo i messaggi di timeout del server quando un utente mobile non risponde immediatamente a un messaggio ISTANTANEo. Per sfruttare al meglio l'integrazione delle cartelle Exchange/Outlook basate su server, sono necessari i client mobili Exchange Server 2013 o versioni successive e aggiornati. 
  
### <a name="enhanced-meeting-experiences"></a>Esperienze di riunioni migliorate

Le funzionalità di riunione disponibili sul desktop sono ora disponibili anche per gli utenti mobili. La nuova funzionalità include:
  
- Spostamento asincrono del contenuto di PowerPoint condiviso
- Capacità del relatore di assumere il controllo del contenuto di PowerPoint condiviso
- Gestione della lobby per i relatori, consentendo loro di ammettere o negare i partecipanti
    
### <a name="skype-for-business-on-android-improvements"></a>Miglioramenti di Skype for business su Android

Skype for business su Android offre ora funzionalità simili a quelle disponibili su Skype for business su iOS e Skype for business su Windows:
  
- Continuare o aggiungere di nuovo le conversazioni
- Abilitare il certificato e l'autenticazione passiva
- Invitare altri utenti a una conversazione
- Avviare facilmente le conversazioni di gruppo
- Partecipare a una riunione senza essere un utente di Skype for business
- Abilitare l'interfaccia utente di smartphone su tablet Android
- Gestire le riunioni aggiungendo o rimuovendo i partecipanti
    
> [!NOTE]
> Queste funzionalità richiedono Android OS versione 4,0 o versioni successive. 
  
## <a name="management-of-on-premises-servers"></a>Gestione dei server locali

Skype for Business Server 2015 offre diverse nuove funzionalità per migliorare la gestibilità dei server locali, tra cui l'aggiornamento sul posto, la configurazione avanzata, i processi di aggiornamento e patch migliorati, la funzionalità di avvio a freddo del pool Front End, il supporto di SQL Server AlwaysOn e la registrazione centralizzata e la risoluzione dei problemi.
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>Aggiornamento sul posto per i server locali

È ora possibile aggiornare i sistemi Lync Server 2013 a Skype for Business Server 2015 utilizzando la nuova funzionalità di aggiornamento sul posto, in cui vengono utilizzati gli investimenti hardware e server di Lync Server 2013, riducendo in tal modo il costo complessivo per la distribuzione di Skype for Business Server 2015.
  
Esistono due scenari per l'aggiornamento sul posto: il metodo Move User, che non richiede tempi di inattività e il metodo offline, che richiede tempi di inattività. Per ulteriori informazioni sulla procedura di aggiornamento adatta alla propria azienda, vedere [plan to upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
> [!NOTE]
> L'opzione sul posto non è disponibile se si esegue l'aggiornamento da Lync Server 2010. Per ulteriori informazioni sull'aggiornamento da Lync Server 2010, vedere [plan to upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
### <a name="smart-setup"></a>Configurazione avanzata

La funzionalità di installazione avanzata, che consente di rilevare e scaricare automaticamente gli aggiornamenti, fa ora parte del programma di installazione. Durante il processo di installazione, all'utente viene richiesto se il processo di installazione deve verificare la disponibilità di aggiornamenti. Per ulteriori informazioni, vedere [Install Skype for Business Server 2015](deploy/install/install.md).
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>Processo di aggiornamento e patching front end server migliorato

Skype for Business Server introduce due nuovi cmdlet che facilitano l'aggiornamento o l'applicazione di patch ai front end server molto più facile rispetto alle versioni precedenti di Lync Server.
  
Quando è necessario applicare una patch o eseguire altre operazioni di manutenzione a un front end server, è sufficiente digitare **Invoke-CsComputerFailOver** e specificare il nome del server. Skype for Business Server sposta temporaneamente il carico di lavoro del server negli altri server del pool. È quindi possibile eseguire la manutenzione e quindi utilizzare il cmdlet **Invoke-CsComputerFailback** per riportare in servizio il server. Se è necessario applicare una patch a ogni server in un pool, è sufficiente seguire questa procedura per ogni server, uno alla volta. Questi nuovi cmdlet consentono di applicare la patch ai server molto più rapidamente rispetto alle versioni precedenti e con un flusso di lavoro più affidabile e semplice.
  
### <a name="improved-front-end-pool-cold-start-capability"></a>Funzionalità di avvio a freddo del pool Front End migliorato

Skype for Business Server introduce un nuovo cmdlet che semplifica e migliora il processo di avvio a freddo di un intero pool Front end. Quando si utilizza il nuovo cmdlet **Start-CsPool** , vengono verificati i prerequisiti per tutti i Front End Server nel pool e quindi viene eseguito un tentativo di avvio di ogni server. Se si verificano problemi, vengono diagnosticati e avvisati con dettagli e soluzioni alternative. In alcuni casi, è possibile avviare il pool anche se alcuni dei singoli server non sono in grado di avviarsi.
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>Supporto di SQL Server AlwaysOn per i server locali

Skype for Business Server 2015 aggiunge il supporto per i gruppi di disponibilità AlwaysOn di SQL Server e le istanze del cluster di failover di SQL Server AlwaysOn. Oltre a queste funzionalità, Skype for Business Server continua il supporto per il mirroring del database e per il clustering di SQL Server, come nelle versioni precedenti di Lync Server.
  
I gruppi di disponibilità AlwaysOn di SQL Server sono una soluzione di disponibilità elevata e di ripristino di emergenza in SQL Server 2012 e SQL Server 2014 che offre un'alternativa al mirroring del database. Un gruppo di disponibilità supporta un ambiente di failover per un set discreto di database (noti come database di disponibilità) che non rientrano più nell'insieme. Un gruppo di disponibilità supporta un insieme di database primari di lettura e scrittura e uno a quattro set di database secondari corrispondenti. Facoltativamente, è possibile rendere disponibili i database secondari per l'accesso in sola lettura e per alcune operazioni di backup.
  
Le istanze del cluster di failover di SQL Server sfruttano le funzionalità di Windows Server failover clustering (WSFC) per garantire la disponibilità elevata locale tramite ridondanza a livello di istanza del server, ovvero un'istanza del cluster di failover (FCI). Un oggetto FCI è una singola istanza di SQL Server installata nei nodi WSFC (Windows Server Failover Clustering) e, possibilmente, su più subnet.
  
Per ulteriori informazioni, vedere [pianificare la disponibilità elevata e il ripristino di emergenza in Skype for Business Server 2015](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>Miglioramenti alla registrazione centralizzata e alla risoluzione dei problemi per i server locali

Il servizio di registrazione centralizzato è l'ambiente di registrazione preferito per Skype for Business Server 2015. Questa versione non contiene nuove funzionalità, ma sono state migliorate l'affidabilità e le prestazioni sia per il servizio che per l'agente di servizio di registrazione centralizzato (ClsAgent.exe): il file eseguibile del servizio che comunica con il controller e riceve i comandi emessi dall'amministratore.
  
Skype for Business Server 2015 utilizza i cmdlet di Windows PowerShell per gestire gli agenti di servizio di registrazione, avviare la traccia e generare i report. Lync Server 2013 ha utilizzato ClsController.exe per eseguire queste attività.
  
Il servizio di registrazione centralizzato può essere eseguito su qualsiasi server Skype for business 2015. Gli scenari predefiniti (tracce predefinite) rimangono invariati, così come la possibilità di creare scenari personalizzati. È presente uno scenario speciale denominato AlwaysOn che è sempre in esecuzione e consente agli amministratori di individuare problemi comuni in tempo quasi reale.
  
Lo strumento di debug di Snooper è stato inoltre aggiornato per consentire il debug dei registri di dispositivi mobili e funziona con le periferiche che si connettono a Lync 2013 o Skype for Business Server 2015. Lo strumento è disponibile come download Web da [strumenti di debug](https://go.microsoft.com/fwlink/?LinkId=285257).
  
## <a name="hybrid-deployment-and-management"></a>Distribuzione e gestione ibrida

Skype for Business Server 2015 Abilita le funzionalità di gestione e amministrazione della distribuzione ibrida introducendo le seguenti funzionalità:
  
- Suggerimenti per le distribuzioni ibride in base allo stato dei cespiti locali del cliente, come stabilito dallo strumento di assistenza automatizzato di OnRamp per Office 365.
- Miglioramenti apportati al pannello di controllo di Skype for Business Server e all'interfaccia di amministrazione di Skype for Business Server, in modo che gli amministratori possano utilizzare questi strumenti per gestire una distribuzione ibrida.
- Miglioramenti del pannello di controllo che consentono agli amministratori di accedere a un tenant di Microsoft 365 o Office 365 e di configurare l'ambiente ibrido con Skype for business online tramite la procedura guidata di configurazione ibrida.
- Supporto del pannello di controllo per spostare gli utenti locali in Skype for business online o spostare gli utenti di Skype for business online di nuovo in locale.
- Funzionalità del pannello di controllo per identificare e filtrare gli oggetti utente locali che sono stati spostati in Skype for business online (ovvero gli utenti ibridi) dagli utenti locali.
- Funzionalità dell'interfaccia di amministrazione per identificare e filtrare gli utenti di cloud creati inizialmente in Skype for business online da utenti ibridi migrati da locali a online.
- La possibilità di amministrare gli utenti ibridi utilizzando il pannello di controllo per le proprietà gestibili dall'ambiente locale e l'interfaccia di amministrazione per le proprietà gestibili da Skype for business online.
- Utilizzo della sincronizzazione delle password con DirSync, la possibilità di sincronizzare le password di Active Directory locale con il tenant online. Se configurata, questa funzionalità rimuove la necessità di distribuire ADFS per l'autenticazione federata, ma AD FS è comunque necessaria per l'autenticazione a più fattori. 
- Supporto continuativo per la coesistenza tra Skype for business online e Exchange locale.
    
> [!NOTE]
> Non è possibile modificare la coesistenza di Lync Online 2013 e la coesistenza di Exchange locale e l'esperienza di supporto. 
  
## <a name="multi-factor-authentication"></a>Autenticazione a più fattori

L'autenticazione a più fattori è un metodo di autenticazione che richiede l'utilizzo di più di un metodo di verifica e aggiunge un secondo livello critico di sicurezza agli accessi e alle transazioni degli utenti. Ad esempio, richiedere un nome utente e una password e un certificato. Skype for Business Server 2015 continua a essere basato sulle funzionalità di autenticazione a più fattori disponibili negli aggiornamenti cumulativi di Lync Server 2013. Le modifiche significative nell'autenticazione a più fattori sono le seguenti:
  
- Utilizzo della libreria di autenticazione di Active Directory di Office 2013 SP1 per l'integrazione con Exchange e SharePoint
- Supporto per la funzionalità di autenticazione a più fattori nel client Skype for Business Web App
    
Con l'autenticazione a più fattori di Skype for business, è ora possibile fornire opzioni di autenticazione diverse in base alla geografia. Ad esempio, i clienti possono configurare il proprio ambiente in modo che l'autenticazione interna si basa sull'autenticazione integrata di Windows, mentre i dipendenti che eseguono l'autenticazione dall'esterno dell'organizzazione utilizzano la possibilità di utilizzare l'autorizzazione a più fattori. 
  
L'esperienza di autenticazione a più fattori di Skype for business è perfetta, indipendentemente da:
  
- Posizione geografica: se l'utente effettua l'accesso dall'interno o dall'esterno dell'organizzazione 
- Tipo di client/dispositivo-utilizzo del client Skype for business e del dispositivo su cui è in esecuzione il client (PC, dispositivi mobili, iPad e così via)
- Posizione dell'account: se l'utente è ospitato in una Active Directory locale o in Azure Active Directory online.
