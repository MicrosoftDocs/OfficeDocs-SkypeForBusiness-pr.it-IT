---
title: Configurare le impostazioni di rete per il routing basato sulla posizione
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come creare e configurare aree di rete, siti e subnet per il routing basato sulla posizione per il routing diretto.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7f6f6f1e74cc50b37ade03e97106d2befe36a6dd
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245107"
---
# <a name="configure-network-settings-for-location-based-routing"></a>Configurare le impostazioni di rete per il routing basato sulla posizione

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

Se non è già stato fatto, leggere il [routing basato sulla posizione del piano per il routing diretto](location-based-routing-plan.md) per esaminare gli altri passaggi che è necessario eseguire prima di configurare le impostazioni di rete per il routing basato sulla posizione.

Questo articolo descrive come configurare le impostazioni di rete per il routing basato sulla posizione. Dopo aver distribuito il routing diretto del sistema telefonico nell'organizzazione, i passaggi successivi sono la creazione e la configurazione di aree di rete, siti di rete e subnet di rete. Per completare la procedura descritta in questo articolo, è necessario avere familiarità con i cmdlet di PowerShell. Per altre informazioni, vedere [Cenni preliminari su teams PowerShell](teams-powershell-overview.md).

## <a name="define-network-regions"></a>Definire le aree di rete
 Un'area geografica di rete interconnette varie parti di una rete in più aree geografiche. Usa il cmdlet [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) per definire le aree di rete. Tieni presente che il parametro RegionID è un nome logico che rappresenta la geografia dell'area geografica e non ha dipendenze o &lt;restrizioni e&gt; il parametro ID sito CentralSite è facoltativo. 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

In questo esempio creiamo un'area di rete denominata India. 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a>Definire i siti di rete

Usare il cmdlet [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) per definire i siti di rete. 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
In questo esempio creiamo due nuovi siti di rete, Delhi e Hyderabad, nell'area dell'India. 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
Nella tabella seguente sono illustrati i siti di rete definiti in questo esempio. 

||Sito 1 |Sito 2 |
|---------|---------|---------|
|ID sito    |    Sito 1 (Delhi)     |  Sito 2 (Hyderabad)       |
|ID area  |     Regione 1 (India)    |   Regione 1 (India)      |

## <a name="define-network-subnets"></a>Definire le subnet di rete

Utilizzare il cmdlet [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) per definire le subnet di rete e associarle ai siti di rete. Ogni subnet interna può essere associata a un solo sito. 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
In questo esempio creiamo un'associazione tra subnet 192.168.0.0 e il sito di rete Delhi e tra subnet 2001:4898: E8:25:844E: 926f: 85AD: dd8e e il sito di rete di Hyderabad.
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad" 
```
La tabella seguente mostra le subnet definite in questo esempio. 

||Sito 1 |Sito 2 |
|---------|---------|---------|
|ID subnet   |    192.168.0.0     |  2001:4898: E8:25:844E: 926f: 85AD: dd8e     |
|Maschera  |     24    |   120      |
|ID sito  | Sito (Delhi) | Sito 2 (Hyderabad) |

Per più subnet, è possibile importare un file CSV usando uno script come il seguente.
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
In questo esempio, il file CSV ha un aspetto simile al seguente:
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a>Definire subnet esterne
Usa il cmdlet [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) per definire subnet esterne e assegnarle al tenant. Puoi definire un numero illimitato di subnet per un tenant. 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
Ad esempio:
```
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a>Passaggi successivi
Accedere a [abilitare il routing basato sulla posizione per il routing diretto](location-based-routing-enable.md).

### <a name="related-topics"></a>Argomenti correlati
- [Pianificare il routing basato sulla posizione per il routing diretto](location-based-routing-plan.md)
- [Terminologia di routing basata sulla posizione](location-based-routing-terminology.md)
