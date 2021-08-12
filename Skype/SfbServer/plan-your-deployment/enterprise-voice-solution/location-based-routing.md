---
title: Pianificare il routing Location-Based in Skype for Business
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
ms.assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
description: Pianificazione del routing basato sulla posizione in Skype for Business Server VoIP aziendale, inclusa l'interazione con squilli e delega simultanei e scenari supportati per il routing basato sulla posizione.
ms.openlocfilehash: 3d76fad2b87c850e18bf5d152234dea4d1321a3ed2e123be694e6a1f107f58ae
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286625"
---
# <a name="plan-for-location-based-routing-in-skype-for-business"></a>Pianificare il routing Location-Based in Skype for Business

Pianificazione del routing basato sulla posizione in Skype for Business Server VoIP aziendale, inclusa l'interazione con squilli e delega simultanei e scenari supportati per il routing basato sulla posizione.

Location-Based routing consente di limitare il routing delle chiamate tra gli endpoint VoIP e gli endpoint PSTN in base alla posizione delle parti nella chiamata. Location-Based Routing è una funzionalità di gestione delle chiamate che controlla il modo in cui le chiamate vengono instradati da Skype for Business Server. Applica le regole di autorizzazione delle chiamate per stabilire se le chiamate possono essere instradati agli endpoint PBX o PSTN in base alla Skype for Business geografica del chiamante.

Location-Based routing introduce un nuovo set di regole che modifica il routing delle chiamate PSTN nazionali e internazionali per evitare il bypass a pedaggio. Location-Based routing offre la flessibilità di ambito di queste regole a aree specifiche, gateway specifici o solo a un set specifico di utenti.

Gli scenari seguenti illustrano i principali tipi di restrizioni Location-Based routing può applicare:

- Egress chiamate - Il routing di Location-Based può imporre l'uscita delle chiamate in uscita verso un gateway PSTN che si trova nella stessa area in cui il chiamante deve impedire il bypass a pagamento PSTN, impedendo così l'uscita delle chiamate a un gateway PSTN che si trova in un'area diversa del chiamante.

- Chiamate in ingresso - Il routing Location-Based può impedire alle chiamate PSTN in arrivo di squillare gli endpoint Skype for Business se il gateway PSTN che instrada la chiamata in arrivo non si trova nella stessa area dell'utente Skype for Business chiamato.

- Aree sconosciute- Il routing Location-Based limita le chiamate PSTN in ingresso e in uscita verso e da utenti che si trovano in posizioni indeterminate ,ad esempio utenti remoti che si connettono da Internet o si trovano in aree sconosciute.

- Aree internazionali: Location-Based routing applica il routing delle chiamate in uscita tramite gateway PSTN internazionali se non è possibile trovare un gateway locale alla posizione dell'utente.

## <a name="guidance-for-where-to-apply-location-based-routing"></a>Indicazioni su dove applicare Location-Based routing

Location-Based routing a seconda della situazione può essere applicato nella posizione del sito di rete dell'endpoint dell'utente o nel percorso del sito di rete del gateway PSTN. In questo argomento vengono fornite indicazioni su come Location-Based routing.

### <a name="applying-location-based-routing-at-the-users-location"></a>Applicazione Location-Based routing nella posizione dell'utente

Location-Based Routing sfrutta le stesse aree di rete, siti e subnet definiti in Skype for Business Server utilizzati da E9-1-1, CAC e Media Bypass per applicare restrizioni di routing delle chiamate per impedire il bypass a pedaggio PSTN. La posizione di un utente è determinata dalla subnet IP degli endpoint Skype for Business dell'utente da cui sono connessi. Ogni subnet IP è associata a un sito di rete, che viene aggregata in aree di rete definite dall'amministratore. Location-Based il routing viene applicato in base al sito di rete dell'utente.

Location-Based le regole di routing vengono applicate in base al sito di rete, ovvero un determinato set di regole verrà applicato a tutti gli endpoint abilitati per il routing Location-Based che si trovano all'interno dello stesso sito di rete. Gli amministratori possono applicare Location-Based routing ai siti di rete che lo richiedono.

I criteri di routing vocale possono essere definiti in base al sito di rete per definire un determinato gateway PSTN che deve essere utilizzato da tutti gli utenti che si trovano nel sito di rete per chiamare i numeri di telefono PSTN. Tali criteri di routing vocale avranno la precedenza sul routing definito dal criterio vocale dell'utente quando l'utente si trova in un sito di rete abilitato per il routing Location-Based e impedirà il routing delle chiamate tramite altri gateway PSTN abilitati per il routing Location-Based. Quando un Skype for Business utente esegue una chiamata PSTN, i criteri vocali dell'utente determinano se l'utente può essere autorizzato a eseguire la chiamata. Se i criteri vocali dell'utente consentono all'utente di eseguire la chiamata, Location-Based routing determina da quale gateway PSTN deve essere in uscita la chiamata. Location-Based routing effettua questa determinazione in base alla posizione dell'utente.

Una posizione utente può essere categorizzata nei modi seguenti:

- L'utente si trova in un sito di rete noto abilitato per Location-Based Routing e il suo numero DID (Direct Inward Dial) termina su un gateway PSTN collocato nello stesso sito di rete (ad esempio office). Il routing delle chiamate in uscita verrà attraverso il criterio di routing vocale del sito di rete in cui si trova l'utente. Le chiamate PSTN in arrivo all'utente vengono instradati agli endpoint che si trovano nello stesso sito di rete del gateway PSTN.

- L'utente si trova in un sito di rete noto diverso dal sito di rete in cui si trova il gateway PSTN. (ad esempio, l'utente si è recato in un altro ufficio aziendale). Il routing delle chiamate in uscita utilizza il criterio di routing vocale del sito di rete in cui si trova l'utente. Le chiamate PSTN in arrivo all'utente non verranno instradati agli endpoint che si trovano in siti diversi rispetto al gateway PSTN per impedire il bypass del numero di caselle PSTN.

- Quando un utente si trova in un sito di rete sconosciuto alla distribuzione di Skype for Business Server, il routing delle chiamate in uscita si baserà sul criterio vocale assegnato all'utente ai gateway PSTN non associati alle restrizioni di routing Location-Based. Le chiamate PSTN in arrivo non verranno instradati agli endpoint che si trovano in siti di rete sconosciuti per impedire il bypass dei numeri a pagamento PSTN.

### <a name="applying-location-based-routing-at-the-pstn-gateways-location"></a>Applicazione Location-Based routing nella posizione del gateway PSTN

Le chiamate instradati tramite gateway PSTN e sistemi PBX potrebbero richiedere Location-Based di routing a seconda della posizione di tali sistemi. Location-Based il routing può essere abilitato con granularità per ogni trunk.

Location-Based routing introduce il set di regole seguente quando abilitato in un trunk:

- Quando Location-Based routing è abilitato per ogni trunk, le regole definite su tale trunk verranno applicate solo alle chiamate instradati attraverso tale trunk.

- Per evitare il bypass dei pedaggi PSTN in cui le chiamate hanno origine da un sito di rete diverso da quello in cui si trova il gateway PSTN, Location-Based Routing introduce l'associazione di un sito di rete a un determinato trunk. Definisce il sito di rete che consente di instradare le chiamate a un determinato trunk.

I trunk possono essere abilitati per Location-Based routing in due modi:

- Il trunk è definito per un gateway PSTN che evade le chiamate alla rete PSTN. Le chiamate in arrivo instradati da un trunk di questo tipo verranno instradati solo agli endpoint che si trovano nello stesso sito di rete del trunk.

- Il trunk è definito per un peer Mediation Server che non evade le chiamate agli utenti PSTN e di servizi con telefoni legacy in posizioni statiche (ad esempio telefoni PBX). Per questa particolare configurazione, tutte le chiamate in arrivo instradati da un trunk di questo tipo verranno considerate provenienti dallo stesso sito di rete del trunk. Le chiamate provenienti da utenti PBX avranno lo stesso Location-Based routing degli utenti Skype for Business che si trovano nello stesso sito di rete del trunk. Se due sistemi PBX situati in siti di rete separati sono connessi tramite Skype for Business Server, Location-Based Routing consentirà il routing da un endpoint PBX in un sito di rete a un altro endpoint PBX nell'altro sito di rete. Questo scenario non verrà bloccato da Location-Based routing. Oltre a questo scenario e in modo analogo a un utente di Skype for Business nella stessa posizione, gli endpoint connessi a un peer Mediation Server con questa configurazione saranno in grado di effettuare o ricevere chiamate da e verso altri peer Mediation Server che non instraderanno le chiamate alla rete PSTN (ad esempio un endpoint connesso a un pbx diverso), indipendentemente dal sito di rete a cui è associato il peer Mediation Server. Tutte le chiamate in ingresso, le chiamate in uscita, i trasferimenti di chiamata e gli inoltro di chiamata che coinvolgono endpoint PSTN saranno soggetti al routing in base alla posizione per utilizzare solo i gateway PSTN definiti come locali per tale peer Mediation Server.

## <a name="scenarios-for-location-based-routing"></a>Scenari per Location-Based routing

Location-Based routing applica le regole generali seguenti quando si instradano le chiamate negli scenari seguenti.

### <a name="outgoing-calls"></a>Chiamate in uscita

Il routing delle chiamate in uscita degli utenti abilitati Location-Based routing è influenzato dal percorso di rete dell'endpoint dell'utente. Nella tabella seguente viene illustrato Location-Based routing influisce sul routing delle chiamate in uscita a seconda della posizione dell'endpoint del chiamante.

**Chiamante che effettua una chiamata in uscita alla rete PSTN**

||**Endpoint utente che si trova in un sito di rete abilitato per Location-Based routing**|**Endpoint utente che si trova in un sito di rete sconosciuto o non abilitato per Location-Based routing**|
|:-----|:-----|:-----|
|Autorizzazione delle chiamate in uscita  <br/> |La chiamata è autorizzata in base ai criteri vocali dell'utente  <br/> |La chiamata è autorizzata in base ai criteri vocali dell'utente  <br/> |
|Routing delle chiamate in uscita  <br/> |La chiamata viene instradata in base ai criteri di routing vocale del sito di rete  <br/> |La chiamata viene instradata in base ai criteri vocali dell'utente e solo tramite trunk non abilitati per Location-Based routing (se disponibile)  <br/> |

### <a name="incoming-calls"></a>Chiamate in arrivo

Il routing delle chiamate in arrivo agli utenti abilitati Location-Based routing dipende dalla posizione dell'endpoint dell'utente. L'instradamento delle chiamate in arrivo è interessato nel modo seguente. Se un utente ha una chiamata in arrivo a un endpoint che si trova in un sito di rete abilitato al routing di Location-Based e l'endpoint si trova nello stesso sito di rete del gateway PSTN, la chiamata verrà instradata. Se un utente ha una chiamata in arrivo a un endpoint che si trova in un sito di rete abilitato al routing di Location-Based e l'endpoint si trova in un sito di rete diverso da quello del gateway PSTN, la chiamata non verrà instradata. Quando un utente non dispone di endpoint nello stesso sito di rete del gateway PSTN da cui proviene la chiamata in arrivo, la chiamata in arrivo verrà instradata direttamente alla segreteria telefonica dell'utente e una notifica di chiamata senza chiamata verrà inviata alla parte chiamata.

Le impostazioni di inoltro di chiamata di un utente abilitato per Location-Based Routing continueranno ad essere applicate, tuttavia, le chiamate inoltrate saranno soggette Location-Based Restrizioni di routing dell'utente.

Nella tabella seguente viene illustrato Location-Based routing influisce sul routing delle chiamate in ingresso a seconda della posizione dell'endpoint del chiamato. Il sito di rete del gateway PSTN è abilitato per il routing Location-Based e il routing Location-Based consente solo il routing delle chiamate PSTN agli endpoint all'interno dello stesso sito di rete.

**Destinatario della chiamata che riceve una chiamata in ingresso dalla rete PSTN**

||**Endpoint del chiamato che si trova nello stesso sito di rete del gateway PSTN**|**L'endpoint del chiamato non si trova nello stesso sito di rete del gateway PSTN**|**Endpoint del chiamato che si trova in un sito di rete sconosciuto o non abilitato per Location-Based routing**|
|:-----|:-----|:-----|:-----|
|Routing delle chiamate PSTN in ingresso  <br/> |La chiamata in arrivo viene instradata agli endpoint del chiamato  <br/> |La chiamata in arrivo non viene instradata agli endpoint del chiamato  <br/> |La chiamata in arrivo non viene instradata agli endpoint del chiamato  <br/> |

### <a name="call-transfers-and-call-forwarding"></a>Trasferimenti di chiamata e inoltro di chiamata

Quando è coinvolto un endpoint PSTN, Location-Based Routing analizza la posizione dell'endpoint del destinatario della chiamata e l'endpoint a cui verrà trasferita o inoltrata la chiamata (ad esempio, destinazione di trasferimento/inoltro). Location-Based routing determina se la chiamata deve essere trasferita o inoltrata a seconda della posizione di entrambi gli endpoint.

Nella tabella seguente viene illustrato lo scenario di un utente Skype for Business in una chiamata con un endpoint PSTN e l'utente di Skype for Business trasferisce la chiamata a un altro Skype for Business utente. A seconda della posizione del sito di rete dell'endpoint del trasferitore, Location-Based routing influisce sul routing del trasferimento o dell'inoltro di chiamata.

**Avvio del trasferimento o dell'inoltro di chiamata**

|**Utente che avvia il trasferimento/inoltro di chiamata**|**L'endpoint di destinazione si trova nello stesso sito di rete dell'utente che avvia il trasferimento di chiamata o l'inoltro**|**L'endpoint di destinazione si trova in un sito di rete diverso quando l'utente avvia il trasferimento o l'inoltro delle chiamate**|**L'endpoint di destinazione si trova nel sito di rete sconosciuto o nel sito di rete non abilitato per Location-Based routing**|
|:-----|:-----|:-----|:-----|
|Skype for Business utente  <br/> |Inoltro di chiamata o trasferimento consentito  <br/> |Inoltro di chiamata o trasferimento non consentito  <br/> |Inoltro di chiamata o trasferimento non consentito  <br/> |

Ad esempio: un Skype for Business utente in una chiamata con un endpoint PSTN trasferisce la chiamata a un altro Skype for Business utente che si trova nello stesso sito di rete. In questo caso, il trasferimento di chiamata è consentito.

Nella tabella seguente viene illustrato lo scenario di un utente Skype for Business in una chiamata con un altro utente Skype for Business e uno degli utenti trasferisce la chiamata a un endpoint PSTN. A seconda della posizione dell'utente a cui viene trasferita la chiamata, la tabella illustra in dettaglio Location-Based routing influisce sulla chiamata.

**Trasferimento o inoltro di chiamata all'endpoint PSTN**

|**Destinazione endpoint trasferimento/inoltro chiamata**|**Skype for Business utenti nello stesso sito di rete**|**Skype for Business utenti in siti di rete diversi**|**Uno o entrambi Skype for Business utenti in un sito di rete sconosciuto o in un sito di rete non abilitato per Location-Based routing**|
|:-----|:-----|:-----|:-----|
|Endpoint PSTN  <br/> |Inoltro di chiamata o trasferimento consentito dal criterio di routing vocale del sito dell'utente trasferito  <br/> |Inoltro di chiamata o trasferimento consentito dal criterio di routing vocale del sito dell'utente trasferito  <br/> |Inoltro di chiamata o trasferimento consentito dal criterio vocale dell'utente trasferito solo tramite trunk non abilitati per Location-Based routing  <br/> |

Ad esempio: un utente Skype for Business in una chiamata con un altro utente di Skype for Business che si trova nello stesso sito di rete trasferisce la chiamata a un endpoint PSTN e il trasferimento di chiamata è consentito.

### <a name="simultaneous-ringing"></a>Squillo simultaneo

Quando la parte chiamata ha attivato lo squillo simultaneo, Location-Based Routing analizza la posizione della parte chiamante e gli endpoint delle parti chiamate per determinare se la chiamata deve essere instradata.

Nella tabella seguente viene illustrato un utente configurato con squilli simultanei e la destinazione di squillo simultaneo è un utente nello stesso sito di rete, in un sito di rete diverso o in un sito di rete sconosciuto.

****

|**Chiamata PSTN in arrivo per**|**Si trova nello stesso sito di rete del chiamato**|**Si trova in un sito di rete diverso da quello del chiamato**|**Si trova in un sito di rete sconosciuto o non abilitato per Location-Based routing**|
|:-----|:-----|:-----|:-----|
|Skype for Business utente  <br/> |Anello simultaneo consentito  <br/> |Anello simultaneo non consentito  <br/> |Anello simultaneo non consentito  <br/> |

Nella tabella seguente viene illustrata una chiamata da un utente Skype for Business (ad esempio un chiamante di Skype for Business) nello stesso sito di rete, in un sito di rete diverso o da un sito di rete sconosciuto. Il destinatario della chiamata dispone di un endpoint PSTN (ad esempio, cellulare) configurato come destinazione dell'anello simultaneo. In questo scenario, Location-Based routing determinerà se la chiamata deve essere instradata alla destinazione dell'anello simultaneo (ad esempio il cellulare) del destinatario della chiamata o meno.

****

|**Destinazione anello simultaneo**|**Si trova nello stesso sito di rete del chiamato**|**Si trova in un sito di rete diverso da quello del chiamato**|**Si trova in un sito di rete sconosciuto o non abilitato per Location-Based routing**|
|:-----|:-----|:-----|:-----|
|Endpoint PSTN  <br/> |Anello simultaneo consentito tramite il criterio di routing vocale del sito del chiamante  <br/> |Anello simultaneo consentito tramite il criterio di routing vocale del sito del chiamante  <br/> |Anello simultaneo consentito tramite i criteri vocali del chiamante ai trunk non abilitati per Location-Based routing  <br/> |

### <a name="skype-for-business-cumulative-update-4"></a>Skype for Business Aggiornamento cumulativo 4

Con l'aggiornamento cumulativo 4, verrà visualizzato quanto segue:

- Location-Based il routing continuerà ad essere abilitato tramite Criteri vocali, inclusi Skype for Business client mobili.

- Il comportamento di chiamata Skype for Business client mobili dipende dal fatto che siano abilitati per Location-Based Routing e il client di comunicazione. È progettato per essere statico, ma in determinate situazioni può essere necessario associare un client Skype for Business Mobile a un gateway PSTN locale e consentire determinati comportamenti, ad esempio un'escalation

- Indipendentemente dal sistema operativo, il Skype for Business mobile deve avere la stessa funzionalità.

La tabella seguente illustra alcuni degli scenari post-aggiornamento cumulativo 4:

|**Utente di routing in base alla posizione**|**Other Party**|**Azione**|**Risultato**|
|:-----|:-----|:-----|:-----|
|Skype for Business Mobile  <br/> |PSTN  <br/> |Skype for Business Il dispositivo mobile riceve una chiamata PSTN in arrivo.  <br/> |La chiamata viene instradata tramite Call via Work (CvW) e non tramite VoIP.  <br/> |
|Skype for Business Mobile  <br/> |PSTN  <br/> |Skype for Business Il dispositivo mobile effettua una chiamata PSTN in uscita.  <br/> |La chiamata viene instradata tramite CvW e non VoIP.  <br/> |
|Skype for Business Mobile  <br/> |PSTN  <br/> |Skype for Business Il dispositivo mobile è in una chiamata PSTN. Skype for Business Mobile quindi inoltrare la chiamata a un altro utente o contatto.  <br/> |La chiamata viene instradata tramite VoIP se l'utente o il contatto è locale al passaggio del gateway PSTN.  <br/> Se l'utente o il contatto è remoto dal passaggio del gateway PSTN, la chiamata viene instradata tramite CvW.  <br/> Se l'utente di destinazione non è raggiungibile tramite PSTN, la chiamata ha esito negativo.  <br/> Se il contatto di destinazione è un Operatore automatico (CAA), la chiamata viene bloccata.  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business client o utente federato  <br/> |Un Skype for Business Mobile avvia una chiamata vocale a un altro Skype for Business o a un utente federato.  <br/> |La chiamata viene completata tramite VoIP.  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business client o utente federato  <br/> | Un Skype for Business o un utente federato avvia una chiamata vocale a un utente Skype for Business Mobile Location-Based Routing. <br/> |La chiamata viene completata tramite VoIP.  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business client o utente federato  <br/> |Un Skype for Business o un utente federato è in una chiamata VoIP a un Skype for Business mobile. Entrambe le parti vengono inoltrate a un Skype for Business o a un utente federato.  <br/> |La chiamata viene completata tramite VoIP.  <br/> |
|Skype for Business Mobile  <br/> |Utente federato  <br/> |Un utente federato è in chiamata vocale a un Skype for Business Mobile Location-Based routing; una Skype for Business mobile viene inoltrata a un utente PSTN.  <br/> |La chiamata è bloccata.  <br/> |
|Skype for Business Mobile  <br/> |Utente federato  <br/> |Un utente federato è in una chiamata VoIP a un Skype for Business Mobile Location-Based routing; entrambe le parti vengono inoltrate a un contatto CAA.  <br/> |La chiamata inoltrata è bloccata, con un messaggio di errore appropriato.  <br/> |
|Skype for Business Mobile  <br/> |Utente federato  <br/> |Un utente federato è in una chiamata VoIP a un utente Skype for Business Mobile Location-Based Routing e l'utente federato viene inoltrato a un utente PSTN.  <br/> |L'escalation sarà consentita o non consentita in base Location-Based routing dell'utente federato. Il Skype for Business mobile Location-Based'applicazione dell'utente di routing non ha alcuna azione.  <br/> |

### <a name="delegation"></a>Delega

Le funzionalità di delega in Skype for Business sono influenzate Location-Based routing nel modo seguente:

- Quando un delegato abilitato per Location-Based Routing esegue una chiamata per conto di un responsabile, il criterio vocale del delegato viene utilizzato per autorizzare la chiamata e il criterio di routing vocale del sito del delegato verrà utilizzato per instradare la chiamata

- Per le chiamate PSTN in arrivo a un responsabile, verranno applicate le stesse regole applicabili per l'inoltro di chiamata o lo squillo simultaneo, come descritto negli argomenti Trasferimenti e inoltro di chiamata e Squillo simultaneo.

- Quando un delegato imposta un endpoint PSTN come destinazione anello simultanea, per una chiamata in arrivo al responsabile, il criterio di routing vocale del sito associato al trunk in ingresso verrà utilizzato per instradare la chiamata all'endpoint PSTN del delegato.

- Per la delega, è consigliabile che il manager e i delegati associati si trovino in genere nello stesso sito di rete.

## <a name="other-planning-considerations"></a>Altre considerazioni sulla pianificazione

Quando si pianifica Location-Based routing, è consigliabile considerare l'impatto sugli scenari seguenti.

### <a name="disaster-recovery"></a>Ripristino d'emergenza

Durante un failover dal pool primario a un pool di backup e durante il ripristino delle normali operazioni nel pool primario, il routing Location-Based rimane sempre applicato durante una procedura di emergenza e ripristino.

### <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

La configurazione Location-Based routing influisce sulla pianificazione della distribuzione dei gateway associati ai Survivable Branch Appliance. Il gateway associato all'SBA deve trovarsi nello stesso sito di rete del Survivable Branch Appliance. in caso contrario, agli utenti ospitati nel Survivable Branch Appliance non sarà consentito effettuare chiamate in uscita se Location-Based routing è configurato. Quando la connessione WAN tra il Survivable Branch Appliance e il sito centrale non è attiva, Location-Based le restrizioni di routing rimangono applicate.

## <a name="client-and-server-support-for-location-based-routing"></a>Supporto client e server per Location-Based routing

Location-Based routing viene applicato da Skype for Business Server. Skype for Business Server i siti di rete in cui gli utenti si connettono dall'interno della rete aziendale. Poiché gli utenti remoti si trova all'esterno della rete aziendale, la loro posizione è considerata sconosciuta.

### <a name="server-support"></a>Supporto server

Location-Based routing richiede che Skype for Business Server o Lync Server 2013 CU1 sia distribuito in tutti i pool Front End e i server edizione Standard in una determinata topologia. Se queste versioni del server non sono installate, le restrizioni di routing in base alla posizione non possono essere applicate completamente.

Nella tabella seguente viene identificata la combinazione di ruoli del server e versioni supportati per Location-Based routing.

****

|**Versione pool**|**Versione Mediation Server**|**Supportata**|
|:-----|:-----|:-----|
|Skype for Business Server aggiornamento cumulativo di febbraio 2013 o Lync Server 2013  <br/> |Skype for Business Server aggiornamento cumulativo di febbraio 2013 o Lync Server 2013  <br/> |sì  <br/> |
|Skype for Business Server aggiornamento cumulativo di febbraio 2013 o Lync Server 2013  <br/> |Lync Server 2013  <br/> |no  <br/> |
|Skype for Business Server aggiornamento cumulativo di febbraio 2013 o Lync Server 2013  <br/> |Lync Server 2010  <br/> |no  <br/> |
|Skype for Business Server aggiornamento cumulativo di febbraio 2013 o Lync Server 2013  <br/> |Office Communications Server 2007 R2  <br/> |no  <br/> |
|Lync Server 2013  <br/> |any  <br/> |no  <br/> |
|Lync Server 2010  <br/> |any  <br/> |no  <br/> |
|Office Communications Server 2007 R2  <br/> |any  <br/> |no  <br/> |

### <a name="client-support"></a>Supporto client

Nella tabella seguente vengono identificati i client supportati Location-Based routing.

****

|**Tipo di client**|**Supportata**|**Dettagli**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |sì  <br/> ||
|Lync 2013  <br/> |sì  <br/> ||
|Lync 2010  <br/> |sì  <br/> ||
|Office Communicator 2007 R2  <br/> |no  <br/> ||
|Lync Phone Edition  <br/> |sì  <br/> ||
|Lync Attendant  <br/> |sì  <br/> ||
|Lync per Windows 8  <br/> |no  <br/> ||
|Lync Mobile 2013  <br/> |no  <br/> |VoIP deve essere disabilitato per i client Lync Mobile 2013 se utilizzato da utenti con routing Location-Based abilitato.  <br/> |
|Lync Mobile 2010  <br/> |sì  <br/> ||

> [!NOTE]
> Per disabilitare VoIP per i client Skype for Business, assegnare un criterio per dispositivi mobili con l'impostazione IP Audio/Video, disabilitata per tutti gli utenti abilitati per Location-Based Routing. Per ulteriori dettagli sui criteri per dispositivi mobili, [vedere New-CsMobilityPolicy.](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)

## <a name="capabilities-not-supported-by-location-based-routing"></a>Funzionalità non supportate da Location-Based routing

Location-Based routing non si applica ai seguenti tipi di interazioni. Location-Based il routing non viene applicato quando Skype for Business endpoint interagiscono con gli endpoint PSTN usando queste funzionalità.

- Accesso con accesso remoto PSTN alle conferenze

- Chiamate PSTN in ingresso e in uscita tramite Response Group

- Parcheggio di chiamata o recupero di chiamate PSTN tramite Parcheggio di chiamata

- Chiamate PSTN in arrivo al servizio Annunci

- Chiamate PSTN in arrivo recuperate tramite prelievo chiamata di gruppo

Per applicare Location-Based di routing ai tipi di interazioni nell'elenco seguente, è necessario abilitare Location-Based routing per le conferenze:

- Chiamate in uscita PSTN dalle conferenze

- Escalation dalle conversazioni audio peer-to-peer alle conferenze che coinvolgono endpoint PSTN

- Trasferimenti consultitivi che coinvolgono endpoint PSTN

Per abilitare Location-Based routing per conferenze, vedere [Routing in base alla posizione per le conferenze](/previous-versions/office/lync-server-2013/lync-server-2013-location-based-routing-for-conferencing).