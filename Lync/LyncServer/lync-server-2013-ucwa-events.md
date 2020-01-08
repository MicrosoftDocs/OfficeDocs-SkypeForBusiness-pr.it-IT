---
title: 'Lync Server 2013: Eventi UCWA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0671b51e5fbd4b5f072676855d9e8f5201b3e04
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="a4b9e-102">Eventi UCWA in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4b9e-102">UCWA events in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4b9e-103">_**Argomento Ultima modifica:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="a4b9e-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="a4b9e-104">Lync Server 2013 usa la Unified Communications Web API (UCWA) per diversi scopi, dall'accesso a Microsoft Exchange per la ricerca di contatti all'aggiornamento della presenza per i client mobili.</span><span class="sxs-lookup"><span data-stu-id="a4b9e-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="a4b9e-105">UCWA scriverà i record del comportamento operativo come tipi di evento informativo, di avviso e di errore.</span><span class="sxs-lookup"><span data-stu-id="a4b9e-105">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="a4b9e-106">La tabella seguente descrive gli eventi che possono essere scritti dai componenti UCWA.</span><span class="sxs-lookup"><span data-stu-id="a4b9e-106">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4b9e-107">ID evento</span><span class="sxs-lookup"><span data-stu-id="a4b9e-107">Event ID</span></span></th>
<th><span data-ttu-id="a4b9e-108">Tipo di evento</span><span class="sxs-lookup"><span data-stu-id="a4b9e-108">Event Type</span></span></th>
<th><span data-ttu-id="a4b9e-109">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="a4b9e-109">Summary</span></span></th>
<th><span data-ttu-id="a4b9e-110">Causa e risoluzione</span><span class="sxs-lookup"><span data-stu-id="a4b9e-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4b9e-111">20001</span><span class="sxs-lookup"><span data-stu-id="a4b9e-111">20001</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-112">Informativo</span><span class="sxs-lookup"><span data-stu-id="a4b9e-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-113">UCWA inizializzato</span><span class="sxs-lookup"><span data-stu-id="a4b9e-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-114">N/D</span><span class="sxs-lookup"><span data-stu-id="a4b9e-114">N/A</span></span></p>
<p><span data-ttu-id="a4b9e-115">N/D</span><span class="sxs-lookup"><span data-stu-id="a4b9e-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4b9e-116">20002</span><span class="sxs-lookup"><span data-stu-id="a4b9e-116">20002</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-117">Errore</span><span class="sxs-lookup"><span data-stu-id="a4b9e-117">Error</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-118">UCWA ha rilevato un'eccezione imprevista durante l'inizializzazione</span><span class="sxs-lookup"><span data-stu-id="a4b9e-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-119">Si è verificato un errore imprevisto durante l'inizializzazione</span><span class="sxs-lookup"><span data-stu-id="a4b9e-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="a4b9e-120">Esaminare i dettagli dell'eccezione nella voce del log eventi associata per determinare la causa possibile</span><span class="sxs-lookup"><span data-stu-id="a4b9e-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4b9e-121">20003</span><span class="sxs-lookup"><span data-stu-id="a4b9e-121">20003</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-122">Errore</span><span class="sxs-lookup"><span data-stu-id="a4b9e-122">Error</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-123">UCWA ha rilevato un'eccezione non gestita</span><span class="sxs-lookup"><span data-stu-id="a4b9e-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-124">È stata generata un'eccezione non gestita</span><span class="sxs-lookup"><span data-stu-id="a4b9e-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="a4b9e-125">Riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="a4b9e-125">Restart the server.</span></span> <span data-ttu-id="a4b9e-126">Se il problema persiste, contattare il supporto tecnico</span><span class="sxs-lookup"><span data-stu-id="a4b9e-126">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4b9e-127">20004</span><span class="sxs-lookup"><span data-stu-id="a4b9e-127">20004</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-128">Errore</span><span class="sxs-lookup"><span data-stu-id="a4b9e-128">Error</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-129">Non è possibile accedere a Exchange per la foto HD</span><span class="sxs-lookup"><span data-stu-id="a4b9e-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-130">La connessione a Exchange non è disponibile</span><span class="sxs-lookup"><span data-stu-id="a4b9e-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="a4b9e-131">Verificare che la connessione a Exchange sia disponibile</span><span class="sxs-lookup"><span data-stu-id="a4b9e-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4b9e-132">20005</span><span class="sxs-lookup"><span data-stu-id="a4b9e-132">20005</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-133">Informativo</span><span class="sxs-lookup"><span data-stu-id="a4b9e-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-134">Recupero della mancata accesso a Exchange per la foto HD</span><span class="sxs-lookup"><span data-stu-id="a4b9e-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-135">N/D</span><span class="sxs-lookup"><span data-stu-id="a4b9e-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4b9e-136">20006</span><span class="sxs-lookup"><span data-stu-id="a4b9e-136">20006</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-137">Errore</span><span class="sxs-lookup"><span data-stu-id="a4b9e-137">Error</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-138">Non è possibile accedere a Exchange per la ricerca di contatti</span><span class="sxs-lookup"><span data-stu-id="a4b9e-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-139">La connessione a Exchange non è disponibile</span><span class="sxs-lookup"><span data-stu-id="a4b9e-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="a4b9e-140">Verificare che la connessione a Exchange sia disponibile</span><span class="sxs-lookup"><span data-stu-id="a4b9e-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4b9e-141">20007</span><span class="sxs-lookup"><span data-stu-id="a4b9e-141">20007</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-142">Informativo</span><span class="sxs-lookup"><span data-stu-id="a4b9e-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-143">Recuperato dalla mancata ricerca del contatto in Exchange</span><span class="sxs-lookup"><span data-stu-id="a4b9e-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-144">N/D</span><span class="sxs-lookup"><span data-stu-id="a4b9e-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4b9e-145">20008</span><span class="sxs-lookup"><span data-stu-id="a4b9e-145">20008</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-146">Avviso</span><span class="sxs-lookup"><span data-stu-id="a4b9e-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-147">Tentativo di sottoscrizione di un numero maggiore di abbonamenti a presenza consentiti per applicazione</span><span class="sxs-lookup"><span data-stu-id="a4b9e-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-148">Tentativo di sottoscrizione di un numero maggiore di abbonamenti a presenza consentiti per applicazione</span><span class="sxs-lookup"><span data-stu-id="a4b9e-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="a4b9e-149">Controllare i client per gli abbonamenti non necessari</span><span class="sxs-lookup"><span data-stu-id="a4b9e-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4b9e-150">20009</span><span class="sxs-lookup"><span data-stu-id="a4b9e-150">20009</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-151">Avviso</span><span class="sxs-lookup"><span data-stu-id="a4b9e-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-152">Tentativo di sottoscrizione di un numero maggiore di abbonamenti di presenza consentiti per batch</span><span class="sxs-lookup"><span data-stu-id="a4b9e-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-153">Tentativo di sottoscrizione di un numero maggiore di abbonamenti di presenza consentiti per batch</span><span class="sxs-lookup"><span data-stu-id="a4b9e-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="a4b9e-154">Controllare i client per gli abbonamenti non necessari</span><span class="sxs-lookup"><span data-stu-id="a4b9e-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4b9e-155">20010</span><span class="sxs-lookup"><span data-stu-id="a4b9e-155">20010</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-156">Errore</span><span class="sxs-lookup"><span data-stu-id="a4b9e-156">Error</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-157">Non è possibile recuperare i dati in banda</span><span class="sxs-lookup"><span data-stu-id="a4b9e-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-158">Non è possibile recuperare i dati in banda</span><span class="sxs-lookup"><span data-stu-id="a4b9e-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="a4b9e-159">Se il problema persiste, contattare il supporto tecnico</span><span class="sxs-lookup"><span data-stu-id="a4b9e-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4b9e-160">20011</span><span class="sxs-lookup"><span data-stu-id="a4b9e-160">20011</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-161">Errore</span><span class="sxs-lookup"><span data-stu-id="a4b9e-161">Error</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-162">Non è possibile sottoscrivere la presenza</span><span class="sxs-lookup"><span data-stu-id="a4b9e-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-163">Non è possibile sottoscrivere la presenza</span><span class="sxs-lookup"><span data-stu-id="a4b9e-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="a4b9e-164">Se il problema persiste, contattare il supporto tecnico</span><span class="sxs-lookup"><span data-stu-id="a4b9e-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4b9e-165">20012</span><span class="sxs-lookup"><span data-stu-id="a4b9e-165">20012</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-166">Errore</span><span class="sxs-lookup"><span data-stu-id="a4b9e-166">Error</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-167">Impossibile registrare l'endpoint</span><span class="sxs-lookup"><span data-stu-id="a4b9e-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-168">Impossibile registrare l'endpoint</span><span class="sxs-lookup"><span data-stu-id="a4b9e-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="a4b9e-169">Se il problema persiste, contattare il supporto tecnico</span><span class="sxs-lookup"><span data-stu-id="a4b9e-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4b9e-170">20013</span><span class="sxs-lookup"><span data-stu-id="a4b9e-170">20013</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-171">Errore</span><span class="sxs-lookup"><span data-stu-id="a4b9e-171">Error</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-172">La MCU di messaggistica istantanea non è disponibile</span><span class="sxs-lookup"><span data-stu-id="a4b9e-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-173">La MCU di messaggistica istantanea non è disponibile</span><span class="sxs-lookup"><span data-stu-id="a4b9e-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="a4b9e-174">Verificare se è in corso una MCU di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="a4b9e-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4b9e-175">20014</span><span class="sxs-lookup"><span data-stu-id="a4b9e-175">20014</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-176">Informativo</span><span class="sxs-lookup"><span data-stu-id="a4b9e-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-177">Ripristino della mancata connessione alla MCU istantanea</span><span class="sxs-lookup"><span data-stu-id="a4b9e-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-178">N/D</span><span class="sxs-lookup"><span data-stu-id="a4b9e-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4b9e-179">20015</span><span class="sxs-lookup"><span data-stu-id="a4b9e-179">20015</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-180">Errore</span><span class="sxs-lookup"><span data-stu-id="a4b9e-180">Error</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-181">MCU AV non disponibile</span><span class="sxs-lookup"><span data-stu-id="a4b9e-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-182">MCU AV non disponibile</span><span class="sxs-lookup"><span data-stu-id="a4b9e-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="a4b9e-183">Verificare se è in corso una MCU AV</span><span class="sxs-lookup"><span data-stu-id="a4b9e-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4b9e-184">20016</span><span class="sxs-lookup"><span data-stu-id="a4b9e-184">20016</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-185">Informativo</span><span class="sxs-lookup"><span data-stu-id="a4b9e-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-186">Recuperato dalla mancata connessione alla MCU AV</span><span class="sxs-lookup"><span data-stu-id="a4b9e-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-187">N/D</span><span class="sxs-lookup"><span data-stu-id="a4b9e-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4b9e-188">20017</span><span class="sxs-lookup"><span data-stu-id="a4b9e-188">20017</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-189">Errore</span><span class="sxs-lookup"><span data-stu-id="a4b9e-189">Error</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-190">Poiché MCU non è disponibile</span><span class="sxs-lookup"><span data-stu-id="a4b9e-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-191">Poiché MCU non è disponibile</span><span class="sxs-lookup"><span data-stu-id="a4b9e-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="a4b9e-192">Verificare l'eventuale funzionamento di MCU</span><span class="sxs-lookup"><span data-stu-id="a4b9e-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4b9e-193">20018</span><span class="sxs-lookup"><span data-stu-id="a4b9e-193">20018</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-194">Informativo</span><span class="sxs-lookup"><span data-stu-id="a4b9e-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-195">Recuperata dalla mancata connessione a come MCU</span><span class="sxs-lookup"><span data-stu-id="a4b9e-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-196">N/D</span><span class="sxs-lookup"><span data-stu-id="a4b9e-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4b9e-197">20019</span><span class="sxs-lookup"><span data-stu-id="a4b9e-197">20019</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-198">Errore</span><span class="sxs-lookup"><span data-stu-id="a4b9e-198">Error</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-199">MCU dati non disponibile</span><span class="sxs-lookup"><span data-stu-id="a4b9e-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-200">MCU dati non disponibile</span><span class="sxs-lookup"><span data-stu-id="a4b9e-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="a4b9e-201">Verificare se è in corso l'uso di MCU dati</span><span class="sxs-lookup"><span data-stu-id="a4b9e-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4b9e-202">20020</span><span class="sxs-lookup"><span data-stu-id="a4b9e-202">20020</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-203">Informativo</span><span class="sxs-lookup"><span data-stu-id="a4b9e-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-204">Recupero dalla mancata connessione a MCU dati</span><span class="sxs-lookup"><span data-stu-id="a4b9e-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-205">N/D</span><span class="sxs-lookup"><span data-stu-id="a4b9e-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4b9e-206">20021</span><span class="sxs-lookup"><span data-stu-id="a4b9e-206">20021</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-207">Errore</span><span class="sxs-lookup"><span data-stu-id="a4b9e-207">Error</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-208">Non è possibile partecipare a una MCU istantanea</span><span class="sxs-lookup"><span data-stu-id="a4b9e-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-209">Non è possibile partecipare a una MCU istantanea</span><span class="sxs-lookup"><span data-stu-id="a4b9e-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="a4b9e-210">Verificare se è in corso una MCU di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="a4b9e-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4b9e-211">20022</span><span class="sxs-lookup"><span data-stu-id="a4b9e-211">20022</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-212">Errore</span><span class="sxs-lookup"><span data-stu-id="a4b9e-212">Error</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-213">Non è possibile partecipare a MCU AV</span><span class="sxs-lookup"><span data-stu-id="a4b9e-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-214">Non è possibile partecipare a MCU AV</span><span class="sxs-lookup"><span data-stu-id="a4b9e-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="a4b9e-215">Verificare se è in corso una MCU AV</span><span class="sxs-lookup"><span data-stu-id="a4b9e-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4b9e-216">20023</span><span class="sxs-lookup"><span data-stu-id="a4b9e-216">20023</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-217">Errore</span><span class="sxs-lookup"><span data-stu-id="a4b9e-217">Error</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-218">Non è possibile partecipare come MCU</span><span class="sxs-lookup"><span data-stu-id="a4b9e-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-219">Non è possibile partecipare come MCU</span><span class="sxs-lookup"><span data-stu-id="a4b9e-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="a4b9e-220">Verificare l'eventuale funzionamento di MCU</span><span class="sxs-lookup"><span data-stu-id="a4b9e-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4b9e-221">20024</span><span class="sxs-lookup"><span data-stu-id="a4b9e-221">20024</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-222">Errore</span><span class="sxs-lookup"><span data-stu-id="a4b9e-222">Error</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-223">Non è possibile partecipare a MCU dati</span><span class="sxs-lookup"><span data-stu-id="a4b9e-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-224">Non è possibile partecipare a MCU dati</span><span class="sxs-lookup"><span data-stu-id="a4b9e-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="a4b9e-225">Verificare se è in corso l'uso di MCU dati</span><span class="sxs-lookup"><span data-stu-id="a4b9e-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4b9e-226">20025</span><span class="sxs-lookup"><span data-stu-id="a4b9e-226">20025</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-227">Errore</span><span class="sxs-lookup"><span data-stu-id="a4b9e-227">Error</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-228">Non è possibile accedere a Active Directory per la foto</span><span class="sxs-lookup"><span data-stu-id="a4b9e-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-229">La connessione a Active Directory non è disponibile</span><span class="sxs-lookup"><span data-stu-id="a4b9e-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="a4b9e-230">Verificare che la connessione a Active Directory sia disponibile</span><span class="sxs-lookup"><span data-stu-id="a4b9e-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4b9e-231">20026</span><span class="sxs-lookup"><span data-stu-id="a4b9e-231">20026</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-232">Informativo</span><span class="sxs-lookup"><span data-stu-id="a4b9e-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-233">Recuperati dal mancato accesso a Active Directory per la foto</span><span class="sxs-lookup"><span data-stu-id="a4b9e-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-234">N/D</span><span class="sxs-lookup"><span data-stu-id="a4b9e-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4b9e-235">20027</span><span class="sxs-lookup"><span data-stu-id="a4b9e-235">20027</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-236">Avviso</span><span class="sxs-lookup"><span data-stu-id="a4b9e-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-237">Non è possibile deserializzare</span><span class="sxs-lookup"><span data-stu-id="a4b9e-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="a4b9e-238">Non è possibile deserializzare</span><span class="sxs-lookup"><span data-stu-id="a4b9e-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="a4b9e-239">Se il problema persiste, contattare il supporto tecnico</span><span class="sxs-lookup"><span data-stu-id="a4b9e-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

