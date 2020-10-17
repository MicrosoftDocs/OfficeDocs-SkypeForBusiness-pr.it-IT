---
title: 'Lync Server 2013: sottoreport riepilogativo P2P'
description: 'Lync Server 2013: sottoreport riepilogativo P2P.'
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
ms.openlocfilehash: eda51e76c4ed7b62535a2a2e4ab52982aa6381f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557382"
---
# <a name="p2p-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="759c5-103">Sottoreport riepilogativo P2P in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="759c5-103">P2P Summary Subreport in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="759c5-104">_**Ultimo argomento modificato:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="759c5-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="759c5-105">Nel sottoreport riepilogativo P2P viene fornita una panoramica delle sessioni di comunicazione peer-to-peer non riuscite.</span><span class="sxs-lookup"><span data-stu-id="759c5-105">The P2P Summary Subreport provides an overall view of your failed peer-to-peer communication sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="759c5-106">Filtri</span><span class="sxs-lookup"><span data-stu-id="759c5-106">Filters</span></span>

<span data-ttu-id="759c5-p101">I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Nella tabella riportata di seguito vengono elencati i filtri che è possibile utilizzare con il sottoreport riepilogativo P2P.</span><span class="sxs-lookup"><span data-stu-id="759c5-p101">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-filters"></a><span data-ttu-id="759c5-109">Filtri del sottoreport riepilogativo P2P</span><span class="sxs-lookup"><span data-stu-id="759c5-109">P2P Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="759c5-110">Nome</span><span class="sxs-lookup"><span data-stu-id="759c5-110">Name</span></span></th>
<th><span data-ttu-id="759c5-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="759c5-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="759c5-112"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="759c5-112"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="759c5-p102">Data e ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, inserire sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="759c5-p102">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="759c5-115">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="759c5-115">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="759c5-p103">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="759c5-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="759c5-118">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="759c5-118">7/7/2012</span></span></p>
<p><span data-ttu-id="759c5-119">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="759c5-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="759c5-120">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="759c5-120">7/3/2012</span></span></p>
<p><span data-ttu-id="759c5-121">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="759c5-121">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="759c5-122"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="759c5-122"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="759c5-p104">Data e ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, inserire sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="759c5-p104">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="759c5-125">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="759c5-125">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="759c5-p105">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="759c5-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="759c5-128">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="759c5-128">7/7/2012</span></span></p>
<p><span data-ttu-id="759c5-129">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="759c5-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="759c5-130">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="759c5-130">7/3/2012</span></span></p>
<p><span data-ttu-id="759c5-131">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="759c5-131">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="759c5-132"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="759c5-132"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="759c5-p106">Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool oppure fare clic su <strong>[Tutto]</strong> per visualizzare i dati di tutti i pool. Le voci disponibili in questo elenco a discesa vengono inserite automaticamente in base ai record presenti nel database.</span><span class="sxs-lookup"><span data-stu-id="759c5-p106">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="759c5-136">Metriche</span><span class="sxs-lookup"><span data-stu-id="759c5-136">Metrics</span></span>

<span data-ttu-id="759c5-137">Nella tabella seguente sono elencate le informazioni fornite nel sottoreport riepilogativo P2P.</span><span class="sxs-lookup"><span data-stu-id="759c5-137">The following table lists the information provided in the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-metrics"></a><span data-ttu-id="759c5-138">Metriche del sottoreport riepilogativo P2P</span><span class="sxs-lookup"><span data-stu-id="759c5-138">P2P Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="759c5-139">Nome</span><span class="sxs-lookup"><span data-stu-id="759c5-139">Name</span></span></th>
<th><span data-ttu-id="759c5-140">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="759c5-140">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="759c5-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="759c5-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="759c5-142"><strong>Totale sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="759c5-142"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="759c5-143">No</span><span class="sxs-lookup"><span data-stu-id="759c5-143">No</span></span></p></td>
<td><p><span data-ttu-id="759c5-144">Numero totale di sessioni, comprendente le sessioni con esito positivo, le sessioni con esito negativo (per errori sia previsti che imprevisti) e le sessioni senza categoria.</span><span class="sxs-lookup"><span data-stu-id="759c5-144">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="759c5-145"><strong>Frequenza errori</strong></span><span class="sxs-lookup"><span data-stu-id="759c5-145"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="759c5-146">No</span><span class="sxs-lookup"><span data-stu-id="759c5-146">No</span></span></p></td>
<td><p><span data-ttu-id="759c5-147">Percentuale delle sessioni peer-to-peer non riuscite.</span><span class="sxs-lookup"><span data-stu-id="759c5-147">Percentage of peer-to-peer sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="759c5-148"><strong>Sessioni per modalità</strong></span><span class="sxs-lookup"><span data-stu-id="759c5-148"><strong>Sessions by Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="759c5-149">No</span><span class="sxs-lookup"><span data-stu-id="759c5-149">No</span></span></p></td>
<td><p><span data-ttu-id="759c5-150">Numero totale di sessioni raggruppate per modalità (ad esempio, messaggistica istantanea).</span><span class="sxs-lookup"><span data-stu-id="759c5-150">Total number of sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="759c5-151"><strong>Frequenza errori per modalità</strong></span><span class="sxs-lookup"><span data-stu-id="759c5-151"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="759c5-152">No</span><span class="sxs-lookup"><span data-stu-id="759c5-152">No</span></span></p></td>
<td><p><span data-ttu-id="759c5-153">Numero totale di sessioni non riuscite raggruppate per modalità (ad esempio, messaggistica istantanea).</span><span class="sxs-lookup"><span data-stu-id="759c5-153">Total number of failed sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

