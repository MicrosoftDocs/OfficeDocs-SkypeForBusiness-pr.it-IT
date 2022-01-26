---
title: Configurare webinar in Microsoft Teams
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
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Informazioni su come gestire i criteri webinar per Teams riunioni.
ms.openlocfilehash: 5536a6c03df15be349edea7d980932b5fc0173ab
ms.sourcegitcommit: faeb8976299375e7658499ff31d25e8ef6003144
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2022
ms.locfileid: "62224003"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>Configurare webinar in Microsoft Teams

Questo articolo illustra come configurare l'organizzazione per ospitare webinar.

## <a name="what-are-webinars"></a>Che cosa sono i webinar?

I webinar sono riunioni strutturate in cui relatori e partecipanti hanno ruoli chiari, spesso usati per scopi di formazione o scenari di creazione di lead generation per vendite e marketing.

Dopo aver impostato webinar nell'organizzazione, gli utenti possono pianificare webinar e aprire la registrazione ai partecipanti. A differenza delle riunioni tradizionali che includono molte discussioni e attività, i webinar sono pensati per presentazioni interattive e forniscono strumenti per l'analisi dei partecipanti.

> [!IMPORTANT]
> Per consentire agli utenti di configurare webinar, Elenchi Microsoft devono essere configurati in SharePoint abilitando la creazione di elenchi personali. Per altre informazioni, vedere [Impostazioni di controllo per Elenchi Microsoft.](/sharepoint/control-lists)

## <a name="allow-users-to-schedule-webinars-in-the-teams-admin-center"></a>Consentire agli utenti di pianificare webinar nell'Teams di amministrazione

È possibile usare l'Teams di amministrazione per configurare webinar per l'organizzazione. I criteri per configurare i webinar sono presenti nell'interfaccia di amministrazione Teams riunioni in **Criteri**  >  **riunione**.

### <a name="meeting-registration"></a>Registrazione della riunione

Se si attiva questa opzione, gli utenti possono pianificare webinar. Per impostazione predefinita, questa opzione è attivata. Se si vuole disattivare la registrazione alla riunione, impostare questo criterio su **Disattivato.**

> [!IMPORTANT]
> **La pianificazione privata delle riunioni** deve essere in esecuzione perché la registrazione della riunione funzioni. Per impostazione predefinita, questo criterio è attivato nell'Teams di amministrazione. Per gli studenti dei tenant dell'istruzione, questo criterio è disattivato per impostazione predefinita. Per altre informazioni su come abilitare la pianificazione privata delle riunioni per gli studenti, vedere Teams per l'istruzione [criteri e pacchetti di criteri.](policy-packages-edu.md)

### <a name="who-can-register"></a>Who può registrarsi

Se si seleziona **Tutti**, tutti gli utenti, inclusi gli utenti anonimi, possono registrarsi e partecipare ai webinar. Se si seleziona **Tutti nell'organizzazione,** solo gli utenti dell'organizzazione possono registrarsi per i webinar. Se la registrazione alla riunione è disattivata, questa opzione non sarà disponibile e nessuno potrà registrarsi per i webinar.

> [!NOTE]
> Il valore predefinito per Who **può essere registrato** è Tutti gli utenti **dell'organizzazione** nei tenant dell'istruzione. Per altre informazioni, vedere Teams per l'istruzione [guidata Criteri.](easy-policy-setup-edu.md)

### <a name="engagement-report"></a>Report impegno

Quando questa opzione è impostata, gli organizzatori possono visualizzare i report sugli utenti che hanno registrato e partecipato ai webinar che hanno configurato. Questo criterio è in base all'impostazione predefinita. Per altre informazioni, vedere [Criteri riunione in Teams - Report impegno.](meeting-policies-in-teams-general.md#engagement-report) Per informazioni sull'esperienza utente finale, vedere Visualizzare e [scaricare i report sulla partecipazione alla riunione.](https://support.microsoft.com/office/view-and-download-meeting-attendance-reports-in-teams-ae7cf170-530c-47d3-84c1-3aedac74d310?ui=en-US&#x26;rs=en-US&#x26;ad=US)

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>Consentire agli utenti di pianificare webinar con PowerShell

È possibile usare gli attributi seguenti all'interno Windows PowerShell cmdlet **Set-CsTeamsMeetingPolicy** per configurare i webinar in Teams.

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

Per altre informazioni sul cmdlet, vedere [Set-CsTeamsMeetingPolicy.](/powershell/module/skype/set-csteamsmeetingpolicy)

> [!NOTE]
> Prima di eseguire questi cmdlet, è necessario essere connessi a Microsoft Teams PowerShell. Per altre informazioni, vedere [Gestire Teams con Microsoft Teams PowerShell.](/microsoftteams/teams-powershell-managing-teams)

### <a name="allow-users-to-schedule-webinars"></a>Consentire agli utenti di pianificare webinar

È possibile limitare la registrazione solo agli utenti dell'organizzazione o aprirla a tutti gli utenti interni ed esterni al tenant. Per impostazione predefinita, **WhoCanRegister** è abilitato e impostato su **Tutti** per il criterio Globale **(impostazione** predefinita a livello di organizzazione). Se si vuole disattivare la registrazione alla riunione, impostare **AllowMeetingRegistration** su **False**.

> [!IMPORTANT]
> **AllowPrivateMeetingScheduling** deve essere impostato su **True** perché **AllowMeetingRegistration** funzioni.

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
> Se l'accesso anonimo è disattivato nelle impostazioni della riunione, gli utenti anonimi non possono partecipare ai webinar. Per altre informazioni e abilitare questa impostazione, vedere [Impostazioni riunione in Teams](meeting-settings-in-teams.md).

### <a name="collect-meeting-attendance"></a>Raccogliere la partecipazione alla riunione

Il **parametro AllowEngagementReport** consente di vedere chi ha registrato e partecipato ai webinar. Questo criterio è attivato per impostazione predefinita. Per disattivarlo, eseguire il comando seguente in PowerShell:

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Disabled
```

## <a name="configure-webinar-settings"></a>Configurare le impostazioni del webinar

Dopo aver abilitato l'ambiente per i webinar, non è necessaria alcuna ulteriore gestione dell'amministratore. I criteri controllano le opzioni da visualizzare per gli organizzatori del webinar.

## <a name="related-topics"></a>Argomenti correlati

- [Criteri riunione in Teams - Generale](meeting-policies-in-teams-general.md)
- [Documentazione di Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Teams per l'istruzione guidata Criteri di gruppo](easy-policy-setup-edu.md)
