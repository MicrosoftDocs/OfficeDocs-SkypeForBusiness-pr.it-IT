---
title: 'Lync Server 2013: delega'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegation
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994045(v=OCS.15)
ms:contentKeyID: 51803956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57de37ff1ef0b43a8a6ea9c03b715d3ebe570a6b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190909"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delegation-in-lync-server-2013"></a>Delega in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-09_

Le funzionalità di delega di Lync sono intaccate dal routing basato sulla posizione nel modo seguente:

  - Quando un delegato abilitato per il routing in base alla posizione inserisce una chiamata per conto di un responsabile, il criterio vocale del delegato viene utilizzato per autorizzare la chiamata e il criterio di routing vocale del sito del delegato verrà utilizzato per instradare la chiamata

  - Per le chiamate PSTN in arrivo a un Manager, si applicano le stesse regole applicabili per l'inoltro di chiamata o lo squillo simultaneo come descritto negli argomenti trasferimento di chiamata e inoltro e squillo simultaneo.

  - Quando un delegato imposta un endpoint PSTN come destinazione anello simultaneo, per una chiamata in arrivo al responsabile, il criterio di routing vocale del sito associato al trunk in ingresso verrà utilizzato per instradare la chiamata all'endpoint PSTN del delegato.

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

