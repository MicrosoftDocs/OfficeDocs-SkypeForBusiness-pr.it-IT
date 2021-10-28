---
title: Esempio di script di PowerShell - Creare & criteri di messaggistica
author: cichur
ms.author: serdars
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: Usare questo script di PowerShell per creare criteri di messaggistica in Teams e assegnarli agli utenti dell'organizzazione.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c76f7441e335532fcacaf3fe41561fc0ef7ef516
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2021
ms.locfileid: "60605192"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>Esempio di script di PowerShell - Creare e assegnare criteri di messaggistica

Usare questo script di PowerShell per creare criteri di messaggistica in Microsoft Teams e assegnarli agli utenti. 

Per altre informazioni sull'uso di questo script di PowerShell, vedere [Guida introduttiva - Teams per l'istruzione](../teams-quick-start-edu.yml).

Questo script usa il cmdlet [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) nel modulo di PowerShell Skype for Business Online. Vedere [Teams panoramica di PowerShell](../teams-powershell-overview.md) per altre informazioni sulla gestione Teams tramite PowerShell.


## <a name="before-you-start"></a>Prima di iniziare

Scaricare e installare il modulo [di PowerShell Skype for Business Online,](https://www.microsoft.com/download/details.aspx?id=39366)quindi riavviare il computer, se richiesto.

Per snellire di più, [vedere Gestire Skype for Business Online con Office 365 PowerShell.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

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
> È anche possibile assegnare un criterio di messaggistica direttamente agli utenti su larga scala tramite un'assegnazione di criteri batch o a un gruppo di cui gli utenti sono membri. Per altre informazioni, vedere [Assegnare criteri a grandi set](../batch-group-policy-assignment-edu.md) di utenti dell'istituto di istruzione e [Assegnare](../policy-assignment-overview.md)criteri agli utenti in Teams .