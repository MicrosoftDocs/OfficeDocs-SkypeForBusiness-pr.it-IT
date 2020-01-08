---
title: 'Lync Server 2013: report di controllo ammissione chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Admission Control Report
ms:assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615043(v=OCS.15)
ms:contentKeyID: 48185933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f31159742757b7ef8b6889b7961bad747b1f6d2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-report-in-lync-server-2013"></a><span data-ttu-id="dbab0-102">Report controllo ammissione chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbab0-102">Call Admission Control Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbab0-103">_**Argomento Ultima modifica:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="dbab0-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="dbab0-104">Il report controllo ammissione chiamata fornisce informazioni sulle sessioni peer-to-peer e di conferenza che sono state svolte in restrizioni impostate in posizione tramite il controllo di ammissione delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="dbab0-104">The Call Admission Control Report provides information about peer-to-peer and conferencing sessions that were conducted under restrictions set in place by Call Admission Control.</span></span> <span data-ttu-id="dbab0-105">Il controllo di ammissione delle chiamate, introdotto in Microsoft Lync Server 2010, consente agli amministratori di consentire alle sessioni di comunicazione (o non consentire) in base ai vincoli di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="dbab0-105">Call Admission Control, introduced in Microsoft Lync Server 2010, provides a way for administrators to allow (or not allow) communication sessions based on bandwidth constraints.</span></span> <span data-ttu-id="dbab0-106">Ad esempio, gli amministratori possono creare criteri che impongono un limite alla quantità di larghezza di banda disponibile per le chiamate vocali e video.</span><span class="sxs-lookup"><span data-stu-id="dbab0-106">For example, administrators can create policies that impose a limit on the amount of bandwidth available for voice and video calls.</span></span> <span data-ttu-id="dbab0-107">Se è stato raggiunto il limite di larghezza di banda, non è possibile inserire nuove chiamate vocali o videochiamate finché una delle chiamate correnti non è terminata e ha liberato le risorse di rete necessarie.</span><span class="sxs-lookup"><span data-stu-id="dbab0-107">If that bandwidth limit has been reached, then no new voice or video calls can be placed until one of the current calls has ended and freed up the required network resources.</span></span>

<div>

## <a name="accessing-the-call-admission-control-report"></a><span data-ttu-id="dbab0-108">Accesso al report di controllo ammissione chiamata</span><span class="sxs-lookup"><span data-stu-id="dbab0-108">Accessing the Call Admission Control Report</span></span>

<span data-ttu-id="dbab0-109">Il report controllo ammissione chiamata si accede dalla Home page dei report di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="dbab0-109">The Call Admission Control Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="dbab0-110">Nel report controllo ammissione chiamata è possibile eseguire il drill-down per uno dei report seguenti:</span><span class="sxs-lookup"><span data-stu-id="dbab0-110">From the Call Admission Control Report you can drill down to either of the following reports:</span></span>

  - <span data-ttu-id="dbab0-111">Report Dettagli conferenza: per accedere a questo report, fare clic sulla metrica dettagli di una sessione di conferenza.</span><span class="sxs-lookup"><span data-stu-id="dbab0-111">Conference Detail Report – To access this report, click the Details metric from a conference session.</span></span>

  - <span data-ttu-id="dbab0-112">Report Dettagli sessione peer-to-peer: per accedere a questo report, fare clic sulla metrica Dettagli per una sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="dbab0-112">Peer-to-Peer Session Detail Report – To access this report, click the Details metric for a peer-to-peer session.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a><span data-ttu-id="dbab0-113">Uso ottimale del report di controllo dell'ammissione alle chiamate</span><span class="sxs-lookup"><span data-stu-id="dbab0-113">Making the Best Use of the Call Admission Control Report</span></span>

<span data-ttu-id="dbab0-114">Per ottenere un elenco delle chiamate non riuscite a causa della larghezza di banda insufficiente, selezionare chiamate rifiutate a causa del controllo di ammissione di chiamata nell'elenco a discesa categoria chiamata.</span><span class="sxs-lookup"><span data-stu-id="dbab0-114">To get a list of calls that failed because of insufficient bandwidth, select Calls rejected because of call admission control from the Call category dropdown list.</span></span> <span data-ttu-id="dbab0-115">La maggior parte delle chiamate restituite avrà probabilmente un ID di diagnostica pari a 5:</span><span class="sxs-lookup"><span data-stu-id="dbab0-115">Most of the returned calls will likely have a diagnostic ID of 5:</span></span>

<span data-ttu-id="dbab0-116">Larghezza di banda insufficiente per stabilire una sessione.</span><span class="sxs-lookup"><span data-stu-id="dbab0-116">Insufficient bandwidth to establish session.</span></span> <span data-ttu-id="dbab0-117">Provare a eseguire la reinstradazione PSTN.</span><span class="sxs-lookup"><span data-stu-id="dbab0-117">Attempt PSTN re-route.</span></span>

<span data-ttu-id="dbab0-118">Ciò indica che le limitazioni del controllo di ammissione alle chiamate impedivano che la chiamata venisse eseguita nella rete VoIP.</span><span class="sxs-lookup"><span data-stu-id="dbab0-118">That indicates that Call Admission Control limitations were preventing the call from being made on the VoIP network.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="dbab0-119">Filtri</span><span class="sxs-lookup"><span data-stu-id="dbab0-119">Filters</span></span>

<span data-ttu-id="dbab0-120">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="dbab0-120">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="dbab0-121">Ad esempio, il report controllo ammissione chiamata consente di filtrare le chiamate dall'utente che ha avviato la chiamata o dall'utente che è stato chiamato.</span><span class="sxs-lookup"><span data-stu-id="dbab0-121">For example, the Call Admission Control Report enables you to filter calls by the user who initiated the call or by the user who was being called.</span></span> <span data-ttu-id="dbab0-122">È anche possibile scegliere la modalità di raggruppamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="dbab0-122">You can also choose how data should be grouped.</span></span> <span data-ttu-id="dbab0-123">In questo caso, le chiamate vengono raggruppate per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="dbab0-123">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="dbab0-124">Nella tabella seguente sono elencati i filtri che è possibile usare con il report controllo ammissione chiamata.</span><span class="sxs-lookup"><span data-stu-id="dbab0-124">The following table lists the filters that you can use with the Call Admission Control Report.</span></span>

### <a name="call-admission-control-report-filters"></a><span data-ttu-id="dbab0-125">Filtri dei report di controllo ammissione chiamata</span><span class="sxs-lookup"><span data-stu-id="dbab0-125">Call Admission Control Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbab0-126">Nome</span><span class="sxs-lookup"><span data-stu-id="dbab0-126">Name</span></span></th>
<th><span data-ttu-id="dbab0-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dbab0-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbab0-128"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="dbab0-128"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="dbab0-129">Data/ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="dbab0-129">Start date/time for the time range.</span></span> <span data-ttu-id="dbab0-130">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="dbab0-130">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="dbab0-131">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="dbab0-131">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="dbab0-132">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="dbab0-132">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="dbab0-133">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="dbab0-133">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="dbab0-134">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="dbab0-134">7/17/12012</span></span></p>
<p><span data-ttu-id="dbab0-135">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="dbab0-135">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="dbab0-136">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="dbab0-136">7/13/2012</span></span></p>
<p><span data-ttu-id="dbab0-137">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="dbab0-137">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbab0-138"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="dbab0-138"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="dbab0-139">Data/ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="dbab0-139">End date/time for the time range.</span></span> <span data-ttu-id="dbab0-140">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="dbab0-140">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="dbab0-141">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="dbab0-141">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="dbab0-142">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="dbab0-142">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="dbab0-143">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="dbab0-143">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="dbab0-144">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="dbab0-144">7/17/12012</span></span></p>
<p><span data-ttu-id="dbab0-145">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="dbab0-145">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="dbab0-146">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="dbab0-146">7/13/2012</span></span></p>
<p><span data-ttu-id="dbab0-147">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="dbab0-147">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbab0-148"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="dbab0-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="dbab0-149">Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="dbab0-149">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="dbab0-150">È possibile selezionare un singolo pool o fare clic su <strong>[tutti]</strong> per visualizzare i dati per tutti i pool.</span><span class="sxs-lookup"><span data-stu-id="dbab0-150">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="dbab0-151">Questo elenco a discesa viene compilato automaticamente in base ai record nel database.</span><span class="sxs-lookup"><span data-stu-id="dbab0-151">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbab0-152"><strong>Tipo di attività</strong></span><span class="sxs-lookup"><span data-stu-id="dbab0-152"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="dbab0-153">Tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="dbab0-153">Type of activity.</span></span> <span data-ttu-id="dbab0-154">Selezionare una delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="dbab0-154">Select one of the following activities:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbab0-155">Tutti</span><span class="sxs-lookup"><span data-stu-id="dbab0-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="dbab0-156">Peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="dbab0-156">Peer-to-Peer</span></span></p></li>
<li><p><span data-ttu-id="dbab0-157">Conferenza</span><span class="sxs-lookup"><span data-stu-id="dbab0-157">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbab0-158"><strong>Categoria chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="dbab0-158"><strong>Call category</strong></span></span></p></td>
<td><p><span data-ttu-id="dbab0-159">Indica il motivo per cui è stato usato CAC per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="dbab0-159">Indicates the reason that CAC was used for the call.</span></span> <span data-ttu-id="dbab0-160">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dbab0-160">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbab0-161">Tutti</span><span class="sxs-lookup"><span data-stu-id="dbab0-161">[All]</span></span></p></li>
<li><p><span data-ttu-id="dbab0-162">Chiamata rifiutata a causa del controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="dbab0-162">Call rejected because of call admission control</span></span></p></li>
<li><p><span data-ttu-id="dbab0-163">Chiamate reinstradate tramite PSTN a causa del controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="dbab0-163">Calls rerouted through PSTN because of call admission control</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="dbab0-164">Metriche per le sessioni peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="dbab0-164">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="dbab0-165">La tabella seguente elenca le informazioni fornite nel report di controllo dell'ammissione delle chiamate per le sessioni peer-to-peer, ovvero le sessioni che coinvolgono solo due partecipanti.</span><span class="sxs-lookup"><span data-stu-id="dbab0-165">The following table lists the information provided in the Call Admission Control Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="dbab0-166">Metriche per le sessioni peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="dbab0-166">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbab0-167">Nome</span><span class="sxs-lookup"><span data-stu-id="dbab0-167">Name</span></span></th>
<th><span data-ttu-id="dbab0-168">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="dbab0-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="dbab0-169">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dbab0-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbab0-170"><strong>Dettaglio</strong></span><span class="sxs-lookup"><span data-stu-id="dbab0-170"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="dbab0-171">No</span><span class="sxs-lookup"><span data-stu-id="dbab0-171">No</span></span></p></td>
<td><p><span data-ttu-id="dbab0-172">Quando si fa clic su questo elemento, il report Mostra un report Dettagli sessione peer-to-peer per la sessione specificata.</span><span class="sxs-lookup"><span data-stu-id="dbab0-172">When you click this item, the report shows you a Peer-to-Peer Session Detail Report for the specified session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbab0-173"><strong>Dall'utente</strong></span><span class="sxs-lookup"><span data-stu-id="dbab0-173"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="dbab0-174">Sì</span><span class="sxs-lookup"><span data-stu-id="dbab0-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbab0-175">Indirizzo SIP dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="dbab0-175">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbab0-176"><strong>All'utente</strong></span><span class="sxs-lookup"><span data-stu-id="dbab0-176"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="dbab0-177">Sì</span><span class="sxs-lookup"><span data-stu-id="dbab0-177">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbab0-178">Indirizzo SIP dell'utente invitato a partecipare alla sessione.</span><span class="sxs-lookup"><span data-stu-id="dbab0-178">SIP address of the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbab0-179"><strong>Modalità</strong></span><span class="sxs-lookup"><span data-stu-id="dbab0-179"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="dbab0-180">Sì</span><span class="sxs-lookup"><span data-stu-id="dbab0-180">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbab0-181">Modalità di comunicazione (ad esempio audio e video) usate durante la sessione.</span><span class="sxs-lookup"><span data-stu-id="dbab0-181">Communication modalities (such as audio and video) that were used during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbab0-182"><strong>Invitare il tempo</strong></span><span class="sxs-lookup"><span data-stu-id="dbab0-182"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="dbab0-183">Sì</span><span class="sxs-lookup"><span data-stu-id="dbab0-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbab0-184">Data e ora in cui l'invito alla sessione iniziale è stato inviato all'utente da.</span><span class="sxs-lookup"><span data-stu-id="dbab0-184">Date and time the initial session invitation was sent to the From user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbab0-185"><strong>Tempo di risposta</strong></span><span class="sxs-lookup"><span data-stu-id="dbab0-185"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="dbab0-186">Sì</span><span class="sxs-lookup"><span data-stu-id="dbab0-186">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbab0-187">Data e ora in cui è stata ricevuta l'accettazione dell'invito.</span><span class="sxs-lookup"><span data-stu-id="dbab0-187">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbab0-188"><strong>Ora di fine</strong></span><span class="sxs-lookup"><span data-stu-id="dbab0-188"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="dbab0-189">Sì</span><span class="sxs-lookup"><span data-stu-id="dbab0-189">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbab0-190">Data e ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="dbab0-190">Date and time that the session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbab0-191"><strong>ID diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="dbab0-191"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="dbab0-192">Sì</span><span class="sxs-lookup"><span data-stu-id="dbab0-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbab0-193">Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori.</span><span class="sxs-lookup"><span data-stu-id="dbab0-193">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="dbab0-194">Le intestazioni di diagnostica sono facoltative (è possibile avere sessioni SIP che non includono queste intestazioni) e gli ID di diagnostica vengono riportati solo per le sessioni con problemi di qualche tipo.</span><span class="sxs-lookup"><span data-stu-id="dbab0-194">Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="dbab0-195">Metriche per le sessioni di conferenza</span><span class="sxs-lookup"><span data-stu-id="dbab0-195">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="dbab0-196">Nella tabella seguente sono elencate le informazioni fornite nel report di controllo dell'ammissione alle chiamate per le sessioni di conferenza, ovvero le sessioni che coinvolgono tre o più partecipanti.</span><span class="sxs-lookup"><span data-stu-id="dbab0-196">The following table lists the information provided in the Call Admission Control Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="dbab0-197">Metriche per le sessioni di conferenza</span><span class="sxs-lookup"><span data-stu-id="dbab0-197">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbab0-198">Nome</span><span class="sxs-lookup"><span data-stu-id="dbab0-198">Name</span></span></th>
<th><span data-ttu-id="dbab0-199">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="dbab0-199">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="dbab0-200">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dbab0-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbab0-201"><strong>URI conferenza</strong></span><span class="sxs-lookup"><span data-stu-id="dbab0-201"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="dbab0-202">Sì</span><span class="sxs-lookup"><span data-stu-id="dbab0-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbab0-203">Identificatore univoco per la conferenza.</span><span class="sxs-lookup"><span data-stu-id="dbab0-203">Unique identifier for the conference.</span></span> <span data-ttu-id="dbab0-204">Quando si fa clic su questo elemento, il report Mostra i singoli partecipanti alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="dbab0-204">When you click this item, the report shows the individual conference participants.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbab0-205"><strong>Organizzatore</strong></span><span class="sxs-lookup"><span data-stu-id="dbab0-205"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="dbab0-206">Sì</span><span class="sxs-lookup"><span data-stu-id="dbab0-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbab0-207">Indirizzo SIP dell'utente che ha organizzato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="dbab0-207">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbab0-208"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="dbab0-208"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="dbab0-209">Sì</span><span class="sxs-lookup"><span data-stu-id="dbab0-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbab0-210">Server perimetrale usato nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="dbab0-210">Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbab0-211"><strong>Ora di inizio</strong></span><span class="sxs-lookup"><span data-stu-id="dbab0-211"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="dbab0-212">Sì</span><span class="sxs-lookup"><span data-stu-id="dbab0-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbab0-213">Data e ora in cui è stata avviata la conferenza.</span><span class="sxs-lookup"><span data-stu-id="dbab0-213">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbab0-214"><strong>Ora di fine</strong></span><span class="sxs-lookup"><span data-stu-id="dbab0-214"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="dbab0-215">Sì</span><span class="sxs-lookup"><span data-stu-id="dbab0-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbab0-216">Data e ora di fine della conferenza.</span><span class="sxs-lookup"><span data-stu-id="dbab0-216">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="dbab0-217">Metriche per singoli partecipanti alla conferenza</span><span class="sxs-lookup"><span data-stu-id="dbab0-217">Metrics for Individual Conference Participants</span></span>

<span data-ttu-id="dbab0-218">Nella tabella seguente sono elencate le informazioni fornite nel report di controllo dell'ammissione delle chiamate per singoli partecipanti alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="dbab0-218">The following table lists the information provided in the Call Admission Control Report for individual conference participants.</span></span>

### <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="dbab0-219">Metriche per singoli partecipanti alla conferenza</span><span class="sxs-lookup"><span data-stu-id="dbab0-219">Metrics for Individual Conference Participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbab0-220">Nome</span><span class="sxs-lookup"><span data-stu-id="dbab0-220">Name</span></span></th>
<th><span data-ttu-id="dbab0-221">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="dbab0-221">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="dbab0-222">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dbab0-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbab0-223"><strong>Ruolo</strong></span><span class="sxs-lookup"><span data-stu-id="dbab0-223"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="dbab0-224">No</span><span class="sxs-lookup"><span data-stu-id="dbab0-224">No</span></span></p></td>
<td><p><span data-ttu-id="dbab0-225">Ruolo (ad esempio, relatore) riprodotto dal partecipante alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="dbab0-225">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbab0-226"><strong>Partecipante</strong></span><span class="sxs-lookup"><span data-stu-id="dbab0-226"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="dbab0-227">No</span><span class="sxs-lookup"><span data-stu-id="dbab0-227">No</span></span></p></td>
<td><p><span data-ttu-id="dbab0-228">Indirizzo SIP del partecipante alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="dbab0-228">SIP address of the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbab0-229"><strong>Connettività</strong></span><span class="sxs-lookup"><span data-stu-id="dbab0-229"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="dbab0-230">No</span><span class="sxs-lookup"><span data-stu-id="dbab0-230">No</span></span></p></td>
<td><p><span data-ttu-id="dbab0-231">Connettività di rete (in genere da interno o da esterno) per il partecipante.</span><span class="sxs-lookup"><span data-stu-id="dbab0-231">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbab0-232"><strong>Modalità</strong></span><span class="sxs-lookup"><span data-stu-id="dbab0-232"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="dbab0-233">No</span><span class="sxs-lookup"><span data-stu-id="dbab0-233">No</span></span></p></td>
<td><p><span data-ttu-id="dbab0-234">Tipo di conferenza (ad esempio, A/V Conferencing).</span><span class="sxs-lookup"><span data-stu-id="dbab0-234">Conference type (for example, A/V conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbab0-235"><strong>Tempo di partecipazione</strong></span><span class="sxs-lookup"><span data-stu-id="dbab0-235"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="dbab0-236">No</span><span class="sxs-lookup"><span data-stu-id="dbab0-236">No</span></span></p></td>
<td><p><span data-ttu-id="dbab0-237">Data e ora in cui il partecipante ha partecipato alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="dbab0-237">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbab0-238"><strong>Ora di uscita</strong></span><span class="sxs-lookup"><span data-stu-id="dbab0-238"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="dbab0-239">No</span><span class="sxs-lookup"><span data-stu-id="dbab0-239">No</span></span></p></td>
<td><p><span data-ttu-id="dbab0-240">Data e ora in cui il partecipante ha lasciato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="dbab0-240">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbab0-241"><strong>ID diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="dbab0-241"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="dbab0-242">No</span><span class="sxs-lookup"><span data-stu-id="dbab0-242">No</span></span></p></td>
<td><p><span data-ttu-id="dbab0-243">Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori.</span><span class="sxs-lookup"><span data-stu-id="dbab0-243">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="dbab0-244">Le intestazioni di diagnostica sono facoltative (è possibile avere sessioni SIP che non includono queste intestazioni) e gli ID di diagnostica vengono riportati solo per le sessioni con problemi di qualche tipo.</span><span class="sxs-lookup"><span data-stu-id="dbab0-244">Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

