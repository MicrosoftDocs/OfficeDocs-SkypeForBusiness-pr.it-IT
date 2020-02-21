---
title: 'Lync Server 2013: rapporto voce e video peer-to-peer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Voice and Video Report
ms:assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615040(v=OCS.15)
ms:contentKeyID: 48185535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcb58becb1b495c16338ef9590ede8fb4005bc2d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a><span data-ttu-id="c5879-102">Rapporto voce e video peer-to-peer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5879-102">Peer-to-Peer Voice and Video Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5879-103">_**Ultimo argomento modificato:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="c5879-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="c5879-p101">Il Rapporto voce e video peer-to-peer consente di esaminare in modo dettagliato la distribuzione delle chiamate voce e video per un periodo di tempo specificato, ad esempio le chiamate per ora o per giorno. Il rapporto offre inoltre la possibilità di visualizzare tutte le chiamate voce e video effettuate oppure solo quelle riuscite o non riuscite. Le informazioni sulle chiamate nel rapporto sono suddivise nei raggruppamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5879-p101">The Peer-to-Peer Voice and Video Report provides a detailed look at the distribution of voice and video calls over a specified period of time (for example, calls per hour or calls per day). The report also gives you the option of viewing all the voice and video calls that were made, or of viewing only the successful or failed calls. The reports shows call information broken down into the following groupings:</span></span>

  - <span data-ttu-id="c5879-107">Chiamate per pool</span><span class="sxs-lookup"><span data-stu-id="c5879-107">Calls per pool</span></span>

  - <span data-ttu-id="c5879-108">Chiamate per tipo di chiamata (ad esempio, una chiamata Lync a Lync e un Lync a una persona sulla rete PSTN)</span><span class="sxs-lookup"><span data-stu-id="c5879-108">Calls per call type (for example, a Lync to Lync call vs. a Lync call to a person on the PSTN network)</span></span>

  - <span data-ttu-id="c5879-109">Chiamate per tipo di accesso (utenti connessi alla rete interna o alla rete esterna)</span><span class="sxs-lookup"><span data-stu-id="c5879-109">Calls per access type (users logged on to the internal network vs. users logged on to the external network)</span></span>

  - <span data-ttu-id="c5879-110">Chiamate per Mediation Server</span><span class="sxs-lookup"><span data-stu-id="c5879-110">Calls per Mediation Server</span></span>

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="c5879-111">Per accedere al rapporto voce e video peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="c5879-111">To access the peer-to-peer voice and video report</span></span>

<span data-ttu-id="c5879-112">L'unico modo per accedere al Rapporto voce e video peer-to-peer consiste nell'aprire il Rapporto riepilogativo attività peer-to-peer e fare clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5879-112">You can access the Peer-to-Peer Voice and Video Report only by opening the Peer-to-Peer Activity Summary Report and then clicking any of the following metrics:</span></span>

  - <span data-ttu-id="c5879-113">Totale sessioni audio peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="c5879-113">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="c5879-114">Totale minuti sessioni audio peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="c5879-114">Total peer-to-peer audio minutes</span></span>

  - <span data-ttu-id="c5879-115">Totale sessioni audio peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="c5879-115">Total peer-to-peer video sessions</span></span>

  - <span data-ttu-id="c5879-116">Totale minuti sessioni video peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="c5879-116">Total peer-to-peer video minutes</span></span>

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="c5879-117">Per utilizzare in modo ottimale il rapporto voce e video peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="c5879-117">To make the best use of the peer-to-peer voice and video report</span></span>

<span data-ttu-id="c5879-p102">È possibile filtrare il Rapporto voce e video peer-to-peer in vari modi. Le opzioni di filtro, tuttavia, sono nascoste dalla visualizzazione per impostazione predefinita. Per visualizzare le opzioni di filtro disponibili, fare clic sul pulsante \*\*Mostra/Nascondi parametri \*\*nell'angolo in alto a destra della finestra Rapporto.</span><span class="sxs-lookup"><span data-stu-id="c5879-p102">There are a number of ways you can filter the Peer-to-Peer Voice and Video Report. However, those filtering options are hidden from view by default. To view the filtering options available to you, click **Show/Hide Parameters** button in the upper-right corner of the Report window.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="c5879-121">Filtri</span><span class="sxs-lookup"><span data-stu-id="c5879-121">Filters</span></span>

<span data-ttu-id="c5879-p103">I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati. Nella tabella seguente sono elencati i filtri che è possibile utilizzare con il Rapporto voce e video peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="c5879-p103">Filters provide a way for you to return a more finely targeted set of data or to view the data in different ways. The following table lists the filters that you can use with the Peer-to-Peer Voice and Video Report.</span></span>

### <a name="peer-to-peer-voice-and-video-report-filters"></a><span data-ttu-id="c5879-124">Filtri per il rapporto voce e video peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="c5879-124">Peer-to-peer voice and video report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5879-125">Name</span><span class="sxs-lookup"><span data-stu-id="c5879-125">Name</span></span></th>
<th><span data-ttu-id="c5879-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c5879-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5879-127"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="c5879-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="c5879-p104">Data e ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, inserire sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="c5879-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="c5879-130">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="c5879-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c5879-p105">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="c5879-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c5879-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c5879-133">7/7/2012</span></span></p>
<p><span data-ttu-id="c5879-134">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="c5879-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c5879-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c5879-135">7/3/2012</span></span></p>
<p><span data-ttu-id="c5879-136">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="c5879-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5879-137"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="c5879-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="c5879-p106">Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="c5879-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="c5879-140">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c5879-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c5879-p107">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="c5879-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c5879-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c5879-143">7/7/2012</span></span></p>
<p><span data-ttu-id="c5879-144">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="c5879-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c5879-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c5879-145">7/3/2012</span></span></p>
<p><span data-ttu-id="c5879-146">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="c5879-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5879-147"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="c5879-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="c5879-p108">Selezionare uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5879-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c5879-150">Orario (è possibile visualizzare un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="c5879-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c5879-151">Giornaliero (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="c5879-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c5879-152">Settimanale (è possibile visualizzare un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="c5879-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c5879-153">Mensile (è possibile visualizzare un massimo di 12 mesi)</span><span class="sxs-lookup"><span data-stu-id="c5879-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="c5879-p109">Se per le date di inizio e di fine si immette un numero di valori superiore al massimo consentito per l'intervallo selezionato, verrà visualizzato solo il numero massimo di valori (a partire dalla data di inizio). Se ad esempio si seleziona l'intervallo Giornaliero con la data di inizio 07/08/2012 e la data di fine 28/09/2012, verranno visualizzati i dati relativi ai giorni da 07/08/2012 alle 00.00 a 07/09/2012 alle 00.00, ovvero per un totale di 31 giorni.</span><span class="sxs-lookup"><span data-stu-id="c5879-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5879-156"><strong>Tipo di supporto</strong></span><span class="sxs-lookup"><span data-stu-id="c5879-156"><strong>Media type</strong></span></span></p></td>
<td><p><span data-ttu-id="c5879-p110">Indica il tipo di supporto utilizzato nella sezione. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5879-p110">Indicates the type of media used in the session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c5879-159">Sia</span><span class="sxs-lookup"><span data-stu-id="c5879-159">Both</span></span></p></li>
<li><p><span data-ttu-id="c5879-160">Audio</span><span class="sxs-lookup"><span data-stu-id="c5879-160">Audio</span></span></p></li>
<li><p><span data-ttu-id="c5879-161">Video</span><span class="sxs-lookup"><span data-stu-id="c5879-161">Video</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5879-162"><strong>Disposizione chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="c5879-162"><strong>Call disposition</strong></span></span></p></td>
<td><p><span data-ttu-id="c5879-p111">Indica l'esito positivo o negativo della sezione. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5879-p111">Indicates the success or failure of the session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c5879-165">Tutti</span><span class="sxs-lookup"><span data-stu-id="c5879-165">[All]</span></span></p></li>
<li><p><span data-ttu-id="c5879-166">Chiamate riuscite</span><span class="sxs-lookup"><span data-stu-id="c5879-166">Success Calls</span></span></p></li>
<li><p><span data-ttu-id="c5879-167">Chiamate non riuscite</span><span class="sxs-lookup"><span data-stu-id="c5879-167">Failed Calls</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5879-168"><strong>Rapporto di</strong></span><span class="sxs-lookup"><span data-stu-id="c5879-168"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="c5879-p112">Indica i valori da utilizzare nel rapporto. Selezionare una delle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5879-p112">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c5879-171">Numero di sessioni</span><span class="sxs-lookup"><span data-stu-id="c5879-171">Session count</span></span></p></li>
<li><p><span data-ttu-id="c5879-172">Minuti chiamata</span><span class="sxs-lookup"><span data-stu-id="c5879-172">Call minutes</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="c5879-173">Metriche per le attività voce e video peer-to-peer per pool</span><span class="sxs-lookup"><span data-stu-id="c5879-173">Metrics for peer-to-peer voice and video activity by Pool</span></span>

<span data-ttu-id="c5879-174">Nella tabella seguente sono elencate le informazioni fornite nel Rapporto voce e video peer-to-peer per ogni pool.</span><span class="sxs-lookup"><span data-stu-id="c5879-174">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each pool.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="c5879-175">Metriche per le attività voce e video peer-to-peer per pool</span><span class="sxs-lookup"><span data-stu-id="c5879-175">Metrics for peer-to-peer voice and video activity by pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5879-176">Name</span><span class="sxs-lookup"><span data-stu-id="c5879-176">Name</span></span></th>
<th><span data-ttu-id="c5879-177">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="c5879-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c5879-178">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c5879-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5879-179"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="c5879-179"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="c5879-180">No</span><span class="sxs-lookup"><span data-stu-id="c5879-180">No</span></span></p></td>
<td><p><span data-ttu-id="c5879-181">Nome del pool di registrazione o del server perimetrale utilizzato per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c5879-181">Name of the Registrar pool or Edge Server used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5879-182"><strong>Data/ora</strong></span><span class="sxs-lookup"><span data-stu-id="c5879-182"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="c5879-183">No</span><span class="sxs-lookup"><span data-stu-id="c5879-183">No</span></span></p></td>
<td><p><span data-ttu-id="c5879-184">Data e ora in cui è stata effettuata la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c5879-184">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5879-185"><strong>Totale</strong></span><span class="sxs-lookup"><span data-stu-id="c5879-185"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="c5879-186">No</span><span class="sxs-lookup"><span data-stu-id="c5879-186">No</span></span></p></td>
<td><p><span data-ttu-id="c5879-187">Numero totale di sessioni o di messaggi.</span><span class="sxs-lookup"><span data-stu-id="c5879-187">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="c5879-188">Metriche per le attività voce e video peer-to-peer per tipo di chiamata</span><span class="sxs-lookup"><span data-stu-id="c5879-188">Metrics for peer-to-peer voice and video activity by call type</span></span>

<span data-ttu-id="c5879-189">Nella tabella seguente sono elencate le informazioni fornite nel Rapporto voce e video peer-to-peer per ogni tipo di chiamata effettuata.</span><span class="sxs-lookup"><span data-stu-id="c5879-189">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each type of call that was made.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="c5879-190">Metriche per le attività voce e video peer-to-peer per tipo di chiamata</span><span class="sxs-lookup"><span data-stu-id="c5879-190">Metrics for peer-to-peer voice and video activity by call type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5879-191">Name</span><span class="sxs-lookup"><span data-stu-id="c5879-191">Name</span></span></th>
<th><span data-ttu-id="c5879-192">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="c5879-192">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c5879-193">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c5879-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5879-194"><strong>Tipo di chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="c5879-194"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="c5879-195">No</span><span class="sxs-lookup"><span data-stu-id="c5879-195">No</span></span></p></td>
<td><p><span data-ttu-id="c5879-p113">Indica il tipo di chiamata che è stata effettuata. I valori sono uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5879-p113">Indicates the type of call that was made. Values are one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c5879-198">Da UC a UC</span><span class="sxs-lookup"><span data-stu-id="c5879-198">UC-to-UC</span></span></p></li>
<li><p><span data-ttu-id="c5879-199">Da UC a PSTN</span><span class="sxs-lookup"><span data-stu-id="c5879-199">UC-to-PSTN</span></span></p></li>
<li><p><span data-ttu-id="c5879-200">PSTN-to-UC</span><span class="sxs-lookup"><span data-stu-id="c5879-200">PSTN-to-UC</span></span></p></li>
<li><p><span data-ttu-id="c5879-201">PSTN-PSTN</span><span class="sxs-lookup"><span data-stu-id="c5879-201">PSTN-to-PSTN</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5879-202"><strong>Data/ora</strong></span><span class="sxs-lookup"><span data-stu-id="c5879-202"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="c5879-203">No</span><span class="sxs-lookup"><span data-stu-id="c5879-203">No</span></span></p></td>
<td><p><span data-ttu-id="c5879-204">Data e ora in cui è stata effettuata la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c5879-204">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5879-205"><strong>Totale</strong></span><span class="sxs-lookup"><span data-stu-id="c5879-205"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="c5879-206">No</span><span class="sxs-lookup"><span data-stu-id="c5879-206">No</span></span></p></td>
<td><p><span data-ttu-id="c5879-207">Numero totale di sessioni o di messaggi.</span><span class="sxs-lookup"><span data-stu-id="c5879-207">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="c5879-208">Metriche per le attività voce e video peer-to-peer per tipo di accesso</span><span class="sxs-lookup"><span data-stu-id="c5879-208">Metrics for peer-to-peer voice and video activity by access type</span></span>

<span data-ttu-id="c5879-209">Nella tabella seguente sono elencate le informazioni fornite nel Rapporto voce e video peer-to-peer per ogni tipo di accesso di rete.</span><span class="sxs-lookup"><span data-stu-id="c5879-209">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each network access type.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="c5879-210">Metriche per le attività voce e video peer-to-peer per tipo di accesso</span><span class="sxs-lookup"><span data-stu-id="c5879-210">Metrics for peer-to-peer voice and video activity by access type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5879-211">Name</span><span class="sxs-lookup"><span data-stu-id="c5879-211">Name</span></span></th>
<th><span data-ttu-id="c5879-212">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="c5879-212">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c5879-213">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c5879-213">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5879-214"><strong>Tipo di attività</strong></span><span class="sxs-lookup"><span data-stu-id="c5879-214"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="c5879-215">No</span><span class="sxs-lookup"><span data-stu-id="c5879-215">No</span></span></p></td>
<td><p><span data-ttu-id="c5879-p114">Indica se al momento dell'esecuzione della chiamata i client sono connessi alla rete interna o a quella esterna. I valori sono in genere i seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5879-p114">Indicates whether the clients were logged on to the internal network or the external network when the call was placed. Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c5879-218">Interna</span><span class="sxs-lookup"><span data-stu-id="c5879-218">Internal</span></span></p></li>
<li><p><span data-ttu-id="c5879-219">Esterna</span><span class="sxs-lookup"><span data-stu-id="c5879-219">External</span></span></p></li>
<li><p><span data-ttu-id="c5879-220">Mista</span><span class="sxs-lookup"><span data-stu-id="c5879-220">Mixed</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5879-221"><strong>Data/ora</strong></span><span class="sxs-lookup"><span data-stu-id="c5879-221"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="c5879-222">No</span><span class="sxs-lookup"><span data-stu-id="c5879-222">No</span></span></p></td>
<td><p><span data-ttu-id="c5879-223">Data e ora in cui è stata effettuata la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c5879-223">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5879-224"><strong>Totale</strong></span><span class="sxs-lookup"><span data-stu-id="c5879-224"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="c5879-225">No</span><span class="sxs-lookup"><span data-stu-id="c5879-225">No</span></span></p></td>
<td><p><span data-ttu-id="c5879-226">Numero totale di sessioni o di messaggi.</span><span class="sxs-lookup"><span data-stu-id="c5879-226">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="c5879-227">Metriche per le attività voce e video peer-to-peer per Mediation Server</span><span class="sxs-lookup"><span data-stu-id="c5879-227">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<span data-ttu-id="c5879-228">Nella tabella seguente sono elencate le informazioni fornite nel rapporto voce e video peer-to-peer per ogni Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="c5879-228">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each Mediation Server.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="c5879-229">Metriche per le attività voce e video peer-to-peer per Mediation Server</span><span class="sxs-lookup"><span data-stu-id="c5879-229">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5879-230">Name</span><span class="sxs-lookup"><span data-stu-id="c5879-230">Name</span></span></th>
<th><span data-ttu-id="c5879-231">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="c5879-231">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c5879-232">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c5879-232">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5879-233"><strong>Mediation Server</strong></span><span class="sxs-lookup"><span data-stu-id="c5879-233"><strong>Mediation Server</strong></span></span></p></td>
<td><p><span data-ttu-id="c5879-234">No</span><span class="sxs-lookup"><span data-stu-id="c5879-234">No</span></span></p></td>
<td><p><span data-ttu-id="c5879-235">Nome del Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="c5879-235">Name of the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5879-236"><strong>Data/ora</strong></span><span class="sxs-lookup"><span data-stu-id="c5879-236"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="c5879-237">No</span><span class="sxs-lookup"><span data-stu-id="c5879-237">No</span></span></p></td>
<td><p><span data-ttu-id="c5879-238">Data e ora in cui è stata effettuata la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c5879-238">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5879-239"><strong>Totale</strong></span><span class="sxs-lookup"><span data-stu-id="c5879-239"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="c5879-240">No</span><span class="sxs-lookup"><span data-stu-id="c5879-240">No</span></span></p></td>
<td><p><span data-ttu-id="c5879-241">Numero totale di sessioni o di messaggi.</span><span class="sxs-lookup"><span data-stu-id="c5879-241">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

