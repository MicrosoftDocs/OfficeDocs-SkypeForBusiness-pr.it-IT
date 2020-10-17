---
title: Interpretazione dei risultati
description: Interpretare i risultati.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8342a1ec1e15e42852fc5293f87342e98587a60
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565342"
---
# <a name="interpreting-the-results"></a><span data-ttu-id="7b069-103">Interpretazione dei risultati</span><span class="sxs-lookup"><span data-stu-id="7b069-103">Interpreting the Results</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b069-104">_**Ultimo argomento modificato:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="7b069-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="7b069-105">Lo strumento di stress e prestazioni di Lync Server 2013 (LyncPerfTool.exe) dispone di numerosi contatori che è possibile utilizzare per comprendere le operazioni eseguite dal client e l'eventuale presenza di problemi.</span><span class="sxs-lookup"><span data-stu-id="7b069-105">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="7b069-106">Contatori client</span><span class="sxs-lookup"><span data-stu-id="7b069-106">Client Counters</span></span>

<span data-ttu-id="7b069-107">Ogni istanza di LyncPerfTool.exe in esecuzione ha un'istanza separata dei contatori.</span><span class="sxs-lookup"><span data-stu-id="7b069-107">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="7b069-108">Ogni istanza è denominata dal relativo ID di processo.</span><span class="sxs-lookup"><span data-stu-id="7b069-108">Each instance is named by its process ID.</span></span>

<span data-ttu-id="7b069-109">Se i client sono sovraccarichi, è possibile che si verifichino problemi.</span><span class="sxs-lookup"><span data-stu-id="7b069-109">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="7b069-110">Per evitare questi problemi, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b069-110">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="7b069-111">Monitorare la CPU e l'utilizzo della memoria nei computer client.</span><span class="sxs-lookup"><span data-stu-id="7b069-111">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="7b069-112">Se la CPU è costantemente al di sopra del 90%, ridurre il numero di utenti.</span><span class="sxs-lookup"><span data-stu-id="7b069-112">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="7b069-113">Se l'ingombro della memoria è elevato, è possibile che si verifichino problemi se il file di paging non è abbastanza grande.</span><span class="sxs-lookup"><span data-stu-id="7b069-113">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="7b069-114">Verificare che la carica di commit non colpisca il limite del computer.</span><span class="sxs-lookup"><span data-stu-id="7b069-114">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="7b069-115">Se si esegue in limiti di memoria, è consigliabile aumentare le dimensioni del file di paging o ridurre il numero di utenti</span><span class="sxs-lookup"><span data-stu-id="7b069-115">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="7b069-116">Nelle tabelle riportate di seguito sono elencati i contatori delle prestazioni principali di LyncPerfTool.</span><span class="sxs-lookup"><span data-stu-id="7b069-116">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="7b069-117">**Informazioni generali**</span><span class="sxs-lookup"><span data-stu-id="7b069-117">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b069-118"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="7b069-118"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="7b069-119"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="7b069-119"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b069-120">Tempo impiegato in minuti</span><span class="sxs-lookup"><span data-stu-id="7b069-120">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="7b069-121">Tempo trascorso dopo l'avvio del processo.</span><span class="sxs-lookup"><span data-stu-id="7b069-121">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b069-122">Endpoint attivi</span><span class="sxs-lookup"><span data-stu-id="7b069-122">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="7b069-123">Numero di endpoint attualmente connessi al server.</span><span class="sxs-lookup"><span data-stu-id="7b069-123">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b069-124">Accessi non riusciti</span><span class="sxs-lookup"><span data-stu-id="7b069-124">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="7b069-125">Numero totale di errori di accesso endpoint.</span><span class="sxs-lookup"><span data-stu-id="7b069-125">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b069-126">Tentativi di accesso</span><span class="sxs-lookup"><span data-stu-id="7b069-126">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="7b069-127">Numero totale di tentativi di accesso all'endpoint.</span><span class="sxs-lookup"><span data-stu-id="7b069-127">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b069-128">Endpoint disconnessi</span><span class="sxs-lookup"><span data-stu-id="7b069-128">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="7b069-129">Numero totale di endpoint che sono stati disconnessi.</span><span class="sxs-lookup"><span data-stu-id="7b069-129">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7b069-130">**Informazioni sulla presenza**</span><span class="sxs-lookup"><span data-stu-id="7b069-130">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b069-131"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="7b069-131"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="7b069-132"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="7b069-132"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b069-133">Chiamate di sepresenza</span><span class="sxs-lookup"><span data-stu-id="7b069-133">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="7b069-134">Numero totale di tentativi di modifica della presenza.</span><span class="sxs-lookup"><span data-stu-id="7b069-134">Total number of presence change attempts.</span></span> <span data-ttu-id="7b069-135">Per i diversi tipi di modifiche alla presenza, vedere il contatore delle prestazioni chiamate di tipo sepresence (Presence Type).</span><span class="sxs-lookup"><span data-stu-id="7b069-135">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b069-136">Risposte di NNN per la presenza</span><span class="sxs-lookup"><span data-stu-id="7b069-136">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="7b069-137">Numero totale di codici di risposta nnn ricevuti dal server.</span><span class="sxs-lookup"><span data-stu-id="7b069-137">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b069-138">Chiamate GetPresence</span><span class="sxs-lookup"><span data-stu-id="7b069-138">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="7b069-139">Numero totale di tentativi di richiesta di presenza per ottenere.</span><span class="sxs-lookup"><span data-stu-id="7b069-139">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b069-140">Risposte di NNN per GetPresence</span><span class="sxs-lookup"><span data-stu-id="7b069-140">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="7b069-141">Numero totale di codici di risposta nnn ricevuti dal server.</span><span class="sxs-lookup"><span data-stu-id="7b069-141">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7b069-142">**Informazioni sul servizio Rubrica**</span><span class="sxs-lookup"><span data-stu-id="7b069-142">**Address Book service Information**</span></span>

<span data-ttu-id="7b069-143">In questa categoria sono inclusi i contatori utilizzati per monitorare i download di file in ABS (Address Book Service) e le richieste del servizio query Web della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="7b069-143">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b069-144"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="7b069-144"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="7b069-145"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="7b069-145"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b069-146">Download di file in ABS Full/Delta tentati</span><span class="sxs-lookup"><span data-stu-id="7b069-146">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="7b069-147">Numero totale di richieste di download di file completi o Delta tentate.</span><span class="sxs-lookup"><span data-stu-id="7b069-147">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b069-148">Download di file completi/Delta in ABS con esito positivo</span><span class="sxs-lookup"><span data-stu-id="7b069-148">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="7b069-149">Numero totale di richieste di download di file completi o Delta tentate.</span><span class="sxs-lookup"><span data-stu-id="7b069-149">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b069-150">Contatori correlati al servizio query Web della Rubrica</span><span class="sxs-lookup"><span data-stu-id="7b069-150">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="7b069-151">Contatori relativi al download di file della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="7b069-151">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b069-152">Tentativi di WS ABS</span><span class="sxs-lookup"><span data-stu-id="7b069-152">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="7b069-153">Numero totale di richieste del servizio query Web della rubrica tentate.</span><span class="sxs-lookup"><span data-stu-id="7b069-153">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b069-154">Chiamate in ABS WS con esito positivo</span><span class="sxs-lookup"><span data-stu-id="7b069-154">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="7b069-155">Numero totale di richieste del servizio di query Web della rubrica che hanno restituito un codice di risposta corretto.</span><span class="sxs-lookup"><span data-stu-id="7b069-155">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b069-156">Chiamate in ABS WS non riuscite</span><span class="sxs-lookup"><span data-stu-id="7b069-156">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="7b069-157">Numero totale di richieste del servizio di query Web della rubrica che hanno restituito un codice di risposta di errore.</span><span class="sxs-lookup"><span data-stu-id="7b069-157">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7b069-158">**Informazioni sulle liste di distribuzione (DL)**</span><span class="sxs-lookup"><span data-stu-id="7b069-158">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b069-159"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="7b069-159"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="7b069-160"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="7b069-160"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b069-161">Tentativi di chiamata</span><span class="sxs-lookup"><span data-stu-id="7b069-161">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="7b069-162">Numero totale di richieste del servizio Web di espansione della lista di distribuzione (DLX) tentate.</span><span class="sxs-lookup"><span data-stu-id="7b069-162">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b069-163">Chiamate con esito positivo</span><span class="sxs-lookup"><span data-stu-id="7b069-163">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="7b069-164">Numero totale di richieste del servizio Web DLX che hanno restituito un codice di risposta corretto.</span><span class="sxs-lookup"><span data-stu-id="7b069-164">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b069-165">Chiamate non riuscite</span><span class="sxs-lookup"><span data-stu-id="7b069-165">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="7b069-166">Numero totale di richieste del servizio Web DLX che hanno restituito un codice di risposta di errore.</span><span class="sxs-lookup"><span data-stu-id="7b069-166">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7b069-167">**Informazioni di base sul VoIP**</span><span class="sxs-lookup"><span data-stu-id="7b069-167">**VoIP Basic Information**</span></span>

<span data-ttu-id="7b069-168">I contatori delle prestazioni elencati di seguito numeri di rapporto per tutte le chiamate VoIP (Voice over IP), incluse le chiamate a Mediation Server, A/V Conferencing Server, Edge Server, Response Group Application e Conference Auto Attendant, quando questi scenari sono abilitati.</span><span class="sxs-lookup"><span data-stu-id="7b069-168">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b069-169"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="7b069-169"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="7b069-170"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="7b069-170"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b069-171">Chiamate attive</span><span class="sxs-lookup"><span data-stu-id="7b069-171">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="7b069-172">Numero totale di chiamate vocali in ingresso/in uscita attualmente in corso.</span><span class="sxs-lookup"><span data-stu-id="7b069-172">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b069-173">Chiamate terminate</span><span class="sxs-lookup"><span data-stu-id="7b069-173">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="7b069-174">Numero totale di chiamate vocali in ingresso/in uscita già terminate.</span><span class="sxs-lookup"><span data-stu-id="7b069-174">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b069-175">Chiamate rifiutate</span><span class="sxs-lookup"><span data-stu-id="7b069-175">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="7b069-176">Il numero totale di chiamate vocali in ingresso è stato rifiutato.</span><span class="sxs-lookup"><span data-stu-id="7b069-176">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b069-177">Tentativi di chiamata in arrivo/in uscita</span><span class="sxs-lookup"><span data-stu-id="7b069-177">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="7b069-178">Numero totale di chiamate vocali in ingresso/in uscita tentate.</span><span class="sxs-lookup"><span data-stu-id="7b069-178">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b069-179">Chiamate in ingresso/in uscita stabilite</span><span class="sxs-lookup"><span data-stu-id="7b069-179">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="7b069-180">Numero totale di chiamate vocali in ingresso/in uscita stabilite.</span><span class="sxs-lookup"><span data-stu-id="7b069-180">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b069-181">Chiamate NNN ricevute</span><span class="sxs-lookup"><span data-stu-id="7b069-181">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="7b069-182">Numero totale di codici di risposta nnn ricevuti dal server.</span><span class="sxs-lookup"><span data-stu-id="7b069-182">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b069-183">Velocità di passaggio VoIP (%)</span><span class="sxs-lookup"><span data-stu-id="7b069-183">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="7b069-184">Total calls established/Total calls Tented.</span><span class="sxs-lookup"><span data-stu-id="7b069-184">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7b069-185">**Informazioni sulle chiamate di servizio di Response Group**</span><span class="sxs-lookup"><span data-stu-id="7b069-185">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b069-186"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="7b069-186"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="7b069-187"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="7b069-187"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b069-188">Chiamate attive</span><span class="sxs-lookup"><span data-stu-id="7b069-188">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="7b069-189">Numero totale di chiamate attive all'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="7b069-189">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b069-190">Tentativi di chiamata</span><span class="sxs-lookup"><span data-stu-id="7b069-190">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="7b069-191">Numero totale di chiamate tentate.</span><span class="sxs-lookup"><span data-stu-id="7b069-191">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7b069-192">**Informazioni sulle chiamate di messaggistica immediata**</span><span class="sxs-lookup"><span data-stu-id="7b069-192">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b069-193"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="7b069-193"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="7b069-194"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="7b069-194"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b069-195">Chiamate attive</span><span class="sxs-lookup"><span data-stu-id="7b069-195">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="7b069-196">Numero totale di chiamate di messaggistica istantanea in arrivo/in uscita.</span><span class="sxs-lookup"><span data-stu-id="7b069-196">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b069-197">Chiamate terminate</span><span class="sxs-lookup"><span data-stu-id="7b069-197">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="7b069-198">Numero totale di chiamate di messaggistica istantanea in ingresso/in uscita già terminate.</span><span class="sxs-lookup"><span data-stu-id="7b069-198">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b069-199">Chiamate NNN ricevute</span><span class="sxs-lookup"><span data-stu-id="7b069-199">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="7b069-200">Numero totale di codici di risposta nnn ricevuti dal server.</span><span class="sxs-lookup"><span data-stu-id="7b069-200">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b069-201">Messaggi di messaggistica istantanea ricevuti/inviati</span><span class="sxs-lookup"><span data-stu-id="7b069-201">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="7b069-202">Numero totale di messaggi ricevuti o inviati per tutte le sessioni.</span><span class="sxs-lookup"><span data-stu-id="7b069-202">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b069-203">Tentativi di chiamata in arrivo/in uscita</span><span class="sxs-lookup"><span data-stu-id="7b069-203">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="7b069-204">Numero totale di chiamate di messaggistica istantanea in arrivo/in uscita tentate.</span><span class="sxs-lookup"><span data-stu-id="7b069-204">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b069-205">Chiamate in ingresso/in uscita stabilite</span><span class="sxs-lookup"><span data-stu-id="7b069-205">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="7b069-206">Numero totale di chiamate di messaggi istantanei in arrivo/in uscita stabilite.</span><span class="sxs-lookup"><span data-stu-id="7b069-206">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7b069-207">**Informazioni sulle chiamate di condivisione delle app**</span><span class="sxs-lookup"><span data-stu-id="7b069-207">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b069-208"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="7b069-208"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="7b069-209"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="7b069-209"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b069-210">Chiamate attive</span><span class="sxs-lookup"><span data-stu-id="7b069-210">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="7b069-211">Numero totale di chiamate di condivisione delle applicazioni in arrivo/in uscita.</span><span class="sxs-lookup"><span data-stu-id="7b069-211">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b069-212">Chiamate terminate</span><span class="sxs-lookup"><span data-stu-id="7b069-212">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="7b069-213">Numero totale di chiamate di condivisione applicazioni in ingresso/in uscita già terminate.</span><span class="sxs-lookup"><span data-stu-id="7b069-213">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b069-214">Chiamate NNN ricevute</span><span class="sxs-lookup"><span data-stu-id="7b069-214">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="7b069-215">Numero totale di codici di risposta nnn ricevuti dal server.</span><span class="sxs-lookup"><span data-stu-id="7b069-215">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b069-216">Tentativi di chiamata in arrivo/in uscita</span><span class="sxs-lookup"><span data-stu-id="7b069-216">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="7b069-217">Numero totale di chiamate di condivisione applicazioni in ingresso/in uscita tentate.</span><span class="sxs-lookup"><span data-stu-id="7b069-217">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b069-218">Chiamate in ingresso/in uscita stabilite</span><span class="sxs-lookup"><span data-stu-id="7b069-218">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="7b069-219">Numero totale di chiamate di condivisione delle applicazioni in ingresso/in uscita stabilite.</span><span class="sxs-lookup"><span data-stu-id="7b069-219">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7b069-220">**Informazioni sulle chiamate CAA**</span><span class="sxs-lookup"><span data-stu-id="7b069-220">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b069-221"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="7b069-221"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="7b069-222"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="7b069-222"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b069-223">Chiamate attive</span><span class="sxs-lookup"><span data-stu-id="7b069-223">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="7b069-224">Numero totale di chiamate PSTN (Public Switched Telephone Network) in ingresso/in uscita attualmente in corso.</span><span class="sxs-lookup"><span data-stu-id="7b069-224">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b069-225">Chiamate terminate</span><span class="sxs-lookup"><span data-stu-id="7b069-225">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="7b069-226">Numero totale di chiamate PSTN in ingresso/in uscita già terminate.</span><span class="sxs-lookup"><span data-stu-id="7b069-226">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b069-227">Tentativi di chiamata in arrivo/in uscita</span><span class="sxs-lookup"><span data-stu-id="7b069-227">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="7b069-228">Numero totale di chiamate PSTN in ingresso/in uscita tentate.</span><span class="sxs-lookup"><span data-stu-id="7b069-228">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b069-229">Chiamate in ingresso/in uscita stabilite</span><span class="sxs-lookup"><span data-stu-id="7b069-229">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="7b069-230">Numero totale di chiamate PSTN in ingresso/in uscita stabilite.</span><span class="sxs-lookup"><span data-stu-id="7b069-230">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7b069-231">**Informazioni sulla conferenza**</span><span class="sxs-lookup"><span data-stu-id="7b069-231">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b069-232"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="7b069-232"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="7b069-233"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="7b069-233"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b069-234">Conferenze di messaggistica istantanea attive</span><span class="sxs-lookup"><span data-stu-id="7b069-234">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="7b069-235">Numero totale di conferenze di messaggistica istantanea in continuo.</span><span class="sxs-lookup"><span data-stu-id="7b069-235">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b069-236">Conferenze audio/video attive</span><span class="sxs-lookup"><span data-stu-id="7b069-236">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="7b069-237">Numero totale di conferenze audio/video (A/V) in uscita.</span><span class="sxs-lookup"><span data-stu-id="7b069-237">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b069-238">Conferenze di condivisione applicazioni attive</span><span class="sxs-lookup"><span data-stu-id="7b069-238">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="7b069-239">Numero totale di conferenze di condivisione applicazioni in uscita.</span><span class="sxs-lookup"><span data-stu-id="7b069-239">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b069-240">Numero di partecipanti</span><span class="sxs-lookup"><span data-stu-id="7b069-240">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="7b069-241">Numero totale di partecipanti attualmente connessi a conferenze.</span><span class="sxs-lookup"><span data-stu-id="7b069-241">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b069-242">Errore della pianificazione delle conferenze</span><span class="sxs-lookup"><span data-stu-id="7b069-242">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="7b069-243">Numero totale di errori durante il tentativo di pianificazione di una conferenza.</span><span class="sxs-lookup"><span data-stu-id="7b069-243">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b069-244">Partecipare a una conferenza non riuscita</span><span class="sxs-lookup"><span data-stu-id="7b069-244">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="7b069-245">Numero totale di errori durante il tentativo di connessione a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="7b069-245">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7b069-246">**Contatori client di UCWA**</span><span class="sxs-lookup"><span data-stu-id="7b069-246">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b069-247"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="7b069-247"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="7b069-248"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="7b069-248"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b069-249">Numero totale di join IMMCU con esito positivo</span><span class="sxs-lookup"><span data-stu-id="7b069-249">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="7b069-250">Numero totale di conferenze di messaggistica istantanea Unite.</span><span class="sxs-lookup"><span data-stu-id="7b069-250">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b069-251">Numero totale di join DMCU con esito positivo</span><span class="sxs-lookup"><span data-stu-id="7b069-251">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="7b069-252">Numero totale di conferenze A/V Unite.</span><span class="sxs-lookup"><span data-stu-id="7b069-252">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

