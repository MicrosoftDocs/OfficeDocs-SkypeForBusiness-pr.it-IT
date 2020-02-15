---
title: 'Lync Server 2013: requisiti di backup e ripristino: strumenti e autorizzazioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: tools and permissions'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202171(v=OCS.15)
ms:contentKeyID: 51541465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b86f283aae05985ea903a17dfb15dff83574c42f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a><span data-ttu-id="b0aea-102">Requisiti di backup e ripristino in Lync Server 2013: Tools and Permissions</span><span class="sxs-lookup"><span data-stu-id="b0aea-102">Backup and restoration requirements in Lync Server 2013: tools and permissions</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0aea-103">_**Ultimo argomento modificato:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="b0aea-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="b0aea-104">In questo argomento vengono identificati gli strumenti che è possibile utilizzare per eseguire il backup e il ripristino di Lync Server 2013, le autorizzazioni necessarie e la possibilità di eseguire comandi in remoto o localmente.</span><span class="sxs-lookup"><span data-stu-id="b0aea-104">This topic identifies the tools that you can use to back up and restore Lync Server 2013, the permissions that you need, and whether you can run commands remotely or locally.</span></span> <span data-ttu-id="b0aea-105">In particolare, questo argomento si concentra sugli strumenti forniti con Lync Server per il backup e il ripristino.</span><span class="sxs-lookup"><span data-stu-id="b0aea-105">Specifically, this topic focuses on tools that are provided with Lync Server for backup and restoration.</span></span>

<div>

## <a name="backups"></a><span data-ttu-id="b0aea-106">Backup</span><span class="sxs-lookup"><span data-stu-id="b0aea-106">Backups</span></span>

<span data-ttu-id="b0aea-107">Per eseguire il backup di Lync Server, utilizzare gli strumenti identificati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b0aea-107">To back up Lync Server, use the tools identified in the following table.</span></span> <span data-ttu-id="b0aea-108">Tutti i comandi di cui è necessario eseguire il backup di Lync Server possono essere scritti in remoto e possono essere eseguiti in modalità remota.</span><span class="sxs-lookup"><span data-stu-id="b0aea-108">All the commands that you need to back up Lync Server can be scripted and can be run remotely.</span></span>

### <a name="tools-for-backing-up-lync-server"></a><span data-ttu-id="b0aea-109">Strumenti per il backup di Lync Server</span><span class="sxs-lookup"><span data-stu-id="b0aea-109">Tools for Backing Up Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0aea-110">Per il backup di questo componente:</span><span class="sxs-lookup"><span data-stu-id="b0aea-110">To back up this:</span></span></th>
<th><span data-ttu-id="b0aea-111">Utilizzare questo strumento o cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b0aea-111">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0aea-112">Dati di configurazione della topologia (Xds.mdf)</span><span class="sxs-lookup"><span data-stu-id="b0aea-112">Topology configuration data (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="b0aea-113">Export-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="b0aea-113">Export-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0aea-114">Dati del servizio Informazioni percorso (E9-1-1) (Lis.mdf)</span><span class="sxs-lookup"><span data-stu-id="b0aea-114">Location information service (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="b0aea-115">Export-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="b0aea-115">Export-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0aea-116">Dati di configurazione di Response Group (RgsConfig.mdf)</span><span class="sxs-lookup"><span data-stu-id="b0aea-116">Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="b0aea-117">Export-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="b0aea-117">Export-CsRgsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0aea-118">Dati utente permanenti (database rtcxds. MDF)</span><span class="sxs-lookup"><span data-stu-id="b0aea-118">Persistent user data (Rtcxds.mdf database)</span></span></p>
<p><span data-ttu-id="b0aea-119">ID conferenza</span><span class="sxs-lookup"><span data-stu-id="b0aea-119">Conference IDs</span></span></p></td>
<td><p><span data-ttu-id="b0aea-120">Export-CsUserData</span><span class="sxs-lookup"><span data-stu-id="b0aea-120">Export-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="b0aea-121">Database di archiviazione (LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="b0aea-121">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="b0aea-122">Database di registrazione dettagli chiamata di monitoraggio (LcsCDR.mdf)</span><span class="sxs-lookup"><span data-stu-id="b0aea-122">Monitoring call detail record database (LcsCDR.mdf)</span></span></p></li>
<li><p><span data-ttu-id="b0aea-123">Database QoE di monitoraggio (QoEMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="b0aea-123">Monitoring QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="b0aea-124">Strumento dei database di SQL Server, ad esempio SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b0aea-124">SQL Server database tool, such as SQL Server Management Studio</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0aea-125">Database di chat persistente (MGC. MDF)</span><span class="sxs-lookup"><span data-stu-id="b0aea-125">Persistent Chat database (Mgc.mdf)</span></span></p></td>
<td><p><span data-ttu-id="b0aea-126">Procedure di backup o Export-CsPersistentChatData di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b0aea-126">SQL Server backup procedures or Export-CsPersistentChatData.</span></span> <span data-ttu-id="b0aea-127">Export-CsPersistentChatData Esporta i dati della chat persistente come file.</span><span class="sxs-lookup"><span data-stu-id="b0aea-127">Export-CsPersistentChatData exports Persistent Chat data as a file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0aea-128">Tutti gli archivi file: archivio file di Lync Server, archivio file di archiviazione</span><span class="sxs-lookup"><span data-stu-id="b0aea-128">All file stores: Lync Server file store, Archiving file store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b0aea-129">Non eseguire il backup dei file denominati <STRONG>Meeting.Active</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b0aea-129">Files named <STRONG>Meeting.Active</STRONG> should not be backed up.</span></span> <span data-ttu-id="b0aea-130">Questi file sono in uso e bloccati mentre è in corso una riunione.</span><span class="sxs-lookup"><span data-stu-id="b0aea-130">These files are in use and locked while a meeting takes place.</span></span>


</div></td>
<td><p><span data-ttu-id="b0aea-131">Strumento di gestione del file System standard, ad esempio Robocopy.</span><span class="sxs-lookup"><span data-stu-id="b0aea-131">Standard file system management tool, such as Robocopy.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a><span data-ttu-id="b0aea-132">Ripristino</span><span class="sxs-lookup"><span data-stu-id="b0aea-132">Restoration</span></span>

<span data-ttu-id="b0aea-133">Per ripristinare Lync Server, utilizzare gli strumenti riportati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b0aea-133">To restore Lync Server, use the tools in the following table.</span></span> <span data-ttu-id="b0aea-134">Tutti i comandi necessari per il ripristino di Lync Server possono essere scritti tramite script.</span><span class="sxs-lookup"><span data-stu-id="b0aea-134">All the commands that you need to restore Lync Server can be scripted.</span></span> <span data-ttu-id="b0aea-135">Alcuni possono essere eseguiti in remoto, mentre altri devono essere eseguiti localmente, come specificato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b0aea-135">Some can be run remotely, but others need to be run locally, as specified in the following table.</span></span>

### <a name="tools-for-restoring-lync-server"></a><span data-ttu-id="b0aea-136">Strumenti per il ripristino di Lync Server</span><span class="sxs-lookup"><span data-stu-id="b0aea-136">Tools for Restoring Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0aea-137">Per eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="b0aea-137">To do this:</span></span></th>
<th><span data-ttu-id="b0aea-138">Utilizzare questo strumento o cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b0aea-138">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0aea-139">Creare un computer nuovo o pulito</span><span class="sxs-lookup"><span data-stu-id="b0aea-139">Build a new or clean computer</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b0aea-140">Software di installazione del sistema operativo Windows</span><span class="sxs-lookup"><span data-stu-id="b0aea-140">Windows operating system installation software</span></span></p></li>
<li><p><span data-ttu-id="b0aea-141">Software di installazione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="b0aea-141">SQL Server installation software</span></span></p></li>
<li><p><span data-ttu-id="b0aea-142">Snap-in MMC (Microsoft Management Console) Certificati, per ripristinare certificati con una chiave privata esportabile</span><span class="sxs-lookup"><span data-stu-id="b0aea-142">Certificates Microsoft Management Console (MMC) snap-in, if restoring certificates with an exportable private key</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0aea-143">Ripristinare dati dell'archivio file</span><span class="sxs-lookup"><span data-stu-id="b0aea-143">Restore file store data</span></span></p></td>
<td><p><span data-ttu-id="b0aea-144">Strumento di gestione del file system standard, ad esempio Robocopy</span><span class="sxs-lookup"><span data-stu-id="b0aea-144">Standard file system management tool, such as Robocopy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0aea-145">Ricreare database vuoti e impostare le autorizzazioni per gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b0aea-145">Recreate empty databases and set permissions for the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b0aea-146">Archivio di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="b0aea-146">Central Management store</span></span></p></li>
<li><p><span data-ttu-id="b0aea-147">Server back-end</span><span class="sxs-lookup"><span data-stu-id="b0aea-147">Back End Server</span></span></p></li>
<li><p><span data-ttu-id="b0aea-148">Database di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="b0aea-148">Monitoring database</span></span></p></li>
<li><p><span data-ttu-id="b0aea-149">Database di archiviazione</span><span class="sxs-lookup"><span data-stu-id="b0aea-149">Archiving database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="b0aea-150">Install-CsDatabase</span><span class="sxs-lookup"><span data-stu-id="b0aea-150">Install-CsDatabase</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0aea-151">Ripristinare il puntatore di servizi di dominio Active Directory all'archivio di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="b0aea-151">Restore the Active Directory Domain Services pointer to the Central Management store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b0aea-152">Se a un certo punto si perde il punto di connessione del servizio, è possibile eseguire di nuovo questo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b0aea-152">If you lose the service connection point at any time, you can rerun this cmdlet.</span></span>


</div></td>
<td><p><span data-ttu-id="b0aea-153">Set-CsConfigurationStoreLocation</span><span class="sxs-lookup"><span data-stu-id="b0aea-153">Set-CsConfigurationStoreLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0aea-154">Importare la topologia, i criteri e le impostazioni di configurazione nell'archivio di gestione centrale (XDS. MDF)</span><span class="sxs-lookup"><span data-stu-id="b0aea-154">Import the topology, policies, and configuration settings to the Central Management store (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="b0aea-155">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="b0aea-155">Import-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0aea-156">Pubblicare e abilitare la topologia</span><span class="sxs-lookup"><span data-stu-id="b0aea-156">Publish and enable the topology</span></span></p></td>
<td><p><span data-ttu-id="b0aea-157">Strumento di generazione topologia</span><span class="sxs-lookup"><span data-stu-id="b0aea-157">Topology Builder</span></span></p>
<p><span data-ttu-id="b0aea-158">-oppure-</span><span class="sxs-lookup"><span data-stu-id="b0aea-158">-or-</span></span></p>
<p><span data-ttu-id="b0aea-159">Publish-CsTopology e Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="b0aea-159">Publish-CsTopology and Enable-CsTopology</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0aea-160">Abilitare l'ultima topologia pubblicata</span><span class="sxs-lookup"><span data-stu-id="b0aea-160">Enable the last published topology</span></span></p></td>
<td><p><span data-ttu-id="b0aea-161">Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="b0aea-161">Enable-CsTopology</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0aea-162">Reinstallare i componenti di Lync Server</span><span class="sxs-lookup"><span data-stu-id="b0aea-162">Reinstall Lync Server components</span></span></p></td>
<td><p><span data-ttu-id="b0aea-163">Installazione di Lync Server</span><span class="sxs-lookup"><span data-stu-id="b0aea-163">Lync Server Setup</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b0aea-164">Si trova nella cartella di installazione di Lync Server o nel supporto in \setup\amd64\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="b0aea-164">Located in the Lync Server installation folder or media at \setup\amd64\Setup.exe.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0aea-165">Ripristinare i dati di Informazioni percorso (E9-1-1) (Lis.mdf)</span><span class="sxs-lookup"><span data-stu-id="b0aea-165">Restore location information (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="b0aea-166">Import-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="b0aea-166">Import-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0aea-167">Ripristinare i dati utente permanenti (rtcxds. MDF)</span><span class="sxs-lookup"><span data-stu-id="b0aea-167">Restore persistent user data (Rtcxds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="b0aea-168">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="b0aea-168">Import-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0aea-169">Ripristinare i dati di configurazione di Response Group (RgsConfig.mdf)</span><span class="sxs-lookup"><span data-stu-id="b0aea-169">Restore Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="b0aea-170">Import-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="b0aea-170">Import-CsRgsConfiguration</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b0aea-171">Se la configurazione viene ripristinata in un pool appena distribuito che non dispone di dati di Response Group nel database, è consigliabile utilizzare l'opzione – OverwriteOwner.</span><span class="sxs-lookup"><span data-stu-id="b0aea-171">If the configuration is being restored in a newly deployed pool that has no Response Group data in the database, then you should use the –OverwriteOwner option.</span></span> <span data-ttu-id="b0aea-172">Utilizzare questa opzione anche se i dati ripristinati sono presenti in un pool con lo stesso nome di dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="b0aea-172">Use this option even if the data being restored is in a pool with the same fully qualified domain name (FQDN).</span></span> <span data-ttu-id="b0aea-173">In caso contrario, l'importazione non avrà esito positivo, a causa degli oggetti contatto ai Response Group già esistenti in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b0aea-173">Otherwise, the import will not succeed, due to the contact objects to the Response Groups already existing in Active Directory.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0aea-174">Ripristinare i database seguenti:</span><span class="sxs-lookup"><span data-stu-id="b0aea-174">Restore the following databases:</span></span></p>
<ul>
<li><p><span data-ttu-id="b0aea-175">Database di archiviazione (LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="b0aea-175">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="b0aea-176">Database di monitoraggio: database di registrazione dettagli chiamata (LcsCDR.mdf) e database QoE (QoEMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="b0aea-176">Monitoring databases: call detail record database (LcsCDR.mdf) and QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="b0aea-177">Strumenti di gestione dei database di SQL Server</span><span class="sxs-lookup"><span data-stu-id="b0aea-177">SQL Server database management tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0aea-178">Database di chat persistente (MGS. MDF)</span><span class="sxs-lookup"><span data-stu-id="b0aea-178">Persistent Chat database (Mgs.mdf)</span></span></p></td>
<td><p><span data-ttu-id="b0aea-179">Procedure di ripristino di SQL Server o Import-CsPersistentChatData.</span><span class="sxs-lookup"><span data-stu-id="b0aea-179">SQL Server restore procedures or Import-CsPersistentChatData.</span></span> <span data-ttu-id="b0aea-180">È possibile utilizzare Import-CsPersistentChatData con un file creato da Export-CsPersistentChatData e i dati verranno importati nel database di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="b0aea-180">You can use Import-CsPersistentChatData with a file created by Export-CsPersistentChatData, and the data will be imported into the Persistent Chat database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a><span data-ttu-id="b0aea-181">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="b0aea-181">Required Permissions</span></span>

<span data-ttu-id="b0aea-182">Gli utenti devono essere membri del gruppo **RTCUniversalServerAdmins** per eseguire tutti i comandi descritti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b0aea-182">Users must be a member of the **RTCUniversalServerAdmins** group to perform all the commands described in this topic.</span></span> <span data-ttu-id="b0aea-183">La maggior parte dei comandi di backup e ripristino non supporta il controllo di accesso basato sui ruoli (RBAC).</span><span class="sxs-lookup"><span data-stu-id="b0aea-183">Most backup and restore commands do not support role-based access control (RBAC).</span></span> <span data-ttu-id="b0aea-184">Due eccezioni sono i cmdlet di Persistent Chat Export-CsPersistentChatData e Import-CsPersistentChatData, che devono essere eseguiti da un utente membro del gruppo ruolo CsPersistentChatAdministrator.</span><span class="sxs-lookup"><span data-stu-id="b0aea-184">Two exceptions are the Persistent Chat cmdlets Export-CsPersistentChatData and Import-CsPersistentChatData, which must be run by a user who is a member of the CsPersistentChatAdministrator group.</span></span> <span data-ttu-id="b0aea-185">Per eseguire la distribuzione guidata di Lync Server, è necessario che un utente sia anche membro del gruppo amministratori locale.</span><span class="sxs-lookup"><span data-stu-id="b0aea-185">To run Lync Server Deployment Wizard, a user must also be a member of the Local Adminstrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

