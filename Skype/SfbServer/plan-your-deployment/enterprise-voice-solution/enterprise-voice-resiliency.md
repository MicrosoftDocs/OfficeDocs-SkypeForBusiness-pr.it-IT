---
title: Pianificare la resilienza VoIP aziendale in Skype for Business Server
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
ms.openlocfilehash: 493f599f7fbec2a67efaaf59851fd7c2f3b2d144
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675478"
---
# <a name="plan-for-enterprise-voice-resiliency-in-skype-for-business-server"></a>Pianificare la resilienza VoIP aziendale in Skype for Business Server

Informazioni su come supportare la resilienza vocale in Skype for Business Server VoIP aziendale, sia nei siti centrali che nei siti di succursale. Le opzioni del sito di succursale includono la distribuzione di Survivable Branch Appliance o Survivable Branch Server.

La resilienza vocale si riferisce alla possibilità degli utenti di continuare a effettuare e ricevere chiamate se un sito centrale che ospita Skype for Business Server diventa non disponibile, sia tramite un errore wan (WAN) che per un'altra causa. In caso di errore di un sito centrale, il servizio VoIP aziendale deve proseguire senza interruzione mediante failover ininterrotto su un sito di backup. In caso di errore della WAN, le chiamate dei siti di succursale devono essere reindirizzate a un PSTN locale. In questa sezione viene illustrata la pianificazione della resilienza vocale in caso di errore di un sito centrale o della WAN.

## <a name="central-site-resiliency"></a>Resilienza del sito centrale

Le aziende dispongono sempre più spesso di diversi siti sparsi in tutto il mondo. La gestione dei servizi di emergenza, l'accesso all'help desk e la possibilità di svolgere attività aziendali critiche quando un sito centrale è fuori servizio è essenziale per qualsiasi soluzione di resilienza VoIP aziendale. Quando un sito centrale diventa non disponibile, devono essere soddisfatte le condizioni seguenti:

- Deve essere predisposto il failover dei servizi vocali.

- Gli utenti che in genere si registrano nel pool Front End nel sito centrale devono essere in grado di registrarsi con un pool Front End alternativo. Questa operazione può essere eseguita creando più record SRV DNS, ognuno dei quali si risolve in un pool director o front-end in ognuno dei siti centrali. È possibile modificare la priorità e il peso dei record SRV in modo che gli utenti serviti da tale sito centrale ottengano il pool Director e Front End corrispondente prima di quelli in altri record SRV.

- Le chiamate verso e da utenti in altri siti devono essere reindirizzate al PSTN.

Questo argomento descrive la soluzione consigliata per la protezione della resilienza dei servizi vocali del sito centrale.

### <a name="architecture-and-topology"></a>Architettura e topologia

La pianificazione della resilienza vocale in un sito centrale richiede una conoscenza di base del ruolo centrale svolto dal registrar Skype for Business Server nell'abilitazione del failover vocale. Il registrar Skype for Business Server è un servizio che consente la registrazione e l'autenticazione client e fornisce servizi di routing. Viene eseguito in tutti i server edizione Standard, Front End Server, Director o Survivable Branch Appliance. Un pool di registrar è costituito da Servizi di registrazione in esecuzione nel pool Front End e che risiede nello stesso sito. Un client Skype for Business individua il pool Front End tramite il meccanismo di individuazione seguente:

1. Record SRV DNS

2. Servizio Web di individuazione automatica

3. Opzione DHCP 120

Dopo la connessione del client Skype for Business al pool Front End, il servizio di bilanciamento del carico lo indirizza a uno dei Front End Server nel pool. Tale Front End Server, a sua volta, reindirizza il client a un registrar preferito nel pool.

Ogni utente abilitato per VoIP aziendale viene assegnato a un pool di registrar specifico, che diventa il pool di registrar principale dell'utente. In ogni sito, un singolo pool di registrazione principale è solitamente condiviso da centinaia o migliaia di utenti. Per pianificare il consumo delle risorse del sito centrale da parte di eventuali utenti di siti di succursale che si basano sul sito centrale per i servizi di presenza, conferenza o failover, è consigliabile considerare ogni utente di sito di succursale come se fosse un utente registrato nel sito centrale. Attualmente non sono previsti limiti al numero di utenti del sito di succursale, inclusi gli utenti registrati con un'appliance survivable branch.

Per garantire la resilienza dei servizi vocali in caso di errore del sito centrale, per il pool di registrazione principale deve esistere un singolo pool di registrazione di backup designato in un altro sito. Il backup può essere configurato usando le impostazioni di resilienza di Generatore di topologie. Presupponendo l'esistenza di un collegamento WAN resiliente tra due siti, gli utenti per cui non è più disponibile il pool di registrazione principale verranno reindirizzati automaticamente al pool di registrazione di backup.

I passaggi seguenti descrivono il processo di individuazione e registrazione dei client:

1. Un client individua Skype for Business Server tramite record SRV DNS. In Skype for Business Server, i record SRV DNS possono essere configurati per restituire più di un FQDN alla query DNS SRV. Ad esempio, se l'azienda Contoso dispone di tre siti centrali (Nord America, Europa e Asia-Pacifico) e un pool di server Director in ogni sito centrale, i record DNS SRV possono puntare ai nomi FQDN del pool di server Director in ognuna delle tre posizioni. Finché il pool di director in una delle posizioni è disponibile, il client può connettersi al primo hop Skype for Business Server.

    > [!NOTE]
    > L'uso di un pool di director è facoltativo. È invece possibile usare un pool Front End.

2. Il pool di server director informa il client Skype for Business sul pool di registrazione primario dell'utente e sul pool di registrazione di backup.

3. Il client Skype for Business tenta prima di tutto di connettersi al pool di registrazione primario dell'utente. Se è disponibile, la registrazione viene accettata. Se il pool di registrar primario non è disponibile, il client Skype for Business tenta di connettersi al pool di registrazione di backup. Se il pool di registrazione di backup è disponibile e ha determinato che il pool di registrazione primario dell'utente non è disponibile (rilevando una mancanza di heartbeat per un intervallo di failover specificato), il pool di registrazione di backup accetta la registrazione dell'utente. Dopo che il registrar di backup ha rilevato che il registrar primario è nuovamente disponibile, il pool di registrar di backup reindirizza i client di failover al pool primario.

### <a name="requirements-and-recommendations"></a>Requisiti e raccomandazioni

I requisiti e le raccomandazioni seguenti per l'implementazione della resilienza dei servizi vocali del sito centrale sono appropriati per la maggior parte delle organizzazioni:

- I siti in cui risiedono i pool di registrazione principale e di backup dovrebbero essere connessi tramite un collegamento WAN resiliente.

- Ogni sito centrale deve contenere un pool di registrazione composto da una o più funzioni di registrazione.

- Ogni pool di registrazione deve essere bilanciato dal carico usando il bilanciamento del carico DNS, il bilanciamento del carico hardware o entrambi. Per informazioni dettagliate sulla pianificazione della configurazione del bilanciamento del carico, vedere [Requisiti di bilanciamento del carico per Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md).

- Ogni utente deve essere assegnato a un pool di registrazione primario usando il cmdlet **set-CsUser** di Skype for Business Server Management Shell o il Skype for Business Server Pannello di controllo.

- Per il pool di registrazione principale deve esistere un singolo pool di registrazione di backup posizionato in un diverso sito centrale.

- Il pool di registrazione principale deve essere configurato per il failover sul pool di registrazione di backup. Per impostazione predefinita, il pool principale è impostato per eseguire il failover sul pool di back dopo un intervallo di 300 secondi. È possibile modificare questo intervallo usando Skype for Business Server Generatore di topologie.

- Configurare una route di failover. Durante la configurazione della route specificare un gateway posizionato in un sito diverso da quello del gateway impostato nella route principale.

- Se il sito centrale contiene il server di gestione primario e il sito è probabilmente inattivo per un periodo prolungato, sarà necessario reinstallare gli strumenti di gestione nel sito di backup; in caso contrario, non sarà possibile modificare le impostazioni di gestione.

### <a name="dependencies"></a>Dipendenze

Skype for Business Server dipende dall'infrastruttura e dai componenti software seguenti per garantire la resilienza vocale:

|**Componente** <br/> |**Funzionale** <br/> |
|:-----|:-----|
|DNS  <br/> |Risoluzione dei record SRV e A per la connettività tra server e tra server e client  <br/> |
|Exchange e Servizi Web Exchange  <br/> |Archiviazione dei contatti; dati del calendario  <br/> |
|Messaggistica unificata di Exchange e Servizi Web Exchange  <br/> |Registri chiamate, segreteria telefonica e messaggi di segreteria telefonica  <br/> |
|Opzione DHCP 120  <br/> |Se non sono disponibili record DNS SRV, il client tenterà di utilizzare l'opzione DHCP 120 per individuare la funzione di registrazione. Affinché funzioni, è necessario configurare un server DHCP o Skype for Business Server DHCP deve essere abilitato.  <br/> |

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

  - Configurare il dial plan di messaggistica unificata Exchange di ogni utente per includere Exchange server di messaggistica unificata sia nel sito centrale che nel sito di backup, ma designare il backup Exchange server di messaggistica unificata come disabilitato. Se il sito primario non è più disponibile, l'amministratore Exchange deve contrassegnare i server di messaggistica unificata Exchange nel sito di backup come abilitati.

    Se nessuna delle soluzioni precedenti è possibile, Exchange messaggistica unificata non sarà disponibile nel caso in cui il sito centrale non sia disponibile.

- Conferenze di tutti i tipi

    Un utente reindirizzato su un sito di backup per il failover può partecipare a una conferenza creata e ospitata da un organizzatore assegnato a un pool disponibile, ma non può creare o ospitare una conferenza nel suo pool principale, che non è più disponibile. Analogamente, gli altri utenti non possono partecipare a conferenze ospitate nel pool primario dell'utente interessato.

Le funzionalità vocali seguenti non sono disponibili quando un sito centrale principale è fuori servizio:

- Operatore Conferenza

- Routing basato su DNS e basato sulla presenza

- Aggiornamento delle impostazioni di inoltro di chiamata.

- Response Group Service e parcheggio di chiamata

- Provisioning di nuovi telefoni e client

- Ricerca Web nella Rubrica

## <a name="branch-site-resiliency"></a>Resilienza del sito di succursale

Per garantire la resilienza del sito di succursale, ovvero il servizio di VoIP aziendale a disponibilità elevata, sono disponibili tre opzioni:

- Survivable Branch Appliance

- Server Survivable Branch

- Una distribuzione Skype for Business Server completa nel sito di succursale

Le informazioni in questa guida sono utili per valutare la soluzione di resilienza ottimale per l'organizzazione e, in base alla soluzione di resilienza, quale soluzione di connettività PSTN utilizzare. Saranno inoltre utili per preparare la distribuzione della soluzione scelta grazie alla descrizione dei prerequisiti e di altre considerazioni sulla pianificazione.

### <a name="branch-site-resiliency-features"></a>Funzionalità di resilienza del sito di succursale

Se si fornisce la resilienza del sito del ramo, se la connessione WAN di un sito di succursale a un sito centrale ha esito negativo o se il sito centrale non è raggiungibile, le funzionalità vocali seguenti devono continuare a essere disponibili:

- Chiamate PSTN in entrata e in uscita

- Chiamate Enterprise tra utenti dello stesso sito e di due siti diversi

- Gestione di base delle chiamate inclusi la messa in attesa, il recupero e il trasferimento

- Messaggistica istantanea tra due parti

- Inoltro di chiamata, squillo simultaneo di endpoint, delega delle chiamate e servizi di chiamata del team, ma solo se il delegato e il delegato (ad esempio, un manager e l'amministratore del manager) o tutti i membri del team, sono configurati nello stesso sito

- Registrazione dettagli chiamata (CDR)

- Conferenze telefoniche con accesso esterno PSTN con Operatore automatico conferenza

- Funzionalità di segreteria telefonica, se si configurano le impostazioni di rerouting della segreteria telefonica.

- Autenticazione e autorizzazione utente

Le funzionalità seguenti saranno disponibili solo se la soluzione di resilienza è una distribuzione Skype for Business Server su larga scala nel sito di succursale:

- Conferenze di messaggistica istantanea, Web e audio/video

- Routing in base a presenza e Non disturbare (le chiamate non squillano agli interni che hanno il Non disturbare attivato)

- Aggiornamento delle impostazioni di inoltro di chiamata.

- Applicazione response group e applicazione parcheggio di chiamata

- Provisioning di nuovi telefoni e client, ma solo se Active Directory Domain Services è presente nel sito di succursale.

- Enhanced 9-1-1 (E9-1-1)

    Se viene distribuito E9-1-1 e il trunk SIP nel sito centrale non è disponibile perché il collegamento WAN è inattivo, Survivable Branch Appliance instrada le chiamate E9-1-1 al gateway di succursale locale. Per abilitare questa funzionalità, i criteri vocali degli utenti del sito di succursale devono instradare le chiamate al gateway locale in caso di errore della rete WAN.

> [!NOTE]
> SBA (survivable Branch Office) non è supportato per XMPP. Gli utenti ospitati in configurazioni SBA non saranno in grado di inviare IMs o visualizzare La presenza con i contatti XMPP.

### <a name="branch-site-resiliency-solutions"></a>Soluzioni di resilienza del sito di succursale

Esistono vantaggi evidenti per la resilienza del sito di succursale per l'organizzazione. In particolare, se si perde la connessione al sito centrale, gli utenti del sito di succursale continueranno a disporre di VoIP aziendale servizio e segreteria telefonica (se si configurano le impostazioni di reindirizzamento della segreteria telefonica). Tuttavia, per i siti con meno di 25 utenti, una soluzione di resilienza potrebbe non fornire un ritorno sugli investimenti sufficiente.

Se si decide di garantire la resilienza dei siti di succursale, sono disponibili tre opzioni. Per scegliere l'opzione più adatta all'organizzazione, utilizzare come riferimento la tabella riportata di seguito.

|**Se tu...**|**È consigliabile usare un...**|
|:-----|:-----|
|Nel sito di succursale vengono ospitati dai 25 ai 1000 utenti e l'utile sugli investimenti non consente una distribuzione completa oppure non è disponibile supporto amministrativo locale  <br/> |Survivable Branch Appliance  <br/> Survivable Branch Appliance è un server blade standard del settore con un registrar Skype for Business Server e mediation server in esecuzione in Windows Server 2008 R2. Survivable Branch Appliance contiene anche un gateway PSTN (Public Switched Telephone Network). I dispositivi di terze parti qualificati, sviluppati da partner Microsoft nell'ambito del programma di qualifica e certificazione degli SBA (Survivable Branch Appliance), forniscono una connessione PSTN continua in caso di problemi della rete WAN, ma non garantiscono un servizio di presenza o conferenza resiliente perché tali funzionalità dipendono dai Front End Server nel sito centrale.  <br/> Per informazioni dettagliate su Survivable Branch Appliance, vedere "Dettagli su Survivable Branch Appliance" più avanti in questo argomento.  <br/> **Nota:** Se si decide di usare anche un trunk SIP con Survivable Branch Appliance, contattare il fornitore di Survivable Branch Appliance per informazioni sul provider di servizi più adatto all'organizzazione. <br/> |
|Ospitare tra 1000 e 2000 utenti nel sito di succursale, non dispone di una connessione WAN resiliente e sono stati sottoposti a training Skype for Business Server amministratori disponibili  <br/> |Survivable Branch Server o due appliance Survivable Branch.  <br/> Survivable Branch Server è un server di Windows che soddisfa i requisiti hardware specificati in cui sono installati Skype for Business Server software Registrar e Mediation Server. Deve connettersi a un gateway PSTN o a un trunk SIP verso un provider di servizi telefonici.  <br/> Per informazioni dettagliate su Survivable Branch Server, vedere "Dettagli su Survivable Branch Server" più avanti in questo argomento.  <br/> |
|Se sono necessarie funzionalità di presenza e conferenza oltre alle funzionalità vocali per un massimo di 5000 utenti e sono stati formati Skype for Business Server amministratori disponibili  <br/> |Eseguire la distribuzione come sito centrale con un server Standard Edition anziché come sito di succursale.  <br/> Una distribuzione di Skype for Business Server su larga scala offre una connessione PSTN continua e una presenza resiliente e conferenze in caso di errore della rete WAN.  <br/> |

#### <a name="resiliency-topologies"></a>Topologie di resilienza

Nella figura seguente vengono illustrate le topologie consigliate per la resilienza dei siti di succursale.

**Opzioni di resilienza per i siti di succursale**

![Opzioni di resilienza di Voice Branch.](../../media/Plan_OCS_Voice_BranchResiliencyOptions.jpg)

#### <a name="survivable-branch-appliance-details"></a>Dettagli relativi al Survivable Branch Appliance

La Skype for Business Server Survivable Branch Appliance include i componenti seguenti:

- Una funzione di registrazione per l'autenticazione degli utenti, la registrazione e il routing delle chiamate

- Un Mediation Server per la gestione dei segnali tra la funzione di registrazione e un gateway PSTN

- Un gateway PSTN per il routing delle chiamate alla rete PSTN come trasporto di fallback in caso di problemi della rete WAN

- SQL Server Express per l'archiviazione dei dati degli utenti in locale

Survivable Branch Appliance include anche trunk PSTN, porte analogiche e un adattatore Ethernet.

Se la connessione WAN del sito di succursale a un sito centrale non è più disponibile, gli utenti del ramo interno continuano a essere registrati con Survivable Branch Appliance Registrar e ottengono un servizio vocale ininterrotto tramite la connessione di Survivable Branch Appliance alla rete PSTN. Gli utenti del sito di succursale che si connettono da casa o da altre postazioni remote saranno in grado di registrarsi in un server di registrazione presso un sito centrale in caso di non disponibilità del collegamento WAN al sito di succursale. Tali utenti disporranno della funzionalità di comunicazione unificata completa, con l'unica eccezione che le chiamate in ingresso nel sito di succursale verranno indirizzate alla segreteria telefonica. Quando la connessione WAN torna disponibile, per gli utenti del sito di succursale viene ripristinata la funzionalità completa. Né il failover in Survivable Branch Appliance né il ripristino del servizio richiedono la presenza di un amministratore IT.

Skype for Business Server supporta fino a due Survivable Branch Appliance in un sito di succursale.

#### <a name="survivable-branch-appliance-deployment-overview"></a>Panoramica della distribuzione del Survivable Branch Appliance

Survivable Branch Appliance è prodotto da produttori di apparecchiature originali in collaborazione con Microsoft e distribuito per loro conto da rivenditori a valore aggiunto. Questa distribuzione deve essere eseguita solo dopo Skype for Business Server è stata distribuita nel sito centrale, è stata stabilita una connessione WAN al sito di succursale e gli utenti del sito di succursale sono abilitati per VoIP aziendale.

Per informazioni dettagliate su queste fasi, vedere [Deploying a Survivable Branch Appliance or Server](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-a-survivable-branch-appliance-or-server) nella documentazione relativa alla distribuzione.

|**Fase**|**Procedura**|**Diritti utente**|
|:-----|:-----|:-----|
|Configurare Active Directory Domain Services per Survivable Branch Appliance  <br/> |**Nel sito centrale:** <br/>  Creare un account utente di dominio (o un'identità aziendale) per il tecnico che installerà e attiverà Survivable Branch Appliance nel sito del ramo. <br/>  Creare un account computer (con il nome di dominio completo (FQDN) applicabile per Survivable Branch Appliance in Active Directory Domain Services. <br/>  In Generatore di topologie creare e pubblicare Survivable Branch Appliance. <br/> |L'account utente del tecnico deve essere membro del gruppo RTCUniversalSBATechnicians. L'appliance survivable Branch deve appartenere al gruppo RTCSBAUniversalServices, che si verifica automaticamente quando si usa Generatore di topologie.  <br/> |
|Installare e attivare Survivable Branch Appliance.  <br/> |**Nel sito di succursale:** <br/>  Connessione Survivable Branch Appliance a una porta Ethernet e a una porta PSTN. <br/>  Avviare Survivable Branch Appliance. <br/>  Aggiungere Survivable Branch Appliance al dominio usando l'account utente di dominio creato per Survivable Branch Appliance nel sito centrale. Impostare l'FQDN e l'indirizzo IP in modo che corrispondano all'FQDN creato nell'account computer. <br/>  Configurare Survivable Branch Appliance usando l'interfaccia utente OEM. <br/>  Verificare la connettività PSTN. <br/> |L'account utente del tecnico deve essere membro del gruppo RTCUniversalSBATechnicians.  <br/> |

#### <a name="survivable-branch-server-details"></a>Dettagli relativi al Survivable Branch Server

In Generatore di topologie creare il sito del ramo aggiungere survivable Branch Server a tale sito ed eseguire la Distribuzione guidata Skype for Business Server nel computer in cui si vuole installare il ruolo.

### <a name="branch-site-resiliency-requirements"></a>Requisiti di resilienza del sito di succursale

In questo argomento vengono fornite informazioni utili per preparare gli utenti per la resilienza dei siti di succursale e per il funzionamento continuato (survivability) della segreteria telefonica e vengono specificati i requisiti hardware e software pertinenti.

#### <a name="preparing-branch-users-for-branch-site-resiliency"></a>Preparazione degli utenti di succursale per la resilienza del sito di succursale

Preparare gli utenti per la resilienza del sito di succursale impostando il pool di registrar come Survivable Branch Appliance (SBA) o Survivable Branch Server.

#### <a name="registrar-assignments-for-branch-users"></a>Assegnazioni di registrazione per utenti di succursale

Indipendentemente dalla soluzione di resilienza del sito del ramo scelta, sarà necessario assegnare un registrar primario a ogni utente. Gli utenti del sito di succursale devono sempre registrarsi al registrar nel sito di succursale, indipendentemente dal fatto che il registrar si trovi in Survivable Branch Appliance, Survivable Branch Server o in un server autonomo Skype for Business Server Standard o edizione Enterprise. È necessario un record di risorse del servizio DNS (Domain Name System) per consentire a un client di individuare il pool di registrar. Se Survivable Branch Appliance diventa non disponibile, questo è il modo in cui i client del sito di succursale individuano automaticamente il registrar di backup.

Se un sito di succursale non dispone di un server DNS, esistono due modi alternativi per configurare l'individuazione di Survivable Branch Appliance o Survivable Branch Server:

- Configurare l'opzione DHCP 120 nel server DHCP (Dynamic Host Configuration Protocol) del sito del ramo in modo che punti al nome di dominio completo (FQDN) dell'appliance survivable branch o del server di succursale Survivable.

- Configurare Survivable Branch Appliance o Survivable Branch Server per rispondere alle query DHCP 120.

#### <a name="voice-routing-for-branch-users"></a>Routing vocale per gli utenti di succursale

Per gli utenti di un sito di succursale è consigliabile creare criteri VoIP (Voice over Internet Protocol) a livello di utente separati. Questo criterio deve includere una route primaria che usa survivable Branch Appliance o il gateway del server di succursale e una o più route di backup che usano un trunk con un gateway PSTN (Public Switched Telephone Network) nel sito centrale. Se la route principale non è disponibile, viene sostituita dalla route di backup, che può utilizzare uno o più gateway del sito centrale. In questo modo, indipendentemente dalla posizione in cui un utente è registrato, nel registrar del sito di succursale o nel pool di registrar di backup nel sito centrale, i criteri VoIP dell'utente sono sempre attivi. Questa considerazione è particolarmente importante per gli scenari di failover. Ad esempio, se è necessario rinominare Survivable Branch Appliance o riconfigurare Survivable Branch Appliance per connettersi a un pool di registrar di backup nel sito centrale, è necessario spostare gli utenti del sito di succursale nel sito centrale per la durata. Per informazioni dettagliate sulla ridenominazione o la riconfigurazione di un'appliance survivable Branch, vedere [Appendice B: Gestione di un'appliance survivable branch](/previous-versions/office/lync-server-2013/lync-server-2013-appendix-b-managing-a-survivable-branch-appliance) nella documentazione relativa alla distribuzione. Se tali utenti non hanno criteri VoIP a livello di utente o dial plan a livello di utente, quando gli utenti vengono spostati in un altro sito, i criteri VoIP a livello di sito e i dial plan a livello di sito del sito centrale si applicano agli utenti per impostazione predefinita, anziché ai criteri VoIP e ai dial plan a livello di sito di succursale. In questo scenario le chiamate degli utenti del sito di succursale avranno esito positivo se a tali utenti non è possibile applicare i criteri VoIP e i dial plan a livello di sito utilizzati dal pool di registrazione di backup. Se ad esempio gli utenti di un sito di succursale situato in Giappone vengono spostati in un sito centrale situato a Redmond, è improbabile che un dial plan con regole di normalizzazione che antepongono il prefisso +1425 a tutte le chiamate a numeri di sette cifre sia in grado di convertire correttamente le chiamate di tali utenti.

> [!IMPORTANT]
> Quando si crea una route di backup per una succursale, è consigliabile aggiungere ai criteri utente della succursale due record di utilizzo telefono PSTN e assegnare route distinte a ognuno. La prima route, o primaria, indirizza le chiamate al gateway associato a Survivable Branch Appliance (SBA) o al server di succursale; la seconda route, o backup, indirizza le chiamate al gateway nel sito centrale. Per l'indirizzamento delle chiamate, l'SBA o il server di succursale dovrà tentare tutte le route assegnate al primo record di utilizzo PSTN prima di tentare quelle del secondo record di utilizzo.

Per garantire che le chiamate in ingresso agli utenti del sito di succursale raggiungano gli utenti quando il gateway di succursale o il componente Windows del sito su Survivable Branch Appliance non è disponibile (ad esempio, se l'appliance di ramo Survivable o il gateway ramo non è attivo per la manutenzione), creare una route di failover nel gateway (o collaborare con il provider DID (Direct Inward Dialing) per reindirizzare le chiamate in ingresso al pool di registrar di backup nel sito centrale. Dal pool di registrazione di backup del sito centrale le chiamate verranno instradate agli utenti di succursale attraverso il collegamento WAN. Assicurarsi che la route traduca i numeri in modo che siano conformi ai formati di numero di telefono accettati del gateway PSTN o di altri peer trunk. Per informazioni dettagliate sulla creazione di una route di failover, vedere [Configuring a Failover Route](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-a-failover-route). Per consentire la normalizzazione delle chiamate in arrivo da parte del trunk associato al gateway del sito di succursale, è inoltre necessario creare dial plan a livello di servizio. Se si dispone di due survivable Branch Appliance in un sito di succursale, è possibile creare un dial plan a livello di sito per entrambi, a meno che non sia necessario un piano a livello di servizio separato per ognuno di essi.

> [!NOTE]
> Per tenere conto del consumo delle risorse del sito centrale da parte degli utenti dei siti di succursale che si appoggiano al sito centrale per le funzionalità di presenza, conferenza o failover, è consigliabile considerare ogni utente del sito di succursale come se fosse registrato presso il sito centrale. Attualmente non sono previsti limiti al numero di utenti del sito di succursale, inclusi gli utenti registrati con un'appliance survivable branch.

È inoltre consigliabile creare criteri vocali e di dial plan a livello di utente e quindi assegnarli agli utenti del sito di succursale. Per informazioni dettagliate, vedere [Creare o modificare un dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md) e [Creare i criteri di routing VoIP per gli utenti dei rami](/previous-versions/office/lync-server-2013/lync-server-2013-create-the-voip-routing-policy-for-branch-users) nella documentazione relativa alla distribuzione.

#### <a name="routing-extension-numbers"></a>Routing di numeri di interno

Quando si preparano i dial plan e i criteri vocali per gli utenti del sito di succursale, assicurarsi di includere regole di normalizzazione e regole di conversione che corrispondono alle stringhe e al formato numerico usati nell'attributo msRTCSIP-line (o URI di riga), in modo che Skype for Business chiamate abilitate tra gli utenti del sito di succursale e gli utenti del sito centrale vengano indirizzate correttamente, in particolare quando le chiamate devono essere reindirizzate sul PSTN perché il collegamento WAN non è disponibile. Per i numeri composti contenenti numeri di interno, sono inoltre necessarie considerazioni specifiche rispetto ai numeri di telefono semplici.

Per le regole di normalizzazione e le regole di conversione corrispondenti a URI di linea contenenti un numero di interno, da solo o insieme a un numero di telefono E. 164 completo, esistono requisiti aggiuntivi. In questa sezione sono descritti alcuni scenari di esempio con l'indirizzamento di chiamate per URI di linea contenenti un numero di interno.

Se nell'organizzazione non sono configurati numeri di telefono DID (Direct Inward Dial) per utenti singoli e l'URI di linea di ogni utente è configurato con un solo numero di interno, gli utenti interni possono chiamarsi componendo solo il numero di interno desiderato. È tuttavia necessario configurare regole di normalizzazione applicabili alle chiamate da un utente di un sito di succursale a un utente del sito centrale corrispondenti ai numeri di interno.

In uno scenario in cui sia disponibile un collegamento WAN tra il sito di succursale e il sito centrale, per le chiamate tra utenti del sito di succursale e utenti del sito centrale non è necessaria la regola di normalizzazione per la conversione del numero, poiché la chiamata non viene indirizzata attraverso PSTN. Ad esempio:

|**Nome regola**|**Descrizione**|**Formato numero**|**Conversione**|**Esempio**|
|:-----|:-----|:-----|:-----|:-----|
|5digitExtensions  <br/> |Non converte i numeri a cinque cifre  <br/> |^(\d{5})$  <br/> |$1  <br/> |10001 non viene convertito  <br/> |

È inoltre necessario prevedere numeri di interno per scenari specifici in cui, ad esempio, il collegamento WAN tra un sito di succursale e il sito centrale non sia disponibile e sia necessario instradare tramite PSTN le chiamate provenienti dal sito di succursale. Durante un'interruzione della rete WAN, se un utente del sito di succursale chiama un utente del sito centrale solo chiamando l'estensione dell'utente del sito centrale, è necessario disporre di una regola di traduzione in uscita che aggiunge il numero di telefono completo dell'utente del sito centrale. Se l'URI di riga di un utente contiene il numero di telefono completo dell'organizzazione e il numero di estensione univoco dell'utente anziché un numero di telefono completo univoco per l'utente, è necessario disporre di una regola di traduzione in uscita che aggiunge invece il numero di telefono completo dell'organizzazione. Ad esempio:

|**Descrizione**|**Modello di corrispondenza**|**Conversione**|**Esempio**|
|:-----|:-----|:-----|:-----|
|Converte i numeri a 5 cifre nel numero di telefono e nell'estensione di un utente  <br/> |^(\d{5})$  <br/> |+14255550123;ext=$1  <br/> |10001 viene convertito in +14255550123;ext=10001  <br/> |
|Converte i numeri a 5 cifre nel numero di telefono dell'organizzazione e nell'estensione di un utente  <br/> |^(\d{5})$  <br/> |+14255550100;ext=$1  <br/> |10001 viene convertito in +14255550100;ext=10001  <br/> |

In questo scenario, se i numeri di interno non sono supportati dal trunk peer che gestisce il reindirizzamento a PSTN, la regola di conversione in uscita deve inoltre prevedere la rimozione del numero di interno. Ad esempio:

|**Descrizione**|**Modello di corrispondenza**|**Conversione**|**Esempio**|
|:-----|:-----|:-----|:-----|
|Rimuove l'interno dai numeri di telefono con interno  <br/> |^\+(\d\*); ext=(\d\*)$  <br/> |+$1  <br/> |+14255550123;ext=10001 viene convertito in +14255550123  <br/> |

Indipendentemente dal fatto che sia disponibile un collegamento WAN, se l'organizzazione non dispone di numeri DID configurati per i singoli utenti e l'URI di riga per un utente contiene il numero di telefono dell'organizzazione e il numero di estensione univoco dell'utente, è necessario configurare l'URI di riga del numero di telefono dell'organizzazione con un numero raggiungibile dal peer trunk o dal gateway PSTN nel sito di succursale. È anche necessario configurare l'URI di linea del numero di telefono dell'organizzazione in modo da includere la propria estensione univoca per l'instradamento delle chiamate a tale numero.

#### <a name="preparing-for-voice-mail-survivability"></a>Preparazione per il funzionamento continuato (survivability) della segreteria telefonica

Exchange messaggistica unificata viene in genere installata solo in un sito centrale e non nei siti di succursale. Il chiamante deve poter lasciare un messaggio nella segreteria telefonica anche quando il collegamento WAN tra il sito di succursale e il sito centrale non è disponibile. Di conseguenza, la configurazione dell'URI di riga per il numero di telefono dell'operatore automatico di messaggistica unificata Exchange che fornisce la segreteria telefonica per gli utenti del sito di succursale richiede considerazioni speciali, oltre ai criteri vocali, al dial plan e alle regole di normalizzazione applicabili a tale numero di segreteria telefonica.

Survivable Branch Appliance (SBA) e Survivable Branch Server offrono la possibilità di sopravvivenza della segreteria telefonica per gli utenti dei rami durante un'interruzione della rete WAN. In particolare, se si usa survivable Branch Appliance o Survivable Branch Server e la rete WAN non è più disponibile, SBA o Survivable Branch Server reindirizza le chiamate senza risposta tramite PSTN per Exchange messaggistica unificata nel sito centrale. Con SBA o Survivable Branch Server, gli utenti possono anche recuperare i messaggi di segreteria telefonica tramite pstn durante un'interruzione della rete WAN. Infine, durante un'interruzione della rete WAN, Survivable Branch Appliance o Survivable Branch Server accoda le notifiche di chiamata senza risposta e quindi le carica nel server di messaggistica unificata Exchange quando viene ripristinata la rete WAN. Per garantire che il reindirizzamento della segreteria telefonica sia resiliente, assicurarsi di aggiungere una voce per l'FQDN del pool di siti centrale e una voce per l'FQDN del server perimetrale al file hosts nel survivable Branch Server. In caso contrario, se il sito di succursale non dispone di un server DNS, può verificarsi il timeout della risoluzione DNS.

Per configurare il funzionamento continuato (survivability) della segreteria telefonica per gli utenti dei siti di succursale, sono consigliate le configurazioni seguenti:

- Un amministratore di Microsoft Exchange deve configurare Exchange operatore automatico di messaggistica unificata (AA) per accettare solo i messaggi. Con questa configurazione viene disabilitata ogni altra funzionalità generica, ad esempio il trasferimento a un utente o al centralino. In alternativa, l'amministratore di Exchange può indirizzare le chiamate al centralino utilizzando Operatore automatico, generico o personalizzato.

- L'amministratore Skype for Business Server deve prendere il numero di telefono AA e usare tale numero di telefono come numero **di operatore automatico di messaggistica unificata di scambio** nelle impostazioni di reindirizzamento della segreteria telefonica per survivable Branch Appliance o il server di succursale.

- L'amministratore Skype for Business Server deve ottenere il numero di telefono di accesso del sottoscrittore di messaggistica unificata Exchange e usarlo come numero di **accesso del Sottoscrittore** nelle impostazioni di reindirizzamento della segreteria telefonica per Survivable Branch Appliance o Survivable Branch Server.

- L'amministratore Skype for Business Server deve configurare Exchange messaggistica unificata in modo che un solo dial plan sia associato a tutti gli utenti del ramo che devono accedere alla segreteria telefonica durante un'interruzione della rete WAN.

- Quando il collegamento WAN non è disponibile, le chiamate agli utenti del sito di succursale possono essere indirizzate alla cassetta postale vocale Exchange messaggistica unificata dell'utente, ma solo se i criteri vocali applicati alla chiamata specificano un numero di telefono della segreteria telefonica univoco e non include un numero di estensione.

#### <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Requisiti hardware e software per la resilienza dei siti di succursale

I requisiti hardware e software variano a seconda della soluzione di resilienza in uso.

#### <a name="requirements-for-survivable-branch-appliances"></a>Requisiti per Survivable Branch Appliance

L'hardware e il software necessari sono integrati in Survivable Branch Appliance. Tuttavia, è anche consigliabile che ogni sito di succursale distribuisa un server DHCP per ottenere gli indirizzi IP client; in caso contrario, quando il lease DHCP scade, i client non avranno connettività IP.

Se i server DNS aziendali si trovano solo nei siti centrali, gli utenti del sito di succursale non saranno in grado di connettersi a tali server durante un'interruzione della rete WAN e pertanto Skype for Business Server'individuazione che usa il record di risorse SRV DNS (servizio SRV) avrà esito negativo. Per garantire il reindirizzamento delle richieste durante un'interruzione della rete WAN, i record DNS devono essere memorizzati nella cache nel sito del ramo. Se il router del ramo lo supporta, attivare la memorizzazione nella cache DNS. In alternativa, è possibile distribuire un server DNS nel ramo. Può trattarsi di un server autonomo o di una versione di Survivable Branch Appliance che supporta le funzionalità DNS. Per informazioni dettagliate, contattare il provider di Survivable Branch Appliance.

> [!NOTE]
> Presso un sito di succursale non è necessario un controller di dominio. Survivable Branch Appliance autentica i client usando un certificato speciale che invia il client in risposta alla richiesta di certificato del client al momento dell'accesso.

Skype for Business client possono individuare il Skype for Business Server usando l'opzione DHCP 120 (opzione di registrazione SIP). È possibile configurare tale opzione in uno dei due modi seguenti:

- Configurare il server DHCP nel sito di succursale per rispondere alle query DHCP 120, che restituiscono il nome di dominio completo del registrar in Survivable Branch Appliance o Survivable Branch Server.Configure the DHCP server at the Branch Site to reply to DHCP 120 queries, which return the FQDN of the Registrar on the Survivable Branch Appliance or Survivable Branch Server.

- Attivare Skype for Business Server DHCP. Quando questa opzione è attivata, il registrar Skype for Business Server risponde alle query dell'opzione DHCP 120. Si noti che la funzione di registrazione risponde solo alle query DHCP con l'opzione 120.

Nei siti di succursale di grandi dimensioni dotati di più subnet, per inoltrare query DHCP 120 al server DHCP (configurazione 1) o alla funzione di registrazione (configurazione 2), è inoltre necessario abilitare gli agenti di inoltro DHCP.

Infine, gli utenti del sito di succursale devono essere configurati per VoIP aziendale e sottoposti a provisioning con un endpoint di comunicazione unificata appropriato.

#### <a name="requirements-for-survivable-branch-servers"></a>Requisiti per Survivable Branch Server

I requisiti per Survivable Branch Server sono gli stessi dei requisiti per un Front End Server. Per informazioni dettagliate, vedere [Requisiti del server per Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

#### <a name="requirements-for-full-scale-skype-for-business-server-branch-site-deployments"></a>Requisiti per le distribuzioni Full-Scale Skype for Business Server Branch-Site

Per informazioni dettagliate, vedere [Requisiti del server per Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) nella documentazione relativa alla pianificazione.

### <a name="example-configuring-a-failover-route"></a>Esempio: configurazione di una route di failover

 Nell'esempio seguente viene illustrato il modo in cui un amministratore può definire una route di failover da utilizzare se Dallas-GW1 viene disconnesso per la manutenzione o è altrimenti non disponibile. Nelle tabelle seguenti viene illustrata la modifica di configurazione necessaria.

**Tabella 1. Criteri utente**

|**Criterio utente**|**Utilizzo telefono**|
|:-----|:-----|
|Criteri di chiamata predefiniti  <br/> |Locale  <br/> GlobalPSTNHopoff  <br/> |
|Criteri locali Redmond  <br/> |RedmondLocal  <br/> |
|Criteri di chiamata Dallas  <br/> |DallasUsers  <br/> GlobalPSTNHopoff  <br/> |

**Tabella 2. Route**


| **Nome route**             | **Formato numero** | **Utilizzo telefono**         | **Tronco**                                 | **Gateway**                                     |
|:---------------------------|:-------------------|:------------------------|:------------------------------------------|:------------------------------------------------|
| Route locale Redmond  <br/> | ^\+1(425           | 206                     | 253)(\d{7})$  <br/>                       | Locale  <br/> RedmondLocal  <br/>                |
| Route locale Dallas  <br/>  | ^\+1(972           | 214                     | 469)(\d{7})$  <br/>                       | Locale  <br/>                                    |
| Universal Route  <br/>     | ^\+? (\d\*) $  <br/> | GlobalPSTNHopoff  <br/> | Trunk1  <br/> Trunk2  <br/> Trunk3  <br/> | Red-GW1  <br/> Red-GW2  <br/> Dallas-GW1  <br/> |
| Route utenti Dallas  <br/>  | ^\+? (\d\*) $  <br/> | DallasUsers  <br/>      | Trunk3  <br/>                             | Dallas-GW1  <br/>                               |

Nella tabella 1, è stato aggiunto l'utilizzo telefono GlobalPSTNHopoff dopo l'utilizzo telefono DallasUsers nei criteri di chiamata Dallas. In questo modo, le chiamate con i criteri di chiamata Dallas possono utilizzare le route configurate per l'utilizzo telefono GlobalPSTNHopoff se non è disponibile una route per l'utilizzo telefono DallasUsers.