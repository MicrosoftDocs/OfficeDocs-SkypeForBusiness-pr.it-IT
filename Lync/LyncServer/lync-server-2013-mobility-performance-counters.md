---
title: 'Lync Server 2013: contatori delle prestazioni mobili'
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
ms.openlocfilehash: 439c179476c89de8a5245e80e26586d42f4f6e3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758688"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="6883d-102">Contatori delle prestazioni di mobilità in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6883d-102">Mobility performance counters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6883d-103">_**Argomento Ultima modifica:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="6883d-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="6883d-104">Le tabelle seguenti elencano i nomi e le descrizioni dei contatori delle prestazioni che è possibile usare per monitorare i server che usano Unified Communications Web API (UCWA) e il servizio di mobilità MCX di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6883d-104">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="6883d-105">Il nome della categoria per i contatori nella tabella UCWA è **ls: Web – UCWA**.</span><span class="sxs-lookup"><span data-stu-id="6883d-105">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="6883d-106">Il nome della categoria per i contatori nella tabella del servizio di mobilità MCX è **ls: Web-servizio di comunicazione mobile**.</span><span class="sxs-lookup"><span data-stu-id="6883d-106">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="6883d-107">Contatori delle prestazioni per UCWA</span><span class="sxs-lookup"><span data-stu-id="6883d-107">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6883d-108">Contatore</span><span class="sxs-lookup"><span data-stu-id="6883d-108">Counter</span></span></th>
<th><span data-ttu-id="6883d-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6883d-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6883d-110">Conteggio applicazioni attive</span><span class="sxs-lookup"><span data-stu-id="6883d-110">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="6883d-111">Numero corrente di applicazioni</span><span class="sxs-lookup"><span data-stu-id="6883d-111">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-112">Conteggio delle modalità di condivisione delle applicazioni attive</span><span class="sxs-lookup"><span data-stu-id="6883d-112">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="6883d-113">Numero corrente di modalità di condivisione delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="6883d-113">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-114">Conteggio modalità audio attiva</span><span class="sxs-lookup"><span data-stu-id="6883d-114">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="6883d-115">Numero corrente di modalità audio</span><span class="sxs-lookup"><span data-stu-id="6883d-115">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-116">Conteggio delle modalità di collaborazione con i dati attivi</span><span class="sxs-lookup"><span data-stu-id="6883d-116">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="6883d-117">Numero corrente di modalità di collaborazione dei dati</span><span class="sxs-lookup"><span data-stu-id="6883d-117">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-118">Active Directory Photo Get latenza (MS)</span><span class="sxs-lookup"><span data-stu-id="6883d-118">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="6883d-119">Questo contatore mostra il tempo medio (in millisecondi) per recuperare una foto da Active Directory</span><span class="sxs-lookup"><span data-stu-id="6883d-119">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-120">Conteggio delle modalità di messaggistica attiva</span><span class="sxs-lookup"><span data-stu-id="6883d-120">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="6883d-121">Numero corrente di modalità di messaggistica</span><span class="sxs-lookup"><span data-stu-id="6883d-121">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-122">Conteggio delle modalità video panoramico attivo</span><span class="sxs-lookup"><span data-stu-id="6883d-122">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="6883d-123">Numero corrente di modalità video panoramico</span><span class="sxs-lookup"><span data-stu-id="6883d-123">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-124">Conteggio in sospeso attivo</span><span class="sxs-lookup"><span data-stu-id="6883d-124">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="6883d-125">Il numero di ritorni in sospeso attualmente attivi; connessioni Long-Held al server</span><span class="sxs-lookup"><span data-stu-id="6883d-125">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-126">Conteggio sessioni attive</span><span class="sxs-lookup"><span data-stu-id="6883d-126">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="6883d-127">Numero corrente di endpoint registrati in UCWA per applicazione e totale</span><span class="sxs-lookup"><span data-stu-id="6883d-127">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-128">Conteggio istanze utente attivo</span><span class="sxs-lookup"><span data-stu-id="6883d-128">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="6883d-129">Numero corrente di istanze utente</span><span class="sxs-lookup"><span data-stu-id="6883d-129">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-130">Istanze utente attive senza applicazione</span><span class="sxs-lookup"><span data-stu-id="6883d-130">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="6883d-131">Numero corrente di istanze utente senza applicazione</span><span class="sxs-lookup"><span data-stu-id="6883d-131">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-132">Conteggio modalità video attivo</span><span class="sxs-lookup"><span data-stu-id="6883d-132">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="6883d-133">Numero corrente di modalità video</span><span class="sxs-lookup"><span data-stu-id="6883d-133">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-134">Richieste di creazione di applicazioni ricevute/seconde</span><span class="sxs-lookup"><span data-stu-id="6883d-134">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="6883d-135">Tasso per secondo delle richieste di creazione di applicazioni ricevute</span><span class="sxs-lookup"><span data-stu-id="6883d-135">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-136">Errori di join di MCU</span><span class="sxs-lookup"><span data-stu-id="6883d-136">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="6883d-137">Numero di errori di join di MCU</span><span class="sxs-lookup"><span data-stu-id="6883d-137">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-138">Errore di join di MCU AV</span><span class="sxs-lookup"><span data-stu-id="6883d-138">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="6883d-139">Numero di errori di join di MCU AV</span><span class="sxs-lookup"><span data-stu-id="6883d-139">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-140">Tempo di avvio dell'applicazione medio (MS)</span><span class="sxs-lookup"><span data-stu-id="6883d-140">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="6883d-141">Tempo di avvio dell'applicazione medio in millisecondi</span><span class="sxs-lookup"><span data-stu-id="6883d-141">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-142">Durata media per la sessione (MS)</span><span class="sxs-lookup"><span data-stu-id="6883d-142">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="6883d-143">Durata media per una sessione in millisecondi</span><span class="sxs-lookup"><span data-stu-id="6883d-143">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-144">Errori di join di MCU dati</span><span class="sxs-lookup"><span data-stu-id="6883d-144">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="6883d-145">Numero di errori di join di MCU dati</span><span class="sxs-lookup"><span data-stu-id="6883d-145">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-146">Latenza ricerca contatti di Exchange (MS)</span><span class="sxs-lookup"><span data-stu-id="6883d-146">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="6883d-147">Questo contatore mostra il tempo medio (in millisecondi) per cercare il contatto in Exchange</span><span class="sxs-lookup"><span data-stu-id="6883d-147">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-148">Exchange HD Photo Get latenza (MS)</span><span class="sxs-lookup"><span data-stu-id="6883d-148">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="6883d-149">Questo contatore mostra il tempo medio (in millisecondi) per recuperare una foto da Exchange</span><span class="sxs-lookup"><span data-stu-id="6883d-149">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-150">Risposte 4xx HTTP/secondo</span><span class="sxs-lookup"><span data-stu-id="6883d-150">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="6883d-151">Il tasso di risposta al secondo con il codice HTTP 4xx</span><span class="sxs-lookup"><span data-stu-id="6883d-151">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-152">Risposte 5xx HTTP/secondo</span><span class="sxs-lookup"><span data-stu-id="6883d-152">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="6883d-153">Il tasso di risposta al secondo con il codice HTTP 5xx</span><span class="sxs-lookup"><span data-stu-id="6883d-153">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-154">Errori di join di MCU di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="6883d-154">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="6883d-155">Numero di errori di join di MCU di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="6883d-155">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-156">Numero di foto di Active Directory Get Failures</span><span class="sxs-lookup"><span data-stu-id="6883d-156">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="6883d-157">Numero totale di errori per il recupero di foto da Active Directory</span><span class="sxs-lookup"><span data-stu-id="6883d-157">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-158">Numero di errori di ricerca dei contatti</span><span class="sxs-lookup"><span data-stu-id="6883d-158">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="6883d-159">Numero totale di errori per cercare i contatti in Exchange</span><span class="sxs-lookup"><span data-stu-id="6883d-159">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-160">Numero di errori di deserializzazione</span><span class="sxs-lookup"><span data-stu-id="6883d-160">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="6883d-161">Numero totale di errori di deserializzazione</span><span class="sxs-lookup"><span data-stu-id="6883d-161">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-162">Numero di errori di ottenimento della foto HD</span><span class="sxs-lookup"><span data-stu-id="6883d-162">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="6883d-163">Numero totale di errori per recuperare le foto HD da Exchange</span><span class="sxs-lookup"><span data-stu-id="6883d-163">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-164">Oltre il numero massimo di abbonamenti per applicazione</span><span class="sxs-lookup"><span data-stu-id="6883d-164">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="6883d-165">Numero di richieste di sottoscrizione sul massimo consentito per ogni applicazione</span><span class="sxs-lookup"><span data-stu-id="6883d-165">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-166">Oltre il numero massimo di abbonamenti per batch</span><span class="sxs-lookup"><span data-stu-id="6883d-166">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="6883d-167">Numero di richieste di sottoscrizione sul massimo consentito per batch</span><span class="sxs-lookup"><span data-stu-id="6883d-167">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-168">Errori di sottoscrizione presenza</span><span class="sxs-lookup"><span data-stu-id="6883d-168">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="6883d-169">Numero di errori di sottoscrizione della presenza</span><span class="sxs-lookup"><span data-stu-id="6883d-169">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-170">Registrazione degli errori di endpoint</span><span class="sxs-lookup"><span data-stu-id="6883d-170">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="6883d-171">Numero di errori per la registrazione degli endpoint</span><span class="sxs-lookup"><span data-stu-id="6883d-171">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-172">Richieste ricevute/seconde</span><span class="sxs-lookup"><span data-stu-id="6883d-172">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="6883d-173">Tasso per secondo delle richieste ricevute</span><span class="sxs-lookup"><span data-stu-id="6883d-173">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-174">Richieste succeeded/Second</span><span class="sxs-lookup"><span data-stu-id="6883d-174">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="6883d-175">Il tasso per secondo delle richieste di successo (codici di risposta HTTP 2xx/3xx)</span><span class="sxs-lookup"><span data-stu-id="6883d-175">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-176">Succeeded Create application requests/Second</span><span class="sxs-lookup"><span data-stu-id="6883d-176">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="6883d-177">Tasso per secondo delle richieste di creazione di applicazioni di successo</span><span class="sxs-lookup"><span data-stu-id="6883d-177">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-178">Conteggio scaduto in sospeso</span><span class="sxs-lookup"><span data-stu-id="6883d-178">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="6883d-179">Il numero di operazioni in sospeso viene scaduta</span><span class="sxs-lookup"><span data-stu-id="6883d-179">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-180">Totale richieste di creazione di applicazioni ricevute</span><span class="sxs-lookup"><span data-stu-id="6883d-180">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="6883d-181">Numero totale di richieste di creazione di applicazioni ricevute dopo l'avvio del servizio</span><span class="sxs-lookup"><span data-stu-id="6883d-181">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-182">Risposte 4xx totali HTTP</span><span class="sxs-lookup"><span data-stu-id="6883d-182">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="6883d-183">Numero totale di risposte 4xx HTTP</span><span class="sxs-lookup"><span data-stu-id="6883d-183">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-184">Risposte 5xx totali HTTP</span><span class="sxs-lookup"><span data-stu-id="6883d-184">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="6883d-185">Numero totale di risposte 5xx HTTP</span><span class="sxs-lookup"><span data-stu-id="6883d-185">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-186">Totale richieste ricevute nel canale di comando</span><span class="sxs-lookup"><span data-stu-id="6883d-186">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="6883d-187">Numero totale di richieste ricevute nel canale di comando</span><span class="sxs-lookup"><span data-stu-id="6883d-187">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-188">Totale richieste riuscite</span><span class="sxs-lookup"><span data-stu-id="6883d-188">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="6883d-189">Numero totale di richieste che sono state riuscite</span><span class="sxs-lookup"><span data-stu-id="6883d-189">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-190">Totale delle sessioni avviate</span><span class="sxs-lookup"><span data-stu-id="6883d-190">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="6883d-191">Numero totale di sessioni avviate dopo l'avvio del servizio</span><span class="sxs-lookup"><span data-stu-id="6883d-191">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-192">Totale delle sessioni terminate a causa del timeout inattivo</span><span class="sxs-lookup"><span data-stu-id="6883d-192">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="6883d-193">Numero totale di sessioni terminate a causa del timeout di inattività dell'utente</span><span class="sxs-lookup"><span data-stu-id="6883d-193">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-194">Totale applicazioni a limitazione</span><span class="sxs-lookup"><span data-stu-id="6883d-194">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="6883d-195">Numero di applicazioni limitate</span><span class="sxs-lookup"><span data-stu-id="6883d-195">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="6883d-196">Contatori delle prestazioni per il servizio di mobilità MCX</span><span class="sxs-lookup"><span data-stu-id="6883d-196">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6883d-197">Contatore</span><span class="sxs-lookup"><span data-stu-id="6883d-197">Counter</span></span></th>
<th><span data-ttu-id="6883d-198">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6883d-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6883d-199">Durata media per una sessione in millisecondi</span><span class="sxs-lookup"><span data-stu-id="6883d-199">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="6883d-200">Durata media per una sessione in millisecondi</span><span class="sxs-lookup"><span data-stu-id="6883d-200">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-201">Abbonamenti alle notifiche push correnti</span><span class="sxs-lookup"><span data-stu-id="6883d-201">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="6883d-202">Numero corrente di abbonamenti alle notifiche push.</span><span class="sxs-lookup"><span data-stu-id="6883d-202">The current number of push notification subscriptions.</span></span> <span data-ttu-id="6883d-203">Questo numero, in combinazione con il conteggio delle sessioni attivo, rappresenta il sottoinsieme delle sessioni attualmente attive registrate per i dispositivi Windows Mobile o iPhone.</span><span class="sxs-lookup"><span data-stu-id="6883d-203">This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-204">Conteggio del sondaggio di timeout di rete attualmente attivo</span><span class="sxs-lookup"><span data-stu-id="6883d-204">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="6883d-205">Numero di sondaggi di rete scaduti</span><span class="sxs-lookup"><span data-stu-id="6883d-205">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-206">Conteggio sondaggi attualmente attivi</span><span class="sxs-lookup"><span data-stu-id="6883d-206">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="6883d-207">Numero di sondaggi attualmente attivi (connessioni a lungo termine al server)</span><span class="sxs-lookup"><span data-stu-id="6883d-207">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-208">Conteggio sessioni attualmente attivo</span><span class="sxs-lookup"><span data-stu-id="6883d-208">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="6883d-209">Numero corrente di endpoint registrati nel servizio mobilità</span><span class="sxs-lookup"><span data-stu-id="6883d-209">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-210">Conteggio sessioni attivo con abbonamenti alla presenza attiva</span><span class="sxs-lookup"><span data-stu-id="6883d-210">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="6883d-211">Numero di sessioni attualmente attive con abbonamenti a presenza attiva</span><span class="sxs-lookup"><span data-stu-id="6883d-211">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-212">Richieste di notifica push fallite/seconde</span><span class="sxs-lookup"><span data-stu-id="6883d-212">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="6883d-213">Frequenza per il secondo delle notifiche push non riuscite</span><span class="sxs-lookup"><span data-stu-id="6883d-213">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-214">Richieste di notifica push succeeded/Second</span><span class="sxs-lookup"><span data-stu-id="6883d-214">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="6883d-215">Il tasso al secondo delle notifiche push di successo</span><span class="sxs-lookup"><span data-stu-id="6883d-215">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-216">Richieste di notifica push Throttled/Second</span><span class="sxs-lookup"><span data-stu-id="6883d-216">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="6883d-217">Il tasso al secondo delle notifiche push limitate</span><span class="sxs-lookup"><span data-stu-id="6883d-217">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-218">Richieste di notifica push/secondo</span><span class="sxs-lookup"><span data-stu-id="6883d-218">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="6883d-219">Il tasso al secondo delle notifiche push inviate</span><span class="sxs-lookup"><span data-stu-id="6883d-219">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-220">Richieste non riuscite/secondo</span><span class="sxs-lookup"><span data-stu-id="6883d-220">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="6883d-221">Tasso per secondo delle richieste non riuscite</span><span class="sxs-lookup"><span data-stu-id="6883d-221">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-222">Richieste ricevute/seconde</span><span class="sxs-lookup"><span data-stu-id="6883d-222">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="6883d-223">Tasso per secondo delle richieste ricevute</span><span class="sxs-lookup"><span data-stu-id="6883d-223">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-224">Richieste rifiutate/seconde</span><span class="sxs-lookup"><span data-stu-id="6883d-224">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="6883d-225">Tasso al secondo delle richieste rifiutate</span><span class="sxs-lookup"><span data-stu-id="6883d-225">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-226">Richieste succeeded/Second</span><span class="sxs-lookup"><span data-stu-id="6883d-226">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="6883d-227">Il tasso al secondo delle richieste di successo</span><span class="sxs-lookup"><span data-stu-id="6883d-227">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-228">Le richieste di sessione avviate sono successe al secondo</span><span class="sxs-lookup"><span data-stu-id="6883d-228">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="6883d-229">Il tasso al secondo delle richieste di posizione di ottenimento riuscito.</span><span class="sxs-lookup"><span data-stu-id="6883d-229">The per second rate of successful Get Location requests.</span></span> <span data-ttu-id="6883d-230">Le richieste di avvio di una sessione utilizzano la maggior parte della CPU nel server.</span><span class="sxs-lookup"><span data-stu-id="6883d-230">Requests to initiate a session consume the most CPU on the server.</span></span> <span data-ttu-id="6883d-231">Il carico supportato di picco è 12/secondo.</span><span class="sxs-lookup"><span data-stu-id="6883d-231">Peak supported load is 12/second.</span></span> <span data-ttu-id="6883d-232">La sostenibilità dipende da altri carichi nel server.</span><span class="sxs-lookup"><span data-stu-id="6883d-232">Sustainability depends on other loads on the server.</span></span> <span data-ttu-id="6883d-233">L'avvio di una sessione in genere indica un accesso per un utente che è stato disconnesso per un periodo di tempo prolungato.</span><span class="sxs-lookup"><span data-stu-id="6883d-233">Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-234">Chiamate vocali in ingresso rifiutate totali</span><span class="sxs-lookup"><span data-stu-id="6883d-234">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="6883d-235">Numero totale di chiamate vocali in ingresso rifiutate</span><span class="sxs-lookup"><span data-stu-id="6883d-235">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-236">Totale chiamate vocali in ingresso non riuscito</span><span class="sxs-lookup"><span data-stu-id="6883d-236">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="6883d-237">Numero totale di chiamate vocali in ingresso non riuscite</span><span class="sxs-lookup"><span data-stu-id="6883d-237">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-238">Totale chiamate vocali in uscita non riuscite</span><span class="sxs-lookup"><span data-stu-id="6883d-238">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="6883d-239">Numero totale di chiamate vocali in uscita non riuscite</span><span class="sxs-lookup"><span data-stu-id="6883d-239">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-240">Numero totale di sessioni terminate dall'utente</span><span class="sxs-lookup"><span data-stu-id="6883d-240">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="6883d-241">Numero totale di sessioni terminate dagli utenti</span><span class="sxs-lookup"><span data-stu-id="6883d-241">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-242">Totale richieste di notifica push</span><span class="sxs-lookup"><span data-stu-id="6883d-242">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="6883d-243">Numero totale di richieste di notifica push</span><span class="sxs-lookup"><span data-stu-id="6883d-243">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-244">Totale richieste di notifica push non riuscite</span><span class="sxs-lookup"><span data-stu-id="6883d-244">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="6883d-245">Numero totale di richieste di notifica push non riuscite</span><span class="sxs-lookup"><span data-stu-id="6883d-245">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-246">Totale richieste di notifica push riuscite</span><span class="sxs-lookup"><span data-stu-id="6883d-246">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="6883d-247">Numero totale di richieste di notifica push che hanno avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="6883d-247">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-248">Richieste di notifica push totali limitate</span><span class="sxs-lookup"><span data-stu-id="6883d-248">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="6883d-249">Numero totale di richieste di notifica push che sono state strozzate</span><span class="sxs-lookup"><span data-stu-id="6883d-249">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-250">Totale richieste non riuscite</span><span class="sxs-lookup"><span data-stu-id="6883d-250">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="6883d-251">Numero totale di richieste non riuscite</span><span class="sxs-lookup"><span data-stu-id="6883d-251">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-252">Totale richieste ricevute nel canale di comando</span><span class="sxs-lookup"><span data-stu-id="6883d-252">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="6883d-253">Numero totale di richieste ricevute nel canale di comando</span><span class="sxs-lookup"><span data-stu-id="6883d-253">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-254">Totale richieste rifiutate</span><span class="sxs-lookup"><span data-stu-id="6883d-254">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="6883d-255">Numero totale di richieste rifiutate</span><span class="sxs-lookup"><span data-stu-id="6883d-255">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-256">Totale richieste riuscite</span><span class="sxs-lookup"><span data-stu-id="6883d-256">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="6883d-257">Numero totale di richieste effettuate al servizio di mobilità riuscito</span><span class="sxs-lookup"><span data-stu-id="6883d-257">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-258">Numero totale avviato dalla sessione</span><span class="sxs-lookup"><span data-stu-id="6883d-258">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="6883d-259">Numero totale di sessioni avviate da quando è stato avviato il servizio di mobilità</span><span class="sxs-lookup"><span data-stu-id="6883d-259">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-260">Totale delle sessioni terminate a causa del timeout di inattività dell'utente</span><span class="sxs-lookup"><span data-stu-id="6883d-260">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="6883d-261">Numero totale di sessioni terminate a causa del timeout di inattività dell'utente</span><span class="sxs-lookup"><span data-stu-id="6883d-261">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6883d-262">Totale successo delle chiamate vocali in entrata</span><span class="sxs-lookup"><span data-stu-id="6883d-262">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="6883d-263">Numero totale di chiamate vocali in entrata che hanno avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="6883d-263">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6883d-264">Totale successo delle chiamate vocali in uscita</span><span class="sxs-lookup"><span data-stu-id="6883d-264">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="6883d-265">Numero totale di chiamate vocali in uscita che hanno avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="6883d-265">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

