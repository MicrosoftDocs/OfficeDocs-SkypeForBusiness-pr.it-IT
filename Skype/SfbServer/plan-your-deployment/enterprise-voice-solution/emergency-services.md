---
title: Pianificare i servizi di emergenza in Skype for Business Server
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
ms.assetid: ed843ed7-371f-46cc-969a-f8062c06fc55
description: Informazioni sui servizi avanzati di 9-1-1 (E9-1-1) in Skype for Business Server VoIP aziendale, incluso l'acquisizione della posizione e il routing delle chiamate.
ms.openlocfilehash: 20d1a258b022b8369f59aaa74a2b95de45f931e2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187703"
---
# <a name="plan-for-emergency-services-in-skype-for-business-server"></a>Pianificare i servizi di emergenza in Skype for Business Server

Informazioni sui servizi avanzati di 9-1-1 (E9-1-1) in Skype for Business Server VoIP aziendale, incluso l'acquisizione della posizione e il routing delle chiamate.

Skype for Business Server supporta i servizi avanzati di 9-1-1 (E9-1-1) all'interno degli Stati Uniti nell'ambito di una distribuzione di VoIP aziendale. E9-1-1 è una funzionalità di invio di emergenza che associa una chiamata di 9-1-1 a un percorso di risposta di emergenza (elfi) costituito da indirizzi civici (ovvero Street) e altre informazioni sulla posizione più specifiche, ad esempio i numeri di piano, per le chiamate da edifici di Office e altre strutture multitenant. Usando gli elfi forniti, un PSAP (Public Safety Answering Point) può immediatamente inviare i primi risponditori al chiamante in difficoltà con un rischio ridotto di indirizzare inavvertitamente il risponditore a una posizione non corretta o ambigua.

> [!NOTE]
> Skype for Business Server ora supporta la configurazione di più numeri di emergenza per un client. Per altre informazioni, vedere [pianificare più numeri di emergenza in Skype for Business Server](multiple-emergency-numbers.md).

> [!NOTE]
> Skype for Business Server include tre funzionalità vocali avanzate: controllo ammissione chiamata, servizi di emergenza (E9-1-1) e bypass multimediale. Per una panoramica delle informazioni sulla pianificazione comuni a tutte e tre queste caratteristiche, vedere [impostazioni di rete per le funzionalità vocali avanzate di VoIP aziendale in Skype for Business Server](network-settings-for-advanced-features.md).

Skype for Business Server supporta le chiamate avanzate di 9-1-1 (E9-1-1) dai client Skype for business e dai dispositivi Lync Phone Edition. Quando si configura Skype for Business Server per E9-1-1, le chiamate di emergenza effettuate da Skype for business o Lync Phone Edition includono le informazioni sulla posizione di risposta alle emergenze dal database del servizio informazioni sulla posizione. Posizioni ERL è costituito da indirizzi civici (ovvero Street) e altre informazioni utili per identificare una posizione più precisa negli edifici di Office e in altre strutture multitenant. Quando un utente effettua una chiamata di emergenza, Skype for Business Server instrada l'audio della chiamata, insieme alla posizione e alle informazioni di callback, tramite un Mediation Server a un provider di servizi E9-1-1. Il provider di servizi E9-1-1 USA l'indirizzo civico del chiamante per instradare la chiamata al punto di PSAP (Public Safety Answering Point) che serve la posizione del chiamante e invia lungo una chiave di query del servizio di emergenza (ESQK) che PSAP USA per cercare gli Elfi del chiamante.

Skype for Business Server supporta due metodi per il routing delle chiamate di emergenza a un provider di servizi E9-1-1:

- Connessione trunk SIP (Session Initiation Protocol) a un provider di servizi E9-1-1 qualificato

- Un gateway ELIN (Emergency Location Identification Number) a un provider di servizi E9-1-1 Basato su PSTN (Public Switched Telephone)

Quando si usa un provider di servizi E9-1-1 trunk SIP, è possibile aggiungere posizioni ERL al database del servizio informazioni sulla posizione e quindi convalidare le posizioni in base a una guida all'indirizzo Master Street (stradario) gestita dal provider di servizi E9-1-1. Se un provider di servizi E9-1-1 riceve una chiamata che non ha informazioni sulla posizione o ha una posizione che non è stata convalidata rispetto a stradario, il provider di servizi E9-1-1 instrada la chiamata a un centro di risposta alle chiamate di emergenza nazionale/regionale (ECRC), che è personale qualificato con personale specializzato che ottiene verbalmente la posizione del chiamante, se possibile, e instrada manualmente la chiamata al PSAP appropriato. Alcuni provider di servizi E9-1-1 del trunk SIP forniscono anche ai clienti un numero di chiamate PSTN Direct inwarding (DID) per il ECRC, che fornisce un mezzo alternativo per il routing delle telefonate di 9-1-1, se il trunk SIP non riesce per qualsiasi motivo.

A differenza del TDM (Time Division Multiplexing) e dei telefoni PBX (Private Branch Exchange) basati su IP, che hanno posizioni fisse, un endpoint di Skype for business può essere molto mobile. Quando si distribuisce la funzionalità E9-1-1, Skype for Business Server garantisce che non importa dove si trova un chiamante, la chiamata di emergenza può essere instradata al PSAP che serve la posizione del chiamante. Ad esempio, se l'ufficio principale di un utente si trova a Redmond, Washington, ma l'utente inserisce una chiamata di emergenza da un computer in una filiale di Wichita, Kansas, il trunk SIP o il provider di servizi E9-1-1 Basato su PSTN instradano la chiamata a PSAP in Wichita , non al PSAP di Redmond.

Quando si usa un gateway ELIN, si aggiunge anche posizioni ERL al database del servizio informazioni sulla posizione, ma si include anche un numero ELIN per ogni posizione. Il numero ELIN diventa il numero delle chiamate di emergenza durante la chiamata di emergenza. Devi quindi verificare che il gestore PSTN carichi i dati ELIN nel database ALI (Automatic Location Identification).

> [!NOTE]
> I dispositivi analogici connessi a Skype for business non possono ricevere informazioni sulla posizione dal servizio informazioni sulla posizione o trasmettere il percorso al provider di servizi E9-1-1.

 Se si usa l'opzione del provider di servizi E9-1-1 SIP trunk ed è necessario supportare E9-1-1 da telefoni analogici, sono disponibili due opzioni:

- **Opzione PS-Ali tradizionale** Se si hanno gateway PSTN locali in ogni sito in cui sono distribuiti telefoni analogici e ogni telefono analogico ha un DID, è possibile eseguire il provisioning della posizione del dispositivo analogico direttamente con un provider di servizi di switch privato/identificazione automatica della posizione (PS-ALI). In questo caso, è possibile configurare i criteri vocali Skype for business appositamente creati e assegnarli agli oggetti contatto del dispositivo analogico in modo che le chiamate E9-1-1 da questi telefoni vengano indirizzate direttamente attraverso il gateway locale al provider PSTN che assiste il sito (invece di routing della chiamata a un trunk SIP del provider di servizi E9-1-1. Quando viene inserita una chiamata di emergenza, un database di un provider PS-ALI associato al trunk PSTN esegue il mapping dell'DID di ogni telefono analogico in una posizione fisica e fornisce questa posizione al PSAP. Questi record devono essere aggiornati con il provider di servizi PS-ALI ogni volta che i telefoni vengono spostati in posizioni ERL diversi.

- **Opzione provider di servizi E9-1-1** È possibile registrare il telefono analogico DIDs e la relativa posizioni ERL con il provider di servizi E9-1-1, se supportato dal provider di servizi E9-1-1. Se il provider riceve una chiamata da Skype for Business Server che non include i dati di PIDF-LO, il provider può verificare se esiste una corrispondenza di database nel numero DID della parte chiamante. Usando gli elfi recuperati dal relativo database, il provider può instradare automaticamente la chiamata di emergenza al PSAP corretto e PSAP riceverà l'DID del dispositivo analogico e un record ESQK che consente al dispatcher di cercare la posizione del chiamante.

Se si usa l'opzione gateway ELIN ed è necessario supportare E9-1-1 da telefoni analogici, è possibile eseguire il provisioning della posizione del dispositivo analogico direttamente con il provider di servizi PS-ALI, come descritto nella prima opzione precedente.

Da una prospettiva di Skype for Business Server, il processo E9-1-1 può essere separato in due fasi:

- Fase 1: acquisizione di una posizione

- Fase 2: routing della chiamata di emergenza a un provider di servizi E9-1-1

Questa sezione descrive il funzionamento di queste fasi.

Se si prevede di configurare l'infrastruttura per rilevare automaticamente la posizione del client, è prima di tutto necessario decidere quali elementi di rete verranno usati per eseguire il mapping dei chiamanti alle posizioni. Per informazioni dettagliate sulle possibili opzioni, vedere [definire gli elementi di rete usati per determinare la posizione in Skype for Business Server](network-location.md).

## <a name="acquiring-a-location"></a>Acquisizione di una posizione

In una distribuzione di E9-1-1 di Skype for Business Server, ogni client Skype for business o Lync Phone Edition connesso internamente acquisisce la propria posizione. Dopo la registrazione SIP, il client fornisce tutte le informazioni di connettività di rete che conosce da sola in una richiesta di posizione al servizio informazioni sulla posizione, un servizio Web supportato da un database di SQL Server replicato. Ogni pool di sito centrale include un servizio di informazioni sulla posizione, che usa le informazioni di rete per eseguire query sui record per una posizione corrispondente. Se c'è una corrispondenza, il servizio informazioni sulla posizione restituisce un percorso al client. Se non è presente una corrispondenza, all'utente potrebbe essere richiesto di immettere manualmente una posizione (a seconda delle impostazioni dei criteri di posizione). I dati della posizione vengono trasmessi al client in un formato XML standardizzato di Internet Engineering Task Force (IETF), denominato oggetto location Data Format Information (PIDF-LO).

Il client Skype for business include i dati di PIDF-LO nell'ambito di una chiamata di emergenza e questi dati vengono usati dal provider di servizi E9-1-1 per determinare la PSAP appropriata e instradare la chiamata a tale PSAP insieme al ESQK corretto, che consente al dispatcher di PSAP di ottenere la posizione del chiamante.

Il diagramma seguente mostra il modo in cui un client Skype for business acquisisce una posizione (ad eccezione del metodo di posizione basato su indirizzo MAC del client di terze parti):

![Diagramma della modalità con cui il client acquisisce una posizione](../../media/Plan_LyncServer_E911_LocationAcquisition.jpg)

Affinché un client acquisisca una posizione, è necessario eseguire la procedura seguente:

1. L'amministratore compila il database del servizio informazioni sulla posizione con il wiremap di rete (tabelle che mappano vari tipi di indirizzi di rete ai corrispondenti percorsi di risposta di emergenza (posizioni ERL)).

2. Se si usa un provider di servizi E9-1-1 trunk SIP, l'amministratore convalida le parti degli indirizzi civici di posizioni ERL in base a un database di stradario (Master Street Address Guide) gestito dal provider di servizi E9-1-1. Se si usa un gateway ELIN, l'amministratore garantisce che il gestore PSTN carichi i numeri ELIN nel database ALI (Automatic Location Identification).

3. Durante la registrazione o ogni volta che si verifica un cambiamento di rete, un client connesso internamente invia una richiesta di posizione che contiene gli indirizzi di rete individuati del client al servizio informazioni sulla posizione.

4. Il servizio informazioni sulla posizione esegue una query sui record pubblicati per una posizione e, se viene trovata una corrispondenza, restituisce gli elfi al client in formato PIDF-LO.

## <a name="routing-e9-1-1-calls-using-a-sip-trunk"></a>Routing delle chiamate E9-1-1 tramite trunk SIP

L'uso di un trunk SIP per connettersi a un provider di servizi E9-1-1 qualificato è un modo in cui è possibile distribuire E9-1-1. Per informazioni dettagliate sull'uso di un gateway ELIN per la connessione a un provider di servizi E9-1-1 Basato su PSTN (Public Switched Telephone Network), vedere [routing delle chiamate di E9-1-1 tramite un gateway ELIN](https://technet.microsoft.com/library/5a3997e3-898d-49cb-922a-4184c3373350.aspx).

Il diagramma seguente mostra il modo in cui viene instradata una chiamata di emergenza da Skype for Business Server al punto di PSAP (Public Safety Answering Point) quando si usa un trunk SIP e un provider di servizi E9-1-1 qualificato.

**Routing di chiamate E9-1-1 tramite trunk SIP**

![Routing delle chiamate di emergenza da Lync Server a PSAP](../../media/Plan_LyncServer_E911_CallRouting.jpg)

Quando viene inserita una chiamata di emergenza da un client Skype for Business Server compatibile:

1. Un invito SIP che contiene la posizione, il numero di callback del chiamante e l'URL di notifica (facoltativo) e il numero di callback della conferenza vengono instradati a Skype for Business Server.

2. Skype for Business Server corrisponde al numero di emergenza e instrada la chiamata (in base al valore di **utilizzo PSTN** definito nel criterio di posizione applicabile) a un Mediation Server e da lì, tramite un trunk SIP al provider di servizi E9-1-1.

3. Il provider di servizi E9-1-1 instrada la chiamata di emergenza alla PSAP corretta in base alla posizione fornita con la chiamata. Quando il client include un percorso di risposta di emergenza convalidato con la chiamata di emergenza, il provider instrada automaticamente la chiamata al PSAP appropriato. Se la posizione è stata immessa manualmente dall'utente, il centro risposte per le chiamate di emergenza (ECRC) verifica verbalmente la precisione della posizione con il chiamante prima di instradare la chiamata di emergenza al PSAP.

4. Se sono stati configurati i criteri di posizione per le notifiche, uno o più agenti di sicurezza dell'organizzazione riceveranno un messaggio istantaneo speciale per la notifica di emergenza Skype for business. Questo messaggio compare sempre nella schermata degli addetti alla sicurezza e contiene il nome, il numero di telefono, l'ora e la posizione del chiamante, che consente al personale di sicurezza di rispondere rapidamente al chiamante di emergenza usando un messaggio istantaneo o una voce.

5. Se sono stati configurati i criteri di posizione per le conferenze ed è supportato dal provider di servizi E9-1-1, è possibile partecipare a una conferenza di sicurezza interna alla chiamata con audio unidirezionale o audio bidirezionale.

6. Se la chiamata viene interrotta prematuramente, PSAP usa il numero di callback per contattare direttamente il chiamante.

## <a name="routing-e9-1-1-calls-by-using-an-elin-gateway"></a>Routing delle chiamate di emergenza tramite un gateway ELIN

Alcuni partner del programma Unified Communications Open Interoperability offrono i gateway con funzionalità di sicurezza per le chiamate di emergenza qualificati (ELIN), che possono fungere da alternativa a una connessione trunk SIP a un provider di servizi E9-1-1 qualificato. I gateway ELIN supportano la connettività (CAMA) ISDN o centralizzata per l'accounting automatico dei messaggi con servizi E9-1-1 basati su PSTN (Public Switched Telephone Network). Per informazioni dettagliate sui partner che includono gateway ELIN e collegamenti alla propria documentazione, vedere [infrastruttura qualificata per l'infrastruttura Microsoft Lync](https://go.microsoft.com/fwlink/p/?LinkId=248425) e la [telefonia per Skype for business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).

Analogamente alle connessioni trunk SIP ai provider di servizi E9-1-1, i gateway ELIN supportano anche i mezzi per il routing di una chiamata di emergenza al punto di risposta di sicurezza pubblica più appropriato del chiamante (PSAP), ma questi gateway usano un ELIN come identificatore della posizione. Si definiscono gli ELIN per ogni posizione di risposta all'emergenza nell'organizzazione (per informazioni dettagliate, vedere [gestire le posizioni per i gateway ELIN in Skype for Business Server](elin-gateways.md)).

Quando si usa un gateway ELIN per le chiamate di emergenza, si usa la stessa infrastruttura E9-1-1 di Skype for Business Server che si usa per una connessione trunk SIP. Il database del servizio informazioni sulla posizione fornisce la posizione al client Skype for business e il criterio della posizione Abilita la caratteristica e definisce il routing. Con un gateway ELIN, tuttavia, è necessario aggiungere il contrassegno ELINs al database del servizio informazioni sulla posizione e fare in modo che il gestore PSTN li carichi nel database ALI (Automatic Location Identification).

Quando un client Skype for business ottiene la propria posizione dal servizio informazioni sulla posizione, la posizione include il ELIN. Durante una chiamata di emergenza, il ELIN è incluso nella posizione inviata al gateway ELIN. Il gateway ELIN identifica la chiamata come chiamata di emergenza e scambia il numero della parte chiamante con ELIN. Il gateway ELIN instrada quindi la chiamata alla rete PSTN con il numero di chiamata ELIN. Il provider E9-1-1 PSTN cerca il numero ELIN nel database ALI, un database complementare per il database stradario (Master Street Address Guide). La rete PSTN invia quindi la chiamata al PSAP più appropriato in base alla ricerca di ALI e PSAP invia i primi soccorritori alla posizione del chiamante in base alla ricerca di ALI. Il numero chiamante viene memorizzato nella cache del gateway ELIN per un periodo di tempo predefinito per i callback. Durante un callback, il PSAP raggiunge il gateway ELIN, che scambia il numero ELIN per il num DID (Direct Interior Dialing) del chiamante.

I gateway ELIN supportano le chiamate di emergenza solo dall'interno della rete dell'organizzazione. Non supportano le chiamate di emergenza effettuate dall'esterno della rete.

> [!NOTE]
> Per informazioni dettagliate sull'uso di una connessione trunk SIP per le chiamate di emergenza, vedere [routing di chiamate E9-1-1 tramite trunk SIP](https://technet.microsoft.com/library/157753c3-fe74-4e2c-81da-ee06911d4cc2.aspx).

Il diagramma seguente mostra come viene instradata una chiamata di emergenza da Skype for Business Server a PSAP quando si usa un gateway ELIN.

**Routing delle chiamate E9-1-1 con un gateway ELIN**

![Mostra il modo in cui una chiamata ai servizi di emergenza passa attraverso il Mediation Server e quindi al provider di servizi di emergenza. Dopo questa operazione può essere facoltativamente inviato un messaggio istantaneo alla sicurezza del sito e/o una chiamata di nuovo al chiamante originale.](../../media/Plan_LyncServer_E911_ELINCallRouting.jpg)

1. Un invito SIP che contiene la posizione, il numero di callback del chiamante e l'URL di notifica (facoltativo) e il numero di callback della conferenza vengono instradati a Skype for Business Server.

2. Skype for Business Server corrisponde al numero di emergenza e quindi instrada la chiamata (in base al valore di **utilizzo PSTN** definito nel criterio di posizione applicabile) a un Mediation Server e da lì a un gateway ELIN.

3. Il gateway ELIN instrada la chiamata su un trunk ISDN o CAMA verso la rete PSTN.

4. La PSTN identifica la chiamata come chiamata di emergenza e la instrada a un router selettivo E9-1-1 nella rete. Il router selettivo E9-1-1 Cerca il numero del chiamante nel database ALI per ottenere la posizione geografica. Il router selettivo E9-1-1 Invia la chiamata al PSAP più appropriato in base alle informazioni sulla posizione recuperate dal database ALI.

5. Se sono stati configurati i criteri di posizione per le notifiche, uno o più agenti di sicurezza dell'organizzazione riceveranno un messaggio istantaneo speciale per la notifica di emergenza Skype for business. Questo messaggio compare sempre nella schermata degli addetti alla sicurezza e contiene il nome, il numero di telefono, l'ora e la posizione del chiamante, che consente al personale di sicurezza di rispondere rapidamente al chiamante di emergenza usando un messaggio istantaneo o una voce.

6. Se la chiamata viene interrotta prematuramente, PSAP usa il ELIN per contattare direttamente il chiamante. Il gateway ELIN scambia il ELIN per il chiamante.


