---
title: Configurare la risposta automatica per i Teams Android
author: KarliStites
ms.author: kastites
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: kponnus
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
  - M365-collaboration
appliesto:
  - Microsoft Teams
f1.keywords:
  - CSH
ms.custom: null
description: Informazioni su come configurare la funzionalità di risposta automatica per Microsoft Teams Rooms dispositivi Android e Teams video con PowerShell.
---

# <a name="set-up-auto-answer-for-microsoft-teams-rooms-on-android-and-teams-video-phone-devices"></a>Configurare la risposta automatica per Microsoft Teams Rooms nei dispositivi android e Teams video

Questo articolo ti aiuterà a configurare la funzionalità di risposta automatica Microsoft Teams Rooms nei dispositivi android e Teams video. La risposta automatica consente agli utenti dell'organizzazione con privilegi amministrativi di modificare le impostazioni del dispositivo in modo da accettare automaticamente gli inviti alle riunioni in arrivo e accettare automaticamente le chiamate con video.

## <a name="enable-auto-answer-with-powershell"></a>Abilitare la risposta automatica con PowerShell

Usare gli attributi seguenti per abilitare la risposta automatica nei dispositivi Microsoft Teams Rooms android e Teams video:

- **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType**
- **Set-CsTeamsIPPhonePolicy -SignInMode**

### <a name="1-turn-on-auto-answer-for-incoming-meeting-invites"></a>1. Attivare la risposta automatica per gli inviti alle riunioni in arrivo

Si usa **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType** per attivare la risposta automatica per gli inviti alle riunioni in arrivo. La risposta automatica **è disattivata per** impostazione predefinita. Questo criterio si applica solo agli inviti alle riunioni in arrivo e non supporta altri tipi di chiamata. Per [altre informazioni sul cmdlet, vedere Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy) .

```powershell
Set-CsTeamsCallingPolicy -AutoAnswerEnabledType Enabled
```

### <a name="2-set-the-device-sign-in-mode"></a>2. Impostare la modalità di accesso del dispositivo

Si usa **Set-CsTeamsIPPhonePolicy -SignInMode** per impostare la modalità di accesso per il dispositivo per determinare il comportamento durante l'accesso a Teams. Per [altre informazioni sul cmdlet, vedere Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy) .

Per la modalità di accesso sono disponibili tre opzioni:

- **UserSignIn:** Consente a un singolo utente Teams'esperienza sul telefono.
- **CommonAreaPhoneSignIn:** Consente un'esperienza telefonica comune sul telefono.
- **MeetingSignIn:** Consente l'esperienza di una sala riunioni sul telefono.

Ad esempio, il criterio seguente imposta la modalità di accesso su un'esperienza di sala riunioni.

```powershell
Set-CsTeamsIPPhonePolicy -Identity Device -SignInMode MeetingSignIn
```

### <a name="configure-device-settings"></a>Configurare le impostazioni del dispositivo

Dopo aver abilitato la risposta automatica, gli utenti con autorizzazioni amministrative possono attivare la funzionalità nelle impostazioni del dispositivo. Per abilitare la funzionalità a livello di dispositivo, è necessario attivare Accetta automaticamente gli inviti **alle riunioni in arrivo**. È anche possibile attivare **l'accettazione automatica con il video**. Entrambe le impostazioni sono disattivate per impostazione predefinita.

## <a name="related-topics"></a>Argomenti correlati

[Supporto Tecnico Microsoft: chiamate e dispositivi](https://support.microsoft.com/office/calls-and-devices-4d96653e-6176-4978-98ab-2c19df137e43#ID0EBBD=Devices)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy)
