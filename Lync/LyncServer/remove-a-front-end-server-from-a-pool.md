---
title: Rimuovere un Front End Server da un pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0637754c6e7b1a03c233025703297c182dc3099
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="af5b2-102">Rimuovere un Front End Server da un pool</span><span class="sxs-lookup"><span data-stu-id="af5b2-102">Remove a Front End Server from a pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af5b2-103">_**Argomento Ultima modifica:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="af5b2-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="af5b2-104">Il server front-end di Microsoft Lync Server 2010 Enterprise Edition non può esistere come computer autonomo.</span><span class="sxs-lookup"><span data-stu-id="af5b2-104">The Microsoft Lync Server 2010 Enterprise Edition Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="af5b2-105">Deve essere definito come pool Front-End, anche se è presente solo un singolo computer nel pool.</span><span class="sxs-lookup"><span data-stu-id="af5b2-105">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>

<span data-ttu-id="af5b2-106">Questo argomento illustra il processo di rimozione di un singolo server front-end da un pool Front-end esistente.</span><span class="sxs-lookup"><span data-stu-id="af5b2-106">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="af5b2-107">Se il server front-end è l'ultimo server del pool o se si sta rimuovendo completamente il pool, vedere [rimuovere il pool Front-end o il server Standard Edition](remove-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="af5b2-107">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="af5b2-108">Non è necessario rimuovere i singoli server front-end prima di rimuovere il pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="af5b2-108">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="af5b2-109">Quando si rimuove il pool, si rimuove ogni server front-end.</span><span class="sxs-lookup"><span data-stu-id="af5b2-109">When you remove the pool, you remove each Front End Server.</span></span>

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="af5b2-110">Per rimuovere un server front-end da un pool</span><span class="sxs-lookup"><span data-stu-id="af5b2-110">To remove a Front End Server from a pool</span></span>

1.  <span data-ttu-id="af5b2-111">Aprire il server front-end di Lync Server 2013, aprire Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="af5b2-111">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="af5b2-112">Passare al nodo Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="af5b2-112">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="af5b2-113">Espandi i **pool Front End di Enterprise Edition**, Espandi il pool Front end con il front end server che vuoi rimuovere, fai clic con il pulsante destro del mouse sul server front-end che vuoi rimuovere e quindi fai clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="af5b2-113">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

