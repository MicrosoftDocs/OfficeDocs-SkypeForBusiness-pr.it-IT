---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: c612f8d8e0f48249d9eabe19c5ae7513b0ae9d75
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593670"
---
1. Installare PowerShell versione 7 o successiva. Per istruzioni dettagliate, vedere Installazione [di PowerShell in](/powershell/scripting/install/installing-powershell-on-windows) Windows.

1. Eseguire PowerShell in modalità amministratore.
1. Installare il modulo di Microsoft Graph PowerShell.

    ```powershell
    Install-Module Microsoft.Graph
    Import-Module Microsoft.Graph
    ```

    Verificare che sia la versione 1.6.1 o successiva.

    ```powershell
    Get-InstalledModule Microsoft.Graph 
    ```

1. Installare il modulo di PowerShell Teams Preview.

    ```powershell
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force
    Import-Module MicrosoftTeams 
    ```

    Verificare che sia almeno la versione 4.1.0 e che contenga i cmdlet del connettore Shifts.

    ```powershell
    Get-Command -Module MicrosoftTeams -Name *teamsshiftsconnection* 
    ```
 
1. Installare il modulo msal powershell.

    ```powershell
    Install-Module -Name MSAL.PS
    Import-Module MSAL.PS
    ```

1. Impostare PowerShell per uscire se si verifica un errore durante l'esecuzione dello script.

    ```powershell
    $ErrorActionPreference = "Stop" 
    ```

1. Abilitare l'esecuzione di script in Windows.

    ```powershell
    Set-ExecutionPolicy bypass 
    ```