---
title: 'Lync Server 2013: sottoreport riepilogo conferenze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Summary Subreport
ms:assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204779(v=OCS.15)
ms:contentKeyID: 48183742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b87ea9648404f495f487a639a3b11900f91dcda4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="3b285-102">Sottoreport riepilogo conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b285-102">Conference Summary Subreport in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b285-103">_**Argomento Ultima modifica:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="3b285-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="3b285-104">Il sottoreport riepilogo conferenze offre una visualizzazione complessiva delle sessioni di conferenza non riuscite.</span><span class="sxs-lookup"><span data-stu-id="3b285-104">The Conference Summary Subreport provides an overall view of failed conference sessions.</span></span> <span data-ttu-id="3b285-105">Queste sessioni non riuscite sono ulteriormente suddivise per tipo di sessione: sessioni di stato di attivazione e sessioni MCU.</span><span class="sxs-lookup"><span data-stu-id="3b285-105">These failed sessions are further broken down by session type: Focus sessions and MCU sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="3b285-106">Filtri</span><span class="sxs-lookup"><span data-stu-id="3b285-106">Filters</span></span>

<span data-ttu-id="3b285-107">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="3b285-107">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="3b285-108">Nella tabella seguente sono elencati i filtri che è possibile usare con il sottoreport di riepilogo conferenza.</span><span class="sxs-lookup"><span data-stu-id="3b285-108">The following table lists the filters that you can use with the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-filters"></a><span data-ttu-id="3b285-109">Filtri per i sottoreport di riepilogo conferenza</span><span class="sxs-lookup"><span data-stu-id="3b285-109">Conference Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b285-110">Nome</span><span class="sxs-lookup"><span data-stu-id="3b285-110">Name</span></span></th>
<th><span data-ttu-id="3b285-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3b285-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b285-112"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="3b285-112"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="3b285-113">Data/ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="3b285-113">Start date/time for the time range.</span></span> <span data-ttu-id="3b285-114">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="3b285-114">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="3b285-115">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="3b285-115">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="3b285-116">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="3b285-116">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="3b285-117">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="3b285-117">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="3b285-118">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="3b285-118">7/7/2012</span></span></p>
<p><span data-ttu-id="3b285-119">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="3b285-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="3b285-120">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="3b285-120">7/3/2012</span></span></p>
<p><span data-ttu-id="3b285-121">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="3b285-121">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b285-122"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="3b285-122"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="3b285-123">Data/ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="3b285-123">End date/time for the time range.</span></span> <span data-ttu-id="3b285-124">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="3b285-124">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="3b285-125">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="3b285-125">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="3b285-126">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="3b285-126">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="3b285-127">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="3b285-127">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="3b285-128">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="3b285-128">7/7/2012</span></span></p>
<p><span data-ttu-id="3b285-129">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="3b285-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="3b285-130">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="3b285-130">7/3/2012</span></span></p>
<p><span data-ttu-id="3b285-131">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="3b285-131">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b285-132"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="3b285-132"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="3b285-133">Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="3b285-133">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="3b285-134">È possibile selezionare un singolo pool o fare clic su <strong>[tutti]</strong> per visualizzare i dati per tutti i pool.</span><span class="sxs-lookup"><span data-stu-id="3b285-134">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="3b285-135">Questo elenco a discesa viene compilato automaticamente in base ai record nel database.</span><span class="sxs-lookup"><span data-stu-id="3b285-135">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="3b285-136">Metriche</span><span class="sxs-lookup"><span data-stu-id="3b285-136">Metrics</span></span>

<span data-ttu-id="3b285-137">Nella tabella seguente sono elencate le informazioni fornite nel sottoreport di riepilogo conferenza.</span><span class="sxs-lookup"><span data-stu-id="3b285-137">The following table lists the information provided in the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-metrics"></a><span data-ttu-id="3b285-138">Metriche del sottoreport di riepilogo conferenza</span><span class="sxs-lookup"><span data-stu-id="3b285-138">Conference Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b285-139">Nome</span><span class="sxs-lookup"><span data-stu-id="3b285-139">Name</span></span></th>
<th><span data-ttu-id="3b285-140">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="3b285-140">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="3b285-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3b285-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b285-142"><strong>Totale conferenze</strong></span><span class="sxs-lookup"><span data-stu-id="3b285-142"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="3b285-143">No</span><span class="sxs-lookup"><span data-stu-id="3b285-143">No</span></span></p></td>
<td><p><span data-ttu-id="3b285-144">Numero totale di conferenze organizzate.</span><span class="sxs-lookup"><span data-stu-id="3b285-144">Total number of conferences held.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b285-145"><strong>Totale delle sessioni di conferenza</strong></span><span class="sxs-lookup"><span data-stu-id="3b285-145"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="3b285-146">No</span><span class="sxs-lookup"><span data-stu-id="3b285-146">No</span></span></p></td>
<td><p><span data-ttu-id="3b285-147">Numero totale di sessioni di conferenza.</span><span class="sxs-lookup"><span data-stu-id="3b285-147">Total number of conference sessions.</span></span> <span data-ttu-id="3b285-148">Una singola conferenza può avere più sessioni; ad esempio, una conferenza può includere sia una sessione dello stato di attivazione che una sessione MCU.</span><span class="sxs-lookup"><span data-stu-id="3b285-148">A single conference can have multiple sessions; for example, a conference might include both a Focus session and an MCU session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b285-149"><strong>Tasso di errore complessivo della sessione</strong></span><span class="sxs-lookup"><span data-stu-id="3b285-149"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="3b285-150">No</span><span class="sxs-lookup"><span data-stu-id="3b285-150">No</span></span></p></td>
<td><p><span data-ttu-id="3b285-151">Percentuale di tutte le conferenze non riuscite.</span><span class="sxs-lookup"><span data-stu-id="3b285-151">Percentage of all conferences that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b285-152"><strong>Sessioni di stato attiva</strong></span><span class="sxs-lookup"><span data-stu-id="3b285-152"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="3b285-153">No</span><span class="sxs-lookup"><span data-stu-id="3b285-153">No</span></span></p></td>
<td><p><span data-ttu-id="3b285-154">Numero totale di sessioni di stato attivate.</span><span class="sxs-lookup"><span data-stu-id="3b285-154">Total number of Focus sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b285-155"><strong>Tasso di errore dello stato di avanzamento</strong></span><span class="sxs-lookup"><span data-stu-id="3b285-155"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="3b285-156">No</span><span class="sxs-lookup"><span data-stu-id="3b285-156">No</span></span></p></td>
<td><p><span data-ttu-id="3b285-157">Percentuale delle sessioni di stato di attivazione non riuscite.</span><span class="sxs-lookup"><span data-stu-id="3b285-157">Percentage of Focus sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b285-158">Sessioni MCU</span><span class="sxs-lookup"><span data-stu-id="3b285-158">MCU sessions</span></span></p></td>
<td><p><span data-ttu-id="3b285-159">No</span><span class="sxs-lookup"><span data-stu-id="3b285-159">No</span></span></p></td>
<td><p><span data-ttu-id="3b285-160">Numero totale di sessioni MCU.</span><span class="sxs-lookup"><span data-stu-id="3b285-160">Total number of MCU sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b285-161"><strong>Tasso di errore MCU</strong></span><span class="sxs-lookup"><span data-stu-id="3b285-161"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="3b285-162">No</span><span class="sxs-lookup"><span data-stu-id="3b285-162">No</span></span></p></td>
<td><p><span data-ttu-id="3b285-163">Percentuale di sessioni MCU non riuscite.</span><span class="sxs-lookup"><span data-stu-id="3b285-163">Percentage of MCU sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b285-164"><strong>Sessioni MCU per modalità</strong></span><span class="sxs-lookup"><span data-stu-id="3b285-164"><strong>MCU sessions by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="3b285-165">No</span><span class="sxs-lookup"><span data-stu-id="3b285-165">No</span></span></p></td>
<td><p><span data-ttu-id="3b285-166">Numero totale di sessioni MCU, raggruppate per modalità (ad esempio, servizi di conferenza di messaggistica istantanea).</span><span class="sxs-lookup"><span data-stu-id="3b285-166">Total number of MCU sessions, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b285-167"><strong>Tasso di errore per modalità</strong></span><span class="sxs-lookup"><span data-stu-id="3b285-167"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="3b285-168">No</span><span class="sxs-lookup"><span data-stu-id="3b285-168">No</span></span></p></td>
<td><p><span data-ttu-id="3b285-169">Percentuale di sessioni MCU non riuscite, raggruppate per modalità (ad esempio, servizi di conferenza di messaggistica istantanea).</span><span class="sxs-lookup"><span data-stu-id="3b285-169">Percentage of MCU sessions that failed, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

