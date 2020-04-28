---
title: Installare il modulo di PowerShell StaffHub
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come installare e connettersi al modulo di PowerShell Microsoft StaffHub e trasferire i team di StaffHub in Microsoft teams.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 52b4e0c41520468bc1e05734644d1beb05fed5be
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905728"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Installare il modulo di PowerShell Microsoft StaffHub

> [!IMPORTANT]
> Efficace 31 dicembre 2019, Microsoft StaffHub sarà ritirato. Stiamo costruendo funzionalità di StaffHub in Microsoft teams. Oggi teams include l'app turni per la gestione della pianificazione e le funzionalità aggiuntive verranno distribuite nel tempo. StaffHub smetterà di funzionare per tutti gli utenti il 31 dicembre 2019. Chiunque tenti di aprire StaffHub verrà visualizzato un messaggio che li indirizza a scaricare teams. Per altre informazioni, vedere [Microsoft StaffHub per ritirarsi](microsoft-staffhub-to-be-retired.md).  

Seguire i passaggi di questo articolo per installare e connettersi al modulo di PowerShell Microsoft StaffHub. Sarà necessario questo per [trasferire i team di StaffHub in teams](move-staffhub-teams-to-shifts-in-teams.md).

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Installare il modulo di PowerShell Microsoft StaffHub

1. Scaricare il [modulo di PowerShell StaffHub](https://www.powershellgallery.com/packages/MicrosoftStaffHub).
2. Aprire Windows PowerShell 3,0 o versione successiva come amministratore. A tale scopo, fare clic sul pulsante **Start**, digitare **Windows PowerShell**, fare clic con il pulsante destro del mouse su **Windows PowerShell**e quindi scegliere **Esegui come amministratore**.
    > [!NOTE]
    > Per ottenere la versione più recente di Windows PowerShell, vedere [installazione di Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).
3. Esegui il seguente comando:

    ```PowerShell
    $ENV:PSModulePath
    ```
4. Controllare il percorso della cartella nell'output e verificare che nel computer siano presenti tutte le cartelle del percorso prima di procedere con il passaggio successivo. Se le cartelle sono mancanti, crearle.
5. Eseguire la procedura seguente per consentire l'installazione del modulo di PowerShell StaffHub:

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
6. Eseguire la procedura seguente, &lt;dove&gt; path è il percorso nell'output del passaggio 3. Ad esempio, il percorso potrebbe essere simile a C:\Users\User1\Documents\WindowsPowerShell\Modules.

    Assicurarsi di eseguire ogni comando separatamente.

    ```PowerShell
    Install-Module -Name PackageManagement -Force  -AllowClobber
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    ```
7. Uscire da Windows PowerShell.
8. Aprire Windows PowerShell 3,0 o versione successiva come amministratore globale, quindi eseguire le operazioni seguenti:

    ```PowerShell
    Install-Module -Name MicrosoftStaffHub
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>Connettersi al modulo di PowerShell Microsoft StaffHub

1. Esegui il seguente comando:

    ```PowerShell
    Connect-StaffHub
    ```

2. Quando viene richiesto, accedere come amministratore globale.

## <a name="related-topics"></a>Argomenti correlati

- [Riferimento a Microsoft PowerShell per StaffHub](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
- [Spostare i team di Microsoft StaffHub in Turni in Teams](move-staffhub-teams-to-shifts-in-teams.md)
