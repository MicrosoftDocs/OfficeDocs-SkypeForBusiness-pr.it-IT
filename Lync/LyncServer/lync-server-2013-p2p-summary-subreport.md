---
title: 'Lync Server 2013: sottoreport di riepilogo P2P'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: P2P Summary Subreport
ms:assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205416(v=OCS.15)
ms:contentKeyID: 48185950
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3cff1eb86376068d53651f0d88224bf7f030921
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="p2p-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="883d0-102">Sottoreport di riepilogo P2P in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="883d0-102">P2P Summary Subreport in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="883d0-103">_**Argomento Ultima modifica:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="883d0-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="883d0-104">Il sottoreport di riepilogo P2P offre una visualizzazione complessiva delle sessioni di comunicazione peer-to-peer non riuscite.</span><span class="sxs-lookup"><span data-stu-id="883d0-104">The P2P Summary Subreport provides an overall view of your failed peer-to-peer communication sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="883d0-105">Filtri</span><span class="sxs-lookup"><span data-stu-id="883d0-105">Filters</span></span>

<span data-ttu-id="883d0-106">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="883d0-106">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="883d0-107">Nella tabella seguente sono elencati i filtri che è possibile usare con il sottoreport di riepilogo P2P.</span><span class="sxs-lookup"><span data-stu-id="883d0-107">The following table lists the filters that you can use with the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-filters"></a><span data-ttu-id="883d0-108">Filtri per i sottoreport di riepilogo P2P</span><span class="sxs-lookup"><span data-stu-id="883d0-108">P2P Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="883d0-109">Nome</span><span class="sxs-lookup"><span data-stu-id="883d0-109">Name</span></span></th>
<th><span data-ttu-id="883d0-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="883d0-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="883d0-111"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="883d0-111"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="883d0-112">Data e ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="883d0-112">Start date and time for the time range.</span></span> <span data-ttu-id="883d0-113">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="883d0-113">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="883d0-114">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="883d0-114">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="883d0-115">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="883d0-115">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="883d0-116">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="883d0-116">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="883d0-117">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="883d0-117">7/7/2012</span></span></p>
<p><span data-ttu-id="883d0-118">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="883d0-118">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="883d0-119">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="883d0-119">7/3/2012</span></span></p>
<p><span data-ttu-id="883d0-120">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="883d0-120">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="883d0-121"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="883d0-121"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="883d0-122">Data e ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="883d0-122">End date and time for the time range.</span></span> <span data-ttu-id="883d0-123">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="883d0-123">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="883d0-124">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="883d0-124">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="883d0-125">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="883d0-125">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="883d0-126">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="883d0-126">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="883d0-127">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="883d0-127">7/7/2012</span></span></p>
<p><span data-ttu-id="883d0-128">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="883d0-128">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="883d0-129">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="883d0-129">7/3/2012</span></span></p>
<p><span data-ttu-id="883d0-130">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="883d0-130">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="883d0-131"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="883d0-131"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="883d0-132">Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="883d0-132">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="883d0-133">È possibile selezionare un singolo pool o fare clic su <strong>[tutti]</strong> per visualizzare i dati per tutti i pool.</span><span class="sxs-lookup"><span data-stu-id="883d0-133">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="883d0-134">Questo elenco a discesa viene compilato automaticamente in base ai record nel database.</span><span class="sxs-lookup"><span data-stu-id="883d0-134">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="883d0-135">Metriche</span><span class="sxs-lookup"><span data-stu-id="883d0-135">Metrics</span></span>

<span data-ttu-id="883d0-136">La tabella seguente elenca le informazioni fornite nel sottoreport di riepilogo P2P.</span><span class="sxs-lookup"><span data-stu-id="883d0-136">The following table lists the information provided in the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-metrics"></a><span data-ttu-id="883d0-137">Metriche per il sottoreport di riepilogo P2P</span><span class="sxs-lookup"><span data-stu-id="883d0-137">P2P Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="883d0-138">Nome</span><span class="sxs-lookup"><span data-stu-id="883d0-138">Name</span></span></th>
<th><span data-ttu-id="883d0-139">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="883d0-139">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="883d0-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="883d0-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="883d0-141"><strong>Totale sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="883d0-141"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="883d0-142">No</span><span class="sxs-lookup"><span data-stu-id="883d0-142">No</span></span></p></td>
<td><p><span data-ttu-id="883d0-143">Numero totale di sessioni, incluse le sessioni di successo, le sessioni non riuscite (errori previsti e gli errori imprevisti) e le sessioni Uncategorized.</span><span class="sxs-lookup"><span data-stu-id="883d0-143">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="883d0-144"><strong>Tasso di errore</strong></span><span class="sxs-lookup"><span data-stu-id="883d0-144"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="883d0-145">No</span><span class="sxs-lookup"><span data-stu-id="883d0-145">No</span></span></p></td>
<td><p><span data-ttu-id="883d0-146">Percentuale di sessioni peer-to-peer non riuscite.</span><span class="sxs-lookup"><span data-stu-id="883d0-146">Percentage of peer-to-peer sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="883d0-147"><strong>Sessioni per modalità</strong></span><span class="sxs-lookup"><span data-stu-id="883d0-147"><strong>Sessions by Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="883d0-148">No</span><span class="sxs-lookup"><span data-stu-id="883d0-148">No</span></span></p></td>
<td><p><span data-ttu-id="883d0-149">Numero totale di sessioni raggruppate per modalità, ad esempio la messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="883d0-149">Total number of sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="883d0-150"><strong>Tasso di errore per modalità</strong></span><span class="sxs-lookup"><span data-stu-id="883d0-150"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="883d0-151">No</span><span class="sxs-lookup"><span data-stu-id="883d0-151">No</span></span></p></td>
<td><p><span data-ttu-id="883d0-152">Numero totale di sessioni non riuscite raggruppate per modalità, ad esempio la messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="883d0-152">Total number of failed sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

