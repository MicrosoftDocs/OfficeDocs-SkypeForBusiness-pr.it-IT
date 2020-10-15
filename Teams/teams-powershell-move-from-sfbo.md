---
title: Passaggio dal connettore Skype for business online al modulo di PowerShell Teams
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Informazioni su come passa da Skype for Business Online Connector al modulo teams PowerShell per gestire i team.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e1838540e57cd91578e898818e2ed12e7b63a78
ms.sourcegitcommit: 51d94d621e3411f35622e852b699275f526600dd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469667"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Passaggio dal connettore Skype for business online al modulo di PowerShell Teams

Per cambiare l'uso di Skype for Business Online Connector con il modulo teams PowerShell per gestire i team, è necessario aggiornare gli script di PowerShell esistenti. Questo articolo illustra come eseguire questa operazione.

1. Installare il modulo di PowerShell più recente di teams. Per i passaggi, vedere [installare Microsoft teams PowerShell](teams-powershell-install.md).
2. Disinstallare Skype for Business Online Connector. A questo scopo, nel pannello di controllo, vai a **programmi e funzionalità**, seleziona **Skype for business online, modulo di Windows PowerShell**e quindi scegli **Disinstalla**. 
3. Negli script di PowerShell modificare il nome del modulo a cui si fa riferimento in ```Import-Module``` from ```SkypeOnlineConnector``` o ```LyncOnlineConnector``` to ```MicrosoftTeams``` .

    Ad esempio, cambia ```Import-Module -Name SkypeOnlineConnector``` in ```Import-Module -Name MicrosoftTeams``` .

> [!NOTE]
> Gli amministratori devono continuare a usare [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) e importare la sessione prima di usare i cmdlet di Skype for business online. 

## <a name="related-topics"></a>Argomenti correlati

[Installare Microsoft teams PowerShell](teams-powershell-install.md)

[Gestire teams con teams PowerShell](teams-powershell-managing-teams.md)

[Note sulla versione di PowerShell per Teams](teams-powershell-release-notes.md)

[Informazioni di riferimento sui cmdlet di Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Informazioni di riferimento sui cmdlet di Skype for business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
