---
title: 'Lync Server 2013: configurazione del servizio di mobilità per prestazioni elevate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Mobility Service for high performance
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48185332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54a1c9b901e9a861b40a5cfa8c2642e3e3e41ffe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a><span data-ttu-id="8bbd7-102">Configurazione del servizio di mobilità per prestazioni elevate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bbd7-102">Configuring Mobility Service for high performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bbd7-103">_**Argomento Ultima modifica:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="8bbd7-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8bbd7-104">Questo argomento si applica solo al servizio di mobilità di Lync Server 2013 (MCX) e non si applica a UCWA (Unified Communications Web API), come fornito negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.</span><span class="sxs-lookup"><span data-stu-id="8bbd7-104">This topic applies only to the Lync Server 2013 Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="8bbd7-105">Quando si installa il servizio di mobilità (MCX) in Internet Information Services (IIS) 7,5, il programma di installazione del servizio di mobilità configura alcune impostazioni di prestazioni nel server front-end.</span><span class="sxs-lookup"><span data-stu-id="8bbd7-105">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="8bbd7-106">È consigliabile usare IIS 7,5 per la mobilità.</span><span class="sxs-lookup"><span data-stu-id="8bbd7-106">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="8bbd7-107">Le impostazioni influenzano il numero massimo di richieste utente simultanee e il numero massimo di thread consentiti per il servizio di mobilità.</span><span class="sxs-lookup"><span data-stu-id="8bbd7-107">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>

<span data-ttu-id="8bbd7-108">Ecco le impostazioni delle prestazioni:</span><span class="sxs-lookup"><span data-stu-id="8bbd7-108">Here are the performance settings:</span></span>

<div>

## <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="8bbd7-109">Impostazioni per MCX in IIS 7,5</span><span class="sxs-lookup"><span data-stu-id="8bbd7-109">Settings for Mcx on IIS 7.5</span></span>

1.  <span data-ttu-id="8bbd7-110">**MaxConcurrentThreadsPerCPU** è impostato su zero (0).</span><span class="sxs-lookup"><span data-stu-id="8bbd7-110">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>

2.  <span data-ttu-id="8bbd7-111">**maxConcurrentRequestsPerCPU** è impostato su zero (0).</span><span class="sxs-lookup"><span data-stu-id="8bbd7-111">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>

3.  <span data-ttu-id="8bbd7-112">Il modello di processo di ASP.NET è impostato su AutoConfig (solo per IIS 7,5).</span><span class="sxs-lookup"><span data-stu-id="8bbd7-112">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>

4.  <span data-ttu-id="8bbd7-113">Il limite della coda HTTP. sys è impostato su 1.000 (per impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="8bbd7-113">HTTP.sys queue limit is set to 1,000 (by default).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

