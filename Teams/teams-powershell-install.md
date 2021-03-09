---
title: Installare Microsoft Teams PowerShell
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Informazioni su come usare i controlli di PowerShell per la gestione di Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a99967df019a91460bde5fd4e3e6e7aee15444d3
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569112"
---
# <a name="install-microsoft-teams-powershell"></a>Installare Microsoft Teams PowerShell

Questo articolo spiega come installare il modulo Microsoft Teams PowerShell tramite [PowerShellGet.](/powershell/scripting/gallery/installing-psget) Queste istruzioni funzionano su [piattaforme Azure Cloud Shell,](/azure/cloud-shell/overview)Linux, macOS e Windows.

## <a name="requirements"></a>Requisiti

Teams PowerShell richiede PowerShell 5.1 o versione successiva su tutte le piattaforme. Installare [l'ultima versione di PowerShell disponibile](/powershell/scripting/install/installing-powershell) per il sistema operativo in uso.

> [!WARNING]
> Ci sono problemi noti con PowerShell 7 e PowerShell di Teams. Per un'esperienza ottimale, è consigliabile usare PowerShell 5.1.

## <a name="install-the-teams-powershell-module"></a>Installare il modulo Teams di PowerShell

> [!NOTE]
> Per un'esperienza ottimale, usare i moduli Disponibilità generale (GA) o Anteprima pubblica, non entrambi. Non dovrebbero lavorare insieme.


Usare i **cmdlet PowerShellGet** per installare il modulo Di PowerShell di Teams. L'installazione del modulo per tutti gli utenti in un sistema richiede privilegi elevati. Avviare la sessione di PowerShell **con Esegui come amministratore** in Windows o usare il comando su `sudo` macOS o Linux:

```powershell
Install-Module MicrosoftTeams
```

Per impostazione predefinita, la raccolta di PowerShell (PSGallery) non è configurata come archivio attendibile per **PowerShellGet.** La prima volta che si usa PSGallery, viene visualizzato il messaggio seguente:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Rispondere **Sì** o **Sì a Tutti per** continuare l'installazione.


## <a name="install-teams-powershell-public-preview"></a>Installare Teams PowerShell Public Preview

> [!NOTE]
> Se si usa la versione Anteprima pubblica di Teams PowerShell, si consiglia vivamente di disinstallare prima Skype for Business Online Connector.

L'installazione del modulo di anteprima pubblica di Teams PowerShell per tutti gli utenti in un sistema richiede privilegi elevati. Avviare la sessione di PowerShell **con Esegui come amministratore** in Windows o usare il comando su `sudo` macOS o Linux.

Se si usa PowerShell 5.1, è necessario aggiornare il modulo **PowerShellGet** in anticipo. Dopo aver aggiornato **PowerShellGet,** chiudere e riaprire una sessione di PowerShell con privilegi elevati per assicurarsi che sia caricata **l'ultima sessione PowerShellGet.**

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

Per installare Teams PowerShell Public Preview, eseguire il comando di PowerShell riportato di seguito.

> [!NOTE]
> Puoi trovare l'ultima versione di anteprima nella Raccolta [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) o in PowerShell eseguendo "Find-Module MicrosoftTeams -AllowPrerelease"

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a>Installare Skype for Business Online Connector

> [!NOTE]
>
> Skype for Business Online Connector fa attualmente parte del più recente modulo PowerShell di Teams.
> Se si usa la versione pubblica più recente di [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)non è necessario installare Skype for Business Online Connector.


```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## <a name="sign-in"></a>Accedi

Per iniziare a lavorare con PowerShell di Teams, accedere con le credenziali di Azure.

> [!NOTE]
> Se si usa l'ultima versione di Anteprima pubblica di PowerShell per [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)non è necessario installare Skype for Business Online Connector.

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a>Aggiornare PowerShell di Teams

Per aggiornare Teams PowerShell, aprire un nuovo prompt dei comandi di PowerShell con privilegi elevati ed eseguire quanto segue:

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Se Teams PowerShell è già stato importato nella sessione di PowerShell, l'aggiornamento del modulo non riuscirà. Chiudere PowerShell e ria aprire una nuova sessione di PowerShell con privilegi elevati.


## <a name="uninstall-teams-powershell"></a>Disinstallare Teams PowerShell



Per disinstallare Teams PowerShell, aprire un nuovo prompt dei comandi di PowerShell con privilegi elevati ed eseguire quanto segue:

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> Se Teams PowerShell è già stato importato nella sessione di PowerShell, la disinstallazione del modulo non riesce. Chiudere PowerShell e ria aprire una nuova sessione di PowerShell con privilegi elevati.

## <a name="next-steps"></a>Passaggi successivi

Ora sei pronto per gestire Teams con Teams PowerShell. Per [informazioni introduttive, vedere Gestione dei team con PowerShell](teams-powershell-managing-teams.md) di Teams.

## <a name="related-topics"></a>Argomenti correlati

[Gestione di Teams con PowerShell di Teams](teams-powershell-managing-teams.md)

[Note sulla versione di PowerShell di Teams](teams-powershell-release-notes.md)

[Informazioni di riferimento per i cmdlet di Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Informazioni di riferimento per i cmdlet di Skype for Business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
