---
title: Verificare le regole di normalizzazione per Call Park in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Informazioni sulle regole di normalizzazione per Call Park in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 38de300970341d563f2a532847a39c2fe98e15e7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240265"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a><span data-ttu-id="2e385-103">Verificare le regole di normalizzazione per Call Park in Skype for business</span><span class="sxs-lookup"><span data-stu-id="2e385-103">Verify normalization rules for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="2e385-104">Informazioni sulle regole di normalizzazione per Call Park in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="2e385-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="2e385-105">Le orbite del parcheggio delle chiamate non devono essere normalizzate.</span><span class="sxs-lookup"><span data-stu-id="2e385-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="2e385-106">Controlla i piani di chiamata per verificare che i numeri dell'orbita non siano normalizzati.</span><span class="sxs-lookup"><span data-stu-id="2e385-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="2e385-107">Se è necessario creare una regola di normalizzazione aggiuntiva per evitare che le orbite vengano normalizzate, seguire la procedura descritta in [creare o modificare un dial plan in Skype for Business Server](dial-plans.md) per definire una nuova regola di normalizzazione, in modo che il **modello corrisponda** identifica l'intervallo di orbite e il **modello di traduzione** è **$1**.</span><span class="sxs-lookup"><span data-stu-id="2e385-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="2e385-108">Ad esempio, se l'intervallo di Orbit di Call Park è 7000-7999, il **pattern da corrispondere** è **^ (7{3}\ d) $** e il **modello di traduzione** è **$1**.</span><span class="sxs-lookup"><span data-stu-id="2e385-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2e385-109">Assicurarsi che la regola di normalizzazione predefinita nei piani di chiamata non contenga **^ (\*\d)**.</span><span class="sxs-lookup"><span data-stu-id="2e385-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="2e385-110">In caso contrario, la regola di normalizzazione del parcheggio delle chiamate non verrà mai eseguita.</span><span class="sxs-lookup"><span data-stu-id="2e385-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2e385-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e385-111">See also</span></span>

[<span data-ttu-id="2e385-112">Creare o modificare un dial plan in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2e385-112">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

