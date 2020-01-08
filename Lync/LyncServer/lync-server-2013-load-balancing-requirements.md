---
title: Requisiti di bilanciamento del carico di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Load balancing requirements
ms:assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615011(v=OCS.15)
ms:contentKeyID: 48184697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4848c78c755b95a15c28ab1f8e2555a180e22bfa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="load-balancing-requirements-for-lync-server-2013"></a>Requisiti di bilanciamento del carico per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-05_

Se sono presenti pool di front-end, pool di Director o pool di Edge Server, è necessario distribuire il bilanciamento del carico per questi pool. Il bilanciamento del carico distribuisce il traffico tra i server in un pool.

Lync Server 2013 supporta due tipi di soluzioni di bilanciamento del carico per il traffico da client a server: bilanciamento del carico DNS (Domain Name System) e bilanciamento del carico hardware. Il bilanciamento del carico DNS offre diversi vantaggi, tra cui l'amministrazione più semplice, la risoluzione dei problemi più efficiente e la possibilità di isolare gran parte del traffico di Lync Server da qualsiasi potenziale problema di bilanciamento del carico hardware.

Decidere quale soluzione di bilanciamento del carico è appropriata per ogni pool della distribuzione, tenendo presenti le restrizioni seguenti:

  - L'interfaccia perimetrale interna e l'interfaccia perimetrale esterna devono usare lo stesso tipo di bilanciamento del carico. Non è possibile usare il bilanciamento del carico DNS su un'interfaccia e un bilanciamento del carico hardware dall'altro.

  - Alcuni tipi di traffico richiedono un bilanciamento del carico hardware. Ad esempio, il traffico HTTP richiede un bilanciamento del carico hardware invece del bilanciamento del carico DNS. Il bilanciamento del carico DNS non funziona con il traffico Web da client a server.

Per altre informazioni sulla scelta di una soluzione di bilanciamento del carico hardware, vedere [requisiti di bilanciamento del carico hardware per Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).

Se si sceglie di usare il bilanciamento del carico DNS per un pool, ma occorre comunque implementare il bilanciamento del carico hardware per il traffico, ad esempio il traffico HTTP, l'amministrazione dei dispositivi di bilanciamento del carico hardware è notevolmente semplificata. Ad esempio, la configurazione del servizio di bilanciamento del carico hardware sarà più semplice perché gestirà solo il traffico HTTP e HTTPS, mentre tutti gli altri protocolli verranno gestiti dal bilanciamento del carico DNS. Per informazioni dettagliate, vedere [bilanciamento del carico DNS in Lync Server 2013](lync-server-2013-dns-load-balancing.md).

Per il traffico da server a server, Lync Server 2013 usa il bilanciamento del carico che supporta la topologia. I server leggono la topologia pubblicata in Central Management store per ottenere i nomi di dominio completi dei server nella topologia e distribuiscono automaticamente il traffico tra i server. Gli amministratori non devono configurare o gestire questo tipo di bilanciamento del carico.

Se si usa il bilanciamento del carico DNS ed è necessario bloccare il traffico verso un computer specifico, non è sufficiente rimuovere semplicemente le voci di indirizzo IP dall'FQDN del pool. È necessario rimuovere anche la voce DNS per il computer.

</div>

<span> </span>

</div>

</div>

</div>

