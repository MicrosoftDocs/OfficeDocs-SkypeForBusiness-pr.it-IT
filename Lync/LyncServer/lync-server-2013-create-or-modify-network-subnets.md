---
title: 'Lync Server 2013: creare o modificare le subnet di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e7d5822438b1907cf718e2ea0365d9e9dad0814
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501663"
---
# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a><span data-ttu-id="5fa2f-102">Creare o modificare le subnet di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fa2f-102">Create or modify network subnets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fa2f-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="5fa2f-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="5fa2f-104">Una subnet di rete deve essere associata a un sito di rete per la determinazione della posizione geografica dell'host appartenente alla subnet.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-104">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="5fa2f-105">È possibile utilizzare il pannello di controllo di Lync Server per configurare le subnet.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-105">You can use Lync Server Control Panel to configure subnets.</span></span> <span data-ttu-id="5fa2f-106">Dal pannello di controllo di Lync Server, è possibile creare, modificare o eliminare una subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-106">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="5fa2f-107">Per informazioni dettagliate sull'eliminazione delle subnet di rete, vedere [eliminazione di subnet di rete in Lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="5fa2f-107">For details about deleting network subnets, see [Deleting network subnets in Lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span></span>

<span data-ttu-id="5fa2f-108">Nella maggior parte delle distribuzioni di Microsoft Lync Server 2013 in cui è implementato il controllo di ammissione di chiamata (CAC), in genere vi sarà un numero elevato di subnet.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-108">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="5fa2f-109">Per questo motivo, è spesso preferibile configurare le subnet da Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-109">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="5fa2f-110">Da questa pagina è possibile chiamare **New-CsNetworkSubnet** in combinazione con il cmdlet **Import-CSV**di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-110">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="5fa2f-111">Se si utilizzano questi cmdlet insieme, è possibile leggere le impostazioni della subnet da un file con valori delimitati da virgole (con estensione CSV) e creare più subnet contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-111">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="5fa2f-112">Per esempi su come creare subnet da un file CSV, vedere [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="5fa2f-112">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-create-a-network-subnet"></a><span data-ttu-id="5fa2f-113">Per creare una subnet di rete</span><span class="sxs-lookup"><span data-stu-id="5fa2f-113">To create a network subnet</span></span>

1.  <span data-ttu-id="5fa2f-114">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5fa2f-115">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5fa2f-116">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5fa2f-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5fa2f-117">Nella barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Subnet**.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-117">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="5fa2f-118">Nella pagina **Subnet** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-118">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="5fa2f-p104">In **Nuova subnet** immettere un valore nel campo **ID subnet**. Questo valore deve essere il primo indirizzo IP (ad esempio, 174.11.12.0) dell'intervallo di indirizzi IP definito dalla subnet.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-p104">In **New Subnet**, enter a value in the **Subnet ID** field. This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="5fa2f-121">Nel campo **Maschera** immettere un valore numerico compreso tra 1 e 32.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-121">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5fa2f-122">Questo valore corrisponde alla maschera di bit da applicare alla subnet da creare.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-122">This value is the bitmask that is to be applied to the subnet being created.</span></span>

    
    </div>

7.  <span data-ttu-id="5fa2f-123">In **ID sito di rete** selezionare il sito a cui appartiene la subnet.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-123">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="5fa2f-124">(Facoltativo) Digitare un valore nel campo **Descrizione** per fornire ulteriori informazioni sulla subnet che non possono essere espresse dal solo nome.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-124">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="5fa2f-125">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-subnet"></a><span data-ttu-id="5fa2f-126">Per modificare una subnet di rete</span><span class="sxs-lookup"><span data-stu-id="5fa2f-126">To modify a network subnet</span></span>

1.  <span data-ttu-id="5fa2f-127">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5fa2f-128">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5fa2f-129">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5fa2f-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5fa2f-130">Nella barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Subnet**.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-130">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="5fa2f-131">Nella pagina **Subnet** fare clic sulla subnet che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-131">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="5fa2f-132">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-132">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="5fa2f-p106">Nella pagina **Modifica Subnet** è possibile modificare la maschera di bit, il sito di rete associato o la descrizione. Se si modifica la maschera di bit, tenere presente che l'ID subnet deve essere comunque il primo indirizzo IP dell'intervallo di indirizzi IP definito dalla subnet.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-p106">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description. If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="5fa2f-135">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="5fa2f-135">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5fa2f-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5fa2f-136">See Also</span></span>


[<span data-ttu-id="5fa2f-137">Eliminazione di subnet di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fa2f-137">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  


[<span data-ttu-id="5fa2f-138">Informazioni su aree di rete, siti e subnet in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fa2f-138">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[<span data-ttu-id="5fa2f-139">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="5fa2f-139">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[<span data-ttu-id="5fa2f-140">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="5fa2f-140">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[<span data-ttu-id="5fa2f-141">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="5fa2f-141">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[<span data-ttu-id="5fa2f-142">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="5fa2f-142">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

