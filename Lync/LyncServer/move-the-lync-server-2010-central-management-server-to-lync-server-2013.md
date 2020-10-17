---
title: Spostare il server di gestione centrale Lync Server 2010 in Lync Server 2013
description: Spostare il server di gestione centrale Lync Server 2010 in Lync Server 2013.
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
ms.openlocfilehash: 19d53d797375b1eb8fde72f6b999e509b97f85ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571282"
---
# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a><span data-ttu-id="b6a49-103">Spostare il server di gestione centrale Lync Server 2010 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6a49-103">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6a49-104">_**Ultimo argomento modificato:** 2013-11-25_</span><span class="sxs-lookup"><span data-stu-id="b6a49-104">_**Topic Last Modified:** 2013-11-25_</span></span>

<span data-ttu-id="b6a49-105">Dopo aver eseguito la migrazione da Lync Server 2010 a Lync Server 2013, è necessario spostare il server di gestione centrale Lync Server 2010 in Lync Server 2013 front end server o pool, prima di poter rimuovere il server Lync Server 2010 legacy.</span><span class="sxs-lookup"><span data-stu-id="b6a49-105">After migrating from Lync Server 2010 to Lync Server 2013, you need to move the Lync Server 2010 Central Management Server to the Lync Server 2013 Front End Server or pool, before you can remove the legacy Lync Server 2010 server.</span></span>

<span data-ttu-id="b6a49-106">Il server di gestione centrale è un singolo sistema di replica master/multiple, in cui la copia di lettura/scrittura del database è conservata dal front end server che contiene il server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="b6a49-106">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="b6a49-107">Ogni computer della topologia, incluso il front end server che contiene il server di gestione centrale, dispone di una copia di sola lettura dei dati dell'archivio di gestione centrale nel database di SQL Server, denominata RTCLOCAL per impostazione predefinita, installata nel computer durante l'installazione e la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b6a49-107">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="b6a49-108">Il database locale riceve gli aggiornamenti delle repliche tramite l'agente Replicator di replica di Lync Server eseguito come servizio in tutti i computer.</span><span class="sxs-lookup"><span data-stu-id="b6a49-108">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="b6a49-109">Il nome del database effettivo sul server di gestione centrale e la replica locale è XDS, costituito dai file XDS. mdf e XDS. ldf.</span><span class="sxs-lookup"><span data-stu-id="b6a49-109">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="b6a49-110">Il percorso del database master è fatto riferimento da un punto di controllo del servizio (SCP) in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b6a49-110">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="b6a49-111">Tutti gli strumenti che utilizzano il server di gestione centrale per la gestione e la configurazione di Lync Server utilizzano l'SCP per individuare l'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="b6a49-111">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>

<span data-ttu-id="b6a49-112">Dopo aver correttamente spostato il server di gestione centrale, è necessario rimuovere i database del server di gestione centrale dal front end server originale.</span><span class="sxs-lookup"><span data-stu-id="b6a49-112">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="b6a49-113">Per informazioni sulla rimozione dei database del server di gestione centrale, vedere [rimuovere il database di SQL Server per un pool Front End](remove-the-sql-server-database-for-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="b6a49-113">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>

<span data-ttu-id="b6a49-114">Utilizzare il cmdlet **Move-csmanagementserver** di Windows PowerShell in Lync Server Management Shell per spostare il database dal database di SQL Server lync Server 2010 al database di SQL Server di lync Server 2013 e quindi aggiornare il punto SCP in modo che punti al percorso del server di gestione centrale di lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6a49-114">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Lync Server Management Shell to move the database from the Lync Server 2010 SQL Server database to the Lync Server 2013 SQL Server database, and then update the SCP to point to the Lync Server 2013 Central Management Server location.</span></span>

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a><span data-ttu-id="b6a49-115">Preparazione dei front end server di Lync Server 2013 prima dello spostamento del server di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="b6a49-115">Preparing Lync Server 2013 Front End Servers before moving the Central Management Server</span></span>

<span data-ttu-id="b6a49-116">Utilizzare le procedure descritte in questa sezione per preparare i server front end di Lync Server 2013 prima di spostare il server di gestione centrale Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="b6a49-116">Use the procedures in this section to prepare the Lync Server 2013 Front End Servers before you move the Lync Server 2010 Central Management Server.</span></span>

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="b6a49-117">Per preparare un pool Enterprise Edition front end</span><span class="sxs-lookup"><span data-stu-id="b6a49-117">To prepare an Enterprise Edition Front End pool</span></span>

1.  <span data-ttu-id="b6a49-118">Nel pool Lync Server 2013 Enterprise Edition front end in cui si desidera spostare il server di gestione centrale, eseguire l'accesso al computer in cui è installato Lync Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="b6a49-118">On the Lync Server 2013 Enterprise Edition Front End pool where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="b6a49-119">È inoltre necessario disporre di autorizzazioni e diritti utente del database di SQL Server per il database in cui si desidera installare l'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="b6a49-119">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span>

2.  <span data-ttu-id="b6a49-120">Aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b6a49-120">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="b6a49-121">Per creare il nuovo archivio di gestione centrale nel database di SQL Server Lync Server 2013, in Lync Server Management Shell digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b6a49-121">To create the new Central Management store in the Lync Server 2013 SQL Server database, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  <span data-ttu-id="b6a49-122">Verificare che lo stato del servizio **Lync Server Front-End** sia **Avviato**.</span><span class="sxs-lookup"><span data-stu-id="b6a49-122">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="b6a49-123">Per preparare un front end server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="b6a49-123">To prepare a Standard Edition Front End Server</span></span>

1.  <span data-ttu-id="b6a49-124">Nel server Lync Server 2013 Standard Edition front end in cui si desidera spostare il server di gestione centrale, eseguire l'accesso al computer in cui è installato Lync Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="b6a49-124">On the Lync Server 2013 Standard Edition Front End Server where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span>

2.  <span data-ttu-id="b6a49-125">Aprire la Distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b6a49-125">Open the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="b6a49-126">Nella distribuzione guidata di Lync Server, fare clic su **prepara primo server Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="b6a49-126">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="b6a49-127">Nella pagina **esecuzione comandi** in corso, SQL Server Express è installato come server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="b6a49-127">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="b6a49-128">Vengono create le regole firewall necessarie.</span><span class="sxs-lookup"><span data-stu-id="b6a49-128">Necessary firewall rules are created.</span></span> <span data-ttu-id="b6a49-129">Al termine dell'installazione del database e dei prerequisiti software, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="b6a49-129">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b6a49-130">L'installazione iniziale può richiedere tempo senza che vengano visualizzati aggiornamenti visibili nella schermata riepilogativa di output dei comandi.</span><span class="sxs-lookup"><span data-stu-id="b6a49-130">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="b6a49-131">Ciò è dovuto all'installazione di SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="b6a49-131">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="b6a49-132">Se si desidera monitorare l'installazione del database, usare Gestione attività.</span><span class="sxs-lookup"><span data-stu-id="b6a49-132">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

5.  <span data-ttu-id="b6a49-133">Per creare il nuovo archivio di gestione centrale in Lync Server 2013 Standard Edition Front End Server, in Lync Server Management Shell digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b6a49-133">To create the new Central Management store on the Lync Server 2013 Standard Edition Front End Server, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  <span data-ttu-id="b6a49-134">Verificare che lo stato del servizio **Lync Server Front-End** sia **Avviato**.</span><span class="sxs-lookup"><span data-stu-id="b6a49-134">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a><span data-ttu-id="b6a49-135">Per spostare il server di gestione centrale Lync Server 2010 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6a49-135">To move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

1.  <span data-ttu-id="b6a49-136">Sul server Lync Server 2013 che fungerà da server di gestione centrale: eseguire l'accesso al computer in cui è installato Lync Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="b6a49-136">On the Lync Server 2013 server that will be the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="b6a49-137">È anche necessario disporre dei diritti e delle autorizzazioni di amministratore del database SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b6a49-137">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="b6a49-138">Aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b6a49-138">Open Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="b6a49-139">In Lync Server Management Shell, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b6a49-139">In the Lync Server Management Shell, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="b6a49-140">Se <CODE>Enable-CsTopology</CODE> l'operazione non è riuscita, risolvere il problema impedendo il completamento del comando prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="b6a49-140">If <CODE>Enable-CsTopology</CODE> is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="b6a49-141">Se <STRONG>Enable-CsTopology</STRONG> non ha esito positivo, lo spostamento avrà esito negativo e potrebbe lasciare la topologia in uno stato in cui non è presente un archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="b6a49-141">If <STRONG>Enable-CsTopology</STRONG> is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span>

    
    </div>

4.  <span data-ttu-id="b6a49-142">Nel server Lync Server 2013 front end o nel pool Front End, in Lync Server Management Shell, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b6a49-142">On the Lync Server 2013 Front End Server or Front End pool, in the Lync Server Management Shell, type:</span></span>
    
        Move-CsManagementServer

5.  <span data-ttu-id="b6a49-143">Lync Server Management Shell consente di visualizzare i server, i file Store, gli archivi di database e i punti di connessione del servizio dello stato corrente e dello stato proposto.</span><span class="sxs-lookup"><span data-stu-id="b6a49-143">Lync Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="b6a49-144">Leggere attentamente le informazioni e verificare che l'origine e la destinazione siano corrette.</span><span class="sxs-lookup"><span data-stu-id="b6a49-144">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="b6a49-145">Digitare **S** per continuare o **N** per interrompere lo spostamento.</span><span class="sxs-lookup"><span data-stu-id="b6a49-145">Type **Y** to continue, or **N** to stop the move.</span></span>

6.  <span data-ttu-id="b6a49-146">Esaminare eventuali avvisi o errori generati dal comando **Move-CsManagementServer** e risolverli.</span><span class="sxs-lookup"><span data-stu-id="b6a49-146">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span>

7.  <span data-ttu-id="b6a49-147">Nel server Lync Server 2013 aprire la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b6a49-147">On the Lync Server 2013 server, open the Lync Server Deployment Wizard.</span></span>

8.  <span data-ttu-id="b6a49-148">Nella distribuzione guidata di Lync Server, fare clic su **Installa o aggiorna il sistema Lync Server**, fare clic su **passaggio 2: installazione o rimozione componenti di Lync Server**, fare clic su **Avanti**, esaminare il riepilogo e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="b6a49-148">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

9.  <span data-ttu-id="b6a49-149">Nel server Lync Server 2010 aprire la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b6a49-149">On the Lync Server 2010 server, open the Lync Server Deployment Wizard.</span></span>

10. <span data-ttu-id="b6a49-150">Nella distribuzione guidata di Lync Server, fare clic su **Installa o aggiorna il sistema Lync Server**, fare clic su **passaggio 2: installazione o rimozione componenti di Lync Server**, fare clic su **Avanti**, esaminare il riepilogo e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="b6a49-150">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

11. <span data-ttu-id="b6a49-151">Riavviare il server Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6a49-151">Reboot the Lync Server 2013 server.</span></span> <span data-ttu-id="b6a49-152">Questa operazione è necessaria a causa di una modifica dell'appartenenza a un gruppo al database del server di gestione centrale di Access.</span><span class="sxs-lookup"><span data-stu-id="b6a49-152">This is required because of a group membership change to access Central Management Server database.</span></span>

12. <span data-ttu-id="b6a49-153">Per verificare che la replica con il nuovo archivio di gestione centrale si verifichi, in Lync Server Management Shell digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b6a49-153">To confirm that replication with the new Central Management store is occurring, in the Lync Server Management Shell, type:</span></span>
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b6a49-154">Il processo di replica può richiedere tempo per aggiornare tutte le repliche correnti.</span><span class="sxs-lookup"><span data-stu-id="b6a49-154">The replication may take some time to update all current replicas.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a><span data-ttu-id="b6a49-155">Per rimuovere i file dell'archivio di gestione centrale di Lync Server 2010 dopo uno spostamento</span><span class="sxs-lookup"><span data-stu-id="b6a49-155">To remove Lync Server 2010 Central Management store files after a move</span></span>

1.  <span data-ttu-id="b6a49-156">Nel server Lync Server 2010: accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="b6a49-156">On the Lync Server 2010 server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="b6a49-157">È anche necessario disporre dei diritti e delle autorizzazioni di amministratore del database SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b6a49-157">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="b6a49-158">Aprire Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="b6a49-158">Open Lync Server Management Shell</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="b6a49-159">Non procedere con la rimozione dei file di database precedenti prima del completamento e della stabilizzazione della replica.</span><span class="sxs-lookup"><span data-stu-id="b6a49-159">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="b6a49-160">Se si rimuovono i file prima del completamento della replica, si interrompe il processo di replica e si lascia il server di gestione centrale appena spostato in uno stato sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b6a49-160">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="b6a49-161">Usare il cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> per verificare lo stato della replica.</span><span class="sxs-lookup"><span data-stu-id="b6a49-161">Use the cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> to confirm the replication status.</span></span>

    
    </div>

3.  <span data-ttu-id="b6a49-162">Per rimuovere i file di database dell'archivio di gestione centrale dal server di gestione centrale Lync Server 2010, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b6a49-162">To remove the Central Management store database files from the Lync Server 2010 Central Management Server, type:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    <span data-ttu-id="b6a49-163">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b6a49-163">For example:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    <span data-ttu-id="b6a49-164">Dove \<FQDN of SQL Server\> è il server back-end di Lync server 2010 in una distribuzione Enterprise Edition o il nome di dominio completo del server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="b6a49-164">Where the \<FQDN of SQL Server\> is either the Lync Server 2010 Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

