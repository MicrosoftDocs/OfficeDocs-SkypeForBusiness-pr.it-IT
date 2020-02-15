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
ms.openlocfilehash: 4d42dbd967f90b6e2a905b92558c88fe52ef62d7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="cfdf7-102">Eventi UCWA in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfdf7-102">UCWA events in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cfdf7-103">_**Ultimo argomento modificato:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="cfdf7-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="cfdf7-104">Lync Server 2013 utilizza Unified Communications Web API (UCWA) per una serie di scopi, dall'accesso a Microsoft Exchange per le ricerche dei contatti per l'aggiornamento della presenza per i client mobili.</span><span class="sxs-lookup"><span data-stu-id="cfdf7-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="cfdf7-105">UCWA scriverà i record del comportamento operativo come tipi di evento informativi, di avviso e di errore.</span><span class="sxs-lookup"><span data-stu-id="cfdf7-105">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="cfdf7-106">Nella tabella seguente vengono descritti gli eventi che possono essere scritti dai componenti di UCWA.</span><span class="sxs-lookup"><span data-stu-id="cfdf7-106">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cfdf7-107">ID evento</span><span class="sxs-lookup"><span data-stu-id="cfdf7-107">Event ID</span></span></th>
<th><span data-ttu-id="cfdf7-108">Tipo evento</span><span class="sxs-lookup"><span data-stu-id="cfdf7-108">Event Type</span></span></th>
<th><span data-ttu-id="cfdf7-109">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="cfdf7-109">Summary</span></span></th>
<th><span data-ttu-id="cfdf7-110">Causa e risoluzione</span><span class="sxs-lookup"><span data-stu-id="cfdf7-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cfdf7-111">20001</span><span class="sxs-lookup"><span data-stu-id="cfdf7-111">20001</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-112">Informativo</span><span class="sxs-lookup"><span data-stu-id="cfdf7-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-113">UCWA inizializzato</span><span class="sxs-lookup"><span data-stu-id="cfdf7-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-114">N/D</span><span class="sxs-lookup"><span data-stu-id="cfdf7-114">N/A</span></span></p>
<p><span data-ttu-id="cfdf7-115">N/D</span><span class="sxs-lookup"><span data-stu-id="cfdf7-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfdf7-116">20002</span><span class="sxs-lookup"><span data-stu-id="cfdf7-116">20002</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-117">Errore</span><span class="sxs-lookup"><span data-stu-id="cfdf7-117">Error</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-118">UCWA ha rilevato un'eccezione imprevista durante l'inizializzazione</span><span class="sxs-lookup"><span data-stu-id="cfdf7-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-119">Si è verificato un errore imprevisto durante l'inizializzazione</span><span class="sxs-lookup"><span data-stu-id="cfdf7-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="cfdf7-120">Esaminare i dettagli dell'eccezione nella voce del registro eventi associata per determinare la causa possibile</span><span class="sxs-lookup"><span data-stu-id="cfdf7-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfdf7-121">20003</span><span class="sxs-lookup"><span data-stu-id="cfdf7-121">20003</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-122">Errore</span><span class="sxs-lookup"><span data-stu-id="cfdf7-122">Error</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-123">UCWA ha rilevato un'eccezione non gestita</span><span class="sxs-lookup"><span data-stu-id="cfdf7-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-124">Si è verificata un'eccezione non gestita</span><span class="sxs-lookup"><span data-stu-id="cfdf7-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="cfdf7-125">Riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="cfdf7-125">Restart the server.</span></span> <span data-ttu-id="cfdf7-126">Se il problema persiste, contattare il supporto del prodotto</span><span class="sxs-lookup"><span data-stu-id="cfdf7-126">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfdf7-127">20004</span><span class="sxs-lookup"><span data-stu-id="cfdf7-127">20004</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-128">Errore</span><span class="sxs-lookup"><span data-stu-id="cfdf7-128">Error</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-129">Non è possibile accedere a Exchange per la foto HD</span><span class="sxs-lookup"><span data-stu-id="cfdf7-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-130">La connessione a Exchange non è disponibile</span><span class="sxs-lookup"><span data-stu-id="cfdf7-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="cfdf7-131">Verificare che la connessione a Exchange sia disponibile</span><span class="sxs-lookup"><span data-stu-id="cfdf7-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfdf7-132">20005</span><span class="sxs-lookup"><span data-stu-id="cfdf7-132">20005</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-133">Informativo</span><span class="sxs-lookup"><span data-stu-id="cfdf7-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-134">Recuperato dalla mancata accesso a Exchange per la foto HD</span><span class="sxs-lookup"><span data-stu-id="cfdf7-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-135">N/D</span><span class="sxs-lookup"><span data-stu-id="cfdf7-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfdf7-136">20006</span><span class="sxs-lookup"><span data-stu-id="cfdf7-136">20006</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-137">Errore</span><span class="sxs-lookup"><span data-stu-id="cfdf7-137">Error</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-138">Non è possibile accedere a Exchange per la ricerca dei contatti</span><span class="sxs-lookup"><span data-stu-id="cfdf7-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-139">La connessione a Exchange non è disponibile</span><span class="sxs-lookup"><span data-stu-id="cfdf7-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="cfdf7-140">Verificare che la connessione a Exchange sia disponibile</span><span class="sxs-lookup"><span data-stu-id="cfdf7-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfdf7-141">20007</span><span class="sxs-lookup"><span data-stu-id="cfdf7-141">20007</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-142">Informativo</span><span class="sxs-lookup"><span data-stu-id="cfdf7-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-143">Recuperato dalla mancata ricerca del contatto in Exchange</span><span class="sxs-lookup"><span data-stu-id="cfdf7-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-144">N/D</span><span class="sxs-lookup"><span data-stu-id="cfdf7-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfdf7-145">20008</span><span class="sxs-lookup"><span data-stu-id="cfdf7-145">20008</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-146">Avviso</span><span class="sxs-lookup"><span data-stu-id="cfdf7-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-147">Tentativo di sottoscrizione di un numero maggiore di sottoscrizioni di presenza consentite per applicazione</span><span class="sxs-lookup"><span data-stu-id="cfdf7-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-148">Tentativo di sottoscrizione di un numero maggiore di sottoscrizioni di presenza consentite per applicazione</span><span class="sxs-lookup"><span data-stu-id="cfdf7-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="cfdf7-149">Controllare i client per le sottoscrizioni non necessarie</span><span class="sxs-lookup"><span data-stu-id="cfdf7-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfdf7-150">20009</span><span class="sxs-lookup"><span data-stu-id="cfdf7-150">20009</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-151">Avviso</span><span class="sxs-lookup"><span data-stu-id="cfdf7-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-152">Tentativo di sottoscrizione di un numero maggiore di sottoscrizioni di presenza consentite per batch</span><span class="sxs-lookup"><span data-stu-id="cfdf7-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-153">Tentativo di sottoscrizione di un numero maggiore di sottoscrizioni di presenza consentite per batch</span><span class="sxs-lookup"><span data-stu-id="cfdf7-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="cfdf7-154">Controllare i client per le sottoscrizioni non necessarie</span><span class="sxs-lookup"><span data-stu-id="cfdf7-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfdf7-155">20010</span><span class="sxs-lookup"><span data-stu-id="cfdf7-155">20010</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-156">Errore</span><span class="sxs-lookup"><span data-stu-id="cfdf7-156">Error</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-157">Non è in grado di recuperare i dati inband</span><span class="sxs-lookup"><span data-stu-id="cfdf7-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-158">Non è in grado di recuperare i dati inband</span><span class="sxs-lookup"><span data-stu-id="cfdf7-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="cfdf7-159">Se il problema persiste, contattare il supporto del prodotto</span><span class="sxs-lookup"><span data-stu-id="cfdf7-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfdf7-160">20011</span><span class="sxs-lookup"><span data-stu-id="cfdf7-160">20011</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-161">Errore</span><span class="sxs-lookup"><span data-stu-id="cfdf7-161">Error</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-162">Non è possibile sottoscrivere la presenza</span><span class="sxs-lookup"><span data-stu-id="cfdf7-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-163">Non è possibile sottoscrivere la presenza</span><span class="sxs-lookup"><span data-stu-id="cfdf7-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="cfdf7-164">Se il problema persiste, contattare il supporto del prodotto</span><span class="sxs-lookup"><span data-stu-id="cfdf7-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfdf7-165">20012</span><span class="sxs-lookup"><span data-stu-id="cfdf7-165">20012</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-166">Errore</span><span class="sxs-lookup"><span data-stu-id="cfdf7-166">Error</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-167">Impossibile registrare l'endpoint</span><span class="sxs-lookup"><span data-stu-id="cfdf7-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-168">Impossibile registrare l'endpoint</span><span class="sxs-lookup"><span data-stu-id="cfdf7-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="cfdf7-169">Se il problema persiste, contattare il supporto del prodotto</span><span class="sxs-lookup"><span data-stu-id="cfdf7-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfdf7-170">20013</span><span class="sxs-lookup"><span data-stu-id="cfdf7-170">20013</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-171">Errore</span><span class="sxs-lookup"><span data-stu-id="cfdf7-171">Error</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-172">La MCU di messaggistica istantanea non è disponibile</span><span class="sxs-lookup"><span data-stu-id="cfdf7-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-173">La MCU di messaggistica istantanea non è disponibile</span><span class="sxs-lookup"><span data-stu-id="cfdf7-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="cfdf7-174">Vedere se è in esecuzione MCU di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="cfdf7-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfdf7-175">20014</span><span class="sxs-lookup"><span data-stu-id="cfdf7-175">20014</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-176">Informativo</span><span class="sxs-lookup"><span data-stu-id="cfdf7-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-177">Recuperato dalla mancata connessione a MCU IM</span><span class="sxs-lookup"><span data-stu-id="cfdf7-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-178">N/D</span><span class="sxs-lookup"><span data-stu-id="cfdf7-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfdf7-179">20015</span><span class="sxs-lookup"><span data-stu-id="cfdf7-179">20015</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-180">Errore</span><span class="sxs-lookup"><span data-stu-id="cfdf7-180">Error</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-181">MCU AV non disponibile</span><span class="sxs-lookup"><span data-stu-id="cfdf7-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-182">MCU AV non disponibile</span><span class="sxs-lookup"><span data-stu-id="cfdf7-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="cfdf7-183">Vedere se è in esecuzione MCU AV</span><span class="sxs-lookup"><span data-stu-id="cfdf7-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfdf7-184">20016</span><span class="sxs-lookup"><span data-stu-id="cfdf7-184">20016</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-185">Informativo</span><span class="sxs-lookup"><span data-stu-id="cfdf7-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-186">Recuperato dalla mancata connessione a MCU AV</span><span class="sxs-lookup"><span data-stu-id="cfdf7-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-187">N/D</span><span class="sxs-lookup"><span data-stu-id="cfdf7-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfdf7-188">20017</span><span class="sxs-lookup"><span data-stu-id="cfdf7-188">20017</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-189">Errore</span><span class="sxs-lookup"><span data-stu-id="cfdf7-189">Error</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-190">Poiché MCU non è disponibile</span><span class="sxs-lookup"><span data-stu-id="cfdf7-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-191">Poiché MCU non è disponibile</span><span class="sxs-lookup"><span data-stu-id="cfdf7-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="cfdf7-192">Vedere se è in esecuzione MCU</span><span class="sxs-lookup"><span data-stu-id="cfdf7-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfdf7-193">20018</span><span class="sxs-lookup"><span data-stu-id="cfdf7-193">20018</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-194">Informativo</span><span class="sxs-lookup"><span data-stu-id="cfdf7-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-195">Recuperato dalla mancata connessione a come MCU</span><span class="sxs-lookup"><span data-stu-id="cfdf7-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-196">N/D</span><span class="sxs-lookup"><span data-stu-id="cfdf7-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfdf7-197">20019</span><span class="sxs-lookup"><span data-stu-id="cfdf7-197">20019</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-198">Errore</span><span class="sxs-lookup"><span data-stu-id="cfdf7-198">Error</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-199">MCU dei dati non disponibile</span><span class="sxs-lookup"><span data-stu-id="cfdf7-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-200">MCU dei dati non disponibile</span><span class="sxs-lookup"><span data-stu-id="cfdf7-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="cfdf7-201">Controllare se è in esecuzione MCU dati</span><span class="sxs-lookup"><span data-stu-id="cfdf7-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfdf7-202">20020</span><span class="sxs-lookup"><span data-stu-id="cfdf7-202">20020</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-203">Informativo</span><span class="sxs-lookup"><span data-stu-id="cfdf7-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-204">Ripristino dalla mancata connessione a MCU dei dati</span><span class="sxs-lookup"><span data-stu-id="cfdf7-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-205">N/D</span><span class="sxs-lookup"><span data-stu-id="cfdf7-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfdf7-206">20021</span><span class="sxs-lookup"><span data-stu-id="cfdf7-206">20021</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-207">Errore</span><span class="sxs-lookup"><span data-stu-id="cfdf7-207">Error</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-208">Non è possibile aggiungere MCU IM</span><span class="sxs-lookup"><span data-stu-id="cfdf7-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-209">Non è possibile aggiungere MCU IM</span><span class="sxs-lookup"><span data-stu-id="cfdf7-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="cfdf7-210">Vedere se è in esecuzione MCU di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="cfdf7-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfdf7-211">20022</span><span class="sxs-lookup"><span data-stu-id="cfdf7-211">20022</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-212">Errore</span><span class="sxs-lookup"><span data-stu-id="cfdf7-212">Error</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-213">Non è possibile aggiungere MCU AV</span><span class="sxs-lookup"><span data-stu-id="cfdf7-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-214">Non è possibile aggiungere MCU AV</span><span class="sxs-lookup"><span data-stu-id="cfdf7-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="cfdf7-215">Vedere se è in esecuzione MCU AV</span><span class="sxs-lookup"><span data-stu-id="cfdf7-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfdf7-216">20023</span><span class="sxs-lookup"><span data-stu-id="cfdf7-216">20023</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-217">Errore</span><span class="sxs-lookup"><span data-stu-id="cfdf7-217">Error</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-218">Non è possibile partecipare come MCU</span><span class="sxs-lookup"><span data-stu-id="cfdf7-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-219">Non è possibile partecipare come MCU</span><span class="sxs-lookup"><span data-stu-id="cfdf7-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="cfdf7-220">Vedere se è in esecuzione MCU</span><span class="sxs-lookup"><span data-stu-id="cfdf7-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfdf7-221">20024</span><span class="sxs-lookup"><span data-stu-id="cfdf7-221">20024</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-222">Errore</span><span class="sxs-lookup"><span data-stu-id="cfdf7-222">Error</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-223">Non è possibile aggiungere MCU dati</span><span class="sxs-lookup"><span data-stu-id="cfdf7-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-224">Non è possibile aggiungere MCU dati</span><span class="sxs-lookup"><span data-stu-id="cfdf7-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="cfdf7-225">Controllare se è in esecuzione MCU dati</span><span class="sxs-lookup"><span data-stu-id="cfdf7-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfdf7-226">20025</span><span class="sxs-lookup"><span data-stu-id="cfdf7-226">20025</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-227">Errore</span><span class="sxs-lookup"><span data-stu-id="cfdf7-227">Error</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-228">Non è possibile accedere ad Active Directory per la foto</span><span class="sxs-lookup"><span data-stu-id="cfdf7-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-229">La connessione a Active Directory non è disponibile</span><span class="sxs-lookup"><span data-stu-id="cfdf7-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="cfdf7-230">Verificare che la connessione ad Active Directory sia disponibile</span><span class="sxs-lookup"><span data-stu-id="cfdf7-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfdf7-231">20026</span><span class="sxs-lookup"><span data-stu-id="cfdf7-231">20026</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-232">Informativo</span><span class="sxs-lookup"><span data-stu-id="cfdf7-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-233">Recuperato dalla mancata accesso ad Active Directory per la foto</span><span class="sxs-lookup"><span data-stu-id="cfdf7-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-234">N/D</span><span class="sxs-lookup"><span data-stu-id="cfdf7-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfdf7-235">20027</span><span class="sxs-lookup"><span data-stu-id="cfdf7-235">20027</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-236">Avviso</span><span class="sxs-lookup"><span data-stu-id="cfdf7-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-237">Non può deserializzare</span><span class="sxs-lookup"><span data-stu-id="cfdf7-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="cfdf7-238">Non può deserializzare</span><span class="sxs-lookup"><span data-stu-id="cfdf7-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="cfdf7-239">Se il problema persiste, contattare il supporto del prodotto</span><span class="sxs-lookup"><span data-stu-id="cfdf7-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

