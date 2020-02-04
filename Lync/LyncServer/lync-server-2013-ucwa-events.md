---
title: 'Lync Server 2013: Eventi UCWA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5063aca74fe3454569a2b2309be584a4ca11d13
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744856"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="fcc6b-102">Eventi UCWA in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fcc6b-102">UCWA events in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fcc6b-103">_**Argomento Ultima modifica:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="fcc6b-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="fcc6b-104">Lync Server 2013 usa la Unified Communications Web API (UCWA) per diversi scopi, dall'accesso a Microsoft Exchange per la ricerca di contatti all'aggiornamento della presenza per i client mobili.</span><span class="sxs-lookup"><span data-stu-id="fcc6b-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="fcc6b-105">UCWA scriverà i record del comportamento operativo come tipi di evento informativo, di avviso e di errore.</span><span class="sxs-lookup"><span data-stu-id="fcc6b-105">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="fcc6b-106">La tabella seguente descrive gli eventi che possono essere scritti dai componenti UCWA.</span><span class="sxs-lookup"><span data-stu-id="fcc6b-106">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fcc6b-107">ID evento</span><span class="sxs-lookup"><span data-stu-id="fcc6b-107">Event ID</span></span></th>
<th><span data-ttu-id="fcc6b-108">Tipo di evento</span><span class="sxs-lookup"><span data-stu-id="fcc6b-108">Event Type</span></span></th>
<th><span data-ttu-id="fcc6b-109">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="fcc6b-109">Summary</span></span></th>
<th><span data-ttu-id="fcc6b-110">Causa e risoluzione</span><span class="sxs-lookup"><span data-stu-id="fcc6b-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fcc6b-111">20001</span><span class="sxs-lookup"><span data-stu-id="fcc6b-111">20001</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-112">Informativo</span><span class="sxs-lookup"><span data-stu-id="fcc6b-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-113">UCWA inizializzato</span><span class="sxs-lookup"><span data-stu-id="fcc6b-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-114">N/D</span><span class="sxs-lookup"><span data-stu-id="fcc6b-114">N/A</span></span></p>
<p><span data-ttu-id="fcc6b-115">N/D</span><span class="sxs-lookup"><span data-stu-id="fcc6b-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcc6b-116">20002</span><span class="sxs-lookup"><span data-stu-id="fcc6b-116">20002</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-117">Errore</span><span class="sxs-lookup"><span data-stu-id="fcc6b-117">Error</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-118">UCWA ha rilevato un'eccezione imprevista durante l'inizializzazione</span><span class="sxs-lookup"><span data-stu-id="fcc6b-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-119">Si è verificato un errore imprevisto durante l'inizializzazione</span><span class="sxs-lookup"><span data-stu-id="fcc6b-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="fcc6b-120">Esaminare i dettagli dell'eccezione nella voce del log eventi associata per determinare la causa possibile</span><span class="sxs-lookup"><span data-stu-id="fcc6b-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcc6b-121">20003</span><span class="sxs-lookup"><span data-stu-id="fcc6b-121">20003</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-122">Errore</span><span class="sxs-lookup"><span data-stu-id="fcc6b-122">Error</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-123">UCWA ha rilevato un'eccezione non gestita</span><span class="sxs-lookup"><span data-stu-id="fcc6b-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-124">È stata generata un'eccezione non gestita</span><span class="sxs-lookup"><span data-stu-id="fcc6b-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="fcc6b-125">Riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="fcc6b-125">Restart the server.</span></span> <span data-ttu-id="fcc6b-126">Se il problema persiste, contattare il supporto tecnico</span><span class="sxs-lookup"><span data-stu-id="fcc6b-126">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcc6b-127">20004</span><span class="sxs-lookup"><span data-stu-id="fcc6b-127">20004</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-128">Errore</span><span class="sxs-lookup"><span data-stu-id="fcc6b-128">Error</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-129">Non è possibile accedere a Exchange per la foto HD</span><span class="sxs-lookup"><span data-stu-id="fcc6b-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-130">La connessione a Exchange non è disponibile</span><span class="sxs-lookup"><span data-stu-id="fcc6b-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="fcc6b-131">Verificare che la connessione a Exchange sia disponibile</span><span class="sxs-lookup"><span data-stu-id="fcc6b-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcc6b-132">20005</span><span class="sxs-lookup"><span data-stu-id="fcc6b-132">20005</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-133">Informativo</span><span class="sxs-lookup"><span data-stu-id="fcc6b-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-134">Recupero della mancata accesso a Exchange per la foto HD</span><span class="sxs-lookup"><span data-stu-id="fcc6b-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-135">N/D</span><span class="sxs-lookup"><span data-stu-id="fcc6b-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcc6b-136">20006</span><span class="sxs-lookup"><span data-stu-id="fcc6b-136">20006</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-137">Errore</span><span class="sxs-lookup"><span data-stu-id="fcc6b-137">Error</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-138">Non è possibile accedere a Exchange per la ricerca di contatti</span><span class="sxs-lookup"><span data-stu-id="fcc6b-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-139">La connessione a Exchange non è disponibile</span><span class="sxs-lookup"><span data-stu-id="fcc6b-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="fcc6b-140">Verificare che la connessione a Exchange sia disponibile</span><span class="sxs-lookup"><span data-stu-id="fcc6b-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcc6b-141">20007</span><span class="sxs-lookup"><span data-stu-id="fcc6b-141">20007</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-142">Informativo</span><span class="sxs-lookup"><span data-stu-id="fcc6b-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-143">Recuperato dalla mancata ricerca del contatto in Exchange</span><span class="sxs-lookup"><span data-stu-id="fcc6b-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-144">N/D</span><span class="sxs-lookup"><span data-stu-id="fcc6b-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcc6b-145">20008</span><span class="sxs-lookup"><span data-stu-id="fcc6b-145">20008</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-146">Avviso</span><span class="sxs-lookup"><span data-stu-id="fcc6b-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-147">Tentativo di sottoscrizione di un numero maggiore di abbonamenti a presenza consentiti per applicazione</span><span class="sxs-lookup"><span data-stu-id="fcc6b-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-148">Tentativo di sottoscrizione di un numero maggiore di abbonamenti a presenza consentiti per applicazione</span><span class="sxs-lookup"><span data-stu-id="fcc6b-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="fcc6b-149">Controllare i client per gli abbonamenti non necessari</span><span class="sxs-lookup"><span data-stu-id="fcc6b-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcc6b-150">20009</span><span class="sxs-lookup"><span data-stu-id="fcc6b-150">20009</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-151">Avviso</span><span class="sxs-lookup"><span data-stu-id="fcc6b-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-152">Tentativo di sottoscrizione di un numero maggiore di abbonamenti di presenza consentiti per batch</span><span class="sxs-lookup"><span data-stu-id="fcc6b-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-153">Tentativo di sottoscrizione di un numero maggiore di abbonamenti di presenza consentiti per batch</span><span class="sxs-lookup"><span data-stu-id="fcc6b-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="fcc6b-154">Controllare i client per gli abbonamenti non necessari</span><span class="sxs-lookup"><span data-stu-id="fcc6b-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcc6b-155">20010</span><span class="sxs-lookup"><span data-stu-id="fcc6b-155">20010</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-156">Errore</span><span class="sxs-lookup"><span data-stu-id="fcc6b-156">Error</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-157">Non è possibile recuperare i dati in banda</span><span class="sxs-lookup"><span data-stu-id="fcc6b-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-158">Non è possibile recuperare i dati in banda</span><span class="sxs-lookup"><span data-stu-id="fcc6b-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="fcc6b-159">Se il problema persiste, contattare il supporto tecnico</span><span class="sxs-lookup"><span data-stu-id="fcc6b-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcc6b-160">20011</span><span class="sxs-lookup"><span data-stu-id="fcc6b-160">20011</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-161">Errore</span><span class="sxs-lookup"><span data-stu-id="fcc6b-161">Error</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-162">Non è possibile sottoscrivere la presenza</span><span class="sxs-lookup"><span data-stu-id="fcc6b-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-163">Non è possibile sottoscrivere la presenza</span><span class="sxs-lookup"><span data-stu-id="fcc6b-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="fcc6b-164">Se il problema persiste, contattare il supporto tecnico</span><span class="sxs-lookup"><span data-stu-id="fcc6b-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcc6b-165">20012</span><span class="sxs-lookup"><span data-stu-id="fcc6b-165">20012</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-166">Errore</span><span class="sxs-lookup"><span data-stu-id="fcc6b-166">Error</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-167">Impossibile registrare l'endpoint</span><span class="sxs-lookup"><span data-stu-id="fcc6b-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-168">Impossibile registrare l'endpoint</span><span class="sxs-lookup"><span data-stu-id="fcc6b-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="fcc6b-169">Se il problema persiste, contattare il supporto tecnico</span><span class="sxs-lookup"><span data-stu-id="fcc6b-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcc6b-170">20013</span><span class="sxs-lookup"><span data-stu-id="fcc6b-170">20013</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-171">Errore</span><span class="sxs-lookup"><span data-stu-id="fcc6b-171">Error</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-172">La MCU di messaggistica istantanea non è disponibile</span><span class="sxs-lookup"><span data-stu-id="fcc6b-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-173">La MCU di messaggistica istantanea non è disponibile</span><span class="sxs-lookup"><span data-stu-id="fcc6b-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="fcc6b-174">Verificare se è in corso una MCU di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="fcc6b-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcc6b-175">20014</span><span class="sxs-lookup"><span data-stu-id="fcc6b-175">20014</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-176">Informativo</span><span class="sxs-lookup"><span data-stu-id="fcc6b-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-177">Ripristino della mancata connessione alla MCU istantanea</span><span class="sxs-lookup"><span data-stu-id="fcc6b-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-178">N/D</span><span class="sxs-lookup"><span data-stu-id="fcc6b-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcc6b-179">20015</span><span class="sxs-lookup"><span data-stu-id="fcc6b-179">20015</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-180">Errore</span><span class="sxs-lookup"><span data-stu-id="fcc6b-180">Error</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-181">MCU AV non disponibile</span><span class="sxs-lookup"><span data-stu-id="fcc6b-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-182">MCU AV non disponibile</span><span class="sxs-lookup"><span data-stu-id="fcc6b-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="fcc6b-183">Verificare se è in corso una MCU AV</span><span class="sxs-lookup"><span data-stu-id="fcc6b-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcc6b-184">20016</span><span class="sxs-lookup"><span data-stu-id="fcc6b-184">20016</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-185">Informativo</span><span class="sxs-lookup"><span data-stu-id="fcc6b-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-186">Recuperato dalla mancata connessione alla MCU AV</span><span class="sxs-lookup"><span data-stu-id="fcc6b-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-187">N/D</span><span class="sxs-lookup"><span data-stu-id="fcc6b-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcc6b-188">20017</span><span class="sxs-lookup"><span data-stu-id="fcc6b-188">20017</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-189">Errore</span><span class="sxs-lookup"><span data-stu-id="fcc6b-189">Error</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-190">Poiché MCU non è disponibile</span><span class="sxs-lookup"><span data-stu-id="fcc6b-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-191">Poiché MCU non è disponibile</span><span class="sxs-lookup"><span data-stu-id="fcc6b-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="fcc6b-192">Verificare l'eventuale funzionamento di MCU</span><span class="sxs-lookup"><span data-stu-id="fcc6b-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcc6b-193">20018</span><span class="sxs-lookup"><span data-stu-id="fcc6b-193">20018</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-194">Informativo</span><span class="sxs-lookup"><span data-stu-id="fcc6b-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-195">Recuperata dalla mancata connessione a come MCU</span><span class="sxs-lookup"><span data-stu-id="fcc6b-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-196">N/D</span><span class="sxs-lookup"><span data-stu-id="fcc6b-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcc6b-197">20019</span><span class="sxs-lookup"><span data-stu-id="fcc6b-197">20019</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-198">Errore</span><span class="sxs-lookup"><span data-stu-id="fcc6b-198">Error</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-199">MCU dati non disponibile</span><span class="sxs-lookup"><span data-stu-id="fcc6b-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-200">MCU dati non disponibile</span><span class="sxs-lookup"><span data-stu-id="fcc6b-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="fcc6b-201">Verificare se è in corso l'uso di MCU dati</span><span class="sxs-lookup"><span data-stu-id="fcc6b-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcc6b-202">20020</span><span class="sxs-lookup"><span data-stu-id="fcc6b-202">20020</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-203">Informativo</span><span class="sxs-lookup"><span data-stu-id="fcc6b-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-204">Recupero dalla mancata connessione a MCU dati</span><span class="sxs-lookup"><span data-stu-id="fcc6b-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-205">N/D</span><span class="sxs-lookup"><span data-stu-id="fcc6b-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcc6b-206">20021</span><span class="sxs-lookup"><span data-stu-id="fcc6b-206">20021</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-207">Errore</span><span class="sxs-lookup"><span data-stu-id="fcc6b-207">Error</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-208">Non è possibile partecipare a una MCU istantanea</span><span class="sxs-lookup"><span data-stu-id="fcc6b-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-209">Non è possibile partecipare a una MCU istantanea</span><span class="sxs-lookup"><span data-stu-id="fcc6b-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="fcc6b-210">Verificare se è in corso una MCU di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="fcc6b-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcc6b-211">20022</span><span class="sxs-lookup"><span data-stu-id="fcc6b-211">20022</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-212">Errore</span><span class="sxs-lookup"><span data-stu-id="fcc6b-212">Error</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-213">Non è possibile partecipare a MCU AV</span><span class="sxs-lookup"><span data-stu-id="fcc6b-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-214">Non è possibile partecipare a MCU AV</span><span class="sxs-lookup"><span data-stu-id="fcc6b-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="fcc6b-215">Verificare se è in corso una MCU AV</span><span class="sxs-lookup"><span data-stu-id="fcc6b-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcc6b-216">20023</span><span class="sxs-lookup"><span data-stu-id="fcc6b-216">20023</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-217">Errore</span><span class="sxs-lookup"><span data-stu-id="fcc6b-217">Error</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-218">Non è possibile partecipare come MCU</span><span class="sxs-lookup"><span data-stu-id="fcc6b-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-219">Non è possibile partecipare come MCU</span><span class="sxs-lookup"><span data-stu-id="fcc6b-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="fcc6b-220">Verificare l'eventuale funzionamento di MCU</span><span class="sxs-lookup"><span data-stu-id="fcc6b-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcc6b-221">20024</span><span class="sxs-lookup"><span data-stu-id="fcc6b-221">20024</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-222">Errore</span><span class="sxs-lookup"><span data-stu-id="fcc6b-222">Error</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-223">Non è possibile partecipare a MCU dati</span><span class="sxs-lookup"><span data-stu-id="fcc6b-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-224">Non è possibile partecipare a MCU dati</span><span class="sxs-lookup"><span data-stu-id="fcc6b-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="fcc6b-225">Verificare se è in corso l'uso di MCU dati</span><span class="sxs-lookup"><span data-stu-id="fcc6b-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcc6b-226">20025</span><span class="sxs-lookup"><span data-stu-id="fcc6b-226">20025</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-227">Errore</span><span class="sxs-lookup"><span data-stu-id="fcc6b-227">Error</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-228">Non è possibile accedere a Active Directory per la foto</span><span class="sxs-lookup"><span data-stu-id="fcc6b-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-229">La connessione a Active Directory non è disponibile</span><span class="sxs-lookup"><span data-stu-id="fcc6b-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="fcc6b-230">Verificare che la connessione a Active Directory sia disponibile</span><span class="sxs-lookup"><span data-stu-id="fcc6b-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcc6b-231">20026</span><span class="sxs-lookup"><span data-stu-id="fcc6b-231">20026</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-232">Informativo</span><span class="sxs-lookup"><span data-stu-id="fcc6b-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-233">Recuperati dal mancato accesso a Active Directory per la foto</span><span class="sxs-lookup"><span data-stu-id="fcc6b-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-234">N/D</span><span class="sxs-lookup"><span data-stu-id="fcc6b-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcc6b-235">20027</span><span class="sxs-lookup"><span data-stu-id="fcc6b-235">20027</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-236">Avviso</span><span class="sxs-lookup"><span data-stu-id="fcc6b-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-237">Non è possibile deserializzare</span><span class="sxs-lookup"><span data-stu-id="fcc6b-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="fcc6b-238">Non è possibile deserializzare</span><span class="sxs-lookup"><span data-stu-id="fcc6b-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="fcc6b-239">Se il problema persiste, contattare il supporto tecnico</span><span class="sxs-lookup"><span data-stu-id="fcc6b-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

