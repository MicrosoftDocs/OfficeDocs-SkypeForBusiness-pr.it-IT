---
title: 'Lync Server 2013: creazione o modifica di route delle aree di rete'
description: 'Lync Server 2013: creazione o modifica di route delle aree di rete.'
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
ms.openlocfilehash: 89106c905419778776ea16341f247027d49f1195
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544092"
---
# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="127fd-103">Creazione o modifica delle route delle aree di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="127fd-103">Creating or modifying network region routes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="127fd-104">_**Ultimo argomento modificato:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="127fd-104">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="127fd-105">Ogni area di una configurazione di controllo di ammissione di chiamata deve in qualche modo poter accedere a tutte le altre aree.</span><span class="sxs-lookup"><span data-stu-id="127fd-105">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="127fd-106">Mentre i collegamenti area impostano limitazioni della larghezza di banda nelle connessioni tra aree e rappresentano anche i collegamenti fisici, una route determina il percorso collegato che verrà attraversato dalla connessione per passare da un'area all'altra.</span><span class="sxs-lookup"><span data-stu-id="127fd-106">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="127fd-107">È possibile utilizzare il pannello di controllo di Lync Server per configurare le route delle aree di rete.</span><span class="sxs-lookup"><span data-stu-id="127fd-107">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="127fd-108">Dal pannello di controllo di Lync Server, è possibile creare, modificare o eliminare una route area di rete.</span><span class="sxs-lookup"><span data-stu-id="127fd-108">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="127fd-109">Utilizzare questo argomento per creare o modificare una nuova route area di rete.</span><span class="sxs-lookup"><span data-stu-id="127fd-109">Use this topic to create or modify a network region route.</span></span> <span data-ttu-id="127fd-110">Per informazioni dettagliate sull'eliminazione di una route area di rete esistente, vedere [eliminazione delle route delle aree di rete esistenti in Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).</span><span class="sxs-lookup"><span data-stu-id="127fd-110">For details about deleting an existing network region routes, see [Deleting existing network region routes in Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).</span></span>

<div>

## <a name="to-create-a-network-region-route"></a><span data-ttu-id="127fd-111">Per creare una route area di rete</span><span class="sxs-lookup"><span data-stu-id="127fd-111">To create a network region route</span></span>

1.  <span data-ttu-id="127fd-112">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="127fd-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="127fd-113">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="127fd-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="127fd-114">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="127fd-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="127fd-115">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Route area**.</span><span class="sxs-lookup"><span data-stu-id="127fd-115">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="127fd-116">Nella pagina **Route area** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="127fd-116">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="127fd-117">In **Nuova route area** digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="127fd-117">In **New Region Route**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="127fd-118">Questo valore deve essere univoco all'interno della distribuzione di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="127fd-118">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="127fd-119">Nell'elenco a discesa **area di rete \# 1** Selezionare una delle due aree geografiche da connettere tramite questa route.</span><span class="sxs-lookup"><span data-stu-id="127fd-119">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="127fd-120">Nell'elenco a discesa **area di rete \# 2** Selezionare l'altra area per la route.</span><span class="sxs-lookup"><span data-stu-id="127fd-120">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="127fd-121">Questa area deve essere diversa dall'area selezionata per l'area di rete \# 1.</span><span class="sxs-lookup"><span data-stu-id="127fd-121">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="127fd-p104">Utilizzare la casella di riepilogo **Collegamenti aree di rete** per aggiungere collegamenti area di rete alla route. Fare clic sul pulsante **Aggiungi** per visualizzare la pagina **Collegamento area**. Fare clic su un collegamento area da aggiungere alla route e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="127fd-p104">Use the **Network region links** list box to add region links to the route. Click the **Add** button to display the **Region Link** page. Click a region link to add to this route, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="127fd-125">Continuare a fare clic sul pulsante <STRONG>Aggiungi</STRONG> per aggiungere altri collegamenti oppure selezionare un collegamento e fare clic su <STRONG>Rimuovi</STRONG> per rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="127fd-125">Continue to click the <STRONG>Add</STRONG> button to add more links, or select a link and click <STRONG>Remove</STRONG> to remove a link.</span></span>

    
    </div>

9.  <span data-ttu-id="127fd-126">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="127fd-126">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-route"></a><span data-ttu-id="127fd-127">Per modificare una route area di rete</span><span class="sxs-lookup"><span data-stu-id="127fd-127">To modify a network region route</span></span>

1.  <span data-ttu-id="127fd-128">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="127fd-128">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="127fd-129">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="127fd-129">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="127fd-130">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="127fd-130">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="127fd-131">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Route area**.</span><span class="sxs-lookup"><span data-stu-id="127fd-131">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="127fd-132">Nella pagina **Route area** fare clic sulla route area che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="127fd-132">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="127fd-133">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="127fd-133">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="127fd-134">In **Modifica route area** è possibile modificare le aree unite dalla route e i collegamenti area associati alla route.</span><span class="sxs-lookup"><span data-stu-id="127fd-134">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="127fd-135">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="127fd-135">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="127fd-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="127fd-136">See Also</span></span>


[<span data-ttu-id="127fd-137">Eliminazione delle route delle aree di rete esistenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="127fd-137">Deleting existing network region routes in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

