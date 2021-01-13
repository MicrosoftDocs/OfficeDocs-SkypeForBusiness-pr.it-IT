---
title: Monitorare il servizio per dispositivi mobili e l'utilizzo di UCWA in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Sintesi: gestire il servizio per dispositivi mobili (MCX) e Unified Communications Web API (UCWA) in Skype for Business Server.'
ms.openlocfilehash: 76bcf8727d3abbb417595f033ce9a59ec00a39ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814246"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="b5c70-103">Monitorare il servizio per dispositivi mobili e l'utilizzo di UCWA in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b5c70-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="b5c70-104">**Riepilogo:** Gestire il servizio per dispositivi mobili (MCX) e Unified Communications Web API (UCWA) in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b5c70-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="b5c70-105">Il supporto di MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b5c70-105">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="b5c70-106">Tutti i client per dispositivi mobili Skype for business corrente utilizzano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti.</span><span class="sxs-lookup"><span data-stu-id="b5c70-106">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="b5c70-107">Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.</span><span class="sxs-lookup"><span data-stu-id="b5c70-107">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="b5c70-108">Su base continuativa, è consigliabile monitorare la CPU e la memoria utilizzata da Skype for Business Server Mobility Service (MCX) e Unified Communications Web API (UCWA).</span><span class="sxs-lookup"><span data-stu-id="b5c70-108">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="b5c70-109">Per monitorare l'utilizzo, è possibile utilizzare gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5c70-109">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="b5c70-110">**Per Unified Communications Web API (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="b5c70-110">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="b5c70-111">Il processo di lavoro di **LyncUcwa** in Gestione Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="b5c70-111">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="b5c70-112">Nel riquadro **Processi di lavoro** analizzare le colonne **% CPU** e **Byte privati (KB)** (memoria).</span><span class="sxs-lookup"><span data-stu-id="b5c70-112">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="b5c70-113">Contatori delle prestazioni relativi a **CPU** e **Processore**.</span><span class="sxs-lookup"><span data-stu-id="b5c70-113">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="b5c70-114">Per la maggior parte delle distribuzioni, l'utilizzo della CPU UCWA dovrebbe essere inferiore al 15% in media.</span><span class="sxs-lookup"><span data-stu-id="b5c70-114">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="b5c70-115">L'utilizzo della memoria deve rientrare nei limiti descritti in [Monitor per i limiti di capacità della memoria del server in Skype for Business Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="b5c70-115">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="b5c70-116">Oltre ai contatori di utilizzo della CPU e della memoria, è possibile utilizzare i contatori delle prestazioni seguenti per determinare quando un server è sottoposto a overload con richieste:</span><span class="sxs-lookup"><span data-stu-id="b5c70-116">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="b5c70-117">**Ls: richieste di limitazione Web e Authentication\WEB-totale nell'elaborazione**, che indica il numero di richieste Web in sospeso sul server.</span><span class="sxs-lookup"><span data-stu-id="b5c70-117">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="b5c70-118">Quando questo contatore raggiunge 10.000, le richieste successive avranno esito negativo, con il messaggio di errore "503-servizio non disponibile".</span><span class="sxs-lookup"><span data-stu-id="b5c70-118">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="b5c70-119">**ASP.NET\Requests Queued** (deve essere sempre zero).</span><span class="sxs-lookup"><span data-stu-id="b5c70-119">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="b5c70-120">Se si soddisfano o superano questi valori, è consigliabile rivisitare e ricalcolare la pianificazione della capacità per il corretto dimensionamento della CPU, il numero di core e la memoria dei computer che ospitano i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="b5c70-120">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="b5c70-121">**Per il servizio per dispositivi mobili (MCX):**</span><span class="sxs-lookup"><span data-stu-id="b5c70-121">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="b5c70-122">I processi di lavoro di **CSIntMcxAppPool** e **CSExtMcxAppPool** in Gestione Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="b5c70-122">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="b5c70-123">Nel riquadro **Processi di lavoro** analizzare le colonne **% CPU** e **Byte privati (KB)** (memoria).</span><span class="sxs-lookup"><span data-stu-id="b5c70-123">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="b5c70-124">Contatori delle prestazioni relativi a **CPU** e **Processore**.</span><span class="sxs-lookup"><span data-stu-id="b5c70-124">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="b5c70-125">Per la maggior parte delle distribuzioni, l'utilizzo della CPU del servizio per dispositivi mobili deve essere inferiore al 15%, in media.</span><span class="sxs-lookup"><span data-stu-id="b5c70-125">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="b5c70-126">L'utilizzo della memoria deve rientrare nei limiti descritti in [Monitor per i limiti di capacità della memoria del server in Skype for Business Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="b5c70-126">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="b5c70-127">Oltre ai contatori di utilizzo della CPU e della memoria, è possibile utilizzare il contatori delle prestazioni ASP.NET seguenti per determinare quando un server è sovraccarico di richieste:</span><span class="sxs-lookup"><span data-stu-id="b5c70-127">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="b5c70-128">**ASP.NET v2.0.50727\Requests Current**, che indica il numero di richieste Web in sospeso nel server.</span><span class="sxs-lookup"><span data-stu-id="b5c70-128">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="b5c70-129">Quando questo contatore raggiunge 5.000, le richieste successive avranno esito negativo con il messaggio di errore "503-servizio non disponibile".</span><span class="sxs-lookup"><span data-stu-id="b5c70-129">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="b5c70-130">**ASP.NET\Requests Queued** (deve essere sempre zero).</span><span class="sxs-lookup"><span data-stu-id="b5c70-130">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="b5c70-131">Se si soddisfano o superano questi valori, è consigliabile rivisitare e ricalcolare la pianificazione della capacità per il corretto dimensionamento della CPU, del numero di core e della memoria per i computer che ospitano i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="b5c70-131">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="b5c70-132">Il supporto di MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b5c70-132">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="b5c70-133">Tutti i client per dispositivi mobili Skype for business corrente utilizzano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti.</span><span class="sxs-lookup"><span data-stu-id="b5c70-133">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="b5c70-134">Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.</span><span class="sxs-lookup"><span data-stu-id="b5c70-134">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b5c70-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5c70-135">See also</span></span>

[<span data-ttu-id="b5c70-136">Monitorare i limiti di capacità della memoria del server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b5c70-136">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
