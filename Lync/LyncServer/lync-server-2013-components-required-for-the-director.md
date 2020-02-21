---
title: 'Lync Server 2013: componenti necessari per il Director'
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
ms.openlocfilehash: 84a5765ce21ba955e4354c693171180a9d828210
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204702"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-required-for-the-director-in-lync-server-2013"></a>Componenti necessari per il Director in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-08_

L'unico componente necessario per la creazione e la configurazione di un Director è la distribuzione del ruolo server Director. A tale scopo, utilizzare Generatore di topologie e definire un pool di computer singolo o un pool di più computer nel nodo Pool di server Director. Dopo aver definito il Director o il pool di Director, eseguire la distribuzione guidata di Lync Server nel computer che sarà un Director. Nel caso di un pool di server Director, è possibile eseguire la distribuzione guidata di Lync su ogni server che sarà membro del pool.

<div>

## <a name="topologies"></a>Topologie

È possibile implementare un singolo server Director o un pool di Director. Il Director è sempre un server o un pool separato, non collocato con qualsiasi altro ruolo del server in Lync Server 2013.

<div>


> [!NOTE]  
> Se non si distribuiscono i direttori, il front end server o il pool Front End assumerà il ruolo di amministratore.



</div>

Un pool di Director deve essere bilanciato con bilanciamento del carico. È possibile effettuare una delle operazioni seguenti:

  - Creare una topologia che usa un servizio di bilanciamento del carico hardware per i servizi Web e un bilanciamento del carico DNS (Domain Name System) per le altre tipologie di traffico.
    
    [Pool di server Director con scalabilità orizzontale-bilanciamento del carico DNS e bilanciamento del carico hardware in Lync 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - Creare una topologia che utilizza un dispositivo di bilanciamento del carico hardware per il bilanciamento del carico necessario per il pool di server Director.
    
    [Pool di server Director con scalabilità orizzontale-bilanciamento del carico hardware in Lync 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

