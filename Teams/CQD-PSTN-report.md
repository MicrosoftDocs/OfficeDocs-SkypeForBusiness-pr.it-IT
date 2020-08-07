---
title: Uso del report di routing diretto PSTN di Call Quality dashboard
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
description: Usare il report di routing diretto PSTN di Microsoft teams Call Quality Dashboard (Call Quality Dashboard) per monitorare e risolvere i problemi di chiamate PSTN in Microsoft teams.
ms.openlocfilehash: e4662d80dbba88c1049c7ef98569dae408ca9ba0
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583103"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="bfb03-103">Uso del report di routing diretto PSTN di Call Quality dashboard</span><span class="sxs-lookup"><span data-stu-id="bfb03-103">Using the CQD PSTN Direct Routing report</span></span>

<span data-ttu-id="bfb03-104">Novità di marzo 2020 è stato aggiunto un report di routing diretto PSTN di Microsoft teams Call Quality Dashboard (Call Quality Dashboard) ai [modelli di query di Power bi scaricabili per Call Quality dashboard](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="bfb03-104">New in March 2020, we've added a Microsoft Teams Call Quality Dashboard (CQD) PSTN Direct Routing report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="bfb03-105">Il report routing diretto PSTN di Call Quality Dashboard (Call Quality dashboard PSTN Direct routing report. PBIT) consente di comprendere i modelli di utilizzo e la qualità dei servizi PSTN.</span><span class="sxs-lookup"><span data-stu-id="bfb03-105">The CQD PSTN Direct Routing report (CQD PSTN Direct Routing Report.pbit) helps you understand the usage patterns and quality of your PSTN services.</span></span> <span data-ttu-id="bfb03-106">Questo report consente di monitorare l'utilizzo del servizio, le informazioni relative a session border controller (SBC), il servizio di telefonia, i parametri di rete e i dettagli del rapporto di efficacia della rete.</span><span class="sxs-lookup"><span data-stu-id="bfb03-106">Use this report to monitor service usage, information about your Session Border Controller (SBC), the telephony service, network parameters, and Network Effectiveness Ratio details.</span></span> <span data-ttu-id="bfb03-107">Queste informazioni consentono di identificare i problemi, incluso il motivo per cui sono state eliminate le chiamate.</span><span class="sxs-lookup"><span data-stu-id="bfb03-107">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="bfb03-108">Ad esempio, potrai vedere quando il volume scende o il numero di chiamate che vengono influenzate e per quale motivo.</span><span class="sxs-lookup"><span data-stu-id="bfb03-108">For example, you'll be able to see when volume drops, or how many calls get affected and for what reason.</span></span>


<span data-ttu-id="bfb03-109">Il report routing diretto PSTN di Call Quality dashboard include quattro sezioni:</span><span class="sxs-lookup"><span data-stu-id="bfb03-109">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="bfb03-110">Panoramica PSTN</span><span class="sxs-lookup"><span data-stu-id="bfb03-110">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="bfb03-111">Dettagli del servizio</span><span class="sxs-lookup"><span data-stu-id="bfb03-111">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="bfb03-112">Rapporto efficacia di rete</span><span class="sxs-lookup"><span data-stu-id="bfb03-112">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="bfb03-113">Parametri di rete</span><span class="sxs-lookup"><span data-stu-id="bfb03-113">Network Parameters</span></span>](#network-parameters)

## <a name="highlights"></a><span data-ttu-id="bfb03-114">Evidenzia</span><span class="sxs-lookup"><span data-stu-id="bfb03-114">Highlights</span></span>

1. <span data-ttu-id="bfb03-115">Analizzare per tipo di chiamata, SBC, chiamante e paese chiamato</span><span class="sxs-lookup"><span data-stu-id="bfb03-115">Analyze by call type, SBC, caller and callee country</span></span>

   <span data-ttu-id="bfb03-116">Il report routing diretto PSTN di Call Quality dashboard aggrega le metriche di affidabilità e utilizzo per tutti i SBCs del tenant per gli ultimi 7, 30 o 180 giorni (6 mesi).</span><span class="sxs-lookup"><span data-stu-id="bfb03-116">The CQD PSTN Direct Routing report aggregates reliability and usage metrics for all SBCs on your tenant for the last 7, 30, or 180 days (6 months).</span></span> <span data-ttu-id="bfb03-117">È possibile analizzare i dati per tipo di chiamata, SBC, chiamante e paese chiamato.</span><span class="sxs-lookup"><span data-stu-id="bfb03-117">You can analyze data by call type, SBC, caller and callee country.</span></span> <span data-ttu-id="bfb03-118">Se si è interessati a un determinato SBC o a un paese, sarà possibile identificare le modifiche nelle tendenze nell'intervallo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="bfb03-118">If you're interested in a particular SBC or country, you'll be able to identify changes in trends over the selected time range.</span></span>
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="Screenshot dei filtri disponibili nel report di routing diretto PSTN di Call Quality dashboard":::
   
2. <span data-ttu-id="bfb03-120">Tenere traccia delle tendenze</span><span class="sxs-lookup"><span data-stu-id="bfb03-120">Track trends</span></span>

    <span data-ttu-id="bfb03-121">L'analisi delle tendenze è essenziale quando si cerca di comprendere l'uso e l'affidabilità del servizio.</span><span class="sxs-lookup"><span data-stu-id="bfb03-121">Trends analysis is essential when trying to understand service usage and reliability.</span></span> <span data-ttu-id="bfb03-122">Le tendenze orarie consentono di analizzare in modo ravvicinato le prestazioni quotidiane, che consentono di identificare gli incidenti in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="bfb03-122">Hourly trends provide a close look at daily performance, which helps identify real-time incidents.</span></span> <span data-ttu-id="bfb03-123">Le tendenze quotidiane consentono di visualizzare l'integrità del servizio da una prospettiva di lungo periodo.</span><span class="sxs-lookup"><span data-stu-id="bfb03-123">Daily trends let you see your service health from a long-term perspective.</span></span> <span data-ttu-id="bfb03-124">È importante essere in grado di spostarsi tra queste due modalità con la corretta granularità dei dati.</span><span class="sxs-lookup"><span data-stu-id="bfb03-124">It's important to be able to shift between those two modes with appropriate data granularity.</span></span> <span data-ttu-id="bfb03-125">Il report routing diretto PSTN di Call Quality dashboard offre una panoramica delle tendenze di 6 mesi, le tendenze quotidiane di 7 e 30 giorni e le tendenze orarie in modo da poter analizzare le prestazioni a ogni livello.</span><span class="sxs-lookup"><span data-stu-id="bfb03-125">The CQD PSTN Direct Routing report provides 6-month trends overview, 7- and 30-day daily trends, and hourly trends so you can analyze performance at each level.</span></span>
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="Screenshot dei grafici delle tendenze nel report di routing diretto PSTN di Call Quality dashboard":::

3. <span data-ttu-id="bfb03-127">Eseguire il drill-through a SBC o a livello utente</span><span class="sxs-lookup"><span data-stu-id="bfb03-127">Drill through to SBC or user level</span></span>

   <span data-ttu-id="bfb03-128">È stata creata una funzionalità di drill-through su molte categorie di dati in Call Quality dashboard, che consente di comprendere rapidamente la distribuzione dell'utilizzo o dell'affidabilità a livello di utente o SBC.</span><span class="sxs-lookup"><span data-stu-id="bfb03-128">We've been building in drill-through capability on many data categories in CQD, which lets you quickly understand usage or reliability distribution at the SBC or user level.</span></span> <span data-ttu-id="bfb03-129">Usando drill-through puoi poinpoint rapidamente i problemi e capire l'impatto dell'utente reale.</span><span class="sxs-lookup"><span data-stu-id="bfb03-129">By using drill through, you can quickly poinpoint issues and understand real user impact.</span></span> <span data-ttu-id="bfb03-130">Il report routing diretto PSTN di Call Quality dashboard include le metriche dei dettagli del servizio e della percentuale di efficacia della rete.</span><span class="sxs-lookup"><span data-stu-id="bfb03-130">The CQD PSTN Direct Routing report features drill through on the Service Detail and Network Effectiveness Ratio metrics.</span></span> <span data-ttu-id="bfb03-131">Fare clic sul punto dati a cui si è interessati per eseguire il drill-up a SBC o a livello di utente.</span><span class="sxs-lookup"><span data-stu-id="bfb03-131">Click the data point you're interested in to drill through to SBC- or user-level details.</span></span>
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="Schermata che mostra la funzionalità di drill-through in un punto dati":::


## <a name="pstn-overview"></a><span data-ttu-id="bfb03-133">Panoramica PSTN</span><span class="sxs-lookup"><span data-stu-id="bfb03-133">PSTN Overview</span></span>

<span data-ttu-id="bfb03-134">Il report routing diretto PSTN di Call Quality dashboard fornisce le informazioni seguenti relative all'integrità complessiva del servizio per gli ultimi 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="bfb03-134">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="bfb03-135">![Screenshot: report di Call Quality dashboard PSTN](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="bfb03-135">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="bfb03-136">Ad esempio, se si è interessati all'uso e all'integrità generali di tutte le chiamate in ingresso che attraversano SBC abc.bca.adatum.biz con noi come paese interno:</span><span class="sxs-lookup"><span data-stu-id="bfb03-136">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="bfb03-137">**Chiamata fuori**</span><span class="sxs-lookup"><span data-stu-id="bfb03-137">**Call Out**</span></span> | <span data-ttu-id="bfb03-138">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="bfb03-138">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="bfb03-139">1</span><span class="sxs-lookup"><span data-stu-id="bfb03-139">1</span></span>            | <span data-ttu-id="bfb03-140">È possibile usare i filtri nella parte superiore per eseguire il drill-down e selezionare ByotIn come tipo di chiamata, abc.bca.contoso.com come controller di bordo sessione e Stati Uniti come paese interno.</span><span class="sxs-lookup"><span data-stu-id="bfb03-140">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="bfb03-141">2</span><span class="sxs-lookup"><span data-stu-id="bfb03-141">2</span></span>            | <span data-ttu-id="bfb03-142">Tendenza all'uso degli ultimi 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="bfb03-142">Usage trend for the past 180 days.</span></span> <span data-ttu-id="bfb03-143">È possibile trovare report dettagli utilizzo nella pagina Dettagli servizio.</span><span class="sxs-lookup"><span data-stu-id="bfb03-143">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="bfb03-144">3</span><span class="sxs-lookup"><span data-stu-id="bfb03-144">3</span></span>            | <span data-ttu-id="bfb03-145">Ritardo di post-chiamata, latenza, jitter e tendenza alla perdita di pacchetti per gli ultimi 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="bfb03-145">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="bfb03-146">È possibile trovare report dettagli nella pagina parametri di rete.</span><span class="sxs-lookup"><span data-stu-id="bfb03-146">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="bfb03-147">4</span><span class="sxs-lookup"><span data-stu-id="bfb03-147">4</span></span>            | <span data-ttu-id="bfb03-148">Chiamata simultanea e tendenza utente attiva giornaliera per gli ultimi 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="bfb03-148">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="bfb03-149">Questo grafico può aiutare a comprendere il volume massimo del servizio.</span><span class="sxs-lookup"><span data-stu-id="bfb03-149">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="bfb03-150">5</span><span class="sxs-lookup"><span data-stu-id="bfb03-150">5</span></span>            | <span data-ttu-id="bfb03-151">La qualità del servizio in primo piano è stata interessata per gli ultimi 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="bfb03-151">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="bfb03-152">È possibile trovare informazioni dettagliate sull'integrità dei servizi nella pagina NER (Network effective ratio).</span><span class="sxs-lookup"><span data-stu-id="bfb03-152">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="bfb03-153">Dettagli del servizio</span><span class="sxs-lookup"><span data-stu-id="bfb03-153">Service Details</span></span>

<span data-ttu-id="bfb03-154">Questa pagina fornisce le tendenze di utilizzo del servizio al giorno e la ripartizione dei feedback degli utenti per geografica.</span><span class="sxs-lookup"><span data-stu-id="bfb03-154">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="bfb03-155">**Totale chiamate di tentativo-** Totale tentativo chiamate in tale intervallo di tempo, incluse le chiamate successo e non riuscito</span><span class="sxs-lookup"><span data-stu-id="bfb03-155">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="bfb03-156">**Totale chiamate connesse-** Totale chiamate connesse nell'intervallo di tempo</span><span class="sxs-lookup"><span data-stu-id="bfb03-156">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="bfb03-157">**Minuti totali-** Utilizzo totale dei minuti nell'intervallo di tempo</span><span class="sxs-lookup"><span data-stu-id="bfb03-157">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="bfb03-158">**Utenti attivi giornalieri (DAU)-** Numero di utenti attivi giornalieri che hanno effettuato almeno una chiamata connessa in quel giorno</span><span class="sxs-lookup"><span data-stu-id="bfb03-158">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="bfb03-159">**Chiamate simultanee:** Numero massimo di chiamate attive simultanee in un minuto</span><span class="sxs-lookup"><span data-stu-id="bfb03-159">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="bfb03-160">**Feedback degli utenti:** Il Punteggio "Vota la mia chiamata" proviene dall'utente.</span><span class="sxs-lookup"><span data-stu-id="bfb03-160">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="bfb03-161">3-5 è considerato una buona chiamata.</span><span class="sxs-lookup"><span data-stu-id="bfb03-161">3-5 is considered as a good call.</span></span> <span data-ttu-id="bfb03-162">1-2 viene considerato come una chiamata errata.</span><span class="sxs-lookup"><span data-stu-id="bfb03-162">1-2 is considered as a bad call.</span></span>

![Screenshot: report di Call Quality dashboard PSTN](media/CQD-PSTN-report2.png)

<span data-ttu-id="bfb03-164">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bfb03-164">For example:</span></span>

1.  <span data-ttu-id="bfb03-165">Se viene visualizzata la durata media delle chiamate scende a 0 in 02/14/2020, è possibile verificare se il volume delle chiamate è normale e verificare se esiste una grande discrepanza tra le chiamate di connessione totale e il tentativo totale.</span><span class="sxs-lookup"><span data-stu-id="bfb03-165">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="bfb03-166">Quindi Vai alla pagina rapporto efficacia Network per investire sui motivi di errore di chiamata.</span><span class="sxs-lookup"><span data-stu-id="bfb03-166">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="bfb03-167">Se nella mappa di feedback degli utenti viene visualizzato un numero crescente di punti rossi, è possibile accedere alla pagina rapporto di efficacia della rete e al parametro di rete per verificare se sono presenti anomalie e si può alzare un biglietto usando il servizio di assistenza MS.</span><span class="sxs-lookup"><span data-stu-id="bfb03-167">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="bfb03-168">Rapporto efficacia di rete</span><span class="sxs-lookup"><span data-stu-id="bfb03-168">Network Effectiveness Ratio</span></span>

<span data-ttu-id="bfb03-169">Questa è la stessa metrica visualizzata nel dashboard integrità generale.</span><span class="sxs-lookup"><span data-stu-id="bfb03-169">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="bfb03-170">È possibile controllare il numero di NER ogni ora con le chiamate interessate in dettaglio per entrambe le direzioni delle chiamate (in ingresso/in uscita) nel rapporto oraria di efficacia della rete e nel grafico motivo finale chiamata seguente.</span><span class="sxs-lookup"><span data-stu-id="bfb03-170">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="bfb03-171">**Ner** -l'abilità (%) di una rete per consegnare le chiamate misurando il numero di chiamate inviate rispetto al numero di chiamate recapitate a un destinatario.</span><span class="sxs-lookup"><span data-stu-id="bfb03-171">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="bfb03-172">**Codice di risposta SIP**: il codice di risposta intero a tre cifre Mostra lo stato della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bfb03-172">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="bfb03-173">**Codice di risposta Microsoft**-codice di risposta inviato dal componente Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bfb03-173">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="bfb03-174">**Descrizione** : la fase di Reason che corrisponde al codice di risposta SIP e al codice di risposta Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bfb03-174">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="bfb03-175">**Numero di chiamate interessate** : il numero totale di chiamate è stato influenzato durante l'intervallo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="bfb03-175">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![Screenshot: report di Call Quality dashboard PSTN](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="bfb03-177">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bfb03-177">For example:</span></span>

![Screenshot: report di Call Quality dashboard PSTN](media/CQD-PSTN-report4.png)

<span data-ttu-id="bfb03-179">Se il Daily NER ha un dip in 02/05/2020, è possibile fare clic sulla data e gli altri grafici faranno zoom su quella specifica data.</span><span class="sxs-lookup"><span data-stu-id="bfb03-179">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![Screenshot: report di Call Quality dashboard PSTN](media/CQD-PSTN-report5.png)

<span data-ttu-id="bfb03-181">Dalla buona percentuale di tendenza per ogni ora è possibile trovare il DIP che si verifica intorno a 21:00.</span><span class="sxs-lookup"><span data-stu-id="bfb03-181">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="bfb03-182">Quindi fare di nuovo clic per ingrandire l'ora 21 e controllare i dettagli delle chiamate effettuate per vedere quante chiamate non sono state eseguite in quell'ora e quali sono i motivi per le chiamate finali.</span><span class="sxs-lookup"><span data-stu-id="bfb03-182">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="bfb03-183">Se il problema non è correlato a SBC, è possibile iniziare a eseguire le riprese in caso di problemi su qualsiasi problema o report SBC.</span><span class="sxs-lookup"><span data-stu-id="bfb03-183">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="bfb03-184">Parametri di rete</span><span class="sxs-lookup"><span data-stu-id="bfb03-184">Network Parameters</span></span>

<span data-ttu-id="bfb03-185">Tutti i parametri di rete vengono misurati dall'interfaccia di routing diretto al controller di bordo della sessione.</span><span class="sxs-lookup"><span data-stu-id="bfb03-185">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="bfb03-186">Per informazioni sui valori consigliati, vedere [preparare la rete dell'organizzazione per Microsoft teams](prepare-network.md)e esaminare i valori consigliati di Microsoft Edge per il cliente.</span><span class="sxs-lookup"><span data-stu-id="bfb03-186">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="bfb03-187">**Jitter** : è la misura di millisecondi di variazione nel tempo di ritardo di propagazione della rete calcolato tra due endpoint usando RTCP (il protocollo di controllo RTP).</span><span class="sxs-lookup"><span data-stu-id="bfb03-187">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="bfb03-188">**Perdita di pacchetti** : è una misura del pacchetto che non è riuscita ad arrivare; viene calcolato tra due endpoint.</span><span class="sxs-lookup"><span data-stu-id="bfb03-188">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="bfb03-189">**Latenza** -(nota anche come tempo di andata e ritorno) è il periodo di tempo necessario per l'invio di un segnale più il tempo necessario per il riconoscimento del segnale da ricevere.</span><span class="sxs-lookup"><span data-stu-id="bfb03-189">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="bfb03-190">Questo ritardo temporale è costituito dai tempi di propagazione tra i due punti di un segnale.</span><span class="sxs-lookup"><span data-stu-id="bfb03-190">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![Screenshot: report di Call Quality dashboard PSTN](media/CQD-PSTN-report6.png)

<span data-ttu-id="bfb03-192">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bfb03-192">For example:</span></span>

<span data-ttu-id="bfb03-193">Se viene visualizzato un picco su uno dei quattro grafici (latenza, jitter, tasso di perdita del pacchetto, ritardo della chiamata) per una data specifica, ad esempio la latenza in 02/14/2020, fare clic sul punto di data.</span><span class="sxs-lookup"><span data-stu-id="bfb03-193">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="bfb03-194">E il grafico di tendenza oraria in fondo verrà aggiornato per visualizzare il numero orario.</span><span class="sxs-lookup"><span data-stu-id="bfb03-194">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="bfb03-195">È possibile controllare il SBCs o sollevare un biglietto con il servizio di assistenza MS Service Desk.</span><span class="sxs-lookup"><span data-stu-id="bfb03-195">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![Screenshot: report di Call Quality dashboard PSTN](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="bfb03-197">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="bfb03-197">Related topics</span></span>

[<span data-ttu-id="bfb03-198">Usare Power BI per analizzare i dati di Call Quality dashboard per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bfb03-198">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)

[<span data-ttu-id="bfb03-199">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="bfb03-199">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)