---
title: "Lync Server 2013: Configurare criteri per controllare l'accesso utente federato"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control federated user access
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1aeb1b29637fd3f4a8add770470069e8b4a6eb8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="c28f3-102">Configurare criteri per controllare l'accesso utente federato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c28f3-102">Configure policies to control federated user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c28f3-103">_**Argomento Ultima modifica:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="c28f3-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="c28f3-104">Quando si configurano i criteri per supportare le comunicazioni con partner federati, i criteri si applicano agli utenti di domini federati.</span><span class="sxs-lookup"><span data-stu-id="c28f3-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="c28f3-105">Puoi configurare uno o più criteri di accesso utenti esterni per controllare se gli utenti di domini federati possono collaborare con gli utenti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c28f3-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Lync Server 2013 users.</span></span> <span data-ttu-id="c28f3-106">Per controllare l'accesso degli utenti federati, è possibile configurare i criteri a livello globale, sito e utente.</span><span class="sxs-lookup"><span data-stu-id="c28f3-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="c28f3-107">Le impostazioni dei criteri di Lync Server applicate a un livello di criteri possono eseguire l'override delle impostazioni applicate a un altro livello di criteri.</span><span class="sxs-lookup"><span data-stu-id="c28f3-107">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="c28f3-108">La precedenza dei criteri di Lync Server è: criteri utente (la maggior parte delle influenze) esegue l'override di un criterio del sito e quindi un criterio del sito sostituisce un criterio globale (almeno l'influenza).</span><span class="sxs-lookup"><span data-stu-id="c28f3-108">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="c28f3-109">Ciò significa che l'impostazione del criterio è più vicina all'oggetto che il criterio sta influenzando, più influenza ha sull'oggetto.</span><span class="sxs-lookup"><span data-stu-id="c28f3-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c28f3-110">È possibile configurare i criteri per controllare l'accesso degli utenti federati, anche se non è stata abilitata la Federazione per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c28f3-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="c28f3-111">Tuttavia, i criteri configurati sono attivi solo quando è abilitata la Federazione per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c28f3-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="c28f3-112">Per informazioni dettagliate sull'abilitazione della Federazione, vedere <A href="lync-server-2013-enable-or-disable-remote-user-access.md">abilitare o disabilitare l'accesso remoto agli utenti in Lync Server 2013</A> nella documentazione relativa alla distribuzione o nella documentazione delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="c28f3-112">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="c28f3-113">Inoltre, se specifichi un criterio utente per controllare l'accesso degli utenti federati, il criterio si applica solo agli utenti abilitati per Lync Server 2013 e configurati per l'uso dei criteri.</span><span class="sxs-lookup"><span data-stu-id="c28f3-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="c28f3-114">Per configurare un criterio per il supporto dell'accesso da parte di utenti di domini federati</span><span class="sxs-lookup"><span data-stu-id="c28f3-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="c28f3-115">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="c28f3-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c28f3-116">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c28f3-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c28f3-117">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c28f3-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c28f3-118">Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**e quindi su **criteri di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="c28f3-118">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="c28f3-119">Nella pagina **criteri di accesso esterno** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c28f3-119">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="c28f3-120">Per configurare il criterio globale per il supporto dell'accesso degli utenti federati, fare clic sul criterio globale, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="c28f3-120">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="c28f3-121">Per creare un nuovo criterio sito, fare clic su **nuovo**e quindi su **criteri sito**.</span><span class="sxs-lookup"><span data-stu-id="c28f3-121">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="c28f3-122">In **Seleziona un sito**fare clic sul sito appropriato nell'elenco e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c28f3-122">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="c28f3-123">Per creare un nuovo criterio utente, fare clic su **nuovo**e quindi su **criteri utente**.</span><span class="sxs-lookup"><span data-stu-id="c28f3-123">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="c28f3-124">In **nuovi criteri di accesso esterno**, creare un nome univoco nel campo **nome** che indichi le informazioni relative ai criteri utente, ad esempio **EnableFederatedUsers** , per un criterio utente che consente le comunicazioni per gli utenti di domini federati.</span><span class="sxs-lookup"><span data-stu-id="c28f3-124">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="c28f3-125">Per modificare un criterio esistente, fare clic sul criterio appropriato elencato nella tabella, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="c28f3-125">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="c28f3-126">Opzionale Se si vuole aggiungere o modificare una descrizione, specificare le informazioni per il criterio in **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="c28f3-126">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="c28f3-127">Esegui una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c28f3-127">Do one of the following:</span></span>
    
      - <span data-ttu-id="c28f3-128">Per abilitare l'accesso degli utenti federati per il criterio, selezionare la casella di controllo **Abilita comunicazioni con gli utenti federati** .</span><span class="sxs-lookup"><span data-stu-id="c28f3-128">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="c28f3-129">Per disabilitare l'accesso degli utenti federati per il criterio, deselezionare la casella di controllo **Abilita comunicazioni con gli utenti federati** .</span><span class="sxs-lookup"><span data-stu-id="c28f3-129">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="c28f3-130">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="c28f3-130">Click **Commit**.</span></span>

<span data-ttu-id="c28f3-131">Per abilitare l'accesso degli utenti federati, devi anche abilitare il supporto per la Federazione nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c28f3-131">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="c28f3-132">Per informazioni dettagliate, vedere [abilitare o disabilitare la connettività per la messaggistica istantanea pubblica e la Federazione in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="c28f3-132">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="c28f3-133">Se si tratta di un criterio utente, devi anche applicare il criterio agli utenti che vuoi collaborare con gli utenti federati.</span><span class="sxs-lookup"><span data-stu-id="c28f3-133">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="c28f3-134">Per informazioni dettagliate, vedere [assegnare criteri di accesso degli utenti esterni a un utente abilitato a Lync in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).</span><span class="sxs-lookup"><span data-stu-id="c28f3-134">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).</span></span>

</div>

<div>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="c28f3-135">Per configurare un criterio esistente con Windows PowerShell per supportare l'accesso da parte di utenti di domini federati</span><span class="sxs-lookup"><span data-stu-id="c28f3-135">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="c28f3-136">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="c28f3-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c28f3-137">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c28f3-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c28f3-138">Digitare quanto segue in Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="c28f3-138">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="c28f3-139">Un comando di esempio che imposterà il criterio globale per l'accesso degli utenti federati all'accesso abilitato al dominio XMPP a abilitato, accesso remoto agli utenti abilitati, accesso del provider pubblico abilitato e concedere la possibilità di usare l'audio e il video per i provider pubblici che la supportano:</span><span class="sxs-lookup"><span data-stu-id="c28f3-139">An example command that will set the global policy for Federated user access to enabled, XMPP domain access to enabled, Remote user access to enabled, Public provider access to enabled, and grant the ability to use audio and video for public providers that support it:</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="c28f3-140">Il parametro "EnablePublicCloudAudioVideoAccess" non ha una selezione corrispondente nel pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="c28f3-140">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Lync Server Control Panel</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="c28f3-141">Per creare un nuovo criterio usando Windows PowerShell per supportare l'accesso da parte di utenti di domini federati</span><span class="sxs-lookup"><span data-stu-id="c28f3-141">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="c28f3-142">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="c28f3-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c28f3-143">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c28f3-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c28f3-144">Digitare quanto segue in Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="c28f3-144">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="c28f3-145">Esempio di creazione di un nuovo criterio di sito:</span><span class="sxs-lookup"><span data-stu-id="c28f3-145">An example of creating a new site policy:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

</div>

<div>

## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="c28f3-146">Per eliminare o reimpostare un criterio con Windows PowerShell per supportare l'accesso da parte di utenti di domini federati</span><span class="sxs-lookup"><span data-stu-id="c28f3-146">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="c28f3-147">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="c28f3-147">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c28f3-148">Digitare quanto segue in Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="c28f3-148">Type the following in the Lync Server Management Shell</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    <span data-ttu-id="c28f3-149">Esempio di reimpostazione del criterio globale (il criterio globale può avere solo l'impostazione rimossa.</span><span class="sxs-lookup"><span data-stu-id="c28f3-149">An example of resetting the global policy (The global policy can only have its setting removed.</span></span> <span data-ttu-id="c28f3-150">Non è possibile eliminare i criteri:</span><span class="sxs-lookup"><span data-stu-id="c28f3-150">The policy cannot be deleted):</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    <span data-ttu-id="c28f3-151">Per rimuovere un criterio sito, digitare:</span><span class="sxs-lookup"><span data-stu-id="c28f3-151">To remove a site policy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    <span data-ttu-id="c28f3-152">Elimina i criteri del sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="c28f3-152">Deletes the site policy Redmond.</span></span> <span data-ttu-id="c28f3-153">Per eliminare un criterio utente denominato UserEAPPolicy, digitare:</span><span class="sxs-lookup"><span data-stu-id="c28f3-153">To delete a user policy named UserEAPPolicy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c28f3-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c28f3-154">See Also</span></span>


[<span data-ttu-id="c28f3-155">Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c28f3-155">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[<span data-ttu-id="c28f3-156">Assegnare criteri di accesso per gli utenti esterni a un utente abilitato per Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c28f3-156">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  


[<span data-ttu-id="c28f3-157">Gestire i domini federati SIP per l'organizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c28f3-157">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="c28f3-158">Gestire i provider federati SIP per l'organizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c28f3-158">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
[<span data-ttu-id="c28f3-159">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="c28f3-159">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="c28f3-160">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="c28f3-160">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="c28f3-161">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="c28f3-161">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="c28f3-162">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="c28f3-162">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="c28f3-163">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="c28f3-163">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

