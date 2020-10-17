---
title: 'Lync Server 2013: esclusioni di analisi antivirus'
description: 'Lync Server 2013: esclusioni di analisi antivirus.'
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
ms.openlocfilehash: 20c395f529cad91993d003efdeb231bd66f4b9bc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561912"
---
# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a><span data-ttu-id="4a5c9-103">Esclusioni di analisi antivirus per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a5c9-103">Antivirus scanning exclusions for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a5c9-104">_**Ultimo argomento modificato:** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="4a5c9-104">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="4a5c9-105">Per assicurarsi che lo scanner antivirus non interferisca con il funzionamento di Lync Server 2013, è necessario escludere processi e directory specifici per ogni server Lync Server 2013 o ruolo del server in cui si esegue uno scanner antivirus.</span><span class="sxs-lookup"><span data-stu-id="4a5c9-105">To ensure that the antivirus scanner does not interfere with the operation of Lync Server 2013, you must exclude specific processes and directories for each Lync Server 2013 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="4a5c9-106">È necessario escludere le directory e i processi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4a5c9-106">The following processes and directories should be excluded:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4a5c9-107">Le posizioni dei file e delle cartelle elencate di seguito sono le posizioni predefinite per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a5c9-107">Folder and file locations listed below are the default locations for Lync Server 2013.</span></span> <span data-ttu-id="4a5c9-108">Per tutti i percorsi per i quali non è stata utilizzata l'impostazione predefinita, escludere i percorsi specificati per l'organizzazione anziché i percorsi predefiniti specificati in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="4a5c9-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4a5c9-109">Tenere presente che alcuni programmi antivirus potrebbero richiedere percorsi assoluti, non relativi, per l'elenco di esclusione.</span><span class="sxs-lookup"><span data-stu-id="4a5c9-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>



</div>

  - <span data-ttu-id="4a5c9-110">Lync Server 2013 processi:</span><span class="sxs-lookup"><span data-stu-id="4a5c9-110">Lync Server 2013 processes:</span></span>
    
      - <span data-ttu-id="4a5c9-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-111">ABServer.exe</span></span>
    
      - <span data-ttu-id="4a5c9-112">AcpMcuSvc.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-112">AcpMcuSvc.exe</span></span>
    
      - <span data-ttu-id="4a5c9-113">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-113">ASMCUSvc.exe</span></span>
    
      - <span data-ttu-id="4a5c9-114">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-114">AVMCUSvc.exe</span></span>
    
      - <span data-ttu-id="4a5c9-115">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-115">ChannelService.exe</span></span>
    
      - <span data-ttu-id="4a5c9-116">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-116">ClsAgent.exe</span></span>
    
      - <span data-ttu-id="4a5c9-117">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-117">ComplianceService.exe</span></span>
    
      - <span data-ttu-id="4a5c9-118">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-118">DataMCUSvc.exe</span></span>
    
      - <span data-ttu-id="4a5c9-119">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-119">DataProxy.exe</span></span>
    
      - <span data-ttu-id="4a5c9-120">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-120">FileTransferAgent.exe</span></span>
    
      - <span data-ttu-id="4a5c9-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-121">IMMCUSvc.exe</span></span>
    
      - <span data-ttu-id="4a5c9-122">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-122">LysSvc.exe</span></span>
    
      - <span data-ttu-id="4a5c9-123">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-123">MasterReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="4a5c9-124">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-124">MediaRelaySvc.exe</span></span>
    
      - <span data-ttu-id="4a5c9-125">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-125">MediationServerSvc.exe</span></span>
    
      - <span data-ttu-id="4a5c9-126">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-126">MRASSvc.exe</span></span>
    
      - <span data-ttu-id="4a5c9-127">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-127">OcsAppServerHost.exe</span></span>
    
      - <span data-ttu-id="4a5c9-128">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-128">ReplicaReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="4a5c9-129">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-129">ReplicationApp.exe</span></span>
    
      - <span data-ttu-id="4a5c9-130">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-130">RtcHost.exe</span></span>
    
      - <span data-ttu-id="4a5c9-131">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-131">RTCSrv.exe</span></span>
    
      - <span data-ttu-id="4a5c9-132">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-132">XmppProxy.exe</span></span>
    
      - <span data-ttu-id="4a5c9-133">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-133">XmppTGW.exe</span></span>

  - <span data-ttu-id="4a5c9-134">Processi del servizio host Windows Fabric:</span><span class="sxs-lookup"><span data-stu-id="4a5c9-134">Windows Fabric Host Service processes:</span></span>
    
      - <span data-ttu-id="4a5c9-135">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-135">Fabric.exe</span></span>
    
      - <span data-ttu-id="4a5c9-136">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-136">FabricDCA.exe</span></span>
    
      - <span data-ttu-id="4a5c9-137">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-137">FabricHost.exe</span></span>

  - <span data-ttu-id="4a5c9-138">Processi IIS:</span><span class="sxs-lookup"><span data-stu-id="4a5c9-138">IIS processes:</span></span>
    
      - <span data-ttu-id="4a5c9-139">% SystemRoot% \\ system32 \\ inetsrv \\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-139">%systemroot%\\system32\\inetsrv\\w3wp.exe</span></span>
    
      - <span data-ttu-id="4a5c9-140">% SystemRoot% \\ SysWow64 \\ inetsrv \\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-140">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span></span>

  - <span data-ttu-id="4a5c9-141">Processi di Back-End di SQL Server:</span><span class="sxs-lookup"><span data-stu-id="4a5c9-141">SQL Server Back-End processes:</span></span>
    
      - <span data-ttu-id="4a5c9-142">% ProgramFiles% \\ Microsoft SQL Server \\ MSSQL11. MSSQLSERVER \\ MSSQL \\ contenitori \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="4a5c9-142">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="4a5c9-143">% ProgramFiles% \\ Microsoft SQL Server \\ MSRS11. \\ReportingServicesService.exe di servizi di Reporting Services \\ ReportServer \\ \\</span><span class="sxs-lookup"><span data-stu-id="4a5c9-143">%ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span></span>
    
      - <span data-ttu-id="4a5c9-144">% ProgramFiles% \\ Microsoft SQL Server \\ MSAS11. \\MSMDSrv.exe di \\ bin \\ OLAP di MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4a5c9-144">%ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span></span>

  - <span data-ttu-id="4a5c9-145">Processi di Front-End di SQL Server:</span><span class="sxs-lookup"><span data-stu-id="4a5c9-145">SQL Server Front-End processes:</span></span>
    
      - <span data-ttu-id="4a5c9-146">% ProgramFiles% \\ Microsoft SQL Server \\ MSSQL11.SQLServr.exe di LYNCLOCAL \\ MSSQL \\ contenitori \\</span><span class="sxs-lookup"><span data-stu-id="4a5c9-146">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="4a5c9-147">% ProgramFiles% \\ Microsoft SQL Server \\ MSSQL11.SQLServr.exe di RTCLOCAL \\ MSSQL \\ contenitori \\</span><span class="sxs-lookup"><span data-stu-id="4a5c9-147">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>

  - <span data-ttu-id="4a5c9-148">Directory e file:</span><span class="sxs-lookup"><span data-stu-id="4a5c9-148">Directories and files:</span></span>
    
      - <span data-ttu-id="4a5c9-149">file di log di% SystemRoot% \\ system32 \\</span><span class="sxs-lookup"><span data-stu-id="4a5c9-149">%systemroot%\\System32\\LogFiles</span></span>
    
      - <span data-ttu-id="4a5c9-150">file di registro% SystemRoot% \\ SysWow64 \\</span><span class="sxs-lookup"><span data-stu-id="4a5c9-150">%systemroot%\\SysWow64\\LogFiles</span></span>
    
      - <span data-ttu-id="4a5c9-151">% SystemRoot% \\ Microsoft.NET \\ assembly \\ \_ MSIL GAC</span><span class="sxs-lookup"><span data-stu-id="4a5c9-151">%systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span></span>
    
      - <span data-ttu-id="4a5c9-152">% ProgramFiles% \\ Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a5c9-152">%programfiles%\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="4a5c9-153">% ProgramFiles% \\ Common Files \\ Microsoft Lync Server 2013 \\ Watcher node</span><span class="sxs-lookup"><span data-stu-id="4a5c9-153">%programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node</span></span>
    
      - <span data-ttu-id="4a5c9-154">% ProgramFiles% \\ file comuni \\ Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a5c9-154">%programfiles%\\Common Files\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="4a5c9-155">% SystemDrive% \\ RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="4a5c9-155">%SystemDrive%\\RtcReplicaRoot</span></span>
    
      - <span data-ttu-id="4a5c9-156">Archivio condivisione file (specificato in Generatore di topologie).</span><span class="sxs-lookup"><span data-stu-id="4a5c9-156">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="4a5c9-157">Gli archivi file sono specificati in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="4a5c9-157">File stores are specified in Topology Builder.</span></span>
    
      - <span data-ttu-id="4a5c9-158">File di registro e dati di SQL Server, inclusi quelli per il database back-end, l'archivio utente, l'archivio di archiviazione, l'archivio di monitoraggio e l'archivio applicazioni.</span><span class="sxs-lookup"><span data-stu-id="4a5c9-158">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="4a5c9-159">I file di registro e di database possono essere specificati in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="4a5c9-159">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="4a5c9-160">Per informazioni dettagliate sui file di dati e di registro per ogni database, inclusi i nomi predefiniti, vedere [SQL Server Data and log file Placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4a5c9-160">For details about the data and log files for each database, including default names, see [SQL Server data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="4a5c9-161">File di dati e di registro di SQL Server, inclusi quelli per il database front-end, l'archivio Lync e l'archivio di RtcDatabase.</span><span class="sxs-lookup"><span data-stu-id="4a5c9-161">SQL Server data and log files, including those for the Front-end database, Lync store, and RtcDatabase store.</span></span> <span data-ttu-id="4a5c9-162">Sono in genere in% UnitàLocale% \\ CSData.</span><span class="sxs-lookup"><span data-stu-id="4a5c9-162">They are normally under %localdrive%\\CSData.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

