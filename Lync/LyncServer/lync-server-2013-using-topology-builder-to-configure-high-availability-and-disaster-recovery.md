---
title: Utilizzo di Generatore di topologie per configurare la disponibilità elevata e il ripristino di emergenza
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Topology Builder to configure high availability and disaster recovery
ms:assetid: abc1a25d-1f5e-46ef-91d2-0144fc847206
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205172(v=OCS.15)
ms:contentKeyID: 48185113
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b167ea64f42510febe0f405d15e2eafab7efc2bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="72223-102">Utilizzo di Generatore di topologie per configurare la disponibilità elevata e il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72223-102">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72223-103">_**Argomento Ultima modifica:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="72223-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="72223-104">Eseguire i passaggi seguenti in Generatore di topologia per configurare l'elevata disponibilità e il ripristino di emergenza per il server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="72223-104">Perform the following steps within Topology Builder to configure high availability and disaster recovery for Persistent Chat Server.</span></span>

1.  <span data-ttu-id="72223-105">Aggiungere i database mirror e il database secondario del log shipping di SQL Server Store.</span><span class="sxs-lookup"><span data-stu-id="72223-105">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>

2.  <span data-ttu-id="72223-106">Modificare le proprietà del servizio server di chat persistente in:</span><span class="sxs-lookup"><span data-stu-id="72223-106">Edit the Persistent Chat Server service properties to:</span></span>
    
    1.  <span data-ttu-id="72223-107">Abilitare il mirroring per il database primario.</span><span class="sxs-lookup"><span data-stu-id="72223-107">Enable mirroring for the primary database.</span></span>
    
    2.  <span data-ttu-id="72223-108">Aggiungere il mirror principale di SQL Server Store.</span><span class="sxs-lookup"><span data-stu-id="72223-108">Add the primary mirror SQL Server store.</span></span>
    
    3.  <span data-ttu-id="72223-109">Abilitare il database di log shipping di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="72223-109">Enable the SQL Server Log Shipping database.</span></span>
    
    4.  <span data-ttu-id="72223-110">Aggiungere l'archivio SQL Server log shipping secondario di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="72223-110">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    5.  <span data-ttu-id="72223-111">Aggiungere il mirror di SQL Server Store per il database secondario.</span><span class="sxs-lookup"><span data-stu-id="72223-111">Add the SQL Server store mirror for the secondary database.</span></span>
    
    6.  <span data-ttu-id="72223-112">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="72223-112">Publish the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

