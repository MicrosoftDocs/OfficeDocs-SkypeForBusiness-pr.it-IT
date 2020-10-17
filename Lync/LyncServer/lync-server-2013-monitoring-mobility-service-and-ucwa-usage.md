---
title: 'Lync Server 2013: monitoraggio del servizio per dispositivi mobili e utilizzo di UCWA'
description: 'Lync Server 2013: monitoraggio del servizio per dispositivi mobili e utilizzo di UCWA.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Mobility Service and UCWA usage
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48184683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6575941faf904e46cd1f66d7226a16c88e8cbaa3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548112"
---
# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a><span data-ttu-id="fc0e4-103">Monitoraggio del servizio per dispositivi mobili e utilizzo di UCWA in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc0e4-103">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc0e4-104">_**Ultimo argomento modificato:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="fc0e4-104">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="fc0e4-105">Per una base continuativa, è consigliabile monitorare la CPU e la memoria utilizzata da Lync Server Mobility Service (MCX) e Unified Communications Web API (UCWA).</span><span class="sxs-lookup"><span data-stu-id="fc0e4-105">On an ongoing basis, you should monitor the CPU and memory that is used by the Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="fc0e4-106">Per monitorare l'utilizzo, è possibile utilizzare gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="fc0e4-106">To monitor usage, you can use the following:</span></span>

<span data-ttu-id="fc0e4-107">**Per Unified Communications Web API (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="fc0e4-107">**For Unified Communications Web API (UCWA):**</span></span>

  - <span data-ttu-id="fc0e4-108">Il processo di lavoro di **LyncUcwa** in Gestione Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="fc0e4-108">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="fc0e4-109">Nel riquadro **Processi di lavoro** analizzare le colonne **% CPU** e **Byte privati (KB)** (memoria).</span><span class="sxs-lookup"><span data-stu-id="fc0e4-109">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="fc0e4-110">Contatori delle prestazioni relativi a **CPU** e **Processore**.</span><span class="sxs-lookup"><span data-stu-id="fc0e4-110">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="fc0e4-111">Per la maggior parte delle distribuzioni, l'utilizzo della CPU UCWA dovrebbe essere inferiore al 15% in media.</span><span class="sxs-lookup"><span data-stu-id="fc0e4-111">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="fc0e4-112">L'utilizzo della memoria deve rientrare nei limiti descritti in [monitoraggio dei limiti di capacità della memoria del server in Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="fc0e4-112">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="fc0e4-113">Oltre ai contatori di utilizzo della CPU e della memoria, è possibile utilizzare i contatori delle prestazioni seguenti per determinare quando un server è sottoposto a overload con richieste:</span><span class="sxs-lookup"><span data-stu-id="fc0e4-113">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="fc0e4-114">**Ls: Web – limitazione e autenticazione \\ WEB: Totale richieste di elaborazione**, che indica il numero di richieste Web in sospeso sul server.</span><span class="sxs-lookup"><span data-stu-id="fc0e4-114">**LS:WEB – Throttling and Authentication\\WEB – Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="fc0e4-115">Quando questo contatore raggiunge 10.000, le richieste successive avranno esito negativo, con il messaggio di errore "503-servizio non disponibile".</span><span class="sxs-lookup"><span data-stu-id="fc0e4-115">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="fc0e4-116">**ASP.NET \\ Richieste in coda** (dovrebbe essere sempre zero).</span><span class="sxs-lookup"><span data-stu-id="fc0e4-116">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fc0e4-117">Se si soddisfano o superano questi valori, è consigliabile rivisitare e ricalcolare la pianificazione della capacità per il corretto dimensionamento della CPU, il numero di core e la memoria dei computer che ospitano i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="fc0e4-117">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the Web services.</span></span>



</div>

<span data-ttu-id="fc0e4-118">**Per il servizio per dispositivi mobili (MCX):**</span><span class="sxs-lookup"><span data-stu-id="fc0e4-118">**For the Mobility Service (Mcx):**</span></span>

  - <span data-ttu-id="fc0e4-119">I processi di lavoro di **CSIntMcxAppPool** e **CSExtMcxAppPool** in Gestione Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="fc0e4-119">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="fc0e4-120">Nel riquadro **Processi di lavoro** analizzare le colonne **% CPU** e **Byte privati (KB)** (memoria).</span><span class="sxs-lookup"><span data-stu-id="fc0e4-120">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="fc0e4-121">Contatori delle prestazioni relativi a **CPU** e **Processore**.</span><span class="sxs-lookup"><span data-stu-id="fc0e4-121">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="fc0e4-122">Per la maggior parte delle distribuzioni, l'utilizzo della CPU del servizio per dispositivi mobili deve essere inferiore al 15%, in media.</span><span class="sxs-lookup"><span data-stu-id="fc0e4-122">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="fc0e4-123">L'utilizzo della memoria deve rientrare nei limiti descritti in [monitoraggio dei limiti di capacità della memoria del server in Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="fc0e4-123">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="fc0e4-124">Oltre ai contatori di utilizzo della CPU e della memoria, è possibile utilizzare il contatori delle prestazioni ASP.NET seguenti per determinare quando un server è sovraccarico di richieste:</span><span class="sxs-lookup"><span data-stu-id="fc0e4-124">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="fc0e4-125">**ASP.NET v 2.0.50727 \\ Richieste Current**, che indica il numero di richieste Web in sospeso sul server.</span><span class="sxs-lookup"><span data-stu-id="fc0e4-125">**ASP.NET v2.0.50727\\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="fc0e4-126">Quando questo contatore raggiunge 5.000, le richieste successive avranno esito negativo con il messaggio di errore "503-servizio non disponibile".</span><span class="sxs-lookup"><span data-stu-id="fc0e4-126">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="fc0e4-127">**ASP.NET \\ Richieste in coda** (dovrebbe essere sempre zero).</span><span class="sxs-lookup"><span data-stu-id="fc0e4-127">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fc0e4-128">Se si soddisfano o superano questi valori, è consigliabile rivisitare e ricalcolare la pianificazione della capacità per il corretto dimensionamento della CPU, del numero di core e della memoria per i computer che ospitano i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="fc0e4-128">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the Web services.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fc0e4-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc0e4-129">See Also</span></span>


[<span data-ttu-id="fc0e4-130">Monitoraggio dei limiti di capacità della memoria del server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc0e4-130">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

