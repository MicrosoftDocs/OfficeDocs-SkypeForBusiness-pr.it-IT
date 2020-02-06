---
title: Configurare criteri per controllare l'accesso utente federato
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
description: 'Quando si configurano i criteri per supportare le comunicazioni con partner federati, i criteri si applicano agli utenti di domini federati. '
ms.openlocfilehash: 2e9385436427fd73f90e308d7747cf304bf37501
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818317"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a><span data-ttu-id="40162-103">Configurare i criteri per controllare l'accesso degli utenti federati in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="40162-103">Configure policies to control federated user access in Skype for Business Server</span></span>

<span data-ttu-id="40162-104">Quando si configurano i criteri per supportare le comunicazioni con partner federati, i criteri si applicano agli utenti di domini federati.</span><span class="sxs-lookup"><span data-stu-id="40162-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="40162-105">Puoi configurare uno o più criteri di accesso utenti esterni per controllare se gli utenti di domini federati possono collaborare con gli utenti di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="40162-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Skype for Business Server users.</span></span> <span data-ttu-id="40162-106">Per controllare l'accesso degli utenti federati, è possibile configurare i criteri a livello globale, sito e utente.</span><span class="sxs-lookup"><span data-stu-id="40162-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="40162-107">Le impostazioni dei criteri di Skype for Business Server applicate a un livello di criteri possono eseguire l'override delle impostazioni applicate a un altro livello di criteri.</span><span class="sxs-lookup"><span data-stu-id="40162-107">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="40162-108">La precedenza dei criteri di Skype for Business Server è: criteri utente (la maggior parte delle influenze) esegue l'override di un criterio del sito e quindi un criterio del sito sostituisce un criterio globale (almeno l'influenza).</span><span class="sxs-lookup"><span data-stu-id="40162-108">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="40162-109">Ciò significa che l'impostazione del criterio è più vicina all'oggetto che il criterio sta influenzando, più influenza ha sull'oggetto.</span><span class="sxs-lookup"><span data-stu-id="40162-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


> [!NOTE]  
> <span data-ttu-id="40162-110">È possibile configurare i criteri per controllare l'accesso degli utenti federati, anche se non è stata abilitata la Federazione per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="40162-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="40162-111">Tuttavia, i criteri configurati sono attivi solo quando è abilitata la Federazione per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="40162-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="40162-112">Per informazioni dettagliate sull'abilitazione della Federazione, vedere [abilitare o disabilitare l'accesso remoto agli utenti](../access-edge/enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="40162-112">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>  <span data-ttu-id="40162-113">Inoltre, se specifichi un criterio utente per controllare l'accesso degli utenti federati, il criterio si applica solo agli utenti abilitati per Skype for Business Server e configurati per l'uso dei criteri.</span><span class="sxs-lookup"><span data-stu-id="40162-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span>


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="40162-114">Per configurare un criterio per il supporto dell'accesso da parte di utenti di domini federati</span><span class="sxs-lookup"><span data-stu-id="40162-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="40162-115">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="40162-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="40162-116">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="40162-116">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="40162-117">Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**e quindi su **criteri di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="40162-117">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="40162-118">Nella pagina **criteri di accesso esterno** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="40162-118">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="40162-119">Per configurare il criterio globale per il supporto dell'accesso degli utenti federati, fare clic sul criterio globale, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="40162-119">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="40162-120">Per creare un nuovo criterio sito, fare clic su **nuovo**e quindi su **criteri sito**.</span><span class="sxs-lookup"><span data-stu-id="40162-120">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="40162-121">In **Seleziona un sito**fare clic sul sito appropriato nell'elenco e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="40162-121">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="40162-122">Per creare un nuovo criterio utente, fare clic su **nuovo**e quindi su **criteri utente**.</span><span class="sxs-lookup"><span data-stu-id="40162-122">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="40162-123">In **nuovi criteri di accesso esterno**, creare un nome univoco nel campo **nome** che indichi le informazioni relative ai criteri utente, ad esempio **EnableFederatedUsers** , per un criterio utente che consente le comunicazioni per gli utenti di domini federati.</span><span class="sxs-lookup"><span data-stu-id="40162-123">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="40162-124">Per modificare un criterio esistente, fare clic sul criterio appropriato elencato nella tabella, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="40162-124">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="40162-125">Opzionale Se si vuole aggiungere o modificare una descrizione, specificare le informazioni per il criterio in **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="40162-125">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="40162-126">Esegui una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="40162-126">Do one of the following:</span></span>
    
      - <span data-ttu-id="40162-127">Per abilitare l'accesso degli utenti federati per il criterio, selezionare la casella di controllo **Abilita comunicazioni con gli utenti federati** .</span><span class="sxs-lookup"><span data-stu-id="40162-127">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="40162-128">Per disabilitare l'accesso degli utenti federati per il criterio, deselezionare la casella di controllo **Abilita comunicazioni con gli utenti federati** .</span><span class="sxs-lookup"><span data-stu-id="40162-128">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="40162-129">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="40162-129">Click **Commit**.</span></span>

<span data-ttu-id="40162-130">Per abilitare l'accesso degli utenti federati, devi anche abilitare il supporto per la Federazione nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="40162-130">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="40162-131">Per informazioni dettagliate, vedere [abilitare o disabilitare la connettività per la messaggistica istantanea pubblica e la Federazione](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="40162-131">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="40162-132">Se si tratta di un criterio utente, devi anche applicare il criterio agli utenti che vuoi collaborare con gli utenti federati.</span><span class="sxs-lookup"><span data-stu-id="40162-132">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="40162-133">Per informazioni dettagliate, vedere [assegnare criteri di accesso degli utenti esterni](assign-an-external-user-access-policy.md).</span><span class="sxs-lookup"><span data-stu-id="40162-133">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="40162-134">Per configurare un criterio esistente con Windows PowerShell per supportare l'accesso da parte di utenti di domini federati</span><span class="sxs-lookup"><span data-stu-id="40162-134">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="40162-135">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="40162-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="40162-136">Avviare Skype for busines Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server**e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="40162-136">Start the Skype for Busines Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="40162-137">Digitare quanto segue in Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="40162-137">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > <span data-ttu-id="40162-138">Il parametro "EnablePublicCloudAudioVideoAccess" non ha una selezione corrispondente nel pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="40162-138">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Skype for Business Server Control Panel</span></span>


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="40162-139">Per creare un nuovo criterio usando Windows PowerShell per supportare l'accesso da parte di utenti di domini federati</span><span class="sxs-lookup"><span data-stu-id="40162-139">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="40162-140">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="40162-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="40162-141">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Microsoft Skype for business**server e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="40162-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="40162-142">Digitare quanto segue in Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="40162-142">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    <span data-ttu-id="40162-143">Esempio di creazione di un nuovo criterio di sito:</span><span class="sxs-lookup"><span data-stu-id="40162-143">An example of creating a new site policy:</span></span>
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="40162-144">Per eliminare o reimpostare un criterio con Windows PowerShell per supportare l'accesso da parte di utenti di domini federati</span><span class="sxs-lookup"><span data-stu-id="40162-144">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="40162-145">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="40162-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="40162-146">Digitare quanto segue in Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="40162-146">Type the following in the Skype for Business Server Management Shell</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    <span data-ttu-id="40162-147">Esempio di reimpostazione del criterio globale (il criterio globale può avere solo l'impostazione rimossa.</span><span class="sxs-lookup"><span data-stu-id="40162-147">An example of resetting the global policy (The global policy can only have its setting removed.</span></span> <span data-ttu-id="40162-148">Non è possibile eliminare i criteri:</span><span class="sxs-lookup"><span data-stu-id="40162-148">The policy cannot be deleted):</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    <span data-ttu-id="40162-149">Per rimuovere un criterio sito, digitare:</span><span class="sxs-lookup"><span data-stu-id="40162-149">To remove a site policy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    <span data-ttu-id="40162-150">Elimina i criteri del sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="40162-150">Deletes the site policy Redmond.</span></span> <span data-ttu-id="40162-151">Per eliminare un criterio utente denominato UserEAPPolicy, digitare:</span><span class="sxs-lookup"><span data-stu-id="40162-151">To delete a user policy named UserEAPPolicy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a><span data-ttu-id="40162-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40162-152">See Also</span></span>


[<span data-ttu-id="40162-153">Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="40162-153">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[<span data-ttu-id="40162-154">Assegnare criteri di accesso per gli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="40162-154">Assign an external user access policy</span></span>](assign-an-external-user-access-policy.md)

[<span data-ttu-id="40162-155">Gestire i domini federati SIP per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="40162-155">Manage SIP federated domains for your organization</span></span>](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[<span data-ttu-id="40162-156">Gestire i provider federati SIP per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="40162-156">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[<span data-ttu-id="40162-157">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="40162-157">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="40162-158">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="40162-158">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="40162-159">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="40162-159">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="40162-160">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="40162-160">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="40162-161">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="40162-161">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

