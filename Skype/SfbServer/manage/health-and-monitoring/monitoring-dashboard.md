---
title: Uso del dashboard di monitoraggio in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e00e5783-116f-481f-ad17-3af847d6769a
description: 'Riepilogo: informazioni sul dashboard di monitoraggio in Skype for Business Server.'
ms.openlocfilehash: 98a96b8a513bad485a25aff76a69d787fb3079b0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827786"
---
# <a name="using-the-monitoring-dashboard-in-skype-for-business-server"></a><span data-ttu-id="98123-103">Uso del dashboard di monitoraggio in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="98123-103">Using the Monitoring Dashboard in Skype for Business Server</span></span>
 
<span data-ttu-id="98123-104">**Riepilogo:** Informazioni sul dashboard di monitoraggio in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="98123-104">**Summary:** Learn about the Monitoring Dashboard in Skype for Business Server.</span></span>
  
<span data-ttu-id="98123-105">Il dashboard di monitoraggio offre agli amministratori una rapida panoramica dell'integrità e dell'utilizzo del sistema di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="98123-105">The Monitoring Dashboard provides administrators with a quick overview of their Skype for Business Server system health and system usage.</span></span> <span data-ttu-id="98123-106">Il dashboard è progettato per mostrare una visualizzazione aggregata delle metriche di sistema chiave e a tale scopo visualizzando:</span><span class="sxs-lookup"><span data-stu-id="98123-106">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>
  
- <span data-ttu-id="98123-107">Totali del giorno corrente.</span><span class="sxs-lookup"><span data-stu-id="98123-107">Totals for the current day.</span></span> <span data-ttu-id="98123-108">Si noti che i valori visualizzati per il giorno corrente rappresentano i dati registrati dalla mezzanotte all'ora corrente (in base all'ora locale del server di report).</span><span class="sxs-lookup"><span data-stu-id="98123-108">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="98123-109">Ciò significa che in genere si visualizzano i dati per un giorno parziale e non per un periodo di 24 ore.</span><span class="sxs-lookup"><span data-stu-id="98123-109">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="98123-110">Ad esempio, se l'ora locale del server è alle 8.00, verranno visualizzati otto ore di dati perché sono presenti otto ore tra la mezzanotte e l'ora corrente delle 8.00.</span><span class="sxs-lookup"><span data-stu-id="98123-110">For example, if the local time of the server is 8:00 AM, you see eight hours' worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>
    
- <span data-ttu-id="98123-111">Totali della settimana e totali delle tendenze delle ultime sei settimane.</span><span class="sxs-lookup"><span data-stu-id="98123-111">Totals for the week, and trend totals for the past six weeks.</span></span>
    
- <span data-ttu-id="98123-112">Totali del mese e totali delle tendenze degli ultimi sei mesi (solo per l'utilizzo del sistema).</span><span class="sxs-lookup"><span data-stu-id="98123-112">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>
    
<span data-ttu-id="98123-113">Si noti che è possibile utilizzare il cmdlet [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) per restituire l'URL utilizzato per accedere ai rapporti di monitoraggio di Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="98123-113">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) cmdlet to return the URL used for accessing Skype for Business Server Monitoring Reports:</span></span>
  
```PowerShell
Get-CsReportingConfiguration
```

<span data-ttu-id="98123-114">Per impostazione predefinita, il dashboard di monitoraggio mostra i dati per le metriche seguenti per la settimana corrente (e i totali delle tendenze delle sei settimane precedenti):</span><span class="sxs-lookup"><span data-stu-id="98123-114">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>
  
## <a name="system-usage-metrics"></a><span data-ttu-id="98123-115">Metriche di utilizzo del sistema</span><span class="sxs-lookup"><span data-stu-id="98123-115">System Usage Metrics</span></span>

 <span data-ttu-id="98123-116">**Registrazione**</span><span class="sxs-lookup"><span data-stu-id="98123-116">**Registration**</span></span>
  
- <span data-ttu-id="98123-117">Accessi utente univoci</span><span class="sxs-lookup"><span data-stu-id="98123-117">Unique user logons</span></span>
    
  <span data-ttu-id="98123-118">**Peer-to-peer**</span><span class="sxs-lookup"><span data-stu-id="98123-118">**Peer-to-peer**</span></span>
  
- <span data-ttu-id="98123-119">Totale sessioni</span><span class="sxs-lookup"><span data-stu-id="98123-119">Total sessions</span></span>
    
- <span data-ttu-id="98123-120">Sessioni di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="98123-120">IM sessions</span></span>
    
- <span data-ttu-id="98123-121">Sessioni audio</span><span class="sxs-lookup"><span data-stu-id="98123-121">Audio sessions</span></span>
    
- <span data-ttu-id="98123-122">Sessioni video</span><span class="sxs-lookup"><span data-stu-id="98123-122">Video sessions</span></span>
    
- <span data-ttu-id="98123-123">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="98123-123">Application sharing</span></span>
    
- <span data-ttu-id="98123-124">Totale minuti sessione audio</span><span class="sxs-lookup"><span data-stu-id="98123-124">Total audio session minutes</span></span>
    
- <span data-ttu-id="98123-125">Media minuti sessione audio</span><span class="sxs-lookup"><span data-stu-id="98123-125">Avg. audio session minutes</span></span>
    
  <span data-ttu-id="98123-126">**Conferenza**</span><span class="sxs-lookup"><span data-stu-id="98123-126">**Conference**</span></span>
  
- <span data-ttu-id="98123-127">Totale conferenze</span><span class="sxs-lookup"><span data-stu-id="98123-127">Total conferences</span></span>
    
- <span data-ttu-id="98123-128">Conferenze di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="98123-128">IM conferences</span></span>
    
- <span data-ttu-id="98123-129">Conferenze audio/video</span><span class="sxs-lookup"><span data-stu-id="98123-129">A/V conferences</span></span>
    
- <span data-ttu-id="98123-130">Conferenze di condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="98123-130">Application sharing conferences</span></span>
    
- <span data-ttu-id="98123-131">Conferenze Web</span><span class="sxs-lookup"><span data-stu-id="98123-131">Web conferences</span></span>
    
- <span data-ttu-id="98123-132">Totale organizzatori</span><span class="sxs-lookup"><span data-stu-id="98123-132">Total organizers</span></span>
    
- <span data-ttu-id="98123-133">Totale minuti di conferenza audio/video</span><span class="sxs-lookup"><span data-stu-id="98123-133">Total A/V conference minutes</span></span>
    
- <span data-ttu-id="98123-134">Media Minuti conferenza audio/video</span><span class="sxs-lookup"><span data-stu-id="98123-134">Avg. A/V conference minutes</span></span>
    
- <span data-ttu-id="98123-135">Totale conferenze PSTN</span><span class="sxs-lookup"><span data-stu-id="98123-135">Total PSTN conferences</span></span>
    
- <span data-ttu-id="98123-136">Totale partecipanti PSTN</span><span class="sxs-lookup"><span data-stu-id="98123-136">Total PSTN participants</span></span>
    
- <span data-ttu-id="98123-137">Totale minuti partecipante PSTN</span><span class="sxs-lookup"><span data-stu-id="98123-137">Total PSTN participant minutes</span></span>
    
<span data-ttu-id="98123-138">Oltre alle metriche di utilizzo del sistema, le metriche seguenti visualizzano il totale per il giorno corrente e per i sei giorni precedenti (se si seleziona Visualizzazione **settimanale)** o per la settimana corrente e le ultime sei settimane se si seleziona Visualizzazione mensile. </span><span class="sxs-lookup"><span data-stu-id="98123-138">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>
  
## <a name="per-user-call-diagnostics"></a><span data-ttu-id="98123-139">Per-User diagnostica chiamate</span><span class="sxs-lookup"><span data-stu-id="98123-139">Per-User Call Diagnostics</span></span>

 <span data-ttu-id="98123-140">**Utenti con errori di chiamata**</span><span class="sxs-lookup"><span data-stu-id="98123-140">**Users with call failures**</span></span>
  
- <span data-ttu-id="98123-141">Totale utenti con errori di chiamata</span><span class="sxs-lookup"><span data-stu-id="98123-141">Total users with call failures</span></span>
    
- <span data-ttu-id="98123-142">Organizzatori di conferenze con errori di chiamata</span><span class="sxs-lookup"><span data-stu-id="98123-142">Conference organizers with call failures</span></span>
    
  <span data-ttu-id="98123-143">**Utenti con chiamate di qualità scarsa**</span><span class="sxs-lookup"><span data-stu-id="98123-143">**Users with poor quality calls**</span></span>
  
- <span data-ttu-id="98123-144">Totale utenti con chiamate di qualità scarsa</span><span class="sxs-lookup"><span data-stu-id="98123-144">Total users with poor quality calls</span></span>
    
## <a name="call-diagnostics"></a><span data-ttu-id="98123-145">Diagnostica chiamate</span><span class="sxs-lookup"><span data-stu-id="98123-145">Call Diagnostics</span></span>

<span data-ttu-id="98123-146">Peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="98123-146">Peer-to-peer</span></span>
  
- <span data-ttu-id="98123-147">Totale errori</span><span class="sxs-lookup"><span data-stu-id="98123-147">Total failures</span></span>
    
- <span data-ttu-id="98123-148">Frequenza di errore complessiva</span><span class="sxs-lookup"><span data-stu-id="98123-148">Overall failure rate</span></span>
    
- <span data-ttu-id="98123-149">Frequenza errori di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="98123-149">IM failure rate</span></span>
    
- <span data-ttu-id="98123-150">Frequenza di errore audio</span><span class="sxs-lookup"><span data-stu-id="98123-150">Audio failure rate</span></span>
    
- <span data-ttu-id="98123-151">Frequenza errori di condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="98123-151">Application sharing failure rate</span></span>
    
<span data-ttu-id="98123-152">Conferenza</span><span class="sxs-lookup"><span data-stu-id="98123-152">Conference</span></span>
  
- <span data-ttu-id="98123-153">Totale errori</span><span class="sxs-lookup"><span data-stu-id="98123-153">Total failures</span></span>
    
- <span data-ttu-id="98123-154">Frequenza di errore complessiva</span><span class="sxs-lookup"><span data-stu-id="98123-154">Overall failure rate</span></span>
    
- <span data-ttu-id="98123-155">Frequenza errori di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="98123-155">IM failure rate</span></span>
    
- <span data-ttu-id="98123-156">Frequenza di errore A/V</span><span class="sxs-lookup"><span data-stu-id="98123-156">A/V failure rate</span></span>
    
- <span data-ttu-id="98123-157">Frequenza errori di condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="98123-157">Application sharing failure rate</span></span>
    
<span data-ttu-id="98123-158">Primi cinque server per sessioni non riuscite</span><span class="sxs-lookup"><span data-stu-id="98123-158">Top five servers by failed sessions</span></span>
  
## <a name="media-quality-diagnostics"></a><span data-ttu-id="98123-159">Diagnostica qualità multimediale</span><span class="sxs-lookup"><span data-stu-id="98123-159">Media Quality Diagnostics</span></span>

<span data-ttu-id="98123-160">Peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="98123-160">Peer-to-peer</span></span>
  
- <span data-ttu-id="98123-161">Totale chiamate di qualità scarsa</span><span class="sxs-lookup"><span data-stu-id="98123-161">Total poor quality calls</span></span>
    
- <span data-ttu-id="98123-162">Percentuale di chiamate di qualità scarsa</span><span class="sxs-lookup"><span data-stu-id="98123-162">Poor quality call percentage</span></span>
    
- <span data-ttu-id="98123-163">Chiamate PSTN con qualità scarsa</span><span class="sxs-lookup"><span data-stu-id="98123-163">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="98123-164">Conferenza</span><span class="sxs-lookup"><span data-stu-id="98123-164">Conference</span></span>
  
- <span data-ttu-id="98123-165">Totale chiamate di qualità scarsa</span><span class="sxs-lookup"><span data-stu-id="98123-165">Total poor quality calls</span></span>
    
- <span data-ttu-id="98123-166">Percentuale di chiamate di qualità scarsa</span><span class="sxs-lookup"><span data-stu-id="98123-166">Poor quality call percentage</span></span>
    
- <span data-ttu-id="98123-167">Chiamate PSTN con qualità scarsa</span><span class="sxs-lookup"><span data-stu-id="98123-167">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="98123-168">Principali server peggiori in base alla percentuale di chiamate di qualità scarsa</span><span class="sxs-lookup"><span data-stu-id="98123-168">Top worst servers by poor quality call percentage</span></span>
  
## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="98123-169">Utilizzo del dashboard di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="98123-169">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="98123-170">Come indicato, per impostazione predefinita vengono visualizzati i totali per la settimana corrente e i valori delle tendenze delle ultime sei settimane.</span><span class="sxs-lookup"><span data-stu-id="98123-170">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks.</span></span> <span data-ttu-id="98123-171">Se si preferisce visualizzare i totali del mese corrente e i valori di tendenza degli ultimi sei mesi, fare clic sul collegamento **Visualizzazione** mensile nell'angolo superiore destro del dashboard.</span><span class="sxs-lookup"><span data-stu-id="98123-171">If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard.</span></span> <span data-ttu-id="98123-172">Se si decide di visualizzare i totali mensili, il testo del collegamento verrà modificato in **Visualizzazione settimanale.**</span><span class="sxs-lookup"><span data-stu-id="98123-172">If you decide to view monthly totals, the link text will change to **Weekly View**.</span></span> <span data-ttu-id="98123-173">È possibile tornare alla visualizzazione settimanale facendo clic su tale collegamento.</span><span class="sxs-lookup"><span data-stu-id="98123-173">You can switch back to the weekly view by clicking that link.</span></span>
  
> [!TIP]
> <span data-ttu-id="98123-174">Il dashboard di monitoraggio limita l'analisi dei totali della settimana (o del mese) corrente e dei valori di tendenza delle ultime sei settimane (o mesi).</span><span class="sxs-lookup"><span data-stu-id="98123-174">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months).</span></span> <span data-ttu-id="98123-175">Non è possibile modificare queste date e ore.</span><span class="sxs-lookup"><span data-stu-id="98123-175">You cannot change these dates and times.</span></span> <span data-ttu-id="98123-176">Ad esempio, non è possibile utilizzare il dashboard per visualizzare i totali dei report per il periodo di tempo che inizia nove mesi fa.</span><span class="sxs-lookup"><span data-stu-id="98123-176">For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span> 
  
<span data-ttu-id="98123-177">I valori visualizzati nelle colonne Questa  **settimana,** Questo **mese** o Oggi collegano l'utente a informazioni più dettagliate sull'elemento.</span><span class="sxs-lookup"><span data-stu-id="98123-177">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item.</span></span> <span data-ttu-id="98123-178">Tenere presente che il nome della colonna e i valori visualizzati in tale colonna spesso variano a seconda della metrica scelta e a seconda che sia stata selezionata la visualizzazione settimanale o mensile.</span><span class="sxs-lookup"><span data-stu-id="98123-178">Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view.</span></span> <span data-ttu-id="98123-179">Ad esempio, se si fa clic  sui totali visualizzati per la metrica Accessi utente univoci, verrà visualizzato il **Rapporto** registrazione utenti per il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="98123-179">For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period.</span></span> <span data-ttu-id="98123-180">È possibile tornare al dashboard di monitoraggio in qualsiasi momento facendo clic su **Dashboard.**</span><span class="sxs-lookup"><span data-stu-id="98123-180">You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>
  
> [!TIP]
> <span data-ttu-id="98123-181">È inoltre possibile accedere alla home page dei rapporti di Monitoring Server facendo clic sul collegamento **Report** nell'angolo in alto a destra del dashboard.</span><span class="sxs-lookup"><span data-stu-id="98123-181">You can also access the Monitoring Server Reports home page by clicking the **Reports** link in the upper right corner of the Dashboard.</span></span>
  
<span data-ttu-id="98123-182">La **colonna Tendenza** visualizza un semplice grafico a linee che mostra i totali delle ultime sei settimane (o, a seconda della metrica e dell'intervallo di tempo, degli ultimi sei giorni o degli ultimi sei mesi).</span><span class="sxs-lookup"><span data-stu-id="98123-182">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months).</span></span> <span data-ttu-id="98123-183">Questi semplici grafici a linee visualizzano una data point senza etichetta per ogni periodo di tempo (ad esempio, una data point senza etichetta per ognuna delle ultime sei settimane).</span><span class="sxs-lookup"><span data-stu-id="98123-183">These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks).</span></span> <span data-ttu-id="98123-184">Tuttavia, puoi recuperare i valori effettivi per questi grafici tenendo il puntatore del mouse sul grafico.</span><span class="sxs-lookup"><span data-stu-id="98123-184">However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph.</span></span> <span data-ttu-id="98123-185">In questo caso, una descrizione comando mostra i valori massimo e minimo nel grafico.</span><span class="sxs-lookup"><span data-stu-id="98123-185">In that case, a tool tip shows you the maximum and minimum values in the graph.</span></span>
  
## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="98123-186">Esportazione di dati dal dashboard di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="98123-186">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="98123-187">Il dashboard di monitoraggio offre diversi modi per esportare la visualizzazione dashboard corrente.</span><span class="sxs-lookup"><span data-stu-id="98123-187">The Monitoring Dashboard provides a number of ways to export the current dashboard view.</span></span> <span data-ttu-id="98123-188">Sulla barra degli strumenti del dashboard verrà visualizzata un'icona simile a un disco floppy a cui è collegata una freccia verde.</span><span class="sxs-lookup"><span data-stu-id="98123-188">On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it.</span></span> <span data-ttu-id="98123-189">Se si fa clic su questa icona, verrà visualizzato un elenco a discesa con i seguenti formati di esportazione dei dati:</span><span class="sxs-lookup"><span data-stu-id="98123-189">If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>
  
- <span data-ttu-id="98123-190">File XML con dati del rapporto</span><span class="sxs-lookup"><span data-stu-id="98123-190">XML file with report data</span></span>
    
- <span data-ttu-id="98123-191">CSV (delimitato da virgole)</span><span class="sxs-lookup"><span data-stu-id="98123-191">CSV (comma delimited)</span></span>
    
- <span data-ttu-id="98123-192">PDF</span><span class="sxs-lookup"><span data-stu-id="98123-192">PDF</span></span>
    
- <span data-ttu-id="98123-193">MHTML (archivio Web)</span><span class="sxs-lookup"><span data-stu-id="98123-193">MHTML (web archive)</span></span>
    
- <span data-ttu-id="98123-194">Excel</span><span class="sxs-lookup"><span data-stu-id="98123-194">Excel</span></span>
    
- <span data-ttu-id="98123-195">File TIFF</span><span class="sxs-lookup"><span data-stu-id="98123-195">TIFF file</span></span>
    
- <span data-ttu-id="98123-196">Word</span><span class="sxs-lookup"><span data-stu-id="98123-196">Word</span></span>
    
<span data-ttu-id="98123-197">Per esportare la visualizzazione dashboard corrente e i relativi valori, fare clic sull'opzione di esportazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="98123-197">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="98123-198">Skype for Business Server genera un report nel formato specificato e quindi consente di aprirlo o salvarlo.</span><span class="sxs-lookup"><span data-stu-id="98123-198">Skype for Business Server generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="98123-199">Si noti che, per impostazione predefinita, Skype for Business Server titoli il **report Monitoring Dashboard** e lo salva nella cartella Download.</span><span class="sxs-lookup"><span data-stu-id="98123-199">Note that, by default, Skype for Business Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="98123-200">Per assegnare un nome diverso al report o archiviarlo in  una cartella diversa, fare clic sulla freccia accanto al pulsante Salva e quindi su **Salva con nome.**</span><span class="sxs-lookup"><span data-stu-id="98123-200">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="98123-201">Se si ha il nome **Dashboard di monitoraggio** e il report viene salvato nella cartella Download, è sufficiente fare clic sul **pulsante** Salva.</span><span class="sxs-lookup"><span data-stu-id="98123-201">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>
  
<span data-ttu-id="98123-202">È possibile che, quando si tenta di  esportare i dati del dashboard, venga visualizzata una finestra di dialogo avviso di sicurezza con il messaggio "Le impostazioni correnti non consentono il download di questo file".</span><span class="sxs-lookup"><span data-stu-id="98123-202">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded."</span></span> <span data-ttu-id="98123-203">In questo caso, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="98123-203">If that occurs, do the following:</span></span>
  
- <span data-ttu-id="98123-204">In Internet Explorer selezionare **Opzioni Internet.**</span><span class="sxs-lookup"><span data-stu-id="98123-204">In Internet Explorer, select **Internet Options**.</span></span>
    
- <span data-ttu-id="98123-205">Nella scheda **Protezione della** finestra di dialogo Opzioni Internet **fare** clic su **Siti attendibili** e quindi su **Siti.**</span><span class="sxs-lookup"><span data-stu-id="98123-205">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>
    
- <span data-ttu-id="98123-206">Nella finestra **di dialogo**  Siti attendibili fare clic su Aggiungi per aggiungere Skype for Business Server che esegue i report di Skype for Business Server alle raccolte di siti Web attendibili.</span><span class="sxs-lookup"><span data-stu-id="98123-206">In the **Trusted sites** dialog box, click **Add** to add the Skype for Business Server that is running Skype for Business Server Reports to the collections of trusted websites.</span></span>
    
- <span data-ttu-id="98123-207">Fare **clic su** Chiudi e quindi su **OK.**</span><span class="sxs-lookup"><span data-stu-id="98123-207">Click **Close** and then click **OK**.</span></span>
    
<span data-ttu-id="98123-208">Sarà quindi necessario aggiornare il dashboard di monitoraggio prima che le modifiche avranno effetto.</span><span class="sxs-lookup"><span data-stu-id="98123-208">You will then need to refresh the Monitoring Dashboard before the changes take effect.</span></span> <span data-ttu-id="98123-209">A tale scopo, premere F5 o fare clic **sull'icona** Aggiorna sulla barra degli strumenti del dashboard.</span><span class="sxs-lookup"><span data-stu-id="98123-209">To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar.</span></span> <span data-ttu-id="98123-210">**L'icona** Aggiorna è un cerchio con una coppia di frecce verdi al suo interno.</span><span class="sxs-lookup"><span data-stu-id="98123-210">(The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>
  
<span data-ttu-id="98123-211">È inoltre possibile creare un foglio di calcolo di Excel che include feed di dati in tempo reale, che include collegamenti ai dati più recenti del dashboard di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="98123-211">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data.</span></span> <span data-ttu-id="98123-212">Per creare un file di feed di dati in tempo reale, fare clic sull'icona arancione Esporta in **feed** dati sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="98123-212">To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>
  
<span data-ttu-id="98123-213">Se si preferisce stampare il dashboard corrente, fare clic sull'icona della stampante sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="98123-213">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>
  

