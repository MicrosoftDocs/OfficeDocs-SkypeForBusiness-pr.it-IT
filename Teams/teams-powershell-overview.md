---
title: Panoramica di Microsoft teams PowerShell
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
description: Informazioni su come usare i controlli di PowerShell per gestire Microsoft teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5385430c7db8aab0adf1efbaec546134e9adf388
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "44943989"
---
# <a name="microsoft-teams-powershell-overview"></a>Panoramica di Microsoft teams PowerShell

Microsoft teams PowerShell è un set di cmdlet per la gestione dei team direttamente dalla riga di comando di PowerShell. Scritto in .NET standard, teams PowerShell funziona su PowerShell 5,1 in Windows, PowerShell 6. x e versioni successive in tutte le piattaforme, incluso Azure Shell.

Prima di poter iniziare a usare PowerShell, è necessario [installarlo](teams-powershell-install.md). 

> [!WARNING]
> Sono presenti problemi noti di PowerShell 7 e teams PowerShell. È consigliabile usare PowerShell 5,1 fino a quando non vengono risolti i problemi.

## <a name="releases"></a>Versioni


Teams PowerShell è disponibile nella [raccolta di PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) in due tipi di rilascio.

- **Disponibilità generale (GA)**: cmdlet pronti per la produzione, aggiornati mensilmente.

- **Anteprima pubblica**: accesso anticipato alle funzionalità. Può essere aggiornato più di frequente rispetto a GA.

Per informazioni dettagliate sulle aggiunte di funzionalità e sui miglioramenti per entrambe le versioni, leggere le [Note sulla versione di PowerShell](teams-powershell-release-notes.md)per i team.


## <a name="manage-teams-with-powershell"></a>Gestire team con PowerShell

Si utilizzeranno entrambi i moduli di PowerShell per gestire completamente i team:

- [Modulo di PowerShell per Microsoft teams](https://www.powershellgallery.com/packages/MicrosoftTeams/): il modulo di PowerShell teams contiene i cmdlet per la gestione di Team, chat e canali.

- [Modulo di PowerShell per Skype for business](https://www.microsoft.com/download/details.aspx?id=39366): il modulo di PowerShell per Skype for business contiene i cmdlet per gestire le funzionalità riunioni, sistema telefonico e criteri.

Per una guida completa alla gestione dei team che usano questi moduli, vedere [gestire team con PowerShell teams](teams-powershell-managing-teams.md).

> [!NOTE]
> La [versione di anteprima pubblica di PowerShell per Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/) più recente è integrata con Skype for Business Online Connector, che fornisce un singolo modulo per la gestione di PowerShell per Teams.

## <a name="related-topics"></a>Argomenti correlati

[Installazione di PowerShell per Teams](teams-powershell-install.md)

[Gestione di team con PowerShell Teams](teams-powershell-managing-teams.md)

[Note sulla versione di PowerShell per Teams](teams-powershell-release-notes.md)

[Informazioni di riferimento sui cmdlet di Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Informazioni di riferimento sui cmdlet di Skype for business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Usare i ruoli di amministratore di Microsoft teams per gestire Teams](using-admin-roles.md)
