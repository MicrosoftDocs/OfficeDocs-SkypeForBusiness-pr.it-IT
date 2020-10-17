---
title: Visualizzare le applicazioni server MSPL (Microsoft SIP Processing Language)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Microsoft SIP Processing Language (MSPL) server applications
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182575(v=OCS.15)
ms:contentKeyID: 48185202
ms.date: 09/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22a4098ed36be274f31aaeebb381654595884377
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518463"
---
# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a><span data-ttu-id="93064-102">Visualizzare le applicazioni server MSPL (Microsoft SIP Processing Language) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93064-102">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93064-103">_**Ultimo argomento modificato:** 2014-09-26_</span><span class="sxs-lookup"><span data-stu-id="93064-103">_**Topic Last Modified:** 2014-09-26_</span></span>

<span data-ttu-id="93064-104">Un'applicazione server MSPL (Microsoft SIP Processing Language) è un'applicazione di solo script che utilizza un linguaggio di script anziché l'API Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="93064-104">A Microsoft SIP Processing Language (MSPL) server application is a script-only application that uses a scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="93064-105">Il linguaggio MSPL garantisce un controllo più granulare sui comportamenti dei proxy e dei filtri, oltre a funzionalità per l'invio di messaggi specifici ad applicazioni SIP basate sulle transazioni.</span><span class="sxs-lookup"><span data-stu-id="93064-105">MSPL provides more granular control over filtering and proxy behaviors, in addition to a facility for dispatching specific messages to transaction-based SIP applications.</span></span> <span data-ttu-id="93064-106">MSPL viene utilizzato in particolare per filtrare ed eseguire il routing di messaggi SIP.</span><span class="sxs-lookup"><span data-stu-id="93064-106">MSPL is used specifically for filtering and routing SIP messages.</span></span> <span data-ttu-id="93064-107">Le applicazioni di MSPL vengono eseguite nello stesso processo del modulo UserServices, mentre un programma basato sull'API Lync 2010 viene eseguito in un processo separato.</span><span class="sxs-lookup"><span data-stu-id="93064-107">MSPL applications run in the same process as the UserServices module, while a program that is based on the Lync 2010 API runs in a separate process.</span></span>

<span data-ttu-id="93064-108">È possibile utilizzare la pagina **applicazione server** nel gruppo di **topologia** del pannello di controllo di Lync Server per visualizzare un elenco delle applicazioni server di MSPL che vengono eseguite nei front end server nell'ambiente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="93064-108">You can use the **Server Application** page in the **Topology** group of Lync Server Control Panel to see a list of MSPL server applications that run on Front End Servers in your Lync Server 2013 environment.</span></span> <span data-ttu-id="93064-109">L'elenco mostra gli script disponibili per ogni pool e indica se sono abilitati o critici.</span><span class="sxs-lookup"><span data-stu-id="93064-109">The list shows the scripts that are available for each pool, as well as whether they are enabled or critical.</span></span> <span data-ttu-id="93064-110">Gli script vengono eseguiti nell'ordine in cui sono elencati.</span><span class="sxs-lookup"><span data-stu-id="93064-110">The scripts run in the order they are listed.</span></span>

<span data-ttu-id="93064-111">Tali script includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="93064-111">These scripts include the following:</span></span>

  - <span data-ttu-id="93064-p103">ClientVersionFilter fornisce all'amministratore un metodo per specificare la versione dei client supportati da un pool. Il filtro della versione client controlla la versione del client e può impedire l'accesso al client o visualizzare un messaggio all'utente per segnalare che sta utilizzando un client non supportato. Il filtro della versione client può inoltre essere configurato per la visualizzazione di un messaggio contenente l'URL della versione scaricabile più recente del client.</span><span class="sxs-lookup"><span data-stu-id="93064-p103">ClientVersionFilter provides the administrator with a way to specify the version of clients that are supported by a pool. The client version filter checks the client version and can either prevent the client from logging on or present the user with a message that indicates he or she is using a client that is not supported. The client version filter can also be configured to display a message to the user that contains the URL of the latest downloadable version of the client.</span></span>

  - <span data-ttu-id="93064-115">TranslationService converte un numero composto da un utente in numero in formato E.164 in base alle regole di normalizzazione definite dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="93064-115">TranslationService translates a number that a user dials to an E.164 number according to the normalization rules defined by the administrator.</span></span> <span data-ttu-id="93064-116">Per informazioni dettagliate, vedere [Translation Rules in Lync Server 2013](lync-server-2013-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="93064-116">For details, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md).</span></span>

  - <span data-ttu-id="93064-117">IncomingFederation impone la convalida di federazione a livello di tenant per i messaggi tra tenant e in arrivo da distribuzioni esterne.</span><span class="sxs-lookup"><span data-stu-id="93064-117">IncomingFederation enforces tenant-level federation validation for inter-tenant and incoming messages from external deployments.</span></span>

  - <span data-ttu-id="93064-p105">UserServices è il componente di un Front End Server per funzione di registrazione SIP, presenza e conferenze. Offre funzionalità altamente integrate di messaggistica istantanea, presenza e per conferenze basate sul proxy SIP.</span><span class="sxs-lookup"><span data-stu-id="93064-p105">UserServices is the SIP Registrar, presence, and conferencing component of a Front End Server. It provides closely integrated IM, presence, and conferencing features built on top of the SIP Proxy.</span></span>

  - <span data-ttu-id="93064-120">InterClusterRouting è responsabile per il routing delle chiamate al pool della funzione di registrazione primario del chiamante.</span><span class="sxs-lookup"><span data-stu-id="93064-120">InterClusterRouting is responsible for routing calls to the callee’s primary Registrar pool.</span></span> <span data-ttu-id="93064-121">Per informazioni dettagliate, vedere [front end server VoIP Components for Lync server 2013](lync-server-2013-front-end-server-voip-components.md).</span><span class="sxs-lookup"><span data-stu-id="93064-121">For details, see [Front End Server VoIP components for Lync Server 2013](lync-server-2013-front-end-server-voip-components.md).</span></span>

  - <span data-ttu-id="93064-122">IIMFilter (Intelligent IM Filter) blocca i messaggi contenenti URL con collegamento ipertestuale o tramite cui vengono tentati trasferimenti di file.</span><span class="sxs-lookup"><span data-stu-id="93064-122">IIMFilter (Intelligent IM Filter) blocks messages that contain clickable URLs or that attempt to initiate file transfers.</span></span> <span data-ttu-id="93064-123">Verifica inoltre la versione client per conto del server.</span><span class="sxs-lookup"><span data-stu-id="93064-123">IIMFilter also checks the client version on behalf of the server.</span></span> <span data-ttu-id="93064-124">IIMFilter influisce sui trasferimenti di file avviati utilizzando Lync Server o Communicator.</span><span class="sxs-lookup"><span data-stu-id="93064-124">IIMFilter affects file transfers that are initiated by using either Lync Server or Communicator.</span></span> <span data-ttu-id="93064-125">Per impostazione predefinita, i collegamenti ipertestuali vengono disabilitati con l'aggiunta di un carattere di sottolineatura prima del primo carattere del collegamento.</span><span class="sxs-lookup"><span data-stu-id="93064-125">By default, clickable links are disabled by adding an underscore character before the first character of the link.</span></span> <span data-ttu-id="93064-126">Un amministratore può modificare questo comportamento in modo da bloccare il collegamento, nel qual caso i messaggi contenenti URL con collegamento ipertestuale o tramite cui vengono tentati trasferimenti di file vengono bloccati dal server e non possono raggiungere le destinazioni previste.</span><span class="sxs-lookup"><span data-stu-id="93064-126">An administrator can change this behavior so that the link is blocked, in which case messages that contain clickable URLs or that attempt to initiate a file transfer are blocked by the server from reaching their intended destinations.</span></span> <span data-ttu-id="93064-127">IIMFilter è installato in tutti i server che eseguono Lync Server, tranne i server proxy e i server di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="93064-127">IIMFilter is installed on all servers running Lync Server except Proxy Servers and Archiving Servers.</span></span>

  - <span data-ttu-id="93064-128">UserPinService viene utilizzato per verificare i numeri di identificazione personale (PIN) degli utenti per le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="93064-128">UserPinService is used to verify user personal identification numbers (PINs) for dial-in conferencing.</span></span>

  - <span data-ttu-id="93064-129">DefaultRouting è l'applicazione di routing predefinita per i server che eseguono Lync Server.</span><span class="sxs-lookup"><span data-stu-id="93064-129">DefaultRouting is the default routing application for servers running Lync Server.</span></span> <span data-ttu-id="93064-130">È disabilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="93064-130">It is enabled by default.</span></span> <span data-ttu-id="93064-131">L'applicazione di routing è installata su tutti i server Standard Edition e Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="93064-131">The routing application is installed on all Standard Edition and Enterprise Edition servers.</span></span>

  - <span data-ttu-id="93064-p109">ExumRouting esegue il routing delle chiamate al server di messaggistica unificata di Exchange Server appropriato. ExumRouting determina il server di messaggistica unificata di Exchange appropriato per il routing della chiamata quando è presente un nuovo messaggio vocale da recapitare. Gestisce inoltre altri aspetti relativi all'integrazione della messaggistica unificata di Exchange, ad esempio il routing all'operatore automatico e l'accesso del sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="93064-p109">ExumRouting routes calls to Exchange Server Unified Messaging (UM). ExumRouting determines the appropriate Exchange UM server to route the call to when there is a new voice mail message to deposit. ExumRouting also handles some other Exchange UM integration aspects, including routing to Auto Attendant and Subscriber Access.</span></span>

  - <span data-ttu-id="93064-p110">OutboundRouting determina il gateway che esegue il routing di una chiamata a un numero di telefono in base al numero composto e all'autorizzazione di composizione dell'utente. Gestisce inoltre un nuovo routing delle chiamate se un gateway non è in grado di elaborare una chiamata.</span><span class="sxs-lookup"><span data-stu-id="93064-p110">OutboundRouting determines the gateway that routes a call to a phone number according to the dialed number and the user’s dialing authorization. OutboundRouting also handles rerouting of calls if a gateway cannot process a call.</span></span>

  - <span data-ttu-id="93064-137">L'agente QoE riceve i rapporti relativi ai dati QoE (Quality of Experience) dagli endpoint tramite richieste SIP SERVICE e invia i dati alla coda di destinazione nel Monitoring Server o a consumer di terze parti con HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="93064-137">QoEAgent receives Quality of Experience (QoE) data reports from endpoints through SIP SERVICE requests, and sends the data to the destination queue on the Monitoring Server or to third-party consumers using HTTP POST.</span></span> <span data-ttu-id="93064-138">Per informazioni dettagliate, vedere [Deploying Monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span><span class="sxs-lookup"><span data-stu-id="93064-138">For details, see [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span></span>

  - <span data-ttu-id="93064-139">OutgoingFederation impone la convalida di federazione a livello di tenant per i messaggi indirizzati a una distribuzione esterna di destinazione.</span><span class="sxs-lookup"><span data-stu-id="93064-139">OutgoingFederation enforces tenant-level federation validation for messages going to a targeted external deployment.</span></span>

  - <span data-ttu-id="93064-140">AcpRouting opera come proxy e indirizza al gateway del provider di servizi di audioconferenza le richieste INVITE destinate a un provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="93064-140">AcpRouting proxies INVITE requests destined for the audio conferencing provider to the audio conferencing provider gateway.</span></span>

<span data-ttu-id="93064-141">Gli script eseguiti nei server perimetrali includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="93064-141">Scripts that run on Edge Servers include the following:</span></span>

  - <span data-ttu-id="93064-142">IIMFilter</span><span class="sxs-lookup"><span data-stu-id="93064-142">IIMFilter</span></span>

  - <span data-ttu-id="93064-143">OptionsHandler risponde alle richieste OPTIONS in arrivo con **200 OK** se la richiesta è destinata al server corrente.</span><span class="sxs-lookup"><span data-stu-id="93064-143">OptionsHandler responds to incoming OPTIONS requests with **200 OK** if the request is destined for the current server.</span></span> <span data-ttu-id="93064-144">Questo script viene utilizzato per la convalida della topologia.</span><span class="sxs-lookup"><span data-stu-id="93064-144">This is used for topology validation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="93064-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93064-145">See Also</span></span>


[<span data-ttu-id="93064-146">Abilitare o disabilitare un'applicazione server MSPL (Microsoft SIP Processing Language) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93064-146">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[<span data-ttu-id="93064-147">Contrassegnare un'applicazione Microsoft SIP Processing Language (MSPL) come critica o non critica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93064-147">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

