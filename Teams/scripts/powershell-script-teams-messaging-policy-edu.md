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
ms.openlocfilehash: 06f2dee7e7dbc4e15d544433057a8bb12b75b7c4
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827414"
---
<a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="41e1c-103">Esempio di script di PowerShell: creare e assegnare un criterio di messaggistica</span><span class="sxs-lookup"><span data-stu-id="41e1c-103">PowerShell script sample - Create and assign a messaging policy</span></span>
-------------------------------------------------------------------------

<span data-ttu-id="41e1c-104">Usa questo script di PowerShell per creare criteri di messaggistica in Microsoft teams e assegnarlo agli utenti.</span><span class="sxs-lookup"><span data-stu-id="41e1c-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="41e1c-105">Per altre informazioni sull'uso di questo script di PowerShell, vedere [Quick Start-teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span><span class="sxs-lookup"><span data-stu-id="41e1c-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="41e1c-106">Se non si ha familiarità con PowerShell e si ha bisogno di assistenza per iniziare, vedere [Panoramica di Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span><span class="sxs-lookup"><span data-stu-id="41e1c-106">If you're new to PowerShell and need help getting started, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span></span>


## <a name="sample-script"></a><span data-ttu-id="41e1c-107">Script di esempio</span><span class="sxs-lookup"><span data-stu-id="41e1c-107">Sample script</span></span>

````powershell
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
````


