---
title: 'Lync Server 2013: distribuzione di aree geografiche, siti e subnet di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying network regions, sites, and subnets
ms:assetid: c4b75601-3538-4d07-8d23-1ad90459ae48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994067(v=OCS.15)
ms:contentKeyID: 51803978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04c39a18147bad3f84bd345ec0a56b606db4cae4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a>Distribuzione di aree geografiche, siti e subnet di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-12_

Dopo aver distribuito Enterprise Voice, è necessario configurare:

  - Aree di rete

  - Siti di rete

  - Subnet di rete

<div>

## <a name="define-network-regions"></a>Definire le aree di rete

Usare il comando Lync Server di Windows PowerShell, New-CsNetworkRegion o il pannello di controllo di Lync Server per definire le aree di rete.

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

Per altre informazioni, vedere [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).

Per questo esempio, il comando di Windows PowerShell seguente illustra l'area geografica della rete, Region 1 (India), definita in questo scenario.

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a>Definire i siti di rete

Usare il comando Lync Server di Windows PowerShell, New-CsNetworkSite o il pannello di controllo di Lync Server per definire i siti di rete.

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

Per altre informazioni, vedere [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).

Per questo esempio, la tabella seguente e il comando di Windows PowerShell di Lync Server illustrano i siti di rete definiti in questo scenario. Nella tabella sono incluse solo le impostazioni specifiche del routing basato sulla posizione.

    New-CsNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
    New-CsNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Sito 1 (Delhi)</th>
<th>Sito 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ID sito</p></td>
<td><p>Sito 1 (Delhi)</p></td>
<td><p>Sito 2 (Hyderabad)</p></td>
</tr>
<tr class="even">
<td><p>ID area</p></td>
<td><p>Regione 1 (India)</p></td>
<td><p>Regione 1 (India)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a>Definire le subnet di rete

Usare il comando Lync Server di Windows PowerShell, New-CsNetworkSubnet o il pannello di controllo di Lync Server per definire le subnet di rete e assegnarle ai siti di rete.

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

Per altre informazioni, vedere [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

Per questo esempio, la tabella seguente e i comandi di Windows PowerShell illustrano l'assegnazione delle subnet di rete ai siti di rete, Delhi e Hyderabad, definiti in questo scenario. Nella tabella sono incluse solo le impostazioni specifiche del routing basato sulla posizione.

    New-CsNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
    New-CsNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Sito 1 (Delhi)</th>
<th>Sito 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ID subnet</p></td>
<td><p>192.168.0.0</p></td>
<td><p>192.168.1.0</p></td>
</tr>
<tr class="even">
<td><p>Maschera</p></td>
<td><p>24</p></td>
<td><p>24</p></td>
</tr>
<tr class="odd">
<td><p>ID sito</p></td>
<td><p>Sito 1 (Delhi)</p></td>
<td><p>Sito 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurazione del routing in base alla posizione in Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

