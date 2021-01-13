---
title: Configurare il servizio per dispositivi mobili per ottenere prestazioni elevate in Skype for Business Server
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
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Riepilogo: informazioni sul servizio per dispositivi mobili in Skype for Business Server.'
ms.openlocfilehash: 83d8d6dc7a32b05a58c738deddc8c92e43bd5557
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817036"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a><span data-ttu-id="36a9e-103">Configurare il servizio per dispositivi mobili per ottenere prestazioni elevate in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="36a9e-103">Configure Mobility Service for high performance in Skype for Business Server</span></span>
 
<span data-ttu-id="36a9e-104">**Riepilogo:** Informazioni sul servizio per dispositivi mobili in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="36a9e-104">**Summary:** Learn about the Mobility Service in Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="36a9e-105">Questo argomento si applica solo al servizio per dispositivi mobili di Skype for Business Server (MCX) e non si applica a Unified Communications Web API (UCWA), come recapitato negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.</span><span class="sxs-lookup"><span data-stu-id="36a9e-105">This topic applies only to the Skype for Business Server Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="36a9e-106">Quando si installa il servizio per dispositivi mobili (MCX) su Internet Information Services (IIS) 7,5, il programma di installazione del servizio per dispositivi mobili configura alcune impostazioni delle prestazioni nel front end server.</span><span class="sxs-lookup"><span data-stu-id="36a9e-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="36a9e-107">È consigliabile utilizzare IIS 7.5 per la mobilità.</span><span class="sxs-lookup"><span data-stu-id="36a9e-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="36a9e-108">Le impostazioni influiscono sul numero massimo di richieste utente simultanee e il numero massimo di thread consentiti per il servizio di mobilità.</span><span class="sxs-lookup"><span data-stu-id="36a9e-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="36a9e-109">Di seguito sono conformate le impostazioni delle prestazioni:</span><span class="sxs-lookup"><span data-stu-id="36a9e-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="36a9e-110">Impostazioni per MCX in IIS 7,5</span><span class="sxs-lookup"><span data-stu-id="36a9e-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="36a9e-111">Il valore **maxConcurrentThreadsPerCPU** viene impostato su zero (0).</span><span class="sxs-lookup"><span data-stu-id="36a9e-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="36a9e-112">Il valore **maxConcurrentRequestsPerCPU** viene impostato su zero (0).</span><span class="sxs-lookup"><span data-stu-id="36a9e-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="36a9e-113">Il modello di processo ASP.NET viene impostato su AutoConfig (solo per IIS 7.5).</span><span class="sxs-lookup"><span data-stu-id="36a9e-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="36a9e-114">Il limite di coda HTTP.sys viene impostato su 1.000 per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="36a9e-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

