---
title: 'Lync Server 2013: delega'
description: 'Lync Server 2013: delega.'
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
ms.openlocfilehash: 6dc25d0ea3dfd64ee1b71677e6bac55c1cb1ca32
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567452"
---
# <a name="delegation-in-lync-server-2013"></a>Delega in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-09_

Le funzionalità di delega di Lync sono intaccate dal routing Location-Based nel modo seguente:

  - Quando un delegato abilitato per il routing Location-Based inserisce una chiamata per conto di un responsabile, il criterio vocale del delegato viene utilizzato per autorizzare la chiamata e il criterio di routing vocale del sito del delegato verrà utilizzato per instradare la chiamata

  - Per le chiamate PSTN in arrivo a un Manager, si applicano le stesse regole applicabili per l'inoltro di chiamata o lo squillo simultaneo come descritto negli argomenti trasferimento di chiamata e inoltro e squillo simultaneo.

  - Quando un delegato imposta un endpoint PSTN come destinazione anello simultaneo, per una chiamata in arrivo al responsabile, il criterio di routing vocale del sito associato al trunk in ingresso verrà utilizzato per instradare la chiamata all'endpoint PSTN del delegato.

  - Per la delega, è consigliabile che il responsabile e i delegati associati si trovino in genere nello stesso sito di rete.

<div>

## <a name="see-also"></a>Vedere anche


[Scenari per il routing Location-Based in Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

