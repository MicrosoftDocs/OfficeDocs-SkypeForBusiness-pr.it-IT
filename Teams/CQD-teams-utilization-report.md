---
title: Visualizzare l'utilizzo di Microsoft Teams in Power BI usando i dati di CQD
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Usare i report Di utilizzo di Teams di Power BI per accedere ai dati di Microsoft Teams Call Quality Dashboard (CQD) per tenere traccia dell'utilizzo di Microsoft Teams nell'organizzazione.
ms.openlocfilehash: bda89f3715997016e6c1bea242dcf6b8b182c6bf
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581547"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="843da-103">Visualizzare l'utilizzo di Microsoft Teams in Power BI usando i dati di CQD</span><span class="sxs-lookup"><span data-stu-id="843da-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="843da-104">A marzo 2020 è stato aggiunto un report sull'utilizzo di Teams ai modelli di query di Power BI scaricabili [per CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="843da-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="843da-105">Questo nuovo report sull'utilizzo di Teams consente di vedere come (e quanto) gli utenti usano Microsoft Teams accedendo ai dati di Teams Call Quality Dashboard (CQD).</span><span class="sxs-lookup"><span data-stu-id="843da-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams by accessing Teams Call Quality Dashboard (CQD) data.</span></span> <span data-ttu-id="843da-106">Questi report sono stati pensati per essere una posizione centralizzata a cui possono accedere rapidamente gli amministratori e i responsabili aziendali.</span><span class="sxs-lookup"><span data-stu-id="843da-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="843da-107">Il report Utilizzo team di Power BI è costituito da due report principali: **[Riepilogo conteggi](#call-count-summary-report)** chiamate e Riepilogo **[minuti audio.](#audio-minutes-summary-report)**</span><span class="sxs-lookup"><span data-stu-id="843da-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="843da-108">I [report Utilizzo](#daily-usage)giornaliero, Dettagli [](#user-list) [audio](#regional-audio-details) [regionale,](#conference-details) Dettagli conferenza ed Elenco utenti vengono riprodotti quando un utente sfrutta i report drill-down, indicati nelle descrizioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="843da-108">The [Daily Usage](#daily-usage), [Regional Audio Details](#regional-audio-details), [Conference Details](#conference-details) and [User List](#user-list) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="843da-109">I dati di edifici e subnet devono essere popolati per fornire funzionalità di filtro di rete e di zona.</span><span class="sxs-lookup"><span data-stu-id="843da-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="843da-110">Report riepilogo conteggi chiamate</span><span class="sxs-lookup"><span data-stu-id="843da-110">Call Count Summary Report</span></span>

<span data-ttu-id="843da-111">La pagina principale (Call Count Summary) fornisce immediatamente il numero di sessioni di condivisione dello schermo, video e audio negli ultimi 30 e 90 giorni, come specificato nel titolo della sezione.</span><span class="sxs-lookup"><span data-stu-id="843da-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="843da-112">I dati inizialmente visualizzati sono per l'intera organizzazione e possono essere filtrati usando le opzioni del menu a discesa del filtro dei dati sul lato sinistro della pagina.</span><span class="sxs-lookup"><span data-stu-id="843da-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![Screenshot: Report sull'utilizzo dei team](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="843da-114">A destra degli elenchi a discesa del filtro dei dati, il numero di chiamate per tipo di contenuto è suddiviso in una visualizzazione interna/esterna negli ultimi trenta giorni.</span><span class="sxs-lookup"><span data-stu-id="843da-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="843da-115">Nella schermata precedente si può vedere che ci sono più chiamate in corso da posizioni esterne all'organizzazione, il che ha senso considerando l'attuale ambiente globale.</span><span class="sxs-lookup"><span data-stu-id="843da-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="843da-116">![Screenshot: Report sull'utilizzo dei team](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="843da-116">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="843da-117">A destra della casella media type count, abbiamo il Numero mensile di chiamate per Tipo di supporto per gli ultimi 90 giorni.</span><span class="sxs-lookup"><span data-stu-id="843da-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="843da-118">È possibile passare il mouse su ogni colonna e tipo di supporto per visualizzare il conteggio per il mese precedente o per il mese corrente fino a oggi, fornendo informazioni sulla tendenza di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="843da-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="843da-119">![Screenshot: Report sull'utilizzo dei team](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="843da-119">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report3.png)</span></span>
 

1. <span data-ttu-id="843da-120">Il grafico centrale funziona come il grafico di 90 giorni, ma fornisce una visualizzazione dell'utilizzo giornaliero per gli ultimi 30 giorni e consente all'utente di fare clic con il pulsante destro del mouse ed eseguire il drill-down dei dettagli per un giorno specifico.</span><span class="sxs-lookup"><span data-stu-id="843da-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="843da-121">![Screenshot: Report sull'utilizzo dei team](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="843da-121">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="843da-122">Nella sezione in basso a sinistra della pagina è presente una tabella che fornisce i valori totali per ogni tipo di supporto nell'ultimo anno.</span><span class="sxs-lookup"><span data-stu-id="843da-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="843da-123">![Screenshot: Screenshot dei report sull'utilizzo dei ](media/CQD-teams-utilization-report5.png) ![ team: Report sull'utilizzo dei team](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="843da-123">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report5.png) ![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report6.png)</span></span>   

<span data-ttu-id="843da-124">A destra della tabella, un grafico a barre mostra i clienti con il maggior utilizzo (chiamate/flussi) degli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="843da-124">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="843da-125">![Screenshot: Report sull'utilizzo dei team](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="843da-125">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report7.png)</span></span>

<span data-ttu-id="843da-126">L'ultimo set di grafici di questa pagina mostra ogni tipo di contenuto multimediale singolarmente, con un'analisi che mostra l'utilizzo di conferenze e P2P.</span><span class="sxs-lookup"><span data-stu-id="843da-126">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="843da-127">I grafici seguenti mostrano che il numero di utilizzo delle conferenze è notevolmente superiore rispetto alla P2P.</span><span class="sxs-lookup"><span data-stu-id="843da-127">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="843da-128">![Screenshot: Report sull'utilizzo dei team](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="843da-128">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="843da-129">Report riepilogo minuti audio</span><span class="sxs-lookup"><span data-stu-id="843da-129">Audio Minutes Summary Report</span></span>

<span data-ttu-id="843da-130">Nel report Sull'utilizzo dei minuti audio, il consumo totale dei minuti viene fornito da diverse visualizzazioni.</span><span class="sxs-lookup"><span data-stu-id="843da-130">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="843da-131">Accanto ai filtri dei dati viene visualizzato un riepilogo dei trenta giorni con l'uso semplice delle caselle di testo.</span><span class="sxs-lookup"><span data-stu-id="843da-131">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="843da-132">Il numero più alto mostra il totale di trenta giorni, con le suddivisioni interne ed esterne al di sotto.</span><span class="sxs-lookup"><span data-stu-id="843da-132">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![Screenshot: Report sull'utilizzo dei team](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="843da-134">Il grafico a barre in alto a destra offre una visualizzazione annuale dell'utilizzo dell'audio delle conferenze.</span><span class="sxs-lookup"><span data-stu-id="843da-134">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="843da-135">Passare il puntatore del mouse nel mese per visualizzare i minuti audio della conferenza.</span><span class="sxs-lookup"><span data-stu-id="843da-135">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="843da-136">Per mostrare la differenza nel P2P e nell'audio della conferenza, il grafico in basso a sinistra prende tutto l'audio dell'ultimo anno e lo suddivide tra i due tipi.</span><span class="sxs-lookup"><span data-stu-id="843da-136">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

![Screenshot: Report sull'utilizzo dei team](media/CQD-teams-utilization-report10.png)

<span data-ttu-id="843da-138">L'ultimo grafico della pagina Minuti audio mostra l'utilizzo dei minuti audio su una mappa globale sovrapposta.</span><span class="sxs-lookup"><span data-stu-id="843da-138">The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="843da-139">Questo grafico funziona solo se i dati dell'edificio e della subnet vengono caricati nel tenant.</span><span class="sxs-lookup"><span data-stu-id="843da-139">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="843da-140">È possibile eseguire il drill-down della sovrapposizione dei grafici a torta sulla mappa, fornendo successivamente l'uso dell'audio locale.</span><span class="sxs-lookup"><span data-stu-id="843da-140">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![Screenshot: Report sull'utilizzo dei team](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a><span data-ttu-id="843da-142">Funzionalità drill-through</span><span class="sxs-lookup"><span data-stu-id="843da-142">Drill-through capabilities</span></span>

<span data-ttu-id="843da-143">Come accennato in precedenza, gli utenti possono eseguire il drill-down dei report sull'utilizzo giornaliero e locale.</span><span class="sxs-lookup"><span data-stu-id="843da-143">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="843da-144">Utilizzo giornaliero</span><span class="sxs-lookup"><span data-stu-id="843da-144">Daily Usage</span></span>

<span data-ttu-id="843da-145">Il report Utilizzo giornaliero consente a un amministratore di identificare i periodi di picco del consumo nell'intera giornata.</span><span class="sxs-lookup"><span data-stu-id="843da-145">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="843da-146">Oltre all'utilizzo, siamo anche in grado di acquisire il feedback generale degli utenti per quella giornata.</span><span class="sxs-lookup"><span data-stu-id="843da-146">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![Screenshot: Report sull'utilizzo dei team](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="843da-148">Il report Utilizzo giornaliero mostra il numero di condivisioni audio, video e schermo per il giorno selezionato con la possibilità di distinguere tra connettività interna ed esterna.</span><span class="sxs-lookup"><span data-stu-id="843da-148">The Daily usage report displays the number of Audio, Video and Screen shares for the selected day with the added ability to differentiate between internal and external connectivity.</span></span> <span data-ttu-id="843da-149">La suddivisione di conferenze e peer-to-peer si trova a destra immediata della casella totale della modalità.</span><span class="sxs-lookup"><span data-stu-id="843da-149">A Conference and Peer to Peer breakdown is to the immediate right of the modality total box.</span></span> <span data-ttu-id="843da-150">Nell'angolo in alto a destra del report è disponibile un elenco delle conferenze con il proprio ID associato e i partecipanti della giornata.</span><span class="sxs-lookup"><span data-stu-id="843da-150">The top right of the report provides a list of conferences with their associated ID and participants for the day.</span></span> <span data-ttu-id="843da-151">L'elenco delle conferenze fornisce un ulteriore drill-down per il report Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="843da-151">The conference list provides an additional drill down to the Conference Details report as well.</span></span> <span data-ttu-id="843da-152">ELEMENTO GRAFICO SOSTITUISCI</span><span class="sxs-lookup"><span data-stu-id="843da-152">REPLACE GRAPHIC</span></span>

![Screenshot: Report sull'utilizzo dei team](media/CQD-teams-utilization-report13.png)

<span data-ttu-id="843da-154">Il grafico a barre nell'area centrale consente all'utente di identificare i periodi di picco del consumo nell'intera giornata.</span><span class="sxs-lookup"><span data-stu-id="843da-154">The bar graph in the center area allows the user to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="843da-155">Gli utenti possono eseguire il drill-down fino all'ora rappresentata nel grafico che presenterà il report Elenco utenti per l'ora.</span><span class="sxs-lookup"><span data-stu-id="843da-155">Users may drill down into the hour represented on the graph which will present the User List report for the hour.</span></span>

<span data-ttu-id="843da-156">A destra del grafico a barre, il feedback dell'utente è presentato in formato visivo.</span><span class="sxs-lookup"><span data-stu-id="843da-156">To the right of the bar graph, User Feedback is presented in a visual format.</span></span> <span data-ttu-id="843da-157">Anche se il valutazione dell'utente può essere soggettiva, fornisce informazioni approfondite che possono essere usate per identificare i potenziali problemi.</span><span class="sxs-lookup"><span data-stu-id="843da-157">While user sentiment can be subjective, it does provide insight that can be used to identify potential issues.</span></span>

<span data-ttu-id="843da-158">La tabella inferiore fornisce un intervallo di metriche per il giorno.</span><span class="sxs-lookup"><span data-stu-id="843da-158">The bottom table provides a range of metrics for the day.</span></span> <span data-ttu-id="843da-159">Le percentuali di scarsa qualità e le percentuali di errore possono fornire a un amministratore potenziali aree di miglioramento.</span><span class="sxs-lookup"><span data-stu-id="843da-159">Poor percentages along with failure rates can provide an administrator with potential areas of improvement.</span></span> <span data-ttu-id="843da-160">Ogni ora può anche essere selezionata singolarmente, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="843da-160">Each hour can also be selected individually as shown below.</span></span>

<span data-ttu-id="843da-161">Questi dati possono essere usati per identificare le aree geografiche che hanno problemi durante i periodi di picco del consumo.</span><span class="sxs-lookup"><span data-stu-id="843da-161">This data can be used to identify regions having problems during peak consumption times.</span></span>


<span data-ttu-id="843da-162">Fare clic sulla colonna del giorno per visualizzare le metriche per quell'ora.</span><span class="sxs-lookup"><span data-stu-id="843da-162">Click on the column for that day to display metrics for that hour.</span></span>
<span data-ttu-id="843da-163">![Screenshot: Report sull'utilizzo dei team](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="843da-163">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report14.png)</span></span>
  
  1.  <span data-ttu-id="843da-164">La tabella sotto il grafico visualizza le metriche per quell'ora.</span><span class="sxs-lookup"><span data-stu-id="843da-164">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="843da-165">Può essere ordinato in base a qualsiasi intestazione di colonna; Tuttavia, siamo interessati a trovare aree problematiche.</span><span class="sxs-lookup"><span data-stu-id="843da-165">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
    ![Screenshot: Report sull'utilizzo dei team](media/CQD-teams-utilization-report15.png)
    
  2.  <span data-ttu-id="843da-167">Durante questo intervallo di tempo, l'area IND sta riscontrando prestazioni scadenti durante le conferenze.</span><span class="sxs-lookup"><span data-stu-id="843da-167">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="843da-168">Successivamente, i report QER di CQD Microsoft possono essere usati per limitare la posizione problematica quando viene identificata l'area geografica e l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="843da-168">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="conference-details"></a><span data-ttu-id="843da-169">Dettagli conferenza</span><span class="sxs-lookup"><span data-stu-id="843da-169">Conference Details</span></span>

<span data-ttu-id="843da-170">Il report Dettagli conferenza fornisce informazioni aggiuntive sulle riunioni, dall'elenco dei partecipanti, ai tipi multimediali usati durante la sessione.</span><span class="sxs-lookup"><span data-stu-id="843da-170">The Conference Details report provides additional insight for meetings, from an attendee list, to the media types used during the session.</span></span>

<span data-ttu-id="843da-171">Fai clic con il pulsante destro del mouse su una conferenza, sulla barra degli ID conferenza nella pagina Utilizzo giornaliero, per visualizzare i dettagli della conferenza.</span><span class="sxs-lookup"><span data-stu-id="843da-171">Right click a conference the participant bar in the conference ID chart on the Daily usage page to drill down into the conference details.</span></span>

![Screenshot: Report sull'utilizzo dei team](media/CQD-teams-utilization-report24.png)

![Screenshot: Report sull'utilizzo dei team](media/CQD-teams-utilization-report25.png)
  

<span data-ttu-id="843da-174">Nella tabella inferiore sono mostrati i partecipanti alla conferenza e tutte le informazioni pertinenti fino alla perdita di pacchetti e al jitter per agevolare le possibili azioni di risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="843da-174">We can see the participants in the conference as well as all the pertinent information down to packet loss and jitter to assist with potential troubleshooting efforts in the bottom table.</span></span>

![Screenshot: Report sull'utilizzo dei team](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a><span data-ttu-id="843da-176">Regional Audio Details</span><span class="sxs-lookup"><span data-stu-id="843da-176">Regional Audio Details</span></span>

<span data-ttu-id="843da-177">Il drill-down di Dettagli audio internazionali mostra in modo specifico l'utilizzo dei minuti audio per l'area selezionata.</span><span class="sxs-lookup"><span data-stu-id="843da-177">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="843da-178">Gli utenti con accesso a CQD possono vedere le tendenze di utilizzo sia per il P2P che per l'audio della conferenza nell'area geografica selezionata.</span><span class="sxs-lookup"><span data-stu-id="843da-178">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="843da-179">Nella pagina Riepilogo numero chiamate eseguire il drill-through come area specifica della tabella.</span><span class="sxs-lookup"><span data-stu-id="843da-179">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="843da-180">![Screenshot: Report sull'utilizzo dei team](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="843da-180">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="843da-181">Selezionare la riga per cui sono necessarie informazioni aggiuntive sull'area.</span><span class="sxs-lookup"><span data-stu-id="843da-181">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="843da-182">![Screenshot: Report sull'utilizzo dei team](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="843da-182">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="843da-183">Le tendenze dei dati mostrano un numero significativo di minuti utilizzati nella rete interna, con conferenze molto più rilevanti per l'uso P2P.</span><span class="sxs-lookup"><span data-stu-id="843da-183">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="843da-184">![Screenshot: Report sull'utilizzo dei team](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="843da-184">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="843da-185">La tendenza audio regionale può essere usata per mostrare in che modo gli utenti sono influenzati dalle influenza esterne nel mondo.</span><span class="sxs-lookup"><span data-stu-id="843da-185">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="843da-186">In particolare, in questo momento, l'utilizzo esterno delle aree EMEA e APAC dovrebbe aumentare con le persone a cui viene chiesto di lavorare in remoto.</span><span class="sxs-lookup"><span data-stu-id="843da-186">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>


### <a name="user-list"></a><span data-ttu-id="843da-187">Elenco utenti</span><span class="sxs-lookup"><span data-stu-id="843da-187">User List</span></span>

<span data-ttu-id="843da-188">Il drill-down dell'Elenco utenti fornisce, come ci si può aspettare, informazioni specifiche dell'utente per un'ora specifica selezionata dalla persona che visualizza il report.</span><span class="sxs-lookup"><span data-stu-id="843da-188">The User List drill down provides, as one might expect, user specific information for a specific hour selected by the person viewing the report.</span></span> <span data-ttu-id="843da-189">Il report Elenco utenti è accessibile tramite un drill-down nel grafico Tendenze orarie nel report Utilizzo giornaliero.</span><span class="sxs-lookup"><span data-stu-id="843da-189">The User List report is accessible through a drill down in the Hourly Trends graph on the Daily Usage report.</span></span> <span data-ttu-id="843da-190">Fare clic con il pulsante destro del mouse sull'ora per cui sono necessarie informazioni aggiuntive e selezionare Drill-through ed Elenco utenti, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="843da-190">Right click on the hour additional information is needed for and select Drill through and User List, as shown below.</span></span>

![Screenshot: Report sull'utilizzo dei team](media/CQD-teams-utilization-report19.png)

<span data-ttu-id="843da-192">Il report Elenco utenti mostra la connettività interna/esterna tramite il grafico ad anello nella parte superiore centrale della pagina.</span><span class="sxs-lookup"><span data-stu-id="843da-192">The User List report shows internal/external connectivity through the doughnut chart in the top center of the page.</span></span> <span data-ttu-id="843da-193">Come si può vedere, la partecipazione dall'esterno della rete aziendale è notevole nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="843da-193">We can see that there is a large amount of participation from Outside the corporate network in the below image.</span></span>

<span data-ttu-id="843da-194">L'angolo in alto a destra del grafico mostra il numero di chiamate effettuate da ogni utente nell'ora specifica.</span><span class="sxs-lookup"><span data-stu-id="843da-194">The top right of the graph shows the number of calls made by each user within that hour.</span></span>

![Screenshot: Report sull'utilizzo dei team](media/CQD-teams-utilization-report20.png)

<span data-ttu-id="843da-196">La tabella inferiore contiene informazioni dettagliate per le sessioni a cui ogni utente ha partecipato durante quell'ora.</span><span class="sxs-lookup"><span data-stu-id="843da-196">The bottom table provides detailed information for the sessions each user participated in during that hour.</span></span> <span data-ttu-id="843da-197">La colonna Tipo errore è utile per determinare la causa dell'eliminazione di una chiamata.</span><span class="sxs-lookup"><span data-stu-id="843da-197">The Failure Type column is useful in determining what caused a call to drop.</span></span> <span data-ttu-id="843da-198">Le colonne Dispositivo di acquisizione e rendering sono utili per identificare il motivo per cui una chiamata ha segnalato una qualità scarsa.</span><span class="sxs-lookup"><span data-stu-id="843da-198">The Capture and Render Device columns are useful in identifying why a call was reported having poor quality.</span></span>


## <a name="related-topics"></a><span data-ttu-id="843da-199">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="843da-199">Related topics</span></span>

[<span data-ttu-id="843da-200">Dimensioni e misure disponibili in Dashboard Qualità della chiamata</span><span class="sxs-lookup"><span data-stu-id="843da-200">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="843da-201">Classificazione del flusso in Dashboard Qualità della chiamata</span><span class="sxs-lookup"><span data-stu-id="843da-201">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="843da-202">Configurazione di Skype for Business Call Analytics</span><span class="sxs-lookup"><span data-stu-id="843da-202">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="843da-203">Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate</span><span class="sxs-lookup"><span data-stu-id="843da-203">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="843da-204">Analisi delle chiamate e Dashboard Qualità della chiamata</span><span class="sxs-lookup"><span data-stu-id="843da-204">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

[<span data-ttu-id="843da-205">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="843da-205">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
 