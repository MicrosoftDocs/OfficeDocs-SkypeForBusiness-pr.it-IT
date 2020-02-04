---
title: 'Lync Server 2013: configurare il clustering di SQL Server'
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
ms.openlocfilehash: b63d338e630da93c90b573ac098d47e0929f0d84
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-clustering-for-lync-server-2013"></a><span data-ttu-id="e704b-102">Configurare il clustering di SQL Server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e704b-102">Configure SQL Server clustering for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e704b-103">_**Argomento Ultima modifica:** 2014-01-10_</span><span class="sxs-lookup"><span data-stu-id="e704b-103">_**Topic Last Modified:** 2014-01-10_</span></span>

<span data-ttu-id="e704b-104">Microsoft Lync Server 2013 supporta il clustering per SQL Server 2012 e SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="e704b-104">Microsoft Lync Server 2013 supports clustering for SQL Server 2012 and SQL Server 2008 R2.</span></span> <span data-ttu-id="e704b-105">Per informazioni dettagliate sulle funzionalità supportate, vedere [supporto software per database in Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="e704b-105">For details about what is supported, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span>

<span data-ttu-id="e704b-106">È consigliabile impostare e configurare il cluster di SQL Server prima di installare e distribuire il server front-end Enterprise Edition e il database back-end.</span><span class="sxs-lookup"><span data-stu-id="e704b-106">You should set up and configure the SQL Server cluster before you install and deploy the Enterprise Edition Front End Server and back-end database.</span></span> <span data-ttu-id="e704b-107">Per le procedure consigliate e le istruzioni di configurazione per il clustering di failover <http://technet.microsoft.com/en-us/library/hh231721.aspx>in SQL Server 2012, vedere.</span><span class="sxs-lookup"><span data-stu-id="e704b-107">For best practices and setup instructions for failover clustering in SQL Server 2012, see <http://technet.microsoft.com/en-us/library/hh231721.aspx>.</span></span> <span data-ttu-id="e704b-108">Per il clustering di failover in SQL Server 2008 <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>, vedere.</span><span class="sxs-lookup"><span data-stu-id="e704b-108">For failover clustering in SQL Server 2008, see <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>.</span></span>

<span data-ttu-id="e704b-109">Quando si installa SQL Server, è necessario installare SQL Server Management Studio per gestire le posizioni per i percorsi dei file di database e di log.</span><span class="sxs-lookup"><span data-stu-id="e704b-109">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations.</span></span> <span data-ttu-id="e704b-110">SQL Server Management Studio viene installato come componente facoltativo durante l'installazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e704b-110">SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e704b-111">Per installare e distribuire i database nel server basato su SQL Server, è necessario essere membri del gruppo sysadmin di SQL Server per il server basato su SQL Server in cui si installano i file di database.</span><span class="sxs-lookup"><span data-stu-id="e704b-111">To install and deploy the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmin group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="e704b-112">Se non si è un membro del gruppo sysadmin di SQL Server, è necessario richiedere che venga aggiunto al gruppo fino a quando non vengono distribuiti i file di database.</span><span class="sxs-lookup"><span data-stu-id="e704b-112">If you are not a member of the SQL Server sysadmin group, you will need to request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="e704b-113">Se non è possibile creare un membro del gruppo sysadmin, è necessario che l'amministratore di database di SQL Server disponga dello script per la configurazione e la distribuzione dei database.</span><span class="sxs-lookup"><span data-stu-id="e704b-113">If you cannot be made a member of the sysadmin group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="e704b-114">Per informazioni dettagliate sui diritti utente appropriati e sulle autorizzazioni necessarie per eseguire le procedure, vedere <A href="lync-server-2013-deployment-permissions-for-sql-server.md">autorizzazioni di distribuzione per SQL Server in Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e704b-114">For details about the proper user rights and permissions that you need to accomplish the procedures, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a><span data-ttu-id="e704b-115">Per configurare il clustering di SQL Server</span><span class="sxs-lookup"><span data-stu-id="e704b-115">To configure SQL Server clustering</span></span>

1.  <span data-ttu-id="e704b-116">Dopo aver completato l'installazione e la configurazione del clustering di SQL Server, è possibile definire l'archivio di SQL Server in Generatore di topologia usando il nome del cluster virtuale dell'istanza di SQL Server (configurato nel clustering per SQL Server) e l'istanza nome del database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e704b-116">After you have completed the installation and configuration of SQL Server clustering, you define the SQL Server store in Topology Builder by using the SQL Server instance virtual cluster name (as configured in the setup for SQL Server clustering) and the instance name of the SQL Server database.</span></span> <span data-ttu-id="e704b-117">Diverso da un singolo server basato su SQL Server, si utilizzerà il nome di dominio completo (FQDN) del nodo virtuale per un server basato su SQL Server in cluster.</span><span class="sxs-lookup"><span data-stu-id="e704b-117">Different from a single SQL Server-based server, you will use the virtual node fully qualified domain name (FQDN) for a clustered SQL Server-based server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e704b-118">I singoli nodi del cluster Windows Server non devono essere configurati per il generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="e704b-118">The individual Windows Server cluster nodes do not have to be configured for Topology Builder.</span></span> <span data-ttu-id="e704b-119">Si utilizzerà solo il nome del cluster di SQL Server virtuale.</span><span class="sxs-lookup"><span data-stu-id="e704b-119">You will use only the virtual SQL Server cluster name.</span></span>

    
    </div>

2.  <span data-ttu-id="e704b-120">Se si usa generatore di topologie per distribuire i database, è necessario essere membri del gruppo sysadmin di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e704b-120">If you are using Topology Builder to deploy your databases, you must be a member of the SQL Server sysadmin group.</span></span> <span data-ttu-id="e704b-121">Se si è un membro del gruppo sysadmin di SQL Server, ma non si hanno privilegi nel dominio, ad esempio un ruolo di amministratore di database di SQL Server, si hanno i diritti per creare i database, ma non per leggere le informazioni necessarie in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e704b-121">If you are a member of the SQL Server sysadmin group, but you do not have privileges in the domain (for example, a SQL Server database administrator role), then you have the rights to create the databases but not to read necessary information in Lync Server.</span></span> <span data-ttu-id="e704b-122">Per informazioni dettagliate sui diritti utente e le autorizzazioni necessarie per la distribuzione di Lync Server, vedere [autorizzazioni di distribuzione per SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e704b-122">For details about the user rights and permissions necessary to deploying Lync Server, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

3.  <span data-ttu-id="e704b-123">Verificare che la cartella di database e i file di log predefiniti vengano mappati correttamente ai dischi condivisi nel cluster di SQL Server tramite SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="e704b-123">Ensure that the database folder and log files folder defaults are mapped correctly to the shared disks in the SQL Server cluster by using SQL Server Management Studio.</span></span> <span data-ttu-id="e704b-124">Questa è una procedura obbligatoria se si vuole creare database usando generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="e704b-124">This is a required procedure if you will create databases by using Topology Builder.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e704b-125">Se SQL Server Management Studio non è stato installato, è possibile installarlo rieseguendo l'installazione di SQL Server e quindi selezionando lo strumento di gestione come funzionalità aggiunta per la distribuzione di SQL Server esistente.</span><span class="sxs-lookup"><span data-stu-id="e704b-125">If you did not install SQL Server Management Studio, you can install it by rerunning the SQL Server installation, and then selecting the management tool as an added feature for the existing SQL Server deployment.</span></span>

    
    </div>

4.  <span data-ttu-id="e704b-126">Installare i database per il server basato su SQL Server utilizzando il generatore di topologia o i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e704b-126">Install the databases for the SQL Server-based server by using either Topology Builder or Windows PowerShell cmdlets.</span></span> <span data-ttu-id="e704b-127">Per usare generatore di topologie, usare la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="e704b-127">To use Topology Builder, use the following procedure.</span></span> <span data-ttu-id="e704b-128">Per usare i cmdlet di Windows PowerShell, vedere [installazione di database tramite Lync Server Management Shell in Lync server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="e704b-128">To use Windows PowerShell cmdlets, see [Database installation using Lync Server Management Shell in Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a><span data-ttu-id="e704b-129">Per creare database tramite Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="e704b-129">To create databases using Topology Builder</span></span>

1.  <span data-ttu-id="e704b-130">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e704b-130">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="e704b-131">La procedura seguente presuppone che sia stata definita e configurata la topologia in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="e704b-131">The following procedure assumes that you have defined and configured your topology in Topology Builder.</span></span> <span data-ttu-id="e704b-132">Per informazioni dettagliate sulla definizione della topologia, vedere<A href="lync-server-2013-defining-and-configuring-the-topology.md">definizione e configurazione della topologia in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e704b-132">For details about defining your topology, see<A href="lync-server-2013-defining-and-configuring-the-topology.md">Defining and configuring the topology in Lync Server 2013</A>.</span></span> <span data-ttu-id="e704b-133">Per usare generatore di topologia per pubblicare la topologia e configurare il database, è necessario accedere come utente con i diritti utente corretti e le appartenenze ai gruppi.</span><span class="sxs-lookup"><span data-stu-id="e704b-133">To use Topology Builder to publish the topology and configure the database, you must log on as a user with the correct user rights and group memberships.</span></span> <span data-ttu-id="e704b-134">Per informazioni dettagliate sui diritti e le appartenenze ai gruppi necessari, vedere <A href="lync-server-2013-deployment-permissions-for-sql-server.md">autorizzazioni di distribuzione per SQL Server in Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e704b-134">For details about the required rights and group memberships, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="e704b-135">In Generatore di topologia, quando si pubblica la topologia, nella pagina **Crea database** fare clic su **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="e704b-135">In Topology Builder, as you publish the topology, on the **Create databases** page, click **Advanced**.</span></span>

3.  <span data-ttu-id="e704b-136">Nella pagina **Selezione percorso file di database** sono disponibili due opzioni che determinano il modo in cui verranno distribuiti i file di database nel cluster di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e704b-136">The **Select Database File Location** page has two options that determine how the database files will be deployed to the SQL Server cluster.</span></span> <span data-ttu-id="e704b-137">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e704b-137">Select one of the following:</span></span>
    
      - <span data-ttu-id="e704b-138">**Determinare automaticamente il percorso del file di database.**</span><span class="sxs-lookup"><span data-stu-id="e704b-138">**Automatically determine the database file location.**</span></span> <span data-ttu-id="e704b-139">Questa selezione usa un algoritmo per determinare il log del database e le posizioni dei file di dati in base alla configurazione dell'unità nel server basato su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e704b-139">This selection uses an algorithm to determine the database log and data file locations based on the drive configuration on the SQL Server-based server.</span></span> <span data-ttu-id="e704b-140">I file verranno distribuiti in modo da provare a ottenere prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="e704b-140">The files will be distributed in such a way as to attempt to provide optimal performance.</span></span>
    
      - <span data-ttu-id="e704b-141">Utilizza i valori predefiniti dell'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e704b-141">Use SQL Server instance defaults.</span></span> <span data-ttu-id="e704b-142">Selezionando questa opzione verranno installati i file di log e di dati in base alle impostazioni dell'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e704b-142">Selecting this option will install the log and data files according to the SQL Server instance settings.</span></span> <span data-ttu-id="e704b-143">Dopo la distribuzione dei file di database a SQL Server, l'amministratore di database di SQL Server potrebbe voler rilocare i file per ottimizzare le prestazioni per i particolari requisiti di configurazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e704b-143">After deployment of the database files to the SQL Server, your SQL Server database administrator may want to relocate the files to optimize performance for your particular SQL Server configuration requirements.</span></span>

4.  <span data-ttu-id="e704b-144">Completare la pubblicazione della topologia e verificare che non siano presenti errori durante l'operazione.</span><span class="sxs-lookup"><span data-stu-id="e704b-144">Complete the publishing of the topology and confirm that there were no errors during the operation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

