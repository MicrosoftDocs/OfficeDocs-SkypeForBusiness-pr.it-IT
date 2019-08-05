---
title: Nozioni di base sulla topologia per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: 'Riepilogo: scegliere la topologia per Skype for Business Server. Informazioni sulla collocazione del server per Skype for Business Server.'
ms.openlocfilehash: 00154c754292fd960942f0f0da7f95bb6b5b1c19
ms.sourcegitcommit: da87a3c4c781223ab7de2fb539bb0796dc27ea9e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2019
ms.locfileid: "36196060"
---
# <a name="topology-basics-for-skype-for-business-server"></a>Nozioni di base sulla topologia per Skype for Business Server

**Riepilogo:** Scegliere la topologia per Skype for Business Server. Informazioni sulla collocazione del server per Skype for Business Server.

Prima di preparare qualsiasi altra cosa, è necessario sapere che si sta pianificando la topologia appropriata per la distribuzione di Skype for Business Server. La prima cosa che devi decidere è se vuoi avere una distribuzione locale di Skype for Business Server o se vuoi combinare questa operazione con una distribuzione di Skype for Business Server online in una distribuzione ibrida. In entrambi i casi, si vuole continuare a leggere, in modo da illustrare in dettaglio le topologie locali, ma i dettagli ibridi sono documentati nella propria sezione.

Puoi anche vedere alcune topologie ad esempio in [topologie di riferimento per Skype for Business Server](reference-topologies.md).

## <a name="sites"></a>Siti

In Skype for Business Server Definisci i siti della rete che contengono componenti di Skype for Business Server. Un sito è un set di computer ben connessi da una rete a bassa latenza ad alta velocità, ad esempio una rete LAN (Local Area Network) o due reti connesse da una rete a fibre ottiche ad alta velocità. Tieni presente che i siti di Skype for Business Server sono un concetto separato da siti di servizi di dominio Active Directory e siti di Microsoft Exchange Server. I siti di Skype for Business Server non devono corrispondere ai siti di Active Directory.

Skype for Business Server supporta la distribuzione locale di uno o più siti che possono essere ridimensionati in base ai requisiti di disponibilità e posizione elevati.

La distribuzione avrà almeno un sito centrale (detto anche Datacenter, si tratta di un Data Center per tutti i server in cui si trova) e ogni sito centrale della distribuzione avrà un server standard o almeno un pool di front-end di Enterprise Edition. È possibile visualizzare le differenze tra le opzioni seguenti:

- Il server Standard Edition include un database SQL Server Express collocato.

- Il pool Front End di Enterprise Edition include:

  - Uno o più server front-end (in teoria almeno tre per la scalabilità), con un massimo di dodici. Il bilanciamento del carico sarebbe necessario per più di un server.

  - Un server back-end separato.

Per altre informazioni sui vari ruoli del server, vedere più avanti in questa sezione.

Oltre ai siti centrali, potresti anche avere uno o più siti di succursale associati al sito centrale. Dipendono dal sito centrale per quasi tutte le loro funzionalità, quindi che cosa sono costituiti, esattamente?

- Survivable Branch Appliance, che combina un gateway PSTN (Public Switched Telephone Network), con alcune funzionalità di Skype for Business Server.

- Survivable Branch Server è un server che gestisce Windows Server che include il software di registrazione di Skype for Business Server e Mediation Server installato.

- Gateway PSTN autonomo (che non fa parte del Survivable Branch Appliance).

- Mediation Server autonomo o pool di Mediation Server autonomi (se non si vuole collocare questo ruolo con Survivable Branch Appliance).

## <a name="whats-in-a-skype-for-business-server-site"></a>Cosa contiene un sito di Skype for Business Server?

Per entrare in maggiore dettaglio, un sito centrale può anche avere:

- Più pool Front-End, nello stesso dominio o in domini diversi (tenere presente che tutti i server front-end in un pool Front-End, insieme ai server back-end per il pool, devono essere nello stesso dominio).

- Più server Standard Edition.

- Office Web Apps Server, usato con Office Web Apps in Skype for Business Server per la condivisione e il rendering delle presentazioni di PowerPoint.

- Edge Server o pool Edge (in una rete perimetrale). Necessario se si vuole che la distribuzione supporti i partner federati, la connettività di messaggistica istantanea pubblica, il gateway XMPP (Extensible Messaging and Presence Protocol) e l'accesso degli utenti remoti. Per ulteriori informazioni, vedere la documentazione relativa alla pianificazione di Edge Server.

- Server di chat persistente. Utile se si vuole che gli utenti possano partecipare a conversazioni multiparte, basate su argomenti che persistono nel tempo. Per altre informazioni, vedere l'argomento Pianificazione per il server di chat persistente.

- Monitoraggio. Consente di supportare la raccolta di dati per la qualità dell'esperienza audio/video (QoE) e la registrazione dei dettagli delle chiamate (CDR) per le conferenze di VoIP aziendale e A/V nella distribuzione. Ne discutiamo in dettaglio nell'argomento Pianificazione per il monitoraggio.

- Pool di Director o Director. Non necessario, ma utile se si vuole migliorare la resilienza e consentire il reindirizzamento delle richieste degli utenti di Skype for business al pool di Home dell'utente. Se si vogliono distribuire gli amministratori, è supportato un massimo di 10 per ogni pool. Se si tratta di un aspetto necessario, continuare a leggere definitivamente nell'argomento Pianificazione per gli amministratori.

- Proxy inverso. Non si tratta di un componente di Skype for Business Server, ma se si vuole supportare la condivisione di contenuto Web per gli utenti federati, se si intende supportare il traffico di mobilità, se gli utenti remoti vogliono usare la Rubrica, partecipare a riunioni e così via, si tratta di un aspetto che verrà desidera avere nell'ambiente. È disponibile un argomento per la configurazione del server proxy inverso che è possibile estrarre per altri dettagli, quando si è pronti.

Altre informazioni sulla collocazione per questi server sono disponibili di seguito.

Tutti i pool di front end e i server standard distribuiti nel sito centrale condividono quanto segue, supponendo che siano stati distribuiti:

||||
|:-----|:-----|:-----|
|Pool di Director o Director  <br/> |Mediation Server autonomo o pool di Mediation Server  <br/> |Server Office Web Apps  <br/> |
|Edge Server o pool di Edge  <br/> |Server di chat persistente o pool di server di chat persistente  <br/> |Monitoraggio  <br/> |

Dov'è il server di messaggistica unificata di Exchange in questo elenco? Puoi certamente usarlo con Skype for Business Server se vuoi integrarti con la messaggistica unificata di Exchange, ma non è un componente del sito di Skype for Business Server, quindi non lo menzioniamo qui.

È possibile che si stia pianificando di avere più siti centrali e, se è così, possono condividere i server e i ruoli seguenti, se distribuiti nel sito centrale:

|||
|:-----|:-----|
|Mediation Server autonomo o pool di Mediation Server  <br/> |Edge Server o pool di Edge  <br/> |
|Server di chat persistente o pool di server di chat persistente  <br/> |Monitoraggio  <br/> |

Proprio come l'ultimo elenco, non è incluso il server Messaggistica unificata di Exchange perché non fa parte della distribuzione di Skype for Business Server, ma rientra anche qui nella stessa categoria.

Ci sono alcuni altri componenti e opzioni che vanno in distribuzioni, naturalmente.

|||||
|:-----|:-----|:-----|:-----|
|Firewall  <br/> |Gateway PSTN (se si distribuisce VoIP aziendale  <br/> |Server Messaggistica unificata di Exchange (se si vuole integrare con la messaggistica unificata di Exchange)  <br/> |Bilanciamento del carico DNS  <br/> |
|Dispositivi di bilanciamento del carico hardware  <br/> |Database di SQL Server  <br/> |Condivisioni file  <br/> ||

## <a name="server-roles"></a>Ruoli del server

Ogni server che esegue Skype for Business Server esegue uno o più ruoli del server. Un ruolo del server è un set definito di funzionalità di Skype for Business Server fornite da tale server. Non è necessario distribuire tutti i ruoli del server disponibili nella rete. Installare solo i ruoli del server che contengono la funzionalità desiderata.

Per la maggior parte dei ruoli del server, per la scalabilità e la disponibilità elevata è possibile distribuire pool di più server tutti in grado di eseguire lo stesso ruolo del server. Ogni server in un pool deve eseguire un ruolo o ruoli del server identico. Per la maggior parte dei tipi di pool in Skype for Business Server, è necessario distribuire un bilanciamento del carico per diffondere il traffico tra i vari server del pool. Skype for Business Server supporta il bilanciamento del carico DNS (Domain Name System) e il bilanciamento del carico hardware.

### <a name="front-end-server-and-back-end-server"></a>Server front-end e server back-end

In Skype for Business Server Enterprise Edition il server front-end è il ruolo principale del server e gestisce molte funzioni di base di Skype for Business Server. Il server front-end, insieme ai server back-end, sono gli unici ruoli del server necessari per qualsiasi distribuzione di Skype for Business Server Enterprise Edition.

Un pool Front End è un set di server front-end, configurati in modo identico, che collaborano per creare servizi per un gruppo di utenti comune. Un pool di più server con lo stesso ruolo offre funzionalità di failover e scalabilità.

Il server front-end include le operazioni seguenti:

- Autenticazione utente e registrazione.

- Informazioni sulla presenza e scambio di schede contatto.

- Servizi Rubrica e espansione della lista di distribuzione.

- Funzionalità di messaggistica istantanea, incluse le conferenze di messaggistica istantanea a più parti.

- Servizi di conferenza Web, servizi di conferenza telefonica con accesso esterno PSTN e servizi di conferenza A/V (se distribuiti).

- Applicazione di hosting, per entrambe le applicazioni incluse in Skype for Business Server (ad esempio, assistente per i servizi di conferenza e Response Group Application) e applicazioni di terze parti.

- Facoltativamente, il monitoraggio consente di raccogliere le informazioni sull'utilizzo sotto forma di record dettagli chiamata (CDRs) e record di errore di chiamata (CER). Queste informazioni forniscono le metriche relative alla qualità dei contenuti multimediali (audio e video) che attraversano la rete sia per le chiamate vocali aziendali che per le conferenze A/V.

- Componenti Web per le attività basate sul Web supportate, ad esempio Web Scheduler e Join Launcher.

- Facoltativamente, l'archiviazione consente di archiviare le comunicazioni ISTANTANEe e il contenuto della riunione per motivi di conformità. Per informazioni dettagliate, vedere [pianificazione per l'archiviazione](https://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx) nella documentazione relativa alla pianificazione.

    In Lync Server 2010 e versioni precedenti, il monitoraggio e l'archiviazione erano ruoli server distinti, non collocati nel server front-end.

- Facoltativamente, se è abilitata la chat persistente, i servizi Web di chat persistente per la gestione delle chat room e i servizi Web di chat persistenti per caricare/scaricare file.

I pool Front-End sono anche l'archivio principale per i dati dell'utente e della conferenza. Le informazioni su ogni utente vengono replicate tra tre server front-end nel pool ed è stato eseguito il backup dei server back-end.

Inoltre, un server front-end nella distribuzione esegue anche il server di gestione centrale, che gestisce e distribuisce i dati di configurazione di base in tutti i server che utilizzano Skype for Business Server. Il server di gestione centrale offre anche Lync Server Management Shell e funzionalità di trasferimento file.

I server back-end sono server di database che esegue Microsoft SQL Server che includono i servizi di database per il pool Front-end. I server back-end fungono da archivi di backup per i dati dell'utente e della conferenza del pool e sono gli archivi principali di altri database, ad esempio il database Response Group. È possibile avere un singolo server back-end, ma è consigliabile [eseguire la disponibilità elevata in Skype for Business Server](../high-availability-and-disaster-recovery/back-end-server.md) per il failover. I server back-end non eseguono alcun software Skype for Business Server.

> [!IMPORTANT]
> Non è consigliabile collocare i database di Skype for Business Server con altri database. In questo caso, la disponibilità e le prestazioni potrebbero essere interessate.

> [!NOTE]
> Il mirroring SQL è disponibile in Skype for Business Server 2015 ma non è più supportato in Skype for Business Server 2019. I gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn (FCI) e i metodi di clustering di failover SQL sono preferiti con Skype for Business Server 2019.

Le informazioni archiviate nei database del server back-end includono le informazioni sulla presenza, gli elenchi di contatti degli utenti, i dati di conferenza, inclusi i dati permanenti sullo stato di tutte le conferenze correnti e i dati relativi alla pianificazione delle conferenze.

### <a name="edge-server"></a>Edge Server

Edge Server consente agli utenti di comunicare e collaborare con utenti esterni ai firewall dell'organizzazione. Questi utenti esterni possono includere gli utenti dell'organizzazione che attualmente lavorano fuori sede, utenti provenienti da organizzazioni partner federate e utenti esterni che sono stati invitati a partecipare a conferenze ospitate nella distribuzione di Skype for Business Server.

La distribuzione di Edge Server consente inoltre ai servizi di mobilità, che supportano le funzionalità di Lync nei dispositivi mobili. Gli utenti possono usare i dispositivi mobili Apple iOS, Android, Windows Phone o Nokia supportati per eseguire attività come l'invio e la ricezione di messaggi istantanei, la visualizzazione dei contatti e la visualizzazione della presenza. I dispositivi mobili supportano inoltre alcune funzionalità VoIP aziendale, ad esempio fare clic per partecipare a una conferenza, chiamare tramite lavoro, raggiungere un numero singolo, la segreteria telefonica e le chiamate perse. La funzionalità mobilità supporta anche le notifiche push per i dispositivi mobili che non supportano le applicazioni in uso in background. Una notifica push è una notifica inviata a un dispositivo mobile su un evento che si verifica mentre un'applicazione per dispositivi mobili è inattiva.

I server Edge includono anche un proxy XMPP (Extensible Messaging and Presence Protocol) completamente integrato, con un gateway XMPP incluso nei server front-end. Puoi configurare questi componenti XMPP per consentire agli utenti di Skype for Business Server di aggiungere contatti da partner basati su XMPP per la messaggistica istantanea e la presenza.

> [!NOTE]
> I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019. Per altre informazioni, Vedi [migrazione della Federazione XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .

### <a name="mediation-server"></a>Mediation Server

Mediation Server è un componente necessario per l'implementazione di VoIP aziendale, chiamata tramite lavoro e servizi di conferenza telefonica con accesso esterno. Mediation Server traduce la segnalazione e, in alcune configurazioni, il contenuto multimediale tra l'infrastruttura di Skype for Business Server interna e un gateway PSTN (Public Switched Telephone Network), IP-PBX o un trunk SIP (Session Initiation Protocol). È possibile eseguire Mediation Server nello stesso server del server front-end oppure separato in un pool di Mediation Server autonomo.

Per informazioni dettagliate, vedere [Componente Mediation Server in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).

### <a name="video-interop-server"></a>Video Interop server

Video Interop server è un nuovo ruolo di Skype for Business Server 2015. Consente di integrare la distribuzione di Skype for Business Server con alcune soluzioni di terze parti di VTC (video teleconferenza System). Un VIS funge da intermediario tra un sistema di teleconferenza di terze parti e una distribuzione di Skype for Business Server. Per questa versione, VIS è focalizzata sull'interoperabilità con i sistemi video Cisco/Tandberg.

Per informazioni dettagliate, vedere [pianificare il video Interop server in Skype for Business Server](../../plan-your-deployment/video-interop-server.md).

### <a name="director"></a>Direttore

Gli amministratori possono autenticare le richieste degli utenti di Skype for Business Server, ma non gli account degli utenti privati o offre servizi di conferenza o presenza. Gli amministratori sono più utili per migliorare la sicurezza nelle distribuzioni che consentono l'accesso degli utenti esterni. Il Director può eseguire l'autenticazione delle richieste prima di inviarle ai server interni. Nel caso di un attacco di negazione del servizio, l'attacco termina con il direttore e non raggiunge i server front-end.

### <a name="persistent-chat-server-roles"></a>Ruoli del server di chat persistente

> [!NOTE]
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015.

La chat persistente consente agli utenti di partecipare a conversazioni multiparte, basate su argomenti che persistono nel tempo. Il server front end di chat persistente esegue il servizio di chat persistente. Il server di back-end della chat persistente archivia i dati della cronologia chat e le informazioni sulle categorie e le chat room. Il server back end di conformità della chat persistente opzionale può archiviare il contenuto della chat e gli eventi di conformità ai fini della conformità.

I server che eseguono Skype for Business Server Standard Edition possono eseguire anche la chat persistente collocata nello stesso server. Non è possibile collocare il server front-end della chat persistente con Enterprise Edition Front End Server.

Per informazioni dettagliate, vedere [pianificare il server di chat persistente in Skype for Business server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

## <a name="high-availability-and-disaster-recovery-support"></a>Supporto per la disponibilità elevata e il ripristino di emergenza

Skype for Business Server offre una disponibilità elevata tramite la ridondanza del server tramite pooling. Se un server che esegue un determinato ruolo del server non riesce, gli altri server nel pool che esegue lo stesso ruolo accettano il carico del server. Questo vale per i server front-end, Edge Server, Mediation Server e direttori.

Skype for Business Server offre anche misure per il ripristino di emergenza abilitando l'associazione in pool. Se si distribuisce questa topologia, verranno designate coppie di pool Front-End, con ogni pool in una coppia che si trova in un centro dati separato e in un'area geografica separata. Se si abbassa un pool o un sito, è possibile reindirizzare gli utenti di tale pool a usare l'altro pool nella coppia, con l'interruzione minima del servizio.

Skype for Business Server supporta anche diverse opzioni per la disponibilità elevata del server back-end. Di seguito sono riportate le seguenti:

- Mirroring del database

- Gruppi di disponibilità AlwaysOn

- Istanze del cluster di failover AlwaysOn (FCI)

- Clustering di failover SQL

Per informazioni dettagliate sull'abbinamento del pool e la disponibilità elevata del server back-end, vedere [pianificare l'elevata disponibilità e il ripristino di emergenza in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

## <a name="server-collocation-in-skype-for-business-server"></a>Collocazione del server in Skype for Business Server

È già stato usato il termine collocato, ma cosa significa? Skype for Business Server consente di individuare alcuni ruoli e funzionalità del server nello stesso server, ossia la co-locazione o su server diversi, ma può risultare fuorviante quando si inizia e se si sta eseguendo un server standard o Enterprise Edition distribuzione (ognuno di essi ha le proprie regole). Per facilitare la pianificazione, stiamo includendo la collocazione del server nelle distribuzioni del server Standard Edition e nelle distribuzioni di front end del pool Enterprise Edition (nella maggior parte dei casi queste informazioni sono identiche e in cui è diverso, viene chiamato in modo specifico).

### <a name="collocation-of-server-roles"></a>Collocazione dei ruoli del server

Il server Standard Edition include il ruolo seguente (è necessaria una configurazione aggiuntiva), mentre nel pool Enterprise Edition front-end questo ruolo può essere collocato oppure distribuito in un server distinto:

- Pubblicitari

Questi ruoli del server devono essere distribuiti in un server distinto:

- Direttore

- Bordo

- Video Interop server

- Office Web Apps

### <a name="databases"></a>Database

Questa è l'area con differenze reali tra distribuzioni di server standard e distribuzioni del pool di server di Enterprise Edition, quindi abbiamo due sezioni seguenti, seguite da alcune regole aggiuntive per entrambe.

#### <a name="standard"></a>Standard

Dato che SQL Server Express è collocato nel server Standard Edition e non può essere spostato, è molto semplice. Inoltre, se si distribuisce il server di chat persistente in un server Standard Edition, si è anche in grado di collocare la chat persistente e il database di conformità della chat persistente nel server Standard Edition, ma non è necessario.

> [!NOTE]
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015.

Questi non possono essere collocati nel server Standard Edition, ma possono essere inseriti in un unico server di database:

- Database di monitoraggio

- Database di archiviazione

- Qualsiasi database back-end per un pool di front-end Enterprise Edition

#### <a name="enterprise"></a>Enterprise

I database seguenti possono essere collocati nello stesso SQL Server di back-end:

- Database back-end

- Database di monitoraggio

- Database di archiviazione

- Database di chat persistente

- Database di conformità della chat persistente

#### <a name="both"></a>Sia

Ci sono altre regole da seguire quando si collocano i database di Skype for Business Server in una singola istanza di SQL o in più istanze SQL nello stesso database di SQL Server:

- Ogni istanza di SQL può contenere solo un database back-end per un pool di front end Enterprise Edition, un singolo database di monitoraggio, un singolo database di archiviazione, un singolo database di chat persistente e un singolo database di conformità della chat persistente.

- Il server di database non supporta più di un pool di front end Enterprise Edition, un server che gestisce l'archiviazione, un server che gestisce il monitoraggio, un singolo database di chat persistente e un singolo database di conformità della chat persistente, ma può supportare uno di essi. indipendentemente dal fatto che i database utilizzino la stessa istanza di SQL Server o le istanze separate di SQL Server.

    > [!NOTE]
    > La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015.

### <a name="file-shares"></a>Condivisioni file

La condivisione file può trovarsi in un server separato oppure può essere collocata nello stesso server di una o tutte le operazioni seguenti:

- Server di database, incluso il server back-end di un pool Front-end Enterprise Edition

- Database di monitoraggio

- Database di archiviazione

- Database di chat persistente

- Database di conformità della chat persistente

> [!CAUTION]
> Tieni presente che, anche se è possibile collocare la condivisione file in questi server, è importante tenere presente che non è consigliabile. Se si sta collocando la condivisione di file con qualsiasi altro ruolo del server, verificare che il monitoraggio dello spazio su disco e dei problemi di prestazioni sia regolare.

### <a name="keep-in-mind"></a>Tieni presente

- Non è possibile collocare un server proxy inverso, che non è un componente di Skype for Business Server, e potrebbe anche non essere incluso nella topologia. È necessario un proxy inverso se si vuole supportare la condivisione di contenuto Web per gli utenti federati, tra molti altri elementi. Se necessario, procedere e implementare il supporto del proxy inverso per Skype for Business Server configurando un server proxy inverso esistente già presente nell'organizzazione usato da altre applicazioni.

- Non è possibile collocare un componente di messaggistica unificata di Exchange o un componente di SharePoint Server con un ruolo di Skype for Business Server.

## <a name="see-also"></a>Vedere anche

[Topologie di riferimento per Skype for Business Server](reference-topologies.md)
