---
title: Modulo di Teams PowerShell - Versioni supportate
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Informazioni sulle versioni supportate del modulo PowerShell di Teams, usato per l'amministrazione di Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5ae244a16e934b70085b2193bee3ef21a277f7ed
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2022
ms.locfileid: "67397287"
---
# <a name="teams-powershell-module---supported-versions"></a>Modulo di Teams PowerShell - Versioni supportate

Le versioni del modulo Microsoft Teams PowerShell (TPM) della serie 4.x.x o successive sono le uniche versioni supportate al momento. Tutte le versioni precedenti sono completamente ritirate dal 15 giugno 2022 & smetteranno di funzionare (post del Centro messaggi per riferimento - MC350371). 

È consigliabile eseguire l'aggiornamento all'ultima versione del modulo di Teams PowerShell.


## <a name="important-notes"></a>Note importanti

- Le note sulla versione per tutte le versioni del modulo PowerShell di Teams sono disponibili nelle [note sulla versione di Teams PowerShell](teams-powershell-release-notes.md).

- Per aggiornare qualsiasi modulo di PowerShell, è consigliabile usare lo stesso metodo usato per installare il modulo. Ad esempio, se hai usato in origine Install-Module, devi usare [Update-Module](/powershell/module/powershellget/update-module) per ottenere la versione più recente.

  ```powershell
  Update-Module MicrosoftTeams
  ```

- Se si sta aggiornando da Teams PowerShell Module versione 1.1.6, aggiornare gli script da usare `Connect-MicrosoftTeams` al posto di `New-CsOnlineSession`.

- Durante l'aggiornamento, è consigliabile non usare TPM 4.x.x/3.x.x insieme alle versioni precedenti alla 3.0.0. Ad esempio, non è consigliabile usare le versioni 4.x.x & 2.6.0 insieme per operazioni amministrative diverse nella stessa organizzazione.

- Modifiche correlate
  - Aggiornamenti a Get-CsOnlineUser & Get-CsOnlineVoiceUser in TPM 3.x.x e versioni successive, maggiori dettagli in [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) & [Get-CsOnlineVoiceUser](/powershell/module/skype/get-csonlinevoiceuser) (post del Centro messaggi - MC340774).

  - Modifiche in arrivo per l'assegnazione del numero di telefono: maggiori dettagli in [Set-CsUser](/powershell/module/skype/set-csuser), [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser), [Set-CsOnlineApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) & [Set-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlinevoiceapplicationinstance) (post del Centro messaggi - MC316139).

  - Modifiche dei parametri in Get-CsTenant - maggiori dettagli in [Get-CsTenant](/powershell/module/skype/get-cstenant) (post del Centro messaggi - MC365397).
  
  - Se gli script usano cmdlet new/set di criteri o di configurazione con i parametri del tipo PSListModifier, è consigliabile usare la versione più recente (4.2.0 o successiva). Post del Centro messaggi per riferimento - MC397428.

  - [Nuovo| Get]-CsCloudCallDataConnection cmdlets are now supported from versions 4.6.0 or later (Message center post - MC408993).

- Durante l'uso di TPM 4.x.x o versione successiva, è consigliabile non usare i cmdlet deprecati o non supportati indicati [di seguito](#deprecated-cmdlets).

## <a name="deprecated-cmdlets"></a>Cmdlet deprecati

- Alcuni dei cmdlet deprecati di recente sono elencati di seguito. I dettagli dello stesso sono disponibili nelle rispettive documentazione pubbliche.
  - [Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  - [Get-CsOnlineDialInConferencingUserInfo](/powershell/module/skype/get-csonlinedialinconferencinguserinfo), [Get-CsOnlineDialInConferencingUserState](/powershell/module/skype/get-csonlinedialinconferencinguserstate), [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/enable-csonlinedialinconferencinguser), [Disable-CsOnlineDialInConferencingUser](/powershell/module/skype/disable-csonlinedialinconferencinguser)
  - [Get-CsOnlineDirectoryTenant](/powershell/module/skype/get-csonlinedirectorytenant)
  - [New-CsOnlineAudioFile](/powershell/module/skype/new-csonlineaudiofile)
  - [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint), [Set-CsOnlineApplicationEndpoint](/powershell/module/skype/set-csonlineapplicationendpoint), [New-CsOnlineApplicationEndpoint](/powershell/module/skype/new-csonlineapplicationendpoint), [Remove-CsOnlineApplicationEndpoint](/powershell/module/skype/remove-csonlineapplicationendpoint), Switch-CsOnlineApplicationEndpoint
  - [Get-CsOnlineTelephoneNumberInventoryCities](/powershell/module/skype/get-csonlinetelephonenumberinventorycities), [Get-CsOnlineTelephoneNumberInventoryAreas](/powershell/module/skype/get-csonlinetelephonenumberinventoryareas), [Get-CsOnlineTelephoneNumberInventoryCountries](/powershell/module/skype/get-csonlinetelephonenumberinventorycountries), [Get-CsOnlineTelephoneNumberInventoryRegions](/powershell/module/skype/get-csonlinetelephonenumberinventoryregions), [Get-CsOnlineTelephoneNumberInventoryTypes](/powershell/module/skype/get-csonlinetelephonenumberinventorytypes), [Search-CsOnlineTelephoneNumberInventory](/powershell/module/skype/search-csonlinetelephonenumberinventory), [Select-CsOnlineTelephoneNumberInventory](/powershell/module/skype/select-csonlinetelephonenumberinventory), [Get-CsOnlineTelephoneNumberAvailableCount](/powershell/module/skype/get-csonlinetelephonenumberavailablecount), [ Clear-CsOnlineTelephoneNumberReservation](/powershell/module/skype/clear-csonlinetelephonenumberreservation), [Get-CsOnlineTelephoneNumberReservationsInformation](/powershell/module/skype/get-csonlinetelephonenumberreservationsinformation), [Get-CsOnlineDirectoryTenantNumberCities](/powershell/module/skype/get-csonlinedirectorytenantnumbercities)
  - [Set-CsTeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy), [New-CsTeamsAppSetupPolicy](/powershell/module/skype/new-csteamsappsetuppolicy), [Set-CsTeamsAppPermissionPolicy](/powershell/module/skype/set-csteamsapppermissionpolicy), [New-CsTeamsAppPermissionPolicy](/powershell/module/skype/new-csteamsapppermissionpolicy)
  - [Test-CsOnlineLisCivicAddress](/powershell/module/skype/test-csonlineliscivicaddress)

- I cmdlet non supportati/rilevanti per gli scenari di Microsoft Teams sono elencati di seguito.
  - [Ottieni| Set]-CsUserPstnSettings
  - [Ottieni| Imposta| Abilita| Disable]-CsMeetingRoom
  - [Grant| Ottieni| Imposta| Novità| Remove]-CsConferencingPolicy
  - [Grant| Ottieni| Imposta| Novità| Remove]-CsClientPolicy
  - [Grant| Get]-CsHostedVoicemailPolicy
  - [Grant| Ottieni| Imposta| Novità| Remove]-CsMobilityPolicy
  - [Grant| Get]-CsVoiceRoutingPolicy
  - [Grant| Get]-CsBroadcastMeetingPolicy
  - [Grant| Get]-CsCloudMeetingPolicy
  - [Grant| Get]-CsGraphPolicy
  - [Grant| Ottieni| Imposta| Novità| Remove]-CsExternalUserCommunicationPolicy
  - [Grant| Ottieni| Set]-CsIPPhonePolicy
  - Get-CsUserServicesPolicy
  - [Ottieni| Set]-CsBroadcastMeetingConfiguration
  - [Ottieni| Set]-CsOAuthConfiguration
  - [Ottieni| Set]-CsMeetingConfiguration
  - [Ottieni| Set]-CsTenantHybridConfiguration
  - [Ottieni| Set]-CsPushNotificationConfiguration
  - [Ottieni| Set]-CsUCPhoneConfiguration
  - Get-CsImFilterConfiguration
  - Get-CsAudioConferencingProvider
  - [Ottieni| Set]-CsTenantPublicProvider
  - Get-CsHostingProvider
  - [Ottieni| Imposta| Registrati| Unregister]-CsHybridPSTNAppliance
  - [Ottieni| Imposta| Novità| Rimuovi]-CsHybridPSTNSite
  - [Ottieni| Set]-CsHybridMediationServer
  - [Ottieni| Imposta| Novità| Rimuovi]-CsTenantUpdateTimeWindow
  - Get-CsUserLocationStatus
  - Invoke-CsUcsRollback
  - [Ottieni| Imposta| Novità| Rimuovi]-CsTeamsPinnedApp
  - [Ottieni| Imposta| Novità| Rimuovi]-CsTenantCatalogApp
  - [Ottieni| Imposta| Novità| Rimuovi]-CsGlobalCatalogApp
  - [Ottieni| Imposta| Novità| Rimuovi]-CsDefaultCatalogApp
  - [Ottieni| Imposta| Novità| Rimuovi]-CsTeamsAppPreset
  - Invoke-CsUserPreferredDataLocationSync
  - [Ottieni| Set]-CsTeamsUpgradeStatus
  - Grant-CsPolicy
  - Set-CsOnlineDirectoryUser

## <a name="related-topics"></a>Argomenti correlati

[Note sulla versione di Teams PowerShell](teams-powershell-release-notes.md)

[Installare Microsoft Teams PowerShell](teams-powershell-install.md)

[Gestire Teams con PowerShell di Teams](teams-powershell-managing-teams.md)

[Riferimento per i cmdlet di Microsoft Teams](/powershell/module/teams)

[riferimento ai cmdlet di Skype for Business](/powershell/module/skype)
