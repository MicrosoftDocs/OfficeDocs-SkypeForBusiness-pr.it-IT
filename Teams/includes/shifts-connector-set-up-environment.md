---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: 3d4ec38f0007460fa119e69eadc79cd9c51887ee
ms.sourcegitcommit: 2ce3e95401ac06c0370a54862372a94ec6291d01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/05/2022
ms.locfileid: "64976019"
---
1. Installare PowerShell versione 7 o successiva. Per indicazioni dettagliate, vedere [Installazione di PowerShell in Windows](/powershell/scripting/install/installing-powershell-on-windows).

1. Eseguire PowerShell in modalità amministratore.
1. Installare il modulo Microsoft Graph PowerShell.

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

    Verificare che sia almeno la versione 4.1.0 e che contenga i cmdlet del connettore Turni.

    ```powershell
    Get-Command -Module MicrosoftTeams -Name *teamsshiftsconnection* 
    ```

1. Impostare PowerShell in modo che esci se si verifica un errore durante l'esecuzione dello script.

    ```powershell
    $ErrorActionPreference = "Stop" 
    ```

1. Abilitare l'esecuzione di script in Windows.

    ```powershell
    Set-ExecutionPolicy bypass 
    ```