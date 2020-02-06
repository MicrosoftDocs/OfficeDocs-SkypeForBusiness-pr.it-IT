---
title: Esclusioni di scansione antivirus per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 10d296e36324fdbc8bca8f7da48370d619774501
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815694"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="a6aa9-103">Esclusioni di scansione antivirus per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a6aa9-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="a6aa9-104">Panoramica dell'interoperabilità dello scanner antivirus con Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a6aa9-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="a6aa9-105">Per assicurarsi che lo scanner antivirus non interferisca con il funzionamento di Skype for Business Server, è necessario escludere processi e directory specifici per ogni ruolo server o server Skype for Business Server in cui si esegue uno scanner antivirus.</span><span class="sxs-lookup"><span data-stu-id="a6aa9-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="a6aa9-106">I processi e le directory seguenti devono essere esclusi:</span><span class="sxs-lookup"><span data-stu-id="a6aa9-106">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="a6aa9-107">Le posizioni di cartella e file elencate di seguito sono le posizioni predefinite per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a6aa9-107">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="a6aa9-108">Per qualsiasi posizione per cui non è stato usato l'impostazione predefinita, escludere i percorsi specificati per l'organizzazione anziché i percorsi predefiniti specificati in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="a6aa9-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6aa9-109">Tieni presente che alcuni programmi antivirus potrebbero avere bisogno di percorsi assoluti, non relativi, per l'elenco di esclusione.</span><span class="sxs-lookup"><span data-stu-id="a6aa9-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="a6aa9-110">Processi di Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="a6aa9-110">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="a6aa9-111">ABServer. exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-111">ABServer.exe</span></span>

  - <span data-ttu-id="a6aa9-112">ASMCUSvc. exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-112">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="a6aa9-113">AVMCUSvc. exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-113">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="a6aa9-114">ChannelService. exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-114">ChannelService.exe</span></span>

  - <span data-ttu-id="a6aa9-115">ClsAgent. exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-115">ClsAgent.exe</span></span>

  - <span data-ttu-id="a6aa9-116">ComplianceService. exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-116">ComplianceService.exe</span></span>

  - <span data-ttu-id="a6aa9-117">DataMCUSvc. exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-117">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="a6aa9-118">Dataproxy. exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-118">DataProxy.exe</span></span>

  - <span data-ttu-id="a6aa9-119">FileTransferAgent. exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-119">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="a6aa9-120">HealthAgent. exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-120">HealthAgent.exe</span></span>

  - <span data-ttu-id="a6aa9-121">IMMCUSvc. exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-121">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="a6aa9-122">LyncBackupService. exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-122">LyncBackupService.exe</span></span>

  - <span data-ttu-id="a6aa9-123">LysSvc. exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-123">LysSvc.exe</span></span>

  - <span data-ttu-id="a6aa9-124">MasterReplicatorAgent. exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-124">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="a6aa9-125">MediaRelaySvc. exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-125">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="a6aa9-126">MediationServerSvc. exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-126">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="a6aa9-127">MRASSvc. exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-127">MRASSvc.exe</span></span>

  - <span data-ttu-id="a6aa9-128">OcsAppServerHost. exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-128">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="a6aa9-129">ReplicaReplicatorAgent. exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-129">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="a6aa9-130">ReplicationApp. exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-130">ReplicationApp.exe</span></span>

  - <span data-ttu-id="a6aa9-131">RtcHost. exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-131">RtcHost.exe</span></span>

  - <span data-ttu-id="a6aa9-132">RTCSrv. exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-132">RTCSrv.exe</span></span>

  - <span data-ttu-id="a6aa9-133">XmppProxy. exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-133">XmppProxy.exe</span></span>

  - <span data-ttu-id="a6aa9-134">XmppTGW. exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-134">XmppTGW.exe</span></span>

- <span data-ttu-id="a6aa9-135">Processi del servizio host di Windows Fabric:</span><span class="sxs-lookup"><span data-stu-id="a6aa9-135">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="a6aa9-136">Fabric. exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-136">Fabric.exe</span></span>

  - <span data-ttu-id="a6aa9-137">FabricDCA. exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-137">FabricDCA.exe</span></span>

  - <span data-ttu-id="a6aa9-138">FabricHost. exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-138">FabricHost.exe</span></span>

- <span data-ttu-id="a6aa9-139">Processi di IIS:</span><span class="sxs-lookup"><span data-stu-id="a6aa9-139">IIS processes:</span></span>

  - <span data-ttu-id="a6aa9-140">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-140">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="a6aa9-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="a6aa9-142">Processi di back-end di SQL Server:</span><span class="sxs-lookup"><span data-stu-id="a6aa9-142">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="a6aa9-143">Tieni presente che questi percorsi sono specifici della versione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a6aa9-143">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="a6aa9-144">%Programmi%\Microsoft SQL Server\MSSQL11. MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="a6aa9-145">%Programmi%\Microsoft SQL Server\MSRS11. MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="a6aa9-146">%Programmi%\Microsoft SQL Server\MSAS11. MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="a6aa9-147">Processi front-end di SQL Server:</span><span class="sxs-lookup"><span data-stu-id="a6aa9-147">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="a6aa9-148">%Programmi%\Microsoft SQL Server\MSSQL12. LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="a6aa9-149">%Programmi%\Microsoft SQL Server\MSSQL12. RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="a6aa9-150">Istanza RTC di installazione di Standard Edition</span><span class="sxs-lookup"><span data-stu-id="a6aa9-150">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="a6aa9-151">%Programmi%\Microsoft SQL Server\MSSQL12. RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="a6aa9-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="a6aa9-152">Directory e file:</span><span class="sxs-lookup"><span data-stu-id="a6aa9-152">Directories and files:</span></span>

  - <span data-ttu-id="a6aa9-153">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="a6aa9-153">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="a6aa9-154">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="a6aa9-154">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="a6aa9-155">GAC_MSIL%systemroot%\Microsoft.NET\assembly\</span><span class="sxs-lookup"><span data-stu-id="a6aa9-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="a6aa9-156">Tieni presente che questi percorsi sono specifici della versione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a6aa9-156">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="a6aa9-157">%programfiles%\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a6aa9-157">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="a6aa9-158">Nodo%programfiles%\Common Skype for Business Server 2015 \ Watcher</span><span class="sxs-lookup"><span data-stu-id="a6aa9-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="a6aa9-159">%programfiles%\Common Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a6aa9-159">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="a6aa9-160">%programfiles%\Common Skype for business online</span><span class="sxs-lookup"><span data-stu-id="a6aa9-160">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="a6aa9-161">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="a6aa9-161">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="a6aa9-162">Archivio condivisione file (specificato in Generatore di topologia).</span><span class="sxs-lookup"><span data-stu-id="a6aa9-162">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="a6aa9-163">Gli archivi di file sono specificati in Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="a6aa9-163">File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="a6aa9-164">Dati e file di log di SQL Server, inclusi quelli per il database back-end, l'archivio utenti, l'archivio archiviazione, l'archivio di monitoraggio e l'archivio applicazioni.</span><span class="sxs-lookup"><span data-stu-id="a6aa9-164">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="a6aa9-165">I file di database e di log possono essere specificati in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="a6aa9-165">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="a6aa9-166">Per informazioni dettagliate sui file di dati e di log per ogni database, inclusi i nomi predefiniti, vedere [dati di SQL Server e registrazione dei file](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a6aa9-166">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="a6aa9-167">Dati e file di log di SQL Server, inclusi quelli per il database front-end, Skype for Business Store e RtcDatabase Store.</span><span class="sxs-lookup"><span data-stu-id="a6aa9-167">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="a6aa9-168">In genere sono in%localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="a6aa9-168">They are normally under %localdrive%\CSData.</span></span>


