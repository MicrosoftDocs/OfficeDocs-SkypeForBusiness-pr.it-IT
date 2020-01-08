---
title: Trasferire il server di gestione centrale di Lync Server 2010 in Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move the Lync Server 2010 Central Management Server to Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49733602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abcb361beb82b98cd765b3797b63b22c280fdf70
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a><span data-ttu-id="c6f5c-102">Trasferire il server di gestione centrale di Lync Server 2010 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6f5c-102">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6f5c-103">_**Argomento Ultima modifica:** 2013-11-25_</span><span class="sxs-lookup"><span data-stu-id="c6f5c-103">_**Topic Last Modified:** 2013-11-25_</span></span>

<span data-ttu-id="c6f5c-104">Dopo aver eseguito la migrazione da Lync Server 2010 a Lync Server 2013, è necessario trasferire il server di gestione centralizzato di Lync Server 2010 in Lync Server 2013 front end server o pool, prima di poter rimuovere il server legacy di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-104">After migrating from Lync Server 2010 to Lync Server 2013, you need to move the Lync Server 2010 Central Management Server to the Lync Server 2013 Front End Server or pool, before you can remove the legacy Lync Server 2010 server.</span></span>

<span data-ttu-id="c6f5c-105">Il server di gestione centrale è un singolo sistema master/replica multipla, in cui la copia di lettura/scrittura del database è tenuta dal server front-end che contiene il server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="c6f5c-106">Ogni computer della topologia, incluso il front end server che contiene il server di gestione centrale, ha una copia di sola lettura dei dati di Central Management store nel database di SQL Server (denominata RTCLOCAL per impostazione predefinita) installati nel computer durante l'installazione e distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="c6f5c-107">Il database locale riceve gli aggiornamenti della replica tramite l'agente replicatore di Lync Server che viene eseguito come servizio in tutti i computer.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-107">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="c6f5c-108">Il nome del database effettivo nel server di gestione centrale e la replica locale è XDS, costituito dai file XDS. mdf e XDS. ldf.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="c6f5c-109">Il percorso del database master viene fatto riferimento da un punto di controllo del servizio (SCP) in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="c6f5c-110">Tutti gli strumenti che usano il server di gestione centralizzato per gestire e configurare Lync Server usano l'SCP per individuare l'Central Management store.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-110">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>

<span data-ttu-id="c6f5c-111">Dopo aver spostato correttamente il server di gestione centrale, è necessario rimuovere i database di Central Management Server dal server front-end originale.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="c6f5c-112">Per informazioni sulla rimozione dei database di Central Management Server, vedere [rimuovere il database di SQL Server per un pool Front-End](remove-the-sql-server-database-for-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="c6f5c-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>

<span data-ttu-id="c6f5c-113">Puoi usare il cmdlet **Move-csmanagementserver** di Windows PowerShell in Lync Server Management Shell per spostare il database dal database di SQL Server di lync Server 2010 al database di SQL Server di lync Server 2013 e quindi aggiornare il SCP in modo che punti al percorso del server di gestione centrale di lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Lync Server Management Shell to move the database from the Lync Server 2010 SQL Server database to the Lync Server 2013 SQL Server database, and then update the SCP to point to the Lync Server 2013 Central Management Server location.</span></span>

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a><span data-ttu-id="c6f5c-114">Preparazione dei server front-end di Lync Server 2013 prima di spostare il server di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="c6f5c-114">Preparing Lync Server 2013 Front End Servers before moving the Central Management Server</span></span>

<span data-ttu-id="c6f5c-115">Usare le procedure descritte in questa sezione per preparare i server front end di Lync Server 2013 prima di trasferire il server di gestione centralizzato di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-115">Use the procedures in this section to prepare the Lync Server 2013 Front End Servers before you move the Lync Server 2010 Central Management Server.</span></span>

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="c6f5c-116">Per preparare un pool di front-end Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="c6f5c-116">To prepare an Enterprise Edition Front End pool</span></span>

1.  <span data-ttu-id="c6f5c-117">Nel pool di front end di Lync Server 2013 Enterprise Edition in cui si vuole spostare il server di gestione centralizzato: accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="c6f5c-117">On the Lync Server 2013 Enterprise Edition Front End pool where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="c6f5c-118">Per il database in cui si vuole installare l'Central Management store, è necessario disporre anche dei diritti utente e delle autorizzazioni di amministratore del database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-118">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span>

2.  <span data-ttu-id="c6f5c-119">Aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-119">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="c6f5c-120">Per creare il nuovo archivio di gestione centrale nel database di SQL Server di Lync Server 2013, in Lync Server Management Shell digitare:</span><span class="sxs-lookup"><span data-stu-id="c6f5c-120">To create the new Central Management store in the Lync Server 2013 SQL Server database, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  <span data-ttu-id="c6f5c-121">Verificare che lo stato del servizio **front-end di Lync Server** sia stato **avviato**.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-121">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="c6f5c-122">Per preparare un server front-end Standard Edition</span><span class="sxs-lookup"><span data-stu-id="c6f5c-122">To prepare a Standard Edition Front End Server</span></span>

1.  <span data-ttu-id="c6f5c-123">Nel server front-end Standard Edition di Lync Server 2013 in cui si vuole spostare il server di gestione centralizzato: accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="c6f5c-123">On the Lync Server 2013 Standard Edition Front End Server where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span>

2.  <span data-ttu-id="c6f5c-124">Aprire la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-124">Open the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="c6f5c-125">Nella distribuzione guidata di Lync Server fare clic su **prepara primo server Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-125">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="c6f5c-126">Nella pagina **esecuzione dei comandi** , SQL Server Express viene installato come server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-126">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="c6f5c-127">Vengono create le regole firewall necessarie.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-127">Necessary firewall rules are created.</span></span> <span data-ttu-id="c6f5c-128">Dopo aver completato l'installazione del database e del software prerequisito, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-128">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c6f5c-129">L'installazione iniziale può richiedere del tempo senza aggiornamenti visibili alla schermata di riepilogo dell'output del comando.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-129">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="c6f5c-130">Ciò è dovuto all'installazione di SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-130">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="c6f5c-131">Se è necessario monitorare l'installazione del database, usare Gestione attività per monitorare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-131">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

5.  <span data-ttu-id="c6f5c-132">Per creare il nuovo archivio di gestione centrale nel server front-end Standard Edition di Lync Server 2013, in Lync Server Management Shell digitare:</span><span class="sxs-lookup"><span data-stu-id="c6f5c-132">To create the new Central Management store on the Lync Server 2013 Standard Edition Front End Server, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  <span data-ttu-id="c6f5c-133">Verificare che lo stato del servizio **front-end di Lync Server** sia stato **avviato**.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-133">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a><span data-ttu-id="c6f5c-134">Per trasferire il server di gestione centrale di Lync Server 2010 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6f5c-134">To move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

1.  <span data-ttu-id="c6f5c-135">Nel server Lync Server 2013 che sarà il server di gestione centralizzato: accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="c6f5c-135">On the Lync Server 2013 server that will be the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="c6f5c-136">È inoltre necessario disporre dei diritti e delle autorizzazioni per gli utenti di amministratore del database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-136">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="c6f5c-137">Aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-137">Open Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="c6f5c-138">In Lync Server Management Shell digitare:</span><span class="sxs-lookup"><span data-stu-id="c6f5c-138">In the Lync Server Management Shell, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="c6f5c-139">Se <CODE>Enable-CsTopology</CODE> l'operazione non riesce, risolvere il problema impedendo il completamento del comando prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-139">If <CODE>Enable-CsTopology</CODE> is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="c6f5c-140">Se <STRONG>Enable-CsTopology</STRONG> non riesce, il passaggio non riesce e può lasciare la topologia in uno stato in cui non è presente un Central Management store.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-140">If <STRONG>Enable-CsTopology</STRONG> is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span>

    
    </div>

4.  <span data-ttu-id="c6f5c-141">Nel server front-end o nel pool Front-End di Lync Server 2013, in Lync Server Management Shell, digitare:</span><span class="sxs-lookup"><span data-stu-id="c6f5c-141">On the Lync Server 2013 Front End Server or Front End pool, in the Lync Server Management Shell, type:</span></span>
    
        Move-CsManagementServer

5.  <span data-ttu-id="c6f5c-142">Lync Server Management Shell Visualizza i server, i file Store, gli archivi di database e i punti di connessione del servizio dello stato corrente e dello stato proposto.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-142">Lync Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="c6f5c-143">Leggere attentamente le informazioni e verificare che si tratta dell'origine e della destinazione desiderate.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-143">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="c6f5c-144">Digitare **Y** per continuare o **N** per interrompere lo stato di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-144">Type **Y** to continue, or **N** to stop the move.</span></span>

6.  <span data-ttu-id="c6f5c-145">Esaminare gli avvisi o gli errori generati dal comando **Move-csmanagementserver** e risolverli.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-145">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span>

7.  <span data-ttu-id="c6f5c-146">Nel server Lync Server 2013 aprire la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-146">On the Lync Server 2013 server, open the Lync Server Deployment Wizard.</span></span>

8.  <span data-ttu-id="c6f5c-147">Nella distribuzione guidata di Lync Server fare clic su **Installa o aggiorna Lync Server System**, fare clic su **passaggio 2: configurare o rimuovere i componenti di Lync Server**, fare clic su **Avanti**, rivedere il riepilogo e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-147">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

9.  <span data-ttu-id="c6f5c-148">Nel server Lync Server 2010 aprire la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-148">On the Lync Server 2010 server, open the Lync Server Deployment Wizard.</span></span>

10. <span data-ttu-id="c6f5c-149">Nella distribuzione guidata di Lync Server fare clic su **Installa o aggiorna Lync Server System**, fare clic su **passaggio 2: configurare o rimuovere i componenti di Lync Server**, fare clic su **Avanti**, rivedere il riepilogo e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-149">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

11. <span data-ttu-id="c6f5c-150">Riavviare il server Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-150">Reboot the Lync Server 2013 server.</span></span> <span data-ttu-id="c6f5c-151">Questa operazione è necessaria a causa di una modifica dell'appartenenza al gruppo per accedere al database di Central Management Server.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-151">This is required because of a group membership change to access Central Management Server database.</span></span>

12. <span data-ttu-id="c6f5c-152">Per verificare che la replica con il nuovo archivio di gestione centrale si verifichi, in Lync Server Management Shell digitare:</span><span class="sxs-lookup"><span data-stu-id="c6f5c-152">To confirm that replication with the new Central Management store is occurring, in the Lync Server Management Shell, type:</span></span>
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c6f5c-153">La replica può richiedere del tempo per aggiornare tutte le repliche correnti.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-153">The replication may take some time to update all current replicas.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a><span data-ttu-id="c6f5c-154">Per rimuovere i file di Lync Server 2010 Central Management store dopo una mossa</span><span class="sxs-lookup"><span data-stu-id="c6f5c-154">To remove Lync Server 2010 Central Management store files after a move</span></span>

1.  <span data-ttu-id="c6f5c-155">Nel server Lync Server 2010: accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="c6f5c-155">On the Lync Server 2010 server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="c6f5c-156">È inoltre necessario disporre dei diritti e delle autorizzazioni per gli utenti di amministratore del database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-156">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="c6f5c-157">Aprire Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="c6f5c-157">Open Lync Server Management Shell</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="c6f5c-158">Non procedere con la rimozione dei file di database precedenti finché la replica non è completa ed è stabile.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-158">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="c6f5c-159">Se si rimuovono i file prima di completare la replica, si interromperà il processo di replica e si lascerà il server di gestione centralizzato appena spostato in uno stato sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-159">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="c6f5c-160">Usa il cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> per confermare lo stato di replica.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-160">Use the cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> to confirm the replication status.</span></span>

    
    </div>

3.  <span data-ttu-id="c6f5c-161">Per rimuovere i file di database di Central Management Store dal server di gestione centrale di Lync Server 2010, digitare:</span><span class="sxs-lookup"><span data-stu-id="c6f5c-161">To remove the Central Management store database files from the Lync Server 2010 Central Management Server, type:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    <span data-ttu-id="c6f5c-162">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c6f5c-162">For example:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    <span data-ttu-id="c6f5c-163">Dove il \<nome di dominio completo\> di SQL Server è il server back-End di Lync Server 2010 in una distribuzione di Enterprise Edition o il nome di dominio completo del server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c6f5c-163">Where the \<FQDN of SQL Server\> is either the Lync Server 2010 Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

