---
title: Lync Server 2013; Creare route interregion di rete
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: admin
manager: serdars
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 0eff2c1dd75258451002a41e0f284c4ad05c9728
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "40979428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a><span data-ttu-id="8dff8-102">Creare route interregion di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8dff8-102">Create network interregion routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8dff8-103">_**Argomento Ultima modifica:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="8dff8-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="8dff8-104">Una *Route interregion di rete* definisce la route tra una coppia di aree della rete.</span><span class="sxs-lookup"><span data-stu-id="8dff8-104">A *network interregion route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="8dff8-105">Ogni coppia di aree della rete nella distribuzione del controllo di ammissione alle chiamate richiede una route interregion di rete.</span><span class="sxs-lookup"><span data-stu-id="8dff8-105">Each pair of network regions in your call admission control deployment requires a network interregion route.</span></span> <span data-ttu-id="8dff8-106">In questo modo ogni area di rete della distribuzione consente di accedere a tutte le altre aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="8dff8-106">This enables every network region within the deployment to access every other region.</span></span>

<span data-ttu-id="8dff8-107">Mentre i collegamenti con le aree geografiche impostano limitazioni della larghezza di banda sulle connessioni tra regioni, una route interregion determina il percorso collegato che la connessione attraverserà da un'area a un'altra.</span><span class="sxs-lookup"><span data-stu-id="8dff8-107">While region links set bandwidth limitations on the connections between regions, an interregion route determines which linked path the connection will traverse from one region to another.</span></span>

<span data-ttu-id="8dff8-108">Per informazioni dettagliate sull'uso delle route interregion di rete, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="8dff8-108">For details about working with network interregion routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="8dff8-109">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="8dff8-109">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="8dff8-110">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="8dff8-110">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="8dff8-111">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="8dff8-111">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="8dff8-112">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="8dff8-112">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

<span data-ttu-id="8dff8-113">Nella topologia di esempio è necessario definire le route interregion di rete per ognuna delle tre coppie di aree geografiche: Nord America/EMEA, EMEA/APAC e Nord America/APAC.</span><span class="sxs-lookup"><span data-stu-id="8dff8-113">In the example topology, network interregion routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a><span data-ttu-id="8dff8-114">Per creare route interregion di rete tramite Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="8dff8-114">To create network interregion routes by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="8dff8-115">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8dff8-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8dff8-116">Eseguire il cmdlet **New-CsNetworkInterRegionRoute** per definire le route necessarie.</span><span class="sxs-lookup"><span data-stu-id="8dff8-116">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="8dff8-117">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="8dff8-117">For example, run:</span></span>
    
       ```
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="8dff8-118">La route interregion di rete Nord America/APAC richiede due collegamenti all'area di rete perché non è presente un collegamento all'area di rete diretta.</span><span class="sxs-lookup"><span data-stu-id="8dff8-118">The North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a><span data-ttu-id="8dff8-119">Per creare route interregion di rete tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="8dff8-119">To create network interregion routes by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8dff8-120">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8dff8-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8dff8-121">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8dff8-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="8dff8-122">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="8dff8-122">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="8dff8-123">Fare clic sul pulsante di spostamento della **Route geografica** .</span><span class="sxs-lookup"><span data-stu-id="8dff8-123">Click the **Region Route** navigation button.</span></span>

4.  <span data-ttu-id="8dff8-124">Fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8dff8-124">Click **New**.</span></span>

5.  <span data-ttu-id="8dff8-125">Nella pagina **nuova route dell'area geografica** fare clic su **nome** e quindi digitare un nome per la route interregion di rete.</span><span class="sxs-lookup"><span data-stu-id="8dff8-125">On the **New Region Route** page, click **Name** and then type a name for the network interregion route.</span></span>

6.  <span data-ttu-id="8dff8-126">Fare clic su **area \#di rete 1**e quindi fare clic su un'area di rete nell'elenco che si vuole instradare all'area geografica \#di rete 2.</span><span class="sxs-lookup"><span data-stu-id="8dff8-126">Click **Network Region \#1**, and then click a network region in the list that you want to route to Network Region \#2.</span></span>

7.  <span data-ttu-id="8dff8-127">Fare clic su **area geografica \#di rete 2**e quindi fare clic su un'area di rete nell'elenco che si \#vuole instradare all'area geografica di rete 1.</span><span class="sxs-lookup"><span data-stu-id="8dff8-127">Click **Network Region \#2**, and then click a network region in the list that you want to route to Network Region \#1.</span></span>

8.  <span data-ttu-id="8dff8-128">Fare clic su **Aggiungi** accanto al campo **collegamenti area geografica** e quindi aggiungere un collegamento all'area di rete che verrà usato nella route interregion di rete.</span><span class="sxs-lookup"><span data-stu-id="8dff8-128">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregion route.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="8dff8-129">Se si sta creando una route per due aree di rete che non dispongono di un collegamento all'area di rete diretta, è necessario aggiungere tutti i collegamenti necessari per completare la route.</span><span class="sxs-lookup"><span data-stu-id="8dff8-129">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route.</span></span> <span data-ttu-id="8dff8-130">Ad esempio, la route interregion di rete Nord America/APAC richiede due collegamenti all'area geografica di rete perché non è presente un collegamento all'area di rete diretta.</span><span class="sxs-lookup"><span data-stu-id="8dff8-130">For example, the North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

9.  <span data-ttu-id="8dff8-131">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="8dff8-131">Click **Commit**.</span></span>

10. <span data-ttu-id="8dff8-132">Per completare la creazione di route interregion di rete per la topologia, ripetere i passaggi da 4 a 9 con le impostazioni per altre route interregion di rete.</span><span class="sxs-lookup"><span data-stu-id="8dff8-132">To finish creating network interregion routes for your topology, repeat steps 4 through 9 with settings for other network interregion routes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

