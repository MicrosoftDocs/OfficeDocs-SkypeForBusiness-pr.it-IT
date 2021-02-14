---
title: Rimuovere il database di SQL Server per un pool Front End
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
description: Dopo aver rimosso un pool Front End o riconfigurato il pool per l'utilizzo di un database diverso, è possibile rimuovere i database SQL Server che ospitavano i dati del pool. Utilizzare le procedure seguenti per rimuovere le definizioni dal Generatore di topologie e quindi rimuovere i file di database e di registro dal server di database.
ms.openlocfilehash: 9047486708b92c07e6ec099fce43ec4c708fa900
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753408"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="5e6ec-104">Rimuovere il database di SQL Server per un pool Front End</span><span class="sxs-lookup"><span data-stu-id="5e6ec-104">Remove the SQL Server database for a Front End pool</span></span>

<span data-ttu-id="5e6ec-105">Dopo aver rimosso un pool Front End o riconfigurato il pool per l'utilizzo di un database diverso, è possibile rimuovere i database SQL Server che ospitavano i dati del pool.</span><span class="sxs-lookup"><span data-stu-id="5e6ec-105">After you remove a Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="5e6ec-106">Utilizzare le procedure seguenti per rimuovere le definizioni dal Generatore di topologie e quindi rimuovere i file di database e di registro dal server di database.</span><span class="sxs-lookup"><span data-stu-id="5e6ec-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="5e6ec-107">Per rimuovere il database SQL Server utilizzando Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="5e6ec-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="5e6ec-108">Dal Front End Server di Skype for Business Server 2019, aprire Generatore di topologie e scaricare la topologia esistente.</span><span class="sxs-lookup"><span data-stu-id="5e6ec-108">From the Skype for Business Server 2019 Front End Server, open Topology Builder and download the existing topology.</span></span> 
    
2. <span data-ttu-id="5e6ec-109">In Generatore di topologie  passare a Componenti condivisi e quindi **SQL Server Archivi,** fare clic con il pulsante destro del mouse sull'istanza di SQL Server associata al pool Front End rimosso o riconfigurato e quindi scegliere **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="5e6ec-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="5e6ec-110">Pubblicare la topologia, quindi verificare lo stato della replica.</span><span class="sxs-lookup"><span data-stu-id="5e6ec-110">Publish the topology, and then check the replication status.</span></span> 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="5e6ec-111">Per rimuovere i database di utenti e applicazioni dal server SQL server</span><span class="sxs-lookup"><span data-stu-id="5e6ec-111">To remove user and application databases from the SQL server</span></span>

1. <span data-ttu-id="5e6ec-112">Per rimuovere i database nel server SQL, è necessario essere membri del gruppo SQL Server sysadmins per il server SQL in cui si stanno rimuovendo i file di database.</span><span class="sxs-lookup"><span data-stu-id="5e6ec-112">To remove the databases on the SQL server, you must be a member of the SQL Server sysadmins group for the SQL server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="5e6ec-113">Aprire Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5e6ec-113">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="5e6ec-114">Per rimuovere il database dall'archivio utenti del pool, digitare:</span><span class="sxs-lookup"><span data-stu-id="5e6ec-114">To remove the database for the pool user store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="5e6ec-115">Dove è il nome di dominio completo (FQDN) del server di database ed è l'istanza di database denominata, ovvero se ne è  _\<FQDN\>_  _\<instance\>_ stata definita una.</span><span class="sxs-lookup"><span data-stu-id="5e6ec-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="5e6ec-116">Per rimuovere il database dall'archivio applicazioni del pool, digitare:</span><span class="sxs-lookup"><span data-stu-id="5e6ec-116">To remove the database for the pool application store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="5e6ec-117">Dove è il nome di dominio completo del server di database ed è l'istanza di database denominata, ovvero se ne  _\<FQDN\>_  _\<instance\>_ è stata definita una.</span><span class="sxs-lookup"><span data-stu-id="5e6ec-117">Where  _\<FQDN\>_ is the FQDN of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
5. <span data-ttu-id="5e6ec-118">Quando il cmdlet **Uninstall-CsDataBase** richiede di confermare le azioni, leggere le informazioni e quindi premere Y (o INVIO) per continuare oppure premere N e invio se si desidera arrestare il cmdlet (se sono presenti errori).</span><span class="sxs-lookup"><span data-stu-id="5e6ec-118">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

