---
title: 'Lync Server 2013: rapporto riepilogativo conferenze PSTN'
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
ms.openlocfilehash: aa902b9e4d53bf0ebbedf835296a371437860095
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="eb9a5-102">Report riepilogativo conferenze PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb9a5-102">PSTN Conference Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb9a5-103">_**Ultimo argomento modificato:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="eb9a5-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="eb9a5-104">In Microsoft Lync Server 2013, una conferenza PSTN è una conferenza in cui almeno un partecipante compone la parte audio tramite un telefono PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="eb9a5-104">In Microsoft Lync Server 2013, a PSTN conference is any conference in which at least one participant dials in to the audio portion by a using a PSTN (public switched telephone network) phone.</span></span> <span data-ttu-id="eb9a5-105">(Un telefono PSTN è una "rete fissa", un telefono cellulare o qualsiasi altro telefono che non utilizza il Voice over IP). Anche se denominate conferenze PSTN nei rapporti di monitoraggio, queste conferenze sono forse più comunemente note come conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="eb9a5-105">(A PSTN phone is a "landline," a cell phone, or any other phone which does not make use of Voice over IP.) Although referred to as PSTN conferences in the Monitoring Reports, these conferences are perhaps more-commonly known as dial-in conferences.</span></span>

<span data-ttu-id="eb9a5-p102">Il Rapporto riepilogativo conferenze PSTN offre informazioni su tutte le conferenze PSTN tenutesi nell'organizzazione, ovvero tutte le conferenze con almeno un utente in accesso esterno. Il rapporto include informazioni sul numero totale di conferenze PSTN, il numero totale di utenti che vi hanno preso parte e (probabilmente il dato più importante) il numero totale di utenti con accesso esterno (metrica Totale partecipanti PSTN).</span><span class="sxs-lookup"><span data-stu-id="eb9a5-p102">The PSTN Conference Summary Report provides information about all the PSTN conferences held in your organization (that is, all the conferences that had at least one dial-in user). The report includes information about the total number of PSTN conferences, the total number of people who participated in those conferences, and, perhaps, most important, the total number of dial-in users (the Total PSTN participants metric).</span></span>

<div>

## <a name="accessing-the-pstn-conference-summary-report"></a><span data-ttu-id="eb9a5-108">Accesso al Rapporto riepilogativo conferenze PSTN</span><span class="sxs-lookup"><span data-stu-id="eb9a5-108">Accessing the PSTN Conference Summary Report</span></span>

<span data-ttu-id="eb9a5-p103">Il Rapporto riepilogativo conferenze PSTN è accessibile solo dalla home page Rapporti di monitoraggio. Questo rapporto non è collegato ad altri rapporti. Tenere presente che non è possibile recuperare informazioni dettagliate sulle chiamate per una conferenza PSTN, in parte perché i singoli endpoint sono responsabili dell'invio di tali informazioni. I telefoni PSTN non sono in grado di registrare o inviare informazioni dettagliate sulle chiamate.</span><span class="sxs-lookup"><span data-stu-id="eb9a5-p103">The PSTN Conference Summary Report can only be accessed from the Monitoring Reports home page. This report is not linked to any other reports. Note that you cannot retrieve detailed call information for a PSTN conference, in part because individual endpoints are responsible for submitting this information. PSTN phones are not capable of tracking or submitting call detail information.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a><span data-ttu-id="eb9a5-113">Uso ottimale del Rapporto riepilogativo conferenze PSTN</span><span class="sxs-lookup"><span data-stu-id="eb9a5-113">Making the Best Use of the PSTN Conference Summary Report</span></span>

<span data-ttu-id="eb9a5-114">Per determinare la percentuale di tutte le conferenze che includono gli utenti con accesso esterno, confrontare il valore della metrica totale conferenze PSTN con le metriche delle conferenze totali trovate [nel rapporto riepilogativo conferenze in Lync Server 2013](lync-server-2013-conference-summary-report.md).</span><span class="sxs-lookup"><span data-stu-id="eb9a5-114">To determine the percentage of all your conferences that include dial-in users, compare the value of the Total PSTN conferences metric with the Total conferences metric found on the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md).</span></span>

<span data-ttu-id="eb9a5-p104">Se non è disponibile il dato previsto sul numero di conferenze PSTN, tenere presente che la capacità di organizzare una conferenza che consenta gli utenti con accesso esterno dipende dai criteri di conferenza assegnati a un utente: se a un numero estremamente esiguo di utenti è consentito tenere conferenze PSTN di conseguenza vi saranno poche conferenze PSTN. È possibile verificare rapidamente gli eventuali criteri di conferenza che consentono agli utenti di pianificare conferenze PSTN eseguendo il comando seguente dalla shell di gestione di Lync Server:</span><span class="sxs-lookup"><span data-stu-id="eb9a5-p104">If you don't see as many PSTN conferences as you might have expected to see, keep in mind that the ability to organize a conference that allows dial-in users depends on the conferencing policy that has been assigned to a user: if very few of your users are allowed to hold PSTN conferences you would obviously see very few PSTN conferences. You can quickly verify which of your conferencing policies (if any) allow users to schedule PSTN conferences by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

<span data-ttu-id="eb9a5-117">Il comando restituisce dati analoghi a questi:</span><span class="sxs-lookup"><span data-stu-id="eb9a5-117">That will return data similar to this:</span></span>

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

<span data-ttu-id="eb9a5-118">Il comando restituisce dati analoghi a questi:</span><span class="sxs-lookup"><span data-stu-id="eb9a5-118">That will return data similar to this:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="eb9a5-119">Filtri</span><span class="sxs-lookup"><span data-stu-id="eb9a5-119">Filters</span></span>

<span data-ttu-id="eb9a5-p105">I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Ad esempio, il rapporto riepilogativo conferenze PSTN consente di scegliere la modalità di raggruppamento dei dati. In questo caso le conferenze sono raggruppabili per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="eb9a5-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the PSTN Conference Summary Report enables you to choose how data should be grouped. In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="eb9a5-123">Nella tabella seguente sono elencati i filtri applicabili al Rapporto riepilogativo conferenze PSTN.</span><span class="sxs-lookup"><span data-stu-id="eb9a5-123">The following table lists the filters that you can use with the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-filters"></a><span data-ttu-id="eb9a5-124">Filtri del Rapporto riepilogativo conferenze PSTN</span><span class="sxs-lookup"><span data-stu-id="eb9a5-124">PSTN Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb9a5-125">Nome</span><span class="sxs-lookup"><span data-stu-id="eb9a5-125">Name</span></span></th>
<th><span data-ttu-id="eb9a5-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eb9a5-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb9a5-127"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="eb9a5-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="eb9a5-p106">Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="eb9a5-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="eb9a5-130">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="eb9a5-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="eb9a5-p107">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="eb9a5-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="eb9a5-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="eb9a5-133">7/7/2012</span></span></p>
<p><span data-ttu-id="eb9a5-134">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="eb9a5-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="eb9a5-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="eb9a5-135">7/3/2012</span></span></p>
<p><span data-ttu-id="eb9a5-136">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="eb9a5-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb9a5-137"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="eb9a5-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="eb9a5-p108">Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="eb9a5-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="eb9a5-140">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="eb9a5-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="eb9a5-p109">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="eb9a5-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="eb9a5-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="eb9a5-143">7/7/2012</span></span></p>
<p><span data-ttu-id="eb9a5-144">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="eb9a5-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="eb9a5-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="eb9a5-145">7/3/2012</span></span></p>
<p><span data-ttu-id="eb9a5-146">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="eb9a5-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb9a5-147"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="eb9a5-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="eb9a5-p110">Selezionare uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="eb9a5-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="eb9a5-150">Orario (è possibile visualizzare un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="eb9a5-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="eb9a5-151">Giornaliero (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="eb9a5-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="eb9a5-152">Settimanale (è possibile visualizzare un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="eb9a5-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="eb9a5-153">Mensile (è possibile visualizzare un massimo di 12 mesi)</span><span class="sxs-lookup"><span data-stu-id="eb9a5-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="eb9a5-p111">Se le date di inizio e fine superano il numero massimo di valori consentiti per l'intervallo specificato, verrà visualizzato solo il numero massimo di valori a partire dalla data di inizio. Se ad esempio si seleziona l'intervallo giornaliero con data di inizio 07/07/2012 e data di fine 28/02/2012, verranno visualizzati i dati per i giorni da 07/08/2012 ore 00.00 a 07/09/2012 ore 00:00 (per un totale di 31 giorni).</span><span class="sxs-lookup"><span data-stu-id="eb9a5-p111">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="eb9a5-156">Metriche</span><span class="sxs-lookup"><span data-stu-id="eb9a5-156">Metrics</span></span>

<span data-ttu-id="eb9a5-157">La tabella seguente elenca le informazioni disponibili nel Rapporto riepilogativo conferenze PSTN.</span><span class="sxs-lookup"><span data-stu-id="eb9a5-157">The following table lists the information in the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-metrics"></a><span data-ttu-id="eb9a5-158">Metriche del Rapporto riepilogativo conferenze PSTN</span><span class="sxs-lookup"><span data-stu-id="eb9a5-158">PSTN Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb9a5-159">Nome</span><span class="sxs-lookup"><span data-stu-id="eb9a5-159">Name</span></span></th>
<th><span data-ttu-id="eb9a5-160">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="eb9a5-160">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="eb9a5-161">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eb9a5-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb9a5-162"><strong>Orario</strong></span><span class="sxs-lookup"><span data-stu-id="eb9a5-162"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="eb9a5-163"><strong>Giornaliero</strong></span><span class="sxs-lookup"><span data-stu-id="eb9a5-163"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="eb9a5-164"><strong>Settimanale</strong></span><span class="sxs-lookup"><span data-stu-id="eb9a5-164"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="eb9a5-165"><strong>Mensile</strong></span><span class="sxs-lookup"><span data-stu-id="eb9a5-165"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="eb9a5-166">No</span><span class="sxs-lookup"><span data-stu-id="eb9a5-166">No</span></span></p></td>
<td><p><span data-ttu-id="eb9a5-p112">Indica l'intervallo di tempo selezionato. Ove applicabile, è possibile fare clic su un determinato intervallo di tempo per visualizzare informazioni dettagliate relative a tale intervallo. Se ad esempio si sta utilizzando l'intervallo giornaliero e si fa clic su 07/07/2012, verranno visualizzate le attività di registrazione degli utenti per tale data, suddivise per ore.</span><span class="sxs-lookup"><span data-stu-id="eb9a5-p112">Indicates the selected time interval. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb9a5-170"><strong>Totale conferenze PSTN</strong></span><span class="sxs-lookup"><span data-stu-id="eb9a5-170"><strong>Total PSTN conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="eb9a5-171">No</span><span class="sxs-lookup"><span data-stu-id="eb9a5-171">No</span></span></p></td>
<td><p><span data-ttu-id="eb9a5-172">Numero totale di conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="eb9a5-172">Total number conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb9a5-173"><strong>Totale partecipanti</strong></span><span class="sxs-lookup"><span data-stu-id="eb9a5-173"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="eb9a5-174">No</span><span class="sxs-lookup"><span data-stu-id="eb9a5-174">No</span></span></p></td>
<td><p><span data-ttu-id="eb9a5-175">Numero totale di persone che hanno partecipato a conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="eb9a5-175">Total number of people who participated in conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb9a5-176"><strong>Totale minuti di conferenza audio/video</strong></span><span class="sxs-lookup"><span data-stu-id="eb9a5-176"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="eb9a5-177">No</span><span class="sxs-lookup"><span data-stu-id="eb9a5-177">No</span></span></p></td>
<td><p><span data-ttu-id="eb9a5-178">Durata totale delle conferenze audio/video.</span><span class="sxs-lookup"><span data-stu-id="eb9a5-178">Total amount of audio/visual conference time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb9a5-179"><strong>Totale minuti partecipante di conferenza audio/video</strong></span><span class="sxs-lookup"><span data-stu-id="eb9a5-179"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="eb9a5-180">No</span><span class="sxs-lookup"><span data-stu-id="eb9a5-180">No</span></span></p></td>
<td><p><span data-ttu-id="eb9a5-p113">Totale minuti di partecipazione a conferenze audio/video. Ad esempio, se un partecipante ha trascorso cinque minuti in una conferenza audio/video e un altro partecipante ha trascorso tre minuti nella stessa conferenza, il totale sarà otto minuti.</span><span class="sxs-lookup"><span data-stu-id="eb9a5-p113">Total amount of audio/visual participant time. For example, if one participant spent five minutes in an A/V conference and another participant spent three minutes in the same conference, the total A/V conference participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb9a5-183"><strong>Totale partecipanti PSTN</strong></span><span class="sxs-lookup"><span data-stu-id="eb9a5-183"><strong>Total PSTN participants</strong></span></span></p></td>
<td><p><span data-ttu-id="eb9a5-184">No</span><span class="sxs-lookup"><span data-stu-id="eb9a5-184">No</span></span></p></td>
<td><p><span data-ttu-id="eb9a5-185">Numero totale di utenti che si sono connessi a conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="eb9a5-185">Total number of users who dialed in to conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb9a5-186"><strong>Totale minuti partecipante PSTN</strong></span><span class="sxs-lookup"><span data-stu-id="eb9a5-186"><strong>Total PSTN participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="eb9a5-187">No</span><span class="sxs-lookup"><span data-stu-id="eb9a5-187">No</span></span></p></td>
<td><p><span data-ttu-id="eb9a5-p114">Tempo totale trascorso in conferenza da utenti connessi tramite chiamata in ingresso. Ad esempio, se un partecipante connesso tramite chiamata in ingresso ha trascorso cinque minuti in una conferenza e un altro partecipante ha trascorso tre minuti nella stessa conferenza, il totale sarà otto minuti.</span><span class="sxs-lookup"><span data-stu-id="eb9a5-p114">Total amount of conference time spent by dial-in users. For example, if one dial-in participant spent five minutes in a conference and another participant spent three minutes in the same conference, the total PSTN participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb9a5-190"><strong>Organizzatori conferenza univoci</strong></span><span class="sxs-lookup"><span data-stu-id="eb9a5-190"><strong>Unique conference organizers</strong></span></span></p></td>
<td><p><span data-ttu-id="eb9a5-191">No</span><span class="sxs-lookup"><span data-stu-id="eb9a5-191">No</span></span></p></td>
<td><p><span data-ttu-id="eb9a5-p115">Numero totale di utenti che hanno organizzato almeno una conferenza telefonica con accesso esterno. Gli utenti che hanno organizzato più conferenze vengono considerati come un organizzatore unico, come gli utenti che hanno organizzato una sola conferenza.</span><span class="sxs-lookup"><span data-stu-id="eb9a5-p115">Total number of users who organized at least one conference that allowed dial-in access. Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

