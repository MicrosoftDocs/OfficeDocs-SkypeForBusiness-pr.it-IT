---
title: Cmdlet in Skype for business online che usano l'ambito globale e l'ambito dei tag
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 04eb5f71a0092452eb8b24fa9acf53d46fb3bcd5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728096"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a><span data-ttu-id="05960-102">Cmdlet in Skype for business online che usano l'ambito globale e l'ambito dei tag</span><span class="sxs-lookup"><span data-stu-id="05960-102">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>

 


<span data-ttu-id="05960-103">In Skype for business online i criteri possono essere configurati sia nell'ambito *globale* che nell'ambito del *tag* (o nell'ambito *per utente*).</span><span class="sxs-lookup"><span data-stu-id="05960-103">In Skype for Business Online, policies can be configured at either the *global scope* or at the *tag scope* (or *per-user scope*).</span></span> <span data-ttu-id="05960-104">Quando si usano i cmdlet **Get-CS** , non è necessario specificare un ambito o un'identità.</span><span class="sxs-lookup"><span data-stu-id="05960-104">When using the **Get-Cs** cmdlets, you do not have to specify a scope or identity.</span></span> <span data-ttu-id="05960-105">Se si chiama uno di questi cmdlet senza parametri, verranno restituiti tutti gli elementi rilevanti.</span><span class="sxs-lookup"><span data-stu-id="05960-105">If you call one of these cmdlets without any parameters, then all the relevant items will be returned.</span></span> <span data-ttu-id="05960-106">Ad esempio, questo comando restituisce informazioni su tutti i criteri di accesso esterno:</span><span class="sxs-lookup"><span data-stu-id="05960-106">For example, this command returns information about all your external access policies:</span></span>

    Get-CsExternalAccessPolicy

<span data-ttu-id="05960-107">Se si vogliono limitare i dati restituiti, è necessario includere solo il parametro Identity o il parametro Filter.</span><span class="sxs-lookup"><span data-stu-id="05960-107">You need to include only the Identity parameter or the Filter parameter if you want to limit the returned data.</span></span> <span data-ttu-id="05960-108">Ad esempio, per restituire solo il criterio globale, usare questo comando:</span><span class="sxs-lookup"><span data-stu-id="05960-108">For example, to return only the global policy, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="05960-109">Per restituire un criterio per utente con l'identità "RedmondAccessPolicy", usare questo comando:</span><span class="sxs-lookup"><span data-stu-id="05960-109">To return a per-user policy that has the Identity “RedmondAccessPolicy”, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> <span data-ttu-id="05960-110">Quando si fa riferimento a un criterio per utente, il <STRONG>prefisso</STRONG> di tag è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="05960-110">When referencing a per-user policy, the tag <STRONG>prefix</STRONG> is optional.</span></span> <span data-ttu-id="05960-111">Questa sintassi, che include il prefisso, è valida anche:</span><span class="sxs-lookup"><span data-stu-id="05960-111">This syntax, which includes the prefix, is also valid:</span></span><BR><span data-ttu-id="05960-112">Get-CsExternalAccessPolicy – Identity "Tag: RedmondAccessPolicy"</span><span class="sxs-lookup"><span data-stu-id="05960-112">Get-CsExternalAccessPolicy –Identity "tag:RedmondAccessPolicy"</span></span>



<span data-ttu-id="05960-113">Per restituire tutti i criteri eccetto i criteri globali, ovvero tutti i criteri per utente, usare questo comando:</span><span class="sxs-lookup"><span data-stu-id="05960-113">To return all policies except the global policies (that is, all the per-user policies), use this command:</span></span>

    Get-CsExternalAccessPolicy -Filter "tag:*"

<span data-ttu-id="05960-114">I cmdlet seguenti funzionano sia per l'ambito globale che per l'ambito per utente (tag):</span><span class="sxs-lookup"><span data-stu-id="05960-114">The following cmdlets operate against both the global scope and the per-user (tag) scope:</span></span>

  - <span data-ttu-id="05960-115">[Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="05960-115">[Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))</span></span>

  - <span data-ttu-id="05960-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="05960-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))</span></span>

  - <span data-ttu-id="05960-117">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="05960-117">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))</span></span>

  - <span data-ttu-id="05960-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="05960-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))</span></span>

  - <span data-ttu-id="05960-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="05960-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))</span></span>

  - <span data-ttu-id="05960-120">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="05960-120">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))</span></span>

  - <span data-ttu-id="05960-121">[Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="05960-121">[Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))</span></span>


> [!NOTE]  
> <span data-ttu-id="05960-122">Nonostante il nome, i dial plan sono, in termini funzionali, i criteri.</span><span class="sxs-lookup"><span data-stu-id="05960-122">Despite the name, dial plans are, functionally speaking, policies.</span></span> <span data-ttu-id="05960-123">Viene usato il <EM>dial plan</EM> di termine anziché, ad esempio, i criteri di chiamata, per preservare la terminologia usata con le versioni precedenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="05960-123">The term <EM>dial plan</EM> is used instead of, for example, dialing policy, in order to preserve the terminology used with previous versions of Lync Server.</span></span>



## <a name="see-also"></a><span data-ttu-id="05960-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05960-124">See Also</span></span>


[<span data-ttu-id="05960-125">Identità, ambiti e tenant in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="05960-125">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="05960-126">[Cmdlet di Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="05960-126">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

