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
description: Informazioni su come installare e connettersi al modulo di PowerShell Microsoft StaffHub.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ce0d1acec923d09591e8f81b3f500ee9a910f5c
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464666"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Installare il modulo di PowerShell Microsoft StaffHub

> [!IMPORTANT]
> Efficace il 1 ° ottobre 2019, Microsoft StaffHub sarà ritirato. Stiamo costruendo funzionalità di StaffHub in Microsoft teams. Oggi teams include l'app turni per la gestione della pianificazione e le funzionalità aggiuntive verranno distribuite nel tempo. StaffHub smetterà di funzionare per tutti gli utenti il 1 ° ottobre 2019. Chiunque tenti di aprire StaffHub verrà visualizzato un messaggio che li indirizza a scaricare teams. Per altre informazioni, vedere [Microsoft StaffHub per](microsoft-staffhub-to-be-retired.md)ritirarsi.  

Seguire i passaggi di questo articolo per installare e connettersi al modulo di PowerShell Microsoft StaffHub. Per gestire StaffHub, è necessario usare PowerShell e trasferire i team di StaffHub in Microsoft teams.

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Installare il modulo di PowerShell Microsoft StaffHub

1. Aprire Windows PowerShell 3,0 o versione successiva come amministratore. A tale scopo, fare clic sul pulsante **Start**, digitare **Windows PowerShell**, fare clic con il pulsante destro del mouse su **Windows PowerShell**e quindi scegliere **Esegui come amministratore**.
    > [!NOTE]
    > Per ottenere la versione più recente di Windows PowerShell, vedere [installazione di Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell). 
2. Eseguire la procedura seguente per installare la versione stabile corrente del modulo di PowerShell StaffHub:

    ```
    Install-Module -Name MicrosoftStaffHub
    ```
    
    È possibile eseguire questo comando solo se è necessario installare la versione più recente, che potrebbe avere più instabilità rispetto alla versione stabile corrente:`Install-Module -Name MicrosoftStaffHub -AllowPrerelease`

     > [!NOTE]
     > Se viene visualizzato un messaggio di errore durante l'installazione della versione più recente con più instabilità, è possibile eseguire:`Install-Module PowershellGet -Force`

3. Potrebbe essere visualizzato il messaggio di avviso:

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

Digitare `Y` e fare `Enter`clic su.
 
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
