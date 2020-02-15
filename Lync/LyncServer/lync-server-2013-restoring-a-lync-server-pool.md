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
ms.openlocfilehash: 6a4cfda150c1ea8fadba3adff98ab1a95255c11e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051228"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-lync-server-pool-in-lync-server-2013"></a><span data-ttu-id="e4d81-102">Ripristino di un pool di Lync Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4d81-102">Restoring a Lync Server pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4d81-103">_**Ultimo argomento modificato:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="e4d81-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="e4d81-104">La distribuzione di Lync Server può includere uno dei tipi di pool seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4d81-104">Your Lync Server deployment may include any of the following types of pools:</span></span>

  - <span data-ttu-id="e4d81-105">Front End Server</span><span class="sxs-lookup"><span data-stu-id="e4d81-105">Front End Server</span></span>

  - <span data-ttu-id="e4d81-106">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="e4d81-106">Mediation Server</span></span>

  - <span data-ttu-id="e4d81-107">server Persistent Chat</span><span class="sxs-lookup"><span data-stu-id="e4d81-107">Persistent Chat Server</span></span>

  - <span data-ttu-id="e4d81-108">Edge Server</span><span class="sxs-lookup"><span data-stu-id="e4d81-108">Edge Server</span></span>

<span data-ttu-id="e4d81-109">Se un intero pool avverte un'interruzione, seguire queste procedure per ogni server membro del pool.</span><span class="sxs-lookup"><span data-stu-id="e4d81-109">If an entire pool experiences an outage, follow these procedures for each member server in the pool.</span></span>

  - <span data-ttu-id="e4d81-110">Per un pool Front End, ripristinare innanzitutto il server back-end e quindi ripristinare ogni Front End Server.</span><span class="sxs-lookup"><span data-stu-id="e4d81-110">For a Front End pool, restore the Back End Server first, and then restore each Front End Server.</span></span> <span data-ttu-id="e4d81-111">Per ulteriori informazioni, vedere [ripristino di un server back-end Enterprise Edition in Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) e [ripristino di un server membro Enterprise Edition in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="e4d81-111">For details, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) and [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

  - <span data-ttu-id="e4d81-112">Per tutti gli altri tipi di pool, ripristinare ogni server membro.</span><span class="sxs-lookup"><span data-stu-id="e4d81-112">For all other types of pools, restore each member server.</span></span> <span data-ttu-id="e4d81-113">Per informazioni dettagliate, vedere [Restoring an Enterprise Edition member server in Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="e4d81-113">For details, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

