---
title: Monitorare la mobilità per le prestazioni in Skype for Business Server
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
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: "Riepilogo: informazioni sul servizio di mobilità (MCX) e sull'API Web Unified Communications (UCWA) in Skype for Business Server."
ms.openlocfilehash: 4d604c46704881a055385336f8b1ff32862d929a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817835"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a><span data-ttu-id="30a72-103">Monitorare la mobilità per le prestazioni in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="30a72-103">Monitor mobility for performance in Skype for Business Server</span></span>
 
<span data-ttu-id="30a72-104">**Riepilogo:** Informazioni sul servizio di mobilità (MCX) e sull'API Unified Communications Web (UCWA) in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="30a72-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>
  
<span data-ttu-id="30a72-105">Il servizio di mobilità di Skype for Business Server (MCX) e l'API Web Unified Communications (UCWA) aumentano il carico nei server front-end e nei pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="30a72-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="30a72-106">I dispositivi mobili che gestiscono una connessione al server anche quando l'applicazione mobile è ridotta a icona, ad esempio dispositivi Android e Nokia che utilizzano Lync 2010 mobile, oltre a dispositivi Android e Apple che utilizzano Lync 2013 mobile, impongono un carico maggiore rispetto ai dispositivi che terminare la connessione al server quando l'applicazione per dispositivi mobili viene ridotta a icona.</span><span class="sxs-lookup"><span data-stu-id="30a72-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="30a72-107">Man mano che l'uso della mobilità aumenta, è necessario monitorare le prestazioni della mobilità per determinare quando è necessario aumentare la propria capacità.</span><span class="sxs-lookup"><span data-stu-id="30a72-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

> [!NOTE]
> <span data-ttu-id="30a72-108">Il supporto di MCX (servizio mobilità) per i client mobili legacy non è più disponibile in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="30a72-108">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="30a72-109">Tutti i client di Skype for business mobile correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti.</span><span class="sxs-lookup"><span data-stu-id="30a72-109">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="30a72-110">Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.</span><span class="sxs-lookup"><span data-stu-id="30a72-110">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="30a72-111">Diversi limiti influenzano le prestazioni di mobilità:</span><span class="sxs-lookup"><span data-stu-id="30a72-111">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="30a72-112">Memoria disponibile</span><span class="sxs-lookup"><span data-stu-id="30a72-112">Available memory</span></span>
    
- <span data-ttu-id="30a72-113">Limite della coda di richiesta</span><span class="sxs-lookup"><span data-stu-id="30a72-113">Request queue limit</span></span>
    
- <span data-ttu-id="30a72-114">Connessioni simultanee</span><span class="sxs-lookup"><span data-stu-id="30a72-114">Concurrent connections</span></span>
    
- <span data-ttu-id="30a72-115">Lunghezza coda di IIS</span><span class="sxs-lookup"><span data-stu-id="30a72-115">IIS queue length</span></span>
    
<span data-ttu-id="30a72-116">Altri limiti per i server che possono influenzare le prestazioni della mobilità sono un massimo di 12 accessi contemporanei, autenticazioni, rinnovi di sessioni e terminazioni.</span><span class="sxs-lookup"><span data-stu-id="30a72-116">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="30a72-117">Non è necessario modificare questi massimali per la maggior parte delle distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="30a72-117">These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="30a72-118">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="30a72-118">In this section</span></span>

- [<span data-ttu-id="30a72-119">Monitorare i limiti di capacità di memoria del server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="30a72-119">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="30a72-120">Monitorare il servizio di mobilità e l'uso di UCWA in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="30a72-120">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="30a72-121">Configurare il servizio di mobilità per prestazioni elevate in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="30a72-121">Configure Mobility Service for high performance in Skype for Business Server</span></span>](configure-service.md)
    
- [<span data-ttu-id="30a72-122">Monitoraggio dei file di log della traccia delle richieste di IIS in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="30a72-122">Monitoring IIS request tracing log files in Skype for Business Server</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="30a72-123">Contatori delle prestazioni di mobilità in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="30a72-123">Mobility performance counters in Skype for Business Server</span></span>](performance-counters.md)
    

