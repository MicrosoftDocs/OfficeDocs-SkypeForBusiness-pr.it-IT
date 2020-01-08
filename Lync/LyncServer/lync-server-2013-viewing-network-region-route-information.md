---
title: "Lync Server 2013: visualizzazione delle informazioni sulla route dell'area di rete"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network region route information
ms:assetid: 34dd9fa3-e695-4680-b244-3019298b5009
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688021(v=OCS.15)
ms:contentKeyID: 49733611
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4438a3af4a9bfbdaf88d4412b769cdaaba9d3d43
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-route-information-in-lync-server-2013"></a><span data-ttu-id="b6338-102">Visualizzazione delle informazioni sulla route dell'area di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6338-102">Viewing network region route information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6338-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b6338-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b6338-104">Ogni area geografica in una configurazione di controllo di ammissione chiamata (CAC) deve avere un modo per accedere a tutte le altre aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="b6338-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="b6338-105">Mentre i collegamenti con le aree geografiche impostano limitazioni della larghezza di banda sulle connessioni tra regioni e rappresentano anche i collegamenti fisici, una route determina il percorso collegato che verrà attraversato dalla connessione da un'area a un'altra.</span><span class="sxs-lookup"><span data-stu-id="b6338-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="b6338-106">Usare le procedure seguenti per visualizzare le route dell'area di rete esistenti nel pannello di controllo di Lync Server 2013 o in Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b6338-106">Use the following procedures to view existing network region routes in Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="b6338-107">Per informazioni dettagliate sulla creazione o la modifica di route di area di rete, vedere [creazione o modifica di route dell'area di rete in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span><span class="sxs-lookup"><span data-stu-id="b6338-107">For details about creating or modifying network region routes, see [Creating or modifying network region routes in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span></span>

<div>

## <a name="to-view-network-region-route-information-in-lync-server-control-panel"></a><span data-ttu-id="b6338-108">Per visualizzare le informazioni sulla route dell'area di rete nel pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="b6338-108">To view network region route information in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b6338-109">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="b6338-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b6338-110">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b6338-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b6338-111">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b6338-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b6338-112">Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **area geografica**.</span><span class="sxs-lookup"><span data-stu-id="b6338-112">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="b6338-113">Nella pagina **route dell'area geografica** fare clic sulla route dell'area geografica che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="b6338-113">On the **Region Route** page, click the region route that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b6338-114">È possibile visualizzare una sola route geografica alla volta.</span><span class="sxs-lookup"><span data-stu-id="b6338-114">You can only view one region route at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="b6338-115">Nel menu **modifica** fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="b6338-115">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b6338-116">Visualizzazione delle informazioni sulla route dell'area di rete tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6338-116">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b6338-117">Le informazioni sulla route dell'area di rete possono essere visualizzate usando Windows PowerShell e il cmdlet Get-CsNetworkInterRegionRoute.</span><span class="sxs-lookup"><span data-stu-id="b6338-117">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="b6338-118">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6338-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b6338-119">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="b6338-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-route-information"></a><span data-ttu-id="b6338-120">Per visualizzare le informazioni sulla route dell'area di rete</span><span class="sxs-lookup"><span data-stu-id="b6338-120">To view network region route information</span></span>

  - <span data-ttu-id="b6338-121">Per visualizzare informazioni su tutte le route dell'area di rete, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="b6338-121">To view information about all your network region routes, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="b6338-122">Questo restituirà informazioni simili alla seguente:</span><span class="sxs-lookup"><span data-stu-id="b6338-122">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

</div>

<span data-ttu-id="b6338-123">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) .</span><span class="sxs-lookup"><span data-stu-id="b6338-123">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b6338-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6338-124">See Also</span></span>


[<span data-ttu-id="b6338-125">Creazione o modifica di route dell'area di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6338-125">Creating or modifying network region routes in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-region-routes.md)  
[<span data-ttu-id="b6338-126">Eliminazione di route di area di rete esistenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6338-126">Deleting existing network region routes in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

