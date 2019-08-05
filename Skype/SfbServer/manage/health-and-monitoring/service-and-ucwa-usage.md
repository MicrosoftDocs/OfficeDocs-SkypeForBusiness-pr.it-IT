---
title: Monitorare il servizio di mobilità e l'uso di UCWA in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Riepilogo: gestire il servizio di mobilità (MCX) e la Unified Communications Web API (UCWA) in Skype for Business Server.'
ms.openlocfilehash: 5447eb0ac8ffe468fd52c7011824cc1f2f2f7b55
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188681"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="1127f-103">Monitorare il servizio di mobilità e l'uso di UCWA in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1127f-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="1127f-104">**Riepilogo:** Gestire il servizio di mobilità (MCX) e la Unified Communications Web API (UCWA) in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1127f-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="1127f-105">Il supporto di MCX (servizio mobilità) per i client mobili legacy non è più disponibile in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1127f-105">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="1127f-106">Tutti i client di Skype for business mobile correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti.</span><span class="sxs-lookup"><span data-stu-id="1127f-106">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="1127f-107">Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.</span><span class="sxs-lookup"><span data-stu-id="1127f-107">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="1127f-108">In base alle proprie attività, è necessario monitorare la CPU e la memoria usate dal servizio di mobilità di Skype for Business Server (MCX) e da Unified Communications Web API (UCWA).</span><span class="sxs-lookup"><span data-stu-id="1127f-108">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="1127f-109">Per monitorare l'uso, è possibile usare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1127f-109">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="1127f-110">**Per Unified Communications Web API (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="1127f-110">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="1127f-111">Processo di lavoro di **LyncUcwa** in Gestione Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="1127f-111">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="1127f-112">Nel riquadro **processi di lavoro** esaminare le colonne **CPU%** e **private bytes (KB)** (memoria).</span><span class="sxs-lookup"><span data-stu-id="1127f-112">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="1127f-113">Contatori delle prestazioni della **CPU** e del **processore** .</span><span class="sxs-lookup"><span data-stu-id="1127f-113">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="1127f-114">Per la maggior parte delle distribuzioni, l'uso della CPU UCWA deve essere inferiore al 15% in media.</span><span class="sxs-lookup"><span data-stu-id="1127f-114">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="1127f-115">L'utilizzo della memoria deve rientrare nei limiti descritti in [Monitor per i limiti di capacità di memoria del server in Skype for Business Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="1127f-115">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="1127f-116">Oltre ai contatori di utilizzo della CPU e della memoria, è possibile usare i contatori delle prestazioni seguenti per determinare quando un server è in overload con le richieste:</span><span class="sxs-lookup"><span data-stu-id="1127f-116">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="1127f-117">**Ls: limitazione del Web e Authentication\WEB-totale delle richieste di elaborazione**, che indica il numero di richieste Web in sospeso nel server.</span><span class="sxs-lookup"><span data-stu-id="1127f-117">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="1127f-118">Quando questo contatore raggiunge 10.000, le richieste successive avranno esito negativo, con il messaggio di errore "503-servizio non disponibile".</span><span class="sxs-lookup"><span data-stu-id="1127f-118">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="1127f-119">**ASP. NET\Richieste in coda** (deve sempre essere zero).</span><span class="sxs-lookup"><span data-stu-id="1127f-119">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="1127f-120">Se si soddisfano o superano questi valori, è necessario rivedere e ricalcolare la pianificazione della capacità per il dimensionamento corretto della CPU, il numero di core e la memoria per i computer che ospitano i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="1127f-120">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="1127f-121">**Per il servizio mobilità (MCX):**</span><span class="sxs-lookup"><span data-stu-id="1127f-121">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="1127f-122">Processi di lavoro di **CSIntMcxAppPool** e **CSExtMcxAppPool** in Gestione Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="1127f-122">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="1127f-123">Nel riquadro **processi di lavoro** esaminare le colonne **CPU%** e **private bytes (KB)** (memoria).</span><span class="sxs-lookup"><span data-stu-id="1127f-123">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="1127f-124">Contatori delle prestazioni della **CPU** e del **processore** .</span><span class="sxs-lookup"><span data-stu-id="1127f-124">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="1127f-125">Per la maggior parte delle distribuzioni, l'uso della CPU del servizio di mobilità deve essere inferiore al 15%, in media.</span><span class="sxs-lookup"><span data-stu-id="1127f-125">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="1127f-126">L'utilizzo della memoria deve rientrare nei limiti descritti in [Monitor per i limiti di capacità di memoria del server in Skype for Business Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="1127f-126">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="1127f-127">Oltre ai contatori di utilizzo della CPU e della memoria, è possibile usare i seguenti contatori delle prestazioni di ASP.NET per determinare quando un server è in overload con le richieste:</span><span class="sxs-lookup"><span data-stu-id="1127f-127">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="1127f-128">**ASP.NET v 2.0.50727 \ richiede Current**, che indica il numero di richieste Web in sospeso nel server.</span><span class="sxs-lookup"><span data-stu-id="1127f-128">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="1127f-129">Quando questo contatore raggiunge 5.000, le richieste successive avranno esito negativo con il messaggio di errore "503-servizio non disponibile".</span><span class="sxs-lookup"><span data-stu-id="1127f-129">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="1127f-130">**ASP. NET\Richieste in coda** (deve sempre essere zero).</span><span class="sxs-lookup"><span data-stu-id="1127f-130">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="1127f-131">Se si soddisfano o superano questi valori, è necessario rivedere e ricalcolare la pianificazione della capacità per il dimensionamento corretto della CPU, del numero di core e della memoria per i computer che ospitano i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="1127f-131">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="1127f-132">Il supporto di MCX (servizio mobilità) per i client mobili legacy non è più disponibile in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1127f-132">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="1127f-133">Tutti i client di Skype for business mobile correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti.</span><span class="sxs-lookup"><span data-stu-id="1127f-133">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="1127f-134">Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.</span><span class="sxs-lookup"><span data-stu-id="1127f-134">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1127f-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1127f-135">See also</span></span>

[<span data-ttu-id="1127f-136">Monitorare i limiti di capacità di memoria del server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1127f-136">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
