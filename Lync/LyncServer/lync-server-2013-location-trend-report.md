---
title: 'Lync Server 2013: Rapporto tendenze percorso'
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
ms.openlocfilehash: ef6c2905bbba3edfcdaba08746a8331b02881320
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="location-trend-report-in-lync-server-2013"></a><span data-ttu-id="b4c9b-102">Rapporto tendenze percorso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4c9b-102">Location Trend Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4c9b-103">_**Ultimo argomento modificato:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="b4c9b-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="b4c9b-104">Il Rapporto tendenze percorso offre informazioni sulle tendenze di qualità delle chiamate per i percorso di rete.</span><span class="sxs-lookup"><span data-stu-id="b4c9b-104">The Location Trend Report provides call quality trend information for network locations.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="b4c9b-105">Filtri</span><span class="sxs-lookup"><span data-stu-id="b4c9b-105">Filters</span></span>

<span data-ttu-id="b4c9b-p101">I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Il Rapporto tendenze percorso, ad esempio, consente di filtrare i dati restituiti in base a fattori come il tipo di accesso (interno o esterno) o il tipo di connessione di rete (cablata o wireless). È inoltre possibile scegliere la modalità di raggruppamento dei dati. In questo caso le chiamate sono raggruppate per ora, giorno o settimana.</span><span class="sxs-lookup"><span data-stu-id="b4c9b-p101">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Location Trend Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, or week.</span></span>

<span data-ttu-id="b4c9b-110">Nella tabella che segue sono elencati i filtri applicabili al Rapporto tendenze percorso.</span><span class="sxs-lookup"><span data-stu-id="b4c9b-110">The following table lists the filters that you can use with the Location Trend Report.</span></span>

### <a name="location-trend-report-filters"></a><span data-ttu-id="b4c9b-111">Filtri del Rapporto tendenze percorso</span><span class="sxs-lookup"><span data-stu-id="b4c9b-111">Location Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b4c9b-112">Name</span><span class="sxs-lookup"><span data-stu-id="b4c9b-112">Name</span></span></th>
<th><span data-ttu-id="b4c9b-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b4c9b-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4c9b-114"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="b4c9b-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="b4c9b-p102">Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="b4c9b-p102">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="b4c9b-117">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="b4c9b-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b4c9b-p103">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="b4c9b-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b4c9b-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b4c9b-120">7/7/2012</span></span></p>
<p><span data-ttu-id="b4c9b-121">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="b4c9b-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b4c9b-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b4c9b-122">7/3/2012</span></span></p>
<p><span data-ttu-id="b4c9b-123">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="b4c9b-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4c9b-124"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="b4c9b-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="b4c9b-p104">Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="b4c9b-p104">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="b4c9b-127">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="b4c9b-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b4c9b-p105">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="b4c9b-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b4c9b-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b4c9b-130">7/7/2012</span></span></p>
<p><span data-ttu-id="b4c9b-131">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="b4c9b-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b4c9b-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b4c9b-132">7/3/2012</span></span></p>
<p><span data-ttu-id="b4c9b-133">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="b4c9b-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4c9b-134"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="b4c9b-134"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="b4c9b-p106">Selezionare uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="b4c9b-p106">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b4c9b-137">Orario (è possibile visualizzare un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="b4c9b-137">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b4c9b-138">Giornaliero (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="b4c9b-138">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b4c9b-139">Settimanale (è possibile visualizzare un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="b4c9b-139">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="b4c9b-p107">Se per le date di inizio e di fine si immette un numero di valori superiore al massimo consentito per l'intervallo selezionato, verrà visualizzato solo il numero massimo di valori (a partire dalla data di inizio). Se ad esempio si seleziona l'intervallo Giornaliero con la data di inizio 01/01/2011 e la data di fine 28/02/2011, verranno visualizzati i dati relativi ai giorni da 01/08/2011 alle 00.00 a 01/09/2011 alle 00.00, ovvero per un totale di 31 giorni.</span><span class="sxs-lookup"><span data-stu-id="b4c9b-p107">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 1/1/2011 and an end date of 2/28/2011, data is displayed for the days 8/1/2011 12:00 AM to 9/1/2011 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4c9b-142"><strong>Tipo di accesso</strong></span><span class="sxs-lookup"><span data-stu-id="b4c9b-142"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="b4c9b-p108">Indica se al momento dell'esecuzione della chiamata il client era connesso alla rete interna o alla rete esterna. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b4c9b-p108">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b4c9b-145">Tutti</span><span class="sxs-lookup"><span data-stu-id="b4c9b-145">[All]</span></span></p></li>
<li><p><span data-ttu-id="b4c9b-146">Interna</span><span class="sxs-lookup"><span data-stu-id="b4c9b-146">Internal</span></span></p></li>
<li><p><span data-ttu-id="b4c9b-147">Esterna</span><span class="sxs-lookup"><span data-stu-id="b4c9b-147">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4c9b-148"><strong>Tipo di rete</strong></span><span class="sxs-lookup"><span data-stu-id="b4c9b-148"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="b4c9b-p109">Indica il tipo di rete alla quale era connesso il client quando è stata effettuata la chiamata. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b4c9b-p109">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b4c9b-151">Tutti</span><span class="sxs-lookup"><span data-stu-id="b4c9b-151">[All]</span></span></p></li>
<li><p><span data-ttu-id="b4c9b-152">Cablata</span><span class="sxs-lookup"><span data-stu-id="b4c9b-152">Wired</span></span></p></li>
<li><p><span data-ttu-id="b4c9b-153">Wireless</span><span class="sxs-lookup"><span data-stu-id="b4c9b-153">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4c9b-154"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="b4c9b-154"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="b4c9b-p110">Indica se un client esterno stava utilizzando una connessione VPN (Virtual Private Network) al momento della chiamata. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b4c9b-p110">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b4c9b-157">Tutti</span><span class="sxs-lookup"><span data-stu-id="b4c9b-157">[All]</span></span></p></li>
<li><p><span data-ttu-id="b4c9b-158">VPN</span><span class="sxs-lookup"><span data-stu-id="b4c9b-158">VPN</span></span></p></li>
<li><p><span data-ttu-id="b4c9b-159">Non VPN</span><span class="sxs-lookup"><span data-stu-id="b4c9b-159">Non-VPN</span></span></p></li>
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

