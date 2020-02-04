---
title: 'Lync Server 2013: report tendenze posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Trend Report
ms:assetid: 61e2db3c-9f10-4411-8e7e-c6950faf8533
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204941(v=OCS.15)
ms:contentKeyID: 48184280
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26f825a33eeb90817685c1694a5c6579110ffcd6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-trend-report-in-lync-server-2013"></a><span data-ttu-id="01171-102">Report tendenze posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01171-102">Location Trend Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01171-103">_**Argomento Ultima modifica:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="01171-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="01171-104">Il report tendenze posizione offre informazioni sulle tendenze della qualità delle chiamate per i percorsi di rete.</span><span class="sxs-lookup"><span data-stu-id="01171-104">The Location Trend Report provides call quality trend information for network locations.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="01171-105">Filtri</span><span class="sxs-lookup"><span data-stu-id="01171-105">Filters</span></span>

<span data-ttu-id="01171-106">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="01171-106">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="01171-107">Ad esempio, il rapporto di tendenza della posizione consente di filtrare i dati restituiti in base a elementi come il tipo di accesso, ovvero l'accesso tramite intervallo o l'accesso esterno, o la connessione di rete cablata/wireless.</span><span class="sxs-lookup"><span data-stu-id="01171-107">For example, the Location Trend Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection.</span></span> <span data-ttu-id="01171-108">È anche possibile scegliere la modalità di raggruppamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="01171-108">You can also choose how data should be grouped.</span></span> <span data-ttu-id="01171-109">In questo caso, le chiamate vengono raggruppate per ora, giorno o settimana.</span><span class="sxs-lookup"><span data-stu-id="01171-109">In this case, calls are grouped by hour, day, or week.</span></span>

<span data-ttu-id="01171-110">Nella tabella seguente sono elencati i filtri che è possibile usare con il report tendenze posizione.</span><span class="sxs-lookup"><span data-stu-id="01171-110">The following table lists the filters that you can use with the Location Trend Report.</span></span>

### <a name="location-trend-report-filters"></a><span data-ttu-id="01171-111">Filtri per i report sulle tendenze di posizione</span><span class="sxs-lookup"><span data-stu-id="01171-111">Location Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01171-112">Nome</span><span class="sxs-lookup"><span data-stu-id="01171-112">Name</span></span></th>
<th><span data-ttu-id="01171-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01171-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01171-114"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="01171-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="01171-115">Data/ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="01171-115">Start date/time for the time range.</span></span> <span data-ttu-id="01171-116">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="01171-116">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="01171-117">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="01171-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="01171-118">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="01171-118">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="01171-119">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="01171-119">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="01171-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="01171-120">7/7/2012</span></span></p>
<p><span data-ttu-id="01171-121">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="01171-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="01171-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="01171-122">7/3/2012</span></span></p>
<p><span data-ttu-id="01171-123">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="01171-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01171-124"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="01171-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="01171-125">Data/ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="01171-125">End date/time for the time range.</span></span> <span data-ttu-id="01171-126">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="01171-126">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="01171-127">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="01171-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="01171-128">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="01171-128">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="01171-129">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="01171-129">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="01171-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="01171-130">7/7/2012</span></span></p>
<p><span data-ttu-id="01171-131">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="01171-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="01171-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="01171-132">7/3/2012</span></span></p>
<p><span data-ttu-id="01171-133">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="01171-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01171-134"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="01171-134"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="01171-135">Intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="01171-135">Time interval.</span></span> <span data-ttu-id="01171-136">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="01171-136">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="01171-137">Ogni ora (può essere visualizzato un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="01171-137">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="01171-138">Giornaliera (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="01171-138">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="01171-139">Settimanale (può essere visualizzato un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="01171-139">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="01171-140">Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, viene visualizzato solo il numero massimo di valori (a partire dalla data di inizio).</span><span class="sxs-lookup"><span data-stu-id="01171-140">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="01171-141">Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 1/1/2011 e una data di fine 2/28/2011, i dati verranno visualizzati per i giorni 8/1/2011 12:00 da AM a 9/1/2011 12:00 AM, ovvero un totale di 31 giorni di dati.</span><span class="sxs-lookup"><span data-stu-id="01171-141">For example, if you select the Daily interval with a start date of 1/1/2011 and an end date of 2/28/2011, data is displayed for the days 8/1/2011 12:00 AM to 9/1/2011 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01171-142"><strong>Tipo di accesso</strong></span><span class="sxs-lookup"><span data-stu-id="01171-142"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="01171-143">Indica se il client ha effettuato l'accesso alla rete interna o alla rete esterna quando è stata inserita la chiamata.</span><span class="sxs-lookup"><span data-stu-id="01171-143">Indicates whether the client was logged on to the internal network or the external network when the call was placed.</span></span> <span data-ttu-id="01171-144">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="01171-144">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="01171-145">Tutti</span><span class="sxs-lookup"><span data-stu-id="01171-145">[All]</span></span></p></li>
<li><p><span data-ttu-id="01171-146">Interno</span><span class="sxs-lookup"><span data-stu-id="01171-146">Internal</span></span></p></li>
<li><p><span data-ttu-id="01171-147">Esterno</span><span class="sxs-lookup"><span data-stu-id="01171-147">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01171-148"><strong>Tipo di rete</strong></span><span class="sxs-lookup"><span data-stu-id="01171-148"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="01171-149">Indica il tipo di rete a cui il client è connesso quando è stata inserita la chiamata.</span><span class="sxs-lookup"><span data-stu-id="01171-149">Indicates the type of network the client was connected to when the call was placed.</span></span> <span data-ttu-id="01171-150">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="01171-150">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="01171-151">Tutti</span><span class="sxs-lookup"><span data-stu-id="01171-151">[All]</span></span></p></li>
<li><p><span data-ttu-id="01171-152">Cablata</span><span class="sxs-lookup"><span data-stu-id="01171-152">Wired</span></span></p></li>
<li><p><span data-ttu-id="01171-153">Wireless</span><span class="sxs-lookup"><span data-stu-id="01171-153">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01171-154"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="01171-154"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="01171-155">Indica se un client esterno usa una connessione VPN (Virtual Private Network) quando la chiamata è stata inserita.</span><span class="sxs-lookup"><span data-stu-id="01171-155">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed.</span></span> <span data-ttu-id="01171-156">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="01171-156">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="01171-157">Tutti</span><span class="sxs-lookup"><span data-stu-id="01171-157">[All]</span></span></p></li>
<li><p><span data-ttu-id="01171-158">VPN</span><span class="sxs-lookup"><span data-stu-id="01171-158">VPN</span></span></p></li>
<li><p><span data-ttu-id="01171-159">Non VPN</span><span class="sxs-lookup"><span data-stu-id="01171-159">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

