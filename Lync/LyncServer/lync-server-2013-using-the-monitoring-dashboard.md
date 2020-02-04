---
title: 'Lync Server 2013: uso del dashboard di monitoraggio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Monitoring Dashboard
ms:assetid: e00e5783-116f-481f-ad17-3af847d6769a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721905(v=OCS.15)
ms:contentKeyID: 49733839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 929d0fbc650a7b067d86738e5ded176a15c511f4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743876"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-monitoring-dashboard-in-lync-server-2013"></a><span data-ttu-id="74945-102">Uso del dashboard di monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74945-102">Using the Monitoring Dashboard in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74945-103">_**Argomento Ultima modifica:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="74945-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="74945-104">Il dashboard di monitoraggio offre agli amministratori una breve panoramica dell'integrità del sistema e dell'utilizzo del sistema di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="74945-104">The Monitoring Dashboard provides administrators with a quick overview of their Microsoft Lync Server 2013 system health and system usage.</span></span> <span data-ttu-id="74945-105">Il dashboard è progettato per mostrare una visualizzazione aggregata delle metriche di sistema chiave e per farlo visualizzando:</span><span class="sxs-lookup"><span data-stu-id="74945-105">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>

  - <span data-ttu-id="74945-106">Totali per il giorno corrente.</span><span class="sxs-lookup"><span data-stu-id="74945-106">Totals for the current day.</span></span> <span data-ttu-id="74945-107">Tieni presente che i valori visualizzati per il giorno corrente rappresentano i dati registrati dalla mezzanotte fino all'ora corrente (in base all'ora locale del server di report).</span><span class="sxs-lookup"><span data-stu-id="74945-107">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="74945-108">Ciò significa che in genere verranno visualizzati i dati per un giorno parziale e non per un periodo di 24 ore.</span><span class="sxs-lookup"><span data-stu-id="74945-108">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="74945-109">Ad esempio, se l'ora locale del server è 8:00 AM, viene visualizzato un valore di otto ore per i dati perché sono presenti otto ore tra mezzanotte e l'ora corrente di 8:00 AM.</span><span class="sxs-lookup"><span data-stu-id="74945-109">For example, if the local time of the server is 8:00 AM, you see eight hours’ worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>

  - <span data-ttu-id="74945-110">Totali per la settimana e totali delle tendenze per le ultime sei settimane.</span><span class="sxs-lookup"><span data-stu-id="74945-110">Totals for the week, and trend totals for the past six weeks.</span></span>

  - <span data-ttu-id="74945-111">Totali per il mese e totali di tendenza per gli ultimi sei mesi (solo per l'uso del sistema).</span><span class="sxs-lookup"><span data-stu-id="74945-111">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>

<span data-ttu-id="74945-112">Tieni presente che puoi usare il cmdlet [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) per restituire l'URL usato per accedere ai report di monitoraggio di Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="74945-112">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) cmdlet to return the URL used for accessing Lync Server 2013 Monitoring Reports:</span></span>

    Get-CsReportingConfiguration

<span data-ttu-id="74945-113">Per impostazione predefinita, il dashboard di monitoraggio Mostra i dati per le metriche seguenti per la settimana corrente (e i totali delle tendenze per le sei settimane precedenti):</span><span class="sxs-lookup"><span data-stu-id="74945-113">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>

<div>

## <a name="system-usage-metrics"></a><span data-ttu-id="74945-114">Metriche per l'uso del sistema</span><span class="sxs-lookup"><span data-stu-id="74945-114">System Usage Metrics</span></span>

<span data-ttu-id="74945-115">**Registrazione**</span><span class="sxs-lookup"><span data-stu-id="74945-115">**Registration**</span></span>

  - <span data-ttu-id="74945-116">Accessi utente univoci</span><span class="sxs-lookup"><span data-stu-id="74945-116">Unique user logons</span></span>

<span data-ttu-id="74945-117">**Peer-to-peer**</span><span class="sxs-lookup"><span data-stu-id="74945-117">**Peer-to-peer**</span></span>

  - <span data-ttu-id="74945-118">Totale sessioni</span><span class="sxs-lookup"><span data-stu-id="74945-118">Total sessions</span></span>

  - <span data-ttu-id="74945-119">Sessioni di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="74945-119">IM sessions</span></span>

  - <span data-ttu-id="74945-120">Sessioni audio</span><span class="sxs-lookup"><span data-stu-id="74945-120">Audio sessions</span></span>

  - <span data-ttu-id="74945-121">Sessioni video</span><span class="sxs-lookup"><span data-stu-id="74945-121">Video sessions</span></span>

  - <span data-ttu-id="74945-122">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="74945-122">Application sharing</span></span>

  - <span data-ttu-id="74945-123">Minuti totali della sessione audio</span><span class="sxs-lookup"><span data-stu-id="74945-123">Total audio session minutes</span></span>

  - <span data-ttu-id="74945-124">Minuti media della sessione audio</span><span class="sxs-lookup"><span data-stu-id="74945-124">Avg. audio session minutes</span></span>

<span data-ttu-id="74945-125">**Conferenza**</span><span class="sxs-lookup"><span data-stu-id="74945-125">**Conference**</span></span>

  - <span data-ttu-id="74945-126">Totale conferenze</span><span class="sxs-lookup"><span data-stu-id="74945-126">Total conferences</span></span>

  - <span data-ttu-id="74945-127">Conferenze di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="74945-127">IM conferences</span></span>

  - <span data-ttu-id="74945-128">Conferenze A/V</span><span class="sxs-lookup"><span data-stu-id="74945-128">A/V conferences</span></span>

  - <span data-ttu-id="74945-129">Conferenze di condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="74945-129">Application sharing conferences</span></span>

  - <span data-ttu-id="74945-130">Conferenze Web</span><span class="sxs-lookup"><span data-stu-id="74945-130">Web conferences</span></span>

  - <span data-ttu-id="74945-131">Totale organizzatori</span><span class="sxs-lookup"><span data-stu-id="74945-131">Total organizers</span></span>

  - <span data-ttu-id="74945-132">Totale minuti di conferenza A/V</span><span class="sxs-lookup"><span data-stu-id="74945-132">Total A/V conference minutes</span></span>

  - <span data-ttu-id="74945-133">AVG. Minuti della conferenza A/V</span><span class="sxs-lookup"><span data-stu-id="74945-133">Avg. A/V conference minutes</span></span>

  - <span data-ttu-id="74945-134">Totale conferenze PSTN</span><span class="sxs-lookup"><span data-stu-id="74945-134">Total PSTN conferences</span></span>

  - <span data-ttu-id="74945-135">Totale partecipanti PSTN</span><span class="sxs-lookup"><span data-stu-id="74945-135">Total PSTN participants</span></span>

  - <span data-ttu-id="74945-136">Minuti totali dei partecipanti PSTN</span><span class="sxs-lookup"><span data-stu-id="74945-136">Total PSTN participant minutes</span></span>

<span data-ttu-id="74945-137">Oltre alle metriche per l'uso del sistema, le metriche seguenti visualizzano Total per il giorno corrente e per i sei giorni precedenti (se si seleziona la **visualizzazione settimanale**) o per la settimana corrente e per le ultime sei settimane se si seleziona **visualizzazione mensile**.</span><span class="sxs-lookup"><span data-stu-id="74945-137">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>

</div>

<div>

## <a name="per-user-call-diagnostics"></a><span data-ttu-id="74945-138">Diagnostica delle chiamate per utente</span><span class="sxs-lookup"><span data-stu-id="74945-138">Per-User Call Diagnostics</span></span>

<span data-ttu-id="74945-139">**Utenti con errori di chiamata**</span><span class="sxs-lookup"><span data-stu-id="74945-139">**Users with call failures**</span></span>

  - <span data-ttu-id="74945-140">Totale utenti con errori di chiamata</span><span class="sxs-lookup"><span data-stu-id="74945-140">Total users with call failures</span></span>

  - <span data-ttu-id="74945-141">Organizzatori di conferenze con errori di chiamata</span><span class="sxs-lookup"><span data-stu-id="74945-141">Conference organizers with call failures</span></span>

<span data-ttu-id="74945-142">**Utenti con chiamate di qualità scadente**</span><span class="sxs-lookup"><span data-stu-id="74945-142">**Users with poor quality calls**</span></span>

  - <span data-ttu-id="74945-143">Totale utenti con chiamate di qualità scadente</span><span class="sxs-lookup"><span data-stu-id="74945-143">Total users with poor quality calls</span></span>

</div>

<div>

## <a name="call-diagnostics"></a><span data-ttu-id="74945-144">Diagnostica chiamate</span><span class="sxs-lookup"><span data-stu-id="74945-144">Call Diagnostics</span></span>

<span data-ttu-id="74945-145">Peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="74945-145">Peer-to-peer</span></span>

  - <span data-ttu-id="74945-146">Totale errori</span><span class="sxs-lookup"><span data-stu-id="74945-146">Total failures</span></span>

  - <span data-ttu-id="74945-147">Tasso di errore complessivo</span><span class="sxs-lookup"><span data-stu-id="74945-147">Overall failure rate</span></span>

  - <span data-ttu-id="74945-148">Tasso di errore di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="74945-148">IM failure rate</span></span>

  - <span data-ttu-id="74945-149">Tasso di errore audio</span><span class="sxs-lookup"><span data-stu-id="74945-149">Audio failure rate</span></span>

  - <span data-ttu-id="74945-150">Tasso di errore di condivisione delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="74945-150">Application sharing failure rate</span></span>

<span data-ttu-id="74945-151">Conferenza</span><span class="sxs-lookup"><span data-stu-id="74945-151">Conference</span></span>

  - <span data-ttu-id="74945-152">Totale errori</span><span class="sxs-lookup"><span data-stu-id="74945-152">Total failures</span></span>

  - <span data-ttu-id="74945-153">Tasso di errore complessivo</span><span class="sxs-lookup"><span data-stu-id="74945-153">Overall failure rate</span></span>

  - <span data-ttu-id="74945-154">Tasso di errore di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="74945-154">IM failure rate</span></span>

  - <span data-ttu-id="74945-155">Tasso di errore A/V</span><span class="sxs-lookup"><span data-stu-id="74945-155">A/V failure rate</span></span>

  - <span data-ttu-id="74945-156">Tasso di errore di condivisione delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="74945-156">Application sharing failure rate</span></span>

<span data-ttu-id="74945-157">Primi cinque server per le sessioni non riuscite</span><span class="sxs-lookup"><span data-stu-id="74945-157">Top five servers by failed sessions</span></span>

</div>

<div>

## <a name="media-quality-diagnostics"></a><span data-ttu-id="74945-158">Diagnostica qualità multimediale</span><span class="sxs-lookup"><span data-stu-id="74945-158">Media Quality Diagnostics</span></span>

<span data-ttu-id="74945-159">Peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="74945-159">Peer-to-peer</span></span>

  - <span data-ttu-id="74945-160">Totale chiamate di qualità scadente</span><span class="sxs-lookup"><span data-stu-id="74945-160">Total poor quality calls</span></span>

  - <span data-ttu-id="74945-161">Percentuale di chiamata di qualità scadente</span><span class="sxs-lookup"><span data-stu-id="74945-161">Poor quality call percentage</span></span>

  - <span data-ttu-id="74945-162">Chiamate PSTN con qualità scadente</span><span class="sxs-lookup"><span data-stu-id="74945-162">PSTN calls with poor quality</span></span>

<span data-ttu-id="74945-163">Conferenza</span><span class="sxs-lookup"><span data-stu-id="74945-163">Conference</span></span>

  - <span data-ttu-id="74945-164">Totale chiamate di qualità scadente</span><span class="sxs-lookup"><span data-stu-id="74945-164">Total poor quality calls</span></span>

  - <span data-ttu-id="74945-165">Percentuale di chiamata di qualità scadente</span><span class="sxs-lookup"><span data-stu-id="74945-165">Poor quality call percentage</span></span>

  - <span data-ttu-id="74945-166">Chiamate PSTN con qualità scadente</span><span class="sxs-lookup"><span data-stu-id="74945-166">PSTN calls with poor quality</span></span>

<span data-ttu-id="74945-167">Top server peggiore per percentuale di chiamata di qualità scadente</span><span class="sxs-lookup"><span data-stu-id="74945-167">Top worst servers by poor quality call percentage</span></span>

</div>

<div>

## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="74945-168">Uso del dashboard di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="74945-168">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="74945-169">Come indicato, per i totali predefiniti vengono visualizzati per la settimana corrente e i valori di tendenza sono visualizzati per le ultime sei settimane.</span><span class="sxs-lookup"><span data-stu-id="74945-169">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks.</span></span> <span data-ttu-id="74945-170">Se si preferisce visualizzare i totali per il mese corrente (nonché i valori di tendenza per gli ultimi sei mesi), fare clic sul collegamento **visualizzazione mensile** nell'angolo in alto a destra del dashboard.</span><span class="sxs-lookup"><span data-stu-id="74945-170">If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard.</span></span> <span data-ttu-id="74945-171">Se si decide di visualizzare i totali mensili, il testo del collegamento cambierà in **visualizzazione settimanale**.</span><span class="sxs-lookup"><span data-stu-id="74945-171">If you decide to view monthly totals, the link text will change to **Weekly View**.</span></span> <span data-ttu-id="74945-172">È possibile tornare alla visualizzazione settimanale facendo clic sul collegamento.</span><span class="sxs-lookup"><span data-stu-id="74945-172">You can switch back to the weekly view by clicking that link.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="74945-173">Il dashboard di monitoraggio limita la visualizzazione dei totali per la settimana (o il mese) corrente e i valori di tendenza per le ultime sei settimane (o mesi).</span><span class="sxs-lookup"><span data-stu-id="74945-173">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months).</span></span> <span data-ttu-id="74945-174">Non è possibile modificare le date e le ore.</span><span class="sxs-lookup"><span data-stu-id="74945-174">You cannot change these dates and times.</span></span> <span data-ttu-id="74945-175">Ad esempio, non è possibile usare il dashboard per visualizzare i totali del report per il periodo di tempo che inizia nove mesi fa.</span><span class="sxs-lookup"><span data-stu-id="74945-175">For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span>



</div>

<span data-ttu-id="74945-176">I valori visualizzati nelle colonne **questa settimana**, **questo mese**o **oggi** possono essere collegati a informazioni più dettagliate sull'elemento.</span><span class="sxs-lookup"><span data-stu-id="74945-176">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item.</span></span> <span data-ttu-id="74945-177">Tieni presente che il nome della colonna e i valori visualizzati in tale colonna saranno spesso diversi a seconda della metrica scelta e a seconda che tu abbia selezionato la visualizzazione settimanale o la visualizzazione mensile.</span><span class="sxs-lookup"><span data-stu-id="74945-177">Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view.</span></span> <span data-ttu-id="74945-178">Ad esempio, se si fa clic sui totali visualizzati per la metrica degli **accessi utente univoci** verrà visualizzato il **rapporto di registrazione utente** per il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="74945-178">For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period.</span></span> <span data-ttu-id="74945-179">È possibile tornare al dashboard di monitoraggio in qualsiasi momento facendo clic su **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="74945-179">You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="74945-180">È anche possibile accedere alla Home page dei report del server di monitoraggio facendo clic sul collegamento <STRONG>report</STRONG> nell'angolo in alto a destra del dashboard.</span><span class="sxs-lookup"><span data-stu-id="74945-180">You can also access the Monitoring Server Reports home page by clicking the <STRONG>Reports</STRONG> link in the upper right corner of the Dashboard.</span></span>



</div>

<span data-ttu-id="74945-181">Nella colonna **tendenza** viene visualizzato un grafico a linee semplice che mostra i totali per le ultime sei settimane (o, a seconda delle metriche e dell'intervallo di tempo, degli ultimi sei giorni o degli ultimi sei mesi).</span><span class="sxs-lookup"><span data-stu-id="74945-181">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months).</span></span> <span data-ttu-id="74945-182">Questi grafici a linee semplici visualizzano un punto dati senza etichetta per ogni periodo di tempo, ad esempio un punto dati senza etichetta per ognuna delle ultime sei settimane.</span><span class="sxs-lookup"><span data-stu-id="74945-182">These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks).</span></span> <span data-ttu-id="74945-183">Puoi tuttavia recuperare i valori effettivi per questi grafici tenendo il puntatore del mouse sul grafico.</span><span class="sxs-lookup"><span data-stu-id="74945-183">However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph.</span></span> <span data-ttu-id="74945-184">In questo caso, una descrizione comando Mostra i valori minimo e massimo nel grafico.</span><span class="sxs-lookup"><span data-stu-id="74945-184">In that case, a tooltip shows you the maximum and minimum values in the graph.</span></span>

</div>

<div>

## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="74945-185">Esportazione di dati dal dashboard di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="74945-185">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="74945-186">Il dashboard di monitoraggio offre diversi modi per esportare la visualizzazione dashboard corrente.</span><span class="sxs-lookup"><span data-stu-id="74945-186">The Monitoring Dashboard provides a number of ways to export the current dashboard view.</span></span> <span data-ttu-id="74945-187">Sulla barra degli strumenti del dashboard verrà visualizzata un'icona che ha l'aspetto di un disco floppy con una freccia verde collegata.</span><span class="sxs-lookup"><span data-stu-id="74945-187">On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it.</span></span> <span data-ttu-id="74945-188">Se si fa clic su questa icona, verrà visualizzato un elenco a discesa che fornisce i formati di esportazione dei dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="74945-188">If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>

  - <span data-ttu-id="74945-189">File XML con i dati del report</span><span class="sxs-lookup"><span data-stu-id="74945-189">XML file with report data</span></span>

  - <span data-ttu-id="74945-190">CSV (delimitato da virgola)</span><span class="sxs-lookup"><span data-stu-id="74945-190">CSV (comma delimited)</span></span>

  - <span data-ttu-id="74945-191">PDF</span><span class="sxs-lookup"><span data-stu-id="74945-191">PDF</span></span>

  - <span data-ttu-id="74945-192">MHTML (archivio Web)</span><span class="sxs-lookup"><span data-stu-id="74945-192">MHTML (web archive)</span></span>

  - <span data-ttu-id="74945-193">Excel</span><span class="sxs-lookup"><span data-stu-id="74945-193">Excel</span></span>

  - <span data-ttu-id="74945-194">File TIFF</span><span class="sxs-lookup"><span data-stu-id="74945-194">TIFF file</span></span>

  - <span data-ttu-id="74945-195">Word</span><span class="sxs-lookup"><span data-stu-id="74945-195">Word</span></span>

<span data-ttu-id="74945-196">Per esportare la visualizzazione dashboard corrente (e i relativi valori), fare clic sull'opzione di esportazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="74945-196">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="74945-197">Lync Server 2013 genera un report nel formato specificato e quindi consente di aprire il report o di salvarlo.</span><span class="sxs-lookup"><span data-stu-id="74945-197">Lync Server 2013 generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="74945-198">Tieni presente che, per impostazione predefinita, Lync Server titoli il **dashboard di monitoraggio** dei report e lo salva nella cartella download.</span><span class="sxs-lookup"><span data-stu-id="74945-198">Note that, by default, Lync Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="74945-199">Per assegnare un nome diverso al report o archiviarlo in un'altra cartella, fare clic sulla freccia accanto al pulsante **Salva** e quindi fare clic su **Salva come**.</span><span class="sxs-lookup"><span data-stu-id="74945-199">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="74945-200">Se si sta bene con il **dashboard di monitoraggio** dei nomi e quando il report viene salvato nella cartella download, è sufficiente fare clic sul pulsante **Salva** .</span><span class="sxs-lookup"><span data-stu-id="74945-200">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>

<span data-ttu-id="74945-201">Quando si prova ad esportare i dati del dashboard, è possibile che venga visualizzata una finestra di dialogo di **avviso di sicurezza** insieme al messaggio "le impostazioni correnti non consentono il download del file".</span><span class="sxs-lookup"><span data-stu-id="74945-201">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded."</span></span> <span data-ttu-id="74945-202">Se si verifica questo problema, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="74945-202">If that occurs, do the following:</span></span>

  - <span data-ttu-id="74945-203">In Internet Explorer selezionare **Opzioni Internet**.</span><span class="sxs-lookup"><span data-stu-id="74945-203">In Internet Explorer, select **Internet Options**.</span></span>

  - <span data-ttu-id="74945-204">Nella finestra di dialogo **Opzioni Internet** fare clic su **siti attendibili** nella scheda **sicurezza** e quindi fare clic su **siti**.</span><span class="sxs-lookup"><span data-stu-id="74945-204">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>

  - <span data-ttu-id="74945-205">Nella finestra di dialogo **siti attendibili** fare clic su **Aggiungi** per aggiungere il Lync Server 2013 che sta usando i report di Lync Server 2013 per le raccolte di siti Web attendibili.</span><span class="sxs-lookup"><span data-stu-id="74945-205">In the **Trusted sites** dialog box, click **Add** to add the Lync Server 2013 that is running Lync Server 2013 Reports to the collections of trusted websites.</span></span>

  - <span data-ttu-id="74945-206">Fare clic su **Chiudi** e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="74945-206">Click **Close** and then click **OK**.</span></span>

<span data-ttu-id="74945-207">Sarà quindi necessario aggiornare il dashboard di monitoraggio prima che le modifiche abbiano effetto.</span><span class="sxs-lookup"><span data-stu-id="74945-207">You will then need to refresh the Monitoring Dashboard before the changes take effect.</span></span> <span data-ttu-id="74945-208">A questo scopo, premi F5 o fai clic sull'icona **Aggiorna** nella barra degli strumenti del dashboard.</span><span class="sxs-lookup"><span data-stu-id="74945-208">To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar.</span></span> <span data-ttu-id="74945-209">L'icona di **aggiornamento** è un cerchio con una coppia di frecce verdi.</span><span class="sxs-lookup"><span data-stu-id="74945-209">(The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>

<span data-ttu-id="74945-210">È anche possibile creare un foglio di calcolo di Excel che include feed di dati dinamici, che include collegamenti ai dati più recenti del dashboard di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="74945-210">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data.</span></span> <span data-ttu-id="74945-211">Per creare un file di feed di dati in tempo reale, fare clic sull'icona arancione **Esporta in feed di dati** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="74945-211">To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>

<span data-ttu-id="74945-212">Se si preferisce stampare il dashboard corrente, fare clic sull'icona della stampante sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="74945-212">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

