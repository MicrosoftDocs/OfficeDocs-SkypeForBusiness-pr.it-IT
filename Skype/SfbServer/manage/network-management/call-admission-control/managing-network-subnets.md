---
title: Gestione delle subnet di rete
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nella maggior parte delle distribuzioni di Skype for Business Server in cui viene implementato il controllo di ammissione di chiamata (CAC), in genere ci sarà un numero elevato di subnet. Per questo motivo, è spesso consigliabile configurare subnet da Skype for Business Server Management Shell.
ms.openlocfilehash: 354dd43fd526ba2a6c6f88c8e1f30d0aae37b3bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188558"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="370b5-104">Gestione delle subnet di rete in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="370b5-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="370b5-105">Puoi usare il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell per gestire le subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="370b5-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="370b5-106">Nella maggior parte delle distribuzioni di Skype for Business Server in cui viene implementato il controllo di ammissione di chiamata (CAC), in genere ci sarà un numero elevato di subnet.</span><span class="sxs-lookup"><span data-stu-id="370b5-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="370b5-107">Per questo motivo, è spesso consigliabile configurare subnet da Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="370b5-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="370b5-108">Usare le sezioni di questo articolo per visualizzare le informazioni sulla subnet di rete o per creare, modificare o eliminare subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="370b5-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="370b5-109">Visualizzare le informazioni sulla subnet di rete</span><span class="sxs-lookup"><span data-stu-id="370b5-109">View network subnet information</span></span> 

<span data-ttu-id="370b5-110">Per visualizzare una subnet di rete, è possibile usare la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="370b5-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="370b5-111">Dal pannello di controllo di Skype for Business Server è possibile creare, modificare o eliminare una subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="370b5-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="370b5-112">Per visualizzare una subnet di rete</span><span class="sxs-lookup"><span data-stu-id="370b5-112">To view a network subnet</span></span>

1.  <span data-ttu-id="370b5-113">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="370b5-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="370b5-114">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="370b5-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="370b5-115">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi fare clic su **Subnet**.</span><span class="sxs-lookup"><span data-stu-id="370b5-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="370b5-116">Nella pagina **subnet** fare clic sulla subnet che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="370b5-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="370b5-117">È possibile visualizzare una sola subnet alla volta.</span><span class="sxs-lookup"><span data-stu-id="370b5-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="370b5-118">Nel menu **modifica** fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="370b5-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="370b5-119">Visualizzare le informazioni di configurazione della subnet di rete usando i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="370b5-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="370b5-120">Le informazioni sulla subnet di rete possono essere visualizzate usando Windows PowerShell e il cmdlet Get-CsNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="370b5-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="370b5-121">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="370b5-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="370b5-122">Per visualizzare le informazioni sulla subnet di rete</span><span class="sxs-lookup"><span data-stu-id="370b5-122">To view network subnet information</span></span>

  - <span data-ttu-id="370b5-123">Per visualizzare informazioni su tutte le subnet di rete, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="370b5-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="370b5-124">Questo restituirà informazioni simili alla seguente:</span><span class="sxs-lookup"><span data-stu-id="370b5-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="370b5-125">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) .</span><span class="sxs-lookup"><span data-stu-id="370b5-125">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="370b5-126">Creare o modificare subnet di rete</span><span class="sxs-lookup"><span data-stu-id="370b5-126">Create or modify network subnets</span></span> 

<span data-ttu-id="370b5-127">Una subnet di rete deve essere associata a un sito di rete allo scopo di determinare la posizione geografica dell'host appartenente alla subnet.</span><span class="sxs-lookup"><span data-stu-id="370b5-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="370b5-128">Puoi usare il pannello di controllo di Skype for Business Server per configurare le subnet.</span><span class="sxs-lookup"><span data-stu-id="370b5-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="370b5-129">Dal pannello di controllo di Skype for Business Server è possibile creare, modificare o eliminare una subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="370b5-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="370b5-130">Nella maggior parte delle distribuzioni di Skype for Business Server in cui viene implementato il controllo di ammissione di chiamata (CAC), in genere ci sarà un numero elevato di subnet.</span><span class="sxs-lookup"><span data-stu-id="370b5-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="370b5-131">Per questo motivo, è spesso consigliabile configurare subnet da Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="370b5-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="370b5-132">Da lì è possibile chiamare **New-CsNetworkSubnet** in combinazione con il cmdlet di Windows PowerShell **Import-CSV**.</span><span class="sxs-lookup"><span data-stu-id="370b5-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="370b5-133">Usando questi cmdlet insieme, è possibile leggere le impostazioni della subnet da un file con valori delimitati da virgole (CSV) e creare più subnet contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="370b5-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="370b5-134">Per esempi su come creare subnet da un file CSV, vedere [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="370b5-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="370b5-135">Per creare una subnet di rete</span><span class="sxs-lookup"><span data-stu-id="370b5-135">To create a network subnet</span></span>

1.  <span data-ttu-id="370b5-136">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="370b5-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="370b5-137">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="370b5-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="370b5-138">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi fare clic su **Subnet**.</span><span class="sxs-lookup"><span data-stu-id="370b5-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="370b5-139">Nella pagina **subnet** fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="370b5-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="370b5-140">Nella **nuova subnet**immettere un valore nel campo **ID Subnet** .</span><span class="sxs-lookup"><span data-stu-id="370b5-140">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="370b5-141">Deve essere un indirizzo IP, ad esempio 174.11.12.0, e deve essere il primo indirizzo nell'intervallo di indirizzi IP definito dalla subnet.</span><span class="sxs-lookup"><span data-stu-id="370b5-141">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="370b5-142">Nel campo **maschera** immettere un valore numerico compreso tra 1 e 32.</span><span class="sxs-lookup"><span data-stu-id="370b5-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="370b5-143">Questo valore è la maschera di maschere che deve essere applicata alla subnet da creare.</span><span class="sxs-lookup"><span data-stu-id="370b5-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="370b5-144">In **ID sito di rete**selezionare il sito a cui appartiene la subnet.</span><span class="sxs-lookup"><span data-stu-id="370b5-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="370b5-145">Opzionale Digitare un valore nel campo **Description** per ottenere altre informazioni su questa subnet che non può essere espressa solo dal nome.</span><span class="sxs-lookup"><span data-stu-id="370b5-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="370b5-146">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="370b5-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="370b5-147">Per modificare una subnet di rete</span><span class="sxs-lookup"><span data-stu-id="370b5-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="370b5-148">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="370b5-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="370b5-149">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="370b5-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="370b5-150">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi fare clic su **Subnet**.</span><span class="sxs-lookup"><span data-stu-id="370b5-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="370b5-151">Nella pagina **subnet** fare clic sulla subnet che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="370b5-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="370b5-152">Nel menu **modifica** fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="370b5-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="370b5-153">Nella pagina **modifica subnet** è possibile modificare la maschera di posizione, il sito di rete associato o la descrizione.</span><span class="sxs-lookup"><span data-stu-id="370b5-153">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="370b5-154">Se modifichi la maschera di base, tieni presente che l'ID subnet deve essere il primo indirizzo nell'intervallo di indirizzi IP definito dalla subnet.</span><span class="sxs-lookup"><span data-stu-id="370b5-154">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="370b5-155">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="370b5-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="370b5-156">Eliminare subnet di rete</span><span class="sxs-lookup"><span data-stu-id="370b5-156">Delete network subnets</span></span>

<span data-ttu-id="370b5-157">Per eliminare una subnet, è possibile usare la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="370b5-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="370b5-158">Dal pannello di controllo di Skype for Business Server è possibile creare, modificare o eliminare una subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="370b5-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="370b5-159">Nella maggior parte delle distribuzioni di Skype for Business Server in cui viene implementato il controllo di ammissione di chiamata (CAC), in genere ci sarà un numero elevato di subnet.</span><span class="sxs-lookup"><span data-stu-id="370b5-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="370b5-160">Per questo motivo, è spesso consigliabile configurare subnet da Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="370b5-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="370b5-161">Da lì è possibile chiamare **New-CsNetworkSubnet** in combinazione con il cmdlet di Windows PowerShell **Import-CSV**.</span><span class="sxs-lookup"><span data-stu-id="370b5-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="370b5-162">Usando questi cmdlet insieme, è possibile leggere le impostazioni della subnet da un file con valori delimitati da virgole (CSV) e creare più subnet contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="370b5-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="370b5-163">Per esempi su come creare subnet da un file CSV, vedere [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="370b5-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="370b5-164">Per eliminare una subnet di rete</span><span class="sxs-lookup"><span data-stu-id="370b5-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="370b5-165">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="370b5-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="370b5-166">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="370b5-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="370b5-167">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi fare clic su **Subnet**.</span><span class="sxs-lookup"><span data-stu-id="370b5-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="370b5-168">Nella pagina **subnet** fare clic sulla subnet che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="370b5-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="370b5-169">Puoi eliminare più di una subnet alla volta.</span><span class="sxs-lookup"><span data-stu-id="370b5-169">You can delete more than one subnet at a time.</span></span> <span data-ttu-id="370b5-170">A questo scopo, premere CTRL e selezionare più subnet tenendo premuto CTRL.</span><span class="sxs-lookup"><span data-stu-id="370b5-170">To do this, press CTRL and select multiple subnets while holding down the CTRL key.</span></span> <span data-ttu-id="370b5-171">In alternativa, per selezionare tutte le subnet, fare clic su **Seleziona tutto** dal menu **modifica** .</span><span class="sxs-lookup"><span data-stu-id="370b5-171">Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="370b5-172">Scegliere **Elimina**dal menu **modifica** .</span><span class="sxs-lookup"><span data-stu-id="370b5-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="370b5-173">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="370b5-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="370b5-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="370b5-174">See Also</span></span>

[<span data-ttu-id="370b5-175">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="370b5-175">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="370b5-176">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="370b5-176">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="370b5-177">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="370b5-177">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="370b5-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="370b5-178">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
