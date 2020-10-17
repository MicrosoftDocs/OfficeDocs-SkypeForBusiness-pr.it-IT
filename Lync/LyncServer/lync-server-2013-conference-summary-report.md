---
title: 'Lync Server 2013: rapporto riepilogativo conferenze'
description: 'Lync Server 2013: rapporto riepilogativo conferenze.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Report
ms:assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558656(v=OCS.15)
ms:contentKeyID: 48184299
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d9c0b8ad7280d2c7336282c14f46e6b5d6a1aec
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550712"
---
# <a name="conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="52de8-103">Report riepilogativo conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52de8-103">Conference Summary Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52de8-104">_**Ultimo argomento modificato:** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="52de8-104">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="52de8-105">Il Rapporto riepilogativo conferenze offre una visuale generale delle sessioni di conferenza online.</span><span class="sxs-lookup"><span data-stu-id="52de8-105">The Conference Summary Report provides an overall view of your online conferencing sessions.</span></span> <span data-ttu-id="52de8-106">Una conferenza in genere coinvolge più di 2 utenti e richiede l'utilizzo di Microsoft Lync Server 2013 Servizi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="52de8-106">A conference typically involves more than 2 users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="52de8-107">Una sessione peer-to-peer, invece, coinvolge in genere solo 2 utenti e non richiede l'utilizzo dei servizi di conferenza di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="52de8-107">By comparison, a peer-to-peer session typically involves just 2 users and does not require the use of Lync Server's conferencing services.</span></span> <span data-ttu-id="52de8-108">Le attività peer-to-peer sono segnalate nel [rapporto riepilogativo attività peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md).</span><span class="sxs-lookup"><span data-stu-id="52de8-108">Peer-to-peer activities are reported on the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md).</span></span>

<span data-ttu-id="52de8-109">Il rapporto riepilogativo conferenze non solo indica quante conferenze sono state tenute durante un determinato periodo di tempo (ogni ora, giornaliero, settimanale, mensile) ma indica anche il numero totale di persone che hanno partecipato a tali conferenze e il numero totale di organizzatori di conferenze univoci.</span><span class="sxs-lookup"><span data-stu-id="52de8-109">The Conference Summary Report not only tells you how many conferences were held during a given time period (hourly, daily, weekly, monthly) but also tells you the total number of people who took part in those conferences, and the total number of unique conference organizers.</span></span>

<span data-ttu-id="52de8-p102">Con organizzatore "univoco” si intende qualsiasi utente che pianifica almeno una conferenza. Se Luisa Cazzaniga pianifica una conferenza, ad esempio, sarà conteggiata come organizzatore univoco. Se Davide Garghentini pianifica 148 conferenze, anche lui sarà conteggiato come singolo organizzatore univoco. La tabella seguente, ad esempio, indica 8 conferenze pianificate ma solo tre organizzatori univoci, ovvero Davide Garghentini, Luisa Cazzaniga e Luca Argentiero.</span><span class="sxs-lookup"><span data-stu-id="52de8-p102">A "unique” organizer is anyone who schedules at least one conference. For example, if Pilar Ackerman schedules one conference she counts as one unique organizer. If Ken Myer schedules 148 conferences he, too counts as one unique organizer. For example, the table below shows 8 conferences scheduled, but just three unique organizers (Ken Myer, Pilar Ackerman, and David Ahs).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52de8-114">Organizzatore conferenza</span><span class="sxs-lookup"><span data-stu-id="52de8-114">Conference Organizer</span></span></th>
<th><span data-ttu-id="52de8-115">Data conferenza</span><span class="sxs-lookup"><span data-stu-id="52de8-115">Conference Date</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52de8-116">Davide Garghentini</span><span class="sxs-lookup"><span data-stu-id="52de8-116">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="52de8-117">07/07/2012 10.00</span><span class="sxs-lookup"><span data-stu-id="52de8-117">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52de8-118">Luca Argentiero</span><span class="sxs-lookup"><span data-stu-id="52de8-118">David Ahs</span></span></p></td>
<td><p><span data-ttu-id="52de8-119">07/07/2012 10.00</span><span class="sxs-lookup"><span data-stu-id="52de8-119">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52de8-120">Davide Garghentini</span><span class="sxs-lookup"><span data-stu-id="52de8-120">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="52de8-121">07/07/2012 11.00</span><span class="sxs-lookup"><span data-stu-id="52de8-121">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52de8-122">Daniela Cazzaniga</span><span class="sxs-lookup"><span data-stu-id="52de8-122">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="52de8-123">07/07/2012 11.00</span><span class="sxs-lookup"><span data-stu-id="52de8-123">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52de8-124">Davide Garghentini</span><span class="sxs-lookup"><span data-stu-id="52de8-124">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="52de8-125">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="52de8-125">7/7/2012 1:00 PM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52de8-126">Daniela Cazzaniga</span><span class="sxs-lookup"><span data-stu-id="52de8-126">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="52de8-127">07/07/2012 14.00</span><span class="sxs-lookup"><span data-stu-id="52de8-127">7/7/2012 2:00 PM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52de8-128">Davide Garghentini</span><span class="sxs-lookup"><span data-stu-id="52de8-128">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="52de8-129">02/07/2012 10.00</span><span class="sxs-lookup"><span data-stu-id="52de8-129">7/2/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52de8-130">Daniela Cazzaniga</span><span class="sxs-lookup"><span data-stu-id="52de8-130">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="52de8-131">02/07/2012 10.00</span><span class="sxs-lookup"><span data-stu-id="52de8-131">7/2/2012 10:00 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="52de8-132">Il Rapporto riepilogativo conferenze indica inoltre il numero di conferenze con audio e video.</span><span class="sxs-lookup"><span data-stu-id="52de8-132">The Conference Summary Report also indicates how many conferences included audio and/or video.</span></span>

<div>

## <a name="accessing-the-conference-summary-report"></a><span data-ttu-id="52de8-133">Accesso al rapporto riepilogativo conferenze</span><span class="sxs-lookup"><span data-stu-id="52de8-133">Accessing the Conference Summary Report</span></span>

<span data-ttu-id="52de8-p103">È possibile accedere al rapporto riepilogativo conferenze dalla home page Relazioni monitoraggio. È possibile eseguire il drill-down al Rapporto attività conferenza facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="52de8-p103">The Conference Summary Report is accessed from the Monitoring Reports home page. You can drill down to the Conference Activity report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="52de8-136">Totale conferenze</span><span class="sxs-lookup"><span data-stu-id="52de8-136">Total conferences</span></span>

  - <span data-ttu-id="52de8-137">Totale partecipanti</span><span class="sxs-lookup"><span data-stu-id="52de8-137">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-summary-report"></a><span data-ttu-id="52de8-138">Utilizzo ottimale del rapporto riepilogativo conferenze</span><span class="sxs-lookup"><span data-stu-id="52de8-138">Making the Best Use of the Conference Summary Report</span></span>

<span data-ttu-id="52de8-p104">I valori totali per la maggior parte delle metriche utilizzate nel Rapporto riepilogativo conferenze sono disponibili nella parte inferiore del rapporto. Scorrere verso il basso per visualizzare valori come il numero totale di conferenze tenutesi durante il periodo di tempo specificato e il numero totale di persone che hanno partecipato a tali conferenze. Una metrica per la quale non è disponibile il totale nella parte inferiore del rapporto è Totale organizzatori conferenza univoci. Uno dei motivi è questo: si supponga di voler esaminare i dati mensili. Nel giorno 1 sono stati rilevati 34 organizzatori di conferenza univoci, nel giorno 2 gli organizzatori univoci sono 27. Ciò non significa tuttavia che per i due giorni il totale degli organizzatori univoci sia 61. Tutte le 27 persone che hanno organizzato conferenze nel giorno 2 potrebbero essere infatti incluse nei 34 organizzatori univoci del giorno 1. In questo semplice rapporto, ad esempio, notare che Davide Garghentini e Daniela Cazzaniga hanno pianificato conferenze sia in data 07/07/2012 che in data 02/07/2012:</span><span class="sxs-lookup"><span data-stu-id="52de8-p104">Total values for most of the metrics used on the Conference Summary Report can be found at the bottom of the report; scroll down to see values such as the total number of conferences held during the specified time period, and the total number of people who participated in those conferences. One metric that is not totaled at the bottom of the report is Total unique conference organizers. Why not? Here’s one reason. Suppose you are looking at a month's worth of data. On day 1 you had 34 unique conference organizers; on day 2 you had 27 unique conference organizers. Does that mean you had 61 unique conference organizers for those two days? Not necessarily. After all, all 27 people who organized conferences on day 2 might be among the 34 people who organized conferences on day 1. For example, in this simple report, note that Ken Myer and Pilar Ackerman scheduled conferences both on 7/7/2012 and on 7/2/2012:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52de8-149">Organizzatore conferenza</span><span class="sxs-lookup"><span data-stu-id="52de8-149">Conference Organizer</span></span></th>
<th><span data-ttu-id="52de8-150">Data conferenza</span><span class="sxs-lookup"><span data-stu-id="52de8-150">Conference Date</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52de8-151">Davide Garghentini</span><span class="sxs-lookup"><span data-stu-id="52de8-151">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="52de8-152">07/07/2012 10.00</span><span class="sxs-lookup"><span data-stu-id="52de8-152">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52de8-153">Luca Argentiero</span><span class="sxs-lookup"><span data-stu-id="52de8-153">David Ahs</span></span></p></td>
<td><p><span data-ttu-id="52de8-154">07/07/2012 10.00</span><span class="sxs-lookup"><span data-stu-id="52de8-154">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52de8-155">Davide Garghentini</span><span class="sxs-lookup"><span data-stu-id="52de8-155">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="52de8-156">07/07/2012 11.00</span><span class="sxs-lookup"><span data-stu-id="52de8-156">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52de8-157">Daniela Cazzaniga</span><span class="sxs-lookup"><span data-stu-id="52de8-157">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="52de8-158">07/07/2012 11.00</span><span class="sxs-lookup"><span data-stu-id="52de8-158">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52de8-159">Davide Garghentini</span><span class="sxs-lookup"><span data-stu-id="52de8-159">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="52de8-160">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="52de8-160">7/7/2012 1:00 PM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52de8-161">Daniela Cazzaniga</span><span class="sxs-lookup"><span data-stu-id="52de8-161">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="52de8-162">07/07/2012 14.00</span><span class="sxs-lookup"><span data-stu-id="52de8-162">7/7/2012 2:00 PM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52de8-163">Davide Garghentini</span><span class="sxs-lookup"><span data-stu-id="52de8-163">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="52de8-164">02/07/2012 10.00</span><span class="sxs-lookup"><span data-stu-id="52de8-164">7/2/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52de8-165">Daniela Cazzaniga</span><span class="sxs-lookup"><span data-stu-id="52de8-165">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="52de8-166">02/07/2012 10.00</span><span class="sxs-lookup"><span data-stu-id="52de8-166">7/2/2012 10:00 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="52de8-167">Per ottenere un'indicazione più precisa del numero totale di utenti univoci che hanno organizzato conferenze, modificare l'intervallo di tempo, ad esempio esaminare i dati su base mensile anziché giornaliera.</span><span class="sxs-lookup"><span data-stu-id="52de8-167">To get a better idea of the total number of unique users who organized conferences, change your time interval; for example, look at the data by month instead of by day.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="52de8-168">Filtri</span><span class="sxs-lookup"><span data-stu-id="52de8-168">Filters</span></span>

<span data-ttu-id="52de8-p105">I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Ad esempio, il rapporto riepilogativo conferenze consente di scegliere la modalità di raggruppamento dei dati. In questo caso le conferenze sono raggruppabili per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="52de8-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Conference Summary Report enables you to choose how data should be grouped. In this case, conferences grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="52de8-172">Nella tabella seguente sono elencati i filtri applicabili al rapporto riepilogativo conferenze.</span><span class="sxs-lookup"><span data-stu-id="52de8-172">The following table lists the filters that you can use with the Conference Summary Report.</span></span>

### <a name="conference-summary-report-filters"></a><span data-ttu-id="52de8-173">Filtri del rapporto riepilogativo conferenze</span><span class="sxs-lookup"><span data-stu-id="52de8-173">Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52de8-174">Nome</span><span class="sxs-lookup"><span data-stu-id="52de8-174">Name</span></span></th>
<th><span data-ttu-id="52de8-175">Descrizione</span><span class="sxs-lookup"><span data-stu-id="52de8-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52de8-176"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="52de8-176"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="52de8-p106">Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="52de8-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="52de8-179">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="52de8-179">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="52de8-p107">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="52de8-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="52de8-182">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="52de8-182">7/7/2012</span></span></p>
<p><span data-ttu-id="52de8-183">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="52de8-183">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="52de8-184">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="52de8-184">7/3/2012</span></span></p>
<p><span data-ttu-id="52de8-185">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="52de8-185">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52de8-186"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="52de8-186"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="52de8-p108">Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="52de8-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="52de8-189">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="52de8-189">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="52de8-p109">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="52de8-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="52de8-192">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="52de8-192">7/7/2012</span></span></p>
<p><span data-ttu-id="52de8-193">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="52de8-193">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="52de8-194">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="52de8-194">7/3/2012</span></span></p>
<p><span data-ttu-id="52de8-195">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="52de8-195">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52de8-196"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="52de8-196"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="52de8-p110">Selezionare uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="52de8-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="52de8-199">Orario (è possibile visualizzare un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="52de8-199">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="52de8-200">Giornaliero (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="52de8-200">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="52de8-201">Settimanale (è possibile visualizzare un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="52de8-201">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="52de8-202">Mensile (è possibile visualizzare un massimo di 12 mesi)</span><span class="sxs-lookup"><span data-stu-id="52de8-202">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="52de8-p111">Se le date di inizio e fine superano il numero massimo di valori consentiti per l'intervallo specificato, verrà visualizzato solo il numero massimo di valori a partire dalla data di inizio. Se ad esempio si seleziona l'intervallo giornaliero con data di inizio 07/07/2012 e data di fine 28/02/2012, verranno visualizzati i dati per i giorni da 07/08/2012 ore 12.00 a 07/09/2012 ore 12.00 (per un totale di 31 giorni).</span><span class="sxs-lookup"><span data-stu-id="52de8-p111">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="52de8-205">Metriche</span><span class="sxs-lookup"><span data-stu-id="52de8-205">Metrics</span></span>

<span data-ttu-id="52de8-206">La tabella seguente elenca le informazioni disponibili nel rapporto riepilogativo conferenze.</span><span class="sxs-lookup"><span data-stu-id="52de8-206">The following table the information provided by the Conferences Summary Report.</span></span>

### <a name="conference-summary-report-metrics"></a><span data-ttu-id="52de8-207">Metriche del rapporto riepilogativo conferenze</span><span class="sxs-lookup"><span data-stu-id="52de8-207">Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52de8-208">Nome</span><span class="sxs-lookup"><span data-stu-id="52de8-208">Name</span></span></th>
<th><span data-ttu-id="52de8-209">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="52de8-209">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="52de8-210">Descrizione</span><span class="sxs-lookup"><span data-stu-id="52de8-210">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52de8-211"><strong>Orario</strong></span><span class="sxs-lookup"><span data-stu-id="52de8-211"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="52de8-212"><strong>Giornaliero</strong></span><span class="sxs-lookup"><span data-stu-id="52de8-212"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="52de8-213"><strong>Settimanale</strong></span><span class="sxs-lookup"><span data-stu-id="52de8-213"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="52de8-214"><strong>Mensile</strong></span><span class="sxs-lookup"><span data-stu-id="52de8-214"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="52de8-215">No</span><span class="sxs-lookup"><span data-stu-id="52de8-215">No</span></span></p></td>
<td><p><span data-ttu-id="52de8-p112">Indica l'intervallo di tempo selezionato sulla barra degli strumenti dei filtri. Ove applicabile, è possibile fare clic su un determinato intervallo di tempo per visualizzare informazioni dettagliate relative a tale intervallo. Se ad esempio si sta utilizzando l'intervallo giornaliero e si fa clic su 07/07/2012, verranno visualizzate le attività di registrazione degli utenti per tale data, suddivise per ore.</span><span class="sxs-lookup"><span data-stu-id="52de8-p112">Indicates the time interval that you selected on the filter toolbar. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52de8-219"><strong>Totale conferenze</strong></span><span class="sxs-lookup"><span data-stu-id="52de8-219"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="52de8-220">No</span><span class="sxs-lookup"><span data-stu-id="52de8-220">No</span></span></p></td>
<td><p><span data-ttu-id="52de8-p113">Numero totale di conferenze eseguite, indipendentemente dal tipo di conferenza. Facendo clic su questo elemento viene visualizzato il rapporto attività conferenza per il periodo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="52de8-p113">Total number of conferences (regardless of conference type) that were held. When you click this item, the report shows you the Conference Activity Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52de8-223"><strong>Totale partecipanti</strong></span><span class="sxs-lookup"><span data-stu-id="52de8-223"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="52de8-224">No</span><span class="sxs-lookup"><span data-stu-id="52de8-224">No</span></span></p></td>
<td><p><span data-ttu-id="52de8-p114">Numero totale di persone che hanno partecipato alle conferenze. Facendo clic su questo elemento viene visualizzato il rapporto attività conferenza per il periodo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="52de8-p114">Total number of people who took part in the conferences. When you click this item, the report shows you the Conference Activity Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52de8-227"><strong>Numero medio di partecipanti per conferenza</strong></span><span class="sxs-lookup"><span data-stu-id="52de8-227"><strong>Average participants per conference</strong></span></span></p></td>
<td><p><span data-ttu-id="52de8-228">No</span><span class="sxs-lookup"><span data-stu-id="52de8-228">No</span></span></p></td>
<td><p><span data-ttu-id="52de8-p115">Numero medio di persone che hanno preso parte a una specifica conferenza, determinato dividendo il numero totale di conferenze per il numero totale di partecipanti.</span><span class="sxs-lookup"><span data-stu-id="52de8-p115">Average number of people who took part in a given conference. Determined by dividing the total conferences by the total participants.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52de8-231"><strong>Totale conferenze audio/video</strong></span><span class="sxs-lookup"><span data-stu-id="52de8-231"><strong>Total A/V conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="52de8-232">No</span><span class="sxs-lookup"><span data-stu-id="52de8-232">No</span></span></p></td>
<td><p><span data-ttu-id="52de8-233">Numero totale di conferenze con audio o video.</span><span class="sxs-lookup"><span data-stu-id="52de8-233">Total number of conferences that included audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52de8-234"><strong>Totale minuti di conferenza audio/video</strong></span><span class="sxs-lookup"><span data-stu-id="52de8-234"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="52de8-235">No</span><span class="sxs-lookup"><span data-stu-id="52de8-235">No</span></span></p></td>
<td><p><span data-ttu-id="52de8-236">Numero totale di minuti dedicati alle conferenze audio/video.</span><span class="sxs-lookup"><span data-stu-id="52de8-236">Total number of minutes devoted to audio/video conferencing.</span></span></p>
<p><span data-ttu-id="52de8-237">La metrica Total A/V Conference minutes riepiloga tutti i tipi di conferenze audio/video, tra cui: conferenze A/V. Conferenze di messaggistica istantanea; Conferenze di condivisione app; Conferenze dati; e conferenze PSTN.</span><span class="sxs-lookup"><span data-stu-id="52de8-237">The Total A/V conference minutes metric summarizes all the audio/visual conference types, including: A/V conferences; IM conferences; app sharing conferences; data conferences; and PSTN conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52de8-238"><strong>Totale minuti partecipante di conferenza audio/video</strong></span><span class="sxs-lookup"><span data-stu-id="52de8-238"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="52de8-239">No</span><span class="sxs-lookup"><span data-stu-id="52de8-239">No</span></span></p></td>
<td><p><span data-ttu-id="52de8-p116">Numero totale di minuti partecipante dedicati alle conferenze audio/video. Si supponga, ad esempio, che un utente dedichi 5 minuti a una conferenza audio/video e che un secondo utente ne dedichi 3 nella stessa conferenza. Si ottiene così un totale di 8 minuti partecipante (5+3).</span><span class="sxs-lookup"><span data-stu-id="52de8-p116">Total number of participant minutes devoted to audio/video conferencing. For example, suppose one user spends 5 minutes in an audio/video conference and a second user spends 3 minutes in that same conference. That makes a total of 8 participant minutes: 5 minutes plus 3 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52de8-243"><strong>Media minuti di conferenza audio/video	</strong></span><span class="sxs-lookup"><span data-stu-id="52de8-243"><strong>Average A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="52de8-244">No</span><span class="sxs-lookup"><span data-stu-id="52de8-244">No</span></span></p></td>
<td><p><span data-ttu-id="52de8-245">Numero medio di minuti per conferenza audio/video.</span><span class="sxs-lookup"><span data-stu-id="52de8-245">Average number of minutes per audio/video conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52de8-246"><strong>Totale organizzatori conferenza univoci</strong></span><span class="sxs-lookup"><span data-stu-id="52de8-246"><strong>Total number of unique organizers of conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="52de8-247">No</span><span class="sxs-lookup"><span data-stu-id="52de8-247">No</span></span></p></td>
<td><p><span data-ttu-id="52de8-p117">Numero totale di utenti che hanno organizzato almeno una conferenza. Gli utenti che hanno organizzato più conferenze vengono considerati come un organizzatore unico, come gli utenti che hanno organizzato una sola conferenza.</span><span class="sxs-lookup"><span data-stu-id="52de8-p117">Total number of users who organized at least one conference. Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52de8-250"><strong>Totale messaggi conferenza</strong></span><span class="sxs-lookup"><span data-stu-id="52de8-250"><strong>Total conference messages</strong></span></span></p></td>
<td><p><span data-ttu-id="52de8-251">No</span><span class="sxs-lookup"><span data-stu-id="52de8-251">No</span></span></p></td>
<td><p><span data-ttu-id="52de8-252">Numero totale di messaggi istantanei inviati durante le conferenze.</span><span class="sxs-lookup"><span data-stu-id="52de8-252">Total number of instant messages sent during the conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

