---
title: Esclusioni di scansione antivirus per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Panoramica dell'interoperabilità dello scanner antivirus con Skype for Business Server.
ms.openlocfilehash: 9ec13b31328744bb154c9eb5e09dff7665c4b540
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194897"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="150fd-103">Esclusioni di scansione antivirus per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="150fd-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="150fd-104">Panoramica dell'interoperabilità dello scanner antivirus con Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="150fd-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="150fd-105">Questo articolo contiene raccomandazioni che possono aiutare un amministratore a determinare la causa di un'instabilità potenziale in un computer che sta usando una versione supportata di Microsoft Windows quando viene usata con il software antivirus in un dominio Active Directory ambiente o in un ambiente aziendale gestito.</span><span class="sxs-lookup"><span data-stu-id="150fd-105">This article contains recommendations that may help an administrator determine the cause of potential instability on a computer that is running a supported version of Microsoft Windows when it is used with antivirus software in an Active Directory domain environment or in a managed business environment.</span></span>

<span data-ttu-id="150fd-106">Ti consigliamo di applicare temporaneamente queste procedure per valutare un sistema.</span><span class="sxs-lookup"><span data-stu-id="150fd-106">We recommend that you temporarily apply these procedures to evaluate a system.</span></span> <span data-ttu-id="150fd-107">Se le prestazioni del sistema o la stabilità sono migliorate dalle raccomandazioni apportate in questo articolo, contattare il fornitore del software antivirus per istruzioni o per una versione aggiornata del software antivirus.</span><span class="sxs-lookup"><span data-stu-id="150fd-107">If your system performance or stability is improved by the recommendations that are made in this article, contact your antivirus software vendor for instructions or for an updated version of the antivirus software.</span></span>

<span data-ttu-id="150fd-108">Questo articolo contiene informazioni che illustrano come semplificare la riduzione delle impostazioni di sicurezza o come disattivare temporaneamente le caratteristiche di sicurezza in un computer.</span><span class="sxs-lookup"><span data-stu-id="150fd-108">This article contains information that shows how to help lower security settings or how to temporarily turn off security features on a computer.</span></span> <span data-ttu-id="150fd-109">È possibile apportare queste modifiche per comprendere la natura di un problema specifico.</span><span class="sxs-lookup"><span data-stu-id="150fd-109">You can make these changes to understand the nature of a specific problem.</span></span> <span data-ttu-id="150fd-110">Prima di apportare queste modifiche, è consigliabile valutare i rischi associati all'implementazione di questa soluzione alternativa nell'ambiente specifico.</span><span class="sxs-lookup"><span data-stu-id="150fd-110">Before you make these changes, we recommend that you evaluate the risks that are associated with implementing this workaround in your particular environment.</span></span> <span data-ttu-id="150fd-111">Se si implementa questa soluzione alternativa, eseguire qualsiasi procedura complementare appropriata per proteggere il computer per i file che non vengono più analizzati dal software antivirus.</span><span class="sxs-lookup"><span data-stu-id="150fd-111">If you implement this workaround, take any appropriate additional steps to help protect the computer for the files that are no longer being scanned by your antivirus software.</span></span>

<span data-ttu-id="150fd-112">Per assicurarsi che lo scanner antivirus non interferisca con il funzionamento di Skype for Business Server, è necessario escludere processi e directory specifici per ogni ruolo server o server Skype for Business Server in cui si esegue uno scanner antivirus.</span><span class="sxs-lookup"><span data-stu-id="150fd-112">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="150fd-113">I processi e le directory seguenti devono essere esclusi:</span><span class="sxs-lookup"><span data-stu-id="150fd-113">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="150fd-114">Le posizioni di cartella e file elencate di seguito sono le posizioni predefinite per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="150fd-114">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="150fd-115">Per qualsiasi posizione per cui non è stato usato l'impostazione predefinita, escludere i percorsi specificati per l'organizzazione anziché i percorsi predefiniti specificati in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="150fd-115">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="150fd-116">Tieni presente che alcuni programmi antivirus potrebbero avere bisogno di percorsi assoluti, non relativi, per l'elenco di esclusione.</span><span class="sxs-lookup"><span data-stu-id="150fd-116">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="150fd-117">Processi di Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="150fd-117">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="150fd-118">ABServer. exe</span><span class="sxs-lookup"><span data-stu-id="150fd-118">ABServer.exe</span></span>

  - <span data-ttu-id="150fd-119">ASMCUSvc. exe</span><span class="sxs-lookup"><span data-stu-id="150fd-119">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="150fd-120">AVMCUSvc. exe</span><span class="sxs-lookup"><span data-stu-id="150fd-120">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="150fd-121">ChannelService. exe</span><span class="sxs-lookup"><span data-stu-id="150fd-121">ChannelService.exe</span></span>

  - <span data-ttu-id="150fd-122">ClsAgent. exe</span><span class="sxs-lookup"><span data-stu-id="150fd-122">ClsAgent.exe</span></span>

  - <span data-ttu-id="150fd-123">ComplianceService. exe</span><span class="sxs-lookup"><span data-stu-id="150fd-123">ComplianceService.exe</span></span>

  - <span data-ttu-id="150fd-124">DataMCUSvc. exe</span><span class="sxs-lookup"><span data-stu-id="150fd-124">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="150fd-125">Dataproxy. exe</span><span class="sxs-lookup"><span data-stu-id="150fd-125">DataProxy.exe</span></span>

  - <span data-ttu-id="150fd-126">FileTransferAgent. exe</span><span class="sxs-lookup"><span data-stu-id="150fd-126">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="150fd-127">HealthAgent. exe</span><span class="sxs-lookup"><span data-stu-id="150fd-127">HealthAgent.exe</span></span>

  - <span data-ttu-id="150fd-128">IMMCUSvc. exe</span><span class="sxs-lookup"><span data-stu-id="150fd-128">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="150fd-129">LyncBackupService. exe</span><span class="sxs-lookup"><span data-stu-id="150fd-129">LyncBackupService.exe</span></span>

  - <span data-ttu-id="150fd-130">LysSvc. exe</span><span class="sxs-lookup"><span data-stu-id="150fd-130">LysSvc.exe</span></span>

  - <span data-ttu-id="150fd-131">MasterReplicatorAgent. exe</span><span class="sxs-lookup"><span data-stu-id="150fd-131">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="150fd-132">MediaRelaySvc. exe</span><span class="sxs-lookup"><span data-stu-id="150fd-132">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="150fd-133">MediationServerSvc. exe</span><span class="sxs-lookup"><span data-stu-id="150fd-133">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="150fd-134">MRASSvc. exe</span><span class="sxs-lookup"><span data-stu-id="150fd-134">MRASSvc.exe</span></span>

  - <span data-ttu-id="150fd-135">OcsAppServerHost. exe</span><span class="sxs-lookup"><span data-stu-id="150fd-135">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="150fd-136">ReplicaReplicatorAgent. exe</span><span class="sxs-lookup"><span data-stu-id="150fd-136">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="150fd-137">ReplicationApp. exe</span><span class="sxs-lookup"><span data-stu-id="150fd-137">ReplicationApp.exe</span></span>

  - <span data-ttu-id="150fd-138">RtcHost. exe</span><span class="sxs-lookup"><span data-stu-id="150fd-138">RtcHost.exe</span></span>

  - <span data-ttu-id="150fd-139">RTCSrv. exe</span><span class="sxs-lookup"><span data-stu-id="150fd-139">RTCSrv.exe</span></span>

  - <span data-ttu-id="150fd-140">XmppProxy. exe</span><span class="sxs-lookup"><span data-stu-id="150fd-140">XmppProxy.exe</span></span>

  - <span data-ttu-id="150fd-141">XmppTGW. exe</span><span class="sxs-lookup"><span data-stu-id="150fd-141">XmppTGW.exe</span></span>

- <span data-ttu-id="150fd-142">Processi del servizio host di Windows Fabric:</span><span class="sxs-lookup"><span data-stu-id="150fd-142">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="150fd-143">Fabric. exe</span><span class="sxs-lookup"><span data-stu-id="150fd-143">Fabric.exe</span></span>

  - <span data-ttu-id="150fd-144">FabricDCA. exe</span><span class="sxs-lookup"><span data-stu-id="150fd-144">FabricDCA.exe</span></span>

  - <span data-ttu-id="150fd-145">FabricHost. exe</span><span class="sxs-lookup"><span data-stu-id="150fd-145">FabricHost.exe</span></span>

- <span data-ttu-id="150fd-146">Processi di IIS:</span><span class="sxs-lookup"><span data-stu-id="150fd-146">IIS processes:</span></span>

  - <span data-ttu-id="150fd-147">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="150fd-147">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="150fd-148">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="150fd-148">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="150fd-149">Processi di back-end di SQL Server:</span><span class="sxs-lookup"><span data-stu-id="150fd-149">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="150fd-150">Tieni presente che questi percorsi sono specifici della versione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="150fd-150">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="150fd-151">%Programmi%\Microsoft SQL Server\MSSQL11. MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="150fd-151">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="150fd-152">%Programmi%\Microsoft SQL Server\MSRS11. MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="150fd-152">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="150fd-153">%Programmi%\Microsoft SQL Server\MSAS11. MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="150fd-153">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="150fd-154">Processi front-end di SQL Server:</span><span class="sxs-lookup"><span data-stu-id="150fd-154">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="150fd-155">%Programmi%\Microsoft SQL Server\MSSQL12. LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="150fd-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="150fd-156">%Programmi%\Microsoft SQL Server\MSSQL12. RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="150fd-156">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="150fd-157">Istanza RTC di installazione di Standard Edition</span><span class="sxs-lookup"><span data-stu-id="150fd-157">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="150fd-158">%Programmi%\Microsoft SQL Server\MSSQL12. RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="150fd-158">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="150fd-159">Directory e file:</span><span class="sxs-lookup"><span data-stu-id="150fd-159">Directories and files:</span></span>

  - <span data-ttu-id="150fd-160">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="150fd-160">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="150fd-161">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="150fd-161">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="150fd-162">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="150fd-162">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="150fd-163">Tieni presente che questi percorsi sono specifici della versione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="150fd-163">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="150fd-164">%programfiles%\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="150fd-164">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="150fd-165">Nodo%programfiles%\Common Skype for Business Server 2015 \ Watcher</span><span class="sxs-lookup"><span data-stu-id="150fd-165">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="150fd-166">%programfiles%\Common Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="150fd-166">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="150fd-167">%programfiles%\Common Skype for business online</span><span class="sxs-lookup"><span data-stu-id="150fd-167">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="150fd-168">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="150fd-168">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="150fd-169">Archivio condivisione file (specificato in Generatore di topologia).</span><span class="sxs-lookup"><span data-stu-id="150fd-169">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="150fd-170">Gli archivi di file sono specificati in Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="150fd-170">File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="150fd-171">Dati e file di log di SQL Server, inclusi quelli per il database back-end, l'archivio utenti, l'archivio archiviazione, l'archivio di monitoraggio e l'archivio applicazioni.</span><span class="sxs-lookup"><span data-stu-id="150fd-171">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="150fd-172">I file di database e di log possono essere specificati in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="150fd-172">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="150fd-173">Per informazioni dettagliate sui file di dati e di log per ogni database, inclusi i nomi predefiniti, vedere [dati di SQL Server e registrazione dei file](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="150fd-173">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="150fd-174">Dati e file di log di SQL Server, inclusi quelli per il database front-end, Skype for Business Store e RtcDatabase Store.</span><span class="sxs-lookup"><span data-stu-id="150fd-174">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="150fd-175">In genere sono in%localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="150fd-175">They are normally under %localdrive%\CSData.</span></span>


