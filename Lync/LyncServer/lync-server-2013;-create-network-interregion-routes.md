---
title: Lync Server 2013; Creare route tra aree di rete
description: Lync Server 2013; Creare route tra aree di rete.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: admin
manager: serdars
f1.keywords:
- NOCSH
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 44c8c62a86f7cfb6ca5b1148dc097c1d7786ad29
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546052"
---
# <a name="create-network-interregion-routes-in-lync-server-2013"></a><span data-ttu-id="8d695-103">Creare route tra aree di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d695-103">Create network interregion routes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d695-104">_**Ultimo argomento modificato:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="8d695-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="8d695-p101">Una *route tra aree di rete* definisce la route tra una coppia di aree di rete. Ogni coppia di aree di rete nella distribuzione del servizio Controllo di ammissione di chiamata richiede una route di questo tipo. In tal modo ogni area di rete della distribuzione può accedere a tutte le altre aree.</span><span class="sxs-lookup"><span data-stu-id="8d695-p101">A *network interregion route* defines the route between a pair of network regions. Each pair of network regions in your call admission control deployment requires a network interregion route. This enables every network region within the deployment to access every other region.</span></span>

<span data-ttu-id="8d695-108">Se i collegamenti di area impostano limitazioni della larghezza di banda per le connessioni tra le aree, una route tra aree determina il percorso collegato attraversato dalla connessione per passare da un'area all'altra.</span><span class="sxs-lookup"><span data-stu-id="8d695-108">While region links set bandwidth limitations on the connections between regions, an interregion route determines which linked path the connection will traverse from one region to another.</span></span>

<span data-ttu-id="8d695-109">Per informazioni dettagliate sull'utilizzo delle route tra aree di rete, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="8d695-109">For details about working with network interregion routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="8d695-110">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="8d695-110">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="8d695-111">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="8d695-111">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="8d695-112">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="8d695-112">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="8d695-113">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="8d695-113">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

<span data-ttu-id="8d695-114">Nella topologia di esempio, le route tra aree di rete devono essere definite per ognuna delle tre coppie di aree, ovvero Nord America/EMEA, EMEA/APAC e Nord America/APAC.</span><span class="sxs-lookup"><span data-stu-id="8d695-114">In the example topology, network interregion routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a><span data-ttu-id="8d695-115">Per creare route tra aree di rete tramite Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="8d695-115">To create network interregion routes by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="8d695-116">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8d695-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8d695-117">Eseguire il cmdlet **New-CsNetworkInterRegionRoute** per definire le route richieste.</span><span class="sxs-lookup"><span data-stu-id="8d695-117">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="8d695-118">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="8d695-118">For example, run:</span></span>
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="8d695-119">La route tra aree di rete Nord America/APAC richiede due collegamenti tra aree di rete perché non esiste un collegamento diretto tra le due aree.</span><span class="sxs-lookup"><span data-stu-id="8d695-119">The North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a><span data-ttu-id="8d695-120">Per creare route tra aree di rete utilizzando il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="8d695-120">To create network interregion routes by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8d695-121">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8d695-121">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8d695-122">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8d695-122">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="8d695-123">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="8d695-123">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="8d695-124">Fare clic sul pulsante di spostamento **Route area**.</span><span class="sxs-lookup"><span data-stu-id="8d695-124">Click the **Region Route** navigation button.</span></span>

4.  <span data-ttu-id="8d695-125">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8d695-125">Click **New**.</span></span>

5.  <span data-ttu-id="8d695-126">Nella pagina **Nuova route aree di rete** fare clic su **Nome** e quindi digitare un nome per la route tra aree di rete.</span><span class="sxs-lookup"><span data-stu-id="8d695-126">On the **New Region Route** page, click **Name** and then type a name for the network interregion route.</span></span>

6.  <span data-ttu-id="8d695-127">Fare clic su area di rete \*\* \# 1\*\*e quindi fare clic su un'area di rete nell'elenco che si desidera instradare all'area di rete \# 2.</span><span class="sxs-lookup"><span data-stu-id="8d695-127">Click **Network Region \#1**, and then click a network region in the list that you want to route to Network Region \#2.</span></span>

7.  <span data-ttu-id="8d695-128">Fare clic su **area di rete \# 2**e quindi fare clic su un'area di rete nell'elenco che si desidera instradare all'area di rete \# 1.</span><span class="sxs-lookup"><span data-stu-id="8d695-128">Click **Network Region \#2**, and then click a network region in the list that you want to route to Network Region \#1.</span></span>

8.  <span data-ttu-id="8d695-129">Fare clic su **Aggiungi** accanto al campo **Collegamenti aree di rete** e quindi aggiungere un collegamento all'area di rete che verrà usato come route tra aree di rete.</span><span class="sxs-lookup"><span data-stu-id="8d695-129">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregion route.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="8d695-p104">Se si crea una route per due aree di rete tra le quali non esiste un collegamento diretto, è necessario aggiungere tutti i collegamenti necessari per completare la route. Ad esempio, la route tra le aree di rete Nord America/APAC richiede due collegamenti tra aree di rete perché non esiste un collegamento diretto tra le due aree.</span><span class="sxs-lookup"><span data-stu-id="8d695-p104">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route. For example, the North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

9.  <span data-ttu-id="8d695-132">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="8d695-132">Click **Commit**.</span></span>

10. <span data-ttu-id="8d695-133">Per completare la creazione delle route tra aree di rete per la topologia, ripetere i passaggi da 4 a 9 con le impostazioni per le altre route.</span><span class="sxs-lookup"><span data-stu-id="8d695-133">To finish creating network interregion routes for your topology, repeat steps 4 through 9 with settings for other network interregion routes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

