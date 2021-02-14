---
title: Usare PowerShell per impostare i criteri per gli eventi live
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Esempi di come usare PowerShell per impostare criteri in Teams per controllare chi può tenere eventi live nell'organizzazione e le funzionalità disponibili negli eventi.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ece22b6debd3c7d6209df96983d1d66ed5f6f3ca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815626"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>Usare PowerShell per impostare criteri per gli eventi live in Microsoft Teams

È possibile usare i cmdlet di Windows PowerShell seguenti per impostare e assegnare le impostazioni dei criteri per gli eventi live in Teams: 
- [Get-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Grant-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

Ecco alcuni esempi.

> [!NOTE]
> Prima di eseguire questi cmdlet, è necessario essere connessi a PowerShell di Skype for Business Online. Per ulteriori informazioni, consulta [Gestire Skype for Business online con Microsoft 365 o PowerShell di Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

## <a name="allow-users-to-schedule-live-events"></a>Consentire agli utenti di pianificare eventi live 

> [!NOTE]
> Questi esempi sono relativi a eventi prodotti in Teams. Per gli eventi prodotti con un'app o un dispositivo esterno, è necessario eseguire alcuni passaggi aggiuntivi. Per altre informazioni, vedere [Consentire agli utenti di pianificare eventi prodotti con un'app o un dispositivo esterno.](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)

**Consentire a un utente di pianificare eventi live**

Se all'utente sono assegnati criteri globali, eseguire e verificare che il parametro *AllowBroadcastScheduling* sia impostato su *True:*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Quindi assegnare l'utente ai criteri globali, eseguire:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>Scenari utente
**Si vuole consentire a tutti gli utenti dell'organizzazione di pianificare eventi live**

Se agli utenti sono assegnati criteri globali, eseguire e verificare che *AllowBroadcastScheduling* *sia impostato su *True:*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Se agli utenti sono assegnati criteri diversi da quelli globali, eseguire e verificare che *-AllowBroadcastScheduling* sia impostato su *True:*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**Si vuole che la pianificazione degli eventi live sia disabilitata nell'intera organizzazione**

Disabilitare la pianificazione di eventi live, eseguire:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Assegnare a tutti gli utenti dell'organizzazione i criteri globali, eseguire:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Si vuole che un numero elevato di utenti sia in grado di pianificare eventi live e impedire a un gruppo di utenti di pianificarli**

Eseguire e verificare che *AllowBroadcastScheduling* sia impostato su *True:*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
Quindi assegnare uno o più utenti ai criteri globali, eseguire:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

Per creare un nuovo criterio che non consente la pianificazione di eventi in tempo reale, eseguire:
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
Disabilitare la pianificazione di eventi live, eseguire:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
Quindi assegnare gli utenti a questo criterio, eseguire:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**Si vuole disabilitare la pianificazione di eventi live per un numero elevato di utenti e consentire a un set di utenti di pianificarli**

Disabilitare la pianificazione di eventi live, eseguire:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Assegnare quindi questi utenti ai criteri globali, eseguire:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Creare un criterio per consentire la pianificazione di eventi live, eseguire:
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
Abilitare la pianificazione di eventi live, eseguire:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
Quindi assegnare gli utenti a questo criterio, eseguire:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>Impostare chi può partecipare a eventi live
 
Impostare i criteri globali per consentire agli utenti di creare eventi a cui tutti, compresi gli utenti anonimi, possono partecipare, eseguire:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>Impostare l'opzione di registrazione per gli eventi live
> [!NOTE]
> Questa impostazione si applica solo agli eventi prodotti in Teams.

Impostare il criterio globale per disabilitare la registrazione per gli eventi live:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a>Impostare sottotitoli in tempo reale negli eventi live
> [!NOTE]
> Questa impostazione si applica solo agli eventi prodotti in Teams. 

Impostare i criteri globali in modo da attivare i sottotitoli in tempo reale (trascrizione) per i partecipanti all'evento:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>Argomenti correlati
- [Configurare gli eventi live di Teams](set-up-for-teams-live-events.md)
- [Panoramica di PowerShell per Teams](../teams-powershell-overview.md)

