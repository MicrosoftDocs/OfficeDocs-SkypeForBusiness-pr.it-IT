---
title: 'Lync Server 2013: rapporto riepilogativo attività peer-to-peer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Summary Report
ms:assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615041(v=OCS.15)
ms:contentKeyID: 48185884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f96470163b1f258f59bb37128b45fbc5e15476e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "41989361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a><span data-ttu-id="0933c-102">Rapporto riepilogativo attività peer-to-peer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0933c-102">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0933c-103">_**Ultimo argomento modificato:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="0933c-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="0933c-104">Il Rapporto riepilogativo attività peer-to-peer offre informazioni generali sulle sessioni di comunicazione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="0933c-104">The Peer-to-Peer Activity Summary Report provides an overall view of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="0933c-105">Una sessione peer-to-peer in genere coinvolge solo due utenti e non richiede l'utilizzo di Lync Server Conferencing Services.</span><span class="sxs-lookup"><span data-stu-id="0933c-105">A peer-to-peer session typically involves just two users, and does not require the use of the Lync Server conferencing services.</span></span> <span data-ttu-id="0933c-106">In base al confronto, una conferenza solitamente coinvolge più di due utenti e richiede l'utilizzo di Microsoft Lync Server 2013 Servizi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="0933c-106">By comparison, a conference typically involves more than two users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="0933c-107">Le attività relative alle conferenze sono riepilogate nel Rapporto riepilogativo conferenze.</span><span class="sxs-lookup"><span data-stu-id="0933c-107">Conference activity is reported on the Conference Summary Report.</span></span>

<span data-ttu-id="0933c-108">Nel Rapporto riepilogativo attività peer-to-peer è possibile trovare risposte a domande come le seguenti:</span><span class="sxs-lookup"><span data-stu-id="0933c-108">The Peer-to-Peer Activity Summary Report helps you answer questions like the following:</span></span>

  - <span data-ttu-id="0933c-109">Quanti messaggi istantanei peer-to-peer si scambiano quotidianamente gli utenti?</span><span class="sxs-lookup"><span data-stu-id="0933c-109">How many peer-to-peer instant messages do my users send on a typical day?</span></span>

  - <span data-ttu-id="0933c-110">Gli utenti sono effettivamente avvantaggiati dalle funzionalità di condivisione delle applicazioni e di trasferimento di file di Lync Server?</span><span class="sxs-lookup"><span data-stu-id="0933c-110">Are any of my users actually taking advantage of the Lync Server application sharing and file transfer capabilities?</span></span>

  - <span data-ttu-id="0933c-p102">Gli utenti si lamentano della lentezza della rete in periodi specifici del giorno. Quanti minuti sono dedicati alle sessioni audio e video peer-to-peer durante tali periodi?</span><span class="sxs-lookup"><span data-stu-id="0933c-p102">Users have been complaining that the network seems slow at certain times of the day. How many minutes are devoted to peer-to-peer audio and video sessions during those time periods?</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="0933c-113">Accesso al Rapporto riepilogativo attività peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="0933c-113">Accessing the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="0933c-114">Il Rapporto riepilogativo attività peer-to-peer è accessibile dalla home page dei rapporti di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="0933c-114">You access the Peer-to-Peer Activity Summary Report from the Monitoring Reports home page.</span></span> <span data-ttu-id="0933c-115">È possibile aprire il [rapporto di messaggistica istantanea peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="0933c-115">You open the [Peer-to-Peer IM Report in Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="0933c-116">Totale sessioni di messaggistica istantanea peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="0933c-116">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="0933c-117">Totale messaggi istantanei peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="0933c-117">Total peer-to-peer IM messages</span></span>

<span data-ttu-id="0933c-118">In modo analogo, è possibile aprire il Rapporto voce e video peer-to-peer facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="0933c-118">Likewise, you can open the Peer-to-Peer Voice and Video Report by clicking any of these metrics:</span></span>

  - <span data-ttu-id="0933c-119">Totale sessioni audio peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="0933c-119">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="0933c-120">Totale minuti sessioni audio peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="0933c-120">Total peer-to-peer audio session minutes</span></span>

  - <span data-ttu-id="0933c-121">Totale sessioni audio peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="0933c-121">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="0933c-122">Totale minuti sessioni audio peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="0933c-122">Total peer-to-peer audio session minutes</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="0933c-123">Utilizzo ottimale del Rapporto riepilogativo attività peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="0933c-123">Making the Best Use of the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="0933c-p104">Nella parte inferiore del Rapporto riepilogativo attività peer-to-peer sono disponibili i totali per le metriche, come Totale sessioni di messaggistica istantanea peer-to-peer e Totale messaggi istantanei peer-to-peer. Questi valori offrono un rapido riepilogo delle informazioni dettagliate disponibili nel corpo del rapporto.</span><span class="sxs-lookup"><span data-stu-id="0933c-p104">At the bottom of the Peer-to-Peer Activity Summary Report you'll find totals for metrics such as Total peer-to-peer IM sessions and Total peer-to-peer IM messages. This provides a quick summary of the detailed information found in the body of the report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="0933c-126">Filtri</span><span class="sxs-lookup"><span data-stu-id="0933c-126">Filters</span></span>

<span data-ttu-id="0933c-p105">I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Il Rapporto riepilogativo attività peer-to-peer consente ad esempio di scegliere la modalità di raggruppamento dei dati. In questo caso le attività sono raggruppate per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="0933c-p105">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. For example, the Peer-to-Peer Activity Summary Report enables you to choose how data should be grouped. In this case, activity grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="0933c-130">Nella tabella seguente sono elencati i filtri che è possibile utilizzare con il Rapporto riepilogativo attività peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="0933c-130">The following table lists the filters that you can use with the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-filters"></a><span data-ttu-id="0933c-131">Filtri del Rapporto riepilogativo attività peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="0933c-131">Peer-to-Peer Activity Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0933c-132">Nome</span><span class="sxs-lookup"><span data-stu-id="0933c-132">Name</span></span></th>
<th><span data-ttu-id="0933c-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0933c-133">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0933c-134"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="0933c-134"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="0933c-p106">Data e ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, inserire sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="0933c-p106">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="0933c-137">17/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="0933c-137">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="0933c-p107">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="0933c-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0933c-140">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="0933c-140">7/17/12012</span></span></p>
<p><span data-ttu-id="0933c-141">Per visualizzare i dati in base alla settimana o al mese, immettere una data che rientra nella settimana o nel mese in base a cui deve essere effettuata la visualizzazione. Non è necessario immettere il primo giorno della settimana o del mese:</span><span class="sxs-lookup"><span data-stu-id="0933c-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0933c-142">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="0933c-142">7/13/2012</span></span></p>
<p><span data-ttu-id="0933c-143">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="0933c-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0933c-144"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="0933c-144"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="0933c-p108">Data e ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, inserire sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="0933c-p108">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="0933c-147">17/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="0933c-147">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="0933c-p109">Se non si specifica l'ora di fine, il rapporto termina automaticamente alla mezzanotte del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="0933c-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0933c-150">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="0933c-150">7/17/12012</span></span></p>
<p><span data-ttu-id="0933c-151">Per visualizzare i dati in base alla settimana o al mese, immettere una data che rientra nella settimana o nel mese in base a cui deve essere effettuata la visualizzazione. Non è necessario immettere il primo giorno della settimana o del mese:</span><span class="sxs-lookup"><span data-stu-id="0933c-151">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0933c-152">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="0933c-152">7/13/2012</span></span></p>
<p><span data-ttu-id="0933c-153">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="0933c-153">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0933c-154"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="0933c-154"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="0933c-p110">Selezionare uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="0933c-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0933c-157">Orario (è possibile visualizzare un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="0933c-157">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0933c-158">Giornaliero (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="0933c-158">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0933c-159">Settimanale (è possibile visualizzare un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="0933c-159">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0933c-160">Mensile (è possibile visualizzare un massimo di 12 mesi)</span><span class="sxs-lookup"><span data-stu-id="0933c-160">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="0933c-p111">Se le date di inizio e fine superano il numero massimo di valori consentiti per l'intervallo selezionato, verrà visualizzato solo il numero massimo di valori, a partire dalla data di inizio. Se ad esempio si seleziona l'intervallo Giornaliero con 07/08/2012 come data di inizio e 28/09/2012 come data di fine, verranno visualizzati i dati dalla mezzanotte del 7 agosto 2012 alla mezzanotte del 7 settembre 2012, ovvero i dati per un totale di 31 giorni.</span><span class="sxs-lookup"><span data-stu-id="0933c-p111">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/17/12012 and an end date of 2/28/2012, data is displayed for the days 8/7/12012 12:00 AM to 9/7/12012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="0933c-163">Metriche</span><span class="sxs-lookup"><span data-stu-id="0933c-163">Metrics</span></span>

<span data-ttu-id="0933c-164">Nella tabella seguente sono indicate le informazioni fornite nel Rapporto riepilogativo attività peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="0933c-164">The following table lists the information provided in the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-metrics"></a><span data-ttu-id="0933c-165">Metriche del Rapporto riepilogativo attività peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="0933c-165">Peer-to-Peer Activity Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0933c-166">Nome</span><span class="sxs-lookup"><span data-stu-id="0933c-166">Name</span></span></th>
<th><span data-ttu-id="0933c-167">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="0933c-167">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0933c-168">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0933c-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0933c-169"><strong>Orario</strong></span><span class="sxs-lookup"><span data-stu-id="0933c-169"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="0933c-170"><strong>Giornaliero</strong></span><span class="sxs-lookup"><span data-stu-id="0933c-170"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="0933c-171"><strong>Settimanale</strong></span><span class="sxs-lookup"><span data-stu-id="0933c-171"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="0933c-172"><strong>Mensile</strong></span><span class="sxs-lookup"><span data-stu-id="0933c-172"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="0933c-173">No</span><span class="sxs-lookup"><span data-stu-id="0933c-173">No</span></span></p></td>
<td><p><span data-ttu-id="0933c-p112">Indica l'intervallo di tempo selezionato sulla barra degli strumenti dei filtri. Ove applicabile, è possibile fare clic su un determinato intervallo di tempo per visualizzare informazioni dettagliate relative a tale intervallo. Se ad esempio si sta utilizzando l'intervallo giornaliero e si fa clic su 17/07/2012, verranno visualizzate le attività di registrazione degli utenti per tale data, suddivise per ore.</span><span class="sxs-lookup"><span data-stu-id="0933c-p112">Indicates the time interval that you selected on the filter toolbar. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/17/12012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0933c-177"><strong>Totale sessioni peer-to-peer</strong></span><span class="sxs-lookup"><span data-stu-id="0933c-177"><strong>Total peer-to-peer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0933c-178">No</span><span class="sxs-lookup"><span data-stu-id="0933c-178">No</span></span></p></td>
<td><p><span data-ttu-id="0933c-179">Numero totale di sessioni peer-to-peer condotte, indipendentemente dal tipo.</span><span class="sxs-lookup"><span data-stu-id="0933c-179">Total number of peer-to-peer sessions conducted, regardless of session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0933c-180"><strong>Totale sessioni di messaggistica istantanea peer-to-peer</strong></span><span class="sxs-lookup"><span data-stu-id="0933c-180"><strong>Total peer-to-peer IM sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0933c-181">No</span><span class="sxs-lookup"><span data-stu-id="0933c-181">No</span></span></p></td>
<td><p><span data-ttu-id="0933c-p113">Numero totale di sessioni di messaggistica istantanea condotte. Se si fa clic su questo elemento, verrà visualizzato il Rapporto di messaggistica istantanea peer-to-peer relativo al periodo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="0933c-p113">Total number of peer-to-peer instant messaging (IM) sessions. When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0933c-184"><strong>Totale messaggi istantanei peer-to-peer</strong></span><span class="sxs-lookup"><span data-stu-id="0933c-184"><strong>Total peer-to-peer IM messages</strong></span></span></p></td>
<td><p><span data-ttu-id="0933c-185">No</span><span class="sxs-lookup"><span data-stu-id="0933c-185">No</span></span></p></td>
<td><p><span data-ttu-id="0933c-p114">Numero totale di messaggi istantanei inviati in sessioni peer-to-peer. Se si fa clic su questo elemento, verrà visualizzato il Rapporto di messaggistica istantanea peer-to-peer relativo al periodo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="0933c-p114">Total number of instant messages sent in peer-to-peer sessions. When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0933c-188"><strong>Totale sessioni audio peer-to-peer audio</strong></span><span class="sxs-lookup"><span data-stu-id="0933c-188"><strong>Total peer-to-peer audio sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0933c-189">No</span><span class="sxs-lookup"><span data-stu-id="0933c-189">No</span></span></p></td>
<td><p><span data-ttu-id="0933c-p115">Numero totale di chiamate audio peer-to-peer. Se si fa clic su questo campo, verrà visualizzato il Rapporto voce e video peer-to-peer relativo al periodo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="0933c-p115">Total number of peer-to-peer audio calls. When you click this field, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0933c-192"><strong>Totale minuti sessioni audio peer-to-peer</strong></span><span class="sxs-lookup"><span data-stu-id="0933c-192"><strong>Total peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="0933c-193">No</span><span class="sxs-lookup"><span data-stu-id="0933c-193">No</span></span></p></td>
<td><p><span data-ttu-id="0933c-194">Quantità totale di tempo impiegato in sessioni audio peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="0933c-194">Total amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="0933c-195">Se si fa clic su questo elemento, verrà visualizzato il Rapporto di messaggistica istantanea peer-to-peer relativo al periodo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="0933c-195">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0933c-196"><strong>Media minuti sessioni audio peer-to-peer</strong></span><span class="sxs-lookup"><span data-stu-id="0933c-196"><strong>Average peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="0933c-197">No</span><span class="sxs-lookup"><span data-stu-id="0933c-197">No</span></span></p></td>
<td><p><span data-ttu-id="0933c-p117">Quantità media di tempo impiegato in sessioni audio peer-to-peer. Il valore viene calcolato dividendo il tempo totale per il numero totale delle sessioni audio.</span><span class="sxs-lookup"><span data-stu-id="0933c-p117">Average amount of time spent in peer-to-peer audio sessions. Calculated by dividing the total audio session time by the total number of audio sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0933c-200"><strong>Totale sessioni video peer-to-peer</strong></span><span class="sxs-lookup"><span data-stu-id="0933c-200"><strong>Total peer-to-peer video sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0933c-201">No</span><span class="sxs-lookup"><span data-stu-id="0933c-201">No</span></span></p></td>
<td><p><span data-ttu-id="0933c-p118">Numero totale di videochiamate peer-to-peer. Si noti che le sessioni video vengono conteggiate anche come sessioni audio. Ogni sessione video viene conteggiata come una sessione video e una sessione audio. Se si fa clic su questo elemento, verrà visualizzato il Rapporto di messaggistica istantanea peer-to-peer relativo al periodo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="0933c-p118">Total number of peer-to-peer video calls. Note that video sessions are also counted as audio sessions: each video session is counted as one video session and one audio session. When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0933c-205"><strong>Totale minuti sessioni video peer-to-peer</strong></span><span class="sxs-lookup"><span data-stu-id="0933c-205"><strong>Total peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="0933c-206">No</span><span class="sxs-lookup"><span data-stu-id="0933c-206">No</span></span></p></td>
<td><p><span data-ttu-id="0933c-p119">Quantità totale di tempo impiegato in sessioni video peer-to-peer. Se si fa clic su questo elemento, verrà visualizzato il Rapporto di messaggistica istantanea peer-to-peer relativo al periodo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="0933c-p119">Total amount of time spent in peer-to-peer video sessions. When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0933c-209"><strong>Media minuti sessioni video peer-to-peer</strong></span><span class="sxs-lookup"><span data-stu-id="0933c-209"><strong>Average peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="0933c-210">No</span><span class="sxs-lookup"><span data-stu-id="0933c-210">No</span></span></p></td>
<td><p><span data-ttu-id="0933c-p120">Quantità media di tempo impiegato in sessioni video peer-to-peer. Il valore viene calcolato dividendo il tempo totale per il numero totale delle sessioni video.</span><span class="sxs-lookup"><span data-stu-id="0933c-p120">Average amount of time spent in peer-to-peer video sessions. Calculated by dividing the total video session time by the total number of video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0933c-213"><strong>Totale sessioni di trasferimento di file peer-to-peer</strong></span><span class="sxs-lookup"><span data-stu-id="0933c-213"><strong>Total peer-to-peer file transfer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0933c-214">No</span><span class="sxs-lookup"><span data-stu-id="0933c-214">No</span></span></p></td>
<td><p><span data-ttu-id="0933c-215">Numero totale di sessioni peer-to-peer che includono trasferimenti di file.</span><span class="sxs-lookup"><span data-stu-id="0933c-215">Total number of peer-to-peer sessions that included file transfers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0933c-216"><strong>Totale sessioni di condivisione applicazioni peer-to-peer</strong></span><span class="sxs-lookup"><span data-stu-id="0933c-216"><strong>Total peer-to-peer application sharing sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0933c-217">No</span><span class="sxs-lookup"><span data-stu-id="0933c-217">No</span></span></p></td>
<td><p><span data-ttu-id="0933c-218">Numero totale di sessioni peer-to-peer che includono la condivisione di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="0933c-218">Total number of peer-to-peer sessions that included application sharing.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

