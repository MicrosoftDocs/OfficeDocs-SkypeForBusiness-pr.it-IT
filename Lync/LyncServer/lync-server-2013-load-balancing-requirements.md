---
title: Requisiti per il bilanciamento del carico di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Load balancing requirements
ms:assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615011(v=OCS.15)
ms:contentKeyID: 48184697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83e5ebe92601b839f50604a93f10f7fc2f5d7deb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134962"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="load-balancing-requirements-for-lync-server-2013"></a>Requisiti per il bilanciamento del carico per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-05_

Se si dispone di pool Front End, pool di Director o pool di server perimetrali, è necessario distribuire il bilanciamento del carico per questi pool. Il bilanciamento del carico consente di distribuire il traffico tra i server in un pool.

Lync Server 2013 supporta due tipi di soluzioni di bilanciamento del carico per il traffico da client a server: bilanciamento del carico DNS (Domain Name System) e bilanciamento del carico hardware. Il bilanciamento del carico DNS offre diversi vantaggi, tra cui l'amministrazione più semplice, la risoluzione dei problemi più efficiente e la possibilità di isolare gran parte del traffico di Lync Server da eventuali problemi di bilanciamento del carico hardware.

Per stabilire quale soluzione di bilanciamento del carico è appropriata per ogni pool nella distribuzione, tenere presenti le restrizioni seguenti:

  - Per l'interfaccia perimetrale interna e per quella esterna è necessario utilizzare lo stesso tipo di bilanciamento del carico. Non è possibile utilizzare il bilanciamento del carico DNS in un'interfaccia e il bilanciamento del carico hardware nell'altra.

  - Alcuni tipi di traffico richiedono un servizio di bilanciamento del carico hardware. Il traffico HTTP richiede, ad esempio, un servizio di bilanciamento del carico hardware anziché il bilanciamento del carico DNS. Il bilanciamento del carico DNS non funziona con il traffico Web da client a server.

Per ulteriori informazioni sulla scelta di una soluzione di bilanciamento del carico hardware, vedere [requisiti hardware del dispositivo di bilanciamento del carico per Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).

Se si sceglie di utilizzare il bilanciamento del carico DNS per un pool, ma è comunque necessario implementare servizi di bilanciamento del carico hardware per il traffico, ad esempio il traffico HTTP, l'amministrazione dei servizi di bilanciamento del carico hardware risulta notevolmente semplificata. Ad esempio, la configurazione del servizio di bilanciamento del carico hardware sarà più semplice poiché gestirà solo il traffico HTTP e HTTPS, mentre tutti gli altri protocolli verranno gestiti dal bilanciamento del carico DNS. Per ulteriori informazioni, vedere [bilanciamento del carico DNS in Lync Server 2013](lync-server-2013-dns-load-balancing.md).

Per il traffico da server a server, Lync Server 2013 utilizza il bilanciamento del carico in grado di riconoscere la topologia. I server leggono la topologia pubblicata nell'archivio di gestione centrale per ottenere i nomi di dominio completi dei server nella topologia e distribuiscono automaticamente il traffico tra i server. Gli amministratori non devono configurare o gestire questo tipo di bilanciamento del carico.

Se si utilizza il bilanciamento del carico DNS ed è necessario bloccare il traffico verso un computer specifico, non è sufficiente rimuovere solo le voci degli indirizzi IP dal nome di dominio completo del pool. È necessario rimuovere anche la voce DNS per il computer.

</div>

<span> </span>

</div>

</div>

</div>

