---
title: 'Lync Server 2013: chiamate in ingresso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Incoming calls
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994038(v=OCS.15)
ms:contentKeyID: 51803948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c153af6e14c291189f714f7054f72301d6859a88
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="incoming-calls-in-lync-server-2013"></a>Chiamate in arrivo in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-09_

Il routing delle chiamate in arrivo agli utenti abilitati per il routing in base alla posizione dipende dalla posizione dell'endpoint dell'utente. Il routing delle chiamate in arrivo è influenzato nel modo seguente. Se un utente dispone di una chiamata in arrivo a un endpoint che si trova in un sito di rete abilitato per il routing basato sul percorso e che l'endpoint si trova nello stesso sito di rete del gateway PSTN, la chiamata verrà instradata. Se un utente dispone di una chiamata in arrivo a un endpoint che si trova in un sito di rete abilitato per il routing basato sul percorso e che l'endpoint si trova in un sito di rete diverso rispetto al gateway PSTN, la chiamata non verrà instradata. Quando un utente non dispone di endpoint situati nello stesso sito di rete del gateway PSTN da cui proviene la chiamata in arrivo, la chiamata in arrivo viene instradata direttamente alla segreteria telefonica dell'utente e viene inviata una notifica di chiamata senza risposta all'interlocutore chiamato.

Le impostazioni di inoltro di chiamata di un utente abilitato per il routing in base alla posizione continueranno a essere applicate, tuttavia, le chiamate inoltrate saranno soggette alle restrizioni di routing basate sul percorso dell'utente.

Nella tabella seguente viene illustrato il modo in cui il routing basato sulla posizione influisce sul routing delle chiamate in ingresso a seconda del percorso dell'endpoint del destinatario della chiamata. Il sito di rete del gateway PSTN è abilitato per il routing in base alla posizione e il routing in base alla posizione consente solo il routing delle chiamate PSTN agli endpoint all'interno dello stesso sito di rete.

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a>Destinatario chiamata che riceve una chiamata in ingresso dalla rete PSTN

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Endpoint del destinatario della chiamata che si trova nello stesso sito di rete del gateway PSTN</th>
<th>Endpoint del destinatario della chiamata non presente nello stesso sito di rete del gateway PSTN</th>
<th>Endpoint del destinatario della chiamata che si trova nel sito di rete sconosciuto o non abilitato per il routing in base alla posizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Routing della chiamata PSTN in ingresso</p></td>
<td><p>La chiamata in arrivo viene instradata agli endpoint del destinatario chiamata</p></td>
<td><p>La chiamata in arrivo non viene instradata agli endpoint del destinatario chiamata</p></td>
<td><p>La chiamata in arrivo non viene instradata agli endpoint del destinatario chiamata</p></td>
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

