---
title: Pianificare l'instradamento basato sulla posizione per Instradamento diretto
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: roykuntz
search.appverid: MET150
description: Informazioni su come pianificare il Location-Based per il routing diretto.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: f05049cdc181aef72f9ed018f20cd8d2e3264909
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822926"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>Pianificare l'instradamento basato sulla posizione per Instradamento diretto

## <a name="overview-of-location-based-routing"></a>Panoramica del routing Location-Based distribuzione

In alcuni paesi e aree geografiche, è illegale bypassare il provider PSTN (Public Switched Telephone Network) per ridurre i costi per le chiamate a distanza. Questo articolo descrive come usare il routing Location-Based per limitare il bypass a numero verde per gli utenti di Microsoft Teams in base alla loro posizione geografica. Questo articolo si applica solo all'instradamento diretto del sistema telefonico.

Verrà fornita una panoramica del routing e delle Location-Based per facilitare la pianificazione. Quando si è pronti per applicare e abilitare Location-Based distribuzione, vedere:

- [Distribuire le impostazioni di rete per Location-Based distribuzione](location-based-routing-configure-network-settings.md)
- [Abilitare l'instradamento basato sulla posizione per Instradamento diretto](location-based-routing-enable.md)

> [!NOTE]
> Location-Based routing delle chiamate non è disponibile nelle distribuzioni High o DoD di Microsoft 365 Government Community Cloud (GCC).

Location-Based routing delle chiamate è una caratteristica che consente di limitare il bypass a numero verde in base ai criteri e alla posizione geografica dell'utente al momento di una chiamata PSTN in ingresso o in uscita. Location-Based routing delle chiamate è stato progettato per fornire un meccanismo per evitare il bypass a numero verde. Non deve essere usato come meccanismo per instradare dinamicamente le chiamate PSTN in base alla posizione dell'utente o potrebbero verificarsi conseguenze indesiderate.

Quando un utente di Teams è abilitato per Location-Based instradamento, si applica quanto segue:

- Per effettuare una chiamata PSTN in uscita, deve essere vera una delle condizioni seguenti:
    - L'endpoint dell'utente si trova in un sito di rete abilitato per il routing di Location-Based e chiama il punto di uscita attraverso il gateway corrispondente abilitato per il routing Location-Based locale. 
    - L'endpoint dell'utente si trova in un sito di rete non abilitato per il routing Location-Based e per le chiamate in uscita attraverso un gateway non abilitato per il routing Location-Based.

    Le chiamate in uscita non sono consentite in altri scenari.

- Per ricevere una chiamata PSTN in ingresso, l'endpoint di risposta dell'utente deve trovarsi nello stesso sito di rete in cui la chiamata in entrata passa attraverso il gateway abilitato per Location-Based instradamento. In qualsiasi altro scenario, ad esempio se l'utente è in roaming, la chiamata non è consentita e viene instradata alle impostazioni di inoltro di chiamata dell'utente (in genere la segreteria telefonica).
- Per trasferire una chiamata PSTN a un altro utente di Teams, l'endpoint dell'utente di destinazione deve trovarsi nello stesso sito di rete dell'utente che avvia il trasferimento. I trasferimenti non sono consentiti in altri scenari. 
- Per trasferire un altro utente di Teams alla rete PSTN, la chiamata deve essere trasferita tramite un gateway abilitato per il routing di Location-Based situato nello stesso sito di rete del chiamante iniziale. I trasferimenti non sono consentiti in altri scenari.

Location-Based routing usa le stesse definizioni di rete, sito e subnet utilizzate da Skype for Business Server. Quando il bypass a pagamento è limitato per una posizione, un amministratore associa ogni subnet IP e ogni gateway PSTN per tale posizione a un sito di rete. La posizione di un utente è determinata dalla subnet IP a cui gli endpoint di Teams dell'utente sono connessi al momento di una chiamata PSTN. Un utente può avere più client di Teams situati in siti diversi, nel qual caso il routing di Location-Based applica il routing di ogni client separatamente a seconda della posizione del relativo endpoint. 

Per acquisire familiarità con parte della terminologia di rete usata in questo articolo, vedere Impostazioni di rete per le [funzionalità vocali cloud in Teams.](cloud-voice-network-settings.md)

## <a name="apply-location-based-routing"></a>Applicare Location-Based distribuzione

È necessario applicare Location-Based a utenti, siti di rete e gateway PSTN.  

### <a name="apply-location-based-routing-at-the-user-location"></a>Applicare Location-Based routing dei messaggi nella posizione dell'utente

Come accennato in Location-Based, il routing Location-Based viene applicato solo agli utenti impostati per il routing diretto. Location-Based'instradamento non è applicabile agli utenti impostati per il Piano per chiamate. Gli utenti devono essere abilitati per il routing Location-Based se sono sotto la restrizione del bypass a pagamento, che controlla le condizioni in cui possono effettuare e ricevere chiamate PSTN e il gateway PSTN che può essere utilizzato. Quando un utente abilitato per il routing di Location-Based si trova in un sito abilitato per il routing Location-Based, l'utente deve effettuare chiamate attraverso un gateway abilitato per il routing di Location-Based connesso al sito. 

Location-Based routing funziona determinando la posizione corrente dell'utente in base all'indirizzo IP dell'endpoint Teams dell'utente e applica le regole di conseguenza. La posizione di un utente abilitato per il routing Location-Based può essere classificata nei modi seguenti: 
- **L'utente si trova nello stesso Location-Based sito abilitato per il routing associato al gateway PSTN a cui è assegnato il suo DID.**<br>In questo scenario, l'utente si trova in un sito di rete noto abilitato per il routing Location-Based e il numero DID (Direct Inward Dial) dell'utente termina su un gateway PSTN nello stesso sito di rete. Ad esempio, l'utente è nel suo ufficio. 
- **L'utente si trova in un percorso diverso Location-Based sito abilitato per il routing non associato al gateway PSTN a cui è assegnato il suo DID.**<br>In questo scenario l'utente si trova in un sito di rete noto abilitato per il routing di Location-Based e non è associato al gateway PSTN a cui è assegnato il numero DID dell'utente. Ad esempio, l'utente viaggia in un altro ufficio.  
- **L'utente si trova in un sito interno non abilitato per il routing Location-Based utenti.** <br>In questo scenario l'utente si trova in un sito di rete interno noto non abilitato per il routing Location-Based locale. 
- **L'utente si trova in un sito sconosciuto.** 
    - L'utente si trova all'interno della rete interna che non è definita come sito di rete. 
    - L'utente si trova all'esterno della rete interna. Ad esempio, l'utente è su Internet a casa o in un bar. 

### <a name="apply-location-based-routing-at-the-network-site"></a>Applicare Location-Based routing sul sito di rete 
I siti di rete devono essere abilitati per il routing Location-Based per determinare quali gateway instradare Location-Based utenti abilitati per il routing in roaming. Se un utente abilitato per il routing di Location-Based viene mappato a un sito abilitato per il routing Location-Based, per le chiamate in uscita può essere usato solo il gateway PSTN abilitato per il routing Location-Based in tale sito. Se un utente abilitato per Location-Based il routing viene mappato a un sito non abilitato per il routing Location-Based, qualsiasi gateway non abilitato per il routing Location-Based può essere usato per le chiamate in uscita.  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>Applicare Location-Based routing al gateway PSTN 

I gateway sono associati ai siti per determinare dove può essere individuato un utente abilitato per il routing Location-Based quando effettua o riceve una chiamata PSTN. I gateway devono essere abilitati per il routing Location-Based per assicurarsi che siano sotto restrizioni di bypass a pagamento e non possano essere usati da utenti non abilitati per Location-Based routing. Lo stesso gateway può essere associato a più siti e può essere configurato per essere abilitato per il routing di Location-Based o non abilitato per il routing Location-Based, a seconda del sito.

## <a name="scenarios-for-location-based-routing"></a>Scenari per il routing in base alla posizione

Questa sezione descrive diversi scenari di limitazione del bypass a numero verde mediante Location-Based Routing e confronta il modo in cui le chiamate vengono instradati per gli utenti non abilitati per il routing Location-Based con gli utenti abilitati per il routing Location-Based.

- [Un utente di Teams inserisce una chiamata in uscita alla rete PSTN](#teams-user-places-an-outbound-call-to-the-pstn)
- [Un utente di Teams riceve una chiamata in entrata dalla rete PSTN](#teams-user-receives-an-inbound-call-from-the-pstn)
- [Un utente di Teams trasferisce o inoltra la chiamata a un altro utente di Teams](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [L'utente di Teams trasferisce o inoltra le chiamate all'endpoint PSTN](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [Squillo simultaneo](#simultaneous-ringing)
- [Delega](#delegation)

Il diagramma seguente illustra le restrizioni abilitate dal routing Location-Based distribuzione in ogni scenario. Gli utenti, i siti di rete e i gateway abilitati per Location-Based routing hanno un bordo intorno ad essi. Usare il diagramma come guida per comprendere il funzionamento Location-Based routing in ogni scenario.  

![Diagramma che illustra gli scenari per il routing Location-Based distribuzione](media/lbr-direct-routing.png "Diagramma che illustra gli scenari per il routing Location-Based distribuzione")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>Un utente di Teams inserisce una chiamata in uscita alla rete PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Utente non abilitato per Location-Based distribuzione

Un utente non abilitato per il routing Location-Based può effettuare chiamate in uscita utilizzando qualsiasi gateway su qualsiasi sito non abilitato per il routing Location-Based attraverso i criteri di routing vocale assegnati. Tuttavia, se un gateway è abilitato per il routing Location-Based, l'utente non può effettuare chiamate in uscita attraverso il gateway anche se è assegnato ai propri criteri di routing vocale. Se l'utente effettua il roaming a un sito abilitato per il routing Location-Based, può effettuare chiamate solo attraverso i gateway di routing normali non abilitati per Location-Based routing.
 
#### <a name="user-enabled-for-location-based-routing"></a>Utente abilitato per Location-Based distribuzione
In confronto, il routing delle chiamate in uscita per gli utenti abilitati per il routing Location-Based è interessato dal percorso di rete dell'endpoint dell'utente. La tabella seguente mostra in che modo Location-Based incide sul routing delle chiamate in uscita di User1, a seconda della posizione dell'Utente1. 

|Posizione endpoint Utente1  |Instradamento delle chiamate in uscita per Utente1  |
|---------|---------|
|Stesso sito in cui è assegnato IL DID dell'utente, sito abilitato per Location-Based routing (Sito1)      |Chiamata instradata attraverso un gateway abilitato per Location-Based Routing (GW1) sul sito1, in base al criterio di routing vocale dell'utente         |
|Sito diverso da quello in cui è assegnato il DID dell'utente, sito abilitato per Location-Based routing (Sito2)    |Chiamata instradata attraverso un gateway abilitato per Location-Based Routing (GW2) al sito di roaming2, in base al criterio di routing vocale dell'utente        |
|Sito diverso da quello in cui è assegnato il DID dell'utente, sito non abilitato per Location-Based routing (Sito3)  |Chiamata instradata attraverso un gateway non abilitato per il routing Location-Based al sito non abilitato per Location-Based Routing (GW3), in base ai criteri di instradamento vocale dell'utente       |
|Rete interna sconosciuta (Percorso4)    |  Chiamate PSTN non consentite       |
|Rete esterna sconosciuta (Percorso5)    | Chiamate PSTN non consentite        |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>Un utente di Teams riceve una chiamata in entrata dalla rete PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Utente non abilitato per Location-Based distribuzione

Un utente non abilitato per il routing Location-Based può ricevere una chiamata in ingresso dal gateway non abilitato per il routing Location-Based da cui ingresse il numero DID assegnato. Se l'utente è in roaming su un sito non abilitato per il routing Location-Based, potrà comunque ricevere chiamate attraverso i normali gateway PSTN.
  
#### <a name="user-enabled-for-location-based-routing"></a>Utente abilitato per Location-Based distribuzione

In confronto, gli utenti abilitati per Location-Based routing possono ricevere chiamate in ingresso solo dal gateway PSTN a cui è stato assegnato il proprio DID quando si trovano nello stesso sito. La tabella seguente mostra in che modo User1 riceve le chiamate in ingresso quando User1 si sposta in percorsi di rete diversi. Se la chiamata non viene instradata all'endpoint dell'utente, passa alle impostazioni di inoltro di chiamata dell'utente, se sono configurate. In genere si tratta della segreteria telefonica.  

|Posizione endpoint Utente1  |Instradamento delle chiamate in ingresso all'Utente1  |
|---------|---------|
|Stesso sito in cui è assegnato IL DID dell'utente, sito abilitato per Location-Based routing (Sito1)   | Chiamate indirizzate all'endpoint Utente1 in Site1        |
|Sito diverso da quello in cui è assegnato il DID dell'utente, sito abilitato per Location-Based routing (Sito2)    | Chiamate non instradati agli endpoint nel Sito2        |
|Sito diverso da quello in cui è assegnato il DID dell'utente, sito non abilitato per Location-Based routing (Sito3)    | Chiamate non instradati agli endpoint in Site3        |
|Rete interna sconosciuta (Percorso4)   | Chiamate non instradati agli endpoint in Location4        |
|Rete esterna sconosciuta (Percorso5)     | Chiamate non instradati agli endpoint in Location5        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>Un utente di Teams trasferisce o inoltra la chiamata a un altro utente di Teams

Quando viene coinvolto un endpoint PSTN, il routing di Location-Based analizza se uno o entrambi gli utenti sono abilitati per il routing Location-Based e determina se la chiamata deve essere trasferita o inoltrata a seconda della posizione di entrambi gli endpoint. 
 
Il trasferimento di chiamata richiede all'utente che avvia la chiamata di rispondere mentre l'inoltro di chiamata non richiede la risposta alla chiamata iniziale. Questo significa che le chiamate possono essere inoltrate anche se l'Utente1 non è in una posizione per ricevere le chiamate in entrata (vedere la tabella nell'utente di Teams riceve una chiamata in entrata dalla sezione [PSTN)](#teams-user-receives-an-inbound-call-from-the-pstn) e le chiamate non possono essere trasferite se l'Utente1 non è in grado di ricevere la chiamata in entrata. 

#### <a name="user-not-enabled-for-location-based-routing"></a>Utente non abilitato per Location-Based distribuzione

Un utente non abilitato per Location-Based instradamento può trasferire o inoltrare chiamate PSTN ad altri utenti non abilitati per Location-Based utenti. In genere, all'utente non sarà consentito trasferire o inoltrare una chiamata PSTN a un utente abilitato per il routing Location-Based in quanto gli utenti abilitati per Location-Based routing possono in genere essere collocati in co-posizione solo Location-Based nei gateway abilitati per il routing per le chiamate PSTN. Fa eccezione il roaming di Location-Based di un utente abilitato per il routing a un sito non abilitato per Location-Based distribuzione. In questo scenario, la chiamata trasferita è consentita.  

Analogamente, un utente non abilitato per l'instradamento Location-Based può ricevere solo un trasferimento o una chiamata PSTN inoltrata da un altro utente non abilitato per Location-Based instradamento. 

#### <a name="user-enabled-for-location-based-routing"></a>Utente abilitato per Location-Based distribuzione

In generale, il trasferimento e l'inoltro di chiamate PSTN in ingresso da un gateway abilitato per il routing Location-Based è consentito solo se l'utente di destinazione è abilitato per il routing Location-Based e si trova nello stesso sito. In caso contrario, il trasferimento e l'inoltro delle chiamate non sono consentiti. 

La tabella seguente mostra se l'inoltro di chiamata e i trasferimenti di chiamata sono consentiti, a seconda della posizione dell'utente di destinazione. In questa tabella, Utente1, che si trova in Sito1, avvia il trasferimento o l'inoltro ad altri utenti di Teams che sono anche abilitati per Location-Based Routing e che si trovano in posizioni diverse.  

|Posizione endpoint utente di destinazione|Utente1 avvia il trasferimento di chiamata |User1 avvia l'inoltro di chiamata|
|---------|---------|---------|
|Stesso sito di rete dell'iniziatore (Utente2)|Consentito|Consentito|
|Sito di rete diverso, sito abilitato per Location-Based routing (Utente3)|Non consentito|Non consentito|
|Sito di rete diverso, sito non abilitato per Location-Based routing (Utente4)|Non consentito|Non consentito|
|Rete interna sconosciuta (Utente5)| Non consentito|Non consentito|
|Rete esterna sconosciuta (Utente6)| Non consentito|Non consentito|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>L'utente di Teams trasferisce o inoltra le chiamate all'endpoint PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Utente non abilitato per Location-Based distribuzione

- È consentito il trasferimento e l'inoltro di una chiamata PSTN a un altro numero PSTN. 
- Il trasferimento e l'inoltro di una chiamata VOIP in ingresso alla rete PSTN devono rispettare le limitazioni del bypass a numero verde del chiamante. 
    - Se il chiamante non è abilitato per Location-Based, può essere trasferito a qualsiasi gateway PSTN non abilitato per Location-Based instradamento.
    - Se il chiamante è abilitato per Location-Based, può essere trasferito solo a un gateway abilitato per il routing di Location-Based situato nello stesso sito di rete. 

#### <a name="user-enabled-for-location-based-routing"></a>Utente abilitato per Location-Based distribuzione

- Il trasferimento e l'inoltro in ingresso di una chiamata PSTN a un altro numero PSTN devono essere instradati allo stesso gateway abilitato per il Location-Based in cui è entrata la chiamata in ingresso. 
- Il trasferimento e l'inoltro di una chiamata VOIP in ingresso alla rete PSTN devono rispettare sia il chiamante che le restrizioni sul bypass a numero verde dell'utente. 
    - Se il chiamante non è abilitato per Location-Based, può essere trasferito a qualsiasi gateway PSTN non abilitato per Location-Based instradamento.
    - Se il chiamante è abilitato per Location-Based, può essere trasferito solo a un gateway abilitato per il routing di Location-Based situato nello stesso sito di rete.
 
La tabella seguente mostra in che modo il routing di Location-Based influisce sul routing di una chiamata VOIP dall'Utente1 al Sito1 agli utenti che trasferiscono o inoltrano la chiamata a un endpoint PSTN.  

|Utente che avvia il trasferimento o l'inoltro di chiamata  |Trasferimento a PSTN  |Inoltrare a PSTN  |
|---------|---------|---------|
|Stesso sito di rete, sito abilitato per Location-Based routing (Utente2)   |Il trasferimento di chiamata può essere instradato solo attraverso Location-Based routing abilitato per Gateway1 nel sito1, in base al criterio di routing vocale dell'utente2         |L'inoltro di chiamata può essere instradato solo attraverso Location-Based routing abilitato per Gateway1 al sito1, in base al criterio di routing vocale dell'utente2         |
|Sito di rete diverso, sito abilitato per Location-Based routing (Utente3)    |Il trasferimento di chiamata può essere instradato solo attraverso Location-Based routing abilitato per Gateway1 al sito1, in base al criterio di routing vocale dell'Utente3         |L'inoltro di chiamata può essere instradato solo attraverso Location-Based routing abilitato per Gateway1 nel sito1, in base al criterio di routing vocale dell'utente3         |
|Sito di rete diverso, sito non abilitato per Location-Based routing (Utente4)    |Il trasferimento di chiamata può essere instradato solo attraverso Location-Based routing abilitato per Gateway1 nel sito1, in base al criterio di routing vocale di User4         |L'inoltro di chiamata può essere instradato solo attraverso Location-Based routing abilitato per Gateway1 nel sito1, in base al criterio di routing vocale di User4         |
|Rete interna sconosciuta (Utente5)     |Il trasferimento di chiamata può essere instradato solo attraverso Location-Based routing abilitato per Gateway1 nel sito1, in base al criterio di routing vocale dell'utente5         |L'inoltro di chiamata può essere instradato solo attraverso Location-Based routing abilitato per Gateway1 nel sito1, in base al criterio di routing vocale dell'utente5         |
|Rete esterna sconosciuta (Utente6)   |Il trasferimento di chiamata può essere instradato solo attraverso Location-Based routing abilitato per Gateway1 nel sito1, in base al criterio di routing vocale dell'utente6        |L'inoltro di chiamata può essere instradato solo attraverso Location-Based routing abilitato per Gateway1 al sito1, in base al criterio di routing vocale dell'utente6         |

### <a name="simultaneous-ringing"></a>Squillo simultaneo

Quando un utente abilitato per Location-Based Routing riceve una chiamata e ha abilitato lo squillo simultaneo, Location-Based Routing analizza la posizione del chiamante e gli endpoint delle parti chiamate per determinare se la chiamata deve essere instradata. Lo squillo simultaneo segue le stesse Location-Based di trasferimento di chiamata e inoltro. 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>Squillo simultaneo per un altro utente di Teams

La tabella seguente mostra se Location-Based instradamento simultaneo consente lo squillo simultaneo a diversi utenti per una chiamata PSTN in ingresso per l'utente1.

|Posizione endpoint utente di destinazione|Squillo simultaneo  |
|---------|---------|
|Stesso sito di rete dell'iniziatore (Utente2)   |Consentito         |
|Diverso sito di rete roaming abilitato per Location-Based routing (Utente3)   |Non consentito         |
|Sito di rete di roaming non abilitato per Location-Based routing remoto (Utente4)   |Non consentito        |
|Rete interna sconosciuta (Utente5)    | Non consentito        |
|Rete esterna sconosciuta (Utente6)    |Non consentito        |
|L'utente di destinazione è un numero PSTN    |La chiamata può essere instradata solo attraverso Location-Based routing abilitato per Gateway1 nel sito1, in base al criterio di routing vocale dell'utente1      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>Squillo simultaneo a un endpoint PSTN

La tabella seguente mostra Location-Based routing per una chiamata VOIP in ingresso dall'Utente1 situato in Site1 agli utenti in località diverse con squillo simultaneo impostato su un numero PSTN. 

|Posizione endpoint utente chiamata  |La destinazione dell'anello simultaneo è l'endpoint PSTN |
|---------|---------|
|Stesso sito di rete, sito abilitato per Location-Based routing (Utente2)    |La chiamata può essere instradata solo attraverso Location-Based Gateway1 di routing sul sito1, in base al criterio di routing vocale dell'utente2       |
|Diverso sito di rete abilitato per Location-Based (Utente3)    |La chiamata può essere instradata solo attraverso Location-Based Gateway di routing 1 nel sito1, in base al criterio di instradamento vocale dell'Utente3        |
|Sito di rete diverso non abilitato per Location-Based distribuzione (Utente4)    |La chiamata può essere instradata solo attraverso Location-Based Gateway1 di routing sul sito1, in base al criterio di routing vocale di User4         |
|Rete interna sconosciuta (Utente5)    |La chiamata può essere instradata solo attraverso Location-Based Gateway1 di routing sul sito1, in base al criterio di instradamento vocale dell'Utente5         |
|Rete esterna sconosciuta (Utente6)   |La chiamata può essere instradata solo attraverso Location-Based Gateway di routing 1 nel sito1, in base al criterio di routing vocale dell'utente6         |

#### <a name="inbound-calls-through-voice-app-auto-attendant-or-call-queue"></a>Chiamate in entrata tramite l'app vocale (Operatore automatico chiamata o coda di chiamata)

Le chiamate PSTN in ingresso da un gateway Location-Based routing abilitato sono autorizzate a connettersi a un operatore automatico o a una coda di chiamata. Gli utenti abilitati per Location-Based routing delle chiamate in ingresso possono ricevere trasferimenti di chiamata in ingresso da queste applicazioni solo quando si trovano nello stesso sito da cui proviene la chiamata PSTN in ingresso. 
 
L'inoltro di chiamata e lo squillo simultaneo agli utenti e PSTN sono consentiti per i trasferimenti di app vocali. Il completamento della chiamata al target è soggetto alle stesse regole di Location-Based routing elencate in precedenza.  
 
È consentito anche l'inoltro alla segreteria telefonica.  

### <a name="delegation"></a>Delega

Un utente di Teams può scegliere delegati che possono effettuare e ricevere chiamate per conto loro. Le funzionalità di delega in Teams sono interessate dal routing Location-Based come indicato di seguito: 
- Per le chiamate in uscita da un Location-Based delegato abilitato per conto di un delegante, si applicano le stesse regole. Il routing delle chiamate si basa sul criterio di autorizzazione delle chiamate del delegato, sul criterio di instradamento vocale e sulla posizione. Per altre informazioni, vedere [l'utente di Teams inserisce una chiamata in uscita alla rete PSTN.](#teams-user-places-an-outbound-call-to-the-pstn) 
- Per le chiamate PSTN in ingresso a un delegante, ai delegati si applicano le stesse regole di routing Location-Based applicate per l'inoltro di chiamata o lo squillo simultaneo ad altri utenti. Per altre informazioni, vedere L'utente di Teams trasferisce o inoltra le chiamate a un altro utente di [Teams,](#teams-user-transfers-or-forwards-call-to-another-teams-user)l'utente di Teams trasferisce o inoltra le chiamate [all'endpoint PSTN](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)e chiama [contemporaneamente.](#simultaneous-ringing) Quando un delegato imposta un endpoint PSTN come destinazione di squillo simultaneo, il criterio di instradamento vocale del delegato viene usato per instradare la chiamata al server PSTN. 
- Per la delega, è consigliabile che il delegante e i delegati associati si trovino nello stesso sito di rete. 

## <a name="other-planning-considerations"></a>Altre considerazioni sulla pianificazione

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>Modifiche apportate a una distribuzione di Location-Based distribuzione locale

I criteri di routing vocale del sito di rete non vengono più usati. Useremo invece i criteri di instradamento vocale dell'utente. Questo significa che per consentire agli utenti di eseguire il roaming ad altri siti, il criterio di routing vocale deve includere i gateway dei siti di roaming. 

### <a name="technical-considerations-for-location-based-routing"></a>Considerazioni tecniche per il routing in base alla posizione

Le subnet IPv4 e IPv6 sono supportate, ma hanno la precedenza quando si verifica una corrispondenza.

### <a name="client-support-for-location-based-routing"></a>Supporto client per Location-Based distribuzione

Sono supportati i client di Teams seguenti:
- Client desktop di Teams (Windows e Mac)
- Client di Teams per dispositivi mobili (iOS e Android)
- Telefoni IP di Teams

Il client Web di Teams e i client Skype for Business non sono supportati.

### <a name="capabilities-not-supported-by-location-based-routing"></a>Funzionalità non supportate dal routing in base alla posizione

Location-Based routing non è applicabile ai tipi di interazioni seguenti. Location-Based routing non viene applicato quando gli endpoint di Teams interagiscono con gli endpoint PSTN negli scenari seguenti: 
- Call park or retrieval of PSTN calls through Call Park 
- Un utente Skype for Business locale o un utente skype for Business online chiama un utente di Teams  

### <a name="location-based-routing-for-conferencing"></a>Location-Based routing per le conferenze

Un utente Location-Based instradamento automatico durante una chiamata PSTN non è autorizzato ad avviare una conferenza con un altro utente o un numero PSTN. È consentita la connessione agli operatori automatici o alle code di chiamata. Se l'utente dispone di una licenza per conferenze, l'utente deve avviare una conferenza con gli utenti pertinenti e chiamare la rete PSTN attraverso il bridge di conferenza per avviare una conferenza telefonica.  

### <a name="media-bypass-requirement-for-location-based-routing"></a>Requisito del bypass multimediale per Location-Based distribuzione

Se si distribuisce il Location-Based in India, è obbligatorio configurare anche il bypass multimediale. Per altre informazioni, vedere Pianificare il [bypass multimediale con il routing diretto](direct-routing-plan-media-bypass.md) e l'ottimizzazione del supporto locale per il routing [diretto.](direct-routing-media-optimization.md)

### <a name="direct-voice-over-ip-voip"></a>Direct Voice over IP (VoIP)

Le chiamate VoIP (Direct Voice over IP) non devono essere distribuite con apparecchiature di telefonia in India.

## <a name="next-steps"></a>Passaggi successivi

Passare a [Configurare le impostazioni di rete per Location-Based routing.](location-based-routing-configure-network-settings.md)

## <a name="related-topics"></a>Argomenti correlati

- [Abilitare l'instradamento basato sulla posizione per Instradamento diretto](location-based-routing-enable.md)
- [Impostazioni di rete per le funzionalità vocali cloud in Teams](cloud-voice-network-settings.md)
