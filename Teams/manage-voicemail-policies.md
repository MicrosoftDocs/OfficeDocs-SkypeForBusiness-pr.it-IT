---
title: Gestire i criteri della segreteria telefonica
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Gestire i criteri della segreteria telefonica per gli utenti.
ms.openlocfilehash: aa6b08cba7118a5e43f7f2bd3baea7fb3bc7f158
ms.sourcegitcommit: 2419348e964cfe97b72d533f267c5d7055d5366f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/12/2021
ms.locfileid: "52910058"
---
# <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="3e842-103">Impostazione dei criteri di segreteria telefonica dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="3e842-103">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="3e842-104">Per Skype for Business clienti, la disabilitazione della segreteria telefonica tramite un criterio Microsoft Teams chiamate potrebbe anche disabilitare il servizio di segreteria telefonica per gli utenti Skype for Business utenti.</span><span class="sxs-lookup"><span data-stu-id="3e842-104">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

## <a name="voicemail-organization-defaults-for-all-users"></a><span data-ttu-id="3e842-105">Impostazioni predefinite dell'organizzazione della segreteria telefonica per tutti gli utenti</span><span class="sxs-lookup"><span data-stu-id="3e842-105">Voicemail organization defaults for all users</span></span>
- <span data-ttu-id="3e842-106">La trascrizione della segreteria telefonica è abilitata.</span><span class="sxs-lookup"><span data-stu-id="3e842-106">Voicemail transcription is enabled.</span></span>
- <span data-ttu-id="3e842-107">Il mascheramento volgare della trascrizione della segreteria telefonica è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="3e842-107">Voicemail transcription profanity masking is disabled.</span></span>
- <span data-ttu-id="3e842-108">La durata massima della registrazione è impostata su cinque minuti.</span><span class="sxs-lookup"><span data-stu-id="3e842-108">The maximum recording duration is set to five minutes.</span></span>

<span data-ttu-id="3e842-109">È possibile controllare queste impostazioni predefinite usando i cmdlet [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) e [Grant-CsOnlineVoicemailPolicy.](/powershell/module/skype/Get-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="3e842-109">You can control these defaults by using the [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) and [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlets.</span></span>

<span data-ttu-id="3e842-110">I messaggi della segreteria telefonica ricevuti dagli utenti dell'organizzazione vengono trascritti nell'area geografica in cui è ospitata Microsoft 365 o Office 365'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3e842-110">Voicemail messages received by users in your organization are transcribed in the region where your Microsoft 365 or Office 365 organization is hosted.</span></span> <span data-ttu-id="3e842-111">L'area geografica in cui è ospitato il tenant potrebbe non essere la stessa area geografica in cui si trova l'utente che riceve il messaggio della segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="3e842-111">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="3e842-112">Per visualizzare l'area in cui è ospitato il tenant, passare alla pagina [Profilo](https://go.microsoft.com/fwlink/p/?linkid=2067339) organizzazione e quindi fare clic **su** Visualizza dettagli accanto a Posizione **dati.**</span><span class="sxs-lookup"><span data-stu-id="3e842-112">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3e842-113">Non è possibile creare una nuova istanza dei criteri per il mascheramento volgare della trascrizione e della trascrizione usando il cmdlet **New-CsOnlineVoiceMailPolicy** e non è possibile rimuovere un'istanza dei criteri esistente usando il cmdlet **Remove-CsOnlineVoiceMailPolicy.**</span><span class="sxs-lookup"><span data-stu-id="3e842-113">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="3e842-114">È possibile gestire le impostazioni di trascrizione per gli utenti che utilizzano i criteri segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="3e842-114">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="3e842-115">Per visualizzare tutte le istanze dei criteri della segreteria telefonica disponibili, è possibile usare il cmdlet [Get-CsOnlineVoicemailPolicy.](/powershell/module/skype/Get-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="3e842-115">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlet.</span></span>

```PowerShell
PS C:\> Get-CsOnlineVoicemailPolicy


Identity                            : Global
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:Default
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionProfanityMaskingEnabled
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : True
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionDisabled
EnableTranscription                 : False
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True
```
  
## <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="3e842-116">Disattivare la trascrizione per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="3e842-116">Turning off transcription for your organization</span></span>

<span data-ttu-id="3e842-p103">Dato che l'impostazione predefinita per la trascrizione è attiva per la propria organizzazione, si consiglia di disabilitarla utilizzando il cmdlet [set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy). Per farlo, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3e842-p103">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy). To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

## <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="3e842-119">Attivazione del mascheramento di volgarità sulla trascrizione per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="3e842-119">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="3e842-120">Il mascheramento di volgarità sulla trascrizione è disabilitato per impostazione predefinita per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3e842-120">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="3e842-121">Se non vi è un requisito aziendale per abilitarlo, è possibile abilitare il mascheramento di volgarità sulla trascrizione tramite [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span><span class="sxs-lookup"><span data-stu-id="3e842-121">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="3e842-122">Per farlo, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3e842-122">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

## <a name="changing-the-recording-duration-for-your-organization"></a><span data-ttu-id="3e842-123">Modifica della durata della registrazione per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="3e842-123">Changing the recording duration for your organization</span></span>

<span data-ttu-id="3e842-124">La durata massima della registrazione è impostata su cinque minuti per impostazione predefinita per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3e842-124">The maximum recording length is set to five minutes by default for your organization.</span></span> <span data-ttu-id="3e842-125">Se esiste un requisito aziendale per aumentare o ridurre la lunghezza massima della registrazione, questa operazione può essere eseguita usando [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span><span class="sxs-lookup"><span data-stu-id="3e842-125">If there is a business requirement to increase or decrease the maximum recording length, this can be done by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="3e842-126">Ad esempio, per impostare il tempo massimo di registrazione su 60 secondi, eseguire:</span><span class="sxs-lookup"><span data-stu-id="3e842-126">For example, to set the maximum recording time to 60 seconds,  run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

## <a name="dual-language-system-prompts-for-your-organization"></a><span data-ttu-id="3e842-127">Richieste di sistema in doppia lingua per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="3e842-127">Dual language system prompts for your organization</span></span>

<span data-ttu-id="3e842-128">Per impostazione predefinita, le richieste di sistema della segreteria telefonica vengono presentate ai chiamanti nella lingua selezionata dall'utente durante la configurazione della segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="3e842-128">By default, the voicemail system prompts are presented to callers in the language selected by the user when setting up their voicemail.</span></span> <span data-ttu-id="3e842-129">Se è necessario che le richieste del sistema di segreteria telefonica siano presentate in due lingue, è possibile farlo usando [Set-CsOnlineVoicemailPolicy.](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="3e842-129">If there is a business requirement to have the voicemail system prompts presented in two languages, this can be done by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="3e842-130">È necessario impostare una lingua principale e una secondaria e non essere la stessa.</span><span class="sxs-lookup"><span data-stu-id="3e842-130">A primary and secondary language must be set and may not be the same.</span></span> <span data-ttu-id="3e842-131">Per farlo, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3e842-131">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

## <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="3e842-132">Disattivare la trascrizione per un utente</span><span class="sxs-lookup"><span data-stu-id="3e842-132">Turning off transcription for a user</span></span>

<span data-ttu-id="3e842-133">I criteri utente vengono valutati prima delle impostazioni predefinite dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3e842-133">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="3e842-134">Ad esempio, se la trascrizione della segreteria telefonica è abilitata per tutti gli utenti, è possibile assegnare un criterio per disabilitare la trascrizione per un utente specifico usando il cmdlet [Grant-CsOnlineVoicemailPolicy.](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="3e842-134">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="3e842-135">Per disabilitare la trascrizione per un singolo utente, eseguire:</span><span class="sxs-lookup"><span data-stu-id="3e842-135">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

## <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="3e842-136">Attivazione del mascheramento di volgarità sulla trascrizione per un utente</span><span class="sxs-lookup"><span data-stu-id="3e842-136">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="3e842-137">Per abilitare il mascheramento di volgarità sulla trascrizione per un utente specifico, è possibile assegnare un criterio per abilitare il mascheramento di volgarità sulla trascrizione per un utente specifico utilizzando il cmdlet [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy).</span><span class="sxs-lookup"><span data-stu-id="3e842-137">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="3e842-138">Per abilitare il mascheramento di volgarità sulla trascrizione per un singolo utente, eseguire:</span><span class="sxs-lookup"><span data-stu-id="3e842-138">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

## <a name="changing-the-recording-duration-for-a-user"></a><span data-ttu-id="3e842-139">Modifica della durata della registrazione per un utente</span><span class="sxs-lookup"><span data-stu-id="3e842-139">Changing the recording duration for a user</span></span>

<span data-ttu-id="3e842-140">È prima di tutto necessario creare criteri di segreteria telefonica personalizzati usando il cmdlet [New-CsOnlineVoicemailPolicy.](/powershell/module/skype/New-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="3e842-140">You must first create a custom voicemail policy using the [New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) cmdlet.</span></span> <span data-ttu-id="3e842-141">Il comando illustrato di seguito crea un criterio della segreteria telefonica online per utente OneMinuteVoicemailPolicy con MaximumRecordingLength impostato su 60 secondi e altri campi impostati sul valore globale a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="3e842-141">The command shown below creates a per-user online voicemail policy OneMinuteVoicemailPolicy with MaximumRecordingLength set to 60 seconds and other fields set to tenant level global value.</span></span>

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "OneMinuteVoicemailPolicy" -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

<span data-ttu-id="3e842-142">Per assegnare questo criterio personalizzato a un utente, eseguire:</span><span class="sxs-lookup"><span data-stu-id="3e842-142">To assign this custom policy to a user, run:</span></span> 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName OneMinuteVoicemailPolicy -Identity sip:amosmar@contoso.com
```

## <a name="dual-language-system-prompts-for-a-user"></a><span data-ttu-id="3e842-143">Richiesta di sistema in doppia lingua per un utente</span><span class="sxs-lookup"><span data-stu-id="3e842-143">Dual language system prompts for a user</span></span>

<span data-ttu-id="3e842-144">È prima di tutto necessario creare criteri di segreteria telefonica personalizzati usando il cmdlet [New-CsOnlineVoicemailPolicy.](/powershell/module/skype/New-CsOnlineVoicemailPolicy)</span><span class="sxs-lookup"><span data-stu-id="3e842-144">You must first create a custom voicemail policy using the [New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) cmdlet.</span></span> <span data-ttu-id="3e842-145">Il comando illustrato di seguito crea un criterio della segreteria telefonica online per utente enUS-esSP-VoicemailPolicy con PrimarySystemPromptLanguage impostato su en-US (Inglese - Stati Uniti) e SecondarySystemPromptLanguage impostato su es-SP (spagnolo - Spagna).</span><span class="sxs-lookup"><span data-stu-id="3e842-145">The command shown below creates a per-user online voicemail policy enUS-esSP-VoicemailPolicy with the PrimarySystemPromptLanguage set to en-US (English - United States) and the SecondarySystemPromptLanguage set to es-SP (Spanish - Spain).</span></span>

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "enUS-esES-VoicemailPolicy" -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

<span data-ttu-id="3e842-146">Per assegnare questo criterio personalizzato a un utente, eseguire:</span><span class="sxs-lookup"><span data-stu-id="3e842-146">To assign this custom policy to a user, run:</span></span> 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName "enUS-esES-VoicemailPolicy" -Identity sip:amosmar@contoso.com
```

> [!NOTE]
> <span data-ttu-id="3e842-147">Il cmdlet Get-CsOnlineVoicemailPolicy non restituisce attualmente i valori per PrimarySystemPromptLanguage e SecondarySystemPromptLanguage.</span><span class="sxs-lookup"><span data-stu-id="3e842-147">The Get-CsOnlineVoicemailPolicy cmdlet is not currently returning the values for PrimarySystemPromptLanguage and SecondarySystemPromptLanguage.</span></span> <span data-ttu-id="3e842-148">Per visualizzare questi valori, modificare il comando nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="3e842-148">To see these values modify the command as follows:</span></span>
>
> >```PowerShell
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).PrimarySystemPromptLanguage or
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).SecondarySystemPromptLanguage 
>
> <span data-ttu-id="3e842-149">Sostituire **PolicyName** con il nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="3e842-149">Replace **PolicyName** with the name of the policy.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="3e842-150">Il servizio di segreteria telefonica in Microsoft 365 e Office 365 i criteri della segreteria telefonica e aggiorna la cache ogni 6 ore.</span><span class="sxs-lookup"><span data-stu-id="3e842-150">The voicemail service in Microsoft 365 and Office 365 caches voicemail policies and updates the cache every 6 hours.</span></span> <span data-ttu-id="3e842-151">Pertanto, le modifiche ai criteri apportate possono richiedere fino a 6 ore.</span><span class="sxs-lookup"><span data-stu-id="3e842-151">So, policy changes that you make can take up to 6 hours to be applied.</span></span>
