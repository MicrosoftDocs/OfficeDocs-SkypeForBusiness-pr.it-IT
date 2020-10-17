---
title: 'Lync Server 2013: contatori delle prestazioni per dispositivi mobili'
description: 'Lync Server 2013: contatori delle prestazioni per dispositivi mobili.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility performance counters
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48185441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 922288f6c026f088d651dc61afdcb6ba04fed30a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550532"
---
# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="1949c-103">Contatori delle prestazioni per dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1949c-103">Mobility performance counters in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1949c-104">_**Ultimo argomento modificato:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="1949c-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="1949c-105">Nelle tabelle riportate di seguito sono elencati i nomi e le descrizioni dei contatori delle prestazioni che è possibile utilizzare per monitorare i server che eseguono Unified Communications Web API (UCWA) e il servizio per dispositivi mobili di Lync Server 2013 MCX.</span><span class="sxs-lookup"><span data-stu-id="1949c-105">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="1949c-106">Il nome della categoria per i contatori nella tabella UCWA è **ls: Web – UCWA**.</span><span class="sxs-lookup"><span data-stu-id="1949c-106">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="1949c-107">Il nome della categoria per i contatori nella tabella dei servizi per dispositivi mobili di MCX è **ls: servizio di comunicazione web-mobile**.</span><span class="sxs-lookup"><span data-stu-id="1949c-107">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="1949c-108">Contatori delle prestazioni per UCWA</span><span class="sxs-lookup"><span data-stu-id="1949c-108">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1949c-109">Contatore</span><span class="sxs-lookup"><span data-stu-id="1949c-109">Counter</span></span></th>
<th><span data-ttu-id="1949c-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1949c-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1949c-111">Numero di applicazioni attive</span><span class="sxs-lookup"><span data-stu-id="1949c-111">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="1949c-112">Il numero corrente di applicazioni</span><span class="sxs-lookup"><span data-stu-id="1949c-112">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-113">Conteggio delle modalità di condivisione delle applicazioni attive</span><span class="sxs-lookup"><span data-stu-id="1949c-113">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="1949c-114">Numero corrente di modalità di condivisione delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="1949c-114">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-115">Conteggio modalità audio attivo</span><span class="sxs-lookup"><span data-stu-id="1949c-115">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="1949c-116">Numero corrente di modalità audio</span><span class="sxs-lookup"><span data-stu-id="1949c-116">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-117">Conteggio delle modalità di collaborazione dei dati attivi</span><span class="sxs-lookup"><span data-stu-id="1949c-117">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="1949c-118">Il numero corrente di modalità di collaborazione dei dati</span><span class="sxs-lookup"><span data-stu-id="1949c-118">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-119">Latenza della foto di Active Directory (MS)</span><span class="sxs-lookup"><span data-stu-id="1949c-119">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="1949c-120">Questo contatore indica il tempo medio (in millisecondi) per recuperare una foto da Active Directory</span><span class="sxs-lookup"><span data-stu-id="1949c-120">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-121">Conteggio modalità di messaggistica attiva</span><span class="sxs-lookup"><span data-stu-id="1949c-121">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="1949c-122">Numero corrente di modalità di messaggistica</span><span class="sxs-lookup"><span data-stu-id="1949c-122">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-123">Conteggio delle modalità video panoramico attivo</span><span class="sxs-lookup"><span data-stu-id="1949c-123">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="1949c-124">Il numero corrente di modalità video panoramico</span><span class="sxs-lookup"><span data-stu-id="1949c-124">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-125">Conteggio di ottenere attivo in sospeso</span><span class="sxs-lookup"><span data-stu-id="1949c-125">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="1949c-126">Il numero di in sospeso corrente viene attivato. connessioni Long-Held al server</span><span class="sxs-lookup"><span data-stu-id="1949c-126">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-127">Conteggio delle sessioni attive</span><span class="sxs-lookup"><span data-stu-id="1949c-127">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="1949c-128">Numero corrente di endpoint registrati in UCWA per applicazione e totale</span><span class="sxs-lookup"><span data-stu-id="1949c-128">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-129">Conteggio delle istanze dell'utente attivo</span><span class="sxs-lookup"><span data-stu-id="1949c-129">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="1949c-130">Numero corrente di istanze utente</span><span class="sxs-lookup"><span data-stu-id="1949c-130">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-131">Istanze utente attive senza applicazione</span><span class="sxs-lookup"><span data-stu-id="1949c-131">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="1949c-132">Numero corrente di istanze utente senza applicazione</span><span class="sxs-lookup"><span data-stu-id="1949c-132">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-133">Conteggio delle modalità video attivo</span><span class="sxs-lookup"><span data-stu-id="1949c-133">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="1949c-134">Il numero corrente di modalità video</span><span class="sxs-lookup"><span data-stu-id="1949c-134">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-135">Richieste di creazione di applicazioni ricevute al secondo</span><span class="sxs-lookup"><span data-stu-id="1949c-135">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="1949c-136">La percentuale di richieste di creazione di applicazioni ricevute al secondo</span><span class="sxs-lookup"><span data-stu-id="1949c-136">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-137">Gli errori di join di MCU</span><span class="sxs-lookup"><span data-stu-id="1949c-137">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="1949c-138">Numero di errori di join di MCU</span><span class="sxs-lookup"><span data-stu-id="1949c-138">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-139">Errore di join di MCU AV</span><span class="sxs-lookup"><span data-stu-id="1949c-139">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="1949c-140">Numero di errori di join di MCU AV</span><span class="sxs-lookup"><span data-stu-id="1949c-140">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-141">Tempo medio di avvio dell'applicazione (MS)</span><span class="sxs-lookup"><span data-stu-id="1949c-141">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="1949c-142">Tempo di avvio medio dell'applicazione in millisecondi</span><span class="sxs-lookup"><span data-stu-id="1949c-142">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-143">Durata media della sessione (MS)</span><span class="sxs-lookup"><span data-stu-id="1949c-143">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="1949c-144">Durata media di una sessione in millisecondi</span><span class="sxs-lookup"><span data-stu-id="1949c-144">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-145">Errori di join dei dati MCU</span><span class="sxs-lookup"><span data-stu-id="1949c-145">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="1949c-146">Numero di errori di join di MCU di dati</span><span class="sxs-lookup"><span data-stu-id="1949c-146">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-147">Latenza ricerca contatti di Exchange (MS)</span><span class="sxs-lookup"><span data-stu-id="1949c-147">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="1949c-148">Questo contatore indica il tempo medio (in millisecondi) per il contatto di ricerca in Exchange</span><span class="sxs-lookup"><span data-stu-id="1949c-148">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-149">Exchange HD Photo Get latenza (MS)</span><span class="sxs-lookup"><span data-stu-id="1949c-149">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="1949c-150">Questo contatore indica il tempo medio (in millisecondi) per il recupero di una foto da Exchange</span><span class="sxs-lookup"><span data-stu-id="1949c-150">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-151">Risposte 4xx HTTP/secondo</span><span class="sxs-lookup"><span data-stu-id="1949c-151">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="1949c-152">La percentuale di risposte al secondo con il codice 4xx HTTP</span><span class="sxs-lookup"><span data-stu-id="1949c-152">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-153">Risposte 5xx HTTP/secondo</span><span class="sxs-lookup"><span data-stu-id="1949c-153">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="1949c-154">La percentuale di risposte al secondo con il codice 5xx HTTP</span><span class="sxs-lookup"><span data-stu-id="1949c-154">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-155">Errori di join di MCU IM</span><span class="sxs-lookup"><span data-stu-id="1949c-155">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="1949c-156">Il numero di errori di join di MCU di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="1949c-156">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-157">Numero di errori della foto di Active Directory</span><span class="sxs-lookup"><span data-stu-id="1949c-157">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="1949c-158">Il numero totale di errori per il recupero delle foto da Active Directory</span><span class="sxs-lookup"><span data-stu-id="1949c-158">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-159">Numero di errori di ricerca dei contatti</span><span class="sxs-lookup"><span data-stu-id="1949c-159">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="1949c-160">Il numero totale di errori per la ricerca dei contatti in Exchange</span><span class="sxs-lookup"><span data-stu-id="1949c-160">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-161">Numero di errori di deserializzazione</span><span class="sxs-lookup"><span data-stu-id="1949c-161">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="1949c-162">Il numero totale di errori di deserializzazione</span><span class="sxs-lookup"><span data-stu-id="1949c-162">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-163">Numero di errori di ricezione foto HD</span><span class="sxs-lookup"><span data-stu-id="1949c-163">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="1949c-164">Il numero totale di errori per il recupero delle foto HD da Exchange</span><span class="sxs-lookup"><span data-stu-id="1949c-164">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-165">Oltre il numero massimo di abbonamenti per applicazione</span><span class="sxs-lookup"><span data-stu-id="1949c-165">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="1949c-166">Il numero di richieste di sottoscrizione sul massimo consentito per applicazione</span><span class="sxs-lookup"><span data-stu-id="1949c-166">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-167">Oltre il numero massimo di sottoscrizioni per batch</span><span class="sxs-lookup"><span data-stu-id="1949c-167">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="1949c-168">Il numero di richieste di sottoscrizione sul massimo consentito per ogni batch</span><span class="sxs-lookup"><span data-stu-id="1949c-168">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-169">Errori di sottoscrizione alla presenza</span><span class="sxs-lookup"><span data-stu-id="1949c-169">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="1949c-170">Il numero di errori da sottoscrivere la presenza</span><span class="sxs-lookup"><span data-stu-id="1949c-170">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-171">Registrazione degli errori degli endpoint</span><span class="sxs-lookup"><span data-stu-id="1949c-171">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="1949c-172">Il numero di errori di registrazione degli endpoint</span><span class="sxs-lookup"><span data-stu-id="1949c-172">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-173">Richieste ricevute/secondo</span><span class="sxs-lookup"><span data-stu-id="1949c-173">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="1949c-174">La percentuale di richieste ricevute al secondo</span><span class="sxs-lookup"><span data-stu-id="1949c-174">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-175">Richieste con esito positivo/secondo</span><span class="sxs-lookup"><span data-stu-id="1949c-175">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="1949c-176">Il tasso al secondo delle richieste riuscite (HTTP 2xx/3xx Response codes)</span><span class="sxs-lookup"><span data-stu-id="1949c-176">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-177">Esito positivo della creazione delle richieste di applicazione/secondo</span><span class="sxs-lookup"><span data-stu-id="1949c-177">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="1949c-178">La velocità al secondo delle richieste di creazione di applicazioni riuscite</span><span class="sxs-lookup"><span data-stu-id="1949c-178">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-179">Conteggio scaduto in sospeso</span><span class="sxs-lookup"><span data-stu-id="1949c-179">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="1949c-180">Il numero di in sospeso viene superato</span><span class="sxs-lookup"><span data-stu-id="1949c-180">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-181">Totale richieste di creazione di applicazioni ricevute</span><span class="sxs-lookup"><span data-stu-id="1949c-181">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="1949c-182">Il numero totale di richieste di creazione di applicazioni ricevute dopo l'avvio del servizio</span><span class="sxs-lookup"><span data-stu-id="1949c-182">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-183">Totale risposte 4xx HTTP</span><span class="sxs-lookup"><span data-stu-id="1949c-183">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="1949c-184">Il numero totale di risposte 4xx HTTP</span><span class="sxs-lookup"><span data-stu-id="1949c-184">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-185">Totale risposte 5xx HTTP</span><span class="sxs-lookup"><span data-stu-id="1949c-185">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="1949c-186">Il numero totale di risposte 5xx HTTP</span><span class="sxs-lookup"><span data-stu-id="1949c-186">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-187">Totale richieste ricevute nel canale di comando</span><span class="sxs-lookup"><span data-stu-id="1949c-187">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="1949c-188">Il numero totale di richieste ricevute nel canale di comando</span><span class="sxs-lookup"><span data-stu-id="1949c-188">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-189">Totale richieste riuscite</span><span class="sxs-lookup"><span data-stu-id="1949c-189">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="1949c-190">Il numero totale di richieste che hanno avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="1949c-190">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-191">Totale sessioni avviate</span><span class="sxs-lookup"><span data-stu-id="1949c-191">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="1949c-192">Il numero totale di sessioni avviate dopo l'avvio del servizio</span><span class="sxs-lookup"><span data-stu-id="1949c-192">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-193">Totale sessioni interrotte a causa del timeout di inattività</span><span class="sxs-lookup"><span data-stu-id="1949c-193">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="1949c-194">Il numero totale di sessioni terminate a causa del timeout di inattività dell'utente</span><span class="sxs-lookup"><span data-stu-id="1949c-194">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-195">Totale applicazioni limitate</span><span class="sxs-lookup"><span data-stu-id="1949c-195">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="1949c-196">Il numero di applicazioni limitate</span><span class="sxs-lookup"><span data-stu-id="1949c-196">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="1949c-197">Contatori delle prestazioni per il servizio per dispositivi mobili MCX</span><span class="sxs-lookup"><span data-stu-id="1949c-197">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1949c-198">Contatore</span><span class="sxs-lookup"><span data-stu-id="1949c-198">Counter</span></span></th>
<th><span data-ttu-id="1949c-199">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1949c-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1949c-200">Durata media di una sessione in millisecondi</span><span class="sxs-lookup"><span data-stu-id="1949c-200">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="1949c-201">Durata media di una sessione in millisecondi</span><span class="sxs-lookup"><span data-stu-id="1949c-201">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-202">Abbonamenti alle notifiche push correnti</span><span class="sxs-lookup"><span data-stu-id="1949c-202">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="1949c-203">Numero corrente di sottoscrizioni di notifica push.</span><span class="sxs-lookup"><span data-stu-id="1949c-203">The current number of push notification subscriptions.</span></span> <span data-ttu-id="1949c-204">Questo numero, insieme al conteggio sessioni attivo, rappresenta il sottoinsieme delle sessioni attualmente attive registrate per i dispositivi Windows Mobile o iPhone.</span><span class="sxs-lookup"><span data-stu-id="1949c-204">This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-205">Conteggio del sondaggio del timeout di rete corrente attivo</span><span class="sxs-lookup"><span data-stu-id="1949c-205">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="1949c-206">Il numero di polli di rete scaduti</span><span class="sxs-lookup"><span data-stu-id="1949c-206">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-207">Conteggio di poll corrente attivo</span><span class="sxs-lookup"><span data-stu-id="1949c-207">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="1949c-208">Il numero di poll attualmente attivi (connessioni di lunga durata al server)</span><span class="sxs-lookup"><span data-stu-id="1949c-208">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-209">Numero di sessione corrente attivo</span><span class="sxs-lookup"><span data-stu-id="1949c-209">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="1949c-210">Numero corrente di endpoint registrati nel servizio per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="1949c-210">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-211">Conteggio delle sessioni attivo con gli abbonamenti a presenza attiva</span><span class="sxs-lookup"><span data-stu-id="1949c-211">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="1949c-212">Il numero di sessioni attive con sottoscrizioni di presenza attiva</span><span class="sxs-lookup"><span data-stu-id="1949c-212">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-213">Richieste di notifica push non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="1949c-213">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="1949c-214">La percentuale di notifiche di push non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="1949c-214">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-215">Richieste di notifica push con esito positivo/secondo</span><span class="sxs-lookup"><span data-stu-id="1949c-215">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="1949c-216">La velocità al secondo delle notifiche push con esito positivo</span><span class="sxs-lookup"><span data-stu-id="1949c-216">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-217">Richieste di notifica push limitate al secondo</span><span class="sxs-lookup"><span data-stu-id="1949c-217">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="1949c-218">La velocità al secondo delle notifiche push limitate</span><span class="sxs-lookup"><span data-stu-id="1949c-218">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-219">Richieste di notifica push/secondo</span><span class="sxs-lookup"><span data-stu-id="1949c-219">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="1949c-220">La velocità al secondo delle notifiche push inviate</span><span class="sxs-lookup"><span data-stu-id="1949c-220">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-221">Richieste non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="1949c-221">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="1949c-222">La percentuale di richieste non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="1949c-222">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-223">Richieste ricevute/secondo</span><span class="sxs-lookup"><span data-stu-id="1949c-223">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="1949c-224">La percentuale di richieste ricevute al secondo</span><span class="sxs-lookup"><span data-stu-id="1949c-224">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-225">Richieste rifiutate/secondo</span><span class="sxs-lookup"><span data-stu-id="1949c-225">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="1949c-226">La percentuale di richieste rifiutate al secondo</span><span class="sxs-lookup"><span data-stu-id="1949c-226">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-227">Richieste con esito positivo/secondo</span><span class="sxs-lookup"><span data-stu-id="1949c-227">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="1949c-228">Il tasso al secondo delle richieste riuscite</span><span class="sxs-lookup"><span data-stu-id="1949c-228">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-229">Esito positivo delle sessioni di avvio/secondo</span><span class="sxs-lookup"><span data-stu-id="1949c-229">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="1949c-230">La velocità al secondo delle richieste di posizione di ottenere riuscite.</span><span class="sxs-lookup"><span data-stu-id="1949c-230">The per second rate of successful Get Location requests.</span></span> <span data-ttu-id="1949c-231">Le richieste di avvio di una sessione utilizzano la maggior parte della CPU sul server.</span><span class="sxs-lookup"><span data-stu-id="1949c-231">Requests to initiate a session consume the most CPU on the server.</span></span> <span data-ttu-id="1949c-232">Il carico supportato di picco è 12/sec.</span><span class="sxs-lookup"><span data-stu-id="1949c-232">Peak supported load is 12/second.</span></span> <span data-ttu-id="1949c-233">La sostenibilità dipende da altri carichi sul server.</span><span class="sxs-lookup"><span data-stu-id="1949c-233">Sustainability depends on other loads on the server.</span></span> <span data-ttu-id="1949c-234">L'avvio di una sessione in genere indica un accesso per un utente che è stato disconnesso per un periodo di tempo prolungato.</span><span class="sxs-lookup"><span data-stu-id="1949c-234">Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-235">Totale chiamate vocali in ingresso rifiutate</span><span class="sxs-lookup"><span data-stu-id="1949c-235">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="1949c-236">Il numero totale di chiamate vocali in ingresso rifiutate</span><span class="sxs-lookup"><span data-stu-id="1949c-236">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-237">Totale chiamate vocali in ingresso non riuscite</span><span class="sxs-lookup"><span data-stu-id="1949c-237">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="1949c-238">Numero totale di chiamate vocali in ingresso non riuscite</span><span class="sxs-lookup"><span data-stu-id="1949c-238">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-239">Totale chiamate vocali in uscita non riuscite</span><span class="sxs-lookup"><span data-stu-id="1949c-239">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="1949c-240">Il numero totale di chiamate vocali in uscita non riuscite</span><span class="sxs-lookup"><span data-stu-id="1949c-240">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-241">Numero totale di sessioni terminate dall'utente</span><span class="sxs-lookup"><span data-stu-id="1949c-241">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="1949c-242">Il numero totale di sessioni terminate dagli utenti</span><span class="sxs-lookup"><span data-stu-id="1949c-242">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-243">Totale richieste di notifica push</span><span class="sxs-lookup"><span data-stu-id="1949c-243">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="1949c-244">Il numero totale di richieste di notifica push</span><span class="sxs-lookup"><span data-stu-id="1949c-244">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-245">Totale richieste di notifica push non riuscite</span><span class="sxs-lookup"><span data-stu-id="1949c-245">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="1949c-246">Il numero totale di richieste di notifica push non riuscite</span><span class="sxs-lookup"><span data-stu-id="1949c-246">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-247">Totale richieste di notifica push con esito positivo</span><span class="sxs-lookup"><span data-stu-id="1949c-247">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="1949c-248">Il numero totale di richieste di notifica push che hanno avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="1949c-248">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-249">Totale richieste di notifica push limitate</span><span class="sxs-lookup"><span data-stu-id="1949c-249">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="1949c-250">Il numero totale di richieste di notifica push che sono state limitate</span><span class="sxs-lookup"><span data-stu-id="1949c-250">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-251">Totale richieste non riuscite</span><span class="sxs-lookup"><span data-stu-id="1949c-251">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="1949c-252">Il numero totale di richieste non riuscite</span><span class="sxs-lookup"><span data-stu-id="1949c-252">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-253">Totale richieste ricevute nel canale di comando</span><span class="sxs-lookup"><span data-stu-id="1949c-253">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="1949c-254">Il numero totale di richieste ricevute nel canale di comando</span><span class="sxs-lookup"><span data-stu-id="1949c-254">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-255">Totale richieste respinte</span><span class="sxs-lookup"><span data-stu-id="1949c-255">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="1949c-256">Il numero totale di richieste che sono state respinte</span><span class="sxs-lookup"><span data-stu-id="1949c-256">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-257">Totale richieste riuscite</span><span class="sxs-lookup"><span data-stu-id="1949c-257">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="1949c-258">Il numero totale di richieste apportate al servizio per dispositivi mobili che hanno avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="1949c-258">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-259">Numero totale di sessioni avviate</span><span class="sxs-lookup"><span data-stu-id="1949c-259">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="1949c-260">Il numero totale di sessioni avviate dopo l'avvio del servizio per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="1949c-260">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-261">Totale sessioni interrotte a causa del timeout di inattività dell'utente</span><span class="sxs-lookup"><span data-stu-id="1949c-261">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="1949c-262">Il numero totale di sessioni terminate a causa del timeout di inattività dell'utente</span><span class="sxs-lookup"><span data-stu-id="1949c-262">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1949c-263">Totale successo delle chiamate vocali in ingresso</span><span class="sxs-lookup"><span data-stu-id="1949c-263">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="1949c-264">Il numero totale di chiamate vocali in ingresso che hanno avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="1949c-264">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1949c-265">Numero totale di chiamate vocali in uscita</span><span class="sxs-lookup"><span data-stu-id="1949c-265">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="1949c-266">Il numero totale di chiamate vocali in uscita che hanno avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="1949c-266">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

