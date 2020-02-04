---
title: 'Lync Server 2013: abilitazione del routing basato sulla posizione'
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
ms.openlocfilehash: e21e1a285fa5b2129d4d0ed0b5d75e8dcee42f2f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735806"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-location-based-routing-in-lync-server-2013"></a>Abilitazione del routing basato sulla posizione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-04-26_

Quando Enterprise Voice viene distribuita e vengono definite aree di rete, siti e subnet, è possibile abilitare il routing basato sulla posizione. Il routing basato sulla posizione deve essere abilitato per gli elementi Voice Enterprise seguenti:

  - Siti di rete

  - Configurazioni trunk

  - Criteri vocali

  - Configurazione del routing

<div>

## <a name="enable-location-based-routing-to-network-sites"></a>Abilitare il routing basato sulla posizione nei siti di rete

Dopo aver distribuito Enterprise Voice e i siti di rete configurati, si è pronti per configurare il routing basato sulla posizione. Prima di tutto, crei un criterio di routing vocale per associare il sito di rete agli usi appropriati PSTN. Quando si assegnano gli utilizzi PSTN a un criterio di routing vocale, assicurarsi di usare solo gli usi PSTN associati alle route vocali che usano un gateway PSTN locale per il sito o un gateway PSTN che si trova in un'area geografica in cui non sono necessarie restrizioni di routing basate sulla posizione. Usare il comando Lync Server di Windows PowerShell, New-CsVoiceRoutingPolicy o il pannello di controllo di Lync Server per creare criteri di routing vocale.

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

Per altre informazioni, vedere [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).

Per questo esempio, la tabella seguente e i comandi di Windows PowerShell illustrano due criteri di routing vocale e gli usi PSTN associati definiti in questo scenario. Nella tabella sono incluse solo le impostazioni specifiche del routing basato sulla posizione.

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
<th>Criteri di routing vocale 1</th>
<th>Criteri di routing vocale 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ID criterio vocale</p></td>
<td><p>Politica di routing vocale Delhi</p></td>
<td><p>Criteri di routing vocale di Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Usi PSTN</p></td>
<td><p>Uso di Delhi, uso del PBX, uso di HYD PBX</p></td>
<td><p>Uso di Hyderabad, uso del PBX HYD, uso del PBX</p></td>
</tr>
</tbody>
</table>

  

Configurare quindi il routing basato sulla posizione per i siti di rete applicabili e associarvi i criteri di routing vocale. Usare il comando di Windows PowerShell di Lync Server, New-CsNetworkSite, per abilitare il routing basato sulla posizione e associare i criteri di routing vocale ai siti di rete che devono applicare restrizioni di routing.

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

In questo esempio la tabella seguente illustra il routing basato sulla posizione per due diversi siti di rete, Delhi e Hyderabad, definiti in questo scenario tramite Lync Server Windows PowerShell. Nella tabella sono incluse solo le impostazioni specifiche del routing basato sulla posizione.

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
<td><p>Criteri di routing vocale</p></td>
<td><p>Politica di routing vocale Delhi</p></td>
<td><p>Criteri di routing vocale di Hyderabad</p></td>
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

## <a name="enable-location-based-routing-to-trunks"></a>Abilitare il routing basato sulla posizione ai trunk

Prima di poter abilitare una configurazione trunk per il routing basato sulla posizione, è necessario creare una configurazione trunk per ogni trunk o ogni sito di rete. Usare il comando di Windows PowerShell di Lync Server, New-CsTrunkConfiguration, per creare una configurazione trunk. Se più trunk sono associati a un sistema specifico (ad esempio gateway o PBX), è necessario modificare ogni configurazione trunk per abilitare le restrizioni di routing basate sul percorso.

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

Per altre informazioni, vedere [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).

Per questo esempio, i comandi di Windows PowerShell seguenti illustrano la creazione di una configurazione trunk per ogni trunk nella distribuzione definita in questo scenario.

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

Una volta configurata una configurazione trunk per ogni trunk, è possibile usare il comando Lync Server di Windows PowerShell, Set-CsTrunkConfiguration, per abilitare il routing basato sulla posizione nei trunk che deve applicare le restrizioni di routing. Abilitare il routing basato sulla posizione per i trunk che instradano le chiamate ai gateway PSTN che instradano le chiamate alla rete PSTN e associano il sito in cui si trova il gateway.

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

Per altre informazioni, vedere [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).

In questo esempio, il routing basato sulla posizione è abilitato per ogni trunk associato ai gateway PSTN di Delhi e Hyderabad:

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

Non abilitare il routing basato sulla posizione per i trunk che non instradano le chiamate alla rete PSTN; Tuttavia, devi comunque associare il trunk al sito di rete in cui il sistema è situato come le restrizioni di routing basate sulla posizione devono essere applicate per le chiamate PSTN raggiungendo endpoint connessi tramite questo trunk. Per questo esempio, il routing basato sulla posizione non è abilitato per ogni trunk associato ai sistemi PBX di Delhi e Hyderabad:

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
Gli endpoint connessi a sistemi che non instradano le chiamate alla rete PSTN (ad esempio PBX) avranno restrizioni simili agli endpoint di Lync degli utenti abilitati per il routing basato sulla posizione. Questo significa che questi utenti potranno effettuare e ricevere chiamate da e verso l'utente di Lync indipendentemente dalla posizione dell'utente. Potranno anche effettuare chiamate di ricezione da e verso altri sistemi che non instradano le chiamate alla rete PSTN (ad esempio un endpoint connesso a un PBX diverso), indipendentemente dal sito di rete a cui è associato il sistema. Tutte le chiamate in ingresso, le chiamate in uscita, i trasferimenti delle chiamate e l'inoltro di chiamata che coinvolgono endpoint PSTN saranno soggetti a imposte di routing basate sulla posizione. Tali chiamate devono usare solo gateway PSTN definiti come locali per tali sistemi.

La tabella seguente illustra la configurazione trunk di quattro trunk in due diversi siti di rete: due collegati a gateway PSTN e due collegati a sistemi PBX.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>EnableLocationRestriction</th>
<th>NetworkSiteID</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PstnGateway: tronco 1 DEL-GW</p></td>
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

## <a name="enable-location-based-routing-to-voice-policies"></a>Abilitare il routing basato sulla posizione ai criteri vocali

Per applicare il routing basato sulla posizione a utenti specifici, configurare i criteri vocali degli utenti per evitare l'esclusione del pedaggio PSTN. Usare il comando di Windows PowerShell di Lync Server, New-CsVoicePolicy, per creare un nuovo criterio vocale o Set-CsVoicePolicy, se si usa un criterio esistente, per abilitare il routing basato sulla posizione impedendo l'esclusione del pedaggio PSTN.

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

Per altre informazioni, vedere [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).

Per questo esempio, la tabella seguente e i comandi di Windows PowerShell illustrano l'abilitazione della prevenzione del bypass a pedaggio PSTN per i criteri vocali di Delhi e Hyderabad definiti in questo scenario. Nella tabella sono incluse solo le impostazioni specifiche del routing basato sulla posizione.

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
<td><p>Politica vocale di Delhi</p></td>
<td><p>Politica vocale di Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Usi PSTN</p></td>
<td><p>Uso di Delhi, uso del PBX, uso di HYD PBX</p></td>
<td><p>Uso di Hyderabad, uso del PBX HYD, uso del PBX</p></td>
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

## <a name="enable-location-based-routing-in-the-routing-configuration"></a>Abilitare il routing basato sulla posizione nella configurazione di routing

Infine, abilitare globalmente il routing basato sulla posizione alla configurazione di routing. Usare il comando di Windows PowerShell di Lync Server, New-CsRoutingConfiguration, per abilitare il routing basato sulla posizione.

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

Per altre informazioni, vedere [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).

<div>


> [!NOTE]  
> mentre il routing basato sulla posizione deve essere abilitato tramite una configurazione globale, il set di regole da applicare verrà applicato solo per i siti, gli utenti e i trunk per i quali è stato configurato come specificato in questa documentazione.



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

