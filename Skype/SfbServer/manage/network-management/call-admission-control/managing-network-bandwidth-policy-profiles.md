---
title: Gestione dei profili dei criteri di larghezza di banda di rete
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Utilizzare le procedure descritte in questo articolo per visualizzare, creare, modificare o eliminare i profili dei criteri di larghezza di banda di rete.
ms.openlocfilehash: 69efe657b6df775b9e647a77bef2588cafdc5b03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816446"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="820a4-103">Gestione dei profili di criteri di larghezza di banda di rete in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="820a4-103">Managing network bandwidth policy profiles in Skype for Business Server</span></span>

<span data-ttu-id="820a4-104">Utilizzare le procedure descritte in questo articolo per visualizzare, creare, modificare o eliminare i profili dei criteri di larghezza di banda di rete.</span><span class="sxs-lookup"><span data-stu-id="820a4-104">Use the procedures in this article to view, create, modify, or delete network bandwidth policy profiles.</span></span>

## <a name="view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="820a4-105">Visualizzare le informazioni sul profilo dei criteri di larghezza di banda di rete</span><span class="sxs-lookup"><span data-stu-id="820a4-105">View network bandwidth policy profile information</span></span>

<span data-ttu-id="820a4-106">In Controllo di ammissione di chiamata (CAC) i criteri di larghezza di banda vengono utilizzati per definire le limitazioni della larghezza di banda per alcune modalità.</span><span class="sxs-lookup"><span data-stu-id="820a4-106">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="820a4-107">In Skype for Business Server, solo le modalità audio e video possono essere assegnate limitazioni della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="820a4-107">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="820a4-108">È possibile impostare limitazioni della larghezza di banda globali o per le sessioni.</span><span class="sxs-lookup"><span data-stu-id="820a4-108">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="820a4-109">Puoi usare il Pannello di controllo di Skype for Business Server per creare, modificare o eliminare un profilo contenitore per questi criteri.</span><span class="sxs-lookup"><span data-stu-id="820a4-109">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="820a4-110">Ogni profilo di criteri della larghezza di banda può essere associato a uno o più siti di rete.</span><span class="sxs-lookup"><span data-stu-id="820a4-110">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="820a4-111">Utilizzare le procedure seguenti per visualizzare un profilo di criteri della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="820a4-111">Use the following procedures to view a bandwidth policy profile.</span></span> 

### <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="820a4-112">Per visualizzare un profilo di criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="820a4-112">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="820a4-113">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="820a4-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="820a4-114">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="820a4-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="820a4-115">Nella barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Criteri larghezza di banda**.</span><span class="sxs-lookup"><span data-stu-id="820a4-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="820a4-116">Nella pagina **Criteri larghezza di** banda fare clic sul profilo dei criteri di larghezza di banda che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="820a4-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="820a4-117">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="820a4-117">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="820a4-118">Visualizzazione delle informazioni sui profili dei criteri di larghezza di banda di rete Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="820a4-118">Viewing network bandwidth policy profile information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="820a4-119">I profili di larghezza di banda di rete possono essere visualizzati Windows PowerShell e il cmdlet Get-CsNetworkBandwidthPolicyProfile rete.</span><span class="sxs-lookup"><span data-stu-id="820a4-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="820a4-120">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="820a4-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="820a4-121">Per visualizzare le informazioni sul profilo dei criteri di larghezza di banda di rete</span><span class="sxs-lookup"><span data-stu-id="820a4-121">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="820a4-122">Per visualizzare informazioni su tutti i profili dei criteri di larghezza di banda di rete, digitare il comando seguente in Skype for Business Server Management Shell, quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="820a4-122">To view information about all your network bandwidth policy profiles, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="820a4-123">Verranno restituite informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="820a4-123">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


<span data-ttu-id="820a4-124">Per ulteriori informazioni, vedere l'argomento della Guida per il cmdlet [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span><span class="sxs-lookup"><span data-stu-id="820a4-124">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>


## <a name="create-or-modify-bandwidth-policy-profiles"></a><span data-ttu-id="820a4-125">Creare o modificare i profili dei criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="820a4-125">Create or modify bandwidth policy profiles</span></span>

<span data-ttu-id="820a4-126">In Controllo di ammissione di chiamata (CAC) i criteri di larghezza di banda vengono utilizzati per definire le limitazioni della larghezza di banda per alcune modalità.</span><span class="sxs-lookup"><span data-stu-id="820a4-126">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="820a4-127">In Skype for Business Server, solo le modalità audio e video possono essere assegnate limitazioni della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="820a4-127">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="820a4-128">È possibile impostare limitazioni della larghezza di banda globali o per le sessioni.</span><span class="sxs-lookup"><span data-stu-id="820a4-128">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="820a4-129">Puoi usare il Pannello di controllo di Skype for Business Server per creare, modificare o eliminare un profilo contenitore per questi criteri.</span><span class="sxs-lookup"><span data-stu-id="820a4-129">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="820a4-130">Ogni profilo di criteri della larghezza di banda può essere associato a uno o più siti di rete.</span><span class="sxs-lookup"><span data-stu-id="820a4-130">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="820a4-131">Utilizzare le procedure seguenti per creare o modificare un profilo di criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="820a4-131">Use the following procedures to create or modify a bandwidth policy profile.</span></span> 

### <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="820a4-132">Per creare un nuovo profilo di criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="820a4-132">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="820a4-133">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="820a4-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="820a4-134">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="820a4-134">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="820a4-135">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Criteri larghezza di **banda.**</span><span class="sxs-lookup"><span data-stu-id="820a4-135">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="820a4-136">Nella pagina **Criteri larghezza di** banda fare clic su **Nuovo.**</span><span class="sxs-lookup"><span data-stu-id="820a4-136">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="820a4-137">In **Nuovo profilo criteri larghezza di** banda digitare un nome nel **campo** Nome.</span><span class="sxs-lookup"><span data-stu-id="820a4-137">In **New Bandwidth Policy Profile**, type a name in the **Name** field.</span></span> <span data-ttu-id="820a4-138">Questo nome deve essere univoco tra tutti i profili dei criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="820a4-138">This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="820a4-139">Nel campo **Limite audio** digitare un valore numerico.</span><span class="sxs-lookup"><span data-stu-id="820a4-139">In the **Audio limit** field, type a numeric value.</span></span> <span data-ttu-id="820a4-140">Questo valore è la quantità massima di larghezza di banda da allocare per tutte le connessioni audio, espressa in kbps.</span><span class="sxs-lookup"><span data-stu-id="820a4-140">This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="820a4-141">Immettere un valore numerico nel campo **Limite sessione** audio.</span><span class="sxs-lookup"><span data-stu-id="820a4-141">Enter a numeric value in the **Audio session limit** field.</span></span> <span data-ttu-id="820a4-142">Questo valore è la quantità massima di larghezza di banda da allocare per una singola connessione audio, espressa in kbps.</span><span class="sxs-lookup"><span data-stu-id="820a4-142">This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps.</span></span> <span data-ttu-id="820a4-143">Questo valore deve essere 40 o superiore.</span><span class="sxs-lookup"><span data-stu-id="820a4-143">This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="820a4-144">Immettere un valore numerico nel campo **Limite video.**</span><span class="sxs-lookup"><span data-stu-id="820a4-144">Enter a numeric value in the **Video limit** field.</span></span> <span data-ttu-id="820a4-145">Questo valore è la quantità massima di larghezza di banda da allocare per tutte le connessioni video, espressa in kbps.</span><span class="sxs-lookup"><span data-stu-id="820a4-145">This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="820a4-146">Immettere un valore numerico nel campo **Limite sessioni** video.</span><span class="sxs-lookup"><span data-stu-id="820a4-146">Enter a numeric value in the **Video session limit** field.</span></span> <span data-ttu-id="820a4-147">Questo valore è la quantità massima di larghezza di banda da allocare per una singola connessione video, espressa in kbps.</span><span class="sxs-lookup"><span data-stu-id="820a4-147">This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps.</span></span> <span data-ttu-id="820a4-148">Questo valore deve essere 100 o superiore.</span><span class="sxs-lookup"><span data-stu-id="820a4-148">This value must be 100 or higher.</span></span>

10. <span data-ttu-id="820a4-149">(Facoltativo) Digitare un valore nel campo **Descrizione** per fornire ulteriori informazioni su questo profilo di criteri di larghezza di banda che non può essere espresso solo dal nome.</span><span class="sxs-lookup"><span data-stu-id="820a4-149">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="820a4-150">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="820a4-150">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="820a4-151">La creazione di un nuovo profilo di criteri di larghezza di banda non applica automaticamente restrizioni di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="820a4-151">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="820a4-152">È innanzitutto necessario associare il profilo dei criteri a un sito.</span><span class="sxs-lookup"><span data-stu-id="820a4-152">You must first associate the policy profile with a site.</span></span> 


### <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="820a4-153">Per modificare un profilo di criteri della larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="820a4-153">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="820a4-154">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="820a4-154">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="820a4-155">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="820a4-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="820a4-156">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Criteri larghezza di **banda.**</span><span class="sxs-lookup"><span data-stu-id="820a4-156">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="820a4-157">Nella pagina **Criteri larghezza di banda** fare clic sul profilo di criteri della larghezza di banda che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="820a4-157">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="820a4-158">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="820a4-158">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="820a4-159">Nella pagina **Modifica profilo criteri larghezza di** banda modificare i campi in base alle esigenze (per informazioni dettagliate, vedere Per creare un nuovo profilo di criteri di larghezza di [banda).](#to-create-a-new-bandwidth-policy-profile)</span><span class="sxs-lookup"><span data-stu-id="820a4-159">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see [To create a new bandwidth policy profile](#to-create-a-new-bandwidth-policy-profile)).</span></span>

7.  <span data-ttu-id="820a4-160">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="820a4-160">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="820a4-161">Quando si modifica il profilo dei criteri di larghezza di banda, vengono immediatamente aggiornate le limitazioni della larghezza di banda di tutti i siti di rete associati a questo profilo di criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="820a4-161">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

  
## <a name="delete-network-bandwidth-policy-profiles"></a><span data-ttu-id="820a4-162">Eliminare i profili dei criteri di larghezza di banda di rete</span><span class="sxs-lookup"><span data-stu-id="820a4-162">Delete network bandwidth policy profiles</span></span>

<span data-ttu-id="820a4-163">In Controllo di ammissione di chiamata (CAC) i criteri di larghezza di banda vengono utilizzati per definire le limitazioni della larghezza di banda per alcune modalità.</span><span class="sxs-lookup"><span data-stu-id="820a4-163">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="820a4-164">In Skype for Business Server, solo le modalità audio e video possono essere assegnate limitazioni della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="820a4-164">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="820a4-165">È possibile impostare limitazioni della larghezza di banda globali o per le sessioni.</span><span class="sxs-lookup"><span data-stu-id="820a4-165">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="820a4-166">Puoi usare il Pannello di controllo di Skype for Business Server per creare, modificare o eliminare un profilo contenitore per questi criteri.</span><span class="sxs-lookup"><span data-stu-id="820a4-166">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="820a4-167">Usare le procedure seguenti per eliminare profili di criteri della larghezza di banda di rete.</span><span class="sxs-lookup"><span data-stu-id="820a4-167">Use the following procedures to delete a network bandwidth policy profiles.</span></span> 

### <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="820a4-168">Per eliminare un profilo di criteri della larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="820a4-168">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="820a4-169">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="820a4-169">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="820a4-170">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="820a4-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="820a4-171">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Criteri larghezza di **banda.**</span><span class="sxs-lookup"><span data-stu-id="820a4-171">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="820a4-172">Nella pagina **Criteri larghezza di banda** fare clic sul profilo di criteri della larghezza di banda che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="820a4-172">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="820a4-p111">È possibile eliminare più profili contemporaneamente. A tale scopo, tenere premuto CTRL e selezionare i diversi profili. In alternativa, per selezionare tutti i profili, scegliere **Seleziona tutto** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="820a4-p111">You can delete more than one profile at a time. To do this, press CTRL and select multiple profiles while holding down the CTRL key. Or, to select all profiles, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="820a4-176">Scegliere **Elimina** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="820a4-176">On the **Edit** menu, click **Delete**.</span></span>
   

    > [!WARNING]  
    > <span data-ttu-id="820a4-177">Non è possibile eliminare un profilo di criteri della larghezza di banda associato a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="820a4-177">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="820a4-178">È necessario rimuovere l'associazione al sito di rete prima di poter eliminare il profilo.</span><span class="sxs-lookup"><span data-stu-id="820a4-178">You must first remove the association with the network site before you can delete the profile.</span></span> 


## <a name="see-also"></a><span data-ttu-id="820a4-179">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="820a4-179">See Also</span></span>

[<span data-ttu-id="820a4-180">Gestione del controllo di ammissione di chiamata per i siti</span><span class="sxs-lookup"><span data-stu-id="820a4-180">Managing call admission control for sites</span></span>](managing-call-admission-control-for-sites.md)
 
[<span data-ttu-id="820a4-181">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="820a4-181">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="820a4-182">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="820a4-182">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="820a4-183">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="820a4-183">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="820a4-184">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="820a4-184">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

