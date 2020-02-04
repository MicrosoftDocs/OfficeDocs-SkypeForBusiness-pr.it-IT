---
title: 'Lync Server 2013: monitoraggio dei limiti della capacità di memoria del server'
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
ms.openlocfilehash: e5c9746240335b1c66606da24edf6ffa2a0e7bda
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a><span data-ttu-id="6133d-102">Monitoraggio dei limiti della capacità di memoria del server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6133d-102">Monitoring for server memory capacity limits in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6133d-103">_**Argomento Ultima modifica:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="6133d-103">_**Topic Last Modified:** 2016-12-08_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> <span data-ttu-id="6133d-104">Le informazioni contenute in questo argomento che fanno riferimento alla pianificazione della capacità riguardano solo i client mobili Lync 2010 e il servizio mobilità (MCX).</span><span class="sxs-lookup"><span data-stu-id="6133d-104">The information in this topic that refers to Capacity Planning pertains only to Lync 2010 Mobile clients and the Mobility Service (Mcx).</span></span> <span data-ttu-id="6133d-105">La pianificazione della capacità per Unified Communications Web API (UCWA), usata dai client per dispositivi mobili Lync 2013, è fornita da Lync Server 2013, strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="6133d-105">Capacity Planning for the Unified Communications Web API (UCWA), used by the Lync 2013 Mobile clients, is provided by the Lync Server 2013, Planning Tool.</span></span>



</div>

<span data-ttu-id="6133d-106">Due contatori delle prestazioni della mobilità possono aiutare a determinare l'uso corrente e ad aiutarti a pianificare la capacità per il servizio di mobilità di Lync Server 2013 (MCX), nonché a monitorare l'uso della memoria per UCWA.</span><span class="sxs-lookup"><span data-stu-id="6133d-106">Two mobility performance counters can help you to determine your current usage and help you plan capacity for the Lync Server 2013 Mobility Service (Mcx), as well as to monitor memory usage for UCWA.</span></span> <span data-ttu-id="6133d-107">Per UCWA, la categoria contatore è **ls: Web – UCWA**.</span><span class="sxs-lookup"><span data-stu-id="6133d-107">For UCWA, the counter category is **LS:WEB – UCWA**.</span></span> <span data-ttu-id="6133d-108">Per il servizio mobilità (MCX), i contatori sono sotto la categoria **ls: Web-servizio di comunicazione mobile**.</span><span class="sxs-lookup"><span data-stu-id="6133d-108">For the Mobility Service (Mcx), the counters are under the category **LS:WEB - Mobile Communication Service**.</span></span> <span data-ttu-id="6133d-109">I contatori da monitorare sono:</span><span class="sxs-lookup"><span data-stu-id="6133d-109">The counters to monitor are:</span></span>

  - <span data-ttu-id="6133d-110">**Conteggio delle sessioni attualmente attivo con gli abbonamenti alla presenza attiva**, ovvero il numero corrente di endpoint registrati tramite UCWA o il servizio di mobilità (MCX) con abbonamenti alla presenza attiva (numero di utenti di dispositivi mobili sempre connessi)</span><span class="sxs-lookup"><span data-stu-id="6133d-110">**Currently Active Session Count with Active Presence Subscriptions**, which is the current number of endpoints registered through UCWA or the Mobility Service (Mcx) that have active presence subscriptions (number of always-connected mobile users)</span></span>

  - <span data-ttu-id="6133d-111">**Conteggio delle sessioni attualmente attivo**, ovvero il numero corrente di endpoint registrati tramite UCWA o il servizio mobilità</span><span class="sxs-lookup"><span data-stu-id="6133d-111">**Currently Active Session Count**, which is the current number of endpoints registered through UCWA or the Mobility Service</span></span>

<span data-ttu-id="6133d-112">Se la differenza tra il **conteggio delle sessioni attive con gli abbonamenti alla presenza attiva** e il conteggio delle **sessioni** attive è ridotta nel tempo, significa che la maggior parte degli utenti di dispositivi mobili ha un dispositivo sempre connesso, ad esempio un dispositivo mobile Android o Nokia (solo per MCX).</span><span class="sxs-lookup"><span data-stu-id="6133d-112">If the difference between **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** is small over time, this means that most mobile device users have an always-connected device, such as an Android or Nokia mobile device (for Mcx only).</span></span> <span data-ttu-id="6133d-113">I dispositivi UCWA sempre connessi includono dispositivi Apple e Android con client mobili Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="6133d-113">UCWA always-connected devices include Apple and Android devices running Lync 2013 Mobile clients).</span></span> <span data-ttu-id="6133d-114">Se il **conteggio delle sessioni attualmente attivo** è molto più elevato del **conteggio delle sessioni attive con gli abbonamenti alla presenza attiva**, questo indica che più utenti usano un dispositivo endpoint in background, ad esempio un dispositivo iOS di Apple o un Windows Phone in MCX.</span><span class="sxs-lookup"><span data-stu-id="6133d-114">If **Currently Active Session Count** is much higher than **Currently Active Session Count with Active Presence Subscriptions**, this indicates that more users are using a background endpoint device, such as an Apple iOS device or Windows Phone under Mcx.</span></span> <span data-ttu-id="6133d-115">Windows Phone è l'unico client per dispositivi mobili Lync 2013 che verrà registrato come questo.</span><span class="sxs-lookup"><span data-stu-id="6133d-115">(Windows Phone is the only Lync 2013 Mobile client that will register as this).</span></span>

<span data-ttu-id="6133d-116">È necessario impostare un limite per il **conteggio delle sessioni attivo con gli abbonamenti alla presenza attiva** e i contatori delle prestazioni **attualmente attivi** , in base ai risultati previsti per l'uso, alla pianificazione della capacità e al monitoraggio continuo del servizio di mobilità e di altri contatori del server front-end.</span><span class="sxs-lookup"><span data-stu-id="6133d-116">You should set a limit on the **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** performance counters based on your expected usage, capacity planning results, and ongoing monitoring of Mobility Service and other Front End Server counters.</span></span> <span data-ttu-id="6133d-117">I limiti impostati devono consentire di valutare la capacità del server e generare avvisi quando viene superata la capacità.</span><span class="sxs-lookup"><span data-stu-id="6133d-117">The limits you set should enable you to evaluate server capacity and raise alerts when capacity is exceeded.</span></span>

<span data-ttu-id="6133d-118">Per determinare i limiti appropriati, è prima di tutto necessario determinare la quantità di memoria disponibile nel server front-end per il servizio di mobilità.</span><span class="sxs-lookup"><span data-stu-id="6133d-118">To determine the appropriate limits, you need to first determine how much memory is available on the Front End Server for the Mobility Service.</span></span> <span data-ttu-id="6133d-119">Monitorare i contatori per determinare quando è necessario pianificare la capacità aggiuntiva, in base alla formula seguente:</span><span class="sxs-lookup"><span data-stu-id="6133d-119">Monitor the counters to determine when you need to plan for extra capacity, according to the following formula:</span></span>

<span data-ttu-id="6133d-120">Memoria totale usata dal servizio di mobilità di MCX (MB) = 164 + (400 + 134)/ \* 1024 **numero di sessione attualmente attivo con abbonamenti alla presenza attiva** + 400/1024 \* (numero di**sessione attivo corrente** - **conteggio sessioni attivo con abbonamenti alla presenza attiva**)</span><span class="sxs-lookup"><span data-stu-id="6133d-120">Total memory used by the Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024 \* **Currently Active Session Count with Active Presence Subscriptions** + 400 / 1024 \* (**Currently Active Session Count** – **Currently Active Session Count with Active Presence Subscriptions**)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6133d-121">Il calcolatore di capacità di Microsoft Lync Server 2010 è un foglio di calcolo precompilato con tutte le formule che consentono a un planner di determinare quali saranno i requisiti per i server, tra cui CPU, memoria e disco rigido.</span><span class="sxs-lookup"><span data-stu-id="6133d-121">The Microsoft Lync Server 2010 Capacity Calculator is a spreadsheet that is prepopulated with all of the formulas that enable a planner to determine what the requirements will be for the servers, including CPU, memory, and hard drive.</span></span> <span data-ttu-id="6133d-122">È possibile scaricare il foglio di calcolo e un documento associato in:<A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span><span class="sxs-lookup"><span data-stu-id="6133d-122">You can download the spreadsheet and an associated document at: <A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span></span>



</div>

<span data-ttu-id="6133d-123">Il server front-end richiede abbastanza memoria disponibile per supportare il servizio di mobilità in situazioni di failover.</span><span class="sxs-lookup"><span data-stu-id="6133d-123">The Front End Server needs enough available memory to support the Mobility Service in failover situations.</span></span> <span data-ttu-id="6133d-124">È possibile monitorare la memoria disponibile corrente sul server front-end usando il contatore **memoria\\disponibile MBytes** oppure usando l'equazione menzionata in precedenza per pianificare la quantità di memoria che si prevede venga usata dal servizio di mobilità.</span><span class="sxs-lookup"><span data-stu-id="6133d-124">You can monitor the current available memory on the Front End Server by using the **Memory\\Available Mbytes** counter, or by using the equation mentioned earlier, to plan for the amount of memory that you expect the Mobility Service to use.</span></span>

<span data-ttu-id="6133d-125">Se la quantità di memoria disponibile nel server front-end è inferiore a 1.500 MB quando si prevede il numero previsto di utenti della mobilità, è necessario aggiungere altro hardware per supportare il servizio di mobilità.</span><span class="sxs-lookup"><span data-stu-id="6133d-125">If the amount of memory available on the Front End Server is lower than 1,500 MB when you plan for the expected number of mobility users, you need to add more hardware to support the Mobility Service.</span></span> <span data-ttu-id="6133d-126">Per altri dettagli, vedere [monitoraggio della mobilità per le prestazioni in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) nella documentazione delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="6133d-126">For more details, see [Monitoring mobility for performance in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) in the Operations documentation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="6133d-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6133d-127">See Also</span></span>


[<span data-ttu-id="6133d-128">Monitoraggio della mobilità per le prestazioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6133d-128">Monitoring mobility for performance in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

