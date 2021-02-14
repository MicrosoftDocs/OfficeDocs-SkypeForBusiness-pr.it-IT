---
title: Spostare il server di gestione centrale
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
description: Dopo aver migrato a Skype for Business Server 2019, è necessario spostare il server di gestione centrale nel Front End Server o nel pool di Skype for Business Server 2019, prima di poter rimuovere il server legacy.
ms.openlocfilehash: b5412e1b538627c50c3f2a98a5b68c64364f00a9
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752468"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="7c9a7-103">Spostare il server di gestione centrale legacy in Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="7c9a7-103">Move the legacy Central Management Server to Skype for Business Server 2019</span></span>

<span data-ttu-id="7c9a7-104">Dopo la migrazione a Skype for Business Server 2019 e prima di rimuovere il server legacy, è necessario spostare il server di gestione centrale nel Front End Server o nel pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-104">After migrating to Skype for Business Server 2019, and before you can remove the legacy server, you need to move the Central Management Server to the Skype for Business Server 2019 Front End Server or pool.</span></span> 
  
<span data-ttu-id="7c9a7-105">Il server di gestione centrale è un singolo sistema di replica master/multiple, in cui la copia di lettura/scrittura del database è contenuta nel Front End Server contenente il server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="7c9a7-106">Ogni computer della topologia, incluso il Front End Server contenente il server di gestione centrale, dispone di una copia di sola lettura dei dati dell'archivio di gestione centrale nel database di SQL Server (denominato RTCLOCAL per impostazione predefinita) installato nel computer durante l'installazione e la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="7c9a7-107">Il database locale riceve gli aggiornamenti delle repliche tramite l'agente ReplicaTor di Skype for Business Server che viene eseguito come servizio in tutti i computer.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-107">The local database receives replica updates by way of the Skype for Business Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="7c9a7-108">Il nome del database effettivo nel server di gestione centrale e nella replica locale è XDS, costituito da file xds.mdf e xds.ldf.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="7c9a7-109">Al percorso del database master viene fatto riferimento da un punto di controllo del servizio (SCP) in Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="7c9a7-110">Tutti gli strumenti che utilizzano il server di gestione centrale per gestire e configurare Skype for Business Server utilizzano il pannello di controllo del servizio per individuare l'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-110">All tools that use the Central Management Server to manage and configure Skype for Business Server use the SCP to locate the Central Management store.</span></span>
  
<span data-ttu-id="7c9a7-111">Dopo aver spostato correttamente il server di gestione centrale, è necessario rimuovere i database del server di gestione centrale dal Front End Server originale.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="7c9a7-112">Per informazioni sulla rimozione dei database del server di gestione centrale, vedere [Remove the SQL Server database for a Front End pool.](remove-the-sql-server-database-for-a-front-end-pool.md)</span><span class="sxs-lookup"><span data-stu-id="7c9a7-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>
  
<span data-ttu-id="7c9a7-113">Utilizzare il cmdlet Windows PowerShell **Move-CsManagementServer** in Skype for Business Server Management Shell per spostare il database dal database di SQL Server di installazione legacy al database SQL Server di Skype for Business Server 2019 e quindi aggiornare il punto SCP in modo che punti al percorso del server di gestione centrale di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Skype for Business Server Management Shell to move the database from the legacy install SQL Server database to the Skype for Business Server 2019 SQL Server database, and then update the SCP to point to the Skype for Business Server 2019 Central Management Server location.</span></span> 
  
<span data-ttu-id="7c9a7-114">Utilizzare le procedure descritte in questa sezione per preparare i Front End Server di Skype for Business Server 2019 prima di spostare il server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-114">Use the procedures in this section to prepare the Skype for Business Server 2019 Front End Servers before you move the Central Management Server.</span></span>
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="7c9a7-115">Per preparare un pool Enterprise Edition Front End</span><span class="sxs-lookup"><span data-stu-id="7c9a7-115">To prepare an Enterprise Edition Front End pool</span></span>

1. <span data-ttu-id="7c9a7-116">Nel pool Front End di Skype for Business Server 2019 Enterprise Edition in cui si desidera spostare il server di gestione centrale, accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo **RTCUniversalServerAdmins.**</span><span class="sxs-lookup"><span data-stu-id="7c9a7-116">On the Skype for Business Server 2019 Enterprise Edition Front End pool where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="7c9a7-117">È inoltre necessario disporre SQL Server autorizzazioni utente sysadmin del database nel database in cui si desidera installare l'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-117">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span> 
    
2. <span data-ttu-id="7c9a7-118">Aprire Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-118">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="7c9a7-119">Per creare il nuovo archivio di gestione centrale nel database di SQL Server di Skype for Business Server 2019, in Skype for Business Server Management Shell digitare:</span><span class="sxs-lookup"><span data-stu-id="7c9a7-119">To create the new Central Management store in the Skype for Business Server 2019 SQL Server database, in the Skype for Business Server Management Shell, type:</span></span>
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. <span data-ttu-id="7c9a7-120">Verificare che lo stato del servizio **Front-End** di Skype for Business Server sia **Avviato.**</span><span class="sxs-lookup"><span data-stu-id="7c9a7-120">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="7c9a7-121">Per preparare un Front End Server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="7c9a7-121">To prepare a Standard Edition Front End Server</span></span>

1. <span data-ttu-id="7c9a7-122">In Skype for Business Server 2019 Standard Edition Front End Server in cui si desidera spostare il server di gestione centrale, accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo **RTCUniversalServerAdmins.**</span><span class="sxs-lookup"><span data-stu-id="7c9a7-122">On the Skype for Business Server 2019 Standard Edition Front End Server where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> 
    
2. <span data-ttu-id="7c9a7-123">Aprire la Distribuzione guidata di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-123">Open the Skype for Business Server Deployment Wizard.</span></span>
    
3. <span data-ttu-id="7c9a7-124">Nella Distribuzione guidata di Skype for Business Server, fare clic **su Prepara il primo server Standard Edition.**</span><span class="sxs-lookup"><span data-stu-id="7c9a7-124">In the Skype for Business Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>
    
4. <span data-ttu-id="7c9a7-125">Nella pagina **Esecuzione comandi in** corso, SQL Server Express viene installato come server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-125">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="7c9a7-126">Vengono create le regole firewall necessarie.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-126">Necessary firewall rules are created.</span></span> <span data-ttu-id="7c9a7-127">Al termine dell'installazione del database e dei prerequisiti software, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-127">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7c9a7-128">L'installazione iniziale può richiedere tempo senza che vengano visualizzati aggiornamenti visibili nella schermata riepilogativa di output dei comandi.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-128">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="7c9a7-129">Ciò è dovuto all'installazione di SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-129">This is due to the installation of SQL Server Express.</span></span> <span data-ttu-id="7c9a7-130">Se si desidera monitorare l'installazione del database, usare Gestione attività.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-130">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span> 
  
5. <span data-ttu-id="7c9a7-131">Per creare il nuovo archivio di gestione centrale in Skype for Business Server 2019 Standard Edition Front End Server, in Skype for Business Server Management Shell digitare:</span><span class="sxs-lookup"><span data-stu-id="7c9a7-131">To create the new Central Management store on the Skype for Business Server 2019 Standard Edition Front End Server, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. <span data-ttu-id="7c9a7-132">Verificare che lo stato del servizio **Front-End** di Skype for Business Server sia **Avviato.**</span><span class="sxs-lookup"><span data-stu-id="7c9a7-132">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="7c9a7-133">Per spostare le installazioni legacy del server di gestione centrale in Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="7c9a7-133">To move the legacy installs Central Management Server to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="7c9a7-134">Nel server Skype for Business Server 2019 che sarà il server di gestione centrale, accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo **RTCUniversalServerAdmins.**</span><span class="sxs-lookup"><span data-stu-id="7c9a7-134">On the Skype for Business Server 2019 server that will be the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="7c9a7-135">È anche necessario disporre dei diritti e delle autorizzazioni di amministratore del database SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-135">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="7c9a7-136">Aprire Skype for Business Server Management Shell (esegui come amministratore).</span><span class="sxs-lookup"><span data-stu-id="7c9a7-136">Open Skype for Business Server Management Shell (run as administrator).</span></span>
    
3. <span data-ttu-id="7c9a7-137">In Skype for Business Server Management Shell digitare:</span><span class="sxs-lookup"><span data-stu-id="7c9a7-137">In the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > <span data-ttu-id="7c9a7-138">In `Enable-CsTopology` caso contrario, risolvere il problema impedendo il completamento del comando prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-138">If `Enable-CsTopology` is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="7c9a7-139">Se **Enable-CsTopology** non riesce, lo spostamento avrà esito negativo e potrebbe lasciare la topologia in uno stato in cui non è presente alcun archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-139">If **Enable-CsTopology** is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span> 
  
4. <span data-ttu-id="7c9a7-140">Nel Front End Server o nel pool Front End Server di Skype for Business Server 2019, in Skype for Business Server Management Shell, digitare:</span><span class="sxs-lookup"><span data-stu-id="7c9a7-140">On the Skype for Business Server 2019 Front End Server or Front End pool, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. <span data-ttu-id="7c9a7-141">Skype for Business Server Management Shell visualizza i server, gli archivi file, gli archivi database e i punti di connessione del servizio dello stato corrente e dello stato proposto.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-141">Skype for Business Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="7c9a7-142">Leggere attentamente le informazioni e verificare che l'origine e la destinazione siano corrette.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-142">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="7c9a7-143">Digitare **S** per continuare o **N** per interrompere lo spostamento.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-143">Type **Y** to continue, or **N** to stop the move.</span></span> 
    
6. <span data-ttu-id="7c9a7-144">Esaminare eventuali avvisi o errori generati dal comando **Move-CsManagementServer** e risolverli.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-144">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span> 
    
7. <span data-ttu-id="7c9a7-145">Nel server Skype for Business Server 2019 apri la Distribuzione guidata di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-145">On the Skype for Business Server 2019 server, open the Skype for Business Server Deployment Wizard.</span></span> 
    
8. <span data-ttu-id="7c9a7-146">In Skype for Business Server Deployment Wizard, fare clic su **Install or Update Skype for Business Server System,** click Step **2: Setup or Remove Skype for Business Server Components,** click **Next,** review the summary, and then click **Finish**.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-146">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
9. <span data-ttu-id="7c9a7-147">Nel server di installazione legacy aprire la Distribuzione guidata.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-147">On the legacy install server, open the Deployment Wizard.</span></span> 
    
10. <span data-ttu-id="7c9a7-148">In Skype for Business Server Deployment Wizard, fare clic su **Install or Update Skype for Business Server System,** click Step **2: Setup or Remove Skype for Business Server Components,** click **Next,** review the summary, and then click **Finish**.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-148">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
11. <span data-ttu-id="7c9a7-149">Riavviare il server Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-149">Reboot the Skype for Business Server 2019 server.</span></span> <span data-ttu-id="7c9a7-150">Questa operazione è necessaria a causa di una modifica dell'appartenenza a un gruppo per accedere al database del server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-150">This is required because of a group membership change to access Central Management Server database.</span></span>
    
12. <span data-ttu-id="7c9a7-151">Per verificare che sia in corso la replica con il nuovo archivio di gestione centrale, in Skype for Business Server Management Shell digitare:</span><span class="sxs-lookup"><span data-stu-id="7c9a7-151">To confirm that replication with the new Central Management store is occurring, in the Skype for Business Server Management Shell, type:</span></span> 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > <span data-ttu-id="7c9a7-152">Il processo di replica può richiedere tempo per aggiornare tutte le repliche correnti.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-152">The replication may take some time to update all current replicas.</span></span> 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a><span data-ttu-id="7c9a7-153">Per rimuovere i file dell'archivio di gestione centrale dell'installazione legacy dopo uno spostamento</span><span class="sxs-lookup"><span data-stu-id="7c9a7-153">To remove legacy install Central Management store files after a move</span></span>

1. <span data-ttu-id="7c9a7-154">Nel server di installazione legacy, accedere al computer in cui è installata Skype for Business Server Management Shell come membro del gruppo **RTCUniversalServerAdmins.**</span><span class="sxs-lookup"><span data-stu-id="7c9a7-154">On the legacy install server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="7c9a7-155">È anche necessario disporre dei diritti e delle autorizzazioni di amministratore del database SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-155">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="7c9a7-156">Aprire Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="7c9a7-156">Open Skype for Business Server Management Shell</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="7c9a7-157">Non procedere con la rimozione dei file di database precedenti prima del completamento e della stabilizzazione della replica.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-157">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="7c9a7-158">Se si rimuovono i file prima di completare la replica, il processo di replica verrà interrotto e il server di gestione centrale appena spostato verrà lasciato in uno stato sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-158">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="7c9a7-159">Usare il cmdlet **Get-CsManagementStoreReplicationStatus** per verificare lo stato della replica.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-159">Use the cmdlet **Get-CsManagementStoreReplicationStatus** to confirm the replication status.</span></span> 
  
3. <span data-ttu-id="7c9a7-160">Per rimuovere i file di database dell'archivio di gestione centrale dal server di gestione centrale dell'installazione legacy, digitare:</span><span class="sxs-lookup"><span data-stu-id="7c9a7-160">To remove the Central Management store database files from the legacy install Central Management Server, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    <span data-ttu-id="7c9a7-161">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7c9a7-161">For example:</span></span>
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    <span data-ttu-id="7c9a7-162">Dove il server back-end di installazione legacy è in una distribuzione Enterprise Edition o il  _\<FQDN of SQL Server\>_ nome di dominio completo del server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7c9a7-162">Where the  _\<FQDN of SQL Server\>_ is either the legacy install Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span> 
    

