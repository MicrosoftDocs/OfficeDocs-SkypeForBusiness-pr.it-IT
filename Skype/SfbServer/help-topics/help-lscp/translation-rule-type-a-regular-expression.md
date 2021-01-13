---
title: Tipo di regola di conversione espressione regolare
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceRuleRegexEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ee83724-b399-4f8d-8f6d-4b53a26296b4
description: Nel campo Trova corrispondenza con specificare il modello di formato da utilizzare per trovare corrispondenze con i numeri da convertire. Nel campo Regola di conversione specificare un modello di formato dei numeri convertiti. Ad esempio, se si immette ^ \+ (\d {9} \d +) $ nel campo corrispondenza di questo modello e 011 $1 nel dominio della regola di conversione, la regola verrà convertita da + 441235551010 a 011441235551010.
ms.openlocfilehash: badbc5a34325e6bc2b5bef7e67ae39a4c8f02dc7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818856"
---
# <a name="translation-rule-type-a-regular-expression"></a><span data-ttu-id="5c192-105">Regola di traduzione: digitare un'espressione regolare</span><span class="sxs-lookup"><span data-stu-id="5c192-105">Translation Rule: Type a Regular Expression</span></span>
 
<span data-ttu-id="5c192-106">Nel campo **Trova corrispondenza con** specificare il modello di formato da utilizzare per trovare corrispondenze con i numeri da convertire.</span><span class="sxs-lookup"><span data-stu-id="5c192-106">In the **Match this pattern** field, specify the pattern that will be used to match the numbers to be translated.</span></span> <span data-ttu-id="5c192-107">Nel campo **Regola di conversione** specificare un modello di formato dei numeri convertiti.</span><span class="sxs-lookup"><span data-stu-id="5c192-107">In the **Translation rule** field, specify a pattern for the format of translated numbers.</span></span> <span data-ttu-id="5c192-108">Ad esempio, se si immette ^ \+ (\d {9} \d +) $ nel campo **corrispondenza di questo modello** e 011 $1 nel **dominio della regola di conversione** , la regola verrà convertita da + 441235551010 a 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="5c192-108">For example, if you enter ^\+(\d{9}\d+)$ in the **Match this pattern** field and 011$1 in the **Translation rule** field, the rule will translate +441235551010 to 011441235551010.</span></span>
  
<span data-ttu-id="5c192-109">Per informazioni dettagliate sulle diverse procedure che è possibile eseguire utilizzando il pannello di controllo di Skype for Business Server, vedere [Manage Skype for Business server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="5c192-109">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  

