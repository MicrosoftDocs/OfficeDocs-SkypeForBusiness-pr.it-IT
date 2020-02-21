---
title: 'Lync Server 2013: contatori delle prestazioni per dispositivi mobili'
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
ms.openlocfilehash: a0f0d9170b4526c443b88c9227af8f2c55dae4b8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="033ba-102">Contatori delle prestazioni per dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="033ba-102">Mobility performance counters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="033ba-103">_**Ultimo argomento modificato:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="033ba-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="033ba-104">Nelle tabelle riportate di seguito sono elencati i nomi e le descrizioni dei contatori delle prestazioni che è possibile utilizzare per monitorare i server che eseguono Unified Communications Web API (UCWA) e il servizio per dispositivi mobili di Lync Server 2013 MCX.</span><span class="sxs-lookup"><span data-stu-id="033ba-104">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="033ba-105">Il nome della categoria per i contatori nella tabella UCWA è **ls: Web – UCWA**.</span><span class="sxs-lookup"><span data-stu-id="033ba-105">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="033ba-106">Il nome della categoria per i contatori nella tabella dei servizi per dispositivi mobili di MCX è **ls: servizio di comunicazione web-mobile**.</span><span class="sxs-lookup"><span data-stu-id="033ba-106">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="033ba-107">Contatori delle prestazioni per UCWA</span><span class="sxs-lookup"><span data-stu-id="033ba-107">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="033ba-108">Contatore</span><span class="sxs-lookup"><span data-stu-id="033ba-108">Counter</span></span></th>
<th><span data-ttu-id="033ba-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="033ba-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="033ba-110">Numero di applicazioni attive</span><span class="sxs-lookup"><span data-stu-id="033ba-110">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="033ba-111">Il numero corrente di applicazioni</span><span class="sxs-lookup"><span data-stu-id="033ba-111">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-112">Conteggio delle modalità di condivisione delle applicazioni attive</span><span class="sxs-lookup"><span data-stu-id="033ba-112">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="033ba-113">Numero corrente di modalità di condivisione delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="033ba-113">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-114">Conteggio modalità audio attivo</span><span class="sxs-lookup"><span data-stu-id="033ba-114">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="033ba-115">Numero corrente di modalità audio</span><span class="sxs-lookup"><span data-stu-id="033ba-115">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-116">Conteggio delle modalità di collaborazione dei dati attivi</span><span class="sxs-lookup"><span data-stu-id="033ba-116">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="033ba-117">Il numero corrente di modalità di collaborazione dei dati</span><span class="sxs-lookup"><span data-stu-id="033ba-117">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-118">Latenza della foto di Active Directory (MS)</span><span class="sxs-lookup"><span data-stu-id="033ba-118">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="033ba-119">Questo contatore indica il tempo medio (in millisecondi) per recuperare una foto da Active Directory</span><span class="sxs-lookup"><span data-stu-id="033ba-119">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-120">Conteggio modalità di messaggistica attiva</span><span class="sxs-lookup"><span data-stu-id="033ba-120">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="033ba-121">Numero corrente di modalità di messaggistica</span><span class="sxs-lookup"><span data-stu-id="033ba-121">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-122">Conteggio delle modalità video panoramico attivo</span><span class="sxs-lookup"><span data-stu-id="033ba-122">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="033ba-123">Il numero corrente di modalità video panoramico</span><span class="sxs-lookup"><span data-stu-id="033ba-123">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-124">Conteggio di ottenere attivo in sospeso</span><span class="sxs-lookup"><span data-stu-id="033ba-124">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="033ba-125">Il numero di in sospeso corrente viene attivato. connessioni Long-Held al server</span><span class="sxs-lookup"><span data-stu-id="033ba-125">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-126">Conteggio delle sessioni attive</span><span class="sxs-lookup"><span data-stu-id="033ba-126">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="033ba-127">Numero corrente di endpoint registrati in UCWA per applicazione e totale</span><span class="sxs-lookup"><span data-stu-id="033ba-127">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-128">Conteggio delle istanze dell'utente attivo</span><span class="sxs-lookup"><span data-stu-id="033ba-128">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="033ba-129">Numero corrente di istanze utente</span><span class="sxs-lookup"><span data-stu-id="033ba-129">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-130">Istanze utente attive senza applicazione</span><span class="sxs-lookup"><span data-stu-id="033ba-130">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="033ba-131">Numero corrente di istanze utente senza applicazione</span><span class="sxs-lookup"><span data-stu-id="033ba-131">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-132">Conteggio delle modalità video attivo</span><span class="sxs-lookup"><span data-stu-id="033ba-132">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="033ba-133">Il numero corrente di modalità video</span><span class="sxs-lookup"><span data-stu-id="033ba-133">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-134">Richieste di creazione di applicazioni ricevute al secondo</span><span class="sxs-lookup"><span data-stu-id="033ba-134">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="033ba-135">La percentuale di richieste di creazione di applicazioni ricevute al secondo</span><span class="sxs-lookup"><span data-stu-id="033ba-135">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-136">Gli errori di join di MCU</span><span class="sxs-lookup"><span data-stu-id="033ba-136">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="033ba-137">Numero di errori di join di MCU</span><span class="sxs-lookup"><span data-stu-id="033ba-137">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-138">Errore di join di MCU AV</span><span class="sxs-lookup"><span data-stu-id="033ba-138">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="033ba-139">Numero di errori di join di MCU AV</span><span class="sxs-lookup"><span data-stu-id="033ba-139">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-140">Tempo medio di avvio dell'applicazione (MS)</span><span class="sxs-lookup"><span data-stu-id="033ba-140">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="033ba-141">Tempo di avvio medio dell'applicazione in millisecondi</span><span class="sxs-lookup"><span data-stu-id="033ba-141">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-142">Durata media della sessione (MS)</span><span class="sxs-lookup"><span data-stu-id="033ba-142">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="033ba-143">Durata media di una sessione in millisecondi</span><span class="sxs-lookup"><span data-stu-id="033ba-143">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-144">Errori di join dei dati MCU</span><span class="sxs-lookup"><span data-stu-id="033ba-144">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="033ba-145">Numero di errori di join di MCU di dati</span><span class="sxs-lookup"><span data-stu-id="033ba-145">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-146">Latenza ricerca contatti di Exchange (MS)</span><span class="sxs-lookup"><span data-stu-id="033ba-146">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="033ba-147">Questo contatore indica il tempo medio (in millisecondi) per il contatto di ricerca in Exchange</span><span class="sxs-lookup"><span data-stu-id="033ba-147">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-148">Exchange HD Photo Get latenza (MS)</span><span class="sxs-lookup"><span data-stu-id="033ba-148">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="033ba-149">Questo contatore indica il tempo medio (in millisecondi) per il recupero di una foto da Exchange</span><span class="sxs-lookup"><span data-stu-id="033ba-149">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-150">Risposte 4xx HTTP/secondo</span><span class="sxs-lookup"><span data-stu-id="033ba-150">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="033ba-151">La percentuale di risposte al secondo con il codice 4xx HTTP</span><span class="sxs-lookup"><span data-stu-id="033ba-151">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-152">Risposte 5xx HTTP/secondo</span><span class="sxs-lookup"><span data-stu-id="033ba-152">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="033ba-153">La percentuale di risposte al secondo con il codice 5xx HTTP</span><span class="sxs-lookup"><span data-stu-id="033ba-153">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-154">Errori di join di MCU IM</span><span class="sxs-lookup"><span data-stu-id="033ba-154">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="033ba-155">Il numero di errori di join di MCU di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="033ba-155">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-156">Numero di errori della foto di Active Directory</span><span class="sxs-lookup"><span data-stu-id="033ba-156">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="033ba-157">Il numero totale di errori per il recupero delle foto da Active Directory</span><span class="sxs-lookup"><span data-stu-id="033ba-157">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-158">Numero di errori di ricerca dei contatti</span><span class="sxs-lookup"><span data-stu-id="033ba-158">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="033ba-159">Il numero totale di errori per la ricerca dei contatti in Exchange</span><span class="sxs-lookup"><span data-stu-id="033ba-159">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-160">Numero di errori di deserializzazione</span><span class="sxs-lookup"><span data-stu-id="033ba-160">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="033ba-161">Il numero totale di errori di deserializzazione</span><span class="sxs-lookup"><span data-stu-id="033ba-161">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-162">Numero di errori di ricezione foto HD</span><span class="sxs-lookup"><span data-stu-id="033ba-162">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="033ba-163">Il numero totale di errori per il recupero delle foto HD da Exchange</span><span class="sxs-lookup"><span data-stu-id="033ba-163">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-164">Oltre il numero massimo di abbonamenti per applicazione</span><span class="sxs-lookup"><span data-stu-id="033ba-164">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="033ba-165">Il numero di richieste di sottoscrizione sul massimo consentito per applicazione</span><span class="sxs-lookup"><span data-stu-id="033ba-165">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-166">Oltre il numero massimo di sottoscrizioni per batch</span><span class="sxs-lookup"><span data-stu-id="033ba-166">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="033ba-167">Il numero di richieste di sottoscrizione sul massimo consentito per ogni batch</span><span class="sxs-lookup"><span data-stu-id="033ba-167">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-168">Errori di sottoscrizione alla presenza</span><span class="sxs-lookup"><span data-stu-id="033ba-168">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="033ba-169">Il numero di errori da sottoscrivere la presenza</span><span class="sxs-lookup"><span data-stu-id="033ba-169">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-170">Registrazione degli errori degli endpoint</span><span class="sxs-lookup"><span data-stu-id="033ba-170">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="033ba-171">Il numero di errori di registrazione degli endpoint</span><span class="sxs-lookup"><span data-stu-id="033ba-171">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-172">Richieste ricevute/secondo</span><span class="sxs-lookup"><span data-stu-id="033ba-172">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="033ba-173">La percentuale di richieste ricevute al secondo</span><span class="sxs-lookup"><span data-stu-id="033ba-173">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-174">Richieste con esito positivo/secondo</span><span class="sxs-lookup"><span data-stu-id="033ba-174">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="033ba-175">Il tasso al secondo delle richieste riuscite (HTTP 2xx/3xx Response codes)</span><span class="sxs-lookup"><span data-stu-id="033ba-175">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-176">Esito positivo della creazione delle richieste di applicazione/secondo</span><span class="sxs-lookup"><span data-stu-id="033ba-176">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="033ba-177">La velocità al secondo delle richieste di creazione di applicazioni riuscite</span><span class="sxs-lookup"><span data-stu-id="033ba-177">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-178">Conteggio scaduto in sospeso</span><span class="sxs-lookup"><span data-stu-id="033ba-178">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="033ba-179">Il numero di in sospeso viene superato</span><span class="sxs-lookup"><span data-stu-id="033ba-179">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-180">Totale richieste di creazione di applicazioni ricevute</span><span class="sxs-lookup"><span data-stu-id="033ba-180">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="033ba-181">Il numero totale di richieste di creazione di applicazioni ricevute dopo l'avvio del servizio</span><span class="sxs-lookup"><span data-stu-id="033ba-181">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-182">Totale risposte 4xx HTTP</span><span class="sxs-lookup"><span data-stu-id="033ba-182">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="033ba-183">Il numero totale di risposte 4xx HTTP</span><span class="sxs-lookup"><span data-stu-id="033ba-183">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-184">Totale risposte 5xx HTTP</span><span class="sxs-lookup"><span data-stu-id="033ba-184">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="033ba-185">Il numero totale di risposte 5xx HTTP</span><span class="sxs-lookup"><span data-stu-id="033ba-185">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-186">Totale richieste ricevute nel canale di comando</span><span class="sxs-lookup"><span data-stu-id="033ba-186">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="033ba-187">Il numero totale di richieste ricevute nel canale di comando</span><span class="sxs-lookup"><span data-stu-id="033ba-187">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-188">Totale richieste riuscite</span><span class="sxs-lookup"><span data-stu-id="033ba-188">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="033ba-189">Il numero totale di richieste che hanno avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="033ba-189">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-190">Totale sessioni avviate</span><span class="sxs-lookup"><span data-stu-id="033ba-190">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="033ba-191">Il numero totale di sessioni avviate dopo l'avvio del servizio</span><span class="sxs-lookup"><span data-stu-id="033ba-191">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-192">Totale sessioni interrotte a causa del timeout di inattività</span><span class="sxs-lookup"><span data-stu-id="033ba-192">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="033ba-193">Il numero totale di sessioni terminate a causa del timeout di inattività dell'utente</span><span class="sxs-lookup"><span data-stu-id="033ba-193">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-194">Totale applicazioni limitate</span><span class="sxs-lookup"><span data-stu-id="033ba-194">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="033ba-195">Il numero di applicazioni limitate</span><span class="sxs-lookup"><span data-stu-id="033ba-195">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="033ba-196">Contatori delle prestazioni per il servizio per dispositivi mobili MCX</span><span class="sxs-lookup"><span data-stu-id="033ba-196">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="033ba-197">Contatore</span><span class="sxs-lookup"><span data-stu-id="033ba-197">Counter</span></span></th>
<th><span data-ttu-id="033ba-198">Descrizione</span><span class="sxs-lookup"><span data-stu-id="033ba-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="033ba-199">Durata media di una sessione in millisecondi</span><span class="sxs-lookup"><span data-stu-id="033ba-199">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="033ba-200">Durata media di una sessione in millisecondi</span><span class="sxs-lookup"><span data-stu-id="033ba-200">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-201">Abbonamenti alle notifiche push correnti</span><span class="sxs-lookup"><span data-stu-id="033ba-201">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="033ba-202">Numero corrente di sottoscrizioni di notifica push.</span><span class="sxs-lookup"><span data-stu-id="033ba-202">The current number of push notification subscriptions.</span></span> <span data-ttu-id="033ba-203">Questo numero, insieme al conteggio sessioni attivo, rappresenta il sottoinsieme delle sessioni attualmente attive registrate per i dispositivi Windows Mobile o iPhone.</span><span class="sxs-lookup"><span data-stu-id="033ba-203">This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-204">Conteggio del sondaggio del timeout di rete corrente attivo</span><span class="sxs-lookup"><span data-stu-id="033ba-204">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="033ba-205">Il numero di polli di rete scaduti</span><span class="sxs-lookup"><span data-stu-id="033ba-205">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-206">Conteggio di poll corrente attivo</span><span class="sxs-lookup"><span data-stu-id="033ba-206">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="033ba-207">Il numero di poll attualmente attivi (connessioni di lunga durata al server)</span><span class="sxs-lookup"><span data-stu-id="033ba-207">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-208">Numero di sessione corrente attivo</span><span class="sxs-lookup"><span data-stu-id="033ba-208">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="033ba-209">Numero corrente di endpoint registrati nel servizio per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="033ba-209">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-210">Conteggio delle sessioni attivo con gli abbonamenti a presenza attiva</span><span class="sxs-lookup"><span data-stu-id="033ba-210">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="033ba-211">Il numero di sessioni attive con sottoscrizioni di presenza attiva</span><span class="sxs-lookup"><span data-stu-id="033ba-211">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-212">Richieste di notifica push non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="033ba-212">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="033ba-213">La percentuale di notifiche di push non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="033ba-213">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-214">Richieste di notifica push con esito positivo/secondo</span><span class="sxs-lookup"><span data-stu-id="033ba-214">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="033ba-215">La velocità al secondo delle notifiche push con esito positivo</span><span class="sxs-lookup"><span data-stu-id="033ba-215">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-216">Richieste di notifica push limitate al secondo</span><span class="sxs-lookup"><span data-stu-id="033ba-216">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="033ba-217">La velocità al secondo delle notifiche push limitate</span><span class="sxs-lookup"><span data-stu-id="033ba-217">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-218">Richieste di notifica push/secondo</span><span class="sxs-lookup"><span data-stu-id="033ba-218">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="033ba-219">La velocità al secondo delle notifiche push inviate</span><span class="sxs-lookup"><span data-stu-id="033ba-219">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-220">Richieste non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="033ba-220">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="033ba-221">La percentuale di richieste non riuscite al secondo</span><span class="sxs-lookup"><span data-stu-id="033ba-221">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-222">Richieste ricevute/secondo</span><span class="sxs-lookup"><span data-stu-id="033ba-222">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="033ba-223">La percentuale di richieste ricevute al secondo</span><span class="sxs-lookup"><span data-stu-id="033ba-223">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-224">Richieste rifiutate/secondo</span><span class="sxs-lookup"><span data-stu-id="033ba-224">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="033ba-225">La percentuale di richieste rifiutate al secondo</span><span class="sxs-lookup"><span data-stu-id="033ba-225">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-226">Richieste con esito positivo/secondo</span><span class="sxs-lookup"><span data-stu-id="033ba-226">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="033ba-227">Il tasso al secondo delle richieste riuscite</span><span class="sxs-lookup"><span data-stu-id="033ba-227">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-228">Esito positivo delle sessioni di avvio/secondo</span><span class="sxs-lookup"><span data-stu-id="033ba-228">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="033ba-229">La velocità al secondo delle richieste di posizione di ottenere riuscite.</span><span class="sxs-lookup"><span data-stu-id="033ba-229">The per second rate of successful Get Location requests.</span></span> <span data-ttu-id="033ba-230">Le richieste di avvio di una sessione utilizzano la maggior parte della CPU sul server.</span><span class="sxs-lookup"><span data-stu-id="033ba-230">Requests to initiate a session consume the most CPU on the server.</span></span> <span data-ttu-id="033ba-231">Il carico supportato di picco è 12/sec.</span><span class="sxs-lookup"><span data-stu-id="033ba-231">Peak supported load is 12/second.</span></span> <span data-ttu-id="033ba-232">La sostenibilità dipende da altri carichi sul server.</span><span class="sxs-lookup"><span data-stu-id="033ba-232">Sustainability depends on other loads on the server.</span></span> <span data-ttu-id="033ba-233">L'avvio di una sessione in genere indica un accesso per un utente che è stato disconnesso per un periodo di tempo prolungato.</span><span class="sxs-lookup"><span data-stu-id="033ba-233">Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-234">Totale chiamate vocali in ingresso rifiutate</span><span class="sxs-lookup"><span data-stu-id="033ba-234">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="033ba-235">Il numero totale di chiamate vocali in ingresso rifiutate</span><span class="sxs-lookup"><span data-stu-id="033ba-235">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-236">Totale chiamate vocali in ingresso non riuscite</span><span class="sxs-lookup"><span data-stu-id="033ba-236">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="033ba-237">Numero totale di chiamate vocali in ingresso non riuscite</span><span class="sxs-lookup"><span data-stu-id="033ba-237">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-238">Totale chiamate vocali in uscita non riuscite</span><span class="sxs-lookup"><span data-stu-id="033ba-238">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="033ba-239">Il numero totale di chiamate vocali in uscita non riuscite</span><span class="sxs-lookup"><span data-stu-id="033ba-239">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-240">Numero totale di sessioni terminate dall'utente</span><span class="sxs-lookup"><span data-stu-id="033ba-240">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="033ba-241">Il numero totale di sessioni terminate dagli utenti</span><span class="sxs-lookup"><span data-stu-id="033ba-241">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-242">Totale richieste di notifica push</span><span class="sxs-lookup"><span data-stu-id="033ba-242">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="033ba-243">Il numero totale di richieste di notifica push</span><span class="sxs-lookup"><span data-stu-id="033ba-243">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-244">Totale richieste di notifica push non riuscite</span><span class="sxs-lookup"><span data-stu-id="033ba-244">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="033ba-245">Il numero totale di richieste di notifica push non riuscite</span><span class="sxs-lookup"><span data-stu-id="033ba-245">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-246">Totale richieste di notifica push con esito positivo</span><span class="sxs-lookup"><span data-stu-id="033ba-246">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="033ba-247">Il numero totale di richieste di notifica push che hanno avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="033ba-247">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-248">Totale richieste di notifica push limitate</span><span class="sxs-lookup"><span data-stu-id="033ba-248">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="033ba-249">Il numero totale di richieste di notifica push che sono state limitate</span><span class="sxs-lookup"><span data-stu-id="033ba-249">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-250">Totale richieste non riuscite</span><span class="sxs-lookup"><span data-stu-id="033ba-250">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="033ba-251">Il numero totale di richieste non riuscite</span><span class="sxs-lookup"><span data-stu-id="033ba-251">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-252">Totale richieste ricevute nel canale di comando</span><span class="sxs-lookup"><span data-stu-id="033ba-252">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="033ba-253">Il numero totale di richieste ricevute nel canale di comando</span><span class="sxs-lookup"><span data-stu-id="033ba-253">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-254">Totale richieste respinte</span><span class="sxs-lookup"><span data-stu-id="033ba-254">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="033ba-255">Il numero totale di richieste che sono state respinte</span><span class="sxs-lookup"><span data-stu-id="033ba-255">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-256">Totale richieste riuscite</span><span class="sxs-lookup"><span data-stu-id="033ba-256">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="033ba-257">Il numero totale di richieste apportate al servizio per dispositivi mobili che hanno avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="033ba-257">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-258">Numero totale di sessioni avviate</span><span class="sxs-lookup"><span data-stu-id="033ba-258">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="033ba-259">Il numero totale di sessioni avviate dopo l'avvio del servizio per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="033ba-259">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-260">Totale sessioni interrotte a causa del timeout di inattività dell'utente</span><span class="sxs-lookup"><span data-stu-id="033ba-260">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="033ba-261">Il numero totale di sessioni terminate a causa del timeout di inattività dell'utente</span><span class="sxs-lookup"><span data-stu-id="033ba-261">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="033ba-262">Totale successo delle chiamate vocali in ingresso</span><span class="sxs-lookup"><span data-stu-id="033ba-262">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="033ba-263">Il numero totale di chiamate vocali in ingresso che hanno avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="033ba-263">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="033ba-264">Numero totale di chiamate vocali in uscita</span><span class="sxs-lookup"><span data-stu-id="033ba-264">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="033ba-265">Il numero totale di chiamate vocali in uscita che hanno avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="033ba-265">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

