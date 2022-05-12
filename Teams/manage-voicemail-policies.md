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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Gestire i criteri della segreteria telefonica per gli utenti.
ms.openlocfilehash: 3f4c64194fc9e2b24c59dc7bc06ed972e801a6a8
ms.sourcegitcommit: cd9a1f7afaaf053741c81022e7052bf6f8008fcc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2022
ms.locfileid: "65370829"
---
# <a name="setting-voicemail-policies-in-your-organization"></a>Impostazione dei criteri di segreteria telefonica dell'organizzazione

> [!WARNING]
> Per Skype for Business clienti, la disabilitazione della segreteria telefonica tramite un criterio di chiamata Microsoft Teams potrebbe disabilitare anche il servizio di segreteria telefonica per gli utenti Skype for Business.

È possibile usare i criteri della segreteria telefonica per controllare le diverse funzionalità correlate a Cloud Voicemail.

## <a name="voicemail-organization-defaults-for-all-users"></a>Impostazioni predefinite dell'organizzazione segreteria telefonica per tutti gli utenti
- La trascrizione della segreteria telefonica è abilitata.
- La traduzione della trascrizione della segreteria telefonica è abilitata.
- Mascheramento profano trascrizione segreteria telefonica è disabilitato.
- La durata massima della registrazione è impostata su cinque minuti.
- La modifica delle regole di risposta alle chiamate è abilitata.
- Le lingue di prompt del sistema primario e secondario sono impostate su Null e viene utilizzata l'impostazione della lingua della segreteria telefonica dell'utente.

È possibile usare il criterio globale (predefinito a livello di organizzazione) creato automaticamente o creare e assegnare criteri personalizzati.

## <a name="create-a-custom-voicemail-policy"></a>Creare criteri per la segreteria telefonica personalizzati

Seguire questa procedura per creare criteri di segreteria telefonica personalizzati.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams **passare a** >  **Criteri segreteria telefonica**.
2. Selezionare **Aggiungi**.
3. Attivare o disattivare le funzionalità che si desidera utilizzare nei criteri della segreteria telefonica.
4. Selezionare **Salva**.

## <a name="edit-a-voicemail-policy"></a>Modificare i criteri della segreteria telefonica

Seguire questa procedura per modificare un criterio della segreteria telefonica esistente.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams selezionare **Criteri** >  segreteria **telefonica**.
2. Fare clic accanto al criterio da modificare e quindi selezionare **Modifica**.
3. Apportare le modifiche desiderate e quindi fare clic su **Salva**.

> [!IMPORTANT]
> Non è possibile modificare o rimuovere le istanze dei criteri pre-configurate denominate TranscriptionDisabled e TranscriptionProfanityMaskingEnabled.


## <a name="assign-a-custom-voicemail-policy-to-users"></a>Assegnare criteri di segreteria telefonica personalizzati agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="voicemail-policy-settings"></a>Impostazioni dei criteri segreteria telefonica
  
### <a name="enable-transcription"></a>Abilitare la trascrizione

Questa impostazione controlla se il servizio Cloud Voicemail genererà una transcipazione del testo della segreteria telefonica registrata e la includerà nel messaggio della segreteria telefonica. La trascrizione verrà eseguita in base alla lingua rilevata nella segreteria telefonica registrata.

### <a name="transcription-translation"></a>Traduzione trascrizione

Questa impostazione controlla se il servizio Cloud Voicemail tradurrà la trascrizione della segreteria telefonica registrata. La traduzione verrà tentata nella lingua preferita del ricevitore della segreteria telefonica.

### <a name="transcription-profanity-masking"></a>Transcription profanity masking

Questa impostazione controlla se il servizio Cloud Voicemail maschera le parolacce trovate nella trascrizione della segreteria telefonica.

### <a name="maximum-recording-duration"></a>Durata massima di registrazione

La lunghezza massima di registrazione controlla il tempo massimo di registrazione di un messaggio vocale. L'impostazione predefinita è 5 minuti.

### <a name="call-answering-rules"></a>Regole di risposta alle chiamate

Questa impostazione controlla se l'utente è autorizzato a configurare le regole di risposta alle chiamate della segreteria telefonica in Microsoft Teams.

### <a name="dual-language-system-prompts"></a>Prompt del sistema dual language

Per impostazione predefinita, le richieste di sistema della segreteria telefonica vengono presentate ai chiamanti nella lingua selezionata dall'utente durante la configurazione della segreteria telefonica. Se è necessario che i messaggi del sistema segreteria telefonica siano presentati in due lingue, è possibile impostare una lingua principale e una lingua secondaria e non essere identici.

### <a name="share-data-for-service-improvements"></a>Condividere i dati per i miglioramenti del servizio

Specifica se i dati della segreteria telefonica e della trascrizione vengono condivisi con il servizio per la formazione e per migliorare l'accuratezza. Se impostato su false, i dati della segreteria telefonica non verranno condivisi, indipendentemente dalla scelta dell'utente.


> [!IMPORTANT]
> Il servizio di segreteria telefonica in Microsoft 365 e Office 365 memorizza nella cache i criteri della segreteria telefonica e aggiorna la cache ogni 6 ore. Di conseguenza, le modifiche apportate ai criteri possono richiedere fino a 6 ore per essere applicate.

## <a name="related-articles"></a>Articoli correlati

[New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy)

[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/set-csonlinevoicemailpolicy)

[Get-CsOnlineVoicemailPolicy](/powershell/module/skype/get-csonlinevoicemailpolicy)

[Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/grant-csonlinevoicemailpolicy)

[Remove-CsOnlineVoicemailPolicy](/powershell/module/skype/remove-csonlinevoicemailpolicy)
