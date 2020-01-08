---
title: 'Lync Server 2013: monitoraggio del servizio di mobilità e uso di UCWA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring Mobility Service and UCWA usage
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48184683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 758fef9e3f2c31bec88927c75b271808d5bbc43c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979467"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a><span data-ttu-id="71edd-102">Monitoraggio del servizio di mobilità e uso di UCWA in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71edd-102">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71edd-103">_**Argomento Ultima modifica:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="71edd-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="71edd-104">In modo continuo, dovresti monitorare la CPU e la memoria usata dal servizio di mobilità di Lync Server (MCX) e dall'API Web Unified Communications (UCWA).</span><span class="sxs-lookup"><span data-stu-id="71edd-104">On an ongoing basis, you should monitor the CPU and memory that is used by the Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="71edd-105">Per monitorare l'uso, è possibile usare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="71edd-105">To monitor usage, you can use the following:</span></span>

<span data-ttu-id="71edd-106">**Per Unified Communications Web API (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="71edd-106">**For Unified Communications Web API (UCWA):**</span></span>

  - <span data-ttu-id="71edd-107">Processo di lavoro di **LyncUcwa** in Gestione Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="71edd-107">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="71edd-108">Nel riquadro **processi di lavoro** esaminare le colonne **CPU%** e **private bytes (KB)** (memoria).</span><span class="sxs-lookup"><span data-stu-id="71edd-108">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="71edd-109">Contatori delle prestazioni della **CPU** e del **processore** .</span><span class="sxs-lookup"><span data-stu-id="71edd-109">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="71edd-110">Per la maggior parte delle distribuzioni, l'uso della CPU UCWA deve essere inferiore al 15% in media.</span><span class="sxs-lookup"><span data-stu-id="71edd-110">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="71edd-111">L'utilizzo della memoria deve rientrare nei limiti descritti in [monitoraggio dei limiti della capacità di memoria del server in Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="71edd-111">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="71edd-112">Oltre ai contatori di utilizzo della CPU e della memoria, è possibile usare i contatori delle prestazioni seguenti per determinare quando un server è in overload con le richieste:</span><span class="sxs-lookup"><span data-stu-id="71edd-112">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="71edd-113">**Ls: Web-limitazione e autenticazione\\Web-totale delle richieste di elaborazione**, che indica il numero di richieste Web in sospeso nel server.</span><span class="sxs-lookup"><span data-stu-id="71edd-113">**LS:WEB – Throttling and Authentication\\WEB – Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="71edd-114">Quando questo contatore raggiunge 10.000, le richieste successive avranno esito negativo, con il messaggio di errore "503-servizio non disponibile".</span><span class="sxs-lookup"><span data-stu-id="71edd-114">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="71edd-115">**Le\\richieste di ASP.NET in coda** (devono essere sempre pari a zero).</span><span class="sxs-lookup"><span data-stu-id="71edd-115">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="71edd-116">Se si soddisfano o superano questi valori, è necessario rivedere e ricalcolare la pianificazione della capacità per il dimensionamento corretto della CPU, il numero di core e la memoria per i computer che ospitano i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="71edd-116">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the Web services.</span></span>



</div>

<span data-ttu-id="71edd-117">**Per il servizio mobilità (MCX):**</span><span class="sxs-lookup"><span data-stu-id="71edd-117">**For the Mobility Service (Mcx):**</span></span>

  - <span data-ttu-id="71edd-118">Processi di lavoro di **CSIntMcxAppPool** e **CSExtMcxAppPool** in Gestione Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="71edd-118">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="71edd-119">Nel riquadro **processi di lavoro** esaminare le colonne **CPU%** e **private bytes (KB)** (memoria).</span><span class="sxs-lookup"><span data-stu-id="71edd-119">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="71edd-120">Contatori delle prestazioni della **CPU** e del **processore** .</span><span class="sxs-lookup"><span data-stu-id="71edd-120">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="71edd-121">Per la maggior parte delle distribuzioni, l'uso della CPU del servizio di mobilità deve essere inferiore al 15%, in media.</span><span class="sxs-lookup"><span data-stu-id="71edd-121">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="71edd-122">L'utilizzo della memoria deve rientrare nei limiti descritti in [monitoraggio dei limiti della capacità di memoria del server in Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="71edd-122">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="71edd-123">Oltre ai contatori di utilizzo della CPU e della memoria, è possibile usare i seguenti contatori delle prestazioni di ASP.NET per determinare quando un server è in overload con le richieste:</span><span class="sxs-lookup"><span data-stu-id="71edd-123">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="71edd-124">**ASP.NET v 2.0.50727\\richiede Current**, che indica il numero di richieste Web in sospeso nel server.</span><span class="sxs-lookup"><span data-stu-id="71edd-124">**ASP.NET v2.0.50727\\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="71edd-125">Quando questo contatore raggiunge 5.000, le richieste successive avranno esito negativo con il messaggio di errore "503-servizio non disponibile".</span><span class="sxs-lookup"><span data-stu-id="71edd-125">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="71edd-126">**Le\\richieste di ASP.NET in coda** (devono essere sempre pari a zero).</span><span class="sxs-lookup"><span data-stu-id="71edd-126">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="71edd-127">Se si soddisfano o superano questi valori, è necessario rivedere e ricalcolare la pianificazione della capacità per il dimensionamento corretto della CPU, del numero di core e della memoria per i computer che ospitano i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="71edd-127">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the Web services.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="71edd-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71edd-128">See Also</span></span>


[<span data-ttu-id="71edd-129">Monitoraggio dei limiti della capacità di memoria del server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71edd-129">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

