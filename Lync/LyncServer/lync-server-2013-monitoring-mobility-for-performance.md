---
title: 'Lync Server 2013: monitorare la mobilità per le prestazioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring mobility for performance
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690033(v=OCS.15)
ms:contentKeyID: 48184908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53bd9c3450617d4fd1db54b52efe0b0938c84c8b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a><span data-ttu-id="d48a9-102">Monitoraggio della mobilità per le prestazioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d48a9-102">Monitoring mobility for performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d48a9-103">_**Argomento Ultima modifica:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="d48a9-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="d48a9-104">Il servizio di mobilità di Lync Server (MCX) e l'API Web Unified Communications (UCWA) aumentano il carico nei server front-end e nei pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="d48a9-104">The Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="d48a9-105">I dispositivi mobili che gestiscono una connessione al server anche quando l'applicazione mobile è ridotta a icona, ad esempio dispositivi Android e Nokia che utilizzano Lync 2010 mobile, oltre a dispositivi Android e Apple che utilizzano Lync 2013 mobile, impongono un carico maggiore rispetto ai dispositivi che terminare la connessione al server quando l'applicazione per dispositivi mobili viene ridotta a icona.</span><span class="sxs-lookup"><span data-stu-id="d48a9-105">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="d48a9-106">Man mano che l'uso della mobilità aumenta, è necessario monitorare le prestazioni della mobilità per determinare quando è necessario aumentare la propria capacità.</span><span class="sxs-lookup"><span data-stu-id="d48a9-106">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

<span data-ttu-id="d48a9-107">Diversi limiti influenzano le prestazioni di mobilità:</span><span class="sxs-lookup"><span data-stu-id="d48a9-107">Several limits influence mobility performance:</span></span>

  - <span data-ttu-id="d48a9-108">Memoria disponibile</span><span class="sxs-lookup"><span data-stu-id="d48a9-108">Available memory</span></span>

  - <span data-ttu-id="d48a9-109">Limite della coda di richiesta</span><span class="sxs-lookup"><span data-stu-id="d48a9-109">Request queue limit</span></span>

  - <span data-ttu-id="d48a9-110">Connessioni simultanee</span><span class="sxs-lookup"><span data-stu-id="d48a9-110">Concurrent connections</span></span>

  - <span data-ttu-id="d48a9-111">Lunghezza coda di IIS</span><span class="sxs-lookup"><span data-stu-id="d48a9-111">IIS queue length</span></span>

<span data-ttu-id="d48a9-112">Altri limiti per i server che possono influenzare le prestazioni della mobilità sono un massimo di dodici accessi contemporanei, autenticazioni, rinnovi di sessioni e terminazioni.</span><span class="sxs-lookup"><span data-stu-id="d48a9-112">Other limits on servers that can influence mobility performance are a maximum of twelve concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="d48a9-113">Non è necessario modificare questi massimali per la maggior parte delle distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="d48a9-113">These maximums do not need to be modified for most deployments.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d48a9-114">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d48a9-114">In This Section</span></span>

  - [<span data-ttu-id="d48a9-115">Monitoraggio dei limiti della capacità di memoria del server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d48a9-115">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [<span data-ttu-id="d48a9-116">Monitoraggio del servizio di mobilità e uso di UCWA in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d48a9-116">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [<span data-ttu-id="d48a9-117">Configurazione del servizio di mobilità per prestazioni elevate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d48a9-117">Configuring Mobility Service for high performance in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [<span data-ttu-id="d48a9-118">Monitoraggio dei file di log della traccia delle richieste di IIS in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d48a9-118">Monitoring IIS request tracing log files in Lync Server 2013</span></span>](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [<span data-ttu-id="d48a9-119">Contatori delle prestazioni di mobilità in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d48a9-119">Mobility performance counters in Lync Server 2013</span></span>](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

