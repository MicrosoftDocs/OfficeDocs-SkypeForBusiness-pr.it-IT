---
title: Usare PowerShell per gestire la connessione Turni a Blue Yonder Workforce Management
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come usare PowerShell per gestire la connessione Turni a Blue Yonder Workforce Management.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: e666117b31064697f9ef41299574935109015aba
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593660"
---
# <a name="use-powershell-to-manage-your-shifts-connection-to-blue-yonder-workforce-management"></a>Usare PowerShell per gestire la connessione Turni a Blue Yonder Workforce Management

## <a name="overview"></a>Panoramica

Il [connettore Microsoft Teams Turni per Blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) consente di integrare l'app Turni in Microsoft Teams con Blue Yonder Workforce Management (Blue Yonder WFM). Dopo aver configurato una connessione, i dipendenti in prima linea possono visualizzare e gestire facilmente le pianificazioni in Blue Yonder WFM dall'interno dei turni.

È possibile usare la [procedura guidata del connettore](shifts-connector-wizard.md) Turni nella interfaccia di amministrazione di Microsoft 365 [o in PowerShell](shifts-connector-blue-yonder-powershell-setup.md) per configurare una connessione. Dopo aver configurato una connessione, è possibile gestirla usando i [cmdlet di PowerShell del connettore Turni](#shifts-connector-cmdlets).

Questo articolo descrive come usare PowerShell per eseguire le operazioni seguenti:

- [Controllare lo stato di configurazione della connessione](#check-connection-setup-status)
- [Visualizzare una segnalazione errori per una connessione](#view-an-error-report-for-a-connection)
- [Risolvere gli errori di connessione](#resolve-connection-errors)
- [Modificare le impostazioni di connessione](#change-connection-settings)
- [Annullare il mapping di un team da una connessione e associarlo a un'altra connessione](#unmap-a-team-from-one-connection-and-map-it-to-another-connection)
- [Disabilitare la sincronizzazione per una connessione](#disable-sync-for-a-connection)

> [!NOTE]
> Questo articolo presuppone che sia già stata impostata una connessione a Blue Yonder WFM usando la procedura guidata o PowerShell.

## <a name="before-you-begin"></a>Prima di iniziare

[!INCLUDE [shifts-connector-admin-role](../../includes/shifts-connector-admin-role.md)]

## <a name="set-up-your-environment"></a>Configurare l'ambiente

> [!NOTE]
> Assicurarsi di seguire questa procedura per configurare l'ambiente prima di eseguire uno dei comandi o degli script descritti in questo articolo.

[!INCLUDE [shifts-connector-set-up-environment](../../includes/shifts-connector-set-up-environment.md)]

## <a name="check-connection-setup-status"></a>Controllare lo stato di configurazione della connessione
<a name="setup_status"> </a>

Per verificare lo stato della connessione impostata usando l'ID operazione ricevuto tramite posta elettronica:

1. [Configurare l'ambiente](#set-up-your-environment) (se non è già stato fatto).
1. Eseguire il comando seguente. Questo comando fornisce lo stato generale dei mapping del team per la connessione.

    ``` powershell
    Get-CsTeamsShiftsConnectionOperation -OperationId <YourOperationId>
    ```

Per altre informazioni, vedere [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation?view=teams-ps).

## <a name="view-an-error-report-for-a-connection"></a>Visualizzare una segnalazione errori per una connessione
<a name="error_report"> </a>

È possibile eseguire un report che mostra i dettagli dell'errore per una connessione. Il report elenca i mapping di team e utenti che hanno avuto esito positivo e negativo. Fornisce anche informazioni su eventuali problemi relativi agli account associati alla connessione.

1. [Configurare l'ambiente](#set-up-your-environment) (se non è già stato fatto).
1. Ottenere un elenco di segnalazioni errori per una connessione.

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. Per visualizzare una segnalazione errori specifica, eseguire il comando seguente:

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ErrorReportId <ErrorReportId>
    ```

Per altre informazioni, vedere [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport?view=teams-ps).

## <a name="resolve-connection-errors"></a>Risolvere gli errori di connessione

### <a name="user-mapping-errors"></a>Errori di mapping degli utenti

Gli errori di mapping degli utenti possono verificarsi se uno o più utenti di un sito WFM Blue Yonder non sono membri del team mappato in Teams. Per risolvere il problema, assicurarsi che gli utenti del team mappato corrispondano agli utenti del sito WFM Blue Yonder.

Per visualizzare i dettagli degli utenti non mappati [, configurare](#set-up-your-environment) l'ambiente (se non è già stato fatto) e quindi eseguire lo script seguente.

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

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

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

Gli errori di autorizzazione dell'account possono verificarsi se l'account di servizio WFM Blue Yonder o Microsoft 365 credenziali dell'account di sistema non sono corrette o non hanno le autorizzazioni necessarie.

Per modificare le credenziali dell'account del servizio WFM Blue Yonder o dell'account di sistema di Microsoft 365 per la connessione, è possibile eseguire il cmdlet [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps) o usare lo script [](#change-connection-settings) di PowerShell nella sezione Modificare le impostazioni di connessione di questo articolo.

## <a name="change-connection-settings"></a>Modificare le impostazioni di connessione
<a name="change_settings"> </a>

Usare questo script per modificare le impostazioni di connessione. Impostazioni che è possibile modificare includono l'account del servizio Blue Yonder WFM e la password, Microsoft 365 account di sistema, mapping del team e impostazioni di sincronizzazione.

Le impostazioni di sincronizzazione includono la frequenza di sincronizzazione (in minuti) e i dati di pianificazione sincronizzati tra Blue Yonder WFM e Turni. I dati di pianificazione sono definiti nei parametri seguenti, che è possibile visualizzare eseguendo [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps).

- Il **parametro enabledConnectorScenarios** definisce i dati sincronizzati da Blue Yonder WFM a Shifts. Le opzioni disponibili `Shift`sono `SwapRequest`, `UserShiftPreferences`, `OpenShift`, `OpenShiftRequest`, `TimeOff`, `TimeOffRequest`.
- Il **parametro enabledWfiScenarios** definisce i dati sincronizzati da Turni a Blue Yonder WFM. Le opzioni sono `SwapRequest`, `OpenShiftRequest`, `TimeOffRequest`, `UserShiftPreferences`.

    > [!NOTE]
    > Se si sceglie di non sincronizzare i turni aperti, le richieste di turni aperti, le richieste di scambio o le richieste di tempo libero tra Turni e Blue Yonder WFM, è necessario eseguire un altro passaggio per nascondere la funzionalità in Turni. Dopo aver eseguito questo script, assicurarsi di seguire i passaggi descritti nella sezione Disabilitare turni aperti, richieste di turni aperti [,](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) richieste di scambio e richieste di tempo libero più avanti in questo articolo.

> [!IMPORTANT]
> Per le impostazioni che non si vogliono modificare, è necessario immettere di nuovo le impostazioni originali quando viene richiesto dallo script.

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

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

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

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>Disabilitare i turni aperti, le richieste di turni aperti, le richieste di scambio e le richieste di tempo libero

> [!IMPORTANT]
> Seguire questa procedura solo se si è scelto di disabilitare turni aperti, richieste di turni aperti, richieste di scambio o richieste di fesa usando lo script nella sezione Modificare le impostazioni di connessione più indietro in questo articolo o usando il cmdlet [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps).[](#change-connection-settings) Il completamento di questo passaggio nasconde la funzionalità in Turni. Senza questo secondo passaggio, gli utenti potranno comunque vedere la funzionalità in Turni e riceveranno un messaggio di errore "Operazione non supportata" se provano a usarla.

Per nascondere turni aperti, richieste di scambio e richieste di tempo [libero in](/graph/api/resources/schedule?view=graph-rest-1.0) Turni, usare il tipo di risorsa pianificazione API Graph per impostare i parametri seguenti su per ogni team mappato a ```false``` un sito WFM Blue Yonder:

- Turni aperti: ```openShiftsEnabled```
- Richieste di scambio:  ```swapShiftsRequestsEnabled```
- Richieste di tempo libero: ```timeOffRequestsEnabled```

Per nascondere le richieste di turni aperti in Turni, passare a **Impostazioni in** Turni e quindi disattivare l'impostazione **Apri turni**.

## <a name="unmap-a-team-from-one-connection-and-map-it-to-another-connection"></a>Annullare il mapping di un team da una connessione e associarlo a un'altra connessione

> [!NOTE]
> L Microsoft 365 di sistema deve essere lo stesso per entrambe le connessioni. In caso contrario, viene visualizzato il messaggio di errore "Il profilo dell'attore designato non ha i privilegi di proprietà del team".

Per annullare il mapping di un team da una connessione e associarlo a un'altra connessione:

1. [Configurare l'ambiente](#set-up-your-environment) (se non è già stato fatto).
1. Visualizzare un elenco di tutti i mapping del team per una connessione.

    ```powershell
    Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. Rimuovere un mapping del team dalla connessione.

    ```powershell
    Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId>
    ```

1. Eseguire il mapping del team a un'altra connessione.

    ```powershell
    New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId> -WfmTeamId <SiteId> -TimeZone <TimeZone>
    ```

Per altre informazioni, vedere [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap?view=teams-ps), [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap?view=teams-ps) e [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap?view=teams-ps).

## <a name="disable-sync-for-a-connection"></a>Disabilitare la sincronizzazione per una connessione

Usare questo script per disabilitare la sincronizzazione per una connessione. Tenere presente che questo script non rimuove o elimina una connessione. Disattiva la sincronizzazione in modo che non siano sincronizzati dati tra Turni e Blue Yonder WFM per la connessione specificata.

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

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

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

## <a name="shifts-connector-cmdlets"></a>Cmdlet del connettore Shifts

Per assistenza con i cmdlet del connettore Shifts, cercare **CsTeamsShiftsConnection** nel riferimento Teams [cmdlet di PowerShell](/powershell/teams/intro?view=teams-ps). Ecco i collegamenti ad alcuni cmdlet di uso comune.

- [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation?view=teams-ps)
- [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance?view=teams-ps)
- [Get-CsTeamsShiftsConnectionInstance](/powershell/module/teams/get-csteamsshiftsconnectioninstance?view=teams-ps)
- [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps)
- [Remove-CsTeamsShiftsConnectionInstance](/powershell/module/teams/remove-csteamsshiftsconnectioninstance?view=teams-ps)
- [Test-CsTeamsShiftsConnectionValidate](/powershell/module/teams/test-csteamsshiftsconnectionvalidate?view=teams-ps)
- [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap?view=teams-ps)
- [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap?view=teams-ps)
- [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap?view=teams-ps)
- [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps)
- [Get-CsTeamsShiftsConnectionSyncResult](/powershell/module/teams/get-csteamsshiftsconnectionsyncresult?view=teams-ps)
- [Get-CsTeamsShiftsConnectionWfmUser](/powershell/module/teams/get-csteamsshiftsconnectionwfmuser?view=teams-ps)
- [Get-CsTeamsShiftsConnectionWfmTeam](/powershell/module/teams/get-csteamsshiftsconnectionwfmteam?view=teams-ps)
- [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport?view=teams-ps)
- [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord?view=teams-ps)

## <a name="related-articles"></a>Articoli correlati

- [Turni connettori](shifts-connectors.md)
- [Usare la procedura guidata connettore Turni per connettere Turni a Blue Yonder Workforce Management](shifts-connector-wizard.md)
- [Usare PowerShell per connettere Turni a Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md)
- [Gestire l'app Turni](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Panoramica di PowerShell per Teams](../../teams-powershell-overview.md)