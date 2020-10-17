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
ms.openlocfilehash: e4612fb48c2e526fa501ebc5f7342d7797ca47b8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511603"
---
# <a name="restoring-a-lync-server-pool-in-lync-server-2013"></a><span data-ttu-id="09feb-102">Ripristino di un pool di Lync Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09feb-102">Restoring a Lync Server pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09feb-103">_**Ultimo argomento modificato:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="09feb-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="09feb-104">La distribuzione di Lync Server può includere uno dei tipi di pool seguenti:</span><span class="sxs-lookup"><span data-stu-id="09feb-104">Your Lync Server deployment may include any of the following types of pools:</span></span>

  - <span data-ttu-id="09feb-105">Front End Server</span><span class="sxs-lookup"><span data-stu-id="09feb-105">Front End Server</span></span>

  - <span data-ttu-id="09feb-106">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="09feb-106">Mediation Server</span></span>

  - <span data-ttu-id="09feb-107">server Persistent Chat</span><span class="sxs-lookup"><span data-stu-id="09feb-107">Persistent Chat Server</span></span>

  - <span data-ttu-id="09feb-108">Edge Server</span><span class="sxs-lookup"><span data-stu-id="09feb-108">Edge Server</span></span>

<span data-ttu-id="09feb-109">Se un intero pool avverte un'interruzione, seguire queste procedure per ogni server membro del pool.</span><span class="sxs-lookup"><span data-stu-id="09feb-109">If an entire pool experiences an outage, follow these procedures for each member server in the pool.</span></span>

  - <span data-ttu-id="09feb-110">Per un pool Front End, ripristinare innanzitutto il server back-end e quindi ripristinare ogni Front End Server.</span><span class="sxs-lookup"><span data-stu-id="09feb-110">For a Front End pool, restore the Back End Server first, and then restore each Front End Server.</span></span> <span data-ttu-id="09feb-111">Per ulteriori informazioni, vedere [ripristino di un server back-end Enterprise Edition in Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) e [ripristino di un server membro Enterprise Edition in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="09feb-111">For details, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) and [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

  - <span data-ttu-id="09feb-112">Per tutti gli altri tipi di pool, ripristinare ogni server membro.</span><span class="sxs-lookup"><span data-stu-id="09feb-112">For all other types of pools, restore each member server.</span></span> <span data-ttu-id="09feb-113">Per informazioni dettagliate, vedere [Restoring an Enterprise Edition member server in Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="09feb-113">For details, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

