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
ms.openlocfilehash: e3d1fa3ebe45785c088852c518ac5490263fa6aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804656"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="6df60-103">Esempio di script di PowerShell - Creare e assegnare criteri di messaggistica</span><span class="sxs-lookup"><span data-stu-id="6df60-103">PowerShell script sample - Create and assign a messaging policy</span></span>

<span data-ttu-id="6df60-104">Usare questo script di PowerShell per creare un criterio di messaggistica in Microsoft Teams e assegnarlo agli utenti.</span><span class="sxs-lookup"><span data-stu-id="6df60-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="6df60-105">Per altre informazioni sull'uso di questo script di PowerShell, vedere [La Guida introduttiva di Teams per l'istruzione.](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)</span><span class="sxs-lookup"><span data-stu-id="6df60-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="6df60-106">Questo script usa il cmdlet [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) presente nel modulo PowerShell di Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="6df60-106">This script uses the [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet which is in the Skype for Business Online PowerShell module.</span></span> <span data-ttu-id="6df60-107">Per altre informazioni sulla gestione di Teams con [PowerShell,](../teams-powershell-overview.md) vedere la panoramica di Teams su PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6df60-107">See [Teams PowerShell overview](../teams-powershell-overview.md) to learn more about managing Teams using PowerShell.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="6df60-108">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="6df60-108">Before you start</span></span>

<span data-ttu-id="6df60-109">Scaricare e installare il [modulo PowerShell di Skype for Business online,](https://www.microsoft.com/download/details.aspx?id=39366)quindi riavviare il computer, se richiesto.</span><span class="sxs-lookup"><span data-stu-id="6df60-109">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer if prompted.</span></span>

<span data-ttu-id="6df60-110">Per saperne di più, [consulta Gestire Skype for Business online con PowerShell di Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="6df60-110">To lean more, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="sample-script"></a><span data-ttu-id="6df60-111">Script di esempio</span><span class="sxs-lookup"><span data-stu-id="6df60-111">Sample script</span></span>

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
> <span data-ttu-id="6df60-112">È anche possibile assegnare criteri di messaggistica direttamente agli utenti su scala mediante un'assegnazione di criteri batch o a un gruppo di cui gli utenti sono membri.</span><span class="sxs-lookup"><span data-stu-id="6df60-112">You can also assign a messaging policy directly to users at scale through a batch policy assignment or to a group that the users are members of.</span></span> <span data-ttu-id="6df60-113">Per altre informazioni, vedere [Assegnare criteri a grandi set di utenti](../batch-group-policy-assignment-edu.md) dell'istituto di istruzione e Assegnare criteri agli utenti in [Teams.](../assign-policies.md)</span><span class="sxs-lookup"><span data-stu-id="6df60-113">For more information see [Assign policies to large sets of users in your school](../batch-group-policy-assignment-edu.md) and [Assign policies to your users in Teams](../assign-policies.md).</span></span>
