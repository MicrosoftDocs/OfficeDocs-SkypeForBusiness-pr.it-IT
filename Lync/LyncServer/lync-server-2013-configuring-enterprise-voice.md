---
title: 'Lync Server 2013: configurazione di VoIP aziendale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Enterprise Voice
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994041(v=OCS.15)
ms:contentKeyID: 51803952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e46bd64efd8aa2eb6e1aead17083aa8593c8544
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978770"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-voice-in-lync-server-2013"></a>Configurazione di VoIP aziendale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-12_

Per distribuire Enterprise Voice, è necessario configurare le operazioni seguenti:

  - Creare un trunk

  - Definire un criterio vocale

  - Definire una route vocale

  - Abilitare gli utenti per VoIP aziendale

<div>

## <a name="create-a-trunk"></a>Creare un trunk

È necessario definire Trunks nella distribuzione di VoIP aziendale. Per il routing basato sulla posizione, devi creare una configurazione trunk per tronco. Usare il generatore di topologia di Lync Server per definire i trunk e usare il comando Lync Server di Windows PowerShell, New-CsTrunkConfiguration o il pannello di controllo di Lync Server per definire le configurazioni trunk corrispondenti. Altre informazioni su come abilitare il routing basato sulla posizione sulle configurazioni trunk sono disponibili nella sezione abilitare il routing basato sulla posizione ai trunk, nell'argomento abilitare il [routing basato sulla posizione in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md). Per questo esempio, la tabella seguente illustra i trunk usati in questo scenario.

Per altre informazioni, vedere [definire trunk aggiuntivi in Generatore di topologia in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).


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

È necessario definire i criteri vocali per la distribuzione vocale aziendale. Definire un criterio vocale per applicare restrizioni di routing basate sul percorso a un sottoinsieme di utenti, se è necessario solo un sottoinsieme per l'uso del routing basato sulla posizione. Per questo esempio, la tabella seguente illustra i criteri vocali usati in questo scenario. Nella tabella sono incluse solo le impostazioni specifiche del routing basato sulla posizione.

Per altre informazioni, vedere [configurazione di criteri vocali e record di utilizzo PSTN per autorizzare le funzionalità e i privilegi di chiamata in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).


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

È necessario definire le route vocali per la distribuzione vocale aziendale. Per questo esempio, la tabella seguente illustra le route vocali usate in questo scenario. Nella tabella sono incluse solo le impostazioni specifiche del routing basato sulla posizione.

Per altre informazioni, vedere [configurazione delle route vocali per le chiamate in uscita in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).


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
<td><p>Itinerario Delhi</p></td>
<td><p>Itinerario di Hyderabad</p></td>
<td><p>PBX del Route</p></td>
<td><p>Route HYD PBX</p></td>
</tr>
<tr class="even">
<td><p>Usi PSTN</p></td>
<td><p>Uso di Delhi</p></td>
<td><p>Uso di Hyderabad</p></td>
<td><p>Utilizzo di PBX del</p></td>
<td><p>Uso di HYD PBX</p></td>
</tr>
<tr class="odd">
<td><p>Tronco</p></td>
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

Consente agli utenti di VoIP aziendale di assegnare loro un criterio vocale già definito. Per questo esempio, la tabella seguente illustra l'assegnazione usata in questo scenario. Nella tabella sono incluse solo le impostazioni specifiche del routing basato sulla posizione.

Per altre informazioni, vedere [abilitare gli utenti per VoIP aziendale in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Utenti ubicati in Delhi</th>
<th>Utenti ubicati in Hyderabad</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Criterio vocale associato</p></td>
<td><p>Politica vocale di Delhi</p></td>
<td><p>Politica vocale di Hyderabad</p></td>
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


[Configurazione del routing in base alla posizione in Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

