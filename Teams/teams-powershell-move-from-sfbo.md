---
title: Passare da Skype for Business Online Connector al modulo PowerShell di Teams
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Informazioni su come passare da Skype for Business Online Connector al modulo Di PowerShell di Teams per gestire Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32029de1ec33ee89c8dba30d8368131b291fc3f8
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569082"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Passare da Skype for Business Online Connector al modulo PowerShell di Teams

Per passare dall'uso di Skype for Business Online Connector al modulo PowerShell di Teams per la gestione di Teams, è necessario aggiornare gli script di PowerShell esistenti. Questo articolo spiega come fare.

1. Installare l'ultima versione del modulo Di PowerShell di Teams. Per istruzioni, vedere [Installare Microsoft Teams Powershell.](teams-powershell-install.md)
2. Disinstallare Skype for Business Online Connector. Per farlo, nel Pannello di controllo vai a Programmi e **funzionalità,** seleziona **Skype for Business online,** Windows PowerShell modulo, quindi **seleziona Disinstalla.** 
3. Negli script di PowerShell modificare il nome del modulo a cui viene fatto riferimento ```Import-Module``` da ```SkypeOnlineConnector``` o in ```LyncOnlineConnector``` ```MicrosoftTeams``` .

    Ad esempio, passare ```Import-Module -Name SkypeOnlineConnector``` a ```Import-Module -Name MicrosoftTeams``` .
4. Quando si usa il modulo Di PowerShell di Teams 2.0 o versione successiva, modificare New-csOnlineSession in Connect-MicrosoftTeams. 

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

[Gestire Teams con PowerShell di Teams](teams-powershell-managing-teams.md)

[Note sulla versione di Teams PowerShell](teams-powershell-release-notes.md)

[Informazioni di riferimento per i cmdlet di Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Informazioni di riferimento per i cmdlet di Skype for Business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
