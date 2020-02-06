---
title: Gestione dei profili di criteri di larghezza di banda di rete
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Usare le procedure descritte in questo articolo per visualizzare, creare, modificare o eliminare i profili dei criteri di larghezza di banda di rete.
ms.openlocfilehash: a9203c0935673e0dfd12d052876f06583c7c92c8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817505"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="f3bfc-103">Gestione dei profili di criteri di larghezza di banda di rete in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f3bfc-103">Managing network bandwidth policy profiles in Skype for Business Server</span></span>

<span data-ttu-id="f3bfc-104">Usare le procedure descritte in questo articolo per visualizzare, creare, modificare o eliminare i profili dei criteri di larghezza di banda di rete.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-104">Use the procedures in this article to view, create, modify, or delete network bandwidth policy profiles.</span></span>

## <a name="view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="f3bfc-105">Visualizzare informazioni sul profilo dei criteri di larghezza di banda di rete</span><span class="sxs-lookup"><span data-stu-id="f3bfc-105">View network bandwidth policy profile information</span></span>

<span data-ttu-id="f3bfc-106">Nell'ambito del controllo di ammissione di chiamata (CAC) viene usato un criterio di larghezza di banda per definire le limitazioni della larghezza di banda per determinate modalità.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-106">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="f3bfc-107">In Skype for Business Server è possibile assegnare limitazioni della larghezza di banda solo alle modalità audio e video.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-107">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="f3bfc-108">Puoi impostare limitazioni generali della larghezza di banda e limitazioni della sessione.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-108">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="f3bfc-109">Puoi usare il pannello di controllo di Skype for Business Server per creare, modificare o eliminare un profilo contenitore per questi criteri.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-109">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="f3bfc-110">Ogni profilo dei criteri di larghezza di banda può essere associato a uno o più siti di rete.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-110">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="f3bfc-111">Usare le procedure seguenti per visualizzare un profilo dei criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-111">Use the following procedures to view a bandwidth policy profile.</span></span> 

### <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="f3bfc-112">Per visualizzare un profilo dei criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="f3bfc-112">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="f3bfc-113">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f3bfc-114">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f3bfc-115">Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **criteri larghezza di banda**.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="f3bfc-116">Nella pagina **criteri di larghezza di banda** fare clic sul profilo dei criteri di larghezza di banda che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="f3bfc-117">Nel menu **modifica** fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-117">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f3bfc-118">Visualizzazione delle informazioni del profilo dei criteri di larghezza di banda di rete tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3bfc-118">Viewing network bandwidth policy profile information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="f3bfc-119">I profili di larghezza di banda di rete possono essere visualizzati usando Windows PowerShell e il cmdlet Get-CsNetworkBandwidthPolicyProfile.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="f3bfc-120">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="f3bfc-121">Per visualizzare le informazioni sul profilo dei criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="f3bfc-121">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="f3bfc-122">Per visualizzare informazioni su tutti i profili dei criteri di larghezza di banda della rete, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="f3bfc-122">To view information about all your network bandwidth policy profiles, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="f3bfc-123">Questo restituirà informazioni simili alla seguente:</span><span class="sxs-lookup"><span data-stu-id="f3bfc-123">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


<span data-ttu-id="f3bfc-124">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) .</span><span class="sxs-lookup"><span data-stu-id="f3bfc-124">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>


## <a name="create-or-modify-bandwidth-policy-profiles"></a><span data-ttu-id="f3bfc-125">Creare o modificare i profili dei criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="f3bfc-125">Create or modify bandwidth policy profiles</span></span>

<span data-ttu-id="f3bfc-126">Nell'ambito del controllo di ammissione di chiamata (CAC) viene usato un criterio di larghezza di banda per definire le limitazioni della larghezza di banda per determinate modalità.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-126">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="f3bfc-127">In Skype for Business Server è possibile assegnare limitazioni della larghezza di banda solo alle modalità audio e video.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-127">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="f3bfc-128">Puoi impostare limitazioni generali della larghezza di banda e limitazioni della sessione.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-128">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="f3bfc-129">Puoi usare il pannello di controllo di Skype for Business Server per creare, modificare o eliminare un profilo contenitore per questi criteri.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-129">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="f3bfc-130">Ogni profilo dei criteri di larghezza di banda può essere associato a uno o più siti di rete.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-130">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="f3bfc-131">Usare le procedure seguenti per creare o modificare un profilo dei criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-131">Use the following procedures to create or modify a bandwidth policy profile.</span></span> 

### <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="f3bfc-132">Per creare un nuovo profilo dei criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="f3bfc-132">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="f3bfc-133">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f3bfc-134">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-134">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f3bfc-135">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **criteri larghezza di banda**.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-135">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="f3bfc-136">Nella pagina **criteri di larghezza di banda** fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-136">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="f3bfc-137">In **nuovo profilo dei criteri di larghezza di banda**Digitare un nome nel campo **nome** .</span><span class="sxs-lookup"><span data-stu-id="f3bfc-137">In **New Bandwidth Policy Profile**, type a name in the **Name** field.</span></span> <span data-ttu-id="f3bfc-138">Questo nome deve essere univoco tra tutti i profili dei criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-138">This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="f3bfc-139">Nel campo **limite audio** Digitare un valore numerico.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-139">In the **Audio limit** field, type a numeric value.</span></span> <span data-ttu-id="f3bfc-140">Questo valore è la quantità massima di larghezza di banda da allocare per tutte le connessioni audio espresse in kbps.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-140">This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="f3bfc-141">Immettere un valore numerico nel campo **limite della sessione audio** .</span><span class="sxs-lookup"><span data-stu-id="f3bfc-141">Enter a numeric value in the **Audio session limit** field.</span></span> <span data-ttu-id="f3bfc-142">Questo valore è la quantità massima di larghezza di banda da allocare per una singola connessione audio, espressa in kbps.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-142">This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps.</span></span> <span data-ttu-id="f3bfc-143">Questo valore deve essere 40 o superiore.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-143">This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="f3bfc-144">Immettere un valore numerico nel campo **limite video** .</span><span class="sxs-lookup"><span data-stu-id="f3bfc-144">Enter a numeric value in the **Video limit** field.</span></span> <span data-ttu-id="f3bfc-145">Questo valore è la quantità massima di larghezza di banda da allocare per tutte le connessioni video espresse in kbps.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-145">This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="f3bfc-146">Immettere un valore numerico nel campo **limite sessione video** .</span><span class="sxs-lookup"><span data-stu-id="f3bfc-146">Enter a numeric value in the **Video session limit** field.</span></span> <span data-ttu-id="f3bfc-147">Questo valore è la quantità massima di larghezza di banda da allocare per una singola connessione video, espressa in kbps.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-147">This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps.</span></span> <span data-ttu-id="f3bfc-148">Questo valore deve essere 100 o superiore.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-148">This value must be 100 or higher.</span></span>

10. <span data-ttu-id="f3bfc-149">Opzionale Digitare un valore nel campo **Description** per ottenere altre informazioni su questo profilo dei criteri di larghezza di banda che non può essere espresso solo dal nome.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-149">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="f3bfc-150">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-150">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="f3bfc-151">La creazione di un nuovo profilo dei criteri di larghezza di banda non applica automaticamente restrizioni della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-151">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="f3bfc-152">È prima di tutto necessario associare il profilo dei criteri a un sito.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-152">You must first associate the policy profile with a site.</span></span> 


### <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="f3bfc-153">Per modificare un profilo dei criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="f3bfc-153">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="f3bfc-154">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-154">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f3bfc-155">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f3bfc-156">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **criteri larghezza di banda**.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-156">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="f3bfc-157">Nella pagina **criteri di larghezza di banda** fare clic sul profilo dei criteri di larghezza di banda che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-157">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="f3bfc-158">Nel menu **modifica** fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-158">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="f3bfc-159">Nella pagina **modifica profilo dei criteri di larghezza di banda** modificare i campi in modo necessario (per informazioni dettagliate, vedere [per creare un nuovo profilo dei criteri di larghezza di banda](#to-create-a-new-bandwidth-policy-profile)).</span><span class="sxs-lookup"><span data-stu-id="f3bfc-159">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see [To create a new bandwidth policy profile](#to-create-a-new-bandwidth-policy-profile)).</span></span>

7.  <span data-ttu-id="f3bfc-160">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-160">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="f3bfc-161">Quando si modifica il profilo dei criteri di larghezza di banda, verranno immediatamente aggiornate le limitazioni della larghezza di banda di tutti i siti di rete associati al profilo del criterio di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-161">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

  
## <a name="delete-network-bandwidth-policy-profiles"></a><span data-ttu-id="f3bfc-162">Eliminare i profili dei criteri di larghezza di banda di rete</span><span class="sxs-lookup"><span data-stu-id="f3bfc-162">Delete network bandwidth policy profiles</span></span>

<span data-ttu-id="f3bfc-163">Nell'ambito del controllo di ammissione di chiamata (CAC) viene usato un criterio di larghezza di banda per definire le limitazioni della larghezza di banda per determinate modalità.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-163">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="f3bfc-164">In Skype for Business Server è possibile assegnare limitazioni della larghezza di banda solo alle modalità audio e video.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-164">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="f3bfc-165">Puoi impostare limitazioni generali della larghezza di banda e limitazioni della sessione.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-165">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="f3bfc-166">Puoi usare il pannello di controllo di Skype for Business Server per creare, modificare o eliminare un profilo contenitore per questi criteri.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-166">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="f3bfc-167">Usare le procedure seguenti per eliminare i profili dei criteri di larghezza di banda di rete.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-167">Use the following procedures to delete a network bandwidth policy profiles.</span></span> 

### <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="f3bfc-168">Per eliminare un profilo dei criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="f3bfc-168">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="f3bfc-169">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-169">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f3bfc-170">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f3bfc-171">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **criteri larghezza di banda**.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-171">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="f3bfc-172">Nella pagina **criteri di larghezza di banda** fare clic sul profilo dei criteri di larghezza di banda che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-172">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="f3bfc-173">È possibile eliminare più di un profilo alla volta.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-173">You can delete more than one profile at a time.</span></span> <span data-ttu-id="f3bfc-174">Per eseguire questa operazione, premere CTRL e selezionare più profili tenendo premuto il tasto CTRL.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-174">To do this, press CTRL and select multiple profiles while holding down the CTRL key.</span></span> <span data-ttu-id="f3bfc-175">In alternativa, per selezionare tutti i profili, fare clic su **Seleziona tutto** dal menu **modifica** .</span><span class="sxs-lookup"><span data-stu-id="f3bfc-175">Or, to select all profiles, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="f3bfc-176">Scegliere **Elimina**dal menu **modifica** .</span><span class="sxs-lookup"><span data-stu-id="f3bfc-176">On the **Edit** menu, click **Delete**.</span></span>
   

    > [!WARNING]  
    > <span data-ttu-id="f3bfc-177">Non è possibile eliminare un profilo dei criteri di larghezza di banda associato a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-177">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="f3bfc-178">Prima di poter eliminare il profilo, devi prima rimuovere l'associazione con il sito di rete.</span><span class="sxs-lookup"><span data-stu-id="f3bfc-178">You must first remove the association with the network site before you can delete the profile.</span></span> 


## <a name="see-also"></a><span data-ttu-id="f3bfc-179">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3bfc-179">See Also</span></span>

[<span data-ttu-id="f3bfc-180">Gestione del controllo dell'ammissione delle chiamate per i siti</span><span class="sxs-lookup"><span data-stu-id="f3bfc-180">Managing call admission control for sites</span></span>](managing-call-admission-control-for-sites.md)
 
[<span data-ttu-id="f3bfc-181">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="f3bfc-181">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="f3bfc-182">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="f3bfc-182">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="f3bfc-183">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="f3bfc-183">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="f3bfc-184">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="f3bfc-184">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

