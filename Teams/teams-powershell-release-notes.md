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
ms.openlocfilehash: 9687dcdca15507caad0c52ef13feb2c12fb61e9a
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768340"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Note sulla versione di Microsoft Teams PowerShell

Questa pagina fornisce il log delle modifiche più recente di PowerShell di Teams per i rilasci disponibilità generale e anteprima pubblica.

## <a name="release-notes"></a>Note sulla versione

> [!NOTE]
> **-preview nella** colonna della versione seguente rappresenta gli aggiornamenti dell'anteprima pubblica di Teams PowerShell.

| Data | Versione | Aggiornamenti |
|------- | -------------------- | ------------------------------ |
| Aprile 2021 | [2.1.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.1.0-preview) | <li>È stata corretta la formattazione dei cmdlet esistenti, ad esempio Get-CsTeamsNetworkRoamingPolicy, Get-CsTeamsMeetingPolicy, Get-CsTeamsMessagingPolicy e altro ancora.</li><li>Elenco di parametri aggiornato dei cmdlet di gestione dei criteri.</li>|
| Marzo 2021 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>Usa MSAL per l'autenticazione & autorizzazione</li> <li>Connect-MicrosoftTeams è il punto di ingresso per tutti i cmdlet.</li><li>New-csOnlineSession non è più disponibile. È stato sostituito con Connect-MicrosoftTeams.</li><li>Enable-csonlinesessionforreconnection non è più necessario. La funzionalità è stata implementata in modo nativo nel modulo di PowerShell di Teams.</li> <li>Cmdlet del pacchetto di criteri di refactoring e aggiunta dell'assegnazione del pacchetto di gruppo</li><li>Miglioramenti significativi delle prestazioni per Get-Team cmdlet</li> <li>Opzione di registrazione e debug migliorata per i cmdlet esistenti </li> <li>Cmdlet per la gestione dei modelli aggiunti</li> <li>Deprecazione New-CsOnlineSession</li>|
| Febbraio 2021 | [1.1.11-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>Cmdlet per la gestione dei modelli aggiunti</li><li>Miglioramenti di mezzo e batch per Get-Team cmdlet</li> <li>Opzione di registrazione e debug migliorata per i cmdlet esistenti </li> <li>Cmdlet per il refactoring dei pacchetti di criteri</li>|
| Dicembre 2020 | [1.1.10-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>Aggiornamenti al cmdlet New-team con un aumento dei tentativi e della durata della sospensione</li>|
| Dicembre 2020 | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Aggiornamenti per l'integrazione di Skype for Business Online</li><li>Correzione della richiesta di duplicazione con Connect-Microsoft Teams</li>|
| Novembre 2020 | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>Aggiunge cmdlet per i pacchetti di criteri personalizzati</li><li>Correzioni per i comandi di caricamento della gerarchia di destinazione</li>|
| Novembre 2020 | [1.1.7-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>Usa MSAL per l'autenticazione & autorizzazione</li><li>Cmdlet del pacchetto di criteri di refactoring e aggiunta dell'assegnazione del pacchetto di gruppo</li><li>Comandi di caricamento della gerarchia di destinazione di refactoring per usare un modello asincrono</li> <li>All'utente verrà richiesto due volte durante l'autenticazione iniziale quando non usa il parametro -credential. Gli utenti possono passare le credenziali usando il parametro -credential per evitare una richiesta di duplicazione. Questo comportamento verrà risolto nella versione successiva.</li> |
| Settembre 2020 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Integrazione di Skype for Business Online Connector</li> |
| Settembre 2020 | [1.1.5-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Integrazione di Skype for Business Online Connector</li> |
| Luglio 2020 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>Cmdlet per [l'assegnazione di Criteri di gruppo aggiunti](./assign-policies.md#assign-a-policy-to-a-group)</li> |
| Giugno 2020 | [1.1.3-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Integrazione di Skype for Business Online Connector<li>Get-Team ottimizzazioni<li>Maggiore affidabilità</li> |
| Giugno 2020 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Aggiunta del precaricamento del cmdlet<li>Ottimizzazioni di .Net Framework</li>   |
| Aprile 2020 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Authenticode e firma dell'assembly<li>Aggiunta di Get-CsPolicyPackage<li>Aggiunta di Get-CsUserPolicyPackage<li>Aggiunta di Get-CsUserPolicyPackageRecommendation<li>Aggiunta di Grant-CsUserPolicyPackage<li>Aggiunta di New-CsBatchPolicyPackageAssignmentOperation<li>Aggiunta di Set-TeamArchivedState<li>Aggiunta di Set-TeamPicture<li>Rimosso Get-TeamHelp</li>  |
| Marzo 2020 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>Aggiunta di New-CsBatchPolicyAssignmentOperation</li> |
| Febbraio 2020 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team ottimizzazioni</li>  |

## <a name="related-topics"></a>Argomenti correlati

[Panoramica di Teams PowerShell](teams-powershell-overview.md)

[Installazione di Teams PowerShell](teams-powershell-install.md)

[Gestione di Teams con Teams PowerShell](teams-powershell-managing-teams.md)

[Informazioni di riferimento sul cmdlet di Microsoft Teams](/powershell/teams/?view=teams-ps)

[Informazioni di riferimento sul cmdlet di Skype for Business](/powershell/skype/intro?view=skype-ps)
