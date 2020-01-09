---
title: Assegnare criteri di conferenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 'Riepilogo: informazioni su come assegnare criteri di conferenza in Skype for Business Server.'
ms.openlocfilehash: f5e88e14c9516785cb3c45b5682bac13865b20ae
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991911"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="b1dbc-103">Assegnare criteri di conferenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b1dbc-103">Assign conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="b1dbc-104">**Riepilogo:** Informazioni su come assegnare criteri di conferenza in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b1dbc-104">**Summary:** Learn how to assign conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="b1dbc-105">Puoi assegnare criteri di conferenza agli utenti usando Skype for Business Server Management Shell e il cmdlet **Grant-CsConferencingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="b1dbc-105">You can assign conferencing policies to users by using Skype for Business Server Management Shell and the **Grant-CsConferencingPolicy** cmdlet.</span></span>
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b1dbc-106">Assegnare criteri di conferenza tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="b1dbc-106">Assign conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="b1dbc-107">Nell'esempio seguente, il criterio SalesConferencingPolicy viene assegnato all'utente con l'identità "Ken":</span><span class="sxs-lookup"><span data-stu-id="b1dbc-107">In the following example, the policy SalesConferencingPolicy is assigned to the user with the Identity "Ken Myer":</span></span>
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

<span data-ttu-id="b1dbc-108">Nell'esempio seguente, il criterio di conferenza FinanceConferencingPolicy viene assegnato a tutti gli utenti che hanno account nell'unità organizzativa Finance.</span><span class="sxs-lookup"><span data-stu-id="b1dbc-108">In the next example, the conferencing policy FinanceConferencingPolicy is assigned to all the users who have accounts in the Finance organizational unit.</span></span> <span data-ttu-id="b1dbc-109">Per assegnare lo stesso criterio a tutti gli utenti di una determinata unità organizzativa, viene usato il cmdlet Get-CsUser per recuperare tutti gli account in tale OU.</span><span class="sxs-lookup"><span data-stu-id="b1dbc-109">To assign the same policy to all the users in a given organizational unit (OU), the Get-CsUser cmdlet is used to retrieve all the accounts in that OU.</span></span> <span data-ttu-id="b1dbc-110">Dopo aver recuperato gli account utente, le informazioni vengono quindi inviate tramite pipe al cmdlet Grant-CsConferencingPolicy, che assegna i criteri FinanceConferencingPolicy a ogni utente della raccolta:</span><span class="sxs-lookup"><span data-stu-id="b1dbc-110">After the user accounts have been retrieved, that information is then piped to the Grant-CsConferencingPolicy cmdlet, which assigns the FinanceConferencingPolicy policy to each user in the collection:</span></span>
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

<span data-ttu-id="b1dbc-111">Per altre informazioni, inclusa la sintassi completa e un elenco di parametri, vedere [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b1dbc-111">For more information, including complete syntax and a list of parameters, see [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span></span>
  

