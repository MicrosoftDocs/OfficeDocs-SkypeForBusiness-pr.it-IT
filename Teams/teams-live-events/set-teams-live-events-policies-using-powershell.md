---
title: Usare PowerShell per impostare criteri per gli eventi live
author: mkbond007
ms.author: mabond
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: Esempi di come usare PowerShell per impostare criteri in Teams per controllare chi può tenere eventi live nell'organizzazione e le funzionalità disponibili negli eventi.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e0d46c0675bd8b810f8dbce8585661184fbef74f
ms.sourcegitcommit: 791d0a341ff873145fa893ece05055729b0b8d50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/18/2022
ms.locfileid: "66838841"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>Usare PowerShell per impostare criteri per gli eventi live in Microsoft Teams

È possibile usare i cmdlet di Windows PowerShell seguenti per impostare e assegnare le impostazioni dei criteri per gli eventi live in Teams: 
- [Get-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Grant-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

Ecco alcuni esempi.

> [!NOTE]
> Prima di eseguire questi cmdlet, è necessario essere connessi a Skype for Business PowerShell online. Per altre informazioni, vedere [Gestire Skype for Business online con Microsoft 365 o Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

## <a name="allow-users-to-schedule-live-events"></a>Consentire agli utenti di pianificare eventi live 

> [!NOTE]
> Questi esempi sono per gli eventi prodotti in Teams. Per gli eventi prodotti con un'app o un dispositivo esterno, è necessario eseguire altre operazioni. Per altre informazioni, vedere [Consentire agli utenti di pianificare gli eventi prodotti con un'app o un dispositivo esterno](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).

**Consentire a un utente di pianificare eventi live**

Se all'utente è assegnato il criterio globale, eseguire e verificare che *il parametro AllowBroadcastScheduling* sia impostato su *True*:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Quindi assegnare l'utente al criterio globale, eseguire:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>Scenari utente
**Si vuole consentire a tutti gli utenti dell'organizzazione di pianificare eventi live**

Se agli utenti sono assegnati i criteri globali, eseguire e verificare che *AllowBroadcastScheduling* *sia impostato su *True*:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Se agli utenti viene assegnato un criterio diverso da quello globale, eseguire e verificare che *-AllowBroadcastScheduling* sia impostato su *True*:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**Si vuole che la pianificazione degli eventi live venga disabilitata nell'intera organizzazione**

Disabilitare la pianificazione degli eventi live, eseguire:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Assegnare tutti gli utenti dell'organizzazione ai criteri globali, eseguire:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Si vuole che un numero elevato di utenti possa pianificare eventi live e impedire a un set di utenti di pianificarli**

Esegui e verifica che *AllowBroadcastScheduling* sia impostato su *True*:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
Assegnare quindi uno o più utenti ai criteri globali, eseguire:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

Creare un nuovo criterio che non consente la pianificazione di eventi live, eseguire:
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
Disabilitare la pianificazione degli eventi live, eseguire:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
Quindi assegnare gli utenti a questo criterio, eseguire:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**Si vuole disabilitare la pianificazione di eventi live per un numero elevato di utenti e consentire a un set di utenti di pianificare**

Disabilitare la pianificazione degli eventi live, eseguire:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Assegnare quindi questi utenti ai criteri globali, eseguire:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Creare un criterio per consentire la pianificazione di eventi in tempo reale, eseguire:
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
 
Impostare i criteri globali per consentire agli utenti di creare eventi a cui tutti, inclusi gli utenti anonimi, possono partecipare, eseguire:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>Impostare l'opzione di registrazione per gli eventi live
> [!NOTE]
> Questa impostazione si applica solo agli eventi prodotti in Teams.

Impostare i criteri globali per disabilitare la registrazione per gli eventi live:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a>Impostare sottotitoli e sottotitoli in tempo reale negli eventi live
> [!NOTE]
> Questa impostazione si applica solo agli eventi prodotti in Teams. 

Impostare i criteri globali per attivare sottotitoli e sottotitoli in tempo reale (trascrizione) per i partecipanti all'evento:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>Argomenti correlati
- [Configurare gli eventi live di Teams](set-up-for-teams-live-events.md)
- [Panoramica di PowerShell per Teams](../teams-powershell-overview.md)