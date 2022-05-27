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
ms.openlocfilehash: 58d64a64fd7c9714e84042e4e1aa1be3eb4505db
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65682007"
---
# <a name="install-microsoft-teams-powershell-module"></a>Installare Microsoft Teams modulo di PowerShell

Questo articolo spiega come installare il modulo di Microsoft Teams PowerShell usando PowerShell Gallery. Il modulo Microsoft Teams PowerShell è supportato in tutte le piattaforme Windows. Mac e Linux non sono supportati.

## <a name="requirements"></a>Requisiti

Microsoft Teams modulo di PowerShell richiede PowerShell 5.1 o versione successiva in tutte le piattaforme. Installare [l'ultima versione di PowerShell](/powershell/scripting/install/installing-powershell) disponibile per il sistema operativo.

Per controllare la versione di PowerShell, eseguire il comando seguente da una sessione di PowerShell:

```powershell
$PSVersionTable.PSVersion
```

È consigliabile usare il cmdlet Install-Module per installare il modulo Microsoft Teams PowerShell.

Se PowerShell Gallery (PSGallery) non è configurato come archivio attendibile per **PowerShellGet**, la prima volta che si usa la PSGallery viene visualizzato il messaggio seguente:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Rispondi **Sì** o **Sì a Tutti** per continuare l'installazione.

## <a name="installing-using-the-powershellgallery"></a>Installazione con PowerShellGallery

Microsoft Teams modulo di PowerShell è attualmente supportato per l'uso con PowerShell 5.1 in Windows. Seguire questa procedura per installare il modulo:

- Eseguire [l'aggiornamento a Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell). Se si usa Windows 10 versione 1607 o successiva, è già installato PowerShell 5.1.
- Installare [.NET Framework 4.7.2](/dotnet/framework/install) o versione successiva.
- Eseguire il comando seguente per installare l'ultima versione di PowerShellGet:

  ```powershell
  Install-Module -Name PowerShellGet -Force -AllowClobber
  ```

- Installare il modulo Teams PowerShell.

  ```powershell
  Install-Module -Name MicrosoftTeams -Force -AllowClobber
  ```

## <a name="offline-installation"></a>Installazione offline

In alcuni ambienti, non è possibile connettersi al PowerShell Gallery. In queste situazioni, segui questi [passaggi di installazione manuale](https://aka.ms/psgallery-manualdownload).

## <a name="sign-in"></a>Accedi

Per iniziare a usare Microsoft Teams modulo di PowerShell, accedere con le credenziali di Azure.

```PowerShell
Connect-MicrosoftTeams
```

## <a name="update-teams-powershell-module"></a>Aggiornare Teams modulo di PowerShell

Per aggiornare qualsiasi modulo di PowerShell, è consigliabile usare lo stesso metodo usato per installare il modulo. Ad esempio, se hai usato in origine Install-Module, devi usare [Update-Module](/powershell/module/powershellget/update-module) per ottenere la versione più recente.

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Se Teams PowerShell è già stato importato nella sessione di PowerShell, l'aggiornamento del modulo avrà esito negativo. Chiudere PowerShell e riaprire una nuova sessione di PowerShell con privilegi elevati.

## <a name="uninstall-teams-powershell"></a>Disinstallare Teams PowerShell

Per disinstallare Microsoft Teams PowerShell, aprire un nuovo prompt dei comandi di PowerShell ed eseguire le operazioni seguenti:

```powershell
Uninstall-Module MicrosoftTeams

# Uninstall all versions of the module
Uninstall-Module MicrosoftTeams -Allversions
```

## <a name="next-steps"></a>Passaggi successivi

Ora puoi gestire Microsoft Teams usando Microsoft Teams PowerShell. Per informazioni introduttive, vedere [Gestione di Teams con Teams PowerShell](teams-powershell-managing-teams.md).

## <a name="related-topics"></a>Argomenti correlati

[Gestione di Teams con Teams PowerShell](teams-powershell-managing-teams.md)

[Note sulla versione di Teams PowerShell](teams-powershell-release-notes.md)

[riferimento ai cmdlet di Microsoft Teams](/powershell/teams/)

[riferimento ai cmdlet di Skype for Business](/powershell/skype/intro)
