---
title: Esempio di script di PowerShell - pulizia Teams distribuzione
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: Usare questo script di PowerShell per disinstallare Teams e rimuovere la Teams per gli utenti.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af5e5fe4c52030add0e60be0cedb5edc54b9c833
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837498"
---
# <a name="powershell-script-sample---teams-deployment-clean-up"></a>Esempio di script di PowerShell : Teams pulizia della distribuzione

Usare questo script per rimuovere Teams. Questo script disinstalla Teams e rimuove la Teams per un utente. Eseguire questo script per ogni profilo utente in cui Teams è stato installato in un computer.


## <a name="sample-script"></a>Script di esempio

````powershell
<#
.SYNOPSIS
This script uninstalls the Teams app and removes the Teams directory for a user.
.DESCRIPTION
Use this script to remove and clear the Teams app from a computer. Run this PowerShell script for each user profile in which Teams was installed on the computer. After you run this script for all user profiles, redeploy Teams.
#>

$TeamsPath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams')
$TeamsUpdateExePath = [System.IO.Path]::Combine($TeamsPath, 'Update.exe')

try
{
    if ([System.IO.File]::Exists($TeamsUpdateExePath)) {
        Write-Host "Uninstalling Teams process"

        # Uninstall app
        $proc = Start-Process $TeamsUpdateExePath "-uninstall -s" -PassThru
        $proc.WaitForExit()
    }
    Write-Host "Deleting Teams directory"
    Remove-Item –path $TeamsPath -recurse
}
catch
{
    Write-Output "Uninstall failed with exception $_.exception.message"
    exit /b 1
}

````

## <a name="related-topics"></a>Argomenti correlati

- [Installare Microsoft Teams usando Microsoft Endpoint Configuration Manager](../msi-deployment.md)
- [Distribuire Teams con Microsoft 365 Apps](/deployoffice/teams-install)
