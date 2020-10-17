---
title: 'Lync Server 2013: requisiti di backup e ripristino: strumenti e autorizzazioni'
description: 'Lync Server 2013: requisiti di backup e ripristino: strumenti e autorizzazioni.'
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
ms.openlocfilehash: 36327d1214854586b44024f126bbd87acad6c4b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553468"
---
# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a><span data-ttu-id="90294-103">Requisiti di backup e ripristino in Lync Server 2013: Tools and Permissions</span><span class="sxs-lookup"><span data-stu-id="90294-103">Backup and restoration requirements in Lync Server 2013: tools and permissions</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90294-104">_**Ultimo argomento modificato:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="90294-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="90294-105">In questo argomento vengono identificati gli strumenti che è possibile utilizzare per eseguire il backup e il ripristino di Lync Server 2013, le autorizzazioni necessarie e la possibilità di eseguire comandi in remoto o localmente.</span><span class="sxs-lookup"><span data-stu-id="90294-105">This topic identifies the tools that you can use to back up and restore Lync Server 2013, the permissions that you need, and whether you can run commands remotely or locally.</span></span> <span data-ttu-id="90294-106">In particolare, questo argomento si concentra sugli strumenti forniti con Lync Server per il backup e il ripristino.</span><span class="sxs-lookup"><span data-stu-id="90294-106">Specifically, this topic focuses on tools that are provided with Lync Server for backup and restoration.</span></span>

<div>

## <a name="backups"></a><span data-ttu-id="90294-107">Backup</span><span class="sxs-lookup"><span data-stu-id="90294-107">Backups</span></span>

<span data-ttu-id="90294-108">Per eseguire il backup di Lync Server, utilizzare gli strumenti identificati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="90294-108">To back up Lync Server, use the tools identified in the following table.</span></span> <span data-ttu-id="90294-109">Tutti i comandi di cui è necessario eseguire il backup di Lync Server possono essere scritti in remoto e possono essere eseguiti in modalità remota.</span><span class="sxs-lookup"><span data-stu-id="90294-109">All the commands that you need to back up Lync Server can be scripted and can be run remotely.</span></span>

### <a name="tools-for-backing-up-lync-server"></a><span data-ttu-id="90294-110">Strumenti per il backup di Lync Server</span><span class="sxs-lookup"><span data-stu-id="90294-110">Tools for Backing Up Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90294-111">Per il backup di questo componente:</span><span class="sxs-lookup"><span data-stu-id="90294-111">To back up this:</span></span></th>
<th><span data-ttu-id="90294-112">Utilizzare questo strumento o cmdlet:</span><span class="sxs-lookup"><span data-stu-id="90294-112">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90294-113">Dati di configurazione della topologia (Xds.mdf)</span><span class="sxs-lookup"><span data-stu-id="90294-113">Topology configuration data (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="90294-114">Export-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="90294-114">Export-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90294-115">Dati del servizio Informazioni percorso (E9-1-1) (Lis.mdf)</span><span class="sxs-lookup"><span data-stu-id="90294-115">Location information service (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="90294-116">Export-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="90294-116">Export-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90294-117">Dati di configurazione di Response Group (RgsConfig.mdf)</span><span class="sxs-lookup"><span data-stu-id="90294-117">Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="90294-118">Export-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="90294-118">Export-CsRgsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90294-119">Dati utente permanenti (database rtcxds. MDF)</span><span class="sxs-lookup"><span data-stu-id="90294-119">Persistent user data (Rtcxds.mdf database)</span></span></p>
<p><span data-ttu-id="90294-120">ID conferenza</span><span class="sxs-lookup"><span data-stu-id="90294-120">Conference IDs</span></span></p></td>
<td><p><span data-ttu-id="90294-121">Export-CsUserData</span><span class="sxs-lookup"><span data-stu-id="90294-121">Export-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="90294-122">Database di archiviazione (LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="90294-122">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="90294-123">Database di registrazione dettagli chiamata di monitoraggio (LcsCDR.mdf)</span><span class="sxs-lookup"><span data-stu-id="90294-123">Monitoring call detail record database (LcsCDR.mdf)</span></span></p></li>
<li><p><span data-ttu-id="90294-124">Database QoE di monitoraggio (QoEMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="90294-124">Monitoring QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="90294-125">Strumento dei database di SQL Server, ad esempio SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="90294-125">SQL Server database tool, such as SQL Server Management Studio</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90294-126">Database di chat persistente (MGC. MDF)</span><span class="sxs-lookup"><span data-stu-id="90294-126">Persistent Chat database (Mgc.mdf)</span></span></p></td>
<td><p><span data-ttu-id="90294-127">Procedure di backup o Export-CsPersistentChatData di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="90294-127">SQL Server backup procedures or Export-CsPersistentChatData.</span></span> <span data-ttu-id="90294-128">Export-CsPersistentChatData Esporta i dati della chat persistente come file.</span><span class="sxs-lookup"><span data-stu-id="90294-128">Export-CsPersistentChatData exports Persistent Chat data as a file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90294-129">Tutti gli archivi file: archivio file di Lync Server, archivio file di archiviazione</span><span class="sxs-lookup"><span data-stu-id="90294-129">All file stores: Lync Server file store, Archiving file store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="90294-130">Non eseguire il backup dei file denominati <STRONG>Meeting.Active</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="90294-130">Files named <STRONG>Meeting.Active</STRONG> should not be backed up.</span></span> <span data-ttu-id="90294-131">Questi file sono in uso e bloccati mentre è in corso una riunione.</span><span class="sxs-lookup"><span data-stu-id="90294-131">These files are in use and locked while a meeting takes place.</span></span>


</div></td>
<td><p><span data-ttu-id="90294-132">Strumento di gestione del file System standard, ad esempio Robocopy.</span><span class="sxs-lookup"><span data-stu-id="90294-132">Standard file system management tool, such as Robocopy.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a><span data-ttu-id="90294-133">Ripristino</span><span class="sxs-lookup"><span data-stu-id="90294-133">Restoration</span></span>

<span data-ttu-id="90294-134">Per ripristinare Lync Server, utilizzare gli strumenti riportati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="90294-134">To restore Lync Server, use the tools in the following table.</span></span> <span data-ttu-id="90294-135">Tutti i comandi necessari per il ripristino di Lync Server possono essere scritti tramite script.</span><span class="sxs-lookup"><span data-stu-id="90294-135">All the commands that you need to restore Lync Server can be scripted.</span></span> <span data-ttu-id="90294-136">Alcuni possono essere eseguiti in remoto, mentre altri devono essere eseguiti localmente, come specificato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="90294-136">Some can be run remotely, but others need to be run locally, as specified in the following table.</span></span>

### <a name="tools-for-restoring-lync-server"></a><span data-ttu-id="90294-137">Strumenti per il ripristino di Lync Server</span><span class="sxs-lookup"><span data-stu-id="90294-137">Tools for Restoring Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90294-138">Per eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="90294-138">To do this:</span></span></th>
<th><span data-ttu-id="90294-139">Utilizzare questo strumento o cmdlet:</span><span class="sxs-lookup"><span data-stu-id="90294-139">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90294-140">Creare un computer nuovo o pulito</span><span class="sxs-lookup"><span data-stu-id="90294-140">Build a new or clean computer</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="90294-141">Software di installazione del sistema operativo Windows</span><span class="sxs-lookup"><span data-stu-id="90294-141">Windows operating system installation software</span></span></p></li>
<li><p><span data-ttu-id="90294-142">Software di installazione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="90294-142">SQL Server installation software</span></span></p></li>
<li><p><span data-ttu-id="90294-143">Snap-in MMC (Microsoft Management Console) Certificati, per ripristinare certificati con una chiave privata esportabile</span><span class="sxs-lookup"><span data-stu-id="90294-143">Certificates Microsoft Management Console (MMC) snap-in, if restoring certificates with an exportable private key</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90294-144">Ripristinare dati dell'archivio file</span><span class="sxs-lookup"><span data-stu-id="90294-144">Restore file store data</span></span></p></td>
<td><p><span data-ttu-id="90294-145">Strumento di gestione del file system standard, ad esempio Robocopy</span><span class="sxs-lookup"><span data-stu-id="90294-145">Standard file system management tool, such as Robocopy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90294-146">Ricreare database vuoti e impostare le autorizzazioni per gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="90294-146">Recreate empty databases and set permissions for the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="90294-147">Archivio di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="90294-147">Central Management store</span></span></p></li>
<li><p><span data-ttu-id="90294-148">Server back-end</span><span class="sxs-lookup"><span data-stu-id="90294-148">Back End Server</span></span></p></li>
<li><p><span data-ttu-id="90294-149">Database di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="90294-149">Monitoring database</span></span></p></li>
<li><p><span data-ttu-id="90294-150">Database di archiviazione</span><span class="sxs-lookup"><span data-stu-id="90294-150">Archiving database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="90294-151">Install-CsDatabase</span><span class="sxs-lookup"><span data-stu-id="90294-151">Install-CsDatabase</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90294-152">Ripristinare il puntatore di servizi di dominio Active Directory all'archivio di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="90294-152">Restore the Active Directory Domain Services pointer to the Central Management store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="90294-153">Se a un certo punto si perde il punto di connessione del servizio, è possibile eseguire di nuovo questo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="90294-153">If you lose the service connection point at any time, you can rerun this cmdlet.</span></span>


</div></td>
<td><p><span data-ttu-id="90294-154">Set-CsConfigurationStoreLocation</span><span class="sxs-lookup"><span data-stu-id="90294-154">Set-CsConfigurationStoreLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90294-155">Importare la topologia, i criteri e le impostazioni di configurazione nell'archivio di gestione centrale (XDS. MDF)</span><span class="sxs-lookup"><span data-stu-id="90294-155">Import the topology, policies, and configuration settings to the Central Management store (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="90294-156">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="90294-156">Import-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90294-157">Pubblicare e abilitare la topologia</span><span class="sxs-lookup"><span data-stu-id="90294-157">Publish and enable the topology</span></span></p></td>
<td><p><span data-ttu-id="90294-158">Strumento di generazione topologia</span><span class="sxs-lookup"><span data-stu-id="90294-158">Topology Builder</span></span></p>
<p><span data-ttu-id="90294-159">-oppure-</span><span class="sxs-lookup"><span data-stu-id="90294-159">-or-</span></span></p>
<p><span data-ttu-id="90294-160">Publish-CsTopology e Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="90294-160">Publish-CsTopology and Enable-CsTopology</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90294-161">Abilitare l'ultima topologia pubblicata</span><span class="sxs-lookup"><span data-stu-id="90294-161">Enable the last published topology</span></span></p></td>
<td><p><span data-ttu-id="90294-162">Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="90294-162">Enable-CsTopology</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90294-163">Reinstallare i componenti di Lync Server</span><span class="sxs-lookup"><span data-stu-id="90294-163">Reinstall Lync Server components</span></span></p></td>
<td><p><span data-ttu-id="90294-164">Installazione di Lync Server</span><span class="sxs-lookup"><span data-stu-id="90294-164">Lync Server Setup</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="90294-165">Si trova nella cartella di installazione di Lync Server o nel file multimediale in \setup\amd64\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="90294-165">Located in the Lync Server installation folder or media at \setup\amd64\Setup.exe.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90294-166">Ripristinare i dati di Informazioni percorso (E9-1-1) (Lis.mdf)</span><span class="sxs-lookup"><span data-stu-id="90294-166">Restore location information (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="90294-167">Import-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="90294-167">Import-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90294-168">Ripristinare i dati utente permanenti (rtcxds. MDF)</span><span class="sxs-lookup"><span data-stu-id="90294-168">Restore persistent user data (Rtcxds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="90294-169">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="90294-169">Import-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90294-170">Ripristinare i dati di configurazione di Response Group (RgsConfig.mdf)</span><span class="sxs-lookup"><span data-stu-id="90294-170">Restore Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="90294-171">Import-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="90294-171">Import-CsRgsConfiguration</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="90294-172">Se la configurazione viene ripristinata in un pool appena distribuito che non dispone di dati di Response Group nel database, è consigliabile utilizzare l'opzione – OverwriteOwner.</span><span class="sxs-lookup"><span data-stu-id="90294-172">If the configuration is being restored in a newly deployed pool that has no Response Group data in the database, then you should use the –OverwriteOwner option.</span></span> <span data-ttu-id="90294-173">Utilizzare questa opzione anche se i dati ripristinati sono presenti in un pool con lo stesso nome di dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="90294-173">Use this option even if the data being restored is in a pool with the same fully qualified domain name (FQDN).</span></span> <span data-ttu-id="90294-174">In caso contrario, l'importazione non avrà esito positivo, a causa degli oggetti contatto ai Response Group già esistenti in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="90294-174">Otherwise, the import will not succeed, due to the contact objects to the Response Groups already existing in Active Directory.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90294-175">Ripristinare i database seguenti:</span><span class="sxs-lookup"><span data-stu-id="90294-175">Restore the following databases:</span></span></p>
<ul>
<li><p><span data-ttu-id="90294-176">Database di archiviazione (LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="90294-176">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="90294-177">Database di monitoraggio: database di registrazione dettagli chiamata (LcsCDR.mdf) e database QoE (QoEMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="90294-177">Monitoring databases: call detail record database (LcsCDR.mdf) and QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="90294-178">Strumenti di gestione dei database di SQL Server</span><span class="sxs-lookup"><span data-stu-id="90294-178">SQL Server database management tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90294-179">Database di chat persistente (MGS. MDF)</span><span class="sxs-lookup"><span data-stu-id="90294-179">Persistent Chat database (Mgs.mdf)</span></span></p></td>
<td><p><span data-ttu-id="90294-180">Procedure di ripristino di SQL Server o Import-CsPersistentChatData.</span><span class="sxs-lookup"><span data-stu-id="90294-180">SQL Server restore procedures or Import-CsPersistentChatData.</span></span> <span data-ttu-id="90294-181">È possibile utilizzare Import-CsPersistentChatData con un file creato da Export-CsPersistentChatData e i dati verranno importati nel database di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="90294-181">You can use Import-CsPersistentChatData with a file created by Export-CsPersistentChatData, and the data will be imported into the Persistent Chat database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a><span data-ttu-id="90294-182">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="90294-182">Required Permissions</span></span>

<span data-ttu-id="90294-183">Gli utenti devono essere membri del gruppo **RTCUniversalServerAdmins** per eseguire tutti i comandi descritti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="90294-183">Users must be a member of the **RTCUniversalServerAdmins** group to perform all the commands described in this topic.</span></span> <span data-ttu-id="90294-184">La maggior parte dei comandi di backup e ripristino non supporta il controllo di accesso basato sui ruoli (RBAC).</span><span class="sxs-lookup"><span data-stu-id="90294-184">Most backup and restore commands do not support role-based access control (RBAC).</span></span> <span data-ttu-id="90294-185">Due eccezioni sono i cmdlet di Persistent Chat Export-CsPersistentChatData e Import-CsPersistentChatData, che devono essere eseguiti da un utente membro del gruppo ruolo CsPersistentChatAdministrator.</span><span class="sxs-lookup"><span data-stu-id="90294-185">Two exceptions are the Persistent Chat cmdlets Export-CsPersistentChatData and Import-CsPersistentChatData, which must be run by a user who is a member of the CsPersistentChatAdministrator group.</span></span> <span data-ttu-id="90294-186">Per eseguire la distribuzione guidata di Lync Server, è necessario che un utente sia anche membro del gruppo amministratori locale.</span><span class="sxs-lookup"><span data-stu-id="90294-186">To run Lync Server Deployment Wizard, a user must also be a member of the Local Adminstrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

