---
title: 'Lync Server 2013: modifica del pool di Edge associato a un pool Front End'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing the Edge pool associated with a Front End pool
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49733613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73d28a6641df35ac1de29fb1f6668e628e8e0ec9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="c0428-102">Modifica del pool di server perimetrali associato a un pool Front end in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="c0428-102">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0428-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c0428-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="c0428-104">Se si verifica un'interruzione di un pool di server perimetrali di un sito, ma il pool Front End dello stesso sito è ancora in esecuzione, sarà necessario impostare il pool Front End in modo che venga utilizzato un pool di server perimetrali di un altro sito fino a quando il pool di server perimetrali non viene ripristinato.</span><span class="sxs-lookup"><span data-stu-id="c0428-104">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="c0428-105">Modifica del pool di server perimetrali associato a un pool Front End</span><span class="sxs-lookup"><span data-stu-id="c0428-105">Changing the Edge Pool Associated with a Front End Pool</span></span>

1.  <span data-ttu-id="c0428-106">Nel Generatore di topologie individuare il nome del pool Front End che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="c0428-106">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="c0428-107">Fare clic con il pulsante destro del mouse sul pool e scegliere **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="c0428-107">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="c0428-108">Nella sezione **Associazioni**, in **Associa pool di server perimetrali (per componenti multimediali)**, usare la casella di riepilogo a discesa per selezionare il pool di server perimetrali a cui si vuole associare il pool Front End.</span><span class="sxs-lookup"><span data-stu-id="c0428-108">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="c0428-109">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0428-109">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c0428-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0428-110">See Also</span></span>


[<span data-ttu-id="c0428-111">Ripristino di emergenza del server perimetrale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0428-111">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

