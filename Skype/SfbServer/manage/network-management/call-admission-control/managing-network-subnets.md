---
title: Gestione delle subnet di rete
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
description: Nella maggior parte delle distribuzioni di Skype for Business Server in cui è implementato il controllo di ammissione di chiamata, in genere è presente un numero elevato di subnet. Per questo, spesso è meglio configurare le subnet da Skype for Business Server Management Shell.
ms.openlocfilehash: ef771ad78f00085374038203e1049790a9179e88
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122440"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="78b0c-104">Gestione delle subnet di rete in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="78b0c-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="78b0c-105">Puoi usare il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell per gestire le subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="78b0c-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="78b0c-106">Nella maggior parte delle distribuzioni di Skype for Business Server in cui è implementato il controllo di ammissione di chiamata, in genere è presente un numero elevato di subnet.</span><span class="sxs-lookup"><span data-stu-id="78b0c-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="78b0c-107">Per questo, spesso è meglio configurare le subnet da Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="78b0c-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="78b0c-108">Utilizzare le sezioni di questo articolo per visualizzare le informazioni sulle subnet di rete o per creare, modificare o eliminare subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="78b0c-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="78b0c-109">Visualizzare le informazioni sulla subnet di rete</span><span class="sxs-lookup"><span data-stu-id="78b0c-109">View network subnet information</span></span> 

<span data-ttu-id="78b0c-110">Per visualizzare una subnet di rete è possibile attenersi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="78b0c-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="78b0c-111">Dal Pannello di controllo di Skype for Business Server puoi creare, modificare o eliminare una subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="78b0c-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="78b0c-112">Per visualizzare una subnet di rete</span><span class="sxs-lookup"><span data-stu-id="78b0c-112">To view a network subnet</span></span>

1.  <span data-ttu-id="78b0c-113">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="78b0c-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="78b0c-114">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="78b0c-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="78b0c-115">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Subnet.**</span><span class="sxs-lookup"><span data-stu-id="78b0c-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="78b0c-116">Nella pagina **Subnet** fare clic sulla subnet che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="78b0c-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="78b0c-117">È possibile visualizzare una sola subnet alla volta.</span><span class="sxs-lookup"><span data-stu-id="78b0c-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="78b0c-118">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="78b0c-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="78b0c-119">Visualizzare le informazioni sulla configurazione della subnet di rete utilizzando Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="78b0c-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="78b0c-120">Le informazioni sulla subnet di rete possono essere visualizzate utilizzando Windows PowerShell e il cmdlet Get-CsNetworkSubnet rete.</span><span class="sxs-lookup"><span data-stu-id="78b0c-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="78b0c-121">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78b0c-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="78b0c-122">Per visualizzare le informazioni sulla subnet di rete</span><span class="sxs-lookup"><span data-stu-id="78b0c-122">To view network subnet information</span></span>

  - <span data-ttu-id="78b0c-123">Per visualizzare informazioni su tutte le subnet di rete, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="78b0c-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="78b0c-124">Verranno restituite informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="78b0c-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="78b0c-125">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsNetworkSubnet](/powershell/module/skype/Get-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="78b0c-125">For more information, see the help topic for the [Get-CsNetworkSubnet](/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="78b0c-126">Creare o modificare subnet di rete</span><span class="sxs-lookup"><span data-stu-id="78b0c-126">Create or modify network subnets</span></span> 

<span data-ttu-id="78b0c-127">Una subnet di rete deve essere associata a un sito di rete per la determinazione della posizione geografica dell'host appartenente alla subnet.</span><span class="sxs-lookup"><span data-stu-id="78b0c-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="78b0c-128">È possibile utilizzare il Pannello di controllo di Skype for Business Server per configurare le subnet.</span><span class="sxs-lookup"><span data-stu-id="78b0c-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="78b0c-129">Dal Pannello di controllo di Skype for Business Server puoi creare, modificare o eliminare una subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="78b0c-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="78b0c-130">Nella maggior parte delle distribuzioni di Skype for Business Server in cui è implementato il controllo di ammissione di chiamata, in genere è presente un numero elevato di subnet.</span><span class="sxs-lookup"><span data-stu-id="78b0c-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="78b0c-131">Per questo, spesso è meglio configurare le subnet da Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="78b0c-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="78b0c-132">Da qui è possibile chiamare **New-CsNetworkSubnet** in combinazione con il cmdlet **Windows PowerShell Import-CSV**.</span><span class="sxs-lookup"><span data-stu-id="78b0c-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="78b0c-133">Utilizzando questi cmdlet insieme, è possibile leggere le impostazioni della subnet da un file con valori delimitati da virgole (csv) e creare più subnet contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="78b0c-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="78b0c-134">Per esempi su come creare subnet da un file CSV, vedere [New-CsNetworkSubnet.](/powershell/module/skype/New-CsNetworkSubnet)</span><span class="sxs-lookup"><span data-stu-id="78b0c-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="78b0c-135">Per creare una subnet di rete</span><span class="sxs-lookup"><span data-stu-id="78b0c-135">To create a network subnet</span></span>

1.  <span data-ttu-id="78b0c-136">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="78b0c-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="78b0c-137">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="78b0c-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="78b0c-138">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Subnet.**</span><span class="sxs-lookup"><span data-stu-id="78b0c-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="78b0c-139">Nella pagina **Subnet** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="78b0c-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="78b0c-p107">In **Nuova subnet** immettere un valore nel campo **ID subnet**. Questo valore deve essere il primo indirizzo IP (ad esempio, 174.11.12.0) dell'intervallo di indirizzi IP definito dalla subnet.</span><span class="sxs-lookup"><span data-stu-id="78b0c-p107">In **New Subnet**, enter a value in the **Subnet ID** field. This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="78b0c-142">Nel campo **Maschera** immettere un valore numerico compreso tra 1 e 32.</span><span class="sxs-lookup"><span data-stu-id="78b0c-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="78b0c-143">Questo valore corrisponde alla maschera di bit da applicare alla subnet da creare.</span><span class="sxs-lookup"><span data-stu-id="78b0c-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="78b0c-144">In **ID sito di rete** selezionare il sito a cui appartiene la subnet.</span><span class="sxs-lookup"><span data-stu-id="78b0c-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="78b0c-145">(Facoltativo) Digitare un valore nel campo **Descrizione** per fornire ulteriori informazioni sulla subnet che non possono essere espresse dal solo nome.</span><span class="sxs-lookup"><span data-stu-id="78b0c-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="78b0c-146">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="78b0c-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="78b0c-147">Per modificare una subnet di rete</span><span class="sxs-lookup"><span data-stu-id="78b0c-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="78b0c-148">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="78b0c-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="78b0c-149">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="78b0c-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="78b0c-150">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Subnet.**</span><span class="sxs-lookup"><span data-stu-id="78b0c-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="78b0c-151">Nella pagina **Subnet** fare clic sulla subnet che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="78b0c-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="78b0c-152">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="78b0c-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="78b0c-p108">Nella pagina **Modifica Subnet** è possibile modificare la maschera di bit, il sito di rete associato o la descrizione. Se si modifica la maschera di bit, tenere presente che l'ID subnet deve essere comunque il primo indirizzo IP dell'intervallo di indirizzi IP definito dalla subnet.</span><span class="sxs-lookup"><span data-stu-id="78b0c-p108">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description. If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="78b0c-155">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="78b0c-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="78b0c-156">Eliminare subnet di rete</span><span class="sxs-lookup"><span data-stu-id="78b0c-156">Delete network subnets</span></span>

<span data-ttu-id="78b0c-157">È possibile utilizzare la procedura seguente per eliminare una subnet.</span><span class="sxs-lookup"><span data-stu-id="78b0c-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="78b0c-158">Dal Pannello di controllo di Skype for Business Server puoi creare, modificare o eliminare una subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="78b0c-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="78b0c-159">Nella maggior parte delle distribuzioni di Skype for Business Server in cui è implementato il controllo di ammissione di chiamata, in genere è presente un numero elevato di subnet.</span><span class="sxs-lookup"><span data-stu-id="78b0c-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="78b0c-160">Per questo, spesso è meglio configurare le subnet da Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="78b0c-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="78b0c-161">Da qui è possibile chiamare **New-CsNetworkSubnet** in combinazione con il cmdlet **Windows PowerShell Import-CSV**.</span><span class="sxs-lookup"><span data-stu-id="78b0c-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="78b0c-162">Utilizzando questi cmdlet insieme, è possibile leggere le impostazioni della subnet da un file con valori delimitati da virgole (csv) e creare più subnet contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="78b0c-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="78b0c-163">Per esempi su come creare subnet da un file CSV, vedere [New-CsNetworkSubnet.](/powershell/module/skype/New-CsNetworkSubnet)</span><span class="sxs-lookup"><span data-stu-id="78b0c-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="78b0c-164">Per eliminare una subnet di rete</span><span class="sxs-lookup"><span data-stu-id="78b0c-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="78b0c-165">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="78b0c-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="78b0c-166">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="78b0c-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="78b0c-167">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Subnet.**</span><span class="sxs-lookup"><span data-stu-id="78b0c-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="78b0c-168">Nella pagina **Subnet** fare clic sulla subnet che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="78b0c-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="78b0c-p111">È possibile eliminare più subnet contemporaneamente. A tale scopo, tenere premuto CTRL e selezionare le diverse subnet. In alternativa, per selezionare tutte le subnet, scegliere **Seleziona tutto** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="78b0c-p111">You can delete more than one subnet at a time. To do this, press CTRL and select multiple subnets while holding down the CTRL key. Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="78b0c-172">Scegliere **Elimina** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="78b0c-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="78b0c-173">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="78b0c-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="78b0c-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78b0c-174">See Also</span></span>

[<span data-ttu-id="78b0c-175">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="78b0c-175">New-CsNetworkSubnet</span></span>](/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="78b0c-176">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="78b0c-176">Set-CsNetworkSubnet</span></span>](/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="78b0c-177">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="78b0c-177">Remove-CsNetworkSubnet</span></span>](/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="78b0c-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="78b0c-178">Get-CsNetworkSubnet</span></span>](/powershell/module/skype/Get-CsNetworkSubnet)