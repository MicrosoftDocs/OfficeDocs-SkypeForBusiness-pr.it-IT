---
title: Modulo di PowerShell Teams - Versioni supportate
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Informazioni sulle versioni supportate dal modulo Teams PowerShell, usato per l'amministrazione di Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c97e3c840452a20be60d6f27e2bf4c3375322be1
ms.sourcegitcommit: bd05783dfb33a63e0eb083a2135f97d110dc81a3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2022
ms.locfileid: "65059417"
---
# <a name="teams-powershell-module---supported-versions"></a>Modulo di PowerShell Teams - Versioni supportate

Microsoft Teams versioni del modulo PowerShell (TPM) della serie 4.x.x o successive saranno le uniche versioni supportate in futuro. Tutte le versioni precedenti sono nel percorso di ritiro. È consigliabile aggiornare Teams modulo di PowerShell alla versione più recente.



## <a name="new-organizations"></a>Nuove organizzazioni

Le organizzazioni che hanno appena avviato l'onboarding a Teams potranno usare Teams modulo PowerShell solo nella serie 4.x.x o successiva a partire dall'1 aprile 2022.



## <a name="current-organizations-non-tpm-active"></a>Organizzazioni correnti (non TPM attivo)

Le organizzazioni che non hanno usato Teams modulo di PowerShell negli ultimi tre mesi (22 gennaio - 22 marzo), potranno usare Teams modulo di PowerShell solo nella serie 4.x.x o versione successiva a partire dal 1° aprile 2022.



## <a name="current-organizations-tpm-active"></a>Organizzazioni correnti (TPM attivo)

Le organizzazioni che usano Teams modulo di PowerShell negli ultimi tre mesi (22 gennaio - 22 marzo), potranno usare Teams modulo di PowerShell solo nella serie 4.x.x o successiva a partire dal 15 giugno 2022. Post del Centro messaggi per riferimento - MC350371. 



## <a name="important-notes"></a>Note importanti

- Le note sulla versione per tutte le versioni Teams modulo di PowerShell sono disponibili in [Teams note sulla versione di PowerShell](teams-powershell-release-notes.md).

- Per aggiornare qualsiasi modulo di PowerShell, è consigliabile usare lo stesso metodo usato per installare il modulo. Ad esempio, se hai usato in origine Install-Module, devi usare [Update-Module](/powershell/module/powershellget/update-module) per ottenere la versione più recente.  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   Se si aggiorna da Teams modulo di PowerShell versione 1.1.6, aggiornare gli script in modo che usino `Connect-MicrosoftTeams` invece di `New-CsOnlineSession`.

-   Durante l'aggiornamento, è consigliabile non usare TPM 4.x.x/3.x.x insieme alle versioni precedenti alla 3.0.0. Ad esempio, non è consigliabile usare le versioni 4.x.x & 2.6.0 insieme per operazioni amministrative diverse nella stessa organizzazione. 

- Modifiche correlate
  * Aggiornamenti per Get-CsOnlineUser & Get-CsOnlineVoiceUser in TPM 3.x.x e versioni successive: maggiori dettagli in [Get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlineuser) &  (post del centro messaggi - MC340774).[](/powershell/module/skype/get-csonlinevoiceuser)

  * Modifiche in arrivo per Telefono assegnazione dei numeri: maggiori dettagli in [Set-CsUser](/powershell/module/skype/set-csuser), [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser), [Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) &  (post del Centro messaggi - MC316139).[](/powershell/module/skype/set-csonlinevoiceapplicationinstance)
  
  * Modifiche al parametro in Get-CsTenant - maggiori dettagli in [Get-CsTenant](/powershell/module/skype/get-cstenant).  

-   Durante l'uso di TPM 4.x.x o versione successiva, è consigliabile non usare i cmdlet deprecati o non supportati indicati [di seguito](#deprecated-cmdlets). 



## <a name="deprecated-cmdlets"></a>Cmdlet deprecati

- Alcuni dei cmdlet deprecati di recente sono elencati di seguito. I dettagli dello stesso sono disponibili nelle rispettive documentazione pubbliche. 
  * [Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  * [Get-CsOnlineDialInConferencingUserInfo](/powershell/module/skype/get-csonlinedialinconferencinguserinfo), [Get-CsOnlineDialInConferencingUserState](/powershell/module/skype/get-csonlinedialinconferencinguserstate), [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/enable-csonlinedialinconferencinguser), [Disable-CsOnlineDialInConferencingUser](/powershell/module/skype/disable-csonlinedialinconferencinguser)
  * [Get-CsOnlineDirectoryTenant](/powershell/module/skype/get-csonlinedirectorytenant)
  * [New-CsOnlineAudioFile](/powershell/module/skype/new-csonlineaudiofile)
  * [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint), [Set-CsOnlineApplicationEndpoint](/powershell/module/skype/set-csonlineapplicationendpoint), [New-CsOnlineApplicationEndpoint](/powershell/module/skype/new-csonlineapplicationendpoint), [Remove-CsOnlineApplicationEndpoint](/powershell/module/skype/remove-csonlineapplicationendpoint)
  * [Get-CsOnlineTelephoneNumberInventoryCities](/powershell/module/skype/get-csonlinetelephonenumberinventorycities), [Get-CsOnlineTelephoneNumberInventoryAreas](/powershell/module/skype/get-csonlinetelephonenumberinventoryareas), [Get-CsOnlineTelephoneNumberInventoryCountries](/powershell/module/skype/get-csonlinetelephonenumberinventorycountries), [Get-CsOnlineTelephoneNumberInventoryRegions](/powershell/module/skype/get-csonlinetelephonenumberinventoryregions), [Get-CsOnlineTelephoneNumberInventoryTypes](/powershell/module/skype/get-csonlinetelephonenumberinventorytypes), [Search-CsOnlineTelephoneNumberInventory](/powershell/module/skype/search-csonlinetelephonenumberinventory), [Select-CsOnlineTelephoneNumberInventory](/powershell/module/skype/select-csonlinetelephonenumberinventory), [Get-CsOnlineTelephoneNumberAvailableCount](/powershell/module/skype/get-csonlinetelephonenumberavailablecount), [ Clear-CsOnlineTelephoneNumberReservation](/powershell/module/skype/clear-csonlinetelephonenumberreservation), [Get-CsOnlineTelephoneNumberReservationsInformation](/powershell/module/skype/get-csonlinetelephonenumberreservationsinformation), [Get-CsOnlineDirectoryTenantNumberCities](/powershell/module/skype/get-csonlinedirectorytenantnumbercities)  
  * [Set-CsTeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy), [New-CsTeamsAppSetupPolicy](/powershell/module/skype/new-csteamsappsetuppolicy), [Set-CsTeamsAppPermissionPolicy](/powershell/module/skype/set-csteamsapppermissionpolicy), [New-CsTeamsAppPermissionPolicy](/powershell/module/skype/new-csteamsapppermissionpolicy)
  * [Test-CsOnlineLisCivicAddress](/powershell/module/skype/test-csonlineliscivicaddress)


- I cmdlet non supportati/rilevanti per Microsoft Teams scenari sono elencati di seguito. 
  * [Ottieni| Set]-CsUserPstnSettings
  * [Ottieni| Imposta| Abilita| Disable]-CsMeetingRoom
  * [Grant| Ottieni| Imposta| Novità| Remove]-CsConferencingPolicy
  * [Grant| Ottieni| Imposta| Novità| Remove]-CsClientPolicy
  * [Grant| Get]-CsHostedVoicemailPolicy
  * [Grant| Ottieni| Imposta| Novità| Remove]-CsMobilityPolicy
  * [Grant| Get] CsVoiceRoutingPolicy
  * [Grant| Get]-CsBroadcastMeetingPolicy
  * [Grant| Get]-CsCloudMeetingPolicy
  * [Grant| Get]-CsGraphPolicy
  * [Grant| Ottieni| Imposta| Novità| Remove]-CsExternalUserCommunicationPolicy
  * [Grant| Ottieni| Set]-CsIPPhonePolicy
  * Get-CsUserServicesPolicy
  * [Ottieni| Set]-CsBroadcastMeetingConfiguration
  * [Ottieni| Set]-CsOAuthConfiguration
  * [Ottieni| Set]-CsMeetingConfiguration
  * [Ottieni| Set]-CsTenantHybridConfiguration
  * [Ottieni| Set]-CsPushNotificationConfiguration
  * [Ottieni| Set]-CsUCPhoneConfiguration
  * Get-CsImFilterConfiguration
  * Get-CsAudioConferencingProvider
  * [Ottieni| Set]-CsTenantPublicProvider
  * Get-CsHostingProvider
  * [Ottieni| Imposta| Registrati| Unregister]-CsHybridPSTNAppliance
  * [Ottieni| Imposta| Novità| Rimuovi]-CsHybridPSTNSite
  * [Ottieni| Set]- CsHybridMediationServer
  * [Ottieni| Imposta| Novità| Rimuovi]-CsTenantUpdateTimeWindow
  * Get-CsUserLocationStatus
  * Invoke-CsUcsRollback
  * [Ottieni| Imposta| Novità| Rimuovi]-CsTeamsPinnedApp
  * [Ottieni| Imposta| Novità| Rimuovi]-CsTenantCatalogApp
  * [Ottieni| Imposta| Novità| Rimuovi]-CsGlobalCatalogApp
  * [Ottieni| Imposta| Novità| Rimuovi]-CsDefaultCatalogApp
  * [Ottieni| Imposta| Novità| Rimuovi]-CsTeamsAppPreset



## <a name="related-topics"></a>Argomenti correlati

[note sulla versione di Teams PowerShell](teams-powershell-release-notes.md)

[Installare Microsoft Teams PowerShell](teams-powershell-install.md)

[Gestire Teams con Teams PowerShell](teams-powershell-managing-teams.md)

[riferimento ai cmdlet di Microsoft Teams](/powershell/module/teams) 

[riferimento ai cmdlet di Skype for Business](/powershell/module/skype) 
