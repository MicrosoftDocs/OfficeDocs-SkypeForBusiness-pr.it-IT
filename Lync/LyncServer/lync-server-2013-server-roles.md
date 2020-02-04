---
title: 'Lync Server 2013: Ruoli del server'
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
ms.openlocfilehash: b22115bf137c388fd6cd15103ac882056affa4f6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-roles-in-lync-server-2013"></a>Ruoli del server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-10-07_

Ogni server che esegue Lync Server esegue uno o più *ruoli del server*. Un ruolo del server è un set definito di funzionalità di Lync Server fornite da tale server. Non è necessario distribuire tutti i ruoli del server disponibili nella rete. Installare solo i ruoli del server che contengono la funzionalità desiderata.

Anche se non si ha familiarità con i ruoli del server in Lync Server, lo strumento di pianificazione può guidare la soluzione migliore per i server che è necessario distribuire, in base alle caratteristiche desiderate. Questa sezione fornisce una breve panoramica dei ruoli del server e delle caratteristiche generali fornite:

  - Server Standard Edition

  - Server front-end e server back-end

  - Edge Server

  - Mediation Server

  - Director

  - Server front end di chat persistente

  - Archivio Chat persistente (server back-end della chat persistente)

  - Archivio conformità della chat persistente (server back end di conformità della chat persistente)

Per la maggior parte dei ruoli del server, per la scalabilità e la disponibilità elevata è possibile distribuire *pool* di più server tutti in grado di eseguire lo stesso ruolo del server. Ogni server in un pool deve eseguire un ruolo o ruoli del server identico. Per la maggior parte dei tipi di pool in Lync Server, è necessario distribuire un bilanciamento del carico per diffondere il traffico tra i vari server del pool. Lync Server supporta il bilanciamento del carico DNS (Domain Name System) e il bilanciamento del carico hardware.

<div>

## <a name="standard-edition-server"></a>Server Standard Edition

Il server Standard Edition è progettato per piccole organizzazioni e per progetti pilota di grandi organizzazioni. Consente di eseguire in un singolo server molte delle funzionalità di Lync Server, inclusi i database necessari. In questo modo è possibile avere la funzionalità Lync Server per un costo inferiore, ma non offre una vera soluzione a elevata disponibilità.

Il server Standard Edition consente di usare messaggistica istantanea, presenza, conferenza e VoIP aziendale, tutti in uso in un server.

Per una soluzione a disponibilità elevata, usare Lync Server Enterprise Edition.

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a>Server front-end e server back-end

In Lync Server Enterprise Edition il server front-end è il ruolo del server principale ed esegue molte funzioni di base di Lync Server. Il server front-end, insieme ai server back-end, sono gli unici ruoli del server necessari per la distribuzione di Lync Server Enterprise Edition.

Un *pool Front End* è un set di server front-end, configurati in modo identico, che collaborano per creare servizi per un gruppo di utenti comune. Un pool di più server con lo stesso ruolo offre funzionalità di failover e scalabilità.

Il server front-end include le operazioni seguenti:

  - Autenticazione e registrazione degli utenti

  - Informazioni sulla presenza e scambio di schede contatto

  - Servizi Rubrica e espansione della lista di distribuzione

  - Funzionalità di messaggistica istantanea, incluse le conferenze di messaggistica istantanea a più parti

  - Servizi di conferenza Web, servizi di conferenza telefonica con accesso esterno PSTN e servizi di conferenza A/V (se distribuiti)

  - Hosting di applicazioni, per entrambe le applicazioni incluse in Lync Server (ad esempio, assistente per i servizi di conferenza e Response Group Application) e applicazioni di terze parti

  - Facoltativamente, il monitoraggio consente di raccogliere le informazioni sull'utilizzo sotto forma di record dettagli chiamata (CDRs) e record di errore di chiamata (CER). Queste informazioni forniscono le metriche relative alla qualità dei contenuti multimediali (audio e video) che attraversano la rete sia per le chiamate vocali aziendali che per le conferenze A/V.

  - Componenti Web per le attività basate sul Web supportate, ad esempio Web Scheduler e Join Launcher.

  - Facoltativamente, l'archiviazione consente di archiviare le comunicazioni ISTANTANEe e il contenuto della riunione per motivi di conformità. Per informazioni dettagliate, vedere [pianificazione dell'archiviazione in Lync Server 2013](lync-server-2013-planning-for-archiving.md) nella documentazione relativa alla pianificazione.
    
    In Lync Server 2010 e versioni precedenti, il monitoraggio e l'archiviazione erano ruoli server distinti, non collocati nel server front-end.

  - Facoltativamente, se è abilitata la chat persistente, i servizi Web di chat persistente per la gestione delle chat room e i servizi Web di chat persistenti per caricare/scaricare file.

I pool Front-End sono anche l'archivio principale per i dati dell'utente e della conferenza. Le informazioni su ogni utente vengono replicate tra tre server front-end nel pool ed è stato eseguito il backup dei server back-end.

Inoltre, un pool Front-end della distribuzione esegue anche il *server di gestione centrale*, che gestisce e distribuisce i dati di configurazione di base in tutti i server che esegue Lync Server. Il server di gestione centrale offre anche Lync Server Management Shell e funzionalità di trasferimento file.

I server back-end sono server di database che esegue Microsoft SQL Server che includono i servizi di database per il pool Front-end. I server back-end fungono da archivi di backup per i dati dell'utente e della conferenza del pool e sono gli archivi principali di altri database, ad esempio il database Response Group. È possibile avere un singolo server back-end, ma una soluzione che usa il mirroring di SQL Server è consigliata per il failover. I server back-end non eseguono alcun software Lync Server.

<div>


> [!IMPORTANT]  
> Non è consigliabile collocare i database di Lync Server con altri database. In questo caso, la disponibilità e le prestazioni potrebbero essere interessate.



</div>

Le informazioni archiviate nei database del server back-end includono le informazioni sulla presenza, gli elenchi di contatti degli utenti, i dati di conferenza, inclusi i dati permanenti sullo stato di tutte le conferenze correnti e i dati relativi alla pianificazione delle conferenze.

</div>

<div>

## <a name="edge-server"></a>Edge Server

Edge Server consente agli utenti di comunicare e collaborare con utenti esterni ai firewall dell'organizzazione. Questi utenti esterni possono includere gli utenti dell'organizzazione che attualmente lavorano fuori sede, utenti provenienti da organizzazioni partner federate e utenti esterni che sono stati invitati a partecipare a conferenze ospitate nella distribuzione di Lync Server. Edge Server consente inoltre la connettività ai servizi di connettività per messaggistica istantanea pubblica, tra cui Windows\!Live, AOL, Yahoo e Google Talk.

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>A partire dal 1 ° settembre 2012, la licenza di abbonamento a Microsoft Lync Public IM Connectivity User ("PIC USL") non è più disponibile per l'acquisto di contratti nuovi o rinnovati. I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo! Messenger fino alla data di chiusura del servizio. Data di fine vita del 2014 giugno per AOL e Yahoo! è stato annunciato. Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</P>
> <LI>
> <P>Il PIC USL è una licenza per abbonamento mensile per ogni utente necessaria per la Federazione di Lync Server o Office Communications Server con Yahoo! Messenger. La capacità di Microsoft di prestare questo servizio è stata subordinata al supporto di Yahoo!, l'accordo sottostante per il quale sta per finire.</P>
> <LI>
> <P>Più che mai, Lync è uno strumento efficace per la connessione tra le organizzazioni e gli utenti di tutto il mondo. La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync. La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e voce.</P></LI></UL>



</div>

La distribuzione di Edge Server consente inoltre ai servizi di mobilità, che supportano le funzionalità di Lync nei dispositivi mobili. Gli utenti possono usare i dispositivi mobili Apple iOS, Android, Windows Phone o Nokia supportati per eseguire attività come l'invio e la ricezione di messaggi istantanei, la visualizzazione dei contatti e la visualizzazione della presenza. I dispositivi mobili supportano inoltre alcune funzionalità VoIP aziendale, ad esempio fare clic per partecipare a una conferenza, chiamare tramite lavoro, raggiungere un numero singolo, la segreteria telefonica e le chiamate perse. La funzionalità mobilità supporta anche le *notifiche push* per i dispositivi mobili che non supportano le applicazioni in uso in background. Una notifica push è una notifica inviata a un dispositivo mobile su un evento che si verifica mentre un'applicazione per dispositivi mobili è inattiva.

I server Edge includono anche un proxy XMPP (Extensible Messaging and Presence Protocol) completamente integrato, con un gateway XMPP incluso nei server front-end. Puoi configurare questi componenti XMPP per consentire agli utenti di Lync Server 2013 di aggiungere contatti da partner basati su XMPP, ad esempio Google Talk, per la messaggistica istantanea e la presenza.

Per informazioni dettagliate, vedere [pianificazione per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) nella documentazione relativa alla pianificazione.

</div>

<div>

## <a name="mediation-server"></a>Mediation Server

Mediation Server è un componente necessario per l'implementazione di servizi di conferenza telefonica con accesso esterno e VoIP aziendale. Mediation Server traduce la segnalazione e, in alcune configurazioni, il contenuto multimediale tra l'infrastruttura di Lync Server interna e un gateway PSTN (Public Switched Telephone Network), IP-PBX o un trunk SIP (Session Initiation Protocol). È possibile eseguire Mediation Server nello stesso server del server front-end oppure separato in un pool di Mediation Server autonomo.

Per informazioni dettagliate, vedere [Componente Mediation Server in Lync server 2013](lync-server-2013-mediation-server-component.md) nella documentazione relativa alla pianificazione.

</div>

<div>

## <a name="director"></a>Director

Gli amministratori possono eseguire l'autenticazione delle richieste degli utenti di Lync Server, ma non gli account degli utenti privati o offre servizi di conferenza o presenza. Gli amministratori sono più utili per migliorare la sicurezza nelle distribuzioni che consentono l'accesso degli utenti esterni. Il Director può eseguire l'autenticazione delle richieste prima di inviarle ai server interni. Nel caso di un attacco di negazione del servizio, l'attacco termina con il direttore e non raggiunge i server front-end. Per informazioni dettagliate, vedere [scenari per il Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) nella documentazione relativa alla pianificazione.

</div>

<div>

## <a name="persistent-chat-server-roles"></a>Ruoli del server di chat persistente

La chat persistente consente agli utenti di partecipare a conversazioni multiparte, basate su argomenti che persistono nel tempo. Il server front end di chat persistente esegue il servizio di chat persistente. Il server di back-end della chat persistente archivia i dati della cronologia chat e le informazioni sulle categorie e le chat room. Il server back end di conformità della chat persistente opzionale può archiviare il contenuto della chat e gli eventi di conformità ai fini della conformità.

I server che eseguono Lync Server Standard Edition possono eseguire anche la chat persistente collocata nello stesso server. Non è possibile collocare il server front-end della chat persistente con Enterprise Edition Front End Server.

Per informazioni dettagliate, vedere [pianificazione per il server di chat persistente in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Componente Mediation Server in Lync Server 2013](lync-server-2013-mediation-server-component.md)  


[Pianificazione dell'archiviazione in Lync Server 2013](lync-server-2013-planning-for-archiving.md)  
[Pianificazione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Scenari per il server Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md)  
[Pianificazione del server Chat persistente in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

