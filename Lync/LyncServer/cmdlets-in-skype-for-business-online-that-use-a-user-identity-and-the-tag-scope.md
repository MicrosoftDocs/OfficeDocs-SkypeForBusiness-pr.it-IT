---
title: Cmdlet in Skype for business online che usano l'identità dell'utente e l'ambito dei tag
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 24c197934705a86d91e0492949aa2a9e6484f903
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727566"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a><span data-ttu-id="4a3ee-102">Cmdlet in Skype for business online che usano l'identità dell'utente e l'ambito dei tag</span><span class="sxs-lookup"><span data-stu-id="4a3ee-102">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>

 


<span data-ttu-id="4a3ee-103">I cmdlet **Grant-CS** (usati per l'assegnazione di criteri agli utenti) richiedono due identificatori: un'identità utente (il parametro Identity) e l'identità di un criterio per utente (il parametro PolicyName).</span><span class="sxs-lookup"><span data-stu-id="4a3ee-103">The **Grant-Cs** cmdlets (used for assigning policies to users) require two identifiers: a user identity (the Identity parameter) and the identity of a per-user policy (the PolicyName parameter).</span></span> <span data-ttu-id="4a3ee-104">Ad esempio, per assegnare il criterio vocale, RedmondVoicePolicy, all'utente Ken per l'uso, è possibile usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4a3ee-104">For example, to assign the voice policy, RedmondVoicePolicy, to the user Ken Myer, you use the following command:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="4a3ee-105">Quando si assegnano criteri agli utenti, è necessario tenere presente due aspetti.</span><span class="sxs-lookup"><span data-stu-id="4a3ee-105">There are two things to keep in mind when assigning policies to users.</span></span> <span data-ttu-id="4a3ee-106">In primo luogo, possono essere assegnati solo i criteri per utente.</span><span class="sxs-lookup"><span data-stu-id="4a3ee-106">First, only per-user policies can be assigned.</span></span> <span data-ttu-id="4a3ee-107">Non è possibile assegnare il criterio globale a un utente.</span><span class="sxs-lookup"><span data-stu-id="4a3ee-107">You cannot assign the global policy to a user.</span></span> <span data-ttu-id="4a3ee-108">Ad esempio, questo comando avrà esito negativo:</span><span class="sxs-lookup"><span data-stu-id="4a3ee-108">For example, this command will fail:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

<span data-ttu-id="4a3ee-109">Questo comando non riesce perché non è necessario assegnare il criterio globale.</span><span class="sxs-lookup"><span data-stu-id="4a3ee-109">This command fails because there is no need to assign the global policy.</span></span> <span data-ttu-id="4a3ee-110">Se si vuole gestire un utente usando il criterio globale, assicurarsi che l'utente non assegni un criterio per utente.</span><span class="sxs-lookup"><span data-stu-id="4a3ee-110">If you want to manage a user by using the global policy, just be sure that you do not assign that user a per-user policy.</span></span> <span data-ttu-id="4a3ee-111">Se non è stato assegnato alcun criterio per utente a un utente, l'utente verrà gestito automaticamente tramite il criterio globale.</span><span class="sxs-lookup"><span data-stu-id="4a3ee-111">If no per-user policy has been assigned to a user, the user will automatically be managed by using the global policy.</span></span>


> [!NOTE]  
> <span data-ttu-id="4a3ee-112">Che cosa succede se all'utente è stato assegnato in precedenza un criterio per utente e si vuole annullare l'assegnazione dei criteri e avere l'utente gestito dal criterio globale?</span><span class="sxs-lookup"><span data-stu-id="4a3ee-112">What if the user has previously been assigned a per-user policy, and you want to unassign that policy and have the user managed by the global policy instead?</span></span> <span data-ttu-id="4a3ee-113">In questo caso, utilizzerai prima di tutto la sintassi seguente, che annulla l'assegnazione di un criterio per utente concedendo un criterio null per l'utente:</span><span class="sxs-lookup"><span data-stu-id="4a3ee-113">In that case, you’ll first use the following syntax, which unassigns a per-user policy by granting that user a null policy:</span></span><BR><span data-ttu-id="4a3ee-114">Grant-CsVoicePolicy-Identity "Ken"-PolicyName $Null</span><span class="sxs-lookup"><span data-stu-id="4a3ee-114">Grant-CsVoicePolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



<span data-ttu-id="4a3ee-115">In secondo luogo, tieni presente che i criteri per utente vengono creati nell'ambito del tag.</span><span class="sxs-lookup"><span data-stu-id="4a3ee-115">Second, keep in mind that per-user policies are created at the tag scope.</span></span> <span data-ttu-id="4a3ee-116">Tuttavia, è possibile omettere il **prefisso** del contrassegno quando si specifica un nome di criterio.</span><span class="sxs-lookup"><span data-stu-id="4a3ee-116">However, you can omit the tag **prefix** when specifying a policy name.</span></span> <span data-ttu-id="4a3ee-117">Questi due comandi sono identici:</span><span class="sxs-lookup"><span data-stu-id="4a3ee-117">These two commands are identical:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="4a3ee-118">Se si vuole restituire le identità per tutti i criteri per utente (o almeno per tutti i criteri per utente di tipo specificato, ad esempio i criteri vocali), usare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="4a3ee-118">If you would like to return the identities for all your per-user policies (or, at least, all the per-user policies of specified type, such as voice policies), use a command similar to this:</span></span>

    Get-CsVoicePolicy -Filter "tag:*"

<span data-ttu-id="4a3ee-119">I cmdlet seguenti sfruttano sia l'identità dell'utente che l'ambito dei tag:</span><span class="sxs-lookup"><span data-stu-id="4a3ee-119">The following cmdlets make use of both a user Identity and the tag scope:</span></span>

  - <span data-ttu-id="4a3ee-120">[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg412942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="4a3ee-120">[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg412942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="4a3ee-121">[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="4a3ee-121">[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\))</span></span>

  - <span data-ttu-id="4a3ee-122">[Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="4a3ee-122">[Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\))</span></span>

  - <span data-ttu-id="4a3ee-123">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="4a3ee-123">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="4a3ee-124">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg412829\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="4a3ee-124">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg412829\(v=ocs.15\))</span></span>

  - <span data-ttu-id="4a3ee-125">[Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="4a3ee-125">[Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="4a3ee-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a3ee-126">See Also</span></span>


[<span data-ttu-id="4a3ee-127">Identità, ambiti e tenant in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="4a3ee-127">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="4a3ee-128">[Cmdlet di Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="4a3ee-128">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

