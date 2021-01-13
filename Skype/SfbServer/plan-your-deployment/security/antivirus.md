---
title: Esclusioni di scansione antivirus per Skype for Business Server
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
description: Panoramica dell'interoperabilità dello scanner antivirus con Skype for Business Server.
ms.openlocfilehash: b59a5c474a96d312ebe3a648536ebe827e684931
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832266"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="a65b0-103">Esclusioni di scansione antivirus per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a65b0-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="a65b0-104">Panoramica dell'interoperabilità dello scanner antivirus con Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a65b0-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="a65b0-105">Per assicurarsi che lo scanner antivirus non interferisca con il funzionamento di Skype for Business Server, è necessario escludere processi e directory specifici per ogni server Skype for Business Server o ruolo del server in cui si esegue uno scanner antivirus.</span><span class="sxs-lookup"><span data-stu-id="a65b0-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="a65b0-106">È necessario escludere le directory e i processi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a65b0-106">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="a65b0-107">Le posizioni dei file e delle cartelle elencate di seguito sono le posizioni predefinite per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a65b0-107">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="a65b0-108">Per tutti i percorsi per i quali non è stata utilizzata l'impostazione predefinita, escludere i percorsi specificati per l'organizzazione anziché i percorsi predefiniti specificati in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="a65b0-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a65b0-109">Tenere presente che alcuni programmi antivirus potrebbero richiedere percorsi assoluti, non relativi, per l'elenco di esclusione.</span><span class="sxs-lookup"><span data-stu-id="a65b0-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="a65b0-110">Processi di Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="a65b0-110">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="a65b0-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-111">ABServer.exe</span></span>

  - <span data-ttu-id="a65b0-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-112">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="a65b0-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-113">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="a65b0-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-114">ChannelService.exe</span></span>

  - <span data-ttu-id="a65b0-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-115">ClsAgent.exe</span></span>

  - <span data-ttu-id="a65b0-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-116">ComplianceService.exe</span></span>

  - <span data-ttu-id="a65b0-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-117">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="a65b0-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-118">DataProxy.exe</span></span>

  - <span data-ttu-id="a65b0-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-119">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="a65b0-120">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-120">HealthAgent.exe</span></span>

  - <span data-ttu-id="a65b0-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-121">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="a65b0-122">LyncBackupService.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-122">LyncBackupService.exe</span></span>

  - <span data-ttu-id="a65b0-123">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-123">LysSvc.exe</span></span>

  - <span data-ttu-id="a65b0-124">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-124">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="a65b0-125">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-125">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="a65b0-126">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-126">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="a65b0-127">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-127">MRASSvc.exe</span></span>

  - <span data-ttu-id="a65b0-128">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-128">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="a65b0-129">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-129">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="a65b0-130">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-130">ReplicationApp.exe</span></span>

  - <span data-ttu-id="a65b0-131">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-131">RtcHost.exe</span></span>

  - <span data-ttu-id="a65b0-132">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-132">RTCSrv.exe</span></span>

  - <span data-ttu-id="a65b0-133">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-133">XmppProxy.exe</span></span>

  - <span data-ttu-id="a65b0-134">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-134">XmppTGW.exe</span></span>

- <span data-ttu-id="a65b0-135">Processi del servizio host Windows Fabric:</span><span class="sxs-lookup"><span data-stu-id="a65b0-135">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="a65b0-136">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-136">Fabric.exe</span></span>

  - <span data-ttu-id="a65b0-137">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-137">FabricDCA.exe</span></span>

  - <span data-ttu-id="a65b0-138">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-138">FabricHost.exe</span></span>

- <span data-ttu-id="a65b0-139">Processi IIS:</span><span class="sxs-lookup"><span data-stu-id="a65b0-139">IIS processes:</span></span>

  - <span data-ttu-id="a65b0-140">% SystemRoot% \system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-140">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="a65b0-141">% SystemRoot% \SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="a65b0-142">Processi di Back-End di SQL Server:</span><span class="sxs-lookup"><span data-stu-id="a65b0-142">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="a65b0-143">Tenere presente che questi percorsi sono specifici della versione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a65b0-143">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="a65b0-144">%Programmi%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="a65b0-145">%ProgramFiles%\Microsoft SQL Server\MSRS11. Services\ReportServer\Bin\ReportingServicesService.exe di MSSQLSERVER\Reporting</span><span class="sxs-lookup"><span data-stu-id="a65b0-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="a65b0-146">%Programmi%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="a65b0-147">Processi di Front-End di SQL Server:</span><span class="sxs-lookup"><span data-stu-id="a65b0-147">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="a65b0-148">%Programmi%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="a65b0-149">%Programmi%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="a65b0-150">Istanza RTC di installazione Standard Edition</span><span class="sxs-lookup"><span data-stu-id="a65b0-150">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="a65b0-151">%Programmi%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="a65b0-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="a65b0-152">Directory e file:</span><span class="sxs-lookup"><span data-stu-id="a65b0-152">Directories and files:</span></span>

  - <span data-ttu-id="a65b0-153">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="a65b0-153">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="a65b0-154">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="a65b0-154">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="a65b0-155">GAC_MSIL di%systemroot%\Microsoft.NET\assembly\</span><span class="sxs-lookup"><span data-stu-id="a65b0-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="a65b0-156">Si noti che questi percorsi sono specifici della versione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a65b0-156">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="a65b0-157">%programfiles%\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a65b0-157">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="a65b0-158">%programfiles%\Common Skype for Business Server 2015 \ nodo Watcher</span><span class="sxs-lookup"><span data-stu-id="a65b0-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="a65b0-159">%programfiles%\Common Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a65b0-159">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="a65b0-160">%programfiles%\Common Skype for business online</span><span class="sxs-lookup"><span data-stu-id="a65b0-160">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="a65b0-161">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="a65b0-161">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="a65b0-p103">Archivio condivisione file (specificato in Generatore di topologie). Gli archivi file sono specificati in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="a65b0-p103">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="a65b0-164">File di registro e dati di SQL Server, inclusi quelli per il database back-end, l'archivio utente, l'archivio di archiviazione, l'archivio di monitoraggio e l'archivio applicazioni.</span><span class="sxs-lookup"><span data-stu-id="a65b0-164">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="a65b0-165">I file di registro e di database possono essere specificati in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="a65b0-165">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="a65b0-166">Per informazioni dettagliate sui dati e i file di registro per ogni database, inclusi i nomi predefiniti, vedere [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a65b0-166">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="a65b0-167">File di dati e di registro di SQL Server, compresi quelli per il database front-end, l'archivio di Skype for business e l'archivio di RtcDatabase.</span><span class="sxs-lookup"><span data-stu-id="a65b0-167">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="a65b0-168">Sono in genere in%localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="a65b0-168">They are normally under %localdrive%\CSData.</span></span>


