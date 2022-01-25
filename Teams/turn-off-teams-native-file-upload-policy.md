---
title: Disattivare Teams criteri di Upload file nativi
author: danieasmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Informazioni su come creare, impostare, assegnare e modificare i criteri Teams file con PowerShell.
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 64bd9d23527ef1a63df4f258e89de5e60862a878
ms.sourcegitcommit: 9ef6e36eeba7db70971f4eb1a45f0ded394b1fe6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/25/2022
ms.locfileid: "62192495"
---
# <a name="turn-off-teams-native-file-upload-policy"></a>Disattivare Teams criteri di Upload file nativi

Microsoft Teams usa OneDrive e SharePoint (ODSP) per archiviare e condividere contenuti, ma alcune organizzazioni e utenti potrebbero preferire l'uso di provider di archiviazione di terze parti.  

Se l'organizzazione sceglie una terza parte per l'archiviazione del contenuto, è necessario disattivare il parametro nei criteri Teams ``NativeFileEntryPoints`` file. Questo parametro è abilitato per impostazione predefinita, che mostra l'opzione per caricare contenuto da ODSP Teams chat o canali.

Questo articolo illustra come creare, impostare, assegnare e rimuovere il ``NativeFileEntryPoints`` parametro usando PowerShell.

>[!NOTE]
>Quando il criterio File di Teams è disattivato, gli utenti non vedono i punti di accesso per OneDrive e SharePoint (ODSP) in Teams, ma la creazione di nuovi team e canali continuerà a attivare la generazione di raccolte SharePoint corrispondenti.

## <a name="prepare-to-update-the-teams-files-policy"></a>Preparare l'aggiornamento del criterio Teams file

### <a name="set-up-microsoft-powershell"></a>Configurare Microsoft PowerShell

Attualmente, questo criterio non può essere modificato nell'Teams di amministrazione. L'amministratore del tenant Microsoft 365 dell'organizzazione dovrà apportare le modifiche usando i cmdlet di PowerShell più avanti in questo articolo.

Per informazioni su come installare il modulo di Teams PowerShell usando la raccolta di PowerShell, vedere Installare Microsoft Teams [modulo di PowerShell.](teams-powershell-install.md)

Per installare o scaricare il modulo Teams PowerShell, vedere [Raccolta powershell per Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0).

Per altre informazioni su come configurare PowerShell per la gestione Teams, vedere Gestire Teams [con Microsoft Teams PowerShell.](teams-powershell-managing-teams.md)

### <a name="allow-third-party-apps-in-teams-admin-center"></a>Consentire app di terze parti nell'Teams di amministrazione

Questo passaggio non è necessario per modificare i criteri file di Teams, ma è necessario quando si è pronti per integrare il provider di archiviazione di terze parti nell'esperienza Teams utenti.

L Microsoft 365 amministratore tenant dovrà abilitare il criterio "Consenti app di terze parti" nell'interfaccia di amministrazione Teams di terze parti.

Per informazioni su come consentire app di terze parti o [personalizzate,](/microsoftteams/manage-apps#manage-org-wide-app-settings)vedere Gestire le impostazioni delle app a livello di organizzazione in Gestire le app nell'Microsoft Teams di amministrazione.

## <a name="turn-off-nativefileentrypoints-for-your-entire-tenant"></a>Disattivare NativeFileEntryPoints per l'intero tenant

Se si ``-Identity`` imposta il parametro ``Global`` su, le impostazioni dei criteri verranno applicate a tutti gli utenti dell'organizzazione.

### <a name="sample-powershell-policy-cmdlet-for-entire-tenant"></a>Cmdlet dei criteri di PowerShell di esempio per l'intero tenant

Questo comando di PowerShell di esempio imposta il ``NativeFileEntryPoints`` parametro su ``Disabled`` per l'intero tenant.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="check-the-status-of-your-tenant"></a>Controllare lo stato del tenant  

Per visualizzare lo stato corrente dei criteri file Teams tenant, usare il ``Get-CsTeamsFilesPolicy`` cmdlet.

```powershell
Get-CsTeamsFilesPolicy -Identity Global
```

### <a name="turn-on-or-turn-off-native-file-upload-point"></a>Attivare o disattivare il punto di caricamento dei file nativi

Per attivare o disattivare il punto di caricamento file nativo per l'intero tenant, impostare il ``NativeFileEntryPoints`` parametro su ``Enabled`` o ``Disabled`` .

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Enabled
```

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="remove-the-policy-for-your-users"></a>Rimuovere i criteri per gli utenti

Per rimuovere il criterio Teams file per gli utenti, usare il ``Remove-CsTeamsFilesPolicy`` cmdlet.

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

## <a name="turn-off-nativefileentrypoints-for-specific-users"></a>Disattivare NativeFileEntryPoints per utenti specifici

È anche possibile aggiornare i criteri Teams file per utenti specifici creando una nuova stringa di criteri Teams File e assegnando i criteri appena ``-Identity`` creati agli utenti.

### <a name="sample-powershell-policy-cmdlet-for-specific-users"></a>Cmdlet dei criteri di PowerShell di esempio per utenti specifici

Questo comando di PowerShell di esempio crea un nuovo con il nome ``CsTeamsFilesPolicy`` e il parametro impostato su ``-Identity`` ``UserPolicy`` ``NativeFileEntryPoints`` ``Disabled`` .

Quando a un utente viene assegnato il con , i punti di ingresso del file nativo ``CsTeamsFilesPolicy`` ``-Identity UserPolicy`` vengono disattivati.

```powershell
New-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Disabled
```

### <a name="assign-a-policy-to-user"></a>Assegnare un criterio all'utente

Dopo aver creato il nuovo criterio, è possibile assegnarlo agli utenti usando il ``Grant-CsTeamsFilesPolicy`` cmdlet.

```powershell
Grant-CsTeamsFilesPolicy  -identity "user email id" -PolicyName UserPolicy
```

### <a name="update-the-policy"></a>Aggiornare i criteri

Se è necessario modificare l'impostazione del nuovo criterio Teams ``UserPolicy`` file, usare il ``Set-CsTeamsFilePolicy`` cmdlet.

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### <a name="remove-the-policy-for-the-complete-list-of-users"></a>Rimuovere i criteri per l'elenco completo di utenti

Per rimuovere il criterio da tutti gli utenti assegnati al criterio Teams ``UserPolicy`` file, usare il ``Remove-CsTeamsFilesPolicy`` cmdlet.

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```
>[!NOTE]
> Dopo aver apportato modifiche ai criteri, è possibile visualizzare le modifiche fino a 12 ore nei client Teams utenti.
