---
title: 'Lync Server 2013: Eventi UCWA'
description: 'Lync Server 2013: eventi di UCWA.'
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
ms.openlocfilehash: 8104ce9c7533350f40ce194e1cde205bc3692792
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548852"
---
# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="4fef5-103">Eventi UCWA in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fef5-103">UCWA events in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fef5-104">_**Ultimo argomento modificato:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="4fef5-104">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="4fef5-105">Lync Server 2013 utilizza Unified Communications Web API (UCWA) per una serie di scopi, dall'accesso a Microsoft Exchange per le ricerche dei contatti per l'aggiornamento della presenza per i client mobili.</span><span class="sxs-lookup"><span data-stu-id="4fef5-105">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="4fef5-106">UCWA scriverà i record del comportamento operativo come tipi di evento informativi, di avviso e di errore.</span><span class="sxs-lookup"><span data-stu-id="4fef5-106">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="4fef5-107">Nella tabella seguente vengono descritti gli eventi che possono essere scritti dai componenti di UCWA.</span><span class="sxs-lookup"><span data-stu-id="4fef5-107">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4fef5-108">ID evento</span><span class="sxs-lookup"><span data-stu-id="4fef5-108">Event ID</span></span></th>
<th><span data-ttu-id="4fef5-109">Tipo evento</span><span class="sxs-lookup"><span data-stu-id="4fef5-109">Event Type</span></span></th>
<th><span data-ttu-id="4fef5-110">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="4fef5-110">Summary</span></span></th>
<th><span data-ttu-id="4fef5-111">Causa e risoluzione</span><span class="sxs-lookup"><span data-stu-id="4fef5-111">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4fef5-112">20001</span><span class="sxs-lookup"><span data-stu-id="4fef5-112">20001</span></span></p></td>
<td><p><span data-ttu-id="4fef5-113">Informativo</span><span class="sxs-lookup"><span data-stu-id="4fef5-113">Informational</span></span></p></td>
<td><p><span data-ttu-id="4fef5-114">UCWA inizializzato</span><span class="sxs-lookup"><span data-stu-id="4fef5-114">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="4fef5-115">N/D</span><span class="sxs-lookup"><span data-stu-id="4fef5-115">N/A</span></span></p>
<p><span data-ttu-id="4fef5-116">N/D</span><span class="sxs-lookup"><span data-stu-id="4fef5-116">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fef5-117">20002</span><span class="sxs-lookup"><span data-stu-id="4fef5-117">20002</span></span></p></td>
<td><p><span data-ttu-id="4fef5-118">Error</span><span class="sxs-lookup"><span data-stu-id="4fef5-118">Error</span></span></p></td>
<td><p><span data-ttu-id="4fef5-119">UCWA ha rilevato un'eccezione imprevista durante l'inizializzazione</span><span class="sxs-lookup"><span data-stu-id="4fef5-119">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="4fef5-120">Si è verificato un errore imprevisto durante l'inizializzazione</span><span class="sxs-lookup"><span data-stu-id="4fef5-120">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="4fef5-121">Esaminare i dettagli dell'eccezione nella voce del registro eventi associata per determinare la causa possibile</span><span class="sxs-lookup"><span data-stu-id="4fef5-121">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4fef5-122">20003</span><span class="sxs-lookup"><span data-stu-id="4fef5-122">20003</span></span></p></td>
<td><p><span data-ttu-id="4fef5-123">Error</span><span class="sxs-lookup"><span data-stu-id="4fef5-123">Error</span></span></p></td>
<td><p><span data-ttu-id="4fef5-124">UCWA ha rilevato un'eccezione non gestita</span><span class="sxs-lookup"><span data-stu-id="4fef5-124">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="4fef5-125">Si è verificata un'eccezione non gestita</span><span class="sxs-lookup"><span data-stu-id="4fef5-125">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="4fef5-126">Riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="4fef5-126">Restart the server.</span></span> <span data-ttu-id="4fef5-127">Se il problema persiste, contattare il supporto del prodotto</span><span class="sxs-lookup"><span data-stu-id="4fef5-127">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fef5-128">20004</span><span class="sxs-lookup"><span data-stu-id="4fef5-128">20004</span></span></p></td>
<td><p><span data-ttu-id="4fef5-129">Error</span><span class="sxs-lookup"><span data-stu-id="4fef5-129">Error</span></span></p></td>
<td><p><span data-ttu-id="4fef5-130">Non è possibile accedere a Exchange per la foto HD</span><span class="sxs-lookup"><span data-stu-id="4fef5-130">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="4fef5-131">La connessione a Exchange non è disponibile</span><span class="sxs-lookup"><span data-stu-id="4fef5-131">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="4fef5-132">Verificare che la connessione a Exchange sia disponibile</span><span class="sxs-lookup"><span data-stu-id="4fef5-132">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4fef5-133">20005</span><span class="sxs-lookup"><span data-stu-id="4fef5-133">20005</span></span></p></td>
<td><p><span data-ttu-id="4fef5-134">Informativo</span><span class="sxs-lookup"><span data-stu-id="4fef5-134">Informational</span></span></p></td>
<td><p><span data-ttu-id="4fef5-135">Recuperato dalla mancata accesso a Exchange per la foto HD</span><span class="sxs-lookup"><span data-stu-id="4fef5-135">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="4fef5-136">N/D</span><span class="sxs-lookup"><span data-stu-id="4fef5-136">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fef5-137">20006</span><span class="sxs-lookup"><span data-stu-id="4fef5-137">20006</span></span></p></td>
<td><p><span data-ttu-id="4fef5-138">Error</span><span class="sxs-lookup"><span data-stu-id="4fef5-138">Error</span></span></p></td>
<td><p><span data-ttu-id="4fef5-139">Non è possibile accedere a Exchange per la ricerca dei contatti</span><span class="sxs-lookup"><span data-stu-id="4fef5-139">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="4fef5-140">La connessione a Exchange non è disponibile</span><span class="sxs-lookup"><span data-stu-id="4fef5-140">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="4fef5-141">Verificare che la connessione a Exchange sia disponibile</span><span class="sxs-lookup"><span data-stu-id="4fef5-141">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4fef5-142">20007</span><span class="sxs-lookup"><span data-stu-id="4fef5-142">20007</span></span></p></td>
<td><p><span data-ttu-id="4fef5-143">Informativo</span><span class="sxs-lookup"><span data-stu-id="4fef5-143">Informational</span></span></p></td>
<td><p><span data-ttu-id="4fef5-144">Recuperato dalla mancata ricerca del contatto in Exchange</span><span class="sxs-lookup"><span data-stu-id="4fef5-144">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="4fef5-145">N/D</span><span class="sxs-lookup"><span data-stu-id="4fef5-145">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fef5-146">20008</span><span class="sxs-lookup"><span data-stu-id="4fef5-146">20008</span></span></p></td>
<td><p><span data-ttu-id="4fef5-147">Avviso</span><span class="sxs-lookup"><span data-stu-id="4fef5-147">Warning</span></span></p></td>
<td><p><span data-ttu-id="4fef5-148">Tentativo di sottoscrizione di un numero maggiore di sottoscrizioni di presenza consentite per applicazione</span><span class="sxs-lookup"><span data-stu-id="4fef5-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="4fef5-149">Tentativo di sottoscrizione di un numero maggiore di sottoscrizioni di presenza consentite per applicazione</span><span class="sxs-lookup"><span data-stu-id="4fef5-149">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="4fef5-150">Controllare i client per le sottoscrizioni non necessarie</span><span class="sxs-lookup"><span data-stu-id="4fef5-150">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4fef5-151">20009</span><span class="sxs-lookup"><span data-stu-id="4fef5-151">20009</span></span></p></td>
<td><p><span data-ttu-id="4fef5-152">Avviso</span><span class="sxs-lookup"><span data-stu-id="4fef5-152">Warning</span></span></p></td>
<td><p><span data-ttu-id="4fef5-153">Tentativo di sottoscrizione di un numero maggiore di sottoscrizioni di presenza consentite per batch</span><span class="sxs-lookup"><span data-stu-id="4fef5-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="4fef5-154">Tentativo di sottoscrizione di un numero maggiore di sottoscrizioni di presenza consentite per batch</span><span class="sxs-lookup"><span data-stu-id="4fef5-154">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="4fef5-155">Controllare i client per le sottoscrizioni non necessarie</span><span class="sxs-lookup"><span data-stu-id="4fef5-155">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fef5-156">20010</span><span class="sxs-lookup"><span data-stu-id="4fef5-156">20010</span></span></p></td>
<td><p><span data-ttu-id="4fef5-157">Error</span><span class="sxs-lookup"><span data-stu-id="4fef5-157">Error</span></span></p></td>
<td><p><span data-ttu-id="4fef5-158">Non è in grado di recuperare i dati inband</span><span class="sxs-lookup"><span data-stu-id="4fef5-158">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="4fef5-159">Non è in grado di recuperare i dati inband</span><span class="sxs-lookup"><span data-stu-id="4fef5-159">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="4fef5-160">Se il problema persiste, contattare il supporto del prodotto</span><span class="sxs-lookup"><span data-stu-id="4fef5-160">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4fef5-161">20011</span><span class="sxs-lookup"><span data-stu-id="4fef5-161">20011</span></span></p></td>
<td><p><span data-ttu-id="4fef5-162">Error</span><span class="sxs-lookup"><span data-stu-id="4fef5-162">Error</span></span></p></td>
<td><p><span data-ttu-id="4fef5-163">Non è possibile sottoscrivere la presenza</span><span class="sxs-lookup"><span data-stu-id="4fef5-163">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="4fef5-164">Non è possibile sottoscrivere la presenza</span><span class="sxs-lookup"><span data-stu-id="4fef5-164">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="4fef5-165">Se il problema persiste, contattare il supporto del prodotto</span><span class="sxs-lookup"><span data-stu-id="4fef5-165">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fef5-166">20012</span><span class="sxs-lookup"><span data-stu-id="4fef5-166">20012</span></span></p></td>
<td><p><span data-ttu-id="4fef5-167">Error</span><span class="sxs-lookup"><span data-stu-id="4fef5-167">Error</span></span></p></td>
<td><p><span data-ttu-id="4fef5-168">Impossibile registrare l'endpoint</span><span class="sxs-lookup"><span data-stu-id="4fef5-168">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="4fef5-169">Impossibile registrare l'endpoint</span><span class="sxs-lookup"><span data-stu-id="4fef5-169">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="4fef5-170">Se il problema persiste, contattare il supporto del prodotto</span><span class="sxs-lookup"><span data-stu-id="4fef5-170">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4fef5-171">20013</span><span class="sxs-lookup"><span data-stu-id="4fef5-171">20013</span></span></p></td>
<td><p><span data-ttu-id="4fef5-172">Error</span><span class="sxs-lookup"><span data-stu-id="4fef5-172">Error</span></span></p></td>
<td><p><span data-ttu-id="4fef5-173">La MCU di messaggistica istantanea non è disponibile</span><span class="sxs-lookup"><span data-stu-id="4fef5-173">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="4fef5-174">La MCU di messaggistica istantanea non è disponibile</span><span class="sxs-lookup"><span data-stu-id="4fef5-174">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="4fef5-175">Vedere se è in esecuzione MCU di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="4fef5-175">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fef5-176">20014</span><span class="sxs-lookup"><span data-stu-id="4fef5-176">20014</span></span></p></td>
<td><p><span data-ttu-id="4fef5-177">Informativo</span><span class="sxs-lookup"><span data-stu-id="4fef5-177">Informational</span></span></p></td>
<td><p><span data-ttu-id="4fef5-178">Recuperato dalla mancata connessione a MCU IM</span><span class="sxs-lookup"><span data-stu-id="4fef5-178">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="4fef5-179">N/D</span><span class="sxs-lookup"><span data-stu-id="4fef5-179">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4fef5-180">20015</span><span class="sxs-lookup"><span data-stu-id="4fef5-180">20015</span></span></p></td>
<td><p><span data-ttu-id="4fef5-181">Error</span><span class="sxs-lookup"><span data-stu-id="4fef5-181">Error</span></span></p></td>
<td><p><span data-ttu-id="4fef5-182">MCU AV non disponibile</span><span class="sxs-lookup"><span data-stu-id="4fef5-182">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="4fef5-183">MCU AV non disponibile</span><span class="sxs-lookup"><span data-stu-id="4fef5-183">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="4fef5-184">Vedere se è in esecuzione MCU AV</span><span class="sxs-lookup"><span data-stu-id="4fef5-184">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fef5-185">20016</span><span class="sxs-lookup"><span data-stu-id="4fef5-185">20016</span></span></p></td>
<td><p><span data-ttu-id="4fef5-186">Informativo</span><span class="sxs-lookup"><span data-stu-id="4fef5-186">Informational</span></span></p></td>
<td><p><span data-ttu-id="4fef5-187">Recuperato dalla mancata connessione a MCU AV</span><span class="sxs-lookup"><span data-stu-id="4fef5-187">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="4fef5-188">N/D</span><span class="sxs-lookup"><span data-stu-id="4fef5-188">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4fef5-189">20017</span><span class="sxs-lookup"><span data-stu-id="4fef5-189">20017</span></span></p></td>
<td><p><span data-ttu-id="4fef5-190">Error</span><span class="sxs-lookup"><span data-stu-id="4fef5-190">Error</span></span></p></td>
<td><p><span data-ttu-id="4fef5-191">Poiché MCU non è disponibile</span><span class="sxs-lookup"><span data-stu-id="4fef5-191">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="4fef5-192">Poiché MCU non è disponibile</span><span class="sxs-lookup"><span data-stu-id="4fef5-192">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="4fef5-193">Vedere se è in esecuzione MCU</span><span class="sxs-lookup"><span data-stu-id="4fef5-193">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fef5-194">20018</span><span class="sxs-lookup"><span data-stu-id="4fef5-194">20018</span></span></p></td>
<td><p><span data-ttu-id="4fef5-195">Informativo</span><span class="sxs-lookup"><span data-stu-id="4fef5-195">Informational</span></span></p></td>
<td><p><span data-ttu-id="4fef5-196">Recuperato dalla mancata connessione a come MCU</span><span class="sxs-lookup"><span data-stu-id="4fef5-196">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="4fef5-197">N/D</span><span class="sxs-lookup"><span data-stu-id="4fef5-197">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4fef5-198">20019</span><span class="sxs-lookup"><span data-stu-id="4fef5-198">20019</span></span></p></td>
<td><p><span data-ttu-id="4fef5-199">Error</span><span class="sxs-lookup"><span data-stu-id="4fef5-199">Error</span></span></p></td>
<td><p><span data-ttu-id="4fef5-200">MCU dei dati non disponibile</span><span class="sxs-lookup"><span data-stu-id="4fef5-200">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="4fef5-201">MCU dei dati non disponibile</span><span class="sxs-lookup"><span data-stu-id="4fef5-201">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="4fef5-202">Controllare se è in esecuzione MCU dati</span><span class="sxs-lookup"><span data-stu-id="4fef5-202">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fef5-203">20020</span><span class="sxs-lookup"><span data-stu-id="4fef5-203">20020</span></span></p></td>
<td><p><span data-ttu-id="4fef5-204">Informativo</span><span class="sxs-lookup"><span data-stu-id="4fef5-204">Informational</span></span></p></td>
<td><p><span data-ttu-id="4fef5-205">Ripristino dalla mancata connessione a MCU dei dati</span><span class="sxs-lookup"><span data-stu-id="4fef5-205">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="4fef5-206">N/D</span><span class="sxs-lookup"><span data-stu-id="4fef5-206">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4fef5-207">20021</span><span class="sxs-lookup"><span data-stu-id="4fef5-207">20021</span></span></p></td>
<td><p><span data-ttu-id="4fef5-208">Error</span><span class="sxs-lookup"><span data-stu-id="4fef5-208">Error</span></span></p></td>
<td><p><span data-ttu-id="4fef5-209">Non è possibile aggiungere MCU IM</span><span class="sxs-lookup"><span data-stu-id="4fef5-209">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="4fef5-210">Non è possibile aggiungere MCU IM</span><span class="sxs-lookup"><span data-stu-id="4fef5-210">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="4fef5-211">Vedere se è in esecuzione MCU di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="4fef5-211">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fef5-212">20022</span><span class="sxs-lookup"><span data-stu-id="4fef5-212">20022</span></span></p></td>
<td><p><span data-ttu-id="4fef5-213">Error</span><span class="sxs-lookup"><span data-stu-id="4fef5-213">Error</span></span></p></td>
<td><p><span data-ttu-id="4fef5-214">Non è possibile aggiungere MCU AV</span><span class="sxs-lookup"><span data-stu-id="4fef5-214">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="4fef5-215">Non è possibile aggiungere MCU AV</span><span class="sxs-lookup"><span data-stu-id="4fef5-215">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="4fef5-216">Vedere se è in esecuzione MCU AV</span><span class="sxs-lookup"><span data-stu-id="4fef5-216">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4fef5-217">20023</span><span class="sxs-lookup"><span data-stu-id="4fef5-217">20023</span></span></p></td>
<td><p><span data-ttu-id="4fef5-218">Error</span><span class="sxs-lookup"><span data-stu-id="4fef5-218">Error</span></span></p></td>
<td><p><span data-ttu-id="4fef5-219">Non è possibile partecipare come MCU</span><span class="sxs-lookup"><span data-stu-id="4fef5-219">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="4fef5-220">Non è possibile partecipare come MCU</span><span class="sxs-lookup"><span data-stu-id="4fef5-220">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="4fef5-221">Vedere se è in esecuzione MCU</span><span class="sxs-lookup"><span data-stu-id="4fef5-221">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fef5-222">20024</span><span class="sxs-lookup"><span data-stu-id="4fef5-222">20024</span></span></p></td>
<td><p><span data-ttu-id="4fef5-223">Error</span><span class="sxs-lookup"><span data-stu-id="4fef5-223">Error</span></span></p></td>
<td><p><span data-ttu-id="4fef5-224">Non è possibile aggiungere MCU dati</span><span class="sxs-lookup"><span data-stu-id="4fef5-224">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="4fef5-225">Non è possibile aggiungere MCU dati</span><span class="sxs-lookup"><span data-stu-id="4fef5-225">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="4fef5-226">Controllare se è in esecuzione MCU dati</span><span class="sxs-lookup"><span data-stu-id="4fef5-226">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4fef5-227">20025</span><span class="sxs-lookup"><span data-stu-id="4fef5-227">20025</span></span></p></td>
<td><p><span data-ttu-id="4fef5-228">Error</span><span class="sxs-lookup"><span data-stu-id="4fef5-228">Error</span></span></p></td>
<td><p><span data-ttu-id="4fef5-229">Non è possibile accedere ad Active Directory per la foto</span><span class="sxs-lookup"><span data-stu-id="4fef5-229">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="4fef5-230">La connessione a Active Directory non è disponibile</span><span class="sxs-lookup"><span data-stu-id="4fef5-230">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="4fef5-231">Verificare che la connessione ad Active Directory sia disponibile</span><span class="sxs-lookup"><span data-stu-id="4fef5-231">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fef5-232">20026</span><span class="sxs-lookup"><span data-stu-id="4fef5-232">20026</span></span></p></td>
<td><p><span data-ttu-id="4fef5-233">Informativo</span><span class="sxs-lookup"><span data-stu-id="4fef5-233">Informational</span></span></p></td>
<td><p><span data-ttu-id="4fef5-234">Recuperato dalla mancata accesso ad Active Directory per la foto</span><span class="sxs-lookup"><span data-stu-id="4fef5-234">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="4fef5-235">N/D</span><span class="sxs-lookup"><span data-stu-id="4fef5-235">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4fef5-236">20027</span><span class="sxs-lookup"><span data-stu-id="4fef5-236">20027</span></span></p></td>
<td><p><span data-ttu-id="4fef5-237">Avviso</span><span class="sxs-lookup"><span data-stu-id="4fef5-237">Warning</span></span></p></td>
<td><p><span data-ttu-id="4fef5-238">Non può deserializzare</span><span class="sxs-lookup"><span data-stu-id="4fef5-238">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="4fef5-239">Non può deserializzare</span><span class="sxs-lookup"><span data-stu-id="4fef5-239">Cannot deserialize</span></span></p>
<p><span data-ttu-id="4fef5-240">Se il problema persiste, contattare il supporto del prodotto</span><span class="sxs-lookup"><span data-stu-id="4fef5-240">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

