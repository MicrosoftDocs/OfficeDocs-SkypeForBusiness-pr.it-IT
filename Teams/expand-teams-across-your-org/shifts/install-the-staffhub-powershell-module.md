---
title: Installare il modulo di PowerShell StaffHub
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Informazioni su come installare e connettersi al modulo di PowerShell Microsoft StaffHub.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2dc7c97a3c8107de3c2515a8f112bbc1993e3d8f
ms.sourcegitcommit: d4ebbebd5e4bfac27280bdc043fc6edd0722d1d7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2019
ms.locfileid: "36184534"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Installare il modulo di PowerShell Microsoft StaffHub

> [!IMPORTANT]
> Efficace il 1 ° ottobre 2019, Microsoft StaffHub sarà ritirato. Stiamo costruendo funzionalità di StaffHub in Microsoft teams. Oggi teams include l'app turni per la gestione della pianificazione e le funzionalità aggiuntive verranno distribuite nel tempo. StaffHub smetterà di funzionare per tutti gli utenti il 1 ° ottobre 2019. Chiunque tenti di aprire StaffHub verrà visualizzato un messaggio che li indirizza a scaricare teams. Per altre informazioni, vedere [Microsoft StaffHub per](microsoft-staffhub-to-be-retired.md)ritirarsi.  

Seguire i passaggi di questo articolo per installare e connettersi al modulo di PowerShell Microsoft StaffHub. Per gestire StaffHub, è necessario usare PowerShell e trasferire i team di StaffHub in Microsoft teams.

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Installare il modulo di PowerShell Microsoft StaffHub

1. Scaricare il [modulo di PowerShell StaffHub](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha). 
2. Aprire Windows PowerShell 3,0 o versione successiva come amministratore. A tale scopo, fare clic sul pulsante **Start**, digitare **Windows PowerShell**, fare clic con il pulsante destro del mouse su **Windows PowerShell**e quindi scegliere **Esegui come amministratore**.
    > [!NOTE]
    > Per ottenere la versione più recente di Windows PowerShell, vedere [installazione di Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell). 
3. Esegui il seguente comando:

    ```
    $ENV:PSModulePath
    ```
    

4. Controllare il percorso della cartella nell'output e verificare che nel computer siano presenti tutte le cartelle del percorso prima di procedere con il passaggio successivo. Se le cartelle sono mancanti, crearle.
5. Eseguire la procedura seguente per consentire l'installazione del modulo di PowerShell StaffHub:

    ```
    Set-ExecutionPolicy RemoteSigned
    ```

6. Eseguire la procedura seguente, &lt;dove&gt; path è il percorso nell'output del passaggio 2. Ad esempio, il percorso potrebbe essere simile a C:\Users\User1\Documents\WindowsPowerShell\Modules.

    Assicurarsi di eseguire ogni comando separatamente.

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PackageManagement -Force  -AllowClobber
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.5-alpha -AllowPrerelease
    ```
7. Uscire da Windows PowerShell.
8. Aprire Windows PowerShell 3,0 o versione successiva come amministratore globale, quindi eseguire le operazioni seguenti:

    ```
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.5-alpha -AllowPrerelease
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>Connettersi al modulo di PowerShell Microsoft StaffHub

1. Esegui il seguente comando:

    ```
    Connect-StaffHub
    ```

2. Quando viene richiesto, accedere come amministratore globale.

## <a name="related-topics"></a>Argomenti correlati

- [Riferimento a Microsoft PowerShell per StaffHub](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [Spostare i team di Microsoft StaffHub in turni in teams](move-staffhub-teams-to-shifts-in-teams.md)
