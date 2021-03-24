---
title: Esclusioni di analisi antivirus per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Panoramica dell'interoperabilità degli scanner antivirus con Skype for Business Server.
ms.openlocfilehash: 64646304b98de075fd9af0a82096da8c0bff2f12
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104242"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="2d1ca-103">Esclusioni di analisi antivirus per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2d1ca-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="2d1ca-104">Panoramica dell'interoperabilità degli scanner antivirus con Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2d1ca-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="2d1ca-105">Per assicurarsi che lo scanner antivirus non interferisca con il funzionamento di Skype for Business Server, è necessario escludere processi e directory specifici per ogni server o ruolo del server Skype for Business Server in cui si esegue uno scanner antivirus.</span><span class="sxs-lookup"><span data-stu-id="2d1ca-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="2d1ca-106">È necessario escludere le directory e i processi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d1ca-106">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="2d1ca-107">I percorsi delle cartelle e dei file elencati di seguito sono i percorsi predefiniti per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2d1ca-107">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="2d1ca-108">Per tutti i percorsi per i quali non è stata utilizzata l'impostazione predefinita, escludere i percorsi specificati per l'organizzazione anziché i percorsi predefiniti specificati in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="2d1ca-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2d1ca-109">Tenere presente che alcuni programmi antivirus potrebbero avere bisogno di percorsi assoluti, non relativi, per l'elenco di esclusione.</span><span class="sxs-lookup"><span data-stu-id="2d1ca-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="2d1ca-110">Processi di Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="2d1ca-110">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="2d1ca-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-111">ABServer.exe</span></span>

  - <span data-ttu-id="2d1ca-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-112">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="2d1ca-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-113">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="2d1ca-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-114">ChannelService.exe</span></span>

  - <span data-ttu-id="2d1ca-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-115">ClsAgent.exe</span></span>

  - <span data-ttu-id="2d1ca-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-116">ComplianceService.exe</span></span>

  - <span data-ttu-id="2d1ca-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-117">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="2d1ca-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-118">DataProxy.exe</span></span>

  - <span data-ttu-id="2d1ca-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-119">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="2d1ca-120">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-120">HealthAgent.exe</span></span>

  - <span data-ttu-id="2d1ca-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-121">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="2d1ca-122">LyncBackupService.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-122">LyncBackupService.exe</span></span>

  - <span data-ttu-id="2d1ca-123">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-123">LysSvc.exe</span></span>

  - <span data-ttu-id="2d1ca-124">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-124">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="2d1ca-125">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-125">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="2d1ca-126">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-126">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="2d1ca-127">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-127">MRASSvc.exe</span></span>

  - <span data-ttu-id="2d1ca-128">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-128">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="2d1ca-129">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-129">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="2d1ca-130">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-130">ReplicationApp.exe</span></span>

  - <span data-ttu-id="2d1ca-131">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-131">RtcHost.exe</span></span>

  - <span data-ttu-id="2d1ca-132">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-132">RTCSrv.exe</span></span>

  - <span data-ttu-id="2d1ca-133">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-133">XmppProxy.exe</span></span>

  - <span data-ttu-id="2d1ca-134">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-134">XmppTGW.exe</span></span>

- <span data-ttu-id="2d1ca-135">Processi del servizio Host Windows Fabric:</span><span class="sxs-lookup"><span data-stu-id="2d1ca-135">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="2d1ca-136">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-136">Fabric.exe</span></span>

  - <span data-ttu-id="2d1ca-137">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-137">FabricDCA.exe</span></span>

  - <span data-ttu-id="2d1ca-138">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-138">FabricHost.exe</span></span>

- <span data-ttu-id="2d1ca-139">Processi IIS:</span><span class="sxs-lookup"><span data-stu-id="2d1ca-139">IIS processes:</span></span>

  - <span data-ttu-id="2d1ca-140">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-140">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="2d1ca-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="2d1ca-142">SQL Server Back-End processi:</span><span class="sxs-lookup"><span data-stu-id="2d1ca-142">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="2d1ca-143">Tieni presente che questi percorsi sono specifici della SQL Server versione.</span><span class="sxs-lookup"><span data-stu-id="2d1ca-143">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="2d1ca-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="2d1ca-145">%ProgramFiles%\Microsoft SQL Server\MSRS11. MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="2d1ca-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="2d1ca-147">SQL Server Front-End processi:</span><span class="sxs-lookup"><span data-stu-id="2d1ca-147">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="2d1ca-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="2d1ca-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="2d1ca-150">Istanza RTC di installazione Standard Edition</span><span class="sxs-lookup"><span data-stu-id="2d1ca-150">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="2d1ca-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="2d1ca-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="2d1ca-152">Directory e file:</span><span class="sxs-lookup"><span data-stu-id="2d1ca-152">Directories and files:</span></span>

  - <span data-ttu-id="2d1ca-153">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="2d1ca-153">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="2d1ca-154">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="2d1ca-154">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="2d1ca-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="2d1ca-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="2d1ca-156">Tieni presente che questi percorsi sono specifici della versione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2d1ca-156">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="2d1ca-157">%programfiles%\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2d1ca-157">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="2d1ca-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="2d1ca-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="2d1ca-159">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2d1ca-159">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="2d1ca-160">%programfiles%\Common Files\Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="2d1ca-160">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="2d1ca-161">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="2d1ca-161">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="2d1ca-p103">Archivio condivisione file (specificato in Generatore di topologie). Gli archivi file sono specificati in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="2d1ca-p103">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="2d1ca-164">File di registro e dati di SQL Server, inclusi quelli per il database back-end, l'archivio utente, l'archivio di archiviazione, l'archivio di monitoraggio e l'archivio applicazioni.</span><span class="sxs-lookup"><span data-stu-id="2d1ca-164">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="2d1ca-165">I file di registro e di database possono essere specificati in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="2d1ca-165">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="2d1ca-166">Per informazioni dettagliate sui dati e i file di registro per ogni database, inclusi i nomi predefiniti, vedere [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2d1ca-166">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in the Deployment documentation.</span></span>

  - <span data-ttu-id="2d1ca-167">SQL Server file di dati e di registro, inclusi quelli per il database front-end, l'archivio Skype for Business e l'archivio RtcDatabase.</span><span class="sxs-lookup"><span data-stu-id="2d1ca-167">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="2d1ca-168">In genere sono in %localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="2d1ca-168">They are normally under %localdrive%\CSData.</span></span>