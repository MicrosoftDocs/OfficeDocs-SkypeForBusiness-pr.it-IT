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
description: Dopo la rimozione di un pool Front end o la riconfigurazione del pool per l'utilizzo di un database diverso, è possibile rimuovere i database di SQL Server che ospitano i dati del pool. Utilizzare le procedure seguenti per rimuovere le definizioni da generatore di topologie, quindi rimuovere il database e i file di registro dal server di database.
ms.openlocfilehash: 9047486708b92c07e6ec099fce43ec4c708fa900
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753408"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="65c47-104">Rimuovere il database di SQL Server per un pool Front End</span><span class="sxs-lookup"><span data-stu-id="65c47-104">Remove the SQL Server database for a Front End pool</span></span>

<span data-ttu-id="65c47-105">Dopo la rimozione di un pool Front end o la riconfigurazione del pool per l'utilizzo di un database diverso, è possibile rimuovere i database di SQL Server che ospitano i dati del pool.</span><span class="sxs-lookup"><span data-stu-id="65c47-105">After you remove a Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="65c47-106">Utilizzare le procedure seguenti per rimuovere le definizioni da generatore di topologie, quindi rimuovere il database e i file di registro dal server di database.</span><span class="sxs-lookup"><span data-stu-id="65c47-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="65c47-107">Per rimuovere il database di SQL Server tramite Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="65c47-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="65c47-108">Dal front end server di Skype for Business Server 2019, aprire Generatore di topologie e scaricare la topologia esistente.</span><span class="sxs-lookup"><span data-stu-id="65c47-108">From the Skype for Business Server 2019 Front End Server, open Topology Builder and download the existing topology.</span></span> 
    
2. <span data-ttu-id="65c47-109">In Generatore di topologie, passare a **componenti condivisi** e quindi a **SQL Server Store**, fare clic con il pulsante destro del mouse sull'istanza di SQL Server associata al pool Front End rimosso o riconfigurato, quindi fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="65c47-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="65c47-110">Pubblicare la topologia, quindi verificare lo stato della replica.</span><span class="sxs-lookup"><span data-stu-id="65c47-110">Publish the topology, and then check the replication status.</span></span> 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="65c47-111">Per rimuovere i database dell'utente e dell'applicazione da SQL Server</span><span class="sxs-lookup"><span data-stu-id="65c47-111">To remove user and application databases from the SQL server</span></span>

1. <span data-ttu-id="65c47-112">Per rimuovere i database di SQL Server, è necessario essere membri del gruppo sysadmins di SQL Server per SQL Server in cui si stanno rimuovendo i file di database.</span><span class="sxs-lookup"><span data-stu-id="65c47-112">To remove the databases on the SQL server, you must be a member of the SQL Server sysadmins group for the SQL server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="65c47-113">Aprire Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="65c47-113">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="65c47-114">Per rimuovere il database dall'archivio utenti del pool, digitare:</span><span class="sxs-lookup"><span data-stu-id="65c47-114">To remove the database for the pool user store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="65c47-115">Dove _\<FQDN\>_ è il nome di dominio completo (FQDN) del server di database e _\<instance\>_ è l'istanza di database denominata, se ne è stata definita una.</span><span class="sxs-lookup"><span data-stu-id="65c47-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="65c47-116">Per rimuovere il database dall'archivio applicazioni del pool, digitare:</span><span class="sxs-lookup"><span data-stu-id="65c47-116">To remove the database for the pool application store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="65c47-117">Dove _\<FQDN\>_ è il nome di dominio completo del server di database e _\<instance\>_ è l'istanza di database denominata, se ne è stata definita una.</span><span class="sxs-lookup"><span data-stu-id="65c47-117">Where  _\<FQDN\>_ is the FQDN of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
5. <span data-ttu-id="65c47-118">Quando il cmdlet **Uninstall-CsDatabase** richiede di confermare le azioni, leggere le informazioni e quindi premere Y (o invio) per continuare oppure N e quindi immettere se si desidera arrestare il cmdlet (in caso di errori).</span><span class="sxs-lookup"><span data-stu-id="65c47-118">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

