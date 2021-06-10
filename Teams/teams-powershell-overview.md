---
title: Microsoft Teams Panoramica di PowerShell
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
ms.openlocfilehash: 448658fb844052815e14b85e0c70a33cb737b72d
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768355"
---
# <a name="microsoft-teams-powershell-overview"></a>Microsoft Teams Panoramica di PowerShell

Microsoft Teams PowerShell è un set di cmdlet per la gestione Teams direttamente dalla riga di comando di PowerShell. Scritto in .NET Standard, Teams PowerShell funziona in PowerShell 5.1 in Windows, PowerShell 6.x e versioni successive in tutte le piattaforme, tra cui Azure Cloud Shell.

Prima di iniziare a usare PowerShell, è necessario [installarlo.](teams-powershell-install.md) 

> [!WARNING]
> Esistono problemi noti con PowerShell 7 e Teams PowerShell. È consigliabile usare PowerShell 5.1 finché i problemi non vengono risolti.

## <a name="releases"></a>Rilasci


Teams PowerShell è disponibile nella [raccolta di PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) in due tipi di versione.

- **Disponibilità generale:** cmdlet pronti per la produzione, aggiornati mensilmente.

- **Anteprima pubblica:** accesso anticipato alle funzionalità. Può essere aggiornato più frequentemente rispetto a GA.

Per informazioni dettagliate sulle aggiunte di funzionalità e sui miglioramenti per entrambi i rilasci, leggere le note sulla Teams [sulla versione di PowerShell.](teams-powershell-release-notes.md)


## <a name="manage-teams-with-powershell"></a>Gestire Teams con PowerShell

Si useranno i moduli Teams PowerShell per gestire completamente Teams:

- [Microsoft Teams di PowerShell:](https://www.powershellgallery.com/packages/MicrosoftTeams/)il modulo Teams PowerShell contiene cmdlet per la gestione di team, chat e canali.

> [!NOTE]
> La Teams versione pubblica di [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) 2.0 o successiva include tutti i cmdlet di Skype for Business Online Connector, che forniscono un unico modulo per la gestione Teams PowerShell.

- [Skype for Business connettore di PowerShell:](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)il connettore Skype for Business PowerShell fa ora parte del Teams di PowerShell.

Per una guida completa alla gestione Teams questi moduli, vedere Gestire Teams [con Teams PowerShell.](teams-powershell-managing-teams.md)


## <a name="related-topics"></a>Argomenti correlati

[Installazione di Teams PowerShell](teams-powershell-install.md)

[Gestione Teams con Teams PowerShell](teams-powershell-managing-teams.md)

[Teams Note sulla versione di PowerShell](teams-powershell-release-notes.md)

[Microsoft Teams di cmdlet](/powershell/teams/?view=teams-ps)

[Skype for Business cmdlet](/powershell/skype/intro?view=skype-ps)

[Usare Microsoft Teams di amministratore per gestire i Teams](using-admin-roles.md)
