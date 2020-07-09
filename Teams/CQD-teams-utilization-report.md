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
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Usare i report di Power BI per l'utilizzo dei team per accedere ai dati di Microsoft teams Call Quality Dashboard (Call Quality Dashboard) per tenere traccia dell'utilizzo di Microsoft teams nell'organizzazione.
ms.openlocfilehash: bd1a95a683da881a78acb5d4849bba0ac55f4898
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085582"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="5ae41-103">Visualizzare l'utilizzo di Microsoft teams in Power BI usando i dati di Call Quality dashboard</span><span class="sxs-lookup"><span data-stu-id="5ae41-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="5ae41-104">Novità di marzo 2020 è stato aggiunto un report di utilizzo dei team ai [modelli di query di Power bi scaricabili per Call Quality dashboard](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="5ae41-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="5ae41-105">I nuovi report di utilizzo dei team consentono di vedere come (e quanto) gli utenti usano Microsoft teams accedendo ai dati di Call Quality Dashboard (teams Call Quality Dashboard).</span><span class="sxs-lookup"><span data-stu-id="5ae41-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams by accessing Teams Call Quality Dashboard (CQD) data.</span></span> <span data-ttu-id="5ae41-106">Questi report sono progettati per essere una posizione centralizzata che consente agli amministratori e alle aziende leader di accedere rapidamente a questi dati.</span><span class="sxs-lookup"><span data-stu-id="5ae41-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="5ae41-107">Il report utilizzo di Power BI di teams è costituito da due report principali: riepilogo delle **[chiamate](#call-count-summary-report)** e riepilogo dei **[minuti audio](#audio-minutes-summary-report)**.</span><span class="sxs-lookup"><span data-stu-id="5ae41-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="5ae41-108">L' [uso quotidiano](#daily-usage), i [dettagli audio regionali](#regional-audio-details), i [Dettagli delle conferenze](#conference-details) e i report [degli elenchi di utenti](#user-list) entrano in gioco quando un utente sfrutta i rapporti di drill-down descritti nelle descrizioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="5ae41-108">The [Daily Usage](#daily-usage), [Regional Audio Details](#regional-audio-details), [Conference Details](#conference-details) and [User List](#user-list) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="5ae41-109">I dati di compilazione e subnet devono essere popolati per consentire funzionalità di filtro di rete e regionali.</span><span class="sxs-lookup"><span data-stu-id="5ae41-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="5ae41-110">Report riepilogo Conteggio chiamate</span><span class="sxs-lookup"><span data-stu-id="5ae41-110">Call Count Summary Report</span></span>

<span data-ttu-id="5ae41-111">La pagina principale (riepilogo Conteggio chiamate) fornisce immediatamente il numero di sessioni di condivisione audio, video e dello schermo negli ultimi 30 e 90 giorni, come indicato nel titolo della sezione.</span><span class="sxs-lookup"><span data-stu-id="5ae41-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="5ae41-112">I dati visualizzati inizialmente sono per l'intera organizzazione e possono essere filtrati usando le opzioni di elenco a discesa del filtro delle informazioni sul lato sinistro della pagina.</span><span class="sxs-lookup"><span data-stu-id="5ae41-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![Screenshot: report sull'utilizzo di Teams](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="5ae41-114">A destra dell'elenco a discesa del filtro dei dati, il numero di chiamate per tipo di elemento multimediale è suddiviso in una visualizzazione interna/esterna negli ultimi trenta giorni.</span><span class="sxs-lookup"><span data-stu-id="5ae41-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="5ae41-115">Possiamo vedere attraverso lo screenshot sopra che ci sono più chiamate che si verificano da posizioni fuori dall'organizzazione, il che ha senso considerando l'ambiente globale corrente.</span><span class="sxs-lookup"><span data-stu-id="5ae41-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="5ae41-116">![Screenshot: report sull'utilizzo di Teams](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="5ae41-116">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="5ae41-117">A destra della casella Conteggio tipi di elementi multimediali è presente il conteggio chiamate mensili per tipo di elemento multimediale per gli ultimi 90 giorni.</span><span class="sxs-lookup"><span data-stu-id="5ae41-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="5ae41-118">Ogni colonna e tipo di elemento multimediale può essere posizionato sopra per visualizzare il conteggio per un mese precedente o il mese corrente fino a data, fornendo informazioni sulle tendenze di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="5ae41-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="5ae41-119">![Screenshot: report sull'utilizzo di Teams](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="5ae41-119">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report3.png)</span></span>
 

1. <span data-ttu-id="5ae41-120">Il grafico centrale funziona come il grafico di 90 giorni, ma offre una visualizzazione giornaliera degli ultimi 30 giorni e consente a un utente di fare clic con il pulsante destro del mouse e di eseguire il drill-down nei dettagli per un giorno specifico.</span><span class="sxs-lookup"><span data-stu-id="5ae41-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="5ae41-121">![Screenshot: report sull'utilizzo di Teams](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="5ae41-121">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="5ae41-122">Nella sezione in basso a sinistra della pagina è disponibile una tabella che fornisce i valori totali per ogni tipo di elemento multimediale dello scorso anno.</span><span class="sxs-lookup"><span data-stu-id="5ae41-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="5ae41-123">![Screenshot: report sull'utilizzo di teams ](media/CQD-teams-utilization-report5.png) ![ screenshot: report sull'utilizzo di Teams](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="5ae41-123">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report5.png) ![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report6.png)</span></span>   

<span data-ttu-id="5ae41-124">A destra della tabella, un grafico a barre Mostra i client con la maggior parte dei casi (chiamate/flussi) per gli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="5ae41-124">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="5ae41-125">![Screenshot: report sull'utilizzo di Teams](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="5ae41-125">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report7.png)</span></span>

<span data-ttu-id="5ae41-126">L'ultimo set di grafici per questa pagina mostra ogni tipo di elemento multimediale individualmente, con una ripartizione che mostra l'uso di conferenze e P2P.</span><span class="sxs-lookup"><span data-stu-id="5ae41-126">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="5ae41-127">I grafici seguenti mostrano che c'è un numero significativamente più elevato di utilizzo delle conferenze rispetto al P2P.</span><span class="sxs-lookup"><span data-stu-id="5ae41-127">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="5ae41-128">![Screenshot: report sull'utilizzo di Teams](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="5ae41-128">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="5ae41-129">Report di riepilogo minuti audio</span><span class="sxs-lookup"><span data-stu-id="5ae41-129">Audio Minutes Summary Report</span></span>

<span data-ttu-id="5ae41-130">Nel report sull'utilizzo dei minuti audio l'utilizzo totale dei minuti viene fornito tramite alcune visualizzazioni diverse.</span><span class="sxs-lookup"><span data-stu-id="5ae41-130">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="5ae41-131">Il riepilogo dell'utilizzo di trenta giorni viene visualizzato accanto ai filtri dei dati come caselle di testo semplici da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="5ae41-131">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="5ae41-132">Il numero superiore mostra il totale di trenta giorni, con guasti interni ed esterni.</span><span class="sxs-lookup"><span data-stu-id="5ae41-132">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![Screenshot: report sull'utilizzo di Teams](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="5ae41-134">Il grafico a barre superiore destro offre una visualizzazione yearlong dell'uso dell'audio per conferenze.</span><span class="sxs-lookup"><span data-stu-id="5ae41-134">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="5ae41-135">Posizionare il puntatore del mouse sul mese per visualizzare i minuti audio della conferenza.</span><span class="sxs-lookup"><span data-stu-id="5ae41-135">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="5ae41-136">Per mostrare la differenza tra il P2P e l'audio per conferenze, il grafico in basso a sinistra prende tutto l'audio per l'anno passato e lo suddivide tra i due tipi.</span><span class="sxs-lookup"><span data-stu-id="5ae41-136">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

![Screenshot: report sull'utilizzo di Teams](media/CQD-teams-utilization-report10.png)

<span data-ttu-id="5ae41-138">Nell'ultimo grafico della pagina minuti audio viene visualizzato l'utilizzo dei minuti audio in una sovrapposizione globale della mappa.</span><span class="sxs-lookup"><span data-stu-id="5ae41-138">The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="5ae41-139">Questo grafico funzionerà solo se i dati di compilazione e subnet vengono caricati nel tenant.</span><span class="sxs-lookup"><span data-stu-id="5ae41-139">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="5ae41-140">È possibile eseguire il drill-down della sovrapposizione del grafico a torta sulla mappa, fornendo in seguito l'utilizzo dell'audio locale.</span><span class="sxs-lookup"><span data-stu-id="5ae41-140">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![Screenshot: report sull'utilizzo di Teams](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a><span data-ttu-id="5ae41-142">Funzionalità di drill-through</span><span class="sxs-lookup"><span data-stu-id="5ae41-142">Drill-through capabilities</span></span>

<span data-ttu-id="5ae41-143">Come indicato in precedenza, gli utenti possono eseguire il drill-up dei report di utilizzo giornalieri e regionali.</span><span class="sxs-lookup"><span data-stu-id="5ae41-143">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="5ae41-144">Uso quotidiano</span><span class="sxs-lookup"><span data-stu-id="5ae41-144">Daily Usage</span></span>

<span data-ttu-id="5ae41-145">Il report utilizzo giornaliero consente a un amministratore di identificare i periodi di consumo di picco nel corso di una giornata.</span><span class="sxs-lookup"><span data-stu-id="5ae41-145">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="5ae41-146">Oltre all'uso, siamo anche in grado di acquisire sentimenti e feedback generali degli utenti per quel giorno.</span><span class="sxs-lookup"><span data-stu-id="5ae41-146">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![Screenshot: report sull'utilizzo di Teams](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="5ae41-148">Nel report utilizzo giornaliero viene visualizzato il numero di condivisioni audio, video e dello schermo per il giorno selezionato, con la possibilità di distinguere tra connettività interna ed esterna.</span><span class="sxs-lookup"><span data-stu-id="5ae41-148">The Daily usage report displays the number of Audio, Video and Screen shares for the selected day with the added ability to differentiate between internal and external connectivity.</span></span> <span data-ttu-id="5ae41-149">Una conferenza e una ripartizione peer-to-peer si trova all'immediata destra della casella totale modalità.</span><span class="sxs-lookup"><span data-stu-id="5ae41-149">A Conference and Peer to Peer breakdown is to the immediate right of the modality total box.</span></span> <span data-ttu-id="5ae41-150">Nell'angolo in alto a destra del report è disponibile un elenco di conferenze con l'ID associato e i partecipanti per il giorno.</span><span class="sxs-lookup"><span data-stu-id="5ae41-150">The top right of the report provides a list of conferences with their associated ID and participants for the day.</span></span> <span data-ttu-id="5ae41-151">L'elenco conferenze offre anche un ulteriore drill-down per il report Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="5ae41-151">The conference list provides an additional drill down to the Conference Details report as well.</span></span> <span data-ttu-id="5ae41-152">SOSTITUISCI ELEMENTO GRAFICO</span><span class="sxs-lookup"><span data-stu-id="5ae41-152">REPLACE GRAPHIC</span></span>

![Screenshot: report sull'utilizzo di Teams](media/CQD-teams-utilization-report13.png)

<span data-ttu-id="5ae41-154">Il grafico a barre nell'area centrale consente all'utente di identificare i periodi di consumo di picco nel corso di una giornata.</span><span class="sxs-lookup"><span data-stu-id="5ae41-154">The bar graph in the center area allows the user to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="5ae41-155">Gli utenti possono eseguire il drill-down nell'ora rappresentata nel grafico che presenterà il rapporto elenco utenti per l'ora.</span><span class="sxs-lookup"><span data-stu-id="5ae41-155">Users may drill down into the hour represented on the graph which will present the User List report for the hour.</span></span>

<span data-ttu-id="5ae41-156">A destra del grafico a barre, il feedback degli utenti viene presentato in un formato visivo.</span><span class="sxs-lookup"><span data-stu-id="5ae41-156">To the right of the bar graph, User Feedback is presented in a visual format.</span></span> <span data-ttu-id="5ae41-157">Mentre il sentimento degli utenti può essere soggettivo, offre informazioni che possono essere usate per identificare potenziali problemi.</span><span class="sxs-lookup"><span data-stu-id="5ae41-157">While user sentiment can be subjective, it does provide insight that can be used to identify potential issues.</span></span>

<span data-ttu-id="5ae41-158">La tabella inferiore include un intervallo di metriche per il giorno.</span><span class="sxs-lookup"><span data-stu-id="5ae41-158">The bottom table provides a range of metrics for the day.</span></span> <span data-ttu-id="5ae41-159">Le percentuali scarse insieme alle tariffe di errore possono essere fornite da un amministratore con potenziali aree di miglioramento.</span><span class="sxs-lookup"><span data-stu-id="5ae41-159">Poor percentages along with failure rates can provide an administrator with potential areas of improvement.</span></span> <span data-ttu-id="5ae41-160">Ogni ora può essere selezionata anche singolarmente, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="5ae41-160">Each hour can also be selected individually as shown below.</span></span>

<span data-ttu-id="5ae41-161">Questi dati possono essere usati per identificare le aree che hanno problemi durante i tempi di consumo massimo.</span><span class="sxs-lookup"><span data-stu-id="5ae41-161">This data can be used to identify regions having problems during peak consumption times.</span></span>


<span data-ttu-id="5ae41-162">Fare clic sulla colonna per il giorno in cui visualizzare le metriche per l'ora.</span><span class="sxs-lookup"><span data-stu-id="5ae41-162">Click on the column for that day to display metrics for that hour.</span></span>
<span data-ttu-id="5ae41-163">![Screenshot: report sull'utilizzo di Teams](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="5ae41-163">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report14.png)</span></span>
  
  1.  <span data-ttu-id="5ae41-164">La tabella sotto il grafico visualizzerà le metriche per l'ora.</span><span class="sxs-lookup"><span data-stu-id="5ae41-164">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="5ae41-165">Questa operazione può essere ordinata in base a qualsiasi intestazione di colonna. Tuttavia, ci interesserebbe trovare aree problematiche.</span><span class="sxs-lookup"><span data-stu-id="5ae41-165">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
    ![Screenshot: report sull'utilizzo di Teams](media/CQD-teams-utilization-report15.png)
    
  2.  <span data-ttu-id="5ae41-167">Vediamo che l'area IND sta vivendo scarse prestazioni video in conferenze durante questo lasso di tempo.</span><span class="sxs-lookup"><span data-stu-id="5ae41-167">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="5ae41-168">In seguito, è possibile usare i report Microsoft Call Quality dashboard QER per limitare la posizione problematica in cui l'area geografica e l'intervallo di tempo sono stati identificati.</span><span class="sxs-lookup"><span data-stu-id="5ae41-168">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="conference-details"></a><span data-ttu-id="5ae41-169">Dettagli conferenza</span><span class="sxs-lookup"><span data-stu-id="5ae41-169">Conference Details</span></span>

<span data-ttu-id="5ae41-170">Il report Dettagli conferenza offre ulteriori informazioni sulle riunioni, da un elenco di partecipanti, ai tipi di elementi multimediali usati durante la sessione.</span><span class="sxs-lookup"><span data-stu-id="5ae41-170">The Conference Details report provides additional insight for meetings, from an attendee list, to the media types used during the session.</span></span>

<span data-ttu-id="5ae41-171">Fare clic con il pulsante destro del mouse su una conferenza nella barra dei partecipanti nel grafico ID conferenza nella pagina uso giornaliero per eseguire il drill-down nei dettagli della conferenza.</span><span class="sxs-lookup"><span data-stu-id="5ae41-171">Right click a conference the participant bar in the conference ID chart on the Daily usage page to drill down into the conference details.</span></span>

![Screenshot: report sull'utilizzo di Teams](media/CQD-teams-utilization-report24.png)

![Screenshot: report sull'utilizzo di Teams](media/CQD-teams-utilization-report25.png)
  

<span data-ttu-id="5ae41-174">Possiamo vedere i partecipanti alla conferenza, nonché tutte le informazioni pertinenti fino a perdita di pacchetti e jitter per facilitare gli sforzi possibili per la risoluzione dei problemi nella tabella inferiore.</span><span class="sxs-lookup"><span data-stu-id="5ae41-174">We can see the participants in the conference as well as all the pertinent information down to packet loss and jitter to assist with potential troubleshooting efforts in the bottom table.</span></span>

![Screenshot: report sull'utilizzo di Teams](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a><span data-ttu-id="5ae41-176">Dettagli audio internazionali</span><span class="sxs-lookup"><span data-stu-id="5ae41-176">Regional Audio Details</span></span>

<span data-ttu-id="5ae41-177">Il drill-down dei dettagli audio internazionali Mostra in modo specifico l'utilizzo dei minuti audio per l'area selezionata.</span><span class="sxs-lookup"><span data-stu-id="5ae41-177">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="5ae41-178">Gli utenti con accesso a Call Quality dashboard possono vedere le tendenze di utilizzo per l'audio sia P2P che congressuale all'interno dell'area selezionata.</span><span class="sxs-lookup"><span data-stu-id="5ae41-178">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="5ae41-179">Nella pagina Riepilogo conteggio chiamate eseguire il drill-through come area specifica tramite la tabella.</span><span class="sxs-lookup"><span data-stu-id="5ae41-179">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="5ae41-180">![Screenshot: report sull'utilizzo di Teams](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="5ae41-180">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="5ae41-181">Selezionare la riga con l'area geografica in cui sono necessarie altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="5ae41-181">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="5ae41-182">![Screenshot: report sull'utilizzo di Teams](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="5ae41-182">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="5ae41-183">Le tendenze dei dati mostrano un numero significativo di minuti usati nella rete interna, con i servizi di conferenza che superano l'uso P2P.</span><span class="sxs-lookup"><span data-stu-id="5ae41-183">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="5ae41-184">![Screenshot: report sull'utilizzo di Teams](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="5ae41-184">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="5ae41-185">La tendenza audio locale può essere usata per mostrare in che modo gli utenti hanno un impatto sulle influenze esterne nel mondo.</span><span class="sxs-lookup"><span data-stu-id="5ae41-185">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="5ae41-186">In particolare, in questo momento, ci si aspetterebbe di vedere l'uso esterno per le aree EMEA e APAC per aumentare le persone che hanno chiesto di lavorare in remoto.</span><span class="sxs-lookup"><span data-stu-id="5ae41-186">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>


### <a name="user-list"></a><span data-ttu-id="5ae41-187">Elenco utenti</span><span class="sxs-lookup"><span data-stu-id="5ae41-187">User List</span></span>

<span data-ttu-id="5ae41-188">Il drill-down elenco utenti offre, come ci si potrebbe aspettare, informazioni specifiche dell'utente per un'ora specifica selezionata dalla persona che Visualizza il report.</span><span class="sxs-lookup"><span data-stu-id="5ae41-188">The User List drill down provides, as one might expect, user specific information for a specific hour selected by the person viewing the report.</span></span> <span data-ttu-id="5ae41-189">Il report elenco utenti è accessibile tramite drill-down nel grafico tendenze orarie nel report utilizzo giornaliero.</span><span class="sxs-lookup"><span data-stu-id="5ae41-189">The User List report is accessible through a drill down in the Hourly Trends graph on the Daily Usage report.</span></span> <span data-ttu-id="5ae41-190">Fare clic con il pulsante destro del mouse sull'ora sono necessarie altre informazioni per selezionare drill-through e elenco utenti, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="5ae41-190">Right click on the hour additional information is needed for and select Drill through and User List, as shown below.</span></span>

![Screenshot: report sull'utilizzo di Teams](media/CQD-teams-utilization-report19.png)

<span data-ttu-id="5ae41-192">Il report elenco utenti Mostra la connettività interna/esterna tramite il grafico ad anello nel centro superiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="5ae41-192">The User List report shows internal/external connectivity through the doughnut chart in the top center of the page.</span></span> <span data-ttu-id="5ae41-193">Possiamo vedere che c'è una grande quantità di partecipazione dall'esterno della rete aziendale nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="5ae41-193">We can see that there is a large amount of participation from Outside the corporate network in the below image.</span></span>

<span data-ttu-id="5ae41-194">L'angolo in alto a destra del grafico mostra il numero di chiamate effettuate da ogni utente in quell'ora.</span><span class="sxs-lookup"><span data-stu-id="5ae41-194">The top right of the graph shows the number of calls made by each user within that hour.</span></span>

![Screenshot: report sull'utilizzo di Teams](media/CQD-teams-utilization-report20.png)

<span data-ttu-id="5ae41-196">Nella tabella inferiore vengono fornite informazioni dettagliate sulle sessioni a cui ogni utente ha partecipato durante tale ora.</span><span class="sxs-lookup"><span data-stu-id="5ae41-196">The bottom table provides detailed information for the sessions each user participated in during that hour.</span></span> <span data-ttu-id="5ae41-197">La colonna tipo di errore è utile per determinare cosa ha causato una chiamata a drop.</span><span class="sxs-lookup"><span data-stu-id="5ae41-197">The Failure Type column is useful in determining what caused a call to drop.</span></span> <span data-ttu-id="5ae41-198">Le colonne del dispositivo di acquisizione e rendering sono utili per identificare il motivo per cui una chiamata è stata segnalata con scarsa qualità.</span><span class="sxs-lookup"><span data-stu-id="5ae41-198">The Capture and Render Device columns are useful in identifying why a call was reported having poor quality.</span></span>


## <a name="related-topics"></a><span data-ttu-id="5ae41-199">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5ae41-199">Related topics</span></span>

[<span data-ttu-id="5ae41-200">Dimensioni e misure disponibili in Dashboard Qualità della chiamata</span><span class="sxs-lookup"><span data-stu-id="5ae41-200">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="5ae41-201">Classificazione del flusso in Dashboard Qualità della chiamata</span><span class="sxs-lookup"><span data-stu-id="5ae41-201">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="5ae41-202">Configurazione di Skype for Business Call Analytics</span><span class="sxs-lookup"><span data-stu-id="5ae41-202">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="5ae41-203">Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate</span><span class="sxs-lookup"><span data-stu-id="5ae41-203">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="5ae41-204">Analisi delle chiamate e Dashboard Qualità della chiamata</span><span class="sxs-lookup"><span data-stu-id="5ae41-204">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

[<span data-ttu-id="5ae41-205">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="5ae41-205">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
 