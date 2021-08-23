---
title: Distribuire Teams telefoni, Teams e Microsoft Teams Rooms su Android con Intune
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
description: Questo articolo fornisce una panoramica delle funzionalità supportate Microsoft Teams display.
ms.openlocfilehash: e7772de5767b9aefe69e1192051be65ccb632656
ms.sourcegitcommit: 85017cf88789c750836780dad2ef707c1c6c39b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2021
ms.locfileid: "58359163"
---
# <a name="deploy-teams-phones-teams-displays-and-microsoft-teams-rooms-on-android-using-intune"></a>Distribuire Teams telefoni, Teams e Microsoft Teams Rooms su Android con Intune

Questo articolo offre una panoramica su come distribuire Teams telefoni, Teams display e Microsoft Teams Rooms su Android con Intune.

## <a name="conditional-access"></a>Accesso condizionale

L'accesso condizionale è una Azure Active Directory (Azure AD) che consente di verificare che i dispositivi che accedono alle risorse Office 365 di rete siano gestiti correttamente e sicuri.  Se si applicano criteri di accesso condizionale al servizio Teams, i dispositivi Android (inclusi telefoni Teams, schermi Teams e Microsoft Teams Rooms in Android) che accedono a Teams devono essere registrati in Intune e le relative impostazioni devono essere conformi ai criteri.  Se il dispositivo non è registrato in Intune o se è registrato ma le relative impostazioni non sono conformi ai criteri, l'accesso condizionale impedirà a un utente di accedere o usare l'app Teams nel dispositivo.

In genere, i criteri di conformità definiti in Intune vengono assegnati a gruppi di utenti.  Questo significa che se si assegnano criteri di conformità Android a user@contoso.com, tali criteri verranno applicati allo stesso modo al proprio smartphone Android e a qualsiasi dispositivo Teams basato su Android a cui user@contoso.com accede.

Se si usa l'accesso condizionale, che richiede l'applicazione della registrazione di Intune, nell'organizzazione è necessario configurare un paio di elementi per consentire la corretta registrazione di Intune:

- **Licenza di Intune** L'utente che accede al dispositivo Teams deve avere una licenza per Intune.  Finché il dispositivo Teams è connesso a un account utente con una licenza intune valida, il dispositivo verrà registrato automaticamente in Microsoft Intune come parte del processo di accesso.
- **Configurare Intune** È necessario avere configurato correttamente un tenant di Intune per la registrazione dell'amministratore di dispositivi Android.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Configurare Intune per la registrazione Teams dispositivi basati su Android

Teams I dispositivi basati su Android sono gestiti da Intune tramite la gestione di Android Device Administrator (DA). Prima che i dispositivi possano essere registrati in Intune, è necessario eseguire alcuni passaggi di base.  Se si stanno già gestendo i dispositivi con Intune oggi, è probabile che siano già state eseguite tutte queste operazioni.  In caso contrario, ecco cosa fare:

> [!NOTE]
> - Se gli amministratori del tenant vogliono che i telefoni di area comune siano registrati in Intune, devono aggiungere una licenza di Intune all'account e seguire i passaggi per la registrazione di Intune.
> - Se l'account utente usato per accedere a un dispositivo Teams non è concesso in licenza per Intune, i criteri di conformità e le restrizioni di registrazione di Intune devono essere disabilitati per l'account.



1. Impostare Intune MDM (gestione di dispositivi mobili) Authority.  

   Se intune non è mai stato usato in precedenza, è necessario impostare l'autorità MDM prima di poter registrare i dispositivi. Per altre informazioni, vedere [Impostare l'autorità di gestione dei dispositivi mobili.](/intune/fundamentals/mdm-authority-set)  Si tratta di un passaggio di una sola volta che deve essere eseguito quando si crea un nuovo tenant di Intune.
1. Abilitare la registrazione dell'amministratore di dispositivi Android.
  
   I dispositivi Teams basati su Android vengono gestiti come dispositivi di amministratore di dispositivi con Intune.  La registrazione dell'amministratore del dispositivo è disattivata per impostazione predefinita per i tenant appena creati. Vedere [Registrazione dell'amministratore di dispositivi Android](/intune/enrollment/android-enroll-device-administrator).
1. Assegnare licenze agli utenti. 
 
   Agli utenti Teams dispositivi di registrazione a Intune deve essere assegnata una licenza intune valida. Per altre informazioni, vedere Assegnare licenze agli utenti in modo [che possano registrare i dispositivi in Intune.](/intune/fundamentals/licenses-assign)
1. Assegnare i criteri di conformità dell'amministratore di dispositivo.  

   1. Creare criteri di conformità per l'amministratore di dispositivi Android.

   1. Assegnarlo al gruppo Azure Active Directory che contiene gli utenti che accederanno ai Teams dispositivi. Vedere [Usare i criteri di conformità per impostare regole per i dispositivi gestiti con Intune.](/mem/intune/protect/device-compliance-get-started)

## <a name="see-also"></a>Vedere anche

[Telefoni per Teams](phones-for-teams.md)

[Telefoni IP certificati per Microsoft Teams](teams-ip-phones.md)

[Teams display](teams-displays.md)

[Gestire i dispositivi in Teams](device-management.md)

[Teams Marketplace](https://office.com/teamsdevices)
