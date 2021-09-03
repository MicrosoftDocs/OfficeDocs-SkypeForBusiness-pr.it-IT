---
title: Migrazione da Skype for Business Online Connector al modulo Teams PowerShell
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Informazioni su come passare da Skype for Business Online Connector al modulo Teams PowerShell per gestire le Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: cdd6460e6a17a15193104a0871a57fa6dbff8105
ms.sourcegitcommit: 70c07a6b1be81681eec32a89872e2218d70c514d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2021
ms.locfileid: "58866358"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Migrazione da Skype for Business Online Connector al modulo Teams PowerShell

Teams Il modulo di PowerShell offre un set completo di cmdlet per la gestione Teams direttamente dalla riga di comando di PowerShell. Gli amministratori non richiedono Skype For Business Online Connector per l'amministrazione Teams utenti.

> [!NOTE]
> Teams amministratore è stato avvisato tramite post del Centro messaggi (MC244740, datato 16 marzo 2021; MC250940, datato 16 aprile 2021) su questa modifica.
>
> Teams Il modulo di PowerShell usa l'autenticazione moderna, ma il client Windows gestione remota (WinRM) sottostante deve essere configurato per consentire l'autenticazione di base. Vedere [Scaricare e installare Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) per istruzioni su come abilitare Gestione remota Windows per l'autenticazione di base.

## <a name="how-to-migrate"></a>Come eseguire la migrazione

La migrazione dall'uso Skype for Business Online Connector Teams modulo di PowerShell è semplice e semplice. La procedura seguente spiega come eseguire questa operazione.

1. Installare il modulo di PowerShell Teams più recente. Per la procedura, vedere [Installare Microsoft Teams PowerShell.](teams-powershell-install.md)

2. Disinstallare Skype For Business Online Connector. A questo scopo, nel Pannello di controllo passare a Programmi e **funzionalità,** selezionare Skype for Business **Online, Windows PowerShell modulo** e quindi selezionare **Disinstalla**.

3. Negli script di PowerShell modificare il nome del modulo a cui si fa riferimento ```Import-Module``` da

    `SkypeOnlineConnector` o `LyncOnlineConnector` su `MicrosoftTeams` .

    Ad esempio, passare `Import-Module -Name SkypeOnlineConnector` a `Import-Module -Name MicrosoftTeams` .

4. Quando si Teams modulo di PowerShell 2.0 o versione successiva, aggiornare gli script che fanno riferimento `New-CsOnlineSession` a `Connect-MicrosoftTeams` . `Import-PsSession`non è più necessario stabilire una sessione remota di PowerShell Skype for Business online come viene eseguita in modo implicito quando si usa `Connect-MicrosoftTeams` .

    ```powershell
       # When using the Skype for Business online connector
         
         # Establishing a session
         Import-Module SkypeOnlineConnector [LyncOnlineConnector]
         $credential = Get-Credential
         $SkypeSession = New-CsOnlineSession -Credential $credential
         Import-Session $SkypeSession
    
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session 
         Get-PsSession $SkypeSession | Remove-PsSession
    
       # When using Teams PowerShell Module 2.0 or later
       
         # Establishing a session
         Import-Module MicrosoftTeams
         $credential = Get-Credential
         Connect-MicrosoftTeams -Credential $credential
       
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session  
         Disconnect-MicrosoftTeams
    ```

## <a name="related-topics"></a>Argomenti correlati

[Installare Microsoft Teams PowerShell](teams-powershell-install.md)

[Gestire Teams con Teams PowerShell](teams-powershell-managing-teams.md)

[Teams Note sulla versione di PowerShell](teams-powershell-release-notes.md)

[Microsoft Teams cmdlet](/powershell/teams/?view=teams-ps)

[Skype for Business cmdlet](/powershell/skype/intro?view=skype-ps)
