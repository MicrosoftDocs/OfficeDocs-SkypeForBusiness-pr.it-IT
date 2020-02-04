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

# <a name="components-required-for-the-director-in-lync-server-2013"></a><span data-ttu-id="00a7e-102">Componenti richiesti per il server Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00a7e-102">Components required for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00a7e-103">_**Argomento Ultima modifica:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="00a7e-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="00a7e-104">L'unico componente necessario per creare e configurare un amministratore consiste nel distribuire il ruolo del server Director.</span><span class="sxs-lookup"><span data-stu-id="00a7e-104">The only component required to create and configure a Director is to deploy the Director server role.</span></span> <span data-ttu-id="00a7e-105">A tale scopo, USA generatore di topologia e Definisci un singolo pool di computer o un pool di computer multipli nel nodo del pool di Director.</span><span class="sxs-lookup"><span data-stu-id="00a7e-105">You do this by using Topology Builder and define either a single computer pool or a multiple computer pool in the Director pool node.</span></span> <span data-ttu-id="00a7e-106">Dopo avere definito il pool di Director o Director, eseguire la distribuzione guidata di Lync Server nel computer che sarà un amministratore.</span><span class="sxs-lookup"><span data-stu-id="00a7e-106">After you have defined the Director or Director pool, run the Lync Server Deployment Wizard on the computer that will be a Director.</span></span> <span data-ttu-id="00a7e-107">Nel caso di un pool di Director, eseguire la distribuzione guidata di Lync Server in ogni server che sarà membro del pool.</span><span class="sxs-lookup"><span data-stu-id="00a7e-107">In the case of a Director pool, you run the Lync Server Deployment Wizard on each server that will be a member of the pool.</span></span>

<div>

## <a name="topologies"></a><span data-ttu-id="00a7e-108">Tecnologie</span><span class="sxs-lookup"><span data-stu-id="00a7e-108">Topologies</span></span>

<span data-ttu-id="00a7e-109">È possibile implementare un singolo server Director o un pool di Director.</span><span class="sxs-lookup"><span data-stu-id="00a7e-109">You can implement a single Director server or a Director pool.</span></span> <span data-ttu-id="00a7e-110">Il Director è sempre un server o un pool separato, non collocato con qualsiasi altro ruolo del server in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="00a7e-110">The Director is always a separate server or pool, not collocated with any other server role in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="00a7e-111">Se non si distribuiscono gli amministratori, il server front-end o il pool Front-End assumerà il ruolo di Director.</span><span class="sxs-lookup"><span data-stu-id="00a7e-111">If you do not deploy Directors, the Front End Server or Front End pool will assume the Director role.</span></span>



</div>

<span data-ttu-id="00a7e-112">Un pool di amministratori deve essere carico bilanciato.</span><span class="sxs-lookup"><span data-stu-id="00a7e-112">A pool of Directors must be load balanced.</span></span> <span data-ttu-id="00a7e-113">È possibile eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="00a7e-113">You can do one of the following:</span></span>

  - <span data-ttu-id="00a7e-114">Creare una topologia che usa un dispositivo di bilanciamento del carico hardware per i servizi Web e il bilanciamento del carico DNS (Domain Name System) per gli altri tipi di traffico.</span><span class="sxs-lookup"><span data-stu-id="00a7e-114">Create a topology that uses a hardware load balancer for web services and Domain Name System (DNS) load balancing for the other traffic types.</span></span>
    
    [<span data-ttu-id="00a7e-115">Pool di server Director con scalabilità implementata - bilanciamento del carico DNS e bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00a7e-115">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - <span data-ttu-id="00a7e-116">Creare una topologia che usa un bilanciamento del carico hardware per il bilanciamento del carico necessario per il pool di Director.</span><span class="sxs-lookup"><span data-stu-id="00a7e-116">Create a topology that uses a hardware load balancer for load balancing needed for the Director pool.</span></span>
    
    [<span data-ttu-id="00a7e-117">Pool di server Director con scalabilità implementata, servizio di bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00a7e-117">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

