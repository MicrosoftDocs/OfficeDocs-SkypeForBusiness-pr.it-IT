---
title: 'Lync Server 2013: monitoraggio della mobilità per le prestazioni'
description: 'Lync Server 2013: monitoraggio della mobilità per le prestazioni.'
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
ms.openlocfilehash: d6c366542e88406df043ba1a782ee12cd64bd804
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562902"
---
# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a><span data-ttu-id="0fd3c-103">Monitoraggio della mobilità per le prestazioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0fd3c-103">Monitoring mobility for performance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0fd3c-104">_**Ultimo argomento modificato:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="0fd3c-104">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="0fd3c-105">Lync Server Mobility Service (MCX) e Unified Communications Web API (UCWA) aumentano il carico nei front end server e nei pool Front end.</span><span class="sxs-lookup"><span data-stu-id="0fd3c-105">The Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="0fd3c-106">I dispositivi mobili che gestiscono una connessione al server anche quando l'applicazione per dispositivi mobili è ridotta a icona, come Android e Nokia su cui è in esecuzione Lync 2010 mobile, così come i dispositivi Android e Apple che eseguono Lync 2013 mobile, impongono un carico maggiore rispetto ai dispositivi che terminano la connessione al server quando l'applicazione per dispositivi mobili è ridotta a icona.</span><span class="sxs-lookup"><span data-stu-id="0fd3c-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="0fd3c-107">Quando l'utilizzo della mobilità aumenta, è necessario monitorare le prestazioni dei dispositivi mobili per determinare quando è necessario aumentare la capacità.</span><span class="sxs-lookup"><span data-stu-id="0fd3c-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

<span data-ttu-id="0fd3c-108">Diversi limiti influenzano le prestazioni della mobilità:</span><span class="sxs-lookup"><span data-stu-id="0fd3c-108">Several limits influence mobility performance:</span></span>

  - <span data-ttu-id="0fd3c-109">Memoria disponibile</span><span class="sxs-lookup"><span data-stu-id="0fd3c-109">Available memory</span></span>

  - <span data-ttu-id="0fd3c-110">Limite coda richieste</span><span class="sxs-lookup"><span data-stu-id="0fd3c-110">Request queue limit</span></span>

  - <span data-ttu-id="0fd3c-111">Connessioni simultanee</span><span class="sxs-lookup"><span data-stu-id="0fd3c-111">Concurrent connections</span></span>

  - <span data-ttu-id="0fd3c-112">Lunghezza coda IIS</span><span class="sxs-lookup"><span data-stu-id="0fd3c-112">IIS queue length</span></span>

<span data-ttu-id="0fd3c-113">Altri limiti nei server che possono influire sulle prestazioni della mobilità sono al massimo dodici accessi simultanei, autenticazioni, rinnovi di sessioni e terminazioni.</span><span class="sxs-lookup"><span data-stu-id="0fd3c-113">Other limits on servers that can influence mobility performance are a maximum of twelve concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="0fd3c-114">Non è necessario modificare questi valori massimi per la maggior parte delle distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="0fd3c-114">These maximums do not need to be modified for most deployments.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0fd3c-115">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="0fd3c-115">In This Section</span></span>

  - [<span data-ttu-id="0fd3c-116">Monitoraggio dei limiti di capacità della memoria del server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0fd3c-116">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [<span data-ttu-id="0fd3c-117">Monitoraggio del servizio per dispositivi mobili e utilizzo di UCWA in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0fd3c-117">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [<span data-ttu-id="0fd3c-118">Configurazione del servizio per dispositivi mobili per prestazioni elevate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0fd3c-118">Configuring Mobility Service for high performance in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [<span data-ttu-id="0fd3c-119">Monitoraggio dei file di registro di traccia delle richieste IIS in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0fd3c-119">Monitoring IIS request tracing log files in Lync Server 2013</span></span>](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [<span data-ttu-id="0fd3c-120">Contatori delle prestazioni per dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0fd3c-120">Mobility performance counters in Lync Server 2013</span></span>](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

