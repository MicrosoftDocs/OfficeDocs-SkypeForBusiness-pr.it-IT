---
title: 'Lync Server 2013: installazione del database mediante Lync Server Management Shell'
description: 'Lync Server 2013: installazione del database mediante Lync Server Management Shell.'
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
ms.openlocfilehash: 2d572984c94d280723b12c5343a92ddfaa12d4f0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558182"
---
# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a><span data-ttu-id="fc792-103">Installazione di database mediante Lync Server Management Shell in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc792-103">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc792-104">_**Ultimo argomento modificato:** 2016-06-16_</span><span class="sxs-lookup"><span data-stu-id="fc792-104">_**Topic Last Modified:** 2016-06-16_</span></span>

<span data-ttu-id="fc792-105">La separazione dei ruoli e delle responsabilità tra gli amministratori dei server e gli amministrazione di SQL Server può causare ritardi nell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="fc792-105">Separation of roles and responsibilities between server administrators and SQL Server administrators can result in delays in implementation.</span></span> <span data-ttu-id="fc792-106">Lync Server 2013 utilizza il controllo di accesso basato sui ruoli (RBAC) per attenuare tali difficoltà.</span><span class="sxs-lookup"><span data-stu-id="fc792-106">Lync Server 2013 uses role-based access control (RBAC) to mitigate these difficulties.</span></span> <span data-ttu-id="fc792-107">In alcuni casi, l'amministratore di SQL Server deve gestire l'installazione dei database nel server basato su SQL Server al di fuori del controllo dell'accesso basato sui ruoli.</span><span class="sxs-lookup"><span data-stu-id="fc792-107">In some instances, the SQL Server administrator must manage the installation of databases on the SQL Server-based server outside RBAC.</span></span> <span data-ttu-id="fc792-108">Lync Server 2013 Management Shell consente all'amministratore di SQL Server di eseguire i cmdlet di Windows PowerShell studiati per configurare i database con i dati e i file di registro corretti.</span><span class="sxs-lookup"><span data-stu-id="fc792-108">The Lync Server 2013 Management Shell provides a way for the SQL Server administrator to run Windows PowerShell cmdlets designed to configure the databases with the correct data and log files.</span></span> <span data-ttu-id="fc792-109">Per informazioni dettagliate, vedere [Deployment Permissions for SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fc792-109">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="fc792-110">La procedura seguente presuppone che siano installati almeno Lync Server 2013 OCSCore.msi, SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012 Management Objects, CLR Types for Microsoft SQL Server 2012 e Microsoft SQL Server 2012 ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="fc792-110">The following procedure assumes that at a minimum the Lync Server 2013 OCSCore.msi, SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012 Management Objects, CLR Types for Microsoft SQL Server 2012 and Microsoft SQL Server 2012 ADOMD.NET are installed.</span></span> <span data-ttu-id="fc792-111">OCSCore.msi si trova sul supporto di installazione nella directory \Setup\AMD64\Setup.</span><span class="sxs-lookup"><span data-stu-id="fc792-111">The OCSCore.msi is located on the installation media in the \Setup\AMD64\Setup directory.</span></span> <span data-ttu-id="fc792-112">I componenti restanti si trovano in \Setup\amd64.</span><span class="sxs-lookup"><span data-stu-id="fc792-112">The remaining components are located in \Setup\amd64.</span></span> <span data-ttu-id="fc792-113">Inoltre, la preparazione di Active Directory per Lync Server 2013 è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="fc792-113">Additionally, Active Directory preparation for Lync Server 2013 has been successfully completed.</span></span>



</div>

<span data-ttu-id="fc792-114">**Install-CsDatabase** è il cmdlet di Windows PowerShell utilizzato per installare i database.</span><span class="sxs-lookup"><span data-stu-id="fc792-114">**Install-CsDatabase** is the Windows PowerShell cmdlet you use to install the databases.</span></span> <span data-ttu-id="fc792-115">Il cmdlet di **Install-CsDatabase** include un numero elevato di parametri, solo alcuni dei quali verranno descritti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="fc792-115">The **Install-CsDatabase** cmdlet has a large number of parameters, only a few of which are discussed here.</span></span> <span data-ttu-id="fc792-116">Per informazioni dettagliate sui possibili parametri, vedere la documentazione di Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="fc792-116">For details about the possible parameters, see the Lync Server 2013 Management Shell documentation.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="fc792-117">Per evitare le prestazioni e i possibili problemi di timeout, utilizzare sempre nomi di dominio completi (FQDN) quando si fa riferimento a server basati su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fc792-117">To avoid performance and possible time-out issues, always use fully qualified domain names (FQDNs) when referring to SQL Server-based servers.</span></span> <span data-ttu-id="fc792-118">Evitare di utilizzare riferimenti solo nome host.</span><span class="sxs-lookup"><span data-stu-id="fc792-118">Avoid using host name-only references.</span></span> <span data-ttu-id="fc792-119">Ad esempio, utilizzare sqlbe01.contoso.net, ma evitare di utilizzare SQLBE01.</span><span class="sxs-lookup"><span data-stu-id="fc792-119">For example, use sqlbe01.contoso.net, but avoid using SQLBE01.</span></span>



</div>

<span data-ttu-id="fc792-120">Per l'installazione dei database, **Install-CsDatabase** utilizza tre metodi principali per inserire i database nel server basato su SQL Server preparato:</span><span class="sxs-lookup"><span data-stu-id="fc792-120">For installing databases, **Install-CsDatabase** uses three primary methods for placing the databases onto the prepared SQL Server-based server:</span></span>

  - <span data-ttu-id="fc792-121">Eseguire **Install-CsDatabase** senza DatabasePaths o UseDefaultSqlPath.</span><span class="sxs-lookup"><span data-stu-id="fc792-121">Run **Install-CsDatabase** without DatabasePaths or UseDefaultSqlPath.</span></span> <span data-ttu-id="fc792-122">Il cmdlet utilizza un algoritmo predefinito per determinare la posizione migliore per i file di registro e di dati.</span><span class="sxs-lookup"><span data-stu-id="fc792-122">The cmdlet uses a built in algorithm to determine the best placement for the log and data files.</span></span> <span data-ttu-id="fc792-123">L'algoritmo può essere utilizzato solo per le implementazioni di SQL Server autonome.</span><span class="sxs-lookup"><span data-stu-id="fc792-123">The algorithm only works for stand-alone SQL Server implementations.</span></span>

  - <span data-ttu-id="fc792-124">Eseguire **Install-CsDatabase** con il parametro DatabasePaths.</span><span class="sxs-lookup"><span data-stu-id="fc792-124">Run **Install-CsDatabase** with the DatabasePaths parameter.</span></span> <span data-ttu-id="fc792-125">Se il parametro DatabasePaths è definito, viene utilizzato l'algoritmo predefinito per ottimizzare i percorsi dei file di registro e di dati.</span><span class="sxs-lookup"><span data-stu-id="fc792-125">The built-in algorithm to optimize log and data file locations is not used if the DatabasePaths parameter is defined.</span></span> <span data-ttu-id="fc792-126">Se si utilizza questo parametro, è possibile definire le posizioni in cui verranno distribuiti i file di log e di dati.</span><span class="sxs-lookup"><span data-stu-id="fc792-126">Using this parameter allows you to define the locations where log and data files will be deployed.</span></span>

  - <span data-ttu-id="fc792-127">Eseguire **Install-CsDatabase** con UseDefaultSqlPaths.</span><span class="sxs-lookup"><span data-stu-id="fc792-127">Run **Install-CsDatabase** with UseDefaultSqlPaths.</span></span> <span data-ttu-id="fc792-128">Questa opzione non utilizza l'algoritmo predefinito per ottimizzare le posizioni dei file di registro e di dati.</span><span class="sxs-lookup"><span data-stu-id="fc792-128">This option does not use the built-in algorithm to optimize the log and data file locations.</span></span> <span data-ttu-id="fc792-129">Tali file vengono distribuiti in base ai valori predefiniti impostati dall'amministratore di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fc792-129">Log and data file are deployed according to the defaults set by the SQL Server administrator.</span></span> <span data-ttu-id="fc792-130">Questi percorsi vengono in genere impostati per l'amministrazione automatica dei file di dati e di registro in SQL Server in anticipo e non sono associati al programma di installazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fc792-130">These paths are typically set for the purpose of automatic administration of log and data files on the SQL Server in advance, and are not associated with the setup of Lync Server 2013.</span></span>

  - <span data-ttu-id="fc792-131">È inoltre possibile utilizzare il parametro DatabasePathMap per specificare in modo esplicito un percorso per ogni database e il rispettivo file di registro.</span><span class="sxs-lookup"><span data-stu-id="fc792-131">The DatabasePathMap parameter can also be used to explicitly specify a location for each database and its respective log file.</span></span>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a><span data-ttu-id="fc792-132">Per utilizzare i cmdlet di Windows PowerShell per configurare l'archivio di gestione centrale di SQL Server</span><span class="sxs-lookup"><span data-stu-id="fc792-132">To use Windows PowerShell cmdlets to configure the SQL Server Central Management store</span></span>

1.  <span data-ttu-id="fc792-133">Su un computer qualsiasi accedere con le credenziali amministrative per la creazione dei database sul server basato su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fc792-133">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="fc792-134">Per informazioni dettagliate, vedere [Deployment Permissions for SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fc792-134">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

2.  <span data-ttu-id="fc792-135">Aprire Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="fc792-135">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="fc792-136">Se non sono stati regolati i criteri di esecuzione per Windows PowerShell, è necessario modificare il criterio per consentire l'esecuzione degli script di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fc792-136">If you have not adjusted the execution policy for Windows PowerShell, you must adjust the policy to allow Windows PowerShell scripts to run.</span></span> <span data-ttu-id="fc792-137">Per informazioni dettagliate, vedere "esame del criterio di esecuzione" all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093) .</span><span class="sxs-lookup"><span data-stu-id="fc792-137">For details, see “Examining the Execution Policy” at [https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093).</span></span>

3.  <span data-ttu-id="fc792-138">Utilizzare il cmdlet **Install-CsDatabase** per installare l'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="fc792-138">Use the **Install-CsDatabase** cmdlet to install the Central Management store.</span></span>
    
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
    > <span data-ttu-id="fc792-139">Il parametro Report è facoltativo ma è utile per documentare il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="fc792-139">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

4.  <span data-ttu-id="fc792-140">**Install-CsDatabase – DatabasePaths** è in grado di utilizzare un massimo di sei parametri di percorso, ognuno dei quali definisce i percorsi delle unità, come definito in SQL Server Data and log file Placement.</span><span class="sxs-lookup"><span data-stu-id="fc792-140">**Install-CsDatabase –DatabasePaths** can use up to six path parameters, each defining the paths for the drives as defined in SQL Server Data and Log File Placement.</span></span> <span data-ttu-id="fc792-141">In base alle regole logiche della configurazione del database in Lync Server 2013, le unità vengono analizzate in bucket di due, quattro o sei.</span><span class="sxs-lookup"><span data-stu-id="fc792-141">By the logical rules of the database configuration in Lync Server 2013, drives are parsed out into buckets of two, four, or six.</span></span> <span data-ttu-id="fc792-142">A seconda della configurazione di SQL Server e del numero di bucket, verranno forniti due percorsi, quattro percorsi o sei percorsi.</span><span class="sxs-lookup"><span data-stu-id="fc792-142">Depending on your SQL Server configuration and the number of buckets, you will supply two paths, four paths, or six paths.</span></span>
    
    <span data-ttu-id="fc792-143">Se si dispone di tre unità, il registro ha la priorità e i file di dati vengono distribuiti successivamente.</span><span class="sxs-lookup"><span data-stu-id="fc792-143">If you have three drives, the log gets priority and the data files are distributed after.</span></span> <span data-ttu-id="fc792-144">Un esempio di un server basato su SQL Server configurato con sei unità:</span><span class="sxs-lookup"><span data-stu-id="fc792-144">An example for a SQL Server-based server configured with six drives:</span></span>
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  <span data-ttu-id="fc792-145">Al termine dell'installazione del database, è possibile chiudere Lync Server 2013 Management Shell oppure passare all'installazione dei database configurati di Lync Server 2013 definiti in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="fc792-145">When the database installation completes, you can close Lync Server 2013 Management Shell or proceed to the installation of the Lync Server 2013 configured databases defined in Topology Builder.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a><span data-ttu-id="fc792-146">Per utilizzare i cmdlet di Windows PowerShell per impostare i database configurati nella topologia di SQL Server</span><span class="sxs-lookup"><span data-stu-id="fc792-146">To use Windows PowerShell cmdlets to configure the SQL Server topology configured databases</span></span>

1.  <span data-ttu-id="fc792-147">Per installare i database configurati da generatore di topologie per Lync Server 2013, l'amministratore di Lync Server 2013 deve pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="fc792-147">To install the Topology Builder configured databases for Lync Server 2013, the Lync Server 2013 administrator must publish the topology.</span></span> <span data-ttu-id="fc792-148">Per ulteriori informazioni, vedere [pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-the-topology.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fc792-148">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="fc792-149">Su un computer qualsiasi collegarsi con le credenziali amministrative per la creazione dei database sul server basato su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fc792-149">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="fc792-150">Per ulteriori informazioni, vedere l'argomento [autorizzazioni di distribuzione per SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fc792-150">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="fc792-151">Per poter configurare i database basati su SQL Server, assicurarsi che l'account di amministratore di SQL Server utilizzato per eseguire la procedura descritta di seguito sia anche un membro del gruppo sysadmins (o equivalente) sul server che esegue SQL Server e che detenga il ruolo del server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="fc792-151">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="fc792-152">Questo è particolarmente importante per controllare eventuali pool di Lync Server 2013 aggiuntivi che richiedono l'installazione o la configurazione del database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fc792-152">This is especially important to check for any additional Lync Server 2013 pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="fc792-153">Ad esempio, se si sta distribuendo un secondo pool (pool02), ma il ruolo del server di gestione centrale è mantenuto da pool01.</span><span class="sxs-lookup"><span data-stu-id="fc792-153">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="fc792-154">Il gruppo sysadmin di SQL Server (o equivalente) deve disporre delle autorizzazioni per entrambi i database basati su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fc792-154">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="fc792-155">Aprire Lync Server 2013 Management Shell, se non è già aperto.</span><span class="sxs-lookup"><span data-stu-id="fc792-155">Open Lync Server 2013 Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="fc792-156">Utilizzare il cmdlet **Install-CsDatabase** per installare i database configurati per il generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="fc792-156">Use the **Install-CsDatabase** cmdlet to install the Topology Builder configured databases.</span></span>
    
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
    > <span data-ttu-id="fc792-157">Il parametro Report è facoltativo ma è utile per documentare il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="fc792-157">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

5.  <span data-ttu-id="fc792-158">Al termine dell'installazione del database, chiudere Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="fc792-158">When the database installation completes, close Lync Server 2013 Management Shell.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a><span data-ttu-id="fc792-159">Per utilizzare i cmdlet di Windows PowerShell per configurare la topologia di SQL Server tramite il parametro DatabasePathMap</span><span class="sxs-lookup"><span data-stu-id="fc792-159">To use Windows PowerShell cmdlets to configure the SQL Server topology using the DatabasePathMap parameter</span></span>

1.  <span data-ttu-id="fc792-160">Per installare i database per Lync Server 2013, è necessario che l'amministratore di Lync Server crei i percorsi e distribuisca i file dei database e i file di registro in base a un set di regole predefinito.</span><span class="sxs-lookup"><span data-stu-id="fc792-160">To install databases for Lync Server 2013, the Lync Server administrator must create the paths and deploy the databases files and log files according to a predefined set of rules.</span></span>

2.  <span data-ttu-id="fc792-161">Su un computer qualsiasi collegarsi con le credenziali amministrative per la creazione dei database sul server basato su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fc792-161">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="fc792-162">Per ulteriori informazioni, vedere l'argomento [autorizzazioni di distribuzione per SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fc792-162">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="fc792-163">Per poter configurare i database basati su SQL Server, assicurarsi che l'account di amministratore di SQL Server utilizzato per eseguire la procedura descritta di seguito sia anche un membro del gruppo sysadmins (o equivalente) sul server che esegue SQL Server e che detenga il ruolo del server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="fc792-163">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="fc792-164">Questo è particolarmente importante per controllare eventuali pool di Lync Server aggiuntivi che richiedono l'installazione o la configurazione del database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fc792-164">This is especially important to check for any additional Lync Server pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="fc792-165">Ad esempio, se si sta distribuendo un secondo pool (pool02), ma il ruolo del server di gestione centrale è mantenuto da pool01.</span><span class="sxs-lookup"><span data-stu-id="fc792-165">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="fc792-166">Il gruppo sysadmin di SQL Server (o equivalente) deve disporre delle autorizzazioni per entrambi i database basati su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fc792-166">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="fc792-167">Aprire Lync Server Management Shell, se non è già aperto.</span><span class="sxs-lookup"><span data-stu-id="fc792-167">Open Lync Server Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="fc792-168">Utilizzare il cmdlet **Install-CsDatabase** con il parametro DatabasePathMap e una tabella hash di PowerShell per installare i database configurati per il generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="fc792-168">Use the **Install-CsDatabase** cmdlet with the DatabasePathMap parameter and a PowerShell hash table to install the Topology Builder configured databases.</span></span>

5.  <span data-ttu-id="fc792-169">Nel codice di esempio, i percorsi definiti per i database possono essere determinati in modo granulare utilizzando il parametro – DatabasePathMap e una tabella hash definita come indicato di seguito (nell'esempio viene utilizzato "C: \\ CSData" per tutti i file di database (con estensione MDF) e "c: \\ CSLogFiles" per tutti i file di registro (con estensione ldf).</span><span class="sxs-lookup"><span data-stu-id="fc792-169">In the example code, the paths defined for the databases can be determined in a granular manner by using the –DatabasePathMap parameter and a defined hash table as follows (the example uses “C:\\CSData” for all database (.mdf) files, and “C:\\CSLogFiles” for all log (.ldf) files.</span></span> <span data-ttu-id="fc792-170">La cartella verrà creata secondo le esigenze di Install-CsDatabase):</span><span class="sxs-lookup"><span data-stu-id="fc792-170">Folder will be created as needed by Install-CsDatabase):</span></span>
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
6.  <span data-ttu-id="fc792-171">Poiché il database e i file di registro sono denominati in modo esplicito con la posizione sul server di database di destinazione, è possibile definire percorsi specifici per il database e il percorso del registro effettivi di ogni tipo di servizio.</span><span class="sxs-lookup"><span data-stu-id="fc792-171">Because the database and log files are explicitly named with their location on the destination database server, you can define specific locations for each service type’s actual database and log location.</span></span> <span data-ttu-id="fc792-172">Nell'esempio seguente vengono attivati i database per ogni tipo di servizio specifico su dischi separati e i file di registro associati su un altro.</span><span class="sxs-lookup"><span data-stu-id="fc792-172">The following example puts databases for each specific service type on separate disks, and associated log files on another.</span></span> <span data-ttu-id="fc792-173">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="fc792-173">For example:</span></span>
    
      - <span data-ttu-id="fc792-174">Tutti i database RTC su "D: \\ RTCDatabase"</span><span class="sxs-lookup"><span data-stu-id="fc792-174">All RTC databases to “D:\\RTCDatabase”</span></span>
    
      - <span data-ttu-id="fc792-175">Tutti i file di registro RTC su "E: \\ RTCLogs"</span><span class="sxs-lookup"><span data-stu-id="fc792-175">All RTC log files to “E:\\RTCLogs”</span></span>
    
      - <span data-ttu-id="fc792-176">Tutti i database dell'archivio applicazioni su "F: \\ CPSDatabases"</span><span class="sxs-lookup"><span data-stu-id="fc792-176">All application store databases to “F:\\CPSDatabases”</span></span>
    
      - <span data-ttu-id="fc792-177">Tutti i registri dell'archivio applicazioni in "G: \\ CPSLogs"</span><span class="sxs-lookup"><span data-stu-id="fc792-177">All application store logs to “G:\\CPSLogs”</span></span>
    
      - <span data-ttu-id="fc792-178">Tutti i database dell'archivio di Response Group su "H: \\ RGSDatabases"</span><span class="sxs-lookup"><span data-stu-id="fc792-178">All response group store databases to “H:\\RGSDatabases”</span></span>
    
      - <span data-ttu-id="fc792-179">Tutti i registri dell'archivio di Response Group su "I: \\ RGSLogs"</span><span class="sxs-lookup"><span data-stu-id="fc792-179">All response group store logs to “I:\\RGSLogs”</span></span>
    
      - <span data-ttu-id="fc792-180">Tutti i database dell'archivio delle rubriche su "J: \\ ABSDatabases"</span><span class="sxs-lookup"><span data-stu-id="fc792-180">All address book store databases to “J:\\ABSDatabases”</span></span>
    
      - <span data-ttu-id="fc792-181">Tutti i file di registro dell'archivio delle rubriche su "K: \\ ABSLogs"</span><span class="sxs-lookup"><span data-stu-id="fc792-181">All address book store log files to “K:\\ABSLogs”</span></span>
    
      - <span data-ttu-id="fc792-182">Tutti i database dell'archivio di archiviazione su "L: \\ ArchivingDatabases"</span><span class="sxs-lookup"><span data-stu-id="fc792-182">All archiving store databases to “L:\\ArchivingDatabases”</span></span>
    
      - <span data-ttu-id="fc792-183">Tutti i registri dell'archivio di archiviazione su "M: \\ ArchivingLogs"</span><span class="sxs-lookup"><span data-stu-id="fc792-183">All archiving store logs to “M:\\ArchivingLogs”</span></span>
    
      - <span data-ttu-id="fc792-184">Tutti i database dell'archivio di monitoraggio su "N: \\ MonitoringDatabases"</span><span class="sxs-lookup"><span data-stu-id="fc792-184">All monitoring store databases to “N:\\MonitoringDatabases”</span></span>
    
      - <span data-ttu-id="fc792-185">Tutti i file di registro dell'archivio di monitoraggio in "O: \\ MonitoringLogfiles"</span><span class="sxs-lookup"><span data-stu-id="fc792-185">All monitoring store log files to “O:\\MonitoringLogfiles”</span></span>
    
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
    
    <span data-ttu-id="fc792-186">Se si utilizza il parametro – DatabasePathMap, è possibile definire qualsiasi combinazione di mapping lettera di unità logica che fornisce la soluzione migliore per i requisiti di posizionamento e prestazioni di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fc792-186">Using the –DatabasePathMap parameter, you can define any logical drive letter mapping combination that provides the best solution for your SQL Server performance and placement requirements.</span></span>

<span data-ttu-id="fc792-187">Se si configurano i file di dati e i file di registro del database utilizzando il metodo **DatabasePathMap** , sarà necessario apportare una leggera modifica al processo normale quando si utilizza il generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="fc792-187">If you configure your database data files and log files by using the **DatabasePathMap** method, you will need to make a slight change to your normal process when using Topology Builder.</span></span> <span data-ttu-id="fc792-188">In genere, è necessario definire le scelte di topologia, pubblicare la topologia e scegliere di distribuire le selezioni di database.</span><span class="sxs-lookup"><span data-stu-id="fc792-188">Typically, you would define your topology choices, publish the topology, and choose to deploy the database selections.</span></span>

<span data-ttu-id="fc792-189">Se è stato utilizzato **DatabasePathMap** , è già stata eseguita la terza parte del processo di generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="fc792-189">If you have used **DatabasePathMap** you have already accomplished the third part of the Topology Builder process.</span></span> <span data-ttu-id="fc792-190">Nel caso di un server di database completamente configurato prima dell'esecuzione del generatore di topologie, è comunque necessario definire tutti i ruoli e le opzioni del server, ma deselezionare l'opzione per la creazione dei database.</span><span class="sxs-lookup"><span data-stu-id="fc792-190">In the case of having a completely configured database server in advance of running Topology Builder, you would still define all of your server roles and options, but deselect the option to create the databases.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

