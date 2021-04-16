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
description: Informazioni sull'uso dei controlli di PowerShell per gestire Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 448658fb844052815e14b85e0c70a33cb737b72d
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768355"
---
# <a name="microsoft-teams-powershell-overview"></a>Panoramica di Microsoft Teams PowerShell

Microsoft Teams PowerShell è un set di cmdlet per la gestione di Teams direttamente dalla riga di comando di PowerShell. Scritto in .NET Standard, Teams PowerShell funziona in PowerShell 5.1 in Windows, PowerShell 6.x e versioni successive in tutte le piattaforme, tra cui Azure Cloud Shell.

Prima di iniziare a usare PowerShell, è necessario [installarlo.](teams-powershell-install.md) 

> [!WARNING]
> Esistono problemi noti con PowerShell 7 e Teams PowerShell. È consigliabile usare PowerShell 5.1 finché i problemi non vengono risolti.

## <a name="releases"></a>Rilasci


Teams PowerShell è disponibile nella [raccolta di PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) in due tipi di rilascio.

- **Disponibilità generale:** cmdlet pronti per la produzione, aggiornati mensilmente.

- **Anteprima pubblica:** accesso anticipato alle funzionalità. Può essere aggiornato più frequentemente rispetto a GA.

Per informazioni dettagliate sulle aggiunte di funzionalità e sui miglioramenti per entrambi i rilasci, leggere le note sulla versione [di PowerShell di Teams.](teams-powershell-release-notes.md)


## <a name="manage-teams-with-powershell"></a>Gestire Teams con PowerShell

I moduli di PowerShell di Teams verranno utilizzati per gestire completamente Teams:

- [Modulo Di PowerShell di Microsoft Teams:](https://www.powershellgallery.com/packages/MicrosoftTeams/)il modulo di PowerShell di Teams contiene cmdlet per la gestione di team, chat e canali.

> [!NOTE]
> La versione pubblica di [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) 2.0 o successiva include tutti i cmdlet di Skype for Business Online Connector, che forniscono un unico modulo per la gestione di PowerShell di Teams.

- [Connettore PowerShell](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)di Skype for Business: il connettore di PowerShell di Skype for Business fa ora parte del modulo di PowerShell di Teams.

Per una guida completa alla gestione di Teams con questi moduli, vedere [Gestire Teams con Teams PowerShell.](teams-powershell-managing-teams.md)


## <a name="related-topics"></a>Argomenti correlati

[Installazione di Teams PowerShell](teams-powershell-install.md)

[Gestione di Teams con Teams PowerShell](teams-powershell-managing-teams.md)

[Note sulla versione di PowerShell di Teams](teams-powershell-release-notes.md)

[Informazioni di riferimento sul cmdlet di Microsoft Teams](/powershell/teams/?view=teams-ps)

[Informazioni di riferimento sul cmdlet di Skype for Business](/powershell/skype/intro?view=skype-ps)

[Usare i ruoli di amministratore di Microsoft Teams per gestire Teams](using-admin-roles.md)
