---
title: Note sulla versione di Microsoft Teams PowerShell
ms.reviewer: brandber
author: BrandBer
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Informazioni sulle ultime modifiche in PowerShell di Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 159e73ff9f499538f830da6dd57c8ff7584e49cd
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874736"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Note sulla versione di Microsoft Teams PowerShell

Questa pagina fornisce il log delle modifiche più recente di PowerShell di Teams per i rilasci disponibilità generale e anteprima pubblica.

## <a name="release-notes"></a>Note sulla versione

> [!NOTE]
> **-preview nella** colonna della versione seguente rappresenta gli aggiornamenti dell'anteprima pubblica di Teams PowerShell.

| Data | Versione | Aggiornamenti |
|------- | -------------------- | ------------------------------ |
| Marzo 2021 | [2.0](https://www.powershellgallery.com/packages/MicrosoftTeams/) | <li>Connect-MicrosoftTeams è il punto di ingresso per tutti i cmdlet.</li><li>New-csOnlineSession non è più disponibile. È stato sostituito con Connect-MicrosoftTeams.</li><li>Enable-csonlinesessionforreconnection non è più necessario. La funzionalità è stata implementata in modo nativo nel modulo di PowerShell di Teams.</li>|
| Novembre 2020 | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Correzioni di bug e miglioramenti</li>|
| Novembre 2020 | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>Correzioni di bug e miglioramenti</li>|
| Marzo 2021 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>Usa MSAL per l'autenticazione & autorizzazione</li><li>Cmdlet del pacchetto di criteri di refactoring e aggiunta dell'assegnazione del pacchetto di gruppo</li><li>Miglioramenti significativi delle prestazioni per Get-Team cmdlet</li> <li>Opzione di registrazione e debug migliorata per i cmdlet esistenti </li> <li>Cmdlet per la gestione dei modelli aggiunti</li> <li>Deprecazione New-CsOnlineSession</li>|
| Febbraio 2021 | [1.1.11-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>Cmdlet per la gestione dei modelli aggiunti</li><li>Miglioramenti di mezzo e batch per Get-Team cmdlet</li> <li>Opzione di registrazione e debug migliorata per i cmdlet esistenti </li> <li>Cmdlet per il refactoring dei pacchetti di criteri</li>|
| Dicembre 2020 | [1.1.10-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>Aggiornamenti al cmdlet New-team con un aumento dei tentativi e della durata della sospensione</li>|
| Dicembre 2020 | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Aggiornamenti per l'integrazione di Skype for Business Online</li><li>Correzione della richiesta di duplicazione con Connect-Microsoft Teams</li>|
| Novembre 2020 | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>Aggiunge cmdlet per i pacchetti di criteri personalizzati</li><li>Correzioni per i comandi di caricamento della gerarchia di destinazione</li>|
| Novembre 2020 | [1.1.7-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>Usa MSAL per l'autenticazione & autorizzazione</li><li>Cmdlet del pacchetto di criteri di refactoring e aggiunta dell'assegnazione del pacchetto di gruppo</li><li>Comandi di caricamento della gerarchia di destinazione di refactoring per usare un modello asincrono</li> <li>All'utente verrà richiesto due volte durante l'autenticazione iniziale quando non usa il parametro -credential. Gli utenti possono passare le credenziali usando il parametro -credential per evitare una richiesta di duplicazione. Questo comportamento verrà risolto nella versione successiva.</li> |
| Settembre 2020 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Integrazione di Skype for Business Online Connector</li> |
| Settembre 2020 | [1.1.5-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Integrazione di Skype for Business Online Connector</li> |
| Luglio 2020 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>Cmdlet per [l'assegnazione di Criteri di gruppo aggiunti](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)</li> |
| Giugno 2020 | [1.1.3-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Integrazione di Skype for Business Online Connector<li>Get-Team ottimizzazioni<li>Maggiore affidabilità</li> |
| Giugno 2020 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Aggiunta del precaricamento del cmdlet<li>Ottimizzazioni di .Net Framework</li>   |
| Aprile 2020 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Authenticode e firma dell'assembly<li>Aggiunta di Get-CsPolicyPackage<li>Aggiunta di Get-CsUserPolicyPackage<li>Aggiunta di Get-CsUserPolicyPackageRecommendation<li>Aggiunta di Grant-CsUserPolicyPackage<li>Aggiunta di New-CsBatchPolicyPackageAssignmentOperation<li>Aggiunta di Set-TeamArchivedState<li>Aggiunta di Set-TeamPicture<li>Rimosso Get-TeamHelp</li>  |
| Marzo 2020 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>Aggiunta di New-CsBatchPolicyAssignmentOperation</li> |
| Febbraio 2020 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team ottimizzazioni</li>  |

### <a name="cmdlet-availability"></a>Disponibilità dei cmdlet

> [!NOTE]
> L'elenco nella tabella seguente include solo i cmdlet che fanno parte nativamente del modulo di PowerShell di Teams. I cmdlet di Teams nel modulo S[kype for Business Online Connector](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps) non vengono visualizzati. Tuttavia, poiché questi cmdlet vengono migrati in modo nativo in PowerShell di Teams, verranno aggiunti a questa tabella.

| Cmdlet | Disponibile nell'anteprima pubblica | Disponibile in Ga |
| -| -- | --|
| [Add-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/add-teamchanneluser?view=teams-ps) | Sì | **No** |
| [Add-TeamUser](https://docs.microsoft.com/powershell/module/teams/add-teamuser?view=teams-ps) | Sì | Sì |
| [Add-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/add-teamsappinstallation?view=teams-ps) | Sì | **No**|
| [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) | Sì | Sì |
| [Disconnetti-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/disconnect-microsoftteams?view=teams-ps) | Sì | Sì |
| [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation?view=teams-ps) | Sì | Sì |
| [Get-CsGroupPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment?view=teams-ps) | Sì | **No** |
| [Get-CsOnlinePowerShellEndpoint](https://docs.microsoft.com/powershell/module/skype/get-csonlineapplicationendpoint?view=skype-ps) | Sì | Sì |
| [Get-CsPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-cspolicypackage?view=teams-ps) | Sì | Sì |
| [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment?view=teams-ps) | Sì | Sì |
| [Get-CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackage?view=teams-ps) | Sì | Sì |
| [Get-CsUserPolicyPackageRecommendation](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackagerecommendation?view=teams-ps) | Sì | Sì |
| [Get-Team](https://docs.microsoft.com/powershell/module/teams/get-team?view=teams-ps) | Sì | Sì |
| [Get-TeamChannel](https://docs.microsoft.com/powershell/module/teams/get-teamchannel?view=teams-ps) | Sì | Sì|
| [Get-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/get-teamchanneluser?view=teams-ps) | Sì | **No** |
| [Get-TeamUser](https://docs.microsoft.com/powershell/module/teams/get-teamuser?view=teams-ps) | Sì | Sì |
| [Get-TeamsApp](https://docs.microsoft.com/powershell/module/teams/get-teamsapp?view=teams-ps) | Sì | Sì |
| [Get-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/get-teamsappinstallation?view=teams-ps) | Sì | **No** |
| [Grant-CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/grant-csuserpolicypackage?view=teams-ps) | Sì | Sì |
| [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) | Sì | Sì |
| [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps) | Sì | Sì |
| [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation?view=teams-ps) | Sì | Sì |
| [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession?view=skype-ps) | Sì | Sì |
| [Nuovo team](https://docs.microsoft.com/powershell/module/teams/new-team?view=teams-ps) | Sì | Sì |
| [New-TeamChannel](https://docs.microsoft.com/powershell/module/teams/new-teamchannel?view=teams-ps) | Sì | Sì |
| [New-TeamsApp](https://docs.microsoft.com/powershell/module/teams/new-teamsapp?view=teams-ps) | Sì | Sì |
| [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment?view=teams-ps) | Sì | Sì |
| [Remove-Team](https://docs.microsoft.com/powershell/module/teams/remove-team?view=teams-ps) | Sì | Sì |
| [Remove-TeamChannel](https://docs.microsoft.com/powershell/module/teams/remove-teamchannel?view=teams-ps) | Sì | Sì |
| [Remove-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/remove-teamchanneluser?view=teams-ps) | Sì | **No** |
| [Remove-TeamsApp](https://docs.microsoft.com/powershell/module/teams/remove-teamsapp?view=teams-ps) | Sì | Sì |
| [Remove-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/remove-teamsappinstallation?view=teams-ps) | Sì | **No** |
| [Remove-TeamTargetingHierarchy](https://docs.microsoft.com/microsoftteams/set-up-your-team-hierarchy#remove-your-hierarchy) | Sì | **No**|
| [Remove-TeamUser](https://docs.microsoft.com/powershell/module/teams/remove-teamuser?view=teams-ps) | Sì | Sì |
| [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment?view=teams-ps) | Sì | **No** |
| [Set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps) | Sì | Sì |
| [Set-TeamArchivedState](https://docs.microsoft.com/powershell/module/teams/set-teamarchivedstate?view=teams-ps) | Sì | Sì |
| [Set-TeamChannel](https://docs.microsoft.com/powershell/module/teams/set-teamchannel?view=teams-ps) | Sì | Sì |
| [Set-TeamPicture](https://docs.microsoft.com/powershell/module/teams/set-teampicture?view=teams-ps) | Sì | Sì |
| [Set-TeamsApp](https://docs.microsoft.com/powershell/module/teams/set-teamapp?view=teams-ps) | Sì | Sì |
| [Set-TeamTargetingHierarchy](https://docs.microsoft.com/powershell/module/teams/set-teamtargetinghierarchy?view=teams-ps) | Sì | **No** |
| [Update-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/update-teamappinstallation?view=teams-ps) | Sì | **No** |
| [Enable-CsOnlineSessionForReconnection](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/diagnose-problems-with-the-skype-for-business-online-connector) | **No** | **No** |


## <a name="related-topics"></a>Argomenti correlati

[Panoramica di Teams PowerShell](teams-powershell-overview.md)

[Installazione di Teams PowerShell](teams-powershell-install.md)

[Gestione di Teams con Teams PowerShell](teams-powershell-managing-teams.md)

[Informazioni di riferimento sul cmdlet di Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Informazioni di riferimento sul cmdlet di Skype for Business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
