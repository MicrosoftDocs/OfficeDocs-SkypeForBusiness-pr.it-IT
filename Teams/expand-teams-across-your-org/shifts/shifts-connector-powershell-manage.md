---
title: Usare PowerShell per gestire la connessione di Turni alla gestione della forza lavoro Blue Yonder
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come usare PowerShell per gestire la connessione turni alla gestione della forza lavoro Blue Yonder.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: a102001c9c35b3d93467a9955329ce9d314532d0
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675368"
---
# <a name="use-powershell-to-manage-your-shifts-connection-to-blue-yonder-workforce-management"></a>Usare PowerShell per gestire la connessione di Turni alla gestione della forza lavoro Blue Yonder

## <a name="overview"></a>Panoramica

Il [connettore Microsoft Teams Turni per Blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) consente di integrare l'app Turni in Microsoft Teams con Blue Yonder Workforce Management (Blue Yonder WFM). Dopo aver configurato una connessione, i dipendenti in prima linea possono visualizzare e gestire facilmente le pianificazioni in Blue Yonder WFM dall'interno di Turni.

È possibile usare la [procedura guidata connettore Turni](shifts-connector-wizard.md) nel interfaccia di amministrazione di Microsoft 365 o [PowerShell](shifts-connector-blue-yonder-powershell-setup.md) per configurare una connessione. Dopo aver configurato una connessione, è possibile gestirla usando [i cmdlet di PowerShell del connettore Turni](#shifts-connector-cmdlets).

Questo articolo descrive come usare PowerShell per eseguire le operazioni seguenti:

- [Controllare lo stato di configurazione della connessione](#check-connection-setup-status)
- [Visualizzare una segnalazione errori per una connessione](#view-an-error-report-for-a-connection)
- [Risolvere gli errori di connessione](#resolve-connection-errors)
- [Modificare le impostazioni di connessione](#change-connection-settings)
- [Rimuovere il mapping di un team da una connessione e mapparlo a un'altra connessione](#unmap-a-team-from-one-connection-and-map-it-to-another-connection)
- [Disabilitare la sincronizzazione per una connessione](#disable-sync-for-a-connection)

> [!NOTE]
> Questo articolo presuppone che sia già stata configurata una connessione a Blue Yonder WFM, tramite la procedura guidata o PowerShell.

## <a name="before-you-begin"></a>Prima di iniziare

[!INCLUDE [shifts-connector-admin-role](../../includes/shifts-connector-admin-role.md)]

## <a name="set-up-your-environment"></a>Configurare l'ambiente

> [!NOTE]
> Assicurarsi di seguire questa procedura per configurare l'ambiente prima di eseguire uno dei comandi o degli script descritti in questo articolo.

[!INCLUDE [shifts-connector-set-up-environment](../../includes/shifts-connector-set-up-environment.md)]

7. Connessione a Teams.

    ```powershell
    Connect-MicrosoftTeams
    ```

    Quando richiesto, accedere con le credenziali di amministratore. È ora possibile eseguire gli script in questo articolo e i cmdlet del connettore Turni.

## <a name="check-connection-setup-status"></a>Controllare lo stato di configurazione della connessione

<a name="setup_status"> </a>

Per controllare lo stato della connessione configurata usando l'ID operazione ricevuto nella posta elettronica:

1. [Configurare l'ambiente](#set-up-your-environment) (se non è già stato fatto).
1. Eseguire il comando seguente. Questo comando fornisce lo stato generale dei mapping del team per la connessione.

    ``` powershell
    Get-CsTeamsShiftsConnectionOperation -OperationId <YourOperationId>
    ```

Per ulteriori informazioni, vedi [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation).

## <a name="view-an-error-report-for-a-connection"></a>Visualizzare una segnalazione errori per una connessione

<a name="error_report"> </a>

È possibile eseguire un report che mostra i dettagli degli errori per una connessione. Il report elenca i mapping di team e utenti che hanno avuto esito positivo e negativo. Fornisce inoltre informazioni su eventuali problemi relativi agli account associati alla connessione.

1. [Configurare l'ambiente](#set-up-your-environment) (se non è già stato fatto).
1. Ottenere un elenco di segnalazioni di errori per una connessione.

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. Per visualizzare un report degli errori specifico, eseguire il comando seguente:

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ErrorReportId <ErrorReportId>
    ```

Per ulteriori informazioni, vedi [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport).

## <a name="resolve-connection-errors"></a>Risolvere gli errori di connessione

### <a name="user-mapping-errors"></a>Errori di mapping dell'utente

Gli errori di mapping dell'utente possono verificarsi se uno o più utenti in un sito WFM Blue Yonder non sono membri del team mappato in Teams. Per risolvere il problema, assicurarsi che gli utenti del team mappato corrispondano agli utenti nel sito WFM Blue Yonder.

Per visualizzare i dettagli degli utenti non mappati, [configurare l'ambiente](#set-up-your-environment) ,se non è già stato fatto, quindi eseguire lo script seguente.

```powershell
#View sync errors script
Write-Host "View sync errors"
Start-Sleep 1

#Ensure Teams module is of version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#List connection instances available
Write-Host "Listing connection instances"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Get an instance
if ($InstanceList.Count -gt 0){
    $InstanceId = Read-Host -Prompt 'Input the instance ID that you want to retrieve user sync results from'
}
else {
    throw "Instance list is empty"
}

#Get a list of the mappings
Write-Host "Listing team mappings"
$mappings = Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId
write $mappings

#For each mapping, retrieve the failed mappings
ForEach ($mapping in $mappings){
    $teamsTeamId = $mapping.TeamId
    $wfmTeamId = $mapping.WfmTeamId
    Write-Host "Failed mapped users in the mapping of ${teamsTeamId} and ${wfmTeamId}:"
    $userSyncResult = Get-CsTeamsShiftsConnectionSyncResult -ConnectorInstanceId $InstanceId -TeamId $teamsTeamId
    Write-Host "Failed AAD users:"
    write $userSyncResult.FailedAadUser
    Write-Host "Failed WFM users:"
    write $userSyncResult.FailedWfmUser
}
```

### <a name="account-authorization-errors"></a>Errori di autorizzazione dell'account

Gli errori di autorizzazione dell'account possono verificarsi se l'account del servizio WFM Blue Yonder o Microsoft 365 credenziali dell'account di sistema non sono corrette o non hanno le autorizzazioni necessarie.

Per modificare l'account del servizio WFM Blue Yonder o Microsoft 365 credenziali dell'account di sistema per la connessione, è possibile eseguire il cmdlet [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance) o utilizzare lo script PowerShell nella sezione [Modificare le impostazioni di connessione](#change-connection-settings) di questo articolo.

## <a name="change-connection-settings"></a>Modificare le impostazioni di connessione
<a name="change_settings"> </a>

Usare questo script per modificare le impostazioni di connessione. Impostazioni modificabili includono l'account del servizio Blue Yonder WFM e la password, l'account di sistema Microsoft 365, i mapping del team e le impostazioni di sincronizzazione.

Le impostazioni di sincronizzazione includono la frequenza di sincronizzazione (in minuti) e i dati di pianificare sincronizzati tra WFM Blue Yonder e Turni. I dati della pianificazione sono definiti nei seguenti parametri, che è possibile visualizzare eseguendo [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector).

- Il parametro **enabledConnectorScenarios definisce i** dati sincronizzati da Blue Yonder WFM a Turni. Le opzioni sono `Shift`, `SwapRequest`, `UserShiftPreferences`, `OpenShift`, `OpenShiftRequest`, `TimeOff`, `TimeOffRequest`.
- Il parametro **enabledWfiScenarios definisce i** dati sincronizzati da Turni a Blue Yonder WFM. Le opzioni sono `SwapRequest`, `OpenShiftRequest`, `TimeOffRequest`, `UserShiftPreferences`.

    > [!NOTE]
    > Se si sceglie di non sincronizzare i turni aperti, le richieste di turno aperte, le richieste di scambio o le richieste di permesso tra Turni e Blue Yonder WFM, è necessario eseguire un altro passaggio per nascondere la funzionalità in Turni. Dopo aver eseguito questo script, assicurarsi di seguire i passaggi descritti nella sezione [Disabilitare turni aperti, richieste di turni aperti, richieste di scambio e richieste di permesso](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) più avanti in questo articolo.

> [!IMPORTANT]
> Per le impostazioni che non si desidera modificare, è necessario immettere di nuovo le impostazioni originali quando lo script lo richiede.

[Configurare l'ambiente](#set-up-your-environment) (se non è già stato fatto) e quindi eseguire lo script seguente.

```powershell
#Update connector instance and mapping script
Write-Host "Update connector instance and mapping"
Start-Sleep 1

#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#Connect to MS Graph
Connect-MgGraph -Scopes "User.Read.All","Group.ReadWrite.All"

#List connector types available (comment out if not implemented for preview)
Write-Host "Listing connector types available"
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$connectors = Get-CsTeamsShiftsConnectionConnector
write $connectors
$blueYonder = $connectors | where {$_.Id -match $BlueYonderId}

#List connection instances available
Write-Host "Listing connection instances available"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Prompt for the WFM username and password
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Get the instance ID
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$InstanceId = Read-Host -Prompt 'Input the instance ID that you want to update'
$Instance = Get-CsTeamsShiftsConnectionInstance -ConnectorInstanceId $InstanceId
$Etag = $Instance.etag

#Change sync setting
$designatorName = Read-Host -Prompt "Input designated actor's user name"
$designator = Get-MgUser -UserId $designatorName
$teamsUserId = $designator.Id
$UpdatedInstanceName = Read-Host -Prompt 'Input new connection instance name'
$updatedConnectorScenarioString = Read-Host -Prompt 'Input new enabled connector scenarios'
$updatedWfiScenarioString = Read-Host -Prompt 'Input new enabled WFI scenarios'
$Delimiters = ",", ".", ":", ";", " ", "`t"
$updatedConnectorScenario = $updatedConnectorScenarioString -Split {$Delimiters -contains $_}
$updatedConnectorScenario = $updatedConnectorScenario.Trim()
$updatedConnectorScenario = $updatedConnectorScenario.Split('',[System.StringSplitOptions]::RemoveEmptyEntries)
$updatedWfiScenario = $updatedWfiScenarioString -Split {$Delimiters -contains $_}
$updatedWfiScenario = $updatedWfiScenario.Trim()
$updatedWfiScenario = $updatedWfiScenario.Split('', [System.StringSplitOptions]::RemoveEmptyEntries)
$adminApiUrl = $Instance.ConnectorSpecificSettingAdminApiUrl
$cookieAuthUrl = $Instance.ConnectorSpecificSettingCookieAuthUrl
$essApiUrl = $Instance.ConnectorSpecificSettingEssApiUrl
$federatedAuthUrl = $Instance.ConnectorSpecificSettingFederatedAuthUrl
$retailWebApiUrl = $Instance.ConnectorSpecificSettingRetailWebApiUrl
$siteManagerUrl = $Instance.ConnectorSpecificSettingSiteManagerUrl
$syncFreq = Read-Host -Prompt 'Input new sync frequency'

#Read admin email list
[psobject[]]$AdminEmailList = @()
while ($true){
$AdminEmail = Read-Host -Prompt "Enter admin's email to receive error report"
$AdminEmailList += $AdminEmail
$title    = 'Adding another email'
$question = 'Would you like to add another admin email?'
$choices  = '&Yes', '&No'
$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}
$UpdatedInstance = Set-CsTeamsShiftsConnectionInstance -ConnectorId $BlueYonderId -ConnectorInstanceId $InstanceId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -DesignatedActorId $teamsUserId -EnabledConnectorScenario $updatedConnectorScenario -EnabledWfiScenario $updatedWfiScenario -Name $UpdatedInstanceName -SyncFrequencyInMin $syncFreq -IfMatch $Etag -ConnectorAdminEmail $AdminEmailList

#Get a list of the mappings
Write-Host "Listing mappings"
$TeamMaps = Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId
write $TeamMaps

#Modify a mapping
#Remove a mapping
Write-Host "Removing a mapping"
$TeamsTeamId = Read-Host -Prompt 'Input the Teams team ID that you want to unlink'
$WfmTeamId = Read-Host -Prompt 'Input the WFM team ID that you want to unlink'
Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId
Write-Host "Success"

#Add a mapping
Write-Host "Adding a mapping"
$TeamsTeamId = Read-Host -Prompt 'Input the Teams team ID that you want to link'
$WfmTeamId = Read-Host -Prompt 'Input the WFM team ID that you want to link'
New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId -TimeZone "America/Los_Angeles" -WfmTeamId $WfmTeamId
Write-Host "Success"
```

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>Disabilitare i turni aperti, le richieste di turni aperti, le richieste di scambio e le richieste di permesso

> [!IMPORTANT]
> Seguire questa procedura solo se si è scelto di disabilitare i turni aperti, le richieste di turno aperte, le richieste di scambio o le richieste di permesso utilizzando lo script nella sezione [Modificare le impostazioni di connessione](#change-connection-settings) più indietro in questo articolo o usando il cmdlet [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance) . Il completamento di questo passaggio nasconde la funzionalità in Turni. Senza questo secondo passaggio, gli utenti vedranno ancora la funzionalità in Turni e riceveranno un messaggio di errore "operazione non supportata" se provano a usarla.

Per nascondere i turni aperti, le richieste di scambio e le richieste di permesso in Turni, usare il [tipo di risorsa API Graph pianificare](/graph/api/resources/schedule) per impostare i parametri ```false``` seguenti per ogni team mappato a un sito WFM Blue Yonder:

- Aprire turni: ```openShiftsEnabled```
- Richieste di scambio:  ```swapShiftsRequestsEnabled```
- Richieste di permesso: ```timeOffRequestsEnabled```

Per nascondere le richieste di turni aperti in Turni, passare a **Impostazioni** in Turni e quindi disattivare l'impostazione **Apri turni**.

## <a name="unmap-a-team-from-one-connection-and-map-it-to-another-connection"></a>Rimuovere il mapping di un team da una connessione e mapparlo a un'altra connessione

> [!NOTE]
> L'account di sistema Microsoft 365 deve essere lo stesso per entrambe le connessioni. In caso contrario, verrà visualizzato il messaggio di errore "Questo profilo attore designato non ha privilegi di proprietà del team".

Se si vuole rimuovere il mapping di un team da una connessione e mapparlo a un'altra connessione:

1. [Configurare l'ambiente](#set-up-your-environment) (se non è già stato fatto).
1. Visualizzare un elenco di tutti i mapping del team per una connessione.

    ```powershell
    Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. Rimuovere un mapping del team dalla connessione.

    ```powershell
    Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId>
    ```

1. Associare il team a un'altra connessione.

    ```powershell
    New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId> -WfmTeamId <SiteId> -TimeZone <TimeZone>
    ```

Per ulteriori informazioni, vedi [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap), [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap) e [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap).

## <a name="disable-sync-for-a-connection"></a>Disabilitare la sincronizzazione per una connessione

Usare questo script per disabilitare la sincronizzazione per una connessione. Tenere presente che questo script non rimuove o elimina una connessione. La sincronizzazione viene disattivata in modo che non venga sincronizzata la sincronizzazione dei dati tra Turni e Blue Yonder WFM per la connessione specificata.

[Configurare l'ambiente](#set-up-your-environment) (se non è già stato fatto) e quindi eseguire lo script seguente.

```powershell
#Disable sync script
Write-Host "Disable sync"
#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#List connection instances available
Write-Host "Listing connection instances"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Get an instance
if ($InstanceList.Count -gt 0){
    $InstanceId = Read-Host -Prompt 'Input the instance ID that you want to disable sync'
    $Instance = Get-CsTeamsShiftsConnectionInstance -ConnectorInstanceId $InstanceId
    $Etag = $Instance.etag
    $InstanceName = $Instance.Name
    $DesignatedActorId = $Instance.designatedActorId
    $adminApiUrl = $Instance.ConnectorSpecificSettingAdminApiUrl
    $cookieAuthUrl = $Instance.ConnectorSpecificSettingCookieAuthUrl
    $essApiUrl = $Instance.ConnectorSpecificSettingEssApiUrl
    $federatedAuthUrl = $Instance.ConnectorSpecificSettingFederatedAuthUrl
    $retailWebApiUrl = $Instance.ConnectorSpecificSettingRetailWebApiUrl
    $siteManagerUrl = $Instance.ConnectorSpecificSettingSiteManagerUrl
    $ConnectorAdminEmail = $Instance.ConnectorAdminEmail
}
else {
    throw "Instance list is empty"
}

#Remove scenarios in the mapping
Write-Host "Disabling scenarios in the team mapping"
$UpdatedInstanceName = $InstanceName + " - Disabled"
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

$UpdatedInstance = Set-CsTeamsShiftsConnectionInstance -ConnectorId $BlueYonderId -ConnectorInstanceId $InstanceId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -DesignatedActorId $DesignatedActorId -EnabledConnectorScenario @() -EnabledWfiScenario @() -Name $UpdatedInstanceName -SyncFrequencyInMin 60 -IfMatch $Etag -ConnectorAdminEmail $ConnectorAdminEmail

if ($UpdatedInstance.Id -ne $null) {
    Write-Host "Success"
}
else {
    throw "Update instance failed"
}
```

## <a name="shifts-connector-cmdlets"></a>Cmdlet del connettore Turni

Per assistenza con i cmdlet del connettore Turni, cerca **CsTeamsShiftsConnection** nel [riferimento ai cmdlet di PowerShell per Teams](/powershell/teams/intro). Ecco i collegamenti ad alcuni cmdlet di uso comune.

- [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation)
- [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance)
- [Get-CsTeamsShiftsConnectionInstance](/powershell/module/teams/get-csteamsshiftsconnectioninstance)
- [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance)
- [Remove-CsTeamsShiftsConnectionInstance](/powershell/module/teams/remove-csteamsshiftsconnectioninstance)
- [Test-CsTeamsShiftsConnectionValidate](/powershell/module/teams/test-csteamsshiftsconnectionvalidate)
- [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap)
- [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap)
- [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap)
- [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector)
- [Get-CsTeamsShiftsConnectionSyncResult](/powershell/module/teams/get-csteamsshiftsconnectionsyncresult)
- [Get-CsTeamsShiftsConnectionWfmUser](/powershell/module/teams/get-csteamsshiftsconnectionwfmuser)
- [Get-CsTeamsShiftsConnectionWfmTeam](/powershell/module/teams/get-csteamsshiftsconnectionwfmteam)
- [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport)
- [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord)

## <a name="related-articles"></a>Articoli correlati

- [Turni connettori](shifts-connectors.md)
- [Usare la procedura guidata connettore Turni per connettere Turni alla gestione della forza lavoro Blue Yonder](shifts-connector-wizard.md)
- [Usare PowerShell per connettere Turni alla gestione della forza lavoro Blue Yonder](shifts-connector-blue-yonder-powershell-setup.md)
- [Gestire l'app Turni](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Panoramica di PowerShell per Teams](../../teams-powershell-overview.md)
