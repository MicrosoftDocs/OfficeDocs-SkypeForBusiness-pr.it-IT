---
title: Installare la versione non definitiva del modulo di PowerShell Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: brandber
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Seguire questa procedura per installare la versione preliminare del modulo teams PowerShell dalla raccolta di test di PowerShell.
ms.openlocfilehash: 1d85fac2ee6a1c8565f8482f7208a2f5ae33db60
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321769"
---
# <a name="install-the-pre-release-version-of-the-teams-powershell-module"></a>Installare la versione non definitiva del modulo di PowerShell Teams

In questo articolo viene descritto come installare la versione più recente di pre-rilascio del modulo teams PowerShell dalla [raccolta di test di PowerShell](https://www.poshtestgallery.com/packages/MicrosoftTeams/). È necessaria la versione preliminare del modulo di PowerShell teams in scenari in cui i cmdlet per la gestione di una caratteristica teams non sono supportati nella versione in generale disponibile del modulo e sono disponibili solo nella versione precedente al rilascio.

Seguire questa procedura per installare la versione più recente di pre-rilascio del modulo di PowerShell teams dalla raccolta di test di PowerShell.

> [!NOTE]
> Non installare il modulo teams PowerShell dalla raccolta di test di PowerShell affiancata con una versione del modulo dalla [raccolta di PowerShell pubblica](https://www.powershellgallery.com/packages/MicrosoftTeams/). Seguire questa procedura per disinstallare prima il modulo di PowerShell teams dalla raccolta di PowerShell pubblica e quindi installare la versione più recente del modulo dalla raccolta di test di PowerShell.

1. Chiudere tutte le sessioni di PowerShell esistenti.
2. Avviare una nuova istanza del modulo di Windows PowerShell.
3. Eseguire la procedura seguente per disinstallare il modulo di PowerShell teams dalla raccolta di PowerShell pubblica:

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. Chiudere tutte le sessioni di PowerShell esistenti.
5. Avviare di nuovo il modulo di Windows PowerShell e quindi eseguire la procedura seguente per registrare la raccolta di test di PowerShell come origine attendibile:

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. Eseguire la procedura seguente per installare il modulo di PowerShell più recente di teams dalla raccolta di test di PowerShell:

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. Eseguire le operazioni seguenti per verificare che la versione più recente del modulo di PowerShell teams della raccolta di test di PowerShell sia installata correttamente:

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a>Aggiornamento alla versione più recente del modulo di PowerShell teams dalla raccolta di test di PowerShell

Se il modulo teams PowerShell è già stato installato dalla raccolta test di PowerShell, eseguire la procedura seguente per aggiornare la versione più recente.

1. Chiudere tutte le sessioni di PowerShell esistenti.
2. Avviare una nuova istanza del modulo di Windows PowerShell.
3. Eseguire la procedura seguente per aggiornare la versione attualmente installata del modulo di PowerShell teams dalla raccolta di test di PowerShell:

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. Eseguire le operazioni seguenti per verificare che la versione più recente del modulo di PowerShell teams della raccolta di test di PowerShell sia installata correttamente:

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
