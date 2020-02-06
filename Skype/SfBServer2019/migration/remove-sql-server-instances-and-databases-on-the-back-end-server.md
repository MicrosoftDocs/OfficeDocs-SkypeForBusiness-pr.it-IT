---
title: Rimuovere database e istanze di SQL Server nel server back-end
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Si rimuovono i database e le istanze di Microsoft SQL Server dopo aver rimosso i server in uso, oppure dopo aver riconfigurato i server per l'utilizzo di un altro database. È necessario eseguire la procedura descritta in questo argomento quando si ritira il server SQL corrente o si riconfigura il server corrente in modo che esegua il rendering dei database obsoleti o non disponibili.
ms.openlocfilehash: 01552fcd494514802fffb35de7db7643f8cc26fd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812984"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="11e81-104">Rimuovere database e istanze di SQL Server nel server back-end</span><span class="sxs-lookup"><span data-stu-id="11e81-104">Remove SQL Server instances and databases on the Back End Server</span></span>

<span data-ttu-id="11e81-105">Si rimuovono i database e le istanze di Microsoft SQL Server dopo aver rimosso i server in uso, oppure dopo aver riconfigurato i server per l'utilizzo di un altro database.</span><span class="sxs-lookup"><span data-stu-id="11e81-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running that are dependent on them, or after you reconfigure the servers to use another database.</span></span> <span data-ttu-id="11e81-106">È necessario eseguire la procedura descritta in questo argomento quando si ritira il server SQL corrente o si riconfigura il server corrente in modo che esegua il rendering dei database obsoleti o non disponibili.</span><span class="sxs-lookup"><span data-stu-id="11e81-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server in such a way that it renders the databases obsolete or unavailable.</span></span>
  
<span data-ttu-id="11e81-107">Per rimuovere i database o le istanze per il server di archiviazione o il server di monitoraggio, è necessario prima di tutto rimuovere il ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="11e81-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="11e81-108">Allo stesso modo, per rimuovere le istanze o i database per il pool Front-End, devi prima rimuovere o riconfigurare il ruolo del server dipendente.</span><span class="sxs-lookup"><span data-stu-id="11e81-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="11e81-109">Queste procedure non fanno distinzione tra database collocati o istanze separate per i server.</span><span class="sxs-lookup"><span data-stu-id="11e81-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="11e81-110">Le procedure non sono influenzate dalla collocazione dei database.</span><span class="sxs-lookup"><span data-stu-id="11e81-110">The procedures are unaffected by the collocation of databases.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="11e81-111">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="11e81-111">In this section</span></span>

- [<span data-ttu-id="11e81-112">Rimuovere il database di SQL Server per un pool Front End</span><span class="sxs-lookup"><span data-stu-id="11e81-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [<span data-ttu-id="11e81-113">Rimuovere il database di SQL Server per un server di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="11e81-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [<span data-ttu-id="11e81-114">Rimuovere il database di SQL Server per un server di archiviazione</span><span class="sxs-lookup"><span data-stu-id="11e81-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)
    

