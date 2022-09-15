---
title: Distribuire telefoni, schermi di Teams, pannelli di Teams e Microsoft Teams Rooms su Android usando Intune
author: CarolynRowe
ms.author: crowe
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
- Teams_ITAdmin_Devices
search.appverid: MET150
ms.localizationpriority: medium
description: Questo articolo fornisce una panoramica e le funzionalità supportate dai dispositivi Android di Microsoft Teams.
ms.openlocfilehash: 388848019806740074401400d0fad6847751489e
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705995"
---
# <a name="deploy-teams-phones-teams-displays-teams-panels-and-microsoft-teams-rooms-on-android-using-intune"></a>Distribuire telefoni, schermi di Teams, pannelli di Teams e Microsoft Teams Rooms su Android usando Intune

Questo articolo offre una panoramica su come distribuire telefoni, schermi di Teams, pannelli di Teams e Microsoft Teams Rooms su Android usando Intune.

## <a name="conditional-access"></a>Accesso condizionale

L'accesso condizionale è una funzionalità di Azure Active Directory (Azure AD) che consente di garantire che i dispositivi che accedono alle risorse Office 365 siano gestiti e protetti correttamente. Se si applicano criteri di accesso condizionale al servizio Teams, i dispositivi Android (inclusi i telefoni Teams, gli schermi di Teams, i pannelli di Teams e Microsoft Teams Rooms su Android) che accedono a Teams devono essere registrati in Intune e le relative impostazioni devono essere conformi ai criteri.  Se il dispositivo non è registrato in Intune o se è registrato ma le impostazioni non sono conformi ai criteri, l'accesso condizionale impedirà a un utente di accedere o usare l'app Teams nel dispositivo.

In genere, i criteri di conformità definiti all'interno di Intune vengono assegnati a gruppi di utenti.  Ciò significa che se si assegnano criteri di conformità Android a user@contoso.com, tali criteri verranno applicati allo stesso modo al proprio smartphone Android e a qualsiasi dispositivo Teams basato su Android a cui user@contoso.com accede.

Se si usa l'accesso condizionale, che richiede l'applicazione della registrazione di Intune, nell'organizzazione è necessario configurare un paio di operazioni per consentire il corretto Intune registrazione:

- **Intune licenza** L'utente che accede al dispositivo Teams deve avere una licenza per Intune.  Se il dispositivo Teams è connesso a un account utente con una licenza di Intune valida, il dispositivo verrà registrato automaticamente in Microsoft Intune nell'ambito del processo di accesso.
- **Configurare Intune** È necessario avere un tenant configurato correttamente Intune per la registrazione dell'amministratore del dispositivo Android.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Configurare Intune per la registrazione di dispositivi Teams basati su Android

I dispositivi basati su Android di Teams sono gestiti da Intune tramite la gestione dell'amministratore di dispositivi Android (DA). Prima di registrare i dispositivi in Intune, è necessario eseguire alcune operazioni di base.  Se oggi stai già gestendo i dispositivi con Intune, probabilmente hai già fatto tutte queste operazioni.  In caso contrario, ecco cosa fare:

> [!NOTE]
> - Se gli amministratori del tenant vogliono che i telefoni dell'area comune siano registrati in Intune, devono aggiungere una licenza di Intune all'account e seguire la procedura per Intune registrazione.
> - Se l'account utente usato per accedere a un dispositivo Teams non è concesso in licenza per Intune, è necessario disabilitare i criteri di conformità Intune e le restrizioni di registrazione per l'account.
> - Se l'account utente usato per accedere a un dispositivo Teams è concesso in licenza per Intune, il dispositivo Teams verrà registrato automaticamente in Intune.



1. Impostare Intune autorità MDM (gestione di dispositivi mobili).  

   Se non si è mai usato Intune prima, è necessario impostare l'autorità MDM prima di poter registrare i dispositivi. Per ulteriori informazioni, vedere [Impostare l'autorità di gestione dei dispositivi mobili](/intune/fundamentals/mdm-authority-set).  Si tratta di un passaggio che deve essere eseguito una sola volta quando si crea un nuovo tenant Intune.
1. Abilita la registrazione dell'amministratore del dispositivo Android.
  
   I dispositivi Teams basati su Android vengono gestiti come dispositivi di amministratore dei dispositivi con Intune.  La registrazione dell'amministratore del dispositivo è disattivata per impostazione predefinita per i nuovi tenant creati. Vedi [Registrazione dell'amministratore del dispositivo Android](/intune/enrollment/android-enroll-device-administrator).
1. Assegnare licenze agli utenti. 
 
   Agli utenti dei dispositivi Teams registrati a Intune deve essere assegnata una licenza di Intune valida. Per altre informazioni, vedere [Assegnare licenze agli utenti in modo che possano registrare dispositivi in Intune](/intune/fundamentals/licenses-assign).
1. Assegnare criteri di conformità per l'amministratore del dispositivo.  

   1. Creare criteri di conformità per l'amministratore del dispositivo Android.

   1. Assegnarlo al gruppo di Azure Active Directory che contiene gli utenti che accederanno ai dispositivi teams. Vedere [Usare i criteri di conformità per impostare le regole per i dispositivi gestiti con Intune](/mem/intune/protect/device-compliance-get-started).

## <a name="see-also"></a>Vedere anche

[Telefoni per Teams](phones-for-teams.md)

[Telefoni IP certificati per Microsoft Teams](teams-ip-phones.md)

[Visualizzazioni di Teams](teams-displays.md)

[Gestire i dispositivi in Teams](device-management.md)

[Teams Marketplace](https://office.com/teamsdevices)
