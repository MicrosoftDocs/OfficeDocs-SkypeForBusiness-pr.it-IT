---
title: 'Lync Server 2013: configurazione di collegamenti tra aree di rete'
description: 'Lync Server 2013: Configuring Network Region Links.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network region links
ms:assetid: 952bc93e-e6aa-4539-85c7-2b15f14eb382
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182551(v=OCS.15)
ms:contentKeyID: 48184829
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b92593f3b8fcd5fe3307a9c193ed7cddcf6dfce0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547012"
---
# <a name="configuring-network-region-links-in-lync-server-2013"></a><span data-ttu-id="1a794-103">Configurazione di collegamenti tra aree di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a794-103">Configuring network region links in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a794-104">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1a794-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1a794-105">È possibile configurare i collegamenti tra due aree di rete nell'ambito del servizio Controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="1a794-105">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="1a794-106">Le aree di una rete sono collegate mediante una connettività WAN fisica.</span><span class="sxs-lookup"><span data-stu-id="1a794-106">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="1a794-107">È possibile utilizzare il pannello di controllo di Lync Server per definire un collegamento tra due aree di rete e impostare le limitazioni della larghezza di banda per le connessioni audio e video tra queste aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="1a794-107">You can use the Lync Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span> <span data-ttu-id="1a794-108">Per informazioni dettagliate sull'eliminazione di un collegamento a un'area di rete esistente, vedere [eliminazione di collegamenti di aree di rete in Lync Server 2013](lync-server-2013-deleting-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="1a794-108">For details about deleting an existing network region link, see [Deleting network region links in Lync Server 2013](lync-server-2013-deleting-network-region-links.md).</span></span>

<div>

## <a name="to-create-a-network-region-link"></a><span data-ttu-id="1a794-109">Per creare un collegamento area di rete</span><span class="sxs-lookup"><span data-stu-id="1a794-109">To create a network region link</span></span>

1.  <span data-ttu-id="1a794-110">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="1a794-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1a794-111">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1a794-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1a794-112">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1a794-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1a794-113">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Collegamento area**.</span><span class="sxs-lookup"><span data-stu-id="1a794-113">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="1a794-114">Nella pagina **collegamento area** fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="1a794-114">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="1a794-115">In **nuovo collegamento area**Digitare un valore nel campo **nome** .</span><span class="sxs-lookup"><span data-stu-id="1a794-115">In **New Region Link**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1a794-116">Questo valore deve essere univoco all'interno della distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1a794-116">This value must be unique within your Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="1a794-117">Nell'elenco a discesa **area di rete \# 1** Selezionare una delle due aree geografiche da collegare.</span><span class="sxs-lookup"><span data-stu-id="1a794-117">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="1a794-118">Nell'elenco a discesa **area di rete \# 2** Selezionare l'altra area da collegare.</span><span class="sxs-lookup"><span data-stu-id="1a794-118">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="1a794-119">Questa area deve essere diversa dall'area selezionata per l'area di rete \# 1.</span><span class="sxs-lookup"><span data-stu-id="1a794-119">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="1a794-120">Optional Se si desidera inserire limitazioni della larghezza di banda per le chiamate audio o video tra queste aree, selezionare un profilo dei criteri di larghezza di banda nell'elenco a discesa **criteri larghezza** di banda.</span><span class="sxs-lookup"><span data-stu-id="1a794-120">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="1a794-121">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="1a794-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-link"></a><span data-ttu-id="1a794-122">Per modificare un collegamento area di rete</span><span class="sxs-lookup"><span data-stu-id="1a794-122">To modify a network region link</span></span>

1.  <span data-ttu-id="1a794-123">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="1a794-123">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1a794-124">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1a794-124">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1a794-125">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1a794-125">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1a794-126">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Collegamento area**.</span><span class="sxs-lookup"><span data-stu-id="1a794-126">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="1a794-127">Nella pagina **collegamento area** fare clic sul collegamento area che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="1a794-127">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="1a794-128">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="1a794-128">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="1a794-129">In **Modifica collegamento area**è possibile modificare le aree collegate o il profilo dei criteri di larghezza di banda per questo collegamento.</span><span class="sxs-lookup"><span data-stu-id="1a794-129">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="1a794-130">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="1a794-130">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1a794-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a794-131">See Also</span></span>


[<span data-ttu-id="1a794-132">Eliminazione di collegamenti delle aree di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a794-132">Deleting network region links in Lync Server 2013</span></span>](lync-server-2013-deleting-network-region-links.md)  


[<span data-ttu-id="1a794-133">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="1a794-133">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  
[<span data-ttu-id="1a794-134">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="1a794-134">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  
[<span data-ttu-id="1a794-135">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="1a794-135">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  
[<span data-ttu-id="1a794-136">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="1a794-136">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
