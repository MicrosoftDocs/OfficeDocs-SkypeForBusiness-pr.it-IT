---
title: 'Lync Server 2013: sottoreport riepilogativo P2P'
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
ms.openlocfilehash: 345a659d3edfe8542391719ed4b90717b45a3c35
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="p2p-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="771d4-102">Sottoreport riepilogativo P2P in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="771d4-102">P2P Summary Subreport in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="771d4-103">_**Ultimo argomento modificato:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="771d4-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="771d4-104">Nel sottoreport riepilogativo P2P viene fornita una panoramica delle sessioni di comunicazione peer-to-peer non riuscite.</span><span class="sxs-lookup"><span data-stu-id="771d4-104">The P2P Summary Subreport provides an overall view of your failed peer-to-peer communication sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="771d4-105">Filtri</span><span class="sxs-lookup"><span data-stu-id="771d4-105">Filters</span></span>

<span data-ttu-id="771d4-p101">I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Nella tabella riportata di seguito vengono elencati i filtri che è possibile utilizzare con il sottoreport riepilogativo P2P.</span><span class="sxs-lookup"><span data-stu-id="771d4-p101">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-filters"></a><span data-ttu-id="771d4-108">Filtri del sottoreport riepilogativo P2P</span><span class="sxs-lookup"><span data-stu-id="771d4-108">P2P Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="771d4-109">Name</span><span class="sxs-lookup"><span data-stu-id="771d4-109">Name</span></span></th>
<th><span data-ttu-id="771d4-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="771d4-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="771d4-111"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="771d4-111"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="771d4-p102">Data e ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, inserire sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="771d4-p102">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="771d4-114">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="771d4-114">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="771d4-p103">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="771d4-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="771d4-117">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="771d4-117">7/7/2012</span></span></p>
<p><span data-ttu-id="771d4-118">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="771d4-118">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="771d4-119">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="771d4-119">7/3/2012</span></span></p>
<p><span data-ttu-id="771d4-120">Le settimane iniziano sempre con il lunedì e terminano con la domenica.</span><span class="sxs-lookup"><span data-stu-id="771d4-120">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="771d4-121"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="771d4-121"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="771d4-p104">Data e ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, inserire sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="771d4-p104">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="771d4-124">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="771d4-124">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="771d4-p105">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="771d4-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="771d4-127">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="771d4-127">7/7/2012</span></span></p>
<p><span data-ttu-id="771d4-128">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="771d4-128">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="771d4-129">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="771d4-129">7/3/2012</span></span></p>
<p><span data-ttu-id="771d4-130">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="771d4-130">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="771d4-131"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="771d4-131"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="771d4-p106">Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool oppure fare clic su <strong>[Tutto]</strong> per visualizzare i dati di tutti i pool. Le voci disponibili in questo elenco a discesa vengono inserite automaticamente in base ai record presenti nel database.</span><span class="sxs-lookup"><span data-stu-id="771d4-p106">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="771d4-135">Metriche</span><span class="sxs-lookup"><span data-stu-id="771d4-135">Metrics</span></span>

<span data-ttu-id="771d4-136">Nella tabella seguente sono elencate le informazioni fornite nel sottoreport riepilogativo P2P.</span><span class="sxs-lookup"><span data-stu-id="771d4-136">The following table lists the information provided in the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-metrics"></a><span data-ttu-id="771d4-137">Metriche del sottoreport riepilogativo P2P</span><span class="sxs-lookup"><span data-stu-id="771d4-137">P2P Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="771d4-138">Name</span><span class="sxs-lookup"><span data-stu-id="771d4-138">Name</span></span></th>
<th><span data-ttu-id="771d4-139">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="771d4-139">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="771d4-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="771d4-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="771d4-141"><strong>Totale sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="771d4-141"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="771d4-142">No</span><span class="sxs-lookup"><span data-stu-id="771d4-142">No</span></span></p></td>
<td><p><span data-ttu-id="771d4-143">Numero totale di sessioni, comprendente le sessioni con esito positivo, le sessioni con esito negativo (per errori sia previsti che imprevisti) e le sessioni senza categoria.</span><span class="sxs-lookup"><span data-stu-id="771d4-143">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="771d4-144"><strong>Frequenza errori</strong></span><span class="sxs-lookup"><span data-stu-id="771d4-144"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="771d4-145">No</span><span class="sxs-lookup"><span data-stu-id="771d4-145">No</span></span></p></td>
<td><p><span data-ttu-id="771d4-146">Percentuale delle sessioni peer-to-peer non riuscite.</span><span class="sxs-lookup"><span data-stu-id="771d4-146">Percentage of peer-to-peer sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="771d4-147"><strong>Sessioni per modalità</strong></span><span class="sxs-lookup"><span data-stu-id="771d4-147"><strong>Sessions by Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="771d4-148">No</span><span class="sxs-lookup"><span data-stu-id="771d4-148">No</span></span></p></td>
<td><p><span data-ttu-id="771d4-149">Numero totale di sessioni raggruppate per modalità (ad esempio, messaggistica istantanea).</span><span class="sxs-lookup"><span data-stu-id="771d4-149">Total number of sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="771d4-150"><strong>Frequenza errori per modalità</strong></span><span class="sxs-lookup"><span data-stu-id="771d4-150"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="771d4-151">No</span><span class="sxs-lookup"><span data-stu-id="771d4-151">No</span></span></p></td>
<td><p><span data-ttu-id="771d4-152">Numero totale di sessioni non riuscite raggruppate per modalità (ad esempio, messaggistica istantanea).</span><span class="sxs-lookup"><span data-stu-id="771d4-152">Total number of failed sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

