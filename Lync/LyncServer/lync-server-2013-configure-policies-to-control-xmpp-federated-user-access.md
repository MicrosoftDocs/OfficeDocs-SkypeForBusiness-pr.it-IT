---
title: "Lync Server 2013: configurare criteri per controllare l'accesso utente federato XMPP"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control XMPP federated user access
ms:assetid: 0fe0ff75-e52a-4e3e-923a-64f6412ac4e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552446(v=OCS.15)
ms:contentKeyID: 48679557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98c1cce84068681640d0b19ad0f604e9a0e518c9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="04028-102">Configurare criteri per controllare l'accesso utente federato XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04028-102">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04028-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="04028-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="04028-104">Si tratta di una documentazione preliminare e soggetta a modifiche.</span><span class="sxs-lookup"><span data-stu-id="04028-104">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="04028-105">Gli argomenti vuoti sono inclusi come segnaposto.</span><span class="sxs-lookup"><span data-stu-id="04028-105">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="04028-106">Quando si configurano i criteri per il supporto di partner federati XMPP (Extensible Messaging and Presence Protocol), i criteri si applicano agli utenti dei domini federati XMPP, ma non agli utenti dei provider di servizi di messaggistica istantanea SIP (Session Initiation Protocol), ad esempio Windows Live, o ai domini federati SIP.</span><span class="sxs-lookup"><span data-stu-id="04028-106">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="04028-107">È necessario configurare un **Partner federato XMPP** per ogni dominio federato XMPP in cui si desidera che gli utenti possano aggiungere contatti o comunicare.</span><span class="sxs-lookup"><span data-stu-id="04028-107">You configure an **XMPP Federated Partner** for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="04028-108">I criteri dei partner federati XMPP sono disponibili solo in un unico ambito; sebbene non siano definiti come criteri globali, si comportano come tali.</span><span class="sxs-lookup"><span data-stu-id="04028-108">XMPP federated partners policies are only available in a single scope, though it is not defined as a global policy, acts as a global policy.</span></span> <span data-ttu-id="04028-109">Per definire criteri globali, sito o utente per Partner federati XMPP, è necessario configurare l'ambito dei criteri creando e configurando innanzitutto Criteri di accesso esterno per l'ambito richiesto.</span><span class="sxs-lookup"><span data-stu-id="04028-109">To define a global, site or user policy for XMPP Federation Partners, you configure the policy scope by first creating and configuring the External Access Policy for the scope you require.</span></span> <span data-ttu-id="04028-110">Per informazioni dettagliate sui tipi di criteri che è possibile configurare per l'accesso esterno e la Federazione, vedere [Managing Federation and External Access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="04028-110">For details about the types of policies that you can configure for external access and federation, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="04028-111">Tutti i criteri <STRONG>Federazione e accesso esterno</STRONG> vengono applicati mediante il provisioning di tipo in-band.</span><span class="sxs-lookup"><span data-stu-id="04028-111">All <STRONG>Federation and External Access</STRONG> policies are applied through in-band provisioning.</span></span> <span data-ttu-id="04028-112">I criteri applicabili all'utente, appartenenti a un sito o con ambito globale vengono comunicati al client durante l'accesso.</span><span class="sxs-lookup"><span data-stu-id="04028-112">The policies that apply to the user, belong to a site, or are global in scope are communicated to the client during login.</span></span> <span data-ttu-id="04028-113">È possibile configurare criteri per il controllo dell'accesso dei partner federati XMPP anche se non è stata abilitata la federazione XMPP per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="04028-113">You can configure policies to control XMPP federated partner access, even if you have not enabled XMPP federation for your organization.</span></span> <span data-ttu-id="04028-114">I criteri configurati, tuttavia, hanno effetto solo dopo avere distribuito, abilitato e configurato la federazione di partner XMPP per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="04028-114">However, the policies that you configure take effect only when you have XMPP partner federation deployed, enabled and configured for your organization.</span></span> <span data-ttu-id="04028-115">Per informazioni dettagliate sulla distribuzione e la configurazione della Federazione dei partner XMPP, vedere <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Configuring SIP Federation, XMPP Federation and Public Instant Messaging in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="04028-115">For details about deploying and configuring XMPP partner federation, see <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="04028-116">Inoltre, se si specifica un criterio utente nel criterio di accesso esterno per controllare i partner federati XMPP, il criterio si applica solo agli utenti abilitati per Lync Server 2013 e configurati per l'utilizzo del criterio.</span><span class="sxs-lookup"><span data-stu-id="04028-116">Additionally, if you specify a user policy in External Access Policy to control XMPP federated partners, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a><span data-ttu-id="04028-117">Per modificare un criterio globale per i partner federati XMPP</span><span class="sxs-lookup"><span data-stu-id="04028-117">To edit a global policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="04028-118">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="04028-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="04028-119">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="04028-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="04028-120">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="04028-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="04028-121">Sulla barra di spostamento sinistra fare clic su **Accesso utente esterno** e quindi su **Criteri di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="04028-121">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="04028-122">Nella pagina **Criteri di accesso esterno** eseguire le operazioni seguenti per il criterio globale:</span><span class="sxs-lookup"><span data-stu-id="04028-122">On the **External Access Policy** page, do the following for the global policy:</span></span>

5.  <span data-ttu-id="04028-123">Fare clic sul criterio globale, fare clic su **Modifica**, quindi su Mostra dettagli.</span><span class="sxs-lookup"><span data-stu-id="04028-123">Click the global policy, click **Edit**, and then click Show details.</span></span>

6.  <span data-ttu-id="04028-124">Inserire una descrizione per il criterio globale (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="04028-124">Provide a description for the Global policy (optional).</span></span>

7.  <span data-ttu-id="04028-125">Selezionare **Abilita comunicazioni con utenti federati**.</span><span class="sxs-lookup"><span data-stu-id="04028-125">Select **Enable communications with federated users**.</span></span>

8.  <span data-ttu-id="04028-126">Selezionare **Abilita le comunicazioni con gli utenti federati XMPP**.</span><span class="sxs-lookup"><span data-stu-id="04028-126">Select **Enable communications with XMPP federated users**.</span></span>

9.  <span data-ttu-id="04028-127">Fare clic su **Commit** per salvare le modifiche al criterio globale.</span><span class="sxs-lookup"><span data-stu-id="04028-127">Click **Commit** to save your changes to the Global policy.</span></span>

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a><span data-ttu-id="04028-128">Per creare criteri sito o utente per i partner federati XMPP</span><span class="sxs-lookup"><span data-stu-id="04028-128">To create a site or user policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="04028-p105">Fare clic su **Nuovo** e quindi su **Criteri sito** o **Criteri utente**. In **Seleziona un sito** fare clic sul sito appropriato nell'elenco e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="04028-p105">Click **New**, and then click **Site policy** or **User policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>

2.  <span data-ttu-id="04028-131">Inserire una descrizione per il criterio del sito (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="04028-131">Provide a description for the Site policy (optional).</span></span>

3.  <span data-ttu-id="04028-132">Nel criterio sito o utente selezionare **Abilita comunicazioni con utenti federati**.</span><span class="sxs-lookup"><span data-stu-id="04028-132">In the site or user policy, select **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="04028-133">Selezionare **Abilita comunicazioni con gli utenti federati XMPP**.</span><span class="sxs-lookup"><span data-stu-id="04028-133">Select **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="04028-134">Fare clic su **Commit** per salvare le modifiche ai criteri sito o utente.</span><span class="sxs-lookup"><span data-stu-id="04028-134">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a><span data-ttu-id="04028-135">Per modificare un criterio esistente per i partner federati XMPP</span><span class="sxs-lookup"><span data-stu-id="04028-135">To edit an existing policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="04028-136">Per modificare un criterio esistente, selezionare il criterio appropriato nell'elenco, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="04028-136">To change an existing policy, select the appropriate policy in the list, click **Edit**, and then click **Show details**.</span></span>

2.  <span data-ttu-id="04028-137">Modificare o aggiornare la descrizione del criterio (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="04028-137">Change or update the description for the policy (optional).</span></span>

3.  <span data-ttu-id="04028-138">Selezionare o deselezionare **Abilita comunicazioni con utenti federati**.</span><span class="sxs-lookup"><span data-stu-id="04028-138">Select or unselect **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="04028-139">Selezionare o deselezionare **Abilita comunicazioni con gli utenti federati XMPP**.</span><span class="sxs-lookup"><span data-stu-id="04028-139">Select or unselect **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="04028-140">Fare clic su **Commit** per salvare le modifiche ai criteri.</span><span class="sxs-lookup"><span data-stu-id="04028-140">Click **Commit** to save your changes to the policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="04028-141">Per modificare un criterio esistente per i partner federati XMPP tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="04028-141">To edit an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="04028-142">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="04028-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="04028-143">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="04028-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="04028-144">Digitare quanto segue in Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="04028-144">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="04028-145">Un comando di esempio che consentirà di impostare i criteri globali per l'accesso degli utenti federati a true (Enabled) e l'accesso al dominio XMPP a true (attivato):</span><span class="sxs-lookup"><span data-stu-id="04028-145">An example command that will set the global policy for Federated user access to True (enabled) and XMPP domain access to True (enabled):</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a><span data-ttu-id="04028-146">Per creare criteri di sito o utente per i partner federati XMPP tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="04028-146">To create a site or user policy for XMPP federated partners using Windows PowerShell</span></span>

1.  <span data-ttu-id="04028-147">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="04028-147">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="04028-148">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="04028-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="04028-149">Digitare quanto segue in Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="04028-149">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="04028-150">Comando di esempio che abilita un criterio per il sito di Redmond per l'accesso utente federato e l'accesso ai domini XMPP:</span><span class="sxs-lookup"><span data-stu-id="04028-150">An example command that will set a site policy for the Redmond site for Federated user access to enabled and XMPP domain access to enabled:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="04028-151">Per eliminare un criterio esistente per i partner federati XMPP tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="04028-151">To delete an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="04028-152">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="04028-152">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="04028-153">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="04028-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="04028-154">Digitare quanto segue in Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="04028-154">Type the following in the Lync Server Management Shell:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    <span data-ttu-id="04028-155">Comando di esempio per l'eliminazione di un criterio utente:</span><span class="sxs-lookup"><span data-stu-id="04028-155">An example command that will delete a user policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  <span data-ttu-id="04028-156">Comando di esempio per il ripristino dei valori predefiniti del criterio globale:</span><span class="sxs-lookup"><span data-stu-id="04028-156">An example command that will reset the global policy to defaults:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="04028-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04028-157">See Also</span></span>


[<span data-ttu-id="04028-158">Assegnare un criterio di accesso utente esterno a un utente abilitato per Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04028-158">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[<span data-ttu-id="04028-159">Abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04028-159">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[<span data-ttu-id="04028-160">Gestire i partner federati XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04028-160">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[<span data-ttu-id="04028-161">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="04028-161">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="04028-162">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="04028-162">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="04028-163">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="04028-163">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="04028-164">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="04028-164">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="04028-165">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="04028-165">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

