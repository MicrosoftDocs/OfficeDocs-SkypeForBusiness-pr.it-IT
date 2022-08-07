---
title: Script di esempio - Script di PowerShell del firewall di Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: harij, rafarhi
ms.localizationpriority: medium
search.appverid: MET150
description: Uno script di esempio che può essere usato per configurare Windows per consentire le connessioni di Teams tramite Windows Firewall.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b15c8e141f8a3cd5cde1915901d3dbcd9e29b23a
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269401"
---
# <a name="sample-script---microsoft-teams-firewall-powershell-script"></a>Script di esempio - Script di PowerShell del firewall di Microsoft Teams

Questo script di esempio, che deve essere eseguito nei computer client nel contesto di un account amministratore con privilegi elevati, creerà una nuova regola del firewall in entrata per ogni cartella utente trovata in c:\Users. Questa regola impedisce all'applicazione di chiedere agli utenti di creare regole del firewall quando effettuano la loro prima chiamata da Teams.

```powershell

<#
.SYNOPSIS
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions.
   The script will create a new inbound firewall rule for each user folder found in c:\users.
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($null -ne $users) {
    foreach ($user in $users) {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath) {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue)) {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}

```
