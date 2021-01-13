---
title: Topologie di riferimento per Skype for Business Server
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
ms.assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
description: Topologie di riferimento per Skype for Business Server, compresi i diagrammi e le decisioni da prendere per le organizzazioni di grandi dimensioni, medie e piccole.
ms.openlocfilehash: 958f6630faf295a16aebe7513ee9e5c98daeeaa5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831736"
---
# <a name="reference-topologies-for-skype-for-business-server"></a>Topologie di riferimento per Skype for Business Server

Topologie di riferimento per Skype for Business Server, compresi i diagrammi e le decisioni da prendere per le organizzazioni di grandi dimensioni, medie e piccole.

La migliore topologia di Skype for Business Server dipende dalle dimensioni dell'organizzazione, dai carichi di lavoro che si desidera distribuire e dalle preferenze per la disponibilità elevata rispetto al costo degli investimenti.

In questa sezione vengono illustrate tre topologie di riferimento di esempio, tra cui il ragionamento dietro molte delle decisioni che sono state fattorizzate in ogni topologia.

## <a name="reference-topology-for-a-small-organization"></a>Topologia di riferimento per un'organizzazione di piccole dimensioni

La topologia di riferimento per le organizzazioni di piccole dimensioni dimostra come è possibile distribuire una soluzione robusta e a disponibilità elevata distribuendo solo tre server che eseguono Skype for Business Server.

**Topologia di riferimento per le organizzazioni di piccole dimensioni**

![Topologia di riferimento per la distribuzione di tre server diagramma](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology1.jpg)

- **Coppia di server Standard Edition distribuiti** Questa organizzazione dispone di 4.000 utenti nel sito centrale. Sono stati distribuiti due server Standard Edition e li hanno associati insieme per abilitare la disponibilità elevata e il ripristino di emergenza. Ogni server Homes 2.000 utenti, ma le informazioni su tutti gli utenti vengono sincronizzate tra i due server. Se si abbassa, un amministratore può avere esito negativo su quegli utenti che devono essere serviti dall'altro server, con un minimo di interruzioni per gli utenti. Per ulteriori informazioni sulle funzionalità di disponibilità elevata e ripristino di emergenza in Skype for Business Server, vedere [pianificare la disponibilità elevata e il ripristino di emergenza in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- **È consigliata la distribuzione di un server perimetrale.** Anche se non è necessario distribuire un server perimetrale per la messaggistica istantanea interna, la presenza e le conferenze, è consigliabile utilizzarne uno persino per le distribuzioni di piccole dimensioni. È possibile massimizzare l'investimento di Skype for Business Server distribuendo un server perimetrale per fornire il servizio agli utenti attualmente esterni ai firewall dell'organizzazione. Tra i vantaggi derivanti dall'utilizzo di server perimetrali sono inclusi i seguenti:

  - Gli utenti dell'organizzazione possono utilizzare le funzionalità di Skype for Business Server, se lavorano da casa o sono in viaggio.

  - Gli utenti possono invitare utenti esterni a partecipare alle riunioni.

  - Se si dispone di un partner, un fornitore o un'organizzazione del cliente che utilizza anche Skype for Business Server, è possibile creare una relazione federata con tale organizzazione. La distribuzione di Skype for Business Server dovrebbe quindi riconoscere gli utenti provenienti da tale organizzazione federata, portando a una migliore collaborazione.

  - Gli utenti possono scambiare messaggi istantanei con gli utenti di alcuni servizi di messaggistica istantanea pubblica.

- **Funzionamento garantito per i siti di succursale.** In questa organizzazione è in esecuzione un programma pilota della caratteristica VoIP aziendale di Skype for Business Server. Alcuni utenti usano Skype for Business Server come soluzione unica per la voce. Alcuni di questi utenti pilota di VoIP aziendale si trovano nel sito di succursale. Il sito di succursale non dispone di un collegamento WAN (Wide Area Network) affidabile al sito centrale, quindi viene distribuito un Survivable Branch Appliance. Con questa distribuzione, se il collegamento WAN si abbassa, gli utenti del sito di succursale possono ancora effettuare e ricevere chiamate (sia le chiamate all'interno dell'organizzazione che le chiamate PSTN), hanno la funzionalità della segreteria telefonica e comunicano con la messaggistica istantanea con due parti. Gli utenti possono inoltre essere autenticati anche quando il collegamento WAN non è disponibile. Per ulteriori informazioni, vedere [pianificare la resilienza di VoIP aziendale in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Distribuzione di Messaggistica unificata di Exchange.** Questa topologia di riferimento include un server di messaggistica unificata di Exchange, che esegue Microsoft Exchange Server, non Skype for Business Server.

- **Server Office Web Apps.** È consigliabile distribuire un server Office Web Apps o una farm di server Office Web Apps in ogni organizzazione che utilizza le conferenze Web. Il server Office Web Apps rende possibile la presentazione di diapositive di PowerPoint nelle conferenze Web.

## <a name="reference-topology-for-a-medium-organization"></a>Topologia di riferimento per un'organizzazione di medie dimensioni

La topologia di riferimento con disponibilità elevata e un solo data center è specifica per un'organizzazione di piccole-medie dimensioni con un unico sito centrale. La topologia esatta nel diagramma seguente è destinata a un'organizzazione di 20.000 utenti.

**Topologia di riferimento per le organizzazioni di medie dimensioni**

![Topologia di riferimento per un singolo diagramma Data Center](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology2.jpg)

- **Supporto di più utenti aggiungendo più Front End Server.** La topologia esatta in questo diagramma ha tre Front End Server per fornire il supporto per gli utenti di 20.000. Se si dispone di un singolo sito centrale e di più utenti, è sufficiente aggiungere più front end server al pool. Il numero massimo di utenti per pool è 80.000, con dodici front end server.

    Tuttavia, la topologia del sito singolo può supportare anche altri utenti aggiungendo un altro pool Front end al sito.

- **È possibile aggiungere il ripristino di emergenza.** Per questa organizzazione, la disponibilità elevata per i servizi di Skype for Business Server è una funzionalità necessaria, ma il ripristino di emergenza non lo è. Il pool di front end server distribuiti garantisce una disponibilità elevata.

    Se si desidera aggiungere un'abilità di ripristino di emergenza, è possibile prendere in considerazione l'impostazione di un altro Data Center e l'aggiunta di un altro pool Front end e l'abbinamento con il pool Front End nel Data Center corrente. Quindi, se si è verificato un errore che influisce sul pool primario, gli amministratori possono eseguire il failover degli utenti nel pool di backup.

- **Mirroring dei server back-end** Per garantire una disponibilità elevata per le funzionalità utente di base, l'organizzazione ha distribuito una coppia di server back-end con mirroring per ogni pool Front end.

- **Opzioni di database del Monitoring Server.** Questa organizzazione ha implementato il monitoraggio per garantire la qualità delle chiamate vocali e delle conferenze audio/video aziendali. Il monitoraggio viene distribuito in tutti i Front End Server e il database di monitoraggio è collocato con i server back-end. È inoltre supportata la topologia in cui il database di monitoraggio si trova su un server separato.

- **Disponibilità elevata del server perimetrale** In questo esempio di organizzazione con 20.000 utenti, solo un server perimetrale sarebbe sufficiente per le prestazioni. Tuttavia, è stato distribuito un pool di due server perimetrali distribuiti per garantire una disponibilità elevata.

- **Opzioni di distribuzione del sito di succursale.** Nell'organizzazione di questa topologia è distribuito VoIP aziendale come soluzione vocale. Il sito di succursale 1 non ha un collegamento WAN (Wide Area Network) resiliente al sito centrale, quindi ha un Survivable Branch Appliance distribuito per mantenere molte caratteristiche di Skype for Business Server, nel caso in cui il collegamento WAN al sito centrale venga inattivo. Nel Sito di succursale 2 invece è presente un collegamento WAN resiliente e pertanto è necessario solo un gateway PSTN (Public Switched Telephone Network). Poiché il gateway PSTN distribuito supporta il bypass multimediale, non sono necessari Mediation Server nel Sito di succursale 2. Per ulteriori informazioni, vedere [pianificare la resilienza di VoIP aziendale in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Bilanciamento del carico DNS.** Il pool Front end e il pool di server perimetrali dispongono del bilanciamento del carico DNS per il traffico SIP distribuito. In questo modo si evita di dover utilizzare dispositivi di bilanciamento del carico hardware per i server perimetrali, riducendo in modo significativo le attività di configurazione e manutenzione dei dispositivi di bilanciamento del carico hardware per gli altri pool, poiché i dispositivi di bilanciamento del carico hardware sono necessari solo per il traffico HTTP. Per ulteriori informazioni, vedere [bilanciamento del carico DNS](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Distribuzione di Messaggistica unificata di Exchange.** Questa topologia di riferimento include un server di messaggistica unificata di Exchange, che esegue Microsoft Exchange Server, non Skype for Business Server.

- **Server Office Web Apps.** È consigliabile distribuire un server Office Web Apps o una farm di server Office Web Apps in ogni organizzazione che utilizza le conferenze Web. Il server Office Web Apps rende possibile la presentazione di diapositive di PowerPoint nelle conferenze Web.

- **È possibile aggiungere i Director.** Se l'organizzazione ha voluto contribuire a migliorare la sicurezza contro gli attacchi Denial of Service, potrebbe anche distribuire un pool di Director. Un amministratore è un ruolo del server facoltativo separato in Skype for Business Server che non ospita account utente o che fornisce servizi di conferenza o presenza. Funge da server hop successivo interno a cui un server perimetrale instrada il traffico SIP in ingresso destinato ai server interni. Il Director esegue la preautenticazione delle richieste in ingresso e le reindirizza al pool o al server Home dell'utente. La preautenticazione nel server Director consente di eliminare le richieste provenienti da account utente sconosciuti alla distribuzione. Un amministratore consente di isolare i Front End Server da traffico dannoso, ad esempio attacchi DoS (Denial of Service). Se la rete viene inondata di traffico esterno non valido in un attacco di questo tipo, il traffico termina nel server Director.

- **È consigliabile utilizzare System Center Operations Manager.** Si consiglia di monitorare l'integrità della distribuzione di Skype for Business Server per garantire la disponibilità del servizio per gli utenti finali. È possibile utilizzare il Management Pack di System Center Operations Manager per Skype for business che è disponibile come download gratuito da Microsoft. Con Skype for Business Management Pack, è possibile ottenere avvisi in tempo reale quando si verificano problemi, eseguire transazioni sintetiche per testare le funzionalità di Skype for business end-to-end, ottenere report per la disponibilità del servizio e così via. Questo consente di rispondere in modo proattivo ai problemi relativi alla distribuzione prima che vengano sperimentati dagli utenti finali.

## <a name="reference-topology-for-a-large-organization"></a>Topologia di riferimento per un'organizzazione di grandi dimensioni

La topologia di riferimento per un'organizzazione di grandi dimensioni con il supporto di più Data Center è per tutte le dimensioni dell'organizzazione con più di un sito centrale. La topologia esatta nel diagramma seguente è destinata a un'organizzazione di 50.000 utenti, con 20.000 utenti nel sito centrale A, 20.000 nel sito centrale B. e un totale di 10.000 nel sito centrale C e nei siti di succursale. Il tipo di topologia illustrato in questo diagramma è in grado di ospitare organizzazioni con qualsiasi numero di utenti.

Oltre alla disponibilità elevata fornita dai pool di front end server, questa topologia aggiunge il supporto per il ripristino di emergenza. I pool Front end nei siti centrali A e B sono abbinati tra loro. Se uno di questi pool si sposta verso il basso, l'amministratore può spostare i servizi per gli utenti coinvolti nel pool associato nel sito inalterato.

Questa topologia è illustrata in più diagrammi, con una panoramica prima seguita da visualizzazioni dettagliate dei siti centrali.

**Panoramica della topologia di riferimento per organizzazioni di grandi dimensioni con più data center**

![Topologia di riferimento per più data center](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-1-new.jpg)

**Topologia di riferimento per le organizzazioni di grandi dimensioni: visualizzazione dettagliata del sito centrale A**

![Topologia 3-2](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-2.jpg)

**Topologia di riferimento per le organizzazioni di grandi dimensioni: visualizzazione dettagliata del sito centrale B**

![Topologia 3-3](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-3.jpg)

**Topologia di riferimento per le organizzazioni di grandi dimensioni: visualizzazione dettagliata del sito centrale C**

![Topologia 3-4](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-4.jpg)

- **I pool Front End sono associati per abilitare il ripristino di emergenza.** I pool Front end del sito A e del sito B sono abbinati tra loro, per fornire il supporto per il ripristino di emergenza. Se il pool di un sito ha esito negativo, l'amministratore può eseguire il failover degli utenti da tale sito al pool Front end associato nell'altro sito, con un minimo di interruzioni del servizio per gli utenti. Ognuno di questi due pool Front end dispone di sei server, che sono sufficienti per tutti gli utenti di 40.000 in entrambi i pool in caso di failover. Per ulteriori informazioni, vedere [pianificare la disponibilità elevata e il ripristino di emergenza in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- **Mirroring dei server back-end** Per garantire una disponibilità elevata per le funzionalità utente di base, l'organizzazione ha distribuito una coppia di server back-end con mirroring per ogni pool Front end. Si tratta di una topologia facoltativa ed è possibile scegliere di distribuire un singolo server back-end. Sono supportati anche il clustering SQL e i gruppi di disponibilità AlwaysOn. Per ulteriori informazioni, vedere [disponibilità elevata del server back-end in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

- **Utilizzo del server Standard Edition in un sito di succursale.** Questa organizzazione considera il sito C come un sito di succursale perché ha solo 600 dipendenti. Tuttavia, gli utenti hanno molte conferenze A/V tra di loro. Se è stato distribuito in Skype for Business Server come sito di succursale, il supporto per queste conferenze verrebbe eseguito attraverso la WAN (Wide Area Network) verso e da un sito centrale in cui è distribuito un server front-end. Per evitare questo carico di larghezza di banda potenziale, sono state installate una coppia di server Standard Edition in questo sito, che ospiterà queste conferenze. E poiché i server Standard Edition sono installati in questa pagina, Skype for Business Server per definizione lo considera un sito centrale e viene trattato come tale in Generatore di topologie e nello strumento di pianificazione.

    Solo un server Standard Edition sarebbe sufficiente per le prestazioni, ma l'organizzazione ha distribuito due e abbinato insieme per garantire una disponibilità elevata nel caso in cui un server venisse abbassato.

    Anche se il sito C è considerato un sito centrale, non è necessario distribuire i server perimetrali. In questo esempio, il sito C utilizzerà i server perimetrali distribuiti nel sito A.

- **Monitoraggio e archiviazione** Questa organizzazione ha implementato sia il monitoraggio che l'archiviazione. Quando si distribuisce il monitoraggio o l'archiviazione, viene eseguito in tutti i Front End Server. I database per queste funzionalità possono essere collocati con il database back-end o in un server separato. Questa organizzazione ha individuato i database in un server separato dai server back-end, nel sito centrale B. I database qui ricevono il monitoraggio e l'archiviazione dei dati dai Front End Server in tutti i siti.

- **Opzioni di distribuzione del sito di succursale.** Questa organizzazione ha in realtà oltre 50 siti di succursale, solo due dei quali sono mostrati nei diagrammi dettagliati. Il sito di succursale 1 non dispone di un collegamento WAN resiliente al sito centrale, in modo che dispongano di Survivable Branch Appliance distribuite per fornire servizi di telefonia nel caso in cui il collegamento WAN al sito centrale venga premuto. Il sito di succursale 2 ha tuttavia un collegamento WAN resiliente, quindi richiede solo un gateway PSTN (Public Switched Telephone Network). Poiché il gateway PSTN distribuito supporta il bypass multimediale, non sono necessari Mediation Server nel Sito di succursale 2. Per informazioni dettagliate sulla scelta dell'installazione in un sito di succursale, vedere [pianificare la resilienza di VoIP aziendale in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Trunking SIP e Mediation Server.** Si noti che nel sito centrale B, Mediation Server non è collocato con i Front End Server. Questo perché Mediation Server autonomo è consigliato per i siti che utilizzano il trunking SIP. Nella maggior parte delle altre istanze, si consiglia di collocare Mediation Server con Front End Server. Per informazioni dettagliate sulle topologie di Mediation Server, vedere [componenti e topologie per Mediation Server](https://technet.microsoft.com/library/71397168-36c3-4d21-b8ef-db6a751634ee.aspx) nella documentazione relativa alla pianificazione.

- **La chat persistente viene distribuita.** In questa organizzazione sono stati distribuiti i server necessari per abilitare la chat persistente. Sono stati distribuiti più front end server di chat persistente per gestire il carico per il numero di utenti nel pool e per garantire una disponibilità elevata. Ha inoltre implementato la conformità per la chat persistente e ha individuato l'archivio di chat persistente e l'archivio di conformità di Persistent Chat su server distinti. Tali archivi potevano essere collocati e possono anche essere collocati con il server back-end, ma questa organizzazione ha scelto di separarli per garantire prestazioni migliori.

    > [!NOTE]
    > La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team oppure continuare a utilizzare Skype for Business Server 2015.

- **Bilanciamento del carico DNS.** Il pool Front end e il pool di server perimetrali utilizzano il bilanciamento del carico DNS. In questo modo viene eliminata la necessità di disporre di un sistema di bilanciamento del carico hardware per l'interfaccia interna dei server perimetrali e diminuisce significativamente la quantità di tempo necessario per l'installazione e la manutenzione dei dispositivi di bilanciamento del carico hardware per gli altri pool, in quanto i dispositivi di bilanciamento del carico hardware sono necessari solo per il traffico HTTP. Per ulteriori informazioni, vedere (.. /.. /Plan-Your-Deployment/Network-requirements/Load-Balancing.MD # BKMK_DNSLoadBalancing).

- **Distribuzione di Messaggistica unificata di Exchange.** Skype for Business Server è compatibile con le distribuzioni locali della messaggistica unificata di Exchange e la messaggistica unificata di Exchange ospitata. Nel sito centrale A è incluso un server di messaggistica unificata di Exchange, che esegue Microsoft Exchange Server, non Skype for Business Server. La funzionalità di messaggistica unificata di Exchange per Skype for Business Server viene eseguita nel pool Front end.

    Il sito centrale B utilizza Exchange ospitato, quindi anche la funzionalità del server Messaggistica unificata di Exchange è ospitata.

    Per informazioni dettagliate sulla messaggistica UNIFICAta di Exchange, vedere l'integrazione della messaggistica unificata di [Exchange locale](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) e l' [integrazione della messaggistica unificata di Exchange ospitata](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx) nella documentazione relativa alla pianificazione.

- **Server Office Web Apps.** È consigliabile distribuire un server Office Web Apps o una farm di server Office Web Apps in ogni organizzazione che utilizza le conferenze Web. È possibile distribuire una singola farm di server Office Web Apps in un sito che utilizza il traffico proveniente da tutti i siti oppure distribuirlo in ogni sito. Il server Office Web Apps rende possibile la presentazione di diapositive di PowerPoint nelle conferenze Web.

- **È possibile aggiungere i Director.** Se l'organizzazione ha voluto aumentare la sicurezza contro gli attacchi Denial of Service, potrebbe anche distribuire un pool di Director. Un amministratore è un ruolo del server facoltativo separato in Skype for Business Server che non ospita account utente o che fornisce servizi di conferenza o presenza. Funge da server hop successivo interno a cui un server perimetrale instrada il traffico SIP in ingresso destinato ai server interni. Il Director esegue la preautenticazione delle richieste in ingresso e le reindirizza al pool o al server Home dell'utente. La preautenticazione nel server Director consente di eliminare le richieste provenienti da account utente sconosciuti alla distribuzione. Un amministratore consente di isolare i Front End Server da traffico dannoso, ad esempio attacchi DoS (Denial of Service). Se la rete viene inondata di traffico esterno non valido in un attacco di questo tipo, il traffico termina nel server Director.

- **È consigliabile utilizzare System Center Operations Manager.** Si consiglia di monitorare l'integrità della distribuzione di Skype for Business Server per garantire la disponibilità del servizio per gli utenti finali. È possibile utilizzare il Management Pack di System Center Operations Manager per Skype for business che è disponibile come download gratuito da Microsoft. Con Skype for Business Management Pack, è possibile ottenere avvisi in tempo reale quando si verificano problemi, eseguire transazioni sintetiche per testare le funzionalità di Skype for business end-to-end, ottenere report per la disponibilità del servizio e così via. Questo consente di rispondere in modo proattivo ai problemi relativi alla distribuzione prima che vengano sperimentati dagli utenti finali.


