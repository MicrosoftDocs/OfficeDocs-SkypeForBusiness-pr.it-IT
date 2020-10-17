---
title: 'Lync Server 2013: configurazione di VoIP aziendale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise Voice
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994041(v=OCS.15)
ms:contentKeyID: 51803952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca998a723e4ef84fc1c203d6eddc5f9016f28739
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532553"
---
# <a name="configuring-enterprise-voice-in-lync-server-2013"></a>Configurazione di VoIP aziendale in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-12_

Per distribuire VoIP aziendale, è necessario configurare quanto segue:

  - Creare un trunk

  - Definire un criterio vocale

  - Definire una route vocale

  - Abilitare gli utenti per VoIP aziendale

<div>

## <a name="create-a-trunk"></a>Creare un trunk

È necessario definire trunk nella distribuzione di VoIP aziendale. Per Location-Based il routing, è necessario creare una configurazione trunk per trunk. Utilizzare il generatore di topologie di Lync Server per definire i trunk e utilizzare il comando di Windows PowerShell di Lync Server, New-CsTrunkConfiguration o il pannello di controllo di Lync Server per definire le configurazioni trunk corrispondenti. Per ulteriori informazioni su come abilitare Location-Based routing sulle configurazioni trunk, vedere la sezione abilitare Location-Based routing ai trunk, nell'argomento, abilitando [Location-Based routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md). In questo esempio, nella tabella seguente vengono illustrati i trunk utilizzati in questo scenario.

Per ulteriori informazioni, vedere [definire ulteriori trunk in Generatore di topologie in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome trunk</th>
<th>Tipo di sistema</th>
<th>Nome</th>
<th>Posizione</th>
<th>Mediation Server</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Trunk 1 DEL-GW</p></td>
<td><p>Gateway PSTN</p></td>
<td><p>DEL-GW</p></td>
<td><p>Delhi</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>Trunk 2 HYD-GW</p></td>
<td><p>Gateway PSTN</p></td>
<td><p>HYD-GW</p></td>
<td><p>Hyderabad</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="odd">
<td><p>Trunk 3 DEL-PBX</p></td>
<td><p>PBX</p></td>
<td><p>DEL-PBX</p></td>
<td><p>Delhi</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>Trunk 4 HYD-PBX</p></td>
<td><p>PBX</p></td>
<td><p>HYD-PBX</p></td>
<td><p>Hyderabad</p></td>
<td><p>MS1</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a>Definisce i criteri vocali

È necessario definire i criteri vocali per la distribuzione di VoIP aziendale. Definire un criterio vocale per applicare Location-Based restrizioni di routing a un sottoinsieme di utenti se solo un sottoinsieme di essi è necessario per l'utilizzo del routing Location-Based. In questo esempio, nella tabella seguente sono illustrati i criteri vocali utilizzati in questo scenario. Solo le impostazioni specifiche per Location-Based il routing sono incluse nella tabella a scopo illustrativo.

Per ulteriori informazioni, vedere [configurazione di criteri vocali e record utilizzo PSTN per autorizzare le funzionalità e i privilegi di chiamata in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).


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
<td><p>False</p></td>
<td><p>False</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a>Definire le route vocali

È necessario definire le route vocali per la distribuzione di VoIP aziendale. In questo esempio, nella tabella seguente vengono illustrate le route vocali utilizzate in questo scenario. Solo le impostazioni specifiche per Location-Based il routing sono incluse nella tabella a scopo illustrativo.

Per ulteriori informazioni, vedere [configurazione delle route vocali per le chiamate in uscita in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Route vocale 1</th>
<th>Route vocale 2</th>
<th>Route vocale 3</th>
<th>Route vocale 4</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nome</p></td>
<td><p>Route Delhi</p></td>
<td><p>Route Hyderabad</p></td>
<td><p>PBX del Route</p></td>
<td><p>Route HYD PBX</p></td>
</tr>
<tr class="even">
<td><p>Utilizzi PSTN</p></td>
<td><p>Utilizzo Delhi</p></td>
<td><p>Utilizzo di Hyderabad</p></td>
<td><p>Utilizzo del sistema PBX del</p></td>
<td><p>Utilizzo di HYD PBX</p></td>
</tr>
<tr class="odd">
<td><p>Trunk</p></td>
<td><p>Trunk 1 DEL-GW</p></td>
<td><p>Trunk 2 HYD-GW</p></td>
<td><p>Trunk 3 DEL-PBX</p></td>
<td><p>Trunk 4 HYD-PBX</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a>Abilitare gli utenti per VoIP aziendale

Abilitare gli utenti per VoIP aziendale e assegnargli un criterio vocale precedentemente definito. In questo esempio, nella tabella seguente viene illustrata l'assegnazione utilizzata in questo scenario. Solo le impostazioni specifiche per Location-Based il routing sono incluse nella tabella a scopo illustrativo.

Per ulteriori informazioni, vedere [abilitare gli utenti per VoIP aziendale in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Utenti che si trovano a Delhi</th>
<th>Utenti che si trovano in Hyderabad</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Criteri vocali associati</p></td>
<td><p>Criteri vocali Delhi</p></td>
<td><p>Criteri vocali di Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Utenti di esempio</p></td>
<td><p>CANC-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</p></td>
<td><p>HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</p></td>
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

