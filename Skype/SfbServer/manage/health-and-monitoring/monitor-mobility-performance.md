---
title: Monitorare i dispositivi mobili per le prestazioni in Skype for Business Server
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
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: "Riepilogo: informazioni sul servizio per dispositivi mobili (MCX) e sull'API Unified Communications Web (UCWA) in Skype for Business Server."
ms.openlocfilehash: d7473d22f2de0576bf6214ae43719c8bfc70d49a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816836"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a><span data-ttu-id="4687d-103">Monitorare i dispositivi mobili per le prestazioni in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4687d-103">Monitor mobility for performance in Skype for Business Server</span></span>
 
<span data-ttu-id="4687d-104">**Riepilogo:** Informazioni su The Mobility Service (MCX) e Unified Communications Web API (UCWA) in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4687d-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>
  
<span data-ttu-id="4687d-105">Skype for Business Server Mobility Service (MCX) e Unified Communications Web API (UCWA) aumentano il carico nei front end server e nei pool Front end.</span><span class="sxs-lookup"><span data-stu-id="4687d-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="4687d-106">I dispositivi mobili che gestiscono una connessione al server anche quando l'applicazione per dispositivi mobili è ridotta a icona, come Android e Nokia su cui è in esecuzione Lync 2010 mobile, così come i dispositivi Android e Apple che eseguono Lync 2013 mobile, impongono un carico maggiore rispetto ai dispositivi che terminano la connessione al server quando l'applicazione per dispositivi mobili è ridotta a icona.</span><span class="sxs-lookup"><span data-stu-id="4687d-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="4687d-107">Quando l'utilizzo della mobilità aumenta, è necessario monitorare le prestazioni dei dispositivi mobili per determinare quando è necessario aumentare la capacità.</span><span class="sxs-lookup"><span data-stu-id="4687d-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

> [!NOTE]
> <span data-ttu-id="4687d-108">Il supporto di MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4687d-108">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="4687d-109">Tutti i client per dispositivi mobili Skype for business corrente utilizzano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti.</span><span class="sxs-lookup"><span data-stu-id="4687d-109">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="4687d-110">Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.</span><span class="sxs-lookup"><span data-stu-id="4687d-110">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="4687d-111">Diversi limiti influenzano le prestazioni della mobilità:</span><span class="sxs-lookup"><span data-stu-id="4687d-111">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="4687d-112">Memoria disponibile</span><span class="sxs-lookup"><span data-stu-id="4687d-112">Available memory</span></span>
    
- <span data-ttu-id="4687d-113">Limite coda richieste</span><span class="sxs-lookup"><span data-stu-id="4687d-113">Request queue limit</span></span>
    
- <span data-ttu-id="4687d-114">Connessioni simultanee</span><span class="sxs-lookup"><span data-stu-id="4687d-114">Concurrent connections</span></span>
    
- <span data-ttu-id="4687d-115">Lunghezza coda IIS</span><span class="sxs-lookup"><span data-stu-id="4687d-115">IIS queue length</span></span>
    
<span data-ttu-id="4687d-116">Altri limiti nei server che possono influire sulle prestazioni della mobilità sono al massimo 12 accessi simultanei, autenticazioni, rinnovi di sessioni e terminazioni.</span><span class="sxs-lookup"><span data-stu-id="4687d-116">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="4687d-117">Non è necessario modificare questi valori massimi per la maggior parte delle distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="4687d-117">These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="4687d-118">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="4687d-118">In this section</span></span>

- [<span data-ttu-id="4687d-119">Monitorare i limiti di capacità della memoria del server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4687d-119">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="4687d-120">Monitorare il servizio per dispositivi mobili e l'utilizzo di UCWA in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4687d-120">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="4687d-121">Configurare il servizio per dispositivi mobili per ottenere prestazioni elevate in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4687d-121">Configure Mobility Service for high performance in Skype for Business Server</span></span>](configure-service.md)
    
- [<span data-ttu-id="4687d-122">Monitoraggio dei file di registro di traccia delle richieste IIS in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4687d-122">Monitoring IIS request tracing log files in Skype for Business Server</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="4687d-123">Contatori delle prestazioni per dispositivi mobili in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4687d-123">Mobility performance counters in Skype for Business Server</span></span>](performance-counters.md)
    

