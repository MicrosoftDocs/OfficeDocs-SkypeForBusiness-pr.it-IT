---
title: "Lync Server 2013: Esclusioni dall'analisi antivirus"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6f354b93bf21f054e9b5b24e3befd1787279bbe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a><span data-ttu-id="e18ee-102">Esclusioni dall'analisi antivirus per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e18ee-102">Antivirus scanning exclusions for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e18ee-103">_**Argomento Ultima modifica:** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="e18ee-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="e18ee-104">Per assicurarsi che lo scanner antivirus non interferisca con l'operazione di Lync Server 2013, è necessario escludere processi e directory specifici per ogni ruolo server o server di Lync Server 2013 in cui si esegue uno scanner antivirus.</span><span class="sxs-lookup"><span data-stu-id="e18ee-104">To ensure that the antivirus scanner does not interfere with the operation of Lync Server 2013, you must exclude specific processes and directories for each Lync Server 2013 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="e18ee-105">I processi e le directory seguenti devono essere esclusi:</span><span class="sxs-lookup"><span data-stu-id="e18ee-105">The following processes and directories should be excluded:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e18ee-106">Le posizioni di cartella e file elencate di seguito sono le posizioni predefinite per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e18ee-106">Folder and file locations listed below are the default locations for Lync Server 2013.</span></span> <span data-ttu-id="e18ee-107">Per qualsiasi posizione per cui non è stato usato l'impostazione predefinita, escludere i percorsi specificati per l'organizzazione anziché i percorsi predefiniti specificati in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e18ee-107">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e18ee-108">Tieni presente che alcuni programmi antivirus potrebbero avere bisogno di percorsi assoluti, non relativi, per l'elenco di esclusione.</span><span class="sxs-lookup"><span data-stu-id="e18ee-108">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>



</div>

  - <span data-ttu-id="e18ee-109">Processi di Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="e18ee-109">Lync Server 2013 processes:</span></span>
    
      - <span data-ttu-id="e18ee-110">ABServer. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-110">ABServer.exe</span></span>
    
      - <span data-ttu-id="e18ee-111">AcpMcuSvc. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-111">AcpMcuSvc.exe</span></span>
    
      - <span data-ttu-id="e18ee-112">ASMCUSvc. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-112">ASMCUSvc.exe</span></span>
    
      - <span data-ttu-id="e18ee-113">AVMCUSvc. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-113">AVMCUSvc.exe</span></span>
    
      - <span data-ttu-id="e18ee-114">ChannelService. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-114">ChannelService.exe</span></span>
    
      - <span data-ttu-id="e18ee-115">ClsAgent. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-115">ClsAgent.exe</span></span>
    
      - <span data-ttu-id="e18ee-116">ComplianceService. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-116">ComplianceService.exe</span></span>
    
      - <span data-ttu-id="e18ee-117">DataMCUSvc. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-117">DataMCUSvc.exe</span></span>
    
      - <span data-ttu-id="e18ee-118">Dataproxy. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-118">DataProxy.exe</span></span>
    
      - <span data-ttu-id="e18ee-119">FileTransferAgent. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-119">FileTransferAgent.exe</span></span>
    
      - <span data-ttu-id="e18ee-120">IMMCUSvc. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-120">IMMCUSvc.exe</span></span>
    
      - <span data-ttu-id="e18ee-121">LysSvc. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-121">LysSvc.exe</span></span>
    
      - <span data-ttu-id="e18ee-122">MasterReplicatorAgent. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-122">MasterReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="e18ee-123">MediaRelaySvc. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-123">MediaRelaySvc.exe</span></span>
    
      - <span data-ttu-id="e18ee-124">MediationServerSvc. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-124">MediationServerSvc.exe</span></span>
    
      - <span data-ttu-id="e18ee-125">MRASSvc. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-125">MRASSvc.exe</span></span>
    
      - <span data-ttu-id="e18ee-126">OcsAppServerHost. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-126">OcsAppServerHost.exe</span></span>
    
      - <span data-ttu-id="e18ee-127">ReplicaReplicatorAgent. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-127">ReplicaReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="e18ee-128">ReplicationApp. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-128">ReplicationApp.exe</span></span>
    
      - <span data-ttu-id="e18ee-129">RtcHost. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-129">RtcHost.exe</span></span>
    
      - <span data-ttu-id="e18ee-130">RTCSrv. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-130">RTCSrv.exe</span></span>
    
      - <span data-ttu-id="e18ee-131">XmppProxy. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-131">XmppProxy.exe</span></span>
    
      - <span data-ttu-id="e18ee-132">XmppTGW. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-132">XmppTGW.exe</span></span>

  - <span data-ttu-id="e18ee-133">Processi del servizio host di Windows Fabric:</span><span class="sxs-lookup"><span data-stu-id="e18ee-133">Windows Fabric Host Service processes:</span></span>
    
      - <span data-ttu-id="e18ee-134">Fabric. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-134">Fabric.exe</span></span>
    
      - <span data-ttu-id="e18ee-135">FabricDCA. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-135">FabricDCA.exe</span></span>
    
      - <span data-ttu-id="e18ee-136">FabricHost. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-136">FabricHost.exe</span></span>

  - <span data-ttu-id="e18ee-137">Processi di IIS:</span><span class="sxs-lookup"><span data-stu-id="e18ee-137">IIS processes:</span></span>
    
      - <span data-ttu-id="e18ee-138">% SystemRoot%\\system32\\inetsrv\\w3wp. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-138">%systemroot%\\system32\\inetsrv\\w3wp.exe</span></span>
    
      - <span data-ttu-id="e18ee-139">% SystemRoot%\\SysWow64\\inetsrv\\w3wp. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-139">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span></span>

  - <span data-ttu-id="e18ee-140">Processi di back-end di SQL Server:</span><span class="sxs-lookup"><span data-stu-id="e18ee-140">SQL Server Back-End processes:</span></span>
    
      - <span data-ttu-id="e18ee-141">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11. MSSQLSERVER\\MSSQL\\contenitori\\sqlservr. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-141">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="e18ee-142">% ProgramFiles%\\Microsoft SQL Server\\MSRS11. MSSQLSERVER\\di Reporting\\Services\\ReportServer\\bin ReportingServicesService. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-142">%ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span></span>
    
      - <span data-ttu-id="e18ee-143">% ProgramFiles%\\Microsoft SQL Server\\MSAS11. MSMDSrv\\.\\exe\\di MSSQLSERVER OLAP bin</span><span class="sxs-lookup"><span data-stu-id="e18ee-143">%ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span></span>

  - <span data-ttu-id="e18ee-144">Processi front-end di SQL Server:</span><span class="sxs-lookup"><span data-stu-id="e18ee-144">SQL Server Front-End processes:</span></span>
    
      - <span data-ttu-id="e18ee-145">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11. LYNCLOCAL\\MSSQL\\contenitori\\sqlservr. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-145">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="e18ee-146">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11. RTCLOCAL\\MSSQL\\contenitori\\sqlservr. exe</span><span class="sxs-lookup"><span data-stu-id="e18ee-146">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>

  - <span data-ttu-id="e18ee-147">Directory e file:</span><span class="sxs-lookup"><span data-stu-id="e18ee-147">Directories and files:</span></span>
    
      - <span data-ttu-id="e18ee-148">file di log\\di\\% SystemRoot% system32</span><span class="sxs-lookup"><span data-stu-id="e18ee-148">%systemroot%\\System32\\LogFiles</span></span>
    
      - <span data-ttu-id="e18ee-149">file di log\\di\\SysWow64% SystemRoot%</span><span class="sxs-lookup"><span data-stu-id="e18ee-149">%systemroot%\\SysWow64\\LogFiles</span></span>
    
      - <span data-ttu-id="e18ee-150">% SystemRoot%\\Microsoft.NET\\assembly\\MSIL\_GAC</span><span class="sxs-lookup"><span data-stu-id="e18ee-150">%systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span></span>
    
      - <span data-ttu-id="e18ee-151">% ProgramFiles%\\Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e18ee-151">%programfiles%\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="e18ee-152">Nodo di Watcher\\di\\Microsoft Lync Server 2013\\per% programmi% comuni</span><span class="sxs-lookup"><span data-stu-id="e18ee-152">%programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node</span></span>
    
      - <span data-ttu-id="e18ee-153">% programmi%\\file\\comuni Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e18ee-153">%programfiles%\\Common Files\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="e18ee-154">% SystemDrive%\\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="e18ee-154">%SystemDrive%\\RtcReplicaRoot</span></span>
    
      - <span data-ttu-id="e18ee-155">Archivio condivisione file (specificato in Generatore di topologia).</span><span class="sxs-lookup"><span data-stu-id="e18ee-155">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="e18ee-156">Gli archivi di file sono specificati in Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="e18ee-156">File stores are specified in Topology Builder.</span></span>
    
      - <span data-ttu-id="e18ee-157">Dati e file di log di SQL Server, inclusi quelli per il database back-end, l'archivio utenti, l'archivio archiviazione, l'archivio di monitoraggio e l'archivio applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e18ee-157">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="e18ee-158">I file di database e di log possono essere specificati in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="e18ee-158">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="e18ee-159">Per informazioni dettagliate sui file di dati e di log per ogni database, inclusi i nomi predefiniti, vedere [dati di SQL Server e il posizionamento dei file di log per Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e18ee-159">For details about the data and log files for each database, including default names, see [SQL Server data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="e18ee-160">Dati e file di log di SQL Server, inclusi quelli per il database front-end, Lync Store e RtcDatabase Store.</span><span class="sxs-lookup"><span data-stu-id="e18ee-160">SQL Server data and log files, including those for the Front-end database, Lync store, and RtcDatabase store.</span></span> <span data-ttu-id="e18ee-161">In genere sono in% UnitàLocale%\\CSData.</span><span class="sxs-lookup"><span data-stu-id="e18ee-161">They are normally under %localdrive%\\CSData.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

