---
title: Note sulla versione di PowerShell per Microsoft Teams
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
description: Informazioni sulle modifiche più recenti in teams PowerShell.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 41aa6cdf05901756bb2bcd13dbb8b9ad2cedabf6
ms.sourcegitcommit: a6c7a0cdbedf6cf32213d7636da52db71b4bac3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2020
ms.locfileid: "48937745"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Note sulla versione di PowerShell per Microsoft Teams

Questa pagina fornisce il log delle modifiche di PowerShell per i team più recenti sia per la disponibilità generale che per le versioni di anteprima pubblica.

## <a name="release-notes"></a>Note sulla versione

> [!NOTE]
> **-l'anteprima** nella colonna versione seguente rappresenta gli aggiornamenti dell'anteprima pubblica di PowerShell per Teams.

| Data | Versione | Aggiornamenti |
|------- | -------------------- | ------------------------------ |
| 2020 novembre | [1.1.7-anteprima](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>USA MSAL per l'autenticazione & autorizzazione</li><li>Cmdlet del pacchetto dei criteri rifattorizzati e aggiunta dell'assegnazione di un pacchetto di gruppo</li><li>Comandi di caricamento della gerarchia di destinazione rifattorizzati per l'uso di un modello asincrono</li> <li>L'utente verrà richiesto due volte durante l'autenticazione iniziale quando non usa il parametro-Credential. Gli utenti possono passare le credenziali usando il parametro-Credential per evitare una richiesta duplicata. Questo comportamento verrà risolto nella versione successiva.</li> |
| 2020 settembre | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Integrazione di Skype for Business Online Connector</li> |
| 2020 settembre | [1.1.5-Anteprima](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Integrazione di Skype for Business Online Connector</li> |
| 2020 luglio | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>Aggiunta di cmdlet per l' [assegnazione di criteri di gruppo](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)</li> |
| 2020 giugno | [1.1.3-Anteprima](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Integrazione di Skype for Business Online Connector<li>Ottimizzazioni Get-Team<li>Maggiore affidabilità</li> |
| 2020 giugno | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Aggiunta del precaricamento del cmdlet<li>Ottimizzazioni di .NET Framework</li>   |
| 2020 aprile | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Firma di Authenticode e assembly<li>Get-CsPolicyPackage aggiunti<li>Get-CsUserPolicyPackage aggiunti<li>Get-CsUserPolicyPackageRecommendation aggiunti<li>Grant-CsUserPolicyPackage aggiunti<li>New-CsBatchPolicyPackageAssignmentOperation aggiunti<li>Set-TeamArchivedState aggiunti<li>Set-TeamPicture aggiunti<li>Get-TeamHelp rimossi</li>  |
| 2020 marzo | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>New-CsBatchPolicyAssignmentOperation aggiunti</li> |
| Feb 2020 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Ottimizzazioni Get-Team</li>  |

### <a name="cmdlet-availability"></a>Disponibilità cmdlet

> [!NOTE]
> L'elenco nella tabella seguente include solo i cmdlet che fanno parte nativa del modulo di PowerShell teams. I cmdlet Teams nel[modulo connettore S kype for business online](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps) non vengono visualizzati. Tuttavia, dato che questi cmdlet vengono migrati in modo nativo in teams PowerShell, verranno aggiunti alla tabella.

| Cmdlet | Disponibile in anteprima pubblica | Disponibile in GA |
| -| -- | --|
| [Add-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/add-teamchanneluser?view=teams-ps) | Sì | **No** |
| [Add-TeamUser](https://docs.microsoft.com/powershell/module/teams/add-teamuser?view=teams-ps) | Sì | Sì |
| [Add-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/add-teamsappinstallation?view=teams-ps) | Sì | **No**|
| [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) | Sì | Sì |
| [Disconnetti-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/disconnect-microsoftteams?view=teams-ps) | Sì | Sì |
| [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation?view=teams-ps) | Sì | Sì |
| [Get-CsGroupPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignmentoperation?view=teams-ps) | Sì | **No** |
| [Get-CsOnlinePowerShellEndpoint](https://docs.microsoft.com/powershell/module/teams/get-csonlinepowershellendpoint?view=teams-ps) | Sì | Sì |
| [Get-CsPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-cspolicypackage?view=teams-ps) | Sì | Sì |
| [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment?view=teams-ps) | Sì | Sì |
| [Get-CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackage?view=teams-ps) | Sì | Sì |
| [Get-CsUserPolicyPackageRecommendation](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackagerecommendation?view=teams-ps) | Sì | Sì |
| [Get-team](https://docs.microsoft.com/powershell/module/teams/get-team?view=teams-ps) | Sì | Sì |
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
| [Rimuovi-Team](https://docs.microsoft.com/powershell/module/teams/remove-team?view=teams-ps) | Sì | Sì |
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

[Panoramica di PowerShell Teams](teams-powershell-overview.md)

[Installazione di PowerShell per Teams](teams-powershell-install.md)

[Gestione di team con PowerShell Teams](teams-powershell-managing-teams.md)

[Informazioni di riferimento sui cmdlet di Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Informazioni di riferimento sui cmdlet di Skype for business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
