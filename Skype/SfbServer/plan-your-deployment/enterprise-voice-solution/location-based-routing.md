---
title: Pianificare Location-Based routing in Skype for business
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
description: Pianificazione del routing in base alla posizione in Skype for Business Server VoIP aziendale, tra cui l'interazione con lo squillo simultaneo e la delega e gli scenari supportati per il routing in base alla posizione.
ms.openlocfilehash: 473ed77dce8edaee3b43822adcb8920027795d9e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825556"
---
# <a name="plan-for-location-based-routing-in-skype-for-business"></a>Pianificare Location-Based routing in Skype for business

Pianificazione del routing in base alla posizione in Skype for Business Server VoIP aziendale, tra cui l'interazione con lo squillo simultaneo e la delega e gli scenari supportati per il routing in base alla posizione.

Location-Based routing rende possibile limitare il routing delle chiamate tra endpoint VoIP e endpoint PSTN in base alla posizione delle parti nella chiamata. Location-Based routing è una funzionalità di gestione delle chiamate che controlla il modo in cui vengono instradate da Skype for Business Server. Applica le regole di autorizzazione delle chiamate per stabilire se le chiamate possono essere instradate a endpoint PBX o PSTN in base alla posizione geografica del chiamante di Skype for business.

Location-Based routing introduce un nuovo set di regole che consente di modificare il routing delle chiamate PSTN nazionali e internazionali per evitare il bypass a pedaggio. Location-Based routing offre la possibilità di applicare queste regole a aree specifiche, gateway specifici o solo a un insieme specifico di utenti.

Negli scenari seguenti vengono illustrati i principali tipi di restrizioni Location-Based il routing può applicare:

- Chiamate in uscita-Location-Based il routing può applicare le chiamate in uscita per l'ingresso a un gateway PSTN che si trova nella stessa regione in cui il chiamante deve impedire il bypass a pedaggio PSTN, impedendo le chiamate all'uscita verso un gateway PSTN che si trova in un'area diversa come chiamante.

- Ingress calls-Location-Based routing può impedire le chiamate PSTN in arrivo per suonare gli endpoint di Skype for business se il gateway PSTN che instrada la chiamata in arrivo non si trova nella stessa area dell'utente chiamato Skype for business.

- Aree sconosciute-Location-Based il routing limita le chiamate PSTN in ingresso e in uscita da e verso gli utenti che si trovano in posizioni Indeterminate (ad esempio, gli utenti remoti che si connettono da Internet o che si trovano in aree sconosciute).

- International Regions-Location-Based routing impone il routing delle chiamate in uscita attraverso i gateway PSTN internazionali se non è possibile trovare un gateway locale per la posizione dell'utente.

## <a name="guidance-for-where-to-apply-location-based-routing"></a>Indicazioni su dove applicare il routing Location-Based

Location-Based il routing a seconda della situazione può essere applicato nella posizione del sito di rete dell'endpoint dell'utente o nel percorso del sito di rete del gateway PSTN. In questo argomento vengono fornite indicazioni sulla modalità di applicazione del routing Location-Based.

### <a name="applying-location-based-routing-at-the-users-location"></a>Applicazione del routing Location-Based nella posizione dell'utente

Location-Based routing utilizza le stesse aree di rete, siti e subnet, come definito in Skype for Business Server utilizzato da E9-1-1, CAC e bypass multimediale per applicare le restrizioni di routing delle chiamate per impedire il bypass a pedaggio PSTN. La posizione di un utente è determinata dalla subnet IP degli endpoint Skype for business dell'utente da cui sono connessi. Ogni subnet IP è associata a un sito di rete, che viene aggregato nelle aree di rete definite dall'amministratore. Location-Based il routing viene applicato in base al sito di rete dell'utente.

Le regole di routing Location-Based vengono applicate in base al sito di rete, ovvero un determinato insieme di regole verrà applicato a tutti gli endpoint abilitati per il routing Location-Based che si trovano all'interno dello stesso sito di rete. Gli amministratori possono applicare il routing Location-Based a siti di rete che lo richiedono.

I criteri di routing vocale possono essere definiti in base al sito di rete per definire un gateway PSTN specifico che deve essere utilizzato da tutti gli utenti che si trovano nel sito di rete per chiamare i numeri di telefono PSTN. Tali criteri di routing vocale avranno la precedenza sul routing definito dal criterio vocale dell'utente quando l'utente si trova in un sito di rete abilitato per il routing Location-Based e impedirà il routing delle chiamate tramite altri gateway PSTN abilitati per il routing Location-Based. Quando un utente di Skype for business inserisce una chiamata PSTN, il criterio vocale dell'utente determina se l'utente può essere autorizzato a effettuare la chiamata. Se il criterio vocale dell'utente consente all'utente di effettuare la chiamata, Location-Based percorso determina il gateway PSTN da cui deve essere eseguita la chiamata. Location-Based routing rende questa determinazione in base alla posizione dell'utente.

Una posizione utente può essere categorizzata nei modi seguenti:

- L'utente si trova in un sito di rete noto abilitato per il routing Location-Based e il numero DID (Direct Inward Dial) termina con un gateway PSTN posizionato nello stesso sito di rete (ad esempio, Office). Il routing delle chiamate in uscita sarà tramite il criterio di routing vocale del sito di rete in cui si trova l'utente. Le chiamate PSTN in arrivo all'utente vengono instradate agli endpoint che si trovano nello stesso sito di rete del gateway PSTN.

- L'utente si trova in un sito di rete noto che è diverso dal sito di rete in cui si trova il gateway PSTN. (ovvero l'utente ha viaggiato in un altro ufficio aziendale). Il routing delle chiamate in uscita utilizzerà i criteri di routing vocale del sito di rete in cui si trova l'utente. Le chiamate PSTN in arrivo all'utente non verranno instradate agli endpoint che si trovano in siti diversi rispetto al gateway PSTN per impedire l'esclusione dei pedaggi PSTN.

- Quando un utente si trova in un sito di rete sconosciuto alla distribuzione di Skype for Business Server, il routing delle chiamate in uscita si baserà sui criteri vocali assegnati all'utente ai gateway PSTN non associati a Location-Based restrizioni di routing. Le chiamate PSTN in arrivo non verranno instradate agli endpoint che si trovano in siti di rete sconosciuti per impedire l'esclusione dei pedaggi PSTN.

### <a name="applying-location-based-routing-at-the-pstn-gateways-location"></a>Applicazione del routing Location-Based alla posizione del gateway PSTN

Le chiamate instradate tramite gateway PSTN e PBX potrebbero richiedere Location-Based limitazioni del routing in base alla posizione di tali sistemi. Location-Based il routing può essere abilitato alla granularità per ogni base trunk.

Location-Based routing introduce il set di regole seguente quando è abilitato su un trunk:

- Quando Location-Based routing è abilitato per ogni trunk, le regole definite su tale trunk verranno applicate solo alle chiamate instradate attraverso il trunk.

- Per evitare che i pedaggi PSTN vengano ignorati in cui le chiamate provengono da un sito di rete diverso da quello del sito di rete in cui si trova il gateway PSTN, Location-Based routing introduce l'associazione di un sito di rete a un trunk specificato. In questo modo viene definito il sito di rete che consente di instradare le chiamate a un determinato trunk.

I trunk possono essere abilitati per il routing Location-Based in due modi:

- Il trunk è definito per un gateway PSTN che egresses le chiamate alla rete PSTN. Le chiamate in arrivo instradate da un trunk di questo tipo verranno instradate solo agli endpoint situati all'interno dello stesso sito di rete del trunk.

- Il trunk è definito per un peer di Mediation Server che non consente di uscire dalle chiamate agli utenti di servizi PSTN e con i telefoni legacy in posizioni statiche (ovvero telefoni PBX). Per questa configurazione specifica, tutte le chiamate in arrivo instradate da un trunk di questo tipo verranno considerate come originate dallo stesso sito di rete del trunk. Le chiamate provenienti da utenti PBX avranno lo stesso Location-Based applicazione di routing per gli utenti di Skype for business che si trovano nello stesso sito di rete del trunk. Se due sistemi PBX situati in siti di rete separati sono connessi tramite Skype for Business Server, Location-Based routing consentirà il routing da un endpoint PBX in un sito di rete a un altro endpoint PBX nell'altro sito di rete. Questo scenario non verrà bloccato da Location-Based routing. Oltre a questo scenario e in modo analogo a quello di un utente Skype for business nello stesso percorso, gli endpoint connessi a un peer di Mediation Server con questa configurazione saranno in grado di effettuare o ricevere chiamate verso e da altri peer di Mediation Server che non instradano le chiamate alla rete PSTN (ovvero un endpoint connesso a un altro sistema PBX) indipendentemente dal sito di rete a cui è associato il peer di Mediation Server. Tutte le chiamate in ingresso, le chiamate in uscita, i trasferimenti di chiamata e gli inoltri di chiamata che coinvolgono endpoint PSTN sono soggetti al routing basato sulla posizione per l'utilizzo di solo gateway PSTN definiti come locali per tale peer di Mediation Server.

## <a name="scenarios-for-location-based-routing"></a>Scenari per il routing Location-Based

Location-Based routing applica le regole generali seguenti quando si esegue il routing delle chiamate negli scenari seguenti.

### <a name="outgoing-calls"></a>Chiamate in uscita

Il routing delle chiamate in uscita degli utenti abilitati per il routing Location-Based è influenzato dal percorso di rete dell'endpoint dell'utente. Nella tabella seguente viene illustrato il modo in cui Location-Based routing influisce sul routing delle chiamate in uscita a seconda del percorso dell'endpoint del chiamante.

**Chiamante che effettua una chiamata in uscita alla rete PSTN**

||**Endpoint utente che si trova in un sito di rete abilitato per il routing Location-Based**|**Endpoint utente che si trova in un sito di rete sconosciuto o non abilitato per il routing Location-Based**|
|:-----|:-----|:-----|
|Autorizzazione delle chiamate in uscita  <br/> |La chiamata è autorizzata in base ai criteri vocali dell'utente  <br/> |La chiamata è autorizzata in base ai criteri vocali dell'utente  <br/> |
|Routing delle chiamate in uscita  <br/> |La chiamata viene instradata in base al criterio di routing vocale del sito di rete  <br/> |La chiamata viene instradata in base ai criteri vocali dell'utente e solo tramite trunk non abilitato per il routing Location-Based (se disponibile)  <br/> |

### <a name="incoming-calls"></a>Chiamate in arrivo

Il routing delle chiamate in arrivo agli utenti abilitati per il routing Location-Based dipende dalla posizione dell'endpoint dell'utente. Il routing delle chiamate in arrivo è influenzato nel modo seguente. Se un utente dispone di una chiamata in arrivo a un endpoint situato in un sito di rete Location-Based abilitato per il routing e l'endpoint si trova nello stesso sito di rete del gateway PSTN, la chiamata verrà instradata. Se un utente dispone di una chiamata in arrivo a un endpoint posizionato in un sito di rete Location-Based abilitato per il routing e l'endpoint si trova in un sito di rete diverso da quello del gateway PSTN, la chiamata non verrà instradata. Quando un utente non dispone di endpoint situati nello stesso sito di rete del gateway PSTN da cui proviene la chiamata in arrivo, la chiamata in arrivo viene instradata direttamente alla segreteria telefonica dell'utente e viene inviata una notifica di chiamata senza risposta all'interlocutore chiamato.

Le impostazioni di inoltro di chiamata di un utente abilitato per il routing di Location-Based continueranno a essere applicate, tuttavia, le chiamate inoltrate saranno soggette a Location-Based limitazioni di routing dell'utente.

Nella tabella seguente viene illustrato il modo in cui Location-Based routing influisce sul routing delle chiamate in ingresso a seconda del percorso dell'endpoint del destinatario della chiamata. Il sito di rete del gateway PSTN è abilitato per il routing Location-Based e Location-Based routing consente solo il routing delle chiamate PSTN agli endpoint all'interno dello stesso sito di rete.

**Destinatario chiamata che riceve una chiamata in ingresso dalla rete PSTN**

||**Endpoint del destinatario della chiamata che si trova nello stesso sito di rete del gateway PSTN**|**Endpoint del destinatario della chiamata non presente nello stesso sito di rete del gateway PSTN**|**Endpoint del destinatario della chiamata che si trova nel sito di rete sconosciuto o non abilitato per il routing Location-Based**|
|:-----|:-----|:-----|:-----|
|Routing della chiamata PSTN in ingresso  <br/> |La chiamata in arrivo viene instradata agli endpoint del destinatario chiamata  <br/> |La chiamata in arrivo non viene instradata agli endpoint del destinatario chiamata  <br/> |La chiamata in arrivo non viene instradata agli endpoint del destinatario chiamata  <br/> |

### <a name="call-transfers-and-call-forwarding"></a>Trasferimenti di chiamata e inoltro di chiamata

Quando viene coinvolto un endpoint PSTN, Location-Based routing analizza la posizione dell'endpoint di Calle e dell'endpoint in cui verrà trasferita o inoltrata la chiamata (ovvero la destinazione di trasferimento/inoltro). Location-Based il routing determina se la chiamata deve essere trasferita o inoltrata a seconda della posizione di entrambi gli endpoint.

Nella tabella seguente viene illustrato lo scenario di un utente Skype for business in una chiamata con un endpoint PSTN e l'utente Skype for business trasferisce la chiamata a un altro utente di Skype for business. A seconda del percorso del sito di rete dell'endpoint del cessionario, Location-Based routing influisce sul routing del trasferimento di chiamata o su Inoltra.

**Avvio del trasferimento delle chiamate o dell'inoltro**

|**Utente che avvia il trasferimento di chiamata/inoltra**|**L'endpoint di destinazione si trova nello stesso sito di rete dell'utente che avvia il trasferimento delle chiamate o inoltra**|**L'endpoint di destinazione si trova in un sito di rete diverso come utente che avvia il trasferimento delle chiamate o inoltra**|**L'endpoint di destinazione è in sito di rete sconosciuto o sito di rete non abilitato per il routing Location-Based**|
|:-----|:-----|:-----|:-----|
|Utente di Skype for business  <br/> |Inoltro di chiamata o trasferimento consentito  <br/> |Non è consentito l'inoltro di chiamata o il trasferimento  <br/> |Non è consentito l'inoltro di chiamata o il trasferimento  <br/> |

Ad esempio, un utente di Skype for business in una chiamata con un endpoint PSTN trasferisce la chiamata a un altro utente Skype for business che si trova nello stesso sito di rete. In questo caso, il trasferimento di chiamata è consentito.

Nella tabella seguente viene illustrato lo scenario di un utente Skype for business in una chiamata con un altro utente di Skype for business e uno degli utenti trasferisce la chiamata a un endpoint PSTN. A seconda della posizione dell'utente in cui viene trasferita la chiamata, la tabella descrive in che modo Location-Based instradamento influisce sulla chiamata.

**Trasferimento di chiamata o inoltra all'endpoint PSTN**

|**Destinazione endpoint trasferimento/inoltro di chiamata**|**Utenti di Skype for business nello stesso sito di rete**|**Utenti di Skype for business in siti di rete diversi**|**Uno o entrambi gli utenti di Skype for business nel sito di rete o sito di rete sconosciuto non sono abilitati per il routing Location-Based**|
|:-----|:-----|:-----|:-----|
|Endpoint PSTN  <br/> |Chiamata inoltra o trasferimento consentito dal criterio di routing vocale del sito dell'utente trasferito  <br/> |Chiamata inoltra o trasferimento consentito dal criterio di routing vocale del sito dell'utente trasferito  <br/> |Chiamata inoltrata o trasferimento consentita dal criterio vocale dell'utente trasferito solo tramite trunk non abilitato per il routing Location-Based  <br/> |

Ad esempio, un utente di Skype for business in una chiamata con un altro utente Skype for business che si trova nello stesso sito di rete trasferisce la chiamata a un endpoint PSTN e il trasferimento di chiamata è consentito.

### <a name="simultaneous-ringing"></a>Squillo simultaneo

Quando la parte chiamata è abilitata alla suoneria simultanea, Location-Based routing analizza la posizione della parte chiamante e gli endpoint delle parti denominate per determinare se la chiamata deve essere instradata.

Nella tabella seguente è illustrato un utente configurato con squillo simultaneo e la destinazione di squillo simultaneo è un utente nello stesso sito di rete, in un sito di rete diverso o in un sito di rete sconosciuto.

****

|**Chiamata PSTN in ingresso per**|**Si trova nello stesso sito di rete del destinatario della chiamata**|**Si trova in un sito di rete diverso dal destinatario della chiamata**|**Si trova in un sito di rete sconosciuto o non è abilitato per il routing Location-Based**|
|:-----|:-----|:-----|:-----|
|Utente di Skype for business  <br/> |Squillo simultaneo consentito  <br/> |Squillo simultaneo non consentito  <br/> |Squillo simultaneo non consentito  <br/> |

Nella tabella seguente viene illustrata una chiamata da un utente Skype for business (ad esempio, chiamante di Skype for business) nello stesso sito di rete, in un sito di rete diverso o da un sito di rete sconosciuto. Il destinatario della chiamata ha un endpoint PSTN (i.e. cellulare) configurato come destinazione anello simultaneo. In questo scenario, Location-Based routing determinerà se la chiamata deve essere instradata alla destinazione dell'anello simultaneo (i.e. cellulare) del destinatario della chiamata oppure no.

****

|**Destinazione anello simultaneo**|**Si trova nello stesso sito di rete del destinatario della chiamata**|**Si trova in un sito di rete diverso dal destinatario della chiamata**|**Si trova in un sito di rete sconosciuto o non è abilitato per il routing Location-Based**|
|:-----|:-----|:-----|:-----|
|Endpoint PSTN  <br/> |Squillo simultaneo consentito tramite il criterio di routing vocale del sito del chiamante  <br/> |Squillo simultaneo consentito tramite il criterio di routing vocale del sito del chiamante  <br/> |Squillo simultaneo consentito tramite il criterio vocale del chiamante ai trunk non abilitati per il routing Location-Based  <br/> |

### <a name="skype-for-business-cumulative-update-4"></a>Aggiornamento cumulativo 4 di Skype for business

Con l'aggiornamento cumulativo 4, verrà visualizzato quanto segue:

- Il routing Location-Based continuerà a essere abilitato tramite il criterio vocale, inclusi i client per dispositivi mobili Skype for business.

- Il comportamento di chiamata per i client mobili Skype for business sarà basato sul fatto che siano abilitati per il routing Location-Based e per il client di comunicazione. Questo è stato creato per essere statico, ma in determinate situazioni potrebbe essere necessario un tentativo di associare un client mobile Skype for business a un gateway PSTN locale e consentire determinati comportamenti, ad esempio un'escalation

- Indipendentemente dal sistema operativo, il client per dispositivi mobili Skype for business dovrebbe avere la stessa funzionalità.

Nella tabella seguente vengono illustrati alcuni degli scenari successivi all'aggiornamento cumulativo 4:

|**Utente di routing in base alla posizione**|**Altra parte**|**Azione**|**Risultato**|
|:-----|:-----|:-----|:-----|
|Skype for business per dispositivi mobili  <br/> |PSTN  <br/> |Skype for business mobile riceve una chiamata PSTN in ingresso.  <br/> |La chiamata viene instradata tramite chiamata tramite lavoro (CvW) e non VoIP.  <br/> |
|Skype for business per dispositivi mobili  <br/> |PSTN  <br/> |Skype for business mobile effettua una chiamata PSTN in uscita.  <br/> |La chiamata viene instradata tramite CvW e non VoIP.  <br/> |
|Skype for business per dispositivi mobili  <br/> |PSTN  <br/> |Skype for business mobile è in una chiamata PSTN. Skype for business mobile inoltra la chiamata a un altro utente o a un contatto.  <br/> |La chiamata viene instradata tramite VoIP se l'utente o il contatto è locale rispetto alla gamba del gateway PSTN.  <br/> Se l'utente o il contatto è remoto dalla gamba del gateway PSTN, la chiamata viene instradata tramite CvW.  <br/> Se l'utente di destinazione non è raggiungibile tramite la rete PSTN, la chiamata ha esito negativo.  <br/> Se il contatto di destinazione è un operatore automatico di conferenza (CAA), la chiamata viene bloccata.  <br/> |
|Skype for business per dispositivi mobili  <br/> |Client Skype for business o utente federato  <br/> |Un cellulare Skype for business avvia una chiamata vocale a un altro client Skype for business o a un utente federato.  <br/> |La chiamata viene completata tramite VoIP.  <br/> |
|Skype for business per dispositivi mobili  <br/> |Client Skype for business o utente federato  <br/> | Un client Skype for business o un utente federato avvia una chiamata vocale a un utente di routing Location-Based per dispositivi mobili di Skype for business. <br/> |La chiamata viene completata tramite VoIP.  <br/> |
|Skype for business per dispositivi mobili  <br/> |Client Skype for business o utente federato  <br/> |Un client Skype for business o un utente federato è su una chiamata VoIP a un utente di Skype for business mobile. Entrambe le parti vengono Escalate in un altro utente di Skype for business o federato.  <br/> |La chiamata viene completata tramite VoIP.  <br/> |
|Skype for business per dispositivi mobili  <br/> |Utente federato  <br/> |Un utente federato è in chiamata vocale a un utente di routing Location-Based per dispositivi mobili di Skype for business; una parte mobile di Skype for business viene inoltrata a un utente PSTN.  <br/> |La chiamata è bloccata.  <br/> |
|Skype for business per dispositivi mobili  <br/> |Utente federato  <br/> |Un utente federato è su una chiamata VoIP a un utente di routing Location-Based per dispositivi mobili di Skype for business; l'una o l'altra parte viene inoltrata a un contatto CAA.  <br/> |La chiamata escalation è bloccata, con un messaggio di errore appropriato.  <br/> |
|Skype for business per dispositivi mobili  <br/> |Utente federato  <br/> |Un utente federato è su una chiamata VoIP a un utente di routing Location-Based per dispositivi mobili di Skype for business e l'utente federato si inoltra a un utente PSTN.  <br/> |L'escalation sarà consentita o non consentita in base al routing Location-Based dell'utente federato. L'applicazione di routing Location-Based di Skype for business per dispositivi mobili non intraprendere alcuna azione.  <br/> |

### <a name="delegation"></a>Delega

Le funzionalità di delega in Skype for business sono intaccate dal routing Location-Based nel modo seguente:

- Quando un delegato abilitato per il routing Location-Based inserisce una chiamata per conto di un responsabile, il criterio vocale del delegato viene utilizzato per autorizzare la chiamata e il criterio di routing vocale del sito del delegato verrà utilizzato per instradare la chiamata

- Per le chiamate PSTN in arrivo a un Manager, si applicano le stesse regole applicabili per l'inoltro di chiamata o lo squillo simultaneo come descritto negli argomenti trasferimento di chiamata e inoltro e squillo simultaneo.

- Quando un delegato imposta un endpoint PSTN come destinazione anello simultaneo, per una chiamata in arrivo al responsabile, il criterio di routing vocale del sito associato al trunk in ingresso verrà utilizzato per instradare la chiamata all'endpoint PSTN del delegato.

- Per la delega, è consigliabile che il responsabile e i delegati associati si trovino in genere nello stesso sito di rete.

## <a name="other-planning-considerations"></a>Altre considerazioni sulla pianificazione

Quando si pianifica Location-Based il routing, è opportuno considerare l'impatto sui seguenti scenari.

### <a name="disaster-recovery"></a>Ripristino d'emergenza

Durante un failover dal pool primario a un pool di backup e durante il ripristino di normali operazioni nel pool primario, Location-Based il routing rimane applicato sempre durante una procedura di ripristino e di emergenza.

### <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

La configurazione di Location-Based influisce sulla pianificazione del percorso in cui vengono distribuiti i gateway associati ai Survivable Branch Appliance. Il gateway associato all'ASB deve trovarsi nello stesso sito di rete del Survivable Branch Appliance. in caso contrario, gli utenti ospitati nel Survivable Branch Appliance non saranno autorizzati a inserire le chiamate in uscita se Location-Based il routing è configurato. Quando la connessione WAN tra il Survivable Branch Appliance e il sito centrale è inattiva, Location-Based restrizioni di routing restano applicate.

## <a name="client-and-server-support-for-location-based-routing"></a>Supporto per client e server per il routing Location-Based

Il routing Location-Based viene applicato da Skype for Business Server. Skype for Business Server è in grado di identificare i siti di rete in cui gli utenti si connettono dall'interno della rete aziendale. Poiché gli utenti remoti si trovano all'esterno della rete aziendale, la loro posizione è considerata sconosciuta.

### <a name="server-support"></a>Supporto server

Location-Based routing richiede che Skype for Business Server o Lync Server 2013 CU1 sia distribuito su tutti i pool Front end e i server Standard Edition in una determinata topologia. Se non sono installate queste versioni del server, non è possibile applicare le restrizioni relative al routing basato sulla posizione.

La tabella seguente identifica la combinazione di ruoli del server e versioni supportate per il routing Location-Based.

****

|**Versione pool**|**Versione Mediation Server**|**Supportata**|
|:-----|:-----|:-----|
|Aggiornamento cumulativo di Skype for Business Server o Lync Server 2013 febbraio 2013  <br/> |Aggiornamento cumulativo di Skype for Business Server o Lync Server 2013 febbraio 2013  <br/> |sì  <br/> |
|Aggiornamento cumulativo di Skype for Business Server o Lync Server 2013 febbraio 2013  <br/> |Lync Server 2013  <br/> |no  <br/> |
|Aggiornamento cumulativo di Skype for Business Server o Lync Server 2013 febbraio 2013  <br/> |Lync Server 2010  <br/> |no  <br/> |
|Aggiornamento cumulativo di Skype for Business Server o Lync Server 2013 febbraio 2013  <br/> |Office Communications Server 2007 R2  <br/> |no  <br/> |
|Lync Server 2013  <br/> |qualsiasi  <br/> |no  <br/> |
|Lync Server 2010  <br/> |qualsiasi  <br/> |no  <br/> |
|Office Communications Server 2007 R2  <br/> |qualsiasi  <br/> |no  <br/> |

### <a name="client-support"></a>Supporto client

Nella tabella seguente vengono identificati i client che Location-Based i supporti di routing.

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
|Lync Mobile 2013  <br/> |no  <br/> |Il VoIP deve essere disabilitato per i client Lync Mobile 2013 se utilizzato dagli utenti con Location-Based routing abilitato.  <br/> |
|Lync Mobile 2010  <br/> |sì  <br/> ||

> [!NOTE]
> Per disabilitare VoIP per i client Skype for business, assegnare un criterio per dispositivi mobili con l'impostazione, audio/video IP, disabilitato per tutti gli utenti abilitati per il routing Location-Based. Per ulteriori informazioni sui criteri per dispositivi mobili, vedere [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).

## <a name="capabilities-not-supported-by-location-based-routing"></a>Funzionalità non supportate dal routing Location-Based

Location-Based routing non si applica ai tipi di interazioni seguenti. Il routing Location-Based non viene applicato quando gli endpoint di Skype for business interagiscono con gli endpoint PSTN utilizzando queste funzionalità.

- Accesso esterno PSTN alle conferenze

- Chiamate PSTN in ingresso e in uscita tramite Response Group

- Parcheggio di chiamata o recupero delle chiamate PSTN tramite il parcheggio di chiamata

- Chiamate PSTN in arrivo per il servizio annunci

- Chiamate PSTN in arrivo recuperate tramite raccolta chiamate di gruppo

Per applicare le regole di routing Location-Based ai tipi di interazioni presenti nell'elenco seguente, è necessario abilitare Location-Based routing per le conferenze:

- Accesso esterno PSTN dalle conferenze

- Escalation dalle conversazioni audio peer-to-peer ai servizi di conferenza che coinvolgono endpoint PSTN

- Trasferimenti consultivi che coinvolgono endpoint PSTN

Per abilitare il routing Location-Based per le conferenze, vedere [routing in base alla posizione per le conferenze](https://technet.microsoft.com/library/e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3.aspx).


