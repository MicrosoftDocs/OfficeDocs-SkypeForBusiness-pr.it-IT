---
title: Topologie di riferimento per Skype for Business Server
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
ms.assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
description: Fare riferimento a topologie per Skype for Business Server, inclusi i diagrammi e le decisioni da apportare alle organizzazioni grandi, medie e piccole.
ms.openlocfilehash: 7f284b141da25175e3a41545349a0e61f6036019
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "37028354"
---
# <a name="reference-topologies-for-skype-for-business-server"></a>Topologie di riferimento per Skype for Business Server

Fare riferimento a topologie per Skype for Business Server, inclusi i diagrammi e le decisioni da apportare alle organizzazioni grandi, medie e piccole.

La topologia di Skype for Business Server migliore dipende dalle dimensioni dell'organizzazione, dai carichi di lavoro che si vogliono distribuire e dalle preferenze per l'elevata disponibilità e il costo degli investimenti.

Questa sezione descrive tre topologie di riferimento di esempio, incluso il ragionamento dietro molte delle decisioni che hanno fattorizzato ogni topologia.

## <a name="reference-topology-for-a-small-organization"></a>Topologia di riferimento per una piccola organizzazione

La topologia di riferimento per le piccole organizzazioni Mostra come distribuire una soluzione robusta e altamente disponibile distribuendo solo tre server con Skype for Business Server.

**Topologia di riferimento per piccole organizzazioni**

![Diagramma della topologia di riferimento per la distribuzione di tre server](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology1.jpg)

- **Coppia di server standard distribuiti** Questa organizzazione ha 4.000 utenti nel loro sito centrale. Hanno distribuito due server Standard Edition e li hanno abbinati per consentire l'elevata disponibilità e il ripristino di emergenza. Ogni server abita 2.000 utenti, ma le informazioni su tutti gli utenti vengono sincronizzate tra i due server. Se si abbassa, un amministratore può eseguire il failover di questi utenti per essere serviti dall'altro server, con un minimo di interruzioni per gli utenti. Per altre informazioni sulle caratteristiche di disponibilità elevata e ripristino di emergenza in Skype for Business Server, vedere [pianificare l'elevata disponibilità e il ripristino di emergenza in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- **È consigliabile distribuire Edge Server.** Anche se la distribuzione di un server perimetrale non è necessaria per la messaggistica istantanea, la presenza e le conferenze interne, è consigliabile anche per piccole distribuzioni. Puoi massimizzare l'investimento di Skype for Business Server distribuendo un server perimetrale per prestare servizio agli utenti al di fuori dei firewall dell'organizzazione. I vantaggi includono i seguenti:

  - Gli utenti dell'organizzazione possono usare le funzionalità di Skype for Business Server, se lavorano da casa o sono in viaggio.

  - Gli utenti possono invitare utenti esterni a partecipare alle riunioni.

  - Se si ha un partner, un fornitore o un'organizzazione di clienti che usa anche Skype for Business Server, è possibile creare una relazione federata con tale organizzazione. La distribuzione di Skype for Business Server riconoscerebbe quindi gli utenti di tale organizzazione federata, con una migliore collaborazione.

  - Gli utenti possono scambiare messaggi istantanei con utenti di alcuni servizi di messaggistica istantanea pubblica.

- **Sopravvivenza del sito della filiale.** Questa organizzazione sta usando un programma pilota della funzionalità VoIP aziendale di Skype for Business Server. Alcuni utenti usano Skype for Business Server come soluzione unica per la voce. Alcuni di questi utenti di Enterprise Voice Pilot si trovano nel sito della filiale. Il sito di succursale non ha un collegamento WAN (Wide Area Network) affidabile al sito centrale, quindi viene distribuito un Survivable Branch Appliance. Con questa distribuzione, se il collegamento WAN si abbassa, gli utenti del sito della filiale possono ancora effettuare e ricevere chiamate (sia le chiamate all'interno dell'organizzazione che le chiamate PSTN), avere la funzionalità della segreteria telefonica e comunicare con messaggistica istantanea a due parti. Gli utenti possono essere autenticati anche quando il collegamento WAN non è disponibile. Per altre informazioni, vedere [pianificare la resilienza di VoIP aziendale in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Distribuzione della messaggistica unificata di Exchange.** Questa topologia di riferimento include un server di messaggistica UNIFICAta di Exchange, che esegue Microsoft Exchange Server e non Skype for Business Server.

- **Server di Office Web Apps.** È consigliabile distribuire un server di Office Web Apps o una server farm di Office Web Apps in tutte le organizzazioni che usano servizi di conferenza Web. Office Web Apps Server consente alle diapositive di PowerPoint di essere presentate in conferenze Web.

## <a name="reference-topology-for-a-medium-organization"></a>Topologia di riferimento per un'organizzazione media

La topologia di riferimento con elevata disponibilità e un singolo centro dati è progettata per un'organizzazione di piccole e medie dimensioni con un sito centrale. La topologia esatta nel diagramma seguente è per un'organizzazione di utenti di 20.000.

**Topologia di riferimento per le organizzazioni medie**

![Diagramma della topologia di riferimento per un singolo data center](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology2.jpg)

- **Accogliere più utenti aggiungendo altri server front-end.** La topologia esatta in questo diagramma include tre server front-end per consentire il supporto per gli utenti di 20.000. Se si dispone di un singolo sito centrale e di più utenti, è possibile aggiungere semplicemente altri server front-end al pool. Il numero massimo di utenti per pool è 80.000, con dodici server front-end.

    Tuttavia, la singola topologia del sito può supportare ancora più utenti aggiungendo un altro pool Front end al sito.

- **Potrebbe essere aggiunto il ripristino di emergenza.** Per questa organizzazione, la disponibilità elevata per i servizi di Skype for Business Server è una caratteristica necessaria, ma il ripristino di emergenza non lo è. Il pool di server front-end distribuiti offre una disponibilità elevata.

    Se si vuole aggiungere un'abilità di ripristino di emergenza, è possibile valutare la possibilità di creare un altro Data Center e aggiungere un altro pool di front-end e associarlo al pool Front-End nel Data Center corrente. In caso di un disastro che influisce sul pool principale, gli amministratori potrebbero non eseguire il failover degli utenti nel pool di backup.

- **Server back-end con mirroring** Per ottenere una disponibilità più elevata per le funzionalità utente di base, l'organizzazione ha distribuito una coppia speculare di server back-end per ogni pool Front-end.

- **Opzioni di database del server di monitoraggio.** Questa organizzazione ha implementato il monitoraggio per garantire la qualità delle chiamate vocali aziendali e delle conferenze A/V. Il monitoraggio viene distribuito in tutti i server front-end e il database di monitoraggio è collocato con i server back-end. Supportiamo anche le topologie in cui il database di monitoraggio si trova in un server separato.

- **Disponibilità elevata in Edge Server** In questo esempio di organizzazione con gli utenti di 20.000 è sufficiente un solo Edge Server per le prestazioni. Tuttavia, hanno distribuito un pool di due server perimetrali distribuiti per ottenere una disponibilità elevata.

- **Opzioni di distribuzione del sito di succursale.** L'organizzazione in questa topologia ha distribuito VoIP aziendale come soluzione vocale. Il sito della filiale 1 non ha un collegamento WAN (Wide Area Network) resiliente al sito centrale, quindi ha un Survivable Branch Appliance distribuito per gestire molte caratteristiche di Skype for Business Server nel caso in cui il collegamento WAN al sito centrale vada giù. Il sito della filiale 2 ha tuttavia un collegamento WAN resiliente, quindi è necessario solo un gateway PSTN (Public Switched Telephone Network). Il gateway PSTN distribuito supporta il bypass multimediale, quindi non è necessario alcun Mediation Server nel sito della filiale 2. Per altre informazioni, vedere [pianificare la resilienza di VoIP aziendale in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Bilanciamento del carico DNS.** Il pool Front-end e il pool Edge Server hanno il bilanciamento del carico DNS per il traffico SIP distribuito. In questo modo, viene eliminata la necessità di un bilanciamento del carico hardware per gli Edge Server e si riduce significativamente la configurazione e la manutenzione dei dispositivi di bilanciamento del carico hardware per gli altri pool, poiché i dispositivi di bilanciamento del carico hardware sono necessari solo per il traffico HTTP. Per altre informazioni, Vedi [bilanciamento del carico DNS](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Distribuzione della messaggistica unificata di Exchange.** Questa topologia di riferimento include un server di messaggistica UNIFICAta di Exchange, che esegue Microsoft Exchange Server e non Skype for Business Server.

- **Server di Office Web Apps.** È consigliabile distribuire un server di Office Web Apps o una server farm di Office Web Apps in tutte le organizzazioni che usano servizi di conferenza Web. Office Web Apps Server rende possibile la presentazione di diapositive di PowerPoint in conferenze Web.

- **Gli amministratori possono essere aggiunti.** Se l'organizzazione ha voluto aiutare ad aumentare la sicurezza dagli attacchi Denial of Service, potrebbe anche distribuire un pool di direttori. Un amministratore è un ruolo di server facoltativo separato in Skype for Business Server che non ospita gli account utente o offre servizi di conferenza o presenza. Funge da server hop interno successivo a cui un Edge Server instrada il traffico SIP in ingresso destinato ai server interni. Il direttore esegue la pre-autenticazione delle richieste in ingresso e le reindirizza al server o al pool Home dell'utente. La pre-autenticazione presso il Director consente di eliminare le richieste da account utente sconosciuto alla distribuzione. Un amministratore consente di isolare i server front-end da traffico illecito, ad esempio attacchi DoS (Denial of Service). Se la rete viene allagata con traffico esterno non valido in un attacco di questo tipo, il traffico termina con il direttore.

- **È consigliabile System Center Operations Manager.** Ti consigliamo di monitorare l'integrità della distribuzione di Skype for Business Server per garantire la disponibilità dei servizi per gli utenti finali. È possibile usare il Management Pack di System Center Operations Manager per Skype for business, disponibile come download gratuito da Microsoft. Con Skype for Business Management Pack puoi ottenere gli avvisi in tempo reale quando si verificano problemi, eseguire transazioni sintetiche per testare le funzionalità di Skype for business end-to-end, ottenere report per la disponibilità del servizio e così via. Questo consente di rispondere in modo proattivo ai problemi della distribuzione prima che gli utenti finali li sperimentino.

## <a name="reference-topology-for-a-large-organization"></a>Topologia di riferimento per un'organizzazione di grandi dimensioni

La topologia di riferimento per un'organizzazione di grandi dimensioni con il supporto di più centri dati è per tutte le dimensioni dell'organizzazione con più di un sito centrale. La topologia esatta nel diagramma seguente è destinata a un'organizzazione di utenti di 50.000, con 20.000 utenti nel sito centrale A, 20.000 presso il sito centrale B. e un totale di 10.000 presso il sito centrale C e i siti di succursale. Il tipo di topologia illustrato in questo diagramma può ospitare le organizzazioni con un numero qualsiasi di utenti.

Oltre alla disponibilità elevata fornita dai pool di server front-end, questa topologia aggiunge il supporto per il ripristino di emergenza. I pool Front-end dei siti centrali A e B sono associati tra loro. Se uno di questi pool scende, l'amministratore può spostare i servizi per gli utenti interessati nel pool associato al sito non interessato.

Questa topologia è illustrata in più diagrammi, con una panoramica seguita da visualizzazioni dettagliate dei siti centrali.

**Panoramica della topologia di riferimento per le organizzazioni di grandi dimensioni con più centri dati**

![Topologia di riferimento per più data center](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-1-new.jpg)

**Topologia di riferimento per le organizzazioni di grandi dimensioni: visualizzazione dettagliata del sito centrale A**

![Topologia 3-2](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-2.jpg)

**Topologia di riferimento per le organizzazioni di grandi dimensioni: visualizzazione dettagliata del sito centrale B**

![Topologia 3-3](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-3.jpg)

**Topologia di riferimento per le organizzazioni di grandi dimensioni: visualizzazione dettagliata del sito centrale C**

![Topologia 3-4](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-4.jpg)

- **I pool Front-End sono associati per consentire il ripristino di emergenza.** I pool Front-end del sito A e del sito B sono associati tra loro per consentire il supporto per il ripristino di emergenza. Se il pool di un sito non riesce, l'amministratore può eseguire il failover degli utenti da tale sito al pool Front-end associato dell'altro sito, con un minimo di interruzioni dei servizi per gli utenti. Ognuno di questi due pool Front-end include sei server, che sono sufficienti per tutti gli utenti di 40.000 in entrambi i pool in caso di failover. Per altre informazioni, Vedi [pianificare l'elevata disponibilità e il ripristino di emergenza in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- **Server back-end con mirroring** Per ottenere una disponibilità più elevata per le funzionalità utente di base, l'organizzazione ha distribuito una coppia speculare di server back-end per ogni pool Front-end. Si tratta di una topologia facoltativa e si può scegliere di distribuire un singolo server back-end. Sono supportati anche i cluster SQL e i gruppi di disponibilità AlwaysOn. Per altre informazioni, vedi la [disponibilità elevata del server back-end in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

- **Uso di server standard in un sito di succursale.** Questa organizzazione considera il sito C come sito di succursale perché ha solo 600 dipendenti. Tuttavia, gli utenti hanno molte conferenze A/V tra di loro. Se è stata distribuita in Skype for Business Server come sito di succursale, il supporto per queste conferenze verrebbe eseguito attraverso la rete WAN e da un sito centrale con un server front-end distribuito. Per evitare questo potenziale carico di larghezza di banda, hanno installato una coppia di server standard in questo sito, che ospiterà queste conferenze. E dato che i server standard sono installati in questa pagina, Skype for Business Server per definizione lo considera un sito centrale e viene trattato come tale in Generatore di topologie e nello strumento di pianificazione.

    Solo un server Standard Edition sarebbe sufficiente per le prestazioni, ma l'organizzazione ha distribuito due e li ha associati per ottenere una disponibilità elevata nel caso in cui un server scendesse.

    Anche se il sito C è considerato un sito centrale, non è necessario distribuire i server perimetrali. In questo esempio, il sito C utilizzerà gli Edge Server distribuiti nel sito A.

- **Monitoraggio e archiviazione** Questa organizzazione ha implementato sia il monitoraggio che l'archiviazione. Quando si distribuisce il monitoraggio o l'archiviazione, viene eseguito in ogni server front-end. I database per queste funzionalità possono essere collocati nel database di back-end o in un server separato. Questa organizzazione ha individuato questi database in un server separato dai server back-end, nel sito centrale B. I database qui ricevono il monitoraggio e l'archiviazione dei dati dai server front-end in tutti i siti.

- **Opzioni di distribuzione del sito di succursale.** Questa organizzazione ha in realtà oltre 50 siti di succursale, solo due dei quali sono mostrati nei diagrammi dettagliati. Il sito della filiale 1 non ha un collegamento WAN resiliente al sito centrale, in modo che abbiano gli elettrodomestici Survivable Branch distribuiti per consentire il servizio telefonico nel caso il collegamento WAN al sito centrale vada giù. Il sito della filiale 2 ha tuttavia un collegamento WAN resiliente, quindi necessita solo di un gateway PSTN (Public Switched Telephone Network). Il gateway PSTN distribuito supporta il bypass multimediale, quindi non è necessario alcun Mediation Server nel sito della filiale 2. Per informazioni dettagliate su come decidere cosa installare in un sito di succursale, vedere [pianificare la resilienza di Enterprise Voice in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Trunking SIP e Mediation Server.** Si noti che nel sito centrale B, Mediation Server non è collocato con i server front-end. Questo avviene perché Mediation Server autonomo è consigliato per i siti che usano il trunking SIP. Nella maggior parte delle altre istanze ti consigliamo di collocare Mediation Server con Front End Server. Per informazioni dettagliate sulle topologie di Mediation Server, vedere [componenti e topologie per Mediation Server](https://technet.microsoft.com/library/71397168-36c3-4d21-b8ef-db6a751634ee.aspx) nella documentazione relativa alla pianificazione.

- **La chat persistente viene distribuita.** Questa organizzazione ha distribuito i server necessari per abilitare la chat persistente. Ha distribuito più server front-end della chat persistente per gestire il carico per il numero di utenti nel pool e per ottenere una disponibilità elevata. Ha inoltre implementato la conformità per la chat persistente e ha individuato l'Archivio Chat persistente e l'archivio conformità della chat persistente in server distinti. Questi archivi potrebbero essere collocati e possono essere collocati anche con il server back-end, ma questa organizzazione ha scelto di separarli per ottenere prestazioni migliori.

    > [!NOTE]
    > La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015.

- **Bilanciamento del carico DNS.** Il pool Front-end e il pool Edge Server usano il bilanciamento del carico DNS. In questo modo, viene eliminata l'esigenza di usare il bilanciamento del carico hardware per l'interfaccia interna di Edge Server e si riduce significativamente la quantità di tempo necessario per la configurazione e la manutenzione dei dispositivi di bilanciamento del carico hardware per gli altri pool, come il caricamento hardware Gli equilibristi sono necessari solo per il traffico HTTP. Per altre informazioni, vedere (.. /.. /plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Distribuzione della messaggistica unificata di Exchange.** Skype for Business Server funziona sia con le distribuzioni locali della messaggistica unificata di Exchange che con la messaggistica unificata di Exchange ospitata. Il sito centrale A include un server di messaggistica UNIFICAta di Exchange, che esegue Microsoft Exchange Server e non Skype for Business Server. La funzionalità di messaggistica unificata di Exchange per Skype for Business Server viene eseguita nel pool Front-end.

    Il sito centrale B usa Exchange ospitata, quindi ospita anche la funzionalità del server Messaggistica unificata di Exchange.

    Per informazioni dettagliate sulla messaggistica unificata di Exchange, vedere integrazione della messaggistica unificata di Exchange [locale](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) e [integrazione della messaggistica unificata di Exchange ospitata](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx) nella documentazione relativa alla pianificazione.

- **Server di Office Web Apps.** È consigliabile distribuire un server di Office Web Apps o una server farm di Office Web Apps in tutte le organizzazioni che usano servizi di conferenza Web. È possibile distribuire una singola farm di Office Web Apps in un sito che serve traffico da tutti i siti o distribuirlo in ogni sito. Office Web Apps Server rende possibile la presentazione di diapositive di PowerPoint in conferenze Web.

- **Gli amministratori possono essere aggiunti.** Se l'organizzazione vuole aumentare la sicurezza dagli attacchi Denial of Service, potrebbe anche distribuire un pool di direttori. Un amministratore è un ruolo di server facoltativo separato in Skype for Business Server che non ospita gli account utente o offre servizi di conferenza o presenza. Funge da server hop interno successivo a cui un Edge Server instrada il traffico SIP in ingresso destinato ai server interni. Il direttore esegue la pre-autenticazione delle richieste in ingresso e le reindirizza al server o al pool Home dell'utente. La pre-autenticazione presso il Director consente di eliminare le richieste da account utente sconosciuto alla distribuzione. Un amministratore consente di isolare i server front-end da traffico illecito, ad esempio attacchi DoS (Denial of Service). Se la rete viene allagata con traffico esterno non valido in un attacco di questo tipo, il traffico termina con il direttore.

- **È consigliabile System Center Operations Manager.** Ti consigliamo di monitorare l'integrità della distribuzione di Skype for Business Server per garantire la disponibilità dei servizi per gli utenti finali. È possibile usare il Management Pack di System Center Operations Manager per Skype for business, disponibile come download gratuito da Microsoft. Con Skype for Business Management Pack puoi ottenere gli avvisi in tempo reale quando si verificano problemi, eseguire transazioni sintetiche per testare le funzionalità di Skype for business end-to-end, ottenere report per la disponibilità del servizio e così via. Questo consente di rispondere in modo proattivo ai problemi della distribuzione prima che gli utenti finali li sperimentino.


