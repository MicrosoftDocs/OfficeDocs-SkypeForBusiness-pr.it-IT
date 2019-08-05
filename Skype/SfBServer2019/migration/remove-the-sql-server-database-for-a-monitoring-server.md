---
title: Rimuovere il database di SQL Server per un server di monitoraggio
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dopo aver rimosso un server di monitoraggio, è possibile rimuovere i database di SQL Server che ospitavano i dati del server. Usare le procedure seguenti per rimuovere le definizioni da generatore di topologie e quindi rimuovere il database e i file di log dal server di database.
ms.openlocfilehash: 2f4a6feb78adb9daa15cb8d59c2041740e45a19d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195221"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="ba17f-104">Rimuovere il database di SQL Server per un server di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="ba17f-104">Remove the SQL Server database for a Monitoring server</span></span>

<span data-ttu-id="ba17f-105">Dopo aver rimosso un server di monitoraggio, è possibile rimuovere i database di SQL Server che ospitavano i dati del server.</span><span class="sxs-lookup"><span data-stu-id="ba17f-105">After you remove a Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="ba17f-106">Usare le procedure seguenti per rimuovere le definizioni da generatore di topologie e quindi rimuovere il database e i file di log dal server di database.</span><span class="sxs-lookup"><span data-stu-id="ba17f-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="ba17f-107">Per rimuovere il database di SQL Server tramite Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="ba17f-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="ba17f-108">Nel server front-end di Skype for Business Server 2019 aprire Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="ba17f-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="ba17f-109">In Generatore di topologie passare a **componenti condivisi** e quindi **archiviare SQL Server**, fare clic con il pulsante destro del mouse sull'istanza di SQL Server associata al server di monitoraggio rimosso o riconfigurato e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="ba17f-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="ba17f-110">Pubblicare la topologia e quindi controllare lo stato della replica.</span><span class="sxs-lookup"><span data-stu-id="ba17f-110">Publish the topology, and then check replication status.</span></span>
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="ba17f-111">Per rimuovere i file di database da SQL Server</span><span class="sxs-lookup"><span data-stu-id="ba17f-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="ba17f-112">Per rimuovere i database nel server basato su SQL Server, è necessario essere membri del gruppo sysadmin di SQL Server per il server SQL Server in cui si stanno rimuovendo i file di database.</span><span class="sxs-lookup"><span data-stu-id="ba17f-112">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>
    
2. <span data-ttu-id="ba17f-113">Aprire Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ba17f-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="ba17f-114">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="ba17f-114">At the command line, type the following:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="ba17f-115">Dove _ \<FQDN\> _ è il nome di dominio completo (FQDN) del server di database e _ \<instance\> _ è l'istanza di database denominata facoltativa.</span><span class="sxs-lookup"><span data-stu-id="ba17f-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the optional named database instance.</span></span> 
    
4. <span data-ttu-id="ba17f-116">Quando il cmdlet **Uninstall-CsDatabase** richiede di confermare le azioni, leggere le informazioni e quindi premere Y (o invio) per procedere oppure premere N e quindi immettere se si vuole arrestare il cmdlet (in caso di errori).</span><span class="sxs-lookup"><span data-stu-id="ba17f-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

