---
title: Identità, ambiti e tenant in Skype for business online
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3e5217c4214e6e86ca4c1dff62410c247cf7f8c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a><span data-ttu-id="30350-102">Identità, ambiti e tenant in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="30350-102">Identities, scopes, and tenants in Skype for Business Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30350-103">_**Ultimo argomento modificato:** 2015-03-09_</span><span class="sxs-lookup"><span data-stu-id="30350-103">_**Topic Last Modified:** 2015-03-09_</span></span>

<span data-ttu-id="30350-104">Molti dei cmdlet di Windows PowerShell utilizzati per gestire Skype for business online richiedono di essere molto specifici sull'elemento che si sta tentando di gestire.</span><span class="sxs-lookup"><span data-stu-id="30350-104">Many of the Windows PowerShell cmdlets used to manage Skype for Business Online require you to be very specific about the item that you are trying to manage.</span></span> <span data-ttu-id="30350-105">Ad esempio, quando si esegue il cmdlet [Set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) , è necessario indicare l'utente che si sta tentando di gestire.</span><span class="sxs-lookup"><span data-stu-id="30350-105">For example, when you run the [Set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) cmdlet, you must indicate which user you are trying to manage.</span></span> <span data-ttu-id="30350-106">Questo ha senso.</span><span class="sxs-lookup"><span data-stu-id="30350-106">This makes sense.</span></span> <span data-ttu-id="30350-107">A meno che non si dica specificatamente al cmdlet per la gestione dell'account utente, il cmdlet **Set-CsUserAcp** non ha alcuna idea di quali informazioni sull'audioconferenza dell'utente devono essere modificate.</span><span class="sxs-lookup"><span data-stu-id="30350-107">Unless you specifically tell the cmdlet which user account to manage, the **Set-CsUserAcp** cmdlet has no idea which user’s audio conferencing information should be modified.</span></span> <span data-ttu-id="30350-108">Per questo motivo, ogni volta che si esegue il cmdlet **Set-CsUserAcp** , è necessario includere il parametro Identity, seguito dall'identità dell'account utente da modificare:</span><span class="sxs-lookup"><span data-stu-id="30350-108">For this reason, each time you run the **Set-CsUserAcp** cmdlet, you’ll need to include the Identity parameter, followed by the Identity of the user account to be modified:</span></span>

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

<span data-ttu-id="30350-109">Se l' *identità* del termine si riferisce sempre all'identità di un account utente, non vi sarebbe alcuna causa di confusione.</span><span class="sxs-lookup"><span data-stu-id="30350-109">If the term *Identity* always referred to the Identity of a user account, there would be little cause for confusion.</span></span> <span data-ttu-id="30350-110">Quando si ha a che fare con persone (utenti, contatti e così via), le identità si riferiscono ai singoli utenti stessi.</span><span class="sxs-lookup"><span data-stu-id="30350-110">When you are dealing with people (users, contacts, and so on), Identities refer to the individual users themselves.</span></span> <span data-ttu-id="30350-111">Tuttavia, gli elementi diversi dagli account utente dispongono anche di identità.</span><span class="sxs-lookup"><span data-stu-id="30350-111">However, items other than user accounts also have Identities.</span></span> <span data-ttu-id="30350-112">Quando si ha a che fare con i componenti del servizio Skype for business online, criteri, impostazioni di configurazione e così via, l'identità del termine significa qualcosa di leggermente diverso.</span><span class="sxs-lookup"><span data-stu-id="30350-112">When you are dealing with components of the Skype for Business Online service—policies, configuration settings, and so on—the term Identity means something slightly different.</span></span> <span data-ttu-id="30350-113">Si consideri, ad esempio, il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="30350-113">For example, consider this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="30350-114">In questo caso, l'identità "globale" si riferisce all'ambito delle impostazioni di configurazione delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="30350-114">In this case, the Identity "global" refers to the scope of the meeting configuration settings.</span></span> <span data-ttu-id="30350-115">*Scope* è un termine utilizzato in Skype for business online (e in Lync Server) per designare gli ambiti di gestione.</span><span class="sxs-lookup"><span data-stu-id="30350-115">*Scope* is a term used in Skype for Business Online (and in Lync Server) to designate spheres of management.</span></span> <span data-ttu-id="30350-116">Per impostazione predefinita, i criteri e le impostazioni hanno sempre un ambito globale.</span><span class="sxs-lookup"><span data-stu-id="30350-116">By default, policies and settings always have a global scope.</span></span> <span data-ttu-id="30350-117">Quando si configura per la prima volta l'account Skype for business online, per impostazione predefinita, è disponibile un insieme di criteri e impostazioni globali, ovvero le impostazioni di configurazione della riunione globale, un criterio di accesso esterno globale, un dial plan globale e così via.</span><span class="sxs-lookup"><span data-stu-id="30350-117">When you first set up your Skype for Business Online account you'll have, by default, a collection of global policies and settings—global meeting configuration settings, a global external access policy, a global dial plan, and so on.</span></span>

<span data-ttu-id="30350-118">I criteri e le impostazioni globali sono stati introdotti in Microsoft Lync Server 2010 per garantire che tutti gli utenti e tutti i componenti vengano gestiti in modo sempre.</span><span class="sxs-lookup"><span data-stu-id="30350-118">These global policies and settings were introduced in Microsoft Lync Server 2010 to help ensure that all users and all components would always, in some way, be managed.</span></span> <span data-ttu-id="30350-119">Questo non è necessariamente vero in Microsoft Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="30350-119">This was not necessarily true in Microsoft Office Communicator 2007 R2.</span></span> <span data-ttu-id="30350-120">A seconda del modo in cui è stato eseguito l'accesso al sistema, è possibile che si possa finire in uno stato ampiamente non gestito (in genere, perché non è stato possibile applicare criteri di gruppo all'account utente).</span><span class="sxs-lookup"><span data-stu-id="30350-120">Depending on how you accessed the system, you could potentially end up in a largely unmanaged state (typically, because Group Policy could not be applied to your user account).</span></span> <span data-ttu-id="30350-121">Al contrario, in Lync Server e in Skype for business online, non è mai rimasto nulla gestito.</span><span class="sxs-lookup"><span data-stu-id="30350-121">In contrast, in Lync Server and in Skype for Business Online, nothing is ever left unmanaged.</span></span> <span data-ttu-id="30350-122">Ciò è dovuto al fatto che, in sostituzione di qualsiasi altra operazione, verranno sempre applicati i criteri globali e le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="30350-122">This is because, in lieu of anything else, global policies and settings will always be enforced.</span></span>

<span data-ttu-id="30350-123">Cosa si intende per "invece di qualcos'altro"?</span><span class="sxs-lookup"><span data-stu-id="30350-123">What do we mean by "in lieu of anything else"?</span></span> <span data-ttu-id="30350-124">Ebbene, nel caso di Skype for business online, è possibile creare criteri nell' *ambito del tag*o nella sfera di gestione.</span><span class="sxs-lookup"><span data-stu-id="30350-124">Well, in the case of Skype for Business Online, it’s possible to create policies at the *tag scope*, or sphere of management.</span></span> <span data-ttu-id="30350-125">I criteri creati nell'ambito dei tag (noti anche come *ambito per utente*) hanno la priorità rispetto ai criteri creati nell'ambito globale.</span><span class="sxs-lookup"><span data-stu-id="30350-125">Policies created at the tag scope (also known as *the per-user scope*) take priority over policies created at the global scope.</span></span> <span data-ttu-id="30350-126">In altre parole, un criterio per utente avrà sempre la precedenza su un criterio globale.</span><span class="sxs-lookup"><span data-stu-id="30350-126">In other words, a per-user policy will always take precedence over a global policy.</span></span> <span data-ttu-id="30350-127">Ad esempio, potrebbe essere necessario disporre di due criteri di accesso utente esterno.</span><span class="sxs-lookup"><span data-stu-id="30350-127">For example, you might have two external user access policies.</span></span> <span data-ttu-id="30350-128">I criteri globali impediscono agli utenti di comunicare con persone che dispongono di account su provider di messaggistica istantanea pubblica, ad esempio Windows Live.</span><span class="sxs-lookup"><span data-stu-id="30350-128">The global policy prohibits users from communicating with people who have accounts on public instant messaging (IM) providers, such as Windows Live.</span></span> <span data-ttu-id="30350-129">Il criterio per utente, AllowPublicIMCommunication, consente la comunicazione con i provider di messaggistica istantanea pubblici.</span><span class="sxs-lookup"><span data-stu-id="30350-129">The per-user policy, AllowPublicIMCommunication, allows communication with public IM providers.</span></span>

<span data-ttu-id="30350-130">Potrebbe essere necessario anche due utenti: Ken e Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="30350-130">You might also have two users: Ken Myer and Pilar Ackerman.</span></span> <span data-ttu-id="30350-131">A Ken è stato assegnato il criterio per utente.</span><span class="sxs-lookup"><span data-stu-id="30350-131">Ken Myer has been assigned the per-user policy.</span></span> <span data-ttu-id="30350-132">A Pilar Ackerman non è stato assegnato un criterio per utente. in altre altre, è gestita dal criterio di accesso esterno globale.</span><span class="sxs-lookup"><span data-stu-id="30350-132">Pilar Ackerman has not been assigned a per-user policy; that is, she is managed by the global external access policy.</span></span> <span data-ttu-id="30350-133">Nella tabella seguente viene illustrato l'eventuale utente che può comunicare con i provider di messaggistica istantanea pubblici:</span><span class="sxs-lookup"><span data-stu-id="30350-133">The following table shows which user (if any) can communicate with public IM providers:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30350-134">Impostazioni di criteri</span><span class="sxs-lookup"><span data-stu-id="30350-134">Policy Settings</span></span></th>
<th><span data-ttu-id="30350-135">Davide Garghentini</span><span class="sxs-lookup"><span data-stu-id="30350-135">Ken Myer</span></span></th>
<th><span data-ttu-id="30350-136">Daniela Cazzaniga</span><span class="sxs-lookup"><span data-stu-id="30350-136">Pilar Ackerman</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30350-137">Impostazione dei criteri globali per i provider di messaggistica istantanea pubblici</span><span class="sxs-lookup"><span data-stu-id="30350-137">Global policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="30350-138">No</span><span class="sxs-lookup"><span data-stu-id="30350-138">No</span></span></p></td>
<td><p><span data-ttu-id="30350-139">No</span><span class="sxs-lookup"><span data-stu-id="30350-139">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30350-140">Impostazione dei criteri per utente per i provider di messaggistica istantanea pubblici</span><span class="sxs-lookup"><span data-stu-id="30350-140">Per-user policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="30350-141">Sì</span><span class="sxs-lookup"><span data-stu-id="30350-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="30350-142">No</span><span class="sxs-lookup"><span data-stu-id="30350-142">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30350-143">L'utente può comunicare con i provider di messaggistica istantanea pubblici</span><span class="sxs-lookup"><span data-stu-id="30350-143">User can communicate with public IM providers</span></span></p></td>
<td><p><span data-ttu-id="30350-144">Sì</span><span class="sxs-lookup"><span data-stu-id="30350-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="30350-145">No</span><span class="sxs-lookup"><span data-stu-id="30350-145">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="30350-146">Come si può notare, Ken è autorizzato a comunicare con i provider di messaggistica istantanea pubblici.</span><span class="sxs-lookup"><span data-stu-id="30350-146">As you can see, Ken Myer is allowed to communicate with public IM providers.</span></span> <span data-ttu-id="30350-147">Ciò è dovuto al fatto che le impostazioni del criterio per utente assegnatogli eseguono l'override delle impostazioni del criterio globale.</span><span class="sxs-lookup"><span data-stu-id="30350-147">This is because the settings in the per-user policy assigned to him override the settings in the global policy.</span></span> <span data-ttu-id="30350-148">Pilar Ackerman non è in grado di comunicare con i provider di messaggistica istantanea pubblici.</span><span class="sxs-lookup"><span data-stu-id="30350-148">Pilar Ackerman cannot communicate with public IM providers.</span></span> <span data-ttu-id="30350-149">Ciò è dovuto al fatto che è gestita dal criterio globale e che il criterio globale proibisce tali comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="30350-149">This is because she is managed by the global policy, and the global policy prohibits such communications.</span></span>

<span data-ttu-id="30350-150">I criteri per utente devono essere creati dal supporto tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="30350-150">Per-user policies must be created for you by Microsoft Support.</span></span> <span data-ttu-id="30350-151">Dopo aver creato i criteri, è possibile assegnarli agli utenti utilizzando il cmdlet **Grant-CS** appropriato (ad esempio, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)).</span><span class="sxs-lookup"><span data-stu-id="30350-151">After the policies are created, you can then assign them to users by using the appropriate **Grant-Cs** cmdlet (for example, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)).</span></span> <span data-ttu-id="30350-152">I criteri per utente sono facili da identificare perché l'identità dei criteri inizia sempre con il **prefisso**del tag.</span><span class="sxs-lookup"><span data-stu-id="30350-152">Per-user policies are easy to identify because the policy Identity always begins with the tag **prefix**.</span></span> <span data-ttu-id="30350-153">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="30350-153">For example:</span></span>

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> <span data-ttu-id="30350-154">Il <STRONG>prefisso</STRONG> di tag risale ai giorni di sviluppo precedenti di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="30350-154">The tag <STRONG>prefix</STRONG> dates back to the early development days of Lync Server 2010.</span></span> <span data-ttu-id="30350-155">In quei giorni, i criteri per utente sono stati denominati <EM>criteri di tag</EM> e sono stati identificati dal <STRONG>prefisso</STRONG>del tag.</span><span class="sxs-lookup"><span data-stu-id="30350-155">In those days, per-user policies were referred to as <EM>tag policies</EM> and were identified by the tag <STRONG>prefix</STRONG>.</span></span> <span data-ttu-id="30350-156">Questi criteri sono ora denominati in modo più accurato come <EM>criteri per utente</EM>e l'ambito dei tag viene definito in modo più accurato come <EM>ambito per utente</EM>.</span><span class="sxs-lookup"><span data-stu-id="30350-156">These policies are now more accurately referred to as <EM>per-user policies</EM>, and the tag scope is more accurately referred to as the <EM>per-user scope</EM>.</span></span> <span data-ttu-id="30350-157">Tuttavia, per motivi tecnici, il <STRONG>prefisso</STRONG> del tag non è mai stato modificato.</span><span class="sxs-lookup"><span data-stu-id="30350-157">However, for technical reasons, the tag <STRONG>prefix</STRONG> was never changed.</span></span>



</div>

<span data-ttu-id="30350-158">Un altro termine chiave utilizzato quando si lavora con Skype for business online e Windows PowerShell è *tenant*.</span><span class="sxs-lookup"><span data-stu-id="30350-158">Another key term used when working with Skype for Business Online and Windows PowerShell is *tenant*.</span></span> <span data-ttu-id="30350-159">Quando si configura un account Skype for business online, alla nuova distribuzione viene assegnato un numero di ID tenant, che è un identificatore univoco globale (GUID) simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="30350-159">When you set up a Skype for Business Online account, your new deployment is assigned a tenant ID number, which is a globally unique identifier (GUID) similar to this:</span></span>

    bf19b7db-6960-41e5-a139-2aa373474354

<span data-ttu-id="30350-160">Alcuni dei cmdlet di Skype for business online richiedono di immettere l'ID tenant ogni volta che si esegue il cmdlet.</span><span class="sxs-lookup"><span data-stu-id="30350-160">A few of the Skype for Business Online cmdlets require you to enter the tenant ID whenever you run the cmdlet.</span></span> <span data-ttu-id="30350-161">È necessario immettere l'ID tenant anche se l'utente ha effettuato l'accesso e dispone di un solo tenant.</span><span class="sxs-lookup"><span data-stu-id="30350-161">You must enter the tenant ID even if you have logged on to, and only have, one tenant.</span></span> <span data-ttu-id="30350-162">Fortunatamente, non è necessario memorizzare l'ID tenant.</span><span class="sxs-lookup"><span data-stu-id="30350-162">Fortunately, you do not have to memorize the tenant ID.</span></span> <span data-ttu-id="30350-163">È possibile recuperare l'ID tenant in qualsiasi momento eseguendo il comando di Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="30350-163">You can retrieve your tenant ID at any time by running the following Windows PowerShell command:</span></span>

    Get-CsTenant | Select-Object TenantId

<span data-ttu-id="30350-164">Naturalmente, conoscere elementi quali la differenza tra l'ambito globale e l'ambito per utente (o l'ambito dei tag) è solo la metà della battaglia.</span><span class="sxs-lookup"><span data-stu-id="30350-164">Of course, knowing things such as the difference between the global scope and the per-user scope (or the tag scope) is only half the battle.</span></span> <span data-ttu-id="30350-165">È inoltre importante sapere quando (o anche se) è possibile utilizzare questi ambiti.</span><span class="sxs-lookup"><span data-stu-id="30350-165">It’s also important to know when (or even if) you can use these scopes.</span></span> <span data-ttu-id="30350-166">Lo stesso vale per le identità e per il parametro tenant.</span><span class="sxs-lookup"><span data-stu-id="30350-166">The same is true for Identities and the tenant parameter.</span></span> <span data-ttu-id="30350-167">Negli argomenti seguenti viene descritto il modo in cui i diversi cmdlet Skype for business online utilizzano identità, ambiti e il parametro tenant:</span><span class="sxs-lookup"><span data-stu-id="30350-167">The following topics describe how the different Skype for Business Online cmdlets use Identities, scopes, and the tenant parameter:</span></span>

  - [<span data-ttu-id="30350-168">Cmdlet in Skype for business online che utilizzano solo l'ambito globale</span><span class="sxs-lookup"><span data-stu-id="30350-168">Cmdlets in Skype for Business Online that use only the global scope</span></span>](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [<span data-ttu-id="30350-169">Cmdlet in Skype for business online che utilizzano l'ambito globale e l'ambito dei tag</span><span class="sxs-lookup"><span data-stu-id="30350-169">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [<span data-ttu-id="30350-170">Cmdlet in Skype for business online che utilizzano un'identità utente</span><span class="sxs-lookup"><span data-stu-id="30350-170">Cmdlets in Skype for Business Online that use a user identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [<span data-ttu-id="30350-171">Cmdlet in Skype for business online che utilizzano l'identità dell'utente e l'ambito dei tag</span><span class="sxs-lookup"><span data-stu-id="30350-171">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [<span data-ttu-id="30350-172">Cmdlet in Skype for business online che utilizzano il parametro tenant</span><span class="sxs-lookup"><span data-stu-id="30350-172">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [<span data-ttu-id="30350-173">Cmdlet in Skype for business online che utilizzano un'identità del provider di servizi di conferenza</span><span class="sxs-lookup"><span data-stu-id="30350-173">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [<span data-ttu-id="30350-174">Cmdlet in Skype for business online che non utilizzano un ambito o un'identità</span><span class="sxs-lookup"><span data-stu-id="30350-174">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

