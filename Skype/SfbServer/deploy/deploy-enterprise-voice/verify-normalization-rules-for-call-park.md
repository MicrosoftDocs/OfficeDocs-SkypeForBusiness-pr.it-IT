---
title: Verificare le regole di normalizzazione per il parcheggio di chiamata in Skype for business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Informazioni sulle regole di normalizzazione per il parcheggio di chiamata in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: d1bcd6817b1f59f73a8c4ef1562e90253a99bd30
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830576"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a><span data-ttu-id="5ebfc-103">Verificare le regole di normalizzazione per il parcheggio di chiamata in Skype for business</span><span class="sxs-lookup"><span data-stu-id="5ebfc-103">Verify normalization rules for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="5ebfc-104">Informazioni sulle regole di normalizzazione per il parcheggio di chiamata in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="5ebfc-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="5ebfc-105">Le orbite del parcheggio di chiamata non devono essere normalizzate.</span><span class="sxs-lookup"><span data-stu-id="5ebfc-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="5ebfc-106">Controllare i dial plan per assicurarsi che i numeri dell'orbita non siano normalizzati.</span><span class="sxs-lookup"><span data-stu-id="5ebfc-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="5ebfc-107">Se è necessario creare una regola di normalizzazione aggiuntiva per evitare che le orbite vengano normalizzate, seguire la procedura descritta in [creare o modificare un dial plan in Skype for Business Server](dial-plans.md) per definire una nuova regola di normalizzazione, in modo che il **motivo corrispondente** identifichi l'intervallo di orbita e il **modello di conversione** sia **$1**.</span><span class="sxs-lookup"><span data-stu-id="5ebfc-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="5ebfc-108">Ad esempio, se l'intervallo di orbit del parcheggio di chiamata è 7000-7999, il **motivo corrispondente** è **^ (7 \ d {3} ) $** e la modalità di **conversione** è **$1**.</span><span class="sxs-lookup"><span data-stu-id="5ebfc-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5ebfc-109">Verificare che la regola di normalizzazione predefinita nei dial plan non contenga **^ (\d \* )**.</span><span class="sxs-lookup"><span data-stu-id="5ebfc-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="5ebfc-110">In caso contrario, la regola di normalizzazione del parcheggio di chiamata non verrà mai eseguita.</span><span class="sxs-lookup"><span data-stu-id="5ebfc-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5ebfc-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ebfc-111">See also</span></span>

[<span data-ttu-id="5ebfc-112">Creare o modificare un dial plan in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5ebfc-112">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

