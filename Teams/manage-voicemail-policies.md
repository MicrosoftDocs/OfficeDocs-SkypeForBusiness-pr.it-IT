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
ms.openlocfilehash: 112a2ac98ee22c46cb78c579ead947f70a1d6d447ac81ace3aef224304a281dd
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54342970"
---
# <a name="setting-voicemail-policies-in-your-organization"></a>Impostazione dei criteri di segreteria telefonica dell'organizzazione

> [!WARNING]
> Per Skype for Business clienti, la disabilitazione della segreteria telefonica tramite un criterio Microsoft Teams chiamate potrebbe anche disabilitare il servizio di segreteria telefonica per gli utenti Skype for Business utenti.

## <a name="voicemail-organization-defaults-for-all-users"></a>Impostazioni predefinite dell'organizzazione della segreteria telefonica per tutti gli utenti
- La trascrizione della segreteria telefonica è abilitata.
- Il mascheramento volgare della trascrizione della segreteria telefonica è disabilitato.
- La durata massima della registrazione è impostata su cinque minuti.

È possibile controllare queste impostazioni predefinite usando i cmdlet [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) e [Grant-CsOnlineVoicemailPolicy.](/powershell/module/skype/Get-CsOnlineVoicemailPolicy)

I messaggi della segreteria telefonica ricevuti dagli utenti dell'organizzazione vengono trascritti nell'area geografica in cui è ospitata Microsoft 365 o Office 365'organizzazione. L'area geografica in cui è ospitato il tenant potrebbe non essere la stessa area geografica in cui si trova l'utente che riceve il messaggio della segreteria telefonica. Per visualizzare l'area in cui è ospitato il tenant, passare alla pagina [Profilo](https://go.microsoft.com/fwlink/p/?linkid=2067339) organizzazione e quindi fare clic **su** Visualizza dettagli accanto a Posizione **dati.**

> [!IMPORTANT]
> Non è possibile creare una nuova istanza dei criteri per il mascheramento volgare della trascrizione e della trascrizione usando il cmdlet **New-CsOnlineVoiceMailPolicy** e non è possibile rimuovere un'istanza dei criteri esistente usando il cmdlet **Remove-CsOnlineVoiceMailPolicy.**

È possibile gestire le impostazioni di trascrizione per gli utenti che utilizzano i criteri segreteria telefonica. Per visualizzare tutte le istanze dei criteri della segreteria telefonica disponibili, è possibile usare il cmdlet [Get-CsOnlineVoicemailPolicy.](/powershell/module/skype/Get-CsOnlineVoicemailPolicy)

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
  
## <a name="turning-off-transcription-for-your-organization"></a>Disattivare la trascrizione per la propria organizzazione

Dato che l'impostazione predefinita per la trascrizione è attiva per la propria organizzazione, si consiglia di disabilitarla utilizzando il cmdlet [set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy). Per farlo, eseguire quanto segue:

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

## <a name="turning-on-transcription-profanity-masking-for-your-organization"></a>Attivazione del mascheramento di volgarità sulla trascrizione per la propria organizzazione

Il mascheramento di volgarità sulla trascrizione è disabilitato per impostazione predefinita per l'organizzazione. Se non vi è un requisito aziendale per abilitarlo, è possibile abilitare il mascheramento di volgarità sulla trascrizione tramite [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy). Per farlo, eseguire quanto segue:

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

## <a name="changing-the-recording-duration-for-your-organization"></a>Modifica della durata della registrazione per l'organizzazione

La durata massima della registrazione è impostata su cinque minuti per impostazione predefinita per l'organizzazione. Se esiste un requisito aziendale per aumentare o ridurre la lunghezza massima della registrazione, questa operazione può essere eseguita usando [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy). Ad esempio, per impostare il tempo massimo di registrazione su 60 secondi, eseguire:

```PowerShell
Set-CsOnlineVoicemailPolicy -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

## <a name="dual-language-system-prompts-for-your-organization"></a>Richieste di sistema in doppia lingua per l'organizzazione

Per impostazione predefinita, le richieste di sistema della segreteria telefonica vengono presentate ai chiamanti nella lingua selezionata dall'utente durante la configurazione della segreteria telefonica. Se è necessario che le richieste del sistema di segreteria telefonica siano presentate in due lingue, è possibile farlo usando [Set-CsOnlineVoicemailPolicy.](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) È necessario impostare una lingua principale e una secondaria e non essere la stessa. Per farlo, eseguire quanto segue:

```PowerShell
Set-CsOnlineVoicemailPolicy -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

## <a name="turning-off-transcription-for-a-user"></a>Disattivare la trascrizione per un utente

I criteri utente vengono valutati prima delle impostazioni predefinite dell'organizzazione. Ad esempio, se la trascrizione della segreteria telefonica è abilitata per tutti gli utenti, è possibile assegnare un criterio per disabilitare la trascrizione per un utente specifico usando il cmdlet [Grant-CsOnlineVoicemailPolicy.](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy)

Per disabilitare la trascrizione per un singolo utente, eseguire:

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

## <a name="turning-on-transcription-profanity-masking-for-a-user"></a>Attivazione del mascheramento di volgarità sulla trascrizione per un utente

Per abilitare il mascheramento di volgarità sulla trascrizione per un utente specifico, è possibile assegnare un criterio per abilitare il mascheramento di volgarità sulla trascrizione per un utente specifico utilizzando il cmdlet [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy).

Per abilitare il mascheramento di volgarità sulla trascrizione per un singolo utente, eseguire:

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

## <a name="changing-the-recording-duration-for-a-user"></a>Modifica della durata della registrazione per un utente

È prima di tutto necessario creare criteri di segreteria telefonica personalizzati usando il cmdlet [New-CsOnlineVoicemailPolicy.](/powershell/module/skype/New-CsOnlineVoicemailPolicy) Il comando illustrato di seguito crea un criterio della segreteria telefonica online per utente OneMinuteVoicemailPolicy con MaximumRecordingLength impostato su 60 secondi e altri campi impostati sul valore globale a livello di tenant.

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "OneMinuteVoicemailPolicy" -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

Per assegnare questo criterio personalizzato a un utente, eseguire: 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName OneMinuteVoicemailPolicy -Identity sip:amosmar@contoso.com
```

## <a name="dual-language-system-prompts-for-a-user"></a>Richiesta di sistema in doppia lingua per un utente

È prima di tutto necessario creare criteri di segreteria telefonica personalizzati usando il cmdlet [New-CsOnlineVoicemailPolicy.](/powershell/module/skype/New-CsOnlineVoicemailPolicy) Il comando illustrato di seguito crea un criterio della segreteria telefonica online per utente enUS-esSP-VoicemailPolicy con PrimarySystemPromptLanguage impostato su en-US (Inglese - Stati Uniti) e SecondarySystemPromptLanguage impostato su es-SP (spagnolo - Spagna).

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "enUS-esES-VoicemailPolicy" -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

Per assegnare questo criterio personalizzato a un utente, eseguire: 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName "enUS-esES-VoicemailPolicy" -Identity sip:amosmar@contoso.com
```

> [!NOTE]
> Il cmdlet Get-CsOnlineVoicemailPolicy non restituisce attualmente i valori per PrimarySystemPromptLanguage e SecondarySystemPromptLanguage. Per visualizzare questi valori, modificare il comando nel modo seguente:
>
> >```PowerShell
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).PrimarySystemPromptLanguage or
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).SecondarySystemPromptLanguage 
>
> Sostituire **PolicyName** con il nome del criterio.


> [!IMPORTANT]
> Il servizio di segreteria telefonica in Microsoft 365 e Office 365 i criteri della segreteria telefonica e aggiorna la cache ogni 6 ore. Pertanto, le modifiche ai criteri apportate possono richiedere fino a 6 ore.
