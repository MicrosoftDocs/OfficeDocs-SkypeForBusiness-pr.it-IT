---
title: Pianificare la resilienza di VoIP aziendale in Skype for Business Server
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
ms.assetid: b3671dcb-6a8b-4a06-84da-0c8837b35099
description: Informazioni su come supportare la resilienza vocale in Skype for Business Server VoIP aziendale, sia in siti centrali che in siti di succursale. Le opzioni del sito della filiale includono la distribuzione di appliance Survivable Branch o Survivable Branch Servers.
ms.openlocfilehash: 2ede1677e59753e5f8f39b3e9a35221041b56263
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187700"
---
# <a name="plan-for-enterprise-voice-resiliency-in-skype-for-business-server"></a>Pianificare la resilienza di VoIP aziendale in Skype for Business Server

Informazioni su come supportare la resilienza vocale in Skype for Business Server VoIP aziendale, sia in siti centrali che in siti di succursale. Le opzioni del sito della filiale includono la distribuzione di appliance Survivable Branch o Survivable Branch Servers.

La resilienza vocale si riferisce alla capacità degli utenti di continuare a effettuare e ricevere chiamate se un sito centrale che ospita Skype for Business Server non è disponibile, sia tramite un errore WAN (Wide Area Network) che con un'altra causa. Se un sito centrale non riesce, il servizio VoIP aziendale deve continuare senza interruzioni attraverso il failover continuo in un sito di backup. In caso di errore WAN, le chiamate del sito di succursale devono essere reindirizzate a un gateway PSTN locale. In questa sezione viene illustrata la pianificazione della resilienza vocale in caso di errori WAN o del sito centrale.

## <a name="central-site-resiliency"></a>Resilienza del sito centrale

Sempre più spesso, le aziende hanno più siti distribuiti in tutto il mondo. La gestione dei servizi di emergenza, l'accesso al supporto tecnico e la possibilità di svolgere attività commerciali critiche quando un sito centrale è fuori servizio sono essenziali per qualsiasi soluzione di resilienza vocale aziendale. Quando un sito centrale diventa non disponibile, è necessario che siano soddisfatte le condizioni seguenti:

- Il failover vocale deve essere specificato.

- Gli utenti che normalmente si iscrivono con il pool Front-end presso il sito centrale devono essere in grado di eseguire la registrazione con un pool di front end alternativo. Questa operazione può essere eseguita creando più record SRV DNS, ognuno dei quali viene risolto in un pool di Director o in un pool di front-end in ognuno dei siti centrali. È possibile modificare la priorità e i pesi dei record SRV in modo che gli utenti serviti da tale sito centrale ottengano il relativo Director e il pool Front end prima di quelli presenti in altri record SRV.

- Le chiamate da e verso gli utenti che si trovano in altri siti devono essere reinstradate alla rete PSTN.

Questo argomento descrive la soluzione consigliata per la protezione della resilienza vocale del sito centrale.

### <a name="architecture-and-topology"></a>Architettura e topologia

La pianificazione della resilienza vocale in un sito centrale richiede una conoscenza di base del ruolo centrale svolto da Skype for Business Server registrar per abilitare il failover vocale. Il registrar di Skype for Business Server è un servizio che consente la registrazione e l'autenticazione del client e fornisce servizi di routing. Viene eseguito in tutti i server standard, Front End Server, Director o Survivable Branch Appliance. Un pool di registrar è costituito da servizi di registrazione eseguiti nel pool Front-end e residenti nello stesso sito. Un client Skype for Business individua il pool Front-end tramite il meccanismo di individuazione seguente:

1. Record SRV DNS

2. Servizio Web di individuazione automatica

3. Opzione DHCP 120

Dopo che il client Skype for business si connette al pool Front-End, viene diretto dal bilanciamento del carico su uno dei server front-end nel pool. Il server front-end, a sua volta, reindirizza il client a un registrar preferito nel pool.

Ogni utente abilitato per VoIP aziendale viene assegnato a un pool di registrar specifico, che diventa il pool di registrar principale dell'utente. In un sito specifico, centinaia o migliaia di utenti condividono in genere un singolo pool di registrar principale. Per tenere conto del consumo di risorse del sito centrale da parte di tutti gli utenti del sito della filiale che si basano sul sito centrale per presenza, conferenza o failover, è consigliabile considerare ogni utente del sito filiale come se l'utente fosse un utente registrato nel sito centrale. Attualmente non esistono limiti al numero di utenti del sito succursale, inclusi gli utenti registrati con un Survivable Branch Appliance.

Per garantire la resilienza vocale in caso di errore di un sito centrale, il pool di registrar principale deve avere un unico pool di registrar di backup designato situato in un altro sito. Il backup può essere configurato usando le impostazioni di resilienza del generatore di topologia. Supponendo che un collegamento WAN resiliente tra i due siti, gli utenti il cui pool di registrar principale non è più disponibile vengano automaticamente indirizzati al pool di registrar di backup.

I passaggi seguenti descrivono il processo di individuazione e registrazione del client:

1. Un client individua Skype for Business Server tramite i record SRV DNS. In Skype for Business Server i record SRV DNS possono essere configurati in grado di restituire più di un FQDN alla query SRV DNS. Ad esempio, se Enterprise Contoso ha tre siti centrali (Nord America, Europa e Asia-Pacifico) e un pool di Director in ogni sito centrale, i record SRV DNS possono puntare agli FQDN del pool di Director in ognuna delle tre posizioni. Purché il pool di Director in una delle posizioni sia disponibile, il client può connettersi al primo server Skype for business hop.

    > [!NOTE]
    > L'uso di un pool di Director è facoltativo. È invece possibile usare un pool Front-end.

2. Il pool di Director informa il client Skype for business sul pool di registrar principale dell'utente e sul pool di registrar di backup.

3. Il client Skype for business tenta innanzitutto di connettersi al pool di registrar principale dell'utente. Se il pool di registrar principale è disponibile, il registrar accetta la registrazione. Se il pool di registrar principale non è disponibile, il client Skype for business tenterà di connettersi al pool di registrazione di backup. Se il pool di registrar di backup è disponibile e ha determinato che il pool di registrar principale dell'utente non è disponibile (rilevando una mancanza di heartbeat per un intervallo di failover specificato), il pool di registrar accetta la registrazione dell'utente. Dopo che il registrar di backup rileva che il registrar principale è di nuovo disponibile, il pool di registrazione di backup reindirizza i client di failover nel pool principale.

### <a name="requirements-and-recommendations"></a>Requisiti e suggerimenti

I requisiti e le raccomandazioni seguenti per l'implementazione della resilienza vocale del sito centrale sono appropriati per la maggior parte delle organizzazioni:

- I siti in cui risiedono i pool di registrar primari e di backup devono essere connessi da un collegamento WAN resiliente.

- Ogni sito centrale deve contenere un pool di registrar costituito da uno o più registrar.

- Ogni pool di registrar deve essere bilanciato tramite bilanciamento del carico DNS, bilanciamento del carico hardware o entrambi. Per informazioni dettagliate sulla pianificazione della configurazione del bilanciamento del carico, vedere [requisiti di bilanciamento del carico per Skype for business](../../plan-your-deployment/network-requirements/load-balancing.md).

- Ogni utente deve essere assegnato a un pool di registrar principale usando il cmdlet **Set-CsUser** di Skype for Business Server Management Shell o il pannello di controllo di Skype for Business Server.

- Il pool di registrar principale deve avere un singolo pool di registrar di backup situato in un sito centrale diverso.

- Il pool di registrar principale deve essere configurato per il failover nel pool di registrazione di backup. Per impostazione predefinita, il registrar principale è impostato per il failover nel pool di registrar di backup dopo un intervallo di 300 secondi. Puoi modificare questo intervallo usando il generatore di topologia di Skype for Business Server.

- Configurare una route di failover. Quando si configura la route, specificare un gateway che si trova in un sito diverso dal gateway specificato nella route principale.

- Se il sito centrale conteneva il server di gestione principale e probabilmente il sito è in calo per un periodo prolungato, sarà necessario reinstallare gli strumenti di gestione nel sito di backup. in caso contrario, non sarà possibile modificare le impostazioni di gestione.

### <a name="dependencies"></a>Dipendenze

Skype for Business Server dipende dai seguenti componenti di infrastruttura e software per assicurare la resilienza vocale:

|**Componente** <br/> |**Funzionale** <br/> |
|:-----|:-----|
|DNS  <br/> |Risoluzione di record SRV e record per la connettività server-server e client-server  <br/> |
|Servizi Web Exchange e Exchange (EWS)  <br/> |Archiviazione contatti; dati del calendario  <br/> |
|Servizi Web di Exchange e messaggistica unificata  <br/> |Registri delle chiamate, elenco della segreteria telefonica, casella vocale  <br/> |
|Opzioni DHCP 120  <br/> |Se DNS SRV non è disponibile, il client tenterà di usare l'opzione DHCP 120 per individuare il registrar. Affinché questo funzioni, è necessario configurare un server DHCP o abilitare il protocollo DHCP di Skype for Business Server.  <br/> |

### <a name="survivable-voice-features"></a>Funzionalità vocali Survivable

Se sono stati implementati i requisiti e le raccomandazioni precedenti, le funzionalità vocali seguenti verranno fornite dal pool di registrazione di backup:

- Chiamate PSTN in uscita

- Chiamate PSTN in ingresso, se il provider del servizio di telefonia supporta la possibilità di eseguire il failover in un sito di backup

- Chiamate aziendali tra utenti sia nello stesso sito che tra due siti diversi

- Gestione delle chiamate di base, incluso il blocco delle chiamate, il recupero e il trasferimento

- Messaggistica istantanea con due parti e condivisione di audio e video tra utenti nello stesso sito

- Inoltro di chiamata, squillo simultaneo di endpoint, delegazione delle chiamate e servizi di chiamata del team, ma solo se entrambe le parti per chiamare delegazione o tutti i membri del team sono configurate nello stesso sito.

- I telefoni e i client esistenti continuano a funzionare.

- Registrazione dettagli chiamata (CDR)

- Autenticazione e autorizzazione

A seconda del modo in cui sono configurate, le funzionalità vocali seguenti potrebbero non funzionare quando un sito centrale principale non è più in servizio:

- Deposito e recupero della segreteria telefonica

    Se si vuole rendere disponibile la messaggistica unificata di Exchange quando il sito centrale principale non è in servizio, è necessario eseguire una delle operazioni seguenti:

  - Modificare i record SRV DNS in modo che i server di messaggistica unificata di Exchange nel sito centrale puntino ai server di messaggistica unificata di Exchange in un altro sito.

  - Configurare il dial plan di messaggistica unificata di Exchange di ogni utente per includere i server di messaggistica unificata di Exchange sia nel sito centrale che nel sito di backup, ma designa i server di messaggistica unificata di Exchange come disabilitati. Se il sito principale diventa non disponibile, l'amministratore di Exchange deve contrassegnare i server di messaggistica unificata di Exchange nel sito di backup come abilitato.

    Se nessuna delle soluzioni precedenti è possibile, la messaggistica unificata di Exchange non sarà disponibile in caso il sito centrale diventi non disponibile.

- Conferenze di tutti i tipi

    Un utente che ha eseguito il failover in un sito di backup può partecipare a una conferenza creata o ospitata da un organizzatore il cui pool è disponibile, ma non può creare o ospitare una conferenza nel proprio pool principale, che non è più disponibile. Analogamente, altri utenti non possono partecipare a conferenze ospitate nel pool principale dell'utente interessato.

Le funzionalità vocali seguenti non funzionano quando un sito centrale principale non è più in servizio:

- Operatore automatico conferenza

- Presenza e routing basato su DND

- Aggiornamento delle impostazioni di inoltro di chiamata

- Servizio Response Group e parcheggio delle chiamate

- Provisioning di nuovi telefoni e client

- Ricerca Web Rubrica

## <a name="branch-site-resiliency"></a>Resilienza del sito della filiale

Se si vuole specificare la resilienza del sito di succursale, ossia il servizio VoIP aziendale a elevata disponibilità, sono disponibili tre opzioni:

- Survivable Branch Appliance

- Survivable Branch Server

- Una distribuzione completa di Skype for Business Server nel sito della filiale

Questa guida ti aiuterà a valutare la soluzione di resilienza migliore per l'organizzazione e, in base alla tua soluzione di resilienza, la soluzione di connettività PSTN da usare. Sarà inoltre utile preparare la distribuzione della soluzione scelta descrivendo i prerequisiti e altre considerazioni sulla pianificazione.

### <a name="branch-site-resiliency-features"></a>Caratteristiche di resilienza del sito filiale

Se si specifica la resilienza del sito di succursale, se la connessione WAN di un sito di succursale a un sito centrale non riesce o se il sito centrale non è raggiungibile, è necessario che le caratteristiche vocali seguenti continuino a essere disponibili:

- Chiamate PSTN (Public Switched Telephone Network) in ingresso e in uscita

- Chiamate aziendali tra utenti sia nello stesso sito che tra due siti diversi

- Gestione delle chiamate di base, incluso il blocco delle chiamate, il recupero e il trasferimento

- Messaggistica istantanea a due parti

- Inoltro di chiamata, squillo simultaneo di endpoint, delega delle chiamate e servizi di chiamata del team, ma solo se il delegante e il delegato, ad esempio un Manager e l'amministratore del responsabile, o tutti i membri del team, sono configurati nello stesso sito

- Record dettagli chiamata (CDRs)

- Servizi di conferenza telefonica con accesso esterno PSTN con l'operatore automatico di conferenza

- Funzionalità della segreteria telefonica se si configurano le impostazioni di reinstradamento della segreteria telefonica.

- Autenticazione e autorizzazione dell'utente

Le caratteristiche seguenti sono disponibili solo se la soluzione di resilienza è una distribuzione su vasta scala di Skype for Business Server presso il sito della filiale:

- Servizi di conferenza di messaggistica istantanea, Web e A/V

- Routing basato su presenza e non disturbare (DND) (dove le chiamate non squillano in estensioni con DND attivato)

- Aggiornamento delle impostazioni di inoltro di chiamata

- Applicazione Response Group Application e Call Park

- Provisioning di nuovi telefoni e client, ma solo se i servizi di dominio Active Directory sono presenti nel sito della filiale.

- Enhanced 9-1-1 (E9-1-1)

    Se E9-1-1 è distribuito e il trunk SIP nel sito centrale non è disponibile perché il collegamento WAN è in calo, il Survivable Branch Appliance instraderà le chiamate E9-1-1 al gateway della filiale locale. Per abilitare questa funzionalità, i criteri vocali degli utenti del sito della filiale devono instradare le chiamate al gateway locale in caso di errore WAN.

> [!NOTE]
> SBA (Survivable Branch Office) non è supportato per XMPP. Gli utenti ospitati in una configurazione SBA non saranno in grado di inviare messaggi istantanei o vedere la presenza con contatti XMPP.

### <a name="branch-site-resiliency-solutions"></a>Soluzioni di resilienza del sito filiale

Sono evidenti i vantaggi per fornire alla propria organizzazione la resilienza del sito di succursale. In particolare, se si perde la connessione al sito centrale, gli utenti del sito succursale continueranno ad avere il servizio VoIP aziendale e la segreteria telefonica (se si configurano le impostazioni di reinstradamento della segreteria telefonica). Tuttavia, per i siti con meno di 25 utenti, una soluzione di resilienza potrebbe non fornire un rendimento sufficiente per gli investimenti.

Se si decide di specificare la resilienza del sito filiale, sono disponibili tre opzioni. La tabella seguente può aiutare a determinare l'opzione migliore per l'organizzazione.

|**Se si...**|**Ti consigliamo di usare un...**|
|:-----|:-----|
|Ospita tra gli utenti di 25 e 1000 nel sito di succursale e se il ritorno sugli investimenti non supporta una distribuzione completa o il supporto amministrativo locale non è disponibile  <br/> |Survivable Branch Appliance  <br/> Survivable Branch Appliance è un server blade di livello industriale con un registrar di Skype for Business Server e Mediation Server in uso in Windows Server 2008 R2. Il Survivable Branch Appliance contiene anche un gateway PSTN (Public Switched Telephone Network). I dispositivi di terze parti qualificati (sviluppati da Microsoft Partners nel programma di qualifica/certificazione di Survivable Branch Appliance (SBA)) garantiscono una connessione PSTN continua in caso di errore WAN, ma questo approccio non offre una soluzione resiliente presenza e conferenza perché queste funzionalità dipendono dai server front-end nel sito centrale.  <br/> Per informazioni dettagliate sugli elettrodomestici Survivable Branch, vedere "dettagli Survivable Branch Appliance" più avanti in questo argomento.  <br/> **Nota:** Se si decide di usare anche un trunk SIP con l'appliance Survivable Branch, contattare il fornitore Survivable Branch Appliance per conoscere il provider di servizi migliore per l'organizzazione. <br/> |
|Host tra gli utenti di 1000 e 2000 nel sito di succursale, non hanno una connessione WAN resiliente e sono disponibili amministratori di Skype for Business Server.  <br/> |Survivable Branch Server o due Survivable Branch Appliance.  <br/> Il Survivable Branch Server è una riunione di Windows Server requisiti hardware specificati che contiene Skype for Business Server registrar e il software Mediation Server installato. Deve essere collegato a un gateway PSTN o a un trunk SIP a un provider di servizi telefonici.  <br/> Per informazioni dettagliate sui Survivable Branch Server, vedere "dettagli Survivable Branch Server" più avanti in questo argomento.  <br/> |
|Se hai bisogno di funzionalità di presenza e conferenze oltre alle funzionalità vocali per un massimo di 5000 utenti e hai addestrato gli amministratori di Skype for Business Server disponibili  <br/> |Distribuire come sito centrale con un server Standard Edition anziché come sito di succursale.  <br/> Una distribuzione su vasta scala di Skype for Business Server offre una connessione PSTN continua e una presenza resiliente e conferenze in caso di errore WAN.  <br/> |

#### <a name="resiliency-topologies"></a>Topologie di resilienza

La figura seguente mostra le topologie consigliate per la resilienza del sito di succursale.

**Opzioni di resilienza del sito filiale**

![Opzioni di resilienza vocale dei siti di succursale (o siti derivati)](../../media/Plan_OCS_Voice_BranchResiliencyOptions.jpg)

#### <a name="survivable-branch-appliance-details"></a>Dettagli Survivable Branch Appliance

Il Survivable Branch Appliance di Skype for Business Server include i componenti seguenti:

- Registrar per l'autenticazione utente, la registrazione e il routing delle chiamate

- Un Mediation Server per la gestione della segnalazione tra il registrar e un gateway PSTN

- Gateway PSTN per il routing delle chiamate alla rete PSTN come trasporto di fallback in caso di interruzioni WAN

- SQL Server Express per l'archiviazione dei dati dell'utente locale

Il Survivable Branch Appliance include anche trunk PSTN, porte analogiche e una scheda Ethernet.

Se la connessione WAN del sito della filiale a un sito centrale diventa non disponibile, gli utenti di Branch interni continuano a essere registrati presso il registrar Survivable Branch Appliance e a ottenere il servizio vocale ininterrotto usando la connessione Survivable Branch Appliance alla rete PSTN. Gli utenti del sito della filiale che si connettono da una sede o da altre posizioni remote potranno eseguire la registrazione presso un server di registrazione in un sito centrale se il collegamento WAN al sito della filiale non è disponibile. Questi utenti avranno la funzionalità di comunicazioni unificate completa, con l'unica eccezione che le chiamate in ingresso al sito della filiale andranno alla segreteria telefonica. Quando la connessione WAN diventa disponibile, la funzionalità completa deve essere ripristinata agli utenti del sito succursale. Né il failover per il Survivable Branch Appliance né il ripristino del servizio richiedono la presenza di un amministratore IT.

Skype for Business Server supporta fino a due Survivable Branch Appliance in un sito di succursale.

#### <a name="survivable-branch-appliance-deployment-overview"></a>Panoramica della distribuzione Survivable Branch Appliance

Il Survivable Branch Appliance è prodotto da produttori di apparecchiature originali in collaborazione con Microsoft e distribuito per loro conto da rivenditori a valore aggiunto. Questa distribuzione deve avvenire solo dopo la distribuzione di Skype for Business Server presso il sito centrale, una connessione WAN al sito di succursale e gli utenti del sito succursale sono abilitati per VoIP aziendale.

Per informazioni dettagliate su queste fasi, vedere [distribuzione di un Survivable Branch Appliance o server](https://technet.microsoft.com/library/cb780c14-dc5f-41ba-8092-f20ae905bd16.aspx) nella documentazione relativa alla distribuzione.

|**Fase**|**Passaggi**|**Diritti utente**|
|:-----|:-----|:-----|
|Configurare servizi di dominio Active Directory per Survivable Branch Appliance  <br/> |**Nel sito centrale:** <br/>  Creare un account utente di dominio (o un'identità aziendale) per il tecnico che installerà e attiverà il Survivable Branch Appliance presso il sito della filiale. <br/>  Creare un account del computer (con il nome di dominio completo applicabile) per Survivable Branch Appliance in servizi di dominio Active Directory. <br/>  In Generatore di topologie creare e pubblicare l'appliance Survivable Branch. <br/> |L'account utente tecnico deve essere un membro di RTCUniversalSBATechnicians. Il Survivable Branch Appliance deve appartenere al gruppo RTCSBAUniversalServices, che si verifica automaticamente quando si usa generatore di topologie.  <br/> |
|Installare e attivare Survivable Branch Appliance.  <br/> |**Nel sito della filiale:** <br/>  Connettere il Survivable Branch Appliance a una porta Ethernet e a una porta PSTN. <br/>  Avviare Survivable Branch Appliance. <br/>  Aggiungere il Survivable Branch Appliance al dominio usando l'account utente di dominio creato per Survivable Branch Appliance nel sito centrale. Impostare il nome di dominio completo e l'indirizzo IP in base al nome di dominio completo creato nell'account del computer. <br/>  Configurare l'appliance Survivable Branch utilizzando l'interfaccia utente OEM. <br/>  Testare la connettività PSTN. <br/> |L'account utente tecnico deve essere un membro di RTCUniversalSBATechnicians.  <br/> |

#### <a name="survivable-branch-server-details"></a>Dettagli Survivable Branch Server

In Generatore di topologia creare il sito della filiale, aggiungere il Survivable Branch Server a tale sito e quindi eseguire la distribuzione guidata di Skype for Business Server nel computer in cui si vuole installare il ruolo.

### <a name="branch-site-resiliency-requirements"></a>Requisiti di resilienza del sito filiale

Questo argomento consente di preparare gli utenti per la sopravvivenza della filiale e della segreteria telefonica e specifica anche i requisiti hardware e software pertinenti.

#### <a name="preparing-branch-users-for-branch-site-resiliency"></a>Preparazione degli utenti della filiale per la resilienza del sito filiale

Preparare gli utenti per la resilienza del sito di succursale impostando il pool di registrar come Survivable Branch Appliance (SBA) o Survivable Branch Server.

#### <a name="registrar-assignments-for-branch-users"></a>Assegnazioni del registrar per gli utenti della filiale

Indipendentemente dalla soluzione di resilienza del sito di succursale scelta, è necessario assegnare un registrar principale a ogni utente. Gli utenti del sito succursale devono sempre registrarsi con il Registrar presso il sito della filiale, indipendentemente dal fatto che il registrar si trovi nella Survivable Branch Appliance, Survivable Branch Server o in Skype for Business Server standard o Enterprise Edition Server. È necessario un record di risorse del servizio DNS (Domain Name System) (SRV) in modo che un client possa individuare il pool di registrar. Se il Survivable Branch Appliance diventa non disponibile, questo è il modo in cui i client del sito Branch verranno automaticamente individuati nel registrar.

Se un sito di succursale non ha un server DNS, esistono due modi alternativi per configurare l'individuazione di Survivable Branch Appliance o Survivable Branch Server:

- Configurare l'opzione DHCP 120 nel server DHCP (Dynamic Host Configuration Protocol) del sito della filiale in modo che punti al nome di dominio completo (FQDN) del Survivable Branch Appliance o Survivable Branch Server.

- Configurare Survivable Branch Appliance o Survivable Branch Server per rispondere alle query di 120 DHCP.

#### <a name="voice-routing-for-branch-users"></a>Routing vocale per gli utenti di Branch

È consigliabile creare un criterio VoIP (Voice over Internet Protocol) separato per gli utenti in un sito di succursale. Questo criterio deve includere una route primaria che usa il gateway Survivable Branch Appliance o Branch Server e una o più route di backup che usano un trunk con un gateway PSTN (Public Switched Telephone Network) nel sito centrale. Se la route principale non è disponibile, viene usata invece la route di backup che usa uno o più gateway di sito centrale. In questo modo, indipendentemente dalla posizione in cui un utente è registrato, nel registrar del sito succursale o nel pool di registrazione del backup presso il sito centrale, il criterio VoIP dell'utente è sempre attivo. Si tratta di una considerazione importante per gli scenari di failover. Ad esempio, se è necessario rinominare il Survivable Branch Appliance o riconfigurare Survivable Branch Appliance per connettersi a un pool di registrar di backup presso il sito centrale, è necessario trasferire gli utenti del sito della filiale nel sito centrale per la durata. Per informazioni dettagliate sulla ridenominazione o la riconfigurazione di un Survivable Branch Appliance, vedere l' [Appendice B: gestione di un Survivable Branch Appliance](https://technet.microsoft.com/library/2ec9d505-6d39-491c-9524-8cf36866b855.aspx) nella documentazione relativa alla distribuzione. Se gli utenti non hanno criteri VoIP a livello di utente o piani di chiamata a livello di utente, quando gli utenti vengono spostati in un altro sito, i criteri VoIP a livello di sito e i piani di chiamata a livello di sito del sito centrale si applicano agli utenti per impostazione predefinita, al posto del VoIP a livello di sito del sito della filiale. criteri e dial plan,. In questo scenario, a meno che i criteri VoIP a livello di sito e i piani di chiamata a livello di sito usati dal pool di registrazione di backup possano essere applicati anche agli utenti del sito succursale, le chiamate non riusciranno. Ad esempio, se gli utenti di un sito di filiale che si trovano in Giappone vengono spostati in un sito centrale di Redmond, un dial plan con regole di normalizzazione che prevedono + 1425 a tutte le chiamate a 7 cifre è improbabile che si traducano in modo appropriato le chiamate per tali utenti.

> [!IMPORTANT]
> Quando si crea una route di backup di una filiale, è consigliabile aggiungere due record di utilizzo PSTN al criterio utente della filiale e assegnare le route separate a ognuna di esse. La route First o Primary indirizza le chiamate al gateway associato a Survivable Branch Appliance (SBA) o Branch Server; la route secondo o backup consentirebbe di indirizzare le chiamate al gateway nel sito centrale. In indirizzamento delle chiamate, l'SBA o il server di succursale tenterà tutte le route assegnate al primo record di utilizzo PSTN prima di tentare il secondo record di utilizzo.

Per assicurarti che le chiamate in ingresso agli utenti del sito succursale raggiungano questi utenti quando il gateway di succursale o il componente Windows del sito Survivable Branch Appliance non è disponibile (il che accadrebbe, ad esempio, se il Survivable Branch Appliance o Branch il gateway non è più disponibile per la manutenzione), crea una route di failover nel gateway (o usa il provider di chiamate dirette in diretta) per reindirizzare le chiamate in arrivo al pool di registrazione del backup presso il sito centrale. Da lì le chiamate verranno instradate sul collegamento WAN agli utenti di Branch. Assicurarsi che la route traguardi i numeri in modo che siano conformi al gateway PSTN o ad altri formati di numeri di telefono accettati del peer trunk. Per informazioni dettagliate sulla creazione di una route di failover, vedere [configurazione di una route di failover](https://technet.microsoft.com/library/76e48df4-3b78-4fb7-b1f7-c1e604b81bad.aspx). Creare anche piani di chiamata a livello di servizio per il trunk associato al gateway nel sito della filiale per normalizzare le chiamate in arrivo. Se si dispone di due appliance Survivable Branch in un sito di succursale, è possibile creare un dial plan a livello di sito per entrambi, a meno che non sia necessario un piano separato a livello di servizio.

> [!NOTE]
> Per tenere conto del consumo di risorse del sito centrale da parte di tutti gli utenti del sito di succursale che si basano sul sito centrale per presenza, conferenza o failover, è consigliabile considerare ogni utente del sito filiale come se l'utente fosse registrato presso il sito centrale. Attualmente non esistono limiti al numero di utenti del sito succursale, inclusi gli utenti registrati con un Survivable Branch Appliance.

Ti consigliamo anche di creare un dial plan a livello di utente e un criterio vocale e quindi assegnarlo agli utenti del sito succursale. Per informazioni dettagliate, vedere [creare o modificare un dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md) e [creare i criteri di routing VoIP per gli utenti della filiale](https://technet.microsoft.com/library/10deca9f-f870-4a42-b25d-e4fc53108658.aspx) nella documentazione relativa alla distribuzione.

#### <a name="routing-extension-numbers"></a>Numeri di interno di routing

Quando si preparano i dial plan e i criteri vocali per gli utenti del sito succursale, assicurarsi di includere regole di normalizzazione e regole di traduzione corrispondenti alle stringhe e al formato numerico usati nell'attributo msRTCSIP-line (o URI di linea), in modo che le chiamate Skype for business siano abilitate tra gli utenti del sito di succursale e gli utenti del sito centrale verranno instradati correttamente, in particolare quando le chiamate devono essere reinstradate tramite la rete PSTN perché il collegamento WAN non è disponibile. Ci sono inoltre considerazioni speciali per i numeri composti che includono numeri di interno, ma solo numeri di telefono.

Regole di normalizzazione e traduzioni che corrispondono a URI di linea che contengono un numero di interno, sia in esclusiva che in aggiunta a un numero di telefono E. 164 completo, hanno requisiti aggiuntivi. Questa sezione descrive diversi scenari di esempio per instradare le chiamate per gli URI di linea con un numero di interno.

Se l'organizzazione non ha numeri di telefono diretti per singoli utenti e l'URI di linea di ogni utente è configurato con solo un numero di interno, gli utenti interni possono chiamarsi a vicenda componendo solo un numero di interno. Tuttavia, è necessario configurare le regole di normalizzazione che possono essere applicate alle chiamate da un utente di un sito di succursale a un utente del sito centrale, che corrispondono ai numeri di interno.

In uno scenario in cui il collegamento WAN tra un sito di succursale e un sito centrale è disponibile, le chiamate dagli utenti del sito della filiale agli utenti del sito centrale non richiedono la regola di normalizzazione corrispondente per tradurre il numero perché la chiamata non viene instradata tramite la rete PSTN. Ad esempio:

|**Nome regola**|**Descrizione**|**Schema numerico**|**Conversione**|**Esempio**|
|:-----|:-----|:-----|:-----|:-----|
|5digitExtensions  <br/> |Non traduce i numeri a 5 cifre  <br/> |^ (\d{5}) $  <br/> |$1  <br/> |10001 non viene tradotto  <br/> |

È inoltre necessario includere i numeri di interno per scenari specifici, ad esempio quando il collegamento WAN tra un sito di succursale e un sito centrale non è disponibile e una chiamata da un sito di succursale deve essere instradata tramite la rete PSTN. Durante un'interruzione WAN, se un utente del sito filiale chiama un utente del sito centrale solo tramite la chiamata dell'estensione dell'utente del sito centrale, è necessario disporre di una regola di traduzione in uscita che aggiunga il numero di telefono completo dell'utente del sito centrale. Se l'URI di linea di un utente contiene il numero di telefono completo dell'organizzazione e il numero di interno univoco dell'utente invece di un numero di telefono completo univoco per l'utente, è necessario disporre di una regola di traduzione in uscita che aggiunga il numero di telefono completo dell'organizzazione. . Ad esempio:

|**Descrizione**|**Modello di corrispondenza**|**Conversione**|**Esempio**|
|:-----|:-----|:-----|:-----|
|Converte i numeri a 5 cifre in un numero di telefono e un'estensione di un utente  <br/> |^ (\d{5}) $  <br/> |+ 14255550123; ext = $1  <br/> |10001 viene convertito in + 14255550123; ext = 10001  <br/> |
|Converte i numeri a 5 cifre nel numero di telefono dell'organizzazione e nell'estensione di un utente  <br/> |^ (\d{5}) $  <br/> |+ 14255550100; ext = $1  <br/> |10001 viene convertito in + 14255550100; ext = 10001  <br/> |

In questo scenario, se il peer trunk che gestisce il reinstradamento alla rete PSTN non supporta i numeri di interno, la regola di traduzione in uscita deve anche rimuovere il numero di interno. Ad esempio:

|**Descrizione**|**Modello di corrispondenza**|**Conversione**|**Esempio**|
|:-----|:-----|:-----|:-----|
|Rimuove l'estensione dai numeri di telefono con le estensioni  <br/> |^\+(\d\*); EXT = (\d\*) $  <br/> |+ $1  <br/> |+ 14255550123; ext = 10001 viene tradotto in + 14255550123  <br/> |

Indipendentemente dal fatto che sia disponibile un collegamento WAN, se l'organizzazione non ha numeri DID configurati per singoli utenti e l'URI di linea per un utente contiene il numero di telefono dell'organizzazione e il numero di interno univoco dell'utente, è necessario configurare il URI della linea numero di telefono dell'organizzazione con un numero raggiungibile dal peer trunk o dal gateway PSTN del sito della filiale. Devi anche configurare l'URI della linea di numeri di telefono dell'organizzazione per includere la relativa estensione univoca per le chiamate da instradare al numero.

#### <a name="preparing-for-voice-mail-survivability"></a>Preparazione per la sopravvivenza della segreteria telefonica

La messaggistica unificata di Exchange viene in genere installata solo in un sito centrale e non nei siti di succursale. Un chiamante dovrebbe essere in grado di uscire da un messaggio di segreteria telefonica, anche se il collegamento WAN tra sito di succursale e sito centrale non è disponibile. Di conseguenza, la configurazione dell'URI di linea per il numero di telefono dell'operatore automatico di messaggistica unificata di Exchange che fornisce la segreteria telefonica per gli utenti del sito filiale richiede considerazioni particolari, oltre al criterio vocale, al dial plan e alle regole di normalizzazione applicabili alla segreteria telefonica. numero.

Survivable Branch Appliances (SBAs) e Survivable Branch Servers garantiscono la sopravvivenza della segreteria telefonica per gli utenti di Branch durante un'interruzione WAN. In particolare, se si usa un Survivable Branch Appliance o Survivable Branch Server e la WAN non è disponibile, l'SBA o Survivable Branch Server reindirizza le chiamate senza risposta tramite la rete PSTN alla messaggistica unificata di Exchange nel sito centrale. Con un SBA o un Survivable Branch Server, gli utenti possono anche recuperare i messaggi della segreteria telefonica tramite la rete PSTN durante un'interruzione WAN. Infine, durante un'interruzione WAN il Survivable Branch Appliance o Survivable Branch Server accoda le notifiche di mancata chiamata e quindi le carica nel server Messaggistica unificata di Exchange quando viene ripristinata la rete WAN. Per assicurarti che il reindirizzamento della segreteria telefonica sia resiliente, assicurati di aggiungere una voce per il nome di dominio completo del pool di siti centrali e una voce per il nome di dominio completo del server perimetrale nel file hosts nel Survivable Branch Server. In caso contrario, la risoluzione DNS può uscire se non si dispone di un server DNS presso il sito della filiale.

Per gli utenti del sito succursale è consigliabile disporre delle configurazioni seguenti per la sopravvivenza della segreteria telefonica:

- Un amministratore di Microsoft Exchange deve configurare l'operatore automatico di messaggistica unificata di Exchange (AA) per accettare solo i messaggi. Questa configurazione Disabilita tutte le altre funzionalità generiche, ad esempio il trasferimento a un utente o il trasferimento a un operatore, e limita l'AA ad accettare solo i messaggi. In alternativa, l'amministratore di Exchange può usare un generico AA o un AA personalizzato per instradare la chiamata a un operatore.

- L'amministratore di Skype for Business Server deve assumere il numero di telefono AA e usare tale numero come numero di **operatore automatico di messaggistica unificata di Exchange** nelle impostazioni di reinstradazione della segreteria telefonica per Survivable Branch Appliance o Branch Server.

- L'amministratore di Skype for Business Server dovrebbe ottenere il numero di telefono dell'accesso abbonato alla messaggistica unificata di Exchange e usare tale numero come numero di **accesso** del Sottoscrittore nelle impostazioni di reinstradazione della segreteria telefonica per Survivable Branch Appliance o Survivable Branch Server .

- L'amministratore di Skype for Business Server deve configurare la messaggistica unificata di Exchange in modo che solo un dial plan sia associato a tutti gli utenti della filiale che hanno bisogno di accedere alla segreteria telefonica durante un'interruzione WAN.

- Quando il collegamento WAN non è disponibile, le chiamate agli utenti del sito succursale possono essere indirizzate alla segreteria telefonica di Exchange Unified Messaging (UM) dell'utente, ma solo se il criterio vocale applicato alla chiamata specifica un numero di telefono della segreteria telefonica univoco e non include un'estensione numero.

#### <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Requisiti hardware e software per la resilienza del sito filiale

I requisiti hardware e software variano a seconda della soluzione di resilienza.

#### <a name="requirements-for-survivable-branch-appliances"></a>Requisiti per gli elettrodomestici Survivable Branch

Hardware e software obbligatori sono integrati nell'appliance Survivable Branch. Tuttavia, è consigliabile anche che ogni sito della filiale distribuisca un server DHCP per ottenere gli indirizzi IP del client. in caso contrario, quando il lease DHCP scade, i client non avranno connettività IP.

Se i server DNS dell'organizzazione si trovano solo nei siti centrali, gli utenti del sito succursale non potranno connettersi a questi ultimi durante un'interruzione WAN e quindi l'individuazione di Skype for Business Server che usa il record di risorse DNS SRV (SRV) non riuscirà. Per assicurare il reinstradamento rapido durante un'interruzione WAN, i record DNS devono essere memorizzati nella cache del sito della filiale. Se il router della filiale lo supporta, attivare la memorizzazione nella cache DNS. In alternativa, è possibile distribuire un server DNS presso la filiale. Può trattarsi di un server autonomo o di una versione dell'appliance Survivable Branch che supporta le funzionalità DNS. Per informazioni dettagliate, contattare il provider Survivable Branch Appliance.

> [!NOTE]
> Non è necessario disporre di un controller di dominio in un sito di succursale. Il Survivable Branch Appliance autentica i client usando un certificato speciale che invia il client in risposta alla richiesta di certificato del client quando viene eseguita la firma.

I client Skype for business possono trovare il server Skype for business usando l'opzione DHCP 120 (opzione registrar SIP). Questa operazione può essere configurata in uno dei due modi seguenti:

- Configurare il server DHCP presso il sito della filiale per rispondere alle query di 120 DHCP, che restituiscono il nome di dominio completo del registrar nel Survivable Branch Appliance o Survivable Branch Server.

- Attivare DHCP per Skype for Business Server. Quando questo è attivato, il registrar di Skype for Business Server risponde alle query di opzione 120 per DHCP. Tieni presente che il registrar non risponde a nessuna query DHCP diversa dalle opzioni DHCP 120.

Inoltre, per i siti di succursale più grandi con più subnet, gli agenti di inoltro DHCP devono essere abilitati per inoltrare query DHCP Option 120 al server DHCP (configurazione 1) o al registrar (configurazione 2).

Infine, gli utenti del sito succursale devono essere configurati per VoIP aziendale e provisioning con un endpoint di comunicazioni unificato appropriato.

#### <a name="requirements-for-survivable-branch-servers"></a>Requisiti per Survivable Branch Servers

I requisiti per i Survivable Branch Server corrispondono ai requisiti per un server front-end. Per informazioni dettagliate, vedere [requisiti del server per Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

#### <a name="requirements-for-full-scale-skype-for-business-server-branch-site-deployments"></a>Requisiti per le distribuzioni del sito di Skype for Business Server su vasta scala

Per informazioni dettagliate, vedere [requisiti del server per Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) nella documentazione relativa alla pianificazione.

### <a name="example-configuring-a-failover-route"></a>Esempio: configurazione di una route di failover

 L'esempio seguente mostra il modo in cui un amministratore può definire una route di failover da usare se Dallas-GW1 è in calo per la manutenzione o altrimenti non è disponibile. Le tabelle seguenti illustrano la modifica della configurazione necessaria.

**Tabella 1. Criteri utente**

|**Criteri utente**|**Uso del telefono**|
|:-----|:-----|
|Criteri di chiamata predefiniti  <br/> |Locale  <br/> GlobalPSTNHopoff  <br/> |
|Criteri locali Redmond  <br/> |RedmondLocal  <br/> |
|Criteri di chiamata Dallas  <br/> |DallasUsers  <br/> GlobalPSTNHopoff  <br/> |

**Tabella 2. Indirizza**


| **Nome Route**             | **Schema numerico** | **Uso del telefono**         | **Tronco**                                 | **Gateway**                                     |
|:---------------------------|:-------------------|:------------------------|:------------------------------------------|:------------------------------------------------|
| Route locale Redmond  <br/> | ^\+1 (425           | 206                     | 253) (\d{7}) $  <br/>                       | Locale  <br/> RedmondLocal  <br/>                |
| Route locale di Dallas  <br/>  | ^\+1 (972           | 214                     | 469) (\d{7}) $  <br/>                       | Locale  <br/>                                    |
| Route universale  <br/>     | ^\+? (\d\*) $  <br/> | GlobalPSTNHopoff  <br/> | Trunk1  <br/> Trunk2  <br/> Trunk3  <br/> | Rosso-GW1  <br/> Rosso-GW2  <br/> Dallas-GW1  <br/> |
| Route utenti Dallas  <br/>  | ^\+? (\d\*) $  <br/> | DallasUsers  <br/>      | Trunk3  <br/>                             | Dallas-GW1  <br/>                               |

Nella tabella 1 viene aggiunto un uso telefonico di GlobalPSTNHopoff dopo l'uso del telefono DallasUsers nei criteri di chiamata di Dallas. In questo modo, le chiamate con i criteri di chiamata di Dallas possono usare le route configurate per l'utilizzo di GlobalPSTNHopoff Phone se non è disponibile una route per l'utilizzo del telefono DallasUsers.


