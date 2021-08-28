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
description: Informazioni su come pianificare il Location-Based routing diretto.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3916eaad8834bc48c0bf937dd1ce561e720f5cf0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58631340"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>Pianificare l'instradamento basato sulla posizione per Instradamento diretto

## <a name="overview-of-location-based-routing"></a>Panoramica del Location-Based routing

In alcuni paesi e aree geografiche, è illegale ignorare il provider PSTN (Public Switched Telephone Network) per ridurre i costi delle chiamate a lunga distanza. Questo articolo descrive come usare il routing Location-Based per limitare il bypass a pedaggio per Microsoft Teams utenti in base alla loro posizione geografica. Questo articolo si applica solo Sistema telefonico routing diretto.

Ecco una panoramica del routing Location-Based e indicazioni utili per la pianificazione. Quando si è pronti per applicare e abilitare Location-Based routing, vedere:

- [Distribuire le impostazioni di rete per Location-Based routing](location-based-routing-configure-network-settings.md)
- [Abilitare l'instradamento basato sulla posizione per Instradamento diretto](location-based-routing-enable.md)

> [!NOTE]
> Location-Based routing non è disponibile nelle distribuzioni high Microsoft 365 Government Community Cloud (GCC) High o DoD.

Location-Based routing è una caratteristica che consente di limitare il bypass a pedaggio in base ai criteri e alla posizione geografica dell'utente al momento di una chiamata PSTN in ingresso o in uscita. Location-Based routing è progettato per fornire un meccanismo per impedire il bypass a pedaggio. Non deve essere usato come meccanismo per instradare dinamicamente le chiamate PSTN in base alla posizione dell'utente o potrebbero verificarsi conseguenze indesiderate.

Quando un Teams utente è abilitato per Location-Based routing, si applica quanto segue:

- Per effettuare una chiamata PSTN in uscita, è necessario che sia vera una delle condizioni seguenti:
    - L'endpoint dell'utente si trova in un sito di rete abilitato per Location-Based Routing e le chiamate in uscita attraverso il gateway corrispondente abilitato per Location-Based Routing. 
    - L'endpoint dell'utente si trova in un sito di rete non abilitato per il routing Location-Based e le chiamate in uscita attraverso un gateway non abilitato per Location-Based Routing.

    Le chiamate in uscita non sono consentite in altri scenari.

- Per ricevere una chiamata PSTN in ingresso, l'endpoint di risposta dell'utente deve trovarsi nello stesso sito di rete in cui la chiamata è in ingresso attraverso il gateway abilitato per Location-Based routing. In qualsiasi altro scenario, ad esempio se l'utente è in roaming, la chiamata non è consentita e viene instradata alle impostazioni di inoltro di chiamata dell'utente (in genere la segreteria telefonica).
- Per trasferire una chiamata PSTN a un altro utente Teams, l'endpoint dell'utente di destinazione deve trovarsi nello stesso sito di rete dell'utente che avvia il trasferimento. I trasferimenti non sono consentiti in altri scenari. 
- Per trasferire un altro Teams utente alla rete PSTN, la chiamata deve essere trasferita tramite un gateway abilitato per Location-Based Routing situato nello stesso sito di rete del chiamante iniziale. I trasferimenti non sono consentiti in altri scenari.

Location-Based routing usa le stesse definizioni di area di rete, sito e subnet Skype for Business Server rete. Quando il bypass a pagamento è limitato per una posizione, un amministratore associa ogni subnet IP e ogni gateway PSTN per tale posizione a un sito di rete. La posizione di un utente è determinata dalla subnet IP a cui sono connessi gli endpoint Teams dell'utente al momento di una chiamata PSTN. Un utente può avere più client Teams situati in siti diversi, nel qual caso Location-Based Routing applica il routing di ogni client separatamente a seconda della posizione dell'endpoint. 

Per acquisire familiarità con alcune delle terminologie di rete usate in questo articolo, vedere Impostazioni di rete per le funzionalità [vocali cloud in Teams](cloud-voice-network-settings.md).

## <a name="apply-location-based-routing"></a>Applicare Location-Based routing

È necessario applicare Location-Based routing a utenti, siti di rete e gateway PSTN.  

### <a name="apply-location-based-routing-at-the-user-location"></a>Applicare Location-Based routing nella posizione dell'utente

Come accennato in precedenza, Location-Based routing si applica solo agli utenti che sono impostati per il routing diretto. Location-Based routing non è applicabile agli utenti che sono impostati per il Piano chiamate. Gli utenti devono essere abilitati per Location-Based Routing se sono in stato di restrizione del bypass a pagamento, che controlla le condizioni in cui possono effettuare e ricevere chiamate PSTN e il gateway PSTN che può essere usato. Quando un utente abilitato per Location-Based Routing si trova in un sito abilitato per il routing Location-Based, l'utente deve effettuare chiamate tramite un gateway abilitato Location-Based Routing connesso al sito. 

Location-Based routing funziona determinando la posizione corrente dell'utente in base all'indirizzo IP dell'endpoint Teams dell'utente e applica le regole di conseguenza. La posizione di un utente abilitato per Location-Based routing può essere suddivisa in categorie nei modi seguenti: 
- **L'utente si trova nello stesso Location-Based sito abilitato per il routing associato al gateway PSTN a cui è assegnato il did.**<br>In questo scenario, l'utente si trova in un sito di rete noto abilitato per Location-Based Routing e il numero DID (Direct Inward Dial) dell'utente termina in un gateway PSTN nello stesso sito di rete. Ad esempio, l'utente si trova nel suo ufficio. 
- **L'utente si trova in un sito Location-Based sito abilitato per il routing non associato al gateway PSTN a cui è assegnato il did.**<br>In questo scenario, l'utente si trova in un sito di rete noto abilitato per il routing di Location-Based e tale sito non è associato al gateway PSTN a cui è assegnato il numero DID dell'utente. Ad esempio, l'utente si sposta in un altro ufficio.  
- **L'utente si trova in un sito interno non abilitato per Location-Based routing.** <br>In questo scenario, l'utente si trova in un sito di rete interna noto non abilitato per Location-Based routing. 
- **L'utente si trova in un sito sconosciuto.** 
    - L'utente si trova all'interno della rete interna non definita come sito di rete. 
    - L'utente si trova all'esterno della rete interna. Ad esempio, l'utente si trova su Internet a casa o in un bar. 

### <a name="apply-location-based-routing-at-the-network-site"></a>Applicare Location-Based routing sul sito di rete 
I siti di rete devono essere abilitati Location-Based routing per determinare quali gateway instradare Location-Based gli utenti abilitati per il routing durante il roaming. Se un utente abilitato per il routing Location-Based si trova in un sito abilitato per il routing Location-Based, solo il gateway PSTN abilitato per il routing Location-Based in quel sito può essere usato per le chiamate in uscita. Se un utente abilitato per Location-Based Routing viene instradato a un sito non abilitato per il routing Location-Based, qualsiasi gateway non abilitato per Location-Based Routing può essere usato per le chiamate in uscita.  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>Applicare Location-Based routing sul gateway PSTN 

I gateway sono associati ai siti per determinare dove si trova un utente abilitato Location-Based routing quando effettua o riceve una chiamata PSTN. I gateway devono essere abilitati per Location-Based routing per assicurarsi che sia sotto restrizioni di bypass a pagamento e non possano essere usati da utenti che non sono abilitati per Location-Based routing. Lo stesso gateway può essere associato a più siti e può essere configurato per essere abilitato per il routing Location-Based o non abilitato per il routing Location-Based, a seconda del sito.

## <a name="scenarios-for-location-based-routing"></a>Scenari per il routing in base alla posizione

Questa sezione descrive diversi scenari per limitare il bypass a pedaggio usando Location-Based Routing e confronta il modo in cui le chiamate vengono instradati per gli utenti che non sono abilitati per Location-Based Routing con gli utenti abilitati per Location-Based Routing.

- [Teams utente inserisce una chiamata in uscita alla rete PSTN](#teams-user-places-an-outbound-call-to-the-pstn)
- [Teams utente riceve una chiamata in ingresso dalla rete PSTN](#teams-user-receives-an-inbound-call-from-the-pstn)
- [Teams utente trasferisce o inoltra una chiamata a un altro Teams utente](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Teams utente trasferisce o inoltra una chiamata all'endpoint PSTN](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [Squillo simultaneo](#simultaneous-ringing)
- [Delega](#delegation)

Il diagramma seguente mostra le restrizioni abilitate Location-Based routing in ogni scenario. Gli utenti, i siti di rete e i gateway abilitati per Location-Based routing hanno un bordo intorno. Usare il diagramma come guida per comprendere il funzionamento Location-Based routing in ogni scenario.  

![Diagramma che mostra gli scenari per Location-Based routing](media/lbr-direct-routing.png "Diagramma che mostra gli scenari per Location-Based routing")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>Teams utente inserisce una chiamata in uscita alla rete PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Utente non abilitato per Location-Based routing

Un utente che non è abilitato per Location-Based Routing può effettuare chiamate in uscita usando qualsiasi gateway in qualsiasi sito non abilitato per il routing Location-Based tramite il criterio di routing vocale assegnato. Tuttavia, se un gateway è abilitato per Location-Based routing, l'utente non può effettuare chiamate in uscita tramite il gateway anche se è assegnato ai criteri di routing vocale. Se l'utente effettua il roaming in un sito abilitato per Location-Based Routing, può effettuare chiamate solo tramite i normali gateway di routing non abilitati per Location-Based Routing.
 
#### <a name="user-enabled-for-location-based-routing"></a>Utente abilitato per Location-Based routing
In confronto, il routing delle chiamate in uscita per gli utenti abilitati per Location-Based routing è influenzato dalla posizione di rete dell'endpoint dell'utente. La tabella seguente mostra in che modo Location-Based routing influisce sul routing delle chiamate in uscita di User1, a seconda della posizione di User1. 

|Posizione dell'endpoint User1  |Instradamento delle chiamate in uscita per Utente1  |
|---------|---------|
|Stesso sito in cui è assegnato il DID dell'utente, sito abilitato per Location-Based Routing (Sito1)      |Chiamata instradata tramite gateway abilitato per Location-Based Routing (GW1) in Site1, in base ai criteri di routing vocale dell'utente         |
|Sito diverso da quello in cui è assegnato il DID dell'utente, sito abilitato per Location-Based Routing (Sito2)    |Chiamata instradata tramite gateway abilitato per Location-Based Routing (GW2) nel sito di roaming Site2, in base ai criteri di routing vocale dell'utente        |
|Sito diverso da quello in cui è assegnato il DID dell'utente, sito non abilitato per Location-Based routing (Sito3)  |Chiamata instradata tramite gateway non abilitato per Location-Based Routing nel sito non abilitato per il routing Location-Based (GW3), in base ai criteri di routing vocale dell'utente       |
|Rete interna sconosciuta (Location4)    |  Chiamate PSTN non consentite       |
|Rete esterna sconosciuta (Location5)    | Chiamate PSTN non consentite        |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>Teams utente riceve una chiamata in ingresso dalla rete PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Utente non abilitato per Location-Based routing

Un utente che non è abilitato per Location-Based Routing può ricevere una chiamata in ingresso dal gateway non abilitata per il routing Location-Based da cui il numero DID assegnato è in ingresso. Se l'utente passa a un sito non abilitato per Location-Based routing, può comunque ricevere chiamate tramite i normali gateway PSTN.
  
#### <a name="user-enabled-for-location-based-routing"></a>Utente abilitato per Location-Based routing

In confronto, gli utenti abilitati per Location-Based Routing possono ricevere chiamate in ingresso solo dal gateway PSTN a cui è assegnato il proprio DID quando si trovano nello stesso sito. La tabella seguente mostra come User1 riceve le chiamate in ingresso quando User1 si sposta in posizioni di rete diverse. Se la chiamata non è instradata all'endpoint dell'utente, viene indirizzata alle impostazioni di inoltro di chiamata dell'utente, se sono configurate. In genere si tratta della segreteria telefonica.  

|Posizione dell'endpoint User1  |Instradamento delle chiamate in ingresso a User1  |
|---------|---------|
|Stesso sito in cui è assegnato il DID dell'utente, sito abilitato per Location-Based Routing (Sito1)   | Chiamate instradati all'endpoint dell'utente1 in Site1        |
|Sito diverso da quello in cui è assegnato il DID dell'utente, sito abilitato per Location-Based Routing (Sito2)    | Chiamate non instradati agli endpoint in Site2        |
|Sito diverso da quello in cui è assegnato il DID dell'utente, sito non abilitato per Location-Based routing (Sito3)    | Chiamate non instradati agli endpoint in Site3        |
|Rete interna sconosciuta (Location4)   | Chiamate non instradati agli endpoint in Location4        |
|Rete esterna sconosciuta (Location5)     | Chiamate non instradati agli endpoint in Location5        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>Teams utente trasferisce o inoltra una chiamata a un altro Teams utente

Quando è coinvolto un endpoint PSTN, Location-Based Routing analizza se uno o entrambi gli utenti sono abilitati per il routing Location-Based e determina se la chiamata deve essere trasferita o inoltrata a seconda della posizione di entrambi gli endpoint. 
 
Il trasferimento di chiamata richiede all'utente che avvia la chiamata di riprendere la chiamata mentre l'inoltro di chiamata non richiede la risposta alla chiamata iniziale. Questo significa che le chiamate possono essere inoltrate anche se l'utente 1 non è in una posizione in cui ricevere le chiamate in ingresso (vedere la tabella nella sezione [Teams)](#teams-user-receives-an-inbound-call-from-the-pstn) e le chiamate non possono essere trasferite se l'utente1 non riesce a ricevere la chiamata in ingresso. 

#### <a name="user-not-enabled-for-location-based-routing"></a>Utente non abilitato per Location-Based routing

Un utente che non è abilitato per Location-Based routing può trasferire o inoltrare chiamate PSTN ad altri utenti che non sono abilitati per Location-Based routing. L'utente in genere non sarà autorizzato a trasferire o inoltrare una chiamata PSTN a un utente abilitato per il routing Location-Based perché gli utenti abilitati per il routing Location-Based in genere possono essere posizionati in modo co-localizzato solo in gateway abilitati per il routing di Location-Based per le chiamate PSTN. L'eccezione si verifica quando un utente abilitato Location-Based routing esegue il roaming in un sito non abilitato per Location-Based routing. In questo scenario, la chiamata trasferita è consentita.  

Analogamente, un utente che non è abilitato per Location-Based Routing può ricevere solo una chiamata PSTN di trasferimento o inoltrata da un altro utente che non è abilitato per Location-Based Routing. 

#### <a name="user-enabled-for-location-based-routing"></a>Utente abilitato per Location-Based routing

In generale, il trasferimento e l'inoltro di chiamate PSTN in ingresso da un gateway abilitato per Location-Based Routing è consentito solo se l'utente di destinazione è abilitato per Location-Based Routing e si trova nello stesso sito. In caso contrario, il trasferimento e l'inoltro delle chiamate non sono consentiti. 

La tabella seguente mostra se l'inoltro di chiamata e i trasferimenti di chiamata sono consentiti, a seconda della posizione dell'utente di destinazione. In questa tabella User1, che si trova in Site1, avvia il trasferimento o l'inoltro ad altri utenti di Teams abilitati anche per Location-Based Routing e che si trovano in posizioni diverse.  

|Posizione dell'endpoint utente di destinazione|Utente1 avvia il trasferimento di chiamata |Utente1 avvia l'inoltro di chiamata|
|---------|---------|---------|
|Stesso sito di rete dell'iniziatore (Utente2)|Consentito|Consentito|
|Sito di rete diverso, sito abilitato per Location-Based routing (Utente3)|Non consentito|Non consentito|
|Sito di rete diverso, sito non abilitato per Location-Based routing (Utente4)|Non consentito|Non consentito|
|Rete interna sconosciuta (Utente5)| Non consentito|Non consentito|
|Rete esterna sconosciuta (Utente6)| Non consentito|Non consentito|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Teams utente trasferisce o inoltra una chiamata all'endpoint PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Utente non abilitato per Location-Based routing

- È consentito trasferire e inoltrare una chiamata PSTN a un altro numero PSTN. 
- Il trasferimento e l'inoltro di una chiamata VOIP in ingresso alla rete PSTN devono rispettare le restrizioni di bypass a pedaggio del chiamante. 
    - Se il chiamante non è abilitato per Location-Based routing, può essere trasferito a qualsiasi gateway PSTN non abilitato per Location-Based routing.
    - Se il chiamante è abilitato per Location-Based routing, può essere trasferito solo a un gateway abilitato per Location-Based routing situato nello stesso sito di rete. 

#### <a name="user-enabled-for-location-based-routing"></a>Utente abilitato per Location-Based routing

- Il trasferimento e l'inoltro in ingresso di una chiamata PSTN a un altro numero PSTN devono essere instradati allo stesso gateway abilitato per il routing Location-Based cui è arrivata la chiamata in ingresso. 
- Il trasferimento e l'inoltro di una chiamata VOIP in ingresso alla rete PSTN devono rispettare sia il chiamante che le restrizioni di bypass a pedaggio dell'utente. 
    - Se il chiamante non è abilitato per Location-Based routing, può essere trasferito a qualsiasi gateway PSTN non abilitato per Location-Based routing.
    - Se il chiamante è abilitato per Location-Based routing, può essere trasferito solo a un gateway abilitato Location-Based Routing situato nello stesso sito di rete.
 
La tabella seguente mostra in che modo Location-Based routing influisce sul routing di una chiamata VOIP da Utente1 in Sito1 agli utenti in posizioni diverse che trasferiscono o inoltrano la chiamata a un endpoint PSTN.  

|Utente che avvia il trasferimento o l'inoltro di chiamata  |Trasferimento a PSTN  |Inoltra a PSTN  |
|---------|---------|---------|
|Stesso sito di rete, sito abilitato per Location-Based routing (Utente2)   |Il trasferimento delle chiamate può essere instradato solo Location-Based gateway1 abilitato per il routing sul sito1, in base ai criteri di routing vocale di User2         |L'inoltro di chiamata può essere instradato solo tramite Location-Based routing abilitato gateway1 su Site1, in base ai criteri di routing vocale di User2         |
|Sito di rete diverso, sito abilitato per Location-Based routing (Utente3)    |Il trasferimento delle chiamate può essere instradato solo tramite Location-Based gateway1 abilitato per il routing sul sito1, in base ai criteri di routing vocale di User3         |L'inoltro di chiamata può essere instradato solo Location-Based gateway1 abilitato per il routing sul sito1, in base ai criteri di routing vocale di User3         |
|Sito di rete diverso, sito non abilitato per Location-Based routing (Utente4)    |Il trasferimento di chiamata può essere instradato solo Location-Based gateway1 abilitato per il routing sul sito1, in base ai criteri di routing vocale di User4         |L'inoltro di chiamata può essere instradato solo Location-Based gateway1 abilitato per il routing su Site1, in base ai criteri di routing vocale di User4         |
|Rete interna sconosciuta (Utente5)     |Il trasferimento di chiamata può essere instradato solo Location-Based gateway1 abilitato per il routing sul sito1, in base ai criteri di routing vocale di User5         |L'inoltro di chiamata può essere instradato solo tramite Location-Based gateway1 abilitato per il routing sul sito1, in base ai criteri di routing vocale di User5         |
|Rete esterna sconosciuta (Utente6)   |Il trasferimento delle chiamate può essere instradato solo Location-Based gateway1 abilitato per il routing sul sito1, in base ai criteri di routing vocale di User6        |L'inoltro di chiamata può essere instradato solo Location-Based gateway1 abilitato per il routing sul sito1, in base ai criteri di routing vocale di User6         |

### <a name="simultaneous-ringing"></a>Squillo simultaneo

Quando un utente abilitato per Location-Based Routing riceve una chiamata e ha attivato lo squillo simultaneo, Location-Based Routing analizza la posizione della parte chiamante e gli endpoint delle parti chiamate per determinare se la chiamata deve essere instradata. Lo squillo simultaneo segue le stesse regole Location-Based di trasferimento e inoltro di chiamata. 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>Squillo simultaneo per un altro Teams utente

La tabella seguente mostra se Location-Based routing consente lo squillo simultaneo a utenti diversi per una chiamata PSTN in ingresso per l'utente1.

|Posizione dell'endpoint utente di destinazione|Anello simultaneo  |
|---------|---------|
|Stesso sito di rete dell'iniziatore (Utente2)   |Consentito         |
|Sito di rete di roaming diverso abilitato per Location-Based routing (Utente3)   |Non consentito         |
|Sito di rete di roaming non abilitato per Location-Based routing (Utente4)   |Non consentito        |
|Rete interna sconosciuta (Utente5)    | Non consentito        |
|Rete esterna sconosciuta (Utente6)    |Non consentito        |
|L'utente di destinazione è un numero PSTN    |La chiamata può essere instradata solo Location-Based gateway1 abilitato per il routing sul sito1, in base ai criteri di routing vocale dell'utente1      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>Squillo simultaneo a un endpoint PSTN

La tabella seguente mostra il Location-Based routing per una chiamata VOIP in ingresso da Utente1 che si trova in Sito1 a utenti in posizioni diverse con squillo simultaneo impostato su un numero PSTN. 

|Posizione dell'endpoint utente chiamata  |La destinazione dell'anello simultaneo è l'endpoint PSTN |
|---------|---------|
|Stesso sito di rete, sito abilitato per Location-Based routing (Utente2)    |La chiamata può essere instradata solo tramite Location-Based Routing Gateway1 su Site1, in base ai criteri di routing vocale di User2       |
|Sito di rete diverso abilitato per Location-Based routing (Utente3)    |La chiamata può essere instradata solo tramite Location-Based Routing Gateway1 su Site1, in base ai criteri di routing vocale di User3        |
|Sito di rete diverso non abilitato per Location-Based routing (Utente4)    |La chiamata può essere instradata solo tramite Location-Based Routing Gateway1 su Site1, in base ai criteri di routing vocale di User4         |
|Rete interna sconosciuta (Utente5)    |La chiamata può essere instradata solo tramite Location-Based Gateway di routing1 su Site1, in base ai criteri di routing vocale di User5         |
|Rete esterna sconosciuta (Utente6)   |La chiamata può essere instradata solo tramite Location-Based Gateway di routing1 su Site1, in base ai criteri di routing vocale di User6         |

#### <a name="inbound-calls-through-voice-app-auto-attendant-or-call-queue"></a>Chiamate in ingresso tramite l'app vocale (Operatore automatico o coda di chiamata)

Le chiamate PSTN in ingresso da Location-Based gateway abilitato per il routing possono connettersi a un operatore automatico o a una coda di chiamata. Gli utenti abilitati Location-Based routing possono ricevere i trasferimenti di chiamata in ingresso da queste applicazioni solo quando si trovano nello stesso sito da cui proviene la chiamata PSTN in ingresso. 
 
L'inoltro di chiamata e lo squillo simultaneo agli utenti e alla rete PSTN sono consentiti per i trasferimenti di app vocali. Il completamento della chiamata alla destinazione è soggetto alle stesse regole Location-Based routing elencate in precedenza.  
 
È consentito anche l'inoltro alla segreteria telefonica.  

### <a name="delegation"></a>Delega

Un Teams può scegliere delegati che possono effettuare e ricevere chiamate per loro conto. Le funzionalità di delega in Teams sono interessate dal routing Location-Based come indicato di seguito: 
- Per le chiamate in uscita da Location-Based delegato abilitato per il routing per conto di un delegato, si applicano le stesse regole. Il routing delle chiamate si basa sui criteri di autorizzazione delle chiamate, sul criterio di routing vocale e sulla posizione del delegato. Per altre informazioni, vedere Teams utente inserisce una chiamata [in uscita alla rete PSTN.](#teams-user-places-an-outbound-call-to-the-pstn) 
- Per le chiamate PSTN in ingresso a un delegato, ai delegati si applicano anche le stesse regole di routing Location-Based che si applicano per l'inoltro di chiamata o lo squillo simultaneo ad altri utenti. Per altre informazioni, vedere Teams utente trasferisce o inoltra una chiamata a un altro utente [Teams,](#teams-user-transfers-or-forwards-call-to-another-teams-user)Teams trasferisce o inoltra chiamate all'endpoint [PSTN](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)e Squillo [simultaneo.](#simultaneous-ringing) Quando un delegato imposta un endpoint PSTN come ring target simultaneo, i criteri di routing vocale del delegato vengono usati per instradare la chiamata alla rete PSTN. 
- Per la delega, è consigliabile che il delegante e i delegati associati si trovino nello stesso sito di rete. 

## <a name="other-planning-considerations"></a>Altre considerazioni sulla pianificazione

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>Modifiche da una distribuzione di routing Location-Based locale

I criteri di routing vocale del sito di rete non vengono più usati. Viene invece utilizzato il criterio di routing vocale dell'utente. Questo significa che per consentire agli utenti di eseguire il roaming in altri siti, i criteri di routing vocale devono includere i gateway dei siti di roaming. 

### <a name="technical-considerations-for-location-based-routing"></a>Considerazioni tecniche per il routing in base alla posizione

Le subnet IPv4 e IPv6 sono supportate, tuttavia, IPv6 ha la precedenza quando si verifica una corrispondenza.

### <a name="client-support-for-location-based-routing"></a>Supporto client per Location-Based routing

Sono supportati Teams client di posta elettronica seguenti:
- Teams desktop (Windows e Mac)
- Teams client mobili (iOS e Android)
- Teams Telefoni IP

I Teams web client e Skype for Business non sono supportati.

### <a name="capabilities-not-supported-by-location-based-routing"></a>Funzionalità non supportate dal routing in base alla posizione

Location-Based routing non si applica ai tipi di interazioni seguenti. Location-Based routing non viene applicato quando gli endpoint Teams interagiscono con gli endpoint PSTN negli scenari seguenti: 
- Parcheggio di chiamata o recupero di chiamate PSTN tramite Call Park 
- Un utente locale Skype for Business o un utente Skype for Business online chiama un utente Teams locale  

### <a name="location-based-routing-for-conferencing"></a>Location-Based routing per le conferenze

Un Location-Based di routing abilitato per una chiamata PSTN non è autorizzato ad avviare una conferenza con un altro utente o numero PSTN. È consentita la connessione agli operatori automatici o alle code di chiamata. Se l'utente ha una licenza di conferenza, l'utente deve avviare una conferenza con gli utenti pertinenti e chiamare la rete PSTN tramite il bridge di conferenza per avviare una conferenza telefonica.  

### <a name="media-bypass-requirement-for-location-based-routing"></a>Requisito di bypass multimediale per Location-Based routing

Se si distribuisce il Location-Based routing in India, è necessario configurare anche il bypass multimediale. Per altre informazioni, vedere Pianificare il [bypass multimediale con Routing diretto](direct-routing-plan-media-bypass.md) e [Ottimizzazione multimediale locale per il routing diretto.](direct-routing-media-optimization.md)

### <a name="direct-voice-over-ip-voip"></a>VoIP (Direct Voice over IP)

Direct Voice over IP (VoIP) non deve essere distribuito con apparecchiature di telefonia in India.

## <a name="next-steps"></a>Passaggi successivi

Passare a [Configurare le impostazioni di rete per Location-Based routing](location-based-routing-configure-network-settings.md).

## <a name="related-topics"></a>Argomenti correlati

- [Abilitare l'instradamento basato sulla posizione per Instradamento diretto](location-based-routing-enable.md)
- [Impostazioni di rete per le funzionalità vocali cloud in Teams](cloud-voice-network-settings.md)
