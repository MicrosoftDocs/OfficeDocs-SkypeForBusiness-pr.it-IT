---
title: 'Lync Server 2013: funzionamento del server di chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Persistent Chat Server works
ms:assetid: 3d04e9a1-3f0c-458e-bcbe-d27c8c464276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ683096(v=OCS.15)
ms:contentKeyID: 49684643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 692f9a40bc2c0fd885fc251a4a792d480a69c57d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a>Funzionamento del server di chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-21_

Lync Server 2013, il server di chat persistente consente di partecipare a conversazioni basate su argomenti multiparte, che persistono nel tempo. Il server di chat persistente può aiutare l'organizzazione a eseguire le operazioni seguenti:

  - Migliorare la comunicazione tra team geograficamente dispersivi e interfunzionali

  - Ampliare la conoscenza e la partecipazione delle informazioni

  - Migliorare la comunicazione con l'organizzazione estesa

  - Ridurre il sovraccarico di informazioni

  - Migliorare la consapevolezza delle informazioni

  - Aumentare la dispersione di conoscenze e informazioni importanti

È possibile distribuire il server di chat persistente come ruolo facoltativo con Lync Server 2013. I servizi di chat persistenti vengono eseguiti in un pool dedicato e un pool di server di chat persistente dipende da un pool di Lync Server per instradare i messaggi. I client usano la comunicazione tramite chat estensibile tramite SIP (XCCOS). I server front-end di Lync Server sono configurati per instradare il traffico verso un pool di server di chat persistente.

<div>

## <a name="high-level-architecture"></a>Architettura di alto livello

I diagrammi seguenti includono prospettive di alto livello per l'architettura e i servizi della Chat Server persistente.

**Architettura di alto livello del server di chat persistente**

![Architettura del server Chat persistente.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Architettura del server Chat persistente.")

**Servizi di alto livello del server Chat persistente**

![Componenti del server Chat persistente.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Componenti del server Chat persistente.")

Due servizi vengono eseguiti nei server front end del server di chat persistente:

  - Chat persistente (canale)

  - Conformità

<div>

## <a name="persistent-chat-channel-service"></a>Servizio chat persistente (canale)

Il servizio chat persistente (canale) è il servizio principale responsabile per il server di chat persistente. Questo servizio offre le funzioni seguenti:

  - Accetta i messaggi in arrivo

  - Registra ed elenca i partecipanti online in una chat room persistente

  - Ritrasmette i messaggi ad altri abbonati al canale

  - Implementa la logica per la gestione dei canali, l'invito alla chat room, la ricerca e le nuove notifiche del contenuto

Il servizio chat persistente (canale) archivia e accede al contenuto della chat room e ad altri metadati di sistema (regole di autorizzazione e così via) usando lo Store di chat persistente. Questo servizio archivia i file caricati nelle chat room nell'archivio di file della chat persistente.

</div>

<div>

## <a name="compliance-service"></a>Servizio conformità

Il servizio conformità è un componente facoltativo del server di chat persistente ed è responsabile dell'archiviazione del contenuto della chat e degli eventi nell'archivio conformità della chat persistente. Se l'organizzazione dispone di regole che richiedono l'archiviazione di attività della chat persistente, è possibile distribuire il servizio di conformità delle chat permanenti facoltative. Il servizio conformità viene installato in ogni server di chat persistente in un pool di chat persistente. Quando è configurato, la conformità persistente del server di chat registra le attività degli utenti, ad esempio l'Unione e l'uscita di sale e la registrazione e la lettura dei messaggi Il servizio conformità archivia i file che devono essere archiviati nell'archivio file di conformità della chat persistente.

</div>

<div>

## <a name="persistent-chat-web-services"></a>Servizi Web di chat persistente

Nei server front-end di Lync Server vengono eseguiti due servizi che dipendono da Internet Information Services (IIS) e vengono implementati come componenti Web:

  - **Servizi Web di chat persistenti per l'upload/download di file** Responsabile della registrazione e del recupero dei file dalle chat room.

  - **Servizi Web di chat persistenti per la gestione delle chat room** Responsabile per offrire agli utenti la possibilità di gestire le chat room e creare nuove chat room.

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a>Come si inizia a usare il server di chat persistente?

Il server di chat persistente è un ruolo server facoltativo nell'infrastruttura di Lync Server 2013. Se si installa il ruolo del server di chat persistente, gli utenti abilitati tramite criteri da un amministratore possono usare la chat persistente con il client Lync 2013.

Per informazioni dettagliate su come distribuire il server di chat persistente e consentire agli utenti di sfruttare le funzionalità in base ai criteri, vedere Distribuzione di un [server di chat persistente in Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md).

Per informazioni dettagliate su come configurare le impostazioni nella distribuzione del server di chat persistente, vedere [distribuzione di server di chat persistente in Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) e [gestione di Lync Server 2013, server di chat persistente](managing-lync-server-2013-persistent-chat-server.md).

Per informazioni dettagliate su come abilitare gli utenti in base ai criteri in modo che possano sfruttare le funzionalità di chat persistenti nel client Lync 2013, vedere Distribuzione di un [server di chat persistente in Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) e [gestione di Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).

Se è stata distribuita la conformità alla chat persistente, vedere [gestione di Lync server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) per informazioni dettagliate su come configurare le impostazioni per la conformità.

</div>

<div>

## <a name="persistent-chat-call-flows"></a>Flussi delle chiamate di chat persistenti

Il client di chat persistente comunica con il servizio di chat persistente usando XCCOS. Le sequenze seguenti descrivono il processo di accesso e uno scenario tipico per l'abbonamento a una sala e un post di messaggio.

<div>

## <a name="sign-in"></a>Accesso

Il diagramma di flusso delle chiamate e i passaggi seguenti descrivono il processo di accesso.

**Flusso delle chiamate di accesso al client di chat persistente**

![Diagramma del flusso di chiamate del server Chat persistente.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Diagramma del flusso di chiamate del server Chat persistente.")

1.  Il client di chat persistente invia prima una sottoscrizione SIP per recuperare il documento di provisioning in banda dal server. Questo documento indica se la chat persistente è abilitata o disabilitata per l'utente e l'elenco degli URI SIP per il pool del server di chat persistente.

2.  Il client di chat persistente invia un messaggio di invito SIP all'URI SIP del server di chat persistente ottenuto nel passaggio precedente. La sequenza INVITE è seguita da 200 OK e ACK e il client di chat persistente ha aperto una sessione SIP con un endpoint del server di chat persistente. Di conseguenza, il client di chat persistente comunica con il server di chat persistente inviando messaggi di informazioni SIP che contengono messaggi di chat o comandi che richiedono al server di eseguire un'azione. Tutti questi messaggi vengono riconosciuti con il servizio di 200 OK o 503 non disponibile (ovvero, in caso di carico elevato del server). Se il client riceve una risposta di 503, ritenterà il messaggio. Questo esempio non include una risposta di 503. Se il server accetta il messaggio o il comando e invia 200 OK, fornisce una risposta al client sotto forma di un messaggio di informazioni SIP separato. Questa risposta include un riferimento al comando di origine.

3.  Il client di chat persistente invia un messaggio di informazioni SIP contenente il comando XCCOS **GetServerInfo** . Il server di chat persistente risponde con un nuovo messaggio di informazioni SIP che contiene informazioni sulla configurazione del servizio chat persistente.

4.  Il client di chat persistente invia un messaggio di informazioni SIP contenente il comando XCCOS **GetAssociations** . Il server di chat persistente risponde con un nuovo messaggio di informazioni SIP che contiene l'elenco delle sale di cui l'utente è membro. Il client di chat persistente ripete il comando per recuperare l'elenco delle sale di cui l'utente è responsabile.

5.  Il client di chat persistente Ottiene l'elenco delle sale seguite dal documento "presenza", in cui ogni sala seguita è rappresentata da una categoria "roomSetting". Tutte le sale seguite sono unite da un singolo messaggio di informazioni SIP contenente il comando XCCOS **bjoin** che contiene l'elenco degli URI della sala. Poiché l'elenco delle sale seguite viene mantenuto nel server, qualsiasi client in qualsiasi computer ha lo stesso elenco di sale seguite per l'URI utente specificato. Il client di chat persistente mantiene anche l'elenco delle sale aperte (se questa opzione è abilitata dall'utente) nel registro di sistema del computer locale e si unisce a ognuna di queste sale all'accesso inviando un messaggio di informazioni SIP contenente il comando XCCOS **join** per ogni sala aperta. Poiché questo elenco viene mantenuto nel registro di sistema, può essere diverso in due client di chat persistenti in uso in computer diversi.

6.  Per ogni sala unita, il client di chat persistente invia un messaggio di informazioni SIP contenente il comando XCCOS **bccontext** . Il server di chat persistente risponde con un nuovo messaggio di informazioni SIP che contiene il messaggio di chat più recente nella sala.

7.  Il client di chat persistente invia un messaggio di informazioni SIP che contiene un comando XCCOS **getinv** (Get invito) per richiedere qualsiasi invito alla nuova sala che il client non abbia ancora visto. In un messaggio di informazioni SIP distinto, il server di chat persistente restituisce un elenco di tali sale.

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a>Sottoscrivere una chat room e pubblicare un messaggio

Il diagramma di flusso delle chiamate e i passaggi seguenti descrivono uno scenario tipico per l'abbonamento a una sala e un post.

**Abbonamento al client Chat persistente e flusso delle chiamate di invio messaggi**

![Scenario di inserimento di messaggi e sottoscrizione a una chat.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Scenario di inserimento di messaggi e sottoscrizione a una chat.")

1.  Dal client di chat persistente, User1 fa clic su **partecipa a una chat room**, fa clic su **Cerca**e quindi immette alcuni criteri di ricerca. Il client di chat persistente invia un messaggio di informazioni SIP contenente il comando XCCOS **chansrch** (sala di ricerca), insieme ai criteri di ricerca. Il server di chat persistente esegue una query nel database back-end e risponde in un nuovo messaggio di informazioni SIP che contiene un elenco di sale disponibili che soddisfano i criteri di ricerca.

2.  User1 seleziona la chat room a cui vuole partecipare e quindi fa clic su **Segui questa sala**. Il client di chat persistente invia il server di chat persistente un messaggio di informazioni SIP contenente il comando di **join** XCCOS e l'ID sala della chat room selezionata dall'utente. Il server di chat persistente risponde con un messaggio di informazioni SIP che contiene i dati di provisioning.

3.  Il client di chat persistente invia il server di chat persistente un messaggio di informazioni SIP contenente il comando XCCOS **bccontext** (backchat context). Il server di chat persistente recupera la cronologia chat e la restituisce al client di chat persistente in un messaggio di informazioni SIP distinto. A questo punto, l'utente accede alla chat room ed è pronto per partecipare.

4.  User1 immette un nuovo messaggio e quindi fa clic su **Invia**. Il client di chat persistente invia il messaggio alla chat room in un comando SIP INFO XCCOS **grpchat** . Il server di chat persistente archivia una copia del nuovo messaggio nel database back-end della chat persistente.

5.  Il server di chat persistente invia una copia separata del messaggio SIP INFO XCCOS **grpchat** a User2, che ha già acceduto alla chat room.

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a>Flussi delle chiamate di conformità della chat persistente

Il server di chat persistente USA Accodamento messaggi (noto anche come MSMQ) e un database di conformità aggiuntivo (mgccomp) per elaborare i dati di conformità. Come esempio di come vengono elaborati gli eventi di conformità, la sequenza di eventi seguente descrive il modo in cui viene elaborato un evento post di messaggio.

1.  Un utente invia un messaggio a una chat room.

2.  Il server di chat persistente colloca le informazioni relative all'evento in una coda privata di Accodamento messaggi.

3.  Il server di conformità della chat persistente legge questo evento dalla coda e lo inserisce nel database mgccomp per l'elaborazione in un secondo momento.

4.  Periodicamente, il server di conformità della chat persistente elabora un set di eventi nel database e li invia alla scheda di conformità della chat persistente per l'elaborazione.

5.  Se l'adapter elabora correttamente i dati, il server di conformità della chat persistente elimina gli eventi dal database di mgccomp.

</div>

</div>

<span> </span>

</div>

</div>

</div>

