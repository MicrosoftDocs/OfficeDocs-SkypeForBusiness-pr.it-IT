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
description: 'Riepilogo: gestire il servizio per dispositivi mobili (Mcx) e Unified Communications Web API (UCWA) in Skype for Business Server.'
ms.openlocfilehash: 76bcf8727d3abbb417595f033ce9a59ec00a39ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814246"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="4aa88-103">Monitorare il servizio per dispositivi mobili e l'utilizzo di UCWA in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4aa88-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="4aa88-104">**Riepilogo:** Gestire il servizio per dispositivi mobili (Mcx) e Unified Communications Web API (UCWA) in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4aa88-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="4aa88-105">Il supporto MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4aa88-105">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="4aa88-106">Tutti i client mobili Skype for Business correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti.</span><span class="sxs-lookup"><span data-stu-id="4aa88-106">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="4aa88-107">Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.</span><span class="sxs-lookup"><span data-stu-id="4aa88-107">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="4aa88-108">Su base continuativa, è consigliabile monitorare la CPU e la memoria utilizzata dal servizio Per dispositivi mobili di Skype for Business Server (Mcx) e da Unified Communications Web API (UCWA).</span><span class="sxs-lookup"><span data-stu-id="4aa88-108">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="4aa88-109">Per monitorare l'utilizzo, è possibile utilizzare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="4aa88-109">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="4aa88-110">**Per UCWA (Unified Communications Web API):**</span><span class="sxs-lookup"><span data-stu-id="4aa88-110">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="4aa88-111">Processo **di lavoro LyncUcwa** in Gestione Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="4aa88-111">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="4aa88-112">Nel riquadro **Processi di lavoro** analizzare le colonne **% CPU** e **Byte privati (KB)** (memoria).</span><span class="sxs-lookup"><span data-stu-id="4aa88-112">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="4aa88-113">Contatori delle prestazioni relativi a **CPU** e **Processore**.</span><span class="sxs-lookup"><span data-stu-id="4aa88-113">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="4aa88-114">Per la maggior parte delle distribuzioni, l'utilizzo medio della CPU di UCWA deve essere inferiore al 15%.</span><span class="sxs-lookup"><span data-stu-id="4aa88-114">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="4aa88-115">L'utilizzo della memoria deve rientrare nei limiti descritti in Monitorare i limiti di capacità della memoria del [server in Skype for Business Server.](server-memory-capacity-limits.md)</span><span class="sxs-lookup"><span data-stu-id="4aa88-115">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="4aa88-116">Oltre ai contatori di utilizzo della CPU e della memoria, è possibile utilizzare i contatori delle prestazioni seguenti per determinare quando un server è sovraccarico di richieste:</span><span class="sxs-lookup"><span data-stu-id="4aa88-116">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="4aa88-117">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, che indica il numero di richieste Web in sospeso nel server.</span><span class="sxs-lookup"><span data-stu-id="4aa88-117">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="4aa88-118">Quando questo contatore raggiunge 10.000, le richieste successive avranno esito negativo, con il messaggio di errore "503 - Servizio non disponibile".</span><span class="sxs-lookup"><span data-stu-id="4aa88-118">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="4aa88-119">**ASP.NET\Requests Queued** (deve essere sempre zero).</span><span class="sxs-lookup"><span data-stu-id="4aa88-119">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="4aa88-120">Se si soddisfano o si superano questi valori, è necessario rivedere e ricalcolare la pianificazione della capacità per il dimensionamento corretto della CPU, il numero di core e la memoria per i computer che ospitano i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="4aa88-120">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="4aa88-121">**Per il servizio per dispositivi mobili (Mcx):**</span><span class="sxs-lookup"><span data-stu-id="4aa88-121">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="4aa88-122">I processi di lavoro **CSIntMcxAppPool** e **CSExtMcxAppPool** in Gestione Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="4aa88-122">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="4aa88-123">Nel riquadro **Processi di lavoro** analizzare le colonne **% CPU** e **Byte privati (KB)** (memoria).</span><span class="sxs-lookup"><span data-stu-id="4aa88-123">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="4aa88-124">Contatori delle prestazioni relativi a **CPU** e **Processore**.</span><span class="sxs-lookup"><span data-stu-id="4aa88-124">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="4aa88-125">Per la maggior parte delle distribuzioni, l'utilizzo medio della CPU del servizio per dispositivi mobili deve essere inferiore al 15%.</span><span class="sxs-lookup"><span data-stu-id="4aa88-125">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="4aa88-126">L'utilizzo della memoria deve rientrare nei limiti descritti in Monitorare i limiti di capacità della memoria del [server in Skype for Business Server.](server-memory-capacity-limits.md)</span><span class="sxs-lookup"><span data-stu-id="4aa88-126">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="4aa88-127">Oltre ai contatori di utilizzo della CPU e della memoria, è possibile utilizzare il contatori delle prestazioni ASP.NET seguenti per determinare quando un server è sovraccarico di richieste:</span><span class="sxs-lookup"><span data-stu-id="4aa88-127">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="4aa88-128">**ASP.NET v2.0.50727\Requests Current**, che indica il numero di richieste Web in sospeso nel server.</span><span class="sxs-lookup"><span data-stu-id="4aa88-128">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="4aa88-129">Quando questo contatore raggiunge 5.000, le richieste successive avranno esito negativo con il messaggio di errore "503 - Servizio non disponibile".</span><span class="sxs-lookup"><span data-stu-id="4aa88-129">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="4aa88-130">**ASP.NET\Requests Queued** (deve essere sempre zero).</span><span class="sxs-lookup"><span data-stu-id="4aa88-130">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="4aa88-131">Se si soddisfano o si superano questi valori, è consigliabile rivedere e ricalcolare la pianificazione della capacità per il dimensionamento corretto della CPU, del numero di core e della memoria per i computer che ospitano i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="4aa88-131">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="4aa88-132">Il supporto MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4aa88-132">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="4aa88-133">Tutti i client mobili Skype for Business correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti.</span><span class="sxs-lookup"><span data-stu-id="4aa88-133">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="4aa88-134">Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.</span><span class="sxs-lookup"><span data-stu-id="4aa88-134">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4aa88-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4aa88-135">See also</span></span>

[<span data-ttu-id="4aa88-136">Monitorare i limiti di capacità della memoria del server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4aa88-136">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
