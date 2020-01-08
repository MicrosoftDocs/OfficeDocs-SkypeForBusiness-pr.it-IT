---
title: 'Lync Server 2013: eliminazione delle aree di rete esistenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting existing network regions
ms:assetid: c7293a2f-2b49-4c4a-903f-f7edcea2bc5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721882(v=OCS.15)
ms:contentKeyID: 49733815
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea9d08121a7d62d10b44f97ff46ff8d4a5ca129e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-regions-in-lync-server-2013"></a><span data-ttu-id="e6b7d-102">Eliminazione delle aree di rete esistenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6b7d-102">Deleting existing network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6b7d-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e6b7d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e6b7d-104">Un'area geografica di rete interconnette varie parti di una rete in più aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="e6b7d-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="e6b7d-105">Ogni area di rete deve essere associata a un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="e6b7d-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="e6b7d-106">Il sito centrale è il sito centro dati in cui è in uso il servizio criteri di larghezza di banda di controllo delle chiamate (CAC).</span><span class="sxs-lookup"><span data-stu-id="e6b7d-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="e6b7d-107">È possibile usare il pannello di controllo di Lync Server per configurare le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="e6b7d-107">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="e6b7d-108">Le aree di rete includono impostazioni che determinano se i percorsi alternativi tramite Internet sono consentiti per le connessioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="e6b7d-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="e6b7d-109">Dal pannello di controllo di Lync Server è possibile creare, modificare o eliminare un'area geografica di rete.</span><span class="sxs-lookup"><span data-stu-id="e6b7d-109">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="e6b7d-110">Usare questo argomento per eliminare le aree di rete esistenti.</span><span class="sxs-lookup"><span data-stu-id="e6b7d-110">Use this topic to delete existing network regions.</span></span> <span data-ttu-id="e6b7d-111">Per informazioni dettagliate sulla creazione o la modifica di aree di rete esistenti, vedere [creazione o modifica di aree di rete in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span><span class="sxs-lookup"><span data-stu-id="e6b7d-111">For details about creating or modifying existing network regions, see [Creating or modifying network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span></span>

<div>

## <a name="to-delete-a-network-region"></a><span data-ttu-id="e6b7d-112">Per eliminare un'area di rete</span><span class="sxs-lookup"><span data-stu-id="e6b7d-112">To delete a network region</span></span>

1.  <span data-ttu-id="e6b7d-113">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="e6b7d-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e6b7d-114">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e6b7d-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e6b7d-115">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e6b7d-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e6b7d-116">Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **area geografica**.</span><span class="sxs-lookup"><span data-stu-id="e6b7d-116">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="e6b7d-117">Nella pagina **area** fare clic sull'area che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="e6b7d-117">On the **Region** page, click the region you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e6b7d-118">Puoi eliminare più di un'area alla volta.</span><span class="sxs-lookup"><span data-stu-id="e6b7d-118">You can delete more than one region at a time.</span></span> <span data-ttu-id="e6b7d-119">A tale scopo, premere CTRL e selezionare più aree mentre si tiene premuto il tasto CTRL.</span><span class="sxs-lookup"><span data-stu-id="e6b7d-119">To do this, press CTRL and select multiple regions while holding down the CTRL key.</span></span> <span data-ttu-id="e6b7d-120">In alternativa, per selezionare tutte le aree geografiche, fare clic su <STRONG>Seleziona tutto</STRONG> dal menu <STRONG>modifica</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="e6b7d-120">Or, to select all regions, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="e6b7d-121">Scegliere **Elimina**dal menu **modifica** .</span><span class="sxs-lookup"><span data-stu-id="e6b7d-121">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="e6b7d-122">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6b7d-122">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="e6b7d-123">Un'area di rete non può essere rimossa se associata a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="e6b7d-123">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="e6b7d-124">Se si tenta di rimuovere un'area associata a un sito, viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="e6b7d-124">If you attempt to remove a region associated with a site you will receive an error message.</span></span> <span data-ttu-id="e6b7d-125">Per verificare se un'area è associata a qualsiasi sito, selezionare l'area geografica e quindi fare clic su <STRONG>Mostra dettagli</STRONG> dal menu <STRONG>modifica</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="e6b7d-125">To see if a region is associated with any sites, select the region and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e6b7d-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6b7d-126">See Also</span></span>


[<span data-ttu-id="e6b7d-127">Creazione o modifica di aree di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6b7d-127">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

