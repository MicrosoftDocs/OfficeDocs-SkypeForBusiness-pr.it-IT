---
title: Configurare i webinar in Microsoft Teams
author: KarliStites
ms.author: kastites
manager: serdars
ms.reviewer: sachung, emryan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Informazioni su come gestire i criteri webinar per Teams riunioni.
ms.openlocfilehash: 14452b0caeee33f90b59f6581b6fccf4d5e0311b
ms.sourcegitcommit: 4a039550bc5c3a497b6b52c7fed08cadf8268b06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926748"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>Configurare i webinar in Microsoft Teams

Questo articolo illustra come configurare l'organizzazione per ospitare webinar.

## <a name="what-are-webinars"></a>Che cosa sono i webinar?

I webinar sono riunioni strutturate in cui relatori e partecipanti hanno ruoli chiari, spesso usati per scopi di formazione o scenari di creazione di lead generation per vendite e marketing.

Dopo aver impostato webinar nell'organizzazione, gli utenti possono pianificare webinar e aprire la registrazione ai partecipanti. A differenza delle riunioni tradizionali che includono molte discussioni e attività, i webinar sono pensati per presentazioni interattive e forniscono strumenti per l'analisi dei partecipanti.

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>Consentire agli utenti di pianificare webinar con PowerShell

È possibile usare gli attributi seguenti all'interno Windows PowerShell cmdlet **Set-CsTeamsMeetingPolicy** per configurare i webinar in Teams.

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

Per altre informazioni sul cmdlet, vedere [Set-CsTeamsMeetingPolicy.](/powershell/module/skype/set-csteamsmeetingpolicy)

> [!NOTE]
> Prima di eseguire questi cmdlet, è necessario essere connessi a Microsoft Teams PowerShell. Per altre informazioni, vedere [Gestire Teams con Microsoft Teams PowerShell.](/microsoftteams/teams-powershell-managing-teams)

### <a name="allow-users-to-schedule-webinars"></a>Consentire agli utenti di pianificare webinar

È possibile limitare la registrazione solo agli utenti dell'organizzazione o aprirla a tutti gli utenti interni ed esterni al tenant. Per impostazione predefinita, **WhoCanRegister** è abilitato e impostato su **Tutti**. Se si vuole disattivare la registrazione della riunione, impostare **AllowMeetingRegistration** su **False**.

> [!IMPORTANT]
> **AllowPrivateMeetingScheduling** deve essere impostato su **True** perché **AllowMeetingRegistration** funzioni. Inoltre, gli elenchi Microsoft devono essere impostati in SharePoint. Per altre informazioni, vedere [Impostazioni di controllo per Elenchi Microsoft.](/sharepoint/control-lists)

1. Attivare la registrazione alla riunione

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```

2. Attivare la pianificazione privata delle riunioni

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

3. Configurare gli utenti che possono registrarsi per i webinar

**Consentire *solo agli* utenti dell'organizzazione di registrarsi per i webinar**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

**Per consentire a chiunque, inclusi gli utenti anonimi, di registrarsi per i webinar, eseguire:**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!CAUTION]
> Se l'accesso anonimo è disattivato nelle impostazioni della riunione, gli utenti anonimi non possono partecipare ai webinar. Per altre informazioni e abilitare questa impostazione, vedere [Impostazioni riunione in Teams.](meeting-settings-in-teams.md)

### <a name="collect-meeting-attendance"></a>Raccogliere la partecipazione alla riunione

Se si vuole che gli organizzatori analizzino chi ha registrato e partecipato ai webinar, è necessario attivare il criterio **AllowEngagementReport.** A questo scopo, eseguire il comando seguente in PowerShell.

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Enabled
```

### <a name="configure-webinar-settings"></a>Configurare le impostazioni del webinar

Dopo aver abilitato l'ambiente per i webinar, non è necessaria alcuna ulteriore gestione dell'amministratore. I criteri controllano le opzioni da visualizzare per gli organizzatori del webinar.

## <a name="related-topics"></a>Argomenti correlati

- [Criteri riunione in Teams - Generale](meeting-policies-in-teams-general.md)
- [Documentazione di Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
