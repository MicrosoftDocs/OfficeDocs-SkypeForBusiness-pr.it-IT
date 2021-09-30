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
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: 'Riepilogo: scegliere la topologia per Skype for Business Server. Informazioni sulla collocazione dei server per Skype for Business Server.'
ms.openlocfilehash: 3fae86501dfc0952bfb3fcf43347a1f0c9641536
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012530"
---
# <a name="topology-basics-for-skype-for-business-server"></a>Nozioni di base sulla topologia per Skype for Business Server

**Riepilogo:** Scegliere la topologia per Skype for Business Server. Informazioni sulla collocazione dei server per Skype for Business Server.

Prima di preparare qualsiasi altra cosa, è necessario sapere che si sta pianificando la topologia giusta per la distribuzione di Skype for Business Server. La prima cosa da decidere è se si ha intenzione di avere una distribuzione locale di Skype for Business Server o se si desidera combinarlo con una distribuzione di Skype for Business Server Online in una distribuzione ibrida. In entrambi i modi, è necessario leggere ulteriormente, in quanto verranno descritte in dettaglio le topologie locali qui, ma i dettagli dell'ambiente ibrido sono documentati nella propria sezione.

È inoltre possibile visualizzare alcune topologie di esempio in [Topologie di riferimento per Skype for Business Server](reference-topologies.md).

## <a name="sites"></a>Siti

In Skype for Business Server, si definiscono i siti nella rete che contengono Skype for Business Server componenti. Un sito è un insieme di computer connessi attraverso una rete a bassa latenza e alta velocità, come una singola rete LAN o due reti connesse tramite una rete a fibra ottica ad alta velocità. Tenere presente che Skype for Business Server siti sono un concetto separato dai siti di Servizi di dominio Active Directory e Microsoft Exchange Server siti. I Skype for Business Server non devono necessariamente corrispondere ai siti di Active Directory.

Skype for Business Server la distribuzione locale di uno o più siti che possono essere ridimensionati in base ai requisiti di disponibilità elevata e posizione.

La distribuzione avrà almeno un sito centrale (denominato anche datacenter, si tratta di un datacenter per tutti i server in essa presenti) e ogni sito centrale della distribuzione avrà un server edizione Standard o almeno un pool Front End di edizione Enterprise. Puoi vedere le differenze in ogni opzione di seguito:

- edizione Standard server include un database SQL Server Express collocato.

- edizione Enterprise Il pool Front End include:

  - Uno o più Front End Server (idealmente almeno tre, per la scalabilità), con un massimo di dodici. Il bilanciamento del carico sarebbe necessario per più di un server.

  - Un server back-end separato.

Ulteriori informazioni sui vari ruoli del server sono disponibili più avanti in questa sezione.

Oltre ai siti centrali, è anche possibile che al sito centrale sia associato uno o più siti di succursale. Dipendono dal sito centrale per quasi tutte le funzionalità, quindi di cosa sono costituito, esattamente?

- Survivable Branch Appliance, che combina un gateway PSTN (Public Switched Telephone Network) con alcune Skype for Business Server funzionalità.

- Survivable Branch Server, è un server che esegue Windows Server in cui è installato Skype for Business Server registrar e Mediation Server.

- Gateway PSTN autonomo (che non fa parte del Survivable Branch Appliance).

- Mediation Server autonomo o pool Mediation Server autonomo (se non si desidera collocare questo ruolo con il Survivable Branch Appliance).

## <a name="whats-in-a-skype-for-business-server-site"></a>Cosa c'è in un Skype for Business Server sito?

Per ottenere informazioni più dettagliate, un sito centrale può anche disporre di:

- Più pool Front End nello stesso dominio o in domini diversi (tenere presente che tutti i Front End Server di un pool Front End, insieme ai server back-end per il pool, devono essere nello stesso dominio).

- Più server Standard Edition.

- Office Web Apps Server, che viene utilizzato con Office Web Apps in Skype for Business Server per la condivisione e il rendering di PowerPoint presentazioni.

- Server perimetrale o pool di server perimetrali (in una rete perimetrale). Necessario se si desidera che la distribuzione supporti i partner federati, la connettività di messaggistica istantanea pubblica, il gateway XMPP (Extensible Messaging and Presence Protocol) e l'accesso degli utenti remoti. Ulteriori dettagli sono disponibili nella documentazione relativa alla pianificazione dei server perimetrali.

- Server Chat persistente. Utile se vuoi che gli utenti siano in grado di partecipare a conversazioni basate su argomenti tra più parti che persistono nel tempo. Per ulteriori informazioni, vedere Planning for Persistent Chat Server.

- Monitoraggio. Usato per supportare la raccolta dei dati per audio/video (A/V) Qualità dell'esperienza (QoE) e registrazione dettagli chiamata (CDR) per VoIP aziendale e conferenze audio/video nella distribuzione. Ne parleremo in dettaglio nell'argomento Planning for Monitoring.

- Director o pool di server Director. Non obbligatorio, ma utile se si desidera migliorare la resilienza e abilitare il reindirizzamento delle richieste Skype for Business utenti al pool principale dell'utente. Se si desidera distribuire Director, è supportato un massimo di 10 per pool. Se è necessario, continuare a leggere l'argomento Planning for Directors.

- Proxy inverso. Non si tratta di un componente di Skype for Business Server, ma se si desidera supportare la condivisione del contenuto Web per gli utenti federati, se si intende supportare il traffico per dispositivi mobili, se gli utenti remoti desiderano utilizzare la rubrica, partecipare alle riunioni e così via, questo è un elemento che si desidera avere nel proprio ambiente. C'è un argomento Setting up Reverse proxy server you can check out for more details, when you're ready.

Ulteriori informazioni sulla collocazione per questi server sono disponibili di seguito.

Tutti i pool Front End e i edizione Standard distribuiti nel sito centrale condividono quanto segue, presupponendo che siano stati distribuiti:

|&nbsp;|&nbsp;|&nbsp;|
|:-----|:-----|:-----|
|Director o pool di server Director   |Mediation Server autonomo o pool Mediation Server   |server Office Web Apps   |
|Server perimetrale o pool di server perimetrali   |Server Chat persistente o pool di server Chat persistente   |Monitoraggio   |

Dove si trova Exchange server Messaggistica unificata in questo elenco? È sicuramente possibile utilizzarlo con Skype for Business Server se si desidera eseguire l'integrazione con la messaggistica unificata di Exchange, ma non è un componente del sito di Skype for Business Server, quindi non viene menzionato qui.

È possibile pianificare la distribuzione di più siti centrali e, in tal caso, possono condividere i server e i ruoli seguenti, se distribuiti nel sito centrale:

|&nbsp;|&nbsp;|
|:-----|:-----|
|Mediation Server autonomo o pool Mediation Server   |Server perimetrale o pool di server perimetrali   |
|Server Chat persistente o pool di server Chat persistente   |Monitoraggio   |

Come nell'ultimo elenco, qui non è incluso il server messaggistica unificata di Exchange perché non fa parte della distribuzione di Skype for Business Server, ma rientra anche nella stessa categoria.

Ci sono alcuni altri componenti e opzioni che vanno nelle distribuzioni, naturalmente.

|&nbsp;|&nbsp;|&nbsp;|&nbsp;|
|:-----|:-----|:-----|:-----|
|Firewall   |Gateway PSTN (se si distribuisce VoIP aziendale   |Exchange Server Messaggistica unificata (se si desidera eseguire l'integrazione con Exchange messaggistica unificata)   |Bilanciamento del carico DNS   |
|Dispositivi di bilanciamento del carico hardware   |Database di SQL Server   |Condivisioni file   ||

## <a name="server-roles"></a>Ruoli del server

Ogni server che Skype for Business Server esegue uno o più ruoli del server. Un ruolo del server è un set definito di Skype for Business Server funzionalità fornite da tale server. Non è necessario distribuire tutti i ruoli del server disponibili nella rete. Installare solo i ruoli del server che contengono le funzionalità desiderate.

Per la maggior parte dei ruoli del server, ai fini di scalabilità e disponibilità elevata è possibile distribuire pool di più server che eseguono tutti lo stesso ruolo del server. Ogni server in un pool deve eseguire uno o più ruoli del server identici. Per la maggior parte dei tipi di pool in Skype for Business Server, è necessario distribuire un servizio di bilanciamento del carico per distribuire il traffico tra i vari server del pool. Skype for Business Server supporta sia il bilanciamento del carico DNS (Domain Name System) che i servizi di bilanciamento del carico hardware.

### <a name="front-end-server-and-back-end-server"></a>Front End Server e server di back-end

In Skype for Business Server edizione Enterprise, il Front End Server è il ruolo di base del server ed esegue molte funzioni Skype for Business Server base. Il Front End Server, insieme ai server back-end, è l'unico ruolo del server necessario in qualsiasi Skype for Business Server edizione Enterprise distribuzione.

Un pool Front End è un insieme di server Front End Server, configurati in modo identico, che funzionano insieme per offrire servizi per un gruppo comune di utenti. Un pool di server multipli che eseguono lo stesso ruolo garantisce funzionalità di scalabilità e failover.

Front End Server include le funzionalità seguenti:

- Autenticazione e registrazione degli utenti.

- Informazioni sulla presenza e scambio di schede contatto.

- Servizi rubrica ed espansione delle liste di distribuzione.

- Funzionalità di messaggistica istantanea, incluse le conferenze di messaggistica istantanea tra più partecipanti.

- Conferenze Web, servizi di conferenza telefonica con accesso esterno PSTN e A/V Conferencing (se distribuiti).

- Hosting di applicazioni, per entrambe le applicazioni incluse in Skype for Business Server (ad esempio, Operatore conferenza e applicazione Response Group) e applicazioni di terze parti.

- Facoltativamente, il monitoraggio, per raccogliere informazioni sull'utilizzo informazioni in forma di registrazione dettagli chiamata (CDR) e registrazione errori di chiamata. Queste informazioni forniscono metriche sulla qualità dei contenuti multimediali (audio e video) che attraversano la rete per VoIP aziendale chiamate e conferenze audio/video.

- Componenti Web per il supporto di attività basate sul Web come Utilità di pianificazione Web e Join Launcher.

- Facoltativamente, l'archiviazione consente di archiviare le comunicazioni di messaggistica istantanea e il contenuto delle riunioni per motivi di conformità. Per informazioni dettagliate, vedere [Planning for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-archiving) nella documentazione relativa alla pianificazione.

    In Lync Server 2010 e versioni precedenti, monitoraggio e archiviazione erano ruoli del server separati, non collocati nel Front End Server.

- Facoltativamente, se la chat persistente è abilitata, Servizi Web della chat persistente per la gestione delle chat room e Servizi Web della chat persistente per l'upload e il download dei file.

I Front End Pool rappresentano inoltre il principale percorso di archiviazione per i dati di utenti e conferenze. Le informazioni relative a ciascun utente sono replicate tra i tre Front End Server nel pool, e il backup è eseguito nei server di back-end.

Inoltre, un Front End Server nella distribuzione esegue anche il server di gestione centrale, che gestisce e distribuisce i dati di configurazione di base in tutti i server che eseguono Skype for Business Server. Il server di gestione centrale fornisce anche Lync Server Management Shell e funzionalità di trasferimento file.

I server back-end sono server di database Microsoft SQL Server che forniscono i servizi di database per il pool Front End. I server back-end fungono da archivi di backup per i dati relativi agli utenti e alle conferenze del pool e sono gli archivi principali per altri database, ad esempio il database di Response Group. È possibile disporre di un singolo server back-end, ma è consigliabile la disponibilità elevata del [server back-end Skype for Business Server](../high-availability-and-disaster-recovery/back-end-server.md) per il failover. I server back-end non eseguono Skype for Business Server software.

> [!IMPORTANT]
> Non è consigliabile collocare Skype for Business Server database con altri database. In caso contrario, disponibilità e prestazioni potrebbero risentirne.

> [!NOTE]
> SQL Il mirroring è disponibile Skype for Business Server 2015, ma non è più supportato in Skype for Business Server 2019. I gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn e i metodi di clustering di failover SQL sono preferiti con Skype for Business Server 2019.

Le informazioni archiviate nei database del server di back-end includono informazioni sulla presenza, elenchi di contatti degli utenti, dati sulle conferenze, ad esempio dati persistenti sullo stato di tutte le conferenze correnti, e dati di pianificazione delle conferenze.

### <a name="edge-server"></a>Server perimetrale

Edge Server consente agli utenti di comunicare e collaborare con utenti esterni ai firewall dell'organizzazione. Questi utenti esterni possono includere gli utenti dell'organizzazione che attualmente lavorano fuori sede, gli utenti di organizzazioni partner federate e gli utenti esterni che sono stati invitati a partecipare alle conferenze ospitate nella distribuzione di Skype for Business Server.

La distribuzione del server perimetrale attiva inoltre i servizi di mobilità, che supportano le funzionalità di Lync nei dispositivi mobili. Gli utenti possono utilizzare dispositivi mobili Apple iOS, Android, Windows Phone o Nokia supportati per eseguire attività quali l'invio e la ricezione di messaggi istantanei, la visualizzazione dei contatti e la visualizzazione della presenza. I dispositivi mobili inoltre supportano alcune funzionalità di VoIP aziendale, tra cui la possibilità di partecipare a una conferenza mediante clic del mouse, la chiamata tramite ufficio, il numero unico, la segreteria telefonica e le chiamate senza risposta. La funzionalità per dispositivi mobili inoltre supporta le notifiche push per i dispositivi mobili che non supportano le applicazioni eseguite in background. Una notifica push è una notifica inviata a un dispositivo mobile relativamente a un evento che si verifica mentre un'applicazione per dispositivi mobili non è attiva.

I server perimetrali includono inoltre un proxy XMPP (Extensible Messaging and Presence Protocol) pienamente integrato, con gateway XMPP incluso sui Front End Server. È possibile configurare questi componenti XMPP per consentire agli utenti Skype for Business Server di aggiungere contatti da partner basati su XMPP per la messaggistica istantanea e la presenza.

> [!NOTE]
> I gateway xMPP e i proxy sono disponibili Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019. Per [ulteriori informazioni, vedere Migrating XMPP federation.](../../../SfBServer2019/migration/migrating-xmpp-federation.md)

### <a name="mediation-server"></a>Mediation Server

Mediation Server è un componente necessario per l'implementazione VoIP aziendale, chiamata tramite lavoro e conferenze telefoniche con accesso esterno. Mediation Server converte la segnalazione e, in alcune configurazioni, i supporti tra l'infrastruttura Skype for Business Server interna e un gateway PSTN (Public Switched Telephone Network), un IP-PBX o un trunk SIP (Session Initiation Protocol). È possibile eseguire Mediation Server collocato sullo stesso server del Front End Server, o separato in un pool Mediation Server indipendente.

Per informazioni dettagliate, vedere [Mediation Server component in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).

### <a name="video-interop-server"></a>Server di interoperabilità video

Video Interop Server è un nuovo ruolo di Skype for Business Server 2015. Consente di integrare la distribuzione Skype for Business Server con alcune soluzioni VTC (Video Teleconferencing System) di terze parti. Un VIS funge da intermediario tra un sistema di teleconferenza di terze parti e una Skype for Business Server distribuzione. Per questa versione, VIS si concentra sull'interoperabilità con i sistemi video Cisco/Tandberg.

Per informazioni dettagliate, vedere [Plan for Video Interop Server in Skype for Business Server](../../plan-your-deployment/video-interop-server.md).

### <a name="director"></a>Direttore

I Director possono autenticare Skype for Business Server utenti, ma non ospitano account utente né forniscono servizi di presenza o conferenza. I Director sono particolarmente utili per migliorare la sicurezza nelle distribuzioni che consentono l'accesso degli utenti esterni. Il Director può autenticare le richieste prima di inviarle ai server interni. In caso di attacco Denial of Service, l'attacco termina con il Director e non raggiunge i Front End Server.

### <a name="persistent-chat-server-roles"></a>Ruoli del server Chat persistente

> [!NOTE]
> La chat persistente è disponibile Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in Teams. Per ulteriori informazioni, vedere [Introduzione all'Microsoft Teams aggiornamento.](/microsoftteams/upgrade-start-here) Se è necessario utilizzare persistent chat, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità Teams o continuare a usare Skype for Business Server 2015.

La Chat persistente consente di partecipare a conversazioni tra più partecipanti basate su argomenti, e permanenti nel tempo. I servizi di chat persistente sono eseguiti dal Front End Server della chat persistente. Il server back-end della chat persistente salva i dati della cronologia delle chat e le informazioni relative a categorie e chat room. Il Compliance server di back-end della chat persistente, facoltativo, può archiviare il contenuto della chat e gli eventi di conformità ai fini della conformità stessa.

I server che Skype for Business Server edizione Standard eseguono chat persistente collocata sullo stesso server. Non è possibile collocare il Front End Server di Persistent Chat edizione Enterprise Front End Server.

Per informazioni dettagliate, [vedere Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

## <a name="high-availability-and-disaster-recovery-support"></a>Disponibilità elevata e supporto per il ripristino di emergenza

Skype for Business Server disponibilità elevata in base alla ridondanza del server tramite il pooling. In caso di errore di un server che esegue un determinato ruolo, gli altri server del pool che eseguono lo stesso ruolo sopportano il carico del server in errore. Ciò vale per Front End Server, server perimetrali, Mediation Server e Director.

Skype for Business Server offre anche misure di ripristino di emergenza abilitando l'associazione dei pool. Se si distribuisce questa topologia, vengono designate coppie di pool Front End, in cui ogni pool si trova in un data center distinto e in un'area geografica separata. Se uno dei pool o dei siti diventa inattivo, è possibile reindirizzare gli utenti che vi appartengono all'altro pool della coppia, provocando in questo modo un'interruzione minima del servizio.

Skype for Business Server supporta inoltre diverse opzioni per la disponibilità elevata del server back-end. Tra le caratteristiche vi sono le seguenti:

- Mirroring del database

- Gruppi di disponibilità AlwaysOn

- Istanze del cluster di failover AlwaysOn

- SQL clustering di failover

Per informazioni dettagliate sull'associazione del pool e sulla disponibilità elevata del server [back-end,](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)vedere Plan for high availability and disaster recovery in Skype for Business Server .

## <a name="server-collocation-in-skype-for-business-server"></a>Collocazione dei server in Skype for Business Server

Abbiamo già usato il termine collocazione, ma cosa significa? Skype for Business Server consente di individuare alcuni ruoli e funzionalità del server nello stesso server, ovvero nella collocazione o in server diversi, ma può creare confusione durante l'avvio e se si sta eseguendo una distribuzione di server di edizione Standard o edizione Enterprise (ognuno con le proprie regole). Per facilitare la pianificazione, è inclusa la collocazione dei server nelle distribuzioni di server edizione Standard e nelle distribuzioni del pool front-end edizione Enterprise (nella maggior parte dei casi queste informazioni sono identiche e dove sono diverse, vengono chiamate in modo specifico).

### <a name="collocation-of-server-roles"></a>Collocazione dei ruoli del server

Il server edizione Standard ha il ruolo seguente collocato (è tuttavia necessaria una configurazione aggiuntiva), mentre nel pool Front End di edizione Enterprise questo ruolo può essere collocato o distribuito in un server separato:

- Mediation

Questi ruoli del server devono essere distribuiti in un server separato:

- Direttore

- Edge

- Server di interoperabilità video

- Office Web Apps

### <a name="databases"></a>Database

Questa è l'area con differenze reali tra distribuzioni di server edizione Standard e distribuzioni di pool di server edizione Enterprise, quindi di seguito saranno disponibili due sezioni, seguite da alcune regole aggiuntive per entrambe.

#### <a name="standard"></a>Standard

Poiché SQL Server Express è collocato nel server edizione Standard e non può essere spostato, questo è piuttosto semplice. Inoltre, se si distribuisce il server Chat persistente in un server edizione Standard, è possibile collocare anche Persistent Chat e il database di conformità di Persistent Chat nel server edizione Standard, ma non è necessario.

> [!NOTE]
> La chat persistente è disponibile Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in Teams. Per ulteriori informazioni, vedere [Introduzione all'Microsoft Teams aggiornamento.](/microsoftteams/upgrade-start-here) Se è necessario utilizzare persistent chat, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità Teams o continuare a usare Skype for Business Server 2015.

Questi server non possono essere collocati nel server edizione Standard, ma possono essere collocati in un singolo server di database:

- Database di monitoraggio

- Database di archiviazione

- Qualsiasi database back-end per un edizione Enterprise Front End

#### <a name="enterprise"></a>Grandi aziende

I database seguenti possono essere collocati nello stesso back-end SQL Server:

- Database back-end

- Database di monitoraggio

- Database di archiviazione

- Database di Persistent Chat

- Database di conformità di Persistent Chat

#### <a name="both"></a>Entrambi

A questo punto, esistono alcune regole aggiuntive da seguire quando si collocano database di Skype for Business Server in una singola istanza di SQL o in più istanze di SQL nello stesso database di SQL Server:

- Ogni istanza SQL può contenere un solo database back-end per un pool Front End di edizione Enterprise, un singolo database di monitoraggio, un singolo database di archiviazione, un singolo database di Persistent Chat e un singolo database di conformità di Persistent Chat.

- Il server database non può supportare più di un pool Front End edizione Enterprise, un server che esegue l'archiviazione, un server che esegue Monitoring, un singolo database di Persistent Chat e un singolo database di conformità di Persistent Chat, ma può supportare uno di essi, indipendentemente dal fatto che i database utilizzino la stessa istanza di SQL Server o istanze separate di SQL Server.

    > [!NOTE]
    > La chat persistente è disponibile Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in Teams. Per ulteriori informazioni, vedere [Introduzione all'Microsoft Teams aggiornamento.](/microsoftteams/upgrade-start-here) Se è necessario utilizzare persistent chat, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità Teams o continuare a usare Skype for Business Server 2015.

### <a name="file-shares"></a>Condivisioni file

La condivisione file può essere in un server separato oppure può essere collocata nello stesso server di uno o tutti gli elementi seguenti:

- Server di database, inclusi il server back-end di un pool Enterprise Edition Front End

- Database di monitoraggio

- Database di archiviazione

- Database di Persistent Chat

- Database di conformità di Persistent Chat

> [!CAUTION]
> Tenere presente che, sebbene sia possibile collocare la condivisione file in questi server, è fondamentale tenere presente che non è consigliabile. Se si colloca la condivisione file con qualsiasi altro ruolo del server, assicurarsi di monitorare regolarmente lo spazio su disco e i problemi di prestazioni.

### <a name="keep-in-mind"></a>Tenere presente che

- Non è possibile collocare un server proxy inverso, che non è un componente Skype for Business Server e potrebbe anche non essere presente nella topologia. È necessario un proxy inverso se si desidera supportare la condivisione del contenuto Web per gli utenti federati, tra le altre cose. Se necessario, procedere con l'implementazione del supporto del proxy inverso per Skype for Business Server configurando un server proxy inverso esistente già presente nell'organizzazione utilizzato da altre applicazioni.

- Non è possibile collocare alcun componente Exchange di messaggistica unificata o SharePoint Server con alcun Skype for Business Server ruolo.

## <a name="see-also"></a>Vedere anche

[Topologie di riferimento per Skype for Business Server](reference-topologies.md)