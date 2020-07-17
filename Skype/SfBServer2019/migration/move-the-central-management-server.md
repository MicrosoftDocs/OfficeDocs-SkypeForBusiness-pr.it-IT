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
description: Dopo aver eseguito la migrazione a Skype for Business Server 2019, è necessario spostare il server di gestione centrale nel server o pool Front End di Skype for Business Server 2019, prima di poter rimuovere il server legacy.
ms.openlocfilehash: b5412e1b538627c50c3f2a98a5b68c64364f00a9
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752468"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="b8915-103">Spostare il server di gestione centrale legacy su Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="b8915-103">Move the legacy Central Management Server to Skype for Business Server 2019</span></span>

<span data-ttu-id="b8915-104">Dopo aver eseguito la migrazione a Skype for Business Server 2019 e prima di poter rimuovere il server legacy, è necessario spostare il server di gestione centrale nel server o nel pool Front End di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b8915-104">After migrating to Skype for Business Server 2019, and before you can remove the legacy server, you need to move the Central Management Server to the Skype for Business Server 2019 Front End Server or pool.</span></span> 
  
<span data-ttu-id="b8915-105">Il server di gestione centrale è un singolo sistema di replica master/multiple, in cui la copia di lettura/scrittura del database è conservata dal front end server che contiene il server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="b8915-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="b8915-106">Ogni computer della topologia, incluso il front end server che contiene il server di gestione centrale, dispone di una copia di sola lettura dei dati dell'archivio di gestione centrale nel database di SQL Server, denominata RTCLOCAL per impostazione predefinita, installata nel computer durante l'installazione e la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b8915-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="b8915-107">Il database locale riceve gli aggiornamenti delle repliche tramite l'agente replica Replicator di Skype for Business Server che viene eseguito come servizio in tutti i computer.</span><span class="sxs-lookup"><span data-stu-id="b8915-107">The local database receives replica updates by way of the Skype for Business Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="b8915-108">Il nome del database effettivo sul server di gestione centrale e la replica locale è XDS, costituito dai file XDS. mdf e XDS. ldf.</span><span class="sxs-lookup"><span data-stu-id="b8915-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="b8915-109">Il percorso del database master è fatto riferimento da un punto di controllo del servizio (SCP) in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b8915-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="b8915-110">Tutti gli strumenti che utilizzano il server di gestione centrale per gestire e configurare Skype for Business Server utilizzano il SCP per individuare l'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="b8915-110">All tools that use the Central Management Server to manage and configure Skype for Business Server use the SCP to locate the Central Management store.</span></span>
  
<span data-ttu-id="b8915-111">Dopo aver correttamente spostato il server di gestione centrale, è necessario rimuovere i database del server di gestione centrale dal front end server originale.</span><span class="sxs-lookup"><span data-stu-id="b8915-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="b8915-112">Per informazioni sulla rimozione dei database del server di gestione centrale, vedere [rimuovere il database di SQL Server per un pool Front End](remove-the-sql-server-database-for-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="b8915-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>
  
<span data-ttu-id="b8915-113">Utilizzare il cmdlet **Move-csmanagementserver** di Windows PowerShell in Skype for Business Server Management Shell per spostare il database dal database di SQL Server di installazione legacy al database di SQL Server di Skype for business server 2019 e quindi aggiornare il punto SCP in modo che punti al percorso del server di gestione centrale di Skype for business server 2019.</span><span class="sxs-lookup"><span data-stu-id="b8915-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Skype for Business Server Management Shell to move the database from the legacy install SQL Server database to the Skype for Business Server 2019 SQL Server database, and then update the SCP to point to the Skype for Business Server 2019 Central Management Server location.</span></span> 
  
<span data-ttu-id="b8915-114">Utilizzare le procedure descritte in questa sezione per preparare i server front end di Skype for Business Server 2019 prima di spostare il server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="b8915-114">Use the procedures in this section to prepare the Skype for Business Server 2019 Front End Servers before you move the Central Management Server.</span></span>
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="b8915-115">Per preparare un pool Enterprise Edition front end</span><span class="sxs-lookup"><span data-stu-id="b8915-115">To prepare an Enterprise Edition Front End pool</span></span>

1. <span data-ttu-id="b8915-116">Nel pool di Skype for Business Server 2019 Enterprise Edition front end in cui si desidera spostare il server di gestione centrale, accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="b8915-116">On the Skype for Business Server 2019 Enterprise Edition Front End pool where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="b8915-117">È inoltre necessario disporre di autorizzazioni e diritti utente del database di SQL Server per il database in cui si desidera installare l'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="b8915-117">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span> 
    
2. <span data-ttu-id="b8915-118">Aprire la shell di gestione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b8915-118">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="b8915-119">Per creare il nuovo archivio di gestione centrale nel database di SQL Server di Skype for Business Server 2019, in Skype for Business Server Management Shell digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b8915-119">To create the new Central Management store in the Skype for Business Server 2019 SQL Server database, in the Skype for Business Server Management Shell, type:</span></span>
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. <span data-ttu-id="b8915-120">Verificare che lo stato del servizio **front-end di Skype for Business Server** sia **avviato**.</span><span class="sxs-lookup"><span data-stu-id="b8915-120">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="b8915-121">Per preparare un front end server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="b8915-121">To prepare a Standard Edition Front End Server</span></span>

1. <span data-ttu-id="b8915-122">In Skype for Business Server 2019 Standard Edition Front End Server in cui si desidera spostare il server di gestione centrale, accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="b8915-122">On the Skype for Business Server 2019 Standard Edition Front End Server where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> 
    
2. <span data-ttu-id="b8915-123">Aprire la distribuzione guidata di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b8915-123">Open the Skype for Business Server Deployment Wizard.</span></span>
    
3. <span data-ttu-id="b8915-124">Nella distribuzione guidata di Skype for Business Server, fare clic su **prepara primo server Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="b8915-124">In the Skype for Business Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>
    
4. <span data-ttu-id="b8915-125">Nella pagina **esecuzione comandi** in corso, SQL Server Express è installato come server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="b8915-125">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="b8915-126">Vengono create le regole firewall necessarie.</span><span class="sxs-lookup"><span data-stu-id="b8915-126">Necessary firewall rules are created.</span></span> <span data-ttu-id="b8915-127">Al termine dell'installazione del database e dei prerequisiti software, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="b8915-127">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b8915-128">L'installazione iniziale può richiedere tempo senza che vengano visualizzati aggiornamenti visibili nella schermata riepilogativa di output dei comandi.</span><span class="sxs-lookup"><span data-stu-id="b8915-128">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="b8915-129">Ciò è dovuto all'installazione di SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="b8915-129">This is due to the installation of SQL Server Express.</span></span> <span data-ttu-id="b8915-130">Se si desidera monitorare l'installazione del database, usare Gestione attività.</span><span class="sxs-lookup"><span data-stu-id="b8915-130">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span> 
  
5. <span data-ttu-id="b8915-131">Per creare il nuovo archivio di gestione centrale in Skype for Business Server 2019 Standard Edition Front End Server, in Skype for Business Server Management Shell digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b8915-131">To create the new Central Management store on the Skype for Business Server 2019 Standard Edition Front End Server, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. <span data-ttu-id="b8915-132">Verificare che lo stato del servizio **front-end di Skype for Business Server** sia **avviato**.</span><span class="sxs-lookup"><span data-stu-id="b8915-132">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="b8915-133">Per spostare l'eredità, installa il server di gestione centrale in Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="b8915-133">To move the legacy installs Central Management Server to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="b8915-134">Sul server Skype for Business Server 2019 che fungerà da server di gestione centrale, accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="b8915-134">On the Skype for Business Server 2019 server that will be the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="b8915-135">È anche necessario disporre dei diritti e delle autorizzazioni di amministratore del database SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b8915-135">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="b8915-136">Aprire Skype for Business Server Management Shell (Esegui come amministratore).</span><span class="sxs-lookup"><span data-stu-id="b8915-136">Open Skype for Business Server Management Shell (run as administrator).</span></span>
    
3. <span data-ttu-id="b8915-137">In Skype for Business Server Management Shell, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b8915-137">In the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > <span data-ttu-id="b8915-138">Se `Enable-CsTopology` l'operazione non è riuscita, risolvere il problema impedendo il completamento del comando prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="b8915-138">If `Enable-CsTopology` is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="b8915-139">Se **Enable-CsTopology** non ha esito positivo, lo spostamento avrà esito negativo e potrebbe lasciare la topologia in uno stato in cui non è presente un archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="b8915-139">If **Enable-CsTopology** is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span> 
  
4. <span data-ttu-id="b8915-140">In Skype for Business Server 2019 front end server o pool Front End, digitare quanto segue nella shell di gestione di Lync</span><span class="sxs-lookup"><span data-stu-id="b8915-140">On the Skype for Business Server 2019 Front End Server or Front End pool, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. <span data-ttu-id="b8915-141">Skype for Business Server Management Shell consente di visualizzare i server, gli archivi di file, gli archivi di database e i punti di connessione del servizio dello stato corrente e dello stato proposto.</span><span class="sxs-lookup"><span data-stu-id="b8915-141">Skype for Business Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="b8915-142">Leggere attentamente le informazioni e verificare che l'origine e la destinazione siano corrette.</span><span class="sxs-lookup"><span data-stu-id="b8915-142">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="b8915-143">Digitare **S** per continuare o **N** per interrompere lo spostamento.</span><span class="sxs-lookup"><span data-stu-id="b8915-143">Type **Y** to continue, or **N** to stop the move.</span></span> 
    
6. <span data-ttu-id="b8915-144">Esaminare eventuali avvisi o errori generati dal comando **Move-CsManagementServer** e risolverli.</span><span class="sxs-lookup"><span data-stu-id="b8915-144">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span> 
    
7. <span data-ttu-id="b8915-145">Sul server Skype for Business Server 2019, aprire la distribuzione guidata di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b8915-145">On the Skype for Business Server 2019 server, open the Skype for Business Server Deployment Wizard.</span></span> 
    
8. <span data-ttu-id="b8915-146">Nella distribuzione guidata di Skype for Business Server, fare clic su **Installa o aggiorna il sistema di Skype for Business Server**, fare clic su **passaggio 2: installazione o rimozione dei componenti di Skype for Business Server**, fare clic su **Avanti**, esaminare il riepilogo e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="b8915-146">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
9. <span data-ttu-id="b8915-147">Nel server di installazione legacy aprire la distribuzione guidata.</span><span class="sxs-lookup"><span data-stu-id="b8915-147">On the legacy install server, open the Deployment Wizard.</span></span> 
    
10. <span data-ttu-id="b8915-148">Nella distribuzione guidata di Skype for Business Server, fare clic su **Installa o aggiorna il sistema di Skype for Business Server**, fare clic su **passaggio 2: installazione o rimozione dei componenti di Skype for Business Server**, fare clic su **Avanti**, esaminare il riepilogo e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="b8915-148">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
11. <span data-ttu-id="b8915-149">Riavviare il server Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b8915-149">Reboot the Skype for Business Server 2019 server.</span></span> <span data-ttu-id="b8915-150">Questa operazione è necessaria a causa di una modifica dell'appartenenza a un gruppo al database del server di gestione centrale di Access.</span><span class="sxs-lookup"><span data-stu-id="b8915-150">This is required because of a group membership change to access Central Management Server database.</span></span>
    
12. <span data-ttu-id="b8915-151">Per confermare che la replica con il nuovo archivio di gestione centrale si sta verificando, in Skype for Business Server Management Shell digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b8915-151">To confirm that replication with the new Central Management store is occurring, in the Skype for Business Server Management Shell, type:</span></span> 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > <span data-ttu-id="b8915-152">Il processo di replica può richiedere tempo per aggiornare tutte le repliche correnti.</span><span class="sxs-lookup"><span data-stu-id="b8915-152">The replication may take some time to update all current replicas.</span></span> 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a><span data-ttu-id="b8915-153">Per rimuovere i file dell'archivio di gestione centrale di installazione legacy dopo uno spostamento</span><span class="sxs-lookup"><span data-stu-id="b8915-153">To remove legacy install Central Management store files after a move</span></span>

1. <span data-ttu-id="b8915-154">Nel server di installazione legacy, eseguire l'accesso al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="b8915-154">On the legacy install server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="b8915-155">È anche necessario disporre dei diritti e delle autorizzazioni di amministratore del database SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b8915-155">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="b8915-156">Aprire la shell di gestione di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b8915-156">Open Skype for Business Server Management Shell</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="b8915-157">Non procedere con la rimozione dei file di database precedenti prima del completamento e della stabilizzazione della replica.</span><span class="sxs-lookup"><span data-stu-id="b8915-157">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="b8915-158">Se si rimuovono i file prima del completamento della replica, si interrompe il processo di replica e si lascia il server di gestione centrale appena spostato in uno stato sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b8915-158">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="b8915-159">Usare il cmdlet **Get-CsManagementStoreReplicationStatus** per verificare lo stato della replica.</span><span class="sxs-lookup"><span data-stu-id="b8915-159">Use the cmdlet **Get-CsManagementStoreReplicationStatus** to confirm the replication status.</span></span> 
  
3. <span data-ttu-id="b8915-160">Per rimuovere i file di database dell'archivio di gestione centrale dal server di gestione centrale di installazione legacy, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b8915-160">To remove the Central Management store database files from the legacy install Central Management Server, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    <span data-ttu-id="b8915-161">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b8915-161">For example:</span></span>
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    <span data-ttu-id="b8915-162">Dove _\<FQDN of SQL Server\>_ è il server back-end di installazione legacy in una distribuzione Enterprise Edition o il nome di dominio completo del server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="b8915-162">Where the  _\<FQDN of SQL Server\>_ is either the legacy install Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span> 
    

