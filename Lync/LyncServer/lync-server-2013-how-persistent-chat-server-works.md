---
title: 'Lync Server 2013: funzionamento del server Chat persistente'
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
ms.openlocfilehash: d919d7c9d955355a45ebf3c05391204ca919a3fa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528173"
---
# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a>Funzionamento del server Chat persistente in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-21_

Lync Server 2013, il server Chat persistente consente di partecipare a conversazioni a più parti, basate su argomenti che persistono nel tempo. Il server Chat persistente può aiutare l'organizzazione a eseguire le operazioni seguenti:

  - Migliorare le comunicazioni tra team interfunzionali e distribuiti in zone geografiche diverse

  - Ampliare la condivisione delle informazioni e la partecipazione

  - Migliorare le comunicazioni con l'organizzazione estesa

  - Ridurre il sovraccarico di informazioni

  - Migliorare la consapevolezza delle informazioni

  - Migliorare la diffusione di informazioni e conoscenze importanti

È possibile distribuire il server Chat persistente come ruolo facoltativo con Lync Server 2013. I servizi di chat persistente vengono eseguiti in un pool dedicato e un pool di server Chat persistente dipende da un pool di Lync Server per instradare i messaggi. I client utilizzano eXtensible Chat Communication Over SIP (XCCOS). I server front end di Lync Server sono configurati per instradare il traffico a un pool di server Chat persistente.

<div>

## <a name="high-level-architecture"></a>Architettura di alto livello

Nei diagrammi seguenti vengono fornite prospettive di alto livello per l'architettura e i servizi del server Chat persistente.

**Architettura di alto livello del server Persistent Chat**

![Architettura del server Chat persistente.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Architettura del server Chat persistente.")

**Servizi di alto livello del server Persistent Chat**

![Componenti del server Chat persistente.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Componenti del server Chat persistente.")

Due servizi vengono eseguiti nei front end server di Persistent Chat:

  - Persistent Chat (Channel Service)

  - Conformità

<div>

## <a name="persistent-chat-channel-service"></a>Persistent Chat (Channel Service)

Il servizio chat persistente (canale) è il servizio di base responsabile del server Chat persistente. Questo servizio fornisce le funzioni seguenti:

  - Accetta i messaggi in arrivo

  - Registra ed elenca i partecipanti online in una chat room persistente

  - Ritrasmette i messaggi ai sottoscrittori di altri canali

  - Implementa la logica per la gestione dei canali, gli inviti alle chat room, le ricerche e le notifiche di nuovi contenuti

Il servizio chat (canale) persistente archivia e accede al contenuto delle chat room e ad altri metadati del sistema (regole di autorizzazione e così via) utilizzando l'Archivio Chat persistente. Questo servizio consente di archiviare i file caricati nelle chat room nell'archivio file di Persistent Chat.

</div>

<div>

## <a name="compliance-service"></a>Servizio Conformità

Il servizio di conformità è un componente facoltativo del server Chat persistente ed è responsabile dell'archiviazione del contenuto e degli eventi della chat nell'archivio di conformità di Persistent Chat. Se nell'organizzazione sono presenti normative che richiedono l'archiviazione di attività di chat persistente, è possibile distribuire il servizio di conformità di Persistent Chat facoltativo. Il servizio di conformità è installato in ogni server Chat persistente in un pool di chat persistente. Una volta configurata, la conformità del server Chat persistente registra le attività degli utenti, ad esempio l'accesso e la lettura dei messaggi. Il servizio di conformità archivia i file che devono essere archiviati nell'archivio file di conformità di Persistent Chat.

</div>

<div>

## <a name="persistent-chat-web-services"></a>Servizi Web di chat persistente

Nei server front end di Lync Server, vengono eseguiti due servizi che dipendono da Internet Information Services (IIS) e vengono implementati come componenti Web:

  - **Servizi Web di chat persistente per il caricamento o il download di file** Responsabile della pubblicazione e del recupero dei file dalle chat room.

  - **Servizi Web di chat persistente per la gestione delle chat room** Responsabile per fornire agli utenti la possibilità di gestire le chat room e creare nuove chat room.

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a>Come iniziare a utilizzare il server Chat persistente

Il server Chat persistente è un ruolo del server facoltativo all'interno dell'infrastruttura di Lync Server 2013. Se si installa il ruolo del server Chat persistente, tutti gli utenti abilitati tramite criteri da un amministratore possono utilizzare la chat persistente con il client Lync 2013.

Per informazioni dettagliate su come distribuire il server Chat persistente e consentire agli utenti di sfruttare le funzionalità in base ai criteri, vedere [Deploying Persistent Chat Server in Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md).

Per informazioni dettagliate su come configurare le impostazioni per la distribuzione del server Chat persistente, vedere [Deploying Persistent Chat Server in Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) e [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).

Per informazioni dettagliate su come abilitare gli utenti in base ai criteri in modo che possano sfruttare le funzionalità di Persistent Chat nel client Lync 2013, vedere [Deploying Persistent Chat Server in Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) e [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).

Se è stata distribuita la conformità a chat persistente, vedere [Managing Lync server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) per informazioni dettagliate su come configurare le impostazioni per la conformità.

</div>

<div>

## <a name="persistent-chat-call-flows"></a>Flussi delle chiamate di chat persistente

Il client Persistent Chat comunica con il servizio chat persistente mediante XCCOS. Le sequenze seguenti descrivono il processo di accesso e un tipico scenario di inserimento di messaggi e sottoscrizione a una chat.

<div>

## <a name="sign-in"></a>Accesso

Il diagramma di flusso di chiamata e i passaggi seguenti descrivono il processo di accesso.

**Flusso delle chiamate di accesso del client di chat persistente**

![Diagramma del flusso di chiamata del server Chat persistente.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Diagramma del flusso di chiamata del server Chat persistente.")

1.  Il client di chat persistente invia innanzitutto una sottoscrizione SIP per recuperare il documento di provisioning di tipo in-band dal server. Questo documento indica se la chat persistente è abilitata o disabilitata per l'utente e l'elenco degli URI SIP per il pool di server Chat persistente.

2.  Il client di chat persistente invia un messaggio SIP INVITE all'URI SIP del server Chat persistente ottenuto nel passaggio precedente. La sequenza di invito è seguita da 200 OK e ACK e il client di chat persistente ha aperto una sessione SIP con un endpoint del server Chat persistente. Di conseguenza, il client di chat persistente comunica con il server Chat persistente inviando messaggi di informazioni SIP che contengono messaggi di chat o comandi che richiedono al server di eseguire un'azione. Tutti questi messaggi sono riconosciuti con 200 OK o 503 servizio non disponibile (ovvero, in caso di carico del server pesante). Se il client riceve una risposta 503, ritenterà il messaggio. In questo esempio non è inclusa una risposta 503. Se il server accetta il messaggio o il comando e invia 200 OK, fornisce una risposta al client nel formato di un messaggio di informazioni SIP separato. Questa risposta include un riferimento al comando di origine.

3.  Il client di chat persistente invia un messaggio di informazioni SIP contenente il comando XCCOS **GetServerInfo** . Il server Chat persistente risponde con un nuovo messaggio di informazioni SIP che contiene informazioni sulla configurazione del servizio chat persistente.

4.  Il client di chat persistente invia un messaggio di informazioni SIP che contiene il comando XCCOS **GetAssociations** . Il server Chat persistente risponde con un nuovo messaggio di informazioni SIP che contiene l'elenco delle sale di cui l'utente è membro. Il client di chat persistente ripete il comando per recuperare l'elenco delle sale di cui l'utente è Manager.

5.  Il client di chat persistente Ottiene l'elenco delle sale seguite dal documento "presenza", in cui ogni sala è rappresentata da una categoria "roomSetting". La partecipazione a tutte le chat seguite avviene mediante un singolo messaggio SIP INFO contenente il comando XCCOS **bjoin** che contiene l'elenco degli URI delle chat. Poiché l'elenco delle chat seguite è mantenuto nel server, i client presenti in qualsiasi computer dispongono dello stesso elenco di chat seguite per l'URI utente specificato. Il client di chat persistente conserva anche l'elenco delle sale aperte (se questa opzione è abilitata dall'utente) nel registro di sistema del computer locale e si unisce a ognuna di queste sale all'accesso inviando un messaggio di informazioni SIP contenente il comando XCCOS **join** per ogni sala aperta. Poiché questo elenco viene conservato nel registro di sistema, può essere diverso in due client di chat persistente in esecuzione su computer diversi.

6.  Per ogni stanza aggiunta, il client di chat persistente invia un messaggio di informazioni SIP che contiene il comando XCCOS **bccontext** . Il server Chat persistente risponde con un nuovo messaggio di informazioni SIP che contiene il messaggio di chat più recente nella sala.

7.  Il client di chat persistente invia un messaggio di informazioni SIP contenente un comando XCCOS **getinv** (ovvero Get invito) per richiedere eventuali inviti a una nuova sala che il client non ha ancora visto. In un messaggio di informazioni SIP separato, il server Chat persistente restituisce un elenco di tali sale.

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a>Sottoscrizione a una chat e inserimento di un messaggio

Il diagramma di flusso di chiamata e i passaggi riportati di seguito descrivono una tipica sottoscrizione sala e uno scenario post messaggio.

**Sottoscrizione della sala client di chat persistente e flusso delle chiamate di registrazione messaggi**

![Scenario di sottoscrizione della sala e post del messaggio.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Scenario di sottoscrizione della sala e post del messaggio.")

1.  Dal client di chat persistente, User1 fa clic su **Unisciti a una chat room**, fa clic su **Cerca**e quindi immette alcuni criteri di ricerca. Il client di chat persistente invia un messaggio di informazioni SIP contenente il comando XCCOS **chansrch** (Room Search), insieme ai criteri di ricerca. Il server Chat persistente esegue una query nel database back-end e risponde in un nuovo messaggio di informazioni SIP contenente un elenco di sale disponibili che soddisfano i criteri di ricerca.

2.  L'utente 1 seleziona la chat cui desidera unirsi e quindi fa clic su **Segui questa chat room**. Il client di chat persistente invia il server Chat persistente un messaggio di informazioni SIP che contiene il comando XCCOS **join** e l'ID della chat room selezionata dall'utente. Il server Chat persistente risponde con un messaggio SIP INFO contenente i dati di provisioning.

3.  Il client di chat persistente invia il server Chat persistente un messaggio di informazioni SIP che contiene il comando XCCOS **bccontext** (backchat context). Il server Chat persistente recupera la cronologia della chat e la restituisce al client di chat persistente in un messaggio di informazioni SIP separato. A questo punto, l'utente accede alla chat room ed è pronto a partecipare.

4.  L'utente 1 immette un nuovo messaggio e quindi fa clic su **Invia**. Il client Chat persistente invia il messaggio alla chat room in un comando SIP INFO XCCOS **grpchat** . Il server Chat persistente archivia una copia di questo nuovo messaggio nel database back-end della chat persistente.

5.  Il server Chat persistente invia una copia separata del messaggio SIP INFO XCCOS **grpchat** a User2, che ha già immesso la chat room.

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a>Flussi delle chiamate di conformità di chat persistente

Il server Chat persistente utilizza l'accodamento dei messaggi (noto anche come MSMQ) e un ulteriore database di conformità (mgccomp) per elaborare i dati di conformità. Come esempio di elaborazione degli eventi di conformità, la sequenza di eventi seguente descrive come viene elaborato un evento di inserimento di un messaggio.

1.  Un utente inserisce un messaggio in una chat.

2.  Il server Chat persistente inserisce informazioni relative all'evento in una coda di Accodamento messaggi privata.

3.  Il server Compliance chat persistente legge questo evento dalla coda e lo inserisce nel database di mgccomp per l'elaborazione in un secondo momento.

4.  Periodicamente, il server di conformità di Persistent Chat elabora un insieme di eventi nel database e li invia alla scheda di conformità di Persistent Chat per l'elaborazione.

5.  Se la scheda elabora correttamente i dati, il server di conformità di Persistent Chat eliminerà gli eventi dal database di mgccomp.

</div>

</div>

<span> </span>

</div>

</div>

</div>

