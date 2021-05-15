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
ms.openlocfilehash: 739c0b5494b0ecc5b9a20fd8db4756313848325b
ms.sourcegitcommit: e5d6a2c3ad45c1285016b93ec4c7afea907d71a1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275520"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>Configurare i webinar in Microsoft Teams

Questo articolo illustra come configurare l'organizzazione per ospitare webinar.

## <a name="what-are-webinars"></a>Che cosa sono i webinar?

I webinar sono riunioni strutturate in cui istruttori e partecipanti hanno ruoli chiari, spesso usati per scopi di formazione o scenari di creazione di lead generation di vendite e marketing.

Dopo aver impostato webinar nell'organizzazione, gli utenti possono pianificare webinar e aprire la registrazione ai partecipanti. A differenza delle riunioni tradizionali che includono molte discussioni e attività, i webinar sono pensati per presentazioni interattive e forniscono strumenti per l'analisi dei partecipanti.

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>Consentire agli utenti di pianificare webinar con PowerShell

È possibile usare gli attributi seguenti all'interno Windows PowerShell cmdlet **Set-CsTeamsMeetingPolicy** per configurare i webinar in Teams.

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

Per altre informazioni sul cmdlet, vedere [Set-CsTeamsMeetingPolicy.](/powershell/module/skype/set-csteamsmeetingpolicy)

> [!NOTE]
> Prima di eseguire questi cmdlet, è necessario essere connessi Skype for Business PowerShell online. Per altre informazioni, vedere [Gestire Skype for Business Online con Microsoft 365 o Office 365 PowerShell.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

### <a name="allow-users-to-schedule-webinars"></a>Consentire agli utenti di pianificare webinar

Per consentire agli utenti dell'organizzazione di pianificare webinar, eseguire:

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration True
```
### <a name="configure-who-can-register-for-webinars"></a>Configurare gli utenti che possono registrarsi per i webinar

È possibile limitare la registrazione solo agli utenti dell'organizzazione o aprirla a tutti gli utenti interni ed esterni al tenant. Per impostazione predefinita, **WhoCanRegister** è abilitato e impostato su **Tutti**. Se si vuole disattivare la registrazione della riunione, impostare **WhoCanRegister** su **False**.

> [!IMPORTANT]
> Tenere presente che **AllowPrivateMeetingScheduling** deve essere impostato su **True** per il funzionamento di **WhoCanRegister.** Inoltre, gli elenchi Microsoft devono essere impostati in SharePoint. Per altre informazioni, vedere [Impostazioni di controllo per Elenchi Microsoft.](/sharepoint/control-lists)

**Per consentire *solo agli* utenti dell'organizzazione di registrarsi per i webinar, eseguire:**

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling True
```

Quindi, esegui:

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

**Per consentire a chiunque, inclusi gli utenti anonimi, di registrarsi per i webinar, eseguire:**

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling True
```

Quindi, esegui:

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!IMPORTANT]
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