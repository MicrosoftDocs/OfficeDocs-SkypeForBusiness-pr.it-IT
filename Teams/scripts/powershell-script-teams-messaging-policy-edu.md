---
title: Esempio di script di PowerShell - Creare & assegnare criteri di messaggistica
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: Usare questo script di PowerShell per creare un criterio di messaggistica in Teams e assegnarlo agli utenti dell'organizzazione.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c665b96c0c44c2ea763c343bb2857d4c2b9dbb26
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117274"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="3e150-103">Esempio di script di PowerShell - Creare e assegnare criteri di messaggistica</span><span class="sxs-lookup"><span data-stu-id="3e150-103">PowerShell script sample - Create and assign a messaging policy</span></span>

<span data-ttu-id="3e150-104">Usare questo script di PowerShell per creare un criterio di messaggistica in Microsoft Teams e assegnarlo agli utenti.</span><span class="sxs-lookup"><span data-stu-id="3e150-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="3e150-105">Per altre informazioni sull'uso di questo script di PowerShell, vedere Guida [introduttiva - Teams per l'istruzione.](../teams-quick-start-edu.yml)</span><span class="sxs-lookup"><span data-stu-id="3e150-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](../teams-quick-start-edu.yml).</span></span>

<span data-ttu-id="3e150-106">Questo script usa il cmdlet [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) nel modulo di PowerShell Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="3e150-106">This script uses the [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet which is in the Skype for Business Online PowerShell module.</span></span> <span data-ttu-id="3e150-107">Vedere [Teams panoramica di PowerShell](../teams-powershell-overview.md) per altre informazioni sulla gestione Teams con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e150-107">See [Teams PowerShell overview](../teams-powershell-overview.md) to learn more about managing Teams using PowerShell.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="3e150-108">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="3e150-108">Before you start</span></span>

<span data-ttu-id="3e150-109">Scaricare e installare il modulo [di PowerShell Skype for Business Online,](https://www.microsoft.com/download/details.aspx?id=39366)quindi riavviare il computer, se richiesto.</span><span class="sxs-lookup"><span data-stu-id="3e150-109">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer if prompted.</span></span>

<span data-ttu-id="3e150-110">Per snellire di più, [vedere Gestire Skype for Business Online con Office 365 PowerShell.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="3e150-110">To lean more, see [Manage Skype for Business Online with Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="sample-script"></a><span data-ttu-id="3e150-111">Script di esempio</span><span class="sxs-lookup"><span data-stu-id="3e150-111">Sample script</span></span>

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

> [!NOTE]
> <span data-ttu-id="3e150-112">È anche possibile assegnare un criterio di messaggistica direttamente agli utenti su larga scala tramite un'assegnazione di criteri batch o a un gruppo di cui gli utenti sono membri.</span><span class="sxs-lookup"><span data-stu-id="3e150-112">You can also assign a messaging policy directly to users at scale through a batch policy assignment or to a group that the users are members of.</span></span> <span data-ttu-id="3e150-113">Per altre informazioni, vedere [Assegnare criteri a grandi set](../batch-group-policy-assignment-edu.md) di utenti dell'istituto di istruzione e [Assegnare](../assign-policies.md)criteri agli utenti in Teams .</span><span class="sxs-lookup"><span data-stu-id="3e150-113">For more information see [Assign policies to large sets of users in your school](../batch-group-policy-assignment-edu.md) and [Assign policies to your users in Teams](../assign-policies.md).</span></span>