---
title: Visualizzare le applicazioni server MSPL (Microsoft SIP Processing Language)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View Microsoft SIP Processing Language (MSPL) server applications
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182575(v=OCS.15)
ms:contentKeyID: 48185202
ms.date: 09/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2a8aea4b412d2d744c42d659d2414a93c8435e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980767"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a><span data-ttu-id="ca96f-102">Visualizzare le applicazioni server MSPL (Microsoft SIP Processing Language) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca96f-102">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca96f-103">_**Argomento Ultima modifica:** 2014-09-26_</span><span class="sxs-lookup"><span data-stu-id="ca96f-103">_**Topic Last Modified:** 2014-09-26_</span></span>

<span data-ttu-id="ca96f-104">Un'applicazione server MSPL (Microsoft SIP Processing Language) è un'applicazione di sola scrittura che usa un linguaggio di scripting anziché l'API Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="ca96f-104">A Microsoft SIP Processing Language (MSPL) server application is a script-only application that uses a scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="ca96f-105">MSPL offre un controllo più granulare sui comportamenti di filtro e proxy, oltre a una funzionalità per l'invio di messaggi specifici alle applicazioni SIP basate sulle transazioni.</span><span class="sxs-lookup"><span data-stu-id="ca96f-105">MSPL provides more granular control over filtering and proxy behaviors, in addition to a facility for dispatching specific messages to transaction-based SIP applications.</span></span> <span data-ttu-id="ca96f-106">MSPL viene usato in modo specifico per filtrare e instradare i messaggi SIP.</span><span class="sxs-lookup"><span data-stu-id="ca96f-106">MSPL is used specifically for filtering and routing SIP messages.</span></span> <span data-ttu-id="ca96f-107">Le applicazioni MSPL vengono eseguite nello stesso processo del modulo UserServices, mentre un programma basato sull'API Lync 2010 viene eseguito in un processo separato.</span><span class="sxs-lookup"><span data-stu-id="ca96f-107">MSPL applications run in the same process as the UserServices module, while a program that is based on the Lync 2010 API runs in a separate process.</span></span>

<span data-ttu-id="ca96f-108">È possibile usare la pagina dell' **applicazione server** nel gruppo **topologia** del pannello di controllo di Lync Server per visualizzare un elenco di applicazioni server MSPL eseguite nei server front-end nell'ambiente Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ca96f-108">You can use the **Server Application** page in the **Topology** group of Lync Server Control Panel to see a list of MSPL server applications that run on Front End Servers in your Lync Server 2013 environment.</span></span> <span data-ttu-id="ca96f-109">L'elenco Mostra gli script disponibili per ogni pool, nonché se sono abilitati o critici.</span><span class="sxs-lookup"><span data-stu-id="ca96f-109">The list shows the scripts that are available for each pool, as well as whether they are enabled or critical.</span></span> <span data-ttu-id="ca96f-110">Gli script vengono eseguiti nell'ordine in cui sono elencati.</span><span class="sxs-lookup"><span data-stu-id="ca96f-110">The scripts run in the order they are listed.</span></span>

<span data-ttu-id="ca96f-111">Questi script includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="ca96f-111">These scripts include the following:</span></span>

  - <span data-ttu-id="ca96f-112">ClientVersionFilter fornisce all'amministratore un modo per specificare la versione dei client supportati da un pool.</span><span class="sxs-lookup"><span data-stu-id="ca96f-112">ClientVersionFilter provides the administrator with a way to specify the version of clients that are supported by a pool.</span></span> <span data-ttu-id="ca96f-113">Il filtro della versione client controlla la versione client e può impedire al client di eseguire l'accesso o presentare l'utente con un messaggio che indica che sta usando un client non supportato.</span><span class="sxs-lookup"><span data-stu-id="ca96f-113">The client version filter checks the client version and can either prevent the client from logging on or present the user with a message that indicates he or she is using a client that is not supported.</span></span> <span data-ttu-id="ca96f-114">Il filtro della versione client può anche essere configurato per visualizzare un messaggio per l'utente che contiene l'URL dell'ultima versione scaricabile del client.</span><span class="sxs-lookup"><span data-stu-id="ca96f-114">The client version filter can also be configured to display a message to the user that contains the URL of the latest downloadable version of the client.</span></span>

  - <span data-ttu-id="ca96f-115">TranslationService converte un numero che un utente compone in un numero E. 164 in base alle regole di normalizzazione definite dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="ca96f-115">TranslationService translates a number that a user dials to an E.164 number according to the normalization rules defined by the administrator.</span></span> <span data-ttu-id="ca96f-116">Per informazioni dettagliate, vedere [regole di traduzione in Lync Server 2013](lync-server-2013-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="ca96f-116">For details, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md).</span></span>

  - <span data-ttu-id="ca96f-117">IncomingFederation impone la convalida della Federazione a livello di tenant per i messaggi in arrivo e tra tenant provenienti da distribuzioni esterne.</span><span class="sxs-lookup"><span data-stu-id="ca96f-117">IncomingFederation enforces tenant-level federation validation for inter-tenant and incoming messages from external deployments.</span></span>

  - <span data-ttu-id="ca96f-118">UserServices è il componente di registrazione, presenza e conferenza SIP di un server front-end.</span><span class="sxs-lookup"><span data-stu-id="ca96f-118">UserServices is the SIP Registrar, presence, and conferencing component of a Front End Server.</span></span> <span data-ttu-id="ca96f-119">Offre funzionalità di messaggistica istantanea, presenza e conferenza strettamente integrate basate sul proxy SIP.</span><span class="sxs-lookup"><span data-stu-id="ca96f-119">It provides closely integrated IM, presence, and conferencing features built on top of the SIP Proxy.</span></span>

  - <span data-ttu-id="ca96f-120">InterClusterRouting è responsabile per il routing delle chiamate al pool di registrar principale del destinatario.</span><span class="sxs-lookup"><span data-stu-id="ca96f-120">InterClusterRouting is responsible for routing calls to the callee’s primary Registrar pool.</span></span> <span data-ttu-id="ca96f-121">Per informazioni dettagliate, vedere [componenti VoIP di front end server per Lync server 2013](lync-server-2013-front-end-server-voip-components.md).</span><span class="sxs-lookup"><span data-stu-id="ca96f-121">For details, see [Front End Server VoIP components for Lync Server 2013](lync-server-2013-front-end-server-voip-components.md).</span></span>

  - <span data-ttu-id="ca96f-122">IIMFilter (Intelligent IM Filter) blocca i messaggi che contengono URL selezionabili o che tentano di avviare i trasferimenti di file.</span><span class="sxs-lookup"><span data-stu-id="ca96f-122">IIMFilter (Intelligent IM Filter) blocks messages that contain clickable URLs or that attempt to initiate file transfers.</span></span> <span data-ttu-id="ca96f-123">IIMFilter controlla anche la versione client per conto del server.</span><span class="sxs-lookup"><span data-stu-id="ca96f-123">IIMFilter also checks the client version on behalf of the server.</span></span> <span data-ttu-id="ca96f-124">IIMFilter influisce sui trasferimenti di file avviati tramite Lync Server o Communicator.</span><span class="sxs-lookup"><span data-stu-id="ca96f-124">IIMFilter affects file transfers that are initiated by using either Lync Server or Communicator.</span></span> <span data-ttu-id="ca96f-125">Per impostazione predefinita, i collegamenti selezionabili vengono disabilitati aggiungendo un carattere di sottolineatura prima del primo carattere del collegamento.</span><span class="sxs-lookup"><span data-stu-id="ca96f-125">By default, clickable links are disabled by adding an underscore character before the first character of the link.</span></span> <span data-ttu-id="ca96f-126">Un amministratore può modificare questo comportamento in modo che il collegamento sia bloccato, in questo caso i messaggi che contengono URL selezionabili o che tentano di avviare un trasferimento di file vengono bloccati dal server per raggiungere le destinazioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="ca96f-126">An administrator can change this behavior so that the link is blocked, in which case messages that contain clickable URLs or that attempt to initiate a file transfer are blocked by the server from reaching their intended destinations.</span></span> <span data-ttu-id="ca96f-127">IIMFilter è installato in tutti i server che utilizzano Lync Server eccetto i server proxy e i server di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="ca96f-127">IIMFilter is installed on all servers running Lync Server except Proxy Servers and Archiving Servers.</span></span>

  - <span data-ttu-id="ca96f-128">UserPinService viene usato per verificare i pin (User Personal Identification Numbers) per i servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="ca96f-128">UserPinService is used to verify user personal identification numbers (PINs) for dial-in conferencing.</span></span>

  - <span data-ttu-id="ca96f-129">DefaultRouting è l'applicazione di routing predefinita per i server che utilizzano Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ca96f-129">DefaultRouting is the default routing application for servers running Lync Server.</span></span> <span data-ttu-id="ca96f-130">È abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ca96f-130">It is enabled by default.</span></span> <span data-ttu-id="ca96f-131">L'applicazione di routing è installata in tutti i server Standard Edition e Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="ca96f-131">The routing application is installed on all Standard Edition and Enterprise Edition servers.</span></span>

  - <span data-ttu-id="ca96f-132">ExumRouting instrada le chiamate alla messaggistica unificata di Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="ca96f-132">ExumRouting routes calls to Exchange Server Unified Messaging (UM).</span></span> <span data-ttu-id="ca96f-133">ExumRouting determina il server di messaggistica unificata di Exchange appropriato per instradare la chiamata quando viene depositato un nuovo messaggio di segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="ca96f-133">ExumRouting determines the appropriate Exchange UM server to route the call to when there is a new voice mail message to deposit.</span></span> <span data-ttu-id="ca96f-134">ExumRouting gestisce anche altri aspetti di integrazione della messaggistica unificata di Exchange, incluso il routing per l'operatore automatico e l'accesso sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="ca96f-134">ExumRouting also handles some other Exchange UM integration aspects, including routing to Auto Attendant and Subscriber Access.</span></span>

  - <span data-ttu-id="ca96f-135">OutboundRouting determina il gateway che instrada una chiamata a un numero di telefono in base al numero selezionato e all'autorizzazione di chiamata dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ca96f-135">OutboundRouting determines the gateway that routes a call to a phone number according to the dialed number and the user’s dialing authorization.</span></span> <span data-ttu-id="ca96f-136">OutboundRouting gestisce anche il reinstradamento delle chiamate se un gateway non è in grado di elaborare una chiamata.</span><span class="sxs-lookup"><span data-stu-id="ca96f-136">OutboundRouting also handles rerouting of calls if a gateway cannot process a call.</span></span>

  - <span data-ttu-id="ca96f-137">QoEAgent riceve i report di dati QoE (Quality of Experience) dagli endpoint tramite le richieste di servizio SIP e invia i dati alla coda di destinazione nel server di monitoraggio o a utenti di terze parti che usano HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="ca96f-137">QoEAgent receives Quality of Experience (QoE) data reports from endpoints through SIP SERVICE requests, and sends the data to the destination queue on the Monitoring Server or to third-party consumers using HTTP POST.</span></span> <span data-ttu-id="ca96f-138">Per informazioni dettagliate, vedere [distribuzione del monitoraggio in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span><span class="sxs-lookup"><span data-stu-id="ca96f-138">For details, see [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span></span>

  - <span data-ttu-id="ca96f-139">OutgoingFederation impone la convalida della Federazione a livello di tenant per i messaggi che vanno a una distribuzione esterna di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ca96f-139">OutgoingFederation enforces tenant-level federation validation for messages going to a targeted external deployment.</span></span>

  - <span data-ttu-id="ca96f-140">AcpRouting proxy invita le richieste destinate al provider di servizi di audioconferenza al gateway del provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="ca96f-140">AcpRouting proxies INVITE requests destined for the audio conferencing provider to the audio conferencing provider gateway.</span></span>

<span data-ttu-id="ca96f-141">Gli script eseguiti in Edge Server includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="ca96f-141">Scripts that run on Edge Servers include the following:</span></span>

  - <span data-ttu-id="ca96f-142">IIMFilter</span><span class="sxs-lookup"><span data-stu-id="ca96f-142">IIMFilter</span></span>

  - <span data-ttu-id="ca96f-143">OptionsHandler risponde alle richieste di opzioni in arrivo con **200 OK** se la richiesta è destinata al server corrente.</span><span class="sxs-lookup"><span data-stu-id="ca96f-143">OptionsHandler responds to incoming OPTIONS requests with **200 OK** if the request is destined for the current server.</span></span> <span data-ttu-id="ca96f-144">Viene usato per la convalida della topologia.</span><span class="sxs-lookup"><span data-stu-id="ca96f-144">This is used for topology validation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="ca96f-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca96f-145">See Also</span></span>


[<span data-ttu-id="ca96f-146">Abilitare o disabilitare un'applicazione server MSPL (Microsoft SIP Processing Language) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca96f-146">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[<span data-ttu-id="ca96f-147">Contrassegnare un'applicazione MSPL (Microsoft SIP Processing Language) come critica o non critica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca96f-147">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

