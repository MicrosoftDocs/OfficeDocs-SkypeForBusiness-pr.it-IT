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
# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a><span data-ttu-id="2962d-102">Funzionamento del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2962d-102">How Persistent Chat Server works in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2962d-103">_**Ultimo argomento modificato:** 2012-11-21_</span><span class="sxs-lookup"><span data-stu-id="2962d-103">_**Topic Last Modified:** 2012-11-21_</span></span>

<span data-ttu-id="2962d-104">Lync Server 2013, il server Chat persistente consente di partecipare a conversazioni a più parti, basate su argomenti che persistono nel tempo.</span><span class="sxs-lookup"><span data-stu-id="2962d-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="2962d-105">Il server Chat persistente può aiutare l'organizzazione a eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2962d-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="2962d-106">Migliorare le comunicazioni tra team interfunzionali e distribuiti in zone geografiche diverse</span><span class="sxs-lookup"><span data-stu-id="2962d-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="2962d-107">Ampliare la condivisione delle informazioni e la partecipazione</span><span class="sxs-lookup"><span data-stu-id="2962d-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="2962d-108">Migliorare le comunicazioni con l'organizzazione estesa</span><span class="sxs-lookup"><span data-stu-id="2962d-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="2962d-109">Ridurre il sovraccarico di informazioni</span><span class="sxs-lookup"><span data-stu-id="2962d-109">Reduce information overload</span></span>

  - <span data-ttu-id="2962d-110">Migliorare la consapevolezza delle informazioni</span><span class="sxs-lookup"><span data-stu-id="2962d-110">Improve information awareness</span></span>

  - <span data-ttu-id="2962d-111">Migliorare la diffusione di informazioni e conoscenze importanti</span><span class="sxs-lookup"><span data-stu-id="2962d-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="2962d-112">È possibile distribuire il server Chat persistente come ruolo facoltativo con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2962d-112">You can deploy Persistent Chat Server as an optional role with Lync Server 2013.</span></span> <span data-ttu-id="2962d-113">I servizi di chat persistente vengono eseguiti in un pool dedicato e un pool di server Chat persistente dipende da un pool di Lync Server per instradare i messaggi.</span><span class="sxs-lookup"><span data-stu-id="2962d-113">Persistent Chat services run on a dedicated pool, and a Persistent Chat Server pool depends on a Lync Server pool to route messages to it.</span></span> <span data-ttu-id="2962d-114">I client utilizzano eXtensible Chat Communication Over SIP (XCCOS).</span><span class="sxs-lookup"><span data-stu-id="2962d-114">Clients use eXtensible Chat Communication Over SIP (XCCOS).</span></span> <span data-ttu-id="2962d-115">I server front end di Lync Server sono configurati per instradare il traffico a un pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2962d-115">The Lync Server Front End Servers are configured to route the traffic to a Persistent Chat Server pool.</span></span>

<div>

## <a name="high-level-architecture"></a><span data-ttu-id="2962d-116">Architettura di alto livello</span><span class="sxs-lookup"><span data-stu-id="2962d-116">High-Level Architecture</span></span>

<span data-ttu-id="2962d-117">Nei diagrammi seguenti vengono fornite prospettive di alto livello per l'architettura e i servizi del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2962d-117">The following diagrams provide high-level perspectives of the Persistent Chat Server architecture and services.</span></span>

<span data-ttu-id="2962d-118">**Architettura di alto livello del server Persistent Chat**</span><span class="sxs-lookup"><span data-stu-id="2962d-118">**Persistent Chat Server High-Level Architecture**</span></span>

<span data-ttu-id="2962d-119">![Architettura del server Chat persistente.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Architettura del server Chat persistente.")</span><span class="sxs-lookup"><span data-stu-id="2962d-119">![Persistent Chat Server architecture.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Persistent Chat Server architecture.")</span></span>

<span data-ttu-id="2962d-120">**Servizi di alto livello del server Persistent Chat**</span><span class="sxs-lookup"><span data-stu-id="2962d-120">**Persistent Chat Server High-Level Services**</span></span>

<span data-ttu-id="2962d-121">![Componenti del server Chat persistente.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Componenti del server Chat persistente.")</span><span class="sxs-lookup"><span data-stu-id="2962d-121">![Persistent Chat Server components.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Persistent Chat Server components.")</span></span>

<span data-ttu-id="2962d-122">Due servizi vengono eseguiti nei front end server di Persistent Chat:</span><span class="sxs-lookup"><span data-stu-id="2962d-122">Two services run on the Persistent Chat Server Front End Servers:</span></span>

  - <span data-ttu-id="2962d-123">Persistent Chat (Channel Service)</span><span class="sxs-lookup"><span data-stu-id="2962d-123">Persistent Chat (Channel)</span></span>

  - <span data-ttu-id="2962d-124">Conformità</span><span class="sxs-lookup"><span data-stu-id="2962d-124">Compliance</span></span>

<div>

## <a name="persistent-chat-channel-service"></a><span data-ttu-id="2962d-125">Persistent Chat (Channel Service)</span><span class="sxs-lookup"><span data-stu-id="2962d-125">Persistent Chat (Channel) Service</span></span>

<span data-ttu-id="2962d-126">Il servizio chat persistente (canale) è il servizio di base responsabile del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2962d-126">The Persistent Chat (Channel) service is the core service responsible for Persistent Chat Server.</span></span> <span data-ttu-id="2962d-127">Questo servizio fornisce le funzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2962d-127">This service provides the following functions:</span></span>

  - <span data-ttu-id="2962d-128">Accetta i messaggi in arrivo</span><span class="sxs-lookup"><span data-stu-id="2962d-128">Accepts incoming messages</span></span>

  - <span data-ttu-id="2962d-129">Registra ed elenca i partecipanti online in una chat room persistente</span><span class="sxs-lookup"><span data-stu-id="2962d-129">Registers and lists online participants within a Persistent Chat room</span></span>

  - <span data-ttu-id="2962d-130">Ritrasmette i messaggi ai sottoscrittori di altri canali</span><span class="sxs-lookup"><span data-stu-id="2962d-130">Retransmits messages to other channel subscribers</span></span>

  - <span data-ttu-id="2962d-131">Implementa la logica per la gestione dei canali, gli inviti alle chat room, le ricerche e le notifiche di nuovi contenuti</span><span class="sxs-lookup"><span data-stu-id="2962d-131">Implements logic for channel management, chat room invitation, search, and new content notifications</span></span>

<span data-ttu-id="2962d-132">Il servizio chat (canale) persistente archivia e accede al contenuto delle chat room e ad altri metadati del sistema (regole di autorizzazione e così via) utilizzando l'Archivio Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2962d-132">The Persistent Chat (Channel) service stores and accesses chat room content and other system metadata (authorization rules, and so on) by using the Persistent Chat Store.</span></span> <span data-ttu-id="2962d-133">Questo servizio consente di archiviare i file caricati nelle chat room nell'archivio file di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="2962d-133">This service stores files that are uploaded into chat rooms in the Persistent Chat File Store.</span></span>

</div>

<div>

## <a name="compliance-service"></a><span data-ttu-id="2962d-134">Servizio Conformità</span><span class="sxs-lookup"><span data-stu-id="2962d-134">Compliance Service</span></span>

<span data-ttu-id="2962d-135">Il servizio di conformità è un componente facoltativo del server Chat persistente ed è responsabile dell'archiviazione del contenuto e degli eventi della chat nell'archivio di conformità di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="2962d-135">The Compliance service is an optional component of Persistent Chat Server and is responsible for archiving chat content and events to the Persistent Chat Compliance Store.</span></span> <span data-ttu-id="2962d-136">Se nell'organizzazione sono presenti normative che richiedono l'archiviazione di attività di chat persistente, è possibile distribuire il servizio di conformità di Persistent Chat facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2962d-136">If your organization has regulations that require Persistent Chat activity to be archived, you can deploy the optional Persistent Chat Compliance service.</span></span> <span data-ttu-id="2962d-137">Il servizio di conformità è installato in ogni server Chat persistente in un pool di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2962d-137">The Compliance service is installed on each Persistent Chat Server in a Persistent Chat pool.</span></span> <span data-ttu-id="2962d-138">Una volta configurata, la conformità del server Chat persistente registra le attività degli utenti, ad esempio l'accesso e la lettura dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="2962d-138">When configured, Persistent Chat Server compliance records user activity such as joining and leaving rooms, and posting and reading of messages.</span></span> <span data-ttu-id="2962d-139">Il servizio di conformità archivia i file che devono essere archiviati nell'archivio file di conformità di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="2962d-139">The Compliance service stores files that need to be archived in the Persistent Chat Compliance File Store.</span></span>

</div>

<div>

## <a name="persistent-chat-web-services"></a><span data-ttu-id="2962d-140">Servizi Web di chat persistente</span><span class="sxs-lookup"><span data-stu-id="2962d-140">Persistent Chat Web Services</span></span>

<span data-ttu-id="2962d-141">Nei server front end di Lync Server, vengono eseguiti due servizi che dipendono da Internet Information Services (IIS) e vengono implementati come componenti Web:</span><span class="sxs-lookup"><span data-stu-id="2962d-141">On the Lync Server Front End Servers, two services run that depend on Internet Information Services (IIS), and are implemented as web components:</span></span>

  - <span data-ttu-id="2962d-142">**Servizi Web di chat persistente per il caricamento o il download di file** Responsabile della pubblicazione e del recupero dei file dalle chat room.</span><span class="sxs-lookup"><span data-stu-id="2962d-142">**Persistent Chat Web Services for File Upload/Download** Responsible for posting and retrieving files from chat rooms.</span></span>

  - <span data-ttu-id="2962d-143">**Servizi Web di chat persistente per la gestione delle chat room** Responsabile per fornire agli utenti la possibilità di gestire le chat room e creare nuove chat room.</span><span class="sxs-lookup"><span data-stu-id="2962d-143">**Persistent Chat Web Services for Chat Room Management** Responsible for providing users the ability to manage their chat rooms, and create new chat rooms.</span></span>

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a><span data-ttu-id="2962d-144">Come iniziare a utilizzare il server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="2962d-144">How Do I Start Using Persistent Chat Server?</span></span>

<span data-ttu-id="2962d-145">Il server Chat persistente è un ruolo del server facoltativo all'interno dell'infrastruttura di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2962d-145">Persistent Chat Server is an optional server role within the Lync Server 2013 infrastructure.</span></span> <span data-ttu-id="2962d-146">Se si installa il ruolo del server Chat persistente, tutti gli utenti abilitati tramite criteri da un amministratore possono utilizzare la chat persistente con il client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="2962d-146">If you install the Persistent Chat Server role, any users who have been enabled through policy by an administrator can use Persistent Chat with the Lync 2013 client.</span></span>

<span data-ttu-id="2962d-147">Per informazioni dettagliate su come distribuire il server Chat persistente e consentire agli utenti di sfruttare le funzionalità in base ai criteri, vedere [Deploying Persistent Chat Server in Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="2962d-147">For details about how to deploy Persistent Chat Server and enable users to leverage the capabilities by policy, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>

<span data-ttu-id="2962d-148">Per informazioni dettagliate su come configurare le impostazioni per la distribuzione del server Chat persistente, vedere [Deploying Persistent Chat Server in Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) e [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="2962d-148">For details about how to configure settings on your Persistent Chat Server deployment, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="2962d-149">Per informazioni dettagliate su come abilitare gli utenti in base ai criteri in modo che possano sfruttare le funzionalità di Persistent Chat nel client Lync 2013, vedere [Deploying Persistent Chat Server in Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) e [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="2962d-149">For details about how to enable users by policy such that they can leverage Persistent Chat functionality in Lync 2013 client, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="2962d-150">Se è stata distribuita la conformità a chat persistente, vedere [Managing Lync server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) per informazioni dettagliate su come configurare le impostazioni per la conformità.</span><span class="sxs-lookup"><span data-stu-id="2962d-150">If you deployed Persistent Chat compliance, see [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) for details about how to configure settings for compliance.</span></span>

</div>

<div>

## <a name="persistent-chat-call-flows"></a><span data-ttu-id="2962d-151">Flussi delle chiamate di chat persistente</span><span class="sxs-lookup"><span data-stu-id="2962d-151">Persistent Chat Call Flows</span></span>

<span data-ttu-id="2962d-152">Il client Persistent Chat comunica con il servizio chat persistente mediante XCCOS.</span><span class="sxs-lookup"><span data-stu-id="2962d-152">The Persistent Chat client communicates with the Persistent Chat service by using XCCOS.</span></span> <span data-ttu-id="2962d-153">Le sequenze seguenti descrivono il processo di accesso e un tipico scenario di inserimento di messaggi e sottoscrizione a una chat.</span><span class="sxs-lookup"><span data-stu-id="2962d-153">The following sequences describe the sign-in process and a typical room subscription and message post scenario.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="2962d-154">Accesso</span><span class="sxs-lookup"><span data-stu-id="2962d-154">Sign-in</span></span>

<span data-ttu-id="2962d-155">Il diagramma di flusso di chiamata e i passaggi seguenti descrivono il processo di accesso.</span><span class="sxs-lookup"><span data-stu-id="2962d-155">The following call flow diagram and steps describe the sign-in process.</span></span>

<span data-ttu-id="2962d-156">**Flusso delle chiamate di accesso del client di chat persistente**</span><span class="sxs-lookup"><span data-stu-id="2962d-156">**Persistent Chat Client Sign-in Call Flow**</span></span>

<span data-ttu-id="2962d-157">![Diagramma del flusso di chiamata del server Chat persistente.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Diagramma del flusso di chiamata del server Chat persistente.")</span><span class="sxs-lookup"><span data-stu-id="2962d-157">![Persistent Chat Server call flow diagram.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Persistent Chat Server call flow diagram.")</span></span>

1.  <span data-ttu-id="2962d-158">Il client di chat persistente invia innanzitutto una sottoscrizione SIP per recuperare il documento di provisioning di tipo in-band dal server.</span><span class="sxs-lookup"><span data-stu-id="2962d-158">The Persistent Chat client first sends a SIP SUBSCRIBE to retrieve the in-band provisioning document from the server.</span></span> <span data-ttu-id="2962d-159">Questo documento indica se la chat persistente è abilitata o disabilitata per l'utente e l'elenco degli URI SIP per il pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2962d-159">This document indicates if Persistent Chat is enabled or disabled for the user and the list of SIP URIs for the Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="2962d-160">Il client di chat persistente invia un messaggio SIP INVITE all'URI SIP del server Chat persistente ottenuto nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="2962d-160">The Persistent Chat client sends a SIP INVITE message to the SIP URI of the Persistent Chat Server that it obtained in the previous step.</span></span> <span data-ttu-id="2962d-161">La sequenza di invito è seguita da 200 OK e ACK e il client di chat persistente ha aperto una sessione SIP con un endpoint del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2962d-161">The INVITE sequence is followed by 200 OK and ACK, and the Persistent Chat client has now opened a SIP session with a Persistent Chat Server endpoint.</span></span> <span data-ttu-id="2962d-162">Di conseguenza, il client di chat persistente comunica con il server Chat persistente inviando messaggi di informazioni SIP che contengono messaggi di chat o comandi che richiedono al server di eseguire un'azione.</span><span class="sxs-lookup"><span data-stu-id="2962d-162">Consequently, the Persistent Chat client communicates with Persistent Chat Server by sending SIP INFO messages that contain either chat messages or commands requesting the server to take an action.</span></span> <span data-ttu-id="2962d-163">Tutti questi messaggi sono riconosciuti con 200 OK o 503 servizio non disponibile (ovvero, in caso di carico del server pesante).</span><span class="sxs-lookup"><span data-stu-id="2962d-163">All of these messages are acknowledged with either 200 OK or 503 Service Unavailable (that is, in the event of heavy server load).</span></span> <span data-ttu-id="2962d-164">Se il client riceve una risposta 503, ritenterà il messaggio.</span><span class="sxs-lookup"><span data-stu-id="2962d-164">If the client receives a 503 response, it will retry the message.</span></span> <span data-ttu-id="2962d-165">In questo esempio non è inclusa una risposta 503. Se il server accetta il messaggio o il comando e invia 200 OK, fornisce una risposta al client nel formato di un messaggio di informazioni SIP separato.</span><span class="sxs-lookup"><span data-stu-id="2962d-165">(This example does not include a 503 response.) If the server accepts the message or command and sends 200 OK, it provides a response to the client in the form of a separate SIP INFO message.</span></span> <span data-ttu-id="2962d-166">Questa risposta include un riferimento al comando di origine.</span><span class="sxs-lookup"><span data-stu-id="2962d-166">This response includes a reference to the originating command.</span></span>

3.  <span data-ttu-id="2962d-167">Il client di chat persistente invia un messaggio di informazioni SIP contenente il comando XCCOS **GetServerInfo** .</span><span class="sxs-lookup"><span data-stu-id="2962d-167">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getserverinfo** command.</span></span> <span data-ttu-id="2962d-168">Il server Chat persistente risponde con un nuovo messaggio di informazioni SIP che contiene informazioni sulla configurazione del servizio chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2962d-168">Persistent Chat Server replies with a new SIP INFO message that contains information about the Persistent Chat service configuration.</span></span>

4.  <span data-ttu-id="2962d-169">Il client di chat persistente invia un messaggio di informazioni SIP che contiene il comando XCCOS **GetAssociations** .</span><span class="sxs-lookup"><span data-stu-id="2962d-169">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getassociations** command.</span></span> <span data-ttu-id="2962d-170">Il server Chat persistente risponde con un nuovo messaggio di informazioni SIP che contiene l'elenco delle sale di cui l'utente è membro.</span><span class="sxs-lookup"><span data-stu-id="2962d-170">Persistent Chat Server replies with a new SIP INFO message that contains the list of rooms of which the user is a member.</span></span> <span data-ttu-id="2962d-171">Il client di chat persistente ripete il comando per recuperare l'elenco delle sale di cui l'utente è Manager.</span><span class="sxs-lookup"><span data-stu-id="2962d-171">The Persistent Chat client repeats the command to retrieve the list of rooms of which the user is a manager.</span></span>

5.  <span data-ttu-id="2962d-172">Il client di chat persistente Ottiene l'elenco delle sale seguite dal documento "presenza", in cui ogni sala è rappresentata da una categoria "roomSetting".</span><span class="sxs-lookup"><span data-stu-id="2962d-172">The Persistent Chat client gets the list of followed rooms from the "presence" document, where each followed room is represented by a "roomSetting" category.</span></span> <span data-ttu-id="2962d-173">La partecipazione a tutte le chat seguite avviene mediante un singolo messaggio SIP INFO contenente il comando XCCOS **bjoin** che contiene l'elenco degli URI delle chat.</span><span class="sxs-lookup"><span data-stu-id="2962d-173">All followed rooms are joined by a single SIP INFO message that contains the XCCOS **bjoin** command that contains the list of room URIs.</span></span> <span data-ttu-id="2962d-174">Poiché l'elenco delle chat seguite è mantenuto nel server, i client presenti in qualsiasi computer dispongono dello stesso elenco di chat seguite per l'URI utente specificato.</span><span class="sxs-lookup"><span data-stu-id="2962d-174">Because the list of followed rooms is kept on the server, any client on any computer has the same list of followed rooms for the specified user URI.</span></span> <span data-ttu-id="2962d-175">Il client di chat persistente conserva anche l'elenco delle sale aperte (se questa opzione è abilitata dall'utente) nel registro di sistema del computer locale e si unisce a ognuna di queste sale all'accesso inviando un messaggio di informazioni SIP contenente il comando XCCOS **join** per ogni sala aperta.</span><span class="sxs-lookup"><span data-stu-id="2962d-175">The Persistent Chat client also keeps the list of opened rooms (if this option is enabled by the user) in the local computer registry, and joins each of these rooms at sign-in by sending a SIP INFO message that contains the XCCOS **join** command for each opened room.</span></span> <span data-ttu-id="2962d-176">Poiché questo elenco viene conservato nel registro di sistema, può essere diverso in due client di chat persistente in esecuzione su computer diversi.</span><span class="sxs-lookup"><span data-stu-id="2962d-176">Because this list is kept in the registry, it can be different on two Persistent Chat clients running on different computers.</span></span>

6.  <span data-ttu-id="2962d-177">Per ogni stanza aggiunta, il client di chat persistente invia un messaggio di informazioni SIP che contiene il comando XCCOS **bccontext** .</span><span class="sxs-lookup"><span data-stu-id="2962d-177">For each room joined, the Persistent Chat client sends a SIP INFO message that contains the XCCOS **bccontext** command.</span></span> <span data-ttu-id="2962d-178">Il server Chat persistente risponde con un nuovo messaggio di informazioni SIP che contiene il messaggio di chat più recente nella sala.</span><span class="sxs-lookup"><span data-stu-id="2962d-178">Persistent Chat Server replies with a new SIP INFO message that contains the most recent chat message in the room.</span></span>

7.  <span data-ttu-id="2962d-179">Il client di chat persistente invia un messaggio di informazioni SIP contenente un comando XCCOS **getinv** (ovvero Get invito) per richiedere eventuali inviti a una nuova sala che il client non ha ancora visto.</span><span class="sxs-lookup"><span data-stu-id="2962d-179">The Persistent Chat client sends a SIP INFO message that contains a XCCOS **getinv** (that is, get invitation) command to request any new room invitations that the client has not yet seen.</span></span> <span data-ttu-id="2962d-180">In un messaggio di informazioni SIP separato, il server Chat persistente restituisce un elenco di tali sale.</span><span class="sxs-lookup"><span data-stu-id="2962d-180">In a separate SIP INFO message, Persistent Chat Server returns a list of those rooms.</span></span>

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a><span data-ttu-id="2962d-181">Sottoscrizione a una chat e inserimento di un messaggio</span><span class="sxs-lookup"><span data-stu-id="2962d-181">Subscribe to a Room and Post a Message</span></span>

<span data-ttu-id="2962d-182">Il diagramma di flusso di chiamata e i passaggi riportati di seguito descrivono una tipica sottoscrizione sala e uno scenario post messaggio.</span><span class="sxs-lookup"><span data-stu-id="2962d-182">The following call flow diagram and steps describe a typical room subscription and message post scenario.</span></span>

<span data-ttu-id="2962d-183">**Sottoscrizione della sala client di chat persistente e flusso delle chiamate di registrazione messaggi**</span><span class="sxs-lookup"><span data-stu-id="2962d-183">**Persistent Chat Client Room Subscription and Message Posting Call Flow**</span></span>

<span data-ttu-id="2962d-184">![Scenario di sottoscrizione della sala e post del messaggio.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Scenario di sottoscrizione della sala e post del messaggio.")</span><span class="sxs-lookup"><span data-stu-id="2962d-184">![Room subscription and message post scenario.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Room subscription and message post scenario.")</span></span>

1.  <span data-ttu-id="2962d-185">Dal client di chat persistente, User1 fa clic su **Unisciti a una chat room**, fa clic su **Cerca**e quindi immette alcuni criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="2962d-185">From the Persistent Chat client, User1 clicks **Join a Chat Room**, clicks **Search**, and then enters some search criteria.</span></span> <span data-ttu-id="2962d-186">Il client di chat persistente invia un messaggio di informazioni SIP contenente il comando XCCOS **chansrch** (Room Search), insieme ai criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="2962d-186">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **chansrch** (room search) command, along with the search criteria.</span></span> <span data-ttu-id="2962d-187">Il server Chat persistente esegue una query nel database back-end e risponde in un nuovo messaggio di informazioni SIP contenente un elenco di sale disponibili che soddisfano i criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="2962d-187">Persistent Chat Server queries the back-end database and replies in a new SIP INFO message that contains a list of available rooms that meet the search criteria.</span></span>

2.  <span data-ttu-id="2962d-188">L'utente 1 seleziona la chat cui desidera unirsi e quindi fa clic su **Segui questa chat room**.</span><span class="sxs-lookup"><span data-stu-id="2962d-188">User1 selects the chat room that he or she wants to join, and then clicks **Follow this room**.</span></span> <span data-ttu-id="2962d-189">Il client di chat persistente invia il server Chat persistente un messaggio di informazioni SIP che contiene il comando XCCOS **join** e l'ID della chat room selezionata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="2962d-189">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **join** command and the room ID of the chat room that the user selected.</span></span> <span data-ttu-id="2962d-190">Il server Chat persistente risponde con un messaggio SIP INFO contenente i dati di provisioning.</span><span class="sxs-lookup"><span data-stu-id="2962d-190">Persistent Chat Server replies with a SIP INFO message that contains the provisioning data.</span></span>

3.  <span data-ttu-id="2962d-191">Il client di chat persistente invia il server Chat persistente un messaggio di informazioni SIP che contiene il comando XCCOS **bccontext** (backchat context).</span><span class="sxs-lookup"><span data-stu-id="2962d-191">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **bccontext** (backchat context) command.</span></span> <span data-ttu-id="2962d-192">Il server Chat persistente recupera la cronologia della chat e la restituisce al client di chat persistente in un messaggio di informazioni SIP separato.</span><span class="sxs-lookup"><span data-stu-id="2962d-192">Persistent Chat Server retrieves the chat history, and returns it to the Persistent Chat client in a separate SIP INFO message.</span></span> <span data-ttu-id="2962d-193">A questo punto, l'utente accede alla chat room ed è pronto a partecipare.</span><span class="sxs-lookup"><span data-stu-id="2962d-193">At this point, the user enters the chat room and is ready to participate.</span></span>

4.  <span data-ttu-id="2962d-194">L'utente 1 immette un nuovo messaggio e quindi fa clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="2962d-194">User1 enters a new message, and then clicks **Send**.</span></span> <span data-ttu-id="2962d-195">Il client Chat persistente invia il messaggio alla chat room in un comando SIP INFO XCCOS **grpchat** .</span><span class="sxs-lookup"><span data-stu-id="2962d-195">The Persistent Chat client posts the message to the chat room in a SIP INFO XCCOS **grpchat** command.</span></span> <span data-ttu-id="2962d-196">Il server Chat persistente archivia una copia di questo nuovo messaggio nel database back-end della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2962d-196">Persistent Chat Server stores a copy of this new message in the Persistent Chat back-end database.</span></span>

5.  <span data-ttu-id="2962d-197">Il server Chat persistente invia una copia separata del messaggio SIP INFO XCCOS **grpchat** a User2, che ha già immesso la chat room.</span><span class="sxs-lookup"><span data-stu-id="2962d-197">Persistent Chat Server sends a separate copy of the SIP INFO XCCOS **grpchat** message to User2, who has already entered the chat room.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a><span data-ttu-id="2962d-198">Flussi delle chiamate di conformità di chat persistente</span><span class="sxs-lookup"><span data-stu-id="2962d-198">Persistent Chat Compliance Call Flows</span></span>

<span data-ttu-id="2962d-199">Il server Chat persistente utilizza l'accodamento dei messaggi (noto anche come MSMQ) e un ulteriore database di conformità (mgccomp) per elaborare i dati di conformità.</span><span class="sxs-lookup"><span data-stu-id="2962d-199">Persistent Chat Server uses Message Queuing (also known as MSMQ) and an additional compliance database (mgccomp) to process compliance data.</span></span> <span data-ttu-id="2962d-200">Come esempio di elaborazione degli eventi di conformità, la sequenza di eventi seguente descrive come viene elaborato un evento di inserimento di un messaggio.</span><span class="sxs-lookup"><span data-stu-id="2962d-200">As an example of how compliance events are processed, the following sequence of events describes how a message post event is processed.</span></span>

1.  <span data-ttu-id="2962d-201">Un utente inserisce un messaggio in una chat.</span><span class="sxs-lookup"><span data-stu-id="2962d-201">A user posts a message to a room.</span></span>

2.  <span data-ttu-id="2962d-202">Il server Chat persistente inserisce informazioni relative all'evento in una coda di Accodamento messaggi privata.</span><span class="sxs-lookup"><span data-stu-id="2962d-202">Persistent Chat Server places information pertaining to the event in a private Message Queuing queue.</span></span>

3.  <span data-ttu-id="2962d-203">Il server Compliance chat persistente legge questo evento dalla coda e lo inserisce nel database di mgccomp per l'elaborazione in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="2962d-203">Persistent Chat Compliance server reads this event from the queue, and places it into the mgccomp database for processing later.</span></span>

4.  <span data-ttu-id="2962d-204">Periodicamente, il server di conformità di Persistent Chat elabora un insieme di eventi nel database e li invia alla scheda di conformità di Persistent Chat per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="2962d-204">Periodically, the Persistent Chat Compliance server processes a set of events in the database, and sends them to the Persistent Chat Compliance adapter for processing.</span></span>

5.  <span data-ttu-id="2962d-205">Se la scheda elabora correttamente i dati, il server di conformità di Persistent Chat eliminerà gli eventi dal database di mgccomp.</span><span class="sxs-lookup"><span data-stu-id="2962d-205">If the adapter successfully processes the data, Persistent Chat Compliance server deletes the events from the mgccomp database.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

