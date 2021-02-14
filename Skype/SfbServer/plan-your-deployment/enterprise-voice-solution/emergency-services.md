---
title: Pianificare i servizi di emergenza in Skype for Business Server
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
ms.assetid: ed843ed7-371f-46cc-969a-f8062c06fc55
description: Informazioni sui servizi Enhanced 9-1-1 (E9-1-1) in Skype for Business Server VoIP aziendale, tra cui l'acquisizione della posizione e il routing delle chiamate.
ms.openlocfilehash: e8eb805a4e4d55f08a4c6aec1a57618c74bcfa02
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825766"
---
# <a name="plan-for-emergency-services-in-skype-for-business-server"></a>Pianificare i servizi di emergenza in Skype for Business Server

Informazioni sui servizi Enhanced 9-1-1 (E9-1-1) in Skype for Business Server VoIP aziendale, tra cui l'acquisizione della posizione e il routing delle chiamate.

Skype for Business Server supporta i servizi Enhanced 9-1-1 (E9-1-1) all'interno degli Stati Uniti come parte di una VoIP aziendale distribuzione. Tale funzionalità associa una chiamata a un numero di emergenza a una posizione ERL (Emergency Response Location) costituita da una via e un numero civico e da altre informazioni più specifiche, ad esempio il numero del piano, per le chiamate provenienti da edifici per uso ufficio e da altre strutture con più locatari. Utilizzando la posizione ERL fornita, un centro di raccolta delle chiamate di emergenza (PSAP, Public Safety Answering Point) può fornire immediatamente i servizi di emergenza al chiamante in difficoltà con un minore rischio di indirizzare inavvertitamente l'operatore a una posizione errata o ambigua.

> [!NOTE]
> Skype for Business Server ora supporta la configurazione di più numeri di emergenza per un client. Per ulteriori informazioni, vedere [Pianificare più numeri di emergenza in Skype for Business Server.](multiple-emergency-numbers.md)

> [!NOTE]
> Skype for Business Server include tre funzionalità VoIP aziendale avanzate: controllo di ammissione di chiamata, servizi di emergenza (E9-1-1) e bypass multimediale. Per una panoramica delle informazioni di pianificazione comuni a tutte e tre queste funzionalità, vedere Impostazioni di rete per le funzionalità VoIP aziendale avanzate [in Skype for Business Server.](network-settings-for-advanced-features.md)

Skype for Business Server supporta le chiamate Enhanced 9-1-1 (E9-1-1) dai client Skype for Business e dai dispositivi Lync Phone Edition. Quando si configura Skype for Business Server per il servizio E9-1-1, le chiamate di emergenza effettuate da Skype for Business o Lync Phone Edition includono le informazioni ERL (Emergency Response Location) del database del servizio informazioni sulla posizione. Le informazioni ERL includono gli indirizzi civici (ovvero la via) e altri dati che consentono di individuare la posizione con maggiore precisione in edifici di uffici e altre strutture con più occupanti. Quando un utente effettua una chiamata di emergenza, Skype for Business Server instrada l'audio della chiamata, insieme alle informazioni sulla posizione e sulla richiamata, tramite un Mediation Server a un provider di servizi E9-1-1. Tale provider utilizza l'indirizzo civico del chiamante per instradare la chiamata al centro di raccolta delle chiamate di emergenza (PSAP) responsabile per l'area in cui si trova il chiamante, quindi invia la chiave di query del servizio di emergenza (ESQK, Emergency Service Query Key) che verrà utilizzata dal centro PSAP per cercare le informazioni ERL del chiamante.

Skype for Business Server supporta due metodi per il routing delle chiamate di emergenza a un provider di servizi E9-1-1:

- Una connessione trunk SIP (Session Initiation Protocol) a un provider di servizi E9-1-1 qualificato

- Un gateway ELIN (Emergency Location Identification Number) a un provider di servizi E9-1-1 basato su PSTN (Public Switched Telephone Network)

Quando si utilizza un provider di servizi E9-1-1 trunk SIP, si aggiungono ERL al database del servizio informazioni percorso e quindi si convalidano le posizioni in base a un master street address guide (MSAG) gestito dal provider di servizi E9-1-1. Se un provider di servizi E9-1-1 riceve una chiamata che non dispone di informazioni sulla posizione o dispone di una posizione che non è stata convalidata rispetto al servizio MSAG, il provider di servizi E9-1-1 instrada la chiamata a un ECRC (Emergency Call Response Center) nazionale/regionale, che dispone di personale appositamente formato che ottiene verbalmente la posizione del chiamante, se possibile, e instrada manualmente la chiamata al CENTRO PSAP appropriato. Alcuni provider di servizi E9-1-1 su trunk SIP inoltre forniscono ai clienti un numero DID (Direct Inward Dialing) PSTN per il centro ECRC, offrendo un mezzo alternativo per il routing delle chiamate 9-1-1 in caso di malfunzionamento del trunk SIP per un motivo qualsiasi.

A differenza dei telefoni TDM (Time Division Multiplexing) e PBX (Private Branch Exchange) basati su IP, che hanno posizioni fisse, un endpoint Skype for Business può essere molto mobile. Quando si distribuisce la funzionalità E9-1-1, Skype for Business Server garantisce che, indipendentemente dalla posizione del chiamante, la chiamata di emergenza possa essere instradata al centro psap che serve la posizione del chiamante. Ad esempio, se l'ufficio principale di un utente si trova a Redmond, Washington, ma l'utente esegue una chiamata di emergenza da un computer in una succursale di Wichita, Indro, il trunk SIP o il provider di servizi E9-1-1 basato su PSTN instraderà la chiamata al CENTRO PSAP di Wichita, non al centro PSAP di Redmond.

Quando si utilizza un gateway ELIN, si aggiungono anche ERL al database del servizio informazioni percorso, ma si include anche un numero ELIN per ogni posizione. Il numero ELIN diventa il numero chiamante durante la chiamata di emergenza. È quindi necessario verificare che la portante PSTN carichi i numeri ELIN nel database ALI (Automatic Location Identification).

> [!NOTE]
> I dispositivi analogici connessi a Skype for Business non possono ricevere informazioni sulla posizione dal servizio informazioni sulla posizione o trasmettere la posizione al provider di servizi E9-1-1.

 Se si utilizzata l'opzione del provider di servizi E9-1-1 su trunk SIP ed è necessario supportare i servizi E9-1-1 da telefoni analogici, sono disponibili due opzioni:

- **Opzione PS-ALI tradizionale** Se si dispone di gateway PSTN locali in ogni sito in cui sono distribuiti telefoni analogici e ogni telefono analogico dispone di un DID, è possibile effettuare il provisioning della posizione del dispositivo analogico direttamente con un provider di servizi PS-ALI (Private Switch/Automatic Location Identification). In questo caso, è possibile configurare criteri vocali Skype for Business appositamente predisposti e assegnarli agli oggetti contatto del dispositivo analogico in modo che le chiamate E9-1-1 provenienti da questi telefoni instradino direttamente attraverso il gateway locale al provider PSTN che servizi il sito (anziché instradare la chiamata a un trunk SIP del provider di servizi E9-1-1). Quando viene effettuata una chiamata di emergenza, un database presso un provider PS-ALI associato al trunk PSTN mappa il DID di ogni telefono analogico a una posizione fisica, quindi fornisce tale posizione al centro PSAP. Questi record devono essere aggiornati presso il provider di servizi PS-ALI ogni volta che i telefoni vengono spostati in posizioni ERL diverse.

- Opzione del provider di servizi **E9-1-1** È possibile registrare i DID dei telefoni analogici e gli ERL corrispondenti con il provider di servizi E9-1-1, se supportato dal provider di servizi E9-1-1. Se il provider riceve una chiamata da Skype for Business Server che non include dati PIDF-LO, il provider può vedere se esiste una corrispondenza del database nel numero DID della parte chiamante. Utilizzando l'elenco di revoche di certificati (ERL) recuperato dal relativo database, il provider può instradare automaticamente la chiamata di emergenza al psAP corretto e il centro psap riceverà il DID del dispositivo analogico e un record ESQK che consente al dispatcher di cercare la posizione del chiamante.

Se si utilizza l'opzione del gateway ELIN ed è necessario supportare i servizi E9-1-1 da telefoni analogici, è possibile eseguire il provisioning della posizione del dispositivo analogico direttamente con il provider di servizi PS-ALI, come descritto in precedenza nella prima opzione.

Dal punto di vista di Skype for Business Server, il processo E9-1-1 può essere suddiviso in due fasi:

- Fase 1: acquisizione di una posizione

- Fase 2: instradamento della chiamata di emergenza a un provider di servizi E9-1-1

In questa sezione viene descritto il funzionamento di queste due fasi.

Se si prevede di configurare l'infrastruttura per il rilevamento automatico della posizione dei client, è innanzitutto necessario decidere quali elementi di rete verranno utilizzati per il mapping tra chiamanti e posizioni. Per informazioni dettagliate sulle opzioni possibili, vedere Definire gli elementi di rete utilizzati per determinare [la posizione in Skype for Business Server.](network-location.md)

## <a name="acquiring-a-location"></a>Acquisizione di una posizione

In una distribuzione di Skype for Business Server E9-1-1, ogni client Skype for Business o Lync Phone Edition connesso internamente acquisisce attivamente la propria posizione. Dopo la registrazione SIP, il client fornisce tutte le informazioni sulla connettività di rete a sua conoscenza in una richiesta di percorso al servizio Informazioni percorso, ovvero un servizio Web supportato da un database SQL Server replicato. Ogni pool di siti centrale dispone di un servizio informazioni percorso, che utilizza le informazioni di rete per eseguire query sui relativi record per una posizione corrispondente. Se è presente una corrispondenza, il servizio informazioni percorso restituisce una posizione al client. Se non viene trovata una corrispondenza, può venire richiesto all'utente di immettere manualmente una posizione (a seconda delle impostazioni dei criteri percorso). I dati sulla posizione vengono trasmessi di nuovo al client in un formato XML basato su standard IETF (Internet Engineering Task Force) denominato PIDF-LO (Presence Information Data Format Location Object).

Il client Skype for Business include i dati PIDF-LO come parte di una chiamata di emergenza e questi dati vengono utilizzati dal provider di servizi E9-1-1 per determinare il CENTRO PSAP appropriato e instradare la chiamata a tale PSAP insieme all'ESQK corretto, che consente al dispatcher PSAP di ottenere la posizione del chiamante.

Il diagramma seguente mostra come un client Skype for Business acquisisce una posizione (ad eccezione del metodo di posizione basato sull'indirizzo MAC del client di terze parti):

![Come il client acquisisce un diagramma percorso](../../media/Plan_LyncServer_E911_LocationAcquisition.jpg)

Per consentire a un client di acquisire una posizione, sono necessari i passaggi seguenti:

1. L'amministratore popola il database del servizio informazioni percorso con la wiremap di rete (tabelle che mappano vari tipi di indirizzi di rete alle posizioni ERL corrispondenti).

2. Se si utilizza un provider di servizi E9-1-1 tramite trunk SIP, l'amministratore convalida le parti dell'indirizzo civico della posizione ERL in base a un database dello stradario generale gestito dal provider di servizi E9-1-1. Se si utilizza una gateway ELIN, l'amministratore verifica che i numeri ELIN vengano caricati dal gestore PSTN nel database ALI (Automatic Location Identification).

3. Durante la registrazione o ogni volta che si verifica una modifica della rete, un client connesso internamente invia al servizio Informazioni percorso una richiesta di posizione contenente gli indirizzi di rete individuati del client.

4. Il servizio informazioni percorso esegue una query sui record pubblicati per trovare una posizione e, se viene trovata una corrispondenza, restituisce l'elenco di revoche di certificati al client in formato PIDF-LO.

## <a name="routing-e9-1-1-calls-using-a-sip-trunk"></a>Routing delle chiamate E9-1-1 tramite un trunk SIP

L'utilizzo di un trunk SIP per la connessione a un provider di servizi E9-1-1 qualificato rappresenta un metodo per la distribuzione del servizio E9-1-1. Per informazioni dettagliate sull'utilizzo di un gateway ELIN per la connessione a un provider di servizi E9-1-1 basato su PSTN (Public Switched Telephone Network), vedere [Routing E9-1-1 Calls by Using an ELIN Gateway](https://technet.microsoft.com/library/5a3997e3-898d-49cb-922a-4184c3373350.aspx).

Il diagramma seguente mostra come una chiamata di emergenza viene instradata da Skype for Business Server al punto di risposta alla sicurezza pubblica (PSAP) quando si utilizza un trunk SIP e un provider di servizi E9-1-1 qualificato.

**Routing delle chiamate al servizio E9-1-1 tramite un trunk SIP**

![Routing delle chiamate di emergenza da Lync Server a PSAP](../../media/Plan_LyncServer_E911_CallRouting.jpg)

Quando viene messa una chiamata di emergenza da un client Skype for Business Server compatibile:

1. Un INVITO SIP che contiene la posizione, il numero di richiamata del chiamante e l'URL di notifica (facoltativo) e il numero di richiamata della conferenza vengono instradati a Skype for Business Server.

2. Skype for Business Server corrisponde al numero di emergenza e instrada la chiamata (in base al valore utilizzo **PSTN** definito nei criteri percorso applicabili) a un Mediation Server e da qui, tramite un trunk SIP al provider di servizi E9-1-1.

3. Il provider di servizi E9-1-1 instrada la chiamata di emergenza al centro di raccolta delle chiamate di emergenza (PSAP, Public Safety Answering Point) appropriato in base alle informazioni sulla posizione fornite nella chiamata. Quando il client include nella chiamata di emergenza una posizione ERL (Emergency Response Location) convalidata, la chiamata viene instradata automaticamente dal provider al centro di raccolta delle chiamate di emergenza appropriato. Se la posizione è stata immessa manualmente dall'utente, il centro ECRC (Emergency Call Response Center) verifica innanzitutto verbalmente l'accuratezza della posizione con il chiamante prima di instradare la chiamata al centro di raccolta delle chiamate di emergenza.

4. Se è stato configurato il criterio percorso per le notifiche, a uno o più responsabili della sicurezza dell'organizzazione viene inviato uno speciale messaggio istantaneo di notifica di emergenza Skype for Business. Questo messaggio viene sempre visualizzato sullo schermo dei responsabili della sicurezza e contiene il nome, il numero di telefono, l'ora e la posizione del chiamante, consentendo al personale di sicurezza di rispondere rapidamente al chiamante di emergenza utilizzando un messaggio istantaneo o una voce.

5. Se i criteri percorso sono stati configurati per la conferenza e il servizio è supportato dal provider di servizi E9-1-1, un desk di sicurezza interno viene aggiunto a una conferenza telefonica con audio unidirezionale o bidirezionale.

6. Se la chiamata viene interrotta prematuramente, il centro di raccolta delle chiamate di emergenza utilizza il numero di richiamata per contattare direttamente il chiamante.

## <a name="routing-e9-1-1-calls-by-using-an-elin-gateway"></a>Routing delle chiamate E9-1-1 tramite un gateway ELIN

Alcuni partner del programma Unified Communications Open Interoperability offrono gateway ELIN (Emergency Location Identification Number) qualificati, che rappresentano un'alternativa a una connessione trunk SIP a un provider di servizi E9-1-1 qualificato. I gateway ELIN supportano la connettività ISDN o CAMA (Centralized Automatic Message Accounting) ai servizi E9-1-1 basati su PSTN (Public Switched Telephone Network). Per informazioni dettagliate sui partner che forniscono gateway ELIN e collegamenti alla documentazione, vedere Infrastruttura qualificata per [Microsoft Lync](https://go.microsoft.com/fwlink/p/?LinkId=248425) e Infrastruttura di telefonia per Skype [for Business.](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)

Come le connessioni trunk SIP ai provider di servizi E9-1-1, i gateway ELIN forniscono anche i mezzi per instradare una chiamata di emergenza al punto psAP (Public Safety Answering Point) più appropriato del chiamante, ma questi gateway utilizzano un ELIN come identificatore di posizione. I numeri ELIN vengono definiti per ogni posizione di risposta alle emergenze (ERL) nell'organizzazione (per informazioni dettagliate, vedere Gestire le posizioni per [i gateway ELIN in Skype for Business Server).](elin-gateways.md)

Quando si utilizza un gateway ELIN per le chiamate di emergenza, si utilizza la stessa infrastruttura E9-1-1 di Skype for Business Server che si utilizzerebbe per una connessione trunk SIP. In altre informazioni, il database del servizio informazioni percorso fornisce la posizione al client Skype for Business e i criteri percorso abilitano la funzionalità e definiscono il routing. Con un gateway ELIN, tuttavia, è necessario aggiungere i numeri ELIN al database del servizio informazioni sulla posizione e fare in modo che il gestore PSTN li carichi nel database ALI (Automatic Location Identification).

Quando un client Skype for Business ottiene la propria posizione dal servizio informazioni sulla posizione, la posizione include l'ELIN. Durante la chiamata di emergenza, il numero ELIN viene incluso nella posizione inviata al gateway ELIN. Il gateway ELIN identifica la chiamata come chiamata di emergenza e scambia il numero del chiamante con il numero ELIN. La chiamata viene quindi instradata dal gateway ELIN a PSTN con il numero ELIN indicato come numero chiamante. Il provider di servizi E9-1-1 PSTN cerca il numero ELIN nel database ALI, che è un database complementare a quello dello stradario generale. La chiamata viene quindi inviata tramite PSTN al centro di raccolta delle chiamate di emergenza (PSAP, Public Safety Answering Point) più appropriato, in base alla ricerca nel database ALI e il centro di raccolta delle chiamate di emergenza invia i soccorsi alla posizione del chiamante in base alla ricerca nel database ALI. Il numero chiamante viene memorizzato nella cache nel gateway ELIN per un periodo di tempo predefinito per le richiamate. Durante la richiamata, il centro di raccolta delle chiamate di emergenza raggiunge il gateway ELIN, che scambia il numero ELIN con il numero DID (Direct Inward Dialing) del chiamante.

I gateway ELIN supportano chiamate di emergenza solo dall'interno della rete dell'organizzazione. Non sono supportate chiamate di emergenza effettuate dall'esterno della rete.

> [!NOTE]
> Per informazioni dettagliate sull'utilizzo di una connessione trunk SIP per le chiamate di emergenza, vedere [Routing E9-1-1 Calls by Using a SIP Trunk](https://technet.microsoft.com/library/157753c3-fe74-4e2c-81da-ee06911d4cc2.aspx).

Il diagramma seguente mostra come una chiamata di emergenza viene instradata da Skype for Business Server al CENTRO PSAP quando si utilizza un gateway ELIN.

**Routing delle chiamate E9-1-1 con un gateway ELIN**

![Mostra il modo in cui una chiamata ai servizi di emergenza passa attraverso il Mediation Server e quindi al provider dei servizi di emergenza. Dopo questa operazione, può essere facoltativamente inviata una messaggistica istantanea alla sicurezza sul posto e/o una chiamata al chiamante originale.](../../media/Plan_LyncServer_E911_ELINCallRouting.jpg)

1. Un SIP INVITE contenente la posizione, il numero di richiamata del chiamante e l'URL di notifica (facoltativo) e il numero di richiamata della conferenza vengono instradati a Skype for Business Server.

2. Skype for Business Server corrisponde al numero di emergenza e quindi instrada la chiamata (in base al valore utilizzo **PSTN** definito nei criteri percorso applicabili) a un Mediation Server e da qui a un gateway ELIN.

3. Il gateway ELIN instrada la chiamata su un trunk ISDN o CAMA alla rete PSTN.

4. La rete PSTN identifica quindi la chiamata come chiamata di emergenza e la instrada a un router selettivo E9-1-1 nella rete. Tale router selettivo E9-1-1 cerca il numero del chiamante nel database ALI per ottenere la posizione geografica. Il router selettivo E9-1-1 invia la chiamata al punto PSAP più appropriato in base alle informazioni sulla posizione recuperate dal database ALI.

5. Se è stato configurato il criterio percorso per le notifiche, a uno o più responsabili della sicurezza dell'organizzazione viene inviato uno speciale messaggio istantaneo di notifica di emergenza Skype for Business. Questo messaggio viene sempre visualizzato sullo schermo dei responsabili della sicurezza e contiene il nome, il numero di telefono, l'ora e la posizione del chiamante, consentendo al personale di sicurezza di rispondere rapidamente al chiamante di emergenza utilizzando un messaggio istantaneo o una voce.

6. Se la chiamata viene interrotta prematuramente, il centro di raccolta delle chiamate di emergenza utilizza il numero ELIN per contattare direttamente il chiamante. Il gateway ELIN scambia i numero ELIN con il numero DID del chiamante.


