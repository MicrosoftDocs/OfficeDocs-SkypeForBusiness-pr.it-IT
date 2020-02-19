---
title: 'Lync Server 2013: utilizzo del dashboard di monitoraggio'
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
ms.openlocfilehash: 4b3fb33c8cef77139ec1f2e6ddd13da3847c1ec9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42117309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-monitoring-dashboard-in-lync-server-2013"></a><span data-ttu-id="0f07f-102">Utilizzo del dashboard di monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f07f-102">Using the Monitoring Dashboard in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f07f-103">_**Ultimo argomento modificato:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="0f07f-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="0f07f-104">Il dashboard di monitoraggio fornisce agli amministratori una breve panoramica dell'integrità del sistema e dell'utilizzo del sistema di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0f07f-104">The Monitoring Dashboard provides administrators with a quick overview of their Microsoft Lync Server 2013 system health and system usage.</span></span> <span data-ttu-id="0f07f-105">Il dashboard è stato creato per mostrare una visualizzazione aggregata delle metriche dei sistemi chiave e per farlo visualizzando:</span><span class="sxs-lookup"><span data-stu-id="0f07f-105">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>

  - <span data-ttu-id="0f07f-106">Totali per il giorno corrente.</span><span class="sxs-lookup"><span data-stu-id="0f07f-106">Totals for the current day.</span></span> <span data-ttu-id="0f07f-107">Si noti che i valori visualizzati per il giorno corrente rappresentano i dati che sono stati registrati dalla mezzanotte fino all'ora corrente (in base all'ora locale del server di report).</span><span class="sxs-lookup"><span data-stu-id="0f07f-107">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="0f07f-108">Questo significa che in genere i dati vengono visualizzati per un giorno parziale e non per un periodo di 24 ore.</span><span class="sxs-lookup"><span data-stu-id="0f07f-108">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="0f07f-109">Ad esempio, se l'ora locale del server è 8:00, è possibile visualizzare un valore di otto ore perché sono presenti otto ore tra la mezzanotte e la data corrente di 8:00.</span><span class="sxs-lookup"><span data-stu-id="0f07f-109">For example, if the local time of the server is 8:00 AM, you see eight hours’ worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>

  - <span data-ttu-id="0f07f-110">Totali per la settimana e totali di tendenza per le ultime sei settimane.</span><span class="sxs-lookup"><span data-stu-id="0f07f-110">Totals for the week, and trend totals for the past six weeks.</span></span>

  - <span data-ttu-id="0f07f-111">Totali per il mese e totali di tendenza negli ultimi sei mesi (solo per l'utilizzo del sistema).</span><span class="sxs-lookup"><span data-stu-id="0f07f-111">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>

<span data-ttu-id="0f07f-112">Si noti che è possibile utilizzare il cmdlet [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) per restituire l'URL utilizzato per l'accesso ai report di monitoraggio di Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="0f07f-112">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) cmdlet to return the URL used for accessing Lync Server 2013 Monitoring Reports:</span></span>

    Get-CsReportingConfiguration

<span data-ttu-id="0f07f-113">Per impostazione predefinita, il dashboard di monitoraggio Visualizza i dati per le metriche seguenti per la settimana corrente (e i totali di tendenza per le sei settimane precedenti):</span><span class="sxs-lookup"><span data-stu-id="0f07f-113">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>

<div>

## <a name="system-usage-metrics"></a><span data-ttu-id="0f07f-114">Metriche di utilizzo del sistema</span><span class="sxs-lookup"><span data-stu-id="0f07f-114">System Usage Metrics</span></span>

<span data-ttu-id="0f07f-115">**Registrazione**</span><span class="sxs-lookup"><span data-stu-id="0f07f-115">**Registration**</span></span>

  - <span data-ttu-id="0f07f-116">Accessi utente univoci</span><span class="sxs-lookup"><span data-stu-id="0f07f-116">Unique user logons</span></span>

<span data-ttu-id="0f07f-117">**Peer-to-peer**</span><span class="sxs-lookup"><span data-stu-id="0f07f-117">**Peer-to-peer**</span></span>

  - <span data-ttu-id="0f07f-118">Totale sessioni</span><span class="sxs-lookup"><span data-stu-id="0f07f-118">Total sessions</span></span>

  - <span data-ttu-id="0f07f-119">Sessioni di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="0f07f-119">IM sessions</span></span>

  - <span data-ttu-id="0f07f-120">Sessioni audio</span><span class="sxs-lookup"><span data-stu-id="0f07f-120">Audio sessions</span></span>

  - <span data-ttu-id="0f07f-121">Sessioni video</span><span class="sxs-lookup"><span data-stu-id="0f07f-121">Video sessions</span></span>

  - <span data-ttu-id="0f07f-122">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="0f07f-122">Application sharing</span></span>

  - <span data-ttu-id="0f07f-123">Totale minuti di sessioni audio</span><span class="sxs-lookup"><span data-stu-id="0f07f-123">Total audio session minutes</span></span>

  - <span data-ttu-id="0f07f-124">Minuti di sessione media. audio</span><span class="sxs-lookup"><span data-stu-id="0f07f-124">Avg. audio session minutes</span></span>

<span data-ttu-id="0f07f-125">**Conferenza**</span><span class="sxs-lookup"><span data-stu-id="0f07f-125">**Conference**</span></span>

  - <span data-ttu-id="0f07f-126">Totale conferenze</span><span class="sxs-lookup"><span data-stu-id="0f07f-126">Total conferences</span></span>

  - <span data-ttu-id="0f07f-127">Conferenze di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="0f07f-127">IM conferences</span></span>

  - <span data-ttu-id="0f07f-128">Conferenze A/V</span><span class="sxs-lookup"><span data-stu-id="0f07f-128">A/V conferences</span></span>

  - <span data-ttu-id="0f07f-129">Conferenze di condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="0f07f-129">Application sharing conferences</span></span>

  - <span data-ttu-id="0f07f-130">Conferenze Web</span><span class="sxs-lookup"><span data-stu-id="0f07f-130">Web conferences</span></span>

  - <span data-ttu-id="0f07f-131">Totale organizzatori</span><span class="sxs-lookup"><span data-stu-id="0f07f-131">Total organizers</span></span>

  - <span data-ttu-id="0f07f-132">Totale minuti di conferenza audio/video</span><span class="sxs-lookup"><span data-stu-id="0f07f-132">Total A/V conference minutes</span></span>

  - <span data-ttu-id="0f07f-133">AVG. Minuti di conferenza A/V</span><span class="sxs-lookup"><span data-stu-id="0f07f-133">Avg. A/V conference minutes</span></span>

  - <span data-ttu-id="0f07f-134">Totale conferenze PSTN</span><span class="sxs-lookup"><span data-stu-id="0f07f-134">Total PSTN conferences</span></span>

  - <span data-ttu-id="0f07f-135">Totale partecipanti PSTN</span><span class="sxs-lookup"><span data-stu-id="0f07f-135">Total PSTN participants</span></span>

  - <span data-ttu-id="0f07f-136">Totale minuti partecipante PSTN</span><span class="sxs-lookup"><span data-stu-id="0f07f-136">Total PSTN participant minutes</span></span>

<span data-ttu-id="0f07f-137">Oltre alle metriche di utilizzo del sistema, le metriche seguenti visualizzano il totale per il giorno corrente e i sei giorni precedenti (se si seleziona **visualizzazione settimanale**) o per la settimana corrente e le sei settimane precedenti se si seleziona **visualizzazione mensile**.</span><span class="sxs-lookup"><span data-stu-id="0f07f-137">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>

</div>

<div>

## <a name="per-user-call-diagnostics"></a><span data-ttu-id="0f07f-138">Diagnostica delle chiamate per utente</span><span class="sxs-lookup"><span data-stu-id="0f07f-138">Per-User Call Diagnostics</span></span>

<span data-ttu-id="0f07f-139">**Utenti con errori di chiamata**</span><span class="sxs-lookup"><span data-stu-id="0f07f-139">**Users with call failures**</span></span>

  - <span data-ttu-id="0f07f-140">Totale utenti con errori di chiamata</span><span class="sxs-lookup"><span data-stu-id="0f07f-140">Total users with call failures</span></span>

  - <span data-ttu-id="0f07f-141">Organizzatori della conferenza con errori di chiamata</span><span class="sxs-lookup"><span data-stu-id="0f07f-141">Conference organizers with call failures</span></span>

<span data-ttu-id="0f07f-142">**Utenti con chiamate di qualità scadente**</span><span class="sxs-lookup"><span data-stu-id="0f07f-142">**Users with poor quality calls**</span></span>

  - <span data-ttu-id="0f07f-143">Totale utenti con chiamate di qualità scadente</span><span class="sxs-lookup"><span data-stu-id="0f07f-143">Total users with poor quality calls</span></span>

</div>

<div>

## <a name="call-diagnostics"></a><span data-ttu-id="0f07f-144">Diagnostica chiamate</span><span class="sxs-lookup"><span data-stu-id="0f07f-144">Call Diagnostics</span></span>

<span data-ttu-id="0f07f-145">Peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="0f07f-145">Peer-to-peer</span></span>

  - <span data-ttu-id="0f07f-146">Totale errori</span><span class="sxs-lookup"><span data-stu-id="0f07f-146">Total failures</span></span>

  - <span data-ttu-id="0f07f-147">Frequenza di errore complessiva</span><span class="sxs-lookup"><span data-stu-id="0f07f-147">Overall failure rate</span></span>

  - <span data-ttu-id="0f07f-148">Frequenza errori di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="0f07f-148">IM failure rate</span></span>

  - <span data-ttu-id="0f07f-149">Frequenza errori audio</span><span class="sxs-lookup"><span data-stu-id="0f07f-149">Audio failure rate</span></span>

  - <span data-ttu-id="0f07f-150">Frequenza errori di condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="0f07f-150">Application sharing failure rate</span></span>

<span data-ttu-id="0f07f-151">Conferenza</span><span class="sxs-lookup"><span data-stu-id="0f07f-151">Conference</span></span>

  - <span data-ttu-id="0f07f-152">Totale errori</span><span class="sxs-lookup"><span data-stu-id="0f07f-152">Total failures</span></span>

  - <span data-ttu-id="0f07f-153">Frequenza di errore complessiva</span><span class="sxs-lookup"><span data-stu-id="0f07f-153">Overall failure rate</span></span>

  - <span data-ttu-id="0f07f-154">Frequenza errori di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="0f07f-154">IM failure rate</span></span>

  - <span data-ttu-id="0f07f-155">Frequenza errori di A/V</span><span class="sxs-lookup"><span data-stu-id="0f07f-155">A/V failure rate</span></span>

  - <span data-ttu-id="0f07f-156">Frequenza errori di condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="0f07f-156">Application sharing failure rate</span></span>

<span data-ttu-id="0f07f-157">Primi cinque server da sessioni non riuscite</span><span class="sxs-lookup"><span data-stu-id="0f07f-157">Top five servers by failed sessions</span></span>

</div>

<div>

## <a name="media-quality-diagnostics"></a><span data-ttu-id="0f07f-158">Diagnostica qualità multimediale</span><span class="sxs-lookup"><span data-stu-id="0f07f-158">Media Quality Diagnostics</span></span>

<span data-ttu-id="0f07f-159">Peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="0f07f-159">Peer-to-peer</span></span>

  - <span data-ttu-id="0f07f-160">Chiamate totali di qualità scadente</span><span class="sxs-lookup"><span data-stu-id="0f07f-160">Total poor quality calls</span></span>

  - <span data-ttu-id="0f07f-161">Percentuale di chiamata di qualità scadente</span><span class="sxs-lookup"><span data-stu-id="0f07f-161">Poor quality call percentage</span></span>

  - <span data-ttu-id="0f07f-162">Chiamate PSTN con qualità scadente</span><span class="sxs-lookup"><span data-stu-id="0f07f-162">PSTN calls with poor quality</span></span>

<span data-ttu-id="0f07f-163">Conferenza</span><span class="sxs-lookup"><span data-stu-id="0f07f-163">Conference</span></span>

  - <span data-ttu-id="0f07f-164">Chiamate totali di qualità scadente</span><span class="sxs-lookup"><span data-stu-id="0f07f-164">Total poor quality calls</span></span>

  - <span data-ttu-id="0f07f-165">Percentuale di chiamata di qualità scadente</span><span class="sxs-lookup"><span data-stu-id="0f07f-165">Poor quality call percentage</span></span>

  - <span data-ttu-id="0f07f-166">Chiamate PSTN con qualità scadente</span><span class="sxs-lookup"><span data-stu-id="0f07f-166">PSTN calls with poor quality</span></span>

<span data-ttu-id="0f07f-167">Top Worst Servers dalla percentuale di chiamata di qualità scadente</span><span class="sxs-lookup"><span data-stu-id="0f07f-167">Top worst servers by poor quality call percentage</span></span>

</div>

<div>

## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="0f07f-168">Utilizzo del dashboard di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="0f07f-168">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="0f07f-169">Come indicato, per i totali predefiniti vengono visualizzati per la settimana corrente e i valori di tendenza vengono visualizzati per le ultime sei settimane.</span><span class="sxs-lookup"><span data-stu-id="0f07f-169">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks.</span></span> <span data-ttu-id="0f07f-170">Se si preferisce visualizzare i totali per il mese corrente (così come i valori di tendenza negli ultimi sei mesi), fare clic sul collegamento **Visualizza mensilmente** nell'angolo in alto a destra del dashboard.</span><span class="sxs-lookup"><span data-stu-id="0f07f-170">If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard.</span></span> <span data-ttu-id="0f07f-171">Se si decide di visualizzare i totali mensili, il testo del collegamento verrà modificato in **visualizzazione settimanale**.</span><span class="sxs-lookup"><span data-stu-id="0f07f-171">If you decide to view monthly totals, the link text will change to **Weekly View**.</span></span> <span data-ttu-id="0f07f-172">È possibile tornare alla visualizzazione settimanale facendo clic su quel collegamento.</span><span class="sxs-lookup"><span data-stu-id="0f07f-172">You can switch back to the weekly view by clicking that link.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="0f07f-173">Il dashboard di monitoraggio consente di limitare l'esame dei totali per la settimana (o il mese) corrente e i valori di tendenza per le ultime sei settimane (o mesi).</span><span class="sxs-lookup"><span data-stu-id="0f07f-173">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months).</span></span> <span data-ttu-id="0f07f-174">Non è possibile modificare queste date e ore.</span><span class="sxs-lookup"><span data-stu-id="0f07f-174">You cannot change these dates and times.</span></span> <span data-ttu-id="0f07f-175">Ad esempio, non è possibile utilizzare il dashboard per visualizzare i totali dei rapporti per il periodo di tempo che inizia nove mesi fa.</span><span class="sxs-lookup"><span data-stu-id="0f07f-175">For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span>



</div>

<span data-ttu-id="0f07f-176">I valori visualizzati nelle colonne **this week**, **this month**o **Today** sono collegati a informazioni più dettagliate sull'elemento.</span><span class="sxs-lookup"><span data-stu-id="0f07f-176">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item.</span></span> <span data-ttu-id="0f07f-177">Tenere presente che il nome della colonna e i valori visualizzati in tale colonna spesso differiscono a seconda della metrica scelta e a seconda che sia stata selezionata la visualizzazione settimanale o la visualizzazione mensile.</span><span class="sxs-lookup"><span data-stu-id="0f07f-177">Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view.</span></span> <span data-ttu-id="0f07f-178">Ad esempio, se si fa clic sui totali visualizzati per la metrica degli **accessi univoci** per l'utente, verrà visualizzato il **rapporto di registrazione degli utenti** per il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="0f07f-178">For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period.</span></span> <span data-ttu-id="0f07f-179">È possibile tornare al dashboard di monitoraggio in qualsiasi momento facendo clic su **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="0f07f-179">You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="0f07f-180">È inoltre possibile accedere alla Home page dei report di Monitoring Server facendo clic sul collegamento <STRONG>report</STRONG> nell'angolo in alto a destra del dashboard.</span><span class="sxs-lookup"><span data-stu-id="0f07f-180">You can also access the Monitoring Server Reports home page by clicking the <STRONG>Reports</STRONG> link in the upper right corner of the Dashboard.</span></span>



</div>

<span data-ttu-id="0f07f-181">La colonna **trend** Visualizza un grafico a linee semplice che mostra i totali per le ultime sei settimane (o, a seconda della metrica e dell'intervallo di tempo, negli ultimi sei giorni o negli ultimi sei mesi).</span><span class="sxs-lookup"><span data-stu-id="0f07f-181">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months).</span></span> <span data-ttu-id="0f07f-182">Questi grafici a linee semplici visualizzano un punto dati senza etichetta per ogni periodo di tempo, ad esempio un punto dati senza etichetta per ognuna delle ultime sei settimane.</span><span class="sxs-lookup"><span data-stu-id="0f07f-182">These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks).</span></span> <span data-ttu-id="0f07f-183">Tuttavia, è possibile recuperare i valori effettivi per questi grafici tenendo il puntatore del mouse sul grafico.</span><span class="sxs-lookup"><span data-stu-id="0f07f-183">However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph.</span></span> <span data-ttu-id="0f07f-184">In questo caso, una descrizione comando Visualizza i valori massimi e minimi del grafico.</span><span class="sxs-lookup"><span data-stu-id="0f07f-184">In that case, a tooltip shows you the maximum and minimum values in the graph.</span></span>

</div>

<div>

## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="0f07f-185">Esportazione di dati dal dashboard di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="0f07f-185">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="0f07f-186">Nel dashboard di monitoraggio sono disponibili diversi modi per esportare la visualizzazione dashboard corrente.</span><span class="sxs-lookup"><span data-stu-id="0f07f-186">The Monitoring Dashboard provides a number of ways to export the current dashboard view.</span></span> <span data-ttu-id="0f07f-187">Sulla barra degli strumenti del dashboard verrà visualizzata un'icona che assomiglia a un disco floppy con una freccia verde associata.</span><span class="sxs-lookup"><span data-stu-id="0f07f-187">On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it.</span></span> <span data-ttu-id="0f07f-188">Se si fa clic su questa icona, verrà visualizzato un elenco a discesa che fornisce i seguenti formati di esportazione dei dati:</span><span class="sxs-lookup"><span data-stu-id="0f07f-188">If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>

  - <span data-ttu-id="0f07f-189">File XML con dati del rapporto</span><span class="sxs-lookup"><span data-stu-id="0f07f-189">XML file with report data</span></span>

  - <span data-ttu-id="0f07f-190">CSV (delimitato da virgole)</span><span class="sxs-lookup"><span data-stu-id="0f07f-190">CSV (comma delimited)</span></span>

  - <span data-ttu-id="0f07f-191">PDF</span><span class="sxs-lookup"><span data-stu-id="0f07f-191">PDF</span></span>

  - <span data-ttu-id="0f07f-192">MHTML (archivio Web)</span><span class="sxs-lookup"><span data-stu-id="0f07f-192">MHTML (web archive)</span></span>

  - <span data-ttu-id="0f07f-193">Excel</span><span class="sxs-lookup"><span data-stu-id="0f07f-193">Excel</span></span>

  - <span data-ttu-id="0f07f-194">File TIFF</span><span class="sxs-lookup"><span data-stu-id="0f07f-194">TIFF file</span></span>

  - <span data-ttu-id="0f07f-195">Word</span><span class="sxs-lookup"><span data-stu-id="0f07f-195">Word</span></span>

<span data-ttu-id="0f07f-196">Per esportare la visualizzazione del dashboard corrente e i relativi valori, fare clic sull'opzione di esportazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="0f07f-196">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="0f07f-197">Lync Server 2013 genera un report nel formato specificato e quindi fornisce la possibilità di aprire il report o di salvarlo.</span><span class="sxs-lookup"><span data-stu-id="0f07f-197">Lync Server 2013 generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="0f07f-198">Si noti che, per impostazione predefinita, Lync Server titola il **dashboard di monitoraggio** dei report e lo salva nella cartella Downloads.</span><span class="sxs-lookup"><span data-stu-id="0f07f-198">Note that, by default, Lync Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="0f07f-199">Per assegnare un nome diverso al report o archiviarlo in una cartella diversa, fare clic sulla freccia accanto al pulsante **Salva** e quindi fare clic su **Salva come**.</span><span class="sxs-lookup"><span data-stu-id="0f07f-199">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="0f07f-200">Se si sta bene con il nome del **dashboard di monitoraggio** e con il report salvato nella cartella Downloads, è possibile fare clic sul pulsante **Salva** .</span><span class="sxs-lookup"><span data-stu-id="0f07f-200">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>

<span data-ttu-id="0f07f-201">È possibile che, quando si tenta di esportare i dati del dashboard, venga visualizzata una finestra di dialogo per l' **avviso di sicurezza** insieme al messaggio "le impostazioni correnti non consentono il download di questo file".</span><span class="sxs-lookup"><span data-stu-id="0f07f-201">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded."</span></span> <span data-ttu-id="0f07f-202">Se ciò accade, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f07f-202">If that occurs, do the following:</span></span>

  - <span data-ttu-id="0f07f-203">In Internet Explorer selezionare **Opzioni Internet**.</span><span class="sxs-lookup"><span data-stu-id="0f07f-203">In Internet Explorer, select **Internet Options**.</span></span>

  - <span data-ttu-id="0f07f-204">Nella scheda **sicurezza** della finestra di dialogo **Opzioni Internet** fare clic su **siti attendibili** e quindi su **siti**.</span><span class="sxs-lookup"><span data-stu-id="0f07f-204">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>

  - <span data-ttu-id="0f07f-205">Nella finestra di dialogo **siti attendibili** fare clic su **Aggiungi** per aggiungere il Lync Server 2013 che esegue i report di Lync Server 2013 agli insiemi di siti Web attendibili.</span><span class="sxs-lookup"><span data-stu-id="0f07f-205">In the **Trusted sites** dialog box, click **Add** to add the Lync Server 2013 that is running Lync Server 2013 Reports to the collections of trusted websites.</span></span>

  - <span data-ttu-id="0f07f-206">Fare clic su **Chiudi** e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f07f-206">Click **Close** and then click **OK**.</span></span>

<span data-ttu-id="0f07f-207">Sarà quindi necessario aggiornare il dashboard di monitoraggio prima che le modifiche abbiano effetto.</span><span class="sxs-lookup"><span data-stu-id="0f07f-207">You will then need to refresh the Monitoring Dashboard before the changes take effect.</span></span> <span data-ttu-id="0f07f-208">A tale scopo, premere F5 o fare clic sull'icona di **aggiornamento** sulla barra degli strumenti del dashboard.</span><span class="sxs-lookup"><span data-stu-id="0f07f-208">To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar.</span></span> <span data-ttu-id="0f07f-209">(L'icona di **aggiornamento** è un cerchio con una coppia di frecce verdi all'interno).</span><span class="sxs-lookup"><span data-stu-id="0f07f-209">(The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>

<span data-ttu-id="0f07f-210">È inoltre possibile creare un foglio di calcolo di Excel che include feed di dati in tempo reale, che include collegamenti ai dati più recenti del dashboard di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="0f07f-210">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data.</span></span> <span data-ttu-id="0f07f-211">Per creare un file dei feed di dati dal vivo, fare clic sull'icona arancione **Esporta nell'alimentazione dei dati** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="0f07f-211">To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>

<span data-ttu-id="0f07f-212">Se si preferisce stampare il dashboard corrente, fare clic sull'icona della stampante sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="0f07f-212">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

