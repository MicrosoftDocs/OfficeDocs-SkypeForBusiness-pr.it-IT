---
title: Criterio di roaming di rete
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
search.appverid: MET150
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Informazioni su come gestire le impostazioni per i criteri di roaming di rete di Teams.
ms.openlocfilehash: c26cdec0fc41e40a9c3eac7d0324050740cf05ef
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853237"
---
# <a name="manage-video-and-media-settings-with-the-network-roaming-policy"></a>Gestire le impostazioni video e multimediali con i criteri di roaming di rete

Oltre a gestire le impostazioni video e multimediali con i criteri riunioni, ora è possibile controllare dinamicamente l'uso degli attributi seguenti usati dal client Microsoft Teams con TeamsNetworkRoamingPolicy: 

- Video IP
- Velocità in bit supporto

Questo criterio consente di assegnare le impostazioni ai siti di rete. Il client di Teams raccoglierà dinamicamente le impostazioni in base al sito di rete a cui si connette. Quando il client di Teams accede da un sito di rete con un criterio di roaming assegnato, verrà usato tale criterio. Se non è assegnato alcun criterio, verranno usati i valori impostati nel criterio riunione. Per altre informazioni sulle impostazioni audio e video dei criteri riunione, vedere [Impostazioni dei criteri riunione per audio e video](meeting-policies-audio-and-video.md).

## <a name="configure-the-teamsnetworkroamingpolicy"></a>Configurare TeamsNetworkRoamingPolicy

Per configurare TeamsNetworkRoamingPolicy, usare i cmdlet di PowerShell seguenti:

- [Get-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/get-csteamsnetworkroamingpolicy)
- [New-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/new-csteamsnetworkroamingpolicy)
- [Set-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/set-csteamsnetworkroamingpolicy)
- [Remove-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/remove-csteamsnetworkroamingpolicy)

TeamsNetworkRoamingPolicy contiene i parametri seguenti:

- AllowIPVideo - Questa impostazione controlla se è possibile attivare il video nelle riunioni ospitate da un utente e nelle chiamate tra due persone e di gruppo avviate da un utente.

- MediaBitRateKb - Questa impostazione determina la velocità media totale in bit per le trasmissioni audio, video e di condivisione di app basate su video nelle chiamate e riunioni dell'utente.

Dopo aver configurato il criterio, assegnarlo a uno o più siti di rete usando il cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) nel modo seguente:

```PowerShell
 Set-CsTenantNetworkSite -Identity Burlington -NetworkRoamingPolicy LowBandwidthSite
 ``` 
 
 Per rimuovere un criterio da un sito di rete, usare il cmdlet seguente:
 
 ```PowerShell
 Set-CsTenantNetworkSite -Identity Burlington -NetworkRoamingPolicy $null
 ```

Per abilitare i criteri di roaming di rete per gli utenti che non sono abilitati per VoIP aziendale, è necessario abilitare anche l'impostazione AllowNetworkConfigurationSettingsLookup in TeamsMeetingPolicy. Questa opzione è disattivata per impostazione predefinita.

Per altre informazioni sulla creazione di siti di rete, vedere [Impostazioni di rete per le funzionalità vocali del cloud](cloud-voice-network-settings.md). 

## <a name="examples"></a>Esempi

```PowerShell
New-CsTeamsNetworkRoamingPolicy -Identity LowBandwidthSite -AllowIPVideo $false -MediaBitRateKb 1000
```

```PowerShell
Set-CsTenantNetworkSite -Identity Burlington -NetworkRoamingPolicy LowBandwidthSite
```

## <a name="supported-clients"></a>Client supportati

- Windows 
- MacOS desktop

## <a name="known-issues"></a>Problemi noti

Quando si specificano i cmdlet New- e Get-CsTeamsNetworkRoamingPolicy in Teams Online PowerShell v 2.0.0, verranno visualizzati dati aggiuntivi.


## <a name="related-topics"></a>Argomenti correlati

- [Get-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/get-csteamsnetworkroamingpolicy)
- [New-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/new-csteamsnetworkroamingpolicy)
- [Set-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/set-csteamsnetworkroamingpolicy)
- [Remove-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/remove-csteamsnetworkroamingpolicy)
- [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite)