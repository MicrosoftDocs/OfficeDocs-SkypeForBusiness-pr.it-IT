---
title: Pianificare l'instradamento basato sulla posizione per Instradamento diretto
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: roykuntz
search.appverid: MET150
description: Informazioni su come pianificare il routing basato sulla posizione per il routing diretto.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c3d5f4eb0cd63dd252d5fcc01bff21f8643a788
ms.sourcegitcommit: ebdad71a8d393466e33a2fdc8606d882a6007588
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2020
ms.locfileid: "44280275"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>Pianificare l'instradamento basato sulla posizione per Instradamento diretto

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

## <a name="overview-of-location-based-routing"></a>Panoramica del routing basato sulla posizione

In alcuni paesi e aree geografiche è vietato aggirare il provider PSTN (Public Switched Telephone Network) per ridurre i costi delle chiamate interurbane. Questo articolo descrive come usare il routing basato sulla posizione per limitare l'esclusione dei pedaggi per gli utenti di Microsoft teams in base alla loro posizione geografica. Questo articolo si applica solo al routing diretto del sistema telefonico.

In questa sezione verrà visualizzata una panoramica del routing basato sulla posizione e delle indicazioni utili per pianificare la pianificazione. Quando si è pronti per applicare e abilitare il routing basato sulla posizione, vedere:
- [Distribuire le impostazioni di rete per il routing basato sulla posizione](location-based-routing-configure-network-settings.md)
- [Abilitare l'instradamento basato sulla posizione per Instradamento diretto](location-based-routing-enable.md)

Il routing basato sulla posizione è una caratteristica che consente di limitare l'esclusione dei pedaggi in base ai criteri e alla posizione geografica dell'utente al momento della chiamata PSTN in ingresso o in uscita. 

Quando un utente di teams è abilitato per il routing basato sulla posizione, si applicano le operazioni seguenti:
- Per effettuare una chiamata PSTN in uscita, una delle operazioni seguenti deve essere vera:
    - L'endpoint dell'utente si trova in un sito di rete abilitato per il routing basato sulla posizione e chiama l'uscita tramite il gateway corrispondente abilitato per il routing basato sulla posizione. 
    - L'endpoint dell'utente si trova in un sito di rete non abilitato per il routing basato sulla posizione e chiama l'uscita tramite un gateway non abilitato per il routing basato sulla posizione.

    Le chiamate in uscita non sono consentite in altri scenari.

- Per ricevere una chiamata PSTN in ingresso, l'endpoint di risposta dell'utente deve trovarsi nello stesso sito di rete in cui la chiamata entra attraverso il gateway abilitato per il routing basato sulla posizione. In qualsiasi altro scenario, ad esempio se l'utente è in roaming, la chiamata non è consentita e viene instradata alle impostazioni di inoltro di chiamata dell'utente (in genere Voicemail).
- Per trasferire una chiamata PSTN a un altro utente di teams, l'endpoint dell'utente di destinazione deve trovarsi nello stesso sito di rete dell'utente che avvia il trasferimento. I trasferimenti non sono consentiti in altri scenari. 
- Per trasferire un altro utente di teams alla rete PSTN, la chiamata deve essere trasferita tramite un gateway abilitato per il routing basato sulla posizione che si trova nello stesso sito di rete del chiamante iniziale. I trasferimenti non sono consentiti in altri scenari.

Il routing basato sulla posizione usa le stesse definizioni di area di rete, sito e subnet usate da Skype for Business Server. Quando l'esclusione dei pedaggi è limitata per una posizione, un amministratore associa ogni subnet IP e ogni gateway PSTN per tale posizione a un sito di rete. La posizione di un utente è determinata dalla subnet IP a cui sono connessi gli endpoint del team dell'utente al momento di una chiamata PSTN. Un utente può avere più client di teams situati in siti diversi, in questo caso il routing basato sulla posizione impone il routing di ogni client separatamente a seconda della posizione del relativo endpoint. 

Per familiarizzare con alcuni aspetti della terminologia di rete usati in questo articolo, vedere [impostazioni di rete per le funzionalità vocali di cloud in teams](cloud-voice-network-settings.md).

## <a name="apply-location-based-routing"></a>Applicare il routing basato sulla posizione

È necessario applicare il routing basato sulla posizione a utenti, siti di rete e gateway PSTN.  

### <a name="apply-location-based-routing-at-the-user-location"></a>Applicare il routing basato sulla posizione nella posizione dell'utente

Come accennato in precedenza, il routing basato sulla posizione si applica solo agli utenti configurati per il routing diretto. Il routing basato sulla posizione non si applica agli utenti configurati per il piano di chiamata. Gli utenti devono essere abilitati per il routing basato sulla posizione se sono in restrizione di esclusione dei pedaggi, che controlla le condizioni in cui possono effettuare e ricevere chiamate PSTN e il gateway PSTN che può essere usato. Quando un utente abilitato per il routing basato sulla posizione si trova in un sito abilitato per il routing basato sulla posizione, l'utente deve effettuare chiamate tramite un gateway abilitato per il routing basato sulla posizione connesso al sito. 

Il routing basato sulla posizione funziona determinando la posizione corrente dell'utente in base all'indirizzo IP dell'endpoint Teams dell'utente e applica le regole di conseguenza. La posizione di un utente abilitato per il routing basato sulla posizione può essere categorizzata nei modi seguenti: 
- **L'utente si trova nello stesso sito abilitato al routing basato sulla posizione associato al gateway PSTN in cui è stato assegnato il loro DID.**<br>In questo scenario l'utente si trova in un sito di rete noto abilitato per il routing basato sulla posizione e il numero di telefono diretto (DID) dell'utente termina in un gateway PSTN nello stesso sito di rete. Ad esempio, l'utente è in ufficio. 
- **L'utente si trova in un altro sito abilitato per il routing basato sulla posizione non associato al gateway PSTN in cui è stato assegnato il loro DID.**<br>In questo scenario l'utente si trova in un sito di rete noto abilitato per il routing basato sulla posizione e tale sito non è associato al gateway PSTN in cui è assegnato il numero DID dell'utente. Ad esempio, l'utente si sposta in un altro ufficio.  
- **L'utente si trova in un sito interno che non è abilitato per il routing basato sulla posizione.** <br>In questo scenario l'utente si trova in un sito di rete interna noto che non è abilitato per il routing basato sulla posizione. 
- **L'utente si trova in un sito sconosciuto.** 
    - L'utente si trova all'interno della rete interna non definita come sito di rete. 
    - L'utente si trova all'esterno della rete interna. Ad esempio, l'utente si trova su Internet a casa o in un coffee shop. 

### <a name="apply-location-based-routing-at-the-network-site"></a>Applicare il routing basato sulla posizione nel sito di rete 
I siti di rete devono essere abilitati per il routing basato sulla posizione per determinare quali gateway per il routing basato sulla posizione hanno consentito agli utenti di spostarsi in roaming. Se un utente abilitato per il routing basato sulla posizione si sposta in un sito abilitato per il routing basato sulla posizione, è possibile usare solo il gateway PSTN abilitato per il routing basato sulla posizione in tale sito per le chiamate in uscita. Se un utente abilitato per il routing basato sulla posizione viene eseguito in roaming in un sito non abilitato per il routing basato sulla posizione, è possibile usare qualsiasi gateway non abilitato per il routing basato sulla posizione per le chiamate in uscita.  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>Applicare il routing basato sulla posizione presso il gateway PSTN 

I gateway sono associati ai siti per determinare dove un utente abilitato per il routing basato sulla posizione può essere individuato quando effettua o riceve una chiamata PSTN. I gateway devono essere abilitati per il routing basato sulla posizione per assicurarsi che siano in restrizioni di esclusione dei pedaggi e che non possano essere usati dagli utenti non abilitati per il routing basato sulla posizione. Lo stesso gateway può essere associato a più siti e può essere configurato per essere abilitato per il routing basato sulla posizione o non abilitato per il routing basato sulla posizione, a seconda del sito.

## <a name="scenarios-for-location-based-routing"></a>Scenari per il routing in base alla posizione

Questa sezione descrive diversi scenari per limitare l'esclusione dei pedaggi usando il routing basato sulla posizione e confronta il modo in cui le chiamate vengono instradate per gli utenti che non sono abilitati per il routing basato sulla posizione con gli utenti abilitati per il routing basato sulla posizione.

- [L'utente teams inserisce una chiamata in uscita per la rete PSTN](#teams-user-places-an-outbound-call-to-the-pstn)
- [L'utente di Teams riceve una chiamata in ingresso dalla rete PSTN](#teams-user-receives-an-inbound-call-from-the-pstn)
- [Gli utenti del team trasferiscono o inoltrano la chiamata a un altro utente di Teams](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Gli utenti del team trasferiscono o inoltrano la chiamata all'endpoint PSTN](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [Squillo simultaneo](#simultaneous-ringing)
- [Delega](#delegation)

Il diagramma seguente mostra le restrizioni abilitate per il routing basato sulla posizione in ogni scenario. Gli utenti, i siti di rete e i gateway abilitati per il routing basato sulla posizione hanno un bordo intorno. Usare il diagramma come guida per capire come funziona il routing basato sulla posizione in ogni scenario.  

![Diagramma che Mostra gli scenari per il routing basato sulla posizione](media/lbr-direct-routing.png "Diagramma che Mostra gli scenari per il routing basato sulla posizione")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>L'utente teams inserisce una chiamata in uscita per la rete PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Utente non abilitato per il routing basato sulla posizione

Un utente che non è abilitato per il routing basato sulla posizione può effettuare chiamate in uscita usando qualsiasi gateway in qualsiasi sito non abilitato per il routing basato sulla posizione tramite il criterio di routing vocale assegnato. Tuttavia, se un gateway è abilitato per il routing basato sulla posizione, l'utente non può effettuare chiamate in uscita tramite il gateway anche se è assegnato ai criteri di routing vocale. Se l'utente si sposta in un sito abilitato per il routing basato sulla posizione, può effettuare chiamate solo tramite i normali gateway di routing che non sono abilitati per il routing basato sulla posizione.
 
#### <a name="user-enabled-for-location-based-routing"></a>Utente abilitato per il routing basato sulla posizione
In confronto, il routing delle chiamate in uscita per gli utenti abilitati per il routing basato sulla posizione è influenzato dalla posizione di rete dell'endpoint dell'utente. La tabella seguente mostra il modo in cui il routing basato sulla posizione influisce sul routing delle chiamate in uscita di User1, a seconda della posizione di User1. 

|Posizione dell'endpoint User1  |Routing delle chiamate in uscita per User1  |
|---------|---------|
|Stesso sito in cui è stato assegnato l'utente, sito abilitato per il routing basato sulla posizione (Microsoft1)      |Chiamata instradata tramite gateway abilitato per il routing basato sulla posizione (GW1) su Microsoft1, in base ai criteri di routing vocale dell'utente         |
|Sito diverso da quello in cui è stato assegnato l'utente, sito abilitato per il routing basato sulla posizione (sito2)    |Chiamata instradata tramite gateway abilitato per il routing basato sulla posizione (GW2) su Roam sito2, in base ai criteri di routing vocale dell'utente        |
|Sito diverso da quello in cui è stato assegnato l'utente, il sito non è abilitato per il routing basato sulla posizione (Site3)  |Chiamata instradata tramite gateway non abilitato per il routing basato sulla posizione presso il sito non abilitato per il routing basato sulla posizione (GW3), in base ai criteri di routing vocale dell'utente       |
|Rete interna sconosciuta (Location4)    |  Chiamate PSTN non consentite       |
|Rete esterna sconosciuta (Location5)    | Chiamate PSTN non consentite        |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>L'utente di Teams riceve una chiamata in ingresso dalla rete PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Utente non abilitato per il routing basato sulla posizione

Un utente che non è abilitato per il routing basato sulla posizione può ricevere una chiamata in ingresso dal gateway non abilitato per il routing basato sulla posizione da cui il numero di ingressi assegnati. Se l'utente si sposta in un sito non abilitato per il routing basato sulla posizione, può comunque ricevere chiamate tramite i normali gateway PSTN.
  
#### <a name="user-enabled-for-location-based-routing"></a>Utente abilitato per il routing basato sulla posizione

In confronto, gli utenti abilitati per il routing basato sulla posizione possono ricevere solo le chiamate in ingresso dal gateway PSTN a cui è stato assegnato il destinatario quando si trovano nello stesso sito. La tabella seguente mostra il modo in cui User1 riceve le chiamate in ingresso quando User1 si sposta in percorsi di rete diversi. Se la chiamata non viene instradata all'endpoint dell'utente, passa alle impostazioni di inoltro di chiamata dell'utente, se le impostazioni sono configurate. In genere, si tratta della segreteria telefonica.  

|Posizione dell'endpoint User1  |Routing delle chiamate in ingresso a User1  |
|---------|---------|
|Lo stesso sito in cui è stato assegnato l'utente, sito abilitato per il routing basato sulla posizione (Microsoft1)   | Chiamate indirizzate a endpoint Utente1 in Microsoft1        |
|Sito diverso da quello in cui è stato assegnato l'utente, sito abilitato per il routing basato sulla posizione (sito2)    | Chiamate non indirizzate agli endpoint in sito2        |
|Sito diverso da quello in cui è stato assegnato l'utente, il sito non è abilitato per il routing basato sulla posizione (Site3)    | Chiamate non indirizzate agli endpoint in Site3        |
|Rete interna sconosciuta (Location4)   | Chiamate non indirizzate agli endpoint in Location4        |
|Rete esterna sconosciuta (Location5)     | Chiamate non indirizzate agli endpoint in Location5        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>Gli utenti del team trasferiscono o inoltrano la chiamata a un altro utente di Teams

Quando viene coinvolto un endpoint PSTN, il routing basato sulla posizione analizza se uno o entrambi gli utenti sono abilitati per il routing basato sulla posizione e determina se la chiamata deve essere trasferita o inoltrata a seconda della posizione di entrambi gli endpoint. 
 
Il trasferimento delle chiamate richiede che l'utente che inizia a prendere la chiamata mentre l'inoltro di chiamata non richieda la risposta della chiamata iniziale. Questo significa che le chiamate possono essere inoltrate anche se User1 non è in una posizione per ricevere chiamate in ingresso (Vedi la tabella nell' [utente Teams riceve una chiamata in ingresso dalla sezione PSTN](#teams-user-receives-an-inbound-call-from-the-pstn) ) e le chiamate non possono essere trasferite se User1 non è in grado di ricevere la chiamata in ingresso. 

#### <a name="user-not-enabled-for-location-based-routing"></a>Utente non abilitato per il routing basato sulla posizione

Un utente che non è abilitato per il routing basato sulla posizione può trasferire o inoltrare chiamate PSTN ad altri utenti non abilitati per il routing basato sulla posizione. L'utente in genere non è autorizzato a trasferire o inoltrare una chiamata PSTN a un utente abilitato per il routing basato sulla posizione, perché gli utenti abilitati al routing basato sulla posizione sono in genere consentiti solo per essere congiunti in gateway abilitati al routing basato sulla posizione per le chiamate PSTN. L'eccezione è quando un routing basato sulla posizione ha abilitato il roaming di un utente a un sito non abilitato per il routing basato sulla posizione. In questo scenario, la chiamata trasferita è consentita.  

Allo stesso modo, un utente che non è abilitato per il routing basato sulla posizione può ricevere solo una chiamata PSTN transfer o Forwarded da un altro utente che non è abilitato per il routing basato sulla posizione. 

#### <a name="user-enabled-for-location-based-routing"></a>Utente abilitato per il routing basato sulla posizione

In generale, il trasferimento e l'inoltro di chiamate PSTN in ingresso da un gateway abilitato per il routing basato sulla posizione è consentito solo se l'utente di destinazione è abilitato per il routing basato sulla posizione e si trova nello stesso sito. In caso contrario, non è consentito trasferire e inoltrare le chiamate. 

La tabella seguente mostra se l'inoltro di chiamata e i trasferimenti di chiamata sono consentiti, a seconda della posizione dell'utente di destinazione. In questa tabella, User1, che si trova in Microsoft1, avvia il trasferimento o inoltra ad altri utenti di Team abilitati anche per il routing basato sulla posizione e che si trovano in posizioni diverse.  

|Posizione dell'endpoint utente di destinazione|User1 avvia il trasferimento delle chiamate |User1 avvia la chiamata in avanti|
|---------|---------|---------|
|Stesso sito di rete come iniziatore (User2)|Consentiti|Consentiti|
|Sito di rete diverso, sito abilitato per il routing basato sulla posizione (User3)|Non consentito|Non consentito|
|Sito di rete diverso, sito non abilitato per il routing basato sulla posizione (User4)|Non consentito|Non consentito|
|Rete interna sconosciuta (User5)| Non consentito|Non consentito|
|Rete esterna sconosciuta (USER6)| Non consentito|Non consentito|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Gli utenti del team trasferiscono o inoltrano la chiamata all'endpoint PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Utente non abilitato per il routing basato sulla posizione

- È consentito trasferire e inoltrare una chiamata PSTN a un altro numero PSTN. 
- Il trasferimento e l'inoltro di una chiamata VOIP in ingresso alla rete PSTN deve rispettare le restrizioni di esclusione dei pedaggi del chiamante. 
    - Se il chiamante non è abilitato per il routing basato sulla posizione, è possibile trasferirlo in qualsiasi gateway PSTN non abilitato per il routing basato sulla posizione.
    - Se il chiamante è abilitato per il routing basato sulla posizione, è possibile trasferirlo solo in un gateway abilitato per il routing basato sulla posizione situato nello stesso sito di rete. 

#### <a name="user-enabled-for-location-based-routing"></a>Utente abilitato per il routing basato sulla posizione

- Trasferimento e inoltro in ingresso una chiamata PSTN a un altro numero PSTN deve essere instradata allo stesso gateway abilitato per il routing basato sulla posizione in cui è arrivata la chiamata in ingresso. 
- Il trasferimento e l'inoltro di una chiamata VOIP in ingresso alla rete PSTN deve rispettare sia il chiamante che le restrizioni di esclusione dei pedaggi dell'utente. 
    - Se il chiamante non è abilitato per il routing basato sulla posizione, è possibile trasferirlo in qualsiasi gateway PSTN non abilitato per il routing basato sulla posizione.
    - Se il chiamante è abilitato per il routing basato sulla posizione, è possibile trasferirlo solo in un gateway abilitato per il routing basato sulla posizione situato nello stesso sito di rete.
 
La tabella seguente mostra il modo in cui il routing basato sulla posizione influenza il routing di una chiamata VOIP da User1 in Microsoft1 agli utenti in posizioni diverse che trasferiscono o inoltrano la chiamata a un endpoint PSTN.  

|Utente che avvia il trasferimento delle chiamate o inoltra  |Trasferimento in PSTN  |Inoltra a PSTN  |
|---------|---------|---------|
|Stesso sito di rete, sito abilitato per il routing basato sulla posizione (User2)   |Il trasferimento delle chiamate può essere instradato solo attraverso il routing basato sulla posizione abilitato Gateway1 su Microsoft1, in base ai criteri di routing vocale di User2's         |La chiamata inoltra può essere instradata solo attraverso il routing basato sulla posizione abilitato Gateway1 su Microsoft1, in base ai criteri di routing vocale di User2's         |
|Sito di rete diverso, sito abilitato per il routing basato sulla posizione (User3)    |Il trasferimento delle chiamate può essere instradato solo attraverso il routing basato sulla posizione abilitato Gateway1 su Microsoft1, in base ai criteri di routing vocale di User3's         |La chiamata inoltra può essere instradata solo attraverso il routing basato sulla posizione abilitato Gateway1 su Microsoft1, in base ai criteri di routing vocale di User3's         |
|Sito di rete diverso, sito non abilitato per il routing basato sulla posizione (User4)    |Il trasferimento delle chiamate può essere instradato solo attraverso il routing basato sulla posizione abilitato Gateway1 su Microsoft1, in base ai criteri di routing vocale di User4's         |La chiamata inoltra può essere instradata solo attraverso il routing basato sulla posizione abilitato Gateway1 su Microsoft1, in base ai criteri di routing vocale di User4's         |
|Rete interna sconosciuta (User5)     |Il trasferimento delle chiamate può essere instradato solo attraverso il routing basato sulla posizione abilitato Gateway1 su Microsoft1, in base ai criteri di routing vocale di User5's         |La chiamata inoltra può essere instradata solo attraverso il routing basato sulla posizione abilitato Gateway1 su Microsoft1, in base ai criteri di routing vocale di User5's         |
|Rete esterna sconosciuta (USER6)   |Il trasferimento delle chiamate può essere instradato solo attraverso il routing basato sulla posizione abilitato Gateway1 su Microsoft1, in base ai criteri di routing vocale di User6's        |La chiamata inoltra può essere instradata solo attraverso il routing basato sulla posizione abilitato Gateway1 su Microsoft1, in base ai criteri di routing vocale di User6's         |

### <a name="simultaneous-ringing"></a>Squillo simultaneo

Quando un utente abilitato per il routing basato sulla posizione riceve una chiamata e ha abilitato l'attivazione simultanea, il routing basato sulla posizione analizza la posizione della parte chiamante e gli endpoint delle parti chiamate per determinare se la chiamata deve essere instradata. La suoneria simultanea segue le stesse regole basate sulla posizione dei trasferimenti e degli inoltri delle chiamate. 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>Squillo simultaneo per un altro utente di Teams

Nella tabella seguente viene indicato se il routing basato sulla posizione consente di effettuare chiamate simultanee a utenti diversi per una chiamata PSTN in ingresso per User1.

|Posizione dell'endpoint utente di destinazione|Squillo simultaneo  |
|---------|---------|
|Stesso sito di rete come iniziatore (User2)   |Consentiti         |
|Sito di rete roaming diverso abilitato per il routing basato sulla posizione (User3)   |Non consentito         |
|Sito di rete roaming non abilitato per il routing basato sulla posizione (User4)   |Non consentito        |
|Rete interna sconosciuta (User5)    | Non consentito        |
|Rete esterna sconosciuta (USER6)    |Non consentito        |
|L'utente di destinazione è un numero PSTN    |La chiamata può essere instradata solo attraverso il routing basato sulla posizione abilitato Gateway1 su Microsoft1, in base ai criteri di routing vocale di Utente1      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>Squillo simultaneo a un endpoint PSTN

La tabella seguente mostra il comportamento di routing basato sulla posizione per una chiamata VOIP in ingresso da User1 che si trova in Microsoft1 per gli utenti in posizioni diverse con anello simultaneo impostato su un numero PSTN. 

|Posizione dell'endpoint utente denominata  |La destinazione dell'anello simultaneo è l'endpoint PSTN |
|---------|---------|
|Stesso sito di rete, sito abilitato per il routing basato sulla posizione (User2)    |La chiamata può essere instradata solo attraverso il routing basato sulla posizione Gateway1 su Microsoft1, in base ai criteri di routing vocale di User2's       |
|Sito di rete diverso abilitato per il routing basato sulla posizione (User3)    |La chiamata può essere instradata solo attraverso il routing basato sulla posizione Gateway1 su Microsoft1, in base ai criteri di routing vocale di User3's        |
|Sito di rete diverso non abilitato per il routing basato sulla posizione (User4)    |La chiamata può essere instradata solo attraverso il routing basato sulla posizione Gateway1 su Microsoft1, in base ai criteri di routing vocale di User4's         |
|Rete interna sconosciuta (User5)    |La chiamata può essere instradata solo attraverso il routing basato sulla posizione Gateway1 su Microsoft1, in base ai criteri di routing vocale di User5's         |
|Rete esterna sconosciuta (USER6)   |La chiamata può essere instradata solo attraverso il routing basato sulla posizione Gateway1 su Microsoft1, in base ai criteri di routing vocale di User6's         |

#### <a name="inbound-calls-through-voice-app-auto-attendant-or-call-queue"></a>Chiamate in ingresso tramite l'app vocale (operatore automatico o coda di chiamata)

Le chiamate PSTN in ingresso da un gateway abilitato per il routing basato sulla posizione possono connettersi a un operatore automatico o a una coda di chiamata. Gli utenti abilitati per il routing basato sulla posizione possono ricevere solo i trasferimenti di chiamata in ingresso da queste applicazioni quando si trovano nello stesso sito da cui proviene la chiamata PSTN in ingresso. 
 
L'inoltro di chiamata e lo squillo simultaneo agli utenti e PSTN sono consentiti per i trasferimenti di app vocali. Il completamento della chiamata alla destinazione è soggetto alle stesse regole di routing basate sulla posizione elencate in precedenza.  
 
È anche consentito l'inoltro alla segreteria telefonica.  

### <a name="delegation"></a>Delega

Un utente di teams può scegliere delegati che possono effettuare e ricevere chiamate per loro conto. Le funzionalità di delega in teams sono interessate dal routing basato sulla posizione nel modo seguente: 
- Per le chiamate in uscita da un delegato abilitato per il routing basato sulla posizione per conto di un delegante, valgono le stesse regole. Il routing delle chiamate si basa sui criteri di autorizzazione delle chiamate del delegato, sui criteri di routing vocale e sulla posizione. Per altre informazioni, vedere [l'utente di teams inserisce una chiamata in uscita per la rete PSTN](#teams-user-places-an-outbound-call-to-the-pstn). 
- Per le chiamate PSTN in ingresso a un delegante, le stesse regole di routing basate sulla posizione che si applicano per l'inoltro di chiamata o lo squillo simultaneo ad altri utenti si applicano anche ai delegati. Per altre informazioni, vedere [trasferimenti o inoltro di una chiamata a un altro utente di](#teams-user-transfers-or-forwards-call-to-another-teams-user)teams, l' [utente del team trasferisce o inoltra una chiamata a endpoint PSTN](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)e [squillo simultaneo](#simultaneous-ringing). Quando un delegato imposta un endpoint PSTN come destinazione squillo simultaneo, il criterio di routing vocale del delegato viene usato per instradare la chiamata alla rete PSTN. 
- Per la delega, è consigliabile che il delegante e i delegati associati si trovino nello stesso sito di rete. 

## <a name="other-planning-considerations"></a>Altre considerazioni sulla pianificazione

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>Modifiche da una distribuzione di routing basata sulla posizione locale

I criteri di routing vocale del sito di rete non vengono più usati. Usiamo invece i criteri di routing vocale dell'utente. Ciò significa che per consentire agli utenti di spostarsi in altri siti, il criterio di routing vocale deve includere i gateway dei siti in roaming. 

### <a name="technical-considerations-for-location-based-routing"></a>Considerazioni tecniche per il routing in base alla posizione

Le subnet IPv4 e IPv6 sono supportate, tuttavia, il protocollo IPv6 ha la precedenza quando si verifica una corrispondenza.

### <a name="client-support-for-location-based-routing"></a>Supporto client per il routing basato sulla posizione

Sono supportati i client Team seguenti:
- Client desktop Teams (Windows e Mac)
- Client per dispositivi mobili Teams (iOS e Android)
- Telefoni IP Teams

Il client Web teams e i client Skype for business non sono supportati.

### <a name="capabilities-not-supported-by-location-based-routing"></a>Funzionalità non supportate dal routing in base alla posizione

Il routing basato sulla posizione non si applica ai tipi di interazioni seguenti. Il routing basato sulla posizione non viene applicato quando gli endpoint del team interagiscono con endpoint PSTN negli scenari seguenti: 
- Parcheggio di chiamata o recupero di chiamate PSTN tramite Call Park 
- Un utente di Skype for business locale o un utente di Skype for business online chiama un utente di Teams  

### <a name="location-based-routing-for-conferencing"></a>Routing basato sulla posizione per i servizi di conferenza

Un utente abilitato al routing basato sulla posizione su una chiamata PSTN non è autorizzato ad avviare una conferenza con un altro utente o un numero PSTN. La connessione agli operatori automatici o alle code di chiamata è consentita. Se l'utente ha una licenza per conferenze, l'utente deve avviare una conferenza con gli utenti pertinenti e chiamare la rete PSTN tramite il Bridge conferenza per avviare una conferenza telefonica.  

### <a name="media-bypass-requirement-for-location-based-routing"></a>Requisiti per il bypass multimediale per il routing basato sulla posizione

Se si sta distribuendo il routing basato sulla posizione in India, è necessario configurare anche il bypass multimediale. Per altre informazioni, vedere [pianificare il bypass multimediale con routing diretto](direct-routing-plan-media-bypass.md).

## <a name="next-steps"></a>Passaggi successivi

Accedere a [configurare le impostazioni di rete per il routing basato sulla posizione](location-based-routing-configure-network-settings.md).

## <a name="related-topics"></a>Argomenti correlati

- [Abilitare l'instradamento basato sulla posizione per Instradamento diretto](location-based-routing-enable.md)
- [Impostazioni di rete per le funzionalità vocali di cloud in teams](cloud-voice-network-settings.md)
