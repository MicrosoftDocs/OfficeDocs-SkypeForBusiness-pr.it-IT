---
title: Esempio di script di PowerShell - Creare & assegnare criteri di messaggistica
author: serdars
ms.author: serdars
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: Usare questo script di PowerShell per creare un criterio di messaggistica in Teams e assegnarlo agli utenti dell'organizzazione.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 09254f9ed85f69551ee825dbeb8ae063a010f780
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823707"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>Esempio di script di PowerShell : creare e assegnare criteri di messaggistica

Usare questo script di PowerShell per creare un criterio di messaggistica in Microsoft Teams e assegnarlo agli utenti. 

Per altre informazioni sull'uso di questo script di PowerShell, vedere [Guida introduttiva - Teams per l'istruzione](../teams-quick-start-edu.yml).

Questo script usa il cmdlet [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) incluso nel modulo powershell di Skype for Business Online. Per altre informazioni sulla gestione di Teams con PowerShell, vedere Teams [panoramica di PowerShell](../teams-powershell-overview.md).


## <a name="before-you-start"></a>Prima di iniziare

Scaricare e installare il [modulo di PowerShell di Skype for Business Online](https://www.microsoft.com/download/details.aspx?id=54616), quindi riavviare il computer se richiesto.

Per altre informazioni, vedere [Gestire Skype for Business Online con Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

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
> È anche possibile assegnare criteri di messaggistica direttamente agli utenti in scala tramite un'assegnazione di criteri batch o a un gruppo di cui gli utenti sono membri. Per altre informazioni, vedere [Assegnare criteri a grandi gruppi di utenti dell'istituto di](../batch-group-policy-assignment-edu.md) istruzione e [Assegnare criteri agli utenti in Teams](../policy-assignment-overview.md).