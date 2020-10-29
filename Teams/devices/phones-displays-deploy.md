---
title: Distribuire telefoni e team di teams visualizzati con Intune
ms.author: v-lanac
author: lanachin
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
description: Questo articolo offre una panoramica delle funzionalità e delle caratteristiche supportate da Microsoft teams.
ms.openlocfilehash: acebf619d76cd6df2f0da305deedec9dd3b79aa0
ms.sourcegitcommit: e07b2d7470b93e52b9e85207db0d6fa3a136efd9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "48787637"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a>Distribuire telefoni e team di teams visualizzati con Intune

Questo articolo offre una panoramica su come distribuire i telefoni dei team e i team visualizzati con Intune.

## <a name="conditional-access"></a>Accesso condizionale

L'accesso condizionale è una caratteristica di Azure Active Directory (Azure AD) che consente di verificare che i dispositivi che accedono alle risorse di Office 365 siano gestiti correttamente e siano sicuri.  Se si applicano criteri di accesso condizionale al servizio teams, i dispositivi Android (inclusi i telefoni delle squadre e i team vengono visualizzati) che i team di Access devono essere iscritti a Intune e le relative impostazioni devono essere conformi ai criteri.  Se il dispositivo non è registrato in Intune o se è registrato ma le sue impostazioni non sono conformi ai criteri, l'accesso condizionale impedirà a un utente di accedere o usare l'app Teams nel dispositivo.

In genere, i criteri di conformità definiti in Intune vengono assegnati a gruppi di utenti.  Questo significa che se assegni un criterio di conformità Android a user@contoso.com, tale criterio verrà applicato ugualmente allo smartphone Android e a qualsiasi dispositivo team basato su Android in cui user@contoso.com.

Se si usa l'accesso condizionale, che richiede la registrazione di Intune per essere applicata, nell'organizzazione sono disponibili un paio di cose che è necessario configurare per consentire una registrazione di Intune riuscita:

- **Licenza Intune** L'utente che esegue l'accesso al dispositivo Teams deve essere concesso in licenza per Intune.  Purché il dispositivo teams abbia eseguito l'accesso a un account utente con una licenza valida di Intune, il dispositivo verrà registrato automaticamente in Microsoft Intune come parte del processo di accesso.
- **Configurare Intune** È necessario disporre di un tenant di Intune configurato in modo appropriato per la registrazione di amministratore di dispositivi Android.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Configurare Intune per la registrazione di Team dispositivi basati su Android

I dispositivi basati su Android di teams sono gestiti da in Intune tramite la gestione di Android Device Administrator (DA). Prima di poter registrare i dispositivi in Intune, è possibile eseguire alcuni passaggi di base.  Se si stanno già gestendo i dispositivi con Intune oggi, è probabile che siano già stati eseguiti tutti questi elementi.  In caso contrario, ecco cosa fare:

1. Impostare l'autorità di Intune MDM (Mobile Device Management).  Se non si è mai usato Intune prima, è necessario impostare l'autorità MDM prima di poter registrare i dispositivi. Per altre informazioni, vedere [impostare l'autorità di gestione di dispositivi mobili](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set).  Si tratta di un passaggio di una sola volta che deve essere eseguito dopo la creazione di un nuovo tenant di Intune.
2. Abilitare la registrazione di amministratore di dispositivi Android. Il dispositivo teams basato su Android viene gestito come dispositivi di amministrazione dei dispositivi con Intune.  La registrazione dell'amministratore del dispositivo è disinserita per impostazione predefinita per i tenant appena creati.  Per altre informazioni, Vedi [registrazione di amministratore di dispositivi Android](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator).
3. Assegnare licenze agli utenti. Agli utenti dei dispositivi team che si iscrive a Intune deve essere assegnata una licenza valida di Intune. Per altre informazioni, vedere [assegnare licenze agli utenti in modo che possano registrare i dispositivi in Intune](https://docs.microsoft.com/intune/fundamentals/licenses-assign).
4. Assegnare criteri di conformità di amministratore del dispositivo.  Creare un criterio di conformità di amministratore di dispositivi Android e assegnarlo al gruppo di Azure Active Directory che contiene gli utenti che effettueranno l'accesso ai dispositivi teams. Per altre informazioni, vedere [usare i criteri di conformità per impostare regole per i dispositivi gestiti con Intune](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started).

## <a name="see-also"></a>Vedere anche

[Telefoni per Teams](phones-for-teams.md)

[Telefoni IP certificati per Microsoft Teams](teams-ip-phones.md)

[Mostra Teams](teams-displays.md)

[Gestire i dispositivi in Teams](device-management.md)

[Marketplace Teams](https://office.com/teamsdevices)
