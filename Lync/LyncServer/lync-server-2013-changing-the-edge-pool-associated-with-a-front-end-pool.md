---
title: 'Lync Server 2013: Modifica del pool di server perimetrali associato a un pool Front End'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changing the Edge pool associated with a Front End pool
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49733613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bbb2e6ffdaa238dcbd4a184c8db890c26dd6340
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="a6381-102">Modifica del pool di server perimetrali associato a un pool Front End in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6381-102">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6381-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="a6381-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="a6381-104">Se un pool di bordi scende ma il pool Front-end nello stesso sito è ancora in corso, è necessario impostare il pool Front-end in modo da usare un pool di Edge in un sito diverso fino a quando non viene ripristinato il pool di Edge non riuscito.</span><span class="sxs-lookup"><span data-stu-id="a6381-104">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="a6381-105">Modifica del pool di bordi associato a un pool Front-End</span><span class="sxs-lookup"><span data-stu-id="a6381-105">Changing the Edge Pool Associated with a Front End Pool</span></span>

1.  <span data-ttu-id="a6381-106">In Generatore di topologie passare al nome del pool Front-end che è necessario modificare.</span><span class="sxs-lookup"><span data-stu-id="a6381-106">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="a6381-107">Fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a6381-107">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="a6381-108">Nella sezione **associazioni** , in **associa Edge pool (per i componenti multimediali)**, usare la casella di controllo a discesa per selezionare il pool di bordi a cui si vuole associare questo pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="a6381-108">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="a6381-109">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6381-109">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a6381-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6381-110">See Also</span></span>


[<span data-ttu-id="a6381-111">Ripristino di emergenza dei server perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6381-111">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

