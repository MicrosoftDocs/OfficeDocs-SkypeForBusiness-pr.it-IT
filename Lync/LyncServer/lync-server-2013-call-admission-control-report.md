---
title: 'Lync Server 2013: report di controllo ammissione chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Admission Control Report
ms:assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615043(v=OCS.15)
ms:contentKeyID: 48185933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff036a27149db4360a938fe2ce9d63c2718f4d94
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-report-in-lync-server-2013"></a><span data-ttu-id="7940e-102">Report controllo ammissione chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7940e-102">Call Admission Control Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7940e-103">_**Argomento Ultima modifica:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="7940e-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="7940e-104">Il report controllo ammissione chiamata fornisce informazioni sulle sessioni peer-to-peer e di conferenza che sono state svolte in restrizioni impostate in posizione tramite il controllo di ammissione delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="7940e-104">The Call Admission Control Report provides information about peer-to-peer and conferencing sessions that were conducted under restrictions set in place by Call Admission Control.</span></span> <span data-ttu-id="7940e-105">Il controllo di ammissione delle chiamate, introdotto in Microsoft Lync Server 2010, consente agli amministratori di consentire alle sessioni di comunicazione (o non consentire) in base ai vincoli di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="7940e-105">Call Admission Control, introduced in Microsoft Lync Server 2010, provides a way for administrators to allow (or not allow) communication sessions based on bandwidth constraints.</span></span> <span data-ttu-id="7940e-106">Ad esempio, gli amministratori possono creare criteri che impongono un limite alla quantità di larghezza di banda disponibile per le chiamate vocali e video.</span><span class="sxs-lookup"><span data-stu-id="7940e-106">For example, administrators can create policies that impose a limit on the amount of bandwidth available for voice and video calls.</span></span> <span data-ttu-id="7940e-107">Se è stato raggiunto il limite di larghezza di banda, non è possibile inserire nuove chiamate vocali o videochiamate finché una delle chiamate correnti non è terminata e ha liberato le risorse di rete necessarie.</span><span class="sxs-lookup"><span data-stu-id="7940e-107">If that bandwidth limit has been reached, then no new voice or video calls can be placed until one of the current calls has ended and freed up the required network resources.</span></span>

<div>

## <a name="accessing-the-call-admission-control-report"></a><span data-ttu-id="7940e-108">Accesso al report di controllo ammissione chiamata</span><span class="sxs-lookup"><span data-stu-id="7940e-108">Accessing the Call Admission Control Report</span></span>

<span data-ttu-id="7940e-109">Il report controllo ammissione chiamata si accede dalla Home page dei report di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="7940e-109">The Call Admission Control Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="7940e-110">Nel report controllo ammissione chiamata è possibile eseguire il drill-down per uno dei report seguenti:</span><span class="sxs-lookup"><span data-stu-id="7940e-110">From the Call Admission Control Report you can drill down to either of the following reports:</span></span>

  - <span data-ttu-id="7940e-111">Report Dettagli conferenza: per accedere a questo report, fare clic sulla metrica dettagli di una sessione di conferenza.</span><span class="sxs-lookup"><span data-stu-id="7940e-111">Conference Detail Report – To access this report, click the Details metric from a conference session.</span></span>

  - <span data-ttu-id="7940e-112">Report Dettagli sessione peer-to-peer: per accedere a questo report, fare clic sulla metrica Dettagli per una sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="7940e-112">Peer-to-Peer Session Detail Report – To access this report, click the Details metric for a peer-to-peer session.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a><span data-ttu-id="7940e-113">Uso ottimale del report di controllo dell'ammissione alle chiamate</span><span class="sxs-lookup"><span data-stu-id="7940e-113">Making the Best Use of the Call Admission Control Report</span></span>

<span data-ttu-id="7940e-114">Per ottenere un elenco delle chiamate non riuscite a causa della larghezza di banda insufficiente, selezionare chiamate rifiutate a causa del controllo di ammissione di chiamata nell'elenco a discesa categoria chiamata.</span><span class="sxs-lookup"><span data-stu-id="7940e-114">To get a list of calls that failed because of insufficient bandwidth, select Calls rejected because of call admission control from the Call category dropdown list.</span></span> <span data-ttu-id="7940e-115">La maggior parte delle chiamate restituite avrà probabilmente un ID di diagnostica pari a 5:</span><span class="sxs-lookup"><span data-stu-id="7940e-115">Most of the returned calls will likely have a diagnostic ID of 5:</span></span>

<span data-ttu-id="7940e-116">Larghezza di banda insufficiente per stabilire una sessione.</span><span class="sxs-lookup"><span data-stu-id="7940e-116">Insufficient bandwidth to establish session.</span></span> <span data-ttu-id="7940e-117">Provare a eseguire la reinstradazione PSTN.</span><span class="sxs-lookup"><span data-stu-id="7940e-117">Attempt PSTN re-route.</span></span>

<span data-ttu-id="7940e-118">Ciò indica che le limitazioni del controllo di ammissione alle chiamate impedivano che la chiamata venisse eseguita nella rete VoIP.</span><span class="sxs-lookup"><span data-stu-id="7940e-118">That indicates that Call Admission Control limitations were preventing the call from being made on the VoIP network.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="7940e-119">Filtri</span><span class="sxs-lookup"><span data-stu-id="7940e-119">Filters</span></span>

<span data-ttu-id="7940e-120">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="7940e-120">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="7940e-121">Ad esempio, il report controllo ammissione chiamata consente di filtrare le chiamate dall'utente che ha avviato la chiamata o dall'utente che è stato chiamato.</span><span class="sxs-lookup"><span data-stu-id="7940e-121">For example, the Call Admission Control Report enables you to filter calls by the user who initiated the call or by the user who was being called.</span></span> <span data-ttu-id="7940e-122">È anche possibile scegliere la modalità di raggruppamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="7940e-122">You can also choose how data should be grouped.</span></span> <span data-ttu-id="7940e-123">In questo caso, le chiamate vengono raggruppate per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="7940e-123">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="7940e-124">Nella tabella seguente sono elencati i filtri che è possibile usare con il report controllo ammissione chiamata.</span><span class="sxs-lookup"><span data-stu-id="7940e-124">The following table lists the filters that you can use with the Call Admission Control Report.</span></span>

### <a name="call-admission-control-report-filters"></a><span data-ttu-id="7940e-125">Filtri dei report di controllo ammissione chiamata</span><span class="sxs-lookup"><span data-stu-id="7940e-125">Call Admission Control Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7940e-126">Nome</span><span class="sxs-lookup"><span data-stu-id="7940e-126">Name</span></span></th>
<th><span data-ttu-id="7940e-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7940e-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7940e-128"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="7940e-128"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="7940e-129">Data/ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="7940e-129">Start date/time for the time range.</span></span> <span data-ttu-id="7940e-130">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7940e-130">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="7940e-131">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="7940e-131">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="7940e-132">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="7940e-132">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="7940e-133">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="7940e-133">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7940e-134">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="7940e-134">7/17/12012</span></span></p>
<p><span data-ttu-id="7940e-135">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="7940e-135">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7940e-136">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="7940e-136">7/13/2012</span></span></p>
<p><span data-ttu-id="7940e-137">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="7940e-137">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7940e-138"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="7940e-138"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="7940e-139">Data/ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="7940e-139">End date/time for the time range.</span></span> <span data-ttu-id="7940e-140">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7940e-140">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="7940e-141">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="7940e-141">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="7940e-142">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="7940e-142">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="7940e-143">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="7940e-143">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7940e-144">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="7940e-144">7/17/12012</span></span></p>
<p><span data-ttu-id="7940e-145">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="7940e-145">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7940e-146">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="7940e-146">7/13/2012</span></span></p>
<p><span data-ttu-id="7940e-147">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="7940e-147">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7940e-148"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="7940e-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="7940e-149">Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="7940e-149">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="7940e-150">È possibile selezionare un singolo pool o fare clic su <strong>[tutti]</strong> per visualizzare i dati per tutti i pool.</span><span class="sxs-lookup"><span data-stu-id="7940e-150">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="7940e-151">Questo elenco a discesa viene compilato automaticamente in base ai record nel database.</span><span class="sxs-lookup"><span data-stu-id="7940e-151">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7940e-152"><strong>Tipo di attività</strong></span><span class="sxs-lookup"><span data-stu-id="7940e-152"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="7940e-153">Tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="7940e-153">Type of activity.</span></span> <span data-ttu-id="7940e-154">Selezionare una delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="7940e-154">Select one of the following activities:</span></span></p>
<ul>
<li><p><span data-ttu-id="7940e-155">Tutti</span><span class="sxs-lookup"><span data-stu-id="7940e-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="7940e-156">Peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="7940e-156">Peer-to-Peer</span></span></p></li>
<li><p><span data-ttu-id="7940e-157">Conferenza</span><span class="sxs-lookup"><span data-stu-id="7940e-157">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7940e-158"><strong>Categoria chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="7940e-158"><strong>Call category</strong></span></span></p></td>
<td><p><span data-ttu-id="7940e-159">Indica il motivo per cui è stato usato CAC per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7940e-159">Indicates the reason that CAC was used for the call.</span></span> <span data-ttu-id="7940e-160">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7940e-160">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7940e-161">Tutti</span><span class="sxs-lookup"><span data-stu-id="7940e-161">[All]</span></span></p></li>
<li><p><span data-ttu-id="7940e-162">Chiamata rifiutata a causa del controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="7940e-162">Call rejected because of call admission control</span></span></p></li>
<li><p><span data-ttu-id="7940e-163">Chiamate reinstradate tramite PSTN a causa del controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="7940e-163">Calls rerouted through PSTN because of call admission control</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="7940e-164">Metriche per le sessioni peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="7940e-164">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="7940e-165">La tabella seguente elenca le informazioni fornite nel report di controllo dell'ammissione delle chiamate per le sessioni peer-to-peer, ovvero le sessioni che coinvolgono solo due partecipanti.</span><span class="sxs-lookup"><span data-stu-id="7940e-165">The following table lists the information provided in the Call Admission Control Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="7940e-166">Metriche per le sessioni peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="7940e-166">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7940e-167">Nome</span><span class="sxs-lookup"><span data-stu-id="7940e-167">Name</span></span></th>
<th><span data-ttu-id="7940e-168">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="7940e-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7940e-169">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7940e-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7940e-170"><strong>Dettaglio</strong></span><span class="sxs-lookup"><span data-stu-id="7940e-170"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="7940e-171">No</span><span class="sxs-lookup"><span data-stu-id="7940e-171">No</span></span></p></td>
<td><p><span data-ttu-id="7940e-172">Quando si fa clic su questo elemento, il report Mostra un report Dettagli sessione peer-to-peer per la sessione specificata.</span><span class="sxs-lookup"><span data-stu-id="7940e-172">When you click this item, the report shows you a Peer-to-Peer Session Detail Report for the specified session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7940e-173"><strong>Dall'utente</strong></span><span class="sxs-lookup"><span data-stu-id="7940e-173"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="7940e-174">Sì</span><span class="sxs-lookup"><span data-stu-id="7940e-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="7940e-175">Indirizzo SIP dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="7940e-175">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7940e-176"><strong>All'utente</strong></span><span class="sxs-lookup"><span data-stu-id="7940e-176"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="7940e-177">Sì</span><span class="sxs-lookup"><span data-stu-id="7940e-177">Yes</span></span></p></td>
<td><p><span data-ttu-id="7940e-178">Indirizzo SIP dell'utente invitato a partecipare alla sessione.</span><span class="sxs-lookup"><span data-stu-id="7940e-178">SIP address of the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7940e-179"><strong>Modalità</strong></span><span class="sxs-lookup"><span data-stu-id="7940e-179"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="7940e-180">Sì</span><span class="sxs-lookup"><span data-stu-id="7940e-180">Yes</span></span></p></td>
<td><p><span data-ttu-id="7940e-181">Modalità di comunicazione (ad esempio audio e video) usate durante la sessione.</span><span class="sxs-lookup"><span data-stu-id="7940e-181">Communication modalities (such as audio and video) that were used during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7940e-182"><strong>Invitare il tempo</strong></span><span class="sxs-lookup"><span data-stu-id="7940e-182"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="7940e-183">Sì</span><span class="sxs-lookup"><span data-stu-id="7940e-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="7940e-184">Data e ora in cui l'invito alla sessione iniziale è stato inviato all'utente da.</span><span class="sxs-lookup"><span data-stu-id="7940e-184">Date and time the initial session invitation was sent to the From user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7940e-185"><strong>Tempo di risposta</strong></span><span class="sxs-lookup"><span data-stu-id="7940e-185"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="7940e-186">Sì</span><span class="sxs-lookup"><span data-stu-id="7940e-186">Yes</span></span></p></td>
<td><p><span data-ttu-id="7940e-187">Data e ora in cui è stata ricevuta l'accettazione dell'invito.</span><span class="sxs-lookup"><span data-stu-id="7940e-187">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7940e-188"><strong>Ora di fine</strong></span><span class="sxs-lookup"><span data-stu-id="7940e-188"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="7940e-189">Sì</span><span class="sxs-lookup"><span data-stu-id="7940e-189">Yes</span></span></p></td>
<td><p><span data-ttu-id="7940e-190">Data e ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="7940e-190">Date and time that the session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7940e-191"><strong>ID diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="7940e-191"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="7940e-192">Sì</span><span class="sxs-lookup"><span data-stu-id="7940e-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="7940e-193">Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori.</span><span class="sxs-lookup"><span data-stu-id="7940e-193">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="7940e-194">Le intestazioni di diagnostica sono facoltative (è possibile avere sessioni SIP che non includono queste intestazioni) e gli ID di diagnostica vengono riportati solo per le sessioni con problemi di qualche tipo.</span><span class="sxs-lookup"><span data-stu-id="7940e-194">Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="7940e-195">Metriche per le sessioni di conferenza</span><span class="sxs-lookup"><span data-stu-id="7940e-195">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="7940e-196">Nella tabella seguente sono elencate le informazioni fornite nel report di controllo dell'ammissione alle chiamate per le sessioni di conferenza, ovvero le sessioni che coinvolgono tre o più partecipanti.</span><span class="sxs-lookup"><span data-stu-id="7940e-196">The following table lists the information provided in the Call Admission Control Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="7940e-197">Metriche per le sessioni di conferenza</span><span class="sxs-lookup"><span data-stu-id="7940e-197">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7940e-198">Nome</span><span class="sxs-lookup"><span data-stu-id="7940e-198">Name</span></span></th>
<th><span data-ttu-id="7940e-199">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="7940e-199">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7940e-200">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7940e-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7940e-201"><strong>URI conferenza</strong></span><span class="sxs-lookup"><span data-stu-id="7940e-201"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="7940e-202">Sì</span><span class="sxs-lookup"><span data-stu-id="7940e-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="7940e-203">Identificatore univoco per la conferenza.</span><span class="sxs-lookup"><span data-stu-id="7940e-203">Unique identifier for the conference.</span></span> <span data-ttu-id="7940e-204">Quando si fa clic su questo elemento, il report Mostra i singoli partecipanti alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="7940e-204">When you click this item, the report shows the individual conference participants.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7940e-205"><strong>Organizzatore</strong></span><span class="sxs-lookup"><span data-stu-id="7940e-205"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="7940e-206">Sì</span><span class="sxs-lookup"><span data-stu-id="7940e-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="7940e-207">Indirizzo SIP dell'utente che ha organizzato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="7940e-207">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7940e-208"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="7940e-208"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="7940e-209">Sì</span><span class="sxs-lookup"><span data-stu-id="7940e-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="7940e-210">Server perimetrale usato nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="7940e-210">Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7940e-211"><strong>Ora di inizio</strong></span><span class="sxs-lookup"><span data-stu-id="7940e-211"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="7940e-212">Sì</span><span class="sxs-lookup"><span data-stu-id="7940e-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="7940e-213">Data e ora in cui è stata avviata la conferenza.</span><span class="sxs-lookup"><span data-stu-id="7940e-213">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7940e-214"><strong>Ora di fine</strong></span><span class="sxs-lookup"><span data-stu-id="7940e-214"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="7940e-215">Sì</span><span class="sxs-lookup"><span data-stu-id="7940e-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="7940e-216">Data e ora di fine della conferenza.</span><span class="sxs-lookup"><span data-stu-id="7940e-216">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="7940e-217">Metriche per singoli partecipanti alla conferenza</span><span class="sxs-lookup"><span data-stu-id="7940e-217">Metrics for Individual Conference Participants</span></span>

<span data-ttu-id="7940e-218">Nella tabella seguente sono elencate le informazioni fornite nel report di controllo dell'ammissione delle chiamate per singoli partecipanti alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="7940e-218">The following table lists the information provided in the Call Admission Control Report for individual conference participants.</span></span>

### <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="7940e-219">Metriche per singoli partecipanti alla conferenza</span><span class="sxs-lookup"><span data-stu-id="7940e-219">Metrics for Individual Conference Participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7940e-220">Nome</span><span class="sxs-lookup"><span data-stu-id="7940e-220">Name</span></span></th>
<th><span data-ttu-id="7940e-221">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="7940e-221">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7940e-222">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7940e-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7940e-223"><strong>Ruolo</strong></span><span class="sxs-lookup"><span data-stu-id="7940e-223"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="7940e-224">No</span><span class="sxs-lookup"><span data-stu-id="7940e-224">No</span></span></p></td>
<td><p><span data-ttu-id="7940e-225">Ruolo (ad esempio, relatore) riprodotto dal partecipante alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="7940e-225">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7940e-226"><strong>Partecipante</strong></span><span class="sxs-lookup"><span data-stu-id="7940e-226"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="7940e-227">No</span><span class="sxs-lookup"><span data-stu-id="7940e-227">No</span></span></p></td>
<td><p><span data-ttu-id="7940e-228">Indirizzo SIP del partecipante alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="7940e-228">SIP address of the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7940e-229"><strong>Connettività</strong></span><span class="sxs-lookup"><span data-stu-id="7940e-229"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="7940e-230">No</span><span class="sxs-lookup"><span data-stu-id="7940e-230">No</span></span></p></td>
<td><p><span data-ttu-id="7940e-231">Connettività di rete (in genere da interno o da esterno) per il partecipante.</span><span class="sxs-lookup"><span data-stu-id="7940e-231">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7940e-232"><strong>Modalità</strong></span><span class="sxs-lookup"><span data-stu-id="7940e-232"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="7940e-233">No</span><span class="sxs-lookup"><span data-stu-id="7940e-233">No</span></span></p></td>
<td><p><span data-ttu-id="7940e-234">Tipo di conferenza (ad esempio, A/V Conferencing).</span><span class="sxs-lookup"><span data-stu-id="7940e-234">Conference type (for example, A/V conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7940e-235"><strong>Tempo di partecipazione</strong></span><span class="sxs-lookup"><span data-stu-id="7940e-235"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="7940e-236">No</span><span class="sxs-lookup"><span data-stu-id="7940e-236">No</span></span></p></td>
<td><p><span data-ttu-id="7940e-237">Data e ora in cui il partecipante ha partecipato alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="7940e-237">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7940e-238"><strong>Ora di uscita</strong></span><span class="sxs-lookup"><span data-stu-id="7940e-238"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="7940e-239">No</span><span class="sxs-lookup"><span data-stu-id="7940e-239">No</span></span></p></td>
<td><p><span data-ttu-id="7940e-240">Data e ora in cui il partecipante ha lasciato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="7940e-240">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7940e-241"><strong>ID diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="7940e-241"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="7940e-242">No</span><span class="sxs-lookup"><span data-stu-id="7940e-242">No</span></span></p></td>
<td><p><span data-ttu-id="7940e-243">Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori.</span><span class="sxs-lookup"><span data-stu-id="7940e-243">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="7940e-244">Le intestazioni di diagnostica sono facoltative (è possibile avere sessioni SIP che non includono queste intestazioni) e gli ID di diagnostica vengono riportati solo per le sessioni con problemi di qualche tipo.</span><span class="sxs-lookup"><span data-stu-id="7940e-244">Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

