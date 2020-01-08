---
title: 'Lync Server 2013: Squillo simultaneo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7303c1fc77d109bd08044c8acff56aaf538790d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976515"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a>Squillo simultaneo in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-09_

Quando l'entità denominata ha attivato la chiamata simultanea, il routing basato sulla posizione analizza la posizione della parte chiamante e gli endpoint delle parti chiamate per determinare se la chiamata deve essere instradata.

La tabella seguente illustra un utente configurato con squillo simultaneo e la destinazione di chiamata simultanea è un utente nello stesso sito di rete, in un sito di rete diverso o in un sito di rete sconosciuto.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Chiamata PSTN in arrivo per</th>
<th>Situato nello stesso sito di rete di un chiamato</th>
<th>Situato in un sito di rete diverso rispetto al chiamato</th>
<th>Si trova in un sito di rete sconosciuto o non è abilitato per il routing basato sulla posizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utenti di Lync</p></td>
<td><p>Squillo simultaneo consentito</p></td>
<td><p>Anello simultaneo non consentito</p></td>
<td><p>Anello simultaneo non consentito</p></td>
</tr>
</tbody>
</table>

  
Nella tabella seguente viene illustrata una chiamata da un utente di Lync (ad esempio il chiamante di Lync) nello stesso sito di rete, in un sito di rete diverso o da un sito di rete sconosciuto. Il chiamato ha un endpoint PSTN (i.e. cellulare) configurato come destinazione squillo simultaneo. In questo scenario, il routing basato sulla posizione determinerà se la chiamata deve essere instradata alla destinazione squillo simultanea (ad esempio cellulare) del destinatario o meno.


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
<th>Situato nello stesso sito di rete di un chiamato</th>
<th>Situato in un sito di rete diverso rispetto al chiamato</th>
<th>Si trova in un sito di rete sconosciuto o non è abilitato per il routing basato sulla posizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Endpoint PSTN</p></td>
<td><p>Squillo simultaneo consentito tramite il criterio di routing vocale del sito del chiamante</p></td>
<td><p>Squillo simultaneo consentito tramite il criterio di routing vocale del sito del chiamante</p></td>
<td><p>Squillo simultaneo consentito tramite il criterio vocale del chiamante per Trunks non abilitato per il routing basato sulla posizione</p></td>
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

