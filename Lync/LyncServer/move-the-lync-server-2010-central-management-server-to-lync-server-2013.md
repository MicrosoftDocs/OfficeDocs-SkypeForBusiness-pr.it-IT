---
title: Spostare il server di gestione centrale Lync Server 2010 in Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move the Lync Server 2010 Central Management Server to Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49733602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90af32fce28d87b211a0829c5c863c9277129c86
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209732"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a><span data-ttu-id="75348-102">Spostare il server di gestione centrale Lync Server 2010 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75348-102">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75348-103">_**Ultimo argomento modificato:** 2013-11-25_</span><span class="sxs-lookup"><span data-stu-id="75348-103">_**Topic Last Modified:** 2013-11-25_</span></span>

<span data-ttu-id="75348-104">Dopo aver eseguito la migrazione da Lync Server 2010 a Lync Server 2013, è necessario spostare il server di gestione centrale Lync Server 2010 in Lync Server 2013 front end server o pool, prima di poter rimuovere il server Lync Server 2010 legacy.</span><span class="sxs-lookup"><span data-stu-id="75348-104">After migrating from Lync Server 2010 to Lync Server 2013, you need to move the Lync Server 2010 Central Management Server to the Lync Server 2013 Front End Server or pool, before you can remove the legacy Lync Server 2010 server.</span></span>

<span data-ttu-id="75348-105">Il server di gestione centrale è un singolo sistema di replica master/multiple, in cui la copia di lettura/scrittura del database è conservata dal front end server che contiene il server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="75348-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="75348-106">Ogni computer della topologia, incluso il front end server che contiene il server di gestione centrale, dispone di una copia di sola lettura dei dati dell'archivio di gestione centrale nel database di SQL Server, denominata RTCLOCAL per impostazione predefinita, installata nel computer durante l'installazione e distribuzione.</span><span class="sxs-lookup"><span data-stu-id="75348-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="75348-107">Il database locale riceve gli aggiornamenti delle repliche tramite l'agente Replicator di replica di Lync Server eseguito come servizio in tutti i computer.</span><span class="sxs-lookup"><span data-stu-id="75348-107">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="75348-108">Il nome del database effettivo sul server di gestione centrale e la replica locale è XDS, costituito dai file XDS. mdf e XDS. ldf.</span><span class="sxs-lookup"><span data-stu-id="75348-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="75348-109">Il percorso del database master è fatto riferimento da un punto di controllo del servizio (SCP) in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="75348-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="75348-110">Tutti gli strumenti che utilizzano il server di gestione centrale per la gestione e la configurazione di Lync Server utilizzano l'SCP per individuare l'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="75348-110">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>

<span data-ttu-id="75348-111">Dopo aver correttamente spostato il server di gestione centrale, è necessario rimuovere i database del server di gestione centrale dal front end server originale.</span><span class="sxs-lookup"><span data-stu-id="75348-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="75348-112">Per informazioni sulla rimozione dei database del server di gestione centrale, vedere [rimuovere il database di SQL Server per un pool Front End](remove-the-sql-server-database-for-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="75348-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>

<span data-ttu-id="75348-113">Utilizzare il cmdlet **Move-csmanagementserver** di Windows PowerShell in Lync Server Management Shell per spostare il database dal database di SQL Server lync Server 2010 al database di SQL Server di lync Server 2013 e quindi aggiornare il punto SCP in modo che punti al percorso del server di gestione centrale di lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="75348-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Lync Server Management Shell to move the database from the Lync Server 2010 SQL Server database to the Lync Server 2013 SQL Server database, and then update the SCP to point to the Lync Server 2013 Central Management Server location.</span></span>

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a><span data-ttu-id="75348-114">Preparazione dei front end server di Lync Server 2013 prima dello spostamento del server di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="75348-114">Preparing Lync Server 2013 Front End Servers before moving the Central Management Server</span></span>

<span data-ttu-id="75348-115">Utilizzare le procedure descritte in questa sezione per preparare i server front end di Lync Server 2013 prima di spostare il server di gestione centrale Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="75348-115">Use the procedures in this section to prepare the Lync Server 2013 Front End Servers before you move the Lync Server 2010 Central Management Server.</span></span>

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="75348-116">Per preparare un pool Enterprise Edition front end</span><span class="sxs-lookup"><span data-stu-id="75348-116">To prepare an Enterprise Edition Front End pool</span></span>

1.  <span data-ttu-id="75348-117">Nel pool Lync Server 2013 Enterprise Edition front end in cui si desidera spostare il server di gestione centrale, eseguire l'accesso al computer in cui è installato Lync Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="75348-117">On the Lync Server 2013 Enterprise Edition Front End pool where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="75348-118">È inoltre necessario disporre di autorizzazioni e diritti utente del database di SQL Server per il database in cui si desidera installare l'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="75348-118">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span>

2.  <span data-ttu-id="75348-119">Aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="75348-119">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="75348-120">Per creare il nuovo archivio di gestione centrale nel database di SQL Server Lync Server 2013, in Lync Server Management Shell digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="75348-120">To create the new Central Management store in the Lync Server 2013 SQL Server database, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  <span data-ttu-id="75348-121">Verificare che lo stato del servizio **Lync Server Front-End** sia **Avviato**.</span><span class="sxs-lookup"><span data-stu-id="75348-121">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="75348-122">Per preparare un front end server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="75348-122">To prepare a Standard Edition Front End Server</span></span>

1.  <span data-ttu-id="75348-123">Nel server Lync Server 2013 Standard Edition front end in cui si desidera spostare il server di gestione centrale, eseguire l'accesso al computer in cui è installato Lync Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="75348-123">On the Lync Server 2013 Standard Edition Front End Server where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span>

2.  <span data-ttu-id="75348-124">Aprire la Distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="75348-124">Open the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="75348-125">Nella distribuzione guidata di Lync Server, fare clic su **prepara primo server Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="75348-125">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="75348-126">Nella pagina **esecuzione comandi** in corso, SQL Server Express è installato come server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="75348-126">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="75348-127">Vengono create le regole firewall necessarie.</span><span class="sxs-lookup"><span data-stu-id="75348-127">Necessary firewall rules are created.</span></span> <span data-ttu-id="75348-128">Al termine dell'installazione del database e dei prerequisiti software, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="75348-128">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="75348-129">L'installazione iniziale può richiedere tempo senza che vengano visualizzati aggiornamenti visibili nella schermata riepilogativa di output dei comandi.</span><span class="sxs-lookup"><span data-stu-id="75348-129">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="75348-130">Ciò è dovuto all'installazione di SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="75348-130">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="75348-131">Se si desidera monitorare l'installazione del database, usare Gestione attività.</span><span class="sxs-lookup"><span data-stu-id="75348-131">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

5.  <span data-ttu-id="75348-132">Per creare il nuovo archivio di gestione centrale in Lync Server 2013 Standard Edition Front End Server, in Lync Server Management Shell digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="75348-132">To create the new Central Management store on the Lync Server 2013 Standard Edition Front End Server, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  <span data-ttu-id="75348-133">Verificare che lo stato del servizio **Lync Server Front-End** sia **Avviato**.</span><span class="sxs-lookup"><span data-stu-id="75348-133">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a><span data-ttu-id="75348-134">Per spostare il server di gestione centrale Lync Server 2010 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75348-134">To move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

1.  <span data-ttu-id="75348-135">Sul server Lync Server 2013 che fungerà da server di gestione centrale: eseguire l'accesso al computer in cui è installato Lync Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="75348-135">On the Lync Server 2013 server that will be the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="75348-136">È anche necessario disporre dei diritti e delle autorizzazioni di amministratore del database SQL Server.</span><span class="sxs-lookup"><span data-stu-id="75348-136">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="75348-137">Aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="75348-137">Open Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="75348-138">In Lync Server Management Shell, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="75348-138">In the Lync Server Management Shell, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="75348-139">Se <CODE>Enable-CsTopology</CODE> l'operazione non è riuscita, risolvere il problema impedendo il completamento del comando prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="75348-139">If <CODE>Enable-CsTopology</CODE> is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="75348-140">Se <STRONG>Enable-CsTopology</STRONG> non ha esito positivo, lo spostamento avrà esito negativo e potrebbe lasciare la topologia in uno stato in cui non è presente un archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="75348-140">If <STRONG>Enable-CsTopology</STRONG> is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span>

    
    </div>

4.  <span data-ttu-id="75348-141">Nel server Lync Server 2013 front end o nel pool Front End, in Lync Server Management Shell, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="75348-141">On the Lync Server 2013 Front End Server or Front End pool, in the Lync Server Management Shell, type:</span></span>
    
        Move-CsManagementServer

5.  <span data-ttu-id="75348-142">Lync Server Management Shell consente di visualizzare i server, i file Store, gli archivi di database e i punti di connessione del servizio dello stato corrente e dello stato proposto.</span><span class="sxs-lookup"><span data-stu-id="75348-142">Lync Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="75348-143">Leggere attentamente le informazioni e verificare che l'origine e la destinazione siano corrette.</span><span class="sxs-lookup"><span data-stu-id="75348-143">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="75348-144">Digitare **S** per continuare o **N** per interrompere lo spostamento.</span><span class="sxs-lookup"><span data-stu-id="75348-144">Type **Y** to continue, or **N** to stop the move.</span></span>

6.  <span data-ttu-id="75348-145">Esaminare eventuali avvisi o errori generati dal comando **Move-CsManagementServer** e risolverli.</span><span class="sxs-lookup"><span data-stu-id="75348-145">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span>

7.  <span data-ttu-id="75348-146">Nel server Lync Server 2013 aprire la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="75348-146">On the Lync Server 2013 server, open the Lync Server Deployment Wizard.</span></span>

8.  <span data-ttu-id="75348-147">Nella distribuzione guidata di Lync Server, fare clic su **Installa o aggiorna il sistema Lync Server**, fare clic su **passaggio 2: installazione o rimozione componenti di Lync Server**, fare clic su **Avanti**, esaminare il riepilogo e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="75348-147">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

9.  <span data-ttu-id="75348-148">Nel server Lync Server 2010 aprire la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="75348-148">On the Lync Server 2010 server, open the Lync Server Deployment Wizard.</span></span>

10. <span data-ttu-id="75348-149">Nella distribuzione guidata di Lync Server, fare clic su **Installa o aggiorna il sistema Lync Server**, fare clic su **passaggio 2: installazione o rimozione componenti di Lync Server**, fare clic su **Avanti**, esaminare il riepilogo e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="75348-149">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

11. <span data-ttu-id="75348-150">Riavviare il server Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="75348-150">Reboot the Lync Server 2013 server.</span></span> <span data-ttu-id="75348-151">Questa operazione è necessaria a causa di una modifica dell'appartenenza a un gruppo al database del server di gestione centrale di Access.</span><span class="sxs-lookup"><span data-stu-id="75348-151">This is required because of a group membership change to access Central Management Server database.</span></span>

12. <span data-ttu-id="75348-152">Per verificare che la replica con il nuovo archivio di gestione centrale si verifichi, in Lync Server Management Shell digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="75348-152">To confirm that replication with the new Central Management store is occurring, in the Lync Server Management Shell, type:</span></span>
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="75348-153">Il processo di replica può richiedere tempo per aggiornare tutte le repliche correnti.</span><span class="sxs-lookup"><span data-stu-id="75348-153">The replication may take some time to update all current replicas.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a><span data-ttu-id="75348-154">Per rimuovere i file dell'archivio di gestione centrale di Lync Server 2010 dopo uno spostamento</span><span class="sxs-lookup"><span data-stu-id="75348-154">To remove Lync Server 2010 Central Management store files after a move</span></span>

1.  <span data-ttu-id="75348-155">Nel server Lync Server 2010: accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="75348-155">On the Lync Server 2010 server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="75348-156">È anche necessario disporre dei diritti e delle autorizzazioni di amministratore del database SQL Server.</span><span class="sxs-lookup"><span data-stu-id="75348-156">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="75348-157">Aprire Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="75348-157">Open Lync Server Management Shell</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="75348-158">Non procedere con la rimozione dei file di database precedenti prima del completamento e della stabilizzazione della replica.</span><span class="sxs-lookup"><span data-stu-id="75348-158">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="75348-159">Se si rimuovono i file prima del completamento della replica, si interrompe il processo di replica e si lascia il server di gestione centrale appena spostato in uno stato sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="75348-159">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="75348-160">Usare il cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> per verificare lo stato della replica.</span><span class="sxs-lookup"><span data-stu-id="75348-160">Use the cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> to confirm the replication status.</span></span>

    
    </div>

3.  <span data-ttu-id="75348-161">Per rimuovere i file di database dell'archivio di gestione centrale dal server di gestione centrale Lync Server 2010, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="75348-161">To remove the Central Management store database files from the Lync Server 2010 Central Management Server, type:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    <span data-ttu-id="75348-162">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="75348-162">For example:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    <span data-ttu-id="75348-163">Dove il \<nome di dominio completo\> di SQL Server è il server di back-end Lync Server 2010 in una distribuzione Enterprise Edition o il nome di dominio completo del server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="75348-163">Where the \<FQDN of SQL Server\> is either the Lync Server 2010 Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

