---
title: 'Lync Server 2013: Chiamate in uscita'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Outgoing calls
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994049(v=OCS.15)
ms:contentKeyID: 51803960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2ccd095cfe27f173ff0fe7ac0dac92ca51a7c1d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="outgoing-calls-in-lync-server-2013"></a>Chiamate in uscita in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-09_

Il routing delle chiamate in uscita degli utenti abilitate per il routing basato sulla posizione è influenzato dalla posizione di rete dell'endpoint dell'utente. Nella tabella seguente viene illustrato il modo in cui il routing basato sulla posizione influenza il routing delle chiamate in uscita a seconda della posizione dell'endpoint del chiamante.

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a>Chiamante che effettua una chiamata in uscita alla rete PSTN

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Endpoint utente situato in un sito di rete abilitato per il routing basato sulla posizione</th>
<th>Endpoint utente situato in un sito di rete sconosciuto o non abilitato per il routing basato sulla posizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Autorizzazione delle chiamate in uscita</p></td>
<td><p>La chiamata è autorizzata in base al criterio vocale dell'utente</p></td>
<td><p>La chiamata è autorizzata in base al criterio vocale dell'utente</p></td>
</tr>
<tr class="even">
<td><p>Routing della chiamata in uscita</p></td>
<td><p>La chiamata viene instradata in base ai criteri di routing vocale del sito di rete</p></td>
<td><p>La chiamata viene instradata in base al criterio vocale dell'utente e solo tramite Trunks non abilitato per il routing basato sulla posizione (se disponibile)</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Vedere anche


[Scenari per il routing in base alla posizione in Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

