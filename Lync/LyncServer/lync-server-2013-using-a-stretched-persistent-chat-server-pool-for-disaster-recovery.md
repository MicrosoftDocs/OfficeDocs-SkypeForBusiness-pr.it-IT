---
title: Utilizzo di un pool di server Chat persistente esteso per il ripristino di emergenza
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using a stretched Persistent Chat Server pool for disaster recovery
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205007(v=OCS.15)
ms:contentKeyID: 48184506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2d5091623e381191d23ae0c8a62835577a1f66a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="257f5-102">Utilizzo di un pool di server Chat persistente esteso per il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="257f5-102">Using a stretched Persistent Chat Server pool for disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="257f5-103">_**Argomento Ultima modifica:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="257f5-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="257f5-104">La soluzione di ripristino di emergenza per il server di chat persistente è basata su un pool di server di chat persistente allungato.</span><span class="sxs-lookup"><span data-stu-id="257f5-104">The disaster recovery solution for Persistent Chat Server is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="257f5-105">Questa operazione è simile alla resilienza del sito metropolitano in Lync Server 2010; Tuttavia, non esiste alcun requisito per una VLAN (Virtual Local Area Network) allungata.</span><span class="sxs-lookup"><span data-stu-id="257f5-105">This is similar to metropolitan site resiliency in Lync Server 2010; however, there is no requirement for a stretched virtual local area network (VLAN).</span></span> <span data-ttu-id="257f5-106">Allungando il pool di server di chat persistente, essenzialmente si configura un pool nella topologia in modo logico, ma si posiziona fisicamente i server nel pool in due centri dati diversi.</span><span class="sxs-lookup"><span data-stu-id="257f5-106">By stretching Persistent Chat Server pool, you essentially configure one pool in the topology logically, but you physically place the servers in the pool in two different data centers.</span></span> <span data-ttu-id="257f5-107">Configurare il mirroring di SQL Server per il database nello stesso modo e distribuire il database e lo specchio nello stesso centro dati.</span><span class="sxs-lookup"><span data-stu-id="257f5-107">Configure SQL Server mirroring for the database in the same way, and deploy the database and the mirror in the same data center.</span></span> <span data-ttu-id="257f5-108">È necessario configurare un database di backup nel centro dati secondario (con uno specchio facoltativo per ottenere una disponibilità elevata durante il ripristino di emergenza).</span><span class="sxs-lookup"><span data-stu-id="257f5-108">You need to configure a backup database in the secondary data center (with an optional mirror to provide high availability during disaster recovery).</span></span> <span data-ttu-id="257f5-109">Questo è il database di backup usato per il failover durante il ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="257f5-109">This is the backup database used for failover during disaster recovery.</span></span>

<span data-ttu-id="257f5-110">Per informazioni dettagliate su come configurare il mirroring di SQL Server per una disponibilità elevata, vedere [mirroring di SQL Server in Lync server 2013](lync-server-2013-sql-server-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="257f5-110">For details about how to configure SQL Server mirroring for high availability, see [SQL Server mirroring in Lync Server 2013](lync-server-2013-sql-server-mirroring.md).</span></span> <span data-ttu-id="257f5-111">Per informazioni dettagliate sul mancato rispetto del database per il ripristino di emergenza, vedere [configurazione della distribuzione di log di SQL Server in Lync server 2013 per il database primario del server di chat persistente](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) e [configurazione del log shipping di SQL Server tra lo specchio principale e il database secondario del log shipping in Lync Server 2013](lync-server-2013-set-up-log-shipping-secondary-database.md).</span><span class="sxs-lookup"><span data-stu-id="257f5-111">For details about failing over the database for disaster recovery, see [Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) and [Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013](lync-server-2013-set-up-log-shipping-secondary-database.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

