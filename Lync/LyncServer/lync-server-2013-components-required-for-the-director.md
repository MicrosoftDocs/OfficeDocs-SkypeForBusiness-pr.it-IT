---
title: 'Lync Server 2013: Componenti richiesti per il server Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for the Director
ms:assetid: 15c7c8d4-b93f-4386-b2d1-d76dab8f801e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398228(v=OCS.15)
ms:contentKeyID: 48183502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12db97a72a9882964727edd3084e0bd598527358
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-the-director-in-lync-server-2013"></a>Componenti richiesti per il server Director in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-08_

L'unico componente necessario per creare e configurare un amministratore consiste nel distribuire il ruolo del server Director. A tale scopo, USA generatore di topologia e Definisci un singolo pool di computer o un pool di computer multipli nel nodo del pool di Director. Dopo avere definito il pool di Director o Director, eseguire la distribuzione guidata di Lync Server nel computer che sarà un amministratore. Nel caso di un pool di Director, eseguire la distribuzione guidata di Lync Server in ogni server che sarà membro del pool.

<div>

## <a name="topologies"></a>Tecnologie

È possibile implementare un singolo server Director o un pool di Director. Il Director è sempre un server o un pool separato, non collocato con qualsiasi altro ruolo del server in Lync Server 2013.

<div>


> [!NOTE]  
> Se non si distribuiscono gli amministratori, il server front-end o il pool Front-End assumerà il ruolo di Director.



</div>

Un pool di amministratori deve essere carico bilanciato. È possibile eseguire una delle operazioni seguenti:

  - Creare una topologia che usa un dispositivo di bilanciamento del carico hardware per i servizi Web e il bilanciamento del carico DNS (Domain Name System) per gli altri tipi di traffico.
    
    [Pool di server Director con scalabilità implementata - bilanciamento del carico DNS e bilanciamento del carico hardware in Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - Creare una topologia che usa un bilanciamento del carico hardware per il bilanciamento del carico necessario per il pool di Director.
    
    [Pool di server Director con scalabilità implementata, servizio di bilanciamento del carico hardware in Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

