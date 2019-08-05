---
title: Rimuovere il database di SQL Server per un pool Front-End
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dopo aver rimosso un pool Front-end o aver riconfigurato il pool per l'uso di un database diverso, è possibile rimuovere i database di SQL Server che ospitavano i dati del pool. Usare le procedure seguenti per rimuovere le definizioni da generatore di topologie e quindi rimuovere il database e i file di log dal server di database.
ms.openlocfilehash: e89c8cc670256bf56cb3ff93705766191a9e32c8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195222"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="fd92a-104">Rimuovere il database di SQL Server per un pool Front-End</span><span class="sxs-lookup"><span data-stu-id="fd92a-104">Remove the SQL Server database for a Front End pool</span></span>

<span data-ttu-id="fd92a-105">Dopo aver rimosso un pool Front-end o aver riconfigurato il pool per l'uso di un database diverso, è possibile rimuovere i database di SQL Server che ospitavano i dati del pool.</span><span class="sxs-lookup"><span data-stu-id="fd92a-105">After you remove a Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="fd92a-106">Usare le procedure seguenti per rimuovere le definizioni da generatore di topologie e quindi rimuovere il database e i file di log dal server di database.</span><span class="sxs-lookup"><span data-stu-id="fd92a-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="fd92a-107">Per rimuovere il database di SQL Server tramite Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="fd92a-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="fd92a-108">Dal server front-end di Skype for Business Server 2019 aprire Generatore di topologie e scaricare la topologia esistente.</span><span class="sxs-lookup"><span data-stu-id="fd92a-108">From the Skype for Business Server 2019 Front End Server, open Topology Builder and download the existing topology.</span></span> 
    
2. <span data-ttu-id="fd92a-109">In Generatore di topologie passare a **componenti condivisi** e quindi **archiviare SQL Server**, fare clic con il pulsante destro del mouse sull'istanza di SQL Server associata al pool di front-end rimosso o riconfigurato e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="fd92a-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="fd92a-110">Pubblicare la topologia e quindi controllare lo stato della replica.</span><span class="sxs-lookup"><span data-stu-id="fd92a-110">Publish the topology, and then check the replication status.</span></span> 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="fd92a-111">Per rimuovere i database di utenti e applicazioni da SQL Server</span><span class="sxs-lookup"><span data-stu-id="fd92a-111">To remove user and application databases from the SQL server</span></span>

1. <span data-ttu-id="fd92a-112">Per rimuovere i database di SQL Server, è necessario essere membri del gruppo sysadmin di SQL Server per SQL Server in cui si stanno rimuovendo i file di database.</span><span class="sxs-lookup"><span data-stu-id="fd92a-112">To remove the databases on the SQL server, you must be a member of the SQL Server sysadmins group for the SQL server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="fd92a-113">Aprire Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="fd92a-113">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="fd92a-114">Per rimuovere il database per l'archivio utenti del pool, digitare:</span><span class="sxs-lookup"><span data-stu-id="fd92a-114">To remove the database for the pool user store, type:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="fd92a-115">Dove _ \<FQDN\> _ è il nome di dominio completo (FQDN) del server di database e _ \<instance\> _ è l'istanza di database denominata, ovvero se ne è stata definita una.</span><span class="sxs-lookup"><span data-stu-id="fd92a-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="fd92a-116">Per rimuovere il database per l'archivio delle applicazioni del pool, digitare:</span><span class="sxs-lookup"><span data-stu-id="fd92a-116">To remove the database for the pool application store, type:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="fd92a-117">Dove _ \<FQDN\> _ è il nome di dominio completo del server di database e _ \<instance\> _ è l'istanza di database denominata, ovvero se ne è stata definita una.</span><span class="sxs-lookup"><span data-stu-id="fd92a-117">Where  _\<FQDN\>_ is the FQDN of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
5. <span data-ttu-id="fd92a-118">Quando il cmdlet **Uninstall-CsDatabase** richiede di confermare le azioni, leggere le informazioni e quindi premere Y (o invio) per procedere oppure premere N e quindi immettere se si vuole arrestare il cmdlet (in caso di errori).</span><span class="sxs-lookup"><span data-stu-id="fd92a-118">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

