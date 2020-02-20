---
title: 'Lync Server 2013: attivazione del routing in base alla posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Location-Based Routing
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994014(v=OCS.15)
ms:contentKeyID: 51803920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f36d28ca41bb12aa98bab5add471e102ed282b0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42155038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-location-based-routing-in-lync-server-2013"></a>Abilitazione del routing in base alla posizione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-04-26_

Dopo la distribuzione di VoIP aziendale e la definizione di aree di rete, siti e subnet, è possibile abilitare il routing in base alla posizione. Il routing in base alla posizione deve essere abilitato per gli elementi VoIP Enterprise seguenti:

  - Siti di rete

  - Configurazioni trunk

  - Criteri vocali

  - Configurazione del routing

<div>

## <a name="enable-location-based-routing-to-network-sites"></a>Abilitare il routing basato sul percorso ai siti di rete

Dopo aver distribuito VoIP aziendale e configurato i siti di rete, è possibile configurare il routing in base alla posizione. Per prima cosa, è necessario creare un criterio di routing vocale per associare il sito di rete agli utilizzi PSTN corretti. Quando si assegnano gli utilizzi PSTN a un criterio di routing vocale, è necessario utilizzare solo gli utilizzi PSTN associati a route vocali che utilizzano un gateway PSTN locale per il sito o un gateway PSTN che si trova in un'area in cui non sono necessarie restrizioni di routing basate sulla posizione. Utilizzare il comando di Windows PowerShell di Lync Server, New-CsVoiceRoutingPolicy o il pannello di controllo di Lync Server per creare i criteri di routing vocale.

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

Per ulteriori informazioni, vedere [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).

Per questo esempio, nella tabella seguente e nei comandi di Windows PowerShell vengono illustrati due criteri di routing vocale e gli utilizzi PSTN associati definiti in questo scenario. Solo le impostazioni specifiche del routing in base alla posizione sono incluse nella tabella a scopo illustrativo.

    New-CsVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Name "Delhi voice routing policy" -PstnUsages @{add="Delhi usage", "PBX Del usage", "PBX Hyd usage"}
    New-CsVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Name " Hyderabad voice routing policy" -PstnUsages @{add="Hyderabad usage", "PBX Del usage", "PBX Hyd usage"}


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Criterio di routing vocale 1</th>
<th>Criterio di routing vocale 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ID criterio vocale</p></td>
<td><p>Politica di routing vocale Delhi</p></td>
<td><p>Criteri di routing vocale Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Utilizzi PSTN</p></td>
<td><p>Utilizzo di Delhi, utilizzo del sistema PBX del PBX, utilizzo del sistema idraulico HYD</p></td>
<td><p>Utilizzo di Hyderabad, utilizzo del PBX HYD, utilizzo del sistema PBX del</p></td>
</tr>
</tbody>
</table>

  

Successivamente, configurare il routing in base alla posizione per i siti di rete applicabili e associargli i criteri di routing vocale. Utilizzare il comando di Windows PowerShell di Lync Server, New-CsNetworkSite, per abilitare il routing in base alla posizione e associare i criteri di routing vocale ai siti di rete che devono applicare restrizioni di routing.

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

In questo esempio, nella tabella seguente viene illustrato il routing in base alla posizione per due siti di rete diversi, Delhi e Hyderabad, definiti in questo scenario utilizzando Lync Server Windows PowerShell. Solo le impostazioni specifiche del routing in base alla posizione sono incluse nella tabella a scopo illustrativo.

    Set-CsNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "DelhiVoiceRoutingPolicy"
    Set-CsNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "HyderabadVoiceRoutingPolicy"


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
<td><p>Nome sito</p></td>
<td><p>Sito 1 (Delhi)</p></td>
<td><p>Sito 2 (Hyderabad)</p></td>
</tr>
<tr class="even">
<td><p>EnableLocationBasedRouting</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>Criterio di routing vocale</p></td>
<td><p>Politica di routing vocale Delhi</p></td>
<td><p>Criteri di routing vocale Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Subnet</p></td>
<td><p>Subnet 1 (Delhi)</p></td>
<td><p>Subnet 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a>Abilitare il routing basato sul percorso ai trunk

Prima di poter abilitare una configurazione trunk per il routing in base alla posizione, è necessario creare una configurazione trunk per ogni trunk o ogni sito di rete. Utilizzare il comando di Windows PowerShell di Lync Server, New-CsTrunkConfiguration, per creare una configurazione trunk. Se più trunk sono associati a un determinato sistema, ad esempio il gateway o il PBX, è necessario modificare ogni configurazione del trunk per abilitare le restrizioni di routing basate sul percorso.

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

Per ulteriori informazioni, vedere [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).

In questo esempio, i comandi di Windows PowerShell seguenti illustrano la creazione di una configurazione trunk per ogni trunk nella distribuzione definita in questo scenario.

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

Una volta configurata una configurazione trunk per trunk, è possibile utilizzare il comando di Windows PowerShell di Lync Server, Set-CsTrunkConfiguration, per abilitare il routing basato sul percorso ai trunk che devono applicare restrizioni di routing. Abilitare il routing in base alla posizione ai trunk che instradano le chiamate ai gateway PSTN che instradano le chiamate alla rete PSTN e associano il sito in cui si trova il gateway.

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

Per ulteriori informazioni, vedere [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).

In questo esempio, il routing in base alla posizione è abilitato per ogni trunk associato ai gateway PSTN di Delhi e Hyderabad:

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

Non abilitare il routing basato sulla posizione per i trunk che non instradano le chiamate alla rete PSTN; Tuttavia, è necessario associare il trunk al sito di rete in cui si trova il sistema come le restrizioni di routing basate sulla posizione devono essere applicate per le chiamate PSTN raggiungendo gli endpoint connessi tramite questo trunk. Per questo esempio, il routing in base alla posizione non è abilitato per ogni trunk associato a sistemi PBX a Delhi e Hyderabad:

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
Gli endpoint connessi a sistemi che non instradano le chiamate alla rete PSTN (ovvero a un sistema PBX) avranno restrizioni simili a quelle degli endpoint di Lync degli utenti abilitati per il routing in base alla posizione. Questo significa che gli utenti potranno effettuare e ricevere chiamate da e verso l'utente di Lync indipendentemente dalla posizione dell'utente. Sarà inoltre possibile effettuare chiamate di ricezione verso e da altri sistemi che non instradano le chiamate alla rete PSTN (ovvero un endpoint connesso a un altro PBX) indipendentemente dal sito di rete a cui è associato il sistema. Tutte le chiamate in ingresso, le chiamate in uscita, i trasferimenti di chiamata e l'inoltro di chiamata che coinvolgono endpoint PSTN saranno soggetti alle imposte del routing basate sul percorso. Tali chiamate devono utilizzare solo gateway PSTN definiti come locali per tali sistemi.

Nella tabella seguente viene illustrata la configurazione trunk di quattro trunk in due siti di rete diversi: due connessi a gateway PSTN e due connessi a sistemi PBX.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>EnableLocationRestriction</th>
<th>NetworkSiteID</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PstnGateway: trunk 1 DEL-GW</p></td>
<td><p>True</p></td>
<td><p>Sito 1 (Delhi)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway: tronco 2 HYD-GW</p></td>
<td><p>True</p></td>
<td><p>Sito 2 (Hyderabad)</p></td>
</tr>
<tr class="odd">
<td><p>PstnGateway: Trunk 3 DEL-PBX</p></td>
<td><p>False</p></td>
<td><p>Sito 1 (Delhi)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway: trunk 4 HYD-PBX</p></td>
<td><p>False</p></td>
<td><p>Sito 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a>Abilitare il routing basato sul percorso ai criteri vocali

Per applicare il routing basato sul percorso a utenti specifici, configurare i criteri vocali di tali utenti per impedire il bypass a pedaggio PSTN. Utilizzare il comando di Windows PowerShell di Lync Server, New-CsVoicePolicy, per creare un nuovo criterio vocale o Set-CsVoicePolicy, se si utilizza un criterio esistente, per abilitare il routing basato sulla posizione impedendo il bypass a pedaggio PSTN.

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

Per ulteriori informazioni, vedere [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).

Per questo esempio, nella tabella seguente e nei comandi di Windows PowerShell viene illustrato come abilitare la prevenzione del bypass a pedaggio PSTN nei criteri vocali Delhi e Hyderabad definiti in questo scenario. Solo le impostazioni specifiche del routing in base alla posizione sono incluse nella tabella a scopo illustrativo.

    Set-CsVoicePolicy -Identity "Delhi voice policy" -PreventPSTNTollBypass $true
    Set-CsVoicePolicy -Identity "Hyderabad voice policy" -PreventPSTNTollBypass $true


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Criterio vocale 1</th>
<th>Criterio vocale 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ID criterio vocale</p></td>
<td><p>Criteri vocali Delhi</p></td>
<td><p>Criteri vocali di Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Utilizzi PSTN</p></td>
<td><p>Utilizzo di Delhi, utilizzo del sistema PBX del PBX, utilizzo del sistema idraulico HYD</p></td>
<td><p>Utilizzo di Hyderabad, utilizzo del PBX HYD, utilizzo del sistema PBX del</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a>Abilitare il routing in base alla posizione nella configurazione del routing

Infine, abilitare globalmente il routing basato sulla posizione alla configurazione di routing. Utilizzare il comando di Windows PowerShell di Lync Server, New-CsRoutingConfiguration, per abilitare il routing in base alla posizione.

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

Per ulteriori informazioni, vedere [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).

<div>


> [!NOTE]  
> mentre il routing in base alla posizione deve essere abilitato tramite una configurazione globale, l'insieme di regole da applicare verrà applicato solo per i siti, gli utenti e i trunk per i quali è stata configurata come specificato nella presente documentazione.



</div>

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

