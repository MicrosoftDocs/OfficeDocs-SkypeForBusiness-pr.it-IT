---
title: Utilizzo di un pool di server Chat persistente esteso per il ripristino di emergenza
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using a stretched Persistent Chat Server pool for disaster recovery
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205007(v=OCS.15)
ms:contentKeyID: 48184506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cced4904619fdbda87fecb29f35f11b40270c0ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977686"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="9016f-102">Utilizzo di un pool di server Chat persistente esteso per il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9016f-102">Using a stretched Persistent Chat Server pool for disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9016f-103">_**Argomento Ultima modifica:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="9016f-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="9016f-104">La soluzione di ripristino di emergenza per il server di chat persistente è basata su un pool di server di chat persistente allungato.</span><span class="sxs-lookup"><span data-stu-id="9016f-104">The disaster recovery solution for Persistent Chat Server is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="9016f-105">Questa operazione è simile alla resilienza del sito metropolitano in Lync Server 2010; Tuttavia, non esiste alcun requisito per una VLAN (Virtual Local Area Network) allungata.</span><span class="sxs-lookup"><span data-stu-id="9016f-105">This is similar to metropolitan site resiliency in Lync Server 2010; however, there is no requirement for a stretched virtual local area network (VLAN).</span></span> <span data-ttu-id="9016f-106">Allungando il pool di server di chat persistente, essenzialmente si configura un pool nella topologia in modo logico, ma si posiziona fisicamente i server nel pool in due centri dati diversi.</span><span class="sxs-lookup"><span data-stu-id="9016f-106">By stretching Persistent Chat Server pool, you essentially configure one pool in the topology logically, but you physically place the servers in the pool in two different data centers.</span></span> <span data-ttu-id="9016f-107">Configurare il mirroring di SQL Server per il database nello stesso modo e distribuire il database e lo specchio nello stesso centro dati.</span><span class="sxs-lookup"><span data-stu-id="9016f-107">Configure SQL Server mirroring for the database in the same way, and deploy the database and the mirror in the same data center.</span></span> <span data-ttu-id="9016f-108">È necessario configurare un database di backup nel centro dati secondario (con uno specchio facoltativo per ottenere una disponibilità elevata durante il ripristino di emergenza).</span><span class="sxs-lookup"><span data-stu-id="9016f-108">You need to configure a backup database in the secondary data center (with an optional mirror to provide high availability during disaster recovery).</span></span> <span data-ttu-id="9016f-109">Questo è il database di backup usato per il failover durante il ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="9016f-109">This is the backup database used for failover during disaster recovery.</span></span>

<span data-ttu-id="9016f-110">Per informazioni dettagliate su come configurare il mirroring di SQL Server per una disponibilità elevata, vedere [mirroring di SQL Server in Lync server 2013](lync-server-2013-sql-server-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="9016f-110">For details about how to configure SQL Server mirroring for high availability, see [SQL Server mirroring in Lync Server 2013](lync-server-2013-sql-server-mirroring.md).</span></span> <span data-ttu-id="9016f-111">Per informazioni dettagliate sul mancato rispetto del database per il ripristino di emergenza, vedere [configurazione della distribuzione di log di SQL Server in Lync server 2013 per il database primario del server di chat persistente](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) e [configurazione del log shipping di SQL Server tra lo specchio principale e il database secondario del log shipping in Lync Server 2013](lync-server-2013-setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database.md).</span><span class="sxs-lookup"><span data-stu-id="9016f-111">For details about failing over the database for disaster recovery, see [Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) and [Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013](lync-server-2013-setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

