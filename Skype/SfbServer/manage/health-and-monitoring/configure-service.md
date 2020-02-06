---
title: Configurare il servizio di mobilità per prestazioni elevate in Skype for Business Server
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
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Riepilogo: informazioni sul servizio mobilità in Skype for Business Server.'
ms.openlocfilehash: d50aab5ced14753a7665c6560220d1dfdca1061d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818056"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a><span data-ttu-id="8db31-103">Configurare il servizio di mobilità per prestazioni elevate in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8db31-103">Configure Mobility Service for high performance in Skype for Business Server</span></span>
 
<span data-ttu-id="8db31-104">**Riepilogo:** Informazioni sul servizio mobilità in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8db31-104">**Summary:** Learn about the Mobility Service in Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8db31-105">Questo argomento si applica solo al servizio di mobilità di Skype for Business Server (MCX) e non si applica a Unified Communications Web API (UCWA), come fornito negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.</span><span class="sxs-lookup"><span data-stu-id="8db31-105">This topic applies only to the Skype for Business Server Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="8db31-106">Quando si installa il servizio di mobilità (MCX) in Internet Information Services (IIS) 7,5, il programma di installazione del servizio di mobilità configura alcune impostazioni di prestazioni nel server front-end.</span><span class="sxs-lookup"><span data-stu-id="8db31-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="8db31-107">È consigliabile usare IIS 7,5 per la mobilità.</span><span class="sxs-lookup"><span data-stu-id="8db31-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="8db31-108">Le impostazioni influenzano il numero massimo di richieste utente simultanee e il numero massimo di thread consentiti per il servizio di mobilità.</span><span class="sxs-lookup"><span data-stu-id="8db31-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="8db31-109">Ecco le impostazioni delle prestazioni:</span><span class="sxs-lookup"><span data-stu-id="8db31-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="8db31-110">Impostazioni per MCX in IIS 7,5</span><span class="sxs-lookup"><span data-stu-id="8db31-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="8db31-111">**MaxConcurrentThreadsPerCPU** è impostato su zero (0).</span><span class="sxs-lookup"><span data-stu-id="8db31-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="8db31-112">**maxConcurrentRequestsPerCPU** è impostato su zero (0).</span><span class="sxs-lookup"><span data-stu-id="8db31-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="8db31-113">Il modello di processo di ASP.NET è impostato su AutoConfig (solo per IIS 7,5).</span><span class="sxs-lookup"><span data-stu-id="8db31-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="8db31-114">Il limite della coda HTTP. sys è impostato su 1.000 (per impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="8db31-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

