---
title: Cmdlet in Skype for business online che non utilizzano un ambito o un'identità
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad366315bbc4acf5afb417262da92a5683a084df
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001731"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a><span data-ttu-id="82d4b-102">Cmdlet in Skype for business online che non utilizzano un ambito o un'identità</span><span class="sxs-lookup"><span data-stu-id="82d4b-102">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>

 


<span data-ttu-id="82d4b-103">I cmdlet utilizzati per la modifica degli elenchi consentiti e degli elenchi bloccati (elenchi che determinano le organizzazioni esterne a cui gli utenti sono autorizzati a comunicare) non utilizzano un ambito o un'identità.</span><span class="sxs-lookup"><span data-stu-id="82d4b-103">The cmdlets used when modifying the allowed lists and blocked lists (lists that determine which outside organizations your users are allowed to communicate with) do not use either a scope or an Identity.</span></span> <span data-ttu-id="82d4b-104">Infatti, il cmdlet **New-CsEdgeAllowAllKnownDomains** non dispone di alcun parametro.</span><span class="sxs-lookup"><span data-stu-id="82d4b-104">In fact, the **New-CsEdgeAllowAllKnownDomains** cmdlet does not have any parameters whatsoever.</span></span> <span data-ttu-id="82d4b-105">I cmdlet che non utilizzano un ambito o un'identità sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="82d4b-105">The cmdlets that do not use either a scope or an Identity are:</span></span>

  - <span data-ttu-id="82d4b-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/library/jj994088\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="82d4b-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/library/jj994088\(v=ocs.15\))</span></span>

  - <span data-ttu-id="82d4b-107">[New-CsEdgeAllowList](https://technet.microsoft.com/library/jj994023\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="82d4b-107">[New-CsEdgeAllowList](https://technet.microsoft.com/library/jj994023\(v=ocs.15\))</span></span>

  - <span data-ttu-id="82d4b-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/library/jj994040\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="82d4b-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/library/jj994040\(v=ocs.15\))</span></span>

<span data-ttu-id="82d4b-109">Si noti che, con il cmdlet **New-CsEdgeAllowList** e il cmdlet **New-CsEdgeDomainPattern** , è necessario includere il parametro Domain.</span><span class="sxs-lookup"><span data-stu-id="82d4b-109">Note that, with both the **New-CsEdgeAllowList** cmdlet and the **New-CsEdgeDomainPattern** cmdlet, you must include the Domain parameter.</span></span> <span data-ttu-id="82d4b-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="82d4b-110">For example:</span></span>

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a><span data-ttu-id="82d4b-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82d4b-111">See Also</span></span>


[<span data-ttu-id="82d4b-112">Identità, ambiti e tenant in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="82d4b-112">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="82d4b-113">[Cmdlet di Skype for business online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="82d4b-113">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

