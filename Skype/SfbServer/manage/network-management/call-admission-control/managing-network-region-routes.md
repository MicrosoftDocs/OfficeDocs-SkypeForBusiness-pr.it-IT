---
title: Gestione delle route dell'area di rete
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Una route dell'area di rete definisce la route tra una coppia di aree della rete. Ogni coppia di aree della rete nella distribuzione del controllo di ammissione alle chiamate richiede una route dell'area di rete.
ms.openlocfilehash: 174fdd021655f3e338001582a1409107b266582e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188567"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a><span data-ttu-id="9ac6d-104">Gestione delle route dell'area di rete in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9ac6d-104">Managing network region routes in Skype for Business Server</span></span>

<span data-ttu-id="9ac6d-105">Una *route dell'area di rete* definisce la route tra una coppia di aree della rete.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-105">A *network region route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="9ac6d-106">Ogni coppia di aree della rete nella distribuzione del controllo di ammissione alle chiamate richiede una route dell'area di rete.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-106">Each pair of network regions in your call admission control deployment requires a network region route.</span></span> <span data-ttu-id="9ac6d-107">In questo modo ogni area di rete della distribuzione consente di accedere a tutte le altre aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-107">This enables every network region within the deployment to access every other region.</span></span> <span data-ttu-id="9ac6d-108">Usare le procedure descritte in questo artilce per visualizzare, creare, modificare o eliminare le route dell'area di rete.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-108">Use the procedures in this artilce to view, create, modify, or delete network region routes.</span></span>

## <a name="view-network-region-route-information"></a><span data-ttu-id="9ac6d-109">Visualizzare le informazioni sulla route dell'area di rete</span><span class="sxs-lookup"><span data-stu-id="9ac6d-109">View network region route information</span></span> 

<span data-ttu-id="9ac6d-110">Ogni area geografica in una configurazione di controllo di ammissione chiamata (CAC) deve avere un modo per accedere a tutte le altre aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-110">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="9ac6d-111">Mentre i collegamenti con le aree geografiche impostano limitazioni della larghezza di banda sulle connessioni tra regioni e rappresentano anche i collegamenti fisici, una route determina il percorso collegato che verrà attraversato dalla connessione da un'area a un'altra.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-111">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="9ac6d-112">Usare le procedure seguenti per visualizzare le route dell'area geografica esistenti in Skype for Business Server Control Panel o Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-112">Use the following procedures to view existing network region routes in Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="9ac6d-113">Per visualizzare le informazioni sulla route dell'area di rete nel pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9ac6d-113">To view network region route information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="9ac6d-114">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9ac6d-115">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9ac6d-116">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su area geografica. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="9ac6d-116">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="9ac6d-117">Nella pagina **route dell'area geografica** fare clic sulla route dell'area geografica che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-117">On the **Region Route** page, click the region route that you want to view.</span></span>


    > [!NOTE]  
    > <span data-ttu-id="9ac6d-118">È possibile visualizzare una sola route geografica alla volta.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-118">You can only view one region route at a time.</span></span>


5.  <span data-ttu-id="9ac6d-119">Nel menu **modifica** fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-119">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9ac6d-120">Visualizzazione delle informazioni sulla route dell'area di rete tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ac6d-120">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9ac6d-121">Le informazioni sulla route dell'area di rete possono essere visualizzate usando Windows PowerShell e il cmdlet Get-CsNetworkInterRegionRoute.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-121">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="9ac6d-122">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-122">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-route-information"></a><span data-ttu-id="9ac6d-123">Per visualizzare le informazioni sulla route dell'area di rete</span><span class="sxs-lookup"><span data-stu-id="9ac6d-123">To view network region route information</span></span>

  - <span data-ttu-id="9ac6d-124">Per visualizzare informazioni su tutte le route dell'area di rete, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="9ac6d-124">To view information about all your network region routes, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="9ac6d-125">Questo restituirà informazioni simili alla seguente:</span><span class="sxs-lookup"><span data-stu-id="9ac6d-125">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

<span data-ttu-id="9ac6d-126">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) .</span><span class="sxs-lookup"><span data-stu-id="9ac6d-126">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>


## <a name="create-or-modify-network-region-routes"></a><span data-ttu-id="9ac6d-127">Creare o modificare le route dell'area di rete</span><span class="sxs-lookup"><span data-stu-id="9ac6d-127">Create or modify network region routes</span></span>

<span data-ttu-id="9ac6d-128">Ogni area geografica in una configurazione di controllo di ammissione chiamata (CAC) deve avere un modo per accedere a tutte le altre aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-128">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="9ac6d-129">Mentre i collegamenti con le aree geografiche impostano limitazioni della larghezza di banda sulle connessioni tra regioni e rappresentano anche i collegamenti fisici, una route determina il percorso collegato che verrà attraversato dalla connessione da un'area a un'altra.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-129">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="9ac6d-130">Puoi usare il pannello di controllo di Skype for Business Server per configurare le route dell'area di rete.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-130">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="9ac6d-131">Dal pannello di controllo di Skype for Business Server è possibile creare, modificare o eliminare una route dell'area di rete.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-131">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="9ac6d-132">Usare questo argomento per creare o modificare una route dell'area di rete.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-132">Use this topic to create or modify a network region route.</span></span> 

### <a name="to-create-a-network-region-route"></a><span data-ttu-id="9ac6d-133">Per creare una route dell'area di rete</span><span class="sxs-lookup"><span data-stu-id="9ac6d-133">To create a network region route</span></span>

1.  <span data-ttu-id="9ac6d-134">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-134">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9ac6d-135">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9ac6d-136">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su area geografica. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="9ac6d-136">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="9ac6d-137">Nella pagina **Route Region** fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-137">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="9ac6d-138">Nella **Route New Region**Digitare un valore nel campo **nome** .</span><span class="sxs-lookup"><span data-stu-id="9ac6d-138">In **New Region Route**, type a value in the **Name** field.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="9ac6d-139">Questo valore deve essere univoco all'interno della distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-139">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="9ac6d-140">Nell'elenco a discesa \*\* \#area di rete 1\*\* Selezionare una delle due aree geografiche da connettere tramite questa route.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-140">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="9ac6d-141">Nell'elenco a discesa **Network Region \#2** Selezionare l'altra area per questa route.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-141">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="9ac6d-142">L'area geografica deve essere diversa da quella selezionata per l' \#area geografica di rete 1.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-142">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="9ac6d-143">Usare la casella di riepilogo **collegamenti area di rete** per aggiungere collegamenti all'area geografica.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-143">Use the **Network region links** list box to add region links to the route.</span></span> <span data-ttu-id="9ac6d-144">Fare clic sul pulsante **Aggiungi** per visualizzare la pagina del **collegamento all'area geografica** .</span><span class="sxs-lookup"><span data-stu-id="9ac6d-144">Click the **Add** button to display the **Region Link** page.</span></span> <span data-ttu-id="9ac6d-145">Fare clic su un collegamento all'area da aggiungere alla route e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-145">Click a region link to add to this route, and then click **OK**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="9ac6d-146">Continuare a fare clic sul pulsante **Aggiungi** per aggiungere altri collegamenti oppure selezionare un collegamento e fare clic su **Rimuovi** per rimuovere un collegamento.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-146">Continue to click the **Add** button to add more links, or select a link and click **Remove** to remove a link.</span></span>

9.  <span data-ttu-id="9ac6d-147">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-147">Click **Commit**.</span></span>


### <a name="to-modify-a-network-region-route"></a><span data-ttu-id="9ac6d-148">Per modificare una route dell'area di rete</span><span class="sxs-lookup"><span data-stu-id="9ac6d-148">To modify a network region route</span></span>

1.  <span data-ttu-id="9ac6d-149">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-149">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9ac6d-150">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-150">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9ac6d-151">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su area geografica. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="9ac6d-151">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="9ac6d-152">Nella pagina **Route Region** fare clic sulla route dell'area geografica che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-152">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="9ac6d-153">Nel menu **modifica** fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-153">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="9ac6d-154">In **modifica route area**è possibile modificare le aree affiancate da questa route e i collegamenti dell'area geografica associati alla route.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-154">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="9ac6d-155">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-155">Click **Commit**.</span></span>


## <a name="delete-existing-network-region-routes"></a><span data-ttu-id="9ac6d-156">Eliminare le route dell'area di rete esistenti</span><span class="sxs-lookup"><span data-stu-id="9ac6d-156">Delete existing network region routes</span></span>

<span data-ttu-id="9ac6d-157">Ogni area geografica in una configurazione di controllo di ammissione chiamata (CAC) deve avere un modo per accedere a tutte le altre aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-157">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="9ac6d-158">Mentre i collegamenti con le aree geografiche impostano limitazioni della larghezza di banda sulle connessioni tra regioni e rappresentano anche i collegamenti fisici, una route determina il percorso collegato che verrà attraversato dalla connessione da un'area a un'altra.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-158">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="9ac6d-159">Puoi usare il pannello di controllo di Skype for Business Server per configurare le route dell'area di rete.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-159">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="9ac6d-160">Dal pannello di controllo di Skype for Business Server è possibile creare, modificare o eliminare una route dell'area di rete.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-160">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="9ac6d-161">Usare questo argomento per eliminare le route esistenti nell'area di rete.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-161">Use this topic to delete existing network region routes.</span></span> 

### <a name="to-delete-a-network-region-route"></a><span data-ttu-id="9ac6d-162">Per eliminare una route dell'area di rete</span><span class="sxs-lookup"><span data-stu-id="9ac6d-162">To delete a network region route</span></span>

1.  <span data-ttu-id="9ac6d-163">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-163">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9ac6d-164">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9ac6d-165">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su area geografica. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="9ac6d-165">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="9ac6d-166">Nella pagina **route dell'area geografica** fare clic sulla route di area che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-166">On the **Region Route** page, click the region route that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="9ac6d-167">Puoi eliminare più di una route della regione alla volta.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-167">You can delete more than one region route at a time.</span></span> <span data-ttu-id="9ac6d-168">Per eseguire questa operazione, premere CTRL e selezionare più percorsi per le aree geografiche mentre si tiene premuto il tasto CTRL.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-168">To do this, press CTRL and select multiple region routes while holding down the CTRL key.</span></span> <span data-ttu-id="9ac6d-169">In alternativa, per selezionare tutte le route dell'area geografica, fare clic su **Seleziona tutto** dal menu **modifica** .</span><span class="sxs-lookup"><span data-stu-id="9ac6d-169">Or, to select all region routes, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="9ac6d-170">Scegliere **Elimina**dal menu **modifica** .</span><span class="sxs-lookup"><span data-stu-id="9ac6d-170">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="9ac6d-171">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ac6d-171">Click **OK**.</span></span>



## <a name="see-also"></a><span data-ttu-id="9ac6d-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ac6d-172">See Also</span></span>

[<span data-ttu-id="9ac6d-173">Gestione delle aree di rete in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9ac6d-173">Managing network regions in Skype for Business Server</span></span>](managing-network-regions.md)

[<span data-ttu-id="9ac6d-174">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="9ac6d-174">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[<span data-ttu-id="9ac6d-175">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="9ac6d-175">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[<span data-ttu-id="9ac6d-176">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="9ac6d-176">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[<span data-ttu-id="9ac6d-177">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="9ac6d-177">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
