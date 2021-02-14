---
title: Collegamento di aree di rete
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
description: "È possibile configurare i collegamenti tra due aree di rete nell'ambito del servizio Controllo di ammissione di chiamata. "
ms.openlocfilehash: 0a4f5c63b4470fbfe6d2677f0e9e6f52841f7ebb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816466"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a><span data-ttu-id="a586b-103">Collegamento delle aree di rete in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a586b-103">Linking network regions in Skype for Business Server</span></span>

<span data-ttu-id="a586b-104">È possibile configurare i collegamenti tra due aree di rete nell'ambito del servizio Controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="a586b-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="a586b-105">Utilizzare le sezioni di questo articolo per visualizzare le informazioni sui collegamenti dell'area di lavoro oppure configurare o eliminare i collegamenti dell'area netwrok.</span><span class="sxs-lookup"><span data-stu-id="a586b-105">Use the sections in this article to view newtwork region link information or configure or delete netwrok region links.</span></span> 

## <a name="view-network-region-link-information"></a><span data-ttu-id="a586b-106">Visualizzare le informazioni sul collegamento dell'area di rete</span><span class="sxs-lookup"><span data-stu-id="a586b-106">View network region link information</span></span> 

<span data-ttu-id="a586b-107">È possibile visualizzare i collegamenti tra due aree di rete nell'ambito del servizio Controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="a586b-107">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="a586b-108">Le aree di una rete sono collegate mediante una connettività WAN fisica.</span><span class="sxs-lookup"><span data-stu-id="a586b-108">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="a586b-109">È possibile utilizzare il Pannello di controllo di Skype for Business Server per visualizzare un collegamento esistente tra due aree di rete.</span><span class="sxs-lookup"><span data-stu-id="a586b-109">You can use the Skype for Business Server Control Panel to view an existing link between two network regions.</span></span> 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a><span data-ttu-id="a586b-110">Per visualizzare un collegamento area di rete nel Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a586b-110">To view a network region link in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="a586b-111">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="a586b-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a586b-112">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a586b-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a586b-113">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Collegamento **area.**</span><span class="sxs-lookup"><span data-stu-id="a586b-113">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="a586b-114">Nella pagina **Collegamento area** fare clic sul collegamento area che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="a586b-114">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="a586b-115">È possibile visualizzare informazioni su un collegamento aree alla volta.</span><span class="sxs-lookup"><span data-stu-id="a586b-115">You can only view information about one region link at a time.</span></span>

5.  <span data-ttu-id="a586b-116">Scegliere **Elimina** dal menu **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="a586b-116">From the **Edit** menu, select **Show details**.</span></span>

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a586b-117">Visualizzare le informazioni sul collegamento dell'area di rete Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="a586b-117">View network region link information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="a586b-118">È possibile visualizzare i collegamenti delle aree di rete utilizzando Windows PowerShell e il cmdlet **Get-CsNetworkRegionLink.**</span><span class="sxs-lookup"><span data-stu-id="a586b-118">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="a586b-119">È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a586b-119">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-region-link-information"></a><span data-ttu-id="a586b-120">Per visualizzare informazioni su un collegamento area di rete</span><span class="sxs-lookup"><span data-stu-id="a586b-120">To view network region link information</span></span>

  - <span data-ttu-id="a586b-121">To view information about all your network region links, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span><span class="sxs-lookup"><span data-stu-id="a586b-121">To view information about all your network region links, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="a586b-122">Il comando restituisce informazioni simili a quelle riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="a586b-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


<span data-ttu-id="a586b-123">Per informazioni dettagliate, vedere [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="a586b-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>


## <a name="configure-network-region-links"></a><span data-ttu-id="a586b-124">Configurare i collegamenti delle aree di rete</span><span class="sxs-lookup"><span data-stu-id="a586b-124">Configure network region links</span></span> 

<span data-ttu-id="a586b-125">È possibile configurare i collegamenti tra due aree di rete nell'ambito del servizio Controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="a586b-125">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="a586b-126">Le aree di una rete sono collegate mediante una connettività WAN fisica.</span><span class="sxs-lookup"><span data-stu-id="a586b-126">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="a586b-127">È possibile utilizzare il Pannello di controllo di Skype for Business Server per definire un collegamento tra due aree di rete e impostare le limitazioni della larghezza di banda per le connessioni audio e video tra queste aree.</span><span class="sxs-lookup"><span data-stu-id="a586b-127">You can use the Skype for Business Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span>

### <a name="to-create-a-network-region-link"></a><span data-ttu-id="a586b-128">Per creare un collegamento area di rete</span><span class="sxs-lookup"><span data-stu-id="a586b-128">To create a network region link</span></span>

1.  <span data-ttu-id="a586b-129">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="a586b-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a586b-130">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a586b-130">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a586b-131">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Collegamento **area.**</span><span class="sxs-lookup"><span data-stu-id="a586b-131">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="a586b-132">Nella pagina **Collegamento area** fare clic su **Nuovo.**</span><span class="sxs-lookup"><span data-stu-id="a586b-132">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="a586b-133">In **Collegamento nuova area** digitare un valore nel **campo** Nome.</span><span class="sxs-lookup"><span data-stu-id="a586b-133">In **New Region Link**, type a value in the **Name** field.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="a586b-134">Questo valore deve essere univoco all'interno della distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a586b-134">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="a586b-135">Nell'elenco a discesa Area di rete **\# 1** selezionare una delle due aree da collegare.</span><span class="sxs-lookup"><span data-stu-id="a586b-135">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="a586b-136">Nell'elenco a discesa **\# Area di rete 2** selezionare l'altra area da collegare.</span><span class="sxs-lookup"><span data-stu-id="a586b-136">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="a586b-137">Questa area deve essere diversa dall'area selezionata per Area di rete \# 1.</span><span class="sxs-lookup"><span data-stu-id="a586b-137">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="a586b-138">(Facoltativo) Se si desidera impostare limitazioni della larghezza di banda per le chiamate  audio o video tra queste aree, selezionare un profilo di criteri di larghezza di banda nell'elenco a discesa Criteri larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="a586b-138">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="a586b-139">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="a586b-139">Click **Commit**.</span></span>

### <a name="to-modify-a-network-region-link"></a><span data-ttu-id="a586b-140">Per modificare un collegamento area di rete</span><span class="sxs-lookup"><span data-stu-id="a586b-140">To modify a network region link</span></span>

1.  <span data-ttu-id="a586b-141">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="a586b-141">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a586b-142">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a586b-142">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a586b-143">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Collegamento **area.**</span><span class="sxs-lookup"><span data-stu-id="a586b-143">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="a586b-144">Nella pagina **Collegamento area** fare clic sul collegamento dell'area che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="a586b-144">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="a586b-145">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="a586b-145">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="a586b-146">In **Modifica collegamento area** è possibile modificare le aree collegate o il profilo dei criteri di larghezza di banda per questo collegamento.</span><span class="sxs-lookup"><span data-stu-id="a586b-146">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="a586b-147">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="a586b-147">Click **Commit**.</span></span>


## <a name="delete-network-region-links"></a><span data-ttu-id="a586b-148">Eliminare collegamenti area di rete</span><span class="sxs-lookup"><span data-stu-id="a586b-148">Delete network region links</span></span>

<span data-ttu-id="a586b-149">È possibile configurare i collegamenti tra due aree di rete nell'ambito del servizio Controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="a586b-149">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="a586b-150">Le aree di una rete sono collegate mediante una connettività WAN fisica.</span><span class="sxs-lookup"><span data-stu-id="a586b-150">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="a586b-151">È possibile utilizzare il Pannello di controllo di Skype for Business Server per eliminare un collegamento esistente tra due aree di rete.</span><span class="sxs-lookup"><span data-stu-id="a586b-151">You can use the Skype for Business Server Control Panel to delete an existing link between two network regions.</span></span> 

### <a name="to-delete-a-network-region-link"></a><span data-ttu-id="a586b-152">Per eliminare un collegamento area di rete</span><span class="sxs-lookup"><span data-stu-id="a586b-152">To delete a network region link</span></span>

1.  <span data-ttu-id="a586b-153">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="a586b-153">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a586b-154">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a586b-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a586b-155">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Collegamento **area.**</span><span class="sxs-lookup"><span data-stu-id="a586b-155">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="a586b-156">Nella pagina **Collegamento area** fare clic sul collegamento area che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="a586b-156">On the **Region Link** page, click the region link that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="a586b-p107">È possibile eliminare più collegamenti aree contemporaneamente. A tale scopo, premere CTRL e selezionare più collegamenti aree tenendo premuto CTRL. Per selezionare tutti i collegamenti aree, scegliere <STRONG>Seleziona tutto</STRONG> dal menu <STRONG>Modifica</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a586b-p107">You can delete more than one region link at a time. To do this, press CTRL and select multiple region links while holding down the CTRL key. Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

5.  <span data-ttu-id="a586b-160">Scegliere **Elimina** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="a586b-160">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="a586b-161">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a586b-161">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="a586b-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a586b-162">See Also</span></span>

[<span data-ttu-id="a586b-163">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="a586b-163">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[<span data-ttu-id="a586b-164">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="a586b-164">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[<span data-ttu-id="a586b-165">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="a586b-165">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[<span data-ttu-id="a586b-166">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="a586b-166">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
