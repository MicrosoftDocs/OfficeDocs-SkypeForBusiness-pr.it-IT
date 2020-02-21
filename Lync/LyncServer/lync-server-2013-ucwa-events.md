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
ms.openlocfilehash: 950d52dfe86ebf4d5b8b53677248528f1ef49047
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="bd5e2-102">Eventi UCWA in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd5e2-102">UCWA events in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd5e2-103">_**Ultimo argomento modificato:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="bd5e2-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="bd5e2-104">Lync Server 2013 utilizza Unified Communications Web API (UCWA) per una serie di scopi, dall'accesso a Microsoft Exchange per le ricerche dei contatti per l'aggiornamento della presenza per i client mobili.</span><span class="sxs-lookup"><span data-stu-id="bd5e2-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="bd5e2-105">UCWA scriverà i record del comportamento operativo come tipi di evento informativi, di avviso e di errore.</span><span class="sxs-lookup"><span data-stu-id="bd5e2-105">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="bd5e2-106">Nella tabella seguente vengono descritti gli eventi che possono essere scritti dai componenti di UCWA.</span><span class="sxs-lookup"><span data-stu-id="bd5e2-106">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd5e2-107">ID evento</span><span class="sxs-lookup"><span data-stu-id="bd5e2-107">Event ID</span></span></th>
<th><span data-ttu-id="bd5e2-108">Tipo evento</span><span class="sxs-lookup"><span data-stu-id="bd5e2-108">Event Type</span></span></th>
<th><span data-ttu-id="bd5e2-109">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="bd5e2-109">Summary</span></span></th>
<th><span data-ttu-id="bd5e2-110">Causa e risoluzione</span><span class="sxs-lookup"><span data-stu-id="bd5e2-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd5e2-111">20001</span><span class="sxs-lookup"><span data-stu-id="bd5e2-111">20001</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-112">Informativo</span><span class="sxs-lookup"><span data-stu-id="bd5e2-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-113">UCWA inizializzato</span><span class="sxs-lookup"><span data-stu-id="bd5e2-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-114">N/D</span><span class="sxs-lookup"><span data-stu-id="bd5e2-114">N/A</span></span></p>
<p><span data-ttu-id="bd5e2-115">N/D</span><span class="sxs-lookup"><span data-stu-id="bd5e2-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd5e2-116">20002</span><span class="sxs-lookup"><span data-stu-id="bd5e2-116">20002</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-117">Errore</span><span class="sxs-lookup"><span data-stu-id="bd5e2-117">Error</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-118">UCWA ha rilevato un'eccezione imprevista durante l'inizializzazione</span><span class="sxs-lookup"><span data-stu-id="bd5e2-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-119">Si è verificato un errore imprevisto durante l'inizializzazione</span><span class="sxs-lookup"><span data-stu-id="bd5e2-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="bd5e2-120">Esaminare i dettagli dell'eccezione nella voce del registro eventi associata per determinare la causa possibile</span><span class="sxs-lookup"><span data-stu-id="bd5e2-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd5e2-121">20003</span><span class="sxs-lookup"><span data-stu-id="bd5e2-121">20003</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-122">Errore</span><span class="sxs-lookup"><span data-stu-id="bd5e2-122">Error</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-123">UCWA ha rilevato un'eccezione non gestita</span><span class="sxs-lookup"><span data-stu-id="bd5e2-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-124">Si è verificata un'eccezione non gestita</span><span class="sxs-lookup"><span data-stu-id="bd5e2-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="bd5e2-125">Riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="bd5e2-125">Restart the server.</span></span> <span data-ttu-id="bd5e2-126">Se il problema persiste, contattare il supporto del prodotto</span><span class="sxs-lookup"><span data-stu-id="bd5e2-126">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd5e2-127">20004</span><span class="sxs-lookup"><span data-stu-id="bd5e2-127">20004</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-128">Errore</span><span class="sxs-lookup"><span data-stu-id="bd5e2-128">Error</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-129">Non è possibile accedere a Exchange per la foto HD</span><span class="sxs-lookup"><span data-stu-id="bd5e2-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-130">La connessione a Exchange non è disponibile</span><span class="sxs-lookup"><span data-stu-id="bd5e2-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="bd5e2-131">Verificare che la connessione a Exchange sia disponibile</span><span class="sxs-lookup"><span data-stu-id="bd5e2-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd5e2-132">20005</span><span class="sxs-lookup"><span data-stu-id="bd5e2-132">20005</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-133">Informativo</span><span class="sxs-lookup"><span data-stu-id="bd5e2-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-134">Recuperato dalla mancata accesso a Exchange per la foto HD</span><span class="sxs-lookup"><span data-stu-id="bd5e2-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-135">N/D</span><span class="sxs-lookup"><span data-stu-id="bd5e2-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd5e2-136">20006</span><span class="sxs-lookup"><span data-stu-id="bd5e2-136">20006</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-137">Errore</span><span class="sxs-lookup"><span data-stu-id="bd5e2-137">Error</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-138">Non è possibile accedere a Exchange per la ricerca dei contatti</span><span class="sxs-lookup"><span data-stu-id="bd5e2-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-139">La connessione a Exchange non è disponibile</span><span class="sxs-lookup"><span data-stu-id="bd5e2-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="bd5e2-140">Verificare che la connessione a Exchange sia disponibile</span><span class="sxs-lookup"><span data-stu-id="bd5e2-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd5e2-141">20007</span><span class="sxs-lookup"><span data-stu-id="bd5e2-141">20007</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-142">Informativo</span><span class="sxs-lookup"><span data-stu-id="bd5e2-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-143">Recuperato dalla mancata ricerca del contatto in Exchange</span><span class="sxs-lookup"><span data-stu-id="bd5e2-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-144">N/D</span><span class="sxs-lookup"><span data-stu-id="bd5e2-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd5e2-145">20008</span><span class="sxs-lookup"><span data-stu-id="bd5e2-145">20008</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-146">Avviso</span><span class="sxs-lookup"><span data-stu-id="bd5e2-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-147">Tentativo di sottoscrizione di un numero maggiore di sottoscrizioni di presenza consentite per applicazione</span><span class="sxs-lookup"><span data-stu-id="bd5e2-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-148">Tentativo di sottoscrizione di un numero maggiore di sottoscrizioni di presenza consentite per applicazione</span><span class="sxs-lookup"><span data-stu-id="bd5e2-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="bd5e2-149">Controllare i client per le sottoscrizioni non necessarie</span><span class="sxs-lookup"><span data-stu-id="bd5e2-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd5e2-150">20009</span><span class="sxs-lookup"><span data-stu-id="bd5e2-150">20009</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-151">Avviso</span><span class="sxs-lookup"><span data-stu-id="bd5e2-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-152">Tentativo di sottoscrizione di un numero maggiore di sottoscrizioni di presenza consentite per batch</span><span class="sxs-lookup"><span data-stu-id="bd5e2-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-153">Tentativo di sottoscrizione di un numero maggiore di sottoscrizioni di presenza consentite per batch</span><span class="sxs-lookup"><span data-stu-id="bd5e2-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="bd5e2-154">Controllare i client per le sottoscrizioni non necessarie</span><span class="sxs-lookup"><span data-stu-id="bd5e2-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd5e2-155">20010</span><span class="sxs-lookup"><span data-stu-id="bd5e2-155">20010</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-156">Errore</span><span class="sxs-lookup"><span data-stu-id="bd5e2-156">Error</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-157">Non è in grado di recuperare i dati inband</span><span class="sxs-lookup"><span data-stu-id="bd5e2-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-158">Non è in grado di recuperare i dati inband</span><span class="sxs-lookup"><span data-stu-id="bd5e2-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="bd5e2-159">Se il problema persiste, contattare il supporto del prodotto</span><span class="sxs-lookup"><span data-stu-id="bd5e2-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd5e2-160">20011</span><span class="sxs-lookup"><span data-stu-id="bd5e2-160">20011</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-161">Errore</span><span class="sxs-lookup"><span data-stu-id="bd5e2-161">Error</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-162">Non è possibile sottoscrivere la presenza</span><span class="sxs-lookup"><span data-stu-id="bd5e2-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-163">Non è possibile sottoscrivere la presenza</span><span class="sxs-lookup"><span data-stu-id="bd5e2-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="bd5e2-164">Se il problema persiste, contattare il supporto del prodotto</span><span class="sxs-lookup"><span data-stu-id="bd5e2-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd5e2-165">20012</span><span class="sxs-lookup"><span data-stu-id="bd5e2-165">20012</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-166">Errore</span><span class="sxs-lookup"><span data-stu-id="bd5e2-166">Error</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-167">Impossibile registrare l'endpoint</span><span class="sxs-lookup"><span data-stu-id="bd5e2-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-168">Impossibile registrare l'endpoint</span><span class="sxs-lookup"><span data-stu-id="bd5e2-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="bd5e2-169">Se il problema persiste, contattare il supporto del prodotto</span><span class="sxs-lookup"><span data-stu-id="bd5e2-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd5e2-170">20013</span><span class="sxs-lookup"><span data-stu-id="bd5e2-170">20013</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-171">Errore</span><span class="sxs-lookup"><span data-stu-id="bd5e2-171">Error</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-172">La MCU di messaggistica istantanea non è disponibile</span><span class="sxs-lookup"><span data-stu-id="bd5e2-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-173">La MCU di messaggistica istantanea non è disponibile</span><span class="sxs-lookup"><span data-stu-id="bd5e2-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="bd5e2-174">Vedere se è in esecuzione MCU di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="bd5e2-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd5e2-175">20014</span><span class="sxs-lookup"><span data-stu-id="bd5e2-175">20014</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-176">Informativo</span><span class="sxs-lookup"><span data-stu-id="bd5e2-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-177">Recuperato dalla mancata connessione a MCU IM</span><span class="sxs-lookup"><span data-stu-id="bd5e2-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-178">N/D</span><span class="sxs-lookup"><span data-stu-id="bd5e2-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd5e2-179">20015</span><span class="sxs-lookup"><span data-stu-id="bd5e2-179">20015</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-180">Errore</span><span class="sxs-lookup"><span data-stu-id="bd5e2-180">Error</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-181">MCU AV non disponibile</span><span class="sxs-lookup"><span data-stu-id="bd5e2-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-182">MCU AV non disponibile</span><span class="sxs-lookup"><span data-stu-id="bd5e2-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="bd5e2-183">Vedere se è in esecuzione MCU AV</span><span class="sxs-lookup"><span data-stu-id="bd5e2-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd5e2-184">20016</span><span class="sxs-lookup"><span data-stu-id="bd5e2-184">20016</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-185">Informativo</span><span class="sxs-lookup"><span data-stu-id="bd5e2-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-186">Recuperato dalla mancata connessione a MCU AV</span><span class="sxs-lookup"><span data-stu-id="bd5e2-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-187">N/D</span><span class="sxs-lookup"><span data-stu-id="bd5e2-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd5e2-188">20017</span><span class="sxs-lookup"><span data-stu-id="bd5e2-188">20017</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-189">Errore</span><span class="sxs-lookup"><span data-stu-id="bd5e2-189">Error</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-190">Poiché MCU non è disponibile</span><span class="sxs-lookup"><span data-stu-id="bd5e2-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-191">Poiché MCU non è disponibile</span><span class="sxs-lookup"><span data-stu-id="bd5e2-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="bd5e2-192">Vedere se è in esecuzione MCU</span><span class="sxs-lookup"><span data-stu-id="bd5e2-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd5e2-193">20018</span><span class="sxs-lookup"><span data-stu-id="bd5e2-193">20018</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-194">Informativo</span><span class="sxs-lookup"><span data-stu-id="bd5e2-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-195">Recuperato dalla mancata connessione a come MCU</span><span class="sxs-lookup"><span data-stu-id="bd5e2-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-196">N/D</span><span class="sxs-lookup"><span data-stu-id="bd5e2-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd5e2-197">20019</span><span class="sxs-lookup"><span data-stu-id="bd5e2-197">20019</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-198">Errore</span><span class="sxs-lookup"><span data-stu-id="bd5e2-198">Error</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-199">MCU dei dati non disponibile</span><span class="sxs-lookup"><span data-stu-id="bd5e2-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-200">MCU dei dati non disponibile</span><span class="sxs-lookup"><span data-stu-id="bd5e2-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="bd5e2-201">Controllare se è in esecuzione MCU dati</span><span class="sxs-lookup"><span data-stu-id="bd5e2-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd5e2-202">20020</span><span class="sxs-lookup"><span data-stu-id="bd5e2-202">20020</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-203">Informativo</span><span class="sxs-lookup"><span data-stu-id="bd5e2-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-204">Ripristino dalla mancata connessione a MCU dei dati</span><span class="sxs-lookup"><span data-stu-id="bd5e2-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-205">N/D</span><span class="sxs-lookup"><span data-stu-id="bd5e2-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd5e2-206">20021</span><span class="sxs-lookup"><span data-stu-id="bd5e2-206">20021</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-207">Errore</span><span class="sxs-lookup"><span data-stu-id="bd5e2-207">Error</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-208">Non è possibile aggiungere MCU IM</span><span class="sxs-lookup"><span data-stu-id="bd5e2-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-209">Non è possibile aggiungere MCU IM</span><span class="sxs-lookup"><span data-stu-id="bd5e2-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="bd5e2-210">Vedere se è in esecuzione MCU di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="bd5e2-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd5e2-211">20022</span><span class="sxs-lookup"><span data-stu-id="bd5e2-211">20022</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-212">Errore</span><span class="sxs-lookup"><span data-stu-id="bd5e2-212">Error</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-213">Non è possibile aggiungere MCU AV</span><span class="sxs-lookup"><span data-stu-id="bd5e2-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-214">Non è possibile aggiungere MCU AV</span><span class="sxs-lookup"><span data-stu-id="bd5e2-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="bd5e2-215">Vedere se è in esecuzione MCU AV</span><span class="sxs-lookup"><span data-stu-id="bd5e2-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd5e2-216">20023</span><span class="sxs-lookup"><span data-stu-id="bd5e2-216">20023</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-217">Errore</span><span class="sxs-lookup"><span data-stu-id="bd5e2-217">Error</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-218">Non è possibile partecipare come MCU</span><span class="sxs-lookup"><span data-stu-id="bd5e2-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-219">Non è possibile partecipare come MCU</span><span class="sxs-lookup"><span data-stu-id="bd5e2-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="bd5e2-220">Vedere se è in esecuzione MCU</span><span class="sxs-lookup"><span data-stu-id="bd5e2-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd5e2-221">20024</span><span class="sxs-lookup"><span data-stu-id="bd5e2-221">20024</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-222">Errore</span><span class="sxs-lookup"><span data-stu-id="bd5e2-222">Error</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-223">Non è possibile aggiungere MCU dati</span><span class="sxs-lookup"><span data-stu-id="bd5e2-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-224">Non è possibile aggiungere MCU dati</span><span class="sxs-lookup"><span data-stu-id="bd5e2-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="bd5e2-225">Controllare se è in esecuzione MCU dati</span><span class="sxs-lookup"><span data-stu-id="bd5e2-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd5e2-226">20025</span><span class="sxs-lookup"><span data-stu-id="bd5e2-226">20025</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-227">Errore</span><span class="sxs-lookup"><span data-stu-id="bd5e2-227">Error</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-228">Non è possibile accedere ad Active Directory per la foto</span><span class="sxs-lookup"><span data-stu-id="bd5e2-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-229">La connessione a Active Directory non è disponibile</span><span class="sxs-lookup"><span data-stu-id="bd5e2-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="bd5e2-230">Verificare che la connessione ad Active Directory sia disponibile</span><span class="sxs-lookup"><span data-stu-id="bd5e2-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd5e2-231">20026</span><span class="sxs-lookup"><span data-stu-id="bd5e2-231">20026</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-232">Informativo</span><span class="sxs-lookup"><span data-stu-id="bd5e2-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-233">Recuperato dalla mancata accesso ad Active Directory per la foto</span><span class="sxs-lookup"><span data-stu-id="bd5e2-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-234">N/D</span><span class="sxs-lookup"><span data-stu-id="bd5e2-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd5e2-235">20027</span><span class="sxs-lookup"><span data-stu-id="bd5e2-235">20027</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-236">Avviso</span><span class="sxs-lookup"><span data-stu-id="bd5e2-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-237">Non può deserializzare</span><span class="sxs-lookup"><span data-stu-id="bd5e2-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="bd5e2-238">Non può deserializzare</span><span class="sxs-lookup"><span data-stu-id="bd5e2-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="bd5e2-239">Se il problema persiste, contattare il supporto del prodotto</span><span class="sxs-lookup"><span data-stu-id="bd5e2-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

