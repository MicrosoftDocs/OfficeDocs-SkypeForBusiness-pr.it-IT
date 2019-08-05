---
title: Pianificare il routing basato sulla posizione in Skype for business
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
ms.assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
description: Pianificazione del routing basato sulla posizione in Skype for Business Server VoIP aziendale, tra cui l'interazione con la chiamata e la delega simultanea e gli scenari supportati per il routing basato sulla posizione.
ms.openlocfilehash: 8c6ce8467c48231ebcab706874e70341ba431fd8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187646"
---
# <a name="plan-for-location-based-routing-in-skype-for-business"></a>Pianificare il routing basato sulla posizione in Skype for business

Pianificazione del routing basato sulla posizione in Skype for Business Server VoIP aziendale, tra cui l'interazione con la chiamata e la delega simultanea e gli scenari supportati per il routing basato sulla posizione.

Il routing basato sulla posizione consente di limitare il routing delle chiamate tra endpoint VoIP e endpoint PSTN in base alla posizione delle parti nella chiamata. Il routing basato sulla posizione è una caratteristica di gestione delle chiamate che controlla il modo in cui le chiamate vengono instradate da Skype for Business Server. Applica le regole di autorizzazione delle chiamate per indicare se le chiamate possono essere instradate a endpoint PBX o PSTN in base alla posizione geografica del chiamante di Skype for business.

Il routing basato sulla posizione introduce un nuovo set di regole che modifica il routing delle chiamate PSTN nazionali e internazionali per evitare l'esclusione dei pedaggi. Il routing basato sulla posizione offre la flessibilità per l'ambito di queste regole per specifiche aree geografiche, gateway specifici o solo set di utenti specifici.

Gli scenari seguenti illustrano i tipi principali di restrizioni che il routing basato sulla posizione può applicare:

- Chiamate in uscita: il routing basato sulla posizione può applicare le chiamate in uscita all'ingresso in un gateway PSTN che si trova nella stessa area geografica in cui il chiamante deve impedire l'esclusione del pedaggio PSTN, impedendo le chiamate all'uscita in un gateway PSTN situato in un'area diversa come chiamante.

- Chiamate in ingresso: il routing basato sulla posizione può impedire le chiamate PSTN in arrivo per chiamare gli endpoint di Skype for business se il gateway PSTN che instrada la chiamata in arrivo non si trova nella stessa area dell'utente di Skype for business.

- Aree sconosciute-il routing basato sulla posizione limita le chiamate PSTN in ingresso e in uscita a e da utenti che si trovano in posizioni Indeterminate (ad esempio, gli utenti remoti che si connettono da Internet o si trovano in aree sconosciute).

- Aree internazionali-il routing basato sulla posizione impone il routing delle chiamate in uscita tramite gateway PSTN internazionali se non è possibile trovare un gateway locale nella posizione dell'utente.

## <a name="guidance-for-where-to-apply-location-based-routing"></a>Indicazioni su dove applicare il routing basato sulla posizione

Il routing basato sulla posizione a seconda della situazione può essere applicato nella posizione del sito di rete endpoint dell'utente o nella posizione del sito di rete del gateway PSTN. Questo argomento fornisce indicazioni su come applicare il routing basato sulla posizione.

### <a name="applying-location-based-routing-at-the-users-location"></a>Applicazione del routing basato sulla posizione nella posizione dell'utente

Il routing basato sulla posizione sfrutta le stesse aree geografiche, i siti e le subnet di rete definiti in Skype for Business Server usato da E9-1-1, CAC e bypass multimediale per applicare le restrizioni di routing delle chiamate per evitare l'esclusione del pedaggio PSTN. La posizione di un utente è determinata dalla subnet IP degli endpoint Skype for business dell'utente da cui sono connessi. Ogni subnet IP è associata a un sito di rete, che viene aggregato in aree di rete definite dall'amministratore. Il routing basato sulla posizione viene applicato in base al sito di rete dell'utente.

Le regole di routing basate sulla posizione vengono applicate in base al sito di rete, pertanto un set di regole specifico verrà applicato a tutti gli endpoint abilitati per il routing basato sulla posizione che si trovano all'interno dello stesso sito di rete. Gli amministratori possono applicare il routing basato sulla posizione ai siti di rete che lo richiedono.

I criteri di routing vocale possono essere definiti in base al sito di rete per definire un gateway PSTN specifico che deve essere usato da tutti gli utenti presenti nel sito di rete per chiamare i numeri di telefono PSTN. Tali criteri di routing vocale avranno la precedenza sul routing definito dal criterio vocale dell'utente quando l'utente si trova in un sito di rete abilitato per il routing basato sulla posizione e impedirà il routing delle chiamate tramite altri gateway PSTN abilitati per Routing basato sulla posizione. Quando un utente di Skype for business inserisce una chiamata PSTN, il criterio vocale dell'utente determina se l'utente può essere autorizzato a effettuare la chiamata. Se il criterio vocale dell'utente consente all'utente di inserire la chiamata, il routing basato sulla posizione determina il gateway PSTN da cui deve essere uscita la chiamata. Il routing basato sulla posizione rende questa determinazione in base alla posizione dell'utente.

Una posizione utente può essere categorizzata nei modi seguenti:

- L'utente si trova in un sito di rete noto abilitato per il routing basato sulla posizione e il suo numero DID (Direct Inward Dial) termina con un gateway PSTN inserito nello stesso sito di rete (ad esempio Office). Il routing delle chiamate in uscita avverrà tramite il criterio di routing vocale del sito di rete in cui si trova l'utente. Le chiamate PSTN in arrivo all'utente vengono instradate agli endpoint che si trovano nello stesso sito di rete del gateway PSTN.

- L'utente si trova in un sito di rete noto che è diverso dal sito di rete in cui si trova il gateway PSTN. (ossia l'utente ha viaggiato in un altro ufficio aziendale). Il routing delle chiamate in uscita userà i criteri di routing vocale del sito di rete in cui si trova l'utente. Le chiamate PSTN in arrivo per l'utente non verranno instradate agli endpoint che si trovano in siti diversi rispetto al gateway PSTN per evitare l'esclusione dei pedaggi PSTN.

- Quando un utente si trova in un sito di rete sconosciuto alla distribuzione di Skype for Business Server, il routing delle chiamate in uscita sarà basato sul criterio vocale assegnato all'utente ai gateway PSTN non associati alle restrizioni di routing basate sulla posizione. Le chiamate PSTN in arrivo non verranno instradate agli endpoint che si trovano in siti di rete sconosciuti per evitare l'esclusione dei pedaggi PSTN.

### <a name="applying-location-based-routing-at-the-pstn-gateways-location"></a>Applicazione del routing basato sulla posizione nella posizione del gateway PSTN

Le chiamate instradate tramite gateway e PBX PSTN potrebbero richiedere restrizioni di routing basate sulla posizione a seconda della posizione di tali sistemi. Il routing basato sulla posizione può essere abilitato alla granularità per ogni trunk base.

Il routing basato sulla posizione introduce il set di regole seguente quando è abilitato su un trunk:

- Quando il routing basato sulla posizione è abilitato per ogni trunk, le regole definite in tale trunk verranno applicate solo alle chiamate instradate tramite il trunk.

- Per impedire l'esclusione dei pedaggi PSTN in cui le chiamate provengono da un sito di rete diverso da quello del sito di rete in cui si trova il gateway PSTN, il routing basato sulla posizione introduce l'associazione di un sito di rete a un trunk specifico. Questo definisce il sito di rete che consente alle chiamate di essere indirizzate a un trunk specifico.

Trunks può essere abilitato per il routing basato sulla posizione in due modi:

- Il trunk viene definito per un gateway PSTN che egresses chiama alla rete PSTN. Le chiamate in arrivo instradate da un trunk di questo tipo verranno instradate solo agli endpoint situati nello stesso sito di rete del trunk.

- Il trunk viene definito per un peer di Mediation Server che non consente l'uscita delle chiamate agli utenti di servizi e PSTN con telefoni legacy in posizioni statiche (ad esempio telefoni PBX). Per questa particolare configurazione, tutte le chiamate in arrivo instradate da un trunk di questo tipo verranno considerate come originarie dello stesso sito di rete del trunk. Le chiamate degli utenti PBX avranno la stessa applicazione di routing basata sulla posizione degli utenti di Skype for business che si trovano nello stesso sito di rete del trunk. Se due sistemi PBX situati in siti di rete separati sono connessi tramite Skype for Business Server, il routing basato sulla posizione consentirà il routing da un endpoint PBX in un sito di rete a un altro endpoint PBX nell'altro sito di rete. Questo scenario non verrà bloccato dal routing basato sulla posizione. Oltre a questo scenario e in modo simile a quello di un utente Skype for business nella stessa posizione, gli endpoint connessi a un peer di Mediation Server con questa configurazione potranno effettuare o ricevere chiamate da e verso altri peer di Mediation Server che non instradano le chiamate t o PSTN (ad esempio un endpoint connesso a un PBX diverso) indipendentemente dal sito di rete a cui è associato il peer di Mediation Server. Tutte le chiamate in ingresso, le chiamate in uscita, i trasferimenti di chiamata e i forward di chiamata che coinvolgono endpoint PSTN saranno soggetti al routing basato sulla posizione per usare solo gateway PSTN definiti come locali a tale peer di Mediation Server.

## <a name="scenarios-for-location-based-routing"></a>Scenari per il routing in base alla posizione

Il routing basato sulla posizione applica le regole generali seguenti quando si instradano le chiamate negli scenari seguenti.

### <a name="outgoing-calls"></a>Chiamate in uscita

Il routing delle chiamate in uscita degli utenti abilitate per il routing basato sulla posizione è influenzato dalla posizione di rete dell'endpoint dell'utente. Nella tabella seguente viene illustrato il modo in cui il routing basato sulla posizione influenza il routing delle chiamate in uscita a seconda della posizione dell'endpoint del chiamante.

**Chiamante che effettua una chiamata in uscita alla rete PSTN**

||**Endpoint utente situato in un sito di rete abilitato per il routing basato sulla posizione**|**Endpoint utente situato in un sito di rete sconosciuto o non abilitato per il routing basato sulla posizione**|
|:-----|:-----|:-----|
|Autorizzazione delle chiamate in uscita  <br/> |La chiamata è autorizzata in base al criterio vocale dell'utente  <br/> |La chiamata è autorizzata in base al criterio vocale dell'utente  <br/> |
|Routing della chiamata in uscita  <br/> |La chiamata viene instradata in base ai criteri di routing vocale del sito di rete  <br/> |La chiamata viene instradata in base al criterio vocale dell'utente e solo tramite Trunks non abilitato per il routing basato sulla posizione (se disponibile)  <br/> |

### <a name="incoming-calls"></a>Chiamate in arrivo

Il routing delle chiamate in arrivo agli utenti abilitati per il routing basato sulla posizione dipende dalla posizione dell'endpoint dell'utente. Il routing delle chiamate in arrivo è influenzato dal modo seguente. Se un utente ha una chiamata in arrivo a un endpoint situato in un sito di rete abilitato per il routing basato sulla posizione e l'endpoint si trova nello stesso sito di rete del gateway PSTN, la chiamata verrà instradata. Se un utente ha una chiamata in arrivo a un endpoint situato in un sito di rete abilitato per il routing basato sulla posizione e l'endpoint si trova in un sito di rete diverso rispetto al gateway PSTN, la chiamata non verrà instradata. Quando un utente non ha endpoint situati nello stesso sito di rete del gateway PSTN in cui viene originata la chiamata in arrivo, la chiamata in arrivo verrà instradata direttamente alla segreteria telefonica dell'utente e verrà inviata una notifica di chiamata senza risposta alla festa chiamata.

Le impostazioni di inoltro di chiamata di un utente abilitato per il routing basato sulla posizione continueranno ad essere applicate, tuttavia, le chiamate inoltrate saranno soggette alle restrizioni di routing basate sulla posizione dell'utente.

Nella tabella seguente viene illustrato il modo in cui il routing basato sulla posizione influisce sul routing delle chiamate in ingresso a seconda della posizione dell'endpoint del destinatario. Il sito di rete del gateway PSTN è abilitato per il routing basato sulla posizione e il routing basato sulla posizione consente solo il routing delle chiamate PSTN agli endpoint nello stesso sito di rete.

**Chiamata in ricezione di una chiamata in ingresso dalla rete PSTN**

||**Endpoint di callee situato nello stesso sito di rete di gateway PSTN**|**Endpoint del destinatario non presente nello stesso sito di rete di gateway PSTN**|**Endpoint del destinatario situato nel sito di rete sconosciuto o non abilitato per il routing basato sulla posizione**|
|:-----|:-----|:-----|:-----|
|Routing della chiamata PSTN in ingresso  <br/> |La chiamata in arrivo viene instradata agli endpoint del chiamato  <br/> |La chiamata in arrivo non viene instradata agli endpoint del chiamato  <br/> |La chiamata in arrivo non viene instradata agli endpoint del chiamato  <br/> |

### <a name="call-transfers-and-call-forwarding"></a>Trasferimento e inoltro di chiamata

Quando si tratta di un endpoint PSTN, il routing basato sulla posizione analizza la posizione dell'endpoint di Calle e dell'endpoint in cui verrà trasferita o inoltrata la chiamata (ovvero destinazione di trasferimento/inoltro). Il routing basato sulla posizione determina se la chiamata deve essere trasferita o inoltrata a seconda della posizione di entrambi gli endpoint.

La tabella seguente illustra lo scenario di un utente Skype for business in una chiamata con un endpoint PSTN e l'utente di Skype for business trasferisce la chiamata a un altro utente di Skype for business. A seconda della posizione del sito di rete dell'endpoint del cessionario, il routing basato sulla posizione influenza il routing del trasferimento delle chiamate o inoltra.

**Avvio del trasferimento delle chiamate o dell'inoltro**

|**Utente che avvia il trasferimento/inoltro delle chiamate**|**L'endpoint di destinazione si trova nello stesso sito di rete dell'utente che avvia il trasferimento delle chiamate o inoltra**|**L'endpoint di destinazione è in un sito di rete diverso come utente che avvia il trasferimento delle chiamate o inoltra**|**Endpoint di destinazione in un sito di rete o un sito di rete sconosciuto non abilitato per il routing basato sulla posizione**|
|:-----|:-----|:-----|:-----|
|Utenti di Skype for business  <br/> |Inoltro di chiamata o trasferimento consentito  <br/> |La chiamata inoltra o transfer non è consentita  <br/> |La chiamata inoltra o transfer non è consentita  <br/> |

Ad esempio, un utente di Skype for business in una chiamata con un endpoint PSTN trasferisce la chiamata a un altro utente Skype for business che si trova nello stesso sito di rete. In questo caso, il trasferimento della chiamata è consentito.

La tabella seguente illustra lo scenario di un utente Skype for business in una chiamata con un altro utente Skype for business e uno degli utenti trasferisce la chiamata a un endpoint PSTN. A seconda della posizione dell'utente a cui viene trasferita la chiamata, la tabella descrive in che modo il routing basato sulla posizione influenza la chiamata.

**Trasferimento delle chiamate o inoltro all'endpoint PSTN**

|**Destinazione dell'endpoint trasferimento/inoltro chiamate**|**Utenti di Skype for business nello stesso sito di rete**|**Utenti di Skype for business in siti di rete diversi**|**Uno o entrambi gli utenti di Skype for business in un sito di rete o un sito di rete sconosciuto non è abilitato per il routing basato sulla posizione**|
|:-----|:-----|:-----|:-----|
|Endpoint PSTN  <br/> |Inoltro di chiamata o trasferimento consentito dal criterio di routing vocale del sito dell'utente trasferito  <br/> |Inoltro di chiamata o trasferimento consentito dal criterio di routing vocale del sito dell'utente trasferito  <br/> |Inoltro di chiamata o trasferimento consentito dal criterio vocale dell'utente trasferito solo tramite Trunks non abilitato per il routing basato sulla posizione  <br/> |

Ad esempio, un utente di Skype for business in una chiamata con un altro utente Skype for business che si trova nello stesso sito di rete trasferisce la chiamata a un endpoint PSTN e il trasferimento delle chiamate è consentito.

### <a name="simultaneous-ringing"></a>Squillo simultaneo

Quando l'entità denominata ha attivato la chiamata simultanea, il routing basato sulla posizione analizza la posizione della parte chiamante e gli endpoint delle parti chiamate per determinare se la chiamata deve essere instradata.

La tabella seguente illustra un utente configurato con squillo simultaneo e la destinazione di chiamata simultanea è un utente nello stesso sito di rete, in un sito di rete diverso o in un sito di rete sconosciuto.

****

|**Chiamata PSTN in arrivo per**|**Situato nello stesso sito di rete di un chiamato**|**Situato in un sito di rete diverso rispetto al chiamato**|**Si trova in un sito di rete sconosciuto o non è abilitato per il routing basato sulla posizione**|
|:-----|:-----|:-----|:-----|
|Utenti di Skype for business  <br/> |Squillo simultaneo consentito  <br/> |Anello simultaneo non consentito  <br/> |Anello simultaneo non consentito  <br/> |

La tabella seguente illustra una chiamata da un utente di Skype for business (ad esempio, il chiamante di Skype for business) nello stesso sito di rete, in un sito di rete diverso o da un sito di rete sconosciuto. Il chiamato ha un endpoint PSTN (i.e. cellulare) configurato come destinazione squillo simultaneo. In questo scenario, il routing basato sulla posizione determinerà se la chiamata deve essere instradata alla destinazione squillo simultanea (ad esempio cellulare) del destinatario o meno.

****

|**Destinazione anello simultaneo**|**Situato nello stesso sito di rete di un chiamato**|**Situato in un sito di rete diverso rispetto al chiamato**|**Si trova in un sito di rete sconosciuto o non è abilitato per il routing basato sulla posizione**|
|:-----|:-----|:-----|:-----|
|Endpoint PSTN  <br/> |Squillo simultaneo consentito tramite il criterio di routing vocale del sito del chiamante  <br/> |Squillo simultaneo consentito tramite il criterio di routing vocale del sito del chiamante  <br/> |Squillo simultaneo consentito tramite il criterio vocale del chiamante per Trunks non abilitato per il routing basato sulla posizione  <br/> |

### <a name="skype-for-business-cumulative-update-4"></a>Aggiornamento cumulativo di Skype for business 4

Con l'aggiornamento cumulativo 4 verrà visualizzata la seguente procedura:

- Il routing basato sulla posizione continuerà a essere abilitato tramite il criterio vocale, inclusi i client per dispositivi mobili Skype for business.

- Il comportamento delle chiamate per i client di Skype for business mobile sarà basato sul fatto che siano abilitati per il routing basato sulla posizione e il client di comunicazione. Questo è progettato per essere statico, ma in determinate situazioni può essere necessario associare un client mobile Skype for business a un gateway PSTN locale e consentire determinati comportamenti, ad esempio un'escalation

- Indipendentemente dal sistema operativo, il client per dispositivi mobili Skype for business dovrebbe avere la stessa funzionalità.

Nella tabella seguente vengono illustrati alcuni degli scenari di aggiornamento post-cumulativo 4:

|**Utente del routing basato sulla posizione**|**Altra parte**|**Azione**|**Risultato**|
|:-----|:-----|:-----|:-----|
|Skype for business per dispositivi mobili  <br/> |PSTN  <br/> |Skype for business mobile riceve una chiamata PSTN in arrivo.  <br/> |La chiamata viene instradata tramite chiamata tramite lavoro (CvW) e non VoIP.  <br/> |
|Skype for business per dispositivi mobili  <br/> |PSTN  <br/> |Skype for business mobile effettua una chiamata PSTN in uscita.  <br/> |La chiamata viene instradata tramite CvW e non VoIP.  <br/> |
|Skype for business per dispositivi mobili  <br/> |PSTN  <br/> |Skype for business mobile è in una chiamata PSTN. Skype for business mobile inoltra la chiamata a un altro utente o contatto.  <br/> |La chiamata viene instradata tramite VoIP se l'utente o il contatto è locale rispetto alla gamba del gateway PSTN.  <br/> Se l'utente o il contatto è remoto dalla gamba del gateway PSTN, la chiamata viene instradata tramite CvW.  <br/> Se l'utente di destinazione non è raggiungibile tramite la rete PSTN, la chiamata non riesce.  <br/> Se il contatto di destinazione è un operatore automatico di conferenza (CAA), la chiamata è bloccata.  <br/> |
|Skype for business per dispositivi mobili  <br/> |Client Skype for business o utente federato  <br/> |Un dispositivo mobile Skype for business avvia una chiamata vocale a un altro client Skype for business o a un utente federato.  <br/> |La chiamata viene completata tramite VoIP.  <br/> |
|Skype for business per dispositivi mobili  <br/> |Client Skype for business o utente federato  <br/> | Un client Skype for business o un utente federato avvia una chiamata vocale a un utente di routing basato sulla posizione di Skype for business mobile. <br/> |La chiamata viene completata tramite VoIP.  <br/> |
|Skype for business per dispositivi mobili  <br/> |Client Skype for business o utente federato  <br/> |Un client Skype for business o un utente federato si trova su una chiamata VoIP a un utente di Skype for business per dispositivi mobili. Una delle parti si escrescerà in un altro utente di Skype for business o federato.  <br/> |La chiamata viene completata tramite VoIP.  <br/> |
|Skype for business per dispositivi mobili  <br/> |Utente federato  <br/> |Un utente federato è in chiamata vocale a un utente di routing basato sulla posizione di Skype for business per dispositivi mobili; una parte di Skype for business mobile viene escalation a un utente PSTN.  <br/> |La chiamata è bloccata.  <br/> |
|Skype for business per dispositivi mobili  <br/> |Utente federato  <br/> |Un utente federato è in una chiamata VoIP a un utente di routing basato sulla posizione di Skype for business per dispositivi mobili; una delle parti viene escalation in un contatto CAA.  <br/> |La chiamata escalation è bloccata e viene visualizzato un messaggio di errore appropriato.  <br/> |
|Skype for business per dispositivi mobili  <br/> |Utente federato  <br/> |Un utente federato è in una chiamata VoIP a un utente di routing basato sulla posizione di Skype for business mobile e l'utente federato viene escalato in un utente PSTN.  <br/> |L'escalation sarà consentita o non consentita in base al routing basato sulla posizione dell'utente federato. L'applicazione dell'utente del routing basato sulla posizione di Skype for business per dispositivi mobili non accetta alcuna azione.  <br/> |

### <a name="delegation"></a>Delega

Le funzionalità di delega in Skype for business sono influenzate dal routing basato sulla posizione nel modo seguente:

- Quando un delegato abilitato per il routing basato sulla posizione effettua una chiamata per conto di un Manager, il criterio vocale del delegato viene usato per autorizzare la chiamata e i criteri di routing vocale del sito del delegato verranno usati per instradare la chiamata

- Per le chiamate PSTN in arrivo a un responsabile, le stesse regole applicabili per l'inoltro di chiamata o lo squillo simultaneo verranno applicate come descritto negli argomenti trasferimento chiamate e inoltro e squillo simultaneo.

- Quando un delegato imposta un endpoint PSTN come destinazione squillo simultaneo, per una chiamata in arrivo al Manager, il criterio di routing vocale del sito associato al trunk in arrivo verrà usato per instradare la chiamata all'endpoint PSTN del delegato.

- Per la delega, è consigliabile che il responsabile e i delegati associati si trovino in genere nello stesso sito di rete.

## <a name="other-planning-considerations"></a>Altre considerazioni sulla pianificazione

Quando si pianifica il routing basato sulla posizione, è consigliabile considerare l'impatto sugli scenari seguenti.

### <a name="disaster-recovery"></a>Ripristino di emergenza

Durante un failover dal pool principale a un pool di backup e quando si ripristinano le normali operazioni nel pool principale, il routing basato sulla posizione rimane imposto in qualsiasi momento durante una procedura di emergenza e ripristino.

### <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

La configurazione del routing basato sulla posizione ha un impatto sulla pianificazione della distribuzione dei gateway associati agli elettrodomestici Survivable Branch. Il gateway associato alla SBA deve trovarsi nello stesso sito di rete dell'appliance Survivable Branch; in caso contrario, gli utenti residenti nell'appliance Survivable Branch non saranno autorizzati a inserire chiamate in uscita se è configurato il routing basato sulla posizione. Quando la connessione WAN tra l'appliance Survivable Branch e il sito centrale è in calo, le restrizioni di routing basate sulla posizione restano applicate.

## <a name="client-and-server-support-for-location-based-routing"></a>Supporto per client e server per il routing in base alla posizione

Il routing basato sulla posizione viene applicato da Skype for Business Server. Skype for Business Server può identificare i siti di rete in cui gli utenti si connettono dall'interno della rete aziendale. Poiché gli utenti remoti si trovano all'esterno della rete aziendale, la loro posizione è considerata sconosciuta.

### <a name="server-support"></a>Supporto server

Il routing basato sulla posizione richiede che Skype for Business Server o Lync Server 2013 CU1 sia distribuito in tutti i pool Front end e nei server Standard Edition in una determinata topologia. Se queste versioni del server non sono installate, le restrizioni di routing basate sulla posizione non possono essere applicate completamente.

La tabella seguente identifica la combinazione di ruoli server e versioni supportate per il routing basato sulla posizione.

****

|**Versione pool**|**Versione Mediation Server**|**Supportati**|
|:-----|:-----|:-----|
|Aggiornamento cumulativo di Skype for Business Server o Lync Server 2013 febbraio 2013  <br/> |Aggiornamento cumulativo di Skype for Business Server o Lync Server 2013 febbraio 2013  <br/> |Sì  <br/> |
|Aggiornamento cumulativo di Skype for Business Server o Lync Server 2013 febbraio 2013  <br/> |Lync Server 2013  <br/> |non  <br/> |
|Aggiornamento cumulativo di Skype for Business Server o Lync Server 2013 febbraio 2013  <br/> |Lync Server 2010  <br/> |non  <br/> |
|Aggiornamento cumulativo di Skype for Business Server o Lync Server 2013 febbraio 2013  <br/> |Office Communications Server 2007 R2  <br/> |non  <br/> |
|Lync Server 2013  <br/> |qualsiasi  <br/> |non  <br/> |
|Lync Server 2010  <br/> |qualsiasi  <br/> |non  <br/> |
|Office Communications Server 2007 R2  <br/> |qualsiasi  <br/> |non  <br/> |

### <a name="client-support"></a>Supporto client

La tabella seguente identifica i client supportati dal routing basato sulla posizione.

****

|**Tipo di client**|**Supportati**|**Dettagli**|
|:-----|:-----|:-----|
|Skype for business  <br/> |Sì  <br/> ||
|Lync 2013  <br/> |Sì  <br/> ||
|Lync 2010  <br/> |Sì  <br/> ||
|Office Communicator 2007 R2  <br/> |non  <br/> ||
|Lync Phone Edition  <br/> |Sì  <br/> ||
|Assistente di Lync  <br/> |Sì  <br/> ||
|Lync per Windows 8  <br/> |non  <br/> ||
|Lync Mobile 2013  <br/> |non  <br/> |Il VoIP deve essere disabilitato per i client Lync Mobile 2013 se usato dagli utenti con il routing basato sulla posizione abilitato.  <br/> |
|Lync Mobile 2010  <br/> |Sì  <br/> ||

> [!NOTE]
> Per disabilitare il VoIP per i client Skype for business, assegna un criterio di mobilità con l'impostazione, l'audio/video IP, disabilitato per tutti gli utenti abilitati per il routing basato sulla posizione. Per altre informazioni sui criteri di mobilità, vedere [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).

## <a name="capabilities-not-supported-by-location-based-routing"></a>Funzionalità non supportate dal routing in base alla posizione

Il routing basato sulla posizione non si applica ai tipi di interazioni seguenti. Il routing basato sulla posizione non viene applicato quando gli endpoint di Skype for business interagiscono con endpoint PSTN usando queste funzionalità.

- Accesso esterno PSTN alle conferenze

- Chiamate PSTN in arrivo e in uscita tramite Response Group

- Parcheggio di chiamata o recupero di chiamate PSTN tramite Call Park

- Chiamate PSTN in arrivo per il servizio annunci

- Chiamate PSTN in arrivo recuperate tramite raccolta chiamate di gruppo

Per applicare regole di routing basate sul percorso ai tipi di interazioni nell'elenco seguente, è necessario abilitare il routing basato sulla posizione per i servizi di conferenza:

- Chiamata PSTN dalle conferenze

- Escalation dalle conversazioni audio peer-to-peer alle conferenze che coinvolgono endpoint PSTN

- Trasferimenti consultivi che coinvolgono endpoint PSTN

Per abilitare il routing basato sulla posizione per i servizi di conferenza, vedere [routing basato sulla posizione per i](https://technet.microsoft.com/library/e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3.aspx)servizi di conferenza.


