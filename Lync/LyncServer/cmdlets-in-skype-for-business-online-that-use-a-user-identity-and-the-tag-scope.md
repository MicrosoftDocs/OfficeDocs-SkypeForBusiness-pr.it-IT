---
title: Cmdlet in Skype for business online che utilizzano l'identità dell'utente e l'ambito dei tag
description: Cmdlet in Skype for business online che utilizzano l'identità dell'utente e l'ambito dei tag.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity and the tag scope
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56558838
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e2ddbcc9c90096cea5fad4cb680f4ea1797ce48
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545612"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a><span data-ttu-id="2755d-103">Cmdlet in Skype for business online che utilizzano l'identità dell'utente e l'ambito dei tag</span><span class="sxs-lookup"><span data-stu-id="2755d-103">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>

 


<span data-ttu-id="2755d-104">I cmdlet **Grant-CS** (utilizzati per l'assegnazione di criteri agli utenti) richiedono due identificatori: un'identità utente (il parametro Identity) e l'identità di un criterio per utente (il parametro PolicyName).</span><span class="sxs-lookup"><span data-stu-id="2755d-104">The **Grant-Cs** cmdlets (used for assigning policies to users) require two identifiers: a user identity (the Identity parameter) and the identity of a per-user policy (the PolicyName parameter).</span></span> <span data-ttu-id="2755d-105">Ad esempio, per assegnare il criterio vocale, RedmondVoicePolicy, all'utente Ken, è possibile utilizzare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="2755d-105">For example, to assign the voice policy, RedmondVoicePolicy, to the user Ken Myer, you use the following command:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="2755d-106">Quando si assegnano criteri agli utenti, è necessario tenere presente due aspetti.</span><span class="sxs-lookup"><span data-stu-id="2755d-106">There are two things to keep in mind when assigning policies to users.</span></span> <span data-ttu-id="2755d-107">Per prima cosa, è possibile assegnare solo i criteri per utente.</span><span class="sxs-lookup"><span data-stu-id="2755d-107">First, only per-user policies can be assigned.</span></span> <span data-ttu-id="2755d-108">Non è possibile assegnare il criterio globale a un utente.</span><span class="sxs-lookup"><span data-stu-id="2755d-108">You cannot assign the global policy to a user.</span></span> <span data-ttu-id="2755d-109">Ad esempio, questo comando avrà esito negativo:</span><span class="sxs-lookup"><span data-stu-id="2755d-109">For example, this command will fail:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

<span data-ttu-id="2755d-110">Questo comando ha esito negativo perché non è necessario assegnare il criterio globale.</span><span class="sxs-lookup"><span data-stu-id="2755d-110">This command fails because there is no need to assign the global policy.</span></span> <span data-ttu-id="2755d-111">Se si desidera gestire un utente utilizzando il criterio globale, è sufficiente assicurarsi di non assegnare un criterio per utente.</span><span class="sxs-lookup"><span data-stu-id="2755d-111">If you want to manage a user by using the global policy, just be sure that you do not assign that user a per-user policy.</span></span> <span data-ttu-id="2755d-112">Se a un utente non è stato assegnato alcun criterio per utente, l'utente verrà gestito automaticamente utilizzando il criterio globale.</span><span class="sxs-lookup"><span data-stu-id="2755d-112">If no per-user policy has been assigned to a user, the user will automatically be managed by using the global policy.</span></span>


> [!NOTE]  
> <span data-ttu-id="2755d-113">Che cosa succede se all'utente sono stati assegnati in precedenza un criterio per utente e si desidera annullare l'assegnazione di tale criterio e l'utente deve invece essere gestito dal criterio globale?</span><span class="sxs-lookup"><span data-stu-id="2755d-113">What if the user has previously been assigned a per-user policy, and you want to unassign that policy and have the user managed by the global policy instead?</span></span> <span data-ttu-id="2755d-114">In tal caso, si utilizzerà la seguente sintassi, che annulla l'assegnazione di un criterio per utente concedendo a un criterio null l'utente:</span><span class="sxs-lookup"><span data-stu-id="2755d-114">In that case, you’ll first use the following syntax, which unassigns a per-user policy by granting that user a null policy:</span></span><BR><span data-ttu-id="2755d-115">Grant-CsVoicePolicy – Identity "Ken remario" – PolicyName $Null</span><span class="sxs-lookup"><span data-stu-id="2755d-115">Grant-CsVoicePolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



<span data-ttu-id="2755d-116">In secondo luogo, tenere presente che i criteri per utente vengono creati nell'ambito dei tag.</span><span class="sxs-lookup"><span data-stu-id="2755d-116">Second, keep in mind that per-user policies are created at the tag scope.</span></span> <span data-ttu-id="2755d-117">Tuttavia, è possibile omettere il **prefisso** del tag quando si specifica il nome di un criterio.</span><span class="sxs-lookup"><span data-stu-id="2755d-117">However, you can omit the tag **prefix** when specifying a policy name.</span></span> <span data-ttu-id="2755d-118">Questi due comandi sono identici:</span><span class="sxs-lookup"><span data-stu-id="2755d-118">These two commands are identical:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="2755d-119">Se si desidera restituire le identità per tutti i criteri per utente (o almeno per tutti i criteri per utente di tipo specificato, ad esempio i criteri vocali), utilizzare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="2755d-119">If you would like to return the identities for all your per-user policies (or, at least, all the per-user policies of specified type, such as voice policies), use a command similar to this:</span></span>

    Get-CsVoicePolicy -Filter "tag:*"

<span data-ttu-id="2755d-120">I cmdlet seguenti utilizzano sia l'identità dell'utente che l'ambito dei tag:</span><span class="sxs-lookup"><span data-stu-id="2755d-120">The following cmdlets make use of both a user Identity and the tag scope:</span></span>

  - <span data-ttu-id="2755d-121">[Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="2755d-121">[Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="2755d-122">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="2755d-122">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))</span></span>

  - <span data-ttu-id="2755d-123">[Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="2755d-123">[Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))</span></span>

  - <span data-ttu-id="2755d-124">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="2755d-124">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="2755d-125">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="2755d-125">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))</span></span>

  - <span data-ttu-id="2755d-126">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="2755d-126">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="2755d-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2755d-127">See Also</span></span>


[<span data-ttu-id="2755d-128">Identità, ambiti e tenant in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="2755d-128">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="2755d-129">[Cmdlet di Skype for business online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="2755d-129">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

