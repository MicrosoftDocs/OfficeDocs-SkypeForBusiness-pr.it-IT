---
title: 'Lync Server 2013: configurazione del servizio per dispositivi mobili per prestazioni elevate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Mobility Service for high performance
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48185332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 460c56a9e51ab64491402eed22d40d60ad7d89c1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a><span data-ttu-id="11c65-102">Configurazione del servizio per dispositivi mobili per prestazioni elevate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11c65-102">Configuring Mobility Service for high performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11c65-103">_**Ultimo argomento modificato:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="11c65-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="11c65-104">Questo argomento si applica solo a Lync Server 2013 Mobility Service (MCX) e non si applica a Unified Communications Web API (UCWA), come recapitato negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.</span><span class="sxs-lookup"><span data-stu-id="11c65-104">This topic applies only to the Lync Server 2013 Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="11c65-105">Quando si installa il servizio per dispositivi mobili (MCX) su Internet Information Services (IIS) 7,5, il programma di installazione del servizio per dispositivi mobili configura alcune impostazioni delle prestazioni nel front end server.</span><span class="sxs-lookup"><span data-stu-id="11c65-105">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="11c65-106">È consigliabile utilizzare IIS 7.5 per la mobilità.</span><span class="sxs-lookup"><span data-stu-id="11c65-106">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="11c65-107">Le impostazioni influiscono sul numero massimo di richieste utente simultanee e il numero massimo di thread consentiti per il servizio di mobilità.</span><span class="sxs-lookup"><span data-stu-id="11c65-107">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>

<span data-ttu-id="11c65-108">Di seguito sono conformate le impostazioni delle prestazioni:</span><span class="sxs-lookup"><span data-stu-id="11c65-108">Here are the performance settings:</span></span>

<div>

## <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="11c65-109">Impostazioni per MCX in IIS 7,5</span><span class="sxs-lookup"><span data-stu-id="11c65-109">Settings for Mcx on IIS 7.5</span></span>

1.  <span data-ttu-id="11c65-110">Il valore **maxConcurrentThreadsPerCPU** viene impostato su zero (0).</span><span class="sxs-lookup"><span data-stu-id="11c65-110">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>

2.  <span data-ttu-id="11c65-111">Il valore **maxConcurrentRequestsPerCPU** viene impostato su zero (0).</span><span class="sxs-lookup"><span data-stu-id="11c65-111">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>

3.  <span data-ttu-id="11c65-112">Il modello di processo ASP.NET viene impostato su AutoConfig (solo per IIS 7.5).</span><span class="sxs-lookup"><span data-stu-id="11c65-112">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>

4.  <span data-ttu-id="11c65-113">Il limite di coda HTTP.sys viene impostato su 1.000 per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="11c65-113">HTTP.sys queue limit is set to 1,000 (by default).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

