---
title: Esempio di script di PowerShell-export managers and its directs
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.reviewer: brandber
ms.service: msteams
audience: admin
description: Usa questo script di PowerShell per esportare un elenco di Manager e i loro dirigenti per l'organizzazione, in preparazione per la creazione di un team per ogni Manager con i loro dirigenti come membri del team.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 367bf1696e96c6f5190ecda42bbdbe06dba8c16f
ms.sourcegitcommit: cfaae3ecbf853766de788b4825a86e04f68868ca
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "42796207"
---
# <a name="powershell-script-sample---export-managers-and-their-directs"></a><span data-ttu-id="3e65c-103">Esempio di script di PowerShell-export managers and its directs</span><span class="sxs-lookup"><span data-stu-id="3e65c-103">PowerShell script sample - Export managers and their directs</span></span>

<span data-ttu-id="3e65c-104">Usa questo script di PowerShell per esportare un elenco di Manager e i loro dirigenti per l'organizzazione, in preparazione per la creazione di un team di Manager di persone per ogni Manager con i loro dirigenti come membri del team.</span><span class="sxs-lookup"><span data-stu-id="3e65c-104">Use this PowerShell script to export a list of managers and their directs for your organization, in preparation for creating a people manager team for each manager with their directs as team members.</span></span>

<span data-ttu-id="3e65c-105">Per informazioni su questo script di PowerShell, vedere [creare team di People Manager](../create-manager-directs-teams.md).</span><span class="sxs-lookup"><span data-stu-id="3e65c-105">To learn about this PowerShell script, read [Create people manager teams](../create-manager-directs-teams.md).</span></span>

<span data-ttu-id="3e65c-106">Se non si ha familiarità con PowerShell e si ha bisogno di assistenza per iniziare, vedere [Panoramica di Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span><span class="sxs-lookup"><span data-stu-id="3e65c-106">If you're new to PowerShell and need help getting started, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span></span>


## <a name="export-managers-script"></a><span data-ttu-id="3e65c-107">Script di Export-Manager</span><span class="sxs-lookup"><span data-stu-id="3e65c-107">Export-Managers script</span></span>

```powershell
<# 
.SYNOPSIS 
  Name: Export-ManagersDirectsFromAAD.ps1 
  The purpose of this sample script is to build a list of managers and direct reports to use with the New-TeamsFromManagers.ps1 to create a team for each people manager and their directs.
   
.DESCRIPTION 
 This sample script create new Teams based on the tab delimited .txt file you provide of managers and direct reports. It assumes that DisplayName is not null.
 
.NOTES 
  &copy; 2020 Microsoft Corporation. All rights reserved. This document is provided 
    "as-is." Information and views expressed in this document, including URL and 
    other Internet Web site references, may change without notice.
 
.EXAMPLE 
  Export-ManagersDirectsFromAAD.ps1
#> 

#Also create a type that validated the users licenses to ease the create-team burden
#also add checks to see if the types are appropriately in place.

#region Configurable Inputs
$OutputFile = "ExportedManagersDirects.txt"
#endregion

#region Data Model
class DirectReport {
    [string] $UserPrincipalName
}
class Manager {
    [ValidateNotNullOrEmpty()] [string] $UserPrincipalName
    [string] $DisplayName
    [System.Collections.ObjectModel.Collection[DirectReport]]$DirectReports

    Manager (){
        $this.DirectReports = New-Object -TypeName System.Collections.ObjectModel.Collection["DirectReport"]
    }
}
#endregion

#region Helper Functions
Function Get-TimeStamp {
    return "[{0:MM/dd/yy} {0:HH:mm:ss}]" -f (Get-Date)
}
#endregion

#region Script Execution
#Step 1: Retrieve AAD users - attribute filtering off DirectReport cannot be applied
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Starting to retrieve ALL Azure AD users."
$AllAADUsers = Get-AzureADUser -All $true -Filter "UserType eq 'Member' and AccountEnabled eq true"
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Retriving Azure AD Users Complete.. `n"

#Step 2: Iterate through users, identify Managers and Directs
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Starting to Retrieve Directs Reports"
$Managers = New-Object -TypeName System.Collections.ObjectModel.Collection["Manager"]
foreach ($user in $AllAADUsers) {
    $directs = Get-AzureADUserDirectReport -ObjectId $user.UserPrincipalName
        if ($null -ne $directs) {
            if ($user.DisplayName -ne "") {
                $manager = New-Object -TypeName Manager
                $manager.UserPrincipalName = $user.UserPrincipalName
                $manager.DisplayName = $user.DisplayName

                foreach ($direct in $directs) {
                    $directReport = New-Object -TypeName DirectReport
                    $directReport.UserPrincipalName = $direct.UserPrincipalName
                    $manager.DirectReports.Add($directReport)
                }
                $Managers.Add($manager)
                
            }
        Write-Host "$(Get-Timestamp) Info: Added Manager: $($manager.UserPrincipalName)"
        $i++
    }
}
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Retriving Direct Reports Complete.. `n"

#Step 3: Output in tab delimited .txt format
$output = New-Object -TypeName System.Collections.ObjectModel.Collection["String"]
$header = "Name`tDisplayName`tDirects"
$output.Add($header)

foreach ($manager in $Managers) {
    [string] $directs = ""
    foreach ($direct in $manager.DirectReports)
    {
        $directs += $direct.UserPrincipalName + ','
    }
    $directs = $directs.Substring(0,$directs.Length-1)
    $row = "$($manager.UserPrincipalName)`t$($manager.DisplayName)`t$($directs)"
    $output.Add($row) 
}

#If Output File already exists from a previous run, it will be replaced.
$testPath = Test-Path .\$($OutputFile)
if ($testPath) {
    Remove-Item .\$($OutputFile)
}

foreach ($line in $output) {
    $line | Out-File -FilePath .\$($OutputFile) -Append
}
Write-Host -ForegroundColor Green "$(Get-Timestamp) Exported tab delimited output to $($OutputFile). `n"
#endregion



```

