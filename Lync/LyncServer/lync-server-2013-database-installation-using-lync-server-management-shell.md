---
title: 'Lync Server 2013: Installazione di database mediante Lync Server Management Shell'
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
ms.openlocfilehash: 8c617d323eb00476b53677b670c8cc6db0b8d05c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a><span data-ttu-id="4dcfb-102">Installazione di database mediante Lync Server Management Shell in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4dcfb-102">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4dcfb-103">_**Argomento Ultima modifica:** 2016-06-16_</span><span class="sxs-lookup"><span data-stu-id="4dcfb-103">_**Topic Last Modified:** 2016-06-16_</span></span>

<span data-ttu-id="4dcfb-104">La separazione dei ruoli e delle responsabilità tra gli amministratori del server e gli amministratori di SQL Server può causare ritardi nell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-104">Separation of roles and responsibilities between server administrators and SQL Server administrators can result in delays in implementation.</span></span> <span data-ttu-id="4dcfb-105">Lync Server 2013 usa il controllo di accesso basato sui ruoli (RBAC) per attenuare queste difficoltà.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-105">Lync Server 2013 uses role-based access control (RBAC) to mitigate these difficulties.</span></span> <span data-ttu-id="4dcfb-106">In alcuni casi, l'amministratore di SQL Server deve gestire l'installazione di database nel server basato su SQL Server all'esterno di RBAC.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-106">In some instances, the SQL Server administrator must manage the installation of databases on the SQL Server-based server outside RBAC.</span></span> <span data-ttu-id="4dcfb-107">Lync Server 2013 Management Shell consente all'amministratore di SQL Server di eseguire i cmdlet di Windows PowerShell progettati per configurare i database con i dati e i file di log corretti.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-107">The Lync Server 2013 Management Shell provides a way for the SQL Server administrator to run Windows PowerShell cmdlets designed to configure the databases with the correct data and log files.</span></span> <span data-ttu-id="4dcfb-108">Per informazioni dettagliate, vedere [autorizzazioni di distribuzione per SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4dcfb-108">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="4dcfb-109">La procedura seguente presuppone che almeno gli oggetti di gestione di Lync Server 2013 OCSCore. msi, SQL Server Native Client (sqlncli. msi) Microsoft SQL Server 2012, i tipi CLR per Microsoft SQL Server 2012 e Microsoft SQL Server 2012 ADOMD.NET siano installati.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-109">The following procedure assumes that at a minimum the Lync Server 2013 OCSCore.msi, SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012 Management Objects, CLR Types for Microsoft SQL Server 2012 and Microsoft SQL Server 2012 ADOMD.NET are installed.</span></span> <span data-ttu-id="4dcfb-110">Il file OCSCore. msi si trova nel supporto di installazione nella directory \Setup\AMD64\Setup.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-110">The OCSCore.msi is located on the installation media in the \Setup\AMD64\Setup directory.</span></span> <span data-ttu-id="4dcfb-111">I componenti rimanenti si trovano in \Setup\amd64.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-111">The remaining components are located in \Setup\amd64.</span></span> <span data-ttu-id="4dcfb-112">Inoltre, la preparazione di Active Directory per Lync Server 2013 è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-112">Additionally, Active Directory preparation for Lync Server 2013 has been successfully completed.</span></span>



</div>

<span data-ttu-id="4dcfb-113">**Install-CsDatabase** è il cmdlet di Windows PowerShell usato per installare i database.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-113">**Install-CsDatabase** is the Windows PowerShell cmdlet you use to install the databases.</span></span> <span data-ttu-id="4dcfb-114">Il cmdlet **Install-CsDatabase** ha un numero elevato di parametri, solo alcuni dei quali sono discussi qui.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-114">The **Install-CsDatabase** cmdlet has a large number of parameters, only a few of which are discussed here.</span></span> <span data-ttu-id="4dcfb-115">Per informazioni dettagliate sui possibili parametri, vedere la documentazione di Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-115">For details about the possible parameters, see the Lync Server 2013 Management Shell documentation.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="4dcfb-116">Per evitare le prestazioni e i possibili problemi di timeout, USA sempre nomi di dominio completi (FQDN) quando si fa riferimento a server basati su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-116">To avoid performance and possible time-out issues, always use fully qualified domain names (FQDNs) when referring to SQL Server-based servers.</span></span> <span data-ttu-id="4dcfb-117">Evitare di usare i riferimenti solo al nome host.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-117">Avoid using host name-only references.</span></span> <span data-ttu-id="4dcfb-118">Ad esempio, USA sqlbe01.contoso.net, ma evita di usare SQLBE01.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-118">For example, use sqlbe01.contoso.net, but avoid using SQLBE01.</span></span>



</div>

<span data-ttu-id="4dcfb-119">Per l'installazione di database, **Install-CsDatabase** usa tre metodi principali per posizionare i database nel server basato su SQL Server preparato:</span><span class="sxs-lookup"><span data-stu-id="4dcfb-119">For installing databases, **Install-CsDatabase** uses three primary methods for placing the databases onto the prepared SQL Server-based server:</span></span>

  - <span data-ttu-id="4dcfb-120">Eseguire **Install-CsDatabase** senza DatabasePaths o UseDefaultSqlPath.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-120">Run **Install-CsDatabase** without DatabasePaths or UseDefaultSqlPath.</span></span> <span data-ttu-id="4dcfb-121">Il cmdlet usa un algoritmo incorporato per determinare la posizione ottimale per i file di log e di dati.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-121">The cmdlet uses a built in algorithm to determine the best placement for the log and data files.</span></span> <span data-ttu-id="4dcfb-122">L'algoritmo funziona solo per le implementazioni di SQL Server autonome.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-122">The algorithm only works for stand-alone SQL Server implementations.</span></span>

  - <span data-ttu-id="4dcfb-123">Eseguire **Install-CsDatabase** con il parametro DatabasePaths.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-123">Run **Install-CsDatabase** with the DatabasePaths parameter.</span></span> <span data-ttu-id="4dcfb-124">L'algoritmo predefinito per ottimizzare le posizioni di log e file di dati non viene usato se il parametro DatabasePaths è definito.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-124">The built-in algorithm to optimize log and data file locations is not used if the DatabasePaths parameter is defined.</span></span> <span data-ttu-id="4dcfb-125">L'uso di questo parametro consente di definire le posizioni in cui verranno distribuiti i file di log e di dati.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-125">Using this parameter allows you to define the locations where log and data files will be deployed.</span></span>

  - <span data-ttu-id="4dcfb-126">Eseguire **Install-CsDatabase** con UseDefaultSqlPaths.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-126">Run **Install-CsDatabase** with UseDefaultSqlPaths.</span></span> <span data-ttu-id="4dcfb-127">Questa opzione non usa l'algoritmo predefinito per ottimizzare il log e i percorsi dei file di dati.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-127">This option does not use the built-in algorithm to optimize the log and data file locations.</span></span> <span data-ttu-id="4dcfb-128">I file di log e di dati vengono distribuiti in base alle impostazioni predefinite impostate dall'amministratore di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-128">Log and data file are deployed according to the defaults set by the SQL Server administrator.</span></span> <span data-ttu-id="4dcfb-129">Questi percorsi sono in genere impostati per l'amministrazione automatica dei file di log e di dati in SQL Server in anticipo e non sono associati alla configurazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-129">These paths are typically set for the purpose of automatic administration of log and data files on the SQL Server in advance, and are not associated with the setup of Lync Server 2013.</span></span>

  - <span data-ttu-id="4dcfb-130">Il parametro DatabasePathMap può essere usato anche per specificare in modo esplicito una posizione per ogni database e il rispettivo file di log.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-130">The DatabasePathMap parameter can also be used to explicitly specify a location for each database and its respective log file.</span></span>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a><span data-ttu-id="4dcfb-131">Per usare i cmdlet di Windows PowerShell per configurare SQL Server Central Management store</span><span class="sxs-lookup"><span data-stu-id="4dcfb-131">To use Windows PowerShell cmdlets to configure the SQL Server Central Management store</span></span>

1.  <span data-ttu-id="4dcfb-132">In qualsiasi computer accedere con le credenziali amministrative per creare i database nel server basato su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-132">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="4dcfb-133">Per informazioni dettagliate, vedere [autorizzazioni di distribuzione per SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4dcfb-133">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

2.  <span data-ttu-id="4dcfb-134">Aprire Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-134">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="4dcfb-135">Se il criterio di esecuzione non è stato regolato per Windows PowerShell, è necessario modificare i criteri per consentire l'esecuzione degli script di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-135">If you have not adjusted the execution policy for Windows PowerShell, you must adjust the policy to allow Windows PowerShell scripts to run.</span></span> <span data-ttu-id="4dcfb-136">Per informazioni dettagliate, vedere "esaminare il criterio di [http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093)esecuzione".</span><span class="sxs-lookup"><span data-stu-id="4dcfb-136">For details, see “Examining the Execution Policy” at [http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093).</span></span>

3.  <span data-ttu-id="4dcfb-137">Usare il cmdlet **Install-CsDatabase** per installare Central Management store.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-137">Use the **Install-CsDatabase** cmdlet to install the Central Management store.</span></span>
    
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
    > <span data-ttu-id="4dcfb-138">Il parametro report è facoltativo, ma è utile se si sta documentando il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-138">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

4.  <span data-ttu-id="4dcfb-139">**Install-CsDatabase-DatabasePaths** può usare un massimo di sei parametri di percorso, ognuno dei quali definisce i percorsi per le unità come definito nei dati di SQL Server e nella posizione del file di log.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-139">**Install-CsDatabase –DatabasePaths** can use up to six path parameters, each defining the paths for the drives as defined in SQL Server Data and Log File Placement.</span></span> <span data-ttu-id="4dcfb-140">In base alle regole logiche della configurazione del database in Lync Server 2013, le unità vengono analizzate in bucket di due, quattro o sei.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-140">By the logical rules of the database configuration in Lync Server 2013, drives are parsed out into buckets of two, four, or six.</span></span> <span data-ttu-id="4dcfb-141">In base alla configurazione di SQL Server e al numero di contenitori, verranno forniti due percorsi, quattro percorsi o sei percorsi.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-141">Depending on your SQL Server configuration and the number of buckets, you will supply two paths, four paths, or six paths.</span></span>
    
    <span data-ttu-id="4dcfb-142">Se si hanno tre unità, il log diventa prioritario e i file di dati vengono distribuiti dopo.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-142">If you have three drives, the log gets priority and the data files are distributed after.</span></span> <span data-ttu-id="4dcfb-143">Esempio di server basato su SQL Server configurato con sei unità:</span><span class="sxs-lookup"><span data-stu-id="4dcfb-143">An example for a SQL Server-based server configured with six drives:</span></span>
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  <span data-ttu-id="4dcfb-144">Al termine dell'installazione del database, è possibile chiudere Lync Server 2013 Management Shell oppure procedere con l'installazione dei database configurati da Lync Server 2013 definiti in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-144">When the database installation completes, you can close Lync Server 2013 Management Shell or proceed to the installation of the Lync Server 2013 configured databases defined in Topology Builder.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a><span data-ttu-id="4dcfb-145">Per usare i cmdlet di Windows PowerShell per configurare i database di topologia di SQL Server configurati</span><span class="sxs-lookup"><span data-stu-id="4dcfb-145">To use Windows PowerShell cmdlets to configure the SQL Server topology configured databases</span></span>

1.  <span data-ttu-id="4dcfb-146">Per installare i database configurati da generatore di topologia per Lync Server 2013, l'amministratore di Lync Server 2013 deve pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-146">To install the Topology Builder configured databases for Lync Server 2013, the Lync Server 2013 administrator must publish the topology.</span></span> <span data-ttu-id="4dcfb-147">Per informazioni dettagliate, vedere [pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-the-topology.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-147">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="4dcfb-148">In qualsiasi computer accedere con le credenziali amministrative per creare i database nel server basato su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-148">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="4dcfb-149">Vedere l'argomento [autorizzazioni di distribuzione per SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4dcfb-149">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4dcfb-150">Per poter configurare i database basati su SQL Server, verificare che l'account di amministratore di SQL Server usato per eseguire la procedura descritta in questo articolo sia anche un membro del gruppo sysadmin (o equivalente) nel server che esegue SQL Server e che detiene la gestione centralizzata Ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-150">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="4dcfb-151">Questa operazione è particolarmente importante per verificare se sono presenti altri pool di Lync Server 2013 che richiedono l'installazione o la configurazione di database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-151">This is especially important to check for any additional Lync Server 2013 pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="4dcfb-152">Ad esempio, se si sta distribuendo un secondo pool (pool02), ma il ruolo del server di gestione centrale è mantenuto da pool01.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-152">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="4dcfb-153">Il gruppo sysadmin di SQL Server (o equivalente) deve disporre delle autorizzazioni per entrambi i database basati su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-153">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="4dcfb-154">Aprire Lync Server 2013 Management Shell, se non è già aperto.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-154">Open Lync Server 2013 Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="4dcfb-155">Usare il cmdlet **Install-CsDatabase** per installare i database configurati da generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-155">Use the **Install-CsDatabase** cmdlet to install the Topology Builder configured databases.</span></span>
    
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
    > <span data-ttu-id="4dcfb-156">Il parametro report è facoltativo, ma è utile se si sta documentando il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-156">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

5.  <span data-ttu-id="4dcfb-157">Al termine dell'installazione del database, chiudere Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-157">When the database installation completes, close Lync Server 2013 Management Shell.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a><span data-ttu-id="4dcfb-158">Per usare i cmdlet di Windows PowerShell per configurare la topologia di SQL Server tramite il parametro DatabasePathMap</span><span class="sxs-lookup"><span data-stu-id="4dcfb-158">To use Windows PowerShell cmdlets to configure the SQL Server topology using the DatabasePathMap parameter</span></span>

1.  <span data-ttu-id="4dcfb-159">Per installare database per Lync Server 2013, l'amministratore di Lync Server deve creare i percorsi e distribuire i file di database e i file di log in base a un set di regole predefinito.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-159">To install databases for Lync Server 2013, the Lync Server administrator must create the paths and deploy the databases files and log files according to a predefined set of rules.</span></span>

2.  <span data-ttu-id="4dcfb-160">In qualsiasi computer accedere con le credenziali amministrative per creare i database nel server basato su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-160">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="4dcfb-161">Vedere l'argomento [autorizzazioni di distribuzione per SQL Server in Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4dcfb-161">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4dcfb-162">Per poter configurare i database basati su SQL Server, verificare che l'account di amministratore di SQL Server usato per eseguire la procedura descritta in questo articolo sia anche un membro del gruppo sysadmin (o equivalente) nel server che esegue SQL Server e che detiene la gestione centralizzata Ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-162">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="4dcfb-163">Questa operazione è particolarmente importante per verificare la necessità di eventuali pool di Lync Server aggiuntivi che richiedono l'installazione o la configurazione di database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-163">This is especially important to check for any additional Lync Server pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="4dcfb-164">Ad esempio, se si sta distribuendo un secondo pool (pool02), ma il ruolo del server di gestione centrale è mantenuto da pool01.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-164">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="4dcfb-165">Il gruppo sysadmin di SQL Server (o equivalente) deve disporre delle autorizzazioni per entrambi i database basati su SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-165">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="4dcfb-166">Aprire Lync Server Management Shell, se non è già aperto.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-166">Open Lync Server Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="4dcfb-167">Usa il cmdlet **Install-CsDatabase** con il parametro DatabasePathMap e una tabella hash di PowerShell per installare i database configurati da generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-167">Use the **Install-CsDatabase** cmdlet with the DatabasePathMap parameter and a PowerShell hash table to install the Topology Builder configured databases.</span></span>

5.  <span data-ttu-id="4dcfb-168">Nel codice di esempio i percorsi definiti per i database possono essere determinati in modo granulare usando il parametro – DatabasePathMap e una tabella hash definita come indicato di seguito (nell'esempio viene usato "C\\: CSData" per tutti i file di database (MDF) e "c\\: CSLogFiles" per tutti i file di log (con estensione ldf).</span><span class="sxs-lookup"><span data-stu-id="4dcfb-168">In the example code, the paths defined for the databases can be determined in a granular manner by using the –DatabasePathMap parameter and a defined hash table as follows (the example uses “C:\\CSData” for all database (.mdf) files, and “C:\\CSLogFiles” for all log (.ldf) files.</span></span> <span data-ttu-id="4dcfb-169">La cartella verrà creata in base alle esigenze di Install-CsDatabase):</span><span class="sxs-lookup"><span data-stu-id="4dcfb-169">Folder will be created as needed by Install-CsDatabase):</span></span>
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
6.  <span data-ttu-id="4dcfb-170">Poiché il database e i file di log sono denominati in modo esplicito con la loro posizione nel server di database di destinazione, è possibile definire percorsi specifici per il database effettivo e la posizione del log del tipo di servizio.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-170">Because the database and log files are explicitly named with their location on the destination database server, you can define specific locations for each service type’s actual database and log location.</span></span> <span data-ttu-id="4dcfb-171">L'esempio seguente inserisce i database per ogni tipo di servizio specifico su dischi separati e i file di log associati in un altro.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-171">The following example puts databases for each specific service type on separate disks, and associated log files on another.</span></span> <span data-ttu-id="4dcfb-172">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4dcfb-172">For example:</span></span>
    
      - <span data-ttu-id="4dcfb-173">Tutti i database RTC in "D\\: RTCDatabase"</span><span class="sxs-lookup"><span data-stu-id="4dcfb-173">All RTC databases to “D:\\RTCDatabase”</span></span>
    
      - <span data-ttu-id="4dcfb-174">Tutti i file di log RTC in "\\E: RTCLogs"</span><span class="sxs-lookup"><span data-stu-id="4dcfb-174">All RTC log files to “E:\\RTCLogs”</span></span>
    
      - <span data-ttu-id="4dcfb-175">Tutti i database dell'archivio applicazioni in "\\F: CPSDatabases"</span><span class="sxs-lookup"><span data-stu-id="4dcfb-175">All application store databases to “F:\\CPSDatabases”</span></span>
    
      - <span data-ttu-id="4dcfb-176">Tutti i registri dell'archivio applicazioni in "\\G: CPSLogs"</span><span class="sxs-lookup"><span data-stu-id="4dcfb-176">All application store logs to “G:\\CPSLogs”</span></span>
    
      - <span data-ttu-id="4dcfb-177">Tutti i database degli archivi di Response Group in\\"H: RGSDatabases"</span><span class="sxs-lookup"><span data-stu-id="4dcfb-177">All response group store databases to “H:\\RGSDatabases”</span></span>
    
      - <span data-ttu-id="4dcfb-178">Tutti i registri degli archivi di Response Group su\\"I: RGSLogs"</span><span class="sxs-lookup"><span data-stu-id="4dcfb-178">All response group store logs to “I:\\RGSLogs”</span></span>
    
      - <span data-ttu-id="4dcfb-179">Tutti i database dell'archivio Rubrica per "J\\: ABSDatabases"</span><span class="sxs-lookup"><span data-stu-id="4dcfb-179">All address book store databases to “J:\\ABSDatabases”</span></span>
    
      - <span data-ttu-id="4dcfb-180">Tutti i file di log dell'archivio Rubrica in "\\K: ABSLogs"</span><span class="sxs-lookup"><span data-stu-id="4dcfb-180">All address book store log files to “K:\\ABSLogs”</span></span>
    
      - <span data-ttu-id="4dcfb-181">Tutti i database di archiviazione archiviati in "L\\: ArchivingDatabases"</span><span class="sxs-lookup"><span data-stu-id="4dcfb-181">All archiving store databases to “L:\\ArchivingDatabases”</span></span>
    
      - <span data-ttu-id="4dcfb-182">Tutti i registri degli archivi archiviati in "M\\: ArchivingLogs"</span><span class="sxs-lookup"><span data-stu-id="4dcfb-182">All archiving store logs to “M:\\ArchivingLogs”</span></span>
    
      - <span data-ttu-id="4dcfb-183">Tutti i database dell'archivio di monitoraggio in\\"N: MonitoringDatabases"</span><span class="sxs-lookup"><span data-stu-id="4dcfb-183">All monitoring store databases to “N:\\MonitoringDatabases”</span></span>
    
      - <span data-ttu-id="4dcfb-184">Tutti i file di log dell'archivio di monitoraggio\\in "O: MonitoringLogfiles"</span><span class="sxs-lookup"><span data-stu-id="4dcfb-184">All monitoring store log files to “O:\\MonitoringLogfiles”</span></span>
    
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
    
    <span data-ttu-id="4dcfb-185">Usando il parametro – DatabasePathMap, puoi definire qualsiasi combinazione logica di mapping delle lettere dell'unità che offre la soluzione migliore per i requisiti di prestazioni e posizionamento di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-185">Using the –DatabasePathMap parameter, you can define any logical drive letter mapping combination that provides the best solution for your SQL Server performance and placement requirements.</span></span>

<span data-ttu-id="4dcfb-186">Se si configurano i file di dati del database e i file di log usando il metodo **DatabasePathMap** , è necessario apportare una lieve modifica al processo normale quando si usa generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-186">If you configure your database data files and log files by using the **DatabasePathMap** method, you will need to make a slight change to your normal process when using Topology Builder.</span></span> <span data-ttu-id="4dcfb-187">In genere, è necessario definire le opzioni di topologia, pubblicare la topologia e scegliere di distribuire le selezioni del database.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-187">Typically, you would define your topology choices, publish the topology, and choose to deploy the database selections.</span></span>

<span data-ttu-id="4dcfb-188">Se è stato usato **DatabasePathMap** , è già stata eseguita la terza parte del processo di generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-188">If you have used **DatabasePathMap** you have already accomplished the third part of the Topology Builder process.</span></span> <span data-ttu-id="4dcfb-189">Nel caso di un server di database completamente configurato prima dell'uso di generatore di topologia, è comunque necessario definire tutti i ruoli e le opzioni del server, ma deselezionare l'opzione per la creazione dei database.</span><span class="sxs-lookup"><span data-stu-id="4dcfb-189">In the case of having a completely configured database server in advance of running Topology Builder, you would still define all of your server roles and options, but deselect the option to create the databases.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

