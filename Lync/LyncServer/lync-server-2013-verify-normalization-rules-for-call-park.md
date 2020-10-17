---
title: 'Lync Server 2013: verificare le regole di normalizzazione per il parcheggio di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify normalization rules for Call Park
ms:assetid: deaa170f-041e-45cb-8eab-f02931ab541e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398981(v=OCS.15)
ms:contentKeyID: 48185646
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 627832870de3a8306912d07134bb92caeee3076e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518623"
---
# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a><span data-ttu-id="4834c-102">Verificare le regole di normalizzazione per il parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4834c-102">Verify normalization rules for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4834c-103">_**Ultimo argomento modificato:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="4834c-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="4834c-104">Le orbite del parcheggio di chiamata non devono essere normalizzate.</span><span class="sxs-lookup"><span data-stu-id="4834c-104">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="4834c-105">Controllare i dial plan per assicurarsi che i numeri dell'orbita non siano normalizzati.</span><span class="sxs-lookup"><span data-stu-id="4834c-105">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="4834c-106">Se è necessario creare una regola di normalizzazione aggiuntiva per evitare che le orbite vengano normalizzate, seguire la procedura illustrata in [creare un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) per definire una nuova regola di normalizzazione, in modo che il **motivo corrispondente** identifichi l'intervallo di orbita e il **motivo di conversione** sia **$1**.</span><span class="sxs-lookup"><span data-stu-id="4834c-106">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="4834c-107">Ad esempio, se l'intervallo di orbit del parcheggio di chiamata è 7000 – 7999, il **motivo corrispondente** è **^ (7 \\ d {3} ) $** e il **motivo della conversione** è **$1**.</span><span class="sxs-lookup"><span data-stu-id="4834c-107">For example, if your Call Park orbit range is 7000 – 7999, the **Pattern to match** is **^(7\\d{3})$** and **Translation pattern** is **$1**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4834c-108">Verificare che la regola di normalizzazione predefinita nei dial plan non contenga <STRONG>^ (\d \*)</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4834c-108">Be sure that the default normalization rule in your dial plans does not contain <STRONG>^(\d\*)</STRONG>.</span></span> <span data-ttu-id="4834c-109">In caso contrario, la regola di normalizzazione del parcheggio di chiamata non verrà mai eseguita.</span><span class="sxs-lookup"><span data-stu-id="4834c-109">Otherwise, your Call Park normalization rule will never run.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4834c-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4834c-110">See Also</span></span>


[<span data-ttu-id="4834c-111">Creare un dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4834c-111">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

