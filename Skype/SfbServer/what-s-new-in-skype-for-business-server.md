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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: e62c9229-b738-45ef-b637-0b58ca8225a4
description: "Riepilogo: leggere questo argomento per informazioni sulle nuove funzionalità in Skype for Business Server 2015. Per informazioni dettagliate sulla nuova esperienza client, vedere Lync is now Skype for Business -- see what's new."
ms.openlocfilehash: df0a16855ab7430e87847a392d263f35c6ec2993
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617622"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>Novità di Skype for Business Server 2015

**Riepilogo:** Leggere questo argomento per informazioni sulle nuove funzionalità in Skype for Business Server 2015. Per informazioni dettagliate sulla nuova esperienza client, vedere [Lync is now Skype for Business -- see what's new](https://go.microsoft.com/fwlink/p/?LinkId=529022).
  
Lync è ora Skype for Business, una piattaforma di comunicazione e collaborazione che riunisce un'esperienza ispirata a Skype con la sicurezza, la conformità e il controllo di Lync di livello aziendale. Skype for Business offre funzionalità quali presenza, messaggistica istantanea, chiamate vocali e videochiamate e riunioni online. Skype for Business offre una nuova esperienza client, una nuova versione del server e gli aggiornamenti al servizio in Microsoft 365 o Office 365. Se gli utenti dell'organizzazione hanno già familiarità con Skype, apprezzeranno la potenza e la semplicità di Skype for Business in cui è facile trovare e connettersi con i colleghi. Se gli utenti dell'organizzazione vengono a Skype for Business da Lync, riconosceranno tutte le funzionalità già utilizzate, ma in una nuova interfaccia con controlli semplificati e nuove aggiunte. Oltre alla nuova esperienza client, Skype for Business Server 2015 offre diverse nuove funzionalità per migliorare la gestibilità dei server locali e delle soluzioni ibride.
  
Le nuove funzionalità di Skype for Business Server 2015 includono miglioramenti a:
  
- Esperienza utente  
- Supporto vocale e video
- Supporto versioni mobili
- Gestione dei server locali
- Distribuzione e gestione di soluzioni ibride
- Supporto dell'autenticazione a più fattori
    
## <a name="user-experience"></a>Esperienza utente

Il Skype for Business client è molto simile alla versione consumer di Skype e usa gli stessi pulsanti e icone. Un numero minore di menu e una gerarchia di attività più piatta consentono agli utenti di trovare rapidamente i controlli e i comandi necessari. 
  
Skype for Business include la nuova esperienza utente descritta in precedenza e l'esperienza utente di Lync 2013 rilasciata in precedenza. L'inclusione di entrambe le esperienze consente alle aziende di gestire le modifiche per gli utenti controllando il processo e i tempi della nuova implementazione del client. L'esperienza utente predefinita dipende dalla versione del server in uso. Gli amministratori scelgono l'esperienza preferita utilizzando il cmdlet **Set-CsClientPolicy** con il parametro EnableSkypeUI. Per ulteriori informazioni sulla configurazione dell'esperienza client, vedere [Configure the client experience with Skype for Business](deploy/deploy-clients/configure-the-client-experience.md) and Desktop client feature comparison for [Skype for Business](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md).
  
> [!NOTE]
> L'esperienza client lync 2013 non è un'opzione per le Skype for Business client 2016. Prima di tentare di configurare l'ambiente client per l'utilizzo del client Lync 2013, controllare la versione client per verificare che non inizi con il numero 16. ad esempio: 16.x.x.x. 
  
## <a name="voice-and-video-improvements"></a>Miglioramenti vocali e video

Skype for Business Server 2015 include miglioramenti alle funzionalità vocali e video, tra cui la raccolta e l'analisi dei dati delle chiamate, e una migliore interoperabilità con sistemi di videoconferenza di terze parti.
  
### <a name="call-data-collection-and-analysis"></a>Raccolta e analisi dei dati delle chiamate

La funzionalità Tariffa chiamata consente agli Skype for Business Server 2015 di raccogliere i dati delle chiamate. Questa funzionalità è disponibile solo per le distribuzioni locali. Agli utenti viene richiesto di eseguire un sondaggio dopo aver completato una chiamata. Per ulteriori informazioni, vedere [Rate my Call in Skype for Business Server 2015](manage/health-and-monitoring/rate-my-call.md).
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>Interoperabilità migliorata con sistemi di teleconferenza video di terze parti

Il Video Interop Server (VIS) funge da intermediario tra Skype for Business Server e i sistemi VTC (Video Teleconferencing) Cisco. Quando si partecipa a una riunione, gli utenti possono ora selezionare un sistema VTC Cisco. Video Interop Server (VIS) viene implementato come ruolo del server autonomo per le distribuzioni locali. Per ulteriori informazioni, vedere [Plan for Video Interop Server in Skype for Business Server 2015.](plan-your-deployment/video-interop-server.md)
  
### <a name="call-via-work"></a>Chiamata tramite lavoro

La funzionalità Chiama tramite lavoro consente agli utenti aziendali di effettuare chiamate vocali dal client Skype for Business aziendale. Quando un utente esegue una chiamata vocale, viene instradata dalla Skype for Business al PBX o al telefono PSTN dell'autore. Una volta che il mittente risponde al telefono, la chiamata viene quindi indirizzata al numero di destinazione. Il destinatario della chiamata risponde e la chiamata viene stabilita Skype for Business come pannello di controllo. Il mittente può gestire i controlli di presenza e chiamata Skype for Business. Gli amministratori del server abilitano e configurano La chiamata tramite lavoro per l'organizzazione. Per ulteriori informazioni, vedere [Plan for Call Via Work in Skype for Business Server 2015.](plan-your-deployment/enterprise-voice-solution/call-via-work.md) 
  
## <a name="mobile-device-support-improvements"></a>Miglioramenti al supporto dei dispositivi mobili

I miglioramenti apportati al supporto dei dispositivi mobili includono funzionalità per migliorare l'esperienza mobile per gli utenti di edizione Enterprise, ad esempio l'accesso alla cronologia delle conversazioni e ai dati di registro, esperienze di riunioni per dispositivi mobili avanzate e supporto single sign-on in Office. Sono inoltre disponibili miglioramenti al supporto di Android, miglioramenti delle prestazioni e funzionalità per semplificare l'integrazione tramite Common App Framework. 
  
> [!NOTE]
> I server UCWA lync 2013 devono essere aggiornati a Skype for Business Server 2015 per supportare i client mobili. 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>La cronologia delle conversazioni sul lato server è ora disponibile nei dispositivi mobili

Per consentire l'accesso da dispositivi mobili alla cronologia delle conversazioni, alla messaggistica istantanea senza errori e ai dati del registro delle chiamate, l'archiviazione di queste informazioni viene ora elaborata tramite il server per tutti i client mobili. La funzionalità di accettazione automatica per la messaggistica istantanea migliora l'affidabilità impedendo i messaggi di timeout del server quando un utente mobile non risponde immediatamente a un messaggio istantaneo. Per sfruttare l'integrazione delle cartelle Exchange/Outlook basate su server, sono necessari Exchange Server 2013 o versioni più nuove e i client mobili aggiornati. 
  
### <a name="enhanced-meeting-experiences"></a>Esperienze di riunione avanzate

La funzionalità riunione disponibile sul desktop è ora disponibile anche per gli utenti mobili. Le nuove funzionalità includono:
  
- Spostamento asincrono di contenuto PowerPoint condivisi
- Possibilità del relatore di assumere il controllo del contenuto PowerPoint condiviso
- Gestione della sala di attesa per i relatori, consentendo loro di ammettere o negare i partecipanti
    
### <a name="skype-for-business-on-android-improvements"></a>Skype for Business miglioramenti di Android

Skype for Business su Android ora offre funzionalità simili a quelle disponibili in Skype for Business su iOS e Skype for Business su Windows:
  
- Continuare o partecipare di nuovo alle conversazioni
- Abilitare il certificato e l'autenticazione passiva
- Invitare altri utenti a una conversazione
- Avviare facilmente conversazioni di gruppo
- Partecipare a una riunione senza essere un Skype for Business utente
- Abilitare l'interfaccia utente dello smartphone nei tablet Android
- Gestire le riunioni aggiungendo o rimuovendo partecipanti
    
> [!NOTE]
> Queste funzionalità richiedono Android OS versione 4.0 o successiva. 
  
## <a name="management-of-on-premises-servers"></a>Gestione dei server locali

Skype for Business Server 2015 offre diverse nuove funzionalità per migliorare la gestibilità dei server locali, tra cui l'aggiornamento sul posto, l'installazione intelligente, i processi di applicazione di patch e aggiornamento migliorati, la funzionalità di avvio a freddo del pool Front End migliorata, il supporto di SQL Server AlwaysOn e la registrazione centralizzata e la risoluzione dei problemi.
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>Aggiornamento sul posto per i server locali

È ora possibile aggiornare i sistemi Lync Server 2013 a Skype for Business Server 2015 utilizzando la nuova funzionalità di aggiornamento sul posto, che utilizza gli investimenti di server e hardware di Lync Server 2013 esistenti, riducendo così il costo complessivo per la distribuzione di Skype for Business Server 2015.
  
Esistono due scenari per l'aggiornamento sul posto: il metodo Move User, che non richiede tempi di inattività, e il metodo Offline, che richiede tempi di inattività. Per ulteriori informazioni sulla procedura di aggiornamento più giusta per l'azienda, vedere [Plan to upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
> [!NOTE]
> L'opzione sul posto non è disponibile se si esegue l'aggiornamento da Lync Server 2010. Per ulteriori informazioni sull'aggiornamento da Lync Server 2010, vedere [Plan to upgrade to Skype for Business Server 2015](plan-your-deployment/upgrade.md). 
  
### <a name="smart-setup"></a>Installazione intelligente

La funzionalità installazione intelligente, che rileva e scarica automaticamente gli aggiornamenti, fa ora parte del programma di installazione. Durante il processo di installazione, all'utente viene chiesto se il processo di installazione deve verificare la disponibilità di aggiornamenti. Per ulteriori informazioni, vedere [Install Skype for Business Server 2015](deploy/install/install.md).
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>Miglioramento del processo di aggiornamento e applicazione di patch per Front End Server

Skype for Business Server vengono introdotti due nuovi cmdlet che semplificano l'aggiornamento o l'applicazione di patch ai Front End Server rispetto alle versioni precedenti di Lync Server.
  
Quando è necessario applicare una patch o eseguire altre operazioni di manutenzione a un Front End Server, è sufficiente digitare **Invoke-CsComputerFailOver** e specificare il nome del server. Skype for Business Server il carico di lavoro del server viene spostato temporaneamente negli altri server del pool. È quindi possibile eseguire la manutenzione e quindi utilizzare il cmdlet **Invoke-CsComputerFailback** per riportare il server in servizio. Se è necessario applicare patch a ogni server di un pool, seguire questa procedura per ogni server, uno alla volta. Questi nuovi cmdlet consentono di applicare patch ai server molto più rapidamente rispetto alle versioni precedenti e con maggiore affidabilità e un flusso di lavoro più semplice.
  
### <a name="improved-front-end-pool-cold-start-capability"></a>Funzionalità di avvio a freddo del pool Front End migliorata

Skype for Business Server introduce un nuovo cmdlet che semplifica e migliora il processo di avvio a freddo di un intero pool Front End. Quando si utilizza il nuovo cmdlet **Start-CsPool,** controlla i prerequisiti per tutti i Front End Server del pool, quindi tenta di avviare ogni server. Se si verificano problemi, li diagnostica e avvisa l'utente con dettagli e soluzioni alternative. In alcuni casi consente di avviare il pool anche se alcuni dei singoli server non sono in grado di avviarsi.
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>SQL Server Supporto AlwaysOn per i server locali

Skype for Business Server 2015 SQL Server aggiunge il supporto sia per i gruppi di disponibilità AlwaysOn che per SQL Server cluster di failover AlwaysOn. Oltre a queste funzionalità, Skype for Business Server continua il supporto per il mirroring del database e SQL Server clustering, come nelle versioni precedenti di Lync Server.
  
SQL Server Gruppi di disponibilità AlwaysOn è una soluzione a disponibilità elevata e ripristino di emergenza in SQL Server 2012 e SQL Server 2014 che fornisce un'alternativa al mirroring del database. Un gruppo di disponibilità supporta un ambiente di failover per un set discreto di database (noti come database di disponibilità) che esereranno il failover insieme. Un gruppo di disponibilità supporta un set di database primari di lettura/scrittura e da uno a quattro set di database secondari corrispondenti. Facoltativamente, i database secondari possono essere resi disponibili per l'accesso in sola lettura e per alcune operazioni di backup.
  
SQL Server Le istanze del cluster di Windows failover sfruttano la funzionalità WSFC (Server Failover Clustering) per fornire disponibilità elevata locale tramite ridondanza a livello di istanza del server, ovvero un'istanza del cluster di failover (FCI). Un'istanza FCI è una singola istanza di SQL Server che viene installata tra i nodi WSFC (Server Failover Clustering) di Windows e, eventualmente, tra più subnet.
  
Per ulteriori informazioni, vedere [Plan for high availability and disaster recovery in Skype for Business Server 2015.](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>Miglioramenti alla registrazione centralizzata e alla risoluzione dei problemi per i server locali

Il servizio di registrazione centralizzata è l'ambiente di registrazione preferito per Skype for Business Server 2015. Questa versione non include nuove funzionalità, ma l'affidabilità e le prestazioni sono state migliorate sia per il servizio che per l'agente del servizio di registrazione centralizzata (ClsAgent.exe), ovvero l'eseguibile del servizio che comunica con il controller e riceve i comandi emessi dall'amministratore.
  
Skype for Business Server 2015 utilizza Windows PowerShell per gestire gli agenti del servizio di registrazione, avviare la traccia e generare report. Lync Server 2013 ha utilizzato ClsController.exe per eseguire queste attività.
  
Il servizio di registrazione centralizzata può essere eseguito in qualsiasi Skype for Business Server 2015. Gli scenari predefiniti (tracce predefinite) rimangono invariati, così come la possibilità di creare scenari personalizzati. Esiste uno scenario speciale denominato AlwaysOn che è sempre in esecuzione e consente agli amministratori di individuare i problemi comuni quasi in tempo reale.
  
Lo strumento di debug Snooper è stato aggiornato per consentire il debug dei log per dispositivi mobili e funzionerà con i dispositivi che si connettono a Lync 2013 o Skype for Business Server 2015. Lo strumento è disponibile come download Web da [Strumenti di debug](https://go.microsoft.com/fwlink/?LinkId=285257).
  
## <a name="hybrid-deployment-and-management"></a>Distribuzione e gestione ibride

Skype for Business Server 2015 abilita le funzionalità di gestione e amministrazione della distribuzione ibrida introducendo le funzionalità seguenti:
  
- Consigli per le distribuzioni ibride in base allo stato delle risorse locali del cliente, come determinato dallo strumento onRamp per Office 365 assistenza automatizzata.
- Miglioramenti apportati al Pannello Skype for Business Server e all'interfaccia di amministrazione di Skype for Business Server in modo che gli amministratori possano usare questi strumenti per gestire una distribuzione ibrida.
- Miglioramenti del Pannello di controllo che consentono agli amministratori di accedere a un tenant Microsoft 365 o Office 365 e configurare la distribuzione ibrida con Skype for Business Online tramite la procedura guidata di configurazione ibrida.
- Supporto del Pannello di controllo per lo spostamento degli utenti locali in Skype for Business Online o lo spostamento degli utenti di Skype for Business Online in locale.
- Funzionalità del Pannello di controllo per identificare e filtrare gli oggetti utente locali che sono stati spostati in Skype for Business Online (ovvero gli utenti ibridi) dagli utenti locali.
- Funzionalità dell'interfaccia di amministrazione per identificare e filtrare gli utenti cloud creati inizialmente in Skype for Business Online dagli utenti ibridi migrati da locale a Online.
- La possibilità di amministrare gli utenti ibridi usando il Pannello di controllo per le proprietà gestibili dall'ambiente locale e l'interfaccia di amministrazione per le proprietà gestibili da Skype for Business Online.
- Utilizzando la sincronizzazione delle password con DirSync, la possibilità di sincronizzare le password di Active Directory locali con il tenant online. Se configurata, questa funzionalità rimuove la necessità di distribuire ADFS per l'autenticazione federata, ma ADFS è ancora necessario per l'autenticazione a più fattori. 
- Supporto continuo per la coesistenza tra Skype for Business Online e Exchange locale.
    
> [!NOTE]
> Non sono presenti modifiche rispetto a Lync Online 2013 e Exchange'esperienza di coesistenza e supporto locale. 
  
## <a name="multi-factor-authentication"></a>Autenticazione a più fattori

L'autenticazione a più fattori è un metodo di autenticazione che richiede l'utilizzo di più metodi di verifica e aggiunge un secondo livello critico di sicurezza agli account di accesso e alle transazioni degli utenti. Ad esempio, richiedendo un nome utente e una password e un certificato. Skype for Business Server 2015 continua a basarsi sulle funzionalità di autenticazione a più fattori disponibili negli aggiornamenti cumulativi di Lync Server 2013. Le modifiche significative apportate all'autenticazione a più fattori sono:
  
- Utilizzo della libreria di autenticazione di Active Directory Office 2013 SP1 per l'integrazione con Exchange e SharePoint
- Supporto per la funzionalità di autenticazione a più fattori nel client Skype for Business Web App client
    
Con Skype for Business'autenticazione a più fattori, è ora possibile fornire diverse opzioni di autenticazione in base all'area geografica. Ad esempio, i clienti possono configurare il proprio ambiente in modo che l'autenticazione interna si basa sull'autenticazione Windows integrata, mentre i dipendenti che e autenticano dall'esterno dell'organizzazione utilizzano l'autenticazione a più fattori. 
  
L Skype for Business'autenticazione a più fattori è semplice indipendentemente da:
  
- Posizione geografica - Indica se l'utente sta accedendo dall'interno o dall'esterno dell'organizzazione 
- Client/Device Type - Quale Skype for Business client viene usato e su quale dispositivo è in esecuzione il client (PC, dispositivi mobili, iPad e così via)
- Percorso dell'account: indica se l'utente è ospitato in active Directory locale o in Azure Active Directory Online.
