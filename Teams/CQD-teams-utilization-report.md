---
title: Visualizzare l'utilizzo di Microsoft teams in Power BI usando i dati di Call Quality dashboard
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Usare i report di Power BI di utilizzo dei team per tenere traccia dell'utilizzo di Microsoft teams nell'organizzazione.
ms.openlocfilehash: d22f37bb230ecbaa3cf6c33c2ba43f5ea92afaad
ms.sourcegitcommit: 98fcfc03c55917d0aca48b7bd97988f81e8930c1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/07/2020
ms.locfileid: "42559484"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="83299-103">Visualizzare l'utilizzo di Microsoft teams in Power BI usando i dati di Call Quality dashboard</span><span class="sxs-lookup"><span data-stu-id="83299-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="83299-104">Novità di marzo 2020 è stato aggiunto un report di utilizzo dei team ai [modelli di query di Power bi scaricabili per Call Quality dashboard](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="83299-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="83299-105">I nuovi report di utilizzo dei team consentono di vedere come (e quanto) gli utenti usano Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="83299-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams.</span></span> <span data-ttu-id="83299-106">Questi report sono progettati per essere una posizione centralizzata che consente agli amministratori e alle aziende leader di accedere rapidamente a questi dati.</span><span class="sxs-lookup"><span data-stu-id="83299-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="83299-107">Il report utilizzo di Power BI di teams è costituito da due report principali: riepilogo delle **[chiamate](#call-count-summary-report)** e riepilogo dei **[minuti audio](#audio-minutes-summary-report)**.</span><span class="sxs-lookup"><span data-stu-id="83299-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="83299-108">I report [uso quotidiano](#daily-usage) e [dettagli audio regionali](#regional-audio-details) entrano in gioco quando un utente sfrutta i report drill-down descritti nelle descrizioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="83299-108">The [Daily Usage](#daily-usage) and [Regional Audio Details](#regional-audio-details) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="83299-109">I dati di compilazione e subnet devono essere popolati per consentire funzionalità di filtro di rete e regionali.</span><span class="sxs-lookup"><span data-stu-id="83299-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="83299-110">Report riepilogo Conteggio chiamate</span><span class="sxs-lookup"><span data-stu-id="83299-110">Call Count Summary Report</span></span>

<span data-ttu-id="83299-111">La pagina principale (riepilogo Conteggio chiamate) fornisce immediatamente il numero di sessioni di condivisione audio, video e dello schermo negli ultimi 30 e 90 giorni, come indicato nel titolo della sezione.</span><span class="sxs-lookup"><span data-stu-id="83299-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="83299-112">I dati visualizzati inizialmente sono per l'intera organizzazione e possono essere filtrati usando le opzioni di elenco a discesa del filtro delle informazioni sul lato sinistro della pagina.</span><span class="sxs-lookup"><span data-stu-id="83299-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![Screenshot: report Riepilogo Contea chiamata](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="83299-114">A destra dell'elenco a discesa del filtro dei dati, il numero di chiamate per tipo di elemento multimediale è suddiviso in una visualizzazione interna/esterna negli ultimi trenta giorni.</span><span class="sxs-lookup"><span data-stu-id="83299-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="83299-115">Possiamo vedere attraverso lo screenshot sopra che ci sono più chiamate che si verificano da posizioni fuori dall'organizzazione, il che ha senso considerando l'ambiente globale corrente.</span><span class="sxs-lookup"><span data-stu-id="83299-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="83299-116">![Screenshot: report Riepilogo Contea chiamata](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="83299-116">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="83299-117">A destra della casella Conteggio tipi di elementi multimediali è presente il conteggio chiamate mensili per tipo di elemento multimediale per gli ultimi 90 giorni.</span><span class="sxs-lookup"><span data-stu-id="83299-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="83299-118">Ogni colonna e tipo di elemento multimediale può essere posizionato sopra per visualizzare il conteggio per un mese precedente o il mese corrente fino a data, fornendo informazioni sulle tendenze di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="83299-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="83299-119">![Screenshot: report Riepilogo Contea chiamata](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="83299-119">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report3.png)</span></span>

1. <span data-ttu-id="83299-120">Il grafico centrale funziona come il grafico di 90 giorni, ma offre una visualizzazione giornaliera degli ultimi 30 giorni e consente a un utente di fare clic con il pulsante destro del mouse e di eseguire il drill-down nei dettagli per un giorno specifico.</span><span class="sxs-lookup"><span data-stu-id="83299-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="83299-121">![Screenshot: report Riepilogo Contea chiamata](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="83299-121">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="83299-122">Nella sezione in basso a sinistra della pagina è disponibile una tabella che fornisce i valori totali per ogni tipo di elemento multimediale dello scorso anno.</span><span class="sxs-lookup"><span data-stu-id="83299-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="83299-123">![Screenshot: report Riepilogo Contea chiamata](media/CQD-teams-utilization-report5.png)</span><span class="sxs-lookup"><span data-stu-id="83299-123">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report5.png)</span></span>
  
<span data-ttu-id="83299-124">La tabella contiene anche un drill-down disponibile in cui è possibile visualizzare una ripartizione dei dati regionale.</span><span class="sxs-lookup"><span data-stu-id="83299-124">The table also has an available drill down where you can see a regional data breakdown.</span></span>
    <span data-ttu-id="83299-125">![Screenshot: report Riepilogo Contea chiamata](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="83299-125">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report6.png)</span></span>

<span data-ttu-id="83299-126">A destra della tabella, un grafico a barre Mostra i client con la maggior parte dei casi (chiamate/flussi) per gli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="83299-126">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="83299-127">![Screenshot: report Riepilogo Contea chiamata](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="83299-127">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report7.png)</span></span>


<span data-ttu-id="83299-128">L'ultimo set di grafici per questa pagina mostra ogni tipo di elemento multimediale individualmente, con una ripartizione che mostra l'uso di conferenze e P2P.</span><span class="sxs-lookup"><span data-stu-id="83299-128">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="83299-129">I grafici seguenti mostrano che c'è un numero significativamente più elevato di utilizzo delle conferenze rispetto al P2P.</span><span class="sxs-lookup"><span data-stu-id="83299-129">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="83299-130">![Screenshot: report Riepilogo Contea chiamata](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="83299-130">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="83299-131">Report di riepilogo minuti audio</span><span class="sxs-lookup"><span data-stu-id="83299-131">Audio Minutes Summary Report</span></span>

<span data-ttu-id="83299-132">Nel report sull'utilizzo dei minuti audio l'utilizzo totale dei minuti viene fornito tramite alcune visualizzazioni diverse.</span><span class="sxs-lookup"><span data-stu-id="83299-132">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="83299-133">Il riepilogo dell'utilizzo di trenta giorni viene visualizzato accanto ai filtri dei dati come caselle di testo semplici da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="83299-133">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="83299-134">Il numero superiore mostra il totale di trenta giorni, con guasti interni ed esterni.</span><span class="sxs-lookup"><span data-stu-id="83299-134">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![Screenshot: report Riepilogo Contea chiamata](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="83299-136">Il grafico a barre superiore destro offre una visualizzazione yearlong dell'uso dell'audio per conferenze.</span><span class="sxs-lookup"><span data-stu-id="83299-136">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="83299-137">Posizionare il puntatore del mouse sul mese per visualizzare i minuti audio della conferenza.</span><span class="sxs-lookup"><span data-stu-id="83299-137">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="83299-138">Per mostrare la differenza tra il P2P e l'audio per conferenze, il grafico in basso a sinistra prende tutto l'audio per l'anno passato e lo suddivide tra i due tipi.</span><span class="sxs-lookup"><span data-stu-id="83299-138">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

<span data-ttu-id="83299-139">![Screenshot: report](media/CQD-teams-utilization-report10.png) Riepilogo Contea chiamata nell'ultimo grafico della pagina minuti audio viene visualizzato l'utilizzo dei minuti audio in una sovrapposizione di mappa globale.</span><span class="sxs-lookup"><span data-stu-id="83299-139">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report10.png) The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="83299-140">Questo grafico funzionerà solo se i dati di compilazione e subnet vengono caricati nel tenant.</span><span class="sxs-lookup"><span data-stu-id="83299-140">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="83299-141">È possibile eseguire il drill-down della sovrapposizione del grafico a torta sulla mappa, fornendo in seguito l'utilizzo dell'audio locale.</span><span class="sxs-lookup"><span data-stu-id="83299-141">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![Screenshot: report Riepilogo Contea chiamata](media/CQD-teams-utilization-report11.png)

## <a name="drill-through-capabilities"></a><span data-ttu-id="83299-143">Funzionalità di drill-through</span><span class="sxs-lookup"><span data-stu-id="83299-143">Drill-through capabilities</span></span>

<span data-ttu-id="83299-144">Come indicato in precedenza, gli utenti possono eseguire il drill-up dei report di utilizzo giornalieri e regionali.</span><span class="sxs-lookup"><span data-stu-id="83299-144">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="83299-145">Uso quotidiano</span><span class="sxs-lookup"><span data-stu-id="83299-145">Daily Usage</span></span>

<span data-ttu-id="83299-146">Il report utilizzo giornaliero consente a un amministratore di identificare i periodi di consumo di picco nel corso di una giornata.</span><span class="sxs-lookup"><span data-stu-id="83299-146">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="83299-147">Oltre all'uso, siamo anche in grado di acquisire sentimenti e feedback generali degli utenti per quel giorno.</span><span class="sxs-lookup"><span data-stu-id="83299-147">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![Screenshot: report Riepilogo Contea chiamata](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="83299-149">Questi dati possono essere usati per identificare le aree che hanno problemi durante i tempi di consumo massimo.</span><span class="sxs-lookup"><span data-stu-id="83299-149">This data can be used to identify regions having problems during peak consumption times.</span></span>

1.  <span data-ttu-id="83299-150">Nella pagina Riepilogo conteggio chiamate eseguire il drill-through in una data specifica.</span><span class="sxs-lookup"><span data-stu-id="83299-150">On the Call Count Summary page, drill-through on a specific date.</span></span> <span data-ttu-id="83299-151">Esaminare la tendenza oraria in un giorno per trovare l'utilizzo di picco.</span><span class="sxs-lookup"><span data-stu-id="83299-151">Look at the hourly trend that day to find the peak utilization.</span></span>
  <span data-ttu-id="83299-152">![Screenshot: report Riepilogo Contea chiamata](media/CQD-teams-utilization-report13.png)</span><span class="sxs-lookup"><span data-stu-id="83299-152">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report13.png)</span></span>

2.  <span data-ttu-id="83299-153">Fare clic sulla colonna per il giorno in cui visualizzare le metriche per l'ora.</span><span class="sxs-lookup"><span data-stu-id="83299-153">Click on the column for that day to display metrics for that hour.</span></span>
  <span data-ttu-id="83299-154">![Screenshot: report Riepilogo Contea chiamata](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="83299-154">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report14.png)</span></span>
    
    1.  <span data-ttu-id="83299-155">La tabella sotto il grafico visualizzerà le metriche per l'ora.</span><span class="sxs-lookup"><span data-stu-id="83299-155">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="83299-156">Questa operazione può essere ordinata in base a qualsiasi intestazione di colonna. Tuttavia, ci interesserebbe trovare aree problematiche.</span><span class="sxs-lookup"><span data-stu-id="83299-156">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
        ![Screenshot: report Riepilogo Contea chiamata](media/CQD-teams-utilization-report15.png)
    
    2.  <span data-ttu-id="83299-158">Vediamo che l'area IND sta vivendo scarse prestazioni video in conferenze durante questo lasso di tempo.</span><span class="sxs-lookup"><span data-stu-id="83299-158">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="83299-159">In seguito, è possibile usare i report Microsoft Call Quality dashboard QER per limitare la posizione problematica in cui l'area geografica e l'intervallo di tempo sono stati identificati.</span><span class="sxs-lookup"><span data-stu-id="83299-159">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="regional-audio-details"></a><span data-ttu-id="83299-160">Dettagli audio internazionali</span><span class="sxs-lookup"><span data-stu-id="83299-160">Regional Audio Details</span></span>

<span data-ttu-id="83299-161">Il drill-down dei dettagli audio internazionali Mostra in modo specifico l'utilizzo dei minuti audio per l'area selezionata.</span><span class="sxs-lookup"><span data-stu-id="83299-161">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="83299-162">Gli utenti con accesso a Call Quality dashboard possono vedere le tendenze di utilizzo per l'audio sia P2P che congressuale all'interno dell'area selezionata.</span><span class="sxs-lookup"><span data-stu-id="83299-162">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="83299-163">Nella pagina Riepilogo conteggio chiamate eseguire il drill-through come area specifica tramite la tabella.</span><span class="sxs-lookup"><span data-stu-id="83299-163">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="83299-164">![Screenshot: report Riepilogo Contea chiamata](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="83299-164">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="83299-165">Selezionare la riga con l'area geografica in cui sono necessarie altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="83299-165">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="83299-166">![Screenshot: report Riepilogo Contea chiamata](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="83299-166">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="83299-167">Le tendenze dei dati mostrano un numero significativo di minuti usati nella rete interna, con i servizi di conferenza che superano l'uso P2P.</span><span class="sxs-lookup"><span data-stu-id="83299-167">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="83299-168">![Screenshot: report Riepilogo Contea chiamata](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="83299-168">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="83299-169">La tendenza audio locale può essere usata per mostrare in che modo gli utenti hanno un impatto sulle influenze esterne nel mondo.</span><span class="sxs-lookup"><span data-stu-id="83299-169">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="83299-170">In particolare, in questo momento, ci si aspetterebbe di vedere l'uso esterno per le aree EMEA e APAC per aumentare le persone che hanno chiesto di lavorare in remoto.</span><span class="sxs-lookup"><span data-stu-id="83299-170">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>



## <a name="related-topics"></a><span data-ttu-id="83299-171">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="83299-171">Related topics</span></span>

[<span data-ttu-id="83299-172">Dimensioni e misure disponibili in Dashboard Qualità della chiamata</span><span class="sxs-lookup"><span data-stu-id="83299-172">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="83299-173">Classificazione del flusso in Dashboard Qualità della chiamata</span><span class="sxs-lookup"><span data-stu-id="83299-173">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="83299-174">Configurazione di Skype for Business Call Analytics</span><span class="sxs-lookup"><span data-stu-id="83299-174">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="83299-175">Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate</span><span class="sxs-lookup"><span data-stu-id="83299-175">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="83299-176">Analisi delle chiamate e Dashboard Qualità della chiamata</span><span class="sxs-lookup"><span data-stu-id="83299-176">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)
 