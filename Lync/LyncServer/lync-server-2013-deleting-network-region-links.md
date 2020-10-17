---
title: 'Lync Server 2013: eliminazione di collegamenti tra aree di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network region links
ms:assetid: 839273cd-d23f-4b38-84e6-d2dc972f49cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688114(v=OCS.15)
ms:contentKeyID: 49733712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c467d499b0a0c9a3e85884927aed8ab819467d61
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525343"
---
# <a name="deleting-network-region-links-in-lync-server-2013"></a><span data-ttu-id="99b50-102">Eliminazione di collegamenti delle aree di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99b50-102">Deleting network region links in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99b50-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="99b50-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="99b50-104">È possibile configurare i collegamenti tra due aree di rete nell'ambito del servizio Controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="99b50-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="99b50-105">Le aree di una rete sono collegate mediante una connettività WAN fisica.</span><span class="sxs-lookup"><span data-stu-id="99b50-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="99b50-106">È possibile utilizzare il pannello di controllo di Lync Server per eliminare un collegamento esistente tra due aree di rete.</span><span class="sxs-lookup"><span data-stu-id="99b50-106">You can use the Lync Server Control Panel to delete an existing link between two network regions.</span></span> <span data-ttu-id="99b50-107">Per informazioni dettagliate sulla creazione o la modifica di un collegamento area di rete, vedere [Configuring Network Region Links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md)</span><span class="sxs-lookup"><span data-stu-id="99b50-107">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md)</span></span>

<div>

## <a name="to-delete-a-network-region-link"></a><span data-ttu-id="99b50-108">Per eliminare un collegamento area di rete</span><span class="sxs-lookup"><span data-stu-id="99b50-108">To delete a network region link</span></span>

1.  <span data-ttu-id="99b50-109">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="99b50-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="99b50-110">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="99b50-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="99b50-111">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="99b50-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="99b50-112">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Collegamento area**.</span><span class="sxs-lookup"><span data-stu-id="99b50-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="99b50-113">Nella pagina **Collegamento area** fare clic sul collegamento area che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="99b50-113">On the **Region Link** page, click the region link that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="99b50-p103">È possibile eliminare più collegamenti aree contemporaneamente. A tale scopo, premere CTRL e selezionare più collegamenti aree tenendo premuto CTRL. Per selezionare tutti i collegamenti aree, scegliere <STRONG>Seleziona tutto</STRONG> dal menu <STRONG>Modifica</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="99b50-p103">You can delete more than one region link at a time. To do this, press CTRL and select multiple region links while holding down the CTRL key. Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="99b50-117">Scegliere **Elimina** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="99b50-117">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="99b50-118">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="99b50-118">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="99b50-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99b50-119">See Also</span></span>


[<span data-ttu-id="99b50-120">Configurazione di collegamenti tra aree di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99b50-120">Configuring network region links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-region-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

