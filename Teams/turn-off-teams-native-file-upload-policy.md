---
title: Disattivare i criteri di caricamento di file nativi di Teams
author: danieasmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Informazioni su come creare, impostare, assegnare e modificare i criteri per i file di Teams con PowerShell.
audience: admin
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: 1993371099d0712d21106987f21575e85e181ad7
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268928"
---
# <a name="turn-off-teams-native-file-upload-policy"></a>Disattivare i criteri di caricamento di file nativi di Teams

Microsoft Teams usa OneDrive e SharePoint per archiviare e condividere contenuti, ma alcune organizzazioni e utenti potrebbero preferire l'uso di provider di archiviazione di terze parti.  

Se l'organizzazione sceglie una terza parte per l'archiviazione dei contenuti, è necessario disattivare il `NativeFileEntryPoints` parametro nei criteri File di Teams. Questo parametro è abilitato per impostazione predefinita, che mostra l'opzione per caricare contenuti da OneDrive o SharePoint alle chat o ai canali di Teams.

Questo articolo illustra come creare, impostare, assegnare e rimuovere il `NativeFileEntryPoints` parametro con PowerShell.

>[!NOTE]
>Quando il criterio File di Teams è disattivato, gli utenti non vedranno i punti di accesso per OneDrive e SharePoint in Teams, ma la creazione di nuovi team e canali continuerà ad attivare la generazione di raccolte SharePoint corrispondenti.

## <a name="prepare-to-update-the-teams-files-policy"></a>Preparare l'aggiornamento dei criteri File di Teams

### <a name="set-up-microsoft-powershell"></a>Configurare Microsoft PowerShell

Attualmente, questo criterio non può essere modificato nell'interfaccia di amministrazione di Teams. L'amministratore del tenant di Microsoft 365 dell'organizzazione dovrà apportare le modifiche usando i cmdlet di PowerShell descritti più avanti in questo articolo.

Informazioni su come installare il modulo Di Teams di PowerShell usando PowerShell Gallery leggendo [Installare il modulo PowerShell di Microsoft Teams](teams-powershell-install.md).

Per installare o scaricare il modulo PowerShell di Teams, vedere [PowerShell Gallery per Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0).

Per altre informazioni su come configurare PowerShell per la gestione di Teams, vedere [Gestire Teams con Microsoft Teams PowerShell](teams-powershell-managing-teams.md).

### <a name="allow-third-party-apps-in-teams-admin-center"></a>Consentire app di terze parti in Teams Amministrazione Center

Questo passaggio non è necessario per modificare i criteri file di Teams, ma è necessario quando si è pronti per integrare il provider di archiviazione di terze parti nell'esperienza di Teams degli utenti.

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

Per visualizzare lo stato corrente dei criteri per i file di Teams del tenant, usare il `Get-CsTeamsFilesPolicy` cmdlet.

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

Per rimuovere i criteri File di Teams per gli utenti, usare il `Remove-CsTeamsFilesPolicy` cmdlet.

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

## <a name="turn-off-nativefileentrypoints-for-specific-users"></a>Disattivare NativeFileEntryPoints per utenti specifici

È anche possibile aggiornare i criteri File di Teams per utenti specifici creando una nuova stringa di criteri `-Identity` File di Teams e assegnando il criterio appena creato agli utenti.

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

Se è necessario modificare l'impostazione dei nuovi criteri per i file `UserPolicy`di Teams, usare il `Set-CsTeamsFilePolicy` cmdlet.

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### <a name="remove-the-policy-for-the-complete-list-of-users"></a>Rimuovere il criterio per l'elenco completo degli utenti

Per rimuovere il criterio da tutti gli utenti assegnati al criterio `UserPolicy`File di Teams, usare il `Remove-CsTeamsFilesPolicy` cmdlet.

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```
>[!NOTE]
> Dopo aver apportato modifiche al criterio, consenti fino a 12 ore per la visualizzazione delle modifiche nei client di Teams degli utenti.
