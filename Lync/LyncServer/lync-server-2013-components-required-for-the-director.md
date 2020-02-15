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
ms.openlocfilehash: e4409632afc61aea4606864e7dd230ad4d295935
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-the-director-in-lync-server-2013"></a><span data-ttu-id="06630-102">Componenti necessari per il Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06630-102">Components required for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06630-103">_**Ultimo argomento modificato:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="06630-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="06630-104">L'unico componente necessario per la creazione e la configurazione di un Director è la distribuzione del ruolo server Director.</span><span class="sxs-lookup"><span data-stu-id="06630-104">The only component required to create and configure a Director is to deploy the Director server role.</span></span> <span data-ttu-id="06630-105">A tale scopo, utilizzare Generatore di topologie e definire un pool di computer singolo o un pool di più computer nel nodo Pool di server Director.</span><span class="sxs-lookup"><span data-stu-id="06630-105">You do this by using Topology Builder and define either a single computer pool or a multiple computer pool in the Director pool node.</span></span> <span data-ttu-id="06630-106">Dopo aver definito il Director o il pool di Director, eseguire la distribuzione guidata di Lync Server nel computer che sarà un Director.</span><span class="sxs-lookup"><span data-stu-id="06630-106">After you have defined the Director or Director pool, run the Lync Server Deployment Wizard on the computer that will be a Director.</span></span> <span data-ttu-id="06630-107">Nel caso di un pool di server Director, è possibile eseguire la distribuzione guidata di Lync su ogni server che sarà membro del pool.</span><span class="sxs-lookup"><span data-stu-id="06630-107">In the case of a Director pool, you run the Lync Server Deployment Wizard on each server that will be a member of the pool.</span></span>

<div>

## <a name="topologies"></a><span data-ttu-id="06630-108">Topologie</span><span class="sxs-lookup"><span data-stu-id="06630-108">Topologies</span></span>

<span data-ttu-id="06630-109">È possibile implementare un singolo server Director o un pool di Director.</span><span class="sxs-lookup"><span data-stu-id="06630-109">You can implement a single Director server or a Director pool.</span></span> <span data-ttu-id="06630-110">Il Director è sempre un server o un pool separato, non collocato con qualsiasi altro ruolo del server in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="06630-110">The Director is always a separate server or pool, not collocated with any other server role in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="06630-111">Se non si distribuiscono i direttori, il front end server o il pool Front End assumerà il ruolo di amministratore.</span><span class="sxs-lookup"><span data-stu-id="06630-111">If you do not deploy Directors, the Front End Server or Front End pool will assume the Director role.</span></span>



</div>

<span data-ttu-id="06630-112">Un pool di Director deve essere bilanciato con bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="06630-112">A pool of Directors must be load balanced.</span></span> <span data-ttu-id="06630-113">È possibile effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="06630-113">You can do one of the following:</span></span>

  - <span data-ttu-id="06630-114">Creare una topologia che usa un servizio di bilanciamento del carico hardware per i servizi Web e un bilanciamento del carico DNS (Domain Name System) per le altre tipologie di traffico.</span><span class="sxs-lookup"><span data-stu-id="06630-114">Create a topology that uses a hardware load balancer for web services and Domain Name System (DNS) load balancing for the other traffic types.</span></span>
    
    [<span data-ttu-id="06630-115">Pool di server Director con scalabilità orizzontale-bilanciamento del carico DNS e bilanciamento del carico hardware in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="06630-115">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - <span data-ttu-id="06630-116">Creare una topologia che utilizza un dispositivo di bilanciamento del carico hardware per il bilanciamento del carico necessario per il pool di server Director.</span><span class="sxs-lookup"><span data-stu-id="06630-116">Create a topology that uses a hardware load balancer for load balancing needed for the Director pool.</span></span>
    
    [<span data-ttu-id="06630-117">Pool di server Director con scalabilità orizzontale-bilanciamento del carico hardware in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="06630-117">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

