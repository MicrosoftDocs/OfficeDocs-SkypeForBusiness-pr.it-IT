---
title: 'Lync Server 2013: report di riepilogo conferenza PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN Conference Summary Report
ms:assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615014(v=OCS.15)
ms:contentKeyID: 48184764
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8cd36f651a84b25f7e8163a8cfc40aff5162f90
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="d273c-102">Report di riepilogo conferenza PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d273c-102">PSTN Conference Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d273c-103">_**Argomento Ultima modifica:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="d273c-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="d273c-104">In Microsoft Lync Server 2013 una conferenza PSTN è una conferenza in cui almeno un partecipante compone la parte audio tramite un telefono PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="d273c-104">In Microsoft Lync Server 2013, a PSTN conference is any conference in which at least one participant dials in to the audio portion by a using a PSTN (public switched telephone network) phone.</span></span> <span data-ttu-id="d273c-105">(Un telefono PSTN è un "telefono fisso", un cellulare o un altro telefono che non fa uso di Voice over IP.) Anche se si fa riferimento a conferenze PSTN nei report di monitoraggio, queste conferenze sono forse più comunemente note come conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="d273c-105">(A PSTN phone is a "landline," a cell phone, or any other phone which does not make use of Voice over IP.) Although referred to as PSTN conferences in the Monitoring Reports, these conferences are perhaps more-commonly known as dial-in conferences.</span></span>

<span data-ttu-id="d273c-106">Il report Riepilogo conferenza PSTN contiene informazioni su tutte le conferenze PSTN svolte nell'organizzazione, ovvero tutte le conferenze con almeno un utente con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="d273c-106">The PSTN Conference Summary Report provides information about all the PSTN conferences held in your organization (that is, all the conferences that had at least one dial-in user).</span></span> <span data-ttu-id="d273c-107">Il report include informazioni sul numero totale di conferenze PSTN, il numero totale di persone che hanno partecipato a tali conferenze e, forse, più importante, il numero totale di utenti con accesso esterno (la metrica totale dei partecipanti PSTN).</span><span class="sxs-lookup"><span data-stu-id="d273c-107">The report includes information about the total number of PSTN conferences, the total number of people who participated in those conferences, and, perhaps, most important, the total number of dial-in users (the Total PSTN participants metric).</span></span>

<div>

## <a name="accessing-the-pstn-conference-summary-report"></a><span data-ttu-id="d273c-108">Accesso al report di riepilogo conferenza PSTN</span><span class="sxs-lookup"><span data-stu-id="d273c-108">Accessing the PSTN Conference Summary Report</span></span>

<span data-ttu-id="d273c-109">Il report Riepilogo conferenza PSTN può essere accessibile solo dalla Home page dei report di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="d273c-109">The PSTN Conference Summary Report can only be accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="d273c-110">Questo report non è collegato ad altri report.</span><span class="sxs-lookup"><span data-stu-id="d273c-110">This report is not linked to any other reports.</span></span> <span data-ttu-id="d273c-111">Tieni presente che non puoi recuperare informazioni dettagliate sulle chiamate per una conferenza PSTN, in parte perché i singoli endpoint sono responsabili dell'invio di queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="d273c-111">Note that you cannot retrieve detailed call information for a PSTN conference, in part because individual endpoints are responsible for submitting this information.</span></span> <span data-ttu-id="d273c-112">I telefoni PSTN non sono in grado di tenere traccia o inviare informazioni dettagliate sulle chiamate.</span><span class="sxs-lookup"><span data-stu-id="d273c-112">PSTN phones are not capable of tracking or submitting call detail information.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a><span data-ttu-id="d273c-113">Uso ottimale del report di riepilogo conferenza PSTN</span><span class="sxs-lookup"><span data-stu-id="d273c-113">Making the Best Use of the PSTN Conference Summary Report</span></span>

<span data-ttu-id="d273c-114">Per determinare la percentuale di tutte le conferenze che includono utenti con accesso esterno, confrontare il valore della metrica totale conferenze PSTN con la metrica totale conferenze disponibile [nel report di riepilogo conferenza in Lync Server 2013](lync-server-2013-conference-summary-report.md).</span><span class="sxs-lookup"><span data-stu-id="d273c-114">To determine the percentage of all your conferences that include dial-in users, compare the value of the Total PSTN conferences metric with the Total conferences metric found on the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md).</span></span>

<span data-ttu-id="d273c-115">Se non si vedono tutte le conferenze PSTN che si potrebbero prevedere, tenere presente che la possibilità di organizzare una conferenza che consente agli utenti di accesso esterno dipende dal criterio di conferenza assegnato a un utente: se pochissimi utenti sono autorizzati a tenere premuto PS Conferenze TN si vedranno ovviamente pochissime conferenze PSTN.</span><span class="sxs-lookup"><span data-stu-id="d273c-115">If you don't see as many PSTN conferences as you might have expected to see, keep in mind that the ability to organize a conference that allows dial-in users depends on the conferencing policy that has been assigned to a user: if very few of your users are allowed to hold PSTN conferences you would obviously see very few PSTN conferences.</span></span> <span data-ttu-id="d273c-116">È possibile verificare rapidamente quale dei criteri di conferenza (se presenti) consente agli utenti di pianificare conferenze PSTN eseguendo il comando seguente da Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="d273c-116">You can quickly verify which of your conferencing policies (if any) allow users to schedule PSTN conferences by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

<span data-ttu-id="d273c-117">Che restituirà dati simili a questi:</span><span class="sxs-lookup"><span data-stu-id="d273c-117">That will return data similar to this:</span></span>

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

<span data-ttu-id="d273c-118">Che restituirà dati simili a questi:</span><span class="sxs-lookup"><span data-stu-id="d273c-118">That will return data similar to this:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="d273c-119">Filtri</span><span class="sxs-lookup"><span data-stu-id="d273c-119">Filters</span></span>

<span data-ttu-id="d273c-120">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="d273c-120">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="d273c-121">Ad esempio, il report Riepilogo conferenza PSTN consente di scegliere la modalità di raggruppamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="d273c-121">For example, the PSTN Conference Summary Report enables you to choose how data should be grouped.</span></span> <span data-ttu-id="d273c-122">In questo caso, le conferenze vengono raggruppate per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="d273c-122">In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="d273c-123">Nella tabella seguente sono elencati i filtri che è possibile usare con il report di riepilogo conferenza PSTN.</span><span class="sxs-lookup"><span data-stu-id="d273c-123">The following table lists the filters that you can use with the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-filters"></a><span data-ttu-id="d273c-124">Filtri report Riepilogo conferenza PSTN</span><span class="sxs-lookup"><span data-stu-id="d273c-124">PSTN Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d273c-125">Nome</span><span class="sxs-lookup"><span data-stu-id="d273c-125">Name</span></span></th>
<th><span data-ttu-id="d273c-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d273c-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d273c-127"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="d273c-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="d273c-128">Data/ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="d273c-128">Start date/time for the time range.</span></span> <span data-ttu-id="d273c-129">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="d273c-129">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="d273c-130">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="d273c-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="d273c-131">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="d273c-131">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="d273c-132">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="d273c-132">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d273c-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="d273c-133">7/7/2012</span></span></p>
<p><span data-ttu-id="d273c-134">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="d273c-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d273c-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="d273c-135">7/3/2012</span></span></p>
<p><span data-ttu-id="d273c-136">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="d273c-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d273c-137"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="d273c-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="d273c-138">Data/ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="d273c-138">End date/time for the time range.</span></span> <span data-ttu-id="d273c-139">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="d273c-139">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="d273c-140">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="d273c-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="d273c-141">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="d273c-141">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="d273c-142">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="d273c-142">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d273c-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="d273c-143">7/7/2012</span></span></p>
<p><span data-ttu-id="d273c-144">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="d273c-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d273c-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="d273c-145">7/3/2012</span></span></p>
<p><span data-ttu-id="d273c-146">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="d273c-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d273c-147"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="d273c-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="d273c-148">Intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="d273c-148">Time interval.</span></span> <span data-ttu-id="d273c-149">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d273c-149">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d273c-150">Ogni ora (può essere visualizzato un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="d273c-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d273c-151">Giornaliera (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="d273c-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d273c-152">Settimanale (può essere visualizzato un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="d273c-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d273c-153">Mensile (può essere visualizzato un massimo di 12 mesi)</span><span class="sxs-lookup"><span data-stu-id="d273c-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="d273c-154">Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, viene visualizzato solo il numero massimo di valori (a partire dalla data di inizio).</span><span class="sxs-lookup"><span data-stu-id="d273c-154">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="d273c-155">Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/7/2012 e una data di fine 2/28/2012, i dati verranno visualizzati per i giorni 8/7/2012 12:00 da AM a 9/7/2012 12:00 AM, ovvero un totale di 31 giorni di dati.</span><span class="sxs-lookup"><span data-stu-id="d273c-155">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="d273c-156">Metriche</span><span class="sxs-lookup"><span data-stu-id="d273c-156">Metrics</span></span>

<span data-ttu-id="d273c-157">Nella tabella seguente sono elencate le informazioni nel report di riepilogo conferenza PSTN.</span><span class="sxs-lookup"><span data-stu-id="d273c-157">The following table lists the information in the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-metrics"></a><span data-ttu-id="d273c-158">Metriche report Riepilogo conferenza PSTN</span><span class="sxs-lookup"><span data-stu-id="d273c-158">PSTN Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d273c-159">Nome</span><span class="sxs-lookup"><span data-stu-id="d273c-159">Name</span></span></th>
<th><span data-ttu-id="d273c-160">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="d273c-160">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d273c-161">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d273c-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d273c-162"><strong>Oraria</strong></span><span class="sxs-lookup"><span data-stu-id="d273c-162"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="d273c-163"><strong>Quotidiana</strong></span><span class="sxs-lookup"><span data-stu-id="d273c-163"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="d273c-164"><strong>Settimanale</strong></span><span class="sxs-lookup"><span data-stu-id="d273c-164"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="d273c-165"><strong>Mensile</strong></span><span class="sxs-lookup"><span data-stu-id="d273c-165"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="d273c-166">No</span><span class="sxs-lookup"><span data-stu-id="d273c-166">No</span></span></p></td>
<td><p><span data-ttu-id="d273c-167">Indica l'intervallo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="d273c-167">Indicates the selected time interval.</span></span> <span data-ttu-id="d273c-168">Se applicabile, è possibile fare clic su un intervallo di tempo specifico per visualizzare informazioni dettagliate per l'intervallo.</span><span class="sxs-lookup"><span data-stu-id="d273c-168">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="d273c-169">Se ad esempio si usa l'intervallo giornaliero e si fa clic su 7/7/2012, viene visualizzata una ripartizione oraria dell'attività di registrazione utente per tale data.</span><span class="sxs-lookup"><span data-stu-id="d273c-169">For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d273c-170"><strong>Totale conferenze PSTN</strong></span><span class="sxs-lookup"><span data-stu-id="d273c-170"><strong>Total PSTN conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="d273c-171">No</span><span class="sxs-lookup"><span data-stu-id="d273c-171">No</span></span></p></td>
<td><p><span data-ttu-id="d273c-172">Numero totale di conferenze che hanno consentito l'accesso tramite chiamata in ingresso.</span><span class="sxs-lookup"><span data-stu-id="d273c-172">Total number conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d273c-173"><strong>Totale partecipanti</strong></span><span class="sxs-lookup"><span data-stu-id="d273c-173"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="d273c-174">No</span><span class="sxs-lookup"><span data-stu-id="d273c-174">No</span></span></p></td>
<td><p><span data-ttu-id="d273c-175">Numero totale di persone che hanno partecipato a conferenze che hanno consentito l'accesso tramite chiamata in ingresso.</span><span class="sxs-lookup"><span data-stu-id="d273c-175">Total number of people who participated in conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d273c-176"><strong>Totale minuti di conferenza A/V</strong></span><span class="sxs-lookup"><span data-stu-id="d273c-176"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="d273c-177">No</span><span class="sxs-lookup"><span data-stu-id="d273c-177">No</span></span></p></td>
<td><p><span data-ttu-id="d273c-178">Quantità totale di tempo per le conferenze audio/visive.</span><span class="sxs-lookup"><span data-stu-id="d273c-178">Total amount of audio/visual conference time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d273c-179"><strong>Totale minuti partecipanti alla conferenza A/V</strong></span><span class="sxs-lookup"><span data-stu-id="d273c-179"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="d273c-180">No</span><span class="sxs-lookup"><span data-stu-id="d273c-180">No</span></span></p></td>
<td><p><span data-ttu-id="d273c-181">Quantità totale di tempo dei partecipanti audio/visivi.</span><span class="sxs-lookup"><span data-stu-id="d273c-181">Total amount of audio/visual participant time.</span></span> <span data-ttu-id="d273c-182">Ad esempio, se un partecipante ha trascorso cinque minuti in una conferenza A/V e un altro partecipante ha trascorso tre minuti nella stessa conferenza, il tempo totale per i partecipanti alla conferenza A/V sarebbe di otto minuti.</span><span class="sxs-lookup"><span data-stu-id="d273c-182">For example, if one participant spent five minutes in an A/V conference and another participant spent three minutes in the same conference, the total A/V conference participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d273c-183"><strong>Totale partecipanti PSTN</strong></span><span class="sxs-lookup"><span data-stu-id="d273c-183"><strong>Total PSTN participants</strong></span></span></p></td>
<td><p><span data-ttu-id="d273c-184">No</span><span class="sxs-lookup"><span data-stu-id="d273c-184">No</span></span></p></td>
<td><p><span data-ttu-id="d273c-185">Numero totale di utenti che hanno eseguito la chiamata a conferenze che hanno consentito l'accesso tramite chiamata in ingresso.</span><span class="sxs-lookup"><span data-stu-id="d273c-185">Total number of users who dialed in to conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d273c-186"><strong>Minuti totali dei partecipanti PSTN</strong></span><span class="sxs-lookup"><span data-stu-id="d273c-186"><strong>Total PSTN participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="d273c-187">No</span><span class="sxs-lookup"><span data-stu-id="d273c-187">No</span></span></p></td>
<td><p><span data-ttu-id="d273c-188">Importo totale del tempo di conferenza trascorso dagli utenti con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="d273c-188">Total amount of conference time spent by dial-in users.</span></span> <span data-ttu-id="d273c-189">Ad esempio, se un partecipante con accesso esterno ha trascorso cinque minuti in una conferenza e un altro partecipante ha trascorso tre minuti nella stessa conferenza, il tempo totale dei partecipanti PSTN sarebbe di otto minuti.</span><span class="sxs-lookup"><span data-stu-id="d273c-189">For example, if one dial-in participant spent five minutes in a conference and another participant spent three minutes in the same conference, the total PSTN participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d273c-190"><strong>Organizzatori di conferenze univoci</strong></span><span class="sxs-lookup"><span data-stu-id="d273c-190"><strong>Unique conference organizers</strong></span></span></p></td>
<td><p><span data-ttu-id="d273c-191">No</span><span class="sxs-lookup"><span data-stu-id="d273c-191">No</span></span></p></td>
<td><p><span data-ttu-id="d273c-192">Numero totale di utenti che hanno organizzato almeno una conferenza che consentiva l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="d273c-192">Total number of users who organized at least one conference that allowed dial-in access.</span></span> <span data-ttu-id="d273c-193">Gli utenti che hanno organizzato più di una conferenza vengono conteggiati come un unico organizzatore, proprio come gli utenti che hanno organizzato una singola conferenza.</span><span class="sxs-lookup"><span data-stu-id="d273c-193">Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

