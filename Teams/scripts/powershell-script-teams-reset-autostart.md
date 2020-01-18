---
title: Esempio di script di PowerShell-reimpostare l'impostazione autostart in teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: Usa questo script di PowerShell per reimpostare l'impostazione di avvio manuale in teams per ogni singolo utente.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 789b187dccb0cc654e3b8ad771b56627d58057a8
ms.sourcegitcommit: 416a2d404a2ea15b484cd7579035e7f2282ac2cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/18/2020
ms.locfileid: "41233334"
---
# <a name="powershell-script-sample---reset-the-autostart-setting-in-teams"></a><span data-ttu-id="1bbd0-103">Esempio di script di PowerShell-reimpostare l'impostazione autostart in teams</span><span class="sxs-lookup"><span data-stu-id="1bbd0-103">PowerShell script sample - Reset the autostart setting in Teams</span></span>

<span data-ttu-id="1bbd0-104">Usa questo script per reimpostare l'impostazione di avvio manuale dei team per ogni singolo utente.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-104">Use this script to reset the Teams autostart setting on a per-user basis.</span></span> <span data-ttu-id="1bbd0-105">Include tutti i valori impostati dall'utente o dall'app teams.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-105">This includes any values set by the user or the Teams app.</span></span> <span data-ttu-id="1bbd0-106">Per impostazione predefinita, teams avvia automaticamente quando un utente accede al proprio computer dopo l'installazione.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-106">By default, Teams automatically starts when a user logs in to their computer after it's installed.</span></span>

<span data-ttu-id="1bbd0-107">Se i team sono già stati distribuiti e si vuole impostare l'impostazione [Impedisci l'avvio automatico di Microsoft teams dopo l'installazione di criteri di gruppo](../msi-deployment.md#use-group-policy-recommended) per disabilitare l'autostart di teams, è necessario prima di tutto impostare i criteri di gruppo sul valore desiderato e quindi eseguire questo script.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-107">If you've already deployed Teams and want to set the [Prevent Microsoft Teams from starting automatically after installation Group Policy setting](../msi-deployment.md#use-group-policy-recommended) to disable Teams autostart, you'll need to first set the Group Policy setting to the value you want, and then run this script.</span></span>

<span data-ttu-id="1bbd0-108">Dopo l'avvio di teams per un utente, le impostazioni di autostart non possono essere disattivate tramite criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="1bbd0-108">After Teams is started for a user, the autostart settings can't be disabled by using Group Policy.</span></span>

## <a name="sample-script"></a><span data-ttu-id="1bbd0-109">Script di esempio</span><span class="sxs-lookup"><span data-stu-id="1bbd0-109">Sample script</span></span>

````powershell
<#
.SYNOPSIS
This script allows you to reset all autostart settings to the default settings for Teams.
.DESCRIPTION
If you want to use the "Prevent Microsoft Teams from starting automatically after installation"
Group Policy setting, make sure you first set the Group Policy setting to the value you want 
before you run this script.
#>

$ErrorActionPreference = "Stop"

$TeamsDesktopConfigJsonPath = [System.IO.Path]::Combine($env:APPDATA, 'Microsoft', 'Teams', 'desktop-config.json')

$TeamsUpdatePath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams', 'Update.exe')

Function Test-RegistryValue {
    param(
        [Alias("PSPath")]
        [Parameter(Position = 0, Mandatory = $true, ValueFromPipeline = $true, ValueFromPipelineByPropertyName = $true)]
        [String]$Path
        ,
        [Parameter(Position = 1, Mandatory = $true)]
        [String]$Name
    ) 

    process {
        if (Test-Path $Path) {
            $Key = Get-Item -LiteralPath $Path
            if ($null -ne $Key.GetValue($Name, $null)) {
                $true
            } else {
                $false
            }
        } else {
            $false
        }
    }
}

Function Test-Remove-RegistryValue {
    param (
        [Alias("PSPath")]
        [Parameter(Position = 0, Mandatory = $true, ValueFromPipeline = $true, ValueFromPipelineByPropertyName = $true)]
        [String]$Path
        ,
        [Parameter(Position = 1, Mandatory = $true)]
        [String]$Name
    )

    process {
        if (Test-RegistryValue -Path $Path -Name $Name) {
            Write-Host "Removing registry key $Path\$Name"
            Remove-ItemProperty -Path $Path -Name $Name
        }
    }
}

# when determining whether Teams should be auto-started we are checking three flags
Write-Host "Removing Auto-Start-related artifacts"

# 0. Close Teams, if running
$teamsProc = Get-Process -name Teams -ErrorAction SilentlyContinue
if ($null -ne $teamsProc) {
    Write-Host  "Stopping Microsoft Teams..."
    Stop-Process -Name Teams -Force
    # wait some time
    Start-Sleep 5
} else {
    Write-Host  "No running Teams process found"
}

# 1. Check that Teams process isn't still running
$teamsProc = Get-Process -name Teams -ErrorAction SilentlyContinue

if($null -eq $teamsProc) {
    # 2. remove HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\LoggedInOnce registry key
    Test-Remove-RegistryValue -Path "HKCU:\Software\Microsoft\Office\Teams" -Name "LoggedInOnce"

    # 3. remove HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\HomeUserUpn registry key
    Test-Remove-RegistryValue -Path "HKCU:\Software\Microsoft\Office\Teams" -Name "HomeUserUpn"

    # 4. remove HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\DeadEnd registry key
    Test-Remove-RegistryValue -Path "HKCU:\Software\Microsoft\Office\Teams" -Name "DeadEnd"

    # 5. remove HKCU:\Software\Microsoft\Office\Outlook\Addins\TeamsAddin.FastConnect registry key
    Remove-Item -Path "HKCU:\Software\Microsoft\Office\Outlook\Addins\TeamsAddin.FastConnect" -ErrorAction SilentlyContinue

    # 6. restore HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run\com.squirrel.Teams.Teams
    if (!(Test-RegistryValue -Path "HKCU:\Software\Microsoft\Windows\CurrentVersion\Run" -Name "com.squirrel.Teams.Teams")) {
        Write-Host "Restoring registry key HKCU\Software\Microsoft\Windows\CurrentVersion\Run\com.squirrel.Teams.Teams"
        Set-ItemProperty -Path "HKCU:\Software\Microsoft\Windows\CurrentVersion\Run" -Name "com.squirrel.Teams.Teams" -Value "$TeamsUpdatePath --processStart ""Teams.exe"" --process-start-args ""--system-initiated"""
    }

    # 7. We are checking whether there are entries 'isLoggedOut' and 'openAtLogin' in the desktop-config.json file
    if (Test-Path -Path $TeamsDesktopConfigJsonPath) {
        Write-Host "Changing entries 'guestTenantId', 'isLoggedOut' and 'openAtLogin' in the desktop-config.json, if exist"

        # open desktop-config.json file
        $desktopConfigFile = Get-Content -path $TeamsDesktopConfigJsonPath -Raw | ConvertFrom-Json
        $desktopConfigFile.PSObject.Properties.Remove("guestTenantId")
        $desktopConfigFile.PSObject.Properties.Remove("isLoggedOut")
        try {
            $desktopConfigFile.appPreferenceSettings.openAtLogin = $true
        } catch {
            Write-Host  "openAtLogin JSON element doesn't exist"
        }
        $desktopConfigFile | ConvertTo-Json -Compress | Set-Content -Path $TeamsDesktopConfigJsonPath -Force
    }
} else {
    Write-Host  "Teams process is still running, aborting script execution"
}
````

## <a name="related-topics"></a><span data-ttu-id="1bbd0-110">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="1bbd0-110">Related topics</span></span>

- [<span data-ttu-id="1bbd0-111">Installare Teams con MSI</span><span class="sxs-lookup"><span data-stu-id="1bbd0-111">Install Teams using MSI</span></span>](../msi-deployment.md)
- [<span data-ttu-id="1bbd0-112">Distribuire Team con Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="1bbd0-112">Deploy Teams with Office 365 ProPlus</span></span>](https://docs.microsoft.com/deployoffice/teams-install)
