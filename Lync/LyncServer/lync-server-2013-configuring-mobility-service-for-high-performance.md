---
title: 'Lync Server 2013: configurazione del servizio per dispositivi mobili per prestazioni elevate'
description: 'Lync Server 2013: configurazione del servizio per dispositivi mobili per prestazioni elevate.'
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
ms.openlocfilehash: 4732d9f6a92c383a105a6f0d7162c9b6c798de24
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556982"
---
# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a><span data-ttu-id="f1990-103">Configurazione del servizio per dispositivi mobili per prestazioni elevate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1990-103">Configuring Mobility Service for high performance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1990-104">_**Ultimo argomento modificato:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="f1990-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f1990-105">Questo argomento si applica solo a Lync Server 2013 Mobility Service (MCX) e non si applica a Unified Communications Web API (UCWA), come recapitato negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.</span><span class="sxs-lookup"><span data-stu-id="f1990-105">This topic applies only to the Lync Server 2013 Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="f1990-106">Quando si installa il servizio per dispositivi mobili (MCX) su Internet Information Services (IIS) 7,5, il programma di installazione del servizio per dispositivi mobili configura alcune impostazioni delle prestazioni nel front end server.</span><span class="sxs-lookup"><span data-stu-id="f1990-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="f1990-107">È consigliabile utilizzare IIS 7.5 per la mobilità.</span><span class="sxs-lookup"><span data-stu-id="f1990-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="f1990-108">Le impostazioni influiscono sul numero massimo di richieste utente simultanee e il numero massimo di thread consentiti per il servizio di mobilità.</span><span class="sxs-lookup"><span data-stu-id="f1990-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>

<span data-ttu-id="f1990-109">Di seguito sono conformate le impostazioni delle prestazioni:</span><span class="sxs-lookup"><span data-stu-id="f1990-109">Here are the performance settings:</span></span>

<div>

## <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="f1990-110">Impostazioni per MCX in IIS 7,5</span><span class="sxs-lookup"><span data-stu-id="f1990-110">Settings for Mcx on IIS 7.5</span></span>

1.  <span data-ttu-id="f1990-111">Il valore **maxConcurrentThreadsPerCPU** viene impostato su zero (0).</span><span class="sxs-lookup"><span data-stu-id="f1990-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>

2.  <span data-ttu-id="f1990-112">Il valore **maxConcurrentRequestsPerCPU** viene impostato su zero (0).</span><span class="sxs-lookup"><span data-stu-id="f1990-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>

3.  <span data-ttu-id="f1990-113">Il modello di processo ASP.NET viene impostato su AutoConfig (solo per IIS 7.5).</span><span class="sxs-lookup"><span data-stu-id="f1990-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>

4.  <span data-ttu-id="f1990-114">Il limite di coda HTTP.sys viene impostato su 1.000 per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f1990-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

