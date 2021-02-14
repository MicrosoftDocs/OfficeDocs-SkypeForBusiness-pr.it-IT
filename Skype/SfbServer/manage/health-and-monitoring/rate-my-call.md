---
title: Valutare la chiamata in Skype for Business Server
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
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: 'Riepilogo: informazioni sulla funzionalità Valuta la mia chiamata in Skype for Business Server.'
ms.openlocfilehash: 597a8213576e7aa2316ace68ed91288475df2a0d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814336"
---
# <a name="rate-my-call-in-skype-for-business-server"></a><span data-ttu-id="aec14-103">Valutare la chiamata in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="aec14-103">Rate my Call in Skype for Business Server</span></span>

<span data-ttu-id="aec14-104">**Riepilogo:** Informazioni sulla funzionalità Valuta la mia chiamata in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="aec14-104">**Summary:** Learn about the Rate My Call feature in Skype for Business Server.</span></span>

<span data-ttu-id="aec14-105">Rate My Call è stata una nuova funzionalità dei client Skype for Business 2015 e 2016 in Windows che fornisce alle aziende un modo per ottenere feedback dagli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="aec14-105">Rate My Call was a new feature in Skype for Business 2015 and 2016 clients on Windows that provides enterprises a way to get feedback from their end-users.</span></span>

<span data-ttu-id="aec14-106">La finestra Valuta la mia chiamata offre un sistema di classificazione "stella" e token predefiniti per le chiamate audio e video.</span><span class="sxs-lookup"><span data-stu-id="aec14-106">The Rate My Call window offers a "star" rating system and predefined tokens for audio and video calls.</span></span> <span data-ttu-id="aec14-107">Gli amministratori possono inoltre abilitare un campo personalizzato per inviare commenti e suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="aec14-107">In addition, administrators can enable a custom field to provide feedback.</span></span>

<span data-ttu-id="aec14-108">I dati raccolti sulla frequenza delle chiamate personali non sono attualmente inclusi in alcun rapporto di monitoraggio esistente, ma hanno un rapporto di monitoraggio separato.</span><span class="sxs-lookup"><span data-stu-id="aec14-108">Collected Rate My Call data is not currently included in any existing monitoring report, but it has a separate monitoring report.</span></span> <span data-ttu-id="aec14-109">I dati vengono raccolti in SQL a cui è possibile accedere eseguendo SQL query.</span><span class="sxs-lookup"><span data-stu-id="aec14-109">Data is collected in SQL tables that can be accessed by running SQL queries.</span></span>

## <a name="rate-my-call-prerequisites"></a><span data-ttu-id="aec14-110">Valutare i prerequisiti per le chiamate</span><span class="sxs-lookup"><span data-stu-id="aec14-110">Rate my Call Prerequisites</span></span>

<span data-ttu-id="aec14-111">Prima che gli utenti nella distribuzione di Skype for Business Server possano accedere alla funzionalità Valuta chiamate, è necessario distribuire e configurare il seguente set di componenti:</span><span class="sxs-lookup"><span data-stu-id="aec14-111">Before the users in your Skype for Business Server deployment can access Rate My Call functionality, the following set of components must be deployed and configured:</span></span>

-  <span data-ttu-id="aec14-112">È necessario disporre di Skype for Business Server installato (versione 9160 o successiva).</span><span class="sxs-lookup"><span data-stu-id="aec14-112">You must have Skype for Business Server installed (version 9160 or higher).</span></span>

- <span data-ttu-id="aec14-113">Chiedere agli utenti di installare e aggiornare l'ultima versione di Skype for Business e chiedere loro di usare l'interfaccia utente di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="aec14-113">Have your users install and update to the latest version of Skype for Business and also ask them to use the Skype for Business UI.</span></span>

- <span data-ttu-id="aec14-114">Gli utenti devono essere ospitati nel pool Front End di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="aec14-114">Users must be homed on the Skype for Business Server Front End pool.</span></span>

- <span data-ttu-id="aec14-115">È necessario disporre di un database di monitoraggio di Skype for Business Server distribuito e associato ai pool di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="aec14-115">You must have a Skype for Business Server monitoring database deployed and associated to your Skype for Business Server pools.</span></span>

- <span data-ttu-id="aec14-116">È consigliabile distribuire Call Quality Dashboard (CQD).</span><span class="sxs-lookup"><span data-stu-id="aec14-116">We recommend deploying Call Quality Dashboard (CQD).</span></span>

## <a name="configure-rate-my-call"></a><span data-ttu-id="aec14-117">Configurare La tariffa della chiamata</span><span class="sxs-lookup"><span data-stu-id="aec14-117">Configure Rate my Call</span></span>

<span data-ttu-id="aec14-118">La funzionalità Valuta chiamate è abilitata per impostazione predefinita nei criteri client con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="aec14-118">The Rate My Call feature is enabled by default in the Client policy with the following settings:</span></span>

- <span data-ttu-id="aec14-119">Percentuale visualizzazione chiamate - 10%</span><span class="sxs-lookup"><span data-stu-id="aec14-119">Rate My Call Display Percentage - 10%</span></span>

- <span data-ttu-id="aec14-120">Rate My Call Allow Custom User Feedback - disabled</span><span class="sxs-lookup"><span data-stu-id="aec14-120">Rate My Call Allow Custom User Feedback - disabled</span></span>

<span data-ttu-id="aec14-121">Non è necessaria alcuna azione per abilitare la funzionalità di base, ma se vuoi un feedback personalizzato dovrai abilitarla separatamente.</span><span class="sxs-lookup"><span data-stu-id="aec14-121">There is no action required to enable the base feature, however but if you want custom feedback you will need to enable it separately.</span></span> <span data-ttu-id="aec14-122">Il cmdlet Windows PowerShell seguente è un esempio di abilitazione del feedback personalizzato dell'utente finale e modifica dell'intervallo dal 10% all'80%.</span><span class="sxs-lookup"><span data-stu-id="aec14-122">The following Windows PowerShell cmdlet is an example of enabling custom end user feedback and changing the interval from 10% to 80%.</span></span>

```PowerShell
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 -RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a><span data-ttu-id="aec14-123">Accessing Rate My Call Data</span><span class="sxs-lookup"><span data-stu-id="aec14-123">Accessing Rate My Call Data</span></span>

<span data-ttu-id="aec14-124">I dati degli utenti vengono raccolti in due tabelle nel database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="aec14-124">Data from users is collected in two tables in the monitoring database.</span></span>

 <span data-ttu-id="aec14-125">**[QoeMetrics]. [dbo]. [CallQualityFeedbackToken]** - Questa tabella contiene i risultati del polling dei token da parte degli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="aec14-125">**[QoeMetrics].[dbo].[CallQualityFeedbackToken]** - this table contains results of token polling by end users.</span></span>

 <span data-ttu-id="aec14-126">**[QoeMetrics]. [dbo]. [CallQualityFeedbackTokenDef]** - Questa tabella contiene le definizioni di token.</span><span class="sxs-lookup"><span data-stu-id="aec14-126">**[QoeMetrics].[dbo].[CallQualityFeedbackTokenDef]** - this table contains token definitions.</span></span>

<span data-ttu-id="aec14-127">Le definizioni di token sono codificate nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="aec14-127">Token definitions are coded as follows:</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="aec14-128">1 </span><span class="sxs-lookup"><span data-stu-id="aec14-128">1</span></span>  <br/> |<span data-ttu-id="aec14-129">DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="aec14-129">DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="aec14-130">2 </span><span class="sxs-lookup"><span data-stu-id="aec14-130">2</span></span>  <br/> | <span data-ttu-id="aec14-131">ElectronicFeedback</span><span class="sxs-lookup"><span data-stu-id="aec14-131">ElectronicFeedback</span></span> <br/> |
|<span data-ttu-id="aec14-132">3 </span><span class="sxs-lookup"><span data-stu-id="aec14-132">3</span></span>  <br/> | <span data-ttu-id="aec14-133">BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="aec14-133">BackgroundNoise</span></span> <br/> |
|<span data-ttu-id="aec14-134">4 </span><span class="sxs-lookup"><span data-stu-id="aec14-134">4</span></span>  <br/> |<span data-ttu-id="aec14-135">MuffledSpeech</span><span class="sxs-lookup"><span data-stu-id="aec14-135">MuffledSpeech</span></span>  <br/> |
|<span data-ttu-id="aec14-136">5 </span><span class="sxs-lookup"><span data-stu-id="aec14-136">5</span></span>  <br/> |<span data-ttu-id="aec14-137">Echo</span><span class="sxs-lookup"><span data-stu-id="aec14-137">Echo</span></span>  <br/> |
|<span data-ttu-id="aec14-138"> 21</span><span class="sxs-lookup"><span data-stu-id="aec14-138">21</span></span>  <br/> | <span data-ttu-id="aec14-139">FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="aec14-139">FrozenVideo</span></span> <br/> |
|<span data-ttu-id="aec14-140">22</span><span class="sxs-lookup"><span data-stu-id="aec14-140">22</span></span>  <br/> | <span data-ttu-id="aec14-141">PixelatedVideo</span><span class="sxs-lookup"><span data-stu-id="aec14-141">PixelatedVideo</span></span> <br/> |
|<span data-ttu-id="aec14-142">23</span><span class="sxs-lookup"><span data-stu-id="aec14-142">23</span></span>  <br/> | <span data-ttu-id="aec14-143">BlurryImage</span><span class="sxs-lookup"><span data-stu-id="aec14-143">BlurryImage</span></span> <br/> |
|<span data-ttu-id="aec14-144">24</span><span class="sxs-lookup"><span data-stu-id="aec14-144">24</span></span>  <br/> | <span data-ttu-id="aec14-145">PoorColor</span><span class="sxs-lookup"><span data-stu-id="aec14-145">PoorColor</span></span> <br/> |
|<span data-ttu-id="aec14-146">25</span><span class="sxs-lookup"><span data-stu-id="aec14-146">25</span></span>  <br/> | <span data-ttu-id="aec14-147">DarkVideo</span><span class="sxs-lookup"><span data-stu-id="aec14-147">DarkVideo</span></span> <br/> |
|<span data-ttu-id="aec14-148">101</span><span class="sxs-lookup"><span data-stu-id="aec14-148">101</span></span>  <br/> |<span data-ttu-id="aec14-149">Audio_SilentLocal</span><span class="sxs-lookup"><span data-stu-id="aec14-149">Audio_SilentLocal</span></span>  <br/> |
|<span data-ttu-id="aec14-150">102</span><span class="sxs-lookup"><span data-stu-id="aec14-150">102</span></span>  <br/> |<span data-ttu-id="aec14-151">Audio_SilentRemote</span><span class="sxs-lookup"><span data-stu-id="aec14-151">Audio_SilentRemote</span></span>  <br/> |
|<span data-ttu-id="aec14-152">103</span><span class="sxs-lookup"><span data-stu-id="aec14-152">103</span></span>  <br/> |<span data-ttu-id="aec14-153">Audio_Echo</span><span class="sxs-lookup"><span data-stu-id="aec14-153">Audio_Echo</span></span>  <br/> |
|<span data-ttu-id="aec14-154">104</span><span class="sxs-lookup"><span data-stu-id="aec14-154">104</span></span>  <br/> |<span data-ttu-id="aec14-155">Audio_BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="aec14-155">Audio_BackgroundNoise</span></span>  <br/> |
|<span data-ttu-id="aec14-156">105</span><span class="sxs-lookup"><span data-stu-id="aec14-156">105</span></span>  <br/> |<span data-ttu-id="aec14-157">Audio_LowSound</span><span class="sxs-lookup"><span data-stu-id="aec14-157">Audio_LowSound</span></span>  <br/> |
|<span data-ttu-id="aec14-158">106</span><span class="sxs-lookup"><span data-stu-id="aec14-158">106</span></span>  <br/> |<span data-ttu-id="aec14-159">Audio_Dropped</span><span class="sxs-lookup"><span data-stu-id="aec14-159">Audio_Dropped</span></span>  <br/> |
|<span data-ttu-id="aec14-160">107</span><span class="sxs-lookup"><span data-stu-id="aec14-160">107</span></span>  <br/> |<span data-ttu-id="aec14-161">Audio_DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="aec14-161">Audio_DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="aec14-162">108</span><span class="sxs-lookup"><span data-stu-id="aec14-162">108</span></span>  <br/> |<span data-ttu-id="aec14-163">Audio_Interrupted</span><span class="sxs-lookup"><span data-stu-id="aec14-163">Audio_Interrupted</span></span>  <br/> |
|<span data-ttu-id="aec14-164">109</span><span class="sxs-lookup"><span data-stu-id="aec14-164">109</span></span>  <br/> |<span data-ttu-id="aec14-165">Audio_Other</span><span class="sxs-lookup"><span data-stu-id="aec14-165">Audio_Other</span></span>  <br/> |
|<span data-ttu-id="aec14-166">201</span><span class="sxs-lookup"><span data-stu-id="aec14-166">201</span></span>  <br/> |<span data-ttu-id="aec14-167">Video_NoLocalVideo</span><span class="sxs-lookup"><span data-stu-id="aec14-167">Video_NoLocalVideo</span></span>  <br/> |
|<span data-ttu-id="aec14-168">202</span><span class="sxs-lookup"><span data-stu-id="aec14-168">202</span></span>  <br/> |<span data-ttu-id="aec14-169">Video_NoRemoteVideo</span><span class="sxs-lookup"><span data-stu-id="aec14-169">Video_NoRemoteVideo</span></span>  <br/> |
|<span data-ttu-id="aec14-170">203</span><span class="sxs-lookup"><span data-stu-id="aec14-170">203</span></span>  <br/> |<span data-ttu-id="aec14-171">Video_LowQuality</span><span class="sxs-lookup"><span data-stu-id="aec14-171">Video_LowQuality</span></span>  <br/> |
|<span data-ttu-id="aec14-172">204</span><span class="sxs-lookup"><span data-stu-id="aec14-172">204</span></span>  <br/> |<span data-ttu-id="aec14-173">Video_FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="aec14-173">Video_FrozenVideo</span></span>  <br/> |
|<span data-ttu-id="aec14-174">205</span><span class="sxs-lookup"><span data-stu-id="aec14-174">205</span></span>  <br/> |<span data-ttu-id="aec14-175">Video_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="aec14-175">Video_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="aec14-176">206</span><span class="sxs-lookup"><span data-stu-id="aec14-176">206</span></span>  <br/> |<span data-ttu-id="aec14-177">Video_DarkVideo</span><span class="sxs-lookup"><span data-stu-id="aec14-177">Video_DarkVideo</span></span>  <br/> |
|<span data-ttu-id="aec14-178">207</span><span class="sxs-lookup"><span data-stu-id="aec14-178">207</span></span>  <br/> |<span data-ttu-id="aec14-179">Video_NoAudioSync</span><span class="sxs-lookup"><span data-stu-id="aec14-179">Video_NoAudioSync</span></span>  <br/> |
|<span data-ttu-id="aec14-180">208</span><span class="sxs-lookup"><span data-stu-id="aec14-180">208</span></span>  <br/> |<span data-ttu-id="aec14-181">Video_Other</span><span class="sxs-lookup"><span data-stu-id="aec14-181">Video_Other</span></span>  <br/> |
|<span data-ttu-id="aec14-182">301</span><span class="sxs-lookup"><span data-stu-id="aec14-182">301</span></span>  <br/> |<span data-ttu-id="aec14-183">Pstn_DialPad</span><span class="sxs-lookup"><span data-stu-id="aec14-183">Pstn_DialPad</span></span>  <br/> |
|<span data-ttu-id="aec14-184">401</span><span class="sxs-lookup"><span data-stu-id="aec14-184">401</span></span>  <br/> |<span data-ttu-id="aec14-185">SS_NoContentLocal</span><span class="sxs-lookup"><span data-stu-id="aec14-185">SS_NoContentLocal</span></span>  <br/> |
|<span data-ttu-id="aec14-186">402</span><span class="sxs-lookup"><span data-stu-id="aec14-186">402</span></span>  <br/> |<span data-ttu-id="aec14-187">SS_NoContentRemote</span><span class="sxs-lookup"><span data-stu-id="aec14-187">SS_NoContentRemote</span></span>  <br/> |
|<span data-ttu-id="aec14-188">403</span><span class="sxs-lookup"><span data-stu-id="aec14-188">403</span></span>  <br/> |<span data-ttu-id="aec14-189">SS_CantPresent</span><span class="sxs-lookup"><span data-stu-id="aec14-189">SS_CantPresent</span></span>  <br/> |
|<span data-ttu-id="aec14-190">404</span><span class="sxs-lookup"><span data-stu-id="aec14-190">404</span></span>  <br/> |<span data-ttu-id="aec14-191">SS_LowQuality</span><span class="sxs-lookup"><span data-stu-id="aec14-191">SS_LowQuality</span></span>  <br/> |
|<span data-ttu-id="aec14-192">405</span><span class="sxs-lookup"><span data-stu-id="aec14-192">405</span></span>  <br/> |<span data-ttu-id="aec14-193">SS_Freezing</span><span class="sxs-lookup"><span data-stu-id="aec14-193">SS_Freezing</span></span>  <br/> |
|<span data-ttu-id="aec14-194">406</span><span class="sxs-lookup"><span data-stu-id="aec14-194">406</span></span>  <br/> |<span data-ttu-id="aec14-195">SS_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="aec14-195">SS_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="aec14-196">407</span><span class="sxs-lookup"><span data-stu-id="aec14-196">407</span></span>  <br/> |<span data-ttu-id="aec14-197">SS_LargeDelay</span><span class="sxs-lookup"><span data-stu-id="aec14-197">SS_LargeDelay</span></span>  <br/> |
|<span data-ttu-id="aec14-198">408</span><span class="sxs-lookup"><span data-stu-id="aec14-198">408</span></span>  <br/> |<span data-ttu-id="aec14-199">SS_Other</span><span class="sxs-lookup"><span data-stu-id="aec14-199">SS_Other</span></span>  <br/> |
|<span data-ttu-id="aec14-200">501</span><span class="sxs-lookup"><span data-stu-id="aec14-200">501</span></span>  <br/> |<span data-ttu-id="aec14-201">Reliabilty_Join</span><span class="sxs-lookup"><span data-stu-id="aec14-201">Reliabilty_Join</span></span>  <br/> |
|<span data-ttu-id="aec14-202">502</span><span class="sxs-lookup"><span data-stu-id="aec14-202">502</span></span>  <br/> |<span data-ttu-id="aec14-203">Reliabilty_Invite</span><span class="sxs-lookup"><span data-stu-id="aec14-203">Reliabilty_Invite</span></span>  <br/> |

 <span data-ttu-id="aec14-204">**[QoeMetrics]. [dbo]. [CallQualityFeedback]** Questa tabella contiene i risultati del polling del voto "Star" e del feedback dei clienti, se abilitati.</span><span class="sxs-lookup"><span data-stu-id="aec14-204">**[QoeMetrics].[dbo].[CallQualityFeedback]** This table contains polling results from "Star" voting and customer feedback if enabled.</span></span>

<span data-ttu-id="aec14-205">I dati delle tabelle possono essere chiamati utilizzando una query **select \* from [Table.Name]** o utilizzando Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="aec14-205">Data from tables can be called by using a **select \* from [Table.Name]** query or by using Microsoft SQL Server Management Studio.</span></span>

<span data-ttu-id="aec14-206">È possibile SQL query seguenti:</span><span class="sxs-lookup"><span data-stu-id="aec14-206">The following SQL queries can be used:</span></span>

 <span data-ttu-id="aec14-207">**Audio**</span><span class="sxs-lookup"><span data-stu-id="aec14-207">**Audio**</span></span>

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

 <span data-ttu-id="aec14-208">**Video**</span><span class="sxs-lookup"><span data-stu-id="aec14-208">**Video**</span></span>

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

## <a name="updating-token-definitions"></a><span data-ttu-id="aec14-209">Aggiornamento delle definizioni di token</span><span class="sxs-lookup"><span data-stu-id="aec14-209">Updating Token Definitions</span></span>

<span data-ttu-id="aec14-210">I client Skype for Business più recenti segnalano nuovi ID token di problema ( 100) che potrebbero non essere presenti \> in [QoeMetrics].[ dbo]. Tabella [CallQualityFeedbackTokenDef].</span><span class="sxs-lookup"><span data-stu-id="aec14-210">The latest Skype for Business clients report new problem token IDs (\> 100) that may not be present in your [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span> <span data-ttu-id="aec14-211">Per aggiornare la tabella di database con le definizioni di token più recenti, è possibile eseguire il comando SQL seguente nel database di monitoraggio usando Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="aec14-211">To update the database table with the latest token definitions, the below SQL command can be run on the monitoring database using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="aec14-212">Questo comando sostituirà tutte le voci in [QoeMetrics]. [dbo]. Tabella [CallQualityFeedbackTokenDef].</span><span class="sxs-lookup"><span data-stu-id="aec14-212">This command will replace all entries in the [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span>

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


