---
title: Configurare criteri per controllare l'accesso degli utenti federati
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Quando si configurano criteri per supportare le comunicazioni con partner federati, i criteri si applicano agli utenti dei domini federati. '
ms.openlocfilehash: 447aad751ce6fc91bf2d6b80c8a14e92f9d4da82
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037406"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a><span data-ttu-id="302aa-103">Configurazione dei criteri per il controllo dell'accesso degli utenti federati in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="302aa-103">Configure policies to control federated user access in Skype for Business Server</span></span>

<span data-ttu-id="302aa-104">Quando si configurano criteri per supportare le comunicazioni con partner federati, i criteri si applicano agli utenti dei domini federati.</span><span class="sxs-lookup"><span data-stu-id="302aa-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="302aa-105">È possibile configurare uno o più criteri di accesso utente esterno per controllare se gli utenti dei domini federati possono collaborare con gli utenti di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="302aa-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Skype for Business Server users.</span></span> <span data-ttu-id="302aa-106">Per controllare l'accesso utente federato, è possibile configurare criteri a livello globale, di sito e di utente.</span><span class="sxs-lookup"><span data-stu-id="302aa-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="302aa-107">Le impostazioni dei criteri di Skype for Business Server applicate a un livello di criteri possono sovrascrivere le impostazioni applicate a un altro livello di criteri.</span><span class="sxs-lookup"><span data-stu-id="302aa-107">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="302aa-108">La precedenza dei criteri di Skype for Business Server è: criteri utente (la maggior parte delle influenze) sostituisce un criterio di sito e quindi un criterio sito sostituisce un criterio globale (meno influenza).</span><span class="sxs-lookup"><span data-stu-id="302aa-108">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="302aa-109">Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="302aa-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


> [!NOTE]  
> <span data-ttu-id="302aa-110">È possibile configurare criteri per il controllo dell'accesso degli utenti federati anche se non è stata abilitata la federazione per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="302aa-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="302aa-111">I criteri configurati, tuttavia, verranno applicati solo dopo aver abilitato la federazione per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="302aa-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="302aa-112">Per informazioni dettagliate sull'abilitazione della Federazione, vedere [abilitare o disabilitare l'accesso degli utenti remoti](../access-edge/enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="302aa-112">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>  <span data-ttu-id="302aa-113">Inoltre, se si specifica un criterio utente per controllare l'accesso degli utenti federati, il criterio si applica solo agli utenti abilitati per Skype for Business Server e configurati per l'utilizzo del criterio.</span><span class="sxs-lookup"><span data-stu-id="302aa-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span>


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="302aa-114">Per configurare criteri per supportare l'accesso da parte di utenti di domini federati</span><span class="sxs-lookup"><span data-stu-id="302aa-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="302aa-115">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="302aa-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="302aa-116">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="302aa-116">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="302aa-117">Sulla barra di spostamento sinistra fare clic su **Accesso utente esterno** e quindi su **Criteri di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="302aa-117">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="302aa-118">Nella pagina **Criteri di accesso esterno** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="302aa-118">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="302aa-119">Per configurare i criteri globali per il supporto dell'accesso degli utenti federati, fare clic sui criteri globali, su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="302aa-119">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="302aa-p103">Per creare nuovi criteri di sito, fare clic su **Nuovo** e quindi su **Criteri sito**. In **Seleziona un sito** fare clic sul sito appropriato nell'elenco e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="302aa-p103">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="302aa-p104">Per creare nuovi criteri utente, fare clic su **Nuovo** e quindi su **Criteri utente**. In **Nuovi criteri di accesso esterno** creare un nome univoco nel campo **Nome** che indichi lo scopo dei criteri, ad esempio **AbilitaUtentiFederati** per criteri utente che abilitano le comunicazioni per gli utenti di domini federati.</span><span class="sxs-lookup"><span data-stu-id="302aa-p104">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="302aa-124">Per modificare criteri esistenti, fare clic sui criteri appropriati indicati nella tabella, fare clic su **Modifica** e quindi fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="302aa-124">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="302aa-125">(Facoltativo) Se si desidera aggiungere o modificare una descrizione, specificare le informazioni per i criteri in **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="302aa-125">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="302aa-126">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="302aa-126">Do one of the following:</span></span>
    
      - <span data-ttu-id="302aa-127">Per abilitare l'accesso degli utenti federati per i criteri, selezionare la casella di controllo **Abilita comunicazioni con utenti federati**.</span><span class="sxs-lookup"><span data-stu-id="302aa-127">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="302aa-128">Per disabilitare l'accesso degli utenti federati per i criteri, deselezionare la casella di controllo **Abilita comunicazioni con utenti federati**.</span><span class="sxs-lookup"><span data-stu-id="302aa-128">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="302aa-129">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="302aa-129">Click **Commit**.</span></span>

<span data-ttu-id="302aa-130">Per consentire l'accesso degli utenti federati, è inoltre necessario abilitare il supporto per la federazione nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="302aa-130">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="302aa-131">Per ulteriori informazioni, vedere [abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="302aa-131">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="302aa-132">Se si tratta di criteri utente è inoltre necessario applicarli agli utenti ai quali si desidera consentire di collaborare con utenti federati.</span><span class="sxs-lookup"><span data-stu-id="302aa-132">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="302aa-133">Per ulteriori informazioni, vedere [assegnare un criterio di accesso utente esterno](assign-an-external-user-access-policy.md).</span><span class="sxs-lookup"><span data-stu-id="302aa-133">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="302aa-134">Per configurare un criterio esistente utilizzando Windows PowerShell per supportare l'accesso da parte di utenti di domini federati</span><span class="sxs-lookup"><span data-stu-id="302aa-134">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="302aa-135">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="302aa-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="302aa-136">Avviare Skype for busines Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server**e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="302aa-136">Start the Skype for Busines Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="302aa-137">Digitare quanto segue in Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="302aa-137">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > <span data-ttu-id="302aa-138">Il parametro "EnablePublicCloudAudioVideoAccess" non dispone di una selezione corrispondente nel pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="302aa-138">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Skype for Business Server Control Panel</span></span>


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="302aa-139">Per creare un nuovo criterio utilizzando Windows PowerShell per supportare l'accesso da parte di utenti di domini federati</span><span class="sxs-lookup"><span data-stu-id="302aa-139">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="302aa-140">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="302aa-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="302aa-141">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Skype for Business Server**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="302aa-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="302aa-142">Digitare quanto segue in Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="302aa-142">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    <span data-ttu-id="302aa-143">Ecco un esempio di creazione di nuovi criteri sito:</span><span class="sxs-lookup"><span data-stu-id="302aa-143">An example of creating a new site policy:</span></span>
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="302aa-144">Per eliminare o reimpostare un criterio utilizzando Windows PowerShell per supportare l'accesso da parte di utenti di domini federati</span><span class="sxs-lookup"><span data-stu-id="302aa-144">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="302aa-145">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="302aa-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="302aa-146">Digitare quanto segue in Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="302aa-146">Type the following in the Skype for Business Server Management Shell</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    <span data-ttu-id="302aa-p107">Ecco un esempio di reimpostazione dei criteri globali. È possibile rimuovere impostazioni dai criteri globali, ma non è possibile eliminarli:</span><span class="sxs-lookup"><span data-stu-id="302aa-p107">An example of resetting the global policy (The global policy can only have its setting removed. The policy cannot be deleted):</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    <span data-ttu-id="302aa-149">Per rimuovere criteri sito, digitare:</span><span class="sxs-lookup"><span data-stu-id="302aa-149">To remove a site policy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    <span data-ttu-id="302aa-150">Elimina i criteri sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="302aa-150">Deletes the site policy Redmond.</span></span> <span data-ttu-id="302aa-151">Per eliminare criteri utenti denominati UserEAPPolicy, digitare:</span><span class="sxs-lookup"><span data-stu-id="302aa-151">To delete a user policy named UserEAPPolicy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a><span data-ttu-id="302aa-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="302aa-152">See Also</span></span>


[<span data-ttu-id="302aa-153">Abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="302aa-153">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[<span data-ttu-id="302aa-154">Assegnare un criterio di accesso utente esterno</span><span class="sxs-lookup"><span data-stu-id="302aa-154">Assign an external user access policy</span></span>](assign-an-external-user-access-policy.md)

[<span data-ttu-id="302aa-155">Gestire i domini federati SIP per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="302aa-155">Manage SIP federated domains for your organization</span></span>](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[<span data-ttu-id="302aa-156">Gestire i provider federati SIP per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="302aa-156">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[<span data-ttu-id="302aa-157">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="302aa-157">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="302aa-158">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="302aa-158">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="302aa-159">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="302aa-159">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="302aa-160">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="302aa-160">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="302aa-161">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="302aa-161">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

