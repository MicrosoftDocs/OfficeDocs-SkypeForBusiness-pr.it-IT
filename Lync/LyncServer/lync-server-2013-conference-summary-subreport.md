---
title: 'Lync Server 2013: sottorapporto riepilogativo conferenze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Subreport
ms:assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204779(v=OCS.15)
ms:contentKeyID: 48183742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8cc92efe91b1618cd6d0f4f9cdaaf6cdf09730d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="54372-102">Sottoreport riepilogativo conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54372-102">Conference Summary Subreport in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54372-103">_**Ultimo argomento modificato:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="54372-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="54372-p101">Il sottorapporto riepilogativo conferenze offre una visualizzazione generale delle sessioni di conferenza non riuscite. Tali sessioni vengono ulteriormente suddivise per tipo: sessioni Focus e sessioni MCU.</span><span class="sxs-lookup"><span data-stu-id="54372-p101">The Conference Summary Subreport provides an overall view of failed conference sessions. These failed sessions are further broken down by session type: Focus sessions and MCU sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="54372-106">Filtri</span><span class="sxs-lookup"><span data-stu-id="54372-106">Filters</span></span>

<span data-ttu-id="54372-p102">I filtri consentono di restituire un set di dati più appropriato, nonché visualizzare i dati restituiti in diversi modi. Nella tabella che segue sono elencati i filtri che è possibile usare con il sottorapporto riepilogativo conferenze.</span><span class="sxs-lookup"><span data-stu-id="54372-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-filters"></a><span data-ttu-id="54372-109">Filtri del sottorapporto riepilogativo conferenze</span><span class="sxs-lookup"><span data-stu-id="54372-109">Conference Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54372-110">Name</span><span class="sxs-lookup"><span data-stu-id="54372-110">Name</span></span></th>
<th><span data-ttu-id="54372-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="54372-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54372-112"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="54372-112"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="54372-p103">Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="54372-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="54372-115">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="54372-115">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="54372-p104">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="54372-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="54372-118">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="54372-118">7/7/2012</span></span></p>
<p><span data-ttu-id="54372-119">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="54372-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="54372-120">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="54372-120">7/3/2012</span></span></p>
<p><span data-ttu-id="54372-121">Le settimane iniziano sempre con il lunedì e terminano con la domenica.</span><span class="sxs-lookup"><span data-stu-id="54372-121">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54372-122"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="54372-122"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="54372-p105">Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="54372-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="54372-125">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="54372-125">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="54372-p106">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="54372-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="54372-128">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="54372-128">7/7/2012</span></span></p>
<p><span data-ttu-id="54372-129">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="54372-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="54372-130">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="54372-130">7/3/2012</span></span></p>
<p><span data-ttu-id="54372-131">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="54372-131">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54372-132"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="54372-132"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="54372-p107">Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool oppure fare clic su <strong>[Tutto]</strong> per visualizzare i dati di tutti i pool. Le voci disponibili in questo elenco a discesa vengono inserite automaticamente in base ai record presenti nel database.</span><span class="sxs-lookup"><span data-stu-id="54372-p107">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="54372-136">Metriche</span><span class="sxs-lookup"><span data-stu-id="54372-136">Metrics</span></span>

<span data-ttu-id="54372-137">Nella tabella seguente sono elencate le informazioni fornite nel sottoreport riepilogativo conferenze.</span><span class="sxs-lookup"><span data-stu-id="54372-137">The following table lists the information provided in the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-metrics"></a><span data-ttu-id="54372-138">Metriche del sottorapporto riepilogativo conferenze</span><span class="sxs-lookup"><span data-stu-id="54372-138">Conference Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54372-139">Name</span><span class="sxs-lookup"><span data-stu-id="54372-139">Name</span></span></th>
<th><span data-ttu-id="54372-140">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="54372-140">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="54372-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="54372-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54372-142"><strong>Totale conferenze</strong></span><span class="sxs-lookup"><span data-stu-id="54372-142"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="54372-143">No</span><span class="sxs-lookup"><span data-stu-id="54372-143">No</span></span></p></td>
<td><p><span data-ttu-id="54372-144">Numero totale di conferenze effettuate.</span><span class="sxs-lookup"><span data-stu-id="54372-144">Total number of conferences held.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54372-145"><strong>Totale sessioni conferenza</strong></span><span class="sxs-lookup"><span data-stu-id="54372-145"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="54372-146">No</span><span class="sxs-lookup"><span data-stu-id="54372-146">No</span></span></p></td>
<td><p><span data-ttu-id="54372-p108">Numero totale di sessioni di conferenza. Una singola conferenza può includere più sessioni, ad esempio una sessione Focus e una sessione MCU.</span><span class="sxs-lookup"><span data-stu-id="54372-p108">Total number of conference sessions. A single conference can have multiple sessions; for example, a conference might include both a Focus session and an MCU session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54372-149"><strong>Frequenza generale errori sessione</strong></span><span class="sxs-lookup"><span data-stu-id="54372-149"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="54372-150">No</span><span class="sxs-lookup"><span data-stu-id="54372-150">No</span></span></p></td>
<td><p><span data-ttu-id="54372-151">Percentuale di tutte le conferenze non riuscite.</span><span class="sxs-lookup"><span data-stu-id="54372-151">Percentage of all conferences that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54372-152"><strong>Sessioni Focus</strong></span><span class="sxs-lookup"><span data-stu-id="54372-152"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="54372-153">No</span><span class="sxs-lookup"><span data-stu-id="54372-153">No</span></span></p></td>
<td><p><span data-ttu-id="54372-154">Numero totale di sessioni Focus.</span><span class="sxs-lookup"><span data-stu-id="54372-154">Total number of Focus sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54372-155"><strong>Frequenza errori Focus</strong></span><span class="sxs-lookup"><span data-stu-id="54372-155"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="54372-156">No</span><span class="sxs-lookup"><span data-stu-id="54372-156">No</span></span></p></td>
<td><p><span data-ttu-id="54372-157">Percentuale di sessioni Focus non riuscite.</span><span class="sxs-lookup"><span data-stu-id="54372-157">Percentage of Focus sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54372-158">Sessioni MCU</span><span class="sxs-lookup"><span data-stu-id="54372-158">MCU sessions</span></span></p></td>
<td><p><span data-ttu-id="54372-159">No</span><span class="sxs-lookup"><span data-stu-id="54372-159">No</span></span></p></td>
<td><p><span data-ttu-id="54372-160">Numero totale di sessioni MCU.</span><span class="sxs-lookup"><span data-stu-id="54372-160">Total number of MCU sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54372-161"><strong>Frequenza errori MCU</strong></span><span class="sxs-lookup"><span data-stu-id="54372-161"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="54372-162">No</span><span class="sxs-lookup"><span data-stu-id="54372-162">No</span></span></p></td>
<td><p><span data-ttu-id="54372-163">Percentuale di sessioni MCU non riuscite.</span><span class="sxs-lookup"><span data-stu-id="54372-163">Percentage of MCU sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54372-164"><strong>Sessioni MCU per modalità</strong></span><span class="sxs-lookup"><span data-stu-id="54372-164"><strong>MCU sessions by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="54372-165">No</span><span class="sxs-lookup"><span data-stu-id="54372-165">No</span></span></p></td>
<td><p><span data-ttu-id="54372-166">Numero totale di sessioni MCU, raggruppate per modalità (ad esempio IM Conferencing).</span><span class="sxs-lookup"><span data-stu-id="54372-166">Total number of MCU sessions, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54372-167"><strong>Frequenza errori per modalità</strong></span><span class="sxs-lookup"><span data-stu-id="54372-167"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="54372-168">No</span><span class="sxs-lookup"><span data-stu-id="54372-168">No</span></span></p></td>
<td><p><span data-ttu-id="54372-169">Percentuale di sessioni MCU non riuscite, raggruppate per modalità (ad esempio IM Conferencing).</span><span class="sxs-lookup"><span data-stu-id="54372-169">Percentage of MCU sessions that failed, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

