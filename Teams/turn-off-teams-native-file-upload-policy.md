---
title: Disattivare Teams criteri di Upload file nativi
author: danieasmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Informazioni su come creare, impostare, assegnare e modificare i criteri di Teams file con PowerShell.
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2b6089e93b4754fa35edaa9befb5cfa6bb176238
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681907"
---
# <a name="turn-off-teams-native-file-upload-policy"></a>Disattivare Teams criteri di Upload file nativi

Microsoft Teams usa OneDrive e SharePoint per archiviare e condividere contenuti, ma alcune organizzazioni e utenti potrebbero preferire l'uso di provider di archiviazione di terze parti.  

Se l'organizzazione sceglie una terza parte per l'archiviazione del contenuto, è necessario disattivare il `NativeFileEntryPoints` parametro nei criteri File di Teams. Questo parametro è abilitato per impostazione predefinita, che mostra l'opzione per caricare contenuto da OneDrive o SharePoint a chat o canali Teams.

Questo articolo illustra come creare, impostare, assegnare e rimuovere il `NativeFileEntryPoints` parametro con PowerShell.

>[!NOTE]
>Quando il criterio File di Teams è disattivato, gli utenti non vedranno i punti di accesso per OneDrive e SharePoint in Teams, ma la creazione di nuovi team e canali continuerà ad attivare la generazione di raccolte SharePoint corrispondenti.

## <a name="prepare-to-update-the-teams-files-policy"></a>Preparare l'aggiornamento dei criteri File di Teams

### <a name="set-up-microsoft-powershell"></a>Configurare Microsoft PowerShell

Attualmente, questo criterio non può essere modificato nell'interfaccia di amministrazione di Teams. L'amministratore Microsoft 365 tenant dell'organizzazione dovrà apportare le modifiche usando i cmdlet di PowerShell descritti più avanti in questo articolo.

Per informazioni su come installare il modulo di Teams di PowerShell con PowerShell Gallery, vedere [Installare Microsoft Teams modulo di PowerShell](teams-powershell-install.md).

Per installare o scaricare il modulo Teams PowerShell, vedere [PowerShell Gallery for Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0).

Per altre informazioni su come configurare PowerShell per la gestione Teams, vedere [Gestire Teams con Microsoft Teams PowerShell](teams-powershell-managing-teams.md).

### <a name="allow-third-party-apps-in-teams-admin-center"></a>Consenti app di terze parti nel Centro Teams Amministrazione

Questo passaggio non è necessario per modificare i criteri file Teams, ma è necessario quando si è pronti per integrare il provider di archiviazione di terze parti nell'esperienza Teams degli utenti.

L'amministratore del tenant di Microsoft 365 dovrà abilitare i criteri "Consenti app di terze parti" nell'interfaccia di amministrazione di Teams.

Per informazioni su come consentire app di terze parti o personalizzate, vedere Gestire le impostazioni delle app a livello di organizzazione in [Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](/microsoftteams/manage-apps#manage-org-wide-app-settings).

## <a name="turn-off-nativefileentrypoints-for-your-entire-tenant"></a>Disattivare NativeFileEntryPoints per l'intero tenant

Se si imposta il `-Identity` parametro su `Global` , le impostazioni dei criteri verranno applicate a tutti gli utenti dell'organizzazione.

### <a name="sample-powershell-policy-cmdlet-for-entire-tenant"></a>Esempio di cmdlet dei criteri di PowerShell per l'intero tenant

Questo comando di PowerShell di esempio imposterà il parametro `Disabled` su per l'intero`NativeFileEntryPoints` tenant.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="check-the-status-of-your-tenant"></a>Controllare lo stato del tenant  

Per visualizzare lo stato corrente dei criteri file Teams del tenant, usare il `Get-CsTeamsFilesPolicy` cmdlet.

```powershell
Get-CsTeamsFilesPolicy -Identity Global
```

### <a name="turn-on-or-turn-off-native-file-upload-point"></a>Attivare o disattivare il punto di caricamento nativo dei file

Per attivare o disattivare il punto di caricamento nativo dei file per l'intero tenant, impostare il `NativeFileEntryPoints` parametro `Enabled` su o `Disabled`.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Enabled
```

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="remove-the-policy-for-your-users"></a>Rimuovere i criteri per gli utenti

Per rimuovere il criterio file Teams per gli utenti, usare il `Remove-CsTeamsFilesPolicy` cmdlet.

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

## <a name="turn-off-nativefileentrypoints-for-specific-users"></a>Disattivare NativeFileEntryPoints per utenti specifici

È anche possibile aggiornare il criterio file Teams per utenti specifici creando una nuova stringa di criteri `-Identity` File di Teams e assegnando il criterio appena creato agli utenti.

### <a name="sample-powershell-policy-cmdlet-for-specific-users"></a>Esempio di cmdlet dei criteri di PowerShell per utenti specifici

Questo comando di PowerShell di esempio crea un nuovo `CsTeamsFilesPolicy` con il `-Identity` nome as `UserPolicy` e il `NativeFileEntryPoints` parametro impostato su `Disabled`.

Quando a un utente viene assegnato `CsTeamsFilesPolicy` con `-Identity UserPolicy`, i punti di ingresso nativi del file verranno disattivati.

```powershell
New-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Disabled
```

### <a name="assign-a-policy-to-user"></a>Assegnare un criterio all'utente

Dopo aver creato il nuovo criterio, è possibile assegnarlo agli utenti usando il `Grant-CsTeamsFilesPolicy` cmdlet.

```powershell
Grant-CsTeamsFilesPolicy  -identity "user email id" -PolicyName UserPolicy
```

### <a name="update-the-policy"></a>Aggiornare i criteri

Se è necessario modificare l'impostazione del nuovo criterio file `UserPolicy`di Teams, usare il `Set-CsTeamsFilePolicy` cmdlet.

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### <a name="remove-the-policy-for-the-complete-list-of-users"></a>Rimuovere il criterio per l'elenco completo degli utenti

Per rimuovere il criterio da tutti gli utenti assegnati al criterio `UserPolicy`file di Teams, usare il `Remove-CsTeamsFilesPolicy` cmdlet.

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```
>[!NOTE]
> Dopo aver apportato modifiche al criterio, consentire fino a 12 ore per la visualizzazione delle modifiche nei client Teams degli utenti.
