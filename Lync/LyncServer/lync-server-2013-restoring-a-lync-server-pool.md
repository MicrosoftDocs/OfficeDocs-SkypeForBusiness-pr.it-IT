---
title: 'Lync Server 2013: ripristino di un pool di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Lync Server pool
ms:assetid: 6fe80fb3-38ad-4931-a07b-1763b61aa448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202176(v=OCS.15)
ms:contentKeyID: 51541488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f43cbe049fdedc2f0b4d31eecc4a0506a4a62201
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-lync-server-pool-in-lync-server-2013"></a><span data-ttu-id="9b09b-102">Ripristino di un pool di Lync Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b09b-102">Restoring a Lync Server pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b09b-103">_**Argomento Ultima modifica:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="9b09b-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="9b09b-104">La distribuzione di Lync Server può includere uno dei tipi di pool seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b09b-104">Your Lync Server deployment may include any of the following types of pools:</span></span>

  - <span data-ttu-id="9b09b-105">Server front-end</span><span class="sxs-lookup"><span data-stu-id="9b09b-105">Front End Server</span></span>

  - <span data-ttu-id="9b09b-106">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="9b09b-106">Mediation Server</span></span>

  - <span data-ttu-id="9b09b-107">Server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="9b09b-107">Persistent Chat Server</span></span>

  - <span data-ttu-id="9b09b-108">Edge Server</span><span class="sxs-lookup"><span data-stu-id="9b09b-108">Edge Server</span></span>

<span data-ttu-id="9b09b-109">Se un intero pool avverte un'interruzione, seguire queste procedure per ogni server membro nel pool.</span><span class="sxs-lookup"><span data-stu-id="9b09b-109">If an entire pool experiences an outage, follow these procedures for each member server in the pool.</span></span>

  - <span data-ttu-id="9b09b-110">Per un pool Front-End, ripristinare prima il server back-end e quindi ripristinare ogni server front-end.</span><span class="sxs-lookup"><span data-stu-id="9b09b-110">For a Front End pool, restore the Back End Server first, and then restore each Front End Server.</span></span> <span data-ttu-id="9b09b-111">Per informazioni dettagliate, vedere [ripristino di un server back-end Enterprise Edition in Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) e [ripristino di un server membro di Enterprise Edition in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="9b09b-111">For details, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) and [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

  - <span data-ttu-id="9b09b-112">Per tutti gli altri tipi di pool, ripristinare ogni server membro.</span><span class="sxs-lookup"><span data-stu-id="9b09b-112">For all other types of pools, restore each member server.</span></span> <span data-ttu-id="9b09b-113">Per informazioni dettagliate, vedere [ripristino di un server membro di Enterprise Edition in Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="9b09b-113">For details, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

