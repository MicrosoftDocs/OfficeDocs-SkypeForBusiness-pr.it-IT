---
title: Pianificare l'instradamento basato sulla posizione per Instradamento diretto
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: roykuntz
search.appverid: MET150
description: Informazioni su come pianificare Location-Based routing per il routing diretto telefonico di Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 795433f832d57767a7937be1a9d3e7f31e73f240
ms.sourcegitcommit: 41a75f1ba5ceb09f8db7d468aa41b63a89ab9c30
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2022
ms.locfileid: "67647440"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>Pianificare l'instradamento basato sulla posizione per Instradamento diretto

In alcuni paesi e aree geografiche è illegale bypassare il provider PSTN (Public Switched Telephone Network) per ridurre i costi delle chiamate interurbane. 

Questo articolo descrive cosa occorre sapere per usare Location-Based Routing per limitare il bypass a pagamento per gli utenti di Microsoft Teams in base alla loro posizione geografica. Questo articolo si applica solo al routing diretto. Location-Based Routing non si applica al Piano per chiamate o alla Connessione operatore.

Quando si è pronti per abilitare Location-Based Routing, vedere:

- [Configurare le impostazioni di rete per l'instradamento basato sulla posizione](location-based-routing-configure-network-settings.md)
- [Distribuire le impostazioni di rete per Location-Based Routing](location-based-routing-configure-network-settings.md)
- [Abilitare l'instradamento basato sulla posizione per Instradamento diretto](location-based-routing-enable.md)

> [!NOTE]
> Non usare Location-Based Routing per instradare dinamicamente le chiamate PSTN in base alla posizione dell'utente. A tale scopo, potrebbero verificarsi risultati imprevisti.

## <a name="overview"></a>Panoramica

Location-Based Routing consente di limitare il bypass a pagamento per un utente in base ai criteri e alla posizione geografica dell'utente al momento di una chiamata PSTN in entrata o in uscita. 

Location-Based Routing usa la topologia di rete definita per area di rete, sito e subnet. Quando il bypass a pagamento è limitato per una località, associare ogni subnet IP e ogni gateway PSTN per tale posizione a un sito di rete. 

Al momento di una chiamata PSTN, la posizione di un utente è determinata dalla subnet IP a cui sono connessi gli endpoint di Teams dell'utente. Se un utente ha più client di Teams situati in siti diversi, Location-Based Routing applica il routing di ogni client separatamente a seconda della posizione degli endpoint di Teams.

Per altre informazioni sulle impostazioni di rete, vedere [Impostazioni di rete per le funzionalità vocali nel cloud in Teams](cloud-voice-network-settings.md).

Questo articolo presuppone che un sito di rete possa trovarsi in uno degli stati seguenti:

- **Abilitato** : un sito configurato con subnet e siti di rete tenant e abilitato per il routing Location-Based.

- **Non abilitato** : sito configurato con subnet e siti di rete tenant, ma non abilitato per il routing Location-Based.

- **Sconosciuto** : un sito non configurato con subnet e siti di rete tenant. In genere, tali siti sono interni alla rete aziendale, ma non configurati per impostazione grafica o esterni alla rete aziendale. In ogni caso, questi siti non sono abilitati per Location-Based routing. 

### <a name="toll-bypass-evaluation-and-outcome"></a>Valutazione e risultati di bypass a pedaggio

Quando si utilizza Location-Based routing, viene valutata una chiamata tra un utente di Teams e pstn per determinare se il bypass a pagamento è limitato. A seconda dei risultati, la chiamata verrà completata o non verrà completata. 

Se un utente è abilitato per Location-Based Routing e l'utente si trova in un sito in cui sono in vigore Location-Based Restrizioni di routing, il bypass a pagamento è limitato per tale utente. Teams utilizza le seguenti informazioni per determinare se il bypass a pagamento è limitato: 

- Se l'utente di Teams è abilitato per Location-Based Routing, come definito nei criteri per le chiamate di Teams dell'utente.

- Percorso del sito di rete endpoint dell'utente di Teams e se il sito è abilitato o meno per Location-Based Routing.

- Percorso del sito di rete del gateway PSTN usato dalla chiamata.

- Se il gateway PSTN usato dalla chiamata è stato abilitato per Location-Based Routing.

- Per gli scenari di trasferimento, il percorso della chiamata PSTN si basa sulle impostazioni di routing della persona che trasferisce la chiamata e sulle impostazioni di routing Location-Based dell'utente di Teams a cui viene trasferita la chiamata.  

- Per gli scenari di conferenze e chiamate di gruppo, sia che un utente di Teams per cui il bypass a pagamento è limitato sia o sia stato parte della chiamata.

Se una chiamata non può essere completata, l'utente di Teams riceve una notifica come segue:

- Per le chiamate PSTN in uscita, nella finestra della chiamata viene visualizzato il messaggio seguente: Chiamata non consentita a causa delle impostazioni dell'organizzazione.

- Per le chiamate PSTN in ingresso, la chiamata viene instradata in base alle impostazioni di inoltro di chiamata senza risposta dell'utente di Teams, in genere alla segreteria telefonica. Se l'utente di Teams non ha configurato le impostazioni di chiamata senza risposta, la chiamata si disconnetterà.

## <a name="apply-location-based-routing"></a>Applicare Location-Based routing

È necessario applicare Location-Based Routing a quanto segue:

- [Utenti](#apply-location-based-routing-at-the-user-location)
- [Siti di rete](#apply-location-based-routing-at-the-network-site)
- [Gateway PSTN](#apply-location-based-routing-at-the-pstn-gateway)

Tenere presente le procedure consigliate seguenti:

- Il gateway PSTN e il sito di rete associato al gateway devono essere entrambi abilitati per Location-Based Routing.

- Per effettuare chiamate tramite un gateway PSTN abilitato per Location-Based Routing, gli utenti devono essere abilitati anche per il routing Location-Based.

- Per consentire agli utenti abilitati per Location-Based routing di effettuare chiamate PSTN in uscita da un sito di rete sconosciuto, deve essere vero quanto segue:

  - La chiamata deve uscita da un gateway PSTN abilitato per Location-Based Routing.
  - Il gateway PSTN deve essere configurato con il flag GatewayLbrEnabledUserOverride impostato su True.


### <a name="apply-location-based-routing-at-the-user-location"></a>Applicare Location-Based routing nella posizione dell'utente

La restrizione per il bypass a pagamento controlla le condizioni in cui un utente può effettuare e ricevere chiamate PSTN e il gateway PSTN utilizzabile. 

Se un utente è sotto restrizione di bypass a pagamento, quell'utente deve essere abilitato per Location-Based Routing. Quando l'utente abilitato si trova in un sito abilitato per Location-Based Routing, l'utente deve effettuare chiamate tramite un gateway connesso al sito e abilitato per Location-Based Routing. 

Location-Based Routing funziona determinando la posizione corrente dell'utente in base all'indirizzo IP dell'endpoint Teams dell'utente e applica le regole di conseguenza. La posizione di un utente abilitato per Location-Based Routing può essere categorizzata nel modo seguente: 

- **L'utente si trova nello stesso Location-Based Sito abilitato per il routing associato al gateway PSTN a cui è assegnato DID.**<br>In questo scenario, l'utente si trova in un sito di rete configurato abilitato per Location-Based Routing e il numero DID (Direct Inward Dial) dell'utente termina in un gateway PSTN nello stesso sito di rete. Ad esempio, l'utente si trova nel suo ufficio. 

- **L'utente si trova in un altro Location-Based Sito abilitato per il routing non associato al gateway PSTN a cui è assegnato DID.**<br>In questo scenario l'utente si trova in un sito di rete configurato abilitato per Location-Based Routing e tale sito non è associato al gateway PSTN a cui è assegnato il numero DID dell'utente. Ad esempio, l'utente si sposta in un altro ufficio.  

- **L'utente si trova in un sito interno non abilitato per Location-Based Routing.** <br>In questo scenario l'utente si trova in un sito di rete configurato non abilitato per Location-Based Routing. 

- **L'utente si trova in un sito sconosciuto.** 
    - L'utente si trova all'interno della rete interna che non è definita come sito di rete. 
    - L'utente si trova all'esterno della rete interna. Ad esempio, l'utente si trova su Internet a casa o in un bar. 

### <a name="apply-location-based-routing-at-the-network-site"></a>Applicare Location-Based routing nel sito di rete 

Quando gli utenti abilitati per Location-Based Routing sono in roaming, i siti di rete abilitati per Location-Based Routing consentono di determinare quali gateway usare. Ad esempio:

- Se un utente abilitato per Location-Based Routing dei roaming a un sito abilitato per Location-Based Routing, solo il gateway PSTN abilitato per Location-Based Routing nel sito può essere usato per le chiamate in uscita. 

- Se un utente abilitato per Location-Based Routing dei roaming a un sito non abilitato per Location-Based Routing, qualsiasi gateway non abilitato per Location-Based Routing può essere usato per le chiamate in uscita.  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>Applicare Location-Based routing nel gateway PSTN  

Per applicare Location-Based Routing nel gateway PSTN, è necessario eseguire le operazioni seguenti:

- Abilitare il gateway per Location-Based Routing. I gateway devono essere abilitati per Location-Based Routing per assicurarsi che non possano essere usati da utenti non abilitati per Location-Based Routing.

- Assegnare un sito di rete al gateway.

Il sistema determina quindi se un determinato utente in un determinato sito è autorizzato a usare il gateway. 

Inoltre, se si imposta GatewayLbrEnabledUserOverride su True, gli utenti abilitati per il routing basato sulla posizione in siti sconosciuti, ad esempio gli utenti che lavorano a casa, possono effettuare chiamate PSTN in uscita.


## <a name="restriction-rules"></a>Regole di restrizione

Le regole di restrizione dipendono dal fatto che un utente di Teams sia o meno abilitato per Location-Based routing.

### <a name="user-is-enabled-for-location-based-routing"></a>L'utente è abilitato per Location-Based Routing

Quando un utente è abilitato per il routing Location-Based, si applica quanto segue:

- **Per effettuare una chiamata PSTN in uscita**, deve essere vera una delle condizioni seguenti:

  - L'endpoint dell'utente si trova in un sito abilitato per Location-Based Routing e chiamate in uscita tramite un gateway PSTN abilitato per Location-Based Routing nello stesso sito.  

  - L'endpoint dell'utente si trova in un sito sconosciuto e chiama il punto di uscita tramite un gateway PSTN abilitato per Location-Based routing. Il gateway PSTN è configurato con il parametro GatewayLbrEnabledUserOverride impostato su True.

  - L'endpoint dell'utente si trova in un sito non abilitato per Location-Based Routing e chiamate in uscita tramite un gateway PSTN non abilitato per Location-Based Routing.

- **Per ricevere una chiamata PSTN in ingresso**, deve essere vera una delle condizioni seguenti: 

   - L'endpoint di risposta dell'utente e il gateway PSTN attraverso cui è stato eseguito l'ingresso della chiamata devono trovarsi nello stesso sito abilitato per Location-Based Routing. Il gateway PSTN deve essere abilitato per Location-Based Routing.

   - L'endpoint di risposta dell'utente e il gateway PSTN attraverso cui è in ingresso la chiamata devono trovarsi nello stesso sito che non è abilitato per Location-Based Routing. Il gateway PSTN non deve essere abilitato per Location-Based Routing.  Questo scenario implica il reinstradamento della chiamata PSTN in ingresso all'ingresso tramite un altro gateway PSTN rispetto a quello normalmente usato per le chiamate in arrivo al numero di telefono dell'utente.

   - In qualsiasi altro scenario, ad esempio se l'utente è in roaming, la chiamata non è consentita e viene instradata alle impostazioni di inoltro di chiamata senza risposta dell'utente (in genere la segreteria telefonica).  
   
- **Per una chiamata VoIP 1:1 teams e il trasferimento a PSTN**, tenere presente quanto segue:

  - Il routing della chiamata, ovvero il gateway PSTN a cui egressare la chiamata, si basa sulle impostazioni di routing dell'utente che trasferisce la chiamata.

  - Se il trasferimento sarà consentito è basato su quanto segue:
  
    - Le impostazioni di routing Location-Based dell'utente trasferito a PSTN.
    - Percorso del sito di rete dell'endpoint.
    - Se la posizione è abilitata per Location-Based Routing.

    Il trasferimento sarà consentito se l'utente trasferito è in grado di effettuare la chiamata PSTN nella posizione corrente usando lo stesso gateway PSTN.

- **Per una chiamata PSTN in arrivo o in uscita e il trasferimento a un altro utente di Teams**, il trasferimento dipende dai seguenti:

   - Impostazioni di routing dell'utente che riceve la chiamata trasferita. 
   - Percorso del sito di rete dell'endpoint.
   - Se la posizione è abilitata per Location-Based Routing.

   Il trasferimento sarà consentito se la persona che riceve la chiamata trasferita è in grado di effettuare o ricevere la chiamata PSTN nella posizione corrente utilizzando il gateway PSTN usato dalla chiamata PSTN in corso.


### <a name="user-is-not-enabled-for-location-based-routing"></a>L'utente non è abilitato per Location-Based Routing

Quando un utente di Teams non è abilitato per Location-Based Routing, tutte le chiamate da e verso quell'utente devono essere instradate attraverso un gateway PSTN non abilitato per Location-Based Routing. Una chiamata in ingresso a un utente di questo tipo instradata attraverso un gateway PSTN abilitato per Location-Based Il routing verrà instradato alle impostazioni di inoltro di chiamata senza risposta dell'utente (in genere la segreteria telefonica).

### <a name="decision-flows-for-inbound-and-outbound-calls"></a>Flussi decisionali per le chiamate in entrata e in uscita

I diagrammi seguenti mostrano i flussi decisionali per le chiamate in ingresso e in uscita.

**Chiamate in ingresso**

![Diagramma che mostra l'LBR per le chiamate in ingresso](media/lbr-routing-inbound1.png "Diagramma che mostra scenari per Location-Based Routing")

**Chiamate in uscita**

![Diagramma che mostra l'LBR per le chiamate in uscita](media/lbr-routing-outbound1.png "Diagramma che mostra scenari per Location-Based Routing")


## <a name="scenarios-for-location-based-routing"></a>Scenari per il routing in base alla posizione

Questa sezione descrive diversi scenari per limitare il bypass a pagamento tramite Location-Based Routing. Gli scenari confrontano il modo in cui vengono instradate le chiamate per gli utenti che non sono abilitati per Location-Based Routing con utenti abilitati per Location-Based Routing.

- [L'utente di Teams effettua una chiamata in uscita alla rete PSTN](#teams-user-places-an-outbound-call-to-the-pstn)
- [L'utente di Teams riceve una chiamata in ingresso dalla rete PSTN](#teams-user-receives-an-inbound-call-from-the-pstn)
- [L'utente di Teams trasferisce o inoltra la chiamata a un altro utente di Teams](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [L'utente di Teams trasferisce o inoltra la chiamata all'endpoint PSTN](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [Squillo simultaneo](#simultaneous-ringing)
- [Delega](#delegation)

Il diagramma seguente mostra le restrizioni abilitate da Location-Based Routing in ogni scenario. Gli utenti, i siti di rete e i gateway abilitati per Location-Based Il routing è delimitato da un bordo. Usare il diagramma come guida per comprendere come funziona Location-Based routing in ogni scenario.  

![Diagramma che mostra scenari per il routing Location-Based.](media/lbr-direct-routing.png "Diagramma che mostra scenari per Location-Based Routing")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>L'utente di Teams effettua una chiamata in uscita alla rete PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Utente non abilitato per Location-Based Routing

Un utente non abilitato per Location-Based Routing può effettuare chiamate in uscita usando un gateway in qualsiasi sito non abilitato per Location-Based Routing tramite i criteri di routing vocale assegnati. Tuttavia, se un gateway è abilitato per Location-Based Routing, l'utente non può effettuare chiamate in uscita tramite il gateway anche se è assegnato ai criteri di routing vocale. Se l'utente effettua il roaming in un sito abilitato per Location-Based Routing, può effettuare chiamate solo attraverso i normali gateway di routing non abilitati per Location-Based Routing.
 
#### <a name="user-enabled-for-location-based-routing"></a>Utente abilitato per Location-Based Routing

Il routing delle chiamate in uscita per gli utenti abilitati per Location-Based Routing è influenzato dal percorso di rete dell'endpoint dell'utente. La tabella seguente mostra in che modo Location-Based routing influisce sul routing delle chiamate in uscita di User1, a seconda della posizione di User1. 

|Posizione dell'endpoint User1  |Routing delle chiamate in uscita per Utente1  |
|---------|---------|
|Stesso sito in cui è assegnato IL DID dell'utente, sito abilitato per Location-Based Routing (Sito1)      |Chiamata instradata tramite gateway abilitato per Location-Based Routing (GW1) presso Site1, in base ai criteri di routing vocale dell'utente         |
|Sito diverso da quello in cui è assegnato il DID dell'utente, abilitato per Location-Based Routing (Sito2)    |Chiamata instradata attraverso un gateway abilitato per Location-Based Routing (GW2) presso il roaming di Site2, in base ai criteri di routing vocale dell'utente        |
|Sito diverso da quello in cui è assegnato il DID dell'utente, sito non abilitato per Location-Based Routing (Sito3)  |Chiamata instradata attraverso un gateway non abilitato per Location-Based Routing in un sito non abilitato per Location-Based Routing (GW3), in base ai criteri di routing vocale dell'utente       |
|Rete interna sconosciuta (Posizione4)    |  Chiamate PSTN non consentite a meno che gateway non abbia GatewayLbrEnabledUserOverride impostato su True       |
|Rete esterna sconosciuta (Posizione5)    | Chiamate PSTN non consentite a meno che gateway non abbia GatewayLbrEnabledUserOverride impostato su True       |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>L'utente di Teams riceve una chiamata in ingresso dalla rete PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Utente non abilitato per Location-Based Routing

Un utente non abilitato per Location-Based Routing può ricevere una chiamata in ingresso dal gateway non abilitata per Location-Based Routing da cui viene ingressi il numero DID assegnato. Se l'utente esegue il roaming in un sito non abilitato per Location-Based routing, può comunque ricevere chiamate tramite i normali gateway PSTN.
  
#### <a name="user-enabled-for-location-based-routing"></a>Utente abilitato per Location-Based Routing

A confronto, gli utenti abilitati per Location-Based Routing possono ricevere chiamate in ingresso solo dal gateway PSTN a cui è assegnato il proprio DID quando si trovano nello stesso sito. La tabella seguente mostra in che modo User1 riceve le chiamate in ingresso quando l'utente 1 si sposta in percorsi di rete diversi. Se la chiamata non viene instradata all'endpoint dell'utente, passa alle impostazioni di inoltro di chiamata senza risposta dell'utente, se configurate. In genere, le chiamate vengono inoltrate alla segreteria telefonica.  

|Posizione dell'endpoint User1  |Routing delle chiamate in ingresso a Utente1  |
|---------|---------|
|Stesso sito in cui è assegnato il did dell'utente, sito abilitato per Location-Based Routing (Sito1)   | Chiamate instradate all'endpoint dell'utente1 in Sito1        |
|Sito diverso da quello in cui è assegnato il DID dell'utente, abilitato per Location-Based Routing (Sito2)    | Chiamate non indirizzate agli endpoint in Site2        |
|Sito diverso da quello in cui è assegnato il DID dell'utente, sito non abilitato per Location-Based Routing (Sito3)    | Chiamate non indirizzate agli endpoint in Site3        |
|Rete interna sconosciuta (Posizione4)   | Chiamate non indirizzate agli endpoint in Posizione4        |
|Rete esterna sconosciuta (Posizione5)     | Chiamate non indirizzate agli endpoint in Posizione5        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>L'utente di Teams trasferisce o inoltra la chiamata a un altro utente di Teams

Quando è coinvolto un endpoint PSTN, Location-Based Routing analizza se uno o entrambi gli utenti sono abilitati per Location-Based Routing e determina se la chiamata deve essere trasferita o inoltrata a seconda della posizione di entrambi gli endpoint. 
 
Il trasferimento di chiamata richiede che l'utente che avvia la chiamata risponda mentre l'inoltro di chiamata non richiede la risposta alla chiamata iniziale. Le chiamate possono essere inoltrate anche se l'utente 1 non è in una posizione per ricevere chiamate in ingresso (vedere la tabella [dell'utente di Teams riceve una chiamata in ingresso dalla sezione PSTN](#teams-user-receives-an-inbound-call-from-the-pstn) ) e le chiamate non possono essere trasferite se l'Utente1 non è in grado di ricevere la chiamata in ingresso. 

#### <a name="user-not-enabled-for-location-based-routing"></a>Utente non abilitato per Location-Based Routing

Un utente non abilitato per Location-Based Routing può trasferire o inoltrare chiamate PSTN ad altri utenti non abilitati per Location-Based Routing. Gli utenti abilitati per il routing Location-Based in genere si trovano in Location-Based Gateway abilitati per il routing per le chiamate PSTN. Di conseguenza, gli utenti non abilitati non sono autorizzati a trasferire o inoltrare una chiamata PSTN a un utente abilitato per Location-Based Routing. L'eccezione si verifica quando un utente abilitato per il routing Location-Based esegue il roaming a un sito non abilitato per Location-Based Routing. In questo scenario, la chiamata trasferita è consentita.  

Analogamente, un utente non abilitato per Location-Based Routing può ricevere solo un trasferimento o una chiamata PSTN inoltrata da un altro utente non abilitato per Location-Based Routing. 

#### <a name="user-enabled-for-location-based-routing"></a>Utente abilitato per Location-Based Routing

Il trasferimento e l'inoltro di chiamate PSTN in ingresso da un gateway abilitato per Location-Based Routing è consentito solo se l'utente di destinazione è abilitato per Location-Based Routing e si trova nello stesso sito. In caso contrario, il trasferimento e l'inoltro di chiamate non sono consentiti. 

La tabella seguente mostra se l'inoltro di chiamata e i trasferimenti di chiamata sono consentiti, a seconda della posizione dell'utente di destinazione. In questa tabella, User1, che si trova in Site1, avvia il trasferimento o l'inoltro ad altri utenti di Teams che sono abilitati anche per Location-Based Routing e che si trovano in posizioni diverse.  

|Posizione endpoint utente di destinazione|Utente1 avvia il trasferimento di chiamata |Utente1 avvia l'inoltro di chiamata|
|---------|---------|---------|
|Stesso sito di rete dell'iniziatore (Utente2)|Consentito|Consentito|
|Sito di rete diverso, sito abilitato per Location-Based Routing (Utente3)|Non consentito|Non consentito|
|Sito di rete diverso, sito non abilitato per Location-Based Routing (Utente4)|Non consentito|Non consentito|
|Rete interna sconosciuta (Utente5)| Non consentito|Non consentito|
|Rete esterna sconosciuta (Utente6)| Non consentito|Non consentito|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>L'utente di Teams trasferisce o inoltra la chiamata all'endpoint PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Utente non abilitato per Location-Based Routing

- È consentito il trasferimento e l'inoltro di una chiamata PSTN a un altro numero PSTN. 

- Il trasferimento e l'inoltro di una chiamata VOIP in ingresso al PSTN devono rispettare le restrizioni di bypass a pagamento del chiamante. 

    - Se il chiamante non è abilitato per Location-Based Routing, può essere trasferito a qualsiasi gateway PSTN non abilitato per Location-Based Routing.
    - Se il chiamante è abilitato per Location-Based Routing, può essere trasferito solo a un gateway abilitato per il routing Location-Based situato nello stesso sito di rete. 

#### <a name="user-enabled-for-location-based-routing"></a>Utente abilitato per Location-Based Routing

- Il trasferimento e l'inoltro di una chiamata PSTN in ingresso a un altro numero PSTN devono essere instradati allo stesso Location-Based Gateway abilitato per il routing in cui è arrivata la chiamata in ingresso.

- Il trasferimento e l'inoltro di una chiamata VOIP in ingresso al PSTN devono rispettare sia il chiamante che le restrizioni di bypass a pagamento dell'utente. 

    - Se il chiamante non è abilitato per Location-Based Routing, può essere trasferito a qualsiasi gateway PSTN non abilitato per Location-Based Routing.

    - Se il chiamante è abilitato per Location-Based Routing, può essere trasferito solo a un gateway abilitato per il routing Location-Based situato nello stesso sito di rete.
 
La tabella seguente mostra come Location-Based Routing influisca sul routing di una chiamata VOIP da Location-Based Routing abilitato User1 in Site1 a utenti in posizioni diverse che trasferiscono o inoltrano la chiamata a un endpoint PSTN.  

|L'utente avvia il trasferimento o l'inoltro di chiamata  |Trasferire o inoltrare a PSTN  |
|---------|---------|
|Stesso sito di rete, sito abilitato per Location-Based Routing (Utente2)   |La chiamata PSTN risultante sarà consentita solo se il percorso calcolato basato sui criteri di routing vocale di User2 genera un percorso attraverso Location-Based Gateway abilitato per il routing1 in Sito1         |
|Sito di rete diverso, sito abilitato per Location-Based Routing (Utente3)    |La chiamata PSTN risultante sarà consentita solo se il percorso calcolato basato sui criteri di routing vocale dell'Utente3 genera un percorso attraverso Location-Based Gateway abilitato per il routing1 in Sito1 |
|Sito di rete diverso, sito non abilitato per Location-Based Routing (Utente4)    |La chiamata PSTN risultante sarà consentita solo se il percorso calcolato basato sui criteri di routing vocale dell'Utente4 genera un percorso attraverso Location-Based Gateway abilitato per il routing1 in Sito1          |
|Rete interna sconosciuta (Utente5)     |La chiamata PSTN risultante sarà consentita solo se il percorso calcolato basato sui criteri di routing vocale dell'Utente5 genera un percorso attraverso Location-Based Gateway abilitato per il routing1 in Sito1          |
|Rete esterna sconosciuta (Utente6)   |La chiamata PSTN risultante sarà consentita solo se il percorso calcolato basato sui criteri di routing vocale dell'Utente6 genera un percorso attraverso Location-Based Gateway abilitato per il routing1 in Sito1          |

### <a name="simultaneous-ringing"></a>Squillo simultaneo

Quando un utente abilitato per Location-Based Routing riceve una chiamata e lo squillo simultaneo è abilitato, Location-Based Routing analizza la posizione del chiamante e gli endpoint delle parti chiamate per determinare se la chiamata deve essere instradata. Lo squillo simultaneo segue le stesse regole di Location-Based dei trasferimenti e degli inolti delle chiamate. 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>Squillo simultaneo per un altro utente di Teams

La tabella seguente mostra se Location-Based Routing consente lo squillo simultaneo a utenti diversi per una chiamata PSTN in ingresso per User1.

|Posizione endpoint utente di destinazione|Squillo simultaneo  |
|---------|---------|
|Stesso sito di rete dell'iniziatore (Utente2)   |Consentito         |
|Diverso sito di rete in roaming abilitato per Location-Based Routing (Utente3)   |Non consentito         |
|Sito di rete in roaming non abilitato per Location-Based Routing (Utente4)   |Non consentito        |
|Rete interna sconosciuta (Utente5)    | Non consentito        |
|Rete esterna sconosciuta (Utente6)    |Non consentito        |
|L'utente di destinazione è un numero PSTN    |La chiamata può essere instradata solo tramite Location-Based Gateway abilitato per il routing1 nel sito1, in base ai criteri di routing vocale dell'utente1      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>Squillo simultaneo a un endpoint PSTN

La tabella seguente mostra Location-Based Comportamento di routing per una chiamata VoIP in ingresso da Location-Based Utente abilitato per il routing1 situato in Site1 a utenti in posizioni diverse, con lo squillo simultaneo impostato su un numero PSTN. 

|Posizione dell'endpoint utente chiamata  |La destinazione dell'anello simultaneo è l'endpoint PSTN |
|---------|---------|
|Stesso sito di rete, sito abilitato per Location-Based Routing (Utente2)    |La chiamata PSTN risultante sarà consentita solo se il percorso calcolato basato sui criteri di routing vocale di User2 genera un percorso attraverso Location-Based Gateway abilitato per il routing1 in Sito1        |
|Sito di rete diverso abilitato per Location-Based Routing (Utente3)    |La chiamata PSTN risultante sarà consentita solo se il percorso calcolato basato sui criteri di routing vocale dell'Utente3 genera un percorso attraverso Location-Based Gateway abilitato per il routing1 in Sito1         |
|Sito di rete diverso non abilitato per Location-Based Routing (Utente4)    |La chiamata PSTN risultante sarà consentita solo se il percorso calcolato basato sui criteri di routing vocale dell'Utente4 genera un percorso attraverso Location-Based Gateway abilitato per il routing1 in Sito1          |
|Rete interna sconosciuta (Utente5)    |La chiamata PSTN risultante sarà consentita solo se il percorso calcolato basato sui criteri di routing vocale dell'Utente5 genera un percorso attraverso Location-Based Gateway abilitato per il routing1 in Sito1          |
|Rete esterna sconosciuta (Utente6)   |La chiamata PSTN risultante sarà consentita solo se il percorso calcolato basato sui criteri di routing vocale dell'Utente6 genera un percorso attraverso Location-Based Gateway abilitato per il routing1 in Sito1          |

#### <a name="inbound-calls-through-voice-apps-auto-attendant-or-call-queue"></a>Chiamate in ingresso attraverso le app vocali (Operatore automatico o Coda di chiamata)

Le chiamate PSTN in ingresso da un gateway abilitato per il routing Location-Based possono connettersi a un operatore automatico o a una coda di chiamata. 

Gli utenti abilitati per Location-Based Routing sono supportati per ricevere i trasferimenti di chiamata in ingresso per queste applicazioni quando si trovano nello stesso sito da cui proviene la chiamata PSTN in ingresso.
 
L'inoltro di chiamata e lo squillo simultaneo agli utenti e PSTN sono consentiti per i trasferimenti di app vocali. Il completamento della chiamata alla destinazione è soggetto alle stesse regole di routing Location-Based elencate in precedenza.  
 
È anche consentito l'inoltro alla segreteria telefonica.  

### <a name="delegation"></a>Delega

Un utente di Teams può scegliere delegati che possono effettuare e ricevere chiamate per proprio conto. Le funzionalità di delega in Teams sono interessate dal routing Location-Based come segue: 

- Per le chiamate in uscita da un delegato abilitato per il routing Location-Based per conto di un delegante, si applicano le stesse regole. Il routing delle chiamate si basa sui criteri di autorizzazione alle chiamate, sui criteri di routing vocale e sulla posizione del delegato. Per altre informazioni, vedere [L'utente di Teams effettua una chiamata in uscita alla rete PSTN](#teams-user-places-an-outbound-call-to-the-pstn). 

- Per le chiamate PSTN in ingresso a un delegante, le stesse regole di routing Location-Based che si applicano per l'inoltro di chiamata o lo squillo simultaneo ad altri utenti si applicano anche ai delegati. Per altre informazioni, vedere [Trasferimento o inoltro di chiamata a un altro utente di Teams da parte dell'utente di Teams](#teams-user-transfers-or-forwards-call-to-another-teams-user), [trasferimento o inoltro della chiamata all'endpoint PSTN](#teams-user-transfers-or-forwards-call-to-pstn-endpoint) e [Squillo simultaneo](#simultaneous-ringing). Quando un delegato imposta un endpoint PSTN come destinazione squillo simultaneo, il criterio di routing vocale del delegato viene usato per instradare la chiamata alla rete PSTN. 

- Per la delega, Microsoft consiglia che il delegante e i delegati associati si trovino nello stesso sito di rete. 

## <a name="other-planning-considerations"></a>Altre considerazioni sulla pianificazione

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>Modifiche da una distribuzione di routing Location-Based locale

I criteri di routing vocale del sito di rete non vengono più usati. Al contrario, usiamo i criteri di routing vocale dell'utente. Per consentire agli utenti di eseguire il roaming in altri siti, il criterio di routing vocale deve includere i gateway dei siti in roaming. 

### <a name="technical-considerations-for-location-based-routing"></a>Considerazioni tecniche per il routing in base alla posizione

Le subnet IPv4 e IPv6 sono supportate, tuttavia, IPv6 ha la precedenza durante il controllo di una corrispondenza.

### <a name="client-support-for-location-based-routing"></a>Supporto client per Location-Based Routing

Sono supportati i client di Teams seguenti:
- Client desktop di Teams (Windows e Mac)
- Client di Teams per dispositivi mobili (iOS e Android)
- Telefoni IP di Teams

Il client Web di Teams e i client Skype for Business non sono supportati.

### <a name="capabilities-not-supported-by-location-based-routing"></a>Funzionalità non supportate dal routing in base alla posizione

Location-Based Routing non si applica ai tipi di interazioni seguenti. Location-Based Routing non viene applicato quando gli endpoint di Teams interagiscono con gli endpoint PSTN negli scenari seguenti: 

- Parcheggio di chiamata o recupero delle chiamate PSTN tramite Parcheggio di chiamata 

- Un utente Skype for Business locale o un utente di Skype for Business Online chiama un utente di Teams  

### <a name="location-based-routing-for-conferencing"></a>Location-Based Routing per le conferenze

Un utente abilitato per il routing Location-Based senza licenza per i servizi di audioconferenza in una chiamata PSTN non è autorizzato ad avviare una conferenza con un altro utente o numero PSTN. È consentita la connessione agli operatori automatici o alle code di chiamata.

Se l'utente dispone di una licenza per i servizi di audioconferenza, l'utente deve avviare una conferenza con gli utenti interessati e chiamare la rete PSTN tramite il bridge di conferenza per avviare una conferenza telefonica. Se l'utente è già in una chiamata PSTN, può aggiungere un altro utente o un altro numero PSTN alla chiamata tramite l'escalation della chiamata utilizzando il bridge di conferenza per effettuare la chiamata in uscita.

In una conferenza telefonica avviata da un utente senza licenza per i servizi di audioconferenza, l'aggiunta di partecipanti PSTN non è consentita se nella conferenza telefonica è presente o è stato almeno un utente abilitato per il routing Location-Based. Se almeno un partecipante PSTN partecipa a una conferenza telefonica o lo partecipava prima di qualsiasi Location-Based I partecipanti abilitati al routing sono stati invitati a partecipare alla chiamata, ad esempio Location-Based Non è possibile aggiungere alla chiamata partecipanti abilitati per il routing.

Se l'utente abilitato per il routing Location-Based partecipa alla conferenza telefonica da un sito interno non abilitato per Location-Based Routing, le restrizioni nel paragrafo precedente non vengono applicate. 

I servizi di conferenza on-network per i servizi di audioconferenza NON devono essere distribuiti con apparecchiature di telefonia in India.

Un utente abilitato per il routing Location-Based in una chiamata PSTN non è autorizzato a unire la chiamata con un'altra chiamata.

### <a name="media-bypass-requirement-for-location-based-routing"></a>Requisito per il bypass multimediale per il routing Location-Based

Se stai distribuendo Location-Based Routing in India, è necessario configurare anche il bypass multimediale. Per altre informazioni, vedi [Pianificare il bypass multimediale con routing diretto](direct-routing-plan-media-bypass.md) e [Ottimizzazione multimediale locale per il routing diretto](direct-routing-media-optimization.md).

### <a name="direct-voice-over-ip-voip"></a>Direct Voice over IP (VoIP)

Direct Voice over IP (VoIP) non deve essere distribuito con alcun dispositivo di telefonia in India.


## <a name="related-articles"></a>Articoli correlati

- [Abilitare l'instradamento basato sulla posizione per Instradamento diretto](location-based-routing-enable.md)
- [Impostazioni di rete per le funzionalità voce cloud in Teams](cloud-voice-network-settings.md)
