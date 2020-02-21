---
title: 'Lync Server 2013: eliminazione delle route delle aree di rete esistenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network region routes
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49733669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91a8674e635bb5663ebbca994d7d8f865601a193
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206962"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="b5273-102">Eliminazione delle route delle aree di rete esistenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5273-102">Deleting existing network region routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5273-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b5273-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b5273-104">Ogni area di una configurazione di controllo di ammissione di chiamata deve in qualche modo poter accedere a tutte le altre aree.</span><span class="sxs-lookup"><span data-stu-id="b5273-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="b5273-105">Mentre i collegamenti area impostano limitazioni della larghezza di banda nelle connessioni tra aree e rappresentano anche i collegamenti fisici, una route determina il percorso collegato che verrà attraversato dalla connessione per passare da un'area all'altra.</span><span class="sxs-lookup"><span data-stu-id="b5273-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="b5273-106">È possibile utilizzare il pannello di controllo di Lync Server per configurare le route delle aree di rete.</span><span class="sxs-lookup"><span data-stu-id="b5273-106">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="b5273-107">Dal pannello di controllo di Lync Server, è possibile creare, modificare o eliminare una route area di rete.</span><span class="sxs-lookup"><span data-stu-id="b5273-107">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="b5273-108">Utilizzare questo argomento per informazioni su come eliminare le route area di rete.</span><span class="sxs-lookup"><span data-stu-id="b5273-108">Use this topic to delete existing network region routes.</span></span> <span data-ttu-id="b5273-109">Per informazioni dettagliate sulla creazione o la modifica delle route delle aree di rete, vedere [creazione o modifica di route delle aree di rete in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span><span class="sxs-lookup"><span data-stu-id="b5273-109">For details about creating or modifying network region routes, see [Creating or modifying network region routes in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span></span>

<div>

## <a name="to-delete-a-network-region-route"></a><span data-ttu-id="b5273-110">Per eliminare una route area di rete</span><span class="sxs-lookup"><span data-stu-id="b5273-110">To delete a network region route</span></span>

1.  <span data-ttu-id="b5273-111">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="b5273-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b5273-112">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b5273-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b5273-113">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b5273-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b5273-114">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Route area**.</span><span class="sxs-lookup"><span data-stu-id="b5273-114">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="b5273-115">Nella pagina **Route area** fare clic sulla route area che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="b5273-115">On the **Region Route** page, click the region route that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b5273-p103">È possibile eliminare più di una route area per volta. A tale scopo, selezionare più route area tenendo premuto CTRL oppure, per selezionare tutte le route area, scegliere <STRONG>Seleziona tutto</STRONG> dal menu <STRONG>Modifica</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b5273-p103">You can delete more than one region route at a time. To do this, press CTRL and select multiple region routes while holding down the CTRL key. Or, to select all region routes, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="b5273-119">Scegliere **Elimina** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="b5273-119">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="b5273-120">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5273-120">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b5273-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5273-121">See Also</span></span>


[<span data-ttu-id="b5273-122">Creazione o modifica delle route delle aree di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5273-122">Creating or modifying network region routes in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-region-routes.md)  


<span data-ttu-id="b5273-123">[Configurare una route area tra reti](https://technet.microsoft.com/library/gg133706\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b5273-123">[Configure a Network Region Route](https://technet.microsoft.com/library/gg133706\(v=ocs.15\))</span></span>  


[<span data-ttu-id="b5273-124">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="b5273-124">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[<span data-ttu-id="b5273-125">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="b5273-125">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[<span data-ttu-id="b5273-126">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="b5273-126">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[<span data-ttu-id="b5273-127">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="b5273-127">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

