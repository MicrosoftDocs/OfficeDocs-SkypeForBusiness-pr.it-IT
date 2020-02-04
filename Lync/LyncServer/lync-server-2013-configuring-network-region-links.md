---
title: "Lync Server 2013: configurazione di collegamenti all'area di rete"
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
ms.openlocfilehash: 5d069bb5215fc977a35481a916f49e86fa644284
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-region-links-in-lync-server-2013"></a><span data-ttu-id="cad99-102">Configurazione di collegamenti all'area di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cad99-102">Configuring network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cad99-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="cad99-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="cad99-104">È possibile configurare i collegamenti tra due aree di rete nell'ambito del controllo di ammissione di chiamata (CAC).</span><span class="sxs-lookup"><span data-stu-id="cad99-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="cad99-105">Le aree all'interno di una rete sono collegate tramite connettività WAN (Physical Wide Area Network).</span><span class="sxs-lookup"><span data-stu-id="cad99-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="cad99-106">È possibile usare il pannello di controllo di Lync Server per definire un collegamento tra due aree di rete e impostare le limitazioni della larghezza di banda per le connessioni audio e video tra queste aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="cad99-106">You can use the Lync Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span> <span data-ttu-id="cad99-107">Per informazioni dettagliate sull'eliminazione di un collegamento a un'area geografica esistente, vedere [eliminazione di collegamenti all'area di rete in Lync Server 2013](lync-server-2013-deleting-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="cad99-107">For details about deleting an existing network region link, see [Deleting network region links in Lync Server 2013](lync-server-2013-deleting-network-region-links.md).</span></span>

<div>

## <a name="to-create-a-network-region-link"></a><span data-ttu-id="cad99-108">Per creare un collegamento all'area di rete</span><span class="sxs-lookup"><span data-stu-id="cad99-108">To create a network region link</span></span>

1.  <span data-ttu-id="cad99-109">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="cad99-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cad99-110">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cad99-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cad99-111">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cad99-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cad99-112">Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su collegamento all' **area geografica**.</span><span class="sxs-lookup"><span data-stu-id="cad99-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="cad99-113">Nella pagina **collegamento all'area geografica** fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="cad99-113">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="cad99-114">Nel **collegamento New Region**Digitare un valore nel campo **nome** .</span><span class="sxs-lookup"><span data-stu-id="cad99-114">In **New Region Link**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cad99-115">Questo valore deve essere univoco all'interno della distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cad99-115">This value must be unique within your Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="cad99-116">Nell'elenco a discesa **Network Region \#1** Selezionare una delle due aree geografiche da collegare.</span><span class="sxs-lookup"><span data-stu-id="cad99-116">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="cad99-117">Nell'elenco a discesa **Network Region \#2** Selezionare l'altra area da collegare.</span><span class="sxs-lookup"><span data-stu-id="cad99-117">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="cad99-118">L'area geografica deve essere diversa da quella selezionata per l' \#area geografica di rete 1.</span><span class="sxs-lookup"><span data-stu-id="cad99-118">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="cad99-119">Opzionale Se si desidera inserire limitazioni della larghezza di banda per le chiamate audio o video tra queste aree geografiche, selezionare un profilo dei criteri di larghezza di banda nell'elenco a discesa **criteri di larghezza** di banda.</span><span class="sxs-lookup"><span data-stu-id="cad99-119">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="cad99-120">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="cad99-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-link"></a><span data-ttu-id="cad99-121">Per modificare un collegamento all'area di rete</span><span class="sxs-lookup"><span data-stu-id="cad99-121">To modify a network region link</span></span>

1.  <span data-ttu-id="cad99-122">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="cad99-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cad99-123">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cad99-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cad99-124">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cad99-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cad99-125">Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su collegamento all' **area geografica**.</span><span class="sxs-lookup"><span data-stu-id="cad99-125">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="cad99-126">Nella pagina **collegamento all'area geografica** fare clic sul collegamento all'area che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="cad99-126">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="cad99-127">Nel menu **modifica** fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="cad99-127">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="cad99-128">In **Modifica collegamento area**è possibile modificare le aree collegate o il profilo dei criteri di larghezza di banda per questo collegamento.</span><span class="sxs-lookup"><span data-stu-id="cad99-128">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="cad99-129">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="cad99-129">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cad99-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cad99-130">See Also</span></span>


[<span data-ttu-id="cad99-131">Eliminazione di collegamenti all'area di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cad99-131">Deleting network region links in Lync Server 2013</span></span>](lync-server-2013-deleting-network-region-links.md)  


[<span data-ttu-id="cad99-132">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="cad99-132">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  
[<span data-ttu-id="cad99-133">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="cad99-133">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  
[<span data-ttu-id="cad99-134">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="cad99-134">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  
[<span data-ttu-id="cad99-135">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="cad99-135">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
