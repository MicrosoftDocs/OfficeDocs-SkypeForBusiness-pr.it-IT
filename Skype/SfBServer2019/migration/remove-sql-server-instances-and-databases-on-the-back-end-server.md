---
title: Rimuovere database e istanze di SQL Server nel server back-end
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Rimuovere i database Microsoft SQL Server e le istanze dopo aver rimosso i server in esecuzione che dipendono da essi o dopo aver riconfigurato i server per l'utilizzo di un altro database. È necessario eseguire la procedura descritta in questo argomento quando si ritira il SQL Server corrente o si riconfigura il server corrente in modo che il rendering dei database sia obsoleto o non disponibile.
ms.openlocfilehash: 6e108e4dfef86b482b839bd440f54702ab42107d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752158"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="d91c0-104">Rimuovere database e istanze di SQL Server nel server back-end</span><span class="sxs-lookup"><span data-stu-id="d91c0-104">Remove SQL Server instances and databases on the Back End Server</span></span>

<span data-ttu-id="d91c0-105">Rimuovere i database Microsoft SQL Server e le istanze dopo aver rimosso i server in esecuzione che dipendono da essi o dopo aver riconfigurato i server per l'utilizzo di un altro database.</span><span class="sxs-lookup"><span data-stu-id="d91c0-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running that are dependent on them, or after you reconfigure the servers to use another database.</span></span> <span data-ttu-id="d91c0-106">È necessario eseguire la procedura descritta in questo argomento quando si ritira il SQL Server corrente o si riconfigura il server corrente in modo che il rendering dei database sia obsoleto o non disponibile.</span><span class="sxs-lookup"><span data-stu-id="d91c0-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server in such a way that it renders the databases obsolete or unavailable.</span></span>
  
<span data-ttu-id="d91c0-107">Per rimuovere i database o le istanze per il server di archiviazione o il Monitoring Server, è necessario innanzitutto rimuovere il ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="d91c0-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="d91c0-108">Analogamente, per rimuovere le istanze o i database per il pool Front End, è necessario innanzitutto rimuovere o riconfigurare il ruolo del server dipendente.</span><span class="sxs-lookup"><span data-stu-id="d91c0-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="d91c0-109">Per queste procedure non viene fatta distinzione tra database collocati o istanze separate dei server.</span><span class="sxs-lookup"><span data-stu-id="d91c0-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="d91c0-110">La collocazione dei database non incide sulle procedure.</span><span class="sxs-lookup"><span data-stu-id="d91c0-110">The procedures are unaffected by the collocation of databases.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="d91c0-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d91c0-111">In this section</span></span>

- [<span data-ttu-id="d91c0-112">Rimuovere il database di SQL Server per un pool Front End</span><span class="sxs-lookup"><span data-stu-id="d91c0-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [<span data-ttu-id="d91c0-113">Rimuovere il database di SQL Server per un server di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="d91c0-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [<span data-ttu-id="d91c0-114">Rimuovere il database di SQL Server per un server di archiviazione</span><span class="sxs-lookup"><span data-stu-id="d91c0-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)
    

