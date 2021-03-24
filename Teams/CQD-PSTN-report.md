---
title: Uso del report CQD PSTN Direct Routing
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies, fan.fan
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
description: Usare il report Routing diretto PSTN di Microsoft Teams Call Quality Dashboard (CQD) per monitorare e risolvere i problemi relativi alle chiamate PSTN in Microsoft Teams.
ms.openlocfilehash: f2b63f991f42aa4de9e0e4474137f7f992f95c53
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094980"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="47826-103">Uso del report CQD PSTN Direct Routing</span><span class="sxs-lookup"><span data-stu-id="47826-103">Using the CQD PSTN Direct Routing report</span></span>

<span data-ttu-id="47826-104">Novità di marzo 2020, è stato aggiunto un report di Routing diretto PSTN (Call Quality Dashboard) di Microsoft Teams ai modelli di query di Power BI scaricabili per [CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="47826-104">New in March 2020, we've added a Microsoft Teams Call Quality Dashboard (CQD) PSTN Direct Routing report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="47826-105">Il report CQD PSTN Direct Routing Report (CQD PSTN Direct Routing Report.pbit) consente di comprendere i modelli di utilizzo e la qualità dei servizi PSTN.</span><span class="sxs-lookup"><span data-stu-id="47826-105">The CQD PSTN Direct Routing report (CQD PSTN Direct Routing Report.pbit) helps you understand the usage patterns and quality of your PSTN services.</span></span> <span data-ttu-id="47826-106">Usare questo report per monitorare l'utilizzo del servizio, informazioni sul session border controller (SBC), sul servizio di telefonia, sui parametri di rete e sui dettagli sul rapporto di efficacia della rete.</span><span class="sxs-lookup"><span data-stu-id="47826-106">Use this report to monitor service usage, information about your Session Border Controller (SBC), the telephony service, network parameters, and Network Effectiveness Ratio details.</span></span> <span data-ttu-id="47826-107">Queste informazioni consentono di identificare i problemi, incluso il motivo per cui le chiamate sono in uscita.</span><span class="sxs-lookup"><span data-stu-id="47826-107">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="47826-108">Ad esempio, sarà possibile vedere quando il volume scende o quante chiamate vengono interessate e per quale motivo.</span><span class="sxs-lookup"><span data-stu-id="47826-108">For example, you'll be able to see when volume drops, or how many calls get affected and for what reason.</span></span>


<span data-ttu-id="47826-109">Il report di routing diretto PSTN CQD include quattro sezioni:</span><span class="sxs-lookup"><span data-stu-id="47826-109">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="47826-110">Panoramica di PSTN</span><span class="sxs-lookup"><span data-stu-id="47826-110">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="47826-111">Dettagli servizio</span><span class="sxs-lookup"><span data-stu-id="47826-111">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="47826-112">Rapporto di efficacia della rete</span><span class="sxs-lookup"><span data-stu-id="47826-112">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="47826-113">Parametri di rete</span><span class="sxs-lookup"><span data-stu-id="47826-113">Network Parameters</span></span>](#network-parameters)

## <a name="highlights"></a><span data-ttu-id="47826-114">Highlights</span><span class="sxs-lookup"><span data-stu-id="47826-114">Highlights</span></span>

1. <span data-ttu-id="47826-115">Analizza per tipo di chiamata, SBC, paese chiamante e chiamato</span><span class="sxs-lookup"><span data-stu-id="47826-115">Analyze by call type, SBC, caller and callee country</span></span>

   <span data-ttu-id="47826-116">Il report CQD PSTN Direct Routing aggrega le metriche di affidabilità e utilizzo per tutti gli SBC nel tenant per gli ultimi 7, 30 o 180 giorni (6 mesi).</span><span class="sxs-lookup"><span data-stu-id="47826-116">The CQD PSTN Direct Routing report aggregates reliability and usage metrics for all SBCs on your tenant for the last 7, 30, or 180 days (6 months).</span></span> <span data-ttu-id="47826-117">È possibile analizzare i dati per tipo di chiamata, SBC, paese chiamante e chiamato.</span><span class="sxs-lookup"><span data-stu-id="47826-117">You can analyze data by call type, SBC, caller and callee country.</span></span> <span data-ttu-id="47826-118">Se si è interessati a un determinato SBC o paese, sarà possibile identificare le modifiche alle tendenze nell'intervallo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="47826-118">If you're interested in a particular SBC or country, you'll be able to identify changes in trends over the selected time range.</span></span>
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="Screenshot dei filtri disponibili nel report CQD PSTN Direct Routing":::
   
2. <span data-ttu-id="47826-120">Tenere traccia delle tendenze</span><span class="sxs-lookup"><span data-stu-id="47826-120">Track trends</span></span>

    <span data-ttu-id="47826-121">L'analisi delle tendenze è essenziale quando si cerca di comprendere l'utilizzo e l'affidabilità dei servizi.</span><span class="sxs-lookup"><span data-stu-id="47826-121">Trends analysis is essential when trying to understand service usage and reliability.</span></span> <span data-ttu-id="47826-122">Le tendenze orarie offrono un'analisi ravvicinata delle prestazioni quotidiane, che consente di identificare gli incidenti in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="47826-122">Hourly trends provide a close look at daily performance, which helps identify real-time incidents.</span></span> <span data-ttu-id="47826-123">Le tendenze quotidiane consentono di vedere l'integrità dei servizi da una prospettiva a lungo termine.</span><span class="sxs-lookup"><span data-stu-id="47826-123">Daily trends let you see your service health from a long-term perspective.</span></span> <span data-ttu-id="47826-124">È importante poter passare da una modalità all'altra con una granularità dei dati appropriata.</span><span class="sxs-lookup"><span data-stu-id="47826-124">It's important to be able to shift between those two modes with appropriate data granularity.</span></span> <span data-ttu-id="47826-125">Il report CQD PSTN Direct Routing fornisce una panoramica delle tendenze di 6 mesi, tendenze giornaliere di 7 e 30 giorni e tendenze orarie per poter analizzare le prestazioni a ogni livello.</span><span class="sxs-lookup"><span data-stu-id="47826-125">The CQD PSTN Direct Routing report provides 6-month trends overview, 7- and 30-day daily trends, and hourly trends so you can analyze performance at each level.</span></span>
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="Screenshot dei grafici delle tendenze nel report CQD PSTN Direct Routing":::

3. <span data-ttu-id="47826-127">Eseguire il drill-through fino a SBC o a livello utente</span><span class="sxs-lookup"><span data-stu-id="47826-127">Drill through to SBC or user level</span></span>

   <span data-ttu-id="47826-128">Abbiamo creato funzionalità di drill-through su molte categorie di dati in CQD, che consente di comprendere rapidamente l'utilizzo o la distribuzione dell'affidabilità a livello di SBC o utente.</span><span class="sxs-lookup"><span data-stu-id="47826-128">We've been building in drill-through capability on many data categories in CQD, which lets you quickly understand usage or reliability distribution at the SBC or user level.</span></span> <span data-ttu-id="47826-129">Usando il drill-through, è possibile individuare rapidamente i problemi e comprendere l'impatto reale degli utenti.</span><span class="sxs-lookup"><span data-stu-id="47826-129">By using drill through, you can quickly poinpoint issues and understand real user impact.</span></span> <span data-ttu-id="47826-130">Il report CQD PSTN Direct Routing include funzionalità di drill-through nelle metriche Service Detail e Network Effectiveness Ratio.</span><span class="sxs-lookup"><span data-stu-id="47826-130">The CQD PSTN Direct Routing report features drill through on the Service Detail and Network Effectiveness Ratio metrics.</span></span> <span data-ttu-id="47826-131">Fare clic sul punto dati a cui si è interessati per eseguire il drill-through fino ai dettagli ABC o a livello di utente.</span><span class="sxs-lookup"><span data-stu-id="47826-131">Click the data point you're interested in to drill through to SBC- or user-level details.</span></span>
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="Screenshot che mostra la funzionalità drill-through in un punto dati":::


## <a name="pstn-overview"></a><span data-ttu-id="47826-133">Panoramica di PSTN</span><span class="sxs-lookup"><span data-stu-id="47826-133">PSTN Overview</span></span>

<span data-ttu-id="47826-134">Il report di routing diretto PSTN CQD fornisce le informazioni seguenti relative all'integrità generale del servizio per gli ultimi 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="47826-134">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="47826-135">![Screenshot: report CQD PSTN](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="47826-135">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="47826-136">Ad esempio, se si è interessati all'utilizzo generale e all'integrità di tutte le chiamate in ingresso che attraversano SBC abc.bca.adatum.biz con gli Stati Uniti come paese interno:</span><span class="sxs-lookup"><span data-stu-id="47826-136">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="47826-137">**Call Out**</span><span class="sxs-lookup"><span data-stu-id="47826-137">**Call Out**</span></span> | <span data-ttu-id="47826-138">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="47826-138">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="47826-139">1</span><span class="sxs-lookup"><span data-stu-id="47826-139">1</span></span>            | <span data-ttu-id="47826-140">È possibile usare i filtri nella parte superiore per eseguire il drill-down e selezionare ByotIn come tipo di chiamata, abc.bca.contoso.com come session boarder controller e US come paese interno.</span><span class="sxs-lookup"><span data-stu-id="47826-140">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="47826-141">2</span><span class="sxs-lookup"><span data-stu-id="47826-141">2</span></span>            | <span data-ttu-id="47826-142">Tendenza di utilizzo degli ultimi 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="47826-142">Usage trend for the past 180 days.</span></span> <span data-ttu-id="47826-143">Il report dei dettagli sull'utilizzo è presente nella pagina Dettagli servizio.</span><span class="sxs-lookup"><span data-stu-id="47826-143">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="47826-144">3</span><span class="sxs-lookup"><span data-stu-id="47826-144">3</span></span>            | <span data-ttu-id="47826-145">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span><span class="sxs-lookup"><span data-stu-id="47826-145">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="47826-146">Il report dei dettagli è presente nella pagina Parametri di rete.</span><span class="sxs-lookup"><span data-stu-id="47826-146">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="47826-147">4</span><span class="sxs-lookup"><span data-stu-id="47826-147">4</span></span>            | <span data-ttu-id="47826-148">Tendenza delle chiamate simultanee e degli utenti attivi giornalieri degli ultimi 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="47826-148">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="47826-149">Questo grafico consente di comprendere il volume massimo del servizio.</span><span class="sxs-lookup"><span data-stu-id="47826-149">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="47826-150">5</span><span class="sxs-lookup"><span data-stu-id="47826-150">5</span></span>            | <span data-ttu-id="47826-151">Il motivo principale di fine chiamata ha interessato la qualità del servizio degli ultimi 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="47826-151">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="47826-152">I dettagli sull'integrità dei servizi sono nella pagina Network Effective Ratio(NER).</span><span class="sxs-lookup"><span data-stu-id="47826-152">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="47826-153">Dettagli servizio</span><span class="sxs-lookup"><span data-stu-id="47826-153">Service Details</span></span>

<span data-ttu-id="47826-154">Questa pagina fornisce le tendenze di utilizzo dei servizi al giorno e la suddivisione del feedback degli utenti in base all'area geografica.</span><span class="sxs-lookup"><span data-stu-id="47826-154">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="47826-155">**Totale chiamate di tentativo -** Numero totale di chiamate di tentativo nell'intervallo di tempo specificato, incluse sia le chiamate riuscite che quelle non riuscite</span><span class="sxs-lookup"><span data-stu-id="47826-155">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="47826-156">**Totale chiamate connesse -** Totale chiamate connesse in tale intervallo di tempo</span><span class="sxs-lookup"><span data-stu-id="47826-156">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="47826-157">**Totale minuti :** Utilizzo totale dei minuti in tale intervallo di tempo</span><span class="sxs-lookup"><span data-stu-id="47826-157">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="47826-158">**Utenti attivi giornalieri (DAU) –** Numero di utenti attivi giornalieri che hanno effettuato almeno una chiamata connessa in quel giorno</span><span class="sxs-lookup"><span data-stu-id="47826-158">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="47826-159">**Chiamate simultanee :** Numero massimo di chiamate attive simultanee in un minuto</span><span class="sxs-lookup"><span data-stu-id="47826-159">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="47826-160">**Feedback degli utenti :** Il punteggio "Valuta la mia chiamata" proviene dall'utente.</span><span class="sxs-lookup"><span data-stu-id="47826-160">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="47826-161">3-5 è considerato una buona chiamata.</span><span class="sxs-lookup"><span data-stu-id="47826-161">3-5 is considered as a good call.</span></span> <span data-ttu-id="47826-162">1-2 è considerato una chiamata non disponibile.</span><span class="sxs-lookup"><span data-stu-id="47826-162">1-2 is considered as a bad call.</span></span>

![Screenshot: report CQD PSTN](media/CQD-PSTN-report2.png)

<span data-ttu-id="47826-164">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="47826-164">For example:</span></span>

1.  <span data-ttu-id="47826-165">Se la durata media delle chiamate scende a 0 al 14/02/2020, è prima di tutto possibile verificare se il volume della chiamata sembra normale e verificare se esiste una grande discrepanza tra le chiamate di connessione totali e le chiamate di tentativo totali.</span><span class="sxs-lookup"><span data-stu-id="47826-165">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="47826-166">Passare quindi alla pagina Network Effectiveness Ratio per investire per motivi di errore di chiamata.</span><span class="sxs-lookup"><span data-stu-id="47826-166">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="47826-167">Se nella mappa dei feedback degli utenti sono presenti punti rossi crescenti, è possibile passare alla pagina Network Effectiveness Ratio e a Network Parameter per verificare se ci sono anomalie e generare un ticket usando MS Service Desk.</span><span class="sxs-lookup"><span data-stu-id="47826-167">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="47826-168">Rapporto di efficacia della rete</span><span class="sxs-lookup"><span data-stu-id="47826-168">Network Effectiveness Ratio</span></span>

<span data-ttu-id="47826-169">Si tratta della stessa metrica visualizzata nel dashboard Integrità generale.</span><span class="sxs-lookup"><span data-stu-id="47826-169">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="47826-170">È possibile controllare il numero NER orario con i dettagli delle chiamate interessate per entrambe le direzioni di chiamata (in ingresso/uscita) nel grafico rapporto di efficacia della rete oraria e motivo finale della chiamata riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="47826-170">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="47826-171">**NER** - La capacità (%) di una rete per il recapito delle chiamate misurando il numero di chiamate inviate rispetto al numero di chiamate recapitate a un destinatario.</span><span class="sxs-lookup"><span data-stu-id="47826-171">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="47826-172">**Codice di risposta SIP:** un codice di risposta intero a tre cifre mostra lo stato della chiamata.</span><span class="sxs-lookup"><span data-stu-id="47826-172">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="47826-173">**Codice di risposta Microsoft**- Codice di risposta inviato dal componente Microsoft.</span><span class="sxs-lookup"><span data-stu-id="47826-173">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="47826-174">**Descrizione:** fase del motivo corrispondente al codice di risposta SIP e al codice di risposta Microsoft.</span><span class="sxs-lookup"><span data-stu-id="47826-174">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="47826-175">**Numero di chiamate interessate:** il numero totale di chiamate interessate durante l'intervallo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="47826-175">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![Screenshot: report CQD PSTN](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="47826-177">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="47826-177">For example:</span></span>

![Screenshot: report CQD PSTN](media/CQD-PSTN-report4.png)

<span data-ttu-id="47826-179">Se NER giornaliero ha un tuffo il 05/02/2020, è possibile fare clic sulla data e gli altri grafici ingrandiranno la data specifica.</span><span class="sxs-lookup"><span data-stu-id="47826-179">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![Screenshot: report CQD PSTN](media/CQD-PSTN-report5.png)

<span data-ttu-id="47826-181">Dalla tendenza oraria NER Good Percentage, è possibile trovare che il tuffo si verifica intorno alle 21:00.</span><span class="sxs-lookup"><span data-stu-id="47826-181">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="47826-182">Quindi fare di nuovo clic per fare zoom sull'ora 21 e selezionare Dettagli chiamata effettive per vedere quante chiamate non sono riuscite in quell'ora e quali sono i motivi di fine chiamata.</span><span class="sxs-lookup"><span data-stu-id="47826-182">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="47826-183">È possibile iniziare con la risoluzione dei problemi relativi a SBC o segnalare a Service Desk se il problema non è correlato a SBC.</span><span class="sxs-lookup"><span data-stu-id="47826-183">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="47826-184">Parametri di rete</span><span class="sxs-lookup"><span data-stu-id="47826-184">Network Parameters</span></span>

<span data-ttu-id="47826-185">Tutti i parametri di rete vengono misurati dall'interfaccia di routing diretto al session border controller.</span><span class="sxs-lookup"><span data-stu-id="47826-185">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="47826-186">Per informazioni sui valori consigliati, vedere Preparare la rete [dell'organizzazione](prepare-network.md)per Microsoft Teams e esaminare i valori consigliati da Customer Edge a Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="47826-186">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="47826-187">**Instabilità:** misura in millisecondo della variazione del tempo di ritardo della propagazione della rete calcolata tra due endpoint usando RTCP (RtP Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="47826-187">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="47826-188">**Perdita di pacchetti:** misura del pacchetto che non è riuscito ad arrivare. viene calcolato tra due endpoint.</span><span class="sxs-lookup"><span data-stu-id="47826-188">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="47826-189">**Latenza-** (noto anche come tempo di andata e ritorno) è il tempo necessario per l'invio di un segnale più il tempo necessario per la ricezione del riconoscimento del segnale.</span><span class="sxs-lookup"><span data-stu-id="47826-189">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="47826-190">Questo ritardo è costituito dai tempi di propagazione tra i due punti di un segnale.</span><span class="sxs-lookup"><span data-stu-id="47826-190">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![Screenshot: report CQD PSTN](media/CQD-PSTN-report6.png)

<span data-ttu-id="47826-192">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="47826-192">For example:</span></span>

<span data-ttu-id="47826-193">Se viene visualizzato un picco in uno dei quattro grafici (Latenza, Instabilità, Tasso di perdita pacchetti, Ritardo post chiamata) per una data specifica, ad esempio Latenza il 14/02/2020, fare clic sul punto della data.</span><span class="sxs-lookup"><span data-stu-id="47826-193">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="47826-194">Il grafico di tendenza oraria nella parte inferiore verrà aggiornato per visualizzare il numero orario.</span><span class="sxs-lookup"><span data-stu-id="47826-194">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="47826-195">È possibile controllare gli SBC o sollevare un ticket con MS Service Desk.</span><span class="sxs-lookup"><span data-stu-id="47826-195">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![Screenshot: report CQD PSTN](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="47826-197">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="47826-197">Related topics</span></span>

[<span data-ttu-id="47826-198">Usare Power BI per analizzare i dati CQD per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="47826-198">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)

[<span data-ttu-id="47826-199">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="47826-199">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)