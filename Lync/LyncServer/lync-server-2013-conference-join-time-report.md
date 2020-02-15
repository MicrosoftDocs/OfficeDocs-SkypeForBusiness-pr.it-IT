---
title: 'Lync Server 2013: rapporto tempo di partecipazione alla conferenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Join Time Report
ms:assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205344(v=OCS.15)
ms:contentKeyID: 48185686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96b1e8af206e6beaec1bf96bc2d91b88f672bd4f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007865"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-join-time-report-in-lync-server-2013"></a><span data-ttu-id="25851-102">Rapporto tempo di partecipazione alla conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25851-102">Conference Join Time Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25851-103">_**Ultimo argomento modificato:** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="25851-103">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="25851-p101">Il rapporto Tempo di partecipazione alla conferenza consente di determinare il tempo richiesto agli utenti per partecipare a una conferenza. Nel rapporto viene visualizzato il tempo medio di partecipazione (in millisecondi) e sono inoltre disponibili informazioni suddivise che indicano il numero di utenti in grado di partecipare a una conferenza in massimo 2 secondi, il numero di utenti che hanno impiegato tra 2 e 5 secondi per partecipare e così via.</span><span class="sxs-lookup"><span data-stu-id="25851-p101">The Conference Join Time Summary enables you to determine how long it takes your users to join a conference. The report shows the average join time (in milliseconds), and also provides a breakdown that lets you know how many users were able to join a conference in 2 seconds or less, how many users required between 2 and 5 seconds to join the conference, and so on.</span></span>

<div>

## <a name="accessing-the-conference-join-time-report"></a><span data-ttu-id="25851-106">Accesso al rapporto Tempo di partecipazione alla conferenza</span><span class="sxs-lookup"><span data-stu-id="25851-106">Accessing the Conference Join Time Report</span></span>

<span data-ttu-id="25851-107">È possibile accedere al rapporto Tempo di partecipazione alla conferenza dalla home page Relazioni monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="25851-107">The Conference Join Time Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="25851-108">Filtri</span><span class="sxs-lookup"><span data-stu-id="25851-108">Filters</span></span>

<span data-ttu-id="25851-p102">I filtri consentono di restituire un set di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Nella tabella riportata di seguito vengono elencati i filtri che è possibile utilizzare con il rapporto Tempo di partecipazione alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="25851-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-filters"></a><span data-ttu-id="25851-111">Filtri del rapporto Tempo di partecipazione alla conferenza</span><span class="sxs-lookup"><span data-stu-id="25851-111">Conference Join Time Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25851-112">Nome</span><span class="sxs-lookup"><span data-stu-id="25851-112">Name</span></span></th>
<th><span data-ttu-id="25851-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25851-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25851-114"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="25851-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="25851-p103">Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="25851-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="25851-117">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="25851-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="25851-p104">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="25851-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="25851-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="25851-120">7/7/2012</span></span></p>
<p><span data-ttu-id="25851-121">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="25851-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="25851-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="25851-122">7/3/2012</span></span></p>
<p><span data-ttu-id="25851-123">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="25851-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25851-124"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="25851-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="25851-p105">Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="25851-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="25851-127">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="25851-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="25851-p106">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="25851-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="25851-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="25851-130">7/7/2012</span></span></p>
<p><span data-ttu-id="25851-131">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="25851-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="25851-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="25851-132">7/3/2012</span></span></p>
<p><span data-ttu-id="25851-133">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="25851-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25851-134"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="25851-134"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="25851-p107">Selezionare uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="25851-p107">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="25851-137">Orario (è possibile visualizzare un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="25851-137">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="25851-138">Giornaliero (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="25851-138">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="25851-139">Settimanale (è possibile visualizzare un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="25851-139">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="25851-140">Mensile (è possibile visualizzare un massimo di 12 mesi)</span><span class="sxs-lookup"><span data-stu-id="25851-140">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="25851-p108">Se le date di inizio e fine superano il numero massimo di valori consentiti per l'intervallo specificato, verrà visualizzato solo il numero massimo di valori a partire dalla data di inizio. Se ad esempio si seleziona l'intervallo giornaliero con data di inizio 07/07/2012 e data di fine 28/02/2012, verranno visualizzati i dati per i giorni da 07/08/2012 ore 00.00 a 07/09/2012 ore 00:00 (per un totale di 31 giorni).</span><span class="sxs-lookup"><span data-stu-id="25851-p108">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25851-143"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="25851-143"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="25851-p109">Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool oppure fare clic su <strong>[Tutto]</strong> per visualizzare i dati di tutti i pool. Le voci disponibili in questo elenco a discesa vengono inserite automaticamente in base ai record presenti nel database.</span><span class="sxs-lookup"><span data-stu-id="25851-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25851-147"><strong>Sessioni conferenza</strong></span><span class="sxs-lookup"><span data-stu-id="25851-147"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="25851-p110">Tipo di sessione. I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="25851-p110">Type of session. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="25851-150">Tutti</span><span class="sxs-lookup"><span data-stu-id="25851-150">[All]</span></span></p></li>
<li><p><span data-ttu-id="25851-151">Sessioni di messa a fuoco (lo stato attivo è il criterio centrale e il responsabile dello stato per le riunioni online e coordina tutti gli aspetti di una conferenza</span><span class="sxs-lookup"><span data-stu-id="25851-151">Focus sessions (the Focus is the central policy and state manager for online meetings and coordinates all aspects of A conference</span></span></p></li>
<li><p><span data-ttu-id="25851-152">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="25851-152">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="25851-153">Conferenze audio/video</span><span class="sxs-lookup"><span data-stu-id="25851-153">A/V conferencing</span></span></p></li>
</ul>
<p><span data-ttu-id="25851-p111">Se si seleziona [Tutto], nella parte superiore del rapporto verrà visualizzato il tempo totale di partecipazione alla conferenza. Si noti che questi totali sono riferiti solo alle conferenze pianificate tramite Microsoft Exchange o Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="25851-p111">If you select [All], the total conference join time will be displayed at the top of the report. Note that these totals are only for conferences which were scheduled by using Microsoft Exchange or Microsoft Outlook.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="25851-156">Metriche</span><span class="sxs-lookup"><span data-stu-id="25851-156">Metrics</span></span>

<span data-ttu-id="25851-157">La tabella seguente elenca le informazioni disponibili nel rapporto Tempo di partecipazione alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="25851-157">The following table lists the information provided in the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-metrics"></a><span data-ttu-id="25851-158">Metriche del rapporto Tempo di partecipazione alla conferenza</span><span class="sxs-lookup"><span data-stu-id="25851-158">Conference Join Time Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25851-159">Nome</span><span class="sxs-lookup"><span data-stu-id="25851-159">Name</span></span></th>
<th><span data-ttu-id="25851-160">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="25851-160">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="25851-161">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25851-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25851-162"><strong>Data</strong></span><span class="sxs-lookup"><span data-stu-id="25851-162"><strong>Date</strong></span></span></p>
<p><span data-ttu-id="25851-163">Il titolo effettivo di questa metrica varia in base all'intervallo selezionato.</span><span class="sxs-lookup"><span data-stu-id="25851-163">The actual title for this metric will vary depending on the Interval that was selected.</span></span></p></td>
<td><p><span data-ttu-id="25851-164">No</span><span class="sxs-lookup"><span data-stu-id="25851-164">No</span></span></p></td>
<td><p><span data-ttu-id="25851-165">Data e ora in cui ha avuto luogo la conferenza.</span><span class="sxs-lookup"><span data-stu-id="25851-165">Date and time that the conference took place.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25851-166"><strong>Totale sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="25851-166"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="25851-167">No</span><span class="sxs-lookup"><span data-stu-id="25851-167">No</span></span></p></td>
<td><p><span data-ttu-id="25851-168">Numero totale di sessioni, comprendente le sessioni con esito positivo, le sessioni con esito negativo (per errori sia previsti che imprevisti) e le sessioni senza categoria.</span><span class="sxs-lookup"><span data-stu-id="25851-168">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25851-169"><strong>Media (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="25851-169"><strong>Average (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="25851-170">No</span><span class="sxs-lookup"><span data-stu-id="25851-170">No</span></span></p></td>
<td><p><span data-ttu-id="25851-171">Quantità media di tempo (in millisecondi) impiegato dai partecipanti per partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="25851-171">Average amount of time (in milliseconds) that it took participants to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25851-172"><strong>Sessioni &lt; 2 secondi, volume</strong></span><span class="sxs-lookup"><span data-stu-id="25851-172"><strong>Sessions &lt; 2 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="25851-173">No</span><span class="sxs-lookup"><span data-stu-id="25851-173">No</span></span></p></td>
<td><p><span data-ttu-id="25851-174">Numero di partecipanti che sono riusciti a partecipare alla conferenza in meno di 2 secondi.</span><span class="sxs-lookup"><span data-stu-id="25851-174">Number of participants who were able to join the conference in less than 2 seconds.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25851-175"><strong>Sessioni &lt; 2 secondi, percentuale</strong></span><span class="sxs-lookup"><span data-stu-id="25851-175"><strong>Sessions &lt; 2 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="25851-176">No</span><span class="sxs-lookup"><span data-stu-id="25851-176">No</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25851-177"><strong>Sessioni 2-5 secondi, Volume</strong></span><span class="sxs-lookup"><span data-stu-id="25851-177"><strong>Sessions 2-5 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="25851-178">No</span><span class="sxs-lookup"><span data-stu-id="25851-178">No</span></span></p></td>
<td><p><span data-ttu-id="25851-179">Numero di partecipanti che hanno impiegato da 2 a 5 secondi per partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="25851-179">Number of participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25851-180"><strong>Sessioni 2-5 secondi, Percentuale</strong></span><span class="sxs-lookup"><span data-stu-id="25851-180"><strong>Sessions 2-5 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="25851-181">No</span><span class="sxs-lookup"><span data-stu-id="25851-181">No</span></span></p></td>
<td><p><span data-ttu-id="25851-182">Percentuale del numero totale di partecipanti che hanno impiegato da 2 a 5 secondi per partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="25851-182">Percentage of the total call participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25851-183"><strong>Sessioni 5-10 secondi, Volume</strong></span><span class="sxs-lookup"><span data-stu-id="25851-183"><strong>Sessions 5-10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="25851-184">No</span><span class="sxs-lookup"><span data-stu-id="25851-184">No</span></span></p></td>
<td><p><span data-ttu-id="25851-185">Numero di partecipanti che hanno impiegato da 5 a 10 secondi per partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="25851-185">Number of participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25851-186"><strong>Sessioni 5-10 secondi, Percentuale</strong></span><span class="sxs-lookup"><span data-stu-id="25851-186"><strong>Sessions 5-10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="25851-187">No</span><span class="sxs-lookup"><span data-stu-id="25851-187">No</span></span></p></td>
<td><p><span data-ttu-id="25851-188">Percentuale del numero totale di partecipanti che hanno impiegato da 5 a 10 secondi per partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="25851-188">Percentage of the total call participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25851-189"><strong>Sessioni &gt; 10 secondi, volume</strong></span><span class="sxs-lookup"><span data-stu-id="25851-189"><strong>Sessions &gt; 10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="25851-190">No</span><span class="sxs-lookup"><span data-stu-id="25851-190">No</span></span></p></td>
<td><p><span data-ttu-id="25851-191">Numero di partecipanti che hanno impiegato più di 10 secondi per partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="25851-191">Number of participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25851-192"><strong>Sessioni &gt; 10 secondi, percentuale</strong></span><span class="sxs-lookup"><span data-stu-id="25851-192"><strong>Sessions &gt; 10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="25851-193">No</span><span class="sxs-lookup"><span data-stu-id="25851-193">No</span></span></p></td>
<td><p><span data-ttu-id="25851-194">Percentuale del numero totale di partecipanti che hanno impiegato più di 10 secondi per partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="25851-194">Percentage of the total call participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

