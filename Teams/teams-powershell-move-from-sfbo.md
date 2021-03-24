---
title: Passare da Skype for Business Online Connector al modulo di PowerShell di Teams
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Scopri come passare da Skype for Business Online Connector al modulo di PowerShell di Teams per gestire Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5a2b502edc84c853a0a140a11f8c028b7c78aca6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094127"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Passare da Skype for Business Online Connector al modulo di PowerShell di Teams

Per passare dall'uso di Skype for Business Online Connector al modulo di PowerShell di Teams per gestire Teams, è necessario aggiornare gli script di PowerShell esistenti. Questo articolo spiega come eseguire questa operazione.

1. Installare il modulo di PowerShell più recente di Teams. Per la procedura, vedere [Installare Microsoft Teams Powershell.](teams-powershell-install.md)
2. Disinstallare Skype for Business Online Connector. Per farlo, nel Pannello di controllo vai **a** Programmi e funzionalità, seleziona Skype for **Business online, Windows PowerShell Modulo** e quindi seleziona **Disinstalla**. 
3. Negli script di PowerShell modificare il nome del modulo a cui viene fatto riferimento ```Import-Module``` da ```SkypeOnlineConnector``` o in ```LyncOnlineConnector``` ```MicrosoftTeams``` .

    Ad esempio, passare ```Import-Module -Name SkypeOnlineConnector``` a ```Import-Module -Name MicrosoftTeams``` .
4. Quando si usa il modulo powershell di Teams 2.0 o versione successiva, modificare New-csOnlineSession in Connect-MicrosoftTeams. 

```powershell
  # When using Teams PowerShell Module 1.1.6
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfbSession
   
   # When using Teams PowerShell Module 2.0 or later
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## <a name="related-topics"></a>Argomenti correlati

[Installare Microsoft Teams Powershell](teams-powershell-install.md)

[Gestire Teams con Teams PowerShell](teams-powershell-managing-teams.md)

[Note sulla versione di PowerShell di Teams](teams-powershell-release-notes.md)

[Informazioni di riferimento sul cmdlet di Microsoft Teams](/powershell/teams/?view=teams-ps)

[Informazioni di riferimento sul cmdlet di Skype for Business](/powershell/skype/intro?view=skype-ps)