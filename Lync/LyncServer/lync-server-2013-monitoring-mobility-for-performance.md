---
title: 'Lync Server 2013: monitoraggio della mobilità per le prestazioni'
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
ms.openlocfilehash: 840ec938fdd6262468eb86a3b190e100c38bf32c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a><span data-ttu-id="14a4b-102">Monitoraggio della mobilità per le prestazioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14a4b-102">Monitoring mobility for performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14a4b-103">_**Ultimo argomento modificato:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="14a4b-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="14a4b-104">Lync Server Mobility Service (MCX) e Unified Communications Web API (UCWA) aumentano il carico nei front end server e nei pool Front end.</span><span class="sxs-lookup"><span data-stu-id="14a4b-104">The Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="14a4b-105">I dispositivi mobili che gestiscono una connessione al server anche quando l'applicazione per dispositivi mobili è ridotta a icona, come Android e Nokia su cui è in esecuzione Lync 2010 mobile, così come i dispositivi Android e Apple che eseguono Lync 2013 mobile, impongono un carico maggiore rispetto ai dispositivi che terminare la connessione al server quando l'applicazione per dispositivi mobili è ridotta a icona.</span><span class="sxs-lookup"><span data-stu-id="14a4b-105">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="14a4b-106">Quando l'utilizzo della mobilità aumenta, è necessario monitorare le prestazioni dei dispositivi mobili per determinare quando è necessario aumentare la capacità.</span><span class="sxs-lookup"><span data-stu-id="14a4b-106">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

<span data-ttu-id="14a4b-107">Diversi limiti influenzano le prestazioni della mobilità:</span><span class="sxs-lookup"><span data-stu-id="14a4b-107">Several limits influence mobility performance:</span></span>

  - <span data-ttu-id="14a4b-108">Memoria disponibile</span><span class="sxs-lookup"><span data-stu-id="14a4b-108">Available memory</span></span>

  - <span data-ttu-id="14a4b-109">Limite coda richieste</span><span class="sxs-lookup"><span data-stu-id="14a4b-109">Request queue limit</span></span>

  - <span data-ttu-id="14a4b-110">Connessioni simultanee</span><span class="sxs-lookup"><span data-stu-id="14a4b-110">Concurrent connections</span></span>

  - <span data-ttu-id="14a4b-111">Lunghezza coda IIS</span><span class="sxs-lookup"><span data-stu-id="14a4b-111">IIS queue length</span></span>

<span data-ttu-id="14a4b-112">Altri limiti nei server che possono influire sulle prestazioni della mobilità sono al massimo dodici accessi simultanei, autenticazioni, rinnovi di sessioni e terminazioni.</span><span class="sxs-lookup"><span data-stu-id="14a4b-112">Other limits on servers that can influence mobility performance are a maximum of twelve concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="14a4b-113">Non è necessario modificare questi valori massimi per la maggior parte delle distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="14a4b-113">These maximums do not need to be modified for most deployments.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="14a4b-114">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="14a4b-114">In This Section</span></span>

  - [<span data-ttu-id="14a4b-115">Monitoraggio dei limiti di capacità della memoria del server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14a4b-115">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [<span data-ttu-id="14a4b-116">Monitoraggio del servizio per dispositivi mobili e utilizzo di UCWA in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14a4b-116">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [<span data-ttu-id="14a4b-117">Configurazione del servizio per dispositivi mobili per prestazioni elevate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14a4b-117">Configuring Mobility Service for high performance in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [<span data-ttu-id="14a4b-118">Monitoraggio dei file di registro di traccia delle richieste IIS in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14a4b-118">Monitoring IIS request tracing log files in Lync Server 2013</span></span>](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [<span data-ttu-id="14a4b-119">Contatori delle prestazioni per dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14a4b-119">Mobility performance counters in Lync Server 2013</span></span>](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

