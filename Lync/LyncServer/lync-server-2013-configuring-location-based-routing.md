---
title: 'Lync Server 2013: Configurazione del routing in base alla posizione'
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
ms.openlocfilehash: a0e82ae8a0dd9961bfeb9d2a513cb77b0affb2c4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a>Configurazione del routing in base alla posizione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-12_

Lync Server 2013 CU1, il routing basato sulla posizione è una caratteristica di Enterprise Voice. Il routing basato sulla posizione è una caratteristica di gestione delle chiamate che controlla il modo in cui le chiamate vengono instradate da Lync Server 2013 CU1. Impone le restrizioni sulla possibilità di indirizzare le chiamate a destinazioni PBX o PSTN in base alla posizione del chiamante di Lync. Il routing basato sulla posizione applica le regole di autorizzazione delle chiamate alle chiamate PSTN in base al percorso di rete del chiamante. La posizione del chiamante viene determinata in base al sito di rete associato alla subnet di rete a cui è connesso il chiamante. La configurazione del routing basato sulla posizione richiede prima di tutto la distribuzione di VoIP aziendale, quindi la configurazione di aree di rete, siti e subnet. In questo articolo viene impostata la base per l'abilitazione del routing basato sulla posizione.

Prima di distribuire il routing basato sulla posizione, è prima necessario distribuire Enterprise Voice e configurare aree di rete, siti e associare subnet di rete ai siti di rete. Una volta completato, è possibile configurare il routing basato sulla posizione. Per istruzioni su come configurare aree di rete, siti e subnet, vedere [distribuzione di funzionalità vocali avanzate in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

Questa sezione illustra la configurazione del routing basato sulla posizione usando l'esempio seguente come illustrazione.

![Esempio di routing in base alla posizione di VoIP aziendale](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Esempio di routing in base alla posizione di VoIP aziendale")

  
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
<td><p>Ufficio aziendale di Delhi</p></td>
<td><p>CANC-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</p></td>
</tr>
<tr class="even">
<td><p>Lync</p></td>
<td><p>Ufficio aziendale di Hyderabad</p></td>
<td><p>HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</p></td>
</tr>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>Sconosciuto (ad esempio Hotel)</p></td>
<td><p>UNK-LYNC-1</p></td>
</tr>
<tr class="even">
<td><p>PBX</p></td>
<td><p>Ufficio aziendale di Delhi</p></td>
<td><p>DEL-PBX-1, DEL-PBX-2</p></td>
</tr>
<tr class="odd">
<td><p>PBX</p></td>
<td><p>Ufficio aziendale di Hyderabad</p></td>
<td><p>HYD-PBX-1, HYD-PBX-2</p></td>
</tr>
<tr class="even">
<td><p>PSTN</p></td>
<td><p>Sconosciuto</p></td>
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
<th>Nome</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Pool di Lync Server 2013 CU1</p></td>
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

## <a name="in-this-section"></a>Contenuto della sezione

  - [Configurazione di VoIP aziendale in Lync Server 2013](lync-server-2013-configuring-enterprise-voice.md)

  - [Distribuzione di aree geografiche, siti e subnet di rete in Lync Server 2013](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [Abilitazione del routing basato sulla posizione in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Distribuzione di funzionalità vocali avanzate di Enterprise in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

