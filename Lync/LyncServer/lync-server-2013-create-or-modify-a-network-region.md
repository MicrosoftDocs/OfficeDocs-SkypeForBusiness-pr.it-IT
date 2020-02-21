---
title: "Lync Server 2013: creare o modificare un'area di rete"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network region
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412933(v=OCS.15)
ms:contentKeyID: 48185281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 417fece34f8e5177760e470083cd929cbddaab60
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a><span data-ttu-id="d868e-102">Creare o modificare un'area di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d868e-102">Create or modify a network region in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d868e-103">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="d868e-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="d868e-104">Le *aree di rete* sono gli hub di rete o gli backbone utilizzati nella configurazione del controllo di ammissione di chiamata, E9-1-1 e bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="d868e-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="d868e-105">Utilizzare le procedure seguenti per creare o modificare le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="d868e-105">Use the following procedures to create or modify network regions.</span></span> <span data-ttu-id="d868e-106">Ad esempio, se sono già state create aree di rete per una caratteristica vocale, non è necessario creare nuove aree di rete. altre funzionalità di VoIP aziendale avanzate utilizzeranno le stesse aree di rete.</span><span class="sxs-lookup"><span data-stu-id="d868e-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="d868e-107">Potrebbe tuttavia essere necessario modificare una definizione di area di rete esistente per applicare impostazioni specifiche della caratteristica.</span><span class="sxs-lookup"><span data-stu-id="d868e-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="d868e-108">Ad esempio, se sono state create aree di rete per il servizio E9-1-1 (che non richiede un sito centrale associato) e quindi si distribuisce il controllo di ammissione di chiamata, è necessario modificare le definizioni delle aree di rete per specificare un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="d868e-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="d868e-109">Per ulteriori informazioni, vedere [Configure Network Regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="d868e-109">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d868e-110">Tutti i requisiti specifici per particolari funzionalità per le definizioni delle aree di rete sono documentati negli argomenti relativi alla distribuzione per la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="d868e-110">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<span data-ttu-id="d868e-111">Per informazioni dettagliate sull'utilizzo delle aree di rete, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="d868e-111">For details about working with network regions, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="d868e-112">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="d868e-112">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [<span data-ttu-id="d868e-113">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="d868e-113">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="d868e-114">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="d868e-114">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [<span data-ttu-id="d868e-115">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="d868e-115">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a><span data-ttu-id="d868e-116">Creare un'area di rete</span><span class="sxs-lookup"><span data-stu-id="d868e-116">Create a Network Region</span></span>

<span data-ttu-id="d868e-117">Creare un'area di rete utilizzabile dal controllo di ammissione di chiamata, E9-1-1 o il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="d868e-117">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="d868e-118">Per creare un'area di rete utilizzando Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="d868e-118">To create a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="d868e-119">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d868e-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d868e-120">Eseguire il cmdlet New-CsNetworkRegion per creare le aree di rete:</span><span class="sxs-lookup"><span data-stu-id="d868e-120">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="d868e-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d868e-121">For example:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    <span data-ttu-id="d868e-122">Con questo esempio viene creata un'area di rete denominata “NorthAmerica” associata a un sito centrale con ID di sito CHICAGO.</span><span class="sxs-lookup"><span data-stu-id="d868e-122">In this example, you created a network region called “NorthAmerica” that is associated with a central site with site ID CHICAGO.</span></span>

3.  <span data-ttu-id="d868e-123">Per completare la creazione delle aree di rete per la topologia, ripetere il passaggio 2 con le impostazioni per ogni area di rete.</span><span class="sxs-lookup"><span data-stu-id="d868e-123">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="d868e-124">Per creare un'area di rete utilizzando il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d868e-124">To create a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d868e-125">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d868e-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d868e-126">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d868e-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="d868e-127">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="d868e-127">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="d868e-128">Fare clic su **Area**.</span><span class="sxs-lookup"><span data-stu-id="d868e-128">Click **Region**.</span></span>

4.  <span data-ttu-id="d868e-129">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="d868e-129">Click **New**.</span></span>

5.  <span data-ttu-id="d868e-130">Nella pagina **Nuova area** fare clic su **Nome** e quindi digitare un nome per l'area di rete.</span><span class="sxs-lookup"><span data-stu-id="d868e-130">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>

6.  <span data-ttu-id="d868e-131">Fare clic su **Sito centrale** e quindi fare clic su un sito centrale nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="d868e-131">Click **Central site**, and then click a central site in the list.</span></span>

7.  <span data-ttu-id="d868e-132">Facoltativamente, fare clic su **Descrizione** e quindi digitare ulteriori informazioni per descrivere il sito di rete.</span><span class="sxs-lookup"><span data-stu-id="d868e-132">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

8.  <span data-ttu-id="d868e-133">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="d868e-133">Click **Commit**.</span></span>

9.  <span data-ttu-id="d868e-134">Per completare la creazione delle aree di rete per la topologia, ripetere i passaggi da 4 a 8 con le impostazioni per le altre aree.</span><span class="sxs-lookup"><span data-stu-id="d868e-134">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-region"></a><span data-ttu-id="d868e-135">Modificare un'area di rete</span><span class="sxs-lookup"><span data-stu-id="d868e-135">Modify a Network Region</span></span>

<span data-ttu-id="d868e-136">È possibile modificare le impostazioni per un'area di rete esistente per adattarle a modifiche delle informazioni di base sull'area o a modifiche rese necessarie da una nuova funzionalità.</span><span class="sxs-lookup"><span data-stu-id="d868e-136">Modify settings for an existing network region to accommodate changes to the basic region information or changes required by a new feature.</span></span>

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="d868e-137">Per modificare un'area di rete utilizzando Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="d868e-137">To modify a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="d868e-138">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d868e-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d868e-139">Eseguire il cmdlet Set-CsNetworkRegion per modificare un'area di rete esistente:</span><span class="sxs-lookup"><span data-stu-id="d868e-139">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="d868e-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d868e-140">For example:</span></span>
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    <span data-ttu-id="d868e-p103">Con questo esempio si modifica un'area di rete esistente denominata “NorthAmerica” (creata con le procedure descritte in precedenza in questo argomento) modificandone la descrizione. Se per l'area “NorthAmerica” esiste già una descrizione, questo comando la sostituisce con il valore specificato. Se non è mai stata impostata una descrizione, con questo comando viene aggiunta.</span><span class="sxs-lookup"><span data-stu-id="d868e-p103">In this example, you modified an existing network region called “NorthAmerica” (created using the procedures earlier in this topic) by changing the description. If a description existed for the “NorthAmerica” region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>

3.  <span data-ttu-id="d868e-143">Per modificare altre aree di rete, ripetere il passaggio 2 con le impostazioni per le altre aree.</span><span class="sxs-lookup"><span data-stu-id="d868e-143">To modify other network regions, repeat step 2 with settings for other regions.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="d868e-144">Per modificare un'area di rete utilizzando il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d868e-144">To modify a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d868e-145">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d868e-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d868e-146">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d868e-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="d868e-147">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="d868e-147">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="d868e-148">Fare clic sul pulsante di spostamento **Area**.</span><span class="sxs-lookup"><span data-stu-id="d868e-148">Click the **Region** navigation button.</span></span>

4.  <span data-ttu-id="d868e-149">Nella tabella fare clic sull'area di rete che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="d868e-149">In the table, click the network region that you want to modify.</span></span>

5.  <span data-ttu-id="d868e-150">Fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="d868e-150">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="d868e-151">Nella pagina **Modifica area** modificare i valori per le impostazioni dell'area di rete in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="d868e-151">On the **Edit Region** page, change the values for this network region’s settings as appropriate.</span></span>

7.  <span data-ttu-id="d868e-152">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="d868e-152">Click **Commit**.</span></span>

8.  <span data-ttu-id="d868e-153">Per completare la modifica delle aree di rete, ripetere i passaggi da 4 a 7 con le impostazioni per le altre aree.</span><span class="sxs-lookup"><span data-stu-id="d868e-153">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

