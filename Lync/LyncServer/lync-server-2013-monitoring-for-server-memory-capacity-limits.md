---
title: 'Lync Server 2013: monitoraggio dei limiti di capacità della memoria del server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring for server memory capacity limits
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689982(v=OCS.15)
ms:contentKeyID: 48183506
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46580950c30326bb9852abc5ecb2a165398b3587
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a><span data-ttu-id="2a5a0-102">Monitoraggio dei limiti di capacità della memoria del server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a5a0-102">Monitoring for server memory capacity limits in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a5a0-103">_**Ultimo argomento modificato:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="2a5a0-103">_**Topic Last Modified:** 2016-12-08_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> <span data-ttu-id="2a5a0-104">Le informazioni contenute in questo argomento che si riferiscono alla pianificazione della capacità riguardano solo i client mobili Lync 2010 e il servizio di mobilità (MCX).</span><span class="sxs-lookup"><span data-stu-id="2a5a0-104">The information in this topic that refers to Capacity Planning pertains only to Lync 2010 Mobile clients and the Mobility Service (Mcx).</span></span> <span data-ttu-id="2a5a0-105">La pianificazione della capacità per Unified Communications Web API (UCWA), utilizzata dai client per dispositivi mobili Lync 2013, viene fornita da Lync Server 2013, strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="2a5a0-105">Capacity Planning for the Unified Communications Web API (UCWA), used by the Lync 2013 Mobile clients, is provided by the Lync Server 2013, Planning Tool.</span></span>



</div>

<span data-ttu-id="2a5a0-106">Due contatori delle prestazioni per dispositivi mobili consentono di determinare l'utilizzo corrente e di pianificare la capacità per il servizio per dispositivi mobili di Lync Server 2013 (MCX), nonché di monitorare l'utilizzo della memoria per UCWA.</span><span class="sxs-lookup"><span data-stu-id="2a5a0-106">Two mobility performance counters can help you to determine your current usage and help you plan capacity for the Lync Server 2013 Mobility Service (Mcx), as well as to monitor memory usage for UCWA.</span></span> <span data-ttu-id="2a5a0-107">Per UCWA, la categoria del contatore è **ls: Web – UCWA**.</span><span class="sxs-lookup"><span data-stu-id="2a5a0-107">For UCWA, the counter category is **LS:WEB – UCWA**.</span></span> <span data-ttu-id="2a5a0-108">Per il servizio per dispositivi mobili (MCX), i contatori sono sotto la categoria **ls: Web-Mobile Communication Service**.</span><span class="sxs-lookup"><span data-stu-id="2a5a0-108">For the Mobility Service (Mcx), the counters are under the category **LS:WEB - Mobile Communication Service**.</span></span> <span data-ttu-id="2a5a0-109">I contatori da monitorare sono:</span><span class="sxs-lookup"><span data-stu-id="2a5a0-109">The counters to monitor are:</span></span>

  - <span data-ttu-id="2a5a0-110">**Conteggio delle sessioni attivo con gli abbonamenti alla presenza attiva**, ovvero il numero corrente di endpoint registrati tramite UCWA o il servizio per dispositivi mobili (MCX) che dispongono di sottoscrizioni di presenza attiva (numero di utenti mobili sempre connessi)</span><span class="sxs-lookup"><span data-stu-id="2a5a0-110">**Currently Active Session Count with Active Presence Subscriptions**, which is the current number of endpoints registered through UCWA or the Mobility Service (Mcx) that have active presence subscriptions (number of always-connected mobile users)</span></span>

  - <span data-ttu-id="2a5a0-111">**Conteggio delle sessioni attivo**, ovvero il numero corrente di endpoint registrati tramite UCWA o il servizio per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="2a5a0-111">**Currently Active Session Count**, which is the current number of endpoints registered through UCWA or the Mobility Service</span></span>

<span data-ttu-id="2a5a0-112">Se la differenza tra il **conteggio delle sessioni attive con gli abbonamenti alla presenza attiva** e il numero di **sessioni** attivo è di dimensioni ridotte nel tempo, significa che la maggior parte degli utenti di dispositivi mobili ha un dispositivo sempre connesso, ad esempio un dispositivo mobile Android o Nokia (solo per MCX).</span><span class="sxs-lookup"><span data-stu-id="2a5a0-112">If the difference between **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** is small over time, this means that most mobile device users have an always-connected device, such as an Android or Nokia mobile device (for Mcx only).</span></span> <span data-ttu-id="2a5a0-113">I dispositivi sempre connessi di UCWA includono i dispositivi Apple e Android che eseguono client mobili Lync 2013).</span><span class="sxs-lookup"><span data-stu-id="2a5a0-113">UCWA always-connected devices include Apple and Android devices running Lync 2013 Mobile clients).</span></span> <span data-ttu-id="2a5a0-114">Se il **numero di sessioni attualmente** attivo è molto più alto rispetto **al numero di sessioni attivo corrente con gli abbonamenti a presenza attiva**, ciò indica che più utenti utilizzano un dispositivo endpoint in background, ad esempio un dispositivo Apple iOS o Windows Phone in MCX.</span><span class="sxs-lookup"><span data-stu-id="2a5a0-114">If **Currently Active Session Count** is much higher than **Currently Active Session Count with Active Presence Subscriptions**, this indicates that more users are using a background endpoint device, such as an Apple iOS device or Windows Phone under Mcx.</span></span> <span data-ttu-id="2a5a0-115">(Windows Phone è l'unico client per dispositivi mobili Lync 2013 che registrerà questo tipo di registrazione).</span><span class="sxs-lookup"><span data-stu-id="2a5a0-115">(Windows Phone is the only Lync 2013 Mobile client that will register as this).</span></span>

<span data-ttu-id="2a5a0-116">È necessario impostare un limite per il **conteggio delle sessioni attivo con gli abbonamenti per la presenza attiva** e i contatori delle prestazioni del **conteggio delle sessioni** attivo in base all'utilizzo previsto, ai risultati della pianificazione della capacità e al monitoraggio continuo del servizio per dispositivi mobili e di altri contatori di front end server.</span><span class="sxs-lookup"><span data-stu-id="2a5a0-116">You should set a limit on the **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** performance counters based on your expected usage, capacity planning results, and ongoing monitoring of Mobility Service and other Front End Server counters.</span></span> <span data-ttu-id="2a5a0-117">I limiti impostati devono consentire di valutare la capacità del server e aumentare gli avvisi in caso di superamento della capacità.</span><span class="sxs-lookup"><span data-stu-id="2a5a0-117">The limits you set should enable you to evaluate server capacity and raise alerts when capacity is exceeded.</span></span>

<span data-ttu-id="2a5a0-118">Per determinare i limiti corretti, è necessario determinare in primo luogo la quantità di memoria disponibile nel front end server per il servizio per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="2a5a0-118">To determine the appropriate limits, you need to first determine how much memory is available on the Front End Server for the Mobility Service.</span></span> <span data-ttu-id="2a5a0-119">Monitorare i contatori per determinare quando è necessario pianificare la capacità aggiuntiva, in base alla formula seguente:</span><span class="sxs-lookup"><span data-stu-id="2a5a0-119">Monitor the counters to determine when you need to plan for extra capacity, according to the following formula:</span></span>

<span data-ttu-id="2a5a0-120">Memoria totale utilizzata dal servizio per dispositivi mobili MCX (MB) = 164 + (400 + 134)/ \* 1024 **Currently Active Session Count with Active Presence Subscriptions** + \* 400/1024 (**Currently Active Session Count** – **Currently Active Session Count with Active Presence Subscriptions**)</span><span class="sxs-lookup"><span data-stu-id="2a5a0-120">Total memory used by the Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024 \* **Currently Active Session Count with Active Presence Subscriptions** + 400 / 1024 \* (**Currently Active Session Count** – **Currently Active Session Count with Active Presence Subscriptions**)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2a5a0-121">Microsoft Lync Server 2010 capacity Calculator è un foglio di calcolo prepopolato con tutte le formule che consentono a un pianificatore di determinare quali saranno i requisiti per i server, tra cui CPU, memoria e disco rigido.</span><span class="sxs-lookup"><span data-stu-id="2a5a0-121">The Microsoft Lync Server 2010 Capacity Calculator is a spreadsheet that is prepopulated with all of the formulas that enable a planner to determine what the requirements will be for the servers, including CPU, memory, and hard drive.</span></span> <span data-ttu-id="2a5a0-122">È possibile scaricare il foglio di calcolo e un documento associato in:<A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span><span class="sxs-lookup"><span data-stu-id="2a5a0-122">You can download the spreadsheet and an associated document at: <A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span></span>



</div>

<span data-ttu-id="2a5a0-123">Il front end server deve disporre di memoria sufficiente per supportare il servizio per dispositivi mobili in situazioni di failover.</span><span class="sxs-lookup"><span data-stu-id="2a5a0-123">The Front End Server needs enough available memory to support the Mobility Service in failover situations.</span></span> <span data-ttu-id="2a5a0-124">È possibile monitorare la memoria disponibile corrente sul front end server utilizzando il contatore **memoria\\disponibile** per i MByte oppure utilizzando l'equazione citata in precedenza per pianificare la quantità di memoria che il servizio per dispositivi mobili deve utilizzare.</span><span class="sxs-lookup"><span data-stu-id="2a5a0-124">You can monitor the current available memory on the Front End Server by using the **Memory\\Available Mbytes** counter, or by using the equation mentioned earlier, to plan for the amount of memory that you expect the Mobility Service to use.</span></span>

<span data-ttu-id="2a5a0-125">Se la quantità di memoria disponibile nel front end server è inferiore a 1.500 MB quando si pianifica il numero previsto di utenti di dispositivi mobili, è necessario aggiungere altro hardware per supportare il servizio per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="2a5a0-125">If the amount of memory available on the Front End Server is lower than 1,500 MB when you plan for the expected number of mobility users, you need to add more hardware to support the Mobility Service.</span></span> <span data-ttu-id="2a5a0-126">Per ulteriori informazioni, vedere [monitoraggio dei dispositivi mobili per le prestazioni in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="2a5a0-126">For more details, see [Monitoring mobility for performance in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) in the Operations documentation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="2a5a0-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a5a0-127">See Also</span></span>


[<span data-ttu-id="2a5a0-128">Monitoraggio della mobilità per le prestazioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a5a0-128">Monitoring mobility for performance in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

