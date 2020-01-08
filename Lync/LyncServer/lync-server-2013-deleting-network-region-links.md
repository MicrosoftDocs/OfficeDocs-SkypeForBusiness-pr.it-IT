---
title: "Lync Server 2013: eliminazione di collegamenti all'area di rete"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting network region links
ms:assetid: 839273cd-d23f-4b38-84e6-d2dc972f49cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688114(v=OCS.15)
ms:contentKeyID: 49733712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a097626f6e5eb5de8e3503baab0f1ab9ce462549
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-region-links-in-lync-server-2013"></a><span data-ttu-id="3c767-102">Eliminazione di collegamenti all'area di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c767-102">Deleting network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c767-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3c767-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3c767-104">È possibile configurare i collegamenti tra due aree di rete nell'ambito del controllo di ammissione di chiamata (CAC).</span><span class="sxs-lookup"><span data-stu-id="3c767-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="3c767-105">Le aree all'interno di una rete sono collegate tramite connettività WAN (Physical Wide Area Network).</span><span class="sxs-lookup"><span data-stu-id="3c767-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="3c767-106">È possibile usare il pannello di controllo di Lync Server per eliminare un collegamento esistente tra due aree di rete.</span><span class="sxs-lookup"><span data-stu-id="3c767-106">You can use the Lync Server Control Panel to delete an existing link between two network regions.</span></span> <span data-ttu-id="3c767-107">Per informazioni dettagliate su come creare o modificare il collegamento all'area di rete, vedere [configurazione dei collegamenti all'area di rete in Lync Server 2013](lync-server-2013-configuring-network-region-links.md)</span><span class="sxs-lookup"><span data-stu-id="3c767-107">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md)</span></span>

<div>

## <a name="to-delete-a-network-region-link"></a><span data-ttu-id="3c767-108">Per eliminare un collegamento all'area di rete</span><span class="sxs-lookup"><span data-stu-id="3c767-108">To delete a network region link</span></span>

1.  <span data-ttu-id="3c767-109">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="3c767-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3c767-110">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3c767-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3c767-111">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3c767-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3c767-112">Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su collegamento all' **area geografica**.</span><span class="sxs-lookup"><span data-stu-id="3c767-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="3c767-113">Nella pagina **collegamento all'area geografica** fare clic sul collegamento all'area che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="3c767-113">On the **Region Link** page, click the region link that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3c767-114">Puoi eliminare più di un collegamento all'area geografica alla volta.</span><span class="sxs-lookup"><span data-stu-id="3c767-114">You can delete more than one region link at a time.</span></span> <span data-ttu-id="3c767-115">Per eseguire questa operazione, premere CTRL e selezionare più collegamenti all'area geografica tenendo premuto CTRL.</span><span class="sxs-lookup"><span data-stu-id="3c767-115">To do this, press CTRL and select multiple region links while holding down the CTRL key.</span></span> <span data-ttu-id="3c767-116">In alternativa, per selezionare tutti i collegamenti all'area geografica, fare clic su <STRONG>Seleziona tutto</STRONG> dal menu <STRONG>modifica</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="3c767-116">Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="3c767-117">Scegliere **Elimina**dal menu **modifica** .</span><span class="sxs-lookup"><span data-stu-id="3c767-117">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="3c767-118">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3c767-118">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3c767-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c767-119">See Also</span></span>


[<span data-ttu-id="3c767-120">Configurazione di collegamenti all'area di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c767-120">Configuring network region links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-region-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

