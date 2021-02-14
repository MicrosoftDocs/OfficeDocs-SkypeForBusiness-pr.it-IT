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
ms.openlocfilehash: 4e1838540e57cd91578e898818e2ed12e7b63a78
ms.sourcegitcommit: 51d94d621e3411f35622e852b699275f526600dd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469667"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Passare da Skype for Business Online Connector al modulo PowerShell di Teams

Per passare dall'uso di Skype for Business Online Connector al modulo PowerShell di Teams per la gestione di Teams, è necessario aggiornare gli script di PowerShell esistenti. Questo articolo spiega come fare.

1. Installare l'ultima versione del modulo Di PowerShell di Teams. Per istruzioni, vedere [Installare Microsoft Teams Powershell.](teams-powershell-install.md)
2. Disinstallare Skype for Business Online Connector. Per farlo, nel Pannello di controllo vai a Programmi e **funzionalità,** seleziona **Skype for Business online,** Windows PowerShell modulo, quindi **seleziona Disinstalla.** 
3. Negli script di PowerShell modificare il nome del modulo a cui viene fatto riferimento ```Import-Module``` da ```SkypeOnlineConnector``` o a ```LyncOnlineConnector``` ```MicrosoftTeams``` .

    Ad esempio, passare ```Import-Module -Name SkypeOnlineConnector``` a ```Import-Module -Name MicrosoftTeams``` .

> [!NOTE]
> Gli amministratori devono continuare a usare [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) e importare la sessione prima di usare i cmdlet di Skype for Business Online. 

## <a name="related-topics"></a>Argomenti correlati

[Installare Microsoft Teams Powershell](teams-powershell-install.md)

[Gestire Teams con PowerShell di Teams](teams-powershell-managing-teams.md)

[Note sulla versione di PowerShell di Teams](teams-powershell-release-notes.md)

[Informazioni di riferimento per i cmdlet di Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Informazioni di riferimento per i cmdlet di Skype for Business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
