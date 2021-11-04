---
title: Topologie di riferimento per Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
description: Topologie di riferimento per Skype for Business Server, inclusi diagrammi e decisioni da prendere per organizzazioni di grandi, medie e piccole dimensioni.
ms.openlocfilehash: 270814a8a4dacccdec8919a0e31c9c6098603493
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60762104"
---
# <a name="reference-topologies-for-skype-for-business-server"></a>Topologie di riferimento per Skype for Business Server

Topologie di riferimento per Skype for Business Server, inclusi diagrammi e decisioni da prendere per organizzazioni di grandi, medie e piccole dimensioni.

La topologia Skype for Business Server ottimale dipende dalle dimensioni dell'organizzazione, dai carichi di lavoro che si desidera distribuire e dalle preferenze per la disponibilità elevata rispetto al costo dell'investimento.

In questa sezione vengono descritte tre topologie di riferimento di esempio, incluso il ragionamento di molte delle decisioni prese in considerazione in ogni topologia.

## <a name="reference-topology-for-a-small-organization"></a>Topologia di riferimento per un'organizzazione di piccole dimensioni

La topologia di riferimento per le organizzazioni di piccole dimensioni mostra come distribuire una soluzione affidabile e a disponibilità elevata distribuendo solo tre server che eseguono Skype for Business Server.

**Topologia di riferimento per organizzazioni di piccole dimensioni**

![Diagramma della topologia di riferimento che distribuisce tre server.](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology1.jpg)

- **Coppia di edizione Standard server distribuiti** Questa organizzazione ha 4.000 utenti nel sito centrale. Hanno distribuito due server edizione Standard e li hanno associati per consentire la disponibilità elevata e il ripristino di emergenza. Ogni server contiene 2.000 utenti, ma le informazioni su tutti gli utenti vengono sincronizzate tra i due server. In caso di problemi, un amministratore può eseguire il failover di tali utenti per essere serviti dall'altro server, con un minimo di interruzione per gli utenti. Per ulteriori informazioni sulle funzionalità di disponibilità elevata e ripristino di emergenza in Skype for Business Server, vedere [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- **È consigliata la distribuzione di un server perimetrale.** Anche se non è necessario distribuire un server perimetrale per la messaggistica istantanea interna, la presenza e le conferenze, è consigliabile utilizzarne uno persino per le distribuzioni di piccole dimensioni. È possibile ottimizzare l Skype for Business Server'investimento distribuendo un server perimetrale per fornire servizio agli utenti attualmente esterni ai firewall dell'organizzazione. Tra i vantaggi derivanti dall'utilizzo di server perimetrali sono inclusi i seguenti:

  - Gli utenti dell'organizzazione possono utilizzare Skype for Business Server, se lavorano da casa o sono fuori strada.

  - Gli utenti possono invitare utenti esterni a partecipare alle riunioni.

  - Se si dispone di un partner, un fornitore o un'organizzazione cliente che utilizza anche Skype for Business Server, è possibile creare una relazione federata con tale organizzazione. La Skype for Business Server di distribuzione riconoscerebbe quindi gli utenti di tale organizzazione federata, migliorando la collaborazione.

  - Gli utenti possono scambiare messaggi istantanei con gli utenti di alcuni servizi di messaggistica istantanea pubblici.

- **Funzionamento garantito per i siti di succursale.** Questa organizzazione esegue un programma pilota della funzionalità VoIP aziendale di Skype for Business Server. Alcuni utenti usano Skype for Business Server come unica soluzione vocale. Alcuni di questi VoIP aziendale utenti pilota si trovano nel sito di succursale. Il sito di succursale non dispone di un collegamento WAN (Wide Area Network) affidabile al sito centrale, quindi in tale sito viene distribuito un Survivable Branch Appliance. Con questa distribuzione, se il collegamento WAN si ferma, gli utenti del sito di succursale possono comunque effettuare e ricevere chiamate (sia chiamate all'interno dell'organizzazione che chiamate PSTN), avere funzionalità di segreteria telefonica e comunicare con la messaggistica istantanea tra due parti. Gli utenti possono inoltre essere autenticati anche quando il collegamento WAN non è disponibile. Per ulteriori informazioni, vedere [Plan for VoIP aziendale resiliency in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Distribuzione di Messaggistica unificata di Exchange.** Questa topologia di riferimento include un Exchange di messaggistica unificata, che viene eseguito Microsoft Exchange Server, non Skype for Business Server.

- **Office Server Web Apps.** È consigliabile distribuire un Office web apps server o Office farm di server Web Apps in ogni organizzazione che utilizza le conferenze Web. Office Il server Web Apps consente di PowerPoint diapositive in conferenze Web.

## <a name="reference-topology-for-a-medium-organization"></a>Topologia di riferimento per un'organizzazione di medie dimensioni

La topologia di riferimento con disponibilità elevata e un solo data center è specifica per un'organizzazione di piccole-medie dimensioni con un unico sito centrale. La topologia esatta nel diagramma seguente è per un'organizzazione di 20.000 utenti.

**Topologia di riferimento per organizzazioni di medie dimensioni**

![Topologia di riferimento per un singolo diagramma del data center.](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology2.jpg)

- **Supporto di più utenti aggiungendo più Front End Server.** La topologia esatta in questo diagramma include tre Front End Server per fornire supporto a 20.000 utenti. Se si dispone di un singolo sito centrale e di un numero maggiore di utenti, è sufficiente aggiungere altri Front End Server al pool. Il numero massimo di utenti per pool è 80.000, con dodici Front End Server.

    Tuttavia, la topologia a sito singolo può supportare ancora più utenti aggiungendo un altro pool Front End al sito.

- **È possibile aggiungere il ripristino di emergenza.** Per questa organizzazione, la disponibilità elevata per i Skype for Business Server è una funzionalità necessaria, ma il ripristino di emergenza non lo è. Il pool di Front End Server distribuiti offre disponibilità elevata.

    Se desideravano aggiungere la capacità di ripristino di emergenza, potevano prendere in considerazione la creazione di un altro datacenter e l'aggiunta di un altro pool Front End e l'associazione con il pool Front End nel datacenter corrente. Quindi, se si verifica un'emergenza che interessa il pool principale, gli amministratori possono eseguire il failover degli utenti nel pool di backup.

- **I server back-end sono con mirroring** Per garantire maggiore disponibilità per le funzionalità utente di base, l'organizzazione ha distribuito una coppia di server back-end con mirroring per ogni pool Front End.

- **Opzioni di database del Monitoring Server.** Questa organizzazione ha distribuito monitoraggio per garantire la qualità delle chiamate VoIP aziendale e conferenze audio/video. Il monitoraggio viene distribuito in ogni Front End Server e il database di monitoraggio è collocato con i server back-end. Sono inoltre supportate le topologie in cui il database di monitoraggio si trova in un server separato.

- **Disponibilità elevata dei server perimetrali** In questa organizzazione di esempio con 20.000 utenti, un solo server perimetrale sarebbe sufficiente per le prestazioni. Tuttavia, hanno distribuito un pool di due server perimetrali distribuiti per garantire la disponibilità elevata.

- **Opzioni di distribuzione del sito di succursale.** Nell'organizzazione di questa topologia è distribuito VoIP aziendale come soluzione vocale. Il sito di succursale 1 non dispone di un collegamento WAN (Wide Area Network) resiliente al sito centrale, pertanto dispone di un Survivable Branch Appliance distribuito per mantenere molte funzionalità di Skype for Business Server nel caso in cui il collegamento WAN al sito centrale si insedi. Nel Sito di succursale 2 invece è presente un collegamento WAN resiliente e pertanto è necessario solo un gateway PSTN (Public Switched Telephone Network). Poiché il gateway PSTN distribuito supporta il bypass multimediale, non sono necessari Mediation Server nel Sito di succursale 2. Per ulteriori informazioni, vedere [Plan for VoIP aziendale resiliency in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Bilanciamento del carico DNS.** Nel pool Front End e nel pool di server perimetrali è distribuito il bilanciamento del carico DNS per il traffico SIP. In questo modo si evita di dover utilizzare dispositivi di bilanciamento del carico hardware per i server perimetrali, riducendo in modo significativo le attività di configurazione e manutenzione dei dispositivi di bilanciamento del carico hardware per gli altri pool, poiché i dispositivi di bilanciamento del carico hardware sono necessari solo per il traffico HTTP. Per ulteriori informazioni, vedere [Bilanciamento del carico DNS](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Distribuzione di Messaggistica unificata di Exchange.** Questa topologia di riferimento include un Exchange di messaggistica unificata, che viene eseguito Microsoft Exchange Server, non Skype for Business Server.

- **Office Server Web Apps.** È consigliabile distribuire un Office web apps server o Office farm di server Web Apps in ogni organizzazione che utilizza le conferenze Web. Office Il server Web Apps consente di presentare diapositive di Powerpoint in conferenze Web.

- **È possibile aggiungere director.** Se l'organizzazione desidera aumentare la sicurezza dagli attacchi Denial of Service, potrebbe anche distribuire un pool di Director. Un Director è un ruolo del server facoltativo separato in Skype for Business Server che non ospita account utente o fornisce servizi di presenza o conferenza. Funge da server hop successivo interno a cui un server perimetrale instrada il traffico SIP in ingresso destinato ai server interni. Il Director esegue l'autenticazione preliminare delle richieste in ingresso e le reindirizza al pool principale o al server dell'utente. La pre-autenticazione nel Server Director consente di eliminare le richieste dagli account utente sconosciuti alla distribuzione. Un Director consente di isolare i Front End Server da traffico dannoso, ad esempio attacchi Denial of Service (DoS). Se la rete viene inondata di traffico esterno non valido in un attacco di questo tipo, il traffico termina con il Director.

- **System Center Operations Manager è consigliato.** È consigliabile monitorare l'integrità della distribuzione Skype for Business Server per garantire la disponibilità del servizio per gli utenti finali. È possibile utilizzare System Center Management Pack di Operations Manager per Skype for Business disponibile come download gratuito da Microsoft. Con il Management Pack di Skype for Business, è possibile ricevere avvisi in tempo reale in caso di problemi, eseguire transazioni sintetiche per testare la funzionalità di Skype for Business end-to-end, ottenere report sulla disponibilità del servizio e così via. In questo modo è possibile rispondere in modo proattivo ai problemi relativi alla distribuzione prima che gli utenti finali li verifichino.

## <a name="reference-topology-for-a-large-organization"></a>Topologia di riferimento per un'organizzazione di grandi dimensioni

La topologia di riferimento per un'organizzazione di grandi dimensioni con più data center supportati è per qualsiasi dimensione dell'organizzazione con più di un sito centrale. La topologia esatta nel diagramma seguente è per un'organizzazione di 50.000 utenti, con 20.000 utenti nel sito centrale A, 20.000 nel sito centrale B e un totale di 10.000 in sito centrale C e siti di succursale. Il tipo di topologia mostrato in questo diagramma può ospitare organizzazioni con un numero qualsiasi di utenti.

Oltre alla disponibilità elevata fornita dai pool di Front End Server, questa topologia aggiunge il supporto per il ripristino di emergenza. I pool Front End nei siti centrali A e B sono associati tra loro. Se uno di questi pool non è più in funzione, l'amministratore può spostare i servizi per gli utenti interessati nel pool associato nel sito non interessato.

Questa topologia è illustrata in più diagrammi, con una panoramica seguita da visualizzazioni dettagliate dei siti centrali.

**Panoramica della topologia di riferimento per organizzazioni di grandi dimensioni con più data center**

![Topologia di riferimento per più data center.](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-1-new.jpg)

**Topologia di riferimento per organizzazioni di grandi dimensioni: visualizzazione dettagliata del sito centrale A**

![Topologia 3-2.](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-2.jpg)

**Topologia di riferimento per organizzazioni di grandi dimensioni: visualizzazione dettagliata del sito centrale B**

![Topologia 3-3.](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-3.jpg)

**Topologia di riferimento per organizzazioni di grandi dimensioni: visualizzazione dettagliata del sito centrale C**

![Topologia 3-4.](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-4.jpg)

- **I pool Front End sono associati per abilitare il ripristino di emergenza.** I pool Front End nel sito A e nel sito B sono associati tra loro per fornire supporto per il ripristino di emergenza. Se il pool in un sito ha esito negativo, l'amministratore può eseguire il failover degli utenti da tale sito al pool Front End associato nell'altro sito, con un minimo di interruzione del servizio per gli utenti. Ognuno di questi due pool Front End dispone di sei server, il che è sufficiente per tutti i 40.000 utenti in entrambi i pool in caso di failover. Per ulteriori informazioni, vedere [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- **I server back-end sono con mirroring** Per garantire maggiore disponibilità per le funzionalità utente di base, l'organizzazione ha distribuito una coppia di server back-end con mirroring per ogni pool Front End. Si tratta di una topologia facoltativa ed è possibile scegliere di distribuire un singolo server back-end. SQL sono supportati anche il clustering e i gruppi di disponibilità AlwaysOn. Per ulteriori informazioni, vedere [Back End Server high availability in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

- **Utilizzo edizione Standard server in un sito di succursale.** Questa organizzazione considera il sito C come sito di succursale perché ha solo 600 dipendenti. Tuttavia, gli utenti hanno molte conferenze audio/video tra loro. Se è stato distribuito in Skype for Business Server come sito di succursale, i supporti per queste conferenze verrebbero eseguiti attraverso la rete WAN (Wide Area Network) da e verso un sito centrale in cui è distribuito un Front End Server. Per evitare questo potenziale carico di larghezza di banda, hanno installato una coppia di server edizione Standard in questo sito, che ospiteranno queste conferenze. Poiché i edizione Standard sono installati in questa posizione, Skype for Business Server per definizione lo considera un sito centrale e viene considerato come tale in Generatore di topologie e nello Strumento di pianificazione.

    Un solo edizione Standard server sarebbe sufficiente per le prestazioni, ma l'organizzazione ne ha distribuiti due e li ha associati per garantire una disponibilità elevata nel caso in cui un server si insedi.

    Sebbene il sito C sia considerato un sito centrale, non è necessario distribuire i server perimetrali in tale sito. In questo esempio, il sito C utilizzerà i server perimetrali distribuiti nel sito A.

- **Monitoraggio e archiviazione** Questa organizzazione ha distribuito sia monitoraggio che archiviazione. Quando si distribuisce Il monitoraggio o l'archiviazione, viene eseguito in ogni Front End Server. I database per queste funzionalità possono essere collocati nel database back-end o in un server separato. Questa organizzazione ha individuato questi database in un server separato dai server back-end, nel sito centrale B. I database ricevono i dati di monitoraggio e archiviazione dai Front End Server in tutti i siti.

- **Opzioni di distribuzione del sito di succursale.** Questa organizzazione ha in realtà più di 50 siti di succursale, solo due dei quali sono illustrati nei diagrammi dettagliati. Il sito di succursale 1 non dispone di un collegamento WAN resiliente al sito centrale, pertanto dispongono di Survivable Branch Appliance distribuiti per fornire il servizio telefonico nel caso in cui il collegamento WAN al sito centrale si insedi. Il sito di succursale 2 ha tuttavia un collegamento WAN resiliente, pertanto richiede solo un gateway PSTN (Public Switched Telephone Network). Poiché il gateway PSTN distribuito supporta il bypass multimediale, non sono necessari Mediation Server nel Sito di succursale 2. Per informazioni dettagliate sulla scelta degli elementi da installare in un sito di succursale, vedere [Plan for VoIP aziendale resiliency in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Trunking SIP e Mediation Server.** Si noti che nel sito centrale B, Mediation Server non è collocato con i Front End Server. Ciò è dovuto al fatto che il Mediation Server autonomo è consigliato per i siti che utilizzano il trunking SIP. Nella maggior parte degli altri casi, è consigliabile collocare Mediation Server con Front End Server. Per informazioni dettagliate sulle topologie di Mediation Server, vedere [Components and Topologies for Mediation Server](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-mediation-server) nella documentazione relativa alla pianificazione.

- **Persistent Chat è distribuita.** Questa organizzazione ha distribuito i server necessari per abilitare Persistent Chat. Sono stati distribuiti più Front End Server di Persistent Chat per gestire il carico per il numero di utenti nel pool e per fornire disponibilità elevata. Ha inoltre distribuito compliance per Persistent Chat e ha individuato l'archivio chat persistente e l'archivio di conformità di Persistent Chat in server separati. Questi archivi possono essere collocati e possono anche essere collocati con il server back-end, ma questa organizzazione ha scelto di separarli per garantire prestazioni migliori.

    > [!NOTE]
    > La chat persistente è disponibile Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in Teams. Per ulteriori informazioni, vedere [Introduzione all'Microsoft Teams aggiornamento.](/microsoftteams/upgrade-start-here) Se è necessario utilizzare persistent chat, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità Teams o continuare a usare Skype for Business Server 2015.

- **Bilanciamento del carico DNS.** Il pool Front End e il pool di server perimetrali utilizzano il bilanciamento del carico DNS. In questo modo si elimina la necessità di servizi di bilanciamento del carico hardware per l'interfaccia interna dei server perimetrali e si riduce notevolmente il tempo necessario per la configurazione e la manutenzione dei servizi di bilanciamento del carico hardware per gli altri pool, poiché i servizi di bilanciamento del carico hardware sono necessari solo per il traffico HTTP. Per ulteriori informazioni, vedere (.. /.. /plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Distribuzione di Messaggistica unificata di Exchange.** Skype for Business Server funziona sia con le distribuzioni locali di Exchange messaggistica unificata che con la messaggistica unificata ospitata Exchange messaggistica unificata. Il sito centrale A include un Exchange di messaggistica unificata, che viene eseguito Microsoft Exchange Server, non Skype for Business Server. La Exchange di messaggistica unificata per Skype for Business Server viene eseguita nel pool Front End.

    Il sito centrale B utilizza le Exchange ospitate, quindi viene ospitata anche la Exchange server Messaggistica unificata.

    Per informazioni dettagliate Exchange messaggistica unificata, vedere [On-Premises Exchange Unified Messaging Integration](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-exchange-unified-messaging-integration) e [Hosted Exchange Unified Messaging Integration](/previous-versions/office/lync-server-2013/lync-server-2013-hosted-exchange-unified-messaging-integration) nella documentazione relativa alla pianificazione.

- **Office Server Web Apps.** È consigliabile distribuire un Office web apps server o Office farm di server Web Apps in ogni organizzazione che utilizza le conferenze Web. È possibile distribuire una singola farm Office server Web Apps in un sito che serve il traffico da tutti i siti o distribuirla in ogni sito. Office Il server Web Apps consente di presentare diapositive di Powerpoint in conferenze Web.

- **È possibile aggiungere director.** Se l'organizzazione desidera aumentare la sicurezza dagli attacchi Denial of Service, può anche distribuire un pool di Director. Un Director è un ruolo del server facoltativo separato in Skype for Business Server che non ospita account utente o fornisce servizi di presenza o conferenza. Funge da server hop successivo interno a cui un server perimetrale instrada il traffico SIP in ingresso destinato ai server interni. Il Director esegue l'autenticazione preliminare delle richieste in ingresso e le reindirizza al pool principale o al server dell'utente. La pre-autenticazione nel Server Director consente di eliminare le richieste dagli account utente sconosciuti alla distribuzione. Un Director consente di isolare i Front End Server da traffico dannoso, ad esempio attacchi Denial of Service (DoS). Se la rete viene inondata di traffico esterno non valido in un attacco di questo tipo, il traffico termina con il Director.

- **System Center Operations Manager è consigliato.** È consigliabile monitorare l'integrità della distribuzione Skype for Business Server per garantire la disponibilità del servizio per gli utenti finali. È possibile utilizzare System Center Management Pack di Operations Manager per Skype for Business disponibile come download gratuito da Microsoft. Con il Management Pack di Skype for Business, è possibile ricevere avvisi in tempo reale in caso di problemi, eseguire transazioni sintetiche per testare la funzionalità di Skype for Business end-to-end, ottenere report sulla disponibilità del servizio e così via. In questo modo è possibile rispondere in modo proattivo ai problemi relativi alla distribuzione prima che gli utenti finali li verifichino.