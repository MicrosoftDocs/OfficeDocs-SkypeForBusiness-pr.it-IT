---
title: Gestire i criteri della segreteria telefonica
author: crowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
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
ms.openlocfilehash: 7af4fa89dd495679a3ec755dd2e902012ad1ef77
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "66240515"
---
# <a name="manage-cloud-voicemail-policies-for-your-users"></a>Gestire i criteri di Cloud Voicemail per gli utenti

> [!WARNING]
> Per Skype for Business clienti, la disabilitazione della segreteria telefonica tramite un criterio di chiamata di Microsoft Teams potrebbe disabilitare anche il servizio di segreteria telefonica per gli utenti Skype for Business.

I criteri segreteria telefonica consentono di configurare e assegnare criteri di segreteria telefonica esistenti o nuovi a gruppi di utenti per funzionalità come le regole di risposta alle chiamate, la trascrizione della segreteria telefonica, il mascheramento delle trascrizioni, la traduzione della trascrizione e il linguaggio prompt del sistema.

Prima di specificare i criteri, leggere [Configurare Cloud Voicemail](set-up-phone-system-voicemail.md). Per informazioni sulla gestione delle impostazioni per singoli utenti, vedere [Gestire le impostazioni della segreteria](manage-voicemail-settings.md) telefonica.

Per gestire i criteri della segreteria telefonica, è possibile usare l'interfaccia di amministrazione di Teams o il cmdlet New-CsOnlineVoicemailPolicy PowerShell. 

I criteri predefiniti per gli utenti sono:

- La trascrizione della segreteria telefonica è abilitata.
- La traduzione della trascrizione della segreteria telefonica è abilitata.
- Mascheramento profano trascrizione segreteria telefonica è disabilitato.
- La durata massima della registrazione è impostata su cinque minuti.
- La modifica delle regole di risposta alle chiamate è abilitata.
- Le lingue di prompt del sistema primario e secondario sono impostate su Null e viene utilizzata l'impostazione della lingua della segreteria telefonica dell'utente.

È possibile usare il criterio globale (predefinito a livello di organizzazione) creato automaticamente o creare e assegnare criteri personalizzati.

> [!IMPORTANT]
> Il servizio di segreteria telefonica in Microsoft 365 memorizza nella cache i criteri della segreteria telefonica e aggiorna la cache ogni 6 ore. Di conseguenza, le modifiche apportate ai criteri possono richiedere fino a 6 ore per essere applicate.

## <a name="use-teams-admin-center"></a>Usare l'interfaccia di amministrazione di Teams

### <a name="create-a-custom-voicemail-policy"></a>Creare criteri per la segreteria telefonica personalizzati

Seguire questa procedura per creare criteri di segreteria telefonica personalizzati.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams **passare a** > **Criteri segreteria telefonica**.

2. Selezionare **Aggiungi**.

3. Attivare o disattivare le funzionalità che si desidera utilizzare nei criteri della segreteria telefonica.

4. Selezionare **Salva**.

### <a name="edit-a-voicemail-policy"></a>Modificare i criteri della segreteria telefonica

Seguire questa procedura per modificare un criterio della segreteria telefonica esistente.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft **Teams selezionare** > **Criteri segreteria telefonica**.

2. Fare clic accanto al criterio da modificare e quindi selezionare **Modifica**.

3. Apportare le modifiche desiderate e quindi fare clic su **Salva**.

> [!IMPORTANT]
> Non è possibile modificare o rimuovere le istanze dei criteri pre-configurate denominate TranscriptionDisabled e TranscriptionProfanityMaskingEnabled.


### <a name="assign-a-custom-voicemail-policy-to-users"></a>Assegnare criteri di segreteria telefonica personalizzati agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="use-powershell"></a>Usare PowerShell

È anche possibile usare PowerShell per configurare e assegnare criteri di segreteria telefonica esistenti o nuovi. Per gestire i criteri con PowerShell, usare i cmdlet seguenti:

- [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy)

- [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/set-csonlinevoicemailpolicy)

- [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/get-csonlinevoicemailpolicy)

- [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/grant-csonlinevoicemailpolicy)

- [Remove-CsOnlineVoicemailPolicy](/powershell/module/skype/remove-csonlinevoicemailpolicy)

## <a name="voicemail-policy-settings"></a>Impostazioni dei criteri segreteria telefonica
  
- **Abilita trascrizione**: questa impostazione controlla se il servizio Cloud Voicemail genererà una trascipizione del testo della segreteria telefonica registrata e la includerà nel messaggio della segreteria telefonica. La trascrizione verrà eseguita in base alla lingua rilevata nella segreteria telefonica registrata.

- **Traduzione della trascrizione** - Questa impostazione controlla se il servizio Cloud Voicemail tradurrà la trascrizione della segreteria telefonica registrata. La traduzione verrà tentata nella lingua preferita del ricevitore della segreteria telefonica.

- **Transcription profanity masking** - Questa impostazione controlla se il servizio Cloud Voicemail maschera le parolacce trovate nella trascrizione della segreteria telefonica.

- **Durata massima di registrazione** - La durata massima della registrazione controlla il tempo massimo di registrazione di un messaggio vocale. L'impostazione predefinita è 5 minuti.

- **Regole di risposta** alle chiamate - Questa impostazione controlla se l'utente è autorizzato a configurare le regole di risposta alle chiamate vocali in Microsoft Teams.

- **Comandi del sistema a doppia lingua** : per impostazione predefinita, i messaggi del sistema della segreteria telefonica vengono presentati ai chiamanti nella lingua selezionata dall'utente durante la configurazione della segreteria telefonica. Se è necessario che i messaggi del sistema segreteria telefonica siano presentati in due lingue, è possibile impostare una lingua principale e una lingua secondaria e non essere identici.

### <a name="share-data-for-service-improvements"></a>Condividere i dati per i miglioramenti del servizio

Specifica se i dati della segreteria telefonica e della trascrizione vengono condivisi con il servizio per la formazione e per migliorare l'accuratezza. Se impostato su false, i dati della segreteria telefonica non verranno condivisi, indipendentemente dalla scelta dell'utente.


## <a name="related-articles"></a>Articoli correlati


