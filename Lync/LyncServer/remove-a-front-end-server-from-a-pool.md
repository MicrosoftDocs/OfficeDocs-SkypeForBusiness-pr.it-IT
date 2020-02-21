---
title: Rimuovere un front end server da un pool
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
ms.openlocfilehash: 2e9cd348d6a96009e92dfa8a3ef50dae39eb013d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="ae424-102">Rimuovere un front end server da un pool</span><span class="sxs-lookup"><span data-stu-id="ae424-102">Remove a Front End Server from a pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae424-103">_**Ultimo argomento modificato:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="ae424-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="ae424-104">Microsoft Lync Server 2010 Enterprise Edition Front End Server non può esistere come computer autonomo.</span><span class="sxs-lookup"><span data-stu-id="ae424-104">The Microsoft Lync Server 2010 Enterprise Edition Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="ae424-105">Deve essere definito come un pool Front End, anche se è presente un solo computer nel pool.</span><span class="sxs-lookup"><span data-stu-id="ae424-105">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>

<span data-ttu-id="ae424-106">In questo argomento vengono illustrate le procedure per la rimozione di un singolo front end server da un pool Front end esistente.</span><span class="sxs-lookup"><span data-stu-id="ae424-106">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="ae424-107">Se il front end server è l'ultimo server del pool o se si sta rimuovendo completamente il pool, vedere [Remove front end pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="ae424-107">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="ae424-108">Non è necessario rimuovere i singoli Front End Server prima di rimuovere il pool Front end.</span><span class="sxs-lookup"><span data-stu-id="ae424-108">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="ae424-109">Quando si rimuove il pool, è necessario rimuovere ogni Front End Server.</span><span class="sxs-lookup"><span data-stu-id="ae424-109">When you remove the pool, you remove each Front End Server.</span></span>

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="ae424-110">Per rimuovere un server Front End Server da un pool</span><span class="sxs-lookup"><span data-stu-id="ae424-110">To remove a Front End Server from a pool</span></span>

1.  <span data-ttu-id="ae424-111">Aprire Lync Server 2013 front end server, aprire Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="ae424-111">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="ae424-112">Passare al nodo Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="ae424-112">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="ae424-113">Espandere **pool Enterprise Edition front end**, espandere il pool Front end con il front end server che si desidera rimuovere, fare clic con il pulsante destro del mouse sul front end server che si desidera rimuovere, quindi fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="ae424-113">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

