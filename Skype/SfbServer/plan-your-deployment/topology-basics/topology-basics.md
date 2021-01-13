---
title: Nozioni di base sulla topologia per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: 'Riepilogo: scegliere la topologia per Skype for Business Server. Informazioni sulla collocazione dei server per Skype for Business Server.'
ms.openlocfilehash: 9b0dbe6a74a5982c2816c022e5ea7a99ba2abf07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831756"
---
# <a name="topology-basics-for-skype-for-business-server"></a>Nozioni di base sulla topologia per Skype for Business Server

**Riepilogo:** Scegliere la topologia per Skype for Business Server. Informazioni sulla collocazione dei server per Skype for Business Server.

Prima di preparare qualsiasi altra cosa, è necessario sapere che si sta pianificando la topologia corretta per la distribuzione di Skype for Business Server. La prima cosa da fare è decidere se si sta per avere una distribuzione locale di Skype for Business Server o se si intende combinare questo con una distribuzione di Skype for Business Server online in una distribuzione ibrida. In entrambi i casi, è consigliabile leggere ulteriori informazioni, in quanto verranno illustrate le topologie locali, ma i dettagli ibridi sono documentati nella propria sezione.

È inoltre possibile vedere alcuni esempi di topologie nelle [topologie di riferimento per Skype for Business Server](reference-topologies.md).

## <a name="sites"></a>Siti

In Skype for Business Server, è possibile definire i siti della rete che contengono componenti di Skype for Business Server. Un sito è un insieme di computer connessi attraverso una rete a bassa latenza e alta velocità, come una singola rete LAN o due reti connesse tramite una rete a fibra ottica ad alta velocità. Si noti che i siti di Skype for Business Server sono un concetto separato dai siti dei servizi di dominio Active Directory e dai siti di Microsoft Exchange Server. I siti di Skype for Business Server non devono corrispondere ai siti di Active Directory.

Skype for Business Server supporta la distribuzione locale di uno o più siti che possono essere ridimensionati in base ai requisiti per la disponibilità elevata e la posizione.

La distribuzione avrà almeno un sito centrale (denominato anche centro dati, si tratta di un datacenter per tutti i server in esso contenuti) e ogni sito centrale della distribuzione avrà un server Standard Edition o almeno un pool Enterprise Edition front end. È possibile visualizzare le differenze in ogni opzione di seguito:

- Il server Standard Edition include un database di SQL Server Express collocato.

- Il pool Enterprise Edition front end include:

  - Uno o più Front End Server (idealmente almeno tre, per la scalabilità), con un massimo di dodici. Il bilanciamento del carico potrebbe essere necessario per più di un server.

  - Un server back-end separato.

È possibile ottenere ulteriori informazioni sui vari ruoli del server più avanti in questa sezione.

Oltre ai siti centrali, è possibile che si verifichino anche uno o più siti di succursale associati al sito centrale. Essi dipendono dal sito centrale per quasi tutte le loro funzionalità, quindi di cosa sono fatti, esattamente?

- Survivable Branch Appliance, che combina un gateway PSTN (Public Switched Telephone Network), con alcune funzionalità di Skype for Business Server.

- Survivable Branch Server, è un server che esegue Windows Server in cui è installato il software di registrazione e Mediation Server di Skype for Business Server.

- Gateway PSTN autonomo (che non fa parte del Survivable Branch Appliance).

- Mediation Server autonomo o pool Mediation Server autonomo (se non si desidera collocare questo ruolo con Survivable Branch Appliance).

## <a name="whats-in-a-skype-for-business-server-site"></a>Cosa c'è in un sito di Skype for Business Server?

Per ottenere maggiori dettagli, un sito centrale può anche avere:

- Più pool Front End, nello stesso dominio o in domini diversi (ricordarsi di pianificare che tutti i front end server in un pool Front End, insieme ai server back-end per il pool, devono trovarsi nello stesso dominio).

- Più server Standard Edition.

- Server Office Web Apps, utilizzato con Office Web Apps in Skype for Business Server per la condivisione e il rendering delle presentazioni di PowerPoint.

- Server perimetrale o pool Edge (in una rete perimetrale). Necessario se si desidera che la distribuzione supporti i partner federati, la connettività per la messaggistica istantanea pubblica, il gateway XMPP (Extensible Messaging and Presence Protocol) e l'accesso degli utenti remoti. Per ulteriori informazioni, vedere la documentazione relativa alla pianificazione dei server perimetrali.

- Server Chat persistente. Utile se si desidera che gli utenti siano in grado di partecipare a conversazioni a più parti, basate su argomenti che persistono nel tempo. Per ulteriori informazioni, vedere l'argomento Planning for Persistent Chat Server.

- Monitoraggio. Consente di supportare la raccolta dati per la qualità di esperienza audio/video (QoE) e la registrazione dettagli chiamata (CDR) per le conferenze di VoIP aziendale e A/V nella distribuzione. La discussione è dettagliata nell'argomento Planning for Monitoring.

- Server Director o del pool di server Director. Non necessario, ma utile se si vuole migliorare la resilienza e consentire il reindirizzamento delle richieste degli utenti di Skype for business al pool di casa dell'utente. Se si desidera distribuire i Director, è supportato un massimo di 10 per pool. Se si tratta di un elemento necessario, è consigliabile continuare a leggere l'argomento Planning for Directors.

- Proxy inverso. Non si tratta di un componente di Skype for Business Server, ma se si desidera supportare la condivisione di contenuto Web per gli utenti federati, se si intende supportare il traffico per dispositivi mobili, se gli utenti remoti desiderano utilizzare la Rubrica, partecipare a riunioni e così via, questo è un elemento che si vuole avere nell'ambiente. È presente un argomento per la configurazione del server proxy inverso che è possibile estrarre per ulteriori dettagli, quando si è pronti.

Di seguito sono riportate informazioni aggiuntive sulla collocazione di questi server.

Tutti i pool Front end e i server Standard Edition distribuiti nel sito centrale condividono gli elementi seguenti, presupponendo che siano stati distribuiti:

||||
|:-----|:-----|:-----|
|Director o pool di server Director  <br/> |Mediation Server autonomo o pool di Mediation Server  <br/> |server Office Web Apps  <br/> |
|Server perimetrale o pool di server perimetrali  <br/> |Server Chat persistente o pool di server Chat persistente  <br/> |Monitoraggio  <br/> |

Dove si trova il server di messaggistica unificata di Exchange in questo elenco? È certamente possibile utilizzarlo con Skype for Business Server se si desidera eseguire l'integrazione con la messaggistica unificata di Exchange, ma non si tratta di un componente del sito di Skype for Business Server, quindi non viene menzionato qui.

Potrebbe essere necessario disporre di più siti centrali e, in caso affermativo, è possibile condividere i server e i ruoli seguenti, se sono distribuiti nel sito centrale:

|||
|:-----|:-----|
|Mediation Server autonomo o pool di Mediation Server  <br/> |Server perimetrale o pool di server perimetrali  <br/> |
|Server Chat persistente o pool di server Chat persistente  <br/> |Monitoraggio  <br/> |

Analogamente all'ultimo elenco, non viene incluso il server di messaggistica unificata di Exchange, perché non fa parte della distribuzione di Skype for Business Server, ma rientra anche nella stessa categoria.

Ci sono alcuni altri componenti e opzioni che vanno nelle distribuzioni, naturalmente.

|||||
|:-----|:-----|:-----|:-----|
|Firewall  <br/> |Gateway PSTN (se si distribuisce VoIP aziendale  <br/> |Server Messaggistica unificata di Exchange (se si desidera eseguire l'integrazione con la messaggistica unificata di Exchange)  <br/> |Bilanciamento del carico DNS  <br/> |
|Dispositivi di bilanciamento del carico hardware  <br/> |Database di SQL Server  <br/> |Condivisioni file  <br/> ||

## <a name="server-roles"></a>Ruoli del server

Ogni server che esegue Skype for Business Server esegue uno o più ruoli del server. Un ruolo del server è un set definito di funzionalità di Skype for Business Server fornite da quel server. Non è necessario distribuire tutti i ruoli del server disponibili nella rete. Installare solo i ruoli del server che contengono le funzionalità desiderate.

Per la maggior parte dei ruoli del server, ai fini di scalabilità e disponibilità elevata è possibile distribuire pool di più server che eseguono tutti lo stesso ruolo del server. Ogni server in un pool deve eseguire uno o più ruoli del server identici. Per la maggior parte dei tipi di pool in Skype for Business Server, è necessario distribuire un bilanciamento del carico per diffondere il traffico tra i vari server del pool. Skype for Business Server supporta il bilanciamento del carico DNS (Domain Name System) e i dispositivi di bilanciamento del carico hardware.

### <a name="front-end-server-and-back-end-server"></a>Front End Server e server di back-end

In Skype for Business Server Enterprise Edition, il front end server è il ruolo di base del server e gestisce molte funzioni di Basic per Skype for Business Server. Il front end server, insieme ai server back-end, sono gli unici ruoli del server necessari per la distribuzione di Skype for Business Server Enterprise Edition.

Un pool Front End è un insieme di server Front End Server, configurati in modo identico, che funzionano insieme per offrire servizi per un gruppo comune di utenti. Un pool di server multipli che eseguono lo stesso ruolo garantisce funzionalità di scalabilità e failover.

Front End Server include le funzionalità seguenti:

- Autenticazione e registrazione degli utenti.

- Informazioni sulla presenza e lo scambio di schede contatto.

- Servizi Rubrica e espansione della lista di distribuzione.

- Funzionalità di messaggistica istantanea, incluse le conferenze di messaggistica istantanea con più partecipanti.

- Web Conferencing, servizi di conferenza telefonica con accesso esterno PSTN e A/V Conferencing (se distribuito).

- Hosting di applicazioni, per entrambe le applicazioni incluse in Skype for Business Server (ad esempio, operatore conferenza e Response Group Application) e applicazioni di terze parti.

- Facoltativamente, il monitoraggio, per raccogliere informazioni sull'utilizzo informazioni in forma di registrazione dettagli chiamata (CDR) e registrazione errori di chiamata. Queste informazioni forniscono metriche sulla qualità dei file multimediali (audio e video) che attraversano la rete sia per le chiamate VoIP aziendali sia per le conferenze A/V.

- Componenti Web per il supporto di attività basate sul Web come Utilità di pianificazione Web e Join Launcher.

- Facoltativamente, l'archiviazione consente di archiviare le comunicazioni di messaggistica istantanea e il contenuto delle riunioni per motivi di conformità. Per informazioni dettagliate, vedere [Planning for Archiving](https://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx) nella documentazione relativa alla pianificazione.

    In Lync Server 2010 e versioni precedenti, il monitoraggio e l'archiviazione erano ruoli del server distinti, non collocati in front end server.

- Facoltativamente, se la chat persistente è abilitata, Servizi Web della chat persistente per la gestione delle chat room e Servizi Web della chat persistente per l'upload e il download dei file.

I Front End Pool rappresentano inoltre il principale percorso di archiviazione per i dati di utenti e conferenze. Le informazioni relative a ciascun utente sono replicate tra i tre Front End Server nel pool, e il backup è eseguito nei server di back-end.

Inoltre, un front end server nella distribuzione esegue anche il server di gestione centrale, che consente di gestire e distribuire i dati di configurazione di base in tutti i server che eseguono Skype for Business Server. Il server di gestione centrale fornisce anche Lync Server Management Shell e le funzionalità di trasferimento dei file.

I server back-end sono server di database che eseguono Microsoft SQL Server che forniscono i servizi di database per il pool Front end. I server back-end fungono da archivi di backup per i dati dell'utente e della conferenza del pool e sono gli archivi principali di altri database, ad esempio il database Response Group. È possibile disporre di un solo server back-end, ma è consigliabile [eseguire la disponibilità elevata del server back-end in Skype for Business Server](../high-availability-and-disaster-recovery/back-end-server.md) per il failover. I server back-end non eseguono alcun software Skype for Business Server.

> [!IMPORTANT]
> Non è consigliabile collocare i database di Skype for Business Server con altri database. In caso contrario, disponibilità e prestazioni potrebbero risentirne.

> [!NOTE]
> Il mirroring SQL è disponibile in Skype for Business Server 2015 ma non è più supportato in Skype for Business Server 2019. I gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn (FCI) e i metodi di clustering di failover SQL sono preferiti con Skype for Business Server 2019.

Le informazioni archiviate nei database del server di back-end includono informazioni sulla presenza, elenchi di contatti degli utenti, dati sulle conferenze, ad esempio dati persistenti sullo stato di tutte le conferenze correnti, e dati di pianificazione delle conferenze.

### <a name="edge-server"></a>Server perimetrale

Server perimetrale consente agli utenti di comunicare e collaborare con utenti esterni ai firewall dell'organizzazione. Questi utenti esterni possono includere gli utenti dell'organizzazione che attualmente lavorano fuori sede, gli utenti provenienti da organizzazioni partner federate e gli utenti esterni che sono stati invitati a partecipare a conferenze ospitate nella distribuzione di Skype for Business Server.

La distribuzione del server perimetrale attiva inoltre i servizi di mobilità, che supportano le funzionalità di Lync nei dispositivi mobili. Gli utenti possono utilizzare dispositivi mobili Apple iOS, Android, Windows Phone o Nokia supportati per eseguire attività quali l'invio e la ricezione di messaggi istantanei, la visualizzazione dei contatti e la visualizzazione della presenza. I dispositivi mobili inoltre supportano alcune funzionalità di VoIP aziendale, tra cui la possibilità di partecipare a una conferenza mediante clic del mouse, la chiamata tramite ufficio, il numero unico, la segreteria telefonica e le chiamate senza risposta. La funzionalità per dispositivi mobili inoltre supporta le notifiche push per i dispositivi mobili che non supportano le applicazioni eseguite in background. Una notifica push è una notifica inviata a un dispositivo mobile relativamente a un evento che si verifica mentre un'applicazione per dispositivi mobili non è attiva.

I server perimetrali includono inoltre un proxy XMPP (Extensible Messaging and Presence Protocol) pienamente integrato, con gateway XMPP incluso sui Front End Server. È possibile configurare questi componenti XMPP per consentire agli utenti di Skype for Business Server di aggiungere contatti da partner basati su XMPP per la messaggistica istantanea e la presenza.

> [!NOTE]
> I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015 ma non sono più supportati in Skype for Business Server 2019. Per ulteriori informazioni, vedere [migrazione della Federazione XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .

### <a name="mediation-server"></a>Mediation Server

Mediation Server è un componente necessario per l'implementazione di VoIP aziendale, chiamata tramite lavoro e servizi di conferenza telefonica con accesso esterno. Mediation Server converte i segnali e, in alcune configurazioni, i contenuti multimediali tra l'infrastruttura di Skype for Business Server interna e un gateway PSTN (Public Switched Telephone Network), IP-PBX o un trunk SIP (Session Initiation Protocol). È possibile eseguire Mediation Server collocato sullo stesso server del Front End Server, o separato in un pool Mediation Server indipendente.

Per ulteriori informazioni, vedere [Mediation Server Component in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).

### <a name="video-interop-server"></a>Server di interoperabilità video

Video Interop server è un nuovo ruolo di Skype for Business Server 2015. Consente di integrare la distribuzione di Skype for Business Server con determinate soluzioni di terze parti di videoconferenza (video Conferencing System). Un VIS funge da intermediario tra un sistema di teleconferenze di terze parti e una distribuzione di Skype for Business Server. Per questa versione, VIS si concentra sull'interoperabilità con i sistemi video Cisco/Tandberg.

Per ulteriori informazioni, vedere [Plan for video Interop server in Skype for Business Server](../../plan-your-deployment/video-interop-server.md).

### <a name="director"></a>Direttore

Gli amministratori possono autenticare le richieste degli utenti di Skype for Business Server, ma non gli account utente di casa o fornire servizi di conferenza o presenza. I direttori sono molto utili per migliorare la sicurezza nelle distribuzioni che consentono l'accesso degli utenti esterni. Il Director può eseguire l'autenticazione delle richieste prima di inviarle ai server interni. Nel caso di un attacco Denial-of-Service, l'attacco termina con il Director e non raggiunge i Front End Server.

### <a name="persistent-chat-server-roles"></a>Ruoli del server Chat persistente

> [!NOTE]
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team oppure continuare a utilizzare Skype for Business Server 2015.

La Chat persistente consente di partecipare a conversazioni tra più partecipanti basate su argomenti, e permanenti nel tempo. I servizi di chat persistente sono eseguiti dal Front End Server della chat persistente. Il server back-end della chat persistente salva i dati della cronologia delle chat e le informazioni relative a categorie e chat room. Il Compliance server di back-end della chat persistente, facoltativo, può archiviare il contenuto della chat e gli eventi di conformità ai fini della conformità stessa.

Nei server che eseguono Skype for Business Server Standard Edition è inoltre possibile eseguire la chat persistente collocata nello stesso server. Non è possibile collocare il front end server di Persistent Chat con Enterprise Edition Front End Server.

Per ulteriori informazioni, vedere [Plan for Persistent Chat Server in Skype for Business server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

## <a name="high-availability-and-disaster-recovery-support"></a>Supporto per la disponibilità elevata e il ripristino di emergenza

Skype for Business Server garantisce una disponibilità elevata per la ridondanza del server tramite pool. In caso di errore di un server che esegue un determinato ruolo, gli altri server del pool che eseguono lo stesso ruolo sopportano il carico del server in errore. Ciò vale per Front End Server, server perimetrali, Mediation Server e Director.

Skype for Business Server fornisce anche misure di ripristino di emergenza abilitando l'abbinamento del pool. Se si distribuisce questa topologia, vengono designate coppie di pool Front End, in cui ogni pool si trova in un data center distinto e in un'area geografica separata. Se uno dei pool o dei siti diventa inattivo, è possibile reindirizzare gli utenti che vi appartengono all'altro pool della coppia, provocando in questo modo un'interruzione minima del servizio.

Skype for Business Server supporta anche diverse opzioni per la disponibilità elevata del server back-end. Tra le caratteristiche vi sono le seguenti:

- Mirroring del database

- Gruppi di disponibilità AlwaysOn

- Istanze del cluster di failover AlwaysOn (FCI)

- Clustering di failover SQL

Per informazioni dettagliate sull'abbinamento dei pool e sulla disponibilità elevata del server back-end, vedere [pianificare la disponibilità elevata e il ripristino di emergenza in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

## <a name="server-collocation-in-skype-for-business-server"></a>Collocazione dei server in Skype for Business Server

È già stato utilizzato il termine collocae, ma cosa significa questo? Skype for Business Server consente di individuare alcuni ruoli e funzionalità del server sullo stesso server, ovvero la collocazione, o su server diversi, ma può essere confusionario all'inizio e se si sta eseguendo una distribuzione di server Standard Edition o Enterprise Edition (ognuno di essi ha le proprie regole). Per agevolare la pianificazione, è inclusa la collocazione del server nelle distribuzioni di server Standard Edition e nelle distribuzioni di pool Enterprise Edition front end (nella maggior parte dei casi queste informazioni sono identiche e in cui è diverso, è stato chiamato in modo specifico).

### <a name="collocation-of-server-roles"></a>Collocazione dei ruoli del server

Nel server Standard Edition è collocato il ruolo seguente (è necessaria una configurazione aggiuntiva), mentre nel pool Enterprise Edition front end questo ruolo può essere collocato o distribuito in un server separato:

- Mediation

Questi ruoli del server devono essere distribuiti su un server separato:

- Direttore

- Edge

- Server di interoperabilità video

- Office Web Apps

### <a name="databases"></a>Database

Si tratta dell'area con differenze effettive tra distribuzioni di server Standard Edition e distribuzioni di pool di Server Enterprise Edition, quindi sono disponibili due sezioni, seguite da altre regole per entrambi.

#### <a name="standard"></a>Standard

Poiché SQL Server Express è collocato nel server Standard Edition e non può essere spostato, questo è piuttosto semplice. Inoltre, se si distribuisce il server Chat persistente su un server Standard Edition, è anche possibile collocare la chat persistente e il database di conformità di Persistent Chat sul server Standard Edition anche, ma non è necessario.

> [!NOTE]
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team oppure continuare a utilizzare Skype for Business Server 2015.

Non possono essere collocati nel server Standard Edition, ma possono essere installati su un singolo server di database:

- Database di monitoraggio

- Database di archiviazione

- Qualsiasi database back-end di un pool Enterprise Edition front end

#### <a name="enterprise"></a>Enterprise

I database seguenti possono essere collocati nello stesso SQL Server back-end:

- Database back-end

- Database di monitoraggio

- Database di archiviazione

- Database di chat persistente

- Database di conformità di Persistent Chat

#### <a name="both"></a>Sia

A questo punto, sono disponibili ulteriori regole per la collocazione dei database di Skype for Business Server in una singola istanza SQL o in più istanze di SQL nello stesso database di SQL Server:

- Ogni istanza di SQL può contenere solo un singolo database back-end per un pool Enterprise Edition front end, un singolo database di monitoraggio, un singolo database di archiviazione, un singolo database di chat persistente e un singolo database di conformità di Persistent Chat.

- Il server di database non è in grado di supportare più di un pool Enterprise Edition front end, un server che esegue l'archiviazione, un server che esegue il monitoraggio, un singolo database di chat persistente e un singolo database di conformità di Persistent Chat, ma può supportarne uno, indipendentemente dal fatto che i database utilizzino la stessa istanza di SQL Server o di SQL Server.

    > [!NOTE]
    > La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team oppure continuare a utilizzare Skype for Business Server 2015.

### <a name="file-shares"></a>Condivisioni file

La condivisione file può trovarsi in un server separato oppure è possibile collocarla nello stesso server di una o di tutte le operazioni seguenti:

- Server di database, inclusi il server back-end di un pool Enterprise Edition Front End

- Database di monitoraggio

- Database di archiviazione

- Database di chat persistente

- Database di conformità di Persistent Chat

> [!CAUTION]
> Si noti che, sebbene sia possibile collocare la condivisione file su questi server, è importante tenere presente che non è consigliabile. Se si sta collocando la condivisione di file con qualsiasi altro ruolo del server, assicurarsi che si stia monitorando periodicamente lo spazio su disco e i problemi di prestazioni.

### <a name="keep-in-mind"></a>Nota

- Non è possibile collocare un server proxy inverso, che non è un componente di Skype for Business Server, e potrebbe anche non trovarsi nella topologia. Se si desidera supportare la condivisione di contenuto Web per gli utenti federati, è necessario un proxy inverso, tra le altre cose. Se necessario, andare avanti e implementare il supporto per il proxy inverso per Skype for Business Server configurando un server proxy inverso esistente che è già presente nell'organizzazione che viene utilizzato da altre applicazioni.

- Non è possibile collocare alcun componente di messaggistica unificata di Exchange o componente di SharePoint Server con qualsiasi ruolo del server Skype for business.

## <a name="see-also"></a>Vedere anche

[Topologie di riferimento per Skype for Business Server](reference-topologies.md)
