---
title: 'Lync Server 2013: esclusioni di analisi antivirus'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6f3e9afc3bd17f5cba4caa7619cb562be069942
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a><span data-ttu-id="6fb8b-102">Esclusioni di analisi antivirus per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fb8b-102">Antivirus scanning exclusions for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fb8b-103">_**Ultimo argomento modificato:** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="6fb8b-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="6fb8b-104">Per assicurarsi che lo scanner antivirus non interferisca con il funzionamento di Lync Server 2013, è necessario escludere processi e directory specifici per ogni server Lync Server 2013 o ruolo del server in cui si esegue uno scanner antivirus.</span><span class="sxs-lookup"><span data-stu-id="6fb8b-104">To ensure that the antivirus scanner does not interfere with the operation of Lync Server 2013, you must exclude specific processes and directories for each Lync Server 2013 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="6fb8b-105">È necessario escludere le directory e i processi seguenti:</span><span class="sxs-lookup"><span data-stu-id="6fb8b-105">The following processes and directories should be excluded:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6fb8b-106">Le posizioni dei file e delle cartelle elencate di seguito sono le posizioni predefinite per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6fb8b-106">Folder and file locations listed below are the default locations for Lync Server 2013.</span></span> <span data-ttu-id="6fb8b-107">Per tutti i percorsi per i quali non è stata utilizzata l'impostazione predefinita, escludere i percorsi specificati per l'organizzazione anziché i percorsi predefiniti specificati in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="6fb8b-107">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6fb8b-108">Tenere presente che alcuni programmi antivirus potrebbero richiedere percorsi assoluti, non relativi, per l'elenco di esclusione.</span><span class="sxs-lookup"><span data-stu-id="6fb8b-108">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>



</div>

  - <span data-ttu-id="6fb8b-109">Lync Server 2013 processi:</span><span class="sxs-lookup"><span data-stu-id="6fb8b-109">Lync Server 2013 processes:</span></span>
    
      - <span data-ttu-id="6fb8b-110">ABServer. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-110">ABServer.exe</span></span>
    
      - <span data-ttu-id="6fb8b-111">AcpMcuSvc. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-111">AcpMcuSvc.exe</span></span>
    
      - <span data-ttu-id="6fb8b-112">ASMCUSvc. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-112">ASMCUSvc.exe</span></span>
    
      - <span data-ttu-id="6fb8b-113">AVMCUSvc. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-113">AVMCUSvc.exe</span></span>
    
      - <span data-ttu-id="6fb8b-114">ChannelService. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-114">ChannelService.exe</span></span>
    
      - <span data-ttu-id="6fb8b-115">ClsAgent. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-115">ClsAgent.exe</span></span>
    
      - <span data-ttu-id="6fb8b-116">ComplianceService. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-116">ComplianceService.exe</span></span>
    
      - <span data-ttu-id="6fb8b-117">DataMCUSvc. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-117">DataMCUSvc.exe</span></span>
    
      - <span data-ttu-id="6fb8b-118">Dataproxy. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-118">DataProxy.exe</span></span>
    
      - <span data-ttu-id="6fb8b-119">FileTransferAgent. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-119">FileTransferAgent.exe</span></span>
    
      - <span data-ttu-id="6fb8b-120">IMMCUSvc. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-120">IMMCUSvc.exe</span></span>
    
      - <span data-ttu-id="6fb8b-121">LysSvc. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-121">LysSvc.exe</span></span>
    
      - <span data-ttu-id="6fb8b-122">MasterReplicatorAgent. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-122">MasterReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="6fb8b-123">MediaRelaySvc. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-123">MediaRelaySvc.exe</span></span>
    
      - <span data-ttu-id="6fb8b-124">MediationServerSvc. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-124">MediationServerSvc.exe</span></span>
    
      - <span data-ttu-id="6fb8b-125">MRASSvc. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-125">MRASSvc.exe</span></span>
    
      - <span data-ttu-id="6fb8b-126">OcsAppServerHost. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-126">OcsAppServerHost.exe</span></span>
    
      - <span data-ttu-id="6fb8b-127">ReplicaReplicatorAgent. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-127">ReplicaReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="6fb8b-128">ReplicationApp. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-128">ReplicationApp.exe</span></span>
    
      - <span data-ttu-id="6fb8b-129">RtcHost. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-129">RtcHost.exe</span></span>
    
      - <span data-ttu-id="6fb8b-130">RTCSrv. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-130">RTCSrv.exe</span></span>
    
      - <span data-ttu-id="6fb8b-131">XmppProxy. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-131">XmppProxy.exe</span></span>
    
      - <span data-ttu-id="6fb8b-132">XmppTGW. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-132">XmppTGW.exe</span></span>

  - <span data-ttu-id="6fb8b-133">Processi del servizio host Windows Fabric:</span><span class="sxs-lookup"><span data-stu-id="6fb8b-133">Windows Fabric Host Service processes:</span></span>
    
      - <span data-ttu-id="6fb8b-134">Fabric. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-134">Fabric.exe</span></span>
    
      - <span data-ttu-id="6fb8b-135">FabricDCA. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-135">FabricDCA.exe</span></span>
    
      - <span data-ttu-id="6fb8b-136">FabricHost. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-136">FabricHost.exe</span></span>

  - <span data-ttu-id="6fb8b-137">Processi IIS:</span><span class="sxs-lookup"><span data-stu-id="6fb8b-137">IIS processes:</span></span>
    
      - <span data-ttu-id="6fb8b-138">% SystemRoot%\\system32\\inetsrv\\w3wp. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-138">%systemroot%\\system32\\inetsrv\\w3wp.exe</span></span>
    
      - <span data-ttu-id="6fb8b-139">% SystemRoot%\\SysWow64\\inetsrv\\w3wp. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-139">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span></span>

  - <span data-ttu-id="6fb8b-140">Processi back-end di SQL Server:</span><span class="sxs-lookup"><span data-stu-id="6fb8b-140">SQL Server Back-End processes:</span></span>
    
      - <span data-ttu-id="6fb8b-141">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11. MSSQLSERVER\\MSSQL\\contenitori\\sqlservr. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-141">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="6fb8b-142">% ProgramFiles%\\Microsoft SQL Server\\MSRS11. MSSQLSERVER\\Reporting Services\\ReportServer\\bin\\ReportingServicesService. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-142">%ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span></span>
    
      - <span data-ttu-id="6fb8b-143">% ProgramFiles%\\Microsoft SQL Server\\MSAS11. MSMDSrv\\.\\exe\\(MSSQLSERVER OLAP bin)</span><span class="sxs-lookup"><span data-stu-id="6fb8b-143">%ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span></span>

  - <span data-ttu-id="6fb8b-144">Processi front-end di SQL Server:</span><span class="sxs-lookup"><span data-stu-id="6fb8b-144">SQL Server Front-End processes:</span></span>
    
      - <span data-ttu-id="6fb8b-145">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11. LYNCLOCAL\\MSSQL\\contenitori\\sqlservr. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-145">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="6fb8b-146">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11. RTCLOCAL\\MSSQL\\contenitori\\sqlservr. exe</span><span class="sxs-lookup"><span data-stu-id="6fb8b-146">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>

  - <span data-ttu-id="6fb8b-147">Directory e file:</span><span class="sxs-lookup"><span data-stu-id="6fb8b-147">Directories and files:</span></span>
    
      - <span data-ttu-id="6fb8b-148">file di log\\di\\% SystemRoot% system32</span><span class="sxs-lookup"><span data-stu-id="6fb8b-148">%systemroot%\\System32\\LogFiles</span></span>
    
      - <span data-ttu-id="6fb8b-149">file di registro\\%\\SystemRoot% SysWow64</span><span class="sxs-lookup"><span data-stu-id="6fb8b-149">%systemroot%\\SysWow64\\LogFiles</span></span>
    
      - <span data-ttu-id="6fb8b-150">% SystemRoot%\\Microsoft.NET\\assembly\\MSIL\_GAC</span><span class="sxs-lookup"><span data-stu-id="6fb8b-150">%systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span></span>
    
      - <span data-ttu-id="6fb8b-151">% ProgramFiles%\\Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fb8b-151">%programfiles%\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="6fb8b-152">% ProgramFiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher node</span><span class="sxs-lookup"><span data-stu-id="6fb8b-152">%programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node</span></span>
    
      - <span data-ttu-id="6fb8b-153">% ProgramFiles%\\file\\comuni Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fb8b-153">%programfiles%\\Common Files\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="6fb8b-154">% SystemDrive%\\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="6fb8b-154">%SystemDrive%\\RtcReplicaRoot</span></span>
    
      - <span data-ttu-id="6fb8b-155">Archivio condivisione file (specificato in Generatore di topologie).</span><span class="sxs-lookup"><span data-stu-id="6fb8b-155">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="6fb8b-156">Gli archivi file sono specificati in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="6fb8b-156">File stores are specified in Topology Builder.</span></span>
    
      - <span data-ttu-id="6fb8b-157">File di registro e dati di SQL Server, inclusi quelli per il database back-end, l'archivio utente, l'archivio di archiviazione, l'archivio di monitoraggio e l'archivio applicazioni.</span><span class="sxs-lookup"><span data-stu-id="6fb8b-157">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="6fb8b-158">I file di registro e di database possono essere specificati in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="6fb8b-158">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="6fb8b-159">Per informazioni dettagliate sui file di dati e di registro per ogni database, inclusi i nomi predefiniti, vedere [SQL Server Data and log file Placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6fb8b-159">For details about the data and log files for each database, including default names, see [SQL Server data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="6fb8b-160">File di dati e di registro di SQL Server, inclusi quelli per il database front-end, l'archivio Lync e l'archivio di RtcDatabase.</span><span class="sxs-lookup"><span data-stu-id="6fb8b-160">SQL Server data and log files, including those for the Front-end database, Lync store, and RtcDatabase store.</span></span> <span data-ttu-id="6fb8b-161">Sono in genere in% UnitàLocale%\\CSData.</span><span class="sxs-lookup"><span data-stu-id="6fb8b-161">They are normally under %localdrive%\\CSData.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

