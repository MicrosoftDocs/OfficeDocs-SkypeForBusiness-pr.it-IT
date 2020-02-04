---
title: 'Lync Server 2013: Caratteristiche e funzionalità per dispositivi mobili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility features and capabilities
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48183457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e00274e62cc0fe7cf55c45e11a49670c7f1e6a0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758698"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a><span data-ttu-id="c7a47-102">Caratteristiche e funzionalità per dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7a47-102">Mobility features and capabilities in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7a47-103">_**Argomento Ultima modifica:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="c7a47-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="c7a47-104">La funzionalità mobilità introdotta negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 supporta la funzionalità Lync 2010 mobile e Lync 2013 per i client mobili.</span><span class="sxs-lookup"><span data-stu-id="c7a47-104">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2010 Mobile and Lync 2013 Mobile clients functionality.</span></span> <span data-ttu-id="c7a47-105">Quando si distribuisce il servizio di mobilità di Lync Server 2013, gli utenti possono usare i dispositivi mobili Apple iOS, Android e Windows Phone o Nokia Symbian per eseguire attività come l'invio e la ricezione di messaggi istantanei, la visualizzazione dei contatti e la visualizzazione della presenza.</span><span class="sxs-lookup"><span data-stu-id="c7a47-105">When you deploy the Lync Server 2013 Mobility Service, users can use supported Apple iOS, Android, and Windows Phone, or Nokia Symbian mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="c7a47-106">I dispositivi mobili supportano inoltre alcune funzionalità VoIP aziendale, ad esempio fare clic per partecipare a una conferenza, chiamare tramite lavoro, raggiungere un numero singolo, la segreteria telefonica e le chiamate perse.</span><span class="sxs-lookup"><span data-stu-id="c7a47-106">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="c7a47-107">Le nuove funzionalità introdotte negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 includono funzionalità VoIP (Voice over IP) e video (H. 264) per i partecipanti alla riunione.</span><span class="sxs-lookup"><span data-stu-id="c7a47-107">New features introduced in the Cumulative Updates for Lync Server 2013: February 2013 include Voice over IP (VoIP) capability and video (H.264) for meeting attendee.</span></span>

<span data-ttu-id="c7a47-108">La funzionalità mobilità introdotta negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 supporta la funzionalità client per dispositivi mobili Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="c7a47-108">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2013 Mobile client functionality.</span></span> <span data-ttu-id="c7a47-109">Gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 installare Unified Communications Web API o UCWA.</span><span class="sxs-lookup"><span data-stu-id="c7a47-109">The Cumulative Updates for Lync Server 2013: February 2013 install Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="c7a47-110">UCWA è il componente usato per i client mobili Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="c7a47-110">UCWA is the component used for Lync 2013 Mobile clients.</span></span> <span data-ttu-id="c7a47-111">In Lync Server 2013 viene usato MCX per i client mobili di Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="c7a47-111">In Lync Server 2013, Mcx is used for Lync 2010 Mobile clients.</span></span> <span data-ttu-id="c7a47-112">Aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 Introduzione a UCWA come nuovo punto di ingresso per i servizi di mobilità.</span><span class="sxs-lookup"><span data-stu-id="c7a47-112">Cumulative Updates for Lync Server 2013: February 2013 introduce UCWA as the new entry point for mobility services.</span></span> <span data-ttu-id="c7a47-113">Lync Server 2013 implementa contemporaneamente il servizio di mobilità (MCX), introdotto negli aggiornamenti cumulativi per Lync Server 2010: novembre 2011 e fornisce il supporto per Lync 2010 mobile.</span><span class="sxs-lookup"><span data-stu-id="c7a47-113">Lync Server 2013 concurrently implements the Mobility Service (Mcx), introduced in the Cumulative Updates for Lync Server 2010: November 2011, and provides support for Lync 2010 Mobile.</span></span> <span data-ttu-id="c7a47-114">Quando si distribuiscono gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013, gli utenti possono usare i dispositivi mobili supportati da Apple iOS, Android e Windows Phone per eseguire attività quali:</span><span class="sxs-lookup"><span data-stu-id="c7a47-114">When you deploy the Cumulative Updates for Lync Server 2013: February 2013, users can use supported Apple iOS, Android, and Windows Phone mobile devices to perform such activities as:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c7a47-115">Funzionalità supportate dal servizio di mobilità degli aggiornamenti cumulativi per Lync Server 2010: novembre 2011 sono notati con (MCX).</span><span class="sxs-lookup"><span data-stu-id="c7a47-115">Features supported by the Mobility Service from the Cumulative Updates for Lync Server 2010: November 2011 are noted with (Mcx).</span></span> <span data-ttu-id="c7a47-116">Tutte le caratteristiche elencate sono supportate da UCWA, introdotte negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.</span><span class="sxs-lookup"><span data-stu-id="c7a47-116">All listed features are supported by the UCWA, introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

  - <span data-ttu-id="c7a47-117">Inviare e ricevere messaggi istantanei (MCX)</span><span class="sxs-lookup"><span data-stu-id="c7a47-117">Send and receive instant messages (Mcx)</span></span>

  - <span data-ttu-id="c7a47-118">Visualizzazione presenza (MCX)</span><span class="sxs-lookup"><span data-stu-id="c7a47-118">View presence (Mcx)</span></span>

  - <span data-ttu-id="c7a47-119">Visualizzare i contatti (MCX)</span><span class="sxs-lookup"><span data-stu-id="c7a47-119">View contacts (Mcx)</span></span>

  - <span data-ttu-id="c7a47-120">Fare clic per partecipare a una conferenza (MCX)</span><span class="sxs-lookup"><span data-stu-id="c7a47-120">Click to join a conference (Mcx)</span></span>

  - <span data-ttu-id="c7a47-121">Chiamata tramite lavoro (MCX)</span><span class="sxs-lookup"><span data-stu-id="c7a47-121">Call via work (Mcx)</span></span>

  - <span data-ttu-id="c7a47-122">Portata numero singolo (MCX)</span><span class="sxs-lookup"><span data-stu-id="c7a47-122">Single number reach (Mcx)</span></span>

  - <span data-ttu-id="c7a47-123">Segreteria telefonica (MCX)</span><span class="sxs-lookup"><span data-stu-id="c7a47-123">Voice mail (Mcx)</span></span>

  - <span data-ttu-id="c7a47-124">Notifica delle chiamate perse (MCX)</span><span class="sxs-lookup"><span data-stu-id="c7a47-124">Missed call notification (Mcx)</span></span>

  - <span data-ttu-id="c7a47-125">Voice over IP (VoIP)</span><span class="sxs-lookup"><span data-stu-id="c7a47-125">Voice over IP (VoIP)</span></span>

  - <span data-ttu-id="c7a47-126">Video partecipanti (H. 264)</span><span class="sxs-lookup"><span data-stu-id="c7a47-126">Attendee video (H.264)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c7a47-127">Lync 2010 Mobile ha fornito un client per dispositivi Nokia Symbian.</span><span class="sxs-lookup"><span data-stu-id="c7a47-127">Lync 2010 Mobile provided a client for Nokia Symbian devices.</span></span> <span data-ttu-id="c7a47-128">Lync 2013 mobile non avrà un client per dispositivi Nokia basati su Symbian.</span><span class="sxs-lookup"><span data-stu-id="c7a47-128">Lync 2013 Mobile will not have a client for Nokia Symbian-based devices.</span></span>



</div>

<span data-ttu-id="c7a47-129">Gli utenti di Apple iPad avranno accesso a funzionalità avanzate.</span><span class="sxs-lookup"><span data-stu-id="c7a47-129">Apple iPad users will have access to enhanced capabilities.</span></span> <span data-ttu-id="c7a47-130">Dopo aver partecipato a una riunione usando la chiamata audio, un utente di iPad sarà in grado di visualizzare le presentazioni di Microsoft PowerPoint in una riunione, condividere applicazioni e desktop, visualizzare l'elenco dei partecipanti alla riunione e ricevere le notifiche di altri tipi di contenuto. che vengono condivisi all'interno della riunione.</span><span class="sxs-lookup"><span data-stu-id="c7a47-130">After joining a meeting by using audio call back, an iPad user will be able to view uploaded Microsoft PowerPoint presentations within a meeting, share applications and desktops, view the meeting participant list, and receive notifications of other content types that are being shared within the meeting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="c7a47-131">Con un numero a portata di mano, un utente riceve le chiamate su un telefono cellulare che sono state chiamate al numero di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c7a47-131">With single number reach, a user receives calls on a mobile phone that were dialed to the work number.</span></span> <span data-ttu-id="c7a47-132">Con la chiamata tramite il lavoro, l'utente inserisce una chiamata in uscita dal client mobile di Lync usando un numero di telefono dell'ufficio anziché il numero di cellulare.</span><span class="sxs-lookup"><span data-stu-id="c7a47-132">With Call via Work, the user places an outbound call from the Lync Mobile client by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="c7a47-133">Con chiamata in uscita, il client invia una richiesta a MCX o UCWA (in base alla versione per dispositivi mobili Lync) per effettuare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c7a47-133">With dial-out, the client sends a request to Mcx or UCWA (based on the Lync Mobile version) to make the call for them.</span></span> <span data-ttu-id="c7a47-134">Il server avvia la chiamata e quindi richiama l'utente sul telefono cellulare.</span><span class="sxs-lookup"><span data-stu-id="c7a47-134">The server initiates the call and then calls the user back on the mobile phone.</span></span> <span data-ttu-id="c7a47-135">Quando l'utente risponde, il server completa la chiamata componendo l'altra parte.</span><span class="sxs-lookup"><span data-stu-id="c7a47-135">When the user answers, the server completes the call by dialing the other party.</span></span> <span data-ttu-id="c7a47-136">Usando la chiamata tramite il lavoro, gli utenti possono mantenere l'identità del lavoro durante una chiamata, il che significa che il destinatario della chiamata non vede il numero di cellulare del chiamante e il chiamante evita l'incorrere in spese di chiamata in uscita.</span><span class="sxs-lookup"><span data-stu-id="c7a47-136">By using Call via Work, users can maintain their work identity during a call, which means that the call recipient does not see the caller's mobile number, and the caller avoids incurring outbound calling charges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c7a47-137">Non tutte le caratteristiche funzionano esattamente come in tutti i dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="c7a47-137">Not all features work exactly the same on all mobile devices.</span></span> <span data-ttu-id="c7a47-138">Per informazioni dettagliate sulle caratteristiche supportate nei dispositivi mobili, vedere le tabelle di <A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>confronto tra client mobili.</span><span class="sxs-lookup"><span data-stu-id="c7a47-138">For details about features supported on mobile devices, see the Mobile Client Comparison Tables at <A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>.</span></span> <span data-ttu-id="c7a47-139">Per informazioni dettagliate sui dispositivi e i sistemi operativi supportati, vedere gli argomenti relativi ai requisiti in <A href="lync-server-2013-planning-for-mobile-clients.md">pianificazione per i client mobili in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c7a47-139">For details about supported devices and operating systems, see the requirements topics under <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for mobile clients in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="c7a47-140">Quando si usa la funzionalità di individuazione automatica di Lync Server 2013, le applicazioni per dispositivi mobili possono individuare automaticamente i servizi Web di Lync Server 2013 senza richiedere agli utenti di immettere manualmente gli URL nelle impostazioni del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c7a47-140">When you use the Lync Server 2013 Autodiscover feature, mobile applications can automatically locate Lync Server 2013 Web Services without requiring users to manually enter the URLs in their device settings.</span></span> <span data-ttu-id="c7a47-141">È anche supportata l'immissione manuale di URL nelle impostazioni dei dispositivi mobili, principalmente per scopi di risoluzione.</span><span class="sxs-lookup"><span data-stu-id="c7a47-141">Manually entering URLs in mobile device settings is also supported, primarily for troubleshooting purposes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c7a47-142">MCX e UCWA sono servizi gratuiti ed entrambi sono distribuiti per supportare i client mobili Lync 2010 per dispositivi mobili e Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="c7a47-142">The Mcx and UCWA are complimentary services and both are deployed to support Lync 2010 Mobile and Lync 2013 Mobile clients.</span></span> <span data-ttu-id="c7a47-143">Lync 2013 mobile non sarà in grado di accedere alle distribuzioni di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c7a47-143">Lync 2013 Mobile will not be able to sign in to Lync Server 2010 deployments.</span></span> <span data-ttu-id="c7a47-144">Lync 2010 mobile e Lync 2013 mobile saranno in grado di usare una distribuzione di Lync Server 2013 con gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 applicato.</span><span class="sxs-lookup"><span data-stu-id="c7a47-144">Lync 2010 Mobile and Lync 2013 Mobile will be able to use a Lync Server 2013 deployment with the Cumulative Updates for Lync Server 2013: February 2013 applied.</span></span>



</div>

<span data-ttu-id="c7a47-145">La funzionalità mobilità supporta anche le *notifiche push* per i dispositivi mobili che non supportano le applicazioni in uso in background.</span><span class="sxs-lookup"><span data-stu-id="c7a47-145">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="c7a47-146">Una notifica push è una notifica inviata a un dispositivo mobile su un evento che si verifica mentre un'applicazione per dispositivi mobili è inattiva.</span><span class="sxs-lookup"><span data-stu-id="c7a47-146">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span> <span data-ttu-id="c7a47-147">Ad esempio, un invito alla messaggistica istantanea senza risposta può causare una notifica push.</span><span class="sxs-lookup"><span data-stu-id="c7a47-147">For example, a missed instant messaging (IM) invitation can result in a push notification.</span></span>

<span data-ttu-id="c7a47-148">MCX, UCWA, il servizio di individuazione automatica e il supporto per le notifiche push sono disponibili in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c7a47-148">Mcx, UCWA, Autodiscover Service, and support for push notifications are provided in Lync Server 2013.</span></span> <span data-ttu-id="c7a47-149">Le caratteristiche del client aggiornate, le funzionalità e l'uso di UCWA come punto di ingresso per la mobilità vengono introdotte negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.</span><span class="sxs-lookup"><span data-stu-id="c7a47-149">Updated client features, capabilities, and the use of UCWA as the mobility entry point are introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

