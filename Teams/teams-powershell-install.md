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
description: Informazioni sull'uso dei controlli di PowerShell per la gestione Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 99af6bc71bdd25375f6165f1e645bf4626dd3123
ms.sourcegitcommit: 2044fdcb0c5db10dbc77c5d66e382c1b927ccdc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/01/2022
ms.locfileid: "63039974"
---
# <a name="install-microsoft-teams-powershell-module"></a>Installare Microsoft Teams Modulo di PowerShell

Questo articolo spiega come installare il modulo Microsoft Teams PowerShell usando la raccolta di PowerShell. Il Microsoft Teams PowerShell è supportato in tutte le Windows. Mac e Linux non sono supportati.

## <a name="requirements"></a>Requisiti

Microsoft Teams modulo di PowerShell richiede PowerShell 5.1 o versione successiva in tutte le piattaforme. Installare la  [versione più recente di PowerShelldisponibile](/powershell/scripting/install/installing-powershell)  per il sistema operativo. 

Per controllare la versione di PowerShell, eseguire il comando seguente all'interno di una sessione di PowerShell: 

```powershell
$PSVersionTable.PSVersion 
```
È consigliabile usare il cmdlet Install-Module per installare il modulo Microsoft Teams PowerShell. 
 
Se la raccolta di PowerShell (PSGallery) non è configurata come archivio attendibile per **PowerShellGet**, la prima volta che si usa PSGallery viene visualizzato il messaggio seguente:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Rispondere **Sì** o **Sì a Tutti** per continuare con l'installazione.

## <a name="installing-using-the-powershellgallery"></a>Installazione tramite PowerShellGallery

Microsoft Teams modulo di PowerShell è attualmente supportato per l'uso con PowerShell 5.1 in Windows. Seguire questa procedura per installare il modulo: 

- Eseguire [l'aggiornamento Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell). Se si è in Windows 10 versione 1607 o successiva, è già installato PowerShell 5.1. 
- Installare [.NET Framework 4.7.2](/dotnet/framework/install) o versione successiva. 
- Eseguire il comando seguente per installare la versione più recente di PowerShellGet:
 
```powershell
Install-Module -Name PowerShellGet -Force -AllowClobber
```
- Installare il modulo Teams PowerShell.

```powershell
Install-Module -Name MicrosoftTeams -Force -AllowClobber
```

## <a name="offline-installation"></a>Installazione offline 

In alcuni ambienti non è possibile connettersi alla raccolta di PowerShell. In queste situazioni, seguire questa procedura [di installazione manuale](https://aka.ms/psgallery-manualdownload).  

## <a name="sign-in"></a>Accedi

Per iniziare a lavorare con Microsoft Teams di PowerShell, accedere con le credenziali di Azure.

```PowerShell
Connect-MicrosoftTeams 
``` 

## <a name="update-teams-powershell-module"></a>Aggiornare Teams modulo di PowerShell

Per aggiornare qualsiasi modulo di PowerShell, è consigliabile usare lo stesso metodo usato per installare il modulo. Ad esempio, se è stato usato in origine Install-Module, è consigliabile usare [Update-Module](/powershell/module/powershellget/update-module) per ottenere la versione più recente.  

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Se Teams PowerShell è già stato importato nella sessione di PowerShell, l'aggiornamento del modulo non riuscirà. Chiudere PowerShell e ria aprire una nuova sessione di PowerShell con privilegi elevati.


## <a name="uninstall-teams-powershell"></a>Disinstallare Teams PowerShell

Per disinstallare Microsoft Teams PowerShell, aprire un nuovo prompt dei comandi di PowerShell ed eseguire quanto segue: 

```powershell
Uninstall-Module MicrosoftTeams

# Uninstall all versions of the module
Uninstall-Module MicrosoftTeams -Allversions 
```

## <a name="next-steps"></a>Passaggi successivi 

Ora si è pronti per gestire i Microsoft Teams usando Microsoft Teams PowerShell. Vedere [Gestione Teams con Teams PowerShell](teams-powershell-managing-teams.md) per iniziare. 

## <a name="related-topics"></a>Argomenti correlati

[Gestione Teams con Teams PowerShell](teams-powershell-managing-teams.md)

[Teams sulla versione di PowerShell](teams-powershell-release-notes.md)

[Microsoft Teams di cmdlet](/powershell/teams/?view=teams-ps)

[Skype for Business cmdlet](/powershell/skype/intro?view=skype-ps)
