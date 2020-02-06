---
title: Gestione delle subnet di rete
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
description: Nella maggior parte delle distribuzioni di Skype for Business Server in cui viene implementato il controllo di ammissione di chiamata (CAC), in genere ci sarà un numero elevato di subnet. Per questo motivo, è spesso consigliabile configurare subnet da Skype for Business Server Management Shell.
ms.openlocfilehash: fd7d71b3971b176939967830ca3e071ef4c77dbf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817465"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="d8683-104">Gestione delle subnet di rete in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d8683-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="d8683-105">Puoi usare il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell per gestire le subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="d8683-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="d8683-106">Nella maggior parte delle distribuzioni di Skype for Business Server in cui viene implementato il controllo di ammissione di chiamata (CAC), in genere ci sarà un numero elevato di subnet.</span><span class="sxs-lookup"><span data-stu-id="d8683-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="d8683-107">Per questo motivo, è spesso consigliabile configurare subnet da Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d8683-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="d8683-108">Usare le sezioni di questo articolo per visualizzare le informazioni sulla subnet di rete o per creare, modificare o eliminare subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="d8683-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="d8683-109">Visualizzare le informazioni sulla subnet di rete</span><span class="sxs-lookup"><span data-stu-id="d8683-109">View network subnet information</span></span> 

<span data-ttu-id="d8683-110">Per visualizzare una subnet di rete, è possibile usare la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="d8683-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="d8683-111">Dal pannello di controllo di Skype for Business Server è possibile creare, modificare o eliminare una subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="d8683-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="d8683-112">Per visualizzare una subnet di rete</span><span class="sxs-lookup"><span data-stu-id="d8683-112">To view a network subnet</span></span>

1.  <span data-ttu-id="d8683-113">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="d8683-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d8683-114">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d8683-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="d8683-115">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi fare clic su **Subnet**.</span><span class="sxs-lookup"><span data-stu-id="d8683-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="d8683-116">Nella pagina **subnet** fare clic sulla subnet che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="d8683-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="d8683-117">È possibile visualizzare una sola subnet alla volta.</span><span class="sxs-lookup"><span data-stu-id="d8683-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="d8683-118">Nel menu **modifica** fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="d8683-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d8683-119">Visualizzare le informazioni di configurazione della subnet di rete usando i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8683-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="d8683-120">Le informazioni sulla subnet di rete possono essere visualizzate usando Windows PowerShell e il cmdlet Get-CsNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="d8683-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="d8683-121">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8683-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="d8683-122">Per visualizzare le informazioni sulla subnet di rete</span><span class="sxs-lookup"><span data-stu-id="d8683-122">To view network subnet information</span></span>

  - <span data-ttu-id="d8683-123">Per visualizzare informazioni su tutte le subnet di rete, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="d8683-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="d8683-124">Questo restituirà informazioni simili alla seguente:</span><span class="sxs-lookup"><span data-stu-id="d8683-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="d8683-125">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) .</span><span class="sxs-lookup"><span data-stu-id="d8683-125">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="d8683-126">Creare o modificare subnet di rete</span><span class="sxs-lookup"><span data-stu-id="d8683-126">Create or modify network subnets</span></span> 

<span data-ttu-id="d8683-127">Una subnet di rete deve essere associata a un sito di rete allo scopo di determinare la posizione geografica dell'host appartenente alla subnet.</span><span class="sxs-lookup"><span data-stu-id="d8683-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="d8683-128">Puoi usare il pannello di controllo di Skype for Business Server per configurare le subnet.</span><span class="sxs-lookup"><span data-stu-id="d8683-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="d8683-129">Dal pannello di controllo di Skype for Business Server è possibile creare, modificare o eliminare una subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="d8683-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="d8683-130">Nella maggior parte delle distribuzioni di Skype for Business Server in cui viene implementato il controllo di ammissione di chiamata (CAC), in genere ci sarà un numero elevato di subnet.</span><span class="sxs-lookup"><span data-stu-id="d8683-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="d8683-131">Per questo motivo, è spesso consigliabile configurare subnet da Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d8683-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="d8683-132">Da lì è possibile chiamare **New-CsNetworkSubnet** in combinazione con il cmdlet di Windows PowerShell **Import-CSV**.</span><span class="sxs-lookup"><span data-stu-id="d8683-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="d8683-133">Usando questi cmdlet insieme, è possibile leggere le impostazioni della subnet da un file con valori delimitati da virgole (CSV) e creare più subnet contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="d8683-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="d8683-134">Per esempi su come creare subnet da un file CSV, vedere [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="d8683-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="d8683-135">Per creare una subnet di rete</span><span class="sxs-lookup"><span data-stu-id="d8683-135">To create a network subnet</span></span>

1.  <span data-ttu-id="d8683-136">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="d8683-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d8683-137">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d8683-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="d8683-138">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi fare clic su **Subnet**.</span><span class="sxs-lookup"><span data-stu-id="d8683-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="d8683-139">Nella pagina **subnet** fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="d8683-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="d8683-140">Nella **nuova subnet**immettere un valore nel campo **ID Subnet** .</span><span class="sxs-lookup"><span data-stu-id="d8683-140">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="d8683-141">Deve essere un indirizzo IP, ad esempio 174.11.12.0, e deve essere il primo indirizzo nell'intervallo di indirizzi IP definito dalla subnet.</span><span class="sxs-lookup"><span data-stu-id="d8683-141">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="d8683-142">Nel campo **maschera** immettere un valore numerico compreso tra 1 e 32.</span><span class="sxs-lookup"><span data-stu-id="d8683-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="d8683-143">Questo valore è la maschera di maschere che deve essere applicata alla subnet da creare.</span><span class="sxs-lookup"><span data-stu-id="d8683-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="d8683-144">In **ID sito di rete**selezionare il sito a cui appartiene la subnet.</span><span class="sxs-lookup"><span data-stu-id="d8683-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="d8683-145">Opzionale Digitare un valore nel campo **Description** per ottenere altre informazioni su questa subnet che non può essere espressa solo dal nome.</span><span class="sxs-lookup"><span data-stu-id="d8683-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="d8683-146">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="d8683-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="d8683-147">Per modificare una subnet di rete</span><span class="sxs-lookup"><span data-stu-id="d8683-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="d8683-148">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="d8683-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d8683-149">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d8683-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="d8683-150">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi fare clic su **Subnet**.</span><span class="sxs-lookup"><span data-stu-id="d8683-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="d8683-151">Nella pagina **subnet** fare clic sulla subnet che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="d8683-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="d8683-152">Nel menu **modifica** fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="d8683-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="d8683-153">Nella pagina **modifica subnet** è possibile modificare la maschera di posizione, il sito di rete associato o la descrizione.</span><span class="sxs-lookup"><span data-stu-id="d8683-153">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="d8683-154">Se modifichi la maschera di base, tieni presente che l'ID subnet deve essere il primo indirizzo nell'intervallo di indirizzi IP definito dalla subnet.</span><span class="sxs-lookup"><span data-stu-id="d8683-154">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="d8683-155">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="d8683-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="d8683-156">Eliminare subnet di rete</span><span class="sxs-lookup"><span data-stu-id="d8683-156">Delete network subnets</span></span>

<span data-ttu-id="d8683-157">Per eliminare una subnet, è possibile usare la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="d8683-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="d8683-158">Dal pannello di controllo di Skype for Business Server è possibile creare, modificare o eliminare una subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="d8683-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="d8683-159">Nella maggior parte delle distribuzioni di Skype for Business Server in cui viene implementato il controllo di ammissione di chiamata (CAC), in genere ci sarà un numero elevato di subnet.</span><span class="sxs-lookup"><span data-stu-id="d8683-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="d8683-160">Per questo motivo, è spesso consigliabile configurare subnet da Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d8683-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="d8683-161">Da lì è possibile chiamare **New-CsNetworkSubnet** in combinazione con il cmdlet di Windows PowerShell **Import-CSV**.</span><span class="sxs-lookup"><span data-stu-id="d8683-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="d8683-162">Usando questi cmdlet insieme, è possibile leggere le impostazioni della subnet da un file con valori delimitati da virgole (CSV) e creare più subnet contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="d8683-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="d8683-163">Per esempi su come creare subnet da un file CSV, vedere [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="d8683-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="d8683-164">Per eliminare una subnet di rete</span><span class="sxs-lookup"><span data-stu-id="d8683-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="d8683-165">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="d8683-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d8683-166">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d8683-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="d8683-167">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi fare clic su **Subnet**.</span><span class="sxs-lookup"><span data-stu-id="d8683-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="d8683-168">Nella pagina **subnet** fare clic sulla subnet che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="d8683-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="d8683-169">Puoi eliminare più di una subnet alla volta.</span><span class="sxs-lookup"><span data-stu-id="d8683-169">You can delete more than one subnet at a time.</span></span> <span data-ttu-id="d8683-170">A questo scopo, premere CTRL e selezionare più subnet tenendo premuto CTRL.</span><span class="sxs-lookup"><span data-stu-id="d8683-170">To do this, press CTRL and select multiple subnets while holding down the CTRL key.</span></span> <span data-ttu-id="d8683-171">In alternativa, per selezionare tutte le subnet, fare clic su **Seleziona tutto** dal menu **modifica** .</span><span class="sxs-lookup"><span data-stu-id="d8683-171">Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="d8683-172">Scegliere **Elimina**dal menu **modifica** .</span><span class="sxs-lookup"><span data-stu-id="d8683-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="d8683-173">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8683-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="d8683-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8683-174">See Also</span></span>

[<span data-ttu-id="d8683-175">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="d8683-175">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="d8683-176">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="d8683-176">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="d8683-177">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="d8683-177">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="d8683-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="d8683-178">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
