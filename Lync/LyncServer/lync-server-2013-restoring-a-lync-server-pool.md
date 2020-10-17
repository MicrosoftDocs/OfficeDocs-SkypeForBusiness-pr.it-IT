---
title: 'Lync Server 2013: ripristino di un pool di Lync Server'
description: 'Lync Server 2013: ripristino di un pool di Lync Server.'
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
ms.openlocfilehash: 02e92b4e7af9cf782d49c265425006e0118b9161
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543812"
---
# <a name="restoring-a-lync-server-pool-in-lync-server-2013"></a><span data-ttu-id="91b8e-103">Ripristino di un pool di Lync Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91b8e-103">Restoring a Lync Server pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91b8e-104">_**Ultimo argomento modificato:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="91b8e-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="91b8e-105">La distribuzione di Lync Server può includere uno dei tipi di pool seguenti:</span><span class="sxs-lookup"><span data-stu-id="91b8e-105">Your Lync Server deployment may include any of the following types of pools:</span></span>

  - <span data-ttu-id="91b8e-106">Front End Server</span><span class="sxs-lookup"><span data-stu-id="91b8e-106">Front End Server</span></span>

  - <span data-ttu-id="91b8e-107">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="91b8e-107">Mediation Server</span></span>

  - <span data-ttu-id="91b8e-108">server Persistent Chat</span><span class="sxs-lookup"><span data-stu-id="91b8e-108">Persistent Chat Server</span></span>

  - <span data-ttu-id="91b8e-109">Edge Server</span><span class="sxs-lookup"><span data-stu-id="91b8e-109">Edge Server</span></span>

<span data-ttu-id="91b8e-110">Se un intero pool avverte un'interruzione, seguire queste procedure per ogni server membro del pool.</span><span class="sxs-lookup"><span data-stu-id="91b8e-110">If an entire pool experiences an outage, follow these procedures for each member server in the pool.</span></span>

  - <span data-ttu-id="91b8e-111">Per un pool Front End, ripristinare innanzitutto il server back-end e quindi ripristinare ogni Front End Server.</span><span class="sxs-lookup"><span data-stu-id="91b8e-111">For a Front End pool, restore the Back End Server first, and then restore each Front End Server.</span></span> <span data-ttu-id="91b8e-112">Per ulteriori informazioni, vedere [ripristino di un server back-end Enterprise Edition in Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) e [ripristino di un server membro Enterprise Edition in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="91b8e-112">For details, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) and [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

  - <span data-ttu-id="91b8e-113">Per tutti gli altri tipi di pool, ripristinare ogni server membro.</span><span class="sxs-lookup"><span data-stu-id="91b8e-113">For all other types of pools, restore each member server.</span></span> <span data-ttu-id="91b8e-114">Per informazioni dettagliate, vedere [Restoring an Enterprise Edition member server in Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="91b8e-114">For details, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

