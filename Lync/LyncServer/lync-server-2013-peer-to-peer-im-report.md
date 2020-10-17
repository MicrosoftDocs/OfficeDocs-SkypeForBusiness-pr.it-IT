---
title: 'Lync Server 2013: rapporto di messaggistica istantanea peer-to-peer'
description: 'Lync Server 2013: rapporto di messaggistica istantanea peer-to-peer.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer IM Report
ms:assetid: 19ec0145-2398-437b-8989-f780c179b798
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558620(v=OCS.15)
ms:contentKeyID: 48183533
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eac6291d0f099af8269ed15f7dc8c654ac944ed0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557292"
---
# <a name="peer-to-peer-im-report-in-lync-server-2013"></a><span data-ttu-id="8e21e-103">Rapporto di messaggistica istantanea peer-to-peer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e21e-103">Peer-to-Peer IM Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e21e-104">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8e21e-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8e21e-p101">Nel rapporto di messaggistica istantanea peer-to-peer vengono fornite informazioni sulla tendenza delle sessioni di messaggistica istantanea suddivise per pool e per tipo di autenticazione. Il rapporto può inoltre indicare il numero totale di sessioni organizzate oppure segnalare il numero complessivo di messaggi istantanei inviati nel periodo specificato (ad esempio, Giorno o Ora).</span><span class="sxs-lookup"><span data-stu-id="8e21e-p101">The Peer-to-Peer IM Report provides trend information about peer-to-peer instant messaging (IM) sessions, broken down by pool and by authentication type. The report can show either the total number of sessions held during the specified time period (for example, day-by-day or hour-by-hour), or it can show the total number of instant messages sent during that time period.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-im-report"></a><span data-ttu-id="8e21e-107">Accesso al rapporto di messaggistica istantanea peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="8e21e-107">Accessing the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="8e21e-108">È possibile accedere al rapporto di messaggistica istantanea peer-to-peer solo aprendo il [rapporto riepilogativo attività peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) e quindi facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="8e21e-108">You can access the Peer-to-Peer IM Report only by opening the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) and then clicking either of the following metrics:</span></span>

  - <span data-ttu-id="8e21e-109">Totale sessioni di messaggistica istantanea peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="8e21e-109">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="8e21e-110">Totale messaggi istantanei peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="8e21e-110">Total peer-to-peer IM messages</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a><span data-ttu-id="8e21e-111">Utilizzo ottimale del rapporto di messaggistica istantanea peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="8e21e-111">Making the Best Use of the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="8e21e-p102">Nel rapporto di messaggistica istantanea peer-to-peer vengono mostrati, per impostazione predefinita, il numero di messaggi per ora (o giorno, a seconda dell'impostazione configurata). Tuttavia, è anche possibile scegliere di visualizzare il giorno in base alle sessioni per ora. In tal caso, fare clic su **Nascondi/mostra parametri** nell'angolo superiore destro della finestra relativa ai rapporti e quindi fare clic su **Numero di sessioni** nell'elenco **Rapporto di**.</span><span class="sxs-lookup"><span data-stu-id="8e21e-p102">By default, the Peer-to-Peer IM Report shows you the message count per-hour (or day, depending on your settings). However, you can also choose to view the day by sessions per hour. To do that, click **Hide/Show Parameters** in the upper-right corner of the Reports window, and then click **Session Count** from the **Report by** list.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="8e21e-115">Filtri</span><span class="sxs-lookup"><span data-stu-id="8e21e-115">Filters</span></span>

<span data-ttu-id="8e21e-p103">I filtri consentono di ottenere un set di dati più mirato o di visualizzare i dati restituiti in diversi modi. Nella tabella seguente sono riportati i filtri utilizzabili con il rapporto di messaggistica istantanea peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="8e21e-p103">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Peer-to-Peer IM Report.</span></span>

### <a name="peer-to-peer-im-report-filters"></a><span data-ttu-id="8e21e-118">Filtri per il rapporto di messaggistica istantanea peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="8e21e-118">Peer-to-Peer IM Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e21e-119">Nome</span><span class="sxs-lookup"><span data-stu-id="8e21e-119">Name</span></span></th>
<th><span data-ttu-id="8e21e-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8e21e-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e21e-121"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="8e21e-121"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="8e21e-p104">Data e ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, inserire sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="8e21e-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="8e21e-124">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="8e21e-124">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8e21e-p105">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="8e21e-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8e21e-127">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8e21e-127">7/7/2012</span></span></p>
<p><span data-ttu-id="8e21e-128">Per visualizzare i dati in base alla settimana o al mese, immettere una data che rientri nella settimana o nel mese desiderato (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="8e21e-128">To view by week or by month, enter a date that falls anywhere within the week or month (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8e21e-129">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8e21e-129">7/3/2012</span></span></p>
<p><span data-ttu-id="8e21e-130">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="8e21e-130">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e21e-131"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="8e21e-131"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="8e21e-p106">Data e ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, inserire sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="8e21e-p106">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="8e21e-134">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="8e21e-134">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8e21e-p107">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="8e21e-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8e21e-137">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8e21e-137">7/7/2012</span></span></p>
<p><span data-ttu-id="8e21e-138">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="8e21e-138">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8e21e-139">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8e21e-139">7/3/2012</span></span></p>
<p><span data-ttu-id="8e21e-140">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="8e21e-140">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e21e-141"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="8e21e-141"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="8e21e-p108">Selezionare uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="8e21e-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="8e21e-144">Orario (è possibile visualizzare un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="8e21e-144">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="8e21e-145">Giornaliero (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="8e21e-145">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="8e21e-146">Settimanale (è possibile visualizzare un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="8e21e-146">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="8e21e-147">Mensile (possono essere visualizzati al massimo 12 mesi)</span><span class="sxs-lookup"><span data-stu-id="8e21e-147">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="8e21e-p109">Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, verrà visualizzato solo il numero massimo di valori, a partire dalla data di inizio. Se ad esempio si seleziona l'intervallo Giornaliero con 07/07/2012 come data di inizio e 28/02/2012 come data di fine, verranno visualizzati i dati dalla mezzanotte del 7 agosto 2012 alla mezzanotte del 7 settembre 2012, ovvero i dati per un totale di 31 giorni.</span><span class="sxs-lookup"><span data-stu-id="8e21e-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval then only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e21e-150"><strong>Rapporto di</strong></span><span class="sxs-lookup"><span data-stu-id="8e21e-150"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="8e21e-p110">Indica i valori da utilizzare nel rapporto. Selezionare una delle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8e21e-p110">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="8e21e-153">Numero di sessioni</span><span class="sxs-lookup"><span data-stu-id="8e21e-153">Session count</span></span></p></li>
<li><p><span data-ttu-id="8e21e-154">Numero messaggi</span><span class="sxs-lookup"><span data-stu-id="8e21e-154">Message count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="8e21e-155">Metrica delle sessioni di messaggistica istantanea peer-to-peer in base al pool</span><span class="sxs-lookup"><span data-stu-id="8e21e-155">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<span data-ttu-id="8e21e-156">Nella tabella seguente vengono riportate le informazioni fornite nel rapporto di messaggistica istantanea peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="8e21e-156">The following table lists the information provided in the Peer-to-Peer IM Report.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="8e21e-157">Metrica del rapporto di messaggistica istantanea peer-to-peer in base al pool</span><span class="sxs-lookup"><span data-stu-id="8e21e-157">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e21e-158">Nome</span><span class="sxs-lookup"><span data-stu-id="8e21e-158">Name</span></span></th>
<th><span data-ttu-id="8e21e-159">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="8e21e-159">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8e21e-160">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8e21e-160">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e21e-161"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="8e21e-161"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="8e21e-162">No</span><span class="sxs-lookup"><span data-stu-id="8e21e-162">No</span></span></p></td>
<td><p><span data-ttu-id="8e21e-163">Nome del pool di registrazione o del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="8e21e-163">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e21e-164"><strong>Data/ora</strong></span><span class="sxs-lookup"><span data-stu-id="8e21e-164"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="8e21e-165">No</span><span class="sxs-lookup"><span data-stu-id="8e21e-165">No</span></span></p></td>
<td><p><span data-ttu-id="8e21e-166">Data e ora in cui hanno avuto luogo le sessioni.</span><span class="sxs-lookup"><span data-stu-id="8e21e-166">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e21e-167"><strong>Totale</strong></span><span class="sxs-lookup"><span data-stu-id="8e21e-167"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="8e21e-168">No</span><span class="sxs-lookup"><span data-stu-id="8e21e-168">No</span></span></p></td>
<td><p><span data-ttu-id="8e21e-169">Numero totale di sessioni o di messaggi.</span><span class="sxs-lookup"><span data-stu-id="8e21e-169">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="8e21e-170">Metrica delle sessioni di messaggistica istantanea peer-to-peer in base al tipo di autenticazione</span><span class="sxs-lookup"><span data-stu-id="8e21e-170">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<span data-ttu-id="8e21e-171">Nella tabella seguente vengono riportate le informazioni fornite nel rapporto di messaggistica istantanea peer-to-peer per ogni tipo di autenticazione utilizzato dai partecipanti a una sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="8e21e-171">The following table lists the information provided in the Peer-to-Peer IM Report for each type of authentication used by the participants in a peer-to-peer session.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="8e21e-172">Metrica delle sessioni di messaggistica istantanea peer-to-peer in base al tipo di autenticazione</span><span class="sxs-lookup"><span data-stu-id="8e21e-172">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e21e-173">Nome</span><span class="sxs-lookup"><span data-stu-id="8e21e-173">Name</span></span></th>
<th><span data-ttu-id="8e21e-174">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="8e21e-174">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8e21e-175">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8e21e-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e21e-176"><strong>Tipo di autenticazione</strong></span><span class="sxs-lookup"><span data-stu-id="8e21e-176"><strong>Authentication type</strong></span></span></p></td>
<td><p><span data-ttu-id="8e21e-177">No</span><span class="sxs-lookup"><span data-stu-id="8e21e-177">No</span></span></p></td>
<td><p><span data-ttu-id="8e21e-p111">Tipo di autenticazione utilizzato dai partecipanti alla sessione. I valori validi in genere sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="8e21e-p111">Type of authentication used by the session participants. Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="8e21e-180">Enterprise</span><span class="sxs-lookup"><span data-stu-id="8e21e-180">Enterprise</span></span></p></li>
<li><p><span data-ttu-id="8e21e-181">Federati</span><span class="sxs-lookup"><span data-stu-id="8e21e-181">Federated</span></span></p></li>
<li><p><span data-ttu-id="8e21e-182">PIC</span><span class="sxs-lookup"><span data-stu-id="8e21e-182">PIC</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e21e-183"><strong>Data/ora</strong></span><span class="sxs-lookup"><span data-stu-id="8e21e-183"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="8e21e-184">No</span><span class="sxs-lookup"><span data-stu-id="8e21e-184">No</span></span></p></td>
<td><p><span data-ttu-id="8e21e-185">Data e ora in cui hanno avuto luogo le sessioni.</span><span class="sxs-lookup"><span data-stu-id="8e21e-185">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e21e-186"><strong>Totale</strong></span><span class="sxs-lookup"><span data-stu-id="8e21e-186"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="8e21e-187">No</span><span class="sxs-lookup"><span data-stu-id="8e21e-187">No</span></span></p></td>
<td><p><span data-ttu-id="8e21e-188">Numero totale di sessioni o di messaggi.</span><span class="sxs-lookup"><span data-stu-id="8e21e-188">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

