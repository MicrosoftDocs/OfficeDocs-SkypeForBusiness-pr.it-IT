---
title: Rimuovere database e istanze di SQL Server nel server back-end
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bd267ea25dc763342c7ca0971b60617243de6f6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499953"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="77771-102">Rimuovere database e istanze di SQL Server nel server back-end</span><span class="sxs-lookup"><span data-stu-id="77771-102">Remove SQL Server instances and databases on the Back End Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77771-103">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="77771-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="77771-104">È possibile rimuovere i database e le istanze di Microsoft SQL Server dopo aver rimosso i server che eseguono Lync Server 2010 che dipendono da essi o dopo aver riconfigurato i server che eseguono Lync Server 2010 per utilizzare un altro database.</span><span class="sxs-lookup"><span data-stu-id="77771-104">You remove the Microsoft SQL Server databases and instances after you remove the servers running Lync Server 2010 that are dependent on them, or after you reconfigure the servers running Lync Server 2010 to use another database.</span></span> <span data-ttu-id="77771-105">È necessario eseguire la procedura descritta in questo argomento quando si ritira l'oggetto SQL Server corrente o si riconfigura il server corrente che esegue Lync Server 2010 in modo che esegua il rendering dei database obsoleti o non disponibili.</span><span class="sxs-lookup"><span data-stu-id="77771-105">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server running Lync Server 2010 in such a way that it renders the databases obsolete or unavailable.</span></span>

<span data-ttu-id="77771-106">Per rimuovere i database o le istanze per il server di archiviazione o il Monitoring Server, è innanzitutto necessario rimuovere il ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="77771-106">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="77771-107">Analogamente, per rimuovere le istanze o i database per il pool Front End, è necessario prima rimuovere o riconfigurare il ruolo del server dipendente.</span><span class="sxs-lookup"><span data-stu-id="77771-107">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="77771-108">Per queste procedure non viene fatta distinzione tra database collocati o istanze separate dei server.</span><span class="sxs-lookup"><span data-stu-id="77771-108">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="77771-109">La collocazione dei database non incide sulle procedure.</span><span class="sxs-lookup"><span data-stu-id="77771-109">The procedures are unaffected by the collocation of databases.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="77771-110">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="77771-110">In This Section</span></span>

  - [<span data-ttu-id="77771-111">Rimuovere il database di SQL Server per un pool Front End</span><span class="sxs-lookup"><span data-stu-id="77771-111">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [<span data-ttu-id="77771-112">Rimuovere il database di SQL Server per un server di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="77771-112">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [<span data-ttu-id="77771-113">Rimuovere il database di SQL Server per un server di archiviazione</span><span class="sxs-lookup"><span data-stu-id="77771-113">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

