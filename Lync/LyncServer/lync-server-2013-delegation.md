---
title: 'Lync Server 2013: Delega'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delegation
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994045(v=OCS.15)
ms:contentKeyID: 51803956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82be0bdc382440cc8a4307dc0ba981f31c5a9313
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegation-in-lync-server-2013"></a>Delega in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-09_

Le funzionalità di delega di Lync sono interessate dal routing basato sulla posizione nel modo seguente:

  - Quando un delegato abilitato per il routing basato sulla posizione effettua una chiamata per conto di un Manager, il criterio vocale del delegato viene usato per autorizzare la chiamata e i criteri di routing vocale del sito del delegato verranno usati per instradare la chiamata

  - Per le chiamate PSTN in arrivo a un responsabile, le stesse regole applicabili per l'inoltro di chiamata o lo squillo simultaneo verranno applicate come descritto negli argomenti trasferimento chiamate e inoltro e squillo simultaneo.

  - Quando un delegato imposta un endpoint PSTN come destinazione squillo simultaneo, per una chiamata in arrivo al Manager, il criterio di routing vocale del sito associato al trunk in arrivo verrà usato per instradare la chiamata all'endpoint PSTN del delegato.

  - Per la delega, è consigliabile che il responsabile e i delegati associati si trovino in genere nello stesso sito di rete.

<div>

## <a name="see-also"></a>Vedere anche


[Scenari per il routing in base alla posizione in Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

