---
title: Collegamento tra aree di rete
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
description: "È possibile configurare i collegamenti tra due aree di rete nell'ambito del controllo di ammissione di chiamata (CAC). "
ms.openlocfilehash: 4a643f34b9525b53168b9015b77a7f8292abd417
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817525"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a><span data-ttu-id="4c557-103">Collegamento delle aree di rete in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4c557-103">Linking network regions in Skype for Business Server</span></span>

<span data-ttu-id="4c557-104">È possibile configurare i collegamenti tra due aree di rete nell'ambito del controllo di ammissione di chiamata (CAC).</span><span class="sxs-lookup"><span data-stu-id="4c557-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="4c557-105">Usare le sezioni di questo articolo per visualizzare le informazioni sul collegamento all'area del Tritone o per configurare o eliminare i collegamenti all'area geografica di netwrok.</span><span class="sxs-lookup"><span data-stu-id="4c557-105">Use the sections in this article to view newtwork region link information or configure or delete netwrok region links.</span></span> 

## <a name="view-network-region-link-information"></a><span data-ttu-id="4c557-106">Visualizzare le informazioni sul collegamento all'area di rete</span><span class="sxs-lookup"><span data-stu-id="4c557-106">View network region link information</span></span> 

<span data-ttu-id="4c557-107">È possibile visualizzare i collegamenti tra due aree di rete come parte del controllo di ammissione di chiamata (CAC).</span><span class="sxs-lookup"><span data-stu-id="4c557-107">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="4c557-108">Le aree all'interno di una rete sono collegate tramite connettività WAN (Physical Wide Area Network).</span><span class="sxs-lookup"><span data-stu-id="4c557-108">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="4c557-109">Puoi usare il pannello di controllo di Skype for Business Server per visualizzare un collegamento esistente tra due aree di rete.</span><span class="sxs-lookup"><span data-stu-id="4c557-109">You can use the Skype for Business Server Control Panel to view an existing link between two network regions.</span></span> 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a><span data-ttu-id="4c557-110">Per visualizzare un collegamento all'area di rete nel pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4c557-110">To view a network region link in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="4c557-111">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="4c557-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4c557-112">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4c557-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4c557-113">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su collegamento all' **area geografica**.</span><span class="sxs-lookup"><span data-stu-id="4c557-113">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="4c557-114">Nella pagina **collegamento all'area geografica** fare clic sul collegamento all'area che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="4c557-114">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="4c557-115">Puoi visualizzare solo le informazioni su un collegamento all'area geografica alla volta.</span><span class="sxs-lookup"><span data-stu-id="4c557-115">You can only view information about one region link at a time.</span></span>

5.  <span data-ttu-id="4c557-116">Nel menu **modifica** selezionare **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="4c557-116">From the **Edit** menu, select **Show details**.</span></span>

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4c557-117">Visualizzare le informazioni sul collegamento all'area di rete tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c557-117">View network region link information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="4c557-118">È possibile visualizzare i collegamenti all'area di rete usando Windows PowerShell e il cmdlet **Get-CsNetworkRegionLink** .</span><span class="sxs-lookup"><span data-stu-id="4c557-118">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="4c557-119">Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c557-119">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-region-link-information"></a><span data-ttu-id="4c557-120">Per visualizzare le informazioni sul collegamento all'area di rete</span><span class="sxs-lookup"><span data-stu-id="4c557-120">To view network region link information</span></span>

  - <span data-ttu-id="4c557-121">Per visualizzare informazioni su tutti i collegamenti dell'area geografica di rete, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="4c557-121">To view information about all your network region links, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="4c557-122">Questo comando restituisce informazioni simili a quelle seguenti:</span><span class="sxs-lookup"><span data-stu-id="4c557-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


<span data-ttu-id="4c557-123">Per informazioni dettagliate, vedere [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="4c557-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>


## <a name="configure-network-region-links"></a><span data-ttu-id="4c557-124">Configurare i collegamenti dell'area di rete</span><span class="sxs-lookup"><span data-stu-id="4c557-124">Configure network region links</span></span> 

<span data-ttu-id="4c557-125">È possibile configurare i collegamenti tra due aree di rete nell'ambito del controllo di ammissione di chiamata (CAC).</span><span class="sxs-lookup"><span data-stu-id="4c557-125">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="4c557-126">Le aree all'interno di una rete sono collegate tramite connettività WAN (Physical Wide Area Network).</span><span class="sxs-lookup"><span data-stu-id="4c557-126">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="4c557-127">È possibile usare il pannello di controllo di Skype for Business Server per definire un collegamento tra due aree di rete e impostare le limitazioni della larghezza di banda per le connessioni audio e video tra queste aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="4c557-127">You can use the Skype for Business Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span>

### <a name="to-create-a-network-region-link"></a><span data-ttu-id="4c557-128">Per creare un collegamento all'area di rete</span><span class="sxs-lookup"><span data-stu-id="4c557-128">To create a network region link</span></span>

1.  <span data-ttu-id="4c557-129">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="4c557-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4c557-130">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4c557-130">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4c557-131">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su collegamento all' **area geografica**.</span><span class="sxs-lookup"><span data-stu-id="4c557-131">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="4c557-132">Nella pagina **collegamento all'area geografica** fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="4c557-132">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="4c557-133">Nel **collegamento New Region**Digitare un valore nel campo **nome** .</span><span class="sxs-lookup"><span data-stu-id="4c557-133">In **New Region Link**, type a value in the **Name** field.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="4c557-134">Questo valore deve essere univoco all'interno della distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4c557-134">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="4c557-135">Nell'elenco a discesa **Network Region \#1** Selezionare una delle due aree geografiche da collegare.</span><span class="sxs-lookup"><span data-stu-id="4c557-135">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="4c557-136">Nell'elenco a discesa **Network Region \#2** Selezionare l'altra area da collegare.</span><span class="sxs-lookup"><span data-stu-id="4c557-136">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="4c557-137">L'area geografica deve essere diversa da quella selezionata per l' \#area geografica di rete 1.</span><span class="sxs-lookup"><span data-stu-id="4c557-137">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="4c557-138">Opzionale Se si desidera inserire limitazioni della larghezza di banda per le chiamate audio o video tra queste aree geografiche, selezionare un profilo dei criteri di larghezza di banda nell'elenco a discesa **criteri di larghezza** di banda.</span><span class="sxs-lookup"><span data-stu-id="4c557-138">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="4c557-139">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="4c557-139">Click **Commit**.</span></span>

### <a name="to-modify-a-network-region-link"></a><span data-ttu-id="4c557-140">Per modificare un collegamento all'area di rete</span><span class="sxs-lookup"><span data-stu-id="4c557-140">To modify a network region link</span></span>

1.  <span data-ttu-id="4c557-141">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="4c557-141">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4c557-142">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4c557-142">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4c557-143">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su collegamento all' **area geografica**.</span><span class="sxs-lookup"><span data-stu-id="4c557-143">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="4c557-144">Nella pagina **collegamento all'area geografica** fare clic sul collegamento all'area che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="4c557-144">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="4c557-145">Nel menu **modifica** fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="4c557-145">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="4c557-146">In **Modifica collegamento area**è possibile modificare le aree collegate o il profilo dei criteri di larghezza di banda per questo collegamento.</span><span class="sxs-lookup"><span data-stu-id="4c557-146">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="4c557-147">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="4c557-147">Click **Commit**.</span></span>


## <a name="delete-network-region-links"></a><span data-ttu-id="4c557-148">Eliminare i collegamenti all'area di rete</span><span class="sxs-lookup"><span data-stu-id="4c557-148">Delete network region links</span></span>

<span data-ttu-id="4c557-149">È possibile configurare i collegamenti tra due aree di rete nell'ambito del controllo di ammissione di chiamata (CAC).</span><span class="sxs-lookup"><span data-stu-id="4c557-149">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="4c557-150">Le aree all'interno di una rete sono collegate tramite connettività WAN (Physical Wide Area Network).</span><span class="sxs-lookup"><span data-stu-id="4c557-150">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="4c557-151">È possibile usare il pannello di controllo di Skype for Business Server per eliminare un collegamento esistente tra due aree di rete.</span><span class="sxs-lookup"><span data-stu-id="4c557-151">You can use the Skype for Business Server Control Panel to delete an existing link between two network regions.</span></span> 

### <a name="to-delete-a-network-region-link"></a><span data-ttu-id="4c557-152">Per eliminare un collegamento all'area di rete</span><span class="sxs-lookup"><span data-stu-id="4c557-152">To delete a network region link</span></span>

1.  <span data-ttu-id="4c557-153">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="4c557-153">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4c557-154">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4c557-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4c557-155">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su collegamento all' **area geografica**.</span><span class="sxs-lookup"><span data-stu-id="4c557-155">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="4c557-156">Nella pagina **collegamento all'area geografica** fare clic sul collegamento all'area che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="4c557-156">On the **Region Link** page, click the region link that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="4c557-157">Puoi eliminare più di un collegamento all'area geografica alla volta.</span><span class="sxs-lookup"><span data-stu-id="4c557-157">You can delete more than one region link at a time.</span></span> <span data-ttu-id="4c557-158">Per eseguire questa operazione, premere CTRL e selezionare più collegamenti all'area geografica tenendo premuto CTRL.</span><span class="sxs-lookup"><span data-stu-id="4c557-158">To do this, press CTRL and select multiple region links while holding down the CTRL key.</span></span> <span data-ttu-id="4c557-159">In alternativa, per selezionare tutti i collegamenti all'area geografica, fare clic su <STRONG>Seleziona tutto</STRONG> dal menu <STRONG>modifica</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="4c557-159">Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

5.  <span data-ttu-id="4c557-160">Scegliere **Elimina**dal menu **modifica** .</span><span class="sxs-lookup"><span data-stu-id="4c557-160">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="4c557-161">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c557-161">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="4c557-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c557-162">See Also</span></span>

[<span data-ttu-id="4c557-163">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="4c557-163">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[<span data-ttu-id="4c557-164">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="4c557-164">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[<span data-ttu-id="4c557-165">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="4c557-165">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[<span data-ttu-id="4c557-166">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="4c557-166">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
