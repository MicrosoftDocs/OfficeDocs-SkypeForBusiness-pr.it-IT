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
ms.openlocfilehash: c9eb6754a9fa89d1298e22f6c713e8c4d28d5861
ms.sourcegitcommit: 708b489a7dca7fd9e5e9b1ec88c9aba79ecafe5f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2022
ms.locfileid: "64712960"
---
# <a name="teams-powershell-module---supported-versions"></a>Modulo di PowerShell Teams - Versioni supportate

Microsoft Teams versioni del modulo PowerShell (TPM) della serie 4.x.x o versioni successive saranno le uniche supportate in futuro. Tutte le versioni precedenti sono nel percorso di ritiro. È consigliabile aggiornare Teams modulo di PowerShell alla versione più recente.



## <a name="new-organizations"></a>Nuove organizzazioni

Le organizzazioni che hanno appena avviato l'onboarding a Teams potranno usare Teams modulo PowerShell solo nella serie 4.x.x o versione successiva a partire dal 1° aprile 2022.



## <a name="current-organizations-non-tpm-active"></a>Organizzazioni correnti (non TPM attivo)

Le organizzazioni che non hanno usato Teams modulo di PowerShell negli ultimi tre mesi (22 gennaio - 22 marzo), potranno usare Teams modulo di PowerShell solo nella serie 4.x.x o versione successiva a partire dal 1° aprile 2022.



## <a name="current-organizations-tpm-active"></a>Organizzazioni correnti (TPM attivo)

Le organizzazioni che hanno usato Teams modulo di PowerShell negli ultimi tre mesi (22 gennaio - 22 marzo), potranno usare Teams modulo di PowerShell solo nella serie 4.x.x o versione successiva a partire dal 15 giugno 2022. Post del Centro messaggi per riferimento - MC350371. 



## <a name="important-notes"></a>Note importanti

- Le note sulla versione per tutte le versioni Teams modulo di PowerShell sono disponibili in [Teams note sulla versione di PowerShell](teams-powershell-release-notes.md).

- Per aggiornare qualsiasi modulo di PowerShell, è consigliabile usare lo stesso metodo usato per installare il modulo. Ad esempio, se hai usato in origine Install-Module, devi usare [Update-Module](/powershell/module/powershellget/update-module) per ottenere la versione più recente.  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   Se si aggiorna da Teams modulo di PowerShell versione 1.1.6, aggiornare gli script in modo che usino `Connect-MicrosoftTeams` invece di `New-CsOnlineSession`.

-   Durante l'aggiornamento, è consigliabile non usare TPM 4.x.x/3.x.x insieme alle versioni precedenti alla 3.0.0. Ad esempio, non è consigliabile usare le versioni 4.x.x & 2.6.0 insieme per operazioni amministrative diverse nella stessa organizzazione. 

- Modifiche correlate
  * Aggiornamenti per Get-CsOnlineUser & Get-CsOnlineVoiceUser in TPM 3.x.x e versioni successive: maggiori dettagli in [Get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlineuser) &  (post del Centro messaggi - MC340774).[](/powershell/module/skype/get-csonlinevoiceuser)

  * Modifiche in arrivo per Telefono assegnazione dei numeri - ulteriori dettagli in [Set-CsUser](/powershell/module/skype/set-csuser), [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser), [Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) &  (post del Centro messaggi - MC316139)[](/powershell/module/skype/set-csonlinevoiceapplicationinstance)



## <a name="deprecated-cmdlets"></a>Cmdlet deprecati

Alcuni dei cmdlet deprecati di recente o non supportati per Microsoft Teams scenari sono elencati di seguito. I dettagli dello stesso sono disponibili nelle rispettive documentazione pubbliche. 

- [Get-CsUserPstnSettings](/powershell/module/skype/get-csuserpstnsettings), [Set-CsUserPstnSettings](/powershell/module/skype/set-csuserpstnsettings)
- [Get-CsOnlineDialInConferencingUserInfo](/powershell/module/skype/get-csonlinedialinconferencinguserinfo), [Get-CsOnlineDialInConferencingUserState](/powershell/module/skype/get-csonlinedialinconferencinguserstate), [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/enable-csonlinedialinconferencinguser), [Disable-CsOnlineDialInConferencingUser](/powershell/module/skype/disable-csonlinedialinconferencinguser)
- [Get-CsMeetingRoom](/powershell/module/skype/get-csmeetingroom), [Set-CsMeetingRoom](/powershell/module/skype/set-csmeetingroom), [Enable-CsMeetingRoom](/powershell/module/skype/enable-csmeetingroom), [Disable-CsMeetingRoom](/powershell/module/skype/disable-csmeetingroom)
- [Get-CsOnlineDirectoryTenant](/powershell/module/skype/get-csonlinedirectorytenant)
- [New-CsOnlineAudioFile](/powershell/module/skype/new-csonlineaudiofile)
- [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint), [Set-CsOnlineApplicationEndpoint](/powershell/module/skype/set-csonlineapplicationendpoint), [New-CsOnlineApplicationEndpoint](/powershell/module/skype/new-csonlineapplicationendpoint), [Remove-CsOnlineApplicationEndpoint](/powershell/module/skype/remove-csonlineapplicationendpoint)
- [Get-CsOnlineTelephoneNumberInventoryCities](/powershell/module/skype/get-csonlinetelephonenumberinventorycities), [Get-CsOnlineTelephoneNumberInventoryAreas](/powershell/module/skype/get-csonlinetelephonenumberinventoryareas), [Get-CsOnlineTelephoneNumberInventoryCountries](/powershell/module/skype/get-csonlinetelephonenumberinventorycountries), [Get-CsOnlineTelephoneNumberInventoryRegions](/powershell/module/skype/get-csonlinetelephonenumberinventoryregions), [Get-CsOnlineTelephoneNumberInventoryTypes](/powershell/module/skype/get-csonlinetelephonenumberinventorytypes), [Search-CsOnlineTelephoneNumberInventory](/powershell/module/skype/search-csonlinetelephonenumberinventory), [Select-CsOnlineTelephoneNumberInventory](/powershell/module/skype/select-csonlinetelephonenumberinventory), [Get-CsOnlineTelephoneNumberAvailableCount](/powershell/module/skype/get-csonlinetelephonenumberavailablecount), [ Clear-CsOnlineTelephoneNumberReservation](/powershell/module/skype/clear-csonlinetelephonenumberreservation), [Get-CsOnlineTelephoneNumberReservationsInformation](/powershell/module/skype/get-csonlinetelephonenumberreservationsinformation), [Get-CsOnlineDirectoryTenantNumberCities](/powershell/module/skype/get-csonlinedirectorytenantnumbercities)  



## <a name="related-topics"></a>Argomenti correlati

[note sulla versione di Teams PowerShell](teams-powershell-release-notes.md)

[Installare Microsoft Teams PowerShell](teams-powershell-install.md)

[Gestire Teams con Teams PowerShell](teams-powershell-managing-teams.md)

[riferimento ai cmdlet di Microsoft Teams](/powershell/module/teams) 

[riferimento ai cmdlet di Skype for Business](/powershell/module/skype) 
