---
title: Tipo di regola di conversione espressione regolare
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceRuleRegexEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 5ee83724-b399-4f8d-8f6d-4b53a26296b4
ROBOTS: NOINDEX, NOFOLLOW
description: 'Nel campo Trova corrispondenza con specificare il modello di formato da utilizzare per trovare corrispondenze con i numeri da convertire. Nel campo Regola di conversione specificare un modello di formato dei numeri convertiti. '
ms.openlocfilehash: a1e04cc94c004b520c077816ae535ca4154047ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819986"
---
# <a name="translation-rule-type-a-regular-expression"></a><span data-ttu-id="7ad5a-104">Regola di traduzione: digitare un'espressione regolare</span><span class="sxs-lookup"><span data-stu-id="7ad5a-104">Translation Rule: Type a Regular Expression</span></span>
 
<span data-ttu-id="7ad5a-105">Nel campo **Trova corrispondenza con** specificare il modello di formato da utilizzare per trovare corrispondenze con i numeri da convertire.</span><span class="sxs-lookup"><span data-stu-id="7ad5a-105">In the **Match this pattern** field, specify the pattern that will be used to match the numbers to be translated.</span></span> <span data-ttu-id="7ad5a-106">Nel campo **Regola di conversione** specificare un modello di formato dei numeri convertiti.</span><span class="sxs-lookup"><span data-stu-id="7ad5a-106">In the **Translation rule** field, specify a pattern for the format of translated numbers.</span></span> <span data-ttu-id="7ad5a-107">Ad esempio, se si immette ^ (\d \d+)$ nel campo Corrispondenza modello e 011$1 nel campo regola di conversione, la regola tradurrà \+ {9} +441235551010 in 011441235551010.  </span><span class="sxs-lookup"><span data-stu-id="7ad5a-107">For example, if you enter ^\+(\d{9}\d+)$ in the **Match this pattern** field and 011$1 in the **Translation rule** field, the rule will translate +441235551010 to 011441235551010.</span></span> 
  
 
  

