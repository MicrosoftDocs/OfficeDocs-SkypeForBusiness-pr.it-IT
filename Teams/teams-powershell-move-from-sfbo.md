---
title: Migrazione da Skype for Business Online Connector al modulo di PowerShell di Teams
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Informazioni su come passare da Skype for Business Online Connector al modulo PowerShell di Teams per gestire Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 648ce1fb69f9e1641840f2e4b92acc1b98f4bbe8
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242290"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Migrazione da Skype for Business Online Connector al modulo di PowerShell di Teams

Il modulo PowerShell di Teams fornisce un set completo di cmdlet per la gestione di Teams direttamente dalla riga di comando di PowerShell. Gli amministratori non richiedono Skype For Business Online Connector per l'amministrazione di Teams.

> [!NOTE]
> L'amministratore di Teams ha ricevuto una notifica tramite il post del Centro messaggi (MC244740, datato 16 marzo 2021; MC250940, datata 16 aprile 2021) su questo cambiamento.
>
> Il modulo PowerShell di Teams usa l'autenticazione moderna, ma il client Gestione remota Windows sottostante (WinRM) deve essere configurato per consentire l'autenticazione di base. Vedi [Scaricare e installare Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) per istruzioni su come abilitare WinRM per l'autenticazione di base.

## <a name="how-to-migrate"></a>Come eseguire la migrazione

La migrazione dall'uso di Skype for Business Online Connector al modulo PowerShell di Teams è semplice e semplice. La procedura seguente illustra come eseguire questa operazione.

1. Installare il modulo PowerShell di Teams più recente. Per la procedura, vedere [Installare Microsoft PowerShell di Teams](teams-powershell-install.md).

2. Disinstallare Skype for Business Online Connector. A tale scopo, in Pannello di controllo vai a **Programmi e funzionalità**, seleziona **Skype for Business Online, Windows PowerShell Modulo** e quindi **seleziona Disinstalla**.

3. Negli script di PowerShell modificare il nome del modulo a ```Import-Module``` cui si fa riferimento da

    `SkypeOnlineConnector` o `LyncOnlineConnector` a `MicrosoftTeams`.

    Ad esempio, passare `Import-Module -Name SkypeOnlineConnector` a `Import-Module -Name MicrosoftTeams`.

4. Quando si usa Teams PowerShell Module 2.0 o versione successiva, aggiornare gli script che fanno riferimento `New-CsOnlineSession` a `Connect-MicrosoftTeams`. `Import-PsSession`non è più necessario per stabilire una sessione di PowerShell remota di Skype for Business Online in quanto viene eseguita implicita quando si utilizza `Connect-MicrosoftTeams`.

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

[Installare Microsoft PowerShell di Teams](teams-powershell-install.md)

[Gestire Teams con PowerShell di Teams](teams-powershell-managing-teams.md)

[Note sulla versione di Teams PowerShell](teams-powershell-release-notes.md)

[Riferimento per i cmdlet di Microsoft Teams](/powershell/teams/)

[riferimento ai cmdlet di Skype for Business](/powershell/skype/intro)
