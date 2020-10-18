---
title: 'Lync Server 2013: configurare il clustering di SQL Server'
description: 'Lync Server 2013: configurare il clustering di SQL Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server clustering
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56472032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f4b81b62d086de27659f564427ad6adde99ecac
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576752"
---
# <a name="configure-sql-server-clustering-for-lync-server-2013"></a><span data-ttu-id="40e95-103">Configurare il clustering di SQL Server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40e95-103">Configure SQL Server clustering for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40e95-104">_**Ultimo argomento modificato:** 2014-01-10_</span><span class="sxs-lookup"><span data-stu-id="40e95-104">_**Topic Last Modified:** 2014-01-10_</span></span>

<span data-ttu-id="40e95-105">Microsoft Lync Server 2013 supporta il clustering per SQL Server 2012 e SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="40e95-105">Microsoft Lync Server 2013 supports clustering for SQL Server 2012 and SQL Server 2008 R2.</span></span> <span data-ttu-id="40e95-106">Per informazioni dettagliate su ciò che è supportato, vedere [database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="40e95-106">For details about what is supported, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span>

<span data-ttu-id="40e95-107">È necessario impostare e configurare il cluster di SQL Server prima di installare e distribuire Enterprise Edition Front End Server e database back-end.</span><span class="sxs-lookup"><span data-stu-id="40e95-107">You should set up and configure the SQL Server cluster before you install and deploy the Enterprise Edition Front End Server and back-end database.</span></span> <span data-ttu-id="40e95-108">Per le procedure consigliate e le istruzioni di installazione per il clustering di failover in SQL Server 2012, vedere <https://technet.microsoft.com/library/hh231721.aspx> .</span><span class="sxs-lookup"><span data-stu-id="40e95-108">For best practices and setup instructions for failover clustering in SQL Server 2012, see <https://technet.microsoft.com/library/hh231721.aspx>.</span></span> <span data-ttu-id="40e95-109">Per il clustering di failover in SQL Server 2008, vedere <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx> .</span><span class="sxs-lookup"><span data-stu-id="40e95-109">For failover clustering in SQL Server 2008, see <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx>.</span></span>

<span data-ttu-id="40e95-110">Quando si installa SQL Server, è consigliabile installare SQL Server Management Studio per gestire i percorsi dei file di database e di registro.</span><span class="sxs-lookup"><span data-stu-id="40e95-110">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations.</span></span> <span data-ttu-id="40e95-111">SQL Server Management Studio viene installato come componente facoltativo quando si installa SQL Server.</span><span class="sxs-lookup"><span data-stu-id="40e95-111">SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="40e95-112">Per installare e distribuire i database nel server basato su SQL Server, è necessario essere membri del gruppo sysadmin di SQL Server per il server basato su SQL Server in cui si installano i file di database.</span><span class="sxs-lookup"><span data-stu-id="40e95-112">To install and deploy the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmin group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="40e95-113">Se non si è membri del gruppo sysadmin di SQL Server, sarà necessario richiedere di essere aggiunti a tale gruppo finché non verranno distribuiti i file di database.</span><span class="sxs-lookup"><span data-stu-id="40e95-113">If you are not a member of the SQL Server sysadmin group, you will need to request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="40e95-114">Se non è possibile diventare membri del gruppo sysadmin, fornire all'amministratore del database di SQL Server lo script per configurare e distribuire i database.</span><span class="sxs-lookup"><span data-stu-id="40e95-114">If you cannot be made a member of the sysadmin group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="40e95-115">Per informazioni dettagliate sui diritti utente e le autorizzazioni appropriati necessari per eseguire le procedure, vedere <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment Permissions for SQL Server in Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="40e95-115">For details about the proper user rights and permissions that you need to accomplish the procedures, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a><span data-ttu-id="40e95-116">Per configurare il clustering di SQL Server</span><span class="sxs-lookup"><span data-stu-id="40e95-116">To configure SQL Server clustering</span></span>

1.  <span data-ttu-id="40e95-117">Dopo aver completato l'installazione e la configurazione del clustering di SQL Server, è necessario definire l'archivio SQL Server in Generatore di topologie utilizzando il nome del cluster virtuale dell'istanza di SQL Server (come configurato nel programma di installazione per il clustering di SQL Server) e il nome dell'istanza del database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="40e95-117">After you have completed the installation and configuration of SQL Server clustering, you define the SQL Server store in Topology Builder by using the SQL Server instance virtual cluster name (as configured in the setup for SQL Server clustering) and the instance name of the SQL Server database.</span></span> <span data-ttu-id="40e95-118">A differenza di un server basato su SQL Server singolo, per un server basato su SQL Server in cluster verrà utilizzato il nome di dominio completo (FQDN) del nodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="40e95-118">Different from a single SQL Server-based server, you will use the virtual node fully qualified domain name (FQDN) for a clustered SQL Server-based server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="40e95-119">I singoli nodi del cluster di Windows Server non devono essere configurati per il generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="40e95-119">The individual Windows Server cluster nodes do not have to be configured for Topology Builder.</span></span> <span data-ttu-id="40e95-120">Verrà utilizzato solo il nome del cluster di SQL Server virtuale.</span><span class="sxs-lookup"><span data-stu-id="40e95-120">You will use only the virtual SQL Server cluster name.</span></span>

    
    </div>

2.  <span data-ttu-id="40e95-121">Se si utilizza il generatore di topologie per distribuire i database, è necessario essere membri del gruppo sysadmin di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="40e95-121">If you are using Topology Builder to deploy your databases, you must be a member of the SQL Server sysadmin group.</span></span> <span data-ttu-id="40e95-122">Se si è membri del gruppo sysadmin di SQL Server, ma non si dispone di privilegi nel dominio (ad esempio, un ruolo di amministratore di database di SQL Server), si dispone dei diritti necessari per creare i database, ma non per leggere le informazioni necessarie in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="40e95-122">If you are a member of the SQL Server sysadmin group, but you do not have privileges in the domain (for example, a SQL Server database administrator role), then you have the rights to create the databases but not to read necessary information in Lync Server.</span></span> <span data-ttu-id="40e95-123">Per informazioni dettagliate sui diritti utente e le autorizzazioni necessarie per la distribuzione di Lync Server, vedere [Deployment Permissions for SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="40e95-123">For details about the user rights and permissions necessary to deploying Lync Server, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

3.  <span data-ttu-id="40e95-p108">Verificare che le impostazioni predefinite delle cartelle dei database e dei file di registro siano mappate correttamente ai dischi condivisi nel cluster di SQL Server utilizzando SQL Server Management Studio. Questa è una procedura obbligatoria se i database verranno creati utilizzando Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="40e95-p108">Ensure that the database folder and log files folder defaults are mapped correctly to the shared disks in the SQL Server cluster by using SQL Server Management Studio. This is a required procedure if you will create databases by using Topology Builder.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="40e95-126">Se non è stato installato SQL Server Management Studio, è possibile installarlo eseguendo di nuovo l'installazione di SQL Server e quindi selezionando lo strumento di gestione come funzionalità aggiunta per la distribuzione di SQL Server esistente.</span><span class="sxs-lookup"><span data-stu-id="40e95-126">If you did not install SQL Server Management Studio, you can install it by rerunning the SQL Server installation, and then selecting the management tool as an added feature for the existing SQL Server deployment.</span></span>

    
    </div>

4.  <span data-ttu-id="40e95-127">Installare i database per il server basato su SQL Server utilizzando il generatore di topologie o i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="40e95-127">Install the databases for the SQL Server-based server by using either Topology Builder or Windows PowerShell cmdlets.</span></span> <span data-ttu-id="40e95-128">Per utilizzare Generatore di topologie, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="40e95-128">To use Topology Builder, use the following procedure.</span></span> <span data-ttu-id="40e95-129">Per utilizzare i cmdlet di Windows PowerShell, vedere [installazione di database mediante Lync Server Management Shell in Lync server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="40e95-129">To use Windows PowerShell cmdlets, see [Database installation using Lync Server Management Shell in Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a><span data-ttu-id="40e95-130">Per creare database tramite Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="40e95-130">To create databases using Topology Builder</span></span>

1.  <span data-ttu-id="40e95-131">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="40e95-131">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="40e95-132">La procedura seguente presuppone che sia stata definita e configurata la topologia in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="40e95-132">The following procedure assumes that you have defined and configured your topology in Topology Builder.</span></span> <span data-ttu-id="40e95-133">Per informazioni dettagliate sulla definizione della topologia, vedere<A href="lync-server-2013-defining-and-configuring-the-topology.md">define and Configuring the topologie in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="40e95-133">For details about defining your topology, see<A href="lync-server-2013-defining-and-configuring-the-topology.md">Defining and configuring the topology in Lync Server 2013</A>.</span></span> <span data-ttu-id="40e95-134">Per utilizzare Generatore di topologie per la pubblicazione della topologia e la configurazione del database, è necessario eseguire l'accesso in qualità di utente con appartenenze a gruppi e diritti appropriati.</span><span class="sxs-lookup"><span data-stu-id="40e95-134">To use Topology Builder to publish the topology and configure the database, you must log on as a user with the correct user rights and group memberships.</span></span> <span data-ttu-id="40e95-135">Per informazioni dettagliate sui diritti e le appartenenze ai gruppi richiesti, vedere <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment Permissions for SQL Server in Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="40e95-135">For details about the required rights and group memberships, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="40e95-136">In Generatore di topologie, durante la pubblicazione della topologia, nella pagina **Crea database** fare clic su **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="40e95-136">In Topology Builder, as you publish the topology, on the **Create databases** page, click **Advanced**.</span></span>

3.  <span data-ttu-id="40e95-p111">Nella pagina **Seleziona percorso file di database** sono disponibili due opzioni per determinare come verranno distribuiti i file di database nel cluster di SQL Server. Seleziona una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="40e95-p111">The **Select Database File Location** page has two options that determine how the database files will be deployed to the SQL Server cluster. Select one of the following:</span></span>
    
      - <span data-ttu-id="40e95-139">**Determina automaticamente il percorso del file di database.**</span><span class="sxs-lookup"><span data-stu-id="40e95-139">**Automatically determine the database file location.**</span></span> <span data-ttu-id="40e95-140">Verrà utilizzato un algoritmo per determinare i percorsi dei file di dati e di registro del database in base alla configurazione delle unità nel server basato su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="40e95-140">This selection uses an algorithm to determine the database log and data file locations based on the drive configuration on the SQL Server-based server.</span></span> <span data-ttu-id="40e95-141">I file verranno distribuiti in modo da tentare di fornire prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="40e95-141">The files will be distributed in such a way as to attempt to provide optimal performance.</span></span>
    
      - <span data-ttu-id="40e95-142">Utilizza i valori predefiniti dell'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="40e95-142">Use SQL Server instance defaults.</span></span> <span data-ttu-id="40e95-143">Selezionando questa opzione, i file di dati e di registro verranno installati in base alle impostazioni dell'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="40e95-143">Selecting this option will install the log and data files according to the SQL Server instance settings.</span></span> <span data-ttu-id="40e95-144">Dopo la distribuzione dei file di database in SQL Server, è possibile che l'amministratore di database di SQL Server desideri riposizionare i file in modo da ottimizzare le prestazioni in base a requisiti di configurazione di SQL Server specifici.</span><span class="sxs-lookup"><span data-stu-id="40e95-144">After deployment of the database files to the SQL Server, your SQL Server database administrator may want to relocate the files to optimize performance for your particular SQL Server configuration requirements.</span></span>

4.  <span data-ttu-id="40e95-145">Completare la pubblicazione della topologia e controllare che non si siano verificati errori durante l'operazione.</span><span class="sxs-lookup"><span data-stu-id="40e95-145">Complete the publishing of the topology and confirm that there were no errors during the operation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

