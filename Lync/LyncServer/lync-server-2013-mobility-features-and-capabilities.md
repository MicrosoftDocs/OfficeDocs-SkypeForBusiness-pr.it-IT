---
title: 'Lync Server 2013: caratteristiche e funzionalità per dispositivi mobili'
description: 'Lync Server 2013: caratteristiche e funzionalità per dispositivi mobili.'
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
ms.openlocfilehash: 20713145c18260f22d9635c34af291e9a7c5ea9c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550582"
---
# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a><span data-ttu-id="9781e-103">Funzionalità e funzionalità per dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9781e-103">Mobility features and capabilities in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9781e-104">_**Ultimo argomento modificato:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="9781e-104">_**Topic Last Modified:** 2013-02-19_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="9781e-105">La funzionalità di mobilità introdotta negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 supporta la funzionalità Lync 2010 mobile e Lync 2013 Mobile Clients.</span><span class="sxs-lookup"><span data-stu-id="9781e-105">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2010 Mobile and Lync 2013 Mobile clients functionality.</span></span> <span data-ttu-id="9781e-106">Quando si distribuisce il servizio di mobilità di Lync Server 2013, gli utenti possono utilizzare i dispositivi mobili Apple iOS, Android e Windows Phone o Nokia Symbian per eseguire attività quali l'invio e la ricezione di messaggi istantanei, la visualizzazione dei contatti e la visualizzazione della presenza.</span><span class="sxs-lookup"><span data-stu-id="9781e-106">When you deploy the Lync Server 2013 Mobility Service, users can use supported Apple iOS, Android, and Windows Phone, or Nokia Symbian mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="9781e-107">I dispositivi mobili inoltre supportano alcune funzionalità di VoIP aziendale, tra cui la possibilità di partecipare a una conferenza mediante clic del mouse, la chiamata tramite ufficio, il numero unico, la segreteria telefonica e le chiamate senza risposta.</span><span class="sxs-lookup"><span data-stu-id="9781e-107">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="9781e-108">Nuove funzionalità introdotte negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 includono funzionalità Voice over IP (VoIP) e video (H. 264) per la riunione dei partecipanti.</span><span class="sxs-lookup"><span data-stu-id="9781e-108">New features introduced in the Cumulative Updates for Lync Server 2013: February 2013 include Voice over IP (VoIP) capability and video (H.264) for meeting attendee.</span></span>

<span data-ttu-id="9781e-109">La funzionalità di mobilità introdotta negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 supporta la funzionalità client per dispositivi mobili Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="9781e-109">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2013 Mobile client functionality.</span></span> <span data-ttu-id="9781e-110">Gli aggiornamenti cumulativi per Lync Server 2013: February 2013 install Unified Communications Web API, o UCWA.</span><span class="sxs-lookup"><span data-stu-id="9781e-110">The Cumulative Updates for Lync Server 2013: February 2013 install Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="9781e-111">UCWA è il componente utilizzato per i client mobili di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="9781e-111">UCWA is the component used for Lync 2013 Mobile clients.</span></span> <span data-ttu-id="9781e-112">In Lync Server 2013, MCX viene utilizzato per i client mobili di Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="9781e-112">In Lync Server 2013, Mcx is used for Lync 2010 Mobile clients.</span></span> <span data-ttu-id="9781e-113">Aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 introdurre UCWA come nuovo punto di ingresso per i servizi per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="9781e-113">Cumulative Updates for Lync Server 2013: February 2013 introduce UCWA as the new entry point for mobility services.</span></span> <span data-ttu-id="9781e-114">Lync Server 2013 implementa contemporaneamente il servizio per dispositivi mobili (MCX), introdotto negli aggiornamenti cumulativi per Lync Server 2010: novembre 2011 e fornisce il supporto per Lync 2010 mobile.</span><span class="sxs-lookup"><span data-stu-id="9781e-114">Lync Server 2013 concurrently implements the Mobility Service (Mcx), introduced in the Cumulative Updates for Lync Server 2010: November 2011, and provides support for Lync 2010 Mobile.</span></span> <span data-ttu-id="9781e-115">Quando si distribuiscono gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013, gli utenti possono utilizzare i dispositivi mobili Apple iOS, Android e Windows Phone supportati per eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="9781e-115">When you deploy the Cumulative Updates for Lync Server 2013: February 2013, users can use supported Apple iOS, Android, and Windows Phone mobile devices to perform such activities as:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9781e-116">Le funzionalità supportate dal servizio per dispositivi mobili dagli aggiornamenti cumulativi per Lync Server 2010: novembre 2011 sono note con (MCX).</span><span class="sxs-lookup"><span data-stu-id="9781e-116">Features supported by the Mobility Service from the Cumulative Updates for Lync Server 2010: November 2011 are noted with (Mcx).</span></span> <span data-ttu-id="9781e-117">Tutte le funzionalità elencate sono supportate da UCWA, introdotte negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.</span><span class="sxs-lookup"><span data-stu-id="9781e-117">All listed features are supported by the UCWA, introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

  - <span data-ttu-id="9781e-118">Inviare e ricevere messaggi istantanei (MCX)</span><span class="sxs-lookup"><span data-stu-id="9781e-118">Send and receive instant messages (Mcx)</span></span>

  - <span data-ttu-id="9781e-119">Visualizzazione presenza (MCX)</span><span class="sxs-lookup"><span data-stu-id="9781e-119">View presence (Mcx)</span></span>

  - <span data-ttu-id="9781e-120">Visualizza contatti (MCX)</span><span class="sxs-lookup"><span data-stu-id="9781e-120">View contacts (Mcx)</span></span>

  - <span data-ttu-id="9781e-121">Fare clic per partecipare a una conferenza (MCX)</span><span class="sxs-lookup"><span data-stu-id="9781e-121">Click to join a conference (Mcx)</span></span>

  - <span data-ttu-id="9781e-122">Chiamata tramite lavoro (MCX)</span><span class="sxs-lookup"><span data-stu-id="9781e-122">Call via work (Mcx)</span></span>

  - <span data-ttu-id="9781e-123">Portata numeri singola (MCX)</span><span class="sxs-lookup"><span data-stu-id="9781e-123">Single number reach (Mcx)</span></span>

  - <span data-ttu-id="9781e-124">Segreteria telefonica (MCX)</span><span class="sxs-lookup"><span data-stu-id="9781e-124">Voice mail (Mcx)</span></span>

  - <span data-ttu-id="9781e-125">Notifica di chiamata senza risposta (MCX)</span><span class="sxs-lookup"><span data-stu-id="9781e-125">Missed call notification (Mcx)</span></span>

  - <span data-ttu-id="9781e-126">VoIP (Voice over IP)</span><span class="sxs-lookup"><span data-stu-id="9781e-126">Voice over IP (VoIP)</span></span>

  - <span data-ttu-id="9781e-127">Video partecipante (H. 264)</span><span class="sxs-lookup"><span data-stu-id="9781e-127">Attendee video (H.264)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9781e-128">Lync 2010 Mobile ha fornito un client per i dispositivi Nokia Symbian.</span><span class="sxs-lookup"><span data-stu-id="9781e-128">Lync 2010 Mobile provided a client for Nokia Symbian devices.</span></span> <span data-ttu-id="9781e-129">Lync 2013 mobile non avrà un client per dispositivi basati su Nokia Symbian.</span><span class="sxs-lookup"><span data-stu-id="9781e-129">Lync 2013 Mobile will not have a client for Nokia Symbian-based devices.</span></span>



</div>

<span data-ttu-id="9781e-130">Gli utenti di Apple iPad avranno accesso a funzionalità avanzate.</span><span class="sxs-lookup"><span data-stu-id="9781e-130">Apple iPad users will have access to enhanced capabilities.</span></span> <span data-ttu-id="9781e-131">Dopo aver partecipato a una riunione tramite la chiamata audio, un utente iPad sarà in grado di visualizzare le presentazioni di Microsoft PowerPoint caricate all'interno di una riunione, condividere applicazioni e desktop, visualizzare l'elenco dei partecipanti alla riunione e ricevere notifiche di altri tipi di contenuto che vengono condivisi all'interno della riunione.</span><span class="sxs-lookup"><span data-stu-id="9781e-131">After joining a meeting by using audio call back, an iPad user will be able to view uploaded Microsoft PowerPoint presentations within a meeting, share applications and desktops, view the meeting participant list, and receive notifications of other content types that are being shared within the meeting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="9781e-132">Con il numero unico, un utente riceve sul telefono cellulare le chiamate effettuate al suo numero dell'ufficio.</span><span class="sxs-lookup"><span data-stu-id="9781e-132">With single number reach, a user receives calls on a mobile phone that were dialed to the work number.</span></span> <span data-ttu-id="9781e-133">Con la chiamata tramite il lavoro, l'utente inserisce una chiamata in uscita dal client per dispositivi mobili Lync utilizzando un numero di telefono di lavoro invece del numero di cellulare.</span><span class="sxs-lookup"><span data-stu-id="9781e-133">With Call via Work, the user places an outbound call from the Lync Mobile client by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="9781e-134">Con accesso esterno, il client invia una richiesta a MCX o UCWA (in base alla versione Lync mobile) per effettuare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9781e-134">With dial-out, the client sends a request to Mcx or UCWA (based on the Lync Mobile version) to make the call for them.</span></span> <span data-ttu-id="9781e-135">Il server perciò avvia la chiamata e quindi richiama l'utente sul cellulare.</span><span class="sxs-lookup"><span data-stu-id="9781e-135">The server initiates the call and then calls the user back on the mobile phone.</span></span> <span data-ttu-id="9781e-136">Quando l'utente risponde, il server completa la chiamata componendo il numero dell'altra parte.</span><span class="sxs-lookup"><span data-stu-id="9781e-136">When the user answers, the server completes the call by dialing the other party.</span></span> <span data-ttu-id="9781e-137">Mediante la chiamata tramite ufficio, gli utenti possono mantenere la loro identità di lavoro durante una chiamata, pertanto il destinatario non vedrà il numero di cellulare del chiamante e a quest'ultimo non verranno addebitati i costi della chiamata in uscita.</span><span class="sxs-lookup"><span data-stu-id="9781e-137">By using Call via Work, users can maintain their work identity during a call, which means that the call recipient does not see the caller's mobile number, and the caller avoids incurring outbound calling charges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="9781e-138">Non tutte le funzionalità hanno esattamente lo stesso comportamento su tutti i dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="9781e-138">Not all features work exactly the same on all mobile devices.</span></span> <span data-ttu-id="9781e-139">Per informazioni dettagliate sulle funzionalità supportate nei dispositivi mobili, vedere le tabelle di confronto dei client mobili in <A href="https://go.microsoft.com/fwlink/p/?linkid=234777">https://go.microsoft.com/fwlink/p/?LinkId=234777</A> .</span><span class="sxs-lookup"><span data-stu-id="9781e-139">For details about features supported on mobile devices, see the Mobile Client Comparison Tables at <A href="https://go.microsoft.com/fwlink/p/?linkid=234777">https://go.microsoft.com/fwlink/p/?LinkId=234777</A>.</span></span> <span data-ttu-id="9781e-140">Per informazioni dettagliate sui dispositivi e i sistemi operativi supportati, vedere gli argomenti relativi ai requisiti in <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for Mobile Clients in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9781e-140">For details about supported devices and operating systems, see the requirements topics under <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for mobile clients in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="9781e-141">Quando si utilizza la funzionalità di individuazione automatica di Lync Server 2013, le applicazioni per dispositivi mobili possono individuare automaticamente i servizi Web di Lync Server 2013 senza richiedere agli utenti di immettere manualmente gli URL nelle impostazioni dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="9781e-141">When you use the Lync Server 2013 Autodiscover feature, mobile applications can automatically locate Lync Server 2013 Web Services without requiring users to manually enter the URLs in their device settings.</span></span> <span data-ttu-id="9781e-142">Tale immissione manuale degli URL è comunque supportata, principalmente per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="9781e-142">Manually entering URLs in mobile device settings is also supported, primarily for troubleshooting purposes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9781e-143">MCX e UCWA sono servizi gratuiti ed entrambi sono distribuiti per supportare i client mobili Lync 2010 mobile e Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="9781e-143">The Mcx and UCWA are complimentary services and both are deployed to support Lync 2010 Mobile and Lync 2013 Mobile clients.</span></span> <span data-ttu-id="9781e-144">Lync 2013 mobile non sarà in grado di accedere alle distribuzioni di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9781e-144">Lync 2013 Mobile will not be able to sign in to Lync Server 2010 deployments.</span></span> <span data-ttu-id="9781e-145">Lync 2010 mobile e Lync 2013 mobile saranno in grado di utilizzare una distribuzione di Lync Server 2013 con gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 applicato.</span><span class="sxs-lookup"><span data-stu-id="9781e-145">Lync 2010 Mobile and Lync 2013 Mobile will be able to use a Lync Server 2013 deployment with the Cumulative Updates for Lync Server 2013: February 2013 applied.</span></span>



</div>

<span data-ttu-id="9781e-146">La funzionalità per dispositivi mobili inoltre supporta le *notifiche push* per i dispositivi mobili che non supportano le applicazioni eseguite in background.</span><span class="sxs-lookup"><span data-stu-id="9781e-146">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="9781e-147">Una notifica push è una notifica inviata a un dispositivo mobile relativamente a un evento che si verifica mentre un'applicazione per dispositivi mobili non è attiva.</span><span class="sxs-lookup"><span data-stu-id="9781e-147">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span> <span data-ttu-id="9781e-148">Ad esempio, un invito a messaggistica istantanea mancante può comportare una notifica push.</span><span class="sxs-lookup"><span data-stu-id="9781e-148">For example, a missed instant messaging (IM) invitation can result in a push notification.</span></span>

<span data-ttu-id="9781e-149">MCX, UCWA, il servizio di individuazione automatica e il supporto per le notifiche push sono disponibili in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9781e-149">Mcx, UCWA, Autodiscover Service, and support for push notifications are provided in Lync Server 2013.</span></span> <span data-ttu-id="9781e-150">Le funzionalità e le funzionalità del client aggiornate e l'utilizzo di UCWA come punto di ingresso per dispositivi mobili sono stati introdotti negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.</span><span class="sxs-lookup"><span data-stu-id="9781e-150">Updated client features, capabilities, and the use of UCWA as the mobility entry point are introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

