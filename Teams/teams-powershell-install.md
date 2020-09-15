---
title: Installare Microsoft teams PowerShell
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
description: Informazioni su come usare i controlli di PowerShell per la gestione di Microsoft teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f008d154099c57376fca914d576d7c9df4487780
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814465"
---
# <a name="install-microsoft-teams-powershell"></a>Installare Microsoft teams PowerShell

Questo articolo spiega come installare il modulo di PowerShell di Microsoft teams usando [PowerShellGet](/powershell/scripting/gallery/installing-psget). Queste istruzioni funzionano in [Azure cloud Shell](/azure/cloud-shell/overview), Linux, MacOS e piattaforme Windows.

## <a name="requirements"></a>Requisiti

Teams PowerShell richiede PowerShell 5,1 o versioni successive in tutte le piattaforme. Installare la [versione più recente di PowerShell](/powershell/scripting/install/installing-powershell) disponibile per il sistema operativo.

> [!WARNING]
> Sono presenti problemi noti di PowerShell 7 e teams PowerShell. Per un'esperienza ottimale, è consigliabile usare PowerShell 5,1.

## <a name="install-the-teams-powershell-module"></a>Installare il modulo di PowerShell Teams

> [!NOTE]
> Per un'esperienza ottimale, usa la disponibilità generale (GA) o i moduli di anteprima pubblica, non entrambi. Non sono destinati a collaborare.


Usare i cmdlet **PowerShellGet** per installare il modulo di PowerShell teams. L'installazione del modulo per tutti gli utenti in un sistema richiede privilegi elevati. Avviare la sessione di PowerShell usando **Esegui come amministratore** in Windows o usare il `sudo` comando in MacOS o Linux:

```powershell
Install-Module MicrosoftTeams
```

Per impostazione predefinita, la raccolta di PowerShell (PSGallery) non è configurata come repository attendibile per **PowerShellGet**. La prima volta che si usa PSGallery, viene visualizzato il messaggio seguente:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Rispondere **Sì** o **Sì a tutti** per continuare con l'installazione.


## <a name="install-teams-powershell-public-preview"></a>Installare l'anteprima pubblica di PowerShell Teams

> [!NOTE]
> Se si usa la versione di anteprima pubblica di teams PowerShell, è consigliabile disinstallare prima di tutto Skype for Business Online Connector.

L'installazione del modulo anteprima pubblica teams di PowerShell per tutti gli utenti di un sistema richiede privilegi elevati. Avviare la sessione di PowerShell usando **Esegui come amministratore** in Windows o usare il `sudo` comando in MacOS o Linux.

Se si usa PowerShell 5,1, è necessario aggiornare il modulo **PowerShellGet** in anticipo. Dopo l'aggiornamento di **PowerShellGet**, chiudere e riaprire una sessione di PowerShell con privilegi elevati per assicurarsi che venga caricato il **PowerShellGet** più recente.

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

Per installare teams PowerShell Public Preview, eseguire il comando di PowerShell seguente.

> [!NOTE]
> È possibile trovare la versione di anteprima più recente alla [raccolta di PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) o in PowerShell eseguendo "find-module MicrosoftTeams-AllowPrerelease"

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.3-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a>Installare il connettore Skype for business online

> [!NOTE]
>
> Skype for Business Online Connector fa attualmente parte del modulo di PowerShell più recente di teams.
> Se si usa l'ultima [versione pubblica di PowerShell per Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/), non è necessario installare il connettore Skype for business online.

```powershell
Import-Module -Name MicrosoftTeams
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a>Accedi

Per iniziare a usare teams PowerShell, accedere con le credenziali di Azure.

> [!NOTE]
> Se si usa la versione di [anteprima pubblica di PowerShell per Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)più recente, non è necessario installare il connettore Skype for business online.

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a>Aggiornare PowerShell Teams

Per aggiornare teams PowerShell, aprire un nuovo prompt dei comandi di PowerShell con privilegi elevati ed eseguire le operazioni seguenti:

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Se teams PowerShell è già stato importato nella sessione di PowerShell, l'aggiornamento del modulo non riuscirà. Chiudere PowerShell e riaprire una nuova sessione di PowerShell elevata.


## <a name="uninstall-teams-powershell"></a>Disinstallare teams PowerShell



Per disinstallare teams PowerShell, aprire un nuovo prompt dei comandi di PowerShell con privilegi elevati ed eseguire le operazioni seguenti:

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> Se teams PowerShell è già stato importato nella sessione di PowerShell, la disinstallazione del modulo non riuscirà. Chiudere PowerShell e riaprire una nuova sessione di PowerShell elevata.

## <a name="next-steps"></a>Passaggi successivi

Ora sei pronto per gestire teams usando PowerShell teams. Per iniziare, vedere [gestione di team con teams PowerShell](teams-powershell-managing-teams.md) .

## <a name="related-topics"></a>Argomenti correlati

[Gestione di team con PowerShell Teams](teams-powershell-managing-teams.md)

[Note sulla versione di PowerShell per Teams](teams-powershell-release-notes.md)

[Informazioni di riferimento sui cmdlet di Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Informazioni di riferimento sui cmdlet di Skype for business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
