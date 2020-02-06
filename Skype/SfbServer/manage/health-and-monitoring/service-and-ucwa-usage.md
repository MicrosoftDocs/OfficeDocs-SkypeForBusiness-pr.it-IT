---
title: Monitorare il servizio di mobilità e l'uso di UCWA in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Riepilogo: gestire il servizio di mobilità (MCX) e la Unified Communications Web API (UCWA) in Skype for Business Server.'
ms.openlocfilehash: 7c41e92b144e1bd4d198c5e9d9f90913ce41400e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817685"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="46f00-103">Monitorare il servizio di mobilità e l'uso di UCWA in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="46f00-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="46f00-104">**Riepilogo:** Gestire il servizio di mobilità (MCX) e la Unified Communications Web API (UCWA) in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="46f00-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="46f00-105">Il supporto di MCX (servizio mobilità) per i client mobili legacy non è più disponibile in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="46f00-105">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="46f00-106">Tutti i client di Skype for business mobile correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti.</span><span class="sxs-lookup"><span data-stu-id="46f00-106">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="46f00-107">Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.</span><span class="sxs-lookup"><span data-stu-id="46f00-107">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="46f00-108">In base alle proprie attività, è necessario monitorare la CPU e la memoria usate dal servizio di mobilità di Skype for Business Server (MCX) e da Unified Communications Web API (UCWA).</span><span class="sxs-lookup"><span data-stu-id="46f00-108">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="46f00-109">Per monitorare l'uso, è possibile usare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="46f00-109">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="46f00-110">**Per Unified Communications Web API (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="46f00-110">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="46f00-111">Processo di lavoro di **LyncUcwa** in Gestione Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="46f00-111">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="46f00-112">Nel riquadro **processi di lavoro** esaminare le colonne **CPU%** e **private bytes (KB)** (memoria).</span><span class="sxs-lookup"><span data-stu-id="46f00-112">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="46f00-113">Contatori delle prestazioni della **CPU** e del **processore** .</span><span class="sxs-lookup"><span data-stu-id="46f00-113">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="46f00-114">Per la maggior parte delle distribuzioni, l'uso della CPU UCWA deve essere inferiore al 15% in media.</span><span class="sxs-lookup"><span data-stu-id="46f00-114">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="46f00-115">L'utilizzo della memoria deve rientrare nei limiti descritti in [Monitor per i limiti di capacità di memoria del server in Skype for Business Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="46f00-115">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="46f00-116">Oltre ai contatori di utilizzo della CPU e della memoria, è possibile usare i contatori delle prestazioni seguenti per determinare quando un server è in overload con le richieste:</span><span class="sxs-lookup"><span data-stu-id="46f00-116">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="46f00-117">**Ls: limitazione del Web e Authentication\WEB-totale delle richieste di elaborazione**, che indica il numero di richieste Web in sospeso nel server.</span><span class="sxs-lookup"><span data-stu-id="46f00-117">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="46f00-118">Quando questo contatore raggiunge 10.000, le richieste successive avranno esito negativo, con il messaggio di errore "503-servizio non disponibile".</span><span class="sxs-lookup"><span data-stu-id="46f00-118">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="46f00-119">**ASP. Net\richieste accodato** (deve sempre essere zero).</span><span class="sxs-lookup"><span data-stu-id="46f00-119">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="46f00-120">Se si soddisfano o superano questi valori, è necessario rivedere e ricalcolare la pianificazione della capacità per il dimensionamento corretto della CPU, il numero di core e la memoria per i computer che ospitano i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="46f00-120">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="46f00-121">**Per il servizio mobilità (MCX):**</span><span class="sxs-lookup"><span data-stu-id="46f00-121">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="46f00-122">Processi di lavoro di **CSIntMcxAppPool** e **CSExtMcxAppPool** in Gestione Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="46f00-122">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="46f00-123">Nel riquadro **processi di lavoro** esaminare le colonne **CPU%** e **private bytes (KB)** (memoria).</span><span class="sxs-lookup"><span data-stu-id="46f00-123">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="46f00-124">Contatori delle prestazioni della **CPU** e del **processore** .</span><span class="sxs-lookup"><span data-stu-id="46f00-124">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="46f00-125">Per la maggior parte delle distribuzioni, l'uso della CPU del servizio di mobilità deve essere inferiore al 15%, in media.</span><span class="sxs-lookup"><span data-stu-id="46f00-125">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="46f00-126">L'utilizzo della memoria deve rientrare nei limiti descritti in [Monitor per i limiti di capacità di memoria del server in Skype for Business Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="46f00-126">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="46f00-127">Oltre ai contatori di utilizzo della CPU e della memoria, è possibile usare i seguenti contatori delle prestazioni di ASP.NET per determinare quando un server è in overload con le richieste:</span><span class="sxs-lookup"><span data-stu-id="46f00-127">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="46f00-128">**ASP.NET v 2.0.50727 \ richiede Current**, che indica il numero di richieste Web in sospeso nel server.</span><span class="sxs-lookup"><span data-stu-id="46f00-128">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="46f00-129">Quando questo contatore raggiunge 5.000, le richieste successive avranno esito negativo con il messaggio di errore "503-servizio non disponibile".</span><span class="sxs-lookup"><span data-stu-id="46f00-129">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="46f00-130">**ASP. Net\richieste accodato** (deve sempre essere zero).</span><span class="sxs-lookup"><span data-stu-id="46f00-130">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="46f00-131">Se si soddisfano o superano questi valori, è necessario rivedere e ricalcolare la pianificazione della capacità per il dimensionamento corretto della CPU, del numero di core e della memoria per i computer che ospitano i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="46f00-131">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="46f00-132">Il supporto di MCX (servizio mobilità) per i client mobili legacy non è più disponibile in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="46f00-132">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="46f00-133">Tutti i client di Skype for business mobile correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti.</span><span class="sxs-lookup"><span data-stu-id="46f00-133">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="46f00-134">Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.</span><span class="sxs-lookup"><span data-stu-id="46f00-134">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="46f00-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46f00-135">See also</span></span>

[<span data-ttu-id="46f00-136">Monitorare i limiti di capacità di memoria del server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="46f00-136">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
