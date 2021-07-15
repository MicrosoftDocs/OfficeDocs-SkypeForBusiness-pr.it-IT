---
title: Esempio di script di PowerShell - pulizia Teams distribuzione
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: Usare questo script di PowerShell per disinstallare Teams e rimuovere la Teams per gli utenti.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 96f3c7f6d9d9fa52edd09b7ecf690f43d6730367
ms.sourcegitcommit: ede53639ac782eb51d7560fc41fb01ec6979dfd9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53428192"
---
# <a name="powershell-script-sample---teams-deployment-clean-up"></a><span data-ttu-id="e1dcd-103">Esempio di script di PowerShell : Teams pulizia della distribuzione</span><span class="sxs-lookup"><span data-stu-id="e1dcd-103">PowerShell script sample - Teams deployment clean up</span></span>

<span data-ttu-id="e1dcd-104">Usare questo script per rimuovere Teams.</span><span class="sxs-lookup"><span data-stu-id="e1dcd-104">Use this script to remove Teams.</span></span> <span data-ttu-id="e1dcd-105">Questo script disinstalla Teams e rimuove la cartella Teams per un utente.</span><span class="sxs-lookup"><span data-stu-id="e1dcd-105">This script uninstalls Teams and removes the Teams folder for a user.</span></span> <span data-ttu-id="e1dcd-106">Eseguire questo script per ogni profilo utente in cui Teams è stato installato in un computer.</span><span class="sxs-lookup"><span data-stu-id="e1dcd-106">Run this script for each user profile in which Teams was installed on a computer.</span></span>


## <a name="sample-script"></a><span data-ttu-id="e1dcd-107">Script di esempio</span><span class="sxs-lookup"><span data-stu-id="e1dcd-107">Sample script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="e1dcd-108">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e1dcd-108">Related topics</span></span>

- [<span data-ttu-id="e1dcd-109">Installare Microsoft Teams usando Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e1dcd-109">Install Microsoft Teams using Microsoft Endpoint Configuration Manager</span></span>](../msi-deployment.md)
- [<span data-ttu-id="e1dcd-110">Distribuire Teams con Microsoft 365 Apps</span><span class="sxs-lookup"><span data-stu-id="e1dcd-110">Deploy Teams with Microsoft 365 Apps</span></span>](/deployoffice/teams-install)
