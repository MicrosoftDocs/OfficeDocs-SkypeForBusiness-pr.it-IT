---
title: Interpretazione dei risultati
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 484f10757dcbd1463b54cf70ac8d725402decb44
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a><span data-ttu-id="5e7fe-102">Interpretazione dei risultati</span><span class="sxs-lookup"><span data-stu-id="5e7fe-102">Interpreting the Results</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e7fe-103">_**Ultimo argomento modificato:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="5e7fe-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="5e7fe-104">Lo strumento Lync Server 2013 stress and performance (LyncPerfTool. exe) dispone di numerosi contatori che è possibile utilizzare per capire cosa sta facendo il client e se si verificano problemi.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-104">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="5e7fe-105">Contatori client</span><span class="sxs-lookup"><span data-stu-id="5e7fe-105">Client Counters</span></span>

<span data-ttu-id="5e7fe-106">Ogni istanza di LyncPerfTool. exe in esecuzione dispone di un'istanza distinta dei contatori.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-106">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="5e7fe-107">Ogni istanza è denominata dal relativo ID di processo.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-107">Each instance is named by its process ID.</span></span>

<span data-ttu-id="5e7fe-108">Se i client sono sovraccarichi, è possibile che si verifichino problemi.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-108">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="5e7fe-109">Per evitare questi problemi, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e7fe-109">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="5e7fe-110">Monitorare la CPU e l'utilizzo della memoria nei computer client.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-110">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="5e7fe-111">Se la CPU è costantemente al di sopra del 90%, ridurre il numero di utenti.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-111">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="5e7fe-112">Se l'ingombro della memoria è elevato, è possibile che si verifichino problemi se il file di paging non è abbastanza grande.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-112">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="5e7fe-113">Verificare che la carica di commit non colpisca il limite del computer.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-113">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="5e7fe-114">Se si esegue in limiti di memoria, è consigliabile aumentare le dimensioni del file di paging o ridurre il numero di utenti</span><span class="sxs-lookup"><span data-stu-id="5e7fe-114">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="5e7fe-115">Nelle tabelle riportate di seguito sono elencati i contatori delle prestazioni principali di LyncPerfTool.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-115">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="5e7fe-116">**Informazioni generali**</span><span class="sxs-lookup"><span data-stu-id="5e7fe-116">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e7fe-117"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="5e7fe-117"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5e7fe-118"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="5e7fe-118"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e7fe-119">Tempo impiegato in minuti</span><span class="sxs-lookup"><span data-stu-id="5e7fe-119">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-120">Tempo trascorso dopo l'avvio del processo.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-120">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7fe-121">Endpoint attivi</span><span class="sxs-lookup"><span data-stu-id="5e7fe-121">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-122">Numero di endpoint attualmente connessi al server.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-122">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7fe-123">Accessi non riusciti</span><span class="sxs-lookup"><span data-stu-id="5e7fe-123">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-124">Numero totale di errori di accesso endpoint.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-124">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7fe-125">Tentativi di accesso</span><span class="sxs-lookup"><span data-stu-id="5e7fe-125">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-126">Numero totale di tentativi di accesso all'endpoint.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-126">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7fe-127">Endpoint disconnessi</span><span class="sxs-lookup"><span data-stu-id="5e7fe-127">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-128">Numero totale di endpoint che sono stati disconnessi.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-128">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5e7fe-129">**Informazioni sulla presenza**</span><span class="sxs-lookup"><span data-stu-id="5e7fe-129">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e7fe-130"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="5e7fe-130"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5e7fe-131"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="5e7fe-131"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e7fe-132">Chiamate di sepresenza</span><span class="sxs-lookup"><span data-stu-id="5e7fe-132">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-133">Numero totale di tentativi di modifica della presenza.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-133">Total number of presence change attempts.</span></span> <span data-ttu-id="5e7fe-134">Per i diversi tipi di modifiche alla presenza, vedere il contatore delle prestazioni chiamate di tipo sepresence (Presence Type).</span><span class="sxs-lookup"><span data-stu-id="5e7fe-134">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7fe-135">Risposte di NNN per la presenza</span><span class="sxs-lookup"><span data-stu-id="5e7fe-135">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-136">Numero totale di codici di risposta nnn ricevuti dal server.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-136">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7fe-137">Chiamate GetPresence</span><span class="sxs-lookup"><span data-stu-id="5e7fe-137">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-138">Numero totale di tentativi di richiesta di presenza per ottenere.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-138">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7fe-139">Risposte di NNN per GetPresence</span><span class="sxs-lookup"><span data-stu-id="5e7fe-139">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-140">Numero totale di codici di risposta nnn ricevuti dal server.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-140">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5e7fe-141">**Informazioni sul servizio Rubrica**</span><span class="sxs-lookup"><span data-stu-id="5e7fe-141">**Address Book service Information**</span></span>

<span data-ttu-id="5e7fe-142">In questa categoria sono inclusi i contatori utilizzati per monitorare i download di file in ABS (Address Book Service) e le richieste del servizio query Web della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-142">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e7fe-143"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="5e7fe-143"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5e7fe-144"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="5e7fe-144"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e7fe-145">Download di file in ABS Full/Delta tentati</span><span class="sxs-lookup"><span data-stu-id="5e7fe-145">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-146">Numero totale di richieste di download di file completi o Delta tentate.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-146">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7fe-147">Download di file completi/Delta in ABS con esito positivo</span><span class="sxs-lookup"><span data-stu-id="5e7fe-147">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-148">Numero totale di richieste di download di file completi o Delta tentate.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-148">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7fe-149">Contatori correlati al servizio query Web della Rubrica</span><span class="sxs-lookup"><span data-stu-id="5e7fe-149">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-150">Contatori relativi al download di file della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-150">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7fe-151">Tentativi di WS ABS</span><span class="sxs-lookup"><span data-stu-id="5e7fe-151">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-152">Numero totale di richieste del servizio query Web della rubrica tentate.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-152">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7fe-153">Chiamate in ABS WS con esito positivo</span><span class="sxs-lookup"><span data-stu-id="5e7fe-153">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-154">Numero totale di richieste del servizio di query Web della rubrica che hanno restituito un codice di risposta corretto.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-154">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7fe-155">Chiamate in ABS WS non riuscite</span><span class="sxs-lookup"><span data-stu-id="5e7fe-155">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-156">Numero totale di richieste del servizio di query Web della rubrica che hanno restituito un codice di risposta di errore.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-156">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5e7fe-157">**Informazioni sulle liste di distribuzione (DL)**</span><span class="sxs-lookup"><span data-stu-id="5e7fe-157">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e7fe-158"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="5e7fe-158"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5e7fe-159"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="5e7fe-159"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e7fe-160">Tentativi di chiamata</span><span class="sxs-lookup"><span data-stu-id="5e7fe-160">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-161">Numero totale di richieste del servizio Web di espansione della lista di distribuzione (DLX) tentate.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-161">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7fe-162">Chiamate con esito positivo</span><span class="sxs-lookup"><span data-stu-id="5e7fe-162">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-163">Numero totale di richieste del servizio Web DLX che hanno restituito un codice di risposta corretto.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-163">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7fe-164">Chiamate non riuscite</span><span class="sxs-lookup"><span data-stu-id="5e7fe-164">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-165">Numero totale di richieste del servizio Web DLX che hanno restituito un codice di risposta di errore.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-165">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5e7fe-166">**Informazioni di base sul VoIP**</span><span class="sxs-lookup"><span data-stu-id="5e7fe-166">**VoIP Basic Information**</span></span>

<span data-ttu-id="5e7fe-167">I contatori delle prestazioni elencati di seguito numeri di rapporto per tutte le chiamate VoIP (Voice over IP), incluse le chiamate a Mediation Server, A/V Conferencing Server, Edge Server, Response Group Application e Conference Auto Attendant, quando questi scenari sono abilitati.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-167">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e7fe-168"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="5e7fe-168"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5e7fe-169"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="5e7fe-169"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e7fe-170">Chiamate attive</span><span class="sxs-lookup"><span data-stu-id="5e7fe-170">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-171">Numero totale di chiamate vocali in ingresso/in uscita attualmente in corso.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-171">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7fe-172">Chiamate terminate</span><span class="sxs-lookup"><span data-stu-id="5e7fe-172">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-173">Numero totale di chiamate vocali in ingresso/in uscita già terminate.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-173">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7fe-174">Chiamate rifiutate</span><span class="sxs-lookup"><span data-stu-id="5e7fe-174">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-175">Il numero totale di chiamate vocali in ingresso è stato rifiutato.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-175">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7fe-176">Tentativi di chiamata in arrivo/in uscita</span><span class="sxs-lookup"><span data-stu-id="5e7fe-176">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-177">Numero totale di chiamate vocali in ingresso/in uscita tentate.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-177">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7fe-178">Chiamate in ingresso/in uscita stabilite</span><span class="sxs-lookup"><span data-stu-id="5e7fe-178">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-179">Numero totale di chiamate vocali in ingresso/in uscita stabilite.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-179">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7fe-180">Chiamate NNN ricevute</span><span class="sxs-lookup"><span data-stu-id="5e7fe-180">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-181">Numero totale di codici di risposta nnn ricevuti dal server.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-181">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7fe-182">Velocità di passaggio VoIP (%)</span><span class="sxs-lookup"><span data-stu-id="5e7fe-182">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-183">Total calls established/Total calls Tented.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-183">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5e7fe-184">**Informazioni sulle chiamate di servizio di Response Group**</span><span class="sxs-lookup"><span data-stu-id="5e7fe-184">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e7fe-185"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="5e7fe-185"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5e7fe-186"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="5e7fe-186"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e7fe-187">Chiamate attive</span><span class="sxs-lookup"><span data-stu-id="5e7fe-187">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-188">Numero totale di chiamate attive all'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-188">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7fe-189">Tentativi di chiamata</span><span class="sxs-lookup"><span data-stu-id="5e7fe-189">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-190">Numero totale di chiamate tentate.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-190">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5e7fe-191">**Informazioni sulle chiamate di messaggistica immediata**</span><span class="sxs-lookup"><span data-stu-id="5e7fe-191">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e7fe-192"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="5e7fe-192"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5e7fe-193"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="5e7fe-193"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e7fe-194">Chiamate attive</span><span class="sxs-lookup"><span data-stu-id="5e7fe-194">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-195">Numero totale di chiamate di messaggistica istantanea in arrivo/in uscita.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-195">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7fe-196">Chiamate terminate</span><span class="sxs-lookup"><span data-stu-id="5e7fe-196">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-197">Numero totale di chiamate di messaggistica istantanea in ingresso/in uscita già terminate.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-197">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7fe-198">Chiamate NNN ricevute</span><span class="sxs-lookup"><span data-stu-id="5e7fe-198">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-199">Numero totale di codici di risposta nnn ricevuti dal server.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-199">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7fe-200">Messaggi di messaggistica istantanea ricevuti/inviati</span><span class="sxs-lookup"><span data-stu-id="5e7fe-200">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-201">Numero totale di messaggi ricevuti o inviati per tutte le sessioni.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-201">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7fe-202">Tentativi di chiamata in arrivo/in uscita</span><span class="sxs-lookup"><span data-stu-id="5e7fe-202">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-203">Numero totale di chiamate di messaggistica istantanea in arrivo/in uscita tentate.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-203">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7fe-204">Chiamate in ingresso/in uscita stabilite</span><span class="sxs-lookup"><span data-stu-id="5e7fe-204">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-205">Numero totale di chiamate di messaggi istantanei in arrivo/in uscita stabilite.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-205">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5e7fe-206">**Informazioni sulle chiamate di condivisione delle app**</span><span class="sxs-lookup"><span data-stu-id="5e7fe-206">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e7fe-207"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="5e7fe-207"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5e7fe-208"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="5e7fe-208"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e7fe-209">Chiamate attive</span><span class="sxs-lookup"><span data-stu-id="5e7fe-209">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-210">Numero totale di chiamate di condivisione delle applicazioni in arrivo/in uscita.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-210">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7fe-211">Chiamate terminate</span><span class="sxs-lookup"><span data-stu-id="5e7fe-211">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-212">Numero totale di chiamate di condivisione applicazioni in ingresso/in uscita già terminate.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-212">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7fe-213">Chiamate NNN ricevute</span><span class="sxs-lookup"><span data-stu-id="5e7fe-213">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-214">Numero totale di codici di risposta nnn ricevuti dal server.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-214">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7fe-215">Tentativi di chiamata in arrivo/in uscita</span><span class="sxs-lookup"><span data-stu-id="5e7fe-215">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-216">Numero totale di chiamate di condivisione applicazioni in ingresso/in uscita tentate.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-216">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7fe-217">Chiamate in ingresso/in uscita stabilite</span><span class="sxs-lookup"><span data-stu-id="5e7fe-217">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-218">Numero totale di chiamate di condivisione delle applicazioni in ingresso/in uscita stabilite.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-218">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5e7fe-219">**Informazioni sulle chiamate CAA**</span><span class="sxs-lookup"><span data-stu-id="5e7fe-219">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e7fe-220"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="5e7fe-220"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5e7fe-221"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="5e7fe-221"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e7fe-222">Chiamate attive</span><span class="sxs-lookup"><span data-stu-id="5e7fe-222">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-223">Numero totale di chiamate PSTN (Public Switched Telephone Network) in ingresso/in uscita attualmente in corso.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-223">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7fe-224">Chiamate terminate</span><span class="sxs-lookup"><span data-stu-id="5e7fe-224">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-225">Numero totale di chiamate PSTN in ingresso/in uscita già terminate.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-225">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7fe-226">Tentativi di chiamata in arrivo/in uscita</span><span class="sxs-lookup"><span data-stu-id="5e7fe-226">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-227">Numero totale di chiamate PSTN in ingresso/in uscita tentate.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-227">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7fe-228">Chiamate in ingresso/in uscita stabilite</span><span class="sxs-lookup"><span data-stu-id="5e7fe-228">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-229">Numero totale di chiamate PSTN in ingresso/in uscita stabilite.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-229">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5e7fe-230">**Informazioni sulla conferenza**</span><span class="sxs-lookup"><span data-stu-id="5e7fe-230">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e7fe-231"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="5e7fe-231"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5e7fe-232"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="5e7fe-232"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e7fe-233">Conferenze di messaggistica istantanea attive</span><span class="sxs-lookup"><span data-stu-id="5e7fe-233">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-234">Numero totale di conferenze di messaggistica istantanea in continuo.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-234">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7fe-235">Conferenze audio/video attive</span><span class="sxs-lookup"><span data-stu-id="5e7fe-235">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-236">Numero totale di conferenze audio/video (A/V) in uscita.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-236">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7fe-237">Conferenze di condivisione applicazioni attive</span><span class="sxs-lookup"><span data-stu-id="5e7fe-237">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-238">Numero totale di conferenze di condivisione applicazioni in uscita.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-238">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7fe-239">Numero di partecipanti</span><span class="sxs-lookup"><span data-stu-id="5e7fe-239">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-240">Numero totale di partecipanti attualmente connessi a conferenze.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-240">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7fe-241">Errore della pianificazione delle conferenze</span><span class="sxs-lookup"><span data-stu-id="5e7fe-241">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-242">Numero totale di errori durante il tentativo di pianificazione di una conferenza.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-242">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7fe-243">Partecipare a una conferenza non riuscita</span><span class="sxs-lookup"><span data-stu-id="5e7fe-243">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-244">Numero totale di errori durante il tentativo di connessione a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-244">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5e7fe-245">**Contatori client di UCWA**</span><span class="sxs-lookup"><span data-stu-id="5e7fe-245">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e7fe-246"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="5e7fe-246"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="5e7fe-247"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="5e7fe-247"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e7fe-248">Numero totale di join IMMCU con esito positivo</span><span class="sxs-lookup"><span data-stu-id="5e7fe-248">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-249">Numero totale di conferenze di messaggistica istantanea Unite.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-249">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7fe-250">Numero totale di join DMCU con esito positivo</span><span class="sxs-lookup"><span data-stu-id="5e7fe-250">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="5e7fe-251">Numero totale di conferenze A/V Unite.</span><span class="sxs-lookup"><span data-stu-id="5e7fe-251">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

