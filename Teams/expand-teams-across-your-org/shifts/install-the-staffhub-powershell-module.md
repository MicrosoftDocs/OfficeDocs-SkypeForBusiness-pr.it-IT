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
description: Informazioni su come installare e connettersi alla versione prerelease del modulo di PowerShell Microsoft StaffHub.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: aa7f84342b2d4ae16cf801be513e1ae9d6440802
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569211"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Installare il modulo di PowerShell Microsoft StaffHub

> [!IMPORTANT]
> Efficace 31 dicembre 2019, Microsoft StaffHub sarà ritirato. Stiamo costruendo funzionalità di StaffHub in Microsoft teams. Oggi teams include l'app turni per la gestione della pianificazione e le funzionalità aggiuntive verranno distribuite nel tempo. StaffHub smetterà di funzionare per tutti gli utenti il 31 dicembre 2019. Chiunque tenti di aprire StaffHub verrà visualizzato un messaggio che li indirizza a scaricare teams. Per altre informazioni, vedere [Microsoft StaffHub per ritirarsi](microsoft-staffhub-to-be-retired.md).  

Usare i passaggi descritti in questo articolo per installare e connettersi alla versione prerelease del modulo di PowerShell Microsoft StaffHub. Sarà necessario questo per [trasferire i team di StaffHub in teams](move-staffhub-teams-to-shifts-in-teams.md).

## <a name="install-the-prerelease-version-of-the-microsoft-staffhub-powershell-module"></a>Installare la versione prerelease del modulo di PowerShell Microsoft StaffHub

1. Aprire Windows PowerShell 3,0 o versione successiva come amministratore. A tale scopo, fare clic sul pulsante **Start**, digitare **Windows PowerShell**, fare clic con il pulsante destro del mouse su **Windows PowerShell**e quindi scegliere **Esegui come amministratore**.
    > [!NOTE]
    > Per ottenere la versione più recente di Windows PowerShell, vedere [installazione di Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell). 
2. Eseguire la procedura seguente per installare la versione prerelease del modulo di PowerShell StaffHub:

    ```
    Install-Module -Name MicrosoftStaffHub -AllowPrerelease
    ```
3. Potrebbe essere visualizzato il messaggio di avviso:

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

    Digitare `Y`e quindi fare clic `Enter`su.
 
4. Uscire da Windows PowerShell.

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>Connettersi al modulo di PowerShell Microsoft StaffHub

1. Esegui il seguente comando:

    ```
    Connect-StaffHub
    ```

2. Quando viene richiesto, accedere come amministratore globale.

## <a name="related-topics"></a>Argomenti correlati

- [Riferimento a Microsoft PowerShell per StaffHub](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [Spostare i team di Microsoft StaffHub in turni in teams](move-staffhub-teams-to-shifts-in-teams.md)
