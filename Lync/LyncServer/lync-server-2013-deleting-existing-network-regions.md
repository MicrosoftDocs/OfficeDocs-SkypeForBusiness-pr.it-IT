---
title: 'Lync Server 2013: eliminazione di aree di rete esistenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network regions
ms:assetid: c7293a2f-2b49-4c4a-903f-f7edcea2bc5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721882(v=OCS.15)
ms:contentKeyID: 49733815
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3a1c1e697e681eec4886dca9e942d9bc133b0f5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525403"
---
# <a name="deleting-existing-network-regions-in-lync-server-2013"></a><span data-ttu-id="f9908-102">Eliminazione di aree di rete esistenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9908-102">Deleting existing network regions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9908-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f9908-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f9908-104">Un'area di rete interconnette diverse parti di una rete dislocate su più aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="f9908-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="f9908-105">Ogni area di rete deve essere associata a un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="f9908-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="f9908-106">Il sito centrale è il sito del data center in cui è in esecuzione il servizio dei criteri di larghezza di banda del controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="f9908-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="f9908-107">È possibile utilizzare il pannello di controllo di Lync Server per configurare le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="f9908-107">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="f9908-108">Queste includono impostazioni che determinano se consentire percorsi alternativi Internet per le connessioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="f9908-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="f9908-109">Dal pannello di controllo di Lync Server, è possibile creare, modificare o eliminare un'area di rete.</span><span class="sxs-lookup"><span data-stu-id="f9908-109">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="f9908-110">Utilizzare questo argomento per eliminare le aree di rete esistenti.</span><span class="sxs-lookup"><span data-stu-id="f9908-110">Use this topic to delete existing network regions.</span></span> <span data-ttu-id="f9908-111">Per informazioni dettagliate sulla creazione o la modifica delle aree di rete esistenti, vedere [creazione o modifica di aree di rete in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span><span class="sxs-lookup"><span data-stu-id="f9908-111">For details about creating or modifying existing network regions, see [Creating or modifying network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span></span>

<div>

## <a name="to-delete-a-network-region"></a><span data-ttu-id="f9908-112">Per eliminare un'area di rete</span><span class="sxs-lookup"><span data-stu-id="f9908-112">To delete a network region</span></span>

1.  <span data-ttu-id="f9908-113">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="f9908-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f9908-114">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f9908-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f9908-115">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f9908-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f9908-116">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Area**.</span><span class="sxs-lookup"><span data-stu-id="f9908-116">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="f9908-117">Nella pagina **Area** fare clic sull'area che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="f9908-117">On the **Region** page, click the region you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f9908-p103">È possibile eliminare più aree contemporaneamente. A tale scopo, premere CTRL e selezionare più aree tenendo premuto CTRL. Per selezionare tutte le aree, scegliere <STRONG>Seleziona tutto</STRONG> dal menu <STRONG>Modifica</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f9908-p103">You can delete more than one region at a time. To do this, press CTRL and select multiple regions while holding down the CTRL key. Or, to select all regions, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="f9908-121">Scegliere **Elimina** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="f9908-121">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="f9908-122">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f9908-122">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="f9908-p104">Non è possibile rimuovere un'area di rete se è associata a un sito di rete. Se si tenta di rimuovere un'area associata a un sito, verrà visualizzato un messaggio di errore. Per scoprire se un'area è associata a siti, selezionare l'area e quindi scegliere <STRONG>Mostra dettagli</STRONG> dal menu <STRONG>Modifica</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f9908-p104">A network region cannot be removed if it is associated with a network site. If you attempt to remove a region associated with a site you will receive an error message. To see if a region is associated with any sites, select the region and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f9908-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9908-126">See Also</span></span>


[<span data-ttu-id="f9908-127">Creazione o modifica di aree di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9908-127">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

