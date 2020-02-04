---
title: 'Lync Server 2013: Chiamate in arrivo'
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
ms.openlocfilehash: e70e5a489cbfa581c666374e6535b898727e1fdc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="incoming-calls-in-lync-server-2013"></a>Chiamate in arrivo in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-09_

Il routing delle chiamate in arrivo agli utenti abilitati per il routing basato sulla posizione dipende dalla posizione dell'endpoint dell'utente. Il routing delle chiamate in arrivo è influenzato dal modo seguente. Se un utente ha una chiamata in arrivo a un endpoint situato in un sito di rete abilitato per il routing basato sulla posizione e l'endpoint si trova nello stesso sito di rete del gateway PSTN, la chiamata verrà instradata. Se un utente ha una chiamata in arrivo a un endpoint situato in un sito di rete abilitato per il routing basato sulla posizione e l'endpoint si trova in un sito di rete diverso rispetto al gateway PSTN, la chiamata non verrà instradata. Quando un utente non ha endpoint situati nello stesso sito di rete del gateway PSTN in cui viene originata la chiamata in arrivo, la chiamata in arrivo verrà instradata direttamente alla segreteria telefonica dell'utente e verrà inviata una notifica di chiamata senza risposta alla festa chiamata.

Le impostazioni di inoltro di chiamata di un utente abilitato per il routing basato sulla posizione continueranno ad essere applicate, tuttavia, le chiamate inoltrate saranno soggette alle restrizioni di routing basate sulla posizione dell'utente.

Nella tabella seguente viene illustrato il modo in cui il routing basato sulla posizione influisce sul routing delle chiamate in ingresso a seconda della posizione dell'endpoint del destinatario. Il sito di rete del gateway PSTN è abilitato per il routing basato sulla posizione e il routing basato sulla posizione consente solo il routing delle chiamate PSTN agli endpoint nello stesso sito di rete.

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a>Chiamata in ricezione di una chiamata in ingresso dalla rete PSTN

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
<th>Endpoint di callee situato nello stesso sito di rete di gateway PSTN</th>
<th>Endpoint del destinatario non presente nello stesso sito di rete di gateway PSTN</th>
<th>Endpoint del destinatario situato nel sito di rete sconosciuto o non abilitato per il routing basato sulla posizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Routing della chiamata PSTN in ingresso</p></td>
<td><p>La chiamata in arrivo viene instradata agli endpoint del chiamato</p></td>
<td><p>La chiamata in arrivo non viene instradata agli endpoint del chiamato</p></td>
<td><p>La chiamata in arrivo non viene instradata agli endpoint del chiamato</p></td>
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

