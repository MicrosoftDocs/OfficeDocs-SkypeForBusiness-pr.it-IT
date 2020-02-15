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
ms.openlocfilehash: d5ab8e6038fd17daed7f10f11023793b702dd7d0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a><span data-ttu-id="24129-102">Verificare le regole di normalizzazione per il parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24129-102">Verify normalization rules for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24129-103">_**Ultimo argomento modificato:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="24129-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="24129-104">Le orbite del parcheggio di chiamata non devono essere normalizzate.</span><span class="sxs-lookup"><span data-stu-id="24129-104">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="24129-105">Controllare i dial plan per assicurarsi che i numeri dell'orbita non siano normalizzati.</span><span class="sxs-lookup"><span data-stu-id="24129-105">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="24129-106">Se è necessario creare una regola di normalizzazione aggiuntiva per evitare che le orbite vengano normalizzate, seguire la procedura illustrata in [creare un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) per definire una nuova regola di normalizzazione, in modo che il **motivo corrispondente** identifichi l'intervallo di orbita e il **motivo di conversione** sia **$1**.</span><span class="sxs-lookup"><span data-stu-id="24129-106">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="24129-107">Ad esempio, se l'intervallo di orbit del parcheggio di chiamata è 7000 – 7999, il **motivo corrispondente** è **^\\({3}7 d) $** e il **motivo della conversione** è **$1**.</span><span class="sxs-lookup"><span data-stu-id="24129-107">For example, if your Call Park orbit range is 7000 – 7999, the **Pattern to match** is **^(7\\d{3})$** and **Translation pattern** is **$1**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="24129-108">Verificare che la regola di normalizzazione predefinita nei dial plan non contenga <STRONG>^ (\d \*)</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="24129-108">Be sure that the default normalization rule in your dial plans does not contain <STRONG>^(\d\*)</STRONG>.</span></span> <span data-ttu-id="24129-109">In caso contrario, la regola di normalizzazione del parcheggio di chiamata non verrà mai eseguita.</span><span class="sxs-lookup"><span data-stu-id="24129-109">Otherwise, your Call Park normalization rule will never run.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="24129-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24129-110">See Also</span></span>


[<span data-ttu-id="24129-111">Creare un dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24129-111">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

