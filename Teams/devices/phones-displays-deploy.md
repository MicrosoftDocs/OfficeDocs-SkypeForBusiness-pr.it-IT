---
title: Distribuire i telefoni di Teams e gli schermi di Teams con Intune
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
description: Questo articolo fornisce una panoramica delle funzionalità supportate da Microsoft Teams.
ms.openlocfilehash: 178f8c594f8953c56a2d354806e86f4a19de028f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120778"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a>Distribuire i telefoni di Teams e gli schermi di Teams con Intune

Questo articolo offre una panoramica su come distribuire i telefoni di Teams e gli schermi di Teams con Intune.

## <a name="conditional-access"></a>Accesso condizionale

L'accesso condizionale è una funzionalità di Azure Active Directory (Azure AD) che consente di verificare che i dispositivi che accedono alle risorse di Office 365 siano gestiti correttamente e siano sicuri.  Se si applicano criteri di accesso condizionale al servizio Teams, i dispositivi Android (inclusi i telefoni Di Teams e gli schermi di Teams) che accedono a Teams devono essere registrati in Intune e le relative impostazioni devono essere conformi ai criteri.  Se il dispositivo non è registrato in Intune o se è registrato ma le relative impostazioni non sono conformi ai criteri, l'accesso condizionale impedirà a un utente di accedere o usare l'app Teams nel dispositivo.

In genere, i criteri di conformità definiti in Intune vengono assegnati a gruppi di utenti.  Questo significa che se si assegnano criteri di conformità Android a user@contoso.com, tali criteri verranno applicati allo stesso modo al proprio smartphone Android e a qualsiasi dispositivo Teams basato su Android a cui user@contoso.com accede.

Se si usa l'accesso condizionale, che richiede l'applicazione della registrazione di Intune, nell'organizzazione è necessario configurare un paio di elementi per consentire la corretta registrazione di Intune:

- **Licenza di Intune** L'utente che accede al dispositivo Teams deve avere una licenza per Intune.  Finché il dispositivo Teams è connesso a un account utente con una licenza intune valida, il dispositivo verrà registrato automaticamente in Microsoft Intune nell'ambito del processo di accesso.
- **Configurare Intune** È necessario avere configurato correttamente un tenant di Intune per la registrazione dell'amministratore di dispositivi Android.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Configurare Intune per registrare i dispositivi basati su Teams android

I dispositivi basati su Android di Teams sono gestiti da Intune tramite la gestione di Android Device Administrator (DA). Prima che i dispositivi possano essere registrati in Intune, è necessario eseguire alcuni passaggi di base.  Se si stanno già gestendo i dispositivi con Intune oggi, è probabile che siano già state eseguite tutte queste operazioni.  In caso contrario, ecco cosa fare:

1. Impostare Intune MDM (gestione di dispositivi mobili) Authority.  Se intune non è mai stato usato in precedenza, è necessario impostare l'autorità MDM prima di poter registrare i dispositivi. Per altre informazioni, vedere [Impostare l'autorità di gestione dei dispositivi mobili.](/intune/fundamentals/mdm-authority-set)  Si tratta di un passaggio di una sola volta che deve essere eseguito quando si crea un nuovo tenant di Intune.
2. Abilitare la registrazione dell'amministratore di dispositivi Android. I dispositivi Teams basati su Android vengono gestiti come dispositivi di amministratore di dispositivi con Intune.  La registrazione dell'amministratore del dispositivo è disattivata per impostazione predefinita per i tenant appena creati.  Per altre informazioni, vedere Registrazione [dell'amministratore di dispositivi Android](/intune/enrollment/android-enroll-device-administrator).
3. Assegnare licenze agli utenti. Agli utenti dei dispositivi Teams che si registrano a Intune deve essere assegnata una licenza intune valida. Per altre informazioni, vedere Assegnare licenze agli utenti in modo [che possano registrare i dispositivi in Intune.](/intune/fundamentals/licenses-assign)
4. Assegnare i criteri di conformità dell'amministratore di dispositivo.  Creare criteri di conformità di Amministratore dispositivi Android e assegnarli al gruppo Azure Active Directory che contiene gli utenti che accederanno ai dispositivi Teams. Per altre informazioni, vedere [Usare i criteri di conformità per impostare regole per i dispositivi gestiti con Intune.](/mem/intune/protect/device-compliance-get-started)

## <a name="see-also"></a>Vedere anche

[Telefoni per Teams](phones-for-teams.md)

[Telefoni IP certificati per Microsoft Teams](teams-ip-phones.md)

[Visualizzazione di Teams](teams-displays.md)

[Gestire i dispositivi in Teams](device-management.md)

[Teams Marketplace](https://office.com/teamsdevices)