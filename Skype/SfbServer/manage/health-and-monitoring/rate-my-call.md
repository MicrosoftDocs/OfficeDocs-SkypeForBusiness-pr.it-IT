---
title: Vota la mia chiamata in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: 'Riepilogo: informazioni sulla caratteristica Vota la mia chiamata in Skype for Business Server.'
ms.openlocfilehash: 6902bdaa9b5021963d128bf67dab7adc8ab1d982
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991741"
---
# <a name="rate-my-call-in-skype-for-business-server"></a><span data-ttu-id="c14ec-103">Vota la mia chiamata in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c14ec-103">Rate my Call in Skype for Business Server</span></span>

<span data-ttu-id="c14ec-104">**Riepilogo:** Informazioni sulla caratteristica Vota la mia chiamata in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c14ec-104">**Summary:** Learn about the Rate My Call feature in Skype for Business Server.</span></span>

<span data-ttu-id="c14ec-105">Vota la mia chiamata è stata una nuova funzionalità nei client Skype for business 2015 e 2016 in Windows che offre alle aziende un modo per ottenere feedback dagli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="c14ec-105">Rate My Call was a new feature in Skype for Business 2015 and 2016 clients on Windows that provides enterprises a way to get feedback from their end-users.</span></span>

<span data-ttu-id="c14ec-106">La finestra Vota la mia chiamata offre un sistema di classificazione "stella" e i token predefiniti per le chiamate audio e video.</span><span class="sxs-lookup"><span data-stu-id="c14ec-106">The Rate My Call window offers a "star" rating system and predefined tokens for audio and video calls.</span></span> <span data-ttu-id="c14ec-107">Inoltre, gli amministratori possono abilitare un campo personalizzato per inviare commenti e suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="c14ec-107">In addition, administrators can enable a custom field to provide feedback.</span></span>

<span data-ttu-id="c14ec-108">Tasso di raccolta i dati delle chiamate non sono attualmente inclusi in un report di monitoraggio esistente, ma con un rapporto di monitoraggio distinto.</span><span class="sxs-lookup"><span data-stu-id="c14ec-108">Collected Rate My Call data is not currently included in any existing monitoring report, but it has a separate monitoring report.</span></span> <span data-ttu-id="c14ec-109">I dati vengono raccolti nelle tabelle SQL a cui è possibile accedere eseguendo query SQL.</span><span class="sxs-lookup"><span data-stu-id="c14ec-109">Data is collected in SQL tables that can be accessed by running SQL queries.</span></span>

## <a name="rate-my-call-prerequisites"></a><span data-ttu-id="c14ec-110">Valutare i prerequisiti per le chiamate</span><span class="sxs-lookup"><span data-stu-id="c14ec-110">Rate my Call Prerequisites</span></span>

<span data-ttu-id="c14ec-111">Prima che gli utenti della distribuzione di Skype for Business Server possano accedere alla funzionalità chiamata, è necessario distribuire e configurare il set di componenti seguente:</span><span class="sxs-lookup"><span data-stu-id="c14ec-111">Before the users in your Skype for Business Server deployment can access Rate My Call functionality, the following set of components must be deployed and configured:</span></span>

-  <span data-ttu-id="c14ec-112">È necessario avere installato Skype for Business Server (versione 9160 o successiva).</span><span class="sxs-lookup"><span data-stu-id="c14ec-112">You must have Skype for Business Server installed (version 9160 or higher).</span></span>

- <span data-ttu-id="c14ec-113">Gli utenti possono installare e aggiornare l'ultima versione di Skype for business e chiedere anche di usare l'interfaccia utente di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="c14ec-113">Have your users install and update to the latest version of Skype for Business and also ask them to use the Skype for Business UI.</span></span>

- <span data-ttu-id="c14ec-114">Gli utenti devono essere ospitati nel pool Front End di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c14ec-114">Users must be homed on the Skype for Business Server Front End pool.</span></span>

- <span data-ttu-id="c14ec-115">È necessario disporre di un database di monitoraggio di Skype for Business Server distribuito e associato ai pool di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c14ec-115">You must have a Skype for Business Server monitoring database deployed and associated to your Skype for Business Server pools.</span></span>

- <span data-ttu-id="c14ec-116">È consigliabile distribuire Call Quality Dashboard (Call Quality Dashboard).</span><span class="sxs-lookup"><span data-stu-id="c14ec-116">We recommend deploying Call Quality Dashboard (CQD).</span></span>

## <a name="configure-rate-my-call"></a><span data-ttu-id="c14ec-117">Configurare Vota la chiamata</span><span class="sxs-lookup"><span data-stu-id="c14ec-117">Configure Rate my Call</span></span>

<span data-ttu-id="c14ec-118">La caratteristica tasso di chiamata è abilitata per impostazione predefinita nel criterio client con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c14ec-118">The Rate My Call feature is enabled by default in the Client policy with the following settings:</span></span>

- <span data-ttu-id="c14ec-119">Valutare la percentuale di visualizzazione della chiamata-10%</span><span class="sxs-lookup"><span data-stu-id="c14ec-119">Rate My Call Display Percentage - 10%</span></span>

- <span data-ttu-id="c14ec-120">Vota la mia chiamata Consenti feedback degli utenti personalizzati disabilitati</span><span class="sxs-lookup"><span data-stu-id="c14ec-120">Rate My Call Allow Custom User Feedback - disabled</span></span>

<span data-ttu-id="c14ec-121">Non è necessaria alcuna azione per abilitare la caratteristica di base, ma se si vuole ricevere un feedback personalizzato, è necessario abilitarlo separatamente.</span><span class="sxs-lookup"><span data-stu-id="c14ec-121">There is no action required to enable the base feature, however but if you want custom feedback you will need to enable it separately.</span></span> <span data-ttu-id="c14ec-122">Il cmdlet di Windows PowerShell seguente è un esempio di abilitazione del feedback degli utenti finali personalizzati e della modifica dell'intervallo tra il 10% e il 80%.</span><span class="sxs-lookup"><span data-stu-id="c14ec-122">The following Windows PowerShell cmdlet is an example of enabling custom end user feedback and changing the interval from 10% to 80%.</span></span>

```PowerShell
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 - RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a><span data-ttu-id="c14ec-123">Tasso di accesso ai dati delle chiamate</span><span class="sxs-lookup"><span data-stu-id="c14ec-123">Accessing Rate My Call Data</span></span>

<span data-ttu-id="c14ec-124">I dati degli utenti vengono raccolti in due tabelle nel database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="c14ec-124">Data from users is collected in two tables in the monitoring database.</span></span>

 <span data-ttu-id="c14ec-125">**[QoeMetrics]. [dbo]. [CallQualityFeedbackToken]** -Questa tabella contiene i risultati del polling dei token da parte degli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="c14ec-125">**[QoeMetrics].[dbo].[CallQualityFeedbackToken]** - this table contains results of token polling by end users.</span></span>

 <span data-ttu-id="c14ec-126">**[QoeMetrics]. [dbo]. [CallQualityFeedbackTokenDef]** -Questa tabella contiene le definizioni di token.</span><span class="sxs-lookup"><span data-stu-id="c14ec-126">**[QoeMetrics].[dbo].[CallQualityFeedbackTokenDef]** - this table contains token definitions.</span></span>

<span data-ttu-id="c14ec-127">Le definizioni di token sono codificate nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="c14ec-127">Token definitions are coded as follows:</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c14ec-128">1</span><span class="sxs-lookup"><span data-stu-id="c14ec-128">1</span></span>  <br/> |<span data-ttu-id="c14ec-129">DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="c14ec-129">DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="c14ec-130">2</span><span class="sxs-lookup"><span data-stu-id="c14ec-130">2</span></span>  <br/> | <span data-ttu-id="c14ec-131">ElectronicFeedback</span><span class="sxs-lookup"><span data-stu-id="c14ec-131">ElectronicFeedback</span></span> <br/> |
|<span data-ttu-id="c14ec-132">3</span><span class="sxs-lookup"><span data-stu-id="c14ec-132">3</span></span>  <br/> | <span data-ttu-id="c14ec-133">BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="c14ec-133">BackgroundNoise</span></span> <br/> |
|<span data-ttu-id="c14ec-134">4</span><span class="sxs-lookup"><span data-stu-id="c14ec-134">4</span></span>  <br/> |<span data-ttu-id="c14ec-135">MuffledSpeech</span><span class="sxs-lookup"><span data-stu-id="c14ec-135">MuffledSpeech</span></span>  <br/> |
|<span data-ttu-id="c14ec-136">5</span><span class="sxs-lookup"><span data-stu-id="c14ec-136">5</span></span>  <br/> |<span data-ttu-id="c14ec-137">Echo</span><span class="sxs-lookup"><span data-stu-id="c14ec-137">Echo</span></span>  <br/> |
|<span data-ttu-id="c14ec-138">21</span><span class="sxs-lookup"><span data-stu-id="c14ec-138">21</span></span>  <br/> | <span data-ttu-id="c14ec-139">FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="c14ec-139">FrozenVideo</span></span> <br/> |
|<span data-ttu-id="c14ec-140">22</span><span class="sxs-lookup"><span data-stu-id="c14ec-140">22</span></span>  <br/> | <span data-ttu-id="c14ec-141">PixelatedVideo</span><span class="sxs-lookup"><span data-stu-id="c14ec-141">PixelatedVideo</span></span> <br/> |
|<span data-ttu-id="c14ec-142">23</span><span class="sxs-lookup"><span data-stu-id="c14ec-142">23</span></span>  <br/> | <span data-ttu-id="c14ec-143">BlurryImage</span><span class="sxs-lookup"><span data-stu-id="c14ec-143">BlurryImage</span></span> <br/> |
|<span data-ttu-id="c14ec-144">24</span><span class="sxs-lookup"><span data-stu-id="c14ec-144">24</span></span>  <br/> | <span data-ttu-id="c14ec-145">PoorColor</span><span class="sxs-lookup"><span data-stu-id="c14ec-145">PoorColor</span></span> <br/> |
|<span data-ttu-id="c14ec-146">25</span><span class="sxs-lookup"><span data-stu-id="c14ec-146">25</span></span>  <br/> | <span data-ttu-id="c14ec-147">DarkVideo</span><span class="sxs-lookup"><span data-stu-id="c14ec-147">DarkVideo</span></span> <br/> |
|<span data-ttu-id="c14ec-148">101</span><span class="sxs-lookup"><span data-stu-id="c14ec-148">101</span></span>  <br/> |<span data-ttu-id="c14ec-149">Audio_SilentLocal</span><span class="sxs-lookup"><span data-stu-id="c14ec-149">Audio_SilentLocal</span></span>  <br/> |
|<span data-ttu-id="c14ec-150">102</span><span class="sxs-lookup"><span data-stu-id="c14ec-150">102</span></span>  <br/> |<span data-ttu-id="c14ec-151">Audio_SilentRemote</span><span class="sxs-lookup"><span data-stu-id="c14ec-151">Audio_SilentRemote</span></span>  <br/> |
|<span data-ttu-id="c14ec-152">103</span><span class="sxs-lookup"><span data-stu-id="c14ec-152">103</span></span>  <br/> |<span data-ttu-id="c14ec-153">Audio_Echo</span><span class="sxs-lookup"><span data-stu-id="c14ec-153">Audio_Echo</span></span>  <br/> |
|<span data-ttu-id="c14ec-154">104</span><span class="sxs-lookup"><span data-stu-id="c14ec-154">104</span></span>  <br/> |<span data-ttu-id="c14ec-155">Audio_BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="c14ec-155">Audio_BackgroundNoise</span></span>  <br/> |
|<span data-ttu-id="c14ec-156">105</span><span class="sxs-lookup"><span data-stu-id="c14ec-156">105</span></span>  <br/> |<span data-ttu-id="c14ec-157">Audio_LowSound</span><span class="sxs-lookup"><span data-stu-id="c14ec-157">Audio_LowSound</span></span>  <br/> |
|<span data-ttu-id="c14ec-158">106</span><span class="sxs-lookup"><span data-stu-id="c14ec-158">106</span></span>  <br/> |<span data-ttu-id="c14ec-159">Audio_Dropped</span><span class="sxs-lookup"><span data-stu-id="c14ec-159">Audio_Dropped</span></span>  <br/> |
|<span data-ttu-id="c14ec-160">107</span><span class="sxs-lookup"><span data-stu-id="c14ec-160">107</span></span>  <br/> |<span data-ttu-id="c14ec-161">Audio_DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="c14ec-161">Audio_DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="c14ec-162">108</span><span class="sxs-lookup"><span data-stu-id="c14ec-162">108</span></span>  <br/> |<span data-ttu-id="c14ec-163">Audio_Interrupted</span><span class="sxs-lookup"><span data-stu-id="c14ec-163">Audio_Interrupted</span></span>  <br/> |
|<span data-ttu-id="c14ec-164">109</span><span class="sxs-lookup"><span data-stu-id="c14ec-164">109</span></span>  <br/> |<span data-ttu-id="c14ec-165">Audio_Other</span><span class="sxs-lookup"><span data-stu-id="c14ec-165">Audio_Other</span></span>  <br/> |
|<span data-ttu-id="c14ec-166">201</span><span class="sxs-lookup"><span data-stu-id="c14ec-166">201</span></span>  <br/> |<span data-ttu-id="c14ec-167">Video_NoLocalVideo</span><span class="sxs-lookup"><span data-stu-id="c14ec-167">Video_NoLocalVideo</span></span>  <br/> |
|<span data-ttu-id="c14ec-168">202</span><span class="sxs-lookup"><span data-stu-id="c14ec-168">202</span></span>  <br/> |<span data-ttu-id="c14ec-169">Video_NoRemoteVideo</span><span class="sxs-lookup"><span data-stu-id="c14ec-169">Video_NoRemoteVideo</span></span>  <br/> |
|<span data-ttu-id="c14ec-170">203</span><span class="sxs-lookup"><span data-stu-id="c14ec-170">203</span></span>  <br/> |<span data-ttu-id="c14ec-171">Video_LowQuality</span><span class="sxs-lookup"><span data-stu-id="c14ec-171">Video_LowQuality</span></span>  <br/> |
|<span data-ttu-id="c14ec-172">204</span><span class="sxs-lookup"><span data-stu-id="c14ec-172">204</span></span>  <br/> |<span data-ttu-id="c14ec-173">Video_FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="c14ec-173">Video_FrozenVideo</span></span>  <br/> |
|<span data-ttu-id="c14ec-174">205</span><span class="sxs-lookup"><span data-stu-id="c14ec-174">205</span></span>  <br/> |<span data-ttu-id="c14ec-175">Video_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="c14ec-175">Video_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="c14ec-176">206</span><span class="sxs-lookup"><span data-stu-id="c14ec-176">206</span></span>  <br/> |<span data-ttu-id="c14ec-177">Video_DarkVideo</span><span class="sxs-lookup"><span data-stu-id="c14ec-177">Video_DarkVideo</span></span>  <br/> |
|<span data-ttu-id="c14ec-178">207</span><span class="sxs-lookup"><span data-stu-id="c14ec-178">207</span></span>  <br/> |<span data-ttu-id="c14ec-179">Video_NoAudioSync</span><span class="sxs-lookup"><span data-stu-id="c14ec-179">Video_NoAudioSync</span></span>  <br/> |
|<span data-ttu-id="c14ec-180">208</span><span class="sxs-lookup"><span data-stu-id="c14ec-180">208</span></span>  <br/> |<span data-ttu-id="c14ec-181">Video_Other</span><span class="sxs-lookup"><span data-stu-id="c14ec-181">Video_Other</span></span>  <br/> |
|<span data-ttu-id="c14ec-182">301</span><span class="sxs-lookup"><span data-stu-id="c14ec-182">301</span></span>  <br/> |<span data-ttu-id="c14ec-183">Pstn_DialPad</span><span class="sxs-lookup"><span data-stu-id="c14ec-183">Pstn_DialPad</span></span>  <br/> |
|<span data-ttu-id="c14ec-184">401</span><span class="sxs-lookup"><span data-stu-id="c14ec-184">401</span></span>  <br/> |<span data-ttu-id="c14ec-185">SS_NoContentLocal</span><span class="sxs-lookup"><span data-stu-id="c14ec-185">SS_NoContentLocal</span></span>  <br/> |
|<span data-ttu-id="c14ec-186">402</span><span class="sxs-lookup"><span data-stu-id="c14ec-186">402</span></span>  <br/> |<span data-ttu-id="c14ec-187">SS_NoContentRemote</span><span class="sxs-lookup"><span data-stu-id="c14ec-187">SS_NoContentRemote</span></span>  <br/> |
|<span data-ttu-id="c14ec-188">403</span><span class="sxs-lookup"><span data-stu-id="c14ec-188">403</span></span>  <br/> |<span data-ttu-id="c14ec-189">SS_CantPresent</span><span class="sxs-lookup"><span data-stu-id="c14ec-189">SS_CantPresent</span></span>  <br/> |
|<span data-ttu-id="c14ec-190">404</span><span class="sxs-lookup"><span data-stu-id="c14ec-190">404</span></span>  <br/> |<span data-ttu-id="c14ec-191">SS_LowQuality</span><span class="sxs-lookup"><span data-stu-id="c14ec-191">SS_LowQuality</span></span>  <br/> |
|<span data-ttu-id="c14ec-192">405</span><span class="sxs-lookup"><span data-stu-id="c14ec-192">405</span></span>  <br/> |<span data-ttu-id="c14ec-193">SS_Freezing</span><span class="sxs-lookup"><span data-stu-id="c14ec-193">SS_Freezing</span></span>  <br/> |
|<span data-ttu-id="c14ec-194">406</span><span class="sxs-lookup"><span data-stu-id="c14ec-194">406</span></span>  <br/> |<span data-ttu-id="c14ec-195">SS_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="c14ec-195">SS_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="c14ec-196">407</span><span class="sxs-lookup"><span data-stu-id="c14ec-196">407</span></span>  <br/> |<span data-ttu-id="c14ec-197">SS_LargeDelay</span><span class="sxs-lookup"><span data-stu-id="c14ec-197">SS_LargeDelay</span></span>  <br/> |
|<span data-ttu-id="c14ec-198">408</span><span class="sxs-lookup"><span data-stu-id="c14ec-198">408</span></span>  <br/> |<span data-ttu-id="c14ec-199">SS_Other</span><span class="sxs-lookup"><span data-stu-id="c14ec-199">SS_Other</span></span>  <br/> |
|<span data-ttu-id="c14ec-200">501</span><span class="sxs-lookup"><span data-stu-id="c14ec-200">501</span></span>  <br/> |<span data-ttu-id="c14ec-201">Reliabilty_Join</span><span class="sxs-lookup"><span data-stu-id="c14ec-201">Reliabilty_Join</span></span>  <br/> |
|<span data-ttu-id="c14ec-202">502</span><span class="sxs-lookup"><span data-stu-id="c14ec-202">502</span></span>  <br/> |<span data-ttu-id="c14ec-203">Reliabilty_Invite</span><span class="sxs-lookup"><span data-stu-id="c14ec-203">Reliabilty_Invite</span></span>  <br/> |

 <span data-ttu-id="c14ec-204">**[QoeMetrics]. [dbo]. [CallQualityFeedback]** Questa tabella contiene i risultati del polling da "stella" voto e feedback dei clienti, se abilitata.</span><span class="sxs-lookup"><span data-stu-id="c14ec-204">**[QoeMetrics].[dbo].[CallQualityFeedback]** This table contains polling results from "Star" voting and customer feedback if enabled.</span></span>

<span data-ttu-id="c14ec-205">I dati delle tabelle possono essere chiamati tramite una **query \* select from [Table.Name]** o tramite Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="c14ec-205">Data from tables can be called by using a **select \* from [Table.Name]** query or by using Microsoft SQL Server Management Studio.</span></span>

<span data-ttu-id="c14ec-206">È possibile usare le query SQL seguenti:</span><span class="sxs-lookup"><span data-stu-id="c14ec-206">The following SQL queries can be used:</span></span>

 <span data-ttu-id="c14ec-207">**Audio**</span><span class="sxs-lookup"><span data-stu-id="c14ec-207">**Audio**</span></span>

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

 <span data-ttu-id="c14ec-208">**Video**</span><span class="sxs-lookup"><span data-stu-id="c14ec-208">**Video**</span></span>

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

## <a name="updating-token-definitions"></a><span data-ttu-id="c14ec-209">Aggiornamento delle definizioni di token</span><span class="sxs-lookup"><span data-stu-id="c14ec-209">Updating Token Definitions</span></span>

<span data-ttu-id="c14ec-210">Gli ultimi client Skype for business segnalano nuovi ID token di\> problema (100) che potrebbero non essere presenti in [QoeMetrics]. [dbo]. [CallQualityFeedbackTokenDef] tabella.</span><span class="sxs-lookup"><span data-stu-id="c14ec-210">The latest Skype for Business clients report new problem token IDs (\> 100) that may not be present in your [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span> <span data-ttu-id="c14ec-211">Per aggiornare la tabella di database con le definizioni di token più recenti, il comando SQL seguente può essere eseguito nel database di monitoraggio tramite Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="c14ec-211">To update the database table with the latest token definitions, the below SQL command can be run on the monitoring database using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="c14ec-212">Questo comando sostituisce tutte le voci di [QoeMetrics]. [dbo]. [CallQualityFeedbackTokenDef] tabella.</span><span class="sxs-lookup"><span data-stu-id="c14ec-212">This command will replace all entries in the [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span>

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


