---
title: Gestire la topologia di rete per le funzionalità vocali cloud in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
- m365initiative-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come configurare le impostazioni di rete per le funzionalità vocali cloud in Microsoft Teams.
ms.openlocfilehash: 44eeb7792e7fd37273ec8dd013d31b673fa2cf38f09c6c744de24a81f44b4f01
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351885"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a>Gestire la topologia di rete per le funzionalità vocali cloud in Microsoft Teams

Se l'organizzazione distribuisce il [routing](location-based-routing-plan.md) in base alla posizione per il routing diretto o le chiamate di emergenza [dinamiche,](configure-dynamic-emergency-calling.md)è necessario configurare le impostazioni di rete per l'uso con queste funzionalità vocali cloud in Microsoft Teams. Le impostazioni di rete vengono usate per determinare la posizione di un client Teams e includono aree di rete, siti di rete, subnet e indirizzi IP attendibili. A seconda della funzionalità vocale cloud e della funzionalità che si sta distribuendo, è possibile configurare alcune o tutte queste impostazioni. Per altre informazioni su questi termini, vedere [Impostazioni di rete per le funzionalità vocali cloud.](cloud-voice-network-settings.md)

Le impostazioni di rete vengono configurate nella pagina Topologia **di** rete dell'interfaccia Microsoft Teams di amministrazione oppure usando Windows PowerShell.

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a>Configurare le impostazioni di rete nell'Microsoft Teams di amministrazione

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Le aree di rete, i siti di rete e le subnet vengono definiti nella scheda Siti **di** rete della **pagina Topologia di** rete. Qui è possibile creare o modificare un sito di rete, associare un sito a un'area di rete, associare una subnet al sito, attivare il routing in base alla posizione e assegnare criteri di emergenza al sito. È anche possibile aggiungere aree di rete che possono essere usate a livello globale per tutti i siti.

#### <a name="add-and-configure-a-network-site"></a>Aggiungere e configurare un sito di rete

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione passare **a** Topologia rete percorsi e quindi fare clic sulla  >  scheda Siti **di** rete.
2. Fare **clic su** Aggiungi e quindi immettere un nome e una descrizione per il sito.

    ![Screenshot della pagina Aggiungi sito di rete](media/manage-network-topology-add-site.png)

3. Per associare il sito a un'area di rete,  fare clic su **Aggiungi** area di rete, selezionare un'area esistente o fare clic su Aggiungi per aggiungere un'area geografica e quindi su **Collegamento.**  
4. Per abilitare Location-Based routing per il sito, attivare **il routing basato sulla posizione.**
5. Per assegnare criteri dei servizi di emergenza al sito, eseguire una o entrambe le operazioni seguenti:

    - Se l'organizzazione usa Piani per chiamate o è stata distribuita Sistema telefonico Routing diretto, in Criteri per **le** chiamate di emergenza selezionare il criterio desiderato.
    - Se l'organizzazione ha Sistema telefonico routing diretto, in Criteri di **routing** delle chiamate di emergenza selezionare il criterio desiderato.

6. Per associare una subnet al sito, in **Subnet** fare clic **su Aggiungi subnet.** Specificare la versione IP, l'indirizzo IP, l'intervallo di rete, aggiungere una descrizione e quindi fare clic su **Applica.** Ogni subnet deve essere associata a un sito specifico.
7. Fare clic su **Salva**.

#### <a name="modify-a-network-site"></a>Modificare un sito di rete

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione passare **a** Topologia rete percorsi e quindi fare clic sulla  >  scheda Siti **di** rete.
2. Selezionare il sito facendo clic a sinistra del nome del sito e quindi su **Modifica.**
3. Apportare le modifiche desiderate e quindi fare clic su **Salva.**

### <a name="manage-external-trusted-ip-addresses"></a>Gestire indirizzi IP attendibili esterni

Gli indirizzi IP attendibili  esterni vengono gestiti  nella scheda Indirizzi IP attendibili della pagina Topologia di rete dell'Microsoft Teams di amministrazione. È possibile aggiungere un numero illimitato di indirizzi IP attendibili esterni.

#### <a name="add-a-trusted-ip-address"></a>Aggiungere un indirizzo IP attendibile

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione passare **a** Topologia di rete percorsi e quindi fare clic sulla  >  scheda **Ip** attendibili.
2. Fare clic **su Nuovo**.
3. Nel riquadro **Aggiungi indirizzo IP attendibile** specificare la versione IP, l'indirizzo IP, l'intervallo di rete, aggiungere una descrizione e quindi fare clic su **Applica.**

    ![Screenshot del riquadro Aggiungi indirizzo IP attendibile](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a>Modificare un indirizzo IP attendibile

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione passare **a** Topologia di rete percorsi e quindi fare clic sulla  >  scheda **Ip** attendibili.
2. Selezionare l'indirizzo IP facendo clic a sinistra e quindi su **Modifica.**
3. Nel riquadro **Modifica indirizzo IP attendibile** apportare le modifiche desiderate e quindi fare clic su **Applica.**

## <a name="configure-network-settings-using-powershell"></a>Configurare le impostazioni di rete con PowerShell

Per completare i passaggi descritti in questa sezione, è necessaria una certa familiarità con i cmdlet di PowerShell. Per altre informazioni, vedere Teams [panoramica di PowerShell.](teams-powershell-overview.md)

### <a name="define-network-regions"></a>Definire le aree di rete

 Usare il cmdlet [New-CsTenantNetworkRegion](/powershell/module/skype/New-CsTenantNetworkRegion) per definire le aree di rete. Si noti che il parametro RegionID è un nome logico che rappresenta la geografia dell'area geografica e non ha dipendenze o restrizioni e il parametro ID sito CentralSite &lt; &gt; è facoltativo.

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

In questo esempio viene creata un'area di rete denominata India.

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

Vedere anche [Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworkregion).

### <a name="define-network-sites"></a>Definire i siti di rete

Usare il cmdlet [New-CsTenantNetworkSite](/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) per definire i siti di rete. Ogni sito di rete deve essere associato a un'area di rete.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

In questo esempio vengono creati due nuovi siti di rete, Delhi e Hyderabad, nell'area india.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

La tabella seguente mostra i siti di rete definiti in questo esempio.

||Sito 1 |Sito 2 |
|---------|---------|---------|
|ID sito    |    Sito 1 (Delhi)     |  Sito 2 (Hyderabad)       |
|ID area geografica  |     Area geografica 1 (India)    |   Area geografica 1 (India)      |

Vedere anche [Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworksite).

### <a name="define-network-subnets"></a>Definire subnet di rete

Usare il cmdlet [New-CsTenantNetworkSubnet](/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) per definire subnet di rete e associarle ai siti di rete. Ogni subnet di rete può essere associata a un solo sito.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

In questo esempio viene creata un'associazione tra la subnet 192.168.0.0 e il sito di rete di Delhi e tra la subnet 2001:4898:e8:25:844e:926f:85ad:dd8e e il sito di rete di Hyderabad.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

La tabella seguente mostra le subnet definite in questo esempio.

||Sito 1 |Sito 2 |
|---------|---------|---------|
|Subnet ID   |    192.168.0.0     |  2001:4898:e8:25:844e:926f:85ad:dd8e     |
|Maschera  |     24    |   120      |
|ID sito  | Sito (Delhi) | Sito 2 (Hyderabad) |

Per più subnet, è possibile importare un file CSV usando uno script come il seguente.

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.Identity -MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

In questo esempio il file CSV ha un aspetto simile al seguente:

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```


Vedere anche [Set-CsTenantNetworkSubnet](/powershell/module/skype/set-cstenantnetworksubnet).


### <a name="define-external-subnets-external-trusted-ip-addresses"></a>Definire subnet esterne (indirizzi IP attendibili esterni)

Usare il cmdlet [New-CsTenantTrustedIPAddress](/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) per definire subnet esterne e assegnarle al tenant. È possibile definire un numero illimitato di subnet esterne per un tenant.

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

Ad esempio:

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

Vedere anche [Set-CsTenantTrustedIPAddress](/powershell/module/skype/set-cstenanttrustedipaddress).

## <a name="related-topics"></a>Argomenti correlati

- [Impostazioni di rete per le funzionalità vocali cloud in Teams](cloud-voice-network-settings.md)
