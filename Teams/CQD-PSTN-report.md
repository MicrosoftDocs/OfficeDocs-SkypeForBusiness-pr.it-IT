---
title: Uso del report di routing diretto PSTN di CQD
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
description: Usa il report di instradamento diretto PSTN di Microsoft Teams Call Quality Dashboard (CQD) per monitorare e risolvere i problemi relativi alle chiamate PSTN in Microsoft Teams.
ms.openlocfilehash: e4662d80dbba88c1049c7ef98569dae408ca9ba0
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583103"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="f04bf-103">Uso del report di routing diretto PSTN di CQD</span><span class="sxs-lookup"><span data-stu-id="f04bf-103">Using the CQD PSTN Direct Routing report</span></span>

<span data-ttu-id="f04bf-104">A marzo 2020 è stato aggiunto un report di Routing diretto PSTN di Microsoft Teams Call Quality Dashboard (CQD) ai modelli di query di Power BI scaricabili per [Call Quality](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)Dashboard.</span><span class="sxs-lookup"><span data-stu-id="f04bf-104">New in March 2020, we've added a Microsoft Teams Call Quality Dashboard (CQD) PSTN Direct Routing report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="f04bf-105">Il report CQD PSTN Direct Routing (CQD PSTN Direct Routing Report.pbit) consente di conoscere i modelli di utilizzo e la qualità dei servizi PSTN.</span><span class="sxs-lookup"><span data-stu-id="f04bf-105">The CQD PSTN Direct Routing report (CQD PSTN Direct Routing Report.pbit) helps you understand the usage patterns and quality of your PSTN services.</span></span> <span data-ttu-id="f04bf-106">Usare questo report per monitorare l'utilizzo del servizio, le informazioni sul controller dei confini della sessione (SBC), il servizio di telefonia, i parametri di rete e i dettagli sul rapporto efficacia della rete.</span><span class="sxs-lookup"><span data-stu-id="f04bf-106">Use this report to monitor service usage, information about your Session Border Controller (SBC), the telephony service, network parameters, and Network Effectiveness Ratio details.</span></span> <span data-ttu-id="f04bf-107">Queste informazioni possono aiutarti a identificare i problemi, incluso il motivo delle chiamate eliminate.</span><span class="sxs-lookup"><span data-stu-id="f04bf-107">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="f04bf-108">Ad esempio, potrai vedere quando il volume scende o quante chiamate vengono interessate e per quale motivo.</span><span class="sxs-lookup"><span data-stu-id="f04bf-108">For example, you'll be able to see when volume drops, or how many calls get affected and for what reason.</span></span>


<span data-ttu-id="f04bf-109">Il report di routing diretto PSTN di CQD include quattro sezioni:</span><span class="sxs-lookup"><span data-stu-id="f04bf-109">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="f04bf-110">Panoramica di PSTN</span><span class="sxs-lookup"><span data-stu-id="f04bf-110">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="f04bf-111">Dettagli del servizio</span><span class="sxs-lookup"><span data-stu-id="f04bf-111">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="f04bf-112">Network Effectiveness Ratio</span><span class="sxs-lookup"><span data-stu-id="f04bf-112">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="f04bf-113">Parametri di rete</span><span class="sxs-lookup"><span data-stu-id="f04bf-113">Network Parameters</span></span>](#network-parameters)

## <a name="highlights"></a><span data-ttu-id="f04bf-114">Highlights</span><span class="sxs-lookup"><span data-stu-id="f04bf-114">Highlights</span></span>

1. <span data-ttu-id="f04bf-115">Analizzare per tipo di chiamata, SBC, paese chiamante e chiamato</span><span class="sxs-lookup"><span data-stu-id="f04bf-115">Analyze by call type, SBC, caller and callee country</span></span>

   <span data-ttu-id="f04bf-116">Il report Routing diretto PSTN di CQD aggrega metriche di affidabilità e utilizzo per tutti gli SBC del tuo tenant per gli ultimi 7, 30 o 180 giorni (6 mesi).</span><span class="sxs-lookup"><span data-stu-id="f04bf-116">The CQD PSTN Direct Routing report aggregates reliability and usage metrics for all SBCs on your tenant for the last 7, 30, or 180 days (6 months).</span></span> <span data-ttu-id="f04bf-117">È possibile analizzare i dati per tipo di chiamata, SBC, paese chiamante e chiamato.</span><span class="sxs-lookup"><span data-stu-id="f04bf-117">You can analyze data by call type, SBC, caller and callee country.</span></span> <span data-ttu-id="f04bf-118">Se si è interessati a un particolare SBC o paese, sarà possibile identificare le variazioni delle tendenze nell'intervallo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="f04bf-118">If you're interested in a particular SBC or country, you'll be able to identify changes in trends over the selected time range.</span></span>
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="Screenshot dei filtri disponibili nel report di routing diretto PSTN di CQD":::
   
2. <span data-ttu-id="f04bf-120">Tenere traccia delle tendenze</span><span class="sxs-lookup"><span data-stu-id="f04bf-120">Track trends</span></span>

    <span data-ttu-id="f04bf-121">L'analisi delle tendenze è essenziale quando si prova a comprendere l'utilizzo e l'affidabilità dei servizi.</span><span class="sxs-lookup"><span data-stu-id="f04bf-121">Trends analysis is essential when trying to understand service usage and reliability.</span></span> <span data-ttu-id="f04bf-122">Le tendenze orarie offrono un'analisi ravvicinata delle prestazioni giornaliere, che consente di identificare gli incidenti in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="f04bf-122">Hourly trends provide a close look at daily performance, which helps identify real-time incidents.</span></span> <span data-ttu-id="f04bf-123">Le tendenze giornaliere consentono di vedere l'integrità dei servizi da un punto di vista a lungo termine.</span><span class="sxs-lookup"><span data-stu-id="f04bf-123">Daily trends let you see your service health from a long-term perspective.</span></span> <span data-ttu-id="f04bf-124">È importante poter passare da una modalità all'altra con granularità dei dati appropriata.</span><span class="sxs-lookup"><span data-stu-id="f04bf-124">It's important to be able to shift between those two modes with appropriate data granularity.</span></span> <span data-ttu-id="f04bf-125">Il report Dirette PSTN di CQD fornisce una panoramica delle tendenze dei 6 mesi, delle tendenze giornaliere di 7 e 30 giorni e delle tendenze orarie per poter analizzare le prestazioni a ogni livello.</span><span class="sxs-lookup"><span data-stu-id="f04bf-125">The CQD PSTN Direct Routing report provides 6-month trends overview, 7- and 30-day daily trends, and hourly trends so you can analyze performance at each level.</span></span>
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="Screenshot dei grafici delle tendenze nel report di routing diretto PSTN di CQD":::

3. <span data-ttu-id="f04bf-127">Drill-through fino a SBC o a livello utente</span><span class="sxs-lookup"><span data-stu-id="f04bf-127">Drill through to SBC or user level</span></span>

   <span data-ttu-id="f04bf-128">In CQD è stata migliorata la funzionalità drill-through per molte categorie di dati, che consente di comprendere rapidamente l'utilizzo o la distribuzione di affidabilità a livello di utente o SBC.</span><span class="sxs-lookup"><span data-stu-id="f04bf-128">We've been building in drill-through capability on many data categories in CQD, which lets you quickly understand usage or reliability distribution at the SBC or user level.</span></span> <span data-ttu-id="f04bf-129">Con il drill-through, è possibile risolvere rapidamente i problemi e comprendere il reale impatto degli utenti.</span><span class="sxs-lookup"><span data-stu-id="f04bf-129">By using drill through, you can quickly poinpoint issues and understand real user impact.</span></span> <span data-ttu-id="f04bf-130">Il report di routing diretto PSTN di CQD include il drill-through nelle metriche Service Detail and Network Effectiveness Ratio.</span><span class="sxs-lookup"><span data-stu-id="f04bf-130">The CQD PSTN Direct Routing report features drill through on the Service Detail and Network Effectiveness Ratio metrics.</span></span> <span data-ttu-id="f04bf-131">Fare clic sul punto dati a cui si è interessati per eseguire il drill-through fino ai dettagli ABC o a livello utente.</span><span class="sxs-lookup"><span data-stu-id="f04bf-131">Click the data point you're interested in to drill through to SBC- or user-level details.</span></span>
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="Screenshot che mostra la funzionalità drill-through in un punto dati":::


## <a name="pstn-overview"></a><span data-ttu-id="f04bf-133">Panoramica di PSTN</span><span class="sxs-lookup"><span data-stu-id="f04bf-133">PSTN Overview</span></span>

<span data-ttu-id="f04bf-134">Il report di routing pstn diretto di CQD fornisce le seguenti informazioni relative all'integrità generale del servizio negli ultimi 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="f04bf-134">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="f04bf-135">![Screenshot: Report CQD PSTN](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="f04bf-135">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="f04bf-136">Ad esempio, se si è interessati all'utilizzo generale e all'integrità di tutte le chiamate in ingresso tramite SBC abc.bca.adatum.biz con US come paese interno:</span><span class="sxs-lookup"><span data-stu-id="f04bf-136">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="f04bf-137">**Call Out**</span><span class="sxs-lookup"><span data-stu-id="f04bf-137">**Call Out**</span></span> | <span data-ttu-id="f04bf-138">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f04bf-138">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="f04bf-139">1</span><span class="sxs-lookup"><span data-stu-id="f04bf-139">1</span></span>            | <span data-ttu-id="f04bf-140">Puoi utilizzare i filtri in alto per eseguire il drill-down e selezionare ByotIn come tipo di chiamata, abc.bca.contoso.com controller di session boarder e US come paese interno.</span><span class="sxs-lookup"><span data-stu-id="f04bf-140">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="f04bf-141">2</span><span class="sxs-lookup"><span data-stu-id="f04bf-141">2</span></span>            | <span data-ttu-id="f04bf-142">Tendenza di utilizzo degli ultimi 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="f04bf-142">Usage trend for the past 180 days.</span></span> <span data-ttu-id="f04bf-143">Il report dei dettagli sull'utilizzo è presente nella pagina Dettagli servizio.</span><span class="sxs-lookup"><span data-stu-id="f04bf-143">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="f04bf-144">3</span><span class="sxs-lookup"><span data-stu-id="f04bf-144">3</span></span>            | <span data-ttu-id="f04bf-145">Di tendenza Post Dial Delay, Latency, Jitter e Packet Loss degli ultimi 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="f04bf-145">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="f04bf-146">Il report dei dettagli è nella pagina Parametri di rete.</span><span class="sxs-lookup"><span data-stu-id="f04bf-146">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="f04bf-147">4</span><span class="sxs-lookup"><span data-stu-id="f04bf-147">4</span></span>            | <span data-ttu-id="f04bf-148">Tendenza di chiamate contemporanee e di utenti attivi giornalieri degli ultimi 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="f04bf-148">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="f04bf-149">Questo grafico consente di comprendere il volume massimo del servizio.</span><span class="sxs-lookup"><span data-stu-id="f04bf-149">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="f04bf-150">5</span><span class="sxs-lookup"><span data-stu-id="f04bf-150">5</span></span>            | <span data-ttu-id="f04bf-151">Il motivo principale del fine chiamata ha interessato la qualità del servizio degli ultimi 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="f04bf-151">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="f04bf-152">I dettagli sull'integrità dei servizi sono nella pagina Network Effective Ratio (NER).</span><span class="sxs-lookup"><span data-stu-id="f04bf-152">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="f04bf-153">Dettagli del servizio</span><span class="sxs-lookup"><span data-stu-id="f04bf-153">Service Details</span></span>

<span data-ttu-id="f04bf-154">Questa pagina contiene le tendenze di utilizzo del servizio ogni giorno e la suddivisione del feedback degli utenti in base all'area geografica.</span><span class="sxs-lookup"><span data-stu-id="f04bf-154">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="f04bf-155">**Totale chiamate tentate -** Totale chiamate di tentativo in tale intervallo di tempo, incluse sia le chiamate riuscite che quelle non effettuate</span><span class="sxs-lookup"><span data-stu-id="f04bf-155">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="f04bf-156">**Totale chiamate connesse -** Totale chiamate connesse in tale intervallo di tempo</span><span class="sxs-lookup"><span data-stu-id="f04bf-156">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="f04bf-157">**Totale minuti -** Utilizzo totale dei minuti in tale intervallo di tempo</span><span class="sxs-lookup"><span data-stu-id="f04bf-157">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="f04bf-158">**Utenti attivi giornalieri (DAU) –** Numero di utenti attivi giornalieri che hanno effettuato almeno una chiamata connessa in quel giorno</span><span class="sxs-lookup"><span data-stu-id="f04bf-158">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="f04bf-159">**Chiamate contemporanee -** Numero massimo di chiamate attive simultanee in un minuto</span><span class="sxs-lookup"><span data-stu-id="f04bf-159">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="f04bf-160">**Commenti e suggerimenti degli utenti** Il punteggio "Valuta la chiamata" proviene dall'utente.</span><span class="sxs-lookup"><span data-stu-id="f04bf-160">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="f04bf-161">3-5 è considerato una buona chiamata.</span><span class="sxs-lookup"><span data-stu-id="f04bf-161">3-5 is considered as a good call.</span></span> <span data-ttu-id="f04bf-162">1-2 è considerato una chiamata sbagliata.</span><span class="sxs-lookup"><span data-stu-id="f04bf-162">1-2 is considered as a bad call.</span></span>

![Screenshot: Report CQD PSTN](media/CQD-PSTN-report2.png)

<span data-ttu-id="f04bf-164">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f04bf-164">For example:</span></span>

1.  <span data-ttu-id="f04bf-165">Se la durata media della chiamata scende a 0 al 14/02/2020, è possibile verificare prima se il volume della chiamata appare normale e verificare se esiste una grande discrepanza tra il totale delle chiamate di connessione e il totale delle chiamate tentate.</span><span class="sxs-lookup"><span data-stu-id="f04bf-165">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="f04bf-166">Vai quindi alla pagina Network Effectiveness Ratio per investire in motivi di insuccesso di chiamata.</span><span class="sxs-lookup"><span data-stu-id="f04bf-166">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="f04bf-167">Se si nota l'aumento delle aree rosse nella mappa di feedback dell'utente, è possibile passare alla pagina Network Effectiveness Ratio e a Network Parameter per verificare se esistono anomalie e generare un ticket usando MS Service Desk.</span><span class="sxs-lookup"><span data-stu-id="f04bf-167">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="f04bf-168">Network Effectiveness Ratio</span><span class="sxs-lookup"><span data-stu-id="f04bf-168">Network Effectiveness Ratio</span></span>

<span data-ttu-id="f04bf-169">Si tratta della stessa metrica visualizzata nel dashboard Integrità generale.</span><span class="sxs-lookup"><span data-stu-id="f04bf-169">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="f04bf-170">Puoi controllare il numero NER orario con i dettagli delle chiamate interessati sia per le indicazioni telefoniche (in entrata/in uscita) che per il rapporto di efficacia della rete oraria e per il motivo finale della chiamata qui sotto.</span><span class="sxs-lookup"><span data-stu-id="f04bf-170">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="f04bf-171">**NER** - La capacità (%) di una rete per recapitare le chiamate misurando il numero di chiamate inviate rispetto al numero di chiamate effettuate a un destinatario.</span><span class="sxs-lookup"><span data-stu-id="f04bf-171">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="f04bf-172">**Codice di risposta SIP:** un codice di risposta intero a tre cifre mostra lo stato della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f04bf-172">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="f04bf-173">**Codice di risposta Microsoft**-A response code sent out from Microsoft component.</span><span class="sxs-lookup"><span data-stu-id="f04bf-173">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="f04bf-174">**Descrizione:** fase del motivo corrispondente al codice di risposta SIP e al codice di risposta Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f04bf-174">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="f04bf-175">**Numero di chiamate interessate:** il numero totale di chiamate interessate dall'intervallo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="f04bf-175">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![Screenshot: Report CQD PSTN](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="f04bf-177">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f04bf-177">For example:</span></span>

![Screenshot: Report CQD PSTN](media/CQD-PSTN-report4.png)

<span data-ttu-id="f04bf-179">Se NER giornaliero ha un tuffo il 05/02/2020, è possibile fare clic sulla data e gli altri grafici ingrandiranno alla data specifica.</span><span class="sxs-lookup"><span data-stu-id="f04bf-179">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![Screenshot: Report CQD PSTN](media/CQD-PSTN-report5.png)

<span data-ttu-id="f04bf-181">Dalla tendenza oraria NER Good Percentage, la dip si verifica intorno alle 21:00.</span><span class="sxs-lookup"><span data-stu-id="f04bf-181">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="f04bf-182">Quindi fai di nuovo clic per ingrandire all'ora 21 e seleziona Dettagli chiamata effettive per vedere quante chiamate non sono state effettuate in quell'ora e quali sono i motivi per cui la chiamata è stata terminare.</span><span class="sxs-lookup"><span data-stu-id="f04bf-182">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="f04bf-183">Se il problema non è correlato a SBC, è possibile iniziare con la risoluzione dei problemi di auto-problema oppure segnalare a Service Desk.</span><span class="sxs-lookup"><span data-stu-id="f04bf-183">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="f04bf-184">Parametri di rete</span><span class="sxs-lookup"><span data-stu-id="f04bf-184">Network Parameters</span></span>

<span data-ttu-id="f04bf-185">Tutti i parametri di rete vengono misurati dall'interfaccia di routing diretto al controller dei confini della sessione.</span><span class="sxs-lookup"><span data-stu-id="f04bf-185">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="f04bf-186">Per informazioni sui valori consigliati, vedere Preparare la rete [dell'organizzazione](prepare-network.md)per Microsoft Teams e osservare i valori consigliati da Customer Edge a Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="f04bf-186">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="f04bf-187">**Instabilità:** misura in millisecondi della variazione del tempo di ritardo di propagazione della rete calcolata tra due endpoint utilizzando RTCP (RtP Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="f04bf-187">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="f04bf-188">**Perdita pacchetti:** misura del pacchetto che non è riuscito ad arrivare; viene calcolata tra due endpoint.</span><span class="sxs-lookup"><span data-stu-id="f04bf-188">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="f04bf-189">**La latenza** - (nota anche come tempo di round trip) è il tempo di invio di un segnale più il tempo necessario per la conferma di ricezione del segnale.</span><span class="sxs-lookup"><span data-stu-id="f04bf-189">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="f04bf-190">Questo ritardo è costituito dai tempi di propagazione tra i due punti di un segnale.</span><span class="sxs-lookup"><span data-stu-id="f04bf-190">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![Screenshot: Report CQD PSTN](media/CQD-PSTN-report6.png)

<span data-ttu-id="f04bf-192">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f04bf-192">For example:</span></span>

<span data-ttu-id="f04bf-193">Se viene visualizzato un raccoglitore in uno dei quattro grafici (Latenza, Instabilità, Frequenza di perdita pacchetti, Ritardo post chiamata) per una data specifica, ad esempio Latenza il 14/02/2020, fare clic sul punto di data.</span><span class="sxs-lookup"><span data-stu-id="f04bf-193">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="f04bf-194">Inoltre, il grafico di tendenza oraria in basso viene aggiornato in modo da visualizzare il numero orario.</span><span class="sxs-lookup"><span data-stu-id="f04bf-194">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="f04bf-195">È possibile consultare i provider di servizi SBC o alzare un ticket con Service Desk MICROSOFT.</span><span class="sxs-lookup"><span data-stu-id="f04bf-195">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![Screenshot: Report CQD PSTN](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="f04bf-197">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f04bf-197">Related topics</span></span>

[<span data-ttu-id="f04bf-198">Usare Power BI per analizzare i dati di CQD per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f04bf-198">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)

[<span data-ttu-id="f04bf-199">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="f04bf-199">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)