---
title: Distribuisci Teams telefoni, schermi Teams, pannelli Teams e Microsoft Teams Rooms nei Android con Intune
ms.author: serdars
author: SerdarSoysal
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
ms.localizationpriority: medium
description: Questo articolo fornisce una panoramica e le funzionalità supportate da Microsoft Teams Android dispositivi.
ms.openlocfilehash: 17f5e537b44d3aacd967ff5e8ffaa84df9da3f9b
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674858"
---
# <a name="deploy-teams-phones-teams-displays-teams-panels-and-microsoft-teams-rooms-on-android-using-intune"></a>Distribuisci Teams telefoni, schermi Teams, pannelli Teams e Microsoft Teams Rooms nei Android con Intune

Questo articolo offre una panoramica su come distribuire Teams telefoni, schermi Teams, pannelli Teams e Microsoft Teams Rooms Android con Intune.

## <a name="conditional-access"></a>Accesso condizionale

L'accesso condizionale è una funzionalità di Azure Active Directory (Azure AD) che consente di garantire che i dispositivi che accedono alle risorse Office 365 siano gestiti correttamente e siano sicuri.  Se si applicano criteri di accesso condizionale al servizio Teams, Android dispositivi (inclusi telefoni Teams, schermi Teams, pannelli Teams e Microsoft Teams Rooms su Android) che accedono Teams devono essere registrati in Intune e le relative impostazioni devono essere conformi ai criteri.  Se il dispositivo non è registrato in Intune o se è registrato ma le impostazioni non sono conformi ai criteri, l'accesso condizionale impedirà a un utente di accedere o usare l'app Teams nel dispositivo.

In genere, i criteri di conformità definiti all'interno di Intune vengono assegnati a gruppi di utenti.  Questo significa che se si assegnano criteri di conformità Android a user@contoso.com, tali criteri verranno applicati in modo uniforme allo smartphone Android e a qualsiasi dispositivo Teams basato su Android a cui user@contoso.com accede.

Se si usa l'accesso condizionale, che richiede l'applicazione della registrazione di Intune, nell'organizzazione è necessario configurare un paio di operazioni per consentire il corretto Intune registrazione:

- **Intune licenza** L'utente che accede al dispositivo Teams deve avere una licenza per Intune.  Se il dispositivo Teams è connesso a un account utente con una licenza di Intune valida, il dispositivo verrà registrato automaticamente in Microsoft Intune nell'ambito del processo di accesso.
- **Configurare Intune È necessario configurare** correttamente un tenant Intune per Android registrazione di Amministratore dispositivo.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Configurare Intune per la registrazione di dispositivi basati su Teams Android

I dispositivi basati su Teams Android vengono gestiti da Intune tramite la gestione di Android Device Administrator (DA). Prima di registrare i dispositivi in Intune, è necessario eseguire alcune operazioni di base.  Se oggi stai già gestendo i dispositivi con Intune, probabilmente hai già fatto tutte queste operazioni.  In caso contrario, ecco cosa fare:

> [!NOTE]
> - Se gli amministratori del tenant vogliono che i telefoni dell'area comune siano registrati in Intune, devono aggiungere una licenza di Intune all'account e seguire la procedura per Intune registrazione.
> - Se l'account utente usato per accedere a un dispositivo Teams non è concesso in licenza per Intune, è necessario disabilitare i criteri di conformità e le restrizioni di registrazione per Intune per l'account.



1. Impostare Intune autorità MDM (gestione di dispositivi mobili).  

   Se non si è mai usato Intune prima, è necessario impostare l'autorità MDM prima di poter registrare i dispositivi. Per ulteriori informazioni, vedere [Impostare l'autorità di gestione dei dispositivi mobili](/intune/fundamentals/mdm-authority-set).  Si tratta di un passaggio che deve essere eseguito una sola volta quando si crea un nuovo tenant Intune.
1. Abilita Android registrazione dell'amministratore del dispositivo.
  
   I dispositivi Teams basati su Android vengono gestiti come dispositivi di amministratore del dispositivo con Intune.  La registrazione dell'amministratore del dispositivo è disattivata per impostazione predefinita per i nuovi tenant creati. Vedi [Android registrazione dell'amministratore del dispositivo](/intune/enrollment/android-enroll-device-administrator).
1. Assegnare licenze agli utenti. 
 
   Agli utenti di Teams dispositivi registrati a Intune deve essere assegnata una licenza di Intune valida. Per altre informazioni, vedere [Assegnare licenze agli utenti in modo che possano registrare dispositivi in Intune](/intune/fundamentals/licenses-assign).
1. Assegnare criteri di conformità per l'amministratore del dispositivo.  

   1. Creare un Android criteri di conformità per l'amministratore del dispositivo.

   1. Assegnarlo al gruppo Azure Active Directory contenente gli utenti che accederanno ai dispositivi Teams. Vedere [Usare i criteri di conformità per impostare le regole per i dispositivi gestiti con Intune](/mem/intune/protect/device-compliance-get-started).

## <a name="see-also"></a>Vedere anche

[Telefoni per Teams](phones-for-teams.md)

[Telefoni IP certificati per Microsoft Teams](teams-ip-phones.md)

[Teams schermi](teams-displays.md)

[Gestire i dispositivi in Teams](device-management.md)

[Teams Marketplace](https://office.com/teamsdevices)
