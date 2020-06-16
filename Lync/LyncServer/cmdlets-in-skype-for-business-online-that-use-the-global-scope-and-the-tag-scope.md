---
title: Cmdlet in Skype for business online che utilizzano l'ambito globale e l'ambito dei tag
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8063334f2cea6fcca768754197bacbd30869461
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755076"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a><span data-ttu-id="92235-102">Cmdlet in Skype for business online che utilizzano l'ambito globale e l'ambito dei tag</span><span class="sxs-lookup"><span data-stu-id="92235-102">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>

 


<span data-ttu-id="92235-103">In Skype for business online, i criteri possono essere configurati nell'ambito *globale* o nell'ambito dei *tag* (o nell'ambito *per utente*).</span><span class="sxs-lookup"><span data-stu-id="92235-103">In Skype for Business Online, policies can be configured at either the *global scope* or at the *tag scope* (or *per-user scope*).</span></span> <span data-ttu-id="92235-104">Quando si utilizzano i cmdlet **Get-CS** , non è necessario specificare un ambito o un'identità.</span><span class="sxs-lookup"><span data-stu-id="92235-104">When using the **Get-Cs** cmdlets, you do not have to specify a scope or identity.</span></span> <span data-ttu-id="92235-105">Se si chiama uno di questi cmdlet senza alcun parametro, verranno restituiti tutti gli elementi rilevanti.</span><span class="sxs-lookup"><span data-stu-id="92235-105">If you call one of these cmdlets without any parameters, then all the relevant items will be returned.</span></span> <span data-ttu-id="92235-106">Ad esempio, questo comando restituisce informazioni su tutti i criteri di accesso esterno:</span><span class="sxs-lookup"><span data-stu-id="92235-106">For example, this command returns information about all your external access policies:</span></span>

    Get-CsExternalAccessPolicy

<span data-ttu-id="92235-107">Se si desidera limitare i dati restituiti, è necessario includere solo il parametro Identity o il parametro Filter.</span><span class="sxs-lookup"><span data-stu-id="92235-107">You need to include only the Identity parameter or the Filter parameter if you want to limit the returned data.</span></span> <span data-ttu-id="92235-108">Ad esempio, per restituire solo il criterio globale, utilizzare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="92235-108">For example, to return only the global policy, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="92235-109">Per restituire un criterio per utente con identità "RedmondAccessPolicy", utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="92235-109">To return a per-user policy that has the Identity “RedmondAccessPolicy”, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> <span data-ttu-id="92235-110">Quando si fa riferimento a un criterio per utente, il <STRONG>prefisso</STRONG> di tag è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="92235-110">When referencing a per-user policy, the tag <STRONG>prefix</STRONG> is optional.</span></span> <span data-ttu-id="92235-111">Questa sintassi, che include il prefisso, è valida anche:</span><span class="sxs-lookup"><span data-stu-id="92235-111">This syntax, which includes the prefix, is also valid:</span></span><BR><span data-ttu-id="92235-112">Get-CsExternalAccessPolicy – Identity "Tag: RedmondAccessPolicy"</span><span class="sxs-lookup"><span data-stu-id="92235-112">Get-CsExternalAccessPolicy –Identity "tag:RedmondAccessPolicy"</span></span>



<span data-ttu-id="92235-113">Per restituire tutti i criteri, ad eccezione dei criteri globali, ovvero tutti i criteri per utente, utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="92235-113">To return all policies except the global policies (that is, all the per-user policies), use this command:</span></span>

    Get-CsExternalAccessPolicy -Filter "tag:*"

<span data-ttu-id="92235-114">I cmdlet seguenti agiscono sull'ambito globale e sull'ambito per utente (tag):</span><span class="sxs-lookup"><span data-stu-id="92235-114">The following cmdlets operate against both the global scope and the per-user (tag) scope:</span></span>

  - <span data-ttu-id="92235-115">[Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="92235-115">[Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))</span></span>

  - <span data-ttu-id="92235-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="92235-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))</span></span>

  - <span data-ttu-id="92235-117">[Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="92235-117">[Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))</span></span>

  - <span data-ttu-id="92235-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="92235-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))</span></span>

  - <span data-ttu-id="92235-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="92235-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))</span></span>

  - <span data-ttu-id="92235-120">[Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="92235-120">[Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))</span></span>

  - <span data-ttu-id="92235-121">[Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="92235-121">[Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))</span></span>


> [!NOTE]  
> <span data-ttu-id="92235-122">Nonostante il nome, i dial plan sono, funzionalmente, i criteri.</span><span class="sxs-lookup"><span data-stu-id="92235-122">Despite the name, dial plans are, functionally speaking, policies.</span></span> <span data-ttu-id="92235-123">Viene utilizzato il <EM>dial plan</EM> di termini anziché, ad esempio, i criteri di composizione per mantenere la terminologia utilizzata con le versioni precedenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="92235-123">The term <EM>dial plan</EM> is used instead of, for example, dialing policy, in order to preserve the terminology used with previous versions of Lync Server.</span></span>



## <a name="see-also"></a><span data-ttu-id="92235-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92235-124">See Also</span></span>


[<span data-ttu-id="92235-125">Identità, ambiti e tenant in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="92235-125">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="92235-126">[Cmdlet di Skype for business online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="92235-126">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

