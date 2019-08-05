---
title: Configurare il servizio di mobilità per prestazioni elevate in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Riepilogo: informazioni sul servizio mobilità in Skype for Business Server.'
ms.openlocfilehash: 35e04fa080964495ccd9abed28c0688dd7be45a9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195707"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a><span data-ttu-id="a4bc5-103">Configurare il servizio di mobilità per prestazioni elevate in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a4bc5-103">Configure Mobility Service for high performance in Skype for Business Server</span></span>
 
<span data-ttu-id="a4bc5-104">**Riepilogo:** Informazioni sul servizio mobilità in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a4bc5-104">**Summary:** Learn about the Mobility Service in Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a4bc5-105">Questo argomento si applica solo al servizio di mobilità di Skype for Business Server (MCX) e non si applica a Unified Communications Web API (UCWA), come fornito negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.</span><span class="sxs-lookup"><span data-stu-id="a4bc5-105">This topic applies only to the Skype for Business Server Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="a4bc5-106">Quando si installa il servizio di mobilità (MCX) in Internet Information Services (IIS) 7,5, il programma di installazione del servizio di mobilità configura alcune impostazioni di prestazioni nel server front-end.</span><span class="sxs-lookup"><span data-stu-id="a4bc5-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="a4bc5-107">È consigliabile usare IIS 7,5 per la mobilità.</span><span class="sxs-lookup"><span data-stu-id="a4bc5-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="a4bc5-108">Le impostazioni influenzano il numero massimo di richieste utente simultanee e il numero massimo di thread consentiti per il servizio di mobilità.</span><span class="sxs-lookup"><span data-stu-id="a4bc5-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="a4bc5-109">Ecco le impostazioni delle prestazioni:</span><span class="sxs-lookup"><span data-stu-id="a4bc5-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="a4bc5-110">Impostazioni per MCX in IIS 7,5</span><span class="sxs-lookup"><span data-stu-id="a4bc5-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="a4bc5-111">**MaxConcurrentThreadsPerCPU** è impostato su zero (0).</span><span class="sxs-lookup"><span data-stu-id="a4bc5-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="a4bc5-112">**maxConcurrentRequestsPerCPU** è impostato su zero (0).</span><span class="sxs-lookup"><span data-stu-id="a4bc5-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="a4bc5-113">Il modello di processo di ASP.NET è impostato su AutoConfig (solo per IIS 7,5).</span><span class="sxs-lookup"><span data-stu-id="a4bc5-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="a4bc5-114">Il limite della coda HTTP. sys è impostato su 1.000 (per impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="a4bc5-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

