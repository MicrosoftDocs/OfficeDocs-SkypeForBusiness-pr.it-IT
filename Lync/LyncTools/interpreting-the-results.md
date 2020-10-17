---
title: Interpretazione dei risultati
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
ms.openlocfilehash: f3a15880de861b850d3e0355491e85219ba3579d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499913"
---
# <a name="interpreting-the-results"></a><span data-ttu-id="c881c-102">Interpretazione dei risultati</span><span class="sxs-lookup"><span data-stu-id="c881c-102">Interpreting the Results</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c881c-103">_**Ultimo argomento modificato:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="c881c-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="c881c-104">Lo strumento di stress e prestazioni di Lync Server 2013 (LyncPerfTool.exe) dispone di numerosi contatori che è possibile utilizzare per comprendere le operazioni eseguite dal client e l'eventuale presenza di problemi.</span><span class="sxs-lookup"><span data-stu-id="c881c-104">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="c881c-105">Contatori client</span><span class="sxs-lookup"><span data-stu-id="c881c-105">Client Counters</span></span>

<span data-ttu-id="c881c-106">Ogni istanza di LyncPerfTool.exe in esecuzione ha un'istanza separata dei contatori.</span><span class="sxs-lookup"><span data-stu-id="c881c-106">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="c881c-107">Ogni istanza è denominata dal relativo ID di processo.</span><span class="sxs-lookup"><span data-stu-id="c881c-107">Each instance is named by its process ID.</span></span>

<span data-ttu-id="c881c-108">Se i client sono sovraccarichi, è possibile che si verifichino problemi.</span><span class="sxs-lookup"><span data-stu-id="c881c-108">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="c881c-109">Per evitare questi problemi, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c881c-109">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="c881c-110">Monitorare la CPU e l'utilizzo della memoria nei computer client.</span><span class="sxs-lookup"><span data-stu-id="c881c-110">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="c881c-111">Se la CPU è costantemente al di sopra del 90%, ridurre il numero di utenti.</span><span class="sxs-lookup"><span data-stu-id="c881c-111">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="c881c-112">Se l'ingombro della memoria è elevato, è possibile che si verifichino problemi se il file di paging non è abbastanza grande.</span><span class="sxs-lookup"><span data-stu-id="c881c-112">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="c881c-113">Verificare che la carica di commit non colpisca il limite del computer.</span><span class="sxs-lookup"><span data-stu-id="c881c-113">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="c881c-114">Se si esegue in limiti di memoria, è consigliabile aumentare le dimensioni del file di paging o ridurre il numero di utenti</span><span class="sxs-lookup"><span data-stu-id="c881c-114">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="c881c-115">Nelle tabelle riportate di seguito sono elencati i contatori delle prestazioni principali di LyncPerfTool.</span><span class="sxs-lookup"><span data-stu-id="c881c-115">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="c881c-116">**Informazioni generali**</span><span class="sxs-lookup"><span data-stu-id="c881c-116">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c881c-117"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="c881c-117"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="c881c-118"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="c881c-118"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c881c-119">Tempo impiegato in minuti</span><span class="sxs-lookup"><span data-stu-id="c881c-119">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="c881c-120">Tempo trascorso dopo l'avvio del processo.</span><span class="sxs-lookup"><span data-stu-id="c881c-120">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c881c-121">Endpoint attivi</span><span class="sxs-lookup"><span data-stu-id="c881c-121">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="c881c-122">Numero di endpoint attualmente connessi al server.</span><span class="sxs-lookup"><span data-stu-id="c881c-122">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c881c-123">Accessi non riusciti</span><span class="sxs-lookup"><span data-stu-id="c881c-123">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="c881c-124">Numero totale di errori di accesso endpoint.</span><span class="sxs-lookup"><span data-stu-id="c881c-124">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c881c-125">Tentativi di accesso</span><span class="sxs-lookup"><span data-stu-id="c881c-125">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="c881c-126">Numero totale di tentativi di accesso all'endpoint.</span><span class="sxs-lookup"><span data-stu-id="c881c-126">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c881c-127">Endpoint disconnessi</span><span class="sxs-lookup"><span data-stu-id="c881c-127">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="c881c-128">Numero totale di endpoint che sono stati disconnessi.</span><span class="sxs-lookup"><span data-stu-id="c881c-128">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c881c-129">**Informazioni sulla presenza**</span><span class="sxs-lookup"><span data-stu-id="c881c-129">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c881c-130"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="c881c-130"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="c881c-131"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="c881c-131"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c881c-132">Chiamate di sepresenza</span><span class="sxs-lookup"><span data-stu-id="c881c-132">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="c881c-133">Numero totale di tentativi di modifica della presenza.</span><span class="sxs-lookup"><span data-stu-id="c881c-133">Total number of presence change attempts.</span></span> <span data-ttu-id="c881c-134">Per i diversi tipi di modifiche alla presenza, vedere il contatore delle prestazioni chiamate di tipo sepresence (Presence Type).</span><span class="sxs-lookup"><span data-stu-id="c881c-134">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c881c-135">Risposte di NNN per la presenza</span><span class="sxs-lookup"><span data-stu-id="c881c-135">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="c881c-136">Numero totale di codici di risposta nnn ricevuti dal server.</span><span class="sxs-lookup"><span data-stu-id="c881c-136">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c881c-137">Chiamate GetPresence</span><span class="sxs-lookup"><span data-stu-id="c881c-137">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="c881c-138">Numero totale di tentativi di richiesta di presenza per ottenere.</span><span class="sxs-lookup"><span data-stu-id="c881c-138">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c881c-139">Risposte di NNN per GetPresence</span><span class="sxs-lookup"><span data-stu-id="c881c-139">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="c881c-140">Numero totale di codici di risposta nnn ricevuti dal server.</span><span class="sxs-lookup"><span data-stu-id="c881c-140">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c881c-141">**Informazioni sul servizio Rubrica**</span><span class="sxs-lookup"><span data-stu-id="c881c-141">**Address Book service Information**</span></span>

<span data-ttu-id="c881c-142">In questa categoria sono inclusi i contatori utilizzati per monitorare i download di file in ABS (Address Book Service) e le richieste del servizio query Web della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="c881c-142">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c881c-143"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="c881c-143"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="c881c-144"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="c881c-144"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c881c-145">Download di file in ABS Full/Delta tentati</span><span class="sxs-lookup"><span data-stu-id="c881c-145">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="c881c-146">Numero totale di richieste di download di file completi o Delta tentate.</span><span class="sxs-lookup"><span data-stu-id="c881c-146">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c881c-147">Download di file completi/Delta in ABS con esito positivo</span><span class="sxs-lookup"><span data-stu-id="c881c-147">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="c881c-148">Numero totale di richieste di download di file completi o Delta tentate.</span><span class="sxs-lookup"><span data-stu-id="c881c-148">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c881c-149">Contatori correlati al servizio query Web della Rubrica</span><span class="sxs-lookup"><span data-stu-id="c881c-149">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="c881c-150">Contatori relativi al download di file della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="c881c-150">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c881c-151">Tentativi di WS ABS</span><span class="sxs-lookup"><span data-stu-id="c881c-151">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="c881c-152">Numero totale di richieste del servizio query Web della rubrica tentate.</span><span class="sxs-lookup"><span data-stu-id="c881c-152">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c881c-153">Chiamate in ABS WS con esito positivo</span><span class="sxs-lookup"><span data-stu-id="c881c-153">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="c881c-154">Numero totale di richieste del servizio di query Web della rubrica che hanno restituito un codice di risposta corretto.</span><span class="sxs-lookup"><span data-stu-id="c881c-154">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c881c-155">Chiamate in ABS WS non riuscite</span><span class="sxs-lookup"><span data-stu-id="c881c-155">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="c881c-156">Numero totale di richieste del servizio di query Web della rubrica che hanno restituito un codice di risposta di errore.</span><span class="sxs-lookup"><span data-stu-id="c881c-156">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c881c-157">**Informazioni sulle liste di distribuzione (DL)**</span><span class="sxs-lookup"><span data-stu-id="c881c-157">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c881c-158"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="c881c-158"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="c881c-159"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="c881c-159"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c881c-160">Tentativi di chiamata</span><span class="sxs-lookup"><span data-stu-id="c881c-160">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="c881c-161">Numero totale di richieste del servizio Web di espansione della lista di distribuzione (DLX) tentate.</span><span class="sxs-lookup"><span data-stu-id="c881c-161">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c881c-162">Chiamate con esito positivo</span><span class="sxs-lookup"><span data-stu-id="c881c-162">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="c881c-163">Numero totale di richieste del servizio Web DLX che hanno restituito un codice di risposta corretto.</span><span class="sxs-lookup"><span data-stu-id="c881c-163">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c881c-164">Chiamate non riuscite</span><span class="sxs-lookup"><span data-stu-id="c881c-164">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="c881c-165">Numero totale di richieste del servizio Web DLX che hanno restituito un codice di risposta di errore.</span><span class="sxs-lookup"><span data-stu-id="c881c-165">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c881c-166">**Informazioni di base sul VoIP**</span><span class="sxs-lookup"><span data-stu-id="c881c-166">**VoIP Basic Information**</span></span>

<span data-ttu-id="c881c-167">I contatori delle prestazioni elencati di seguito numeri di rapporto per tutte le chiamate VoIP (Voice over IP), incluse le chiamate a Mediation Server, A/V Conferencing Server, Edge Server, Response Group Application e Conference Auto Attendant, quando questi scenari sono abilitati.</span><span class="sxs-lookup"><span data-stu-id="c881c-167">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c881c-168"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="c881c-168"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="c881c-169"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="c881c-169"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c881c-170">Chiamate attive</span><span class="sxs-lookup"><span data-stu-id="c881c-170">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="c881c-171">Numero totale di chiamate vocali in ingresso/in uscita attualmente in corso.</span><span class="sxs-lookup"><span data-stu-id="c881c-171">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c881c-172">Chiamate terminate</span><span class="sxs-lookup"><span data-stu-id="c881c-172">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="c881c-173">Numero totale di chiamate vocali in ingresso/in uscita già terminate.</span><span class="sxs-lookup"><span data-stu-id="c881c-173">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c881c-174">Chiamate rifiutate</span><span class="sxs-lookup"><span data-stu-id="c881c-174">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="c881c-175">Il numero totale di chiamate vocali in ingresso è stato rifiutato.</span><span class="sxs-lookup"><span data-stu-id="c881c-175">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c881c-176">Tentativi di chiamata in arrivo/in uscita</span><span class="sxs-lookup"><span data-stu-id="c881c-176">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="c881c-177">Numero totale di chiamate vocali in ingresso/in uscita tentate.</span><span class="sxs-lookup"><span data-stu-id="c881c-177">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c881c-178">Chiamate in ingresso/in uscita stabilite</span><span class="sxs-lookup"><span data-stu-id="c881c-178">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="c881c-179">Numero totale di chiamate vocali in ingresso/in uscita stabilite.</span><span class="sxs-lookup"><span data-stu-id="c881c-179">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c881c-180">Chiamate NNN ricevute</span><span class="sxs-lookup"><span data-stu-id="c881c-180">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="c881c-181">Numero totale di codici di risposta nnn ricevuti dal server.</span><span class="sxs-lookup"><span data-stu-id="c881c-181">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c881c-182">Velocità di passaggio VoIP (%)</span><span class="sxs-lookup"><span data-stu-id="c881c-182">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="c881c-183">Total calls established/Total calls Tented.</span><span class="sxs-lookup"><span data-stu-id="c881c-183">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c881c-184">**Informazioni sulle chiamate di servizio di Response Group**</span><span class="sxs-lookup"><span data-stu-id="c881c-184">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c881c-185"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="c881c-185"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="c881c-186"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="c881c-186"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c881c-187">Chiamate attive</span><span class="sxs-lookup"><span data-stu-id="c881c-187">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="c881c-188">Numero totale di chiamate attive all'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="c881c-188">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c881c-189">Tentativi di chiamata</span><span class="sxs-lookup"><span data-stu-id="c881c-189">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="c881c-190">Numero totale di chiamate tentate.</span><span class="sxs-lookup"><span data-stu-id="c881c-190">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c881c-191">**Informazioni sulle chiamate di messaggistica immediata**</span><span class="sxs-lookup"><span data-stu-id="c881c-191">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c881c-192"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="c881c-192"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="c881c-193"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="c881c-193"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c881c-194">Chiamate attive</span><span class="sxs-lookup"><span data-stu-id="c881c-194">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="c881c-195">Numero totale di chiamate di messaggistica istantanea in arrivo/in uscita.</span><span class="sxs-lookup"><span data-stu-id="c881c-195">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c881c-196">Chiamate terminate</span><span class="sxs-lookup"><span data-stu-id="c881c-196">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="c881c-197">Numero totale di chiamate di messaggistica istantanea in ingresso/in uscita già terminate.</span><span class="sxs-lookup"><span data-stu-id="c881c-197">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c881c-198">Chiamate NNN ricevute</span><span class="sxs-lookup"><span data-stu-id="c881c-198">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="c881c-199">Numero totale di codici di risposta nnn ricevuti dal server.</span><span class="sxs-lookup"><span data-stu-id="c881c-199">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c881c-200">Messaggi di messaggistica istantanea ricevuti/inviati</span><span class="sxs-lookup"><span data-stu-id="c881c-200">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="c881c-201">Numero totale di messaggi ricevuti o inviati per tutte le sessioni.</span><span class="sxs-lookup"><span data-stu-id="c881c-201">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c881c-202">Tentativi di chiamata in arrivo/in uscita</span><span class="sxs-lookup"><span data-stu-id="c881c-202">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="c881c-203">Numero totale di chiamate di messaggistica istantanea in arrivo/in uscita tentate.</span><span class="sxs-lookup"><span data-stu-id="c881c-203">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c881c-204">Chiamate in ingresso/in uscita stabilite</span><span class="sxs-lookup"><span data-stu-id="c881c-204">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="c881c-205">Numero totale di chiamate di messaggi istantanei in arrivo/in uscita stabilite.</span><span class="sxs-lookup"><span data-stu-id="c881c-205">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c881c-206">**Informazioni sulle chiamate di condivisione delle app**</span><span class="sxs-lookup"><span data-stu-id="c881c-206">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c881c-207"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="c881c-207"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="c881c-208"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="c881c-208"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c881c-209">Chiamate attive</span><span class="sxs-lookup"><span data-stu-id="c881c-209">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="c881c-210">Numero totale di chiamate di condivisione delle applicazioni in arrivo/in uscita.</span><span class="sxs-lookup"><span data-stu-id="c881c-210">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c881c-211">Chiamate terminate</span><span class="sxs-lookup"><span data-stu-id="c881c-211">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="c881c-212">Numero totale di chiamate di condivisione applicazioni in ingresso/in uscita già terminate.</span><span class="sxs-lookup"><span data-stu-id="c881c-212">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c881c-213">Chiamate NNN ricevute</span><span class="sxs-lookup"><span data-stu-id="c881c-213">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="c881c-214">Numero totale di codici di risposta nnn ricevuti dal server.</span><span class="sxs-lookup"><span data-stu-id="c881c-214">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c881c-215">Tentativi di chiamata in arrivo/in uscita</span><span class="sxs-lookup"><span data-stu-id="c881c-215">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="c881c-216">Numero totale di chiamate di condivisione applicazioni in ingresso/in uscita tentate.</span><span class="sxs-lookup"><span data-stu-id="c881c-216">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c881c-217">Chiamate in ingresso/in uscita stabilite</span><span class="sxs-lookup"><span data-stu-id="c881c-217">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="c881c-218">Numero totale di chiamate di condivisione delle applicazioni in ingresso/in uscita stabilite.</span><span class="sxs-lookup"><span data-stu-id="c881c-218">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c881c-219">**Informazioni sulle chiamate CAA**</span><span class="sxs-lookup"><span data-stu-id="c881c-219">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c881c-220"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="c881c-220"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="c881c-221"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="c881c-221"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c881c-222">Chiamate attive</span><span class="sxs-lookup"><span data-stu-id="c881c-222">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="c881c-223">Numero totale di chiamate PSTN (Public Switched Telephone Network) in ingresso/in uscita attualmente in corso.</span><span class="sxs-lookup"><span data-stu-id="c881c-223">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c881c-224">Chiamate terminate</span><span class="sxs-lookup"><span data-stu-id="c881c-224">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="c881c-225">Numero totale di chiamate PSTN in ingresso/in uscita già terminate.</span><span class="sxs-lookup"><span data-stu-id="c881c-225">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c881c-226">Tentativi di chiamata in arrivo/in uscita</span><span class="sxs-lookup"><span data-stu-id="c881c-226">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="c881c-227">Numero totale di chiamate PSTN in ingresso/in uscita tentate.</span><span class="sxs-lookup"><span data-stu-id="c881c-227">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c881c-228">Chiamate in ingresso/in uscita stabilite</span><span class="sxs-lookup"><span data-stu-id="c881c-228">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="c881c-229">Numero totale di chiamate PSTN in ingresso/in uscita stabilite.</span><span class="sxs-lookup"><span data-stu-id="c881c-229">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c881c-230">**Informazioni sulla conferenza**</span><span class="sxs-lookup"><span data-stu-id="c881c-230">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c881c-231"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="c881c-231"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="c881c-232"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="c881c-232"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c881c-233">Conferenze di messaggistica istantanea attive</span><span class="sxs-lookup"><span data-stu-id="c881c-233">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="c881c-234">Numero totale di conferenze di messaggistica istantanea in continuo.</span><span class="sxs-lookup"><span data-stu-id="c881c-234">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c881c-235">Conferenze audio/video attive</span><span class="sxs-lookup"><span data-stu-id="c881c-235">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="c881c-236">Numero totale di conferenze audio/video (A/V) in uscita.</span><span class="sxs-lookup"><span data-stu-id="c881c-236">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c881c-237">Conferenze di condivisione applicazioni attive</span><span class="sxs-lookup"><span data-stu-id="c881c-237">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="c881c-238">Numero totale di conferenze di condivisione applicazioni in uscita.</span><span class="sxs-lookup"><span data-stu-id="c881c-238">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c881c-239">Numero di partecipanti</span><span class="sxs-lookup"><span data-stu-id="c881c-239">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="c881c-240">Numero totale di partecipanti attualmente connessi a conferenze.</span><span class="sxs-lookup"><span data-stu-id="c881c-240">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c881c-241">Errore della pianificazione delle conferenze</span><span class="sxs-lookup"><span data-stu-id="c881c-241">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="c881c-242">Numero totale di errori durante il tentativo di pianificazione di una conferenza.</span><span class="sxs-lookup"><span data-stu-id="c881c-242">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c881c-243">Partecipare a una conferenza non riuscita</span><span class="sxs-lookup"><span data-stu-id="c881c-243">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="c881c-244">Numero totale di errori durante il tentativo di connessione a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="c881c-244">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c881c-245">**Contatori client di UCWA**</span><span class="sxs-lookup"><span data-stu-id="c881c-245">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c881c-246"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="c881c-246"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="c881c-247"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="c881c-247"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c881c-248">Numero totale di join IMMCU con esito positivo</span><span class="sxs-lookup"><span data-stu-id="c881c-248">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="c881c-249">Numero totale di conferenze di messaggistica istantanea Unite.</span><span class="sxs-lookup"><span data-stu-id="c881c-249">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c881c-250">Numero totale di join DMCU con esito positivo</span><span class="sxs-lookup"><span data-stu-id="c881c-250">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="c881c-251">Numero totale di conferenze A/V Unite.</span><span class="sxs-lookup"><span data-stu-id="c881c-251">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

