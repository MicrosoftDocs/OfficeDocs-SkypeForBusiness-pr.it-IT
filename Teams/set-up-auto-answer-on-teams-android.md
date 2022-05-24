---
title: Configurare la risposta automatica per i dispositivi Teams Android
author: mkbond007
ms.author: mabond
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
ms.custom: ''
description: Informazioni su come configurare la funzionalità di risposta automatica per Microsoft Teams Rooms in Android e Teams dispositivi video con PowerShell.
ms.openlocfilehash: fac458a2b7b100a2074dbaac0e209fbdd3527eef
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646595"
---
# <a name="set-up-auto-answer-for-microsoft-teams-rooms-on-android-and-teams-video-phone-devices"></a>Configurare la risposta automatica per Microsoft Teams Rooms nei dispositivi Android e Teams dei telefoni video

Questo articolo illustra come configurare la funzionalità di risposta automatica in Microsoft Teams Rooms in Android e Teams dispositivi per telefoni video. Risposta automatica consente agli utenti dell'organizzazione con privilegi amministrativi di modificare le impostazioni del dispositivo per accettare automaticamente gli inviti alle riunioni in arrivo e accettare automaticamente le chiamate con video.

## <a name="enable-auto-answer-with-powershell"></a>Abilitare la risposta automatica con PowerShell

Usare gli attributi seguenti per abilitare la risposta automatica in Microsoft Teams Rooms nei dispositivi Android e Teams video phone:

- **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType**
- **Set-CsTeamsIPPhonePolicy -SignInMode**

### <a name="1-turn-on-auto-answer-for-incoming-meeting-invites"></a>1. Attivare la risposta automatica per gli inviti alle riunioni in arrivo

Utilizzare **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType** per attivare la risposta automatica per gli inviti alle riunioni in arrivo. La risposta automatica è **disattivata** per impostazione predefinita. Questo criterio si applica solo agli inviti alle riunioni in arrivo e non supporta altri tipi di chiamata. Per altre informazioni sul cmdlet, vedere [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy) .

```powershell
Set-CsTeamsCallingPolicy -AutoAnswerEnabledType Enabled
```

### <a name="2-set-the-device-sign-in-mode"></a>2. Impostare la modalità di accesso del dispositivo

Utilizzare **Set-CsTeamsIPPhonePolicy -SignInMode** per impostare la modalità di accesso per il dispositivo per determinare il comportamento quando si accede a Teams. Per altre informazioni sul cmdlet, vedere [Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy) .

Sono disponibili tre opzioni per la modalità di accesso:

- **UserSignIn:** Consente a un singolo utente Teams'esperienza nel telefono.
- **CommonAreaPhoneSignIn:** Abilita un'esperienza di telefono ad area comune nel telefono.
- **MeetingSignIn:** Consente l'esperienza di una sala riunioni sul telefono.

Ad esempio, i criteri seguenti impostano la modalità di accesso su un'esperienza di sala riunioni.

```powershell
Set-CsTeamsIPPhonePolicy -Identity Device -SignInMode MeetingSignIn
```

### <a name="configure-device-settings"></a>Configurare le impostazioni del dispositivo

Dopo aver abilitato la risposta automatica, gli utenti con autorizzazioni amministrative possono attivare la funzionalità nelle impostazioni del dispositivo. Per abilitare la funzionalità a livello di dispositivo, è necessario attivare **l'opzione Accetta automaticamente gli inviti alle riunioni in arrivo**. È anche possibile attivare **l'opzione Accetta automaticamente con il video**. Entrambe le impostazioni sono disattivate per impostazione predefinita.

## <a name="related-topics"></a>Argomenti correlati

[supporto tecnico Microsoft: Chiamate e dispositivi](https://support.microsoft.com/office/calls-and-devices-4d96653e-6176-4978-98ab-2c19df137e43#ID0EBBD=Devices)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy)
