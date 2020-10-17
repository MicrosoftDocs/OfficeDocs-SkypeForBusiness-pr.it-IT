---
title: 'Lync Server 2013: squillo simultaneo'
description: 'Lync Server 2013: squillo simultaneo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 595c8c1d4ce105e2189002f18733ffae92cff8bf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555662"
---
# <a name="simultaneous-ringing-in-lync-server-2013"></a>Squillo simultaneo in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-09_

Quando la parte chiamata è abilitata alla suoneria simultanea, Location-Based routing analizza la posizione della parte chiamante e gli endpoint delle parti denominate per determinare se la chiamata deve essere instradata.

Nella tabella seguente è illustrato un utente configurato con squillo simultaneo e la destinazione di squillo simultaneo è un utente nello stesso sito di rete, in un sito di rete diverso o in un sito di rete sconosciuto.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Chiamata PSTN in ingresso per</th>
<th>Si trova nello stesso sito di rete del destinatario della chiamata</th>
<th>Si trova in un sito di rete diverso dal destinatario della chiamata</th>
<th>Si trova in un sito di rete sconosciuto o non è abilitato per il routing Location-Based</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utente di Lync</p></td>
<td><p>Squillo simultaneo consentito</p></td>
<td><p>Squillo simultaneo non consentito</p></td>
<td><p>Squillo simultaneo non consentito</p></td>
</tr>
</tbody>
</table>

  
Nella tabella seguente viene illustrata una chiamata proveniente da un utente Lync (ovvero il chiamante Lync) nello stesso sito di rete, in un sito di rete diverso o da un sito di rete sconosciuto. Il destinatario della chiamata ha un endpoint PSTN (i.e. cellulare) configurato come destinazione anello simultaneo. In questo scenario, Location-Based routing determinerà se la chiamata deve essere instradata alla destinazione dell'anello simultaneo (i.e. cellulare) del destinatario della chiamata oppure no.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Destinazione anello simultaneo</th>
<th>Si trova nello stesso sito di rete del destinatario della chiamata</th>
<th>Si trova in un sito di rete diverso dal destinatario della chiamata</th>
<th>Si trova in un sito di rete sconosciuto o non è abilitato per il routing Location-Based</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Endpoint PSTN</p></td>
<td><p>Squillo simultaneo consentito tramite il criterio di routing vocale del sito del chiamante</p></td>
<td><p>Squillo simultaneo consentito tramite il criterio di routing vocale del sito del chiamante</p></td>
<td><p>Squillo simultaneo consentito tramite il criterio vocale del chiamante ai trunk non abilitati per il routing Location-Based</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Vedere anche


[Scenari per il routing Location-Based in Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

