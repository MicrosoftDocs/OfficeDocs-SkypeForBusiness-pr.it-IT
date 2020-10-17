---
title: 'Lync Server 2013: distribuzione di aree di rete, siti e subnet'
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
ms.openlocfilehash: b95d9f7e38e3169474aee33a3004b388c0b13f14
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531143"
---
# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a>Distribuzione di aree di rete, siti e subnet in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-12_

Dopo la distribuzione di VoIP aziendale, è necessario configurare:

  - Aree di rete

  - Siti di rete

  - Subnet di rete

<div>

## <a name="define-network-regions"></a>Definire le aree di rete

Utilizzare il comando di Windows PowerShell di Lync Server, New-CsNetworkRegion o il pannello di controllo di Lync Server per definire le aree di rete.

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

Per ulteriori informazioni, vedere [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).

In questo esempio, il comando di Windows PowerShell seguente illustra l'area di rete, Region 1 (India), definita in questo scenario.

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a>Definire i siti di rete

Utilizzare il comando di Windows PowerShell di Lync Server, New-CsNetworkSite o il pannello di controllo di Lync Server per definire i siti di rete.

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

Per ulteriori informazioni, vedere [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).

Per questo esempio, nella tabella seguente e nel comando di Windows PowerShell di Lync Server vengono illustrati i siti di rete definiti in questo scenario. Solo le impostazioni specifiche per Location-Based il routing sono incluse nella tabella a scopo illustrativo.

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

Utilizzare il comando di Windows PowerShell di Lync Server, New-CsNetworkSubnet o il pannello di controllo di Lync Server per definire le subnet di rete e assegnarle a siti di rete.

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

Per ulteriori informazioni, vedere [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

Per questo esempio, nella tabella seguente e nei comandi di Windows PowerShell viene illustrata l'assegnazione delle subnet di rete ai siti di rete, Delhi e Hyderabad, definiti in questo scenario. Solo le impostazioni specifiche per Location-Based il routing sono incluse nella tabella a scopo illustrativo.

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


[Configurazione del routing Location-Based in Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

