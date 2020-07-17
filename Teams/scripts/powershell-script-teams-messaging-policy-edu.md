---
title: Esempio di script di PowerShell-creare & assegnare criteri di messaggistica
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
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c1df183046dc2378081382e2a8b46c9b3b92c80a
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938195"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="658f2-103">Esempio di script di PowerShell: creare e assegnare un criterio di messaggistica</span><span class="sxs-lookup"><span data-stu-id="658f2-103">PowerShell script sample - Create and assign a messaging policy</span></span>

<span data-ttu-id="658f2-104">Usa questo script di PowerShell per creare criteri di messaggistica in Microsoft teams e assegnarlo agli utenti.</span><span class="sxs-lookup"><span data-stu-id="658f2-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="658f2-105">Per altre informazioni sull'uso di questo script di PowerShell, vedere [Quick Start-teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span><span class="sxs-lookup"><span data-stu-id="658f2-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="658f2-106">Questo script usa il cmdlet [Grant-CsTeamsMessagingPolicy,](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) che si trova nel modulo di PowerShell per Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="658f2-106">This script uses the [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet which is in the Skype for Business Online PowerShell module.</span></span> <span data-ttu-id="658f2-107">Per ulteriori informazioni sulla gestione dei team tramite PowerShell, vedere [Panoramica di teams PowerShell](../teams-powershell-overview.md) .</span><span class="sxs-lookup"><span data-stu-id="658f2-107">See [Teams PowerShell overview](../teams-powershell-overview.md) to learn more about managing Teams using PowerShell.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="658f2-108">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="658f2-108">Before you start</span></span>

<span data-ttu-id="658f2-109">Scaricare e installare il [modulo di PowerShell per Skype for business online](https://www.microsoft.com/download/details.aspx?id=39366)e quindi riavviare il computer, se richiesto.</span><span class="sxs-lookup"><span data-stu-id="658f2-109">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer if prompted.</span></span>

<span data-ttu-id="658f2-110">Per altre informazioni, vedere [gestire Skype for business online con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="658f2-110">To lean more, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>


## <a name="sample-script"></a><span data-ttu-id="658f2-111">Script di esempio</span><span class="sxs-lookup"><span data-stu-id="658f2-111">Sample script</span></span>

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
> <span data-ttu-id="658f2-112">È anche possibile assegnare un criterio di messaggistica direttamente agli utenti in scala tramite un'assegnazione di criteri batch o a un gruppo di cui sono membri gli utenti.</span><span class="sxs-lookup"><span data-stu-id="658f2-112">You can also assign a messaging policy directly to users at scale through a batch policy assignment or to a group that the users are members of.</span></span> <span data-ttu-id="658f2-113">Per altre informazioni, vedere [assegnare criteri a set di utenti di grandi dimensioni dell'Istituto di istruzione](../batch-policy-assignment-edu.md) e [assegnare criteri agli utenti in teams](../assign-policies.md).</span><span class="sxs-lookup"><span data-stu-id="658f2-113">For more information see [Assign policies to large sets of users in your school](../batch-policy-assignment-edu.md) and [Assign policies to your users in Teams](../assign-policies.md).</span></span>
