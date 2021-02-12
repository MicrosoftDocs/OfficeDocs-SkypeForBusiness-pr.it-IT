---
title: Distribuire i telefoni e gli schermi di Teams con Intune
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: Questo articolo offre una panoramica delle funzionalità supportate da Microsoft Teams.
ms.openlocfilehash: 4d955db2f260af0eff3d0c1f059461703cf23d79
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825416"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a>Distribuire i telefoni e gli schermi di Teams con Intune

Questo articolo offre una panoramica su come distribuire i telefoni e i display di Teams con Intune.

## <a name="conditional-access"></a>Accesso condizionale

Accesso condizionale è una caratteristica di Azure Active Directory (Azure AD) che consente di assicurarsi che i dispositivi che accedono alle risorse di Office 365 siano gestiti correttamente e sicuri.  Se si applicano criteri di accesso condizionale al servizio Teams, i dispositivi Android (inclusi i telefoni di Teams e gli schermi di Teams) che accedono a Teams devono essere registrati in Intune e le loro impostazioni devono essere conformi ai criteri.  Se il dispositivo non è registrato in Intune o se è registrato ma le relative impostazioni non sono conformi ai criteri, l'accesso condizionale impedisce a un utente di accedere o usare l'app Teams sul dispositivo.

In genere, i criteri di conformità definiti all'interno di Intune vengono assegnati a gruppi di utenti.  Questo significa che se si assegnano criteri di conformità Android a user@contoso.com, tali criteri verranno applicati in modo uniforme allo smartphone Android e a qualsiasi dispositivo Teams basato su Android a cui user@contoso.com accede.

Se si usa l'accesso condizionale, che richiede l'applicazione della registrazione Intune, nell'organizzazione è necessario configurare un paio di cose per consentire la corretta registrazione di Intune:

- **Licenza intune** L'utente che accede al dispositivo Teams deve avere una licenza per Intune.  Se il dispositivo Teams è connesso a un account utente che dispone di una licenza Intune valida, il dispositivo verrà automaticamente registrato in Microsoft Intune nell'ambito della procedura di accesso.
- **Configurare Intune** È necessario avere un tenant Intune configurato correttamente per la registrazione dell'amministratore del dispositivo Android.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Configurare Intune per registrare i dispositivi basati su Teams per Android

I dispositivi basati su Teams su Android sono gestiti da Intune tramite la gestione di Android Device Administrator (DA). Prima di registrare i dispositivi in Intune, è necessario eseguire alcuni passaggi di base.  Se oggi si gestiscono già i dispositivi con Intune, probabilmente si sono già eseguite tutte queste operazioni.  In caso contrario, ecco cosa fare:

1. Impostare Intune MDM (mobile device management) Authority.  Se non si usa mai Intune, è necessario impostare l'autorità mdm prima di poter registrare i dispositivi. Per altre informazioni, vedere [Impostare l'Autorità di gestione di dispositivi mobili.](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set)  Si tratta di un passaggio singolo che deve essere eseguito durante la creazione di un nuovo tenant di Intune.
2. Abilitare la registrazione dell'amministratore del dispositivo Android. I dispositivi Teams basati su Android vengono gestiti come dispositivi di amministrazione dei dispositivi con Intune.  La registrazione dell'amministratore del dispositivo è disattivata per impostazione predefinita per i nuovi tenant creati.  Per altre informazioni, vedere Registrazione [dell'amministratore di dispositivi Android.](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator)
3. Assegnare licenze agli utenti. Agli utenti di dispositivi Teams che si registrano a Intune deve essere assegnata una licenza Intune valida. Per altre informazioni, vedere Assegnare licenze agli utenti in modo [che possano registrare i dispositivi in Intune.](https://docs.microsoft.com/intune/fundamentals/licenses-assign)
4. Assegnare criteri di conformità per l'amministratore dei dispositivi.  Creare criteri di conformità per gli amministratori di dispositivi Android e assegnarli al gruppo di Azure Active Directory che contiene gli utenti che accederanno ai dispositivi Teams. Per altre informazioni, vedere [Usare i criteri di conformità per impostare le regole per i dispositivi gestiti con Intune.](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)

## <a name="see-also"></a>Vedere anche

[Telefoni per Teams](phones-for-teams.md)

[Telefoni IP certificati per Microsoft Teams](teams-ip-phones.md)

[Display di Teams](teams-displays.md)

[Gestire i dispositivi in Teams](device-management.md)

[Teams Marketplace](https://office.com/teamsdevices)
