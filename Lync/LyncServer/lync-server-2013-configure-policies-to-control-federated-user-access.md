---
title: "Lync Server 2013: configurare i criteri per controllare l'accesso degli utenti federati"
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
ms.openlocfilehash: 6e395b021c61a8b07946c9f428043d7679dcfad9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520423"
---
# <a name="configure-policies-to-control-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="a93dc-102">Configurare criteri per controllare l'accesso degli utenti federati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a93dc-102">Configure policies to control federated user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a93dc-103">_**Ultimo argomento modificato:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="a93dc-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="a93dc-104">Quando si configurano criteri per supportare le comunicazioni con partner federati, i criteri si applicano agli utenti dei domini federati.</span><span class="sxs-lookup"><span data-stu-id="a93dc-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="a93dc-105">È possibile configurare uno o più criteri di accesso utente esterno per controllare se gli utenti dei domini federati possono collaborare con gli utenti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a93dc-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Lync Server 2013 users.</span></span> <span data-ttu-id="a93dc-106">Per controllare l'accesso utente federato, è possibile configurare criteri a livello globale, di sito e di utente.</span><span class="sxs-lookup"><span data-stu-id="a93dc-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="a93dc-107">Le impostazioni criteri di Lync Server applicate a un determinato livello di criteri possono sostituire le impostazioni applicate a un altro livello di criteri.</span><span class="sxs-lookup"><span data-stu-id="a93dc-107">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="a93dc-108">La precedenza dei criteri di Lync Server è la seguente: i criteri utente (maggiore influenza) sostituiscono i criteri sito e i criteri sito sostituiscono i criteri globali (minore influenza).</span><span class="sxs-lookup"><span data-stu-id="a93dc-108">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="a93dc-109">Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="a93dc-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a93dc-110">È possibile configurare criteri per il controllo dell'accesso degli utenti federati anche se non è stata abilitata la federazione per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a93dc-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="a93dc-111">I criteri configurati, tuttavia, verranno applicati solo dopo aver abilitato la federazione per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a93dc-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="a93dc-112">Per informazioni dettagliate sull'abilitazione della Federazione, vedere <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Abilitazione o disabilitazione dell'accesso degli utenti remoti in Lync Server 2013</A> nella documentazione relativa alla distribuzione o nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="a93dc-112">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="a93dc-113">Inoltre, se si specifica un criterio utente per controllare l'accesso degli utenti federati, il criterio si applica solo agli utenti abilitati per Lync Server 2013 e configurati per l'utilizzo dei criteri.</span><span class="sxs-lookup"><span data-stu-id="a93dc-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="a93dc-114">Per configurare criteri per supportare l'accesso da parte di utenti di domini federati</span><span class="sxs-lookup"><span data-stu-id="a93dc-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="a93dc-115">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="a93dc-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a93dc-116">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a93dc-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a93dc-117">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a93dc-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a93dc-118">Sulla barra di spostamento sinistra fare clic su **Accesso utente esterno** e quindi su **Criteri di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="a93dc-118">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="a93dc-119">Nella pagina **Criteri di accesso esterno** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a93dc-119">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="a93dc-120">Per configurare i criteri globali per il supporto dell'accesso degli utenti federati, fare clic sui criteri globali, su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="a93dc-120">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="a93dc-p104">Per creare nuovi criteri di sito, fare clic su **Nuovo** e quindi su **Criteri sito**. In **Seleziona un sito** fare clic sul sito appropriato nell'elenco e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a93dc-p104">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="a93dc-p105">Per creare nuovi criteri utente, fare clic su **Nuovo** e quindi su **Criteri utente**. In **Nuovi criteri di accesso esterno** creare un nome univoco nel campo **Nome** che indichi lo scopo dei criteri, ad esempio **AbilitaUtentiFederati** per criteri utente che abilitano le comunicazioni per gli utenti di domini federati.</span><span class="sxs-lookup"><span data-stu-id="a93dc-p105">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="a93dc-125">Per modificare criteri esistenti, fare clic sui criteri appropriati indicati nella tabella, fare clic su **Modifica** e quindi fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="a93dc-125">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="a93dc-126">(Facoltativo) Se si desidera aggiungere o modificare una descrizione, specificare le informazioni per i criteri in **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="a93dc-126">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="a93dc-127">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a93dc-127">Do one of the following:</span></span>
    
      - <span data-ttu-id="a93dc-128">Per abilitare l'accesso degli utenti federati per i criteri, selezionare la casella di controllo **Abilita comunicazioni con utenti federati**.</span><span class="sxs-lookup"><span data-stu-id="a93dc-128">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="a93dc-129">Per disabilitare l'accesso degli utenti federati per i criteri, deselezionare la casella di controllo **Abilita comunicazioni con utenti federati**.</span><span class="sxs-lookup"><span data-stu-id="a93dc-129">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="a93dc-130">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="a93dc-130">Click **Commit**.</span></span>

<span data-ttu-id="a93dc-131">Per consentire l'accesso degli utenti federati, è inoltre necessario abilitare il supporto per la federazione nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a93dc-131">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="a93dc-132">Per ulteriori informazioni, vedere [abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="a93dc-132">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="a93dc-133">Se si tratta di criteri utente è inoltre necessario applicarli agli utenti ai quali si desidera consentire di collaborare con utenti federati.</span><span class="sxs-lookup"><span data-stu-id="a93dc-133">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="a93dc-134">Per ulteriori informazioni, vedere [assegnare un criterio di accesso utente esterno a un utente abilitato per Lync in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).</span><span class="sxs-lookup"><span data-stu-id="a93dc-134">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).</span></span>

</div>

<div>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="a93dc-135">Per configurare un criterio esistente utilizzando Windows PowerShell per supportare l'accesso da parte di utenti di domini federati</span><span class="sxs-lookup"><span data-stu-id="a93dc-135">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="a93dc-136">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="a93dc-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a93dc-137">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a93dc-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a93dc-138">Digitare quanto segue in Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="a93dc-138">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="a93dc-139">Ecco un comando di esempio che abilita i criteri globali per l'accesso utente federato, l'accesso al dominio XMPP, l'accesso utente remoto e l'accesso provider pubblico, e consente l'uso di audio e video ai provider pubblici che li supportano:</span><span class="sxs-lookup"><span data-stu-id="a93dc-139">An example command that will set the global policy for Federated user access to enabled, XMPP domain access to enabled, Remote user access to enabled, Public provider access to enabled, and grant the ability to use audio and video for public providers that support it:</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="a93dc-140">Il parametro "EnablePublicCloudAudioVideoAccess" non dispone di una selezione corrispondente nel pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="a93dc-140">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Lync Server Control Panel</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="a93dc-141">Per creare un nuovo criterio utilizzando Windows PowerShell per supportare l'accesso da parte di utenti di domini federati</span><span class="sxs-lookup"><span data-stu-id="a93dc-141">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="a93dc-142">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="a93dc-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a93dc-143">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a93dc-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a93dc-144">Digitare quanto segue in Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="a93dc-144">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="a93dc-145">Ecco un esempio di creazione di nuovi criteri sito:</span><span class="sxs-lookup"><span data-stu-id="a93dc-145">An example of creating a new site policy:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

</div>

<div>

## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="a93dc-146">Per eliminare o reimpostare un criterio utilizzando Windows PowerShell per supportare l'accesso da parte di utenti di domini federati</span><span class="sxs-lookup"><span data-stu-id="a93dc-146">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="a93dc-147">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="a93dc-147">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a93dc-148">Digitare quanto segue in Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a93dc-148">Type the following in the Lync Server Management Shell</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    <span data-ttu-id="a93dc-p108">Ecco un esempio di reimpostazione dei criteri globali. È possibile rimuovere impostazioni dai criteri globali, ma non è possibile eliminarli:</span><span class="sxs-lookup"><span data-stu-id="a93dc-p108">An example of resetting the global policy (The global policy can only have its setting removed. The policy cannot be deleted):</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    <span data-ttu-id="a93dc-151">Per rimuovere criteri sito, digitare:</span><span class="sxs-lookup"><span data-stu-id="a93dc-151">To remove a site policy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    <span data-ttu-id="a93dc-152">Elimina i criteri sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="a93dc-152">Deletes the site policy Redmond.</span></span> <span data-ttu-id="a93dc-153">Per eliminare criteri utenti denominati UserEAPPolicy, digitare:</span><span class="sxs-lookup"><span data-stu-id="a93dc-153">To delete a user policy named UserEAPPolicy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a93dc-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a93dc-154">See Also</span></span>


[<span data-ttu-id="a93dc-155">Abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a93dc-155">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[<span data-ttu-id="a93dc-156">Assegnare un criterio di accesso utente esterno a un utente abilitato per Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a93dc-156">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  


[<span data-ttu-id="a93dc-157">Gestire i domini federati SIP per l'organizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a93dc-157">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="a93dc-158">Gestire i provider federati SIP per l'organizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a93dc-158">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
[<span data-ttu-id="a93dc-159">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="a93dc-159">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="a93dc-160">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="a93dc-160">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="a93dc-161">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="a93dc-161">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="a93dc-162">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="a93dc-162">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="a93dc-163">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="a93dc-163">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

