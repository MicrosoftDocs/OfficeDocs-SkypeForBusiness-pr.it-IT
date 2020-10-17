---
title: "Lync Server 2013: gestione dell'infrastruttura di rete di Lync Server 2013"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Lync Server 2013 network infrastructure
ms:assetid: cb13456a-8f66-4595-be21-8887f30ad4eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182585(v=OCS.15)
ms:contentKeyID: 48185638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdbb78b214590228b78b7eb002e6226cc712c175
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524933"
---
# <a name="managing-the-lync-server-2013-network-infrastructure"></a><span data-ttu-id="dfcdf-102">Gestione dell'infrastruttura di rete di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfcdf-102">Managing the Lync Server 2013 network infrastructure</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfcdf-103">_**Ultimo argomento modificato:** 2014-02-11_</span><span class="sxs-lookup"><span data-stu-id="dfcdf-103">_**Topic Last Modified:** 2014-02-11_</span></span>

<span data-ttu-id="dfcdf-104">Microsoft Lync Server 2013 include il supporto per il controllo di ammissione di chiamata (CAC) e il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="dfcdf-104">Microsoft Lync Server 2013 includes support for call admission control (CAC) and media bypass.</span></span> <span data-ttu-id="dfcdf-105">Per implementare queste funzionalità, è necessario configurare una rete di aree, siti, subnet e così via che consentirà di gestire la larghezza di banda in situazioni in cui le trasmissioni audio e video devono essere limitate.</span><span class="sxs-lookup"><span data-stu-id="dfcdf-105">To implement these features you must configure a network of regions, sites, subnets, and so on that will allow you to manage bandwidth in situations where audio and video transmissions need to be restricted.</span></span> <span data-ttu-id="dfcdf-106">È inoltre possibile utilizzare la tecnologia di rete Qualità del servizio (QoS) per fornire un'esperienza utente finale ottimale per le comunicazioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="dfcdf-106">You can also use the Quality of Service (QoS) networking technology to help provide an optimal end-user experience for audio and video communications.</span></span>

<span data-ttu-id="dfcdf-107">È possibile utilizzare il pannello di controllo di Lync Server per configurare e gestire CAC, bypass multimediale e QoS.</span><span class="sxs-lookup"><span data-stu-id="dfcdf-107">You can use the Lync Server Control Panel to set up and manage CAC, media bypass, and QoS.</span></span> <span data-ttu-id="dfcdf-108">Negli argomenti elencati di seguito vengono descritte le procedure correlate.</span><span class="sxs-lookup"><span data-stu-id="dfcdf-108">The following topics provide steps for how to do this.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dfcdf-109">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="dfcdf-109">In This Section</span></span>

  - [<span data-ttu-id="dfcdf-110">Gestione della qualità del servizio (QoS) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfcdf-110">Managing Quality of Service (QoS) in Lync Server 2013</span></span>](lync-server-2013-managing-quality-of-service-qos.md)

  - [<span data-ttu-id="dfcdf-111">Gestione del controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfcdf-111">Managing call admission control in Lync Server 2013</span></span>](lync-server-2013-managing-call-admission-control.md)

  - [<span data-ttu-id="dfcdf-112">Interfacce di rete di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfcdf-112">Lync Server 2013 network interfaces</span></span>](lync-server-2013-lync-server-network-interfaces.md)

  - [<span data-ttu-id="dfcdf-113">Impedire nuove connessioni a Lync Server 2013 per la manutenzione del server</span><span class="sxs-lookup"><span data-stu-id="dfcdf-113">Prevent new connections to Lync Server 2013 for server maintenance</span></span>](lync-server-2013-prevent-new-connections-to-lync-server-for-server-maintenance.md)

  - [<span data-ttu-id="dfcdf-114">Metodologia della qualità delle chiamate di Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfcdf-114">Lync Call Quality Methodology in Lync Server 2013</span></span>](lync-server-2013-poster-lync-call-quality-methodology.md)

  - [<span data-ttu-id="dfcdf-115">Indicatori di integrità chiave in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfcdf-115">Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-poster-key-health-indicators.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

