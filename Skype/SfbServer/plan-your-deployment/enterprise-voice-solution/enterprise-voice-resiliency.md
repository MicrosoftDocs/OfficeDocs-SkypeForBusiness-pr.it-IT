---
title: Pianificare la VoIP aziendale resilienza in Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.assetid: b3671dcb-6a8b-4a06-84da-0c8837b35099
description: Informazioni su come supportare la resilienza vocale in Skype for Business Server VoIP aziendale, sia nei siti centrali che nei siti di succursale. Le opzioni del sito di succursale includono la distribuzione di Survivable Branch Appliance o Survivable Branch Server.
ms.openlocfilehash: fa68fda07e104477bf0e8a089b45adf641ef4ed9
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2022
ms.locfileid: "62400290"
---
# <a name="plan-for-enterprise-voice-resiliency-in-skype-for-business-server"></a>Pianificare la VoIP aziendale resilienza in Skype for Business Server

Informazioni su come supportare la resilienza vocale in Skype for Business Server VoIP aziendale, sia nei siti centrali che nei siti di succursale. Le opzioni del sito di succursale includono la distribuzione di Survivable Branch Appliance o Survivable Branch Server.

La resilienza vocale si riferisce alla capacità degli utenti di continuare a effettuare e ricevere chiamate se un sito centrale che ospita Skype for Business Server diventa non disponibile, a causa di un errore della rete WAN o di un'altra causa. In caso di errore di un sito centrale, il servizio VoIP aziendale deve proseguire senza interruzione mediante failover ininterrotto su un sito di backup. In caso di errore della WAN, le chiamate dei siti di succursale devono essere reindirizzate a un PSTN locale. In questa sezione viene illustrata la pianificazione della resilienza vocale in caso di errore di un sito centrale o della WAN.

## <a name="central-site-resiliency"></a>Resilienza del sito centrale

Le aziende dispongono sempre più spesso di diversi siti sparsi in tutto il mondo. La gestione dei servizi di emergenza, l'accesso all'help desk e la possibilità di eseguire attività aziendali critiche quando un sito centrale non è disponibile è essenziale per qualsiasi soluzione VoIP aziendale resilienza. Quando un sito centrale diventa non disponibile, devono essere soddisfatte le condizioni seguenti:

- Deve essere predisposto il failover dei servizi vocali.

- Gli utenti che in genere si registrano nel pool Front End nel sito centrale devono essere in grado di eseguire la registrazione con un pool Front End alternativo. A tale scopo, è possibile creare più record DNS SRV, ognuno dei quali viene risolto in un pool di server Director o in un pool Front End in ognuno dei siti centrali. È possibile modificare la priorità e i pesi dei record SRV in modo che gli utenti serviti da tale sito centrale otterrà il director e il pool Front End corrispondenti prima di quelli in altri record SRV.

- Le chiamate verso e da utenti in altri siti devono essere reindirizzate al PSTN.

Questo argomento descrive la soluzione consigliata per la protezione della resilienza dei servizi vocali del sito centrale.

### <a name="architecture-and-topology"></a>Architettura e topologia

La pianificazione della resilienza vocale in un sito centrale richiede una conoscenza di base del ruolo centrale svolto dalla funzione di Skype for Business Server registrar per abilitare il failover vocale. La Skype for Business Server registrar è un servizio che consente la registrazione e l'autenticazione dei client e fornisce servizi di routing. Viene eseguito in tutti edizione Standard server, Front End Server, Director o Survivable Branch Appliance. Un pool di registrazione è costituito da servizi di registrazione in esecuzione nel pool Front End e residenti nello stesso sito. Un Skype for Business client individua il pool Front End tramite il meccanismo di individuazione seguente:

1. Record SRV DNS

2. Servizio Web autodiscovery

3. Opzione DHCP 120

Dopo che Skype for Business client si connette al pool Front End, viene indirizzato dal servizio di bilanciamento del carico a uno dei Front End Server nel pool. Il Front End Server, a sua volta, reindirizza il client a una funzione di registrazione preferita nel pool.

Ogni utente abilitato per VoIP aziendale viene assegnato a un particolare pool di registrazione, che diventa il pool di registrazione principale dell'utente. In ogni sito, un singolo pool di registrazione principale è solitamente condiviso da centinaia o migliaia di utenti. Per pianificare il consumo delle risorse del sito centrale da parte di eventuali utenti di siti di succursale che si basano sul sito centrale per i servizi di presenza, conferenza o failover, è consigliabile considerare ogni utente di sito di succursale come se fosse un utente registrato nel sito centrale. Attualmente non esistono limiti al numero di utenti del sito di succursale, inclusi gli utenti registrati con un Survivable Branch Appliance.

Per garantire la resilienza dei servizi vocali in caso di errore del sito centrale, per il pool di registrazione principale deve esistere un singolo pool di registrazione di backup designato in un altro sito. Il backup può essere configurato utilizzando le impostazioni di resilienza di Generatore di topologie. Presupponendo l'esistenza di un collegamento WAN resiliente tra due siti, gli utenti per cui non è più disponibile il pool di registrazione principale verranno reindirizzati automaticamente al pool di registrazione di backup.

I passaggi seguenti descrivono il processo di individuazione e registrazione dei client:

1. Un client individua Skype for Business Server tramite record DNS SRV. In Skype for Business Server, i record DNS SRV possono essere configurati per restituire più di un FQDN alla query DNS SRV. Ad esempio, se l'azienda Contoso dispone di tre siti centrali (Nord America, Europa e Asia-Pacifico) e un pool di server Director in ogni sito centrale, i record DNS SRV possono puntare ai nomi FQDN del pool di server Director in ognuna delle tre posizioni. Finché il pool di server Director in una delle posizioni è disponibile, il client può connettersi al primo hop Skype for Business Server.

    > [!NOTE]
    > L'utilizzo di un pool di server Director è facoltativo. È invece possibile utilizzare un pool Front End.

2. Il pool di server Director informa Skype for Business client sul pool di registrazione principale e sul pool di registrazione di backup dell'utente.

3. Il Skype for Business client tenta prima di connettersi al pool di registrazione principale dell'utente. Se è disponibile, la registrazione viene accettata. Se il pool di registrazione primario non è disponibile, il client Skype for Business tenta di connettersi al pool di registrazione di backup. Se il pool di registrazione di backup è disponibile e ha determinato che il pool di registrazione principale dell'utente non è disponibile (rilevando una mancanza di heartbeat per un intervallo di failover specificato), il pool di registrazione di backup accetta la registrazione dell'utente. Dopo che la funzione di registrazione di backup rileva che la funzione di registrazione principale è di nuovo disponibile, il pool di registrazione di backup reindirizza i client di failover al pool primario.

### <a name="requirements-and-recommendations"></a>Requisiti e raccomandazioni

I requisiti e le raccomandazioni seguenti per l'implementazione della resilienza dei servizi vocali del sito centrale sono appropriati per la maggior parte delle organizzazioni:

- I siti in cui risiedono i pool di registrazione principale e di backup dovrebbero essere connessi tramite un collegamento WAN resiliente.

- Ogni sito centrale deve contenere un pool di registrazione composto da una o più funzioni di registrazione.

- Ogni pool di registrazione deve essere bilanciato tramite il bilanciamento del carico DNS, il bilanciamento del carico hardware o entrambi. Per informazioni dettagliate sulla pianificazione della configurazione di bilanciamento del carico, vedere [Load balancing requirements for Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md).

- Ogni utente deve essere assegnato a un pool di registrazione primario utilizzando il cmdlet **set-CsUser di Skype for Business Server** Management Shell o Skype for Business Server Pannello di controllo.

- Per il pool di registrazione principale deve esistere un singolo pool di registrazione di backup posizionato in un diverso sito centrale.

- Il pool di registrazione principale deve essere configurato per il failover sul pool di registrazione di backup. Per impostazione predefinita, il pool principale è impostato per eseguire il failover sul pool di back dopo un intervallo di 300 secondi. È possibile modificare questo intervallo utilizzando il Skype for Business Server Generatore di topologie.

- Configurare una route di failover. Durante la configurazione della route specificare un gateway posizionato in un sito diverso da quello del gateway impostato nella route principale.

- Se il sito centrale conteneva il server di gestione principale e il sito potrebbe non essere disponibile per un periodo prolungato, sarà necessario reinstallare gli strumenti di gestione nel sito di backup. in caso contrario, non sarà possibile modificare le impostazioni di gestione.

### <a name="dependencies"></a>Dipendenze

Skype for Business Server dipende dall'infrastruttura e dai componenti software seguenti per garantire la resilienza vocale:

|**Componente** <br/> |**Funzionale** <br/> |
|:-----|:-----|
|DNS  <br/> |Risoluzione dei record SRV e A per la connettività tra server e tra server e client  <br/> |
|Exchange e Servizi Web Exchange  <br/> |Archiviazione dei contatti; dati del calendario  <br/> |
|Messaggistica unificata di Exchange e Servizi Web Exchange  <br/> |Registri chiamate, segreteria telefonica e messaggi di segreteria telefonica  <br/> |
|Opzione DHCP 120  <br/> |Se non sono disponibili record DNS SRV, il client tenterà di utilizzare l'opzione DHCP 120 per individuare la funzione di registrazione. Per il corretto funzionamento, è necessario configurare un server DHCP o Skype for Business Server dhcp deve essere abilitato.  <br/> |

### <a name="survivable-voice-features"></a>Funzionalità vocali disponibili

Se si implementano i requisiti e le raccomandazioni precedenti, il pool di registrazione di backup renderà disponibili le funzionalità vocali seguenti:

- Chiamate PSTN in uscita

- Chiamate PSTN in entrata, se il provider di servizi di telefonia supporta il failover su un sito di backup.

- Chiamate Enterprise tra utenti dello stesso sito e di due siti diversi

- Gestione di base delle chiamate inclusi la messa in attesa, il recupero e il trasferimento

- Messaggistica istantanea tra due parti e condivisione di audio e video tra utenti nello stesso sito

- Inoltro di chiamata, squillo simultaneo degli endpoint, delega delle chiamate e servizi di intercettazione team, ma solo se entrambe le parti della delega, oppure tutti i membri del team, sono configurati nello stesso sito

- I telefoni ei client esistenti continuano a funzionare.

- Registrazione dettagli chiamata (CDR)

- Autenticazione e autorizzazione

A seconda della modalità di configurazione, le funzionalità vocali seguenti potrebbero o meno funzionare quando un sito centrale principale è fuori servizio:

- Recapito e recupero di messaggi di segreteria telefonica

    Se si desidera rendere disponibile la messaggistica unificata di Exchange quando il sito centrale principale è fuori servizio, è necessario eseguire una delle operazioni seguenti:

  - Modificare i record DNS SRV in modo che i server di messaggistica unificata di Exchange nel sito centrale puntino ai server di messaggistica unificata di Exchange di backup in un altro sito.

  - Configurare il dial plan di Exchange di messaggistica unificata di ogni utente in modo che includa server di messaggistica unificata Exchange sia nel sito centrale che nel sito di backup, ma designare il server di Exchange di messaggistica unificata come disabilitato. Se il sito principale non è più disponibile, l Exchange amministratore deve contrassegnare i Exchange di messaggistica unificata nel sito di backup come abilitati.

    Se nessuna delle soluzioni precedenti è possibile, Exchange la messaggistica unificata non sarà disponibile nel caso in cui il sito centrale non sia più disponibile.

- Conferenze di tutti i tipi

    Un utente reindirizzato su un sito di backup per il failover può partecipare a una conferenza creata e ospitata da un organizzatore assegnato a un pool disponibile, ma non può creare o ospitare una conferenza nel suo pool principale, che non è più disponibile. Analogamente, altri utenti non possono partecipare a conferenze ospitate nel pool principale dell'utente interessato.

Le funzionalità vocali seguenti non sono disponibili quando un sito centrale principale è fuori servizio:

- Operatore Conferenza

- Routing basato su DNS e basato sulla presenza

- Aggiornamento delle impostazioni di inoltro di chiamata.

- Response Group Service e parcheggio di chiamata

- Provisioning di nuovi telefoni e client

- Ricerca Web nella Rubrica

## <a name="branch-site-resiliency"></a>Resilienza del sito di succursale

Se si desidera fornire resilienza del sito di succursale, ad esempio un servizio di VoIP aziendale a disponibilità elevata, sono disponibili tre opzioni per eseguire questa operazione:

- Survivable Branch Appliance

- Server Survivable Branch

- Una distribuzione Skype for Business Server completa nel sito di succursale

Le informazioni in questa guida sono utili per valutare la soluzione di resilienza ottimale per l'organizzazione e, in base alla soluzione di resilienza, quale soluzione di connettività PSTN utilizzare. Saranno inoltre utili per preparare la distribuzione della soluzione scelta grazie alla descrizione dei prerequisiti e di altre considerazioni sulla pianificazione.

### <a name="branch-site-resiliency-features"></a>Caratteristiche di resilienza dei siti di succursale

Se si fornisce resilienza del sito di succursale, se la connessione WAN di un sito di succursale a un sito centrale non riesce o se il sito centrale non è raggiungibile, le seguenti funzionalità vocali dovrebbero continuare a essere disponibili:

- Chiamate PSTN in entrata e in uscita

- Chiamate Enterprise tra utenti dello stesso sito e di due siti diversi

- Gestione di base delle chiamate inclusi la messa in attesa, il recupero e il trasferimento

- Messaggistica istantanea tra due parti

- Inoltro di chiamata, squillo simultaneo di endpoint, delega delle chiamate e servizi di chiamata del team, ma solo se il delegato e il delegato (ad esempio, un manager e l'amministratore del manager) o tutti i membri del team sono configurati nello stesso sito

- Registrazione dettagli chiamata (CDR)

- Conferenze telefoniche con accesso esterno PSTN con Operatore automatico conferenza

- Funzionalità di segreteria telefonica, se si configurano le impostazioni di rerouting della segreteria telefonica.

- Autenticazione e autorizzazione utente

Le funzionalità seguenti saranno disponibili solo se la soluzione con resilienza è una distribuzione Skype for Business Server distribuzione completa nel sito di succursale:

- Conferenze di messaggistica istantanea, Web e audio/video

- Routing in base a presenza e Non disturbare (le chiamate non squillano agli interni che hanno il Non disturbare attivato)

- Aggiornamento delle impostazioni di inoltro di chiamata.

- Applicazione Response Group e applicazione Parcheggio di chiamata

- Provisioning di nuovi telefoni e client, ma solo se Servizi di dominio Active Directory è presente nel sito di succursale.

- Enhanced 9-1-1 (E9-1-1)

    Se viene distribuito E9-1-1 e il trunk SIP nel sito centrale non è disponibile perché il collegamento WAN non è disponibile, il Survivable Branch Appliance instraderà le chiamate E9-1-1 al gateway di succursale locale. Per abilitare questa funzionalità, i criteri vocali degli utenti del sito di succursale devono instradare le chiamate al gateway locale in caso di errore DELLA WAN.

> [!NOTE]
> SBA (survivable branch office) non è supportato per XMPP. Gli utenti ospitati in configurazioni SBA non potranno inviare messaggistica istantanea o vedere Presenza con contatti XMPP.

### <a name="branch-site-resiliency-solutions"></a>Soluzioni di resilienza dei siti di succursale

Esistono ovvi vantaggi nell'offrire resilienza dei siti di succursale all'organizzazione. In particolare, se si perde la connessione al sito centrale, gli utenti del sito di succursale continueranno VoIP aziendale disporre del servizio e della segreteria telefonica (se si configurano le impostazioni di reindirizzamento della segreteria telefonica). Tuttavia, per i siti con meno di 25 utenti, una soluzione con resilienza potrebbe non fornire un ritorno sufficiente sull'investimento.

Se si decide di garantire la resilienza dei siti di succursale, sono disponibili tre opzioni. Per scegliere l'opzione più adatta all'organizzazione, utilizzare come riferimento la tabella riportata di seguito.

|**Se...**|**È consigliabile utilizzare un…**|
|:-----|:-----|
|Nel sito di succursale vengono ospitati dai 25 ai 1000 utenti e l'utile sugli investimenti non consente una distribuzione completa oppure non è disponibile supporto amministrativo locale  <br/> |Survivable Branch Appliance  <br/> Il Survivable Branch Appliance è un server blade standard del settore con una funzione di registrazione di Skype for Business Server e Mediation Server in esecuzione su Windows Server 2008 R2. Il Survivable Branch Appliance contiene anche un gateway PSTN (Public Switched Telephone Network). I dispositivi di terze parti qualificati, sviluppati da partner Microsoft nell'ambito del programma di qualifica e certificazione degli SBA (Survivable Branch Appliance), forniscono una connessione PSTN continua in caso di problemi della rete WAN, ma non garantiscono un servizio di presenza o conferenza resiliente perché tali funzionalità dipendono dai Front End Server nel sito centrale.  <br/> Per informazioni dettagliate sui Survivable Branch Appliance, vedere "Dettagli su Survivable Branch Appliance" più avanti in questo argomento.  <br/> **Nota:** Se si decide di utilizzare anche un trunk SIP con il Survivable Branch Appliance, contattare il fornitore del Survivable Branch Appliance per informazioni sul provider di servizi più adatto all'organizzazione. <br/> |
|Ospitare tra 1000 e 2000 utenti nel sito di succursale, non dispone di una connessione WAN resiliente e hanno formato Skype for Business Server amministratori disponibili  <br/> |Survivable Branch Server o due Survivable Branch Appliance.  <br/> Il Survivable Branch Server è un Windows Server che rispetta i requisiti hardware specificati in cui è installato Skype for Business Server registrar e Mediation Server. Deve connettersi a un gateway PSTN o a un trunk SIP verso un provider di servizi telefonici.  <br/> Per informazioni dettagliate sui Survivable Branch Server, vedere "Dettagli su Survivable Branch Server" più avanti in questo argomento.  <br/> |
|Se sono necessarie funzionalità di presenza e conferenza oltre alle funzionalità vocali per un massimo di 5.000 utenti e sono disponibili Skype for Business Server amministratori qualificati  <br/> |Eseguire la distribuzione come sito centrale con un server Standard Edition anziché come sito di succursale.  <br/> Una distribuzione completa di Skype for Business Server offre una connessione PSTN continua e una presenza resiliente e conferenze in caso di errore WAN.  <br/> |

#### <a name="resiliency-topologies"></a>Topologie di resilienza

Nella figura seguente vengono illustrate le topologie consigliate per la resilienza dei siti di succursale.

**Opzioni di resilienza per i siti di succursale**

![Opzioni di resilienza di Voice Branch.](../../media/Plan_OCS_Voice_BranchResiliencyOptions.jpg)

#### <a name="survivable-branch-appliance-details"></a>Dettagli relativi al Survivable Branch Appliance

L Skype for Business Server Survivable Branch Appliance include i componenti seguenti:

- Una funzione di registrazione per l'autenticazione degli utenti, la registrazione e il routing delle chiamate

- Un Mediation Server per la gestione dei segnali tra la funzione di registrazione e un gateway PSTN

- Un gateway PSTN per il routing delle chiamate alla rete PSTN come trasporto di fallback in caso di problemi della rete WAN

- SQL Server Express per l'archiviazione dei dati degli utenti in locale

Il Survivable Branch Appliance include anche trunk PSTN, porte analogiche e una scheda Ethernet.

Se la connessione WAN del sito di succursale a un sito centrale non è più disponibile, gli utenti delle succursale interne continuano a essere registrati nella funzione di registrazione di Survivable Branch Appliance e a ottenere il servizio vocale ininterrotta utilizzando la connessione di Survivable Branch Appliance alla rete PSTN. Gli utenti del sito di succursale che si connettono da casa o da altre postazioni remote saranno in grado di registrarsi in un server di registrazione presso un sito centrale in caso di non disponibilità del collegamento WAN al sito di succursale. Tali utenti disporranno della funzionalità di comunicazione unificata completa, con l'unica eccezione che le chiamate in ingresso nel sito di succursale verranno indirizzate alla segreteria telefonica. Quando la connessione WAN torna disponibile, per gli utenti del sito di succursale viene ripristinata la funzionalità completa. Né il failover al Survivable Branch Appliance né il ripristino del servizio richiedono la presenza di un amministratore IT.

Skype for Business Server supporta fino a due Survivable Branch Appliance in un sito di succursale.

#### <a name="survivable-branch-appliance-deployment-overview"></a>Panoramica della distribuzione del Survivable Branch Appliance

Il Survivable Branch Appliance è prodotto da produttori di attrezzature originali in collaborazione con Microsoft e distribuito per loro conto da rivenditori a valore aggiunto. Questa distribuzione deve essere eseguita solo dopo la distribuzione di Skype for Business Server nel sito centrale, quando è attiva una connessione WAN al sito di succursale e gli utenti del sito di succursale sono abilitati per VoIP aziendale.

Per informazioni dettagliate su queste fasi, vedere [Deploying a Survivable Branch Appliance or Server](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-a-survivable-branch-appliance-or-server) nella documentazione relativa alla distribuzione.

|**Fase**|**Procedura**|**Diritti utente**|
|:-----|:-----|:-----|
|Configurare Servizi di dominio Active Directory per il Survivable Branch Appliance  <br/> |**Nel sito centrale:** <br/>  Creare un account utente di dominio (o un'identità aziendale) per il tecnico che installerà e attiverà il Survivable Branch Appliance nel sito di succursale. <br/>  Creare un account computer (con il nome di dominio completo (FQDN) applicabile) per Survivable Branch Appliance in Servizi di dominio Active Directory. <br/>  In Generatore di topologie creare e pubblicare il Survivable Branch Appliance. <br/> |L'account utente del tecnico deve essere membro del gruppo RTCUniversalSBATechnicians. Il Survivable Branch Appliance deve appartenere al gruppo RTCSBAUniversalServices, che si verifica automaticamente quando si utilizza Generatore di topologie.  <br/> |
|Installare e attivare il Survivable Branch Appliance.  <br/> |**Nel sito di succursale:** <br/>  Connessione il Survivable Branch Appliance a una porta Ethernet e a una porta PSTN. <br/>  Avviare il Survivable Branch Appliance. <br/>  Aggiungere il Survivable Branch Appliance al dominio, utilizzando l'account utente di dominio creato per il Survivable Branch Appliance nel sito centrale. Impostare l'FQDN e l'indirizzo IP in modo che corrispondano all'FQDN creato nell'account computer. <br/>  Configurare il Survivable Branch Appliance utilizzando l'interfaccia utente OEM. <br/>  Verificare la connettività PSTN. <br/> |L'account utente del tecnico deve essere membro del gruppo RTCUniversalSBATechnicians.  <br/> |

#### <a name="survivable-branch-server-details"></a>Dettagli relativi al Survivable Branch Server

In Generatore di topologie creare il sito di succursale, aggiungere il Survivable Branch Server al sito e quindi eseguire la Distribuzione guidata di Skype for Business Server nel computer in cui si desidera installare il ruolo.

### <a name="branch-site-resiliency-requirements"></a>Requisiti di resilienza del sito di succursale

In questo argomento vengono fornite informazioni utili per preparare gli utenti per la resilienza dei siti di succursale e per il funzionamento continuato (survivability) della segreteria telefonica e vengono specificati i requisiti hardware e software pertinenti.

#### <a name="preparing-branch-users-for-branch-site-resiliency"></a>Preparazione degli utenti di succursale per la resilienza del sito di succursale

Preparare gli utenti per la resilienza del sito di succursale impostando il pool di registrazione come Survivable Branch Appliance (SBA) o Survivable Branch Server.

#### <a name="registrar-assignments-for-branch-users"></a>Assegnazioni di registrazione per utenti di succursale

Indipendentemente dalla soluzione di resilienza del sito di succursale scelta, sarà necessario assegnare una funzione di registrazione principale a ogni utente. Gli utenti del sito di succursale devono sempre registrarsi con la funzione di registrazione nel sito di succursale, indipendentemente dal fatto che si trovi nel Survivable Branch Appliance, nel Survivable Branch Server o nel server Skype for Business Server Standard o edizione Enterprise autonomo. È necessario un record di risorse del servizio DNS (Domain Name System) (SRV) in modo che un client possa individuare il relativo pool di registrazione. Se il Survivable Branch Appliance non è più disponibile, i client dei siti di succursale scopriranno automaticamente la funzione di registrazione di backup.

Se un sito di succursale non dispone di un server DNS, esistono due modi alternativi per configurare l'individuazione del Survivable Branch Appliance o del Survivable Branch Server:

- Configurare l'opzione DHCP 120 nel server DHCP (Dynamic Host Configuration Protocol) del sito di succursale in modo che punti al nome di dominio completo (FQDN) del Survivable Branch Appliance o del Survivable Branch Server.

- Configurare il Survivable Branch Appliance o il Survivable Branch Server per rispondere alle query DHCP 120.

#### <a name="voice-routing-for-branch-users"></a>Routing vocale per gli utenti di succursale

Per gli utenti di un sito di succursale è consigliabile creare criteri VoIP (Voice over Internet Protocol) a livello di utente separati. Questo criterio deve includere una route principale che utilizza il Survivable Branch Appliance o il gateway del server di succursale e una o più route di backup che utilizzano un trunk con un gateway PSTN (Public Switched Telephone Network) nel sito centrale. Se la route principale non è disponibile, viene sostituita dalla route di backup, che può utilizzare uno o più gateway del sito centrale. In questo modo, indipendentemente dalla posizione in cui è registrato un utente, nel registrar del sito di succursale o nel pool di registrazione di backup nel sito centrale, il criterio VoIP dell'utente è sempre attivo. Questa considerazione è particolarmente importante per gli scenari di failover. Ad esempio, se è necessario rinominare il Survivable Branch Appliance o riconfigurare il Survivable Branch Appliance per connettersi a un pool di registrazione di backup nel sito centrale, è necessario spostare gli utenti del sito di succursale nel sito centrale per la durata. Per informazioni dettagliate sulla ridenominazione o la riconfigurazione di un Survivable Branch Appliance, vedere [Appendix B: Managing a Survivable Branch Appliance](/previous-versions/office/lync-server-2013/lync-server-2013-appendix-b-managing-a-survivable-branch-appliance) nella documentazione relativa alla distribuzione. Se tali utenti non dispongono di criteri VoIP a livello di utente o dial plan a livello di utente, quando gli utenti vengono spostati in un altro sito, i criteri VoIP a livello di sito e i dial plan a livello di sito del sito centrale si applicano agli utenti per impostazione predefinita, anziché ai criteri VoIP e ai dial plan a livello di sito di succursale. In questo scenario le chiamate degli utenti del sito di succursale avranno esito positivo se a tali utenti non è possibile applicare i criteri VoIP e i dial plan a livello di sito utilizzati dal pool di registrazione di backup. Se ad esempio gli utenti di un sito di succursale situato in Giappone vengono spostati in un sito centrale situato a Redmond, è improbabile che un dial plan con regole di normalizzazione che antepongono il prefisso +1425 a tutte le chiamate a numeri di sette cifre sia in grado di convertire correttamente le chiamate di tali utenti.

> [!IMPORTANT]
> Quando si crea una route di backup per una succursale, è consigliabile aggiungere ai criteri utente della succursale due record di utilizzo telefono PSTN e assegnare route distinte a ognuno. La prima route, o principale, indirizza le chiamate al gateway associato al Survivable Branch Appliance (SBA) o al server di succursale; il secondo, o backup, instraderebbe le chiamate al gateway nel sito centrale. Per l'indirizzamento delle chiamate, l'SBA o il server di succursale dovrà tentare tutte le route assegnate al primo record di utilizzo PSTN prima di tentare quelle del secondo record di utilizzo.

Per garantire che le chiamate in ingresso agli utenti del sito di succursale raggiungano tali utenti quando il gateway di succursale o il componente Windows del sito Survivable Branch Appliance non è disponibile (cosa che si verifica, ad esempio, se il Survivable Branch Appliance o il gateway di succursale non è disponibile per la manutenzione), creare una route di failover nel gateway (o collaborare con il provider DID ) per reindirizzare le chiamate in arrivo al pool di registrazione di backup nel sito centrale. Dal pool di registrazione di backup del sito centrale le chiamate verranno instradate agli utenti di succursale attraverso il collegamento WAN. Assicurarsi che la route converta i numeri in modo che siano conformi ai formati di numero di telefono accettati del gateway PSTN o di altri trunk peer. Per informazioni dettagliate sulla creazione di una route di failover, vedere [Configuring a Failover Route](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-a-failover-route). Per consentire la normalizzazione delle chiamate in arrivo da parte del trunk associato al gateway del sito di succursale, è inoltre necessario creare dial plan a livello di servizio. Se si dispone di due Survivable Branch Appliance in un sito di succursale, è possibile creare un dial plan a livello di sito per entrambi, a meno che non sia necessario un piano a livello di servizio separato per ognuno di essi.

> [!NOTE]
> Per tenere conto del consumo delle risorse del sito centrale da parte degli utenti dei siti di succursale che si appoggiano al sito centrale per le funzionalità di presenza, conferenza o failover, è consigliabile considerare ogni utente del sito di succursale come se fosse registrato presso il sito centrale. Attualmente non esistono limiti al numero di utenti del sito di succursale, inclusi gli utenti registrati con un Survivable Branch Appliance.

È inoltre consigliabile creare criteri vocali e di dial plan a livello di utente e quindi assegnarli agli utenti del sito di succursale. Per informazioni dettagliate, vedere [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md) and [Create the VoIP Routing Policy for Branch Users](/previous-versions/office/lync-server-2013/lync-server-2013-create-the-voip-routing-policy-for-branch-users) nella documentazione relativa alla distribuzione.

#### <a name="routing-extension-numbers"></a>Routing di numeri di interno

Quando si preparano dial plan e criteri vocali per gli utenti dei siti di succursale, assicurarsi di includere regole di normalizzazione e regole di conversione che corrispondano alle stringhe e al formato dei numeri utilizzati nell'attributo msRTCSIP-line (o URI linea), in modo che le chiamate Skype for Business abilitate tra gli utenti del sito di succursale e gli utenti del sito centrale vengano instradati correttamente, in particolare quando le chiamate devono essere reinstradati sulla rete PSTN perché il collegamento WAN non è disponibile. Per i numeri composti contenenti numeri di interno, sono inoltre necessarie considerazioni specifiche rispetto ai numeri di telefono semplici.

Per le regole di normalizzazione e le regole di conversione corrispondenti a URI di linea contenenti un numero di interno, da solo o insieme a un numero di telefono E. 164 completo, esistono requisiti aggiuntivi. In questa sezione sono descritti alcuni scenari di esempio con l'indirizzamento di chiamate per URI di linea contenenti un numero di interno.

Se nell'organizzazione non sono configurati numeri di telefono DID (Direct Inward Dial) per utenti singoli e l'URI di linea di ogni utente è configurato con un solo numero di interno, gli utenti interni possono chiamarsi componendo solo il numero di interno desiderato. È tuttavia necessario configurare regole di normalizzazione applicabili alle chiamate da un utente di un sito di succursale a un utente del sito centrale corrispondenti ai numeri di interno.

In uno scenario in cui sia disponibile un collegamento WAN tra il sito di succursale e il sito centrale, per le chiamate tra utenti del sito di succursale e utenti del sito centrale non è necessaria la regola di normalizzazione per la conversione del numero, poiché la chiamata non viene indirizzata attraverso PSTN. Ad esempio:

|**Nome regola**|**Descrizione**|**Formato numero**|**Conversione**|**Esempio**|
|:-----|:-----|:-----|:-----|:-----|
|5digitExtensions  <br/> |Non converte i numeri a cinque cifre  <br/> |^(\d{5})$  <br/> |$1  <br/> |10001 non viene convertito  <br/> |

È inoltre necessario prevedere numeri di interno per scenari specifici in cui, ad esempio, il collegamento WAN tra un sito di succursale e il sito centrale non sia disponibile e sia necessario instradare tramite PSTN le chiamate provenienti dal sito di succursale. Durante un'interruzione della rete WAN, se un utente del sito di succursale chiama un utente del sito centrale solo componendo l'interno dell'utente del sito centrale, è necessario disporre di una regola di conversione in uscita che aggiunge il numero di telefono completo dell'utente del sito centrale. Se l'URI linea di un utente contiene il numero di telefono completo dell'organizzazione e il numero di interno univoco dell'utente anziché un numero di telefono completo univoco per l'utente, è necessario disporre di una regola di conversione in uscita che a sua volta aggiunge il numero di telefono completo dell'organizzazione. Ad esempio:

|**Descrizione**|**Criterio di corrispondenza**|**Conversione**|**Esempio**|
|:-----|:-----|:-----|:-----|
|Converte i numeri a 5 cifre nel numero di telefono e nell'interno di un utente  <br/> |^(\d{5})$  <br/> |+14255550123;ext=$1  <br/> |10001 viene convertito in +14255550123;ext=10001  <br/> |
|Converte i numeri a 5 cifre nel numero di telefono dell'organizzazione e nell'interno di un utente  <br/> |^(\d{5})$  <br/> |+14255550100;ext=$1  <br/> |10001 viene convertito in +14255550100;ext=10001  <br/> |

In questo scenario, se i numeri di interno non sono supportati dal trunk peer che gestisce il reindirizzamento a PSTN, la regola di conversione in uscita deve inoltre prevedere la rimozione del numero di interno. Ad esempio:

|**Descrizione**|**Criterio di corrispondenza**|**Conversione**|**Esempio**|
|:-----|:-----|:-----|:-----|
|Rimuove l'interno dai numeri di telefono con interno  <br/> |^\+(\d\*); ext=(\d\*)$  <br/> |+$1  <br/> |+14255550123;ext=10001 viene convertito in +14255550123  <br/> |

Se è disponibile o meno un collegamento WAN, se nell'organizzazione non sono configurati numeri DID per singoli utenti e l'URI di linea per un utente contiene il numero di telefono dell'organizzazione e il numero di interno univoco dell'utente, è necessario configurare l'URI linea del numero di telefono dell'organizzazione con un numero raggiungibile dal trunk peer o dal gateway PSTN nel sito di succursale. È inoltre necessario configurare l'URI linea del numero di telefono dell'organizzazione in modo da includere il proprio interno univoco per le chiamate da instradare a tale numero.

#### <a name="preparing-for-voice-mail-survivability"></a>Preparazione per il funzionamento continuato (survivability) della segreteria telefonica

Exchange messaggistica unificata viene in genere installata solo in un sito centrale e non nei siti di succursale. Il chiamante deve poter lasciare un messaggio nella segreteria telefonica anche quando il collegamento WAN tra il sito di succursale e il sito centrale non è disponibile. Di conseguenza, la configurazione dell'URI linea per il numero di telefono del Operatore automatico di messaggistica unificata di Exchange che fornisce la segreteria telefonica per gli utenti del sito di succursale richiede considerazioni speciali, oltre ai criteri vocali, al dial plan e alle regole di normalizzazione applicabili a tale numero di segreteria telefonica.

I Survivable Branch Appliance (SBA) e i Survivable Branch Server offrono agli utenti di succursale la sopravvivenza della segreteria telefonica durante un'interruzione della rete WAN. In particolare, se si utilizza un Survivable Branch Appliance o un Survivable Branch Server e la rete WAN non è più disponibile, L'SBA o il Survivable Branch Server reindirizza le chiamate senza risposta sulla rete PSTN alla messaggistica unificata di Exchange nel sito centrale. Con un SBA o un Survivable Branch Server, gli utenti possono anche recuperare i messaggi vocali tramite PSTN durante un'interruzione della rete WAN. Infine, durante un'interruzione della rete WAN il Survivable Branch Appliance o il Survivable Branch Server accoda le notifiche di chiamata senza risposta e quindi le carica nel server Messaggistica unificata di Exchange quando la rete WAN viene ripristinata. Per garantire che il reindirizzamento della posta vocale sia resiliente, assicurarsi di aggiungere una voce per il nome di dominio completo del pool di siti centrale e una voce per l'FQDN del server perimetrale al file hosts nel Survivable Branch Server. In caso contrario, se il sito di succursale non dispone di un server DNS, può verificarsi il timeout della risoluzione DNS.

Per configurare il funzionamento continuato (survivability) della segreteria telefonica per gli utenti dei siti di succursale, sono consigliate le configurazioni seguenti:

- Un amministratore di Microsoft Exchange deve configurare Exchange messaggistica unificata Operatore automatico (AA) in modo che accetti solo i messaggi. Con questa configurazione viene disabilitata ogni altra funzionalità generica, ad esempio il trasferimento a un utente o al centralino. In alternativa, l'amministratore di Exchange può indirizzare le chiamate al centralino utilizzando Operatore automatico, generico o personalizzato.

- L Skype for Business Server amministratore deve prendere il numero di telefono AA e utilizzare tale numero di telefono come numero dell'operatore automatico di messaggistica unificata di **Exchange** nelle impostazioni di reindirizzamento della segreteria telefonica per il Survivable Branch Appliance o il server di succursale.

- L Skype for Business Server amministratore deve ottenere il numero di telefono di accesso del sottoscrittore di messaggistica unificata di Exchange e utilizzare tale  numero come numero di accesso del sottoscrittore nelle impostazioni di reindirizzamento della segreteria telefonica per il Survivable Branch Appliance o il Survivable Branch Server.

- L Skype for Business Server amministratore deve configurare la messaggistica unificata Exchange in modo che sia associato un solo dial plan a tutti gli utenti di succursale che necessitano dell'accesso alla segreteria telefonica durante un'interruzione della rete WAN.

- Quando il collegamento WAN non è disponibile, le chiamate agli utenti del sito di succursale possono essere instradati alla cassetta vocale di messaggistica unificata di Exchange dell'utente, ma solo se il criterio vocale applicato alla chiamata specifica un numero di telefono della segreteria telefonica univoco e non include un numero di interno.

#### <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Requisiti hardware e software per la resilienza dei siti di succursale

I requisiti hardware e software variano a seconda della soluzione di resilienza in uso.

#### <a name="requirements-for-survivable-branch-appliances"></a>Requisiti per Survivable Branch Appliance

L'hardware e il software necessari sono incorporati nel Survivable Branch Appliance. È tuttavia consigliabile che ogni sito di succursale distribuisca un server DHCP per ottenere gli indirizzi IP dei client. in caso contrario, alla scadenza del lease DHCP, i client non avranno connettività IP.

Se i server DNS aziendali si trovano solo nei siti centrali, gli utenti dei siti di succursale non saranno in grado di connettersi a essi durante un'interruzione della Skype for Business Server rete WAN e pertanto l'individuazione che utilizza il record di risorse DNS SRV (servizio) avrà esito negativo. Per garantire il reindirizzamento dei prompt durante un'interruzione della rete WAN, i record DNS devono essere memorizzati nella cache nel sito di succursale. Se il router di succursale lo supporta, attivare la memorizzazione nella cache DNS. In caso contrario, è possibile distribuire un server DNS nella succursale. Può trattarsi di un server autonomo o di una versione del Survivable Branch Appliance che supporta le funzionalità DNS. Per informazioni dettagliate, contattare il provider del Survivable Branch Appliance.

> [!NOTE]
> Presso un sito di succursale non è necessario un controller di dominio. Il Survivable Branch Appliance autentica i client utilizzando uno speciale certificato che invia il client in risposta alla richiesta di certificato del client quando esegue l'accesso.

Skype for Business client possono individuare il Skype for Business Server utilizzando l'opzione DHCP 120 (opzione di registrazione SIP). È possibile configurare tale opzione in uno dei due modi seguenti:

- Configurare il server DHCP nel sito di succursale per rispondere alle query DHCP 120, che restituiscono il nome di dominio completo della funzione di registrazione nel Survivable Branch Appliance o nel Survivable Branch Server.

- Attivare Skype for Business Server DHCP. Quando questa opzione è attivata, Skype for Business Server registrar risponde alle query DHCP Option 120. Si noti che la funzione di registrazione risponde solo alle query DHCP con l'opzione 120.

Nei siti di succursale di grandi dimensioni dotati di più subnet, per inoltrare query DHCP 120 al server DHCP (configurazione 1) o alla funzione di registrazione (configurazione 2), è inoltre necessario abilitare gli agenti di inoltro DHCP.

Infine, gli utenti del sito di succursale devono essere configurati per VoIP aziendale ed eseguire il provisioning con un endpoint di comunicazione unificato appropriato.

#### <a name="requirements-for-survivable-branch-servers"></a>Requisiti per Survivable Branch Server

I requisiti per i Survivable Branch Server sono gli stessi di un Front End Server. Per informazioni dettagliate, vedere [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

#### <a name="requirements-for-full-scale-skype-for-business-server-branch-site-deployments"></a>Requisiti per Full-Scale Skype for Business Server Branch-Site distribuzione

Per informazioni dettagliate, vedere [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) nella documentazione relativa alla pianificazione.

### <a name="example-configuring-a-failover-route"></a>Esempio: configurazione di una route di failover

 Nell'esempio seguente viene illustrato il modo in cui un amministratore può definire una route di failover da utilizzare se Dallas-GW1 viene disconnesso per la manutenzione o è altrimenti non disponibile. Nelle tabelle seguenti viene illustrata la modifica di configurazione necessaria.

**Tabella 1. Criteri utente**

|**Criterio utente**|**Utilizzo telefono**|
|:-----|:-----|
|Criteri di chiamata predefiniti  <br/> |Locale  <br/> GlobalPSTNHopoff  <br/> |
|Criteri locali Redmond  <br/> |RedmondLocal  <br/> |
|Criteri di chiamata Dallas  <br/> |DallasUsers  <br/> GlobalPSTNHopoff  <br/> |

**Tabella 2. Route**


| **Nome route**             | **Formato numero** | **Utilizzo telefono**         | **Trunk**                                 | **Gateway**                                     |
|:---------------------------|:-------------------|:------------------------|:------------------------------------------|:------------------------------------------------|
| Route locale Redmond  <br/> | ^\+1(425           | 206                     | 253)(\d{7})$  <br/>                       | Locale  <br/> RedmondLocal  <br/>                |
| Route locale Dallas  <br/>  | ^\+1(972           | 214                     | 469)(\d{7})$  <br/>                       | Locale  <br/>                                    |
| Universal Route  <br/>     | ^\+? (\d\*) $  <br/> | GlobalPSTNHopoff  <br/> | Trunk1  <br/> Trunk2  <br/> Trunk3  <br/> | Red-GW1  <br/> Red-GW2  <br/> Dallas-GW1  <br/> |
| Route utenti Dallas  <br/>  | ^\+? (\d\*) $  <br/> | DallasUsers  <br/>      | Trunk3  <br/>                             | Dallas-GW1  <br/>                               |

Nella tabella 1, è stato aggiunto l'utilizzo telefono GlobalPSTNHopoff dopo l'utilizzo telefono DallasUsers nei criteri di chiamata Dallas. In questo modo, le chiamate con i criteri di chiamata Dallas possono utilizzare le route configurate per l'utilizzo telefono GlobalPSTNHopoff se non è disponibile una route per l'utilizzo telefono DallasUsers.