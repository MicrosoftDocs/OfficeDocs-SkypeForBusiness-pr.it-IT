---
title: 'Lync Server 2013: installazione del database mediante Lync Server Management Shell'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database installation using Lync Server Management Shell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48185401
ms.date: 06/16/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 443f353a43c2fdfd2f9fc8c7ce1a1b20c11a4a84
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a><span data-ttu-id="28931-102">Installazione di database mediante Lync Server Management Shell in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28931-102">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28931-103">_**Ultimo argomento modificato:** 2016-06-16_</span><span class="sxs-lookup"><span data-stu-id="28931-103">_**Topic Last Modified:** 2016-06-16_</span></span>

<span data-ttu-id="28931-104">La separazione dei ruoli e delle responsabilità tra gli amministratori dei server e gli amministrazione di SQL Server può causare ritardi nell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="28931-104">Separation of roles and responsibilities between server administrators and SQL Server administrators can result in delays in implementation.</span></span> <span data-ttu-id="28931-105">Lync Server 2013 utilizza il controllo di accesso basato sui ruoli (RBAC) per attenuare tali difficoltà.</span><span class="sxs-lookup"><span data-stu-id="28931-105">Lync Server 2013 uses role-based access control (RBAC) to mitigate these difficulties.</span></span> <span data-ttu-id="28931-106">In alcuni casi, l'amministratore di SQL Server deve gestire l'installazione dei database nel server basato su SQL Server al di fuori del controllo dell'accesso basato sui ruoli.</span><span class="sxs-lookup"><span data-stu-id="28931-106">In some instances, the SQL Server administrator must manage the installation of databases on the SQL Server-based server outside RBAC.</span></span> <span data-ttu-id="28931-107">Lync Server 2013 Management Shell consente all'amministratore di SQL Server di eseguire i cmdlet di Windows PowerShell studiati per configurare i database con i dati e i file di registro corretti.</span><span class="sxs-lookup"><span data-stu-id="28931-107">The Lync Server 2013 Management Shell provides a way for the SQL Server administrator to run Windows PowerShell cmdlets designed to configure the databases with the correct data and log files.</span></span> <span data-ttu-id="28931-108">Per informazioni dettagliate, vedere [Deployment Permissions for SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="28931-108">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="28931-109">La procedura seguente presuppone che sia installato almeno il Lync Server 2013 OCSCore. msi, SQL Server Native Client (sqlncli. msi) Microsoft SQL Server 2012 Management Objects, CLR Types for Microsoft SQL Server 2012 e Microsoft SQL Server 2012 ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="28931-109">The following procedure assumes that at a minimum the Lync Server 2013 OCSCore.msi, SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012 Management Objects, CLR Types for Microsoft SQL Server 2012 and Microsoft SQL Server 2012 ADOMD.NET are installed.</span></span> <span data-ttu-id="28931-110">OCSCore.msi si trova sul supporto di installazione nella directory \Setup\AMD64\Setup.</span><span class="sxs-lookup"><span data-stu-id="28931-110">The OCSCore.msi is located on the installation media in the \Setup\AMD64\Setup directory.</span></span> <span data-ttu-id="28931-111">I componenti restanti si trovano in \Setup\amd64.</span><span class="sxs-lookup"><span data-stu-id="28931-111">The remaining components are located in \Setup\amd64.</span></span> <span data-ttu-id="28931-112">Inoltre, la preparazione di Active Directory per Lync Server 2013 è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="28931-112">Additionally, Active Directory preparation for Lync Server 2013 has been successfully completed.</span></span>



</div>

<span data-ttu-id="28931-113">**Install-CsDatabase** è il cmdlet di Windows PowerShell utilizzato per installare i database.</span><span class="sxs-lookup"><span data-stu-id="28931-113">**Install-CsDatabase** is the Windows PowerShell cmdlet you use to install the databases.</span></span> <span data-ttu-id="28931-114">Il cmdlet di **Install-CsDatabase** include un numero elevato di parametri, solo alcuni dei quali verranno descritti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="28931-114">The **Install-CsDatabase** cmdlet has a large number of parameters, only a few of which are discussed here.</span></span> <span data-ttu-id="28931-115">Per informazioni dettagliate sui possibili parametri, vedere la documentazione di Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="28931-115">For details about the possible parameters, see the Lync Server 2013 Management Shell documentation.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="28931-116">Per evitare le prestazioni e i possibili problemi di timeout, utilizzare sempre nomi di dominio completi (FQDN) quando si fa riferimento a server basati su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="28931-116">To avoid performance and possible time-out issues, always use fully qualified domain names (FQDNs) when referring to SQL Server-based servers.</span></span> <span data-ttu-id="28931-117">Evitare di utilizzare riferimenti solo nome host.</span><span class="sxs-lookup"><span data-stu-id="28931-117">Avoid using host name-only references.</span></span> <span data-ttu-id="28931-118">Ad esempio, utilizzare sqlbe01.contoso.net, ma evitare di utilizzare SQLBE01.</span><span class="sxs-lookup"><span data-stu-id="28931-118">For example, use sqlbe01.contoso.net, but avoid using SQLBE01.</span></span>



</div>

<span data-ttu-id="28931-119">Per l'installazione dei database, **Install-CsDatabase** utilizza tre metodi principali per inserire i database nel server basato su SQL Server preparato:</span><span class="sxs-lookup"><span data-stu-id="28931-119">For installing databases, **Install-CsDatabase** uses three primary methods for placing the databases onto the prepared SQL Server-based server:</span></span>

  - <span data-ttu-id="28931-120">Eseguire **Install-CsDatabase** senza DatabasePaths o UseDefaultSqlPath.</span><span class="sxs-lookup"><span data-stu-id="28931-120">Run **Install-CsDatabase** without DatabasePaths or UseDefaultSqlPath.</span></span> <span data-ttu-id="28931-121">Il cmdlet utilizza un algoritmo predefinito per determinare la posizione migliore per i file di registro e di dati.</span><span class="sxs-lookup"><span data-stu-id="28931-121">The cmdlet uses a built in algorithm to determine the best placement for the log and data files.</span></span> <span data-ttu-id="28931-122">L'algoritmo può essere utilizzato solo per le implementazioni di SQL Server autonome.</span><span class="sxs-lookup"><span data-stu-id="28931-122">The algorithm only works for stand-alone SQL Server implementations.</span></span>

  - <span data-ttu-id="28931-123">Eseguire **Install-CsDatabase** con il parametro DatabasePaths.</span><span class="sxs-lookup"><span data-stu-id="28931-123">Run **Install-CsDatabase** with the DatabasePaths parameter.</span></span> <span data-ttu-id="28931-124">Se il parametro DatabasePaths è definito, viene utilizzato l'algoritmo predefinito per ottimizzare i percorsi dei file di registro e di dati.</span><span class="sxs-lookup"><span data-stu-id="28931-124">The built-in algorithm to optimize log and data file locations is not used if the DatabasePaths parameter is defined.</span></span> <span data-ttu-id="28931-125">Se si utilizza questo parametro, è possibile definire le posizioni in cui verranno distribuiti i file di log e di dati.</span><span class="sxs-lookup"><span data-stu-id="28931-125">Using this parameter allows you to define the locations where log and data files will be deployed.</span></span>

  - <span data-ttu-id="28931-126">Eseguire **Install-CsDatabase** con UseDefaultSqlPaths.</span><span class="sxs-lookup"><span data-stu-id="28931-126">Run **Install-CsDatabase** with UseDefaultSqlPaths.</span></span> <span data-ttu-id="28931-127">Questa opzione non utilizza l'algoritmo predefinito per ottimizzare le posizioni dei file di registro e di dati.</span><span class="sxs-lookup"><span data-stu-id="28931-127">This option does not use the built-in algorithm to optimize the log and data file locations.</span></span> <span data-ttu-id="28931-128">Tali file vengono distribuiti in base ai valori predefiniti impostati dall'amministratore di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="28931-128">Log and data file are deployed according to the defaults set by the SQL Server administrator.</span></span> <span data-ttu-id="28931-129">Questi percorsi vengono in genere impostati per l'amministrazione automatica dei file di dati e di registro in SQL Server in anticipo e non sono associati al programma di installazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="28931-129">These paths are typically set for the purpose of automatic administration of log and data files on the SQL Server in advance, and are not associated with the setup of Lync Server 2013.</span></span>

  - <span data-ttu-id="28931-130">È inoltre possibile utilizzare il parametro DatabasePathMap per specificare in modo esplicito un percorso per ogni database e il rispettivo file di registro.</span><span class="sxs-lookup"><span data-stu-id="28931-130">The DatabasePathMap parameter can also be used to explicitly specify a location for each database and its respective log file.</span></span>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a><span data-ttu-id="28931-131">Per utilizzare i cmdlet di Windows PowerShell per configurare l'archivio di gestione centrale di SQL Server</span><span class="sxs-lookup"><span data-stu-id="28931-131">To use Windows PowerShell cmdlets to configure the SQL Server Central Management store</span></span>

1.  <span data-ttu-id="28931-132">Su un computer qualsiasi accedere con le credenziali amministrative per la creazione dei database sul server basato su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="28931-132">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="28931-133">Per informazioni dettagliate, vedere [Deployment Permissions for SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="28931-133">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

2.  <span data-ttu-id="28931-134">Aprire Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="28931-134">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="28931-135">Se non sono stati regolati i criteri di esecuzione per Windows PowerShell, è necessario modificare il criterio per consentire l'esecuzione degli script di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28931-135">If you have not adjusted the execution policy for Windows PowerShell, you must adjust the policy to allow Windows PowerShell scripts to run.</span></span> <span data-ttu-id="28931-136">Per informazioni dettagliate, vedere "esame del criterio di esecuzione" [https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093)all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="28931-136">For details, see “Examining the Execution Policy” at [https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093).</span></span>

3.  <span data-ttu-id="28931-137">Utilizzare il cmdlet **Install-CsDatabase** per installare l'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="28931-137">Use the **Install-CsDatabase** cmdlet to install the Central Management store.</span></span>
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <fully qualified domain name of SQL Server> 
        -SqlInstanceName <named instance> -DatabasePaths <logfile path>,<database file path> 
        -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn sqlbe.contoso.net -SqlInstanceName rtc -DatabasePaths "C:\CSDB-Logs","C:\CSDB-CMS" -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="28931-138">Il parametro Report è facoltativo ma è utile per documentare il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="28931-138">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

4.  <span data-ttu-id="28931-139">**Install-CsDatabase – DatabasePaths** è in grado di utilizzare un massimo di sei parametri di percorso, ognuno dei quali definisce i percorsi delle unità, come definito in SQL Server Data and log file Placement.</span><span class="sxs-lookup"><span data-stu-id="28931-139">**Install-CsDatabase –DatabasePaths** can use up to six path parameters, each defining the paths for the drives as defined in SQL Server Data and Log File Placement.</span></span> <span data-ttu-id="28931-140">In base alle regole logiche della configurazione del database in Lync Server 2013, le unità vengono analizzate in bucket di due, quattro o sei.</span><span class="sxs-lookup"><span data-stu-id="28931-140">By the logical rules of the database configuration in Lync Server 2013, drives are parsed out into buckets of two, four, or six.</span></span> <span data-ttu-id="28931-141">A seconda della configurazione di SQL Server e del numero di bucket, verranno forniti due percorsi, quattro percorsi o sei percorsi.</span><span class="sxs-lookup"><span data-stu-id="28931-141">Depending on your SQL Server configuration and the number of buckets, you will supply two paths, four paths, or six paths.</span></span>
    
    <span data-ttu-id="28931-142">Se si dispone di tre unità, il registro ha la priorità e i file di dati vengono distribuiti successivamente.</span><span class="sxs-lookup"><span data-stu-id="28931-142">If you have three drives, the log gets priority and the data files are distributed after.</span></span> <span data-ttu-id="28931-143">Un esempio di un server basato su SQL Server configurato con sei unità:</span><span class="sxs-lookup"><span data-stu-id="28931-143">An example for a SQL Server-based server configured with six drives:</span></span>
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  <span data-ttu-id="28931-144">Al termine dell'installazione del database, è possibile chiudere Lync Server 2013 Management Shell oppure passare all'installazione dei database configurati di Lync Server 2013 definiti in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="28931-144">When the database installation completes, you can close Lync Server 2013 Management Shell or proceed to the installation of the Lync Server 2013 configured databases defined in Topology Builder.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a><span data-ttu-id="28931-145">Per utilizzare i cmdlet di Windows PowerShell per impostare i database configurati nella topologia di SQL Server</span><span class="sxs-lookup"><span data-stu-id="28931-145">To use Windows PowerShell cmdlets to configure the SQL Server topology configured databases</span></span>

1.  <span data-ttu-id="28931-146">Per installare i database configurati da generatore di topologie per Lync Server 2013, l'amministratore di Lync Server 2013 deve pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="28931-146">To install the Topology Builder configured databases for Lync Server 2013, the Lync Server 2013 administrator must publish the topology.</span></span> <span data-ttu-id="28931-147">Per ulteriori informazioni, vedere [pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-the-topology.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="28931-147">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="28931-148">Su un computer qualsiasi collegarsi con le credenziali amministrative per la creazione dei database sul server basato su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="28931-148">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="28931-149">Per ulteriori informazioni, vedere l'argomento [autorizzazioni di distribuzione per SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="28931-149">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="28931-150">Per poter configurare i database basati su SQL Server, assicurarsi che l'account di amministratore di SQL Server utilizzato per eseguire la procedura descritta di seguito sia anche un membro del gruppo sysadmins (o equivalente) sul server che esegue SQL Server e che detenga la gestione centralizzata. Ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="28931-150">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="28931-151">Questo è particolarmente importante per controllare eventuali pool di Lync Server 2013 aggiuntivi che richiedono l'installazione o la configurazione del database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="28931-151">This is especially important to check for any additional Lync Server 2013 pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="28931-152">Ad esempio, se si sta distribuendo un secondo pool (pool02), ma il ruolo del server di gestione centrale è mantenuto da pool01.</span><span class="sxs-lookup"><span data-stu-id="28931-152">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="28931-153">Il gruppo sysadmin di SQL Server (o equivalente) deve disporre delle autorizzazioni per entrambi i database basati su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="28931-153">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="28931-154">Aprire Lync Server 2013 Management Shell, se non è già aperto.</span><span class="sxs-lookup"><span data-stu-id="28931-154">Open Lync Server 2013 Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="28931-155">Utilizzare il cmdlet **Install-CsDatabase** per installare i database configurati per il generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="28931-155">Use the **Install-CsDatabase** cmdlet to install the Topology Builder configured databases.</span></span>
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <fully qualified domain name of SQL Server> 
         -DatabasePaths <logfile path>,<database file path> -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe.contoso.net 
        -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="28931-156">Il parametro Report è facoltativo ma è utile per documentare il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="28931-156">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

5.  <span data-ttu-id="28931-157">Al termine dell'installazione del database, chiudere Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="28931-157">When the database installation completes, close Lync Server 2013 Management Shell.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a><span data-ttu-id="28931-158">Per utilizzare i cmdlet di Windows PowerShell per configurare la topologia di SQL Server tramite il parametro DatabasePathMap</span><span class="sxs-lookup"><span data-stu-id="28931-158">To use Windows PowerShell cmdlets to configure the SQL Server topology using the DatabasePathMap parameter</span></span>

1.  <span data-ttu-id="28931-159">Per installare i database per Lync Server 2013, è necessario che l'amministratore di Lync Server crei i percorsi e distribuisca i file dei database e i file di registro in base a un set di regole predefinito.</span><span class="sxs-lookup"><span data-stu-id="28931-159">To install databases for Lync Server 2013, the Lync Server administrator must create the paths and deploy the databases files and log files according to a predefined set of rules.</span></span>

2.  <span data-ttu-id="28931-160">Su un computer qualsiasi collegarsi con le credenziali amministrative per la creazione dei database sul server basato su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="28931-160">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="28931-161">Per ulteriori informazioni, vedere l'argomento [autorizzazioni di distribuzione per SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="28931-161">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="28931-162">Per poter configurare i database basati su SQL Server, assicurarsi che l'account di amministratore di SQL Server utilizzato per eseguire la procedura descritta di seguito sia anche un membro del gruppo sysadmins (o equivalente) sul server che esegue SQL Server e che detenga la gestione centralizzata. Ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="28931-162">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="28931-163">Questo è particolarmente importante per controllare eventuali pool di Lync Server aggiuntivi che richiedono l'installazione o la configurazione del database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="28931-163">This is especially important to check for any additional Lync Server pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="28931-164">Ad esempio, se si sta distribuendo un secondo pool (pool02), ma il ruolo del server di gestione centrale è mantenuto da pool01.</span><span class="sxs-lookup"><span data-stu-id="28931-164">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="28931-165">Il gruppo sysadmin di SQL Server (o equivalente) deve disporre delle autorizzazioni per entrambi i database basati su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="28931-165">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="28931-166">Aprire Lync Server Management Shell, se non è già aperto.</span><span class="sxs-lookup"><span data-stu-id="28931-166">Open Lync Server Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="28931-167">Utilizzare il cmdlet **Install-CsDatabase** con il parametro DatabasePathMap e una tabella hash di PowerShell per installare i database configurati per il generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="28931-167">Use the **Install-CsDatabase** cmdlet with the DatabasePathMap parameter and a PowerShell hash table to install the Topology Builder configured databases.</span></span>

5.  <span data-ttu-id="28931-168">Nel codice di esempio, i percorsi definiti per i database possono essere determinati in modo granulare utilizzando il parametro – DatabasePathMap e una tabella hash definita come indicato di seguito (nell'esempio viene utilizzato "\\c: CSData" per tutti i file di database (con estensione MDF)\\e "c: CSLogFiles" per tutti i file di registro (con estensione ldf).</span><span class="sxs-lookup"><span data-stu-id="28931-168">In the example code, the paths defined for the databases can be determined in a granular manner by using the –DatabasePathMap parameter and a defined hash table as follows (the example uses “C:\\CSData” for all database (.mdf) files, and “C:\\CSLogFiles” for all log (.ldf) files.</span></span> <span data-ttu-id="28931-169">La cartella verrà creata secondo le esigenze di Install-CsDatabase):</span><span class="sxs-lookup"><span data-stu-id="28931-169">Folder will be created as needed by Install-CsDatabase):</span></span>
    ```powershell
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="C:\CsData";"BackendStore:BlobStore:LogPath"="C:\CsLogFiles"
    "BackendStore:RtcSharedDatabase:DbPath"="C:\CsData";"BackendStore:RtcSharedDatabase:LogPath"="C:\CsLogFiles"
    "ABSStore:AbsDatabase:DbPath"="C:\CsData";"ABSStore:AbsDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:RgsConfigDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsConfigDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:RgsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsDynDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:CpsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:CpsDynDatabase:LogPath"="C:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="C:\CsData";"ArchivingStore:ArchivingDatabase:LogPath"="C:\CsLogFiles"
    "MonitoringStore:MonitoringDatabase:DbPath"="C:\CsData";"MonitoringStore:MonitoringDatabase:LogPath"="C:\CsLogFiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="C:\CsData";"MonitoringStore:QoEMetricsDatabase:LogPath"="C:\CsLogFiles"
    }
    Install-CsDatabase -ConfigureDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
6.  <span data-ttu-id="28931-170">Poiché il database e i file di registro sono denominati in modo esplicito con la posizione sul server di database di destinazione, è possibile definire percorsi specifici per il database e il percorso del registro effettivi di ogni tipo di servizio.</span><span class="sxs-lookup"><span data-stu-id="28931-170">Because the database and log files are explicitly named with their location on the destination database server, you can define specific locations for each service type’s actual database and log location.</span></span> <span data-ttu-id="28931-171">Nell'esempio seguente vengono attivati i database per ogni tipo di servizio specifico su dischi separati e i file di registro associati su un altro.</span><span class="sxs-lookup"><span data-stu-id="28931-171">The following example puts databases for each specific service type on separate disks, and associated log files on another.</span></span> <span data-ttu-id="28931-172">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="28931-172">For example:</span></span>
    
      - <span data-ttu-id="28931-173">Tutti i database RTC su "D\\: RTCDatabase"</span><span class="sxs-lookup"><span data-stu-id="28931-173">All RTC databases to “D:\\RTCDatabase”</span></span>
    
      - <span data-ttu-id="28931-174">Tutti i file di registro RTC su "\\E: RTCLogs"</span><span class="sxs-lookup"><span data-stu-id="28931-174">All RTC log files to “E:\\RTCLogs”</span></span>
    
      - <span data-ttu-id="28931-175">Tutti i database dell'archivio applicazioni su "\\F: CPSDatabases"</span><span class="sxs-lookup"><span data-stu-id="28931-175">All application store databases to “F:\\CPSDatabases”</span></span>
    
      - <span data-ttu-id="28931-176">Tutti i registri dell'archivio applicazioni in "\\G: CPSLogs"</span><span class="sxs-lookup"><span data-stu-id="28931-176">All application store logs to “G:\\CPSLogs”</span></span>
    
      - <span data-ttu-id="28931-177">Tutti i database dell'archivio di Response Group su\\"H: RGSDatabases"</span><span class="sxs-lookup"><span data-stu-id="28931-177">All response group store databases to “H:\\RGSDatabases”</span></span>
    
      - <span data-ttu-id="28931-178">Tutti i registri dell'archivio di Response Group su\\"I: RGSLogs"</span><span class="sxs-lookup"><span data-stu-id="28931-178">All response group store logs to “I:\\RGSLogs”</span></span>
    
      - <span data-ttu-id="28931-179">Tutti i database dell'archivio delle rubriche su "\\J: ABSDatabases"</span><span class="sxs-lookup"><span data-stu-id="28931-179">All address book store databases to “J:\\ABSDatabases”</span></span>
    
      - <span data-ttu-id="28931-180">Tutti i file di registro dell'archivio delle rubriche su\\"K: ABSLogs"</span><span class="sxs-lookup"><span data-stu-id="28931-180">All address book store log files to “K:\\ABSLogs”</span></span>
    
      - <span data-ttu-id="28931-181">Tutti i database dell'archivio di archiviazione su "\\L: ArchivingDatabases"</span><span class="sxs-lookup"><span data-stu-id="28931-181">All archiving store databases to “L:\\ArchivingDatabases”</span></span>
    
      - <span data-ttu-id="28931-182">Tutti i registri dell'archivio di archiviazione su "\\M: ArchivingLogs"</span><span class="sxs-lookup"><span data-stu-id="28931-182">All archiving store logs to “M:\\ArchivingLogs”</span></span>
    
      - <span data-ttu-id="28931-183">Tutti i database dell'archivio di monitoraggio su\\"N: MonitoringDatabases"</span><span class="sxs-lookup"><span data-stu-id="28931-183">All monitoring store databases to “N:\\MonitoringDatabases”</span></span>
    
      - <span data-ttu-id="28931-184">Tutti i file di registro dell'archivio di monitoraggio\\in "O: MonitoringLogfiles"</span><span class="sxs-lookup"><span data-stu-id="28931-184">All monitoring store log files to “O:\\MonitoringLogfiles”</span></span>
    
    <!-- end list -->
    
    ```powershell    
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="D:\RTCDatabase";"BackendStore:BlobStore:LogPath"="E:\RTCLogs"
    "BackendStore:RtcSharedDatabase:DbPath"="D:\RTCDatabase";"BackendStore:RtcSharedDatabase:LogPath"="E:\RTCLogs"
    "ABSStore:AbsDatabase:DbPath"="J:\ABSDatabases";"ABSStore:AbsDatabase:LogPath"="K:\ABSLogs"
    "ApplicationStore:RgsConfigDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsConfigDatabase:LogPath"="G:\CPSLogs"
    "ApplicationStore:RgsDynDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsDynDatabase:LogPath"="I:\RGSLogs"
    "ApplicationStore:CpsDynDatabase:DbPath"="F:\CPSDatabases";"ApplicationStore:CpsDynDatabase:LogPath"="G:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="M:\ArchivingLogs";"ArchivingStore:ArchivingDatabase:LogPath"="N:\MonitoringDatabases"
    "MonitoringStore:MonitoringDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:MonitoringDatabase:LogPath"="O:\MonitoringLogfiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:QoEMetricsDatabase:LogPath"="O:\MonitoringLogfiles"
    }
    
    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
    
    <span data-ttu-id="28931-185">Se si utilizza il parametro – DatabasePathMap, è possibile definire qualsiasi combinazione di mapping lettera di unità logica che fornisce la soluzione migliore per i requisiti di posizionamento e prestazioni di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="28931-185">Using the –DatabasePathMap parameter, you can define any logical drive letter mapping combination that provides the best solution for your SQL Server performance and placement requirements.</span></span>

<span data-ttu-id="28931-186">Se si configurano i file di dati e i file di registro del database utilizzando il metodo **DatabasePathMap** , sarà necessario apportare una leggera modifica al processo normale quando si utilizza il generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="28931-186">If you configure your database data files and log files by using the **DatabasePathMap** method, you will need to make a slight change to your normal process when using Topology Builder.</span></span> <span data-ttu-id="28931-187">In genere, è necessario definire le scelte di topologia, pubblicare la topologia e scegliere di distribuire le selezioni di database.</span><span class="sxs-lookup"><span data-stu-id="28931-187">Typically, you would define your topology choices, publish the topology, and choose to deploy the database selections.</span></span>

<span data-ttu-id="28931-188">Se è stato utilizzato **DatabasePathMap** , è già stata eseguita la terza parte del processo di generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="28931-188">If you have used **DatabasePathMap** you have already accomplished the third part of the Topology Builder process.</span></span> <span data-ttu-id="28931-189">Nel caso di un server di database completamente configurato prima dell'esecuzione del generatore di topologie, è comunque necessario definire tutti i ruoli e le opzioni del server, ma deselezionare l'opzione per la creazione dei database.</span><span class="sxs-lookup"><span data-stu-id="28931-189">In the case of having a completely configured database server in advance of running Topology Builder, you would still define all of your server roles and options, but deselect the option to create the databases.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

