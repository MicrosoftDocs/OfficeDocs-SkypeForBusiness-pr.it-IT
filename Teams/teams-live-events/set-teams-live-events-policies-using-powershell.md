---
title: Usare PowerShell per impostare i criteri degli eventi dinamici in Microsoft Teams
author: chuckedmonson
ms.author: chucked
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Esempi di come usare PowerShell per impostare i criteri in teams per controllare chi può contenere eventi dinamici nell'organizzazione e le caratteristiche disponibili negli eventi creati
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0d734cd4a92f3ebd32e2d0e6a24292ae50b456e7
ms.sourcegitcommit: 1de5e4d829405b75c0a87918cc7c8fa7227e0ad6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "40952879"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>Usare PowerShell per impostare i criteri degli eventi dinamici in Microsoft Teams

Puoi usare i cmdlet di Windows PowerShell seguenti per impostare e assegnare le impostazioni dei criteri per gli eventi dinamici in teams: 
- [Get-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Grant-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

Ecco alcuni esempi.

## <a name="allow-users-to-schedule-live-events"></a>Consentire agli utenti di pianificare eventi dinamici 

> [!NOTE]
> Questi esempi sono per gli eventi prodotti in teams. Per gli eventi prodotti con un'app o un dispositivo esterno, è necessario eseguire ulteriori operazioni. Per altre informazioni, vedere [consentire agli utenti di pianificare gli eventi prodotti con un'app o un dispositivo esterno](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).

**Consentire a un utente di pianificare eventi dinamici**

Se all'utente viene assegnato il criterio globale, eseguire e verificare che il parametro *AllowBroadcastScheduling* sia impostato su *true*:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Assegnare quindi l'utente al criterio globale, eseguire:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>Scenari utente
**Si vuole che tutti gli utenti dell'organizzazione possano pianificare eventi dinamici**

Se agli utenti viene assegnato il criterio globale, eseguire e verificare che *AllowBroadcastScheduling* * sia impostato su *true*:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Se agli utenti viene assegnato un criterio diverso dal criterio globale, eseguire e verificare che *-AllowBroadcastScheduling* sia impostato su *true*:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**Si vuole che la programmazione di eventi dinamici venga disabilitata nell'organizzazione**

Disabilitare la programmazione di eventi dinamici, eseguire:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Assegnare tutti gli utenti dell'organizzazione al criterio globale, eseguire:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Si vuole che un numero elevato di utenti sia in grado di programmare eventi dinamici e impedire a un gruppo di utenti di pianificarli**

Eseguire e verificare che *AllowBroadcastScheduling* sia impostato su *true*:
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
Assegnare quindi un utente o utenti al criterio globale, eseguire:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

Creare un nuovo criterio che non consenta la pianificazione di eventi dinamici, eseguire:
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
Disabilitare la programmazione di eventi dinamici, eseguire:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
Quindi, assegna gli utenti a questo criterio, Esegui:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**Si vuole disabilitare la programmazione di eventi dinamici per un numero elevato di utenti e consentire a un set di utenti di pianificarli**

Disabilitare la programmazione di eventi dinamici, eseguire:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Quindi, assegna gli utenti al criterio globale, Esegui:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Creare un criterio per consentire la programmazione di eventi dinamici, eseguire:
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
Abilitare la programmazione di eventi dinamici, eseguire:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
Quindi, assegna gli utenti a questo criterio, Esegui:
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>Impostare gli utenti che possono partecipare agli eventi Live
 
Impostare il criterio globale per consentire agli utenti di creare eventi che tutti, inclusi gli utenti anonimi, possono partecipare, eseguire:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>Impostare l'opzione di registrazione per gli eventi dinamici
> [!NOTE]
> Questa impostazione si applica solo agli eventi prodotti in teams.

Impostare il criterio globale per disabilitare la registrazione per gli eventi Live:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a>Impostare didascalie e sottotitoli dinamici in eventi dinamici
> [!NOTE]
> Questa impostazione si applica solo agli eventi prodotti in teams. 

Impostare il criterio globale per attivare le didascalie e i sottotitoli Live (trascrizione) per i partecipanti agli eventi:
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>Argomenti correlati
- [Configurare gli eventi live di Teams](set-up-for-teams-live-events.md)


