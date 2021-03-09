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
description: Informazioni sulle ultime modifiche apportate in Teams PowerShell.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 24fa58e50ad42d3204fd4dc1269c8f59a3349d5e
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569398"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Note sulla versione di Microsoft Teams PowerShell

Questa pagina contiene il log delle modifiche più recente di Teams in PowerShell sia per la disponibilità generale che per le versioni di anteprima pubblica.

## <a name="release-notes"></a>Note sulla versione

> [!NOTE]
> **-preview nella** colonna della versione seguente rappresenta gli aggiornamenti all'anteprima pubblica di PowerShell di Teams.

| Data | Versione | Aggiornamenti |
|------- | -------------------- | ------------------------------ |
| Marzo 2021 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>Usa MSAL per l'autorizzazione & autenticazione</li><li>Cmdlet del pacchetto di criteri a refactoring e aggiunge l'assegnazione del pacchetto di gruppo</li><li>Miglioramenti al mezzo e alla gestione in batch Get-Team cmdlet</li> <li>Opzione di registrazione e debug migliorata per i cmdlet esistenti </li> <li>Cmdlet di gestione dei modelli aggiunti</li> <li>Deprecazione dei New-CsOnlineSession</li>|
| Febbraio 2021 | [Anteprima 1.1.11](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>Cmdlet di gestione dei modelli aggiunti</li><li>Miglioramenti al mezzo e alla gestione in batch Get-Team cmdlet</li> <li>Opzione di registrazione e debug migliorata per i cmdlet esistenti </li> <li>Cmdlet del pacchetto di criteri a cui è stato eseguito il refactoring</li>|
| Dicembre 2020 | [Anteprima 1.1.10](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>Aggiornamenti al cmdlet del nuovo team con un maggior numero di tentativi e la durata della sospensione</li>|
| Dicembre 2020 | [Anteprima 1.1.9](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Aggiornamenti per l'integrazione con Skype for Business Online</li><li>Correzione per la richiesta di duplicazione con Connect-Microsoft Teams</li>|
| Novembre 2020 | [Anteprima 1.1.8](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>Aggiunge cmdlet personalizzati per il pacchetto di criteri</li><li>Correzioni per i comandi di caricamento della gerarchia di destinazione</li>|
| Novembre 2020 | [Anteprima 1.1.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>Usa MSAL per l'autorizzazione & autenticazione</li><li>Cmdlet del pacchetto di criteri a refactoring e aggiunge l'assegnazione del pacchetto di gruppo</li><li>Comandi di caricamento della gerarchia di destinazione a refactoring per usare un modello asincrono</li> <li>All'utente verrà richiesto due volte durante l'autenticazione iniziale se non usa il parametro -credential. Gli utenti possono passare le credenziali usando il parametro -credential per evitare la richiesta di duplicazione. Questo comportamento verrà risolto nella prossima versione.</li> |
| Settembre 2020 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Integrazione di Skype for Business Online Connector</li> |
| Settembre 2020 | [Anteprima 1.1.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Integrazione di Skype for Business Online Connector</li> |
| Luglio 2020 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>Cmdlet [di assegnazione dei criteri di gruppo aggiunti](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)</li> |
| Giugno 2020 | [Anteprima 1.1.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Integrazione di Skype for Business Online Connector<li>Get-Team ottimizzazioni<li>Maggiore affidabilità</li> |
| Giugno 2020 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Aggiunta del precaricamento dei cmdlet<li>Ottimizzazioni di .Net Framework</li>   |
| Aprile 2020 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Firma di assembly e authenticode<li>Aggiunto Get-CsPolicyPackage<li>Aggiunto Get-CsUserPolicyPackage<li>Aggiunto Get-CsUserPolicyPackageRecommendation<li>Aggiunto Grant-CsUserPolicyPackage<li>Aggiunto New-CsBatchPolicyPackageAssignmentOperation<li>Aggiunto Set-TeamArchivedState<li>Aggiunto Set-TeamPicture<li>Rimosso Get-TeamHelp</li>  |
| Marzo 2020 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>Aggiunto New-CsBatchPolicyAssignmentOperation</li> |
| Febbraio 2020 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team ottimizzazioni</li>  |

### <a name="cmdlet-availability"></a>Disponibilità dei cmdlet

> [!NOTE]
> L'elenco nella tabella seguente include solo i cmdlet che fanno parte del modulo PowerShell di Teams in modo nativo. I cmdlet di Teams nel modulo S[kype for Business Online Connector](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps) non vengono visualizzati. Tuttavia, poiché questi cmdlet vengono migrati a livello nativo in Teams PowerShell, li aggiungiamo a questa tabella.

| Cmdlet | Disponibile in anteprima pubblica | Disponibile in ga |
| -| -- | --|
| [Add-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/add-teamchanneluser?view=teams-ps) | Sì | **No** |
| [Add-TeamUser](https://docs.microsoft.com/powershell/module/teams/add-teamuser?view=teams-ps) | Sì | Sì |
| [Add-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/add-teamsappinstallation?view=teams-ps) | Sì | **No**|
| [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) | Sì | Sì |
| [Disconnect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/disconnect-microsoftteams?view=teams-ps) | Sì | Sì |
| [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation?view=teams-ps) | Sì | Sì |
| [Get-CsGroupPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignmentoperation?view=teams-ps) | Sì | **No** |
| [Get-CsOnlinePowerShellEndpoint](https://docs.microsoft.com/powershell/module/teams/get-csonlinepowershellendpoint?view=teams-ps) | Sì | Sì |
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
| [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/teams/new-csonlinesession?view=teams-ps) | Sì | Sì |
| [Nuovo team](https://docs.microsoft.com/powershell/module/teams/new-team?view=teams-ps) | Sì | Sì |
| [New-TeamChannel](https://docs.microsoft.com/powershell/module/teams/new-channel?view=teams-ps) | Sì | Sì |
| [New-TeamsApp](https://docs.microsoft.com/powershell/module/teams/new-teamsapp?view=teams-ps) | Sì | Sì |
| [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment?view=teams-ps) | Sì | Sì |
| [Remove-Team](https://docs.microsoft.com/powershell/module/teams/remove-team?view=teams-ps) | Sì | Sì |
| [Remove-TeamChannel](https://docs.microsoft.com/powershell/module/teams/remove-teamchannel?view=teams-ps) | Sì | Sì |
| [Remove-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/remove-teamchanneluser?view=teams-ps) | Sì | **No** |
| [Remove-TeamsApp](https://docs.microsoft.com/powershell/module/teams/remove-teamsapp?view=teams-ps) | Sì | Sì |
| [Remove-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/remove-teamsappinstallation?view=teams-ps) | Sì | **No** |
| [Remove-TeamTargetingHierarchy](https://docs.microsoft.com/powershell/module/teams/remove-teamtargetinghierarchy?view=teams-ps) | Sì | **No**|
| [Remove-TeamUser](https://docs.microsoft.com/powershell/module/teams/remove-teamuser?view=teams-ps) | Sì | Sì |
| [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment?view=teams-ps) | Sì | **No** |
| [Set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps) | Sì | Sì |
| [Set-TeamArchivedState](https://docs.microsoft.com/powershell/module/teams/set-teamarchivedstate?view=teams-ps) | Sì | Sì |
| [Set-TeamChannel](https://docs.microsoft.com/powershell/module/teams/set-teamchannel?view=teams-ps) | Sì | Sì |
| [Set-TeamPicture](https://docs.microsoft.com/powershell/module/teams/set-teampicture?view=teams-ps) | Sì | Sì |
| [Set-TeamsApp](https://docs.microsoft.com/powershell/module/teams/set-teamapp?view=teams-ps) | Sì | Sì |
| [Set-TeamTargetingHierarchy](https://docs.microsoft.com/powershell/module/teams/set-teamtargetinghierarchy?view=teams-ps) | Sì | **No** |
| [Update-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/update-teamappinstallation?view=teams-ps) | Sì | **No** |

## <a name="related-topics"></a>Argomenti correlati

[Panoramica di Teams su PowerShell](teams-powershell-overview.md)

[Installazione di Teams PowerShell](teams-powershell-install.md)

[Gestione di Teams con PowerShell di Teams](teams-powershell-managing-teams.md)

[Informazioni di riferimento per i cmdlet di Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Informazioni di riferimento per i cmdlet di Skype for Business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
