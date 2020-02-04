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
ms.openlocfilehash: 0dcb1d84392cf9f56f2996281eb53e798690ba1e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a><span data-ttu-id="75ea4-102">Interpretazione dei risultati</span><span class="sxs-lookup"><span data-stu-id="75ea4-102">Interpreting the Results</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75ea4-103">_**Argomento Ultima modifica:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="75ea4-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="75ea4-104">Lo strumento per lo stress e le prestazioni di Lync Server 2013 (LyncPerfTool. exe) contiene molti contatori che è possibile usare per capire cosa sta facendo il client e se si verificano problemi.</span><span class="sxs-lookup"><span data-stu-id="75ea4-104">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="75ea4-105">Contatori client</span><span class="sxs-lookup"><span data-stu-id="75ea4-105">Client Counters</span></span>

<span data-ttu-id="75ea4-106">Ogni istanza di LyncPerfTool. exe in uso ha un'istanza distinta dei contatori.</span><span class="sxs-lookup"><span data-stu-id="75ea4-106">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="75ea4-107">Ogni istanza è denominata dall'ID processo.</span><span class="sxs-lookup"><span data-stu-id="75ea4-107">Each instance is named by its process ID.</span></span>

<span data-ttu-id="75ea4-108">Se i client sono sovraccaricati, è possibile che si verifichino problemi.</span><span class="sxs-lookup"><span data-stu-id="75ea4-108">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="75ea4-109">Per evitare questi problemi, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="75ea4-109">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="75ea4-110">Monitorare la CPU e l'utilizzo della memoria nei computer client.</span><span class="sxs-lookup"><span data-stu-id="75ea4-110">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="75ea4-111">Se la CPU è sempre superiore a 90%, ridurre il numero di utenti.</span><span class="sxs-lookup"><span data-stu-id="75ea4-111">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="75ea4-112">Se l'impronta di memoria è elevata, è possibile che si verificano problemi se il file di pagina non è abbastanza grande.</span><span class="sxs-lookup"><span data-stu-id="75ea4-112">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="75ea4-113">Verificare che la carica di conferma non colpisca il limite nel computer.</span><span class="sxs-lookup"><span data-stu-id="75ea4-113">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="75ea4-114">Se si stanno esaurendo i limiti di memoria, valutare la possibilità di aumentare le dimensioni del file di pagina o ridurre il numero di utenti</span><span class="sxs-lookup"><span data-stu-id="75ea4-114">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="75ea4-115">Le tabelle seguenti elencano i contatori delle prestazioni LyncPerfTool chiave.</span><span class="sxs-lookup"><span data-stu-id="75ea4-115">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="75ea4-116">**Informazioni generali**</span><span class="sxs-lookup"><span data-stu-id="75ea4-116">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75ea4-117"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="75ea4-117"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="75ea4-118"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="75ea4-118"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75ea4-119">Tempo trascorso in minuti</span><span class="sxs-lookup"><span data-stu-id="75ea4-119">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="75ea4-120">Tempo trascorso da quando il processo è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="75ea4-120">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75ea4-121">Endpoint attivi</span><span class="sxs-lookup"><span data-stu-id="75ea4-121">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="75ea4-122">Numero di endpoint attualmente connessi al server.</span><span class="sxs-lookup"><span data-stu-id="75ea4-122">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75ea4-123">Accessi non riusciti</span><span class="sxs-lookup"><span data-stu-id="75ea4-123">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="75ea4-124">Numero totale di errori di accesso di endpoint.</span><span class="sxs-lookup"><span data-stu-id="75ea4-124">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75ea4-125">Tentativi di accesso</span><span class="sxs-lookup"><span data-stu-id="75ea4-125">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="75ea4-126">Numero totale di tentativi di accesso di endpoint.</span><span class="sxs-lookup"><span data-stu-id="75ea4-126">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75ea4-127">Endpoint disconnessi</span><span class="sxs-lookup"><span data-stu-id="75ea4-127">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="75ea4-128">Numero totale di endpoint disconnessi.</span><span class="sxs-lookup"><span data-stu-id="75ea4-128">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="75ea4-129">**Informazioni sulla presenza**</span><span class="sxs-lookup"><span data-stu-id="75ea4-129">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75ea4-130"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="75ea4-130"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="75ea4-131"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="75ea4-131"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75ea4-132">Chiamate di sepresenza</span><span class="sxs-lookup"><span data-stu-id="75ea4-132">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="75ea4-133">Numero totale di tentativi di modifica della presenza.</span><span class="sxs-lookup"><span data-stu-id="75ea4-133">Total number of presence change attempts.</span></span> <span data-ttu-id="75ea4-134">Per i diversi tipi di modifiche alla presenza, Vedi il contatore delle prestazioni chiamate sepresenza (tipo presenza).</span><span class="sxs-lookup"><span data-stu-id="75ea4-134">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75ea4-135">Risposte di NNN per sepresenza</span><span class="sxs-lookup"><span data-stu-id="75ea4-135">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="75ea4-136">Numero totale di codici di risposta nnn ricevuti dal server.</span><span class="sxs-lookup"><span data-stu-id="75ea4-136">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75ea4-137">Chiamate GetPresence</span><span class="sxs-lookup"><span data-stu-id="75ea4-137">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="75ea4-138">Numero totale di tentativi di richiesta di presenza Get.</span><span class="sxs-lookup"><span data-stu-id="75ea4-138">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75ea4-139">Risposte di NNN per GetPresence</span><span class="sxs-lookup"><span data-stu-id="75ea4-139">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="75ea4-140">Numero totale di codici di risposta nnn ricevuti dal server.</span><span class="sxs-lookup"><span data-stu-id="75ea4-140">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="75ea4-141">**Informazioni sul servizio Rubrica**</span><span class="sxs-lookup"><span data-stu-id="75ea4-141">**Address Book service Information**</span></span>

<span data-ttu-id="75ea4-142">Questa categoria include i contatori usati per monitorare i download di file in ABS e le richieste di servizio query Web della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="75ea4-142">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75ea4-143"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="75ea4-143"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="75ea4-144"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="75ea4-144"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75ea4-145">Download di file in ABS Full/Delta tentato</span><span class="sxs-lookup"><span data-stu-id="75ea4-145">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="75ea4-146">Numero totale di richieste di download di file completi o Delta tentate.</span><span class="sxs-lookup"><span data-stu-id="75ea4-146">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75ea4-147">Download di file completi/Delta di ABS riuscito</span><span class="sxs-lookup"><span data-stu-id="75ea4-147">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="75ea4-148">Numero totale di richieste di download di file completi o Delta tentate.</span><span class="sxs-lookup"><span data-stu-id="75ea4-148">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75ea4-149">Contatori correlati al servizio query Web di Rubrica</span><span class="sxs-lookup"><span data-stu-id="75ea4-149">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="75ea4-150">Contatori correlati per il download del file della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="75ea4-150">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75ea4-151">Chiamate in ABS WS tentate</span><span class="sxs-lookup"><span data-stu-id="75ea4-151">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="75ea4-152">Numero totale di richieste di servizio query Web per la Rubrica.</span><span class="sxs-lookup"><span data-stu-id="75ea4-152">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75ea4-153">Chiamate in ABS WS succeeded</span><span class="sxs-lookup"><span data-stu-id="75ea4-153">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="75ea4-154">Numero totale di richieste di servizio query Web per la rubrica che hanno restituito un codice di risposta riuscito.</span><span class="sxs-lookup"><span data-stu-id="75ea4-154">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75ea4-155">Chiamate in ABS WS non riuscite</span><span class="sxs-lookup"><span data-stu-id="75ea4-155">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="75ea4-156">Numero totale di richieste di servizio query Web per la rubrica che hanno restituito un codice di risposta di errore.</span><span class="sxs-lookup"><span data-stu-id="75ea4-156">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="75ea4-157">**Informazioni sulla lista di distribuzione (DL)**</span><span class="sxs-lookup"><span data-stu-id="75ea4-157">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75ea4-158"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="75ea4-158"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="75ea4-159"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="75ea4-159"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75ea4-160">Chiamate tentativo</span><span class="sxs-lookup"><span data-stu-id="75ea4-160">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="75ea4-161">Numero totale di richieste di servizio Web di espansione della lista di distribuzione (DLX) tentato.</span><span class="sxs-lookup"><span data-stu-id="75ea4-161">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75ea4-162">Chiamate succeeded</span><span class="sxs-lookup"><span data-stu-id="75ea4-162">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="75ea4-163">Numero totale di richieste di servizio Web DLX che hanno restituito un codice di risposta riuscito.</span><span class="sxs-lookup"><span data-stu-id="75ea4-163">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75ea4-164">Chiamate non riuscite</span><span class="sxs-lookup"><span data-stu-id="75ea4-164">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="75ea4-165">Numero totale di richieste di servizio Web DLX che hanno restituito un codice di risposta di errore.</span><span class="sxs-lookup"><span data-stu-id="75ea4-165">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="75ea4-166">**Informazioni di base su VoIP**</span><span class="sxs-lookup"><span data-stu-id="75ea4-166">**VoIP Basic Information**</span></span>

<span data-ttu-id="75ea4-167">I contatori delle prestazioni elencati sotto i numeri di report per tutte le chiamate VoIP (Voice over IP), incluse le chiamate a Mediation Server, A/V Conferencing Server, Edge Server, Response Group Application e Conference Auto Attendant, quando questi scenari sono abilitati.</span><span class="sxs-lookup"><span data-stu-id="75ea4-167">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75ea4-168"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="75ea4-168"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="75ea4-169"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="75ea4-169"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75ea4-170">Chiamate attive</span><span class="sxs-lookup"><span data-stu-id="75ea4-170">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="75ea4-171">Numero totale di chiamate vocali in arrivo/in uscita attualmente in corso.</span><span class="sxs-lookup"><span data-stu-id="75ea4-171">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75ea4-172">Chiamate terminate</span><span class="sxs-lookup"><span data-stu-id="75ea4-172">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="75ea4-173">Numero totale di chiamate vocali in arrivo/in uscita già terminate.</span><span class="sxs-lookup"><span data-stu-id="75ea4-173">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75ea4-174">Chiamate rifiutate</span><span class="sxs-lookup"><span data-stu-id="75ea4-174">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="75ea4-175">Numero totale di chiamate vocali in arrivo rifiutate.</span><span class="sxs-lookup"><span data-stu-id="75ea4-175">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75ea4-176">Tentativi di chiamata in arrivo/in uscita</span><span class="sxs-lookup"><span data-stu-id="75ea4-176">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="75ea4-177">Numero totale di chiamate vocali in arrivo/in uscita tentate.</span><span class="sxs-lookup"><span data-stu-id="75ea4-177">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75ea4-178">Chiamate in arrivo/in uscita stabilite</span><span class="sxs-lookup"><span data-stu-id="75ea4-178">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="75ea4-179">Numero totale di chiamate vocali in arrivo/in uscita stabilite.</span><span class="sxs-lookup"><span data-stu-id="75ea4-179">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75ea4-180">Chiamate di NNN ricevute</span><span class="sxs-lookup"><span data-stu-id="75ea4-180">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="75ea4-181">Numero totale di codici di risposta nnn ricevuti dal server.</span><span class="sxs-lookup"><span data-stu-id="75ea4-181">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75ea4-182">Frequenza di abbonamento VoIP (%)</span><span class="sxs-lookup"><span data-stu-id="75ea4-182">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="75ea4-183">Total calls established/Total calls Tented.</span><span class="sxs-lookup"><span data-stu-id="75ea4-183">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="75ea4-184">**Informazioni sulle chiamate di servizio Response Group**</span><span class="sxs-lookup"><span data-stu-id="75ea4-184">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75ea4-185"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="75ea4-185"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="75ea4-186"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="75ea4-186"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75ea4-187">Chiamate attive</span><span class="sxs-lookup"><span data-stu-id="75ea4-187">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="75ea4-188">Numero totale di chiamate attive all'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="75ea4-188">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75ea4-189">Chiamate tentativo</span><span class="sxs-lookup"><span data-stu-id="75ea4-189">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="75ea4-190">Numero totale di chiamate tentate.</span><span class="sxs-lookup"><span data-stu-id="75ea4-190">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="75ea4-191">**Informazioni sulle chiamate di messaggistica istantanea (IM)**</span><span class="sxs-lookup"><span data-stu-id="75ea4-191">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75ea4-192"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="75ea4-192"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="75ea4-193"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="75ea4-193"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75ea4-194">Chiamate attive</span><span class="sxs-lookup"><span data-stu-id="75ea4-194">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="75ea4-195">Numero totale di chiamate di messaggistica istantanea in arrivo/in uscita.</span><span class="sxs-lookup"><span data-stu-id="75ea4-195">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75ea4-196">Chiamate terminate</span><span class="sxs-lookup"><span data-stu-id="75ea4-196">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="75ea4-197">Numero totale di chiamate di messaggistica istantanea in arrivo/in uscita già terminate.</span><span class="sxs-lookup"><span data-stu-id="75ea4-197">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75ea4-198">Chiamate di NNN ricevute</span><span class="sxs-lookup"><span data-stu-id="75ea4-198">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="75ea4-199">Numero totale di codici di risposta nnn ricevuti dal server.</span><span class="sxs-lookup"><span data-stu-id="75ea4-199">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75ea4-200">Messaggi ISTANTANEi ricevuti/inviati</span><span class="sxs-lookup"><span data-stu-id="75ea4-200">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="75ea4-201">Numero totale di messaggi ricevuti o inviati per tutte le sessioni.</span><span class="sxs-lookup"><span data-stu-id="75ea4-201">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75ea4-202">Tentativi di chiamata in arrivo/in uscita</span><span class="sxs-lookup"><span data-stu-id="75ea4-202">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="75ea4-203">Numero totale di chiamate di messaggistica istantanea in arrivo/in uscita tentate.</span><span class="sxs-lookup"><span data-stu-id="75ea4-203">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75ea4-204">Chiamate in arrivo/in uscita stabilite</span><span class="sxs-lookup"><span data-stu-id="75ea4-204">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="75ea4-205">Numero totale di chiamate di messaggi istantanei in arrivo/in uscita stabilite.</span><span class="sxs-lookup"><span data-stu-id="75ea4-205">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="75ea4-206">**Informazioni sulle chiamate di condivisione delle app**</span><span class="sxs-lookup"><span data-stu-id="75ea4-206">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75ea4-207"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="75ea4-207"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="75ea4-208"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="75ea4-208"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75ea4-209">Chiamate attive</span><span class="sxs-lookup"><span data-stu-id="75ea4-209">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="75ea4-210">Numero totale di chiamate di condivisione delle applicazioni in entrata e in uscita.</span><span class="sxs-lookup"><span data-stu-id="75ea4-210">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75ea4-211">Chiamate terminate</span><span class="sxs-lookup"><span data-stu-id="75ea4-211">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="75ea4-212">Numero totale di chiamate di condivisione delle applicazioni in arrivo/in uscita già terminate.</span><span class="sxs-lookup"><span data-stu-id="75ea4-212">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75ea4-213">Chiamate di NNN ricevute</span><span class="sxs-lookup"><span data-stu-id="75ea4-213">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="75ea4-214">Numero totale di codici di risposta nnn ricevuti dal server.</span><span class="sxs-lookup"><span data-stu-id="75ea4-214">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75ea4-215">Tentativi di chiamata in arrivo/in uscita</span><span class="sxs-lookup"><span data-stu-id="75ea4-215">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="75ea4-216">Numero totale di chiamate di condivisione delle applicazioni in arrivo/in uscita tentate.</span><span class="sxs-lookup"><span data-stu-id="75ea4-216">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75ea4-217">Chiamate in arrivo/in uscita stabilite</span><span class="sxs-lookup"><span data-stu-id="75ea4-217">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="75ea4-218">Numero totale di chiamate di condivisione delle applicazioni in arrivo/in uscita stabilite.</span><span class="sxs-lookup"><span data-stu-id="75ea4-218">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="75ea4-219">**Informazioni sulle chiamate CAA**</span><span class="sxs-lookup"><span data-stu-id="75ea4-219">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75ea4-220"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="75ea4-220"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="75ea4-221"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="75ea4-221"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75ea4-222">Chiamate attive</span><span class="sxs-lookup"><span data-stu-id="75ea4-222">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="75ea4-223">Numero totale di chiamate PSTN (Public Switched Telephone Network) in arrivo/in uscita attualmente in corso.</span><span class="sxs-lookup"><span data-stu-id="75ea4-223">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75ea4-224">Chiamate terminate</span><span class="sxs-lookup"><span data-stu-id="75ea4-224">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="75ea4-225">Numero totale di chiamate PSTN in arrivo/in uscita già terminate.</span><span class="sxs-lookup"><span data-stu-id="75ea4-225">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75ea4-226">Tentativi di chiamata in arrivo/in uscita</span><span class="sxs-lookup"><span data-stu-id="75ea4-226">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="75ea4-227">Numero totale di chiamate PSTN in arrivo/in uscita tentate.</span><span class="sxs-lookup"><span data-stu-id="75ea4-227">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75ea4-228">Chiamate in arrivo/in uscita stabilite</span><span class="sxs-lookup"><span data-stu-id="75ea4-228">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="75ea4-229">Numero totale di chiamate PSTN in arrivo/in uscita stabilite.</span><span class="sxs-lookup"><span data-stu-id="75ea4-229">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="75ea4-230">**Informazioni sulla conferenza**</span><span class="sxs-lookup"><span data-stu-id="75ea4-230">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75ea4-231"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="75ea4-231"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="75ea4-232"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="75ea4-232"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75ea4-233">Conferenze di messaggistica istantanea attiva</span><span class="sxs-lookup"><span data-stu-id="75ea4-233">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="75ea4-234">Numero totale di conferenze di messaggistica istantanea in corso.</span><span class="sxs-lookup"><span data-stu-id="75ea4-234">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75ea4-235">Conferenze audio/video attive</span><span class="sxs-lookup"><span data-stu-id="75ea4-235">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="75ea4-236">Numero totale di conferenze audio/video (A/V) in corso.</span><span class="sxs-lookup"><span data-stu-id="75ea4-236">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75ea4-237">Conferenze per la condivisione di applicazioni attive</span><span class="sxs-lookup"><span data-stu-id="75ea4-237">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="75ea4-238">Numero totale di conferenze di condivisione applicazioni in corso.</span><span class="sxs-lookup"><span data-stu-id="75ea4-238">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75ea4-239">Numero di partecipanti</span><span class="sxs-lookup"><span data-stu-id="75ea4-239">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="75ea4-240">Numero totale di partecipanti attualmente connessi alle conferenze.</span><span class="sxs-lookup"><span data-stu-id="75ea4-240">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75ea4-241">Errore di programmazione conferenze</span><span class="sxs-lookup"><span data-stu-id="75ea4-241">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="75ea4-242">Numero totale di errori durante il tentativo di pianificare una conferenza.</span><span class="sxs-lookup"><span data-stu-id="75ea4-242">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75ea4-243">Partecipare a una conferenza non riuscita</span><span class="sxs-lookup"><span data-stu-id="75ea4-243">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="75ea4-244">Numero totale di errori durante il tentativo di connessione a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="75ea4-244">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="75ea4-245">**Contatori client di UCWA**</span><span class="sxs-lookup"><span data-stu-id="75ea4-245">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75ea4-246"><strong>Contatore delle prestazioni</strong></span><span class="sxs-lookup"><span data-stu-id="75ea4-246"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="75ea4-247"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="75ea4-247"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75ea4-248">Numero totale di join IMMCU riusciti</span><span class="sxs-lookup"><span data-stu-id="75ea4-248">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="75ea4-249">Numero totale di conferenze di messaggistica istantanea Unite.</span><span class="sxs-lookup"><span data-stu-id="75ea4-249">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75ea4-250">Numero totale di join DMCU riusciti</span><span class="sxs-lookup"><span data-stu-id="75ea4-250">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="75ea4-251">Numero totale di conferenze A/V Unite.</span><span class="sxs-lookup"><span data-stu-id="75ea4-251">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

