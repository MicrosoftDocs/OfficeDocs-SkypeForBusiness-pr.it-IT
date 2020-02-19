---
title: 'Lync Server 2013: configurazione del routing in base alla posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Location-Based Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994036(v=OCS.15)
ms:contentKeyID: 51803946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64e7df946d5e120352c2f0253a87197cb22b7276
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a>Configurazione del routing in base alla posizione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-12_

Lync Server 2013 CU1, il routing in base alla posizione è una funzionalità di VoIP aziendale. Il routing in base alla posizione è una funzionalità di gestione delle chiamate che controlla il modo in cui vengono instradate da Lync Server 2013 CU1. Impone restrizioni sul fatto che le chiamate possano essere instradate a destinazioni PBX o PSTN in base alla posizione del chiamante di Lync. Il routing in base alla posizione applica le regole di autorizzazione di chiamata alle chiamate PSTN basate sul percorso di rete del chiamante. La posizione del chiamante viene determinata in base al sito di rete associato alla subnet di rete a cui è connesso il chiamante. La configurazione del routing in base alla posizione richiede la prima distribuzione di VoIP aziendale, quindi la configurazione di aree di rete, siti e subnet. In questo modo viene impostata la base per l'abilitazione del routing in base alla posizione.

Prima di distribuire il routing in base alla posizione, è necessario prima distribuire VoIP aziendale e configurare aree di rete, siti e associare le subnet di rete ai siti di rete. Una volta completato, è possibile configurare il routing in base alla posizione. Per istruzioni su come configurare aree di rete, siti e subnet, vedere [Deploying Advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

In questa sezione viene illustrata la configurazione del routing in base alla posizione utilizzando l'esempio seguente come illustrazione.

![Esempio di routing basato sulla posizione di VoIP aziendale](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Esempio di routing basato sulla posizione di VoIP aziendale")

  
La tabella seguente rappresenta gli utenti definiti in questo esempio.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di endpoint</th>
<th>Posizione</th>
<th>Utenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>Ufficio corporativo di Delhi</p></td>
<td><p>CANC-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</p></td>
</tr>
<tr class="even">
<td><p>Lync</p></td>
<td><p>Ufficio corporativo di Hyderabad</p></td>
<td><p>HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</p></td>
</tr>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>Unknown (vale a dire Hotel)</p></td>
<td><p>UNK-LYNC-1</p></td>
</tr>
<tr class="even">
<td><p>PBX</p></td>
<td><p>Ufficio corporativo di Delhi</p></td>
<td><p>DEL-PBX-1, DEL-PBX-2</p></td>
</tr>
<tr class="odd">
<td><p>PBX</p></td>
<td><p>Ufficio corporativo di Hyderabad</p></td>
<td><p>HYD-PBX-1, HYD-PBX-2</p></td>
</tr>
<tr class="even">
<td><p>PSTN</p></td>
<td><p>Unknown</p></td>
<td><p>PSTN-1, PSTN-2, PSTN-3</p></td>
</tr>
</tbody>
</table>

  

La tabella seguente rappresenta i sistemi illustrati in questo esempio di ambiente.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Sistema</th>
<th>Posizione</th>
<th>Name</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 CU1 pool</p></td>
<td><p>qualsiasi</p></td>
<td><p>LS-PL1</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 CU1, Mediation Server</p></td>
<td><p>qualsiasi</p></td>
<td><p>MS-PL1</p></td>
</tr>
<tr class="odd">
<td><p>Gateway PSTN 1</p></td>
<td><p>Delhi</p></td>
<td><p>DEL-GW</p></td>
</tr>
<tr class="even">
<td><p>Gateway PSTN 2</p></td>
<td><p>Hyderabad</p></td>
<td><p>HYD-GW</p></td>
</tr>
<tr class="odd">
<td><p>PBX 1</p></td>
<td><p>Delhi</p></td>
<td><p>DEL-PBX</p></td>
</tr>
<tr class="even">
<td><p>PBX 2</p></td>
<td><p>Hyderabad</p></td>
<td><p>ROSSO-PBX</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Configurazione di VoIP aziendale in Lync Server 2013](lync-server-2013-configuring-enterprise-voice.md)

  - [Distribuzione di aree di rete, siti e subnet in Lync Server 2013](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [Abilitazione del routing in base alla posizione in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Distribuzione di funzionalità di VoIP aziendale avanzate in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

