---
title: Gestione delle route dell'area di rete
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
description: Una route area di rete definisce la route tra una coppia di aree di rete. Ogni coppia di aree di rete nella distribuzione del servizio Controllo di ammissione di chiamata richiede una route di questo tipo.
ms.openlocfilehash: c91f46ff45dd50f638cdb4f256fb93f2d33781ec
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118555"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a><span data-ttu-id="332d1-104">Gestione delle route delle aree di rete in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="332d1-104">Managing network region routes in Skype for Business Server</span></span>

<span data-ttu-id="332d1-105">Una *route area di rete* definisce la route tra una coppia di aree di rete.</span><span class="sxs-lookup"><span data-stu-id="332d1-105">A *network region route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="332d1-106">Ogni coppia di aree di rete nella distribuzione del servizio Controllo di ammissione di chiamata richiede una route di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="332d1-106">Each pair of network regions in your call admission control deployment requires a network region route.</span></span> <span data-ttu-id="332d1-107">In tal modo ogni area di rete della distribuzione può accedere a tutte le altre aree.</span><span class="sxs-lookup"><span data-stu-id="332d1-107">This enables every network region within the deployment to access every other region.</span></span> <span data-ttu-id="332d1-108">Utilizzare le procedure descritte in questa procedura per visualizzare, creare, modificare o eliminare route dell'area di rete.</span><span class="sxs-lookup"><span data-stu-id="332d1-108">Use the procedures in this artilce to view, create, modify, or delete network region routes.</span></span>

## <a name="view-network-region-route-information"></a><span data-ttu-id="332d1-109">Visualizzare le informazioni sulle route dell'area di rete</span><span class="sxs-lookup"><span data-stu-id="332d1-109">View network region route information</span></span> 

<span data-ttu-id="332d1-110">Ogni area di una configurazione di controllo di ammissione di chiamata deve in qualche modo poter accedere a tutte le altre aree.</span><span class="sxs-lookup"><span data-stu-id="332d1-110">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="332d1-111">Mentre i collegamenti area impostano limitazioni della larghezza di banda nelle connessioni tra aree e rappresentano anche i collegamenti fisici, una route determina il percorso collegato che verrà attraversato dalla connessione per passare da un'area all'altra.</span><span class="sxs-lookup"><span data-stu-id="332d1-111">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="332d1-112">Utilizzare le procedure seguenti per visualizzare le route dell'area di rete esistenti nel Pannello di controllo di Skype for Business Server o In Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="332d1-112">Use the following procedures to view existing network region routes in Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="332d1-113">Per visualizzare le informazioni sulla route dell'area di rete nel Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="332d1-113">To view network region route information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="332d1-114">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="332d1-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="332d1-115">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="332d1-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="332d1-116">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Route **area.**</span><span class="sxs-lookup"><span data-stu-id="332d1-116">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="332d1-117">Nella pagina **Route area** fare clic sulla route area che si vuole visualizzare.</span><span class="sxs-lookup"><span data-stu-id="332d1-117">On the **Region Route** page, click the region route that you want to view.</span></span>


    > [!NOTE]  
    > <span data-ttu-id="332d1-118">È possibile visualizzare una sola route area per volta.</span><span class="sxs-lookup"><span data-stu-id="332d1-118">You can only view one region route at a time.</span></span>


5.  <span data-ttu-id="332d1-119">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="332d1-119">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="332d1-120">Visualizzazione delle informazioni sulle route dell'area di rete tramite Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="332d1-120">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="332d1-121">Le informazioni sulla route dell'area di rete possono essere visualizzate Windows PowerShell e il cmdlet Get-CsNetworkInterRegionRoute rete.</span><span class="sxs-lookup"><span data-stu-id="332d1-121">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="332d1-122">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="332d1-122">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-route-information"></a><span data-ttu-id="332d1-123">Per visualizzare le informazioni sulle route dell'area di rete</span><span class="sxs-lookup"><span data-stu-id="332d1-123">To view network region route information</span></span>

  - <span data-ttu-id="332d1-124">Per visualizzare informazioni su tutte le route dell'area di rete, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="332d1-124">To view information about all your network region routes, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="332d1-125">Verranno restituite informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="332d1-125">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

<span data-ttu-id="332d1-126">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsNetworkInterRegionRoute](/powershell/module/skype/Get-CsNetworkInterRegionRoute).</span><span class="sxs-lookup"><span data-stu-id="332d1-126">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>


## <a name="create-or-modify-network-region-routes"></a><span data-ttu-id="332d1-127">Creare o modificare route area di rete</span><span class="sxs-lookup"><span data-stu-id="332d1-127">Create or modify network region routes</span></span>

<span data-ttu-id="332d1-128">Ogni area di una configurazione di controllo di ammissione di chiamata deve in qualche modo poter accedere a tutte le altre aree.</span><span class="sxs-lookup"><span data-stu-id="332d1-128">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="332d1-129">Mentre i collegamenti area impostano limitazioni della larghezza di banda nelle connessioni tra aree e rappresentano anche i collegamenti fisici, una route determina il percorso collegato che verrà attraversato dalla connessione per passare da un'area all'altra.</span><span class="sxs-lookup"><span data-stu-id="332d1-129">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="332d1-130">Puoi usare il Pannello di controllo di Skype for Business Server per configurare le route dell'area di rete.</span><span class="sxs-lookup"><span data-stu-id="332d1-130">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="332d1-131">Dal Pannello di controllo di Skype for Business Server puoi creare, modificare o eliminare una route dell'area di rete.</span><span class="sxs-lookup"><span data-stu-id="332d1-131">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="332d1-132">Utilizzare questo argomento per creare o modificare una nuova route area di rete.</span><span class="sxs-lookup"><span data-stu-id="332d1-132">Use this topic to create or modify a network region route.</span></span> 

### <a name="to-create-a-network-region-route"></a><span data-ttu-id="332d1-133">Per creare una route area di rete</span><span class="sxs-lookup"><span data-stu-id="332d1-133">To create a network region route</span></span>

1.  <span data-ttu-id="332d1-134">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="332d1-134">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="332d1-135">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="332d1-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="332d1-136">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Route **area.**</span><span class="sxs-lookup"><span data-stu-id="332d1-136">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="332d1-137">Nella pagina **Route area** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="332d1-137">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="332d1-138">In **Nuova route area** digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="332d1-138">In **New Region Route**, type a value in the **Name** field.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="332d1-139">Questo valore deve essere univoco all'interno della distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="332d1-139">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="332d1-140">Nell'elenco a discesa Area di rete **\# 1** selezionare una delle due aree da collegare tramite questa route.</span><span class="sxs-lookup"><span data-stu-id="332d1-140">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="332d1-141">Nell'elenco a discesa Area di rete **\# 2** selezionare l'altra area per la route.</span><span class="sxs-lookup"><span data-stu-id="332d1-141">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="332d1-142">Questa area deve essere diversa dall'area selezionata per Area di rete \# 1.</span><span class="sxs-lookup"><span data-stu-id="332d1-142">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="332d1-p107">Utilizzare la casella di riepilogo **Collegamenti aree di rete** per aggiungere collegamenti area di rete alla route. Fare clic sul pulsante **Aggiungi** per visualizzare la pagina **Collegamento area**. Fare clic su un collegamento area da aggiungere alla route e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="332d1-p107">Use the **Network region links** list box to add region links to the route. Click the **Add** button to display the **Region Link** page. Click a region link to add to this route, and then click **OK**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="332d1-146">Continuare a fare clic sul pulsante **Aggiungi** per aggiungere altri collegamenti oppure selezionare un collegamento e fare clic su **Rimuovi** per rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="332d1-146">Continue to click the **Add** button to add more links, or select a link and click **Remove** to remove a link.</span></span>

9.  <span data-ttu-id="332d1-147">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="332d1-147">Click **Commit**.</span></span>


### <a name="to-modify-a-network-region-route"></a><span data-ttu-id="332d1-148">Per modificare una route area di rete</span><span class="sxs-lookup"><span data-stu-id="332d1-148">To modify a network region route</span></span>

1.  <span data-ttu-id="332d1-149">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="332d1-149">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="332d1-150">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="332d1-150">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="332d1-151">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Route **area.**</span><span class="sxs-lookup"><span data-stu-id="332d1-151">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="332d1-152">Nella pagina **Route area** fare clic sulla route area che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="332d1-152">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="332d1-153">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="332d1-153">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="332d1-154">In **Modifica route area** è possibile modificare le aree unite dalla route e i collegamenti area associati alla route.</span><span class="sxs-lookup"><span data-stu-id="332d1-154">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="332d1-155">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="332d1-155">Click **Commit**.</span></span>


## <a name="delete-existing-network-region-routes"></a><span data-ttu-id="332d1-156">Eliminare route area di rete esistenti</span><span class="sxs-lookup"><span data-stu-id="332d1-156">Delete existing network region routes</span></span>

<span data-ttu-id="332d1-157">Ogni area di una configurazione di controllo di ammissione di chiamata deve in qualche modo poter accedere a tutte le altre aree.</span><span class="sxs-lookup"><span data-stu-id="332d1-157">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="332d1-158">Mentre i collegamenti area impostano limitazioni della larghezza di banda nelle connessioni tra aree e rappresentano anche i collegamenti fisici, una route determina il percorso collegato che verrà attraversato dalla connessione per passare da un'area all'altra.</span><span class="sxs-lookup"><span data-stu-id="332d1-158">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="332d1-159">Puoi usare il Pannello di controllo di Skype for Business Server per configurare le route dell'area di rete.</span><span class="sxs-lookup"><span data-stu-id="332d1-159">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="332d1-160">Dal Pannello di controllo di Skype for Business Server puoi creare, modificare o eliminare una route dell'area di rete.</span><span class="sxs-lookup"><span data-stu-id="332d1-160">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="332d1-161">Utilizzare questo argomento per informazioni su come eliminare le route area di rete.</span><span class="sxs-lookup"><span data-stu-id="332d1-161">Use this topic to delete existing network region routes.</span></span> 

### <a name="to-delete-a-network-region-route"></a><span data-ttu-id="332d1-162">Per eliminare una route area di rete</span><span class="sxs-lookup"><span data-stu-id="332d1-162">To delete a network region route</span></span>

1.  <span data-ttu-id="332d1-163">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="332d1-163">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="332d1-164">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="332d1-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="332d1-165">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su Route **area.**</span><span class="sxs-lookup"><span data-stu-id="332d1-165">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="332d1-166">Nella pagina **Route area** fare clic sulla route area che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="332d1-166">On the **Region Route** page, click the region route that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="332d1-p109">È possibile eliminare più di una route area per volta. A tale scopo, selezionare più route area tenendo premuto CTRL oppure, per selezionare tutte le route area, scegliere **Seleziona tutto** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="332d1-p109">You can delete more than one region route at a time. To do this, press CTRL and select multiple region routes while holding down the CTRL key. Or, to select all region routes, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="332d1-170">Scegliere **Elimina** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="332d1-170">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="332d1-171">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="332d1-171">Click **OK**.</span></span>



## <a name="see-also"></a><span data-ttu-id="332d1-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="332d1-172">See Also</span></span>

[<span data-ttu-id="332d1-173">Gestione delle aree di rete in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="332d1-173">Managing network regions in Skype for Business Server</span></span>](managing-network-regions.md)

[<span data-ttu-id="332d1-174">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="332d1-174">New-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[<span data-ttu-id="332d1-175">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="332d1-175">Set-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[<span data-ttu-id="332d1-176">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="332d1-176">Remove-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[<span data-ttu-id="332d1-177">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="332d1-177">Get-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/Get-CsNetworkInterRegionRoute)