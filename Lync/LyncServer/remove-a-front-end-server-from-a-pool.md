---
title: Rimuovere un Front End Server da un pool
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cfcd96d0663ca977c83cc90b56bcafd9359a038
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500163"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="c47b5-102">Rimuovere un Front End Server da un pool</span><span class="sxs-lookup"><span data-stu-id="c47b5-102">Remove a Front End Server from a pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c47b5-103">_**Ultimo argomento modificato:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="c47b5-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="c47b5-104">Microsoft Lync Server 2010 Enterprise Edition Front End Server non può esistere come computer autonomo.</span><span class="sxs-lookup"><span data-stu-id="c47b5-104">The Microsoft Lync Server 2010 Enterprise Edition Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="c47b5-105">Deve essere definito come un pool Front End, anche se è presente un solo computer nel pool.</span><span class="sxs-lookup"><span data-stu-id="c47b5-105">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>

<span data-ttu-id="c47b5-106">In questo argomento vengono illustrate le procedure per la rimozione di un singolo front end server da un pool Front end esistente.</span><span class="sxs-lookup"><span data-stu-id="c47b5-106">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="c47b5-107">Se il front end server è l'ultimo server del pool o se si sta rimuovendo completamente il pool, vedere [Remove front end pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="c47b5-107">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="c47b5-108">Non è necessario rimuovere i singoli Front End Server prima di rimuovere il pool Front end.</span><span class="sxs-lookup"><span data-stu-id="c47b5-108">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="c47b5-109">Quando si rimuove il pool, è necessario rimuovere ogni Front End Server.</span><span class="sxs-lookup"><span data-stu-id="c47b5-109">When you remove the pool, you remove each Front End Server.</span></span>

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="c47b5-110">Per rimuovere un server Front End Server da un pool</span><span class="sxs-lookup"><span data-stu-id="c47b5-110">To remove a Front End Server from a pool</span></span>

1.  <span data-ttu-id="c47b5-111">Aprire Lync Server 2013 front end server, aprire Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="c47b5-111">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="c47b5-112">Passare al nodo Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c47b5-112">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="c47b5-113">Espandere **pool Enterprise Edition front end**, espandere il pool Front end con il front end server che si desidera rimuovere, fare clic con il pulsante destro del mouse sul front end server che si desidera rimuovere, quindi fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="c47b5-113">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

