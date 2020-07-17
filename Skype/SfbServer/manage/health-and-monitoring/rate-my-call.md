---
title: Valutare la chiamata in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: 'Riepilogo: informazioni sulla frequenza delle funzionalità di chiamata in Skype for Business Server.'
ms.openlocfilehash: 15f2bcbcf75690baaa350541f5f1da134fb32025
ms.sourcegitcommit: a73df97a06ea860bfaf5387e0acbf3c724697e14
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "44902220"
---
# <a name="rate-my-call-in-skype-for-business-server"></a><span data-ttu-id="56588-103">Valutare la chiamata in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="56588-103">Rate my Call in Skype for Business Server</span></span>

<span data-ttu-id="56588-104">**Riepilogo:** Per ulteriori informazioni, vedere la caratteristica Rate My Call in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="56588-104">**Summary:** Learn about the Rate My Call feature in Skype for Business Server.</span></span>

<span data-ttu-id="56588-105">Rate My Call è una nuova funzionalità di client Skype for business 2015 e 2016 su Windows che offre alle aziende un modo per ottenere commenti e suggerimenti dagli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="56588-105">Rate My Call was a new feature in Skype for Business 2015 and 2016 clients on Windows that provides enterprises a way to get feedback from their end-users.</span></span>

<span data-ttu-id="56588-106">La finestra Rate My Call offre un sistema di classificazione "stella" e i token predefiniti per le chiamate audio e video.</span><span class="sxs-lookup"><span data-stu-id="56588-106">The Rate My Call window offers a "star" rating system and predefined tokens for audio and video calls.</span></span> <span data-ttu-id="56588-107">Gli amministratori possono inoltre abilitare un campo personalizzato per fornire commenti e suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="56588-107">In addition, administrators can enable a custom field to provide feedback.</span></span>

<span data-ttu-id="56588-108">Tasso di raccolta i dati di chiamata non sono attualmente inclusi in alcun rapporto di monitoraggio esistente, ma dispongono di un rapporto di monitoraggio separato.</span><span class="sxs-lookup"><span data-stu-id="56588-108">Collected Rate My Call data is not currently included in any existing monitoring report, but it has a separate monitoring report.</span></span> <span data-ttu-id="56588-109">I dati vengono raccolti nelle tabelle SQL a cui è possibile accedere eseguendo query SQL.</span><span class="sxs-lookup"><span data-stu-id="56588-109">Data is collected in SQL tables that can be accessed by running SQL queries.</span></span>

## <a name="rate-my-call-prerequisites"></a><span data-ttu-id="56588-110">Valutare i prerequisiti di chiamata</span><span class="sxs-lookup"><span data-stu-id="56588-110">Rate my Call Prerequisites</span></span>

<span data-ttu-id="56588-111">Prima che gli utenti della distribuzione di Skype for Business Server possano accedere alla funzionalità di chiamata, è necessario distribuire e configurare il seguente set di componenti:</span><span class="sxs-lookup"><span data-stu-id="56588-111">Before the users in your Skype for Business Server deployment can access Rate My Call functionality, the following set of components must be deployed and configured:</span></span>

-  <span data-ttu-id="56588-112">È necessario che sia installato Skype for Business Server (versione 9160 o superiore).</span><span class="sxs-lookup"><span data-stu-id="56588-112">You must have Skype for Business Server installed (version 9160 or higher).</span></span>

- <span data-ttu-id="56588-113">Gli utenti possono installare e aggiornare la versione più recente di Skype for business e chiedere loro di usare l'interfaccia utente di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="56588-113">Have your users install and update to the latest version of Skype for Business and also ask them to use the Skype for Business UI.</span></span>

- <span data-ttu-id="56588-114">Gli utenti devono essere ospitati nel pool Front End di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="56588-114">Users must be homed on the Skype for Business Server Front End pool.</span></span>

- <span data-ttu-id="56588-115">È necessario disporre di un database di monitoraggio di Skype for Business Server distribuito e associato ai pool di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="56588-115">You must have a Skype for Business Server monitoring database deployed and associated to your Skype for Business Server pools.</span></span>

- <span data-ttu-id="56588-116">Si consiglia di distribuire Call Quality Dashboard (CQD).</span><span class="sxs-lookup"><span data-stu-id="56588-116">We recommend deploying Call Quality Dashboard (CQD).</span></span>

## <a name="configure-rate-my-call"></a><span data-ttu-id="56588-117">Configurare Rate My Call</span><span class="sxs-lookup"><span data-stu-id="56588-117">Configure Rate my Call</span></span>

<span data-ttu-id="56588-118">La caratteristica Rate My Call è abilitata per impostazione predefinita nel criterio client con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="56588-118">The Rate My Call feature is enabled by default in the Client policy with the following settings:</span></span>

- <span data-ttu-id="56588-119">Valutare la percentuale di visualizzazione della chiamata-10%</span><span class="sxs-lookup"><span data-stu-id="56588-119">Rate My Call Display Percentage - 10%</span></span>

- <span data-ttu-id="56588-120">Rate My Call allow custom user feedback-disabled</span><span class="sxs-lookup"><span data-stu-id="56588-120">Rate My Call Allow Custom User Feedback - disabled</span></span>

<span data-ttu-id="56588-121">Non è necessaria alcuna azione per abilitare la funzionalità di base, ma se si desidera che il feedback personalizzato sia necessario abilitarlo separatamente.</span><span class="sxs-lookup"><span data-stu-id="56588-121">There is no action required to enable the base feature, however but if you want custom feedback you will need to enable it separately.</span></span> <span data-ttu-id="56588-122">Il cmdlet di Windows PowerShell seguente è un esempio di abilitazione dei feedback degli utenti finali personalizzati e modifica dell'intervallo tra il 10% e il 80%.</span><span class="sxs-lookup"><span data-stu-id="56588-122">The following Windows PowerShell cmdlet is an example of enabling custom end user feedback and changing the interval from 10% to 80%.</span></span>

```PowerShell
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 -RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a><span data-ttu-id="56588-123">Velocità di accesso ai dati delle chiamate</span><span class="sxs-lookup"><span data-stu-id="56588-123">Accessing Rate My Call Data</span></span>

<span data-ttu-id="56588-124">I dati degli utenti vengono raccolti in due tabelle nel database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="56588-124">Data from users is collected in two tables in the monitoring database.</span></span>

 <span data-ttu-id="56588-125">**[QoeMetrics]. [dbo]. [CallQualityFeedbackToken]** -Questa tabella contiene i risultati del polling dei token da parte degli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="56588-125">**[QoeMetrics].[dbo].[CallQualityFeedbackToken]** - this table contains results of token polling by end users.</span></span>

 <span data-ttu-id="56588-126">**[QoeMetrics]. [dbo]. [CallQualityFeedbackTokenDef]** -Questa tabella contiene le definizioni di token.</span><span class="sxs-lookup"><span data-stu-id="56588-126">**[QoeMetrics].[dbo].[CallQualityFeedbackTokenDef]** - this table contains token definitions.</span></span>

<span data-ttu-id="56588-127">Le definizioni dei token sono codificate come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="56588-127">Token definitions are coded as follows:</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="56588-128">1 </span><span class="sxs-lookup"><span data-stu-id="56588-128">1</span></span>  <br/> |<span data-ttu-id="56588-129">DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="56588-129">DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="56588-130">2 </span><span class="sxs-lookup"><span data-stu-id="56588-130">2</span></span>  <br/> | <span data-ttu-id="56588-131">ElectronicFeedback</span><span class="sxs-lookup"><span data-stu-id="56588-131">ElectronicFeedback</span></span> <br/> |
|<span data-ttu-id="56588-132">3 </span><span class="sxs-lookup"><span data-stu-id="56588-132">3</span></span>  <br/> | <span data-ttu-id="56588-133">Rumore</span><span class="sxs-lookup"><span data-stu-id="56588-133">BackgroundNoise</span></span> <br/> |
|<span data-ttu-id="56588-134">4 </span><span class="sxs-lookup"><span data-stu-id="56588-134">4</span></span>  <br/> |<span data-ttu-id="56588-135">MuffledSpeech</span><span class="sxs-lookup"><span data-stu-id="56588-135">MuffledSpeech</span></span>  <br/> |
|<span data-ttu-id="56588-136">5 </span><span class="sxs-lookup"><span data-stu-id="56588-136">5</span></span>  <br/> |<span data-ttu-id="56588-137">Echo</span><span class="sxs-lookup"><span data-stu-id="56588-137">Echo</span></span>  <br/> |
|<span data-ttu-id="56588-138"> 21</span><span class="sxs-lookup"><span data-stu-id="56588-138">21</span></span>  <br/> | <span data-ttu-id="56588-139">FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="56588-139">FrozenVideo</span></span> <br/> |
|<span data-ttu-id="56588-140">22</span><span class="sxs-lookup"><span data-stu-id="56588-140">22</span></span>  <br/> | <span data-ttu-id="56588-141">PixelatedVideo</span><span class="sxs-lookup"><span data-stu-id="56588-141">PixelatedVideo</span></span> <br/> |
|<span data-ttu-id="56588-142">23</span><span class="sxs-lookup"><span data-stu-id="56588-142">23</span></span>  <br/> | <span data-ttu-id="56588-143">BlurryImage</span><span class="sxs-lookup"><span data-stu-id="56588-143">BlurryImage</span></span> <br/> |
|<span data-ttu-id="56588-144">24</span><span class="sxs-lookup"><span data-stu-id="56588-144">24</span></span>  <br/> | <span data-ttu-id="56588-145">PoorColor</span><span class="sxs-lookup"><span data-stu-id="56588-145">PoorColor</span></span> <br/> |
|<span data-ttu-id="56588-146">25</span><span class="sxs-lookup"><span data-stu-id="56588-146">25</span></span>  <br/> | <span data-ttu-id="56588-147">DarkVideo</span><span class="sxs-lookup"><span data-stu-id="56588-147">DarkVideo</span></span> <br/> |
|<span data-ttu-id="56588-148">101</span><span class="sxs-lookup"><span data-stu-id="56588-148">101</span></span>  <br/> |<span data-ttu-id="56588-149">Audio_SilentLocal</span><span class="sxs-lookup"><span data-stu-id="56588-149">Audio_SilentLocal</span></span>  <br/> |
|<span data-ttu-id="56588-150">102</span><span class="sxs-lookup"><span data-stu-id="56588-150">102</span></span>  <br/> |<span data-ttu-id="56588-151">Audio_SilentRemote</span><span class="sxs-lookup"><span data-stu-id="56588-151">Audio_SilentRemote</span></span>  <br/> |
|<span data-ttu-id="56588-152">103</span><span class="sxs-lookup"><span data-stu-id="56588-152">103</span></span>  <br/> |<span data-ttu-id="56588-153">Audio_Echo</span><span class="sxs-lookup"><span data-stu-id="56588-153">Audio_Echo</span></span>  <br/> |
|<span data-ttu-id="56588-154">104</span><span class="sxs-lookup"><span data-stu-id="56588-154">104</span></span>  <br/> |<span data-ttu-id="56588-155">Audio_BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="56588-155">Audio_BackgroundNoise</span></span>  <br/> |
|<span data-ttu-id="56588-156">105</span><span class="sxs-lookup"><span data-stu-id="56588-156">105</span></span>  <br/> |<span data-ttu-id="56588-157">Audio_LowSound</span><span class="sxs-lookup"><span data-stu-id="56588-157">Audio_LowSound</span></span>  <br/> |
|<span data-ttu-id="56588-158">106</span><span class="sxs-lookup"><span data-stu-id="56588-158">106</span></span>  <br/> |<span data-ttu-id="56588-159">Audio_Dropped</span><span class="sxs-lookup"><span data-stu-id="56588-159">Audio_Dropped</span></span>  <br/> |
|<span data-ttu-id="56588-160">107</span><span class="sxs-lookup"><span data-stu-id="56588-160">107</span></span>  <br/> |<span data-ttu-id="56588-161">Audio_DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="56588-161">Audio_DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="56588-162">108</span><span class="sxs-lookup"><span data-stu-id="56588-162">108</span></span>  <br/> |<span data-ttu-id="56588-163">Audio_Interrupted</span><span class="sxs-lookup"><span data-stu-id="56588-163">Audio_Interrupted</span></span>  <br/> |
|<span data-ttu-id="56588-164">109</span><span class="sxs-lookup"><span data-stu-id="56588-164">109</span></span>  <br/> |<span data-ttu-id="56588-165">Audio_Other</span><span class="sxs-lookup"><span data-stu-id="56588-165">Audio_Other</span></span>  <br/> |
|<span data-ttu-id="56588-166">201</span><span class="sxs-lookup"><span data-stu-id="56588-166">201</span></span>  <br/> |<span data-ttu-id="56588-167">Video_NoLocalVideo</span><span class="sxs-lookup"><span data-stu-id="56588-167">Video_NoLocalVideo</span></span>  <br/> |
|<span data-ttu-id="56588-168">202</span><span class="sxs-lookup"><span data-stu-id="56588-168">202</span></span>  <br/> |<span data-ttu-id="56588-169">Video_NoRemoteVideo</span><span class="sxs-lookup"><span data-stu-id="56588-169">Video_NoRemoteVideo</span></span>  <br/> |
|<span data-ttu-id="56588-170">203</span><span class="sxs-lookup"><span data-stu-id="56588-170">203</span></span>  <br/> |<span data-ttu-id="56588-171">Video_LowQuality</span><span class="sxs-lookup"><span data-stu-id="56588-171">Video_LowQuality</span></span>  <br/> |
|<span data-ttu-id="56588-172">204</span><span class="sxs-lookup"><span data-stu-id="56588-172">204</span></span>  <br/> |<span data-ttu-id="56588-173">Video_FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="56588-173">Video_FrozenVideo</span></span>  <br/> |
|<span data-ttu-id="56588-174">205</span><span class="sxs-lookup"><span data-stu-id="56588-174">205</span></span>  <br/> |<span data-ttu-id="56588-175">Video_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="56588-175">Video_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="56588-176">206</span><span class="sxs-lookup"><span data-stu-id="56588-176">206</span></span>  <br/> |<span data-ttu-id="56588-177">Video_DarkVideo</span><span class="sxs-lookup"><span data-stu-id="56588-177">Video_DarkVideo</span></span>  <br/> |
|<span data-ttu-id="56588-178">207</span><span class="sxs-lookup"><span data-stu-id="56588-178">207</span></span>  <br/> |<span data-ttu-id="56588-179">Video_NoAudioSync</span><span class="sxs-lookup"><span data-stu-id="56588-179">Video_NoAudioSync</span></span>  <br/> |
|<span data-ttu-id="56588-180">208</span><span class="sxs-lookup"><span data-stu-id="56588-180">208</span></span>  <br/> |<span data-ttu-id="56588-181">Video_Other</span><span class="sxs-lookup"><span data-stu-id="56588-181">Video_Other</span></span>  <br/> |
|<span data-ttu-id="56588-182">301</span><span class="sxs-lookup"><span data-stu-id="56588-182">301</span></span>  <br/> |<span data-ttu-id="56588-183">Pstn_DialPad</span><span class="sxs-lookup"><span data-stu-id="56588-183">Pstn_DialPad</span></span>  <br/> |
|<span data-ttu-id="56588-184">401</span><span class="sxs-lookup"><span data-stu-id="56588-184">401</span></span>  <br/> |<span data-ttu-id="56588-185">SS_NoContentLocal</span><span class="sxs-lookup"><span data-stu-id="56588-185">SS_NoContentLocal</span></span>  <br/> |
|<span data-ttu-id="56588-186">402</span><span class="sxs-lookup"><span data-stu-id="56588-186">402</span></span>  <br/> |<span data-ttu-id="56588-187">SS_NoContentRemote</span><span class="sxs-lookup"><span data-stu-id="56588-187">SS_NoContentRemote</span></span>  <br/> |
|<span data-ttu-id="56588-188">403</span><span class="sxs-lookup"><span data-stu-id="56588-188">403</span></span>  <br/> |<span data-ttu-id="56588-189">SS_CantPresent</span><span class="sxs-lookup"><span data-stu-id="56588-189">SS_CantPresent</span></span>  <br/> |
|<span data-ttu-id="56588-190">404</span><span class="sxs-lookup"><span data-stu-id="56588-190">404</span></span>  <br/> |<span data-ttu-id="56588-191">SS_LowQuality</span><span class="sxs-lookup"><span data-stu-id="56588-191">SS_LowQuality</span></span>  <br/> |
|<span data-ttu-id="56588-192">405</span><span class="sxs-lookup"><span data-stu-id="56588-192">405</span></span>  <br/> |<span data-ttu-id="56588-193">SS_Freezing</span><span class="sxs-lookup"><span data-stu-id="56588-193">SS_Freezing</span></span>  <br/> |
|<span data-ttu-id="56588-194">406</span><span class="sxs-lookup"><span data-stu-id="56588-194">406</span></span>  <br/> |<span data-ttu-id="56588-195">SS_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="56588-195">SS_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="56588-196">407</span><span class="sxs-lookup"><span data-stu-id="56588-196">407</span></span>  <br/> |<span data-ttu-id="56588-197">SS_LargeDelay</span><span class="sxs-lookup"><span data-stu-id="56588-197">SS_LargeDelay</span></span>  <br/> |
|<span data-ttu-id="56588-198">408</span><span class="sxs-lookup"><span data-stu-id="56588-198">408</span></span>  <br/> |<span data-ttu-id="56588-199">SS_Other</span><span class="sxs-lookup"><span data-stu-id="56588-199">SS_Other</span></span>  <br/> |
|<span data-ttu-id="56588-200">501</span><span class="sxs-lookup"><span data-stu-id="56588-200">501</span></span>  <br/> |<span data-ttu-id="56588-201">Reliabilty_Join</span><span class="sxs-lookup"><span data-stu-id="56588-201">Reliabilty_Join</span></span>  <br/> |
|<span data-ttu-id="56588-202">502</span><span class="sxs-lookup"><span data-stu-id="56588-202">502</span></span>  <br/> |<span data-ttu-id="56588-203">Reliabilty_Invite</span><span class="sxs-lookup"><span data-stu-id="56588-203">Reliabilty_Invite</span></span>  <br/> |

 <span data-ttu-id="56588-204">**[QoeMetrics]. [dbo]. [CallQualityFeedback]** Questa tabella contiene i risultati del polling da "stella" voto e commenti dei clienti se abilitati.</span><span class="sxs-lookup"><span data-stu-id="56588-204">**[QoeMetrics].[dbo].[CallQualityFeedback]** This table contains polling results from "Star" voting and customer feedback if enabled.</span></span>

<span data-ttu-id="56588-205">I dati delle tabelle possono essere chiamati tramite una query **Select \* from [Table.Name]** oppure tramite Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="56588-205">Data from tables can be called by using a **select \* from [Table.Name]** query or by using Microsoft SQL Server Management Studio.</span></span>

<span data-ttu-id="56588-206">È possibile utilizzare le query SQL seguenti:</span><span class="sxs-lookup"><span data-stu-id="56588-206">The following SQL queries can be used:</span></span>

 <span data-ttu-id="56588-207">**Audio**</span><span class="sxs-lookup"><span data-stu-id="56588-207">**Audio**</span></span>

```SQL
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [AudioStream] AS a WITH (NOLOCK) ON -- only look at Audio related feedback
            a.MediaLineLabel = m.MediaLineLabel    
            and a.ConferenceDateTime = m.ConferenceDateTime 
            and a.SessionSeq = m.SessionSeq
            and a.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
            (CallerCqfToken.TokenId < 20 or (CallerCqfToken.TokenId > 100 and CallerCqfToken.TokenId < 200)) -- only look at Audio related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

 <span data-ttu-id="56588-208">**Video**</span><span class="sxs-lookup"><span data-stu-id="56588-208">**Video**</span></span>

```SQL
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [VideoStream] AS v WITH (NOLOCK) ON -- only look at Video related feedback
            v.MediaLineLabel = m.MediaLineLabel    
            and v.ConferenceDateTime = m.ConferenceDateTime 
            and v.SessionSeq = m.SessionSeq
            and v.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
           ((CallerCqfToken.TokenId > 20 and CallerCqfToken.TokenId < 100) or (CallerCqfToken.TokenId > 200 and CallerCqfToken.TokenId < 300)) -- only look at Video related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

## <a name="updating-token-definitions"></a><span data-ttu-id="56588-209">Aggiornamento delle definizioni di token</span><span class="sxs-lookup"><span data-stu-id="56588-209">Updating Token Definitions</span></span>

<span data-ttu-id="56588-210">I client Skype for business più recenti segnalano nuovi ID token di problema ( \> 100) che potrebbero non essere presenti nel [QoeMetrics]. [ dbo]. Tabella [CallQualityFeedbackTokenDef].</span><span class="sxs-lookup"><span data-stu-id="56588-210">The latest Skype for Business clients report new problem token IDs (\> 100) that may not be present in your [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span> <span data-ttu-id="56588-211">Per aggiornare la tabella di database con le definizioni dei token più recenti, è possibile eseguire il comando SQL seguente nel database di monitoraggio utilizzando Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="56588-211">To update the database table with the latest token definitions, the below SQL command can be run on the monitoring database using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="56588-212">Questo comando consente di sostituire tutte le voci in [QoeMetrics]. [dbo]. Tabella [CallQualityFeedbackTokenDef].</span><span class="sxs-lookup"><span data-stu-id="56588-212">This command will replace all entries in the [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span>

```SQL
DELETE FROM [CallQualityFeedbackTokenDef];
INSERT INTO [CallQualityFeedbackTokenDef] (TokenId, TokenDescription) VALUES
    (1,   N'DistortedSpeech'),
    (2,   N'ElectronicFeedback'),
    (3,   N'BackgroundNoise'),
    (4,   N'MuffledSpeech'),
    (5,   N'Echo'),
    (21,  N'FrozenVideo'),
    (22,  N'PixelatedVideo'),
    (23,  N'BlurryImage'),
    (24,  N'PoorColor'),
    (25,  N'DarkVideo'),
    (101, N'Audio_SilentLocal'),
    (102, N'Audio_SilentRemote'),
    (103, N'Audio_Echo'),
    (104, N'Audio_BackgroundNoise'),
    (105, N'Audio_LowSound'),
    (106, N'Audio_Dropped'),
    (107, N'Audio_DistortedSpeech'),
    (108, N'Audio_Interrupted'),
    (109, N'Audio_Other'),
    (201, N'Video_NoLocalVideo'),
    (202, N'Video_NoRemoteVideo'),
    (203, N'Video_LowQuality'),
    (204, N'Video_FrozenVideo'),
    (205, N'Video_StoppedUnexpectedly'),
    (206, N'Video_DarkVideo'),
    (207, N'Video_NoAudioSync'),
    (208, N'Video_Other'),
    (301, N'Pstn_DialPad'),
    (401, N'SS_NoContentLocal'),
    (402, N'SS_NoContentRemote'),
    (403, N'SS_CantPresent'),
    (404, N'SS_LowQuality'),
    (405, N'SS_Freezing'),
    (406, N'SS_StoppedUnexpectedly'),
    (407, N'SS_LargeDelay'),
    (408, N'SS_Other'),
    (501, N'Reliabilty_Join'),
    (502, N'Reliabilty_Invite');
```


