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
description: Informazioni su come passare da Skype for Business Online Connector al modulo di PowerShell Teams per gestire Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e788fc8cd31bd6e8754e410132e02829eaa2cad8
ms.sourcegitcommit: 50ec59b454e751d952cde9fd13c8017529d0e1d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2021
ms.locfileid: "52469718"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Migrazione da Skype for Business Online Connector al modulo Teams PowerShell

Teams Il modulo di PowerShell offre un set completo di cmdlet per la gestione Teams direttamente dalla riga di comando di PowerShell. Gli amministratori non richiedono Skype For Business Online Connector per l'amministrazione Teams utenti.

> [!NOTE]
> Teams amministratore è stato avvisato tramite post del Centro messaggi (MC244740, datato 16 marzo 2021; MC250940, datato 16 aprile 2021) su questa modifica.
>
> Teams Il modulo di PowerShell usa l'autenticazione moderna, ma il client Windows gestione remota (WinRM) sottostante deve essere configurato per consentire l'autenticazione di base. Vedere [Scaricare e installare Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) per istruzioni su come abilitare Gestione remota Windows per l'autenticazione di base.

> [!WARNING]
> Skype for Business Le connessioni Online Connector verranno rifiutate a partire dal 17 maggio 2021. Contattare il supporto tecnico Microsoft per assistenza e supporto per la migrazione a Teams modulo di PowerShell.

## <a name="how-to-migrate"></a>Come eseguire la migrazione

La migrazione dall'uso di Skype for Business Online Connector Teams modulo di PowerShell è semplice e semplice. La procedura seguente spiega come eseguire questa operazione.

1. Installare il modulo di PowerShell Teams più recente. Per la procedura, vedere [Installare Microsoft Teams Powershell.](teams-powershell-install.md)
2. Disinstallare Skype For Business Online Connector. A questo scopo, nel Pannello di controllo passare a Programmi e funzionalità **,** selezionare Skype for Business **Online, Windows PowerShell modulo** e quindi selezionare **Disinstalla**.
3. Negli script di PowerShell modificare il nome del modulo a cui si fa riferimento ```Import-Module``` da

    `SkypeOnlineConnector` o `LyncOnlineConnector` su `MicrosoftTeams` .

    Ad esempio, passare `Import-Module -Name SkypeOnlineConnector` a `Import-Module -Name MicrosoftTeams` .

4. Quando si Teams modulo di PowerShell 2.0 o versione successiva, aggiornare gli script che fanno riferimento `New-CsOnlineSession` a `Connect-MicrosoftTeams` . `Import-PsSession`non è più necessario stabilire una sessione remota di PowerShell Skype for Business online, perché questa operazione viene eseguita implicitamente quando si usa `Connect-MicrosoftTeams` .

    ```powershell
       # When using the Skype for Business online connector
         Import-Module SkypeForBusinessConnector [LyncOnlineConnector]
         $credential = Get-Credential
         $SkypeSession = New-CsOnlineSession -Credential $credential
         Import-Session $SkypeSession
    
       # Example getting tenant details
         Get-csTenant
    
       # When using Teams PowerShell Module 2.0 or later
         Import-Module MicrosoftTeams
         $credential = Get-Credential
         Connect-MicrosoftTeams -Credential $credential
       
       # Example getting tenant details
         Get-csTenant
    
       # Closing the Session when using the Skype for Business online connector
         Get-PsSession $SkypeSession | Remove-PsSession
    
       # Disconnecting from Teams PowerShell Module 
         Disconnect-MicrosoftTeams
    ```

## <a name="online-support"></a>Supporto online

È possibile risparmiare tempo avviando la richiesta di servizio online. Microsoft ti aiuterà a trovare una soluzione o a connetterti al supporto tecnico.
1.  Passare all'interfaccia di amministrazione in [https://admin.microsoft.com](https://admin.microsoft.com) . Se viene visualizzato un messaggio che indica che non si è autorizzati ad accedere a questa pagina o a eseguire questa azione, non si è amministratori. Who autorizzazioni di amministratore nella mia azienda?
2.  Selezionare la casella **di controllo Serve assistenza?** .
3.  Nella finestra **Serve aiuto?** , dicci per cosa hai bisogno di aiuto e quindi premi INVIO.
4.  Se i risultati non sono utili, selezionare **Contatta il supporto.**
5.  Immettere una descrizione del problema, confermare il numero di contatto e l'indirizzo di posta elettronica, selezionare il metodo di contatto preferito e quindi **selezionare Contattami**. Il tempo di attesa previsto è indicato nel campo Serve aiuto? riquadro.

## <a name="related-topics"></a>Argomenti correlati

[Installare Microsoft Teams PowerShell](teams-powershell-install.md)

[Gestire Teams con Teams PowerShell](teams-powershell-managing-teams.md)

[Teams Note sulla versione di PowerShell](teams-powershell-release-notes.md)

[Microsoft Teams di cmdlet](/powershell/teams/?view=teams-ps)

[Skype for Business cmdlet](/powershell/skype/intro?view=skype-ps)
