---
title: Utilizzo di generatore di topologie per configurare la disponibilità elevata e il ripristino di emergenza
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Topology Builder to configure high availability and disaster recovery
ms:assetid: abc1a25d-1f5e-46ef-91d2-0144fc847206
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205172(v=OCS.15)
ms:contentKeyID: 48185113
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc0f47bf8e0a0aec5d2a2374decd79ce2bae77f2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007465"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="99d19-102">Utilizzo di generatore di topologie per configurare la disponibilità elevata e il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99d19-102">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99d19-103">_**Ultimo argomento modificato:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="99d19-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="99d19-104">Eseguire i passaggi seguenti all'interno di generatore di topologie per configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="99d19-104">Perform the following steps within Topology Builder to configure high availability and disaster recovery for Persistent Chat Server.</span></span>

1.  <span data-ttu-id="99d19-105">Aggiungere i database mirror e gli archivi SQL Server del database secondario di log shipping.</span><span class="sxs-lookup"><span data-stu-id="99d19-105">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>

2.  <span data-ttu-id="99d19-106">Modificare le proprietà del servizio del server Chat persistente in:</span><span class="sxs-lookup"><span data-stu-id="99d19-106">Edit the Persistent Chat Server service properties to:</span></span>
    
    1.  <span data-ttu-id="99d19-107">Abilitare il mirroring per il database primario.</span><span class="sxs-lookup"><span data-stu-id="99d19-107">Enable mirroring for the primary database.</span></span>
    
    2.  <span data-ttu-id="99d19-108">Aggiungere l'archivio SQL Server mirror primario.</span><span class="sxs-lookup"><span data-stu-id="99d19-108">Add the primary mirror SQL Server store.</span></span>
    
    3.  <span data-ttu-id="99d19-109">Abilitare il database di log shipping di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="99d19-109">Enable the SQL Server Log Shipping database.</span></span>
    
    4.  <span data-ttu-id="99d19-110">Aggiungere l'archivio SQL Server secondario di log shipping di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="99d19-110">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    5.  <span data-ttu-id="99d19-111">Aggiungere il mirror dell'archivio SQL Server per il database secondario.</span><span class="sxs-lookup"><span data-stu-id="99d19-111">Add the SQL Server store mirror for the secondary database.</span></span>
    
    6.  <span data-ttu-id="99d19-112">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="99d19-112">Publish the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

