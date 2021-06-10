---
title: Visualizzare Microsoft Teams utilizzo Power BI dati CQD
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
description: Usare i report Teams utilizzo Power BI per accedere ai Microsoft Teams Call Quality Dashboard (CQD) per tenere traccia Microsoft Teams utilizzo dei dati nell'organizzazione.
ms.openlocfilehash: 719f02ce7a5cd36e96ed7fd563c259c6e77764fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095040"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="018b0-103">Visualizzare Microsoft Teams utilizzo Power BI dati CQD</span><span class="sxs-lookup"><span data-stu-id="018b0-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="018b0-104">A marzo 2020 è stato aggiunto un report sull'Teams utilizzo dei dati ai modelli di query Power BI scaricabili [per CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="018b0-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="018b0-105">Questo nuovo Teams di utilizzo consente di vedere come (e quanto) gli utenti usano Microsoft Teams accedendo ai dati del Teams Call Quality Dashboard (CQD).</span><span class="sxs-lookup"><span data-stu-id="018b0-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams by accessing Teams Call Quality Dashboard (CQD) data.</span></span> <span data-ttu-id="018b0-106">Questi report sono pensati per essere una posizione centralizzata a cui sia gli amministratori che i responsabili aziendali possono accedere rapidamente per questi dati.</span><span class="sxs-lookup"><span data-stu-id="018b0-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="018b0-107">Il report Teams utilizzo Power BI è costituito da due report principali: **[Riepilogo](#call-count-summary-report)** conteggio chiamate **[e Riepilogo minuti audio.](#audio-minutes-summary-report)**</span><span class="sxs-lookup"><span data-stu-id="018b0-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="018b0-108">I [report](#daily-usage)Uso giornaliero, Dettagli [](#user-list) [audio](#regional-audio-details) [locali,](#conference-details) Dettagli conferenza ed Elenco utenti vengono riprodotti quando un utente sfrutta i report di drill-down, come indicato nelle descrizioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="018b0-108">The [Daily Usage](#daily-usage), [Regional Audio Details](#regional-audio-details), [Conference Details](#conference-details) and [User List](#user-list) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="018b0-109">I dati relativi a edifici e subnet devono essere popolati per fornire funzionalità di filtro di rete e locali.</span><span class="sxs-lookup"><span data-stu-id="018b0-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="018b0-110">Report riepilogo conteggio chiamate</span><span class="sxs-lookup"><span data-stu-id="018b0-110">Call Count Summary Report</span></span>

<span data-ttu-id="018b0-111">La pagina principale (Riepilogo conteggio chiamate) fornisce immediatamente il numero di sessioni audio, video e di condivisione dello schermo negli ultimi 30 e 90 giorni, come illustrato nel titolo della sezione.</span><span class="sxs-lookup"><span data-stu-id="018b0-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="018b0-112">I dati inizialmente visualizzati sono per l'intera organizzazione e possono essere filtrati usando le opzioni dell'elenco a discesa del filtro dei dati sul lato sinistro della pagina.</span><span class="sxs-lookup"><span data-stu-id="018b0-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![Screenshot: report Teams utilizzo dei dati](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="018b0-114">A destra degli elenchi a discesa del filtro dei dati, il numero di chiamate per tipo di supporto è suddiviso in una visualizzazione interna/esterna negli ultimi trenta giorni.</span><span class="sxs-lookup"><span data-stu-id="018b0-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="018b0-115">È possibile vedere attraverso lo screenshot precedente che ci sono più chiamate provenienti da posizioni esterne all'organizzazione, il che ha senso considerando l'ambiente globale corrente.</span><span class="sxs-lookup"><span data-stu-id="018b0-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="018b0-116">![Screenshot: report Teams utilizzo dei dati](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="018b0-116">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="018b0-117">A destra della casella Conteggio tipi di supporti, è stato selezionato Il numero di chiamate mensili per tipo di supporto per gli ultimi 90 giorni.</span><span class="sxs-lookup"><span data-stu-id="018b0-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="018b0-118">È possibile passare il puntatore del mouse su ogni colonna e tipo di elemento multimediale per visualizzare il conteggio di un mese precedente o del mese corrente fino alla data corrente, fornendo informazioni sulla tendenza di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="018b0-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="018b0-119">![Screenshot: report Teams utilizzo dei dati](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="018b0-119">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report3.png)</span></span>
 

1. <span data-ttu-id="018b0-120">Il grafico centrale funziona come il grafico di 90 giorni, tuttavia offre una visualizzazione di utilizzo giornaliero per gli ultimi 30 giorni e consente a un utente di fare clic con il pulsante destro del mouse ed eseguire il drill-down nei dettagli per un giorno specifico.</span><span class="sxs-lookup"><span data-stu-id="018b0-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="018b0-121">![Screenshot: report Teams utilizzo dei dati](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="018b0-121">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="018b0-122">Nella sezione in basso a sinistra della pagina è presente una tabella che fornisce i valori totali per ogni tipo di supporto nell'ultimo anno.</span><span class="sxs-lookup"><span data-stu-id="018b0-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="018b0-123">![Screenshot: Teams report sull'utilizzo dei ](media/CQD-teams-utilization-report5.png) ![ dati: Teams di utilizzo](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="018b0-123">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report5.png) ![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report6.png)</span></span>   

<span data-ttu-id="018b0-124">A destra della tabella, un grafico a barre mostra i clienti con il maggior utilizzo (chiamate/flussi) degli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="018b0-124">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="018b0-125">![Screenshot: report Teams utilizzo dei dati](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="018b0-125">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report7.png)</span></span>

<span data-ttu-id="018b0-126">L'ultimo set di grafici per questa pagina mostra ogni tipo di elemento multimediale singolarmente, con una suddivisione che mostra l'uso di conferenze e P2P.</span><span class="sxs-lookup"><span data-stu-id="018b0-126">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="018b0-127">I grafici seguenti mostrano che esiste un numero significativamente maggiore di utilizzo delle conferenze rispetto a P2P.</span><span class="sxs-lookup"><span data-stu-id="018b0-127">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="018b0-128">![Screenshot: report Teams utilizzo dei dati](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="018b0-128">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="018b0-129">Report di riepilogo dei minuti audio</span><span class="sxs-lookup"><span data-stu-id="018b0-129">Audio Minutes Summary Report</span></span>

<span data-ttu-id="018b0-130">Nel report Utilizzo minuti audio, l'utilizzo totale dei minuti viene fornito tramite alcune visualizzazioni diverse.</span><span class="sxs-lookup"><span data-stu-id="018b0-130">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="018b0-131">Accanto ai filtri dei dati viene visualizzato il riepilogo dell'utilizzo di 30 giorni, che semplifica l'uso delle caselle di testo.</span><span class="sxs-lookup"><span data-stu-id="018b0-131">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="018b0-132">Il numero superiore mostra il totale di 30 giorni, con le suddivisioni interne ed esterne inferiori.</span><span class="sxs-lookup"><span data-stu-id="018b0-132">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![Screenshot: report Teams utilizzo dei dati](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="018b0-134">Il grafico a barre in alto a destra offre una visualizzazione annuale dell'utilizzo dell'audio della conferenza.</span><span class="sxs-lookup"><span data-stu-id="018b0-134">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="018b0-135">Passare il puntatore del mouse sul mese per visualizzare i minuti audio della conferenza.</span><span class="sxs-lookup"><span data-stu-id="018b0-135">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="018b0-136">Per mostrare la differenza nell'audio P2P e nella conferenza, il grafico in basso a sinistra prende tutto l'audio dell'anno scorso e lo suddivide tra i due tipi.</span><span class="sxs-lookup"><span data-stu-id="018b0-136">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

![Screenshot: report Teams utilizzo dei dati](media/CQD-teams-utilization-report10.png)

<span data-ttu-id="018b0-138">L'ultimo grafico per la pagina Minuti audio mostra l'utilizzo dei minuti audio in una sovrapposizione mappa globale.</span><span class="sxs-lookup"><span data-stu-id="018b0-138">The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="018b0-139">Questo grafico funziona solo se i dati di edificio e subnet vengono caricati nel tenant.</span><span class="sxs-lookup"><span data-stu-id="018b0-139">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="018b0-140">È possibile eseguire il drill-down della sovrapposizione del grafico a torta sulla mappa, fornendo in seguito l'utilizzo dell'audio locale.</span><span class="sxs-lookup"><span data-stu-id="018b0-140">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![Screenshot: report Teams utilizzo dei dati](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a><span data-ttu-id="018b0-142">Funzionalità di drill-through</span><span class="sxs-lookup"><span data-stu-id="018b0-142">Drill-through capabilities</span></span>

<span data-ttu-id="018b0-143">Come accennato in precedenza, gli utenti possono eseguire il drill-down dei report di utilizzo giornalieri e locali.</span><span class="sxs-lookup"><span data-stu-id="018b0-143">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="018b0-144">Utilizzo giornaliero</span><span class="sxs-lookup"><span data-stu-id="018b0-144">Daily Usage</span></span>

<span data-ttu-id="018b0-145">Il report Utilizzo giornaliero consente a un amministratore di identificare i periodi di picco di consumo nel corso di un giorno.</span><span class="sxs-lookup"><span data-stu-id="018b0-145">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="018b0-146">Oltre all'uso, siamo anche in grado di acquisire il feedback e il feedback degli utenti per quel giorno.</span><span class="sxs-lookup"><span data-stu-id="018b0-146">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![Screenshot: report Teams utilizzo dei dati](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="018b0-148">Il report Utilizzo giornaliero visualizza il numero di condivisioni audio, video e dello schermo per il giorno selezionato, con la possibilità di distinguere tra connettività interna ed esterna.</span><span class="sxs-lookup"><span data-stu-id="018b0-148">The Daily usage report displays the number of Audio, Video and Screen shares for the selected day with the added ability to differentiate between internal and external connectivity.</span></span> <span data-ttu-id="018b0-149">Una suddivisione tra conferenze e peer-to-peer è a destra immediata della casella Totale modalità.</span><span class="sxs-lookup"><span data-stu-id="018b0-149">A Conference and Peer to Peer breakdown is to the immediate right of the modality total box.</span></span> <span data-ttu-id="018b0-150">Nell'angolo in alto a destra del report è disponibile un elenco di conferenze con l'ID associato e i partecipanti per la giornata.</span><span class="sxs-lookup"><span data-stu-id="018b0-150">The top right of the report provides a list of conferences with their associated ID and participants for the day.</span></span> <span data-ttu-id="018b0-151">L'elenco delle conferenze fornisce anche un ulteriore drill-down per il report Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="018b0-151">The conference list provides an additional drill down to the Conference Details report as well.</span></span> <span data-ttu-id="018b0-152">SOSTITUISCI ELEMENTO GRAFICO</span><span class="sxs-lookup"><span data-stu-id="018b0-152">REPLACE GRAPHIC</span></span>

![Screenshot: report Teams utilizzo dei dati](media/CQD-teams-utilization-report13.png)

<span data-ttu-id="018b0-154">Il grafico a barre nell'area centrale consente all'utente di identificare i periodi di picco di consumo nel corso di una giornata.</span><span class="sxs-lookup"><span data-stu-id="018b0-154">The bar graph in the center area allows the user to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="018b0-155">Gli utenti possono eseguire il drill-down nell'ora rappresentata nel grafico che presenterà il report Elenco utenti per l'ora.</span><span class="sxs-lookup"><span data-stu-id="018b0-155">Users may drill down into the hour represented on the graph which will present the User List report for the hour.</span></span>

<span data-ttu-id="018b0-156">A destra del grafico a barre, il feedback degli utenti è presentato in un formato visivo.</span><span class="sxs-lookup"><span data-stu-id="018b0-156">To the right of the bar graph, User Feedback is presented in a visual format.</span></span> <span data-ttu-id="018b0-157">Anche se la valutazione degli utenti può essere soggettiva, fornisce informazioni approfondite che possono essere usate per identificare potenziali problemi.</span><span class="sxs-lookup"><span data-stu-id="018b0-157">While user sentiment can be subjective, it does provide insight that can be used to identify potential issues.</span></span>

<span data-ttu-id="018b0-158">La tabella inferiore fornisce un intervallo di metriche per il giorno.</span><span class="sxs-lookup"><span data-stu-id="018b0-158">The bottom table provides a range of metrics for the day.</span></span> <span data-ttu-id="018b0-159">Le percentuali scarse e le percentuali di errore possono fornire a un amministratore potenziali aree di miglioramento.</span><span class="sxs-lookup"><span data-stu-id="018b0-159">Poor percentages along with failure rates can provide an administrator with potential areas of improvement.</span></span> <span data-ttu-id="018b0-160">Ogni ora può essere selezionata anche singolarmente, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="018b0-160">Each hour can also be selected individually as shown below.</span></span>

<span data-ttu-id="018b0-161">Questi dati possono essere usati per identificare le aree in cui si verificano problemi durante i periodi di picco di consumo.</span><span class="sxs-lookup"><span data-stu-id="018b0-161">This data can be used to identify regions having problems during peak consumption times.</span></span>


<span data-ttu-id="018b0-162">Fare clic sulla colonna del giorno per visualizzare le metriche per quell'ora.</span><span class="sxs-lookup"><span data-stu-id="018b0-162">Click on the column for that day to display metrics for that hour.</span></span>
<span data-ttu-id="018b0-163">![Screenshot: report Teams utilizzo dei dati](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="018b0-163">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report14.png)</span></span>
  
  1.  <span data-ttu-id="018b0-164">La tabella sotto il grafico visualizza le metriche per quell'ora.</span><span class="sxs-lookup"><span data-stu-id="018b0-164">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="018b0-165">Può essere ordinato in base a qualsiasi intestazione di colonna. tuttavia, siamo interessati a trovare aree problematiche.</span><span class="sxs-lookup"><span data-stu-id="018b0-165">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
    ![Screenshot: report Teams utilizzo dei dati](media/CQD-teams-utilization-report15.png)
    
  2.  <span data-ttu-id="018b0-167">Vediamo che l'area IND sta riscontrando prestazioni video scarse nelle conferenze durante questo periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="018b0-167">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="018b0-168">Successivamente, i report QER di CQD Microsoft possono essere usati per restringere la posizione problematica quando è stata identificata l'area geografica e l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="018b0-168">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="conference-details"></a><span data-ttu-id="018b0-169">Dettagli conferenza</span><span class="sxs-lookup"><span data-stu-id="018b0-169">Conference Details</span></span>

<span data-ttu-id="018b0-170">Il report Dettagli conferenza fornisce informazioni aggiuntive per le riunioni, da un elenco di partecipanti, ai tipi di elementi multimediali usati durante la sessione.</span><span class="sxs-lookup"><span data-stu-id="018b0-170">The Conference Details report provides additional insight for meetings, from an attendee list, to the media types used during the session.</span></span>

<span data-ttu-id="018b0-171">Fare clic con il pulsante destro del mouse su una conferenza sulla barra dei partecipanti nel grafico dell'ID conferenza nella pagina Utilizzo quotidiano per eseguire il drill-down dei dettagli della conferenza.</span><span class="sxs-lookup"><span data-stu-id="018b0-171">Right click a conference the participant bar in the conference ID chart on the Daily usage page to drill down into the conference details.</span></span>

![Screenshot: report Teams utilizzo dei dati](media/CQD-teams-utilization-report24.png)

![Screenshot: report Teams utilizzo dei dati](media/CQD-teams-utilization-report25.png)
  

<span data-ttu-id="018b0-174">Possiamo vedere i partecipanti alla conferenza, oltre a tutte le informazioni pertinenti fino alla perdita di pacchetti e al jitter, per aiutare con i potenziali tentativi di risoluzione dei problemi nella tabella inferiore.</span><span class="sxs-lookup"><span data-stu-id="018b0-174">We can see the participants in the conference as well as all the pertinent information down to packet loss and jitter to assist with potential troubleshooting efforts in the bottom table.</span></span>

![Screenshot: report Teams utilizzo dei dati](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a><span data-ttu-id="018b0-176">Dettagli audio locali</span><span class="sxs-lookup"><span data-stu-id="018b0-176">Regional Audio Details</span></span>

<span data-ttu-id="018b0-177">Il drill-down Dettagli audio locali mostra in modo specifico l'utilizzo dei minuti audio per l'area selezionata.</span><span class="sxs-lookup"><span data-stu-id="018b0-177">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="018b0-178">Gli utenti che hanno accesso a CQD possono vedere le tendenze di utilizzo sia per l'audio P2P che per la conferenza all'interno dell'area selezionata.</span><span class="sxs-lookup"><span data-stu-id="018b0-178">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="018b0-179">Nella pagina Riepilogo conteggio chiamate eseguire il drill-through come area specifica della tabella.</span><span class="sxs-lookup"><span data-stu-id="018b0-179">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="018b0-180">![Screenshot: report Teams utilizzo dei dati](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="018b0-180">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="018b0-181">Selezionare la riga per cui sono necessarie informazioni aggiuntive sull'area geografica.</span><span class="sxs-lookup"><span data-stu-id="018b0-181">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="018b0-182">![Screenshot: report Teams utilizzo dei dati](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="018b0-182">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="018b0-183">Le tendenze dei dati mostrano un numero significativo di minuti usati nella rete interna, con conferenze che superano di gran lunga l'uso P2P.</span><span class="sxs-lookup"><span data-stu-id="018b0-183">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="018b0-184">![Screenshot: report Teams utilizzo dei dati](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="018b0-184">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="018b0-185">La tendenza audio regionale può essere usata per mostrare in che modo gli utenti sono influenzati da influenze esterne nel mondo.</span><span class="sxs-lookup"><span data-stu-id="018b0-185">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="018b0-186">In particolare, in questo momento, l'utilizzo esterno per le aree EMEA e APAC dovrebbe aumentare con la richiesta di lavorare in remoto.</span><span class="sxs-lookup"><span data-stu-id="018b0-186">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>


### <a name="user-list"></a><span data-ttu-id="018b0-187">Elenco utenti</span><span class="sxs-lookup"><span data-stu-id="018b0-187">User List</span></span>

<span data-ttu-id="018b0-188">Il drill-down elenco utenti fornisce, come ci si potrebbe aspettare, informazioni specifiche dell'utente per un'ora specifica selezionata dalla persona che visualizza il report.</span><span class="sxs-lookup"><span data-stu-id="018b0-188">The User List drill down provides, as one might expect, user specific information for a specific hour selected by the person viewing the report.</span></span> <span data-ttu-id="018b0-189">Il report Elenco utenti è accessibile tramite un drill-down nel grafico Tendenze orarie nel report Utilizzo giornaliero.</span><span class="sxs-lookup"><span data-stu-id="018b0-189">The User List report is accessible through a drill down in the Hourly Trends graph on the Daily Usage report.</span></span> <span data-ttu-id="018b0-190">Fare clic con il pulsante destro del mouse sull'ora per cui sono necessarie altre informazioni e selezionare Drill-through ed Elenco utenti, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="018b0-190">Right click on the hour additional information is needed for and select Drill through and User List, as shown below.</span></span>

![Screenshot: report Teams utilizzo dei dati](media/CQD-teams-utilization-report19.png)

<span data-ttu-id="018b0-192">Il report Elenco utenti mostra la connettività interna/esterna tramite il grafico ad anello nella parte superiore centrale della pagina.</span><span class="sxs-lookup"><span data-stu-id="018b0-192">The User List report shows internal/external connectivity through the doughnut chart in the top center of the page.</span></span> <span data-ttu-id="018b0-193">Nell'immagine seguente è presente una grande quantità di partecipazione dall'esterno della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="018b0-193">We can see that there is a large amount of participation from Outside the corporate network in the below image.</span></span>

<span data-ttu-id="018b0-194">Nell'angolo in alto a destra del grafico viene visualizzato il numero di chiamate effettuate da ogni utente entro quell'ora.</span><span class="sxs-lookup"><span data-stu-id="018b0-194">The top right of the graph shows the number of calls made by each user within that hour.</span></span>

![Screenshot: report Teams utilizzo dei dati](media/CQD-teams-utilization-report20.png)

<span data-ttu-id="018b0-196">La tabella inferiore contiene informazioni dettagliate per le sessioni a cui ogni utente ha partecipato durante quell'ora.</span><span class="sxs-lookup"><span data-stu-id="018b0-196">The bottom table provides detailed information for the sessions each user participated in during that hour.</span></span> <span data-ttu-id="018b0-197">La colonna Tipo errore è utile per determinare cosa ha causato l'eliminazione di una chiamata.</span><span class="sxs-lookup"><span data-stu-id="018b0-197">The Failure Type column is useful in determining what caused a call to drop.</span></span> <span data-ttu-id="018b0-198">Le colonne Acquisizione e Dispositivo di rendering sono utili per identificare il motivo per cui una chiamata è stata segnalata di qualità scarsa.</span><span class="sxs-lookup"><span data-stu-id="018b0-198">The Capture and Render Device columns are useful in identifying why a call was reported having poor quality.</span></span>


## <a name="related-topics"></a><span data-ttu-id="018b0-199">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="018b0-199">Related topics</span></span>

[<span data-ttu-id="018b0-200">Dimensioni e misure disponibili in Dashboard Qualità della chiamata</span><span class="sxs-lookup"><span data-stu-id="018b0-200">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="018b0-201">Classificazione del flusso in Dashboard Qualità della chiamata</span><span class="sxs-lookup"><span data-stu-id="018b0-201">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="018b0-202">Configurazione di Skype for Business Call Analytics</span><span class="sxs-lookup"><span data-stu-id="018b0-202">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="018b0-203">Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate</span><span class="sxs-lookup"><span data-stu-id="018b0-203">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="018b0-204">Analisi delle chiamate e Dashboard Qualità della chiamata</span><span class="sxs-lookup"><span data-stu-id="018b0-204">Call Analytics and Call Quality Dashboard</span></span>](./monitor-call-quality-qos.md)

[<span data-ttu-id="018b0-205">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="018b0-205">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
