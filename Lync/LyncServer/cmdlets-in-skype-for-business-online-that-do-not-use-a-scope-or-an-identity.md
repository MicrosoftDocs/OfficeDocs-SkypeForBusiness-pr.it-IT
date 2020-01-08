---
title: Cmdlet in Skype for business online che non usano un ambito o un'identità
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c7f6632640277a6a99626c18f458100f6a8cea0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975981"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a><span data-ttu-id="5d18c-102">Cmdlet in Skype for business online che non usano un ambito o un'identità</span><span class="sxs-lookup"><span data-stu-id="5d18c-102">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>

 


<span data-ttu-id="5d18c-103">I cmdlet usati per la modifica degli elenchi consentiti e degli elenchi bloccati (elenchi che determinano le organizzazioni esterne con cui gli utenti possono comunicare) non usano né un ambito né un'identità.</span><span class="sxs-lookup"><span data-stu-id="5d18c-103">The cmdlets used when modifying the allowed lists and blocked lists (lists that determine which outside organizations your users are allowed to communicate with) do not use either a scope or an Identity.</span></span> <span data-ttu-id="5d18c-104">Infatti, il cmdlet **New-CsEdgeAllowAllKnownDomains** non ha alcun tipo di parametro.</span><span class="sxs-lookup"><span data-stu-id="5d18c-104">In fact, the **New-CsEdgeAllowAllKnownDomains** cmdlet does not have any parameters whatsoever.</span></span> <span data-ttu-id="5d18c-105">I cmdlet che non usano né un ambito né un'identità sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="5d18c-105">The cmdlets that do not use either a scope or an Identity are:</span></span>

  - <span data-ttu-id="5d18c-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/en-us/library/jj994088\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5d18c-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/en-us/library/jj994088\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5d18c-107">[New-CsEdgeAllowList](https://technet.microsoft.com/en-us/library/jj994023\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5d18c-107">[New-CsEdgeAllowList](https://technet.microsoft.com/en-us/library/jj994023\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5d18c-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/en-us/library/jj994040\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5d18c-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/en-us/library/jj994040\(v=ocs.15\))</span></span>

<span data-ttu-id="5d18c-109">Tieni presente che, sia con il cmdlet **New-CsEdgeAllowList** che con il cmdlet **New-CsEdgeDomainPattern** , devi includere il parametro Domain.</span><span class="sxs-lookup"><span data-stu-id="5d18c-109">Note that, with both the **New-CsEdgeAllowList** cmdlet and the **New-CsEdgeDomainPattern** cmdlet, you must include the Domain parameter.</span></span> <span data-ttu-id="5d18c-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5d18c-110">For example:</span></span>

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a><span data-ttu-id="5d18c-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d18c-111">See Also</span></span>


[<span data-ttu-id="5d18c-112">Identità, ambiti e tenant in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="5d18c-112">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="5d18c-113">[Cmdlet di Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5d18c-113">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

