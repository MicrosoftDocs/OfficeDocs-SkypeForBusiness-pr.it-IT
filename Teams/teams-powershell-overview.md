---
title: Panoramica di Microsoft Teams PowerShell
ms.reviewer: ''
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Informazioni su come usare i controlli di PowerShell per gestire Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6c2c626d61a10437fc5bb349dd128415d64448a7
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569022"
---
# <a name="microsoft-teams-powershell-overview"></a>Panoramica di Microsoft Teams PowerShell

Microsoft Teams PowerShell è un set di cmdlet per la gestione di Teams direttamente dalla riga di comando di PowerShell. Scritto in .NET Standard, Teams PowerShell funziona su PowerShell 5.1 su Windows, PowerShell 6.x e versioni successive su tutte le piattaforme, tra cui Azure Cloud Shell.

Prima di iniziare a usare PowerShell, è necessario [installarlo.](teams-powershell-install.md) 

> [!WARNING]
> Ci sono problemi noti con PowerShell 7 e PowerShell di Teams. È consigliabile usare PowerShell 5.1 finché i problemi non verranno risolti.

## <a name="releases"></a>Rilasci


Teams PowerShell è disponibile nella [Raccolta PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) in due tipi di rilascio.

- **Disponibilità generale:** cmdlet pronti per la produzione, aggiornati mensilmente.

- **Anteprima pubblica:** accesso anticipato alle funzionalità. Possono essere aggiornati più frequentemente rispetto a Ga.

Per informazioni dettagliate sulle funzionalità aggiunte e i miglioramenti per entrambi i rilasci, leggere le note sulla versione [di Teams PowerShell.](teams-powershell-release-notes.md)


## <a name="manage-teams-with-powershell"></a>Gestire Teams con PowerShell

Userai i moduli di PowerShell di Teams per gestire completamente Teams:

- [Modulo Di PowerShell di Microsoft Teams:](https://www.powershellgallery.com/packages/MicrosoftTeams/)il modulo PowerShell di Teams contiene i cmdlet per la gestione di team, chat e canali.

> [!NOTE]
> La [versione pubblica di Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) 1.1.6 o successiva è integrata con Skype for Business Online Connector, che fornisce un singolo modulo per la gestione di PowerShell di Teams.

- [Connettore PowerShell di Skype for Business:](https://www.microsoft.com/download/details.aspx?id=39366)il connettore Di PowerShell di Skype for Business ora fa parte del modulo PowerShell di Teams.

Per una guida completa alla gestione di Teams con questi moduli, vedere [Gestire Teams con PowerShell di Teams.](teams-powershell-managing-teams.md)


## <a name="related-topics"></a>Argomenti correlati

[Installazione di Teams PowerShell](teams-powershell-install.md)

[Gestione di Teams con PowerShell di Teams](teams-powershell-managing-teams.md)

[Note sulla versione di PowerShell di Teams](teams-powershell-release-notes.md)

[Informazioni di riferimento per i cmdlet di Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Informazioni di riferimento per i cmdlet di Skype for Business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Usare i ruoli di amministratore di Microsoft Teams per gestire Teams](using-admin-roles.md)
