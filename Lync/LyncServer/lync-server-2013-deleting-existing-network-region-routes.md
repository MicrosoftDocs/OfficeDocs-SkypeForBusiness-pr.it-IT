---
title: "Lync Server 2013: eliminare le route esistenti nell'area di rete"
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
ms.openlocfilehash: e9f9ba7c20aff0bba3101edc9b04f3704314cfc8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="06a8d-102">Eliminazione di route di area di rete esistenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06a8d-102">Deleting existing network region routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06a8d-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="06a8d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="06a8d-104">Ogni area geografica in una configurazione di controllo di ammissione chiamata (CAC) deve avere un modo per accedere a tutte le altre aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="06a8d-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="06a8d-105">Mentre i collegamenti con le aree geografiche impostano limitazioni della larghezza di banda sulle connessioni tra regioni e rappresentano anche i collegamenti fisici, una route determina il percorso collegato che verrà attraversato dalla connessione da un'area a un'altra.</span><span class="sxs-lookup"><span data-stu-id="06a8d-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="06a8d-106">È possibile usare il pannello di controllo di Lync Server per configurare le route dell'area di rete.</span><span class="sxs-lookup"><span data-stu-id="06a8d-106">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="06a8d-107">Dal pannello di controllo di Lync Server è possibile creare, modificare o eliminare una route dell'area di rete.</span><span class="sxs-lookup"><span data-stu-id="06a8d-107">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="06a8d-108">Usare questo argomento per eliminare le route esistenti nell'area di rete.</span><span class="sxs-lookup"><span data-stu-id="06a8d-108">Use this topic to delete existing network region routes.</span></span> <span data-ttu-id="06a8d-109">Per informazioni dettagliate sulla creazione o la modifica di route di area di rete, vedere [creazione o modifica di route dell'area di rete in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span><span class="sxs-lookup"><span data-stu-id="06a8d-109">For details about creating or modifying network region routes, see [Creating or modifying network region routes in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span></span>

<div>

## <a name="to-delete-a-network-region-route"></a><span data-ttu-id="06a8d-110">Per eliminare una route dell'area di rete</span><span class="sxs-lookup"><span data-stu-id="06a8d-110">To delete a network region route</span></span>

1.  <span data-ttu-id="06a8d-111">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="06a8d-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="06a8d-112">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06a8d-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="06a8d-113">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="06a8d-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="06a8d-114">Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **area geografica**.</span><span class="sxs-lookup"><span data-stu-id="06a8d-114">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="06a8d-115">Nella pagina **route dell'area geografica** fare clic sulla route di area che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="06a8d-115">On the **Region Route** page, click the region route that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="06a8d-116">Puoi eliminare più di una route della regione alla volta.</span><span class="sxs-lookup"><span data-stu-id="06a8d-116">You can delete more than one region route at a time.</span></span> <span data-ttu-id="06a8d-117">Per eseguire questa operazione, premere CTRL e selezionare più percorsi per le aree geografiche mentre si tiene premuto il tasto CTRL.</span><span class="sxs-lookup"><span data-stu-id="06a8d-117">To do this, press CTRL and select multiple region routes while holding down the CTRL key.</span></span> <span data-ttu-id="06a8d-118">In alternativa, per selezionare tutte le route dell'area geografica, fare clic su <STRONG>Seleziona tutto</STRONG> dal menu <STRONG>modifica</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="06a8d-118">Or, to select all region routes, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="06a8d-119">Scegliere **Elimina**dal menu **modifica** .</span><span class="sxs-lookup"><span data-stu-id="06a8d-119">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="06a8d-120">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="06a8d-120">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="06a8d-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06a8d-121">See Also</span></span>


[<span data-ttu-id="06a8d-122">Creazione o modifica di route dell'area di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06a8d-122">Creating or modifying network region routes in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-region-routes.md)  


<span data-ttu-id="06a8d-123">[Configurare una route di un'area di rete](https://technet.microsoft.com/en-us/library/gg133706\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="06a8d-123">[Configure a Network Region Route](https://technet.microsoft.com/en-us/library/gg133706\(v=ocs.15\))</span></span>  


[<span data-ttu-id="06a8d-124">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="06a8d-124">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[<span data-ttu-id="06a8d-125">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="06a8d-125">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[<span data-ttu-id="06a8d-126">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="06a8d-126">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[<span data-ttu-id="06a8d-127">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="06a8d-127">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

