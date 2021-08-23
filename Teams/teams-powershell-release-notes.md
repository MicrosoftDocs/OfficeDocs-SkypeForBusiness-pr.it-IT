---
title: Microsoft Teams Note sulla versione di PowerShell
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
description: Informazioni sulle modifiche più recenti in Teams PowerShell.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3fbffcf36e05aab945833bcf6a09e097d6c0c39
ms.sourcegitcommit: 2e1d97a3181fe12be43a0641039dca6077863f44
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/18/2021
ms.locfileid: "58380450"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft Teams Note sulla versione di PowerShell

Questa pagina fornisce le versioni più Teams log delle modifiche di PowerShell per i rilasci di Disponibilità generale e Anteprima pubblica.

## <a name="release-notes"></a>Note sulla versione

> [!NOTE]
> **-preview** nella colonna della versione seguente rappresenta gli aggiornamenti Teams anteprima pubblica di PowerShell.

| Data | Versione | Aggiornamenti |
|------- | -------------------- | ------------------------------ |
| Agosto 2021 | [2.5.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.5.0) |<li>Aggiornamenti per l'accesso a AccessToken con Connessione-MicrosoftTeams.</li><li>Correzioni per l'accesso interattivo Connect-MicrosoftTeams in Cloudshell.</li><li>Miglioramenti al cmdlet New-Team per gli scenari di creazione di team.</li><li>I cmdlet TeamsUnassignedNumberTreatment sono ora disponibili.</li><li>Get-CsCsOnlineDialInConferencingBridge e Set-CsOnlineDialInConferencingBridge.</li><li>Rilascia le versioni modernizzate di Get-CsTenant, Get-CsOnlineUser (solo con parametro -identity).</li>|
| Luglio 2021 | [2.4.1-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.4.1-preview) |<li>Concedere le modifiche ai cmdlet ora disponibili.</li><li>Vengono rilasciati nuovi cmdlet correlati alla voce.</li><li>Rimozione dell'autenticazione dell'identificazione personale del certificato per i cmdlet -Cs*.</li><li>Correzione della registrazione per la registrazione dei file di tutti i cmdlet.</li><li>Risolve i problemi con i cmdlet *TeamChannelUser.</li>|
| Giugno 2021 | [2.4.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.4.0-preview) |<li>Anteprima solo delle versioni modernizzate di Get-CsTenant, Get-CsOnlineUser (solo con parametro -identity), Get-CsOnlineDialInConferencingLanguagesSupported e Import-CsOnlineAudioFile.</li><li>Le versioni modernizzate di Get-CsOnlineDialInConferencingLanguagesSupported e Import-CsOnlineAudioFile dovrebbero funzionare in modo simile o analogo alle versioni remote.</li><li>Le versioni modernizzate di Get-CsTenant e Get-CsOnlineUser (se eseguite con il parametro -identity) non generano proprietà deprecate.</li><li>Le versioni modernizzate di Get-CsTenant e Get-CsOnlineUser (se eseguite con il parametro -identity) hanno alcune modifiche di formattazione rispetto alle parti dei contatori per i servizi remoti.</li><li>Rilasci \| [Get Set \| Grant New \| \| Remove]-CsTeamsAudioConferencingPolicy.</li><li>Rilascia Get-CsOnlineAudioFile e Remove-CsOnlineAudioFile cmdlet.</li><li>Set-TeamTargetingHierarchy, Remove-TeamTargetingHierarchy, Get-TeamTargetingHierarchyStatus sono ora disponibili per GCC clienti.</li><li>Corregge l'endpoint chiamato dal Get-TeamTargetingHierarchyStatus comando.</li>|
| Maggio 2021 | [2.3.2-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.2-preview) |<li>Supporto per l'accesso a AccessToken con Connessione-MicrosoftTeams. Aggiunto il parametro -AccessTokens che accetta la matrice di token. MsGraph e Teams token di risorsa sono necessari quando si usa il parametro AccessTokens.</li><li>Sono stati rimossi i parametri AadAccessToken e MsAccessToken.</li>|
| Maggio 2021 | [2.3.1](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.1) |<li>Aggiorna da . NETCore da 2.1 a 3.1</li><li>Cmdlet aggiunto per ottenere un'area geografica multipla per utenti e gruppi</li><li>Correzioni per l'autenticazione integrata di Windows per l'uso di -AccountId con Connect-MicrosoftTeams</li><li>I cmdlet TeamsCallHoldPolicy sono ora disponibili</li><li>Aggiornamenti ai parametri di input e ai formati di output di molti comandi</li><li>Risolve un problema di latenza di grandi dimensioni durante i comandi remoti</li><li>Caratteristiche dei pacchetti personalizzati GA</li>|
| Aprile 2021 | [2.2.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.2.0-preview) | <li>Correzioni per l'autenticazione Windows integrata per l'uso di -AccountId con Connessione-MicrosoftTeams.</li><li>È stato aggiunto un cmdlet per ottenere i dettagli degli eventi di notifica delle modifiche totali che possono essere inviati agli utenti.</li><li>È stato aggiunto un cmdlet per ottenere un'area geografica multipla per utenti e gruppi.</li><li>La gestione dei valori passati a TeamsEnvironment ha fatto distinzione tra maiuscole e minuscole. Questo problema è stato risolto.</li><li>Refactoring principale della gestione remota delle sessioni all'interno del modulo per facilitare gli unit test. Non devono essere presenti modifiche funzionali per gli amministratori del tenant.</li>|
| Aprile 2021 | [2.1.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.1.0-preview) | <li>È stata corretta la formattazione dell'output di alcuni cmdlet per la comunicazione remota, ad esempio Get-CsTeamsNetworkRoamingPolicy, Get-CsTeamsMeetingPolicy, Get-CsTeamsMessagingPolicy e altro ancora.</li><li>Elenco di parametri aggiornato dei cmdlet di gestione dei criteri.</li>|
| Marzo 2021 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>Usa MSAL per l'autenticazione & autorizzazione</li> <li>Connect-MicrosoftTeams è il punto di ingresso per tutti i cmdlet.</li><li>New-csOnlineSession non è più disponibile. È stato sostituito con Connessione-MicrosoftTeams.</li><li>Enable-csonlinesessionforreconnection non è più necessario. La funzionalità è stata implementata in modo nativo nel modulo Teams PowerShell.</li> <li>Cmdlet del pacchetto di criteri di refactoring e aggiunta dell'assegnazione del pacchetto di gruppo</li><li>Miglioramenti significativi delle prestazioni per Get-Team cmdlet</li> <li>Opzione di registrazione e debug migliorata per i cmdlet esistenti </li> <li>Cmdlet per la gestione dei modelli aggiunti</li> <li>Deprecazione New-CsOnlineSession</li>|
| Febbraio 2021 | [1.1.11-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>Cmdlet per la gestione dei modelli aggiunti</li><li>Miglioramenti di mezzo e batch per Get-Team cmdlet</li> <li>Opzione di registrazione e debug migliorata per i cmdlet esistenti </li> <li>Cmdlet del pacchetto di criteri di refactoring</li>|
| Dicembre 2020 | [1.1.10-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>Aggiornamenti al cmdlet New-team con un aumento dei tentativi e della durata della sospensione</li>|
| Dicembre 2020 | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Aggiornamenti per l'integrazione Skype for Business Online</li><li>Correzione per la richiesta di duplicazione con Connect-Microsoft Teams</li>|
| Novembre 2020 | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>Aggiunge cmdlet per i pacchetti di criteri personalizzati</li><li>Correzioni per i comandi di caricamento della gerarchia di destinazione</li>|
| Novembre 2020 | [1.1.7-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>Usa MSAL per l'autenticazione & autorizzazione</li><li>Cmdlet del pacchetto di criteri di refactoring e aggiunta dell'assegnazione del pacchetto di gruppo</li><li>Comandi di caricamento della gerarchia di destinazione di refactoring per usare un modello asincrono</li> <li>All'utente verrà richiesto due volte durante l'autenticazione iniziale quando non usa il parametro -credential. Gli utenti possono passare le credenziali usando il parametro -credential per evitare una richiesta di duplicazione. Questo comportamento verrà risolto nella versione successiva.</li> |
| Settembre 2020 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Skype for Business Integrazione di Online Connector</li> |
| Settembre 2020 | [1.1.5-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Skype for Business Integrazione di Online Connector</li> |
| Luglio 2020 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>Cmdlet per [l'assegnazione di Criteri di gruppo aggiunti](./assign-policies.md#assign-a-policy-to-a-group)</li> |
| Giugno 2020 | [1.1.3-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Skype for Business Integrazione di Online Connector<li>Get-Team ottimizzazioni<li>Maggiore affidabilità</li> |
| Giugno 2020 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Aggiunta del precaricamento del cmdlet<li>Ottimizzazioni di .Net Framework</li>   |
| Aprile 2020 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Authenticode e firma dell'assembly<li>Aggiunta di Get-CsPolicyPackage<li>Aggiunta di Get-CsUserPolicyPackage<li>Aggiunta di Get-CsUserPolicyPackageRecommendation<li>Aggiunta di Grant-CsUserPolicyPackage<li>Aggiunta di New-CsBatchPolicyPackageAssignmentOperation<li>Aggiunta di Set-TeamArchivedState<li>Aggiunta di Set-TeamPicture<li>Rimosso Get-TeamHelp</li>  |
| Marzo 2020 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>Aggiunta di New-CsBatchPolicyAssignmentOperation</li> |
| Febbraio 2020 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team ottimizzazioni</li>  |

## <a name="related-topics"></a>Argomenti correlati

[Teams Panoramica di PowerShell](teams-powershell-overview.md)

[Installazione di Teams PowerShell](teams-powershell-install.md)

[Gestione Teams con Teams PowerShell](teams-powershell-managing-teams.md)

[Microsoft Teams cmdlet](/powershell/teams/?view=teams-ps)

[Skype for Business cmdlet](/powershell/skype/intro?view=skype-ps)
