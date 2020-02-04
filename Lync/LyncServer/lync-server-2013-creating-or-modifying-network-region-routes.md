---
title: 'Lync Server 2013: creazione o modifica di route di area di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network region routes
ms:assetid: 76993daa-76c2-4cec-8363-de8aebef0145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521016(v=OCS.15)
ms:contentKeyID: 48184540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d877de116cc2cf3e0c3354bb6e53d69c211cb482
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="d4546-102">Creazione o modifica di route dell'area di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4546-102">Creating or modifying network region routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4546-103">_**Argomento Ultima modifica:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="d4546-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="d4546-104">Ogni area geografica in una configurazione di controllo di ammissione chiamata (CAC) deve avere un modo per accedere a tutte le altre aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="d4546-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="d4546-105">Mentre i collegamenti con le aree geografiche impostano limitazioni della larghezza di banda sulle connessioni tra regioni e rappresentano anche i collegamenti fisici, una route determina il percorso collegato che verrà attraversato dalla connessione da un'area a un'altra.</span><span class="sxs-lookup"><span data-stu-id="d4546-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="d4546-106">È possibile usare il pannello di controllo di Lync Server per configurare le route dell'area di rete.</span><span class="sxs-lookup"><span data-stu-id="d4546-106">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="d4546-107">Dal pannello di controllo di Lync Server è possibile creare, modificare o eliminare una route dell'area di rete.</span><span class="sxs-lookup"><span data-stu-id="d4546-107">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="d4546-108">Usare questo argomento per creare o modificare una route dell'area di rete.</span><span class="sxs-lookup"><span data-stu-id="d4546-108">Use this topic to create or modify a network region route.</span></span> <span data-ttu-id="d4546-109">Per informazioni dettagliate sull'eliminazione di route di un'area di rete esistenti, vedere [eliminazione di route di area di rete esistenti in Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).</span><span class="sxs-lookup"><span data-stu-id="d4546-109">For details about deleting an existing network region routes, see [Deleting existing network region routes in Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).</span></span>

<div>

## <a name="to-create-a-network-region-route"></a><span data-ttu-id="d4546-110">Per creare una route dell'area di rete</span><span class="sxs-lookup"><span data-stu-id="d4546-110">To create a network region route</span></span>

1.  <span data-ttu-id="d4546-111">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="d4546-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d4546-112">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d4546-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d4546-113">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d4546-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d4546-114">Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **area geografica**.</span><span class="sxs-lookup"><span data-stu-id="d4546-114">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="d4546-115">Nella pagina **Route Region** fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="d4546-115">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="d4546-116">Nella **Route New Region**Digitare un valore nel campo **nome** .</span><span class="sxs-lookup"><span data-stu-id="d4546-116">In **New Region Route**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d4546-117">Questo valore deve essere univoco all'interno della distribuzione di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d4546-117">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="d4546-118">Nell'elenco a discesa \*\* \#area di rete 1\*\* Selezionare una delle due aree geografiche da connettere tramite questa route.</span><span class="sxs-lookup"><span data-stu-id="d4546-118">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="d4546-119">Nell'elenco a discesa **Network Region \#2** Selezionare l'altra area per questa route.</span><span class="sxs-lookup"><span data-stu-id="d4546-119">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="d4546-120">L'area geografica deve essere diversa da quella selezionata per l' \#area geografica di rete 1.</span><span class="sxs-lookup"><span data-stu-id="d4546-120">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="d4546-121">Usare la casella di riepilogo **collegamenti area di rete** per aggiungere collegamenti all'area geografica.</span><span class="sxs-lookup"><span data-stu-id="d4546-121">Use the **Network region links** list box to add region links to the route.</span></span> <span data-ttu-id="d4546-122">Fare clic sul pulsante **Aggiungi** per visualizzare la pagina del **collegamento all'area geografica** .</span><span class="sxs-lookup"><span data-stu-id="d4546-122">Click the **Add** button to display the **Region Link** page.</span></span> <span data-ttu-id="d4546-123">Fare clic su un collegamento all'area da aggiungere alla route e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d4546-123">Click a region link to add to this route, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d4546-124">Continuare a fare clic sul pulsante <STRONG>Aggiungi</STRONG> per aggiungere altri collegamenti oppure selezionare un collegamento e fare clic su <STRONG>Rimuovi</STRONG> per rimuovere un collegamento.</span><span class="sxs-lookup"><span data-stu-id="d4546-124">Continue to click the <STRONG>Add</STRONG> button to add more links, or select a link and click <STRONG>Remove</STRONG> to remove a link.</span></span>

    
    </div>

9.  <span data-ttu-id="d4546-125">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="d4546-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-route"></a><span data-ttu-id="d4546-126">Per modificare una route dell'area di rete</span><span class="sxs-lookup"><span data-stu-id="d4546-126">To modify a network region route</span></span>

1.  <span data-ttu-id="d4546-127">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="d4546-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d4546-128">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d4546-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d4546-129">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d4546-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d4546-130">Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **area geografica**.</span><span class="sxs-lookup"><span data-stu-id="d4546-130">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="d4546-131">Nella pagina **Route Region** fare clic sulla route dell'area geografica che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="d4546-131">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="d4546-132">Nel menu **modifica** fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="d4546-132">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="d4546-133">In **modifica route area**è possibile modificare le aree affiancate da questa route e i collegamenti dell'area geografica associati alla route.</span><span class="sxs-lookup"><span data-stu-id="d4546-133">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="d4546-134">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="d4546-134">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d4546-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4546-135">See Also</span></span>


[<span data-ttu-id="d4546-136">Eliminazione di route di area di rete esistenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4546-136">Deleting existing network region routes in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

