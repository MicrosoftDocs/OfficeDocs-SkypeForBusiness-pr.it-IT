---
title: Uso del report di routing diretto PSTN di Call Quality dashboard
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
description: Usare il report routing diretto PSTN di Call Quality dashboard per monitorare e risolvere i problemi di chiamata PSTN in Microsoft teams.
ms.openlocfilehash: 32d91d56e51c5706c3e460029312f3b6bb6948c3
ms.sourcegitcommit: 98fcfc03c55917d0aca48b7bd97988f81e8930c1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/07/2020
ms.locfileid: "42559487"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="3c04a-103">Uso del report di routing diretto PSTN di Call Quality dashboard</span><span class="sxs-lookup"><span data-stu-id="3c04a-103">Using the CQD PSTN Direct Routing Report</span></span>

<span data-ttu-id="3c04a-104">Novità di marzo 2020 è stato aggiunto un report di routing diretto PSTN di Call Quality Dashboard ai modelli di [query di Power bi scaricabili per Call Quality dashboard](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="3c04a-104">New in March 2020, we've added a CQD PSTN Direct Routing Report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="3c04a-105">Il report routing diretto PSTN di Call Quality dashboard consente ai clienti di comprendere i modelli di utilizzo e la qualità dei servizi PSTN monitorare le informazioni su SBC, il servizio di telefonia, i parametri di rete e i dettagli del rapporto di efficacia della rete e l'utilizzo della servizio.</span><span class="sxs-lookup"><span data-stu-id="3c04a-105">The CQD PSTN Direct Routing Report helps customers to understand the usage patterns and quality of their PSTN services monitor information about your SBC, the telephony service, the network parameters, and Network Effectiveness Ratio details and usage of the service.</span></span> <span data-ttu-id="3c04a-106">Queste informazioni consentono di identificare i problemi, incluso il motivo per cui sono state eliminate le chiamate.</span><span class="sxs-lookup"><span data-stu-id="3c04a-106">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="3c04a-107">Ad esempio, potrai sapere quando il volume scende, quante chiamate vengono influenzate da quale motivo.</span><span class="sxs-lookup"><span data-stu-id="3c04a-107">For example, you will be able to know when volume drops, how many calls get affected by what reason.</span></span>

<span data-ttu-id="3c04a-108">Il report routing diretto PSTN di Call Quality dashboard include quattro sezioni:</span><span class="sxs-lookup"><span data-stu-id="3c04a-108">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="3c04a-109">Panoramica PSTN</span><span class="sxs-lookup"><span data-stu-id="3c04a-109">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="3c04a-110">Dettagli del servizio</span><span class="sxs-lookup"><span data-stu-id="3c04a-110">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="3c04a-111">Rapporto efficacia di rete</span><span class="sxs-lookup"><span data-stu-id="3c04a-111">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="3c04a-112">Parametri di rete</span><span class="sxs-lookup"><span data-stu-id="3c04a-112">Network Parameters</span></span>](#network-parameters)

## <a name="pstn-overview"></a><span data-ttu-id="3c04a-113">Panoramica PSTN</span><span class="sxs-lookup"><span data-stu-id="3c04a-113">PSTN Overview</span></span>

<span data-ttu-id="3c04a-114">Il report routing diretto PSTN di Call Quality dashboard fornisce le informazioni seguenti relative all'integrità complessiva del servizio per gli ultimi 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="3c04a-114">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="3c04a-115">![Screenshot: report di Call Quality dashboard PSTN](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="3c04a-115">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="3c04a-116">Ad esempio, se si è interessati all'uso e all'integrità generali di tutte le chiamate in ingresso che attraversano SBC abc.bca.adatum.biz con noi come paese interno:</span><span class="sxs-lookup"><span data-stu-id="3c04a-116">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="3c04a-117">**Chiamata fuori**</span><span class="sxs-lookup"><span data-stu-id="3c04a-117">**Call Out**</span></span> | <span data-ttu-id="3c04a-118">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="3c04a-118">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="3c04a-119">1</span><span class="sxs-lookup"><span data-stu-id="3c04a-119">1</span></span>            | <span data-ttu-id="3c04a-120">È possibile usare i filtri nella parte superiore per eseguire il drill-down e selezionare ByotIn come tipo di chiamata, abc.bca.contoso.com come controller di bordo sessione e Stati Uniti come paese interno.</span><span class="sxs-lookup"><span data-stu-id="3c04a-120">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="3c04a-121">2</span><span class="sxs-lookup"><span data-stu-id="3c04a-121">2</span></span>            | <span data-ttu-id="3c04a-122">Tendenza all'uso degli ultimi 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="3c04a-122">Usage trend for the past 180 days.</span></span> <span data-ttu-id="3c04a-123">È possibile trovare report dettagli utilizzo nella pagina Dettagli servizio.</span><span class="sxs-lookup"><span data-stu-id="3c04a-123">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="3c04a-124">3</span><span class="sxs-lookup"><span data-stu-id="3c04a-124">3</span></span>            | <span data-ttu-id="3c04a-125">Ritardo di post-chiamata, latenza, jitter e tendenza alla perdita di pacchetti per gli ultimi 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="3c04a-125">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="3c04a-126">È possibile trovare report dettagli nella pagina parametri di rete.</span><span class="sxs-lookup"><span data-stu-id="3c04a-126">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="3c04a-127">4</span><span class="sxs-lookup"><span data-stu-id="3c04a-127">4</span></span>            | <span data-ttu-id="3c04a-128">Chiamata simultanea e tendenza utente attiva giornaliera per gli ultimi 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="3c04a-128">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="3c04a-129">Questo grafico può aiutare a comprendere il volume massimo del servizio.</span><span class="sxs-lookup"><span data-stu-id="3c04a-129">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="3c04a-130">5</span><span class="sxs-lookup"><span data-stu-id="3c04a-130">5</span></span>            | <span data-ttu-id="3c04a-131">La qualità del servizio in primo piano è stata interessata per gli ultimi 180 giorni.</span><span class="sxs-lookup"><span data-stu-id="3c04a-131">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="3c04a-132">È possibile trovare informazioni dettagliate sull'integrità dei servizi nella pagina NER (Network effective ratio).</span><span class="sxs-lookup"><span data-stu-id="3c04a-132">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="3c04a-133">Dettagli del servizio</span><span class="sxs-lookup"><span data-stu-id="3c04a-133">Service Details</span></span>

<span data-ttu-id="3c04a-134">Questa pagina fornisce le tendenze di utilizzo del servizio al giorno e la ripartizione dei feedback degli utenti per geografica.</span><span class="sxs-lookup"><span data-stu-id="3c04a-134">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="3c04a-135">**Totale chiamate di tentativo-** Totale tentativo chiamate in tale intervallo di tempo, incluse le chiamate successo e non riuscito</span><span class="sxs-lookup"><span data-stu-id="3c04a-135">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="3c04a-136">**Totale chiamate connesse-** Totale chiamate connesse nell'intervallo di tempo</span><span class="sxs-lookup"><span data-stu-id="3c04a-136">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="3c04a-137">**Minuti totali-** Utilizzo totale dei minuti nell'intervallo di tempo</span><span class="sxs-lookup"><span data-stu-id="3c04a-137">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="3c04a-138">**Utenti attivi giornalieri (DAU)-** Numero di utenti attivi giornalieri che hanno effettuato almeno una chiamata connessa in quel giorno</span><span class="sxs-lookup"><span data-stu-id="3c04a-138">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="3c04a-139">**Chiamate simultanee:** Numero massimo di chiamate attive simultanee in un minuto</span><span class="sxs-lookup"><span data-stu-id="3c04a-139">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="3c04a-140">**Feedback degli utenti:** Il Punteggio "Vota la mia chiamata" proviene dall'utente.</span><span class="sxs-lookup"><span data-stu-id="3c04a-140">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="3c04a-141">3-5 è considerato una buona chiamata.</span><span class="sxs-lookup"><span data-stu-id="3c04a-141">3-5 is considered as a good call.</span></span> <span data-ttu-id="3c04a-142">1-2 viene considerato come una chiamata errata.</span><span class="sxs-lookup"><span data-stu-id="3c04a-142">1-2 is considered as a bad call.</span></span>

![Screenshot: report di Call Quality dashboard PSTN](media/CQD-PSTN-report2.png)

<span data-ttu-id="3c04a-144">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3c04a-144">For example:</span></span>

1.  <span data-ttu-id="3c04a-145">Se viene visualizzata la durata media delle chiamate scende a 0 in 02/14/2020, è possibile verificare se il volume delle chiamate è normale e verificare se esiste una grande discrepanza tra le chiamate di connessione totale e il tentativo totale.</span><span class="sxs-lookup"><span data-stu-id="3c04a-145">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="3c04a-146">Quindi Vai alla pagina rapporto efficacia Network per investire sui motivi di errore di chiamata.</span><span class="sxs-lookup"><span data-stu-id="3c04a-146">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="3c04a-147">Se nella mappa di feedback degli utenti viene visualizzato un numero crescente di punti rossi, è possibile accedere alla pagina rapporto di efficacia della rete e al parametro di rete per verificare se sono presenti anomalie e si può alzare un biglietto usando il servizio di assistenza MS.</span><span class="sxs-lookup"><span data-stu-id="3c04a-147">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="3c04a-148">Rapporto efficacia di rete</span><span class="sxs-lookup"><span data-stu-id="3c04a-148">Network Effectiveness Ratio</span></span>

<span data-ttu-id="3c04a-149">Questa è la stessa metrica visualizzata nel dashboard integrità generale.</span><span class="sxs-lookup"><span data-stu-id="3c04a-149">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="3c04a-150">È possibile controllare il numero di NER ogni ora con le chiamate interessate in dettaglio per entrambe le direzioni delle chiamate (in ingresso/in uscita) nel rapporto oraria di efficacia della rete e nel grafico motivo finale chiamata seguente.</span><span class="sxs-lookup"><span data-stu-id="3c04a-150">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="3c04a-151">**Ner** -l'abilità (%) di una rete per consegnare le chiamate misurando il numero di chiamate inviate rispetto al numero di chiamate recapitate a un destinatario.</span><span class="sxs-lookup"><span data-stu-id="3c04a-151">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="3c04a-152">**Codice di risposta SIP**: il codice di risposta intero a tre cifre Mostra lo stato della chiamata.</span><span class="sxs-lookup"><span data-stu-id="3c04a-152">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="3c04a-153">**Codice di risposta Microsoft**-codice di risposta inviato dal componente Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3c04a-153">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="3c04a-154">**Descrizione** : la fase di Reason che corrisponde al codice di risposta SIP e al codice di risposta Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3c04a-154">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="3c04a-155">**Numero di chiamate interessate** : il numero totale di chiamate è stato influenzato durante l'intervallo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="3c04a-155">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![Screenshot: report di Call Quality dashboard PSTN](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="3c04a-157">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3c04a-157">For example:</span></span>

![Screenshot: report di Call Quality dashboard PSTN](media/CQD-PSTN-report4.png)

<span data-ttu-id="3c04a-159">Se il Daily NER ha un dip in 02/05/2020, è possibile fare clic sulla data e gli altri grafici faranno zoom su quella specifica data.</span><span class="sxs-lookup"><span data-stu-id="3c04a-159">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![Screenshot: report di Call Quality dashboard PSTN](media/CQD-PSTN-report5.png)

<span data-ttu-id="3c04a-161">Dalla buona percentuale di tendenza per ogni ora è possibile trovare il DIP che si verifica intorno a 21:00.</span><span class="sxs-lookup"><span data-stu-id="3c04a-161">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="3c04a-162">Quindi fare di nuovo clic per ingrandire l'ora 21 e controllare i dettagli delle chiamate effettuate per vedere quante chiamate non sono state eseguite in quell'ora e quali sono i motivi per le chiamate finali.</span><span class="sxs-lookup"><span data-stu-id="3c04a-162">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="3c04a-163">Se il problema non è correlato a SBC, è possibile iniziare a eseguire le riprese in caso di problemi su qualsiasi problema o report SBC.</span><span class="sxs-lookup"><span data-stu-id="3c04a-163">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="3c04a-164">Parametri di rete</span><span class="sxs-lookup"><span data-stu-id="3c04a-164">Network Parameters</span></span>

<span data-ttu-id="3c04a-165">Tutti i parametri di rete vengono misurati dall'interfaccia di routing diretto al controller di bordo della sessione.</span><span class="sxs-lookup"><span data-stu-id="3c04a-165">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="3c04a-166">Per informazioni sui valori consigliati, vedere [preparare la rete dell'organizzazione per Microsoft teams](prepare-network.md)e esaminare i valori consigliati di Microsoft Edge per il cliente.</span><span class="sxs-lookup"><span data-stu-id="3c04a-166">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="3c04a-167">**Jitter** : è la misura di millisecondi di variazione nel tempo di ritardo di propagazione della rete calcolato tra due endpoint usando RTCP (il protocollo di controllo RTP).</span><span class="sxs-lookup"><span data-stu-id="3c04a-167">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="3c04a-168">**Perdita di pacchetti** : è una misura del pacchetto che non è riuscita ad arrivare; viene calcolato tra due endpoint.</span><span class="sxs-lookup"><span data-stu-id="3c04a-168">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="3c04a-169">**Latenza** -(nota anche come tempo di andata e ritorno) è il periodo di tempo necessario per l'invio di un segnale più il tempo necessario per il riconoscimento del segnale da ricevere.</span><span class="sxs-lookup"><span data-stu-id="3c04a-169">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="3c04a-170">Questo ritardo temporale è costituito dai tempi di propagazione tra i due punti di un segnale.</span><span class="sxs-lookup"><span data-stu-id="3c04a-170">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![Screenshot: report di Call Quality dashboard PSTN](media/CQD-PSTN-report6.png)

<span data-ttu-id="3c04a-172">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3c04a-172">For example:</span></span>

<span data-ttu-id="3c04a-173">Se viene visualizzato un picco su uno dei quattro grafici (latenza, jitter, tasso di perdita del pacchetto, ritardo della chiamata) per una data specifica, ad esempio la latenza in 02/14/2020, fare clic sul punto di data.</span><span class="sxs-lookup"><span data-stu-id="3c04a-173">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="3c04a-174">E il grafico di tendenza oraria in fondo verrà aggiornato per visualizzare il numero orario.</span><span class="sxs-lookup"><span data-stu-id="3c04a-174">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="3c04a-175">È possibile controllare il SBCs o sollevare un biglietto con il servizio di assistenza MS Service Desk.</span><span class="sxs-lookup"><span data-stu-id="3c04a-175">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![Screenshot: report di Call Quality dashboard PSTN](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="3c04a-177">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3c04a-177">Related topics</span></span>

[<span data-ttu-id="3c04a-178">Usare Power BI per analizzare i dati di Call Quality dashboard per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3c04a-178">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)