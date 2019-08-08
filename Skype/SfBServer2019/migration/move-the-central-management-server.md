---
title: Trasferire il server di gestione centrale
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dopo aver eseguito la migrazione a Skype for Business Server 2019, è necessario trasferire il server di gestione centrale nel server o nel pool di Skype for Business Server 2019 front end, prima di poter rimuovere il server legacy.
ms.openlocfilehash: 7ba82a3748a98e2f1bc25cd7c48eceabdf76ac19
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244709"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="a424a-103">Trasferire il server di gestione centrale legacy in Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="a424a-103">Move the legacy Central Management Server to Skype for Business Server 2019</span></span>

<span data-ttu-id="a424a-104">Dopo aver eseguito la migrazione a Skype for Business Server 2019 e prima di poter rimuovere il server legacy, è necessario trasferire il server di gestione centrale nel server o nel pool di front end di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a424a-104">After migrating to Skype for Business Server 2019, and before you can remove the legacy server, you need to move the Central Management Server to the Skype for Business Server 2019 Front End Server or pool.</span></span> 
  
<span data-ttu-id="a424a-105">Il server di gestione centrale è un singolo sistema master/replica multipla, in cui la copia di lettura/scrittura del database è tenuta dal server front-end che contiene il server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="a424a-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="a424a-106">Ogni computer della topologia, incluso il front end server che contiene il server di gestione centrale, ha una copia di sola lettura dei dati di Central Management store nel database di SQL Server (denominata RTCLOCAL per impostazione predefinita) installati nel computer durante l'installazione e distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a424a-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="a424a-107">Il database locale riceve gli aggiornamenti delle repliche tramite l'agente di replica Replicator di Skype for Business Server che viene eseguito come servizio in tutti i computer.</span><span class="sxs-lookup"><span data-stu-id="a424a-107">The local database receives replica updates by way of the Skype for Business Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="a424a-108">Il nome del database effettivo nel server di gestione centrale e la replica locale è XDS, costituito dai file XDS. mdf e XDS. ldf.</span><span class="sxs-lookup"><span data-stu-id="a424a-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="a424a-109">Il percorso del database master viene fatto riferimento da un punto di controllo del servizio (SCP) in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a424a-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="a424a-110">Tutti gli strumenti che usano il server di gestione centralizzato per gestire e configurare Skype for Business Server usano l'SCP per individuare l'Central Management store.</span><span class="sxs-lookup"><span data-stu-id="a424a-110">All tools that use the Central Management Server to manage and configure Skype for Business Server use the SCP to locate the Central Management store.</span></span>
  
<span data-ttu-id="a424a-111">Dopo aver spostato correttamente il server di gestione centrale, è necessario rimuovere i database di Central Management Server dal server front-end originale.</span><span class="sxs-lookup"><span data-stu-id="a424a-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="a424a-112">Per informazioni sulla rimozione dei database di Central Management Server, vedere [rimuovere il database di SQL Server per un pool Front-End](remove-the-sql-server-database-for-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="a424a-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>
  
<span data-ttu-id="a424a-113">Puoi usare il cmdlet **Move-csmanagementserver** di Windows PowerShell in Skype for Business Server Management Shell per trasferire il database dal database di SQL Server di installazione legacy al database di SQL Server di Skype for business server 2019 e quindi aggiornare il SCP in modo che punti alla posizione del server di gestione centralizzata di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a424a-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Skype for Business Server Management Shell to move the database from the legacy install SQL Server database to the Skype for Business Server 2019 SQL Server database, and then update the SCP to point to the Skype for Business Server 2019 Central Management Server location.</span></span> 
  
<span data-ttu-id="a424a-114">Usare le procedure descritte in questa sezione per preparare i server front end di Skype for Business Server 2019 prima di trasferire il server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="a424a-114">Use the procedures in this section to prepare the Skype for Business Server 2019 Front End Servers before you move the Central Management Server.</span></span>
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="a424a-115">Per preparare un pool di front-end Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="a424a-115">To prepare an Enterprise Edition Front End pool</span></span>

1. <span data-ttu-id="a424a-116">Nel pool di front end di Skype for Business Server 2019 Enterprise Edition in cui si vuole spostare il server di gestione centralizzato, accedere al computer in cui è installato Skype for Business Server Management Shell come membro di \*\*RTCUniversalServerAdmins \*\*gruppo.</span><span class="sxs-lookup"><span data-stu-id="a424a-116">On the Skype for Business Server 2019 Enterprise Edition Front End pool where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="a424a-117">Per il database in cui si vuole installare l'Central Management store, è necessario disporre anche dei diritti utente e delle autorizzazioni di amministratore del database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a424a-117">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span> 
    
2. <span data-ttu-id="a424a-118">Aprire Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a424a-118">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="a424a-119">Per creare il nuovo Central Management store nel database di SQL Server di Skype for Business Server 2019, in Skype for Business Server Management Shell digitare:</span><span class="sxs-lookup"><span data-stu-id="a424a-119">To create the new Central Management store in the Skype for Business Server 2019 SQL Server database, in the Skype for Business Server Management Shell, type:</span></span>
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. <span data-ttu-id="a424a-120">Verificare che lo stato del servizio **front-end di Skype for Business Server** sia stato **avviato**.</span><span class="sxs-lookup"><span data-stu-id="a424a-120">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="a424a-121">Per preparare un server front-end Standard Edition</span><span class="sxs-lookup"><span data-stu-id="a424a-121">To prepare a Standard Edition Front End Server</span></span>

1. <span data-ttu-id="a424a-122">Nel server front-end di Skype for Business Server 2019 Standard Edition in cui si vuole spostare il server di gestione centralizzato, accedere al computer in cui è installato Skype for Business Server Management Shell come membro di \*\*RTCUniversalServerAdmins \*\*gruppo.</span><span class="sxs-lookup"><span data-stu-id="a424a-122">On the Skype for Business Server 2019 Standard Edition Front End Server where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> 
    
2. <span data-ttu-id="a424a-123">Aprire la distribuzione guidata di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a424a-123">Open the Skype for Business Server Deployment Wizard.</span></span>
    
3. <span data-ttu-id="a424a-124">Nella distribuzione guidata di Skype for Business Server fare clic su **prepara primo server Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="a424a-124">In the Skype for Business Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>
    
4. <span data-ttu-id="a424a-125">Nella pagina **esecuzione dei comandi** , SQL Server Express viene installato come server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="a424a-125">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="a424a-126">Vengono create le regole firewall necessarie.</span><span class="sxs-lookup"><span data-stu-id="a424a-126">Necessary firewall rules are created.</span></span> <span data-ttu-id="a424a-127">Dopo aver completato l'installazione del database e del software prerequisito, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="a424a-127">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a424a-128">L'installazione iniziale può richiedere del tempo senza aggiornamenti visibili alla schermata di riepilogo dell'output del comando.</span><span class="sxs-lookup"><span data-stu-id="a424a-128">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="a424a-129">Ciò è dovuto all'installazione di SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="a424a-129">This is due to the installation of SQL Server Express.</span></span> <span data-ttu-id="a424a-130">Se è necessario monitorare l'installazione del database, usare Gestione attività per monitorare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="a424a-130">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span> 
  
5. <span data-ttu-id="a424a-131">Per creare il nuovo Central Management store in Skype for Business Server 2019 Standard Edition Front End Server, in Skype for Business Server Management Shell digitare:</span><span class="sxs-lookup"><span data-stu-id="a424a-131">To create the new Central Management store on the Skype for Business Server 2019 Standard Edition Front End Server, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. <span data-ttu-id="a424a-132">Verificare che lo stato del servizio **front-end di Skype for Business Server** sia stato **avviato**.</span><span class="sxs-lookup"><span data-stu-id="a424a-132">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="a424a-133">Per trasferire l'eredità, installa il server di gestione centrale in Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="a424a-133">To move the legacy installs Central Management Server to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="a424a-134">Nel server Skype for Business Server 2019, che sarà il server di gestione centrale, accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="a424a-134">On the Skype for Business Server 2019 server that will be the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="a424a-135">È inoltre necessario disporre dei diritti e delle autorizzazioni per gli utenti di amministratore del database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a424a-135">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="a424a-136">Aprire Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a424a-136">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="a424a-137">In Skype for Business Server Management Shell digitare:</span><span class="sxs-lookup"><span data-stu-id="a424a-137">In the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Enable-CsTopology
   ```

    > [!CAUTION]
    > <span data-ttu-id="a424a-138">Se `Enable-CsTopology` l'operazione non riesce, risolvere il problema impedendo il completamento del comando prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="a424a-138">If `Enable-CsTopology` is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="a424a-139">Se **Enable-CsTopology** non riesce, il passaggio non riesce e può lasciare la topologia in uno stato in cui non è presente un Central Management store.</span><span class="sxs-lookup"><span data-stu-id="a424a-139">If **Enable-CsTopology** is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span> 
  
4. <span data-ttu-id="a424a-140">In Skype for Business Server 2019 front end server o front end pool, in Skype for Business Server Management Shell digitare:</span><span class="sxs-lookup"><span data-stu-id="a424a-140">On the Skype for Business Server 2019 Front End Server or Front End pool, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```
   Move-CsManagementServer
   ```

5. <span data-ttu-id="a424a-141">Skype for Business Server Management Shell Visualizza i server, gli archivi di file, gli archivi di database e i punti di connessione del servizio dello stato corrente e dello stato proposto.</span><span class="sxs-lookup"><span data-stu-id="a424a-141">Skype for Business Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="a424a-142">Leggere attentamente le informazioni e verificare che si tratta dell'origine e della destinazione desiderate.</span><span class="sxs-lookup"><span data-stu-id="a424a-142">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="a424a-143">Digitare **Y** per continuare o **N** per interrompere lo stato di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="a424a-143">Type **Y** to continue, or **N** to stop the move.</span></span> 
    
6. <span data-ttu-id="a424a-144">Esaminare gli avvisi o gli errori generati dal comando **Move-csmanagementserver** e risolverli.</span><span class="sxs-lookup"><span data-stu-id="a424a-144">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span> 
    
7. <span data-ttu-id="a424a-145">Nel server Skype for Business Server 2019 aprire la distribuzione guidata di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a424a-145">On the Skype for Business Server 2019 server, open the Skype for Business Server Deployment Wizard.</span></span> 
    
8. <span data-ttu-id="a424a-146">Nella distribuzione guidata di Skype for Business Server fare clic su **installazione o aggiornamento di Skype for Business Server System**, fare clic su **passaggio 2: configurare o rimuovere i componenti di Skype for Business Server**, fare clic su **Avanti**, rivedere il riepilogo e quindi fare clic su \*\*fine. \*\*.</span><span class="sxs-lookup"><span data-stu-id="a424a-146">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
9. <span data-ttu-id="a424a-147">Nel server di installazione legacy aprire la distribuzione guidata.</span><span class="sxs-lookup"><span data-stu-id="a424a-147">On the legacy install server, open the Deployment Wizard.</span></span> 
    
10. <span data-ttu-id="a424a-148">Nella distribuzione guidata di Skype for Business Server fare clic su **installazione o aggiornamento di Skype for Business Server System**, fare clic su **passaggio 2: configurare o rimuovere i componenti di Skype for Business Server**, fare clic su **Avanti**, rivedere il riepilogo e quindi fare clic su \*\*fine. \*\*.</span><span class="sxs-lookup"><span data-stu-id="a424a-148">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
11. <span data-ttu-id="a424a-149">Riavviare il server di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a424a-149">Reboot the Skype for Business Server 2019 server.</span></span> <span data-ttu-id="a424a-150">Questa operazione è necessaria a causa di una modifica dell'appartenenza al gruppo per accedere al database di Central Management Server.</span><span class="sxs-lookup"><span data-stu-id="a424a-150">This is required because of a group membership change to access Central Management Server database.</span></span>
    
12. <span data-ttu-id="a424a-151">Per verificare che la replica con il nuovo Central Management store si verifichi, in Skype for Business Server Management Shell digitare:</span><span class="sxs-lookup"><span data-stu-id="a424a-151">To confirm that replication with the new Central Management store is occurring, in the Skype for Business Server Management Shell, type:</span></span> 
    
    ```
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > <span data-ttu-id="a424a-152">La replica può richiedere del tempo per aggiornare tutte le repliche correnti.</span><span class="sxs-lookup"><span data-stu-id="a424a-152">The replication may take some time to update all current replicas.</span></span> 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a><span data-ttu-id="a424a-153">Per rimuovere i file legacy install Central Management store dopo una mossa</span><span class="sxs-lookup"><span data-stu-id="a424a-153">To remove legacy install Central Management store files after a move</span></span>

1. <span data-ttu-id="a424a-154">Nel server di installazione legacy accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="a424a-154">On the legacy install server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="a424a-155">È inoltre necessario disporre dei diritti e delle autorizzazioni per gli utenti di amministratore del database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a424a-155">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="a424a-156">Aprire Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a424a-156">Open Skype for Business Server Management Shell</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="a424a-157">Non procedere con la rimozione dei file di database precedenti finché la replica non è completa ed è stabile.</span><span class="sxs-lookup"><span data-stu-id="a424a-157">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="a424a-158">Se si rimuovono i file prima di completare la replica, si interromperà il processo di replica e si lascerà il server di gestione centralizzato appena spostato in uno stato sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="a424a-158">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="a424a-159">Usa il cmdlet **Get-CsManagementStoreReplicationStatus** per confermare lo stato di replica.</span><span class="sxs-lookup"><span data-stu-id="a424a-159">Use the cmdlet **Get-CsManagementStoreReplicationStatus** to confirm the replication status.</span></span> 
  
3. <span data-ttu-id="a424a-160">Per rimuovere i file di database di Central Management Store dal server di gestione centrale legacy install, digitare:</span><span class="sxs-lookup"><span data-stu-id="a424a-160">To remove the Central Management store database files from the legacy install Central Management Server, type:</span></span>
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    <span data-ttu-id="a424a-161">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a424a-161">For example:</span></span>
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    <span data-ttu-id="a424a-162">Dove il _ \<nome di dominio completo\> di SQL Server_ è l'installazione legacy back end server in una distribuzione di Enterprise Edition o il nome di dominio completo del server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a424a-162">Where the  _\<FQDN of SQL Server\>_ is either the legacy install Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span> 
    

