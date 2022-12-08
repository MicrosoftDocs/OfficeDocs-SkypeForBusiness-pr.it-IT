---
title: Configurare webinar
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
- highpri
description: Informazioni su come gestire i criteri di registrazione di webinar e riunioni in Teams.
ms.openlocfilehash: 37983f8597b9e1a0ed511c2d767c503494447481
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2022
ms.locfileid: "69307581"
---
# <a name="set-up-webinars-in-microsoft-teams"></a>Configurare webinar in Microsoft Teams

> [!NOTE]
> Questo articolo descrive alcune funzionalità dei webinar che sono in anteprima e richiedono una licenza Di Teams Premium.

Microsoft offre ora una nuova esperienza di webinar. Questo articolo descrive come aggiornare le impostazioni per usare queste funzionalità.

Se si prevede di usare webinar, è consigliabile usare la nuova esperienza webinar.

La registrazione delle riunioni include la funzionalità di base del webinar, la possibilità di richiedere la registrazione per le riunioni e un report sulla partecipazione. Abilitando la nuova esperienza di webinar, è possibile utilizzare la registrazione della riunione e molte nuove funzionalità di webinar, ad esempio:

- Evento dedicato e pagina di registrazione per il webinar
- Co-organizzatori
- Bios del relatore nella pagina dell'evento
- Panoramica e gestione dello stato della registrazione

Per altre informazioni sulle nuove funzionalità disponibili per gli utenti finali, vedere [Introduzione ai webinar di Teams](https://support.microsoft.com/office/42f3f874-22dc-4289-b53f-bbc1a69013e3).

Se l'organizzazione ha abilitato la registrazione delle riunioni, tutti i webinar appena creati avranno la nuova esperienza. I webinar pianificati in precedenza utilizzeranno l'esperienza webinar precedente. La nuova esperienza usa TeamsEventsPolicy. Se i webinar sono disattivati, rimarranno disattivati durante l'esecuzione della nuova esperienza.

Attualmente, l'esperienza di base del webinar è controllata dalla registrazione delle riunioni utilizzando i criteri di riunione di Teams (Set-CsTeamsMeetingPolicy). In futuro, l'impostazione di registrazione della riunione non controllarà i webinar; i webinar stanno passando a essere controllati dal criterio Eventi di Teams (Set-CsTeamsEventsPolicy).

La nuova esperienza webinar è configurata in PowerShell. Ecco alcuni esempi su [come configurare la nuova esperienza di webinar](#set-up-new-webinar-experience).

Per altre informazioni sulle differenze tra riunioni, webinar ed eventi live, vedere [Riunioni, webinar ed eventi live](quick-start-meetings-live-events.md).

> [!IMPORTANT]
> Per consentire agli utenti di configurare webinar, è necessario configurare Elenchi Microsoft in SharePoint abilitando la creazione di elenchi personali per scopi di eDiscovery. Per altre informazioni, vedere [Controllare le impostazioni per Elenchi Microsoft](/sharepoint/control-lists).

## <a name="set-up-new-webinar-experience"></a>Configurare una nuova esperienza di webinar

È necessario usare PowerShell per configurare la nuova esperienza di webinar per l'organizzazione. La possibilità di configurare la nuova esperienza di webinar nell'interfaccia di amministrazione di Teams non è ancora disponibile.

La registrazione della riunione deve essere attivata per utilizzare la nuova esperienza del webinar.

### <a name="configure-the-new-webinar-experience-with-powershell"></a>Configurare la nuova esperienza webinar con PowerShell

Per configurare la nuova esperienza webinar, utilizzare gli attributi seguenti all'interno del cmdlet **Set-CsTeamsEventsPolicy** Windows PowerShell.

|Parametro|Impostazione predefinita|Descrizione|
|---------|-----------|---------------|
|AllowWebinar|Abilitata|Questa impostazione determina se un utente può creare webinar.|
|EventAccessType|Tutti|Questa impostazione determina quali utenti possono accedere alla pagina di registrazione dell'evento o al sito dell'evento da registrare, nonché al tipo di utente consentito di partecipare alle sessioni dell'evento.|

Prima di eseguire questi cmdlet, è necessario essere connessi a Microsoft PowerShell di Teams. Per altre informazioni, vedere [Gestire Teams con Microsoft PowerShell di Teams](/microsoftteams/teams-powershell-managing-teams).

1. Attivare la registrazione della riunione.

    ```powershell
    Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowMeetingRegistration $True
    ```

1. Attivare la nuova esperienza di webinar.

    ```powershell
    Set-CsTeamsEventsPolicy -Identity <policy name> -AllowWebinars Enabled
    ```

1. Configurare chi può registrarsi per webinar e riunioni.

    - **Consenti agli **_only_* _ utenti dell'organizzazione di registrarsi per webinar e meetings_*

        ```powershell
        Set-CsTeamsEventsPolicy -Identity <policy name> -EventAccessType EveryoneInCompanyExcludingGuests
        ```

    - **Consentire a tutti, inclusi gli utenti anonimi, di registrarsi per webinar e riunioni**

        ```powershell
        Set-CsTeamsEventsPolicy -Identity <policy name> -EventAccessType Everyone
        ```

> [!IMPORTANT]
> Se **gli utenti anonimi possono partecipare a una riunione** è disattivato nelle **impostazioni della riunione**, gli utenti anonimi non possono partecipare a webinar. Per altre informazioni e abilitare questa impostazione, vedere [Impostazioni riunione in Teams](meeting-settings-in-teams.md).

## <a name="configure-meeting-registration"></a>Configurare la registrazione della riunione

Se si desidera utilizzare webinar, la registrazione della riunione deve essere attivata.

È possibile usare l'interfaccia di amministrazione di Teams in **Criteri** > **riunione** per configurare la registrazione delle riunioni e i webinar.

### <a name="meeting-registration"></a>Registrazione riunione

Se si attiva **la registrazione delle riunioni**, gli utenti dell'organizzazione possono pianificare webinar e riunioni che richiedono la registrazione. Per impostazione predefinita, questa opzione è attivata. Se si desidera disattivare la registrazione delle riunioni e i webinar, impostare questo criterio su **Disattivato**.

**La pianificazione della riunione privata** deve essere attivata perché la registrazione della riunione funzioni. Altre informazioni sulla [pianificazione di riunioni private](meeting-policies-in-teams-general.md).

Per gli studenti nei tenant per istituti di istruzione, questo criterio è disattivato per impostazione predefinita. Per altre informazioni su come abilitare la pianificazione di riunioni private per gli studenti, vedere [Teams per l'istruzione criteri e pacchetti di criteri](policy-packages-edu.md).

#### <a name="who-can-register"></a>Chi può registrarsi

> [!NOTE]
> Questo criterio non si applica alla nuova esperienza di webinar. Per configurare chi può registrarsi per la nuova esperienza di webinar, usare `Set-CsTeamsEventsPolicy -EventAccessType`, come illustrato in [Configurare la nuova esperienza webinar con PowerShell](#configure-the-new-webinar-experience-with-powershell).

Questo criterio controlla quali utenti possono registrarsi e partecipare ai webinar solo con la registrazione delle riunioni. Questo criterio include due opzioni, che sono disponibili solo se la **registrazione riunione** è attivata. Per impostazione predefinita, **Chi può registrarsi** è impostato su **Tutti**.

Se si seleziona **Tutti**, tutti gli utenti, inclusi gli utenti anonimi, possono registrarsi e partecipare ai webinar. Se si seleziona **Tutti gli utenti dell'organizzazione**, solo gli utenti dell'organizzazione possono registrarsi per i webinar e parteciparvi. Se la registrazione alla riunione è disattivata, l'impostazione **Chi può registrarsi** non sarà disponibile e nessuno potrà registrarsi per i webinar.

Il valore predefinito per **Chi può registrarsi** è **Tutti gli utenti dell'organizzazione** nei tenant per istituti di istruzione. Per altre informazioni, vedere [Creazione guidata Criteri di Teams per l'istruzione](easy-policy-setup-edu.md).

## <a name="collect-webinar-and-meeting-registration-attendance"></a>Raccogliere la partecipazione a un webinar e alla registrazione delle riunioni

È possibile usare l'interfaccia di amministrazione di Teams in **Criteri** > **riunione** per attivare il **report sull'impegno**.

Quando questa opzione è attivata, gli organizzatori possono visualizzare i report degli utenti che hanno registrato e partecipato ai webinar o alle riunioni configurate. Questo criterio è attivato per impostazione predefinita. Per altre informazioni, vedere [Criteri delle riunioni in Teams - Report sul coinvolgimento](meeting-policies-in-teams-general.md#engagement-report). Per informazioni sull'esperienza utente finale, vedere [Visualizzare e scaricare report sulla partecipazione alle riunioni](https://support.microsoft.com/office/ae7cf170-530c-47d3-84c1-3aedac74d310).

In PowerShell è possibile usare il parametro **AllowEngagementReport** per attivare questa opzione. Questo criterio è attivato per impostazione predefinita. Per disattivarlo, eseguire il comando seguente in PowerShell:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowEngagementReport Disabled
```

Per altre informazioni sul cmdlet, vedere [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) .

## <a name="turn-off-webinars"></a>Disattivare i webinar

È possibile disattivare i webinar con PowerShell. In questo modo verranno disattivati la nuova esperienza di webinar e i webinar solo con registrazione della riunione.

Usare lo script di PowerShell seguente per disattivare i webinar:

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowMeetingRegistration $False
Set-CSTeamsEventsPolicy -Identity <policy name> -AllowWebinars Disabled
```

## <a name="related-topics"></a>Argomenti correlati

- [Criteri riunione in Teams - Generale](meeting-policies-in-teams-general.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Set-CsTeamsEventsPolicy](/powershell/module/teams/set-csteamseventspolicy)
