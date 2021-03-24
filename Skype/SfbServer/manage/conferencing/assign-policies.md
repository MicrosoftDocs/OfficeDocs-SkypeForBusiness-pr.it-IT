---
title: Assegnare criteri di conferenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 'Riepilogo: informazioni su come assegnare criteri di conferenza in Skype for Business Server.'
ms.openlocfilehash: 61082a9189b085c852e7593207fc86dcc6509139
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099162"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="debf1-103">Assegnare criteri di conferenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="debf1-103">Assign conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="debf1-104">**Riepilogo:** Informazioni su come assegnare criteri di conferenza in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="debf1-104">**Summary:** Learn how to assign conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="debf1-105">È possibile assegnare criteri di conferenza agli utenti utilizzando Skype for Business Server Management Shell e il cmdlet **Grant-CsConferencingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="debf1-105">You can assign conferencing policies to users by using Skype for Business Server Management Shell and the **Grant-CsConferencingPolicy** cmdlet.</span></span>
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="debf1-106">Assegnare criteri di conferenza tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="debf1-106">Assign conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="debf1-107">Nell'esempio seguente il criterio SalesConferencingPolicy viene assegnato all'utente con identità "Ken Myer":</span><span class="sxs-lookup"><span data-stu-id="debf1-107">In the following example, the policy SalesConferencingPolicy is assigned to the user with the Identity "Ken Myer":</span></span>
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

<span data-ttu-id="debf1-108">Nell'esempio successivo, il criterio di conferenza FinanceConferencingPolicy viene assegnato a tutti gli utenti che dispongono di account nell'unità organizzativa Finance.</span><span class="sxs-lookup"><span data-stu-id="debf1-108">In the next example, the conferencing policy FinanceConferencingPolicy is assigned to all the users who have accounts in the Finance organizational unit.</span></span> <span data-ttu-id="debf1-109">Per assegnare lo stesso criterio a tutti gli utenti di una determinata unità organizzativa (OU), viene utilizzato il cmdlet Get-CsUser per recuperare tutti gli account di tale unità.</span><span class="sxs-lookup"><span data-stu-id="debf1-109">To assign the same policy to all the users in a given organizational unit (OU), the Get-CsUser cmdlet is used to retrieve all the accounts in that OU.</span></span> <span data-ttu-id="debf1-110">Dopo il recupero degli account utente, tali informazioni vengono quindi reindirizzate al cmdlet Grant-CsConferencingPolicy, che assegna il criterio FinanceConferencingPolicy a ogni utente della raccolta:</span><span class="sxs-lookup"><span data-stu-id="debf1-110">After the user accounts have been retrieved, that information is then piped to the Grant-CsConferencingPolicy cmdlet, which assigns the FinanceConferencingPolicy policy to each user in the collection:</span></span>
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

<span data-ttu-id="debf1-111">Per ulteriori informazioni, inclusa la sintassi completa e un elenco di parametri, vedere [Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="debf1-111">For more information, including complete syntax and a list of parameters, see [Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span></span>
