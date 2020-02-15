---
title: Ruoli del server Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server roles
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398536(v=OCS.15)
ms:contentKeyID: 48184456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 093161cec5a13ac12840776dec731773782966c9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-roles-in-lync-server-2013"></a>Ruoli del server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-10-07_

Ogni server che esegue Lync Server esegue uno o più *ruoli del server*. Un ruolo del server è un set definito di funzionalità di Lync Server fornite da tale server. Non è necessario distribuire nella rete tutti i ruoli del server disponibili. Installare solo i ruoli del server che contengono le funzionalità desiderate.

Anche se non si ha familiarità con i ruoli del server in Lync Server, lo strumento di pianificazione è in grado di guidare la soluzione migliore per i server che è necessario distribuire, in base alle caratteristiche desiderate. Questa sezione contiene una breve panoramica dei ruoli del server e delle caratteristiche generali che offrono:

  - server Standard Edition

  - Front End Server e server di back-end

  - Edge Server

  - Mediation Server

  - Director

  - Front End Server della chat persistente

  - Persistent Chat Store (Server di back-end della chat persistente)

  - Persistent Chat Compliance Store (Compliance server di back-end della chat persistente)

Per la maggior parte dei ruoli del server, ai fini di scalabilità e disponibilità elevata è possibile distribuire *pool* di più server che eseguono tutti lo stesso ruolo del server. Ogni server in un pool deve eseguire uno o più ruoli del server identici. Per la maggior parte dei tipi di pool in Lync Server, è necessario distribuire un bilanciamento del carico per diffondere il traffico tra i vari server del pool. Lync Server supporta il bilanciamento del carico DNS (Domain Name System) e i dispositivi di bilanciamento del carico hardware.

<div>

## <a name="standard-edition-server"></a>Server Standard Edition

Il server Standard Edition è progettato per piccole imprese e per progetti pilota di grandi imprese. Consente di eseguire in un singolo server molte delle funzionalità di Lync Server, inclusi i database necessari. In questo modo è possibile disporre di funzionalità di Lync Server per un costo inferiore, ma non fornisce una vera soluzione a disponibilità elevata.

Il server Standard Edition consente di utilizzare la messaggistica istantanea, la presenza, la conferenza e la VoIP aziendale, tutti in esecuzione su un server.

Per una soluzione a disponibilità elevata, utilizzare Lync Server Enterprise Edition.

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a>Front End Server e server di back-end

In Lync Server Enterprise Edition, il front end server è il ruolo del server di base ed esegue molte funzioni di Basic Lync Server. Il front end server, insieme ai server back-end, sono gli unici ruoli del server necessari per la distribuzione di Lync Server Enterprise Edition.

Un *pool Front End* è un insieme di server Front End Server, configurati in modo identico, che funzionano insieme per offrire servizi per un gruppo comune di utenti. Un pool di server multipli che eseguono lo stesso ruolo garantisce funzionalità di scalabilità e failover.

Front End Server include le funzionalità seguenti:

  - Autenticazione utente e registrazione utenti

  - Scambio di informazioni sulla presenza e schede contatto

  - Espansione dei servizi Rubrica e delle liste di distribuzione

  - Funzionalità di messaggistica istantanea, incluse conferenze di messaggistica istantanea con più partecipanti

  - Web conferencing, conferenza PSTN con accesso esterno e conferenza A/V (se distribuita)

  - Hosting di applicazioni, per entrambe le applicazioni incluse in Lync Server (ad esempio, operatore conferenza e Response Group Application) e applicazioni di terze parti

  - Facoltativamente, il monitoraggio, per raccogliere informazioni sull'utilizzo informazioni in forma di registrazione dettagli chiamata (CDR) e registrazione errori di chiamata. Queste informazioni forniscono metriche sulla qualità dei file multimediali (audio e video) che attraversano la rete sia per le chiamate VoIP aziendali sia per le conferenze A/V.

  - Componenti Web per il supporto di attività basate sul Web come Utilità di pianificazione Web e Join Launcher.

  - Facoltativamente, l'archiviazione consente di archiviare le comunicazioni di messaggistica istantanea e il contenuto delle riunioni per motivi di conformità. Per informazioni dettagliate, vedere [Planning for archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) nella documentazione relativa alla pianificazione.
    
    In Lync Server 2010 e versioni precedenti, il monitoraggio e l'archiviazione erano ruoli del server distinti, non collocati in front end server.

  - Facoltativamente, se la chat persistente è abilitata, Servizi Web della chat persistente per la gestione delle chat room e Servizi Web della chat persistente per l'upload e il download dei file.

I Front End Pool rappresentano inoltre il principale percorso di archiviazione per i dati di utenti e conferenze. Le informazioni relative a ciascun utente sono replicate tra i tre Front End Server nel pool, e il backup è eseguito nei server di back-end.

Inoltre, un pool Front end nella distribuzione esegue anche il *server di gestione centrale*, che consente di gestire e distribuire i dati di configurazione di base in tutti i server che eseguono Lync Server. Il server di gestione centrale fornisce anche Lync Server Management Shell e le funzionalità di trasferimento dei file.

I server back-end sono server di database che eseguono Microsoft SQL Server che forniscono i servizi di database per il pool Front end. I server di back-end assumono il ruolo di archivi per il back up dei dati utente e di conferenza del pool, e rappresentano gli archivi principali per altri database, tra cui il database dei Response Group. È possibile disporre di un solo server back-end, ma una soluzione che utilizza il mirroring di SQL Server è consigliata per il failover. I server back-end non eseguono alcun software Lync Server.

<div>


> [!IMPORTANT]  
> Non è consigliabile collocare i database di Lync Server con altri database. In caso contrario, disponibilità e prestazioni potrebbero risentirne.



</div>

Le informazioni archiviate nei database del server di back-end includono informazioni sulla presenza, elenchi di contatti degli utenti, dati sulle conferenze, ad esempio dati persistenti sullo stato di tutte le conferenze correnti, e dati di pianificazione delle conferenze.

</div>

<div>

## <a name="edge-server"></a>Server perimetrale

Server perimetrale consente agli utenti di comunicare e collaborare con utenti esterni ai firewall dell'organizzazione. Questi utenti esterni possono includere gli utenti dell'organizzazione che attualmente lavorano fuori sede, gli utenti provenienti da organizzazioni partner federate e gli utenti esterni che sono stati invitati a partecipare a conferenze ospitate nella distribuzione di Lync Server. Edge Server consente inoltre la connettività ai servizi di connettività di messaggistica istantanea pubblica, tra cui Windows\!Live, AOL, Yahoo e Google Talk.

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Al 1 ° settembre 2012, la licenza di sottoscrizione di Microsoft Lync Public IM Connectivity ("PIC USL") non è più disponibile per l'acquisto dei contratti nuovi o rinnovati. I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo! Messenger fino alla data di arresto del servizio. Una data di fine vita del 2014 giugno per AOL e Yahoo! sono stati annunciati. Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</P>
> <LI>
> <P>Il PIC USL è una licenza per ogni utente per ogni mese che è necessaria per Lync Server o Office Communications Server per la Federazione con Yahoo! Messaggero. La capacità di Microsoft di fornire questo servizio è stata subordinata al supporto da Yahoo!, ovvero il contratto sottostante per il quale si sta liquidando.</P>
> <LI>
> <P>Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo. La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync. La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e vocale.</P></LI></UL>



</div>

La distribuzione del server perimetrale attiva inoltre i servizi di mobilità, che supportano le funzionalità di Lync nei dispositivi mobili. Gli utenti possono utilizzare dispositivi mobili Apple iOS, Android, Windows Phone o Nokia supportati per eseguire attività quali l'invio e la ricezione di messaggi istantanei, la visualizzazione dei contatti e la visualizzazione della presenza. I dispositivi mobili inoltre supportano alcune funzionalità di VoIP aziendale, tra cui la possibilità di partecipare a una conferenza mediante clic del mouse, la chiamata tramite ufficio, il numero unico, la segreteria telefonica e le chiamate senza risposta. La funzionalità per dispositivi mobili inoltre supporta le *notifiche push* per i dispositivi mobili che non supportano le applicazioni eseguite in background. Una notifica push è una notifica inviata a un dispositivo mobile relativamente a un evento che si verifica mentre un'applicazione per dispositivi mobili non è attiva.

I server perimetrali includono inoltre un proxy XMPP (Extensible Messaging and Presence Protocol) pienamente integrato, con gateway XMPP incluso sui Front End Server. È possibile configurare questi componenti XMPP per consentire agli utenti di Lync Server 2013 di aggiungere contatti da partner basati su XMPP (come Google Talk) per la messaggistica istantanea e la presenza.

Per informazioni dettagliate, vedere [Planning for External User Access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) nella documentazione relativa alla pianificazione.

</div>

<div>

## <a name="mediation-server"></a>Mediation Server

Mediation Server è un componente necessario per l'implementazione delle conferenze telefoniche con accesso esterno e VoIP aziendale. Mediation Server converte i segnali e, in alcune configurazioni, i supporti tra l'infrastruttura di Lync Server interna e un gateway PSTN (Public Switched Telephone Network), IP-PBX o un trunk SIP (Session Initiation Protocol). È possibile eseguire Mediation Server collocato sullo stesso server del Front End Server, o separato in un pool Mediation Server indipendente.

Per informazioni dettagliate, vedere [Mediation Server Component in Lync server 2013](lync-server-2013-mediation-server-component.md) nella documentazione relativa alla pianificazione.

</div>

<div>

## <a name="director"></a>Director

Gli amministratori possono autenticare le richieste degli utenti di Lync Server, ma non gli account utente di casa o fornire servizi di conferenza o presenza. I direttori sono molto utili per migliorare la sicurezza nelle distribuzioni che consentono l'accesso degli utenti esterni. Il Director può eseguire l'autenticazione delle richieste prima di inviarle ai server interni. Nel caso di un attacco Denial-of-Service, l'attacco termina con il Director e non raggiunge i Front End Server. Per informazioni dettagliate, vedere [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) nella documentazione relativa alla pianificazione.

</div>

<div>

## <a name="persistent-chat-server-roles"></a>Ruoli del server Chat persistente

La Chat persistente consente di partecipare a conversazioni tra più partecipanti basate su argomenti, e permanenti nel tempo. I servizi di chat persistente sono eseguiti dal Front End Server della chat persistente. Il server back-end della chat persistente salva i dati della cronologia delle chat e le informazioni relative a categorie e chat room. Il Compliance server di back-end della chat persistente, facoltativo, può archiviare il contenuto della chat e gli eventi di conformità ai fini della conformità stessa.

Nei server che eseguono Lync Server Standard Edition è inoltre possibile eseguire la chat persistente collocata nello stesso server. Non è possibile collocare il front end server di Persistent Chat con Enterprise Edition Front End Server.

Per informazioni dettagliate, vedere [Planning for Persistent Chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Componente Mediation Server in Lync Server 2013](lync-server-2013-mediation-server-component.md)  


[Pianificazione dell'archiviazione in Lync Server 2013](lync-server-2013-planning-for-archiving.md)  
[Pianificazione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Scenari per il Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md)  
[Pianificazione del server Chat persistente in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

