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
ms.openlocfilehash: 748167dc8e03b53fc07611df0ff464d984fb5678
ms.sourcegitcommit: 69ff557c79d6b1a3d1089fe5c8f5c8ed8ff7431e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2020
ms.locfileid: "43951061"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>Esempio di script di PowerShell: creare e assegnare un criterio di messaggistica

Usa questo script di PowerShell per creare criteri di messaggistica in Microsoft teams e assegnarlo agli utenti. 

Per altre informazioni sull'uso di questo script di PowerShell, vedere [Quick Start-teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).

Questo script usa il cmdlet [Grant-CsTeamsMessagingPolicy,](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) che si trova nel modulo di PowerShell per Skype for business online. Per ulteriori informazioni sulla gestione dei team tramite PowerShell, vedere [Panoramica di teams PowerShell](../teams-powershell-overview.md) .


## <a name="before-you-start"></a>Prima di iniziare

Scaricare e installare il [modulo di PowerShell per Skype for business online](https://www.microsoft.com/download/details.aspx?id=39366)e quindi riavviare il computer, se richiesto.

Per altre informazioni, vedere [gestire Skype for business online con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).


## <a name="sample-script"></a>Script di esempio

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
> È anche possibile usare l'assegnazione di criteri batch per assegnare un criterio di messaggistica a set di utenti di grandi dimensioni. Per altre informazioni, vedere [assegnare criteri a set di utenti di grandi dimensioni dell'Istituto di istruzione](../batch-policy-assignment-edu.md) e [assegnare criteri agli utenti in teams](../assign-policies.md).
