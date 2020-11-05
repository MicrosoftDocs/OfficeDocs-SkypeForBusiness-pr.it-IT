---
title: Esempio di script di PowerShell-pulizia della distribuzione di Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: Usa questo script di PowerShell per disinstallare teams e rimuovere la cartella teams per gli utenti.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7245e3cfee88beb51389f20bc99bbcc312f55b0
ms.sourcegitcommit: a1524afb546fde9844f53390fab85e7073da8cb2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "48778912"
---
# <a name="powershell-script-sample---teams-deployment-clean-up"></a><span data-ttu-id="77246-103">Esempio di script di PowerShell-pulizia della distribuzione Teams</span><span class="sxs-lookup"><span data-stu-id="77246-103">PowerShell script sample - Teams deployment clean up</span></span>

<span data-ttu-id="77246-104">Usa questo script per rimuovere teams.</span><span class="sxs-lookup"><span data-stu-id="77246-104">Use this script to remove Teams.</span></span> <span data-ttu-id="77246-105">Questo script Disinstalla teams e rimuove la cartella teams per un utente.</span><span class="sxs-lookup"><span data-stu-id="77246-105">This script uninstalls Teams and removes the Teams folder for a user.</span></span> <span data-ttu-id="77246-106">Esegui questo script per ogni profilo utente in cui i team sono stati installati in un computer.</span><span class="sxs-lookup"><span data-stu-id="77246-106">Run this script for each user profile in which Teams was installed on a computer.</span></span>


## <a name="sample-script"></a><span data-ttu-id="77246-107">Script di esempio</span><span class="sxs-lookup"><span data-stu-id="77246-107">Sample script</span></span>

````powershell
<#
.SYNOPSIS
This script uninstalls the Teams app and removes the Teams directory for a user.
.DESCRIPTION
Use this script to remove and clear the Teams app from a computer. Run this PowerShell script for each user profile in which Teams was installed on the computer. After you run this script for all user profiles, redeploy Teams.
#>

$TeamsPath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams')
$TeamsUpdateExePath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams', 'Update.exe')

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

## <a name="related-topics"></a><span data-ttu-id="77246-108">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="77246-108">Related topics</span></span>

- [<span data-ttu-id="77246-109">Installare Microsoft Teams usando Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="77246-109">Install Microsoft Teams using Microsoft Endpoint Configuration Manager</span></span>](../msi-deployment.md)
- [<span data-ttu-id="77246-110">Distribuire Team con le app Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="77246-110">Deploy Teams with Microsoft 365 Apps</span></span>](https://docs.microsoft.com/deployoffice/teams-install)