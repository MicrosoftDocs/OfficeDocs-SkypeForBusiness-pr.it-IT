---
title: 'Esempio di script di PowerShell: creare e assegnare un criterio di messaggistica'
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: Usa questo script di PowerShell per creare un criterio di messaggistica in teams e assegnarlo agli utenti dell'organizzazione.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c1dbd4dfa470f8ed02c83e48603dc2647fdc90b3
ms.sourcegitcommit: 4ee9835282e1440d03abc6dbcd172bc20c5b3015
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2020
ms.locfileid: "43096981"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="903c6-103">Esempio di script di PowerShell: creare e assegnare un criterio di messaggistica</span><span class="sxs-lookup"><span data-stu-id="903c6-103">PowerShell script sample - Create and assign a messaging policy</span></span>

<span data-ttu-id="903c6-104">Usa questo script di PowerShell per creare criteri di messaggistica in Microsoft teams e assegnarlo agli utenti.</span><span class="sxs-lookup"><span data-stu-id="903c6-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="903c6-105">Per altre informazioni sull'uso di questo script di PowerShell, vedere [Quick Start-teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span><span class="sxs-lookup"><span data-stu-id="903c6-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="903c6-106">Se non si ha familiarità con PowerShell e si ha bisogno di assistenza per iniziare, vedere [Panoramica di Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span><span class="sxs-lookup"><span data-stu-id="903c6-106">If you're new to PowerShell and need help getting started, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span></span>


## <a name="before-you-start"></a><span data-ttu-id="903c6-107">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="903c6-107">Before you start</span></span>
<span data-ttu-id="903c6-108">Scaricare e installare il [modulo di Skype for Business Online Connector](https://www.microsoft.com/download/details.aspx?id=39366)e quindi riavviare il computer, se richiesto.</span><span class="sxs-lookup"><span data-stu-id="903c6-108">Download and install the [Skype for Business Online Connector module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer if prompted.</span></span>

<span data-ttu-id="903c6-109">Per ulteriori informazioni, vedere [gestire Skype for business online con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell) .</span><span class="sxs-lookup"><span data-stu-id="903c6-109">View [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell) for more.</span></span>


## <a name="sample-script"></a><span data-ttu-id="903c6-110">Script di esempio</span><span class="sxs-lookup"><span data-stu-id="903c6-110">Sample script</span></span>

```powershell
<#
.SYNOPSIS
This script creates a messaging policy in Teams and assigns it to users.
.DESCRIPTION
Use this script to create a messaging policy and assign it to users in your organization.
#>

$dataSetFilePath = "<csv file with user ids for newly provisioned students> "
 $dataSet = Import-Csv "$($dataSetFilePath)" -Header UserId –delimiter ","
 foreach($line in $dataSet)
 {
    $userId = $line.UserId
    Write-Host $userId
    Grant-CsTeamsMessagingPolicy -PolicyName "<<PolicyName for a policy created with Chat Off>>" -Identity $userId

 }
```


