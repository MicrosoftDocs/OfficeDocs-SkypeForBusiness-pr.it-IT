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
description: Informazioni sui servizi Enhanced 9-1-1 (E9-1-1) in Skype for Business Server VoIP aziendale, tra cui l'acquisizione delle posizioni e il routing delle chiamate.
ms.openlocfilehash: e8eb805a4e4d55f08a4c6aec1a57618c74bcfa02
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825766"
---
# <a name="plan-for-emergency-services-in-skype-for-business-server"></a>Pianificare i servizi di emergenza in Skype for Business Server

Informazioni sui servizi Enhanced 9-1-1 (E9-1-1) in Skype for Business Server VoIP aziendale, tra cui l'acquisizione delle posizioni e il routing delle chiamate.

Skype for Business Server supporta i servizi avanzati 9-1-1 (E9-1-1) all'interno degli Stati Uniti nell'ambito di una distribuzione di VoIP aziendale. Tale funzionalità associa una chiamata a un numero di emergenza a una posizione ERL (Emergency Response Location) costituita da una via e un numero civico e da altre informazioni più specifiche, ad esempio il numero del piano, per le chiamate provenienti da edifici per uso ufficio e da altre strutture con più locatari. Utilizzando la posizione ERL fornita, un centro di raccolta delle chiamate di emergenza (PSAP, Public Safety Answering Point) può fornire immediatamente i servizi di emergenza al chiamante in difficoltà con un minore rischio di indirizzare inavvertitamente l'operatore a una posizione errata o ambigua.

> [!NOTE]
> Skype for Business Server ora supporta la configurazione di più numeri di emergenza per un client. Per ulteriori informazioni, vedere [Plan for multiple Emergency Numbers in Skype for Business Server](multiple-emergency-numbers.md).

> [!NOTE]
> In Skype for Business Server sono disponibili tre funzionalità di VoIP aziendale avanzate: controllo di ammissione di chiamata, servizi di emergenza (E9-1-1) e bypass multimediale. Per una panoramica delle informazioni di pianificazione comuni a tutte e tre queste caratteristiche, vedere [impostazioni di rete per le funzionalità di VoIP aziendale avanzate in Skype for Business Server](network-settings-for-advanced-features.md).

Skype for Business Server supporta la chiamata avanzata 9-1-1 (E9-1-1) dai client Skype for business e dai dispositivi Lync Phone Edition. Quando si configura Skype for Business Server per il servizio E9-1-1, le chiamate di emergenza effettuate da Skype for business o Lync Phone Edition includono le informazioni di Emergency Response Location (elfi) dal database dei servizi di informazioni percorso. Le informazioni ERL includono gli indirizzi civici (ovvero la via) e altri dati che consentono di individuare la posizione con maggiore precisione in edifici di uffici e altre strutture con più occupanti. Quando un utente effettua una chiamata di emergenza, Skype for Business Server instrada l'audio della chiamata, insieme al percorso e alle informazioni di richiamata, tramite un Mediation Server a un provider di servizi E9-1-1. Tale provider utilizza l'indirizzo civico del chiamante per instradare la chiamata al centro di raccolta delle chiamate di emergenza (PSAP) responsabile per l'area in cui si trova il chiamante, quindi invia la chiave di query del servizio di emergenza (ESQK, Emergency Service Query Key) che verrà utilizzata dal centro PSAP per cercare le informazioni ERL del chiamante.

Skype for Business Server supporta due metodi per il routing delle chiamate di emergenza a un provider di servizi E9-1-1:

- Una connessione trunk SIP (Session Initiation Protocol) a un provider di servizi E9-1-1 qualificato

- Un gateway ELIN (Emergency Location Identification Number) a un provider di servizi E9-1-1 basato su PSTN (Public Switched Telephone Network)

Quando si utilizza un provider di servizi E9-1-1 trunk SIP, è possibile aggiungere posizioni ERL al database del servizio informazioni percorso e quindi convalidare le posizioni in base a una guida (allo stradario generale) gestita dal provider di servizi E9-1-1. Se un provider di servizi E9-1-1 riceve una chiamata che non dispone di informazioni sulla posizione o che ha una posizione non convalidata rispetto a allo stradario generale, il provider di servizi E9-1-1 instrada la chiamata a un centro di risposta alle chiamate di emergenza nazionale/regionale (ECRC), che è dotato di personale specializzato che ottiene verbalmente la posizione del chiamante, se possibile, e instrada manualmente la chiamata al PSAP appropriato. Alcuni provider di servizi E9-1-1 su trunk SIP inoltre forniscono ai clienti un numero DID (Direct Inward Dialing) PSTN per il centro ECRC, offrendo un mezzo alternativo per il routing delle chiamate 9-1-1 in caso di malfunzionamento del trunk SIP per un motivo qualsiasi.

A differenza del TDM (Time Division Multiplexing) e dei telefoni PBX (Private Branch Exchange) basati su IP, che dispongono di posizioni fisse, un endpoint di Skype for business può essere molto mobile. Quando si distribuisce la funzionalità E9-1-1, Skype for Business Server aiuta a garantire che, indipendentemente dal luogo in cui si trova un chiamante, la chiamata di emergenza possa essere instradata al PSAP che serve la posizione del chiamante. Ad esempio, se la sede principale di un utente si trova a Redmond, Washington, ma l'utente effettua una chiamata di emergenza da un computer in una succursale di Wichita, Kansas, il trunk SIP o il provider di servizi E9-1-1 Basato su PSTN instraderà la chiamata al PSAP di Wichita, non al PSAP di Redmond.

Quando si utilizza un gateway ELIN, è inoltre possibile aggiungere posizioni ERL al database del servizio informazioni percorso, ma è anche necessario includere un numero ELIN per ogni percorso. Il numero ELIN diventa il numero chiamante durante la chiamata di emergenza. È quindi necessario verificare che la portante PSTN carichi i numeri ELIN nel database ALI (Automatic Location Identification).

> [!NOTE]
> I dispositivi analogici connessi a Skype for business non sono in grado di ricevere informazioni sul percorso dal servizio informazioni percorso o di trasmissione al provider di servizi E9-1-1.

 Se si utilizzata l'opzione del provider di servizi E9-1-1 su trunk SIP ed è necessario supportare i servizi E9-1-1 da telefoni analogici, sono disponibili due opzioni:

- **Opzione tradizionale PS-Ali** Se si dispone di gateway PSTN locali in ogni sito in cui vengono distribuiti telefoni analogici e ogni telefono analogico ha un DID, è possibile eseguire il provisioning della posizione del dispositivo analogico direttamente con un provider di servizi switch privato/rilevamento automatico località (PS-ALI). In questo caso, è possibile configurare i criteri vocali Skype for business appositamente creati e assegnarli agli oggetti contatto del dispositivo analogico in modo che le chiamate E9-1-1 provenienti da tali telefoni si instradano direttamente tramite il gateway locale al provider PSTN che effettua il servizio (invece di instradare la chiamata a un trunk SIP del provider di servizi E9-1-1). Quando viene effettuata una chiamata di emergenza, un database presso un provider PS-ALI associato al trunk PSTN mappa il DID di ogni telefono analogico a una posizione fisica, quindi fornisce tale posizione al centro PSAP. Questi record devono essere aggiornati presso il provider di servizi PS-ALI ogni volta che i telefoni vengono spostati in posizioni ERL diverse.

- **Opzione del provider di servizi E9-1-1** È possibile registrare le DIDs di telefonia analogico e le corrispondenti posizioni ERL con il provider di servizi E9-1-1, se supportato dal provider di servizi E9-1-1. Se il provider riceve una chiamata da Skype for Business Server che non include i dati di PIDF-LO, il provider può vedere se esiste una corrispondenza di database sul numero DID della parte chiamante. Utilizzando gli elfi recuperati dal relativo database, il provider può instradare automaticamente la chiamata di emergenza alla PSAP corretta e il PSAP riceverà l'DID del dispositivo analogico e un record di ESQK che consentirà al dispatcher di cercare la posizione del chiamante.

Se si utilizza l'opzione del gateway ELIN ed è necessario supportare i servizi E9-1-1 da telefoni analogici, è possibile eseguire il provisioning della posizione del dispositivo analogico direttamente con il provider di servizi PS-ALI, come descritto in precedenza nella prima opzione.

Da un punto di vista di Skype for Business Server, il processo di E9-1-1 può essere suddiviso in due fasi:

- Fase 1: acquisizione di una posizione

- Fase 2: instradamento della chiamata di emergenza a un provider di servizi E9-1-1

In questa sezione viene descritto il funzionamento di queste due fasi.

Se si prevede di configurare l'infrastruttura per il rilevamento automatico della posizione dei client, è innanzitutto necessario decidere quali elementi di rete verranno utilizzati per il mapping tra chiamanti e posizioni. Per informazioni dettagliate sulle possibili opzioni, vedere [definire gli elementi di rete utilizzati per determinare la posizione in Skype for Business Server](network-location.md).

## <a name="acquiring-a-location"></a>Acquisizione di una posizione

In una distribuzione di E9-1-1 di Skype for Business Server, ogni client di Skype for business o Lync Phone Edition connesso internamente ha acquisito la propria posizione. Dopo la registrazione SIP, il client fornisce tutte le informazioni di connettività di rete che conosce se stesso in una richiesta di percorso al servizio informazioni percorso, che è un servizio Web di cui è stato eseguito il backup da un database di SQL Server replicato. Ogni pool di sito centrale dispone di un servizio informazioni percorso, che utilizza le informazioni di rete per eseguire una query sui record per un percorso corrispondente. Se esiste una corrispondenza, il servizio informazioni percorso restituirà una posizione al client. Se non viene trovata una corrispondenza, può venire richiesto all'utente di immettere manualmente una posizione (a seconda delle impostazioni dei criteri percorso). I dati sulla posizione vengono trasmessi di nuovo al client in un formato XML basato su standard IETF (Internet Engineering Task Force) denominato PIDF-LO (Presence Information Data Format Location Object).

Il client Skype for business include i dati di PIDF-LO nell'ambito di una chiamata di emergenza e questi dati vengono utilizzati dal provider di servizi E9-1-1 per determinare le PSAP appropriate e instradare la chiamata a tale PSAP insieme al ESQK corretto, che consente al dispatcher di PSAP di ottenere la posizione del chiamante.

Nel diagramma seguente viene illustrato il modo in cui un client Skype for business acquisisce una posizione (ad eccezione del metodo percorso basato sull'indirizzo MAC del client di terze parti):

![Modalità di acquisizione del diagramma di un percorso da parte del client](../../media/Plan_LyncServer_E911_LocationAcquisition.jpg)

Per consentire a un client di acquisire una posizione, sono necessari i passaggi seguenti:

1. L'amministratore compila il database del servizio informazioni percorso con la rete wiremap (tabelle che mappano diversi tipi di indirizzi di rete ai corrispondenti percorsi di risposta alle emergenze (posizioni ERL)).

2. Se si utilizza un provider di servizi E9-1-1 tramite trunk SIP, l'amministratore convalida le parti dell'indirizzo civico della posizione ERL in base a un database dello stradario generale gestito dal provider di servizi E9-1-1. Se si utilizza una gateway ELIN, l'amministratore verifica che i numeri ELIN vengano caricati dal gestore PSTN nel database ALI (Automatic Location Identification).

3. Durante la registrazione o ogni volta che si verifica una modifica di rete, un client connesso internamente invia una richiesta di posizione contenente gli indirizzi di rete individuati del client al servizio informazioni percorso.

4. Il servizio informazioni percorso esegue una query sui record pubblicati per una posizione e, se viene trovata una corrispondenza, restituisce gli oggetti di tipo PIDF-LO per il client in formato.

## <a name="routing-e9-1-1-calls-using-a-sip-trunk"></a>Routing delle chiamate al servizio E9-1-1 tramite un trunk SIP

L'utilizzo di un trunk SIP per la connessione a un provider di servizi E9-1-1 qualificato rappresenta un metodo per la distribuzione del servizio E9-1-1. Per informazioni dettagliate sull'utilizzo di un gateway ELIN per la connessione a un provider di servizi E9-1-1 basato su PSTN (Public Switched Telephone Network), vedere [Routing E9-1-1 Calls by Using an ELIN Gateway](https://technet.microsoft.com/library/5a3997e3-898d-49cb-922a-4184c3373350.aspx).

Nel diagramma seguente viene illustrato in che modo viene instradata una chiamata di emergenza da Skype for Business Server al punto di ricezione della sicurezza pubblica (PSAP) quando si utilizza un trunk SIP e un provider di servizi E9-1-1 qualificato.

**Routing delle chiamate al servizio E9-1-1 tramite un trunk SIP**

![Routing delle chiamate di emergenza da Lync Server a PSAP](../../media/Plan_LyncServer_E911_CallRouting.jpg)

Quando viene effettuata una chiamata di emergenza da un client compatibile con Skype for Business Server:

1. Un invito SIP che contiene la posizione, il numero di richiamata del chiamante e l'URL di notifica (facoltativo) e il numero di richiamata della conferenza sono instradati a Skype for Business Server.

2. Skype for Business Server corrisponde al numero di emergenza e instrada la chiamata (in base al valore di **utilizzo PSTN** definito nei criteri di percorso applicabili) a un Mediation Server e, da qui, tramite un trunk SIP al provider di servizi E9-1-1.

3. Il provider di servizi E9-1-1 instrada la chiamata di emergenza al centro di raccolta delle chiamate di emergenza (PSAP, Public Safety Answering Point) appropriato in base alle informazioni sulla posizione fornite nella chiamata. Quando il client include nella chiamata di emergenza una posizione ERL (Emergency Response Location) convalidata, la chiamata viene instradata automaticamente dal provider al centro di raccolta delle chiamate di emergenza appropriato. Se la posizione è stata immessa manualmente dall'utente, il centro ECRC (Emergency Call Response Center) verifica innanzitutto verbalmente l'accuratezza della posizione con il chiamante prima di instradare la chiamata al centro di raccolta delle chiamate di emergenza.

4. Se i criteri percorso sono stati configurati per le notifiche, uno o più agenti di sicurezza dell'organizzazione vengono inviati a un messaggio istantaneo di notifica di emergenza Skype for business speciale. Questo messaggio viene sempre visualizzato nelle schermate degli addetti alla sicurezza e contiene il nome, il numero di telefono, l'ora e il percorso del chiamante, consentendo al personale di sicurezza di rispondere rapidamente al chiamante di emergenza utilizzando un messaggio istantaneo o una voce.

5. Se i criteri percorso sono stati configurati per la conferenza e il servizio è supportato dal provider di servizi E9-1-1, un desk di sicurezza interno viene aggiunto a una conferenza telefonica con audio unidirezionale o bidirezionale.

6. Se la chiamata viene interrotta prematuramente, il centro di raccolta delle chiamate di emergenza utilizza il numero di richiamata per contattare direttamente il chiamante.

## <a name="routing-e9-1-1-calls-by-using-an-elin-gateway"></a>Routing delle chiamate al servizio E9-1-1 tramite un gateway ELIN

Alcuni partner del programma Unified Communications Open Interoperability offrono gateway ELIN (Emergency Location Identification Number) qualificati, che rappresentano un'alternativa a una connessione trunk SIP a un provider di servizi E9-1-1 qualificato. I gateway ELIN supportano la connettività ISDN o CAMA (Centralized Automatic Message Accounting) ai servizi E9-1-1 basati su PSTN (Public Switched Telephone Network). Per informazioni dettagliate sui partner che forniscono gateway ELIN e collegamenti alla relativa documentazione, vedere [Infrastructure qualified for Microsoft Lync](https://go.microsoft.com/fwlink/p/?LinkId=248425) and [Telephony Infrastructure for Skype for business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).

Analogamente alle connessioni trunk SIP ai provider di servizi E9-1-1, i gateway ELIN offrono anche i mezzi per instradare una chiamata di emergenza al punto di risposta di sicurezza pubblica più appropriato del chiamante (PSAP), ma questi gateway utilizzano un ELIN come identificatore di percorso. È possibile definire gli ELIN per ogni posizione di risposta di emergenza (elfi) dell'organizzazione (per informazioni dettagliate, vedere [gestire percorsi per i gateway ELIN in Skype for Business Server](elin-gateways.md)).

Quando si utilizza un gateway ELIN per le chiamate di emergenza, è possibile utilizzare la stessa infrastruttura E9-1-1 di Skype for Business Server che si desidera utilizzare per una connessione trunk SIP. Questo è il database del servizio informazioni percorso che fornisce il percorso al client Skype for business e il criterio percorso attiva la caratteristica e definisce il routing. Con un gateway ELIN, tuttavia, è necessario aggiungere i numeri ELIN al database del servizio informazioni percorso e fare in modo che il gestore PSTN li carichi nel database ALI (Automatic Location Identification).

Quando un client Skype for business ottiene la propria posizione dal servizio informazioni percorso, il percorso include il valore ELIN. Durante la chiamata di emergenza, il numero ELIN viene incluso nella posizione inviata al gateway ELIN. Il gateway ELIN identifica la chiamata come chiamata di emergenza e scambia il numero del chiamante con il numero ELIN. La chiamata viene quindi instradata dal gateway ELIN a PSTN con il numero ELIN indicato come numero chiamante. Il provider di servizi E9-1-1 PSTN cerca il numero ELIN nel database ALI, che è un database complementare a quello dello stradario generale. La chiamata viene quindi inviata tramite PSTN al centro di raccolta delle chiamate di emergenza (PSAP, Public Safety Answering Point) più appropriato, in base alla ricerca nel database ALI e il centro di raccolta delle chiamate di emergenza invia i soccorsi alla posizione del chiamante in base alla ricerca nel database ALI. Il numero chiamante viene memorizzato nella cache nel gateway ELIN per un periodo di tempo predefinito per le richiamate. Durante la richiamata, il centro di raccolta delle chiamate di emergenza raggiunge il gateway ELIN, che scambia il numero ELIN con il numero DID (Direct Inward Dialing) del chiamante.

I gateway ELIN supportano chiamate di emergenza solo dall'interno della rete dell'organizzazione. Non sono supportate chiamate di emergenza effettuate dall'esterno della rete.

> [!NOTE]
> Per informazioni dettagliate sull'utilizzo di una connessione trunk SIP per le chiamate di emergenza, vedere [Routing E9-1-1 Calls by Using a SIP Trunk](https://technet.microsoft.com/library/157753c3-fe74-4e2c-81da-ee06911d4cc2.aspx).

Nel diagramma seguente viene illustrato in che modo una chiamata di emergenza viene instradata da Skype for Business Server a PSAP quando si utilizza un gateway ELIN.

**Routing delle chiamate E9-1-1 con un gateway ELIN**

![Viene illustrato il modo in cui una chiamata ai servizi di emergenza attraversa il Mediation Server e quindi al provider di servizi di emergenza. Dopo questo può essere facoltativamente un messaggio di posta elettronica inviato alla sicurezza del sito e/o una chiamata di nuovo al chiamante originale.](../../media/Plan_LyncServer_E911_ELINCallRouting.jpg)

1. Un SIP INVITE contenente la posizione, il numero di callback del chiamante e l'URL di notifica (facoltativo) e il numero di richiamata della conferenza sono instradati a Skype for Business Server.

2. Skype for Business Server corrisponde al numero di emergenza e quindi instrada la chiamata (in base al valore di **utilizzo PSTN** definito nei criteri di percorso applicabili) a un Mediation Server e da qui a un gateway ELIN.

3. Il gateway ELIN instrada la chiamata su un trunk ISDN o CAMA alla rete PSTN.

4. La rete PSTN identifica quindi la chiamata come chiamata di emergenza e la instrada a un router selettivo E9-1-1 nella rete. Tale router selettivo E9-1-1 cerca il numero del chiamante nel database ALI per ottenere la posizione geografica. Il router selettivo E9-1-1 invia la chiamata al punto PSAP più appropriato in base alle informazioni sulla posizione recuperate dal database ALI.

5. Se i criteri percorso sono stati configurati per le notifiche, uno o più agenti di sicurezza dell'organizzazione vengono inviati a un messaggio istantaneo di notifica di emergenza Skype for business speciale. Questo messaggio viene sempre visualizzato nelle schermate degli addetti alla sicurezza e contiene il nome, il numero di telefono, l'ora e il percorso del chiamante, consentendo al personale di sicurezza di rispondere rapidamente al chiamante di emergenza utilizzando un messaggio istantaneo o una voce.

6. Se la chiamata viene interrotta prematuramente, il centro di raccolta delle chiamate di emergenza utilizza il numero ELIN per contattare direttamente il chiamante. Il gateway ELIN scambia i numero ELIN con il numero DID del chiamante.


