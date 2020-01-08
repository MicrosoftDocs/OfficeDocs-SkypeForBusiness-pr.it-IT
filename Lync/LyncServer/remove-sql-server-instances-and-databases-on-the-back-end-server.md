---
title: Rimuovere database e istanze di SQL Server nel server back-end
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f03a318e81b839d5f92dbaa4ddcc70bbbc8e2e3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="8602d-102">Rimuovere database e istanze di SQL Server nel server back-end</span><span class="sxs-lookup"><span data-stu-id="8602d-102">Remove SQL Server instances and databases on the Back End Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8602d-103">_**Argomento Ultima modifica:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="8602d-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="8602d-104">Si rimuovono i database e le istanze di Microsoft SQL Server dopo aver rimosso i server in cui è in uso Lync Server 2010, o dopo aver riconfigurato i server che usano Lync Server 2010 per usare un altro database.</span><span class="sxs-lookup"><span data-stu-id="8602d-104">You remove the Microsoft SQL Server databases and instances after you remove the servers running Lync Server 2010 that are dependent on them, or after you reconfigure the servers running Lync Server 2010 to use another database.</span></span> <span data-ttu-id="8602d-105">È necessario eseguire la procedura descritta in questo argomento quando si ritira il server SQL corrente o si riconfigura il server corrente che esegue Lync Server 2010 in modo che esegua il rendering dei database obsoleti o non disponibili.</span><span class="sxs-lookup"><span data-stu-id="8602d-105">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server running Lync Server 2010 in such a way that it renders the databases obsolete or unavailable.</span></span>

<span data-ttu-id="8602d-106">Per rimuovere i database o le istanze per il server di archiviazione o il server di monitoraggio, è necessario prima di tutto rimuovere il ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="8602d-106">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="8602d-107">Allo stesso modo, per rimuovere le istanze o i database per il pool Front-End, devi prima rimuovere o riconfigurare il ruolo del server dipendente.</span><span class="sxs-lookup"><span data-stu-id="8602d-107">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="8602d-108">Queste procedure non fanno distinzione tra database collocati o istanze separate per i server.</span><span class="sxs-lookup"><span data-stu-id="8602d-108">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="8602d-109">Le procedure non sono influenzate dalla collocazione dei database.</span><span class="sxs-lookup"><span data-stu-id="8602d-109">The procedures are unaffected by the collocation of databases.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8602d-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="8602d-110">In This Section</span></span>

  - [<span data-ttu-id="8602d-111">Rimuovere il database di SQL Server per un pool Front End</span><span class="sxs-lookup"><span data-stu-id="8602d-111">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [<span data-ttu-id="8602d-112">Rimuovere il database di SQL Server per un server di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="8602d-112">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [<span data-ttu-id="8602d-113">Rimuovere il database di SQL Server per un server di archiviazione</span><span class="sxs-lookup"><span data-stu-id="8602d-113">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

