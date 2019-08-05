---
title: Uso del dashboard di monitoraggio in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e00e5783-116f-481f-ad17-3af847d6769a
description: 'Riepilogo: informazioni sul dashboard di monitoraggio in Skype for Business Server.'
ms.openlocfilehash: 0ca85bff7cfcad7f3b64a4b0f5b92a22299e5719
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188762"
---
# <a name="using-the-monitoring-dashboard-in-skype-for-business-server"></a><span data-ttu-id="106a1-103">Uso del dashboard di monitoraggio in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="106a1-103">Using the Monitoring Dashboard in Skype for Business Server</span></span>
 
<span data-ttu-id="106a1-104">**Riepilogo:** Informazioni sul dashboard di monitoraggio in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="106a1-104">**Summary:** Learn about the Monitoring Dashboard in Skype for Business Server.</span></span>
  
<span data-ttu-id="106a1-105">Il dashboard di monitoraggio offre agli amministratori una rapida panoramica dell'integrità del sistema e dell'uso del sistema Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="106a1-105">The Monitoring Dashboard provides administrators with a quick overview of their Skype for Business Server system health and system usage.</span></span> <span data-ttu-id="106a1-106">Il dashboard è progettato per mostrare una visualizzazione aggregata delle metriche di sistema chiave e per farlo visualizzando:</span><span class="sxs-lookup"><span data-stu-id="106a1-106">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>
  
- <span data-ttu-id="106a1-107">Totali per il giorno corrente.</span><span class="sxs-lookup"><span data-stu-id="106a1-107">Totals for the current day.</span></span> <span data-ttu-id="106a1-108">Tieni presente che i valori visualizzati per il giorno corrente rappresentano i dati registrati dalla mezzanotte fino all'ora corrente (in base all'ora locale del server di report).</span><span class="sxs-lookup"><span data-stu-id="106a1-108">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="106a1-109">Ciò significa che in genere verranno visualizzati i dati per un giorno parziale e non per un periodo di 24 ore.</span><span class="sxs-lookup"><span data-stu-id="106a1-109">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="106a1-110">Ad esempio, se l'ora locale del server è 8:00 AM, viene visualizzato un valore di otto ore per i dati perché sono presenti otto ore tra mezzanotte e l'ora corrente di 8:00 AM.</span><span class="sxs-lookup"><span data-stu-id="106a1-110">For example, if the local time of the server is 8:00 AM, you see eight hours' worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>
    
- <span data-ttu-id="106a1-111">Totali per la settimana e totali delle tendenze per le ultime sei settimane.</span><span class="sxs-lookup"><span data-stu-id="106a1-111">Totals for the week, and trend totals for the past six weeks.</span></span>
    
- <span data-ttu-id="106a1-112">Totali per il mese e totali di tendenza per gli ultimi sei mesi (solo per l'uso del sistema).</span><span class="sxs-lookup"><span data-stu-id="106a1-112">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>
    
<span data-ttu-id="106a1-113">Tieni presente che puoi usare il cmdlet [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) per restituire l'URL usato per accedere ai report di monitoraggio di Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="106a1-113">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) cmdlet to return the URL used for accessing Skype for Business Server Monitoring Reports:</span></span>
  
```
Get-CsReportingConfiguration
```

<span data-ttu-id="106a1-114">Per impostazione predefinita, il dashboard di monitoraggio Mostra i dati per le metriche seguenti per la settimana corrente (e i totali delle tendenze per le sei settimane precedenti):</span><span class="sxs-lookup"><span data-stu-id="106a1-114">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>
  
## <a name="system-usage-metrics"></a><span data-ttu-id="106a1-115">Metriche per l'uso del sistema</span><span class="sxs-lookup"><span data-stu-id="106a1-115">System Usage Metrics</span></span>

 <span data-ttu-id="106a1-116">**Registrazione**</span><span class="sxs-lookup"><span data-stu-id="106a1-116">**Registration**</span></span>
  
- <span data-ttu-id="106a1-117">Accessi utente univoci</span><span class="sxs-lookup"><span data-stu-id="106a1-117">Unique user logons</span></span>
    
  <span data-ttu-id="106a1-118">**Peer-to-peer**</span><span class="sxs-lookup"><span data-stu-id="106a1-118">**Peer-to-peer**</span></span>
  
- <span data-ttu-id="106a1-119">Totale sessioni</span><span class="sxs-lookup"><span data-stu-id="106a1-119">Total sessions</span></span>
    
- <span data-ttu-id="106a1-120">Sessioni di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="106a1-120">IM sessions</span></span>
    
- <span data-ttu-id="106a1-121">Sessioni audio</span><span class="sxs-lookup"><span data-stu-id="106a1-121">Audio sessions</span></span>
    
- <span data-ttu-id="106a1-122">Sessioni video</span><span class="sxs-lookup"><span data-stu-id="106a1-122">Video sessions</span></span>
    
- <span data-ttu-id="106a1-123">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="106a1-123">Application sharing</span></span>
    
- <span data-ttu-id="106a1-124">Minuti totali della sessione audio</span><span class="sxs-lookup"><span data-stu-id="106a1-124">Total audio session minutes</span></span>
    
- <span data-ttu-id="106a1-125">Minuti media della sessione audio</span><span class="sxs-lookup"><span data-stu-id="106a1-125">Avg. audio session minutes</span></span>
    
  <span data-ttu-id="106a1-126">**Conferenza**</span><span class="sxs-lookup"><span data-stu-id="106a1-126">**Conference**</span></span>
  
- <span data-ttu-id="106a1-127">Totale conferenze</span><span class="sxs-lookup"><span data-stu-id="106a1-127">Total conferences</span></span>
    
- <span data-ttu-id="106a1-128">Conferenze di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="106a1-128">IM conferences</span></span>
    
- <span data-ttu-id="106a1-129">Conferenze A/V</span><span class="sxs-lookup"><span data-stu-id="106a1-129">A/V conferences</span></span>
    
- <span data-ttu-id="106a1-130">Conferenze di condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="106a1-130">Application sharing conferences</span></span>
    
- <span data-ttu-id="106a1-131">Conferenze Web</span><span class="sxs-lookup"><span data-stu-id="106a1-131">Web conferences</span></span>
    
- <span data-ttu-id="106a1-132">Totale organizzatori</span><span class="sxs-lookup"><span data-stu-id="106a1-132">Total organizers</span></span>
    
- <span data-ttu-id="106a1-133">Totale minuti di conferenza A/V</span><span class="sxs-lookup"><span data-stu-id="106a1-133">Total A/V conference minutes</span></span>
    
- <span data-ttu-id="106a1-134">AVG. Minuti della conferenza A/V</span><span class="sxs-lookup"><span data-stu-id="106a1-134">Avg. A/V conference minutes</span></span>
    
- <span data-ttu-id="106a1-135">Totale conferenze PSTN</span><span class="sxs-lookup"><span data-stu-id="106a1-135">Total PSTN conferences</span></span>
    
- <span data-ttu-id="106a1-136">Totale partecipanti PSTN</span><span class="sxs-lookup"><span data-stu-id="106a1-136">Total PSTN participants</span></span>
    
- <span data-ttu-id="106a1-137">Minuti totali dei partecipanti PSTN</span><span class="sxs-lookup"><span data-stu-id="106a1-137">Total PSTN participant minutes</span></span>
    
<span data-ttu-id="106a1-138">Oltre alle metriche per l'uso del sistema, le metriche seguenti visualizzano Total per il giorno corrente e per i sei giorni precedenti (se si seleziona la **visualizzazione settimanale**) o per la settimana corrente e per le ultime sei settimane se si seleziona **visualizzazione mensile**.</span><span class="sxs-lookup"><span data-stu-id="106a1-138">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>
  
## <a name="per-user-call-diagnostics"></a><span data-ttu-id="106a1-139">Diagnostica delle chiamate per utente</span><span class="sxs-lookup"><span data-stu-id="106a1-139">Per-User Call Diagnostics</span></span>

 <span data-ttu-id="106a1-140">**Utenti con errori di chiamata**</span><span class="sxs-lookup"><span data-stu-id="106a1-140">**Users with call failures**</span></span>
  
- <span data-ttu-id="106a1-141">Totale utenti con errori di chiamata</span><span class="sxs-lookup"><span data-stu-id="106a1-141">Total users with call failures</span></span>
    
- <span data-ttu-id="106a1-142">Organizzatori di conferenze con errori di chiamata</span><span class="sxs-lookup"><span data-stu-id="106a1-142">Conference organizers with call failures</span></span>
    
  <span data-ttu-id="106a1-143">**Utenti con chiamate di qualità scadente**</span><span class="sxs-lookup"><span data-stu-id="106a1-143">**Users with poor quality calls**</span></span>
  
- <span data-ttu-id="106a1-144">Totale utenti con chiamate di qualità scadente</span><span class="sxs-lookup"><span data-stu-id="106a1-144">Total users with poor quality calls</span></span>
    
## <a name="call-diagnostics"></a><span data-ttu-id="106a1-145">Diagnostica chiamate</span><span class="sxs-lookup"><span data-stu-id="106a1-145">Call Diagnostics</span></span>

<span data-ttu-id="106a1-146">Peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="106a1-146">Peer-to-peer</span></span>
  
- <span data-ttu-id="106a1-147">Totale errori</span><span class="sxs-lookup"><span data-stu-id="106a1-147">Total failures</span></span>
    
- <span data-ttu-id="106a1-148">Tasso di errore complessivo</span><span class="sxs-lookup"><span data-stu-id="106a1-148">Overall failure rate</span></span>
    
- <span data-ttu-id="106a1-149">Tasso di errore di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="106a1-149">IM failure rate</span></span>
    
- <span data-ttu-id="106a1-150">Tasso di errore audio</span><span class="sxs-lookup"><span data-stu-id="106a1-150">Audio failure rate</span></span>
    
- <span data-ttu-id="106a1-151">Tasso di errore di condivisione delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="106a1-151">Application sharing failure rate</span></span>
    
<span data-ttu-id="106a1-152">Conferenza</span><span class="sxs-lookup"><span data-stu-id="106a1-152">Conference</span></span>
  
- <span data-ttu-id="106a1-153">Totale errori</span><span class="sxs-lookup"><span data-stu-id="106a1-153">Total failures</span></span>
    
- <span data-ttu-id="106a1-154">Tasso di errore complessivo</span><span class="sxs-lookup"><span data-stu-id="106a1-154">Overall failure rate</span></span>
    
- <span data-ttu-id="106a1-155">Tasso di errore di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="106a1-155">IM failure rate</span></span>
    
- <span data-ttu-id="106a1-156">Tasso di errore A/V</span><span class="sxs-lookup"><span data-stu-id="106a1-156">A/V failure rate</span></span>
    
- <span data-ttu-id="106a1-157">Tasso di errore di condivisione delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="106a1-157">Application sharing failure rate</span></span>
    
<span data-ttu-id="106a1-158">Primi cinque server per le sessioni non riuscite</span><span class="sxs-lookup"><span data-stu-id="106a1-158">Top five servers by failed sessions</span></span>
  
## <a name="media-quality-diagnostics"></a><span data-ttu-id="106a1-159">Diagnostica qualità multimediale</span><span class="sxs-lookup"><span data-stu-id="106a1-159">Media Quality Diagnostics</span></span>

<span data-ttu-id="106a1-160">Peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="106a1-160">Peer-to-peer</span></span>
  
- <span data-ttu-id="106a1-161">Totale chiamate di qualità scadente</span><span class="sxs-lookup"><span data-stu-id="106a1-161">Total poor quality calls</span></span>
    
- <span data-ttu-id="106a1-162">Percentuale di chiamata di qualità scadente</span><span class="sxs-lookup"><span data-stu-id="106a1-162">Poor quality call percentage</span></span>
    
- <span data-ttu-id="106a1-163">Chiamate PSTN con qualità scadente</span><span class="sxs-lookup"><span data-stu-id="106a1-163">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="106a1-164">Conferenza</span><span class="sxs-lookup"><span data-stu-id="106a1-164">Conference</span></span>
  
- <span data-ttu-id="106a1-165">Totale chiamate di qualità scadente</span><span class="sxs-lookup"><span data-stu-id="106a1-165">Total poor quality calls</span></span>
    
- <span data-ttu-id="106a1-166">Percentuale di chiamata di qualità scadente</span><span class="sxs-lookup"><span data-stu-id="106a1-166">Poor quality call percentage</span></span>
    
- <span data-ttu-id="106a1-167">Chiamate PSTN con qualità scadente</span><span class="sxs-lookup"><span data-stu-id="106a1-167">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="106a1-168">Top server peggiore per percentuale di chiamata di qualità scadente</span><span class="sxs-lookup"><span data-stu-id="106a1-168">Top worst servers by poor quality call percentage</span></span>
  
## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="106a1-169">Uso del dashboard di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="106a1-169">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="106a1-170">Come indicato, per i totali predefiniti vengono visualizzati per la settimana corrente e i valori di tendenza sono visualizzati per le ultime sei settimane.</span><span class="sxs-lookup"><span data-stu-id="106a1-170">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks.</span></span> <span data-ttu-id="106a1-171">Se si preferisce visualizzare i totali per il mese corrente (nonché i valori di tendenza per gli ultimi sei mesi), fare clic sul collegamento **visualizzazione mensile** nell'angolo in alto a destra del dashboard.</span><span class="sxs-lookup"><span data-stu-id="106a1-171">If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard.</span></span> <span data-ttu-id="106a1-172">Se si decide di visualizzare i totali mensili, il testo del collegamento cambierà in **visualizzazione settimanale**.</span><span class="sxs-lookup"><span data-stu-id="106a1-172">If you decide to view monthly totals, the link text will change to **Weekly View**.</span></span> <span data-ttu-id="106a1-173">È possibile tornare alla visualizzazione settimanale facendo clic sul collegamento.</span><span class="sxs-lookup"><span data-stu-id="106a1-173">You can switch back to the weekly view by clicking that link.</span></span>
  
> [!TIP]
> <span data-ttu-id="106a1-174">Il dashboard di monitoraggio limita la visualizzazione dei totali per la settimana (o il mese) corrente e i valori di tendenza per le ultime sei settimane (o mesi).</span><span class="sxs-lookup"><span data-stu-id="106a1-174">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months).</span></span> <span data-ttu-id="106a1-175">Non è possibile modificare le date e le ore.</span><span class="sxs-lookup"><span data-stu-id="106a1-175">You cannot change these dates and times.</span></span> <span data-ttu-id="106a1-176">Ad esempio, non è possibile usare il dashboard per visualizzare i totali del report per il periodo di tempo che inizia nove mesi fa.</span><span class="sxs-lookup"><span data-stu-id="106a1-176">For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span> 
  
<span data-ttu-id="106a1-177">I valori visualizzati nelle colonne **questa settimana**, **questo mese**o **oggi** possono essere collegati a informazioni più dettagliate sull'elemento.</span><span class="sxs-lookup"><span data-stu-id="106a1-177">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item.</span></span> <span data-ttu-id="106a1-178">Tieni presente che il nome della colonna e i valori visualizzati in tale colonna saranno spesso diversi a seconda della metrica scelta e a seconda che tu abbia selezionato la visualizzazione settimanale o la visualizzazione mensile.</span><span class="sxs-lookup"><span data-stu-id="106a1-178">Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view.</span></span> <span data-ttu-id="106a1-179">Ad esempio, se si fa clic sui totali visualizzati per la metrica degli **accessi utente univoci** verrà visualizzato il **rapporto di registrazione utente** per il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="106a1-179">For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period.</span></span> <span data-ttu-id="106a1-180">È possibile tornare al dashboard di monitoraggio in qualsiasi momento facendo clic su **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="106a1-180">You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>
  
> [!TIP]
> <span data-ttu-id="106a1-181">È anche possibile accedere alla Home page dei report del server di monitoraggio facendo clic sul collegamento **report** nell'angolo in alto a destra del dashboard.</span><span class="sxs-lookup"><span data-stu-id="106a1-181">You can also access the Monitoring Server Reports home page by clicking the **Reports** link in the upper right corner of the Dashboard.</span></span>
  
<span data-ttu-id="106a1-182">Nella colonna **tendenza** viene visualizzato un grafico a linee semplice che mostra i totali per le ultime sei settimane (o, a seconda delle metriche e dell'intervallo di tempo, degli ultimi sei giorni o degli ultimi sei mesi).</span><span class="sxs-lookup"><span data-stu-id="106a1-182">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months).</span></span> <span data-ttu-id="106a1-183">Questi grafici a linee semplici visualizzano un punto dati senza etichetta per ogni periodo di tempo, ad esempio un punto dati senza etichetta per ognuna delle ultime sei settimane.</span><span class="sxs-lookup"><span data-stu-id="106a1-183">These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks).</span></span> <span data-ttu-id="106a1-184">Puoi tuttavia recuperare i valori effettivi per questi grafici tenendo il puntatore del mouse sul grafico.</span><span class="sxs-lookup"><span data-stu-id="106a1-184">However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph.</span></span> <span data-ttu-id="106a1-185">In questo caso, una descrizione comando Mostra i valori minimo e massimo nel grafico.</span><span class="sxs-lookup"><span data-stu-id="106a1-185">In that case, a tool tip shows you the maximum and minimum values in the graph.</span></span>
  
## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="106a1-186">Esportazione di dati dal dashboard di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="106a1-186">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="106a1-187">Il dashboard di monitoraggio offre diversi modi per esportare la visualizzazione dashboard corrente.</span><span class="sxs-lookup"><span data-stu-id="106a1-187">The Monitoring Dashboard provides a number of ways to export the current dashboard view.</span></span> <span data-ttu-id="106a1-188">Sulla barra degli strumenti del dashboard verrà visualizzata un'icona che ha l'aspetto di un disco floppy con una freccia verde collegata.</span><span class="sxs-lookup"><span data-stu-id="106a1-188">On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it.</span></span> <span data-ttu-id="106a1-189">Se si fa clic su questa icona, verrà visualizzato un elenco a discesa che fornisce i formati di esportazione dei dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="106a1-189">If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>
  
- <span data-ttu-id="106a1-190">File XML con i dati del report</span><span class="sxs-lookup"><span data-stu-id="106a1-190">XML file with report data</span></span>
    
- <span data-ttu-id="106a1-191">CSV (delimitato da virgola)</span><span class="sxs-lookup"><span data-stu-id="106a1-191">CSV (comma delimited)</span></span>
    
- <span data-ttu-id="106a1-192">PDF</span><span class="sxs-lookup"><span data-stu-id="106a1-192">PDF</span></span>
    
- <span data-ttu-id="106a1-193">MHTML (archivio Web)</span><span class="sxs-lookup"><span data-stu-id="106a1-193">MHTML (web archive)</span></span>
    
- <span data-ttu-id="106a1-194">Excel</span><span class="sxs-lookup"><span data-stu-id="106a1-194">Excel</span></span>
    
- <span data-ttu-id="106a1-195">File TIFF</span><span class="sxs-lookup"><span data-stu-id="106a1-195">TIFF file</span></span>
    
- <span data-ttu-id="106a1-196">Word</span><span class="sxs-lookup"><span data-stu-id="106a1-196">Word</span></span>
    
<span data-ttu-id="106a1-197">Per esportare la visualizzazione dashboard corrente (e i relativi valori), fare clic sull'opzione di esportazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="106a1-197">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="106a1-198">Skype for Business Server genera un report nel formato specificato e quindi consente di aprire il report o di salvarlo.</span><span class="sxs-lookup"><span data-stu-id="106a1-198">Skype for Business Server generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="106a1-199">Tieni presente che, per impostazione predefinita, Skype for Business Server assegna un titolo al **dashboard di monitoraggio** dei report e lo salva nella cartella download.</span><span class="sxs-lookup"><span data-stu-id="106a1-199">Note that, by default, Skype for Business Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="106a1-200">Per assegnare un nome diverso al report o archiviarlo in un'altra cartella, fare clic sulla freccia accanto al pulsante **Salva** e quindi fare clic su **Salva come**.</span><span class="sxs-lookup"><span data-stu-id="106a1-200">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="106a1-201">Se si sta bene con il **dashboard di monitoraggio** dei nomi e quando il report viene salvato nella cartella download, è sufficiente fare clic sul pulsante **Salva** .</span><span class="sxs-lookup"><span data-stu-id="106a1-201">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>
  
<span data-ttu-id="106a1-202">Quando si prova ad esportare i dati del dashboard, è possibile che venga visualizzata una finestra di dialogo di **avviso di sicurezza** insieme al messaggio "le impostazioni correnti non consentono il download del file".</span><span class="sxs-lookup"><span data-stu-id="106a1-202">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded."</span></span> <span data-ttu-id="106a1-203">Se si verifica questo problema, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="106a1-203">If that occurs, do the following:</span></span>
  
- <span data-ttu-id="106a1-204">In Internet Explorer selezionare **Opzioni Internet**.</span><span class="sxs-lookup"><span data-stu-id="106a1-204">In Internet Explorer, select **Internet Options**.</span></span>
    
- <span data-ttu-id="106a1-205">Nella finestra di dialogo **Opzioni Internet** fare clic su **siti attendibili** nella scheda **sicurezza** e quindi fare clic su **siti**.</span><span class="sxs-lookup"><span data-stu-id="106a1-205">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>
    
- <span data-ttu-id="106a1-206">Nella finestra di dialogo **siti attendibili** fare clic su **Aggiungi** per aggiungere il server Skype for business che gestisce i report di Skype for Business Server per le raccolte di siti Web attendibili.</span><span class="sxs-lookup"><span data-stu-id="106a1-206">In the **Trusted sites** dialog box, click **Add** to add the Skype for Business Server that is running Skype for Business Server Reports to the collections of trusted websites.</span></span>
    
- <span data-ttu-id="106a1-207">Fare clic su **Chiudi** e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="106a1-207">Click **Close** and then click **OK**.</span></span>
    
<span data-ttu-id="106a1-208">Sarà quindi necessario aggiornare il dashboard di monitoraggio prima che le modifiche abbiano effetto.</span><span class="sxs-lookup"><span data-stu-id="106a1-208">You will then need to refresh the Monitoring Dashboard before the changes take effect.</span></span> <span data-ttu-id="106a1-209">A questo scopo, premi F5 o fai clic sull'icona **Aggiorna** nella barra degli strumenti del dashboard.</span><span class="sxs-lookup"><span data-stu-id="106a1-209">To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar.</span></span> <span data-ttu-id="106a1-210">L'icona di **aggiornamento** è un cerchio con una coppia di frecce verdi.</span><span class="sxs-lookup"><span data-stu-id="106a1-210">(The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>
  
<span data-ttu-id="106a1-211">È anche possibile creare un foglio di calcolo di Excel che include feed di dati dinamici, che include collegamenti ai dati più recenti del dashboard di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="106a1-211">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data.</span></span> <span data-ttu-id="106a1-212">Per creare un file di feed di dati in tempo reale, fare clic sull'icona arancione **Esporta in feed di dati** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="106a1-212">To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>
  
<span data-ttu-id="106a1-213">Se si preferisce stampare il dashboard corrente, fare clic sull'icona della stampante sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="106a1-213">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>
  

