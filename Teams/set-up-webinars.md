---
title: Configurare webinar in Microsoft Teams
ms.author: mabond
author: mkbond007
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
description: Informazioni su come gestire i criteri del Webinar per le riunioni di Teams.
ms.openlocfilehash: 26863b26f960b50d81fa1d98090c3616d5b492a7
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706483"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>Configurare webinar in Microsoft Teams

Questo articolo illustra come configurare l'organizzazione per ospitare webinar.

## <a name="what-are-webinars"></a>Cosa sono i webinar?

I webinar sono riunioni strutturate in cui relatori e partecipanti hanno ruoli chiari, spesso usati per scopi di formazione o scenari di vendita e di marketing di lead generation.

Dopo aver configurato webinar nell'organizzazione, gli utenti possono pianificare webinar e aprire la registrazione ai partecipanti. A differenza delle riunioni tradizionali che includono molte discussioni e assegnazioni di attività, i webinar sono pensati per presentazioni interattive e forniscono strumenti per l'analisi dei partecipanti.

> [!IMPORTANT]
> Per consentire agli utenti di configurare webinar, è necessario configurare Elenchi Microsoft in SharePoint abilitando la creazione di elenchi personali. Per altre informazioni, vedere [Controllare le impostazioni per Elenchi Microsoft](/sharepoint/control-lists).

## <a name="allow-users-to-schedule-webinars-in-the-teams-admin-center"></a>Consentire agli utenti di pianificare webinar nell'interfaccia di amministrazione di Teams

È possibile usare l'interfaccia di amministrazione di Teams per configurare webinar per l'organizzazione. I criteri per configurare i webinar sono disponibili nell'interfaccia di amministrazione di Teams in **Criteri riunione** > .

### <a name="meeting-registration"></a>Registrazione riunione

Se si attiva questa opzione, gli utenti possono pianificare webinar. Per impostazione predefinita, questa opzione è attivata. Se si vuole disattivare la registrazione della riunione, impostare questo criterio su **Disattivato**.

> [!IMPORTANT]
> **La pianificazione della riunione privata** deve essere attivata perché la registrazione della riunione funzioni. Per impostazione predefinita, questo criterio è attivato nell'interfaccia di amministrazione di Teams. Per gli studenti nei tenant per istituti di istruzione, questo criterio è disattivato per impostazione predefinita. Per altre informazioni su come abilitare la pianificazione di riunioni private per gli studenti, vedere [Teams per l'istruzione criteri e pacchetti di criteri](policy-packages-edu.md).

### <a name="who-can-register"></a>Chi può registrarsi

Se si seleziona **Tutti**, tutti gli utenti, inclusi gli utenti anonimi, possono registrarsi e partecipare ai webinar. Se si seleziona **Tutti gli utenti dell'organizzazione**, solo gli utenti dell'organizzazione possono registrarsi per i webinar. Se la registrazione della riunione è disattivata, questa opzione non sarà disponibile e nessuno potrà registrarsi per i webinar.

> [!NOTE]
> Il valore predefinito per **Chi può registrarsi** è **Tutti gli utenti dell'organizzazione** nei tenant per istituti di istruzione. Per altre informazioni, vedere [Creazione guidata Criteri di Teams per l'istruzione](easy-policy-setup-edu.md).

### <a name="engagement-report"></a>Report sull'impegno

Quando questa opzione è attivata, gli organizzatori possono vedere i report degli utenti che si sono registrati e che hanno partecipato ai webinar configurati. Questo criterio è attivato per impostazione predefinita. Per altre informazioni, vedere [Criteri delle riunioni in Teams - Report sul coinvolgimento](meeting-policies-in-teams-general.md#engagement-report). Per informazioni sull'esperienza utente finale, vedere [Visualizzare e scaricare report sulla partecipazione alle riunioni](https://support.microsoft.com/office/view-and-download-meeting-attendance-reports-in-teams-ae7cf170-530c-47d3-84c1-3aedac74d310?ui=en-US&#x26;rs=en-US&#x26;ad=US).

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>Consentire agli utenti di pianificare webinar con PowerShell

È possibile utilizzare gli attributi seguenti all'interno del cmdlet **Set-CsTeamsMeetingPolicy Windows PowerShell per configurare** i webinar in Teams.

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

Per altre informazioni sul cmdlet, vedere [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) .

> [!NOTE]
> Prima di eseguire questi cmdlet, è necessario essere connessi a PowerShell di Microsoft Teams. Per altre informazioni, vedere [Gestire Teams con Microsoft Teams PowerShell](/microsoftteams/teams-powershell-managing-teams).

### <a name="allow-users-to-schedule-webinars"></a>Consentire agli utenti di pianificare webinar

È possibile limitare la registrazione agli utenti solo nell'organizzazione o aprirla a tutti gli utenti sia all'interno che all'esterno del tenant. Per impostazione predefinita, **WhoCanRegister** è abilitato e impostato su **Tutti** per il criterio **globale (impostazione predefinita a livello di organizzazione** ). Se si vuole disattivare la registrazione della riunione, impostare **AllowMeetingRegistration** **su False**.

> [!IMPORTANT]
> **AllowPrivateMeetingScheduling** deve essere impostato su **True** per il funzionamento di **AllowMeetingRegistration** .

1. Attivare la registrazione della riunione

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```

2. Attivare la pianificazione delle riunioni private

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

3. Configurare chi può registrarsi per i webinar

**Consentire *solo* agli utenti dell'organizzazione di registrarsi per i webinar**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

**Per consentire a chiunque, inclusi gli utenti anonimi, di registrarsi per i webinar, eseguire:**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!CAUTION]
> Se la partecipazione anonima è disattivata nelle impostazioni della riunione, gli utenti anonimi non possono partecipare a webinar. Per altre informazioni e abilitare questa impostazione, vedere [Impostazioni riunione in Teams](meeting-settings-in-teams.md).

### <a name="collect-meeting-attendance"></a>Raccogliere la partecipazione alle riunioni

Il parametro **AllowEngagementReport** consente di vedere chi ha registrato e frequentato i webinar. Questo criterio è attivato per impostazione predefinita. Per disattivarlo, eseguire il comando seguente in PowerShell:

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Disabled
```

## <a name="configure-webinar-settings"></a>Configurare le impostazioni del webinar

Dopo aver abilitato l'ambiente per i webinar, non è necessaria alcuna ulteriore gestione amministrativa. Il criterio controlla le opzioni visualizzate per gli organizzatori del webinar.

## <a name="related-topics"></a>Argomenti correlati

- [Criteri riunione in Teams - Generale](meeting-policies-in-teams-general.md)
- [Documentazione di Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Creazione guidata Criteri di Teams per l'istruzione](easy-policy-setup-edu.md)
