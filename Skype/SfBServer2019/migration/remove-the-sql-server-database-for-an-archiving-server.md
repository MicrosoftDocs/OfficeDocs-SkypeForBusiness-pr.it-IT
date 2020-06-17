---
title: Rimuovere il database di SQL Server per un server di archiviazione
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
description: Dopo la rimozione di un server di archiviazione, è possibile rimuovere i database di SQL Server che ospitano i dati del pool. Utilizzare le procedure seguenti per rimuovere le definizioni da generatore di topologie, quindi rimuovere il database e i file di registro dal server di database.
ms.openlocfilehash: f8a08b7ea73fa954726bdef986e5a28919c90ceb
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753308"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="02e8c-104">Rimuovere il database di SQL Server per un server di archiviazione</span><span class="sxs-lookup"><span data-stu-id="02e8c-104">Remove the SQL Server database for an Archiving server</span></span>

<span data-ttu-id="02e8c-105">Dopo la rimozione di un server di archiviazione, è possibile rimuovere i database di SQL Server che ospitano i dati del pool.</span><span class="sxs-lookup"><span data-stu-id="02e8c-105">After you remove an Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="02e8c-106">Utilizzare le procedure seguenti per rimuovere le definizioni da generatore di topologie, quindi rimuovere il database e i file di registro dal server di database.</span><span class="sxs-lookup"><span data-stu-id="02e8c-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="02e8c-107">Per rimuovere il database di SQL Server tramite Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="02e8c-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="02e8c-108">Nel server front end di Skype for Business Server 2019 aprire Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="02e8c-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="02e8c-109">In Generatore di topologie, passare a **componenti condivisi** e quindi a **SQL Server Store**, fare clic con il pulsante destro del mouse sull'istanza di SQL Server associata al server di archiviazione rimosso o riconfigurato, quindi fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="02e8c-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="02e8c-110">Pubblicare la topologia, quindi verificare lo stato della replica.</span><span class="sxs-lookup"><span data-stu-id="02e8c-110">Publish the topology, and then check replication status.</span></span> 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="02e8c-111">Per rimuovere i file di database da SQL Server</span><span class="sxs-lookup"><span data-stu-id="02e8c-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="02e8c-112">Per rimuovere i database contenuti nell'istanza di SQL Server, è necessario essere membri del gruppo sysadmins di SQL Server per l'istanza di SQL Server da cui si desidera rimuovere i file di database.</span><span class="sxs-lookup"><span data-stu-id="02e8c-112">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="02e8c-113">Aprire la shell di gestione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="02e8c-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="02e8c-114">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="02e8c-114">At the command line, type the following:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="02e8c-115">Dove _\<FQDN\>_ è il nome di dominio completo (FQDN) del server di database e _\<instance\>_ è l'istanza di database denominata, se ne è stata definita una.</span><span class="sxs-lookup"><span data-stu-id="02e8c-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="02e8c-116">Quando il cmdlet **Uninstall-CsDatabase** richiede di confermare le azioni, leggere le informazioni e quindi premere Y (o invio) per continuare oppure N e quindi immettere se si desidera arrestare il cmdlet (in caso di errori).</span><span class="sxs-lookup"><span data-stu-id="02e8c-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

