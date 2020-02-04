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
ms.openlocfilehash: 75011a28567da8a6e386c42f272ee1510b8ceddc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a><span data-ttu-id="e5e0b-102">Creare o modificare un'area di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5e0b-102">Create or modify a network region in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5e0b-103">_**Argomento Ultima modifica:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="e5e0b-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="e5e0b-104">Le *aree di rete* sono gli hub di rete o le backbone usati nella configurazione del controllo di ammissione alle chiamate, E9-1-1 e bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="e5e0b-105">Usare le procedure seguenti per creare o modificare aree di rete.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-105">Use the following procedures to create or modify network regions.</span></span> <span data-ttu-id="e5e0b-106">Se ad esempio sono già state create aree di rete per una sola funzionalità vocale, non è necessario creare nuove aree di rete. altre funzionalità vocali avanzate di Enterprise useranno le stesse aree di rete.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="e5e0b-107">Può tuttavia essere necessario modificare una definizione di area di rete esistente per applicare impostazioni specifiche delle caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="e5e0b-108">Ad esempio, se sono state create aree di rete per E9-1-1 (che non richiedono un sito centrale associato) e quindi si distribuisce il controllo di ammissione delle chiamate, è necessario modificare le definizioni dell'area di rete per specificare un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="e5e0b-109">Per informazioni dettagliate, vedere [configurare le aree di rete per CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="e5e0b-109">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e5e0b-110">Tutti i requisiti specifici delle caratteristiche per le definizioni di area di rete sono documentati negli argomenti relativi alla distribuzione della funzionalità.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-110">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<span data-ttu-id="e5e0b-111">Per informazioni dettagliate sull'uso delle aree di rete, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="e5e0b-111">For details about working with network regions, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="e5e0b-112">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="e5e0b-112">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [<span data-ttu-id="e5e0b-113">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="e5e0b-113">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="e5e0b-114">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="e5e0b-114">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [<span data-ttu-id="e5e0b-115">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="e5e0b-115">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a><span data-ttu-id="e5e0b-116">Creare un'area di rete</span><span class="sxs-lookup"><span data-stu-id="e5e0b-116">Create a Network Region</span></span>

<span data-ttu-id="e5e0b-117">Creare un'area di rete che può essere usata tramite il controllo di ammissione alle chiamate, E9-1-1 o bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-117">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="e5e0b-118">Per creare un'area di rete con Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="e5e0b-118">To create a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="e5e0b-119">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e5e0b-120">Eseguire il cmdlet New-CsNetworkRegion per creare aree di rete:</span><span class="sxs-lookup"><span data-stu-id="e5e0b-120">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="e5e0b-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e5e0b-121">For example:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    <span data-ttu-id="e5e0b-122">In questo esempio è stata creata un'area di rete denominata "NorthAmerica" associata a un sito centrale con ID sito di CHICAGO.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-122">In this example, you created a network region called “NorthAmerica” that is associated with a central site with site ID CHICAGO.</span></span>

3.  <span data-ttu-id="e5e0b-123">Per completare la creazione di aree di rete per la topologia, ripetere il passaggio 2 con le impostazioni per ogni area di rete.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-123">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="e5e0b-124">Per creare un'area di rete tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="e5e0b-124">To create a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e5e0b-125">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e5e0b-126">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e5e0b-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="e5e0b-127">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-127">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="e5e0b-128">Fare clic su **area geografica**.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-128">Click **Region**.</span></span>

4.  <span data-ttu-id="e5e0b-129">Fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-129">Click **New**.</span></span>

5.  <span data-ttu-id="e5e0b-130">Nella pagina **nuova area** fare clic su **nome** e quindi digitare un nome per l'area di rete.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-130">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>

6.  <span data-ttu-id="e5e0b-131">Fare clic su **sito centrale**e quindi su un sito centrale nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-131">Click **Central site**, and then click a central site in the list.</span></span>

7.  <span data-ttu-id="e5e0b-132">Facoltativamente, fare clic su **Descrizione**e quindi digitare altre informazioni per descrivere questo sito di rete.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-132">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

8.  <span data-ttu-id="e5e0b-133">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-133">Click **Commit**.</span></span>

9.  <span data-ttu-id="e5e0b-134">Per completare la creazione di aree di rete per la topologia, ripetere i passaggi da 4 a 8 con le impostazioni per altre aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-134">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-region"></a><span data-ttu-id="e5e0b-135">Modificare un'area di rete</span><span class="sxs-lookup"><span data-stu-id="e5e0b-135">Modify a Network Region</span></span>

<span data-ttu-id="e5e0b-136">Modificare le impostazioni di un'area geografica esistente per adattare le modifiche alle informazioni relative alle aree di base o alle modifiche necessarie per una nuova funzionalità.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-136">Modify settings for an existing network region to accommodate changes to the basic region information or changes required by a new feature.</span></span>

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="e5e0b-137">Per modificare un'area di rete tramite Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="e5e0b-137">To modify a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="e5e0b-138">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e5e0b-139">Eseguire il cmdlet Set-CsNetworkRegion per modificare un'area di rete esistente:</span><span class="sxs-lookup"><span data-stu-id="e5e0b-139">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="e5e0b-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e5e0b-140">For example:</span></span>
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    <span data-ttu-id="e5e0b-141">In questo esempio è stata modificata un'area di rete esistente denominata "NorthAmerica" (creata usando le procedure descritte più indietro in questo argomento) modificando la descrizione.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-141">In this example, you modified an existing network region called “NorthAmerica” (created using the procedures earlier in this topic) by changing the description.</span></span> <span data-ttu-id="e5e0b-142">Se esiste una descrizione per l'area "NorthAmerica", questo comando lo sovrascrive con questo valore; Se non è stata impostata alcuna descrizione, questo comando lo imposta.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-142">If a description existed for the “NorthAmerica” region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>

3.  <span data-ttu-id="e5e0b-143">Per modificare altre aree di rete, ripetere il passaggio 2 con le impostazioni per altre aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-143">To modify other network regions, repeat step 2 with settings for other regions.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="e5e0b-144">Per modificare un'area di rete tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="e5e0b-144">To modify a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e5e0b-145">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e5e0b-146">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e5e0b-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="e5e0b-147">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-147">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="e5e0b-148">Fare clic sul pulsante di spostamento dell' **area geografica** .</span><span class="sxs-lookup"><span data-stu-id="e5e0b-148">Click the **Region** navigation button.</span></span>

4.  <span data-ttu-id="e5e0b-149">Nella tabella fare clic sull'area di rete che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-149">In the table, click the network region that you want to modify.</span></span>

5.  <span data-ttu-id="e5e0b-150">Fare clic su **modifica**e quindi su **Mostra dettagli.**</span><span class="sxs-lookup"><span data-stu-id="e5e0b-150">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="e5e0b-151">Nella pagina **Edit Region** modificare i valori delle impostazioni dell'area di rete in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-151">On the **Edit Region** page, change the values for this network region’s settings as appropriate.</span></span>

7.  <span data-ttu-id="e5e0b-152">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-152">Click **Commit**.</span></span>

8.  <span data-ttu-id="e5e0b-153">Per completare la modifica delle aree di rete, ripetere i passaggi da 4 a 7 con le impostazioni per altre aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="e5e0b-153">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

