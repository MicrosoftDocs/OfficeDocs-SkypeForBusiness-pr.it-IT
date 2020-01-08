---
title: 'Lync Server 2013: requisiti di backup e ripristino: strumenti e autorizzazioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Backup and restoration requirements: tools and permissions'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202171(v=OCS.15)
ms:contentKeyID: 51541465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53128d99abfd438c174b98544889781b5f29b57b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979812"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a><span data-ttu-id="67967-102">Requisiti di backup e ripristino in Lync Server 2013: strumenti e autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="67967-102">Backup and restoration requirements in Lync Server 2013: tools and permissions</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67967-103">_**Argomento Ultima modifica:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="67967-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="67967-104">Questo argomento identifica gli strumenti che è possibile usare per eseguire il backup e il ripristino di Lync Server 2013, le autorizzazioni necessarie e se è possibile eseguire comandi in remoto o localmente.</span><span class="sxs-lookup"><span data-stu-id="67967-104">This topic identifies the tools that you can use to back up and restore Lync Server 2013, the permissions that you need, and whether you can run commands remotely or locally.</span></span> <span data-ttu-id="67967-105">In particolare, questo argomento si basa sugli strumenti forniti con Lync Server per il backup e il ripristino.</span><span class="sxs-lookup"><span data-stu-id="67967-105">Specifically, this topic focuses on tools that are provided with Lync Server for backup and restoration.</span></span>

<div>

## <a name="backups"></a><span data-ttu-id="67967-106">Backup</span><span class="sxs-lookup"><span data-stu-id="67967-106">Backups</span></span>

<span data-ttu-id="67967-107">Per eseguire il backup di Lync Server, usare gli strumenti identificati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="67967-107">To back up Lync Server, use the tools identified in the following table.</span></span> <span data-ttu-id="67967-108">Tutti i comandi necessari per eseguire il backup di Lync Server possono essere creati tramite script e possono essere eseguiti in remoto.</span><span class="sxs-lookup"><span data-stu-id="67967-108">All the commands that you need to back up Lync Server can be scripted and can be run remotely.</span></span>

### <a name="tools-for-backing-up-lync-server"></a><span data-ttu-id="67967-109">Strumenti per il backup di Lync Server</span><span class="sxs-lookup"><span data-stu-id="67967-109">Tools for Backing Up Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67967-110">Per eseguire il backup:</span><span class="sxs-lookup"><span data-stu-id="67967-110">To back up this:</span></span></th>
<th><span data-ttu-id="67967-111">Usare questo strumento o cmdlet:</span><span class="sxs-lookup"><span data-stu-id="67967-111">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67967-112">Dati di configurazione della topologia (XDS. MDF)</span><span class="sxs-lookup"><span data-stu-id="67967-112">Topology configuration data (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="67967-113">Export-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="67967-113">Export-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67967-114">Dati del servizio informazioni sulla posizione (E9-1-1) (LIS. MDF)</span><span class="sxs-lookup"><span data-stu-id="67967-114">Location information service (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="67967-115">Export-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="67967-115">Export-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67967-116">Dati di configurazione dei gruppi di risposte (RgsConfig. MDF)</span><span class="sxs-lookup"><span data-stu-id="67967-116">Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="67967-117">Export-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="67967-117">Export-CsRgsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67967-118">Dati utente permanenti (database rtcxds. MDF)</span><span class="sxs-lookup"><span data-stu-id="67967-118">Persistent user data (Rtcxds.mdf database)</span></span></p>
<p><span data-ttu-id="67967-119">ID conferenza</span><span class="sxs-lookup"><span data-stu-id="67967-119">Conference IDs</span></span></p></td>
<td><p><span data-ttu-id="67967-120">Export-CsUserData</span><span class="sxs-lookup"><span data-stu-id="67967-120">Export-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="67967-121">Database di archiviazione (LcsLog. MDF)</span><span class="sxs-lookup"><span data-stu-id="67967-121">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="67967-122">Monitoraggio del database di record dettagli chiamata (LcsCDR. MDF)</span><span class="sxs-lookup"><span data-stu-id="67967-122">Monitoring call detail record database (LcsCDR.mdf)</span></span></p></li>
<li><p><span data-ttu-id="67967-123">Monitoraggio del database QoE (QoEMetrics. MDF)</span><span class="sxs-lookup"><span data-stu-id="67967-123">Monitoring QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="67967-124">Strumento database di SQL Server, ad esempio SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="67967-124">SQL Server database tool, such as SQL Server Management Studio</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67967-125">Database di chat persistente (MGC. MDF)</span><span class="sxs-lookup"><span data-stu-id="67967-125">Persistent Chat database (Mgc.mdf)</span></span></p></td>
<td><p><span data-ttu-id="67967-126">Procedure di backup di SQL Server o Export-CsPersistentChatData.</span><span class="sxs-lookup"><span data-stu-id="67967-126">SQL Server backup procedures or Export-CsPersistentChatData.</span></span> <span data-ttu-id="67967-127">Export-CsPersistentChatData Esporta i dati della chat persistente come file.</span><span class="sxs-lookup"><span data-stu-id="67967-127">Export-CsPersistentChatData exports Persistent Chat data as a file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67967-128">Tutti gli archivi di file: Lync Server file Store, archiviazione file Store</span><span class="sxs-lookup"><span data-stu-id="67967-128">All file stores: Lync Server file store, Archiving file store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="67967-129">Non è necessario eseguire il backup dei file denominati <STRONG>meeting. Active</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="67967-129">Files named <STRONG>Meeting.Active</STRONG> should not be backed up.</span></span> <span data-ttu-id="67967-130">Questi file sono in uso e bloccati durante una riunione.</span><span class="sxs-lookup"><span data-stu-id="67967-130">These files are in use and locked while a meeting takes place.</span></span>


</div></td>
<td><p><span data-ttu-id="67967-131">Strumento di gestione del file System standard, ad esempio Robocopy.</span><span class="sxs-lookup"><span data-stu-id="67967-131">Standard file system management tool, such as Robocopy.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a><span data-ttu-id="67967-132">Restauro</span><span class="sxs-lookup"><span data-stu-id="67967-132">Restoration</span></span>

<span data-ttu-id="67967-133">Per ripristinare Lync Server, usare gli strumenti della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="67967-133">To restore Lync Server, use the tools in the following table.</span></span> <span data-ttu-id="67967-134">Tutti i comandi necessari per ripristinare Lync Server possono essere creati tramite script.</span><span class="sxs-lookup"><span data-stu-id="67967-134">All the commands that you need to restore Lync Server can be scripted.</span></span> <span data-ttu-id="67967-135">Alcune possono essere eseguite in remoto, ma altre devono essere eseguite localmente, come specificato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="67967-135">Some can be run remotely, but others need to be run locally, as specified in the following table.</span></span>

### <a name="tools-for-restoring-lync-server"></a><span data-ttu-id="67967-136">Strumenti per il ripristino di Lync Server</span><span class="sxs-lookup"><span data-stu-id="67967-136">Tools for Restoring Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67967-137">Procedi come segue.</span><span class="sxs-lookup"><span data-stu-id="67967-137">To do this:</span></span></th>
<th><span data-ttu-id="67967-138">Usare questo strumento o cmdlet:</span><span class="sxs-lookup"><span data-stu-id="67967-138">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67967-139">Creare un computer nuovo o pulito</span><span class="sxs-lookup"><span data-stu-id="67967-139">Build a new or clean computer</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="67967-140">Software di installazione del sistema operativo Windows</span><span class="sxs-lookup"><span data-stu-id="67967-140">Windows operating system installation software</span></span></p></li>
<li><p><span data-ttu-id="67967-141">Software di installazione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="67967-141">SQL Server installation software</span></span></p></li>
<li><p><span data-ttu-id="67967-142">Snap-in certificati di Microsoft Management Console (MMC), se il ripristino di certificati con una chiave privata esportabile</span><span class="sxs-lookup"><span data-stu-id="67967-142">Certificates Microsoft Management Console (MMC) snap-in, if restoring certificates with an exportable private key</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67967-143">Ripristinare i dati dell'archivio file</span><span class="sxs-lookup"><span data-stu-id="67967-143">Restore file store data</span></span></p></td>
<td><p><span data-ttu-id="67967-144">Strumento di gestione del file System standard, ad esempio Robocopy</span><span class="sxs-lookup"><span data-stu-id="67967-144">Standard file system management tool, such as Robocopy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67967-145">Ricreare database vuoti e impostare le autorizzazioni per gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="67967-145">Recreate empty databases and set permissions for the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="67967-146">Central Management store</span><span class="sxs-lookup"><span data-stu-id="67967-146">Central Management store</span></span></p></li>
<li><p><span data-ttu-id="67967-147">Server back-end</span><span class="sxs-lookup"><span data-stu-id="67967-147">Back End Server</span></span></p></li>
<li><p><span data-ttu-id="67967-148">Database di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="67967-148">Monitoring database</span></span></p></li>
<li><p><span data-ttu-id="67967-149">Database di archiviazione</span><span class="sxs-lookup"><span data-stu-id="67967-149">Archiving database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="67967-150">Install-CsDatabase</span><span class="sxs-lookup"><span data-stu-id="67967-150">Install-CsDatabase</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67967-151">Ripristinare il puntatore di servizi di dominio Active Directory a Central Management store</span><span class="sxs-lookup"><span data-stu-id="67967-151">Restore the Active Directory Domain Services pointer to the Central Management store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="67967-152">Se si perde il punto di connessione del servizio in qualsiasi momento, è possibile rieseguire questo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="67967-152">If you lose the service connection point at any time, you can rerun this cmdlet.</span></span>


</div></td>
<td><p><span data-ttu-id="67967-153">Set-CsConfigurationStoreLocation</span><span class="sxs-lookup"><span data-stu-id="67967-153">Set-CsConfigurationStoreLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67967-154">Importare la topologia, i criteri e le impostazioni di configurazione in Central Management store (XDS. MDF)</span><span class="sxs-lookup"><span data-stu-id="67967-154">Import the topology, policies, and configuration settings to the Central Management store (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="67967-155">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="67967-155">Import-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67967-156">Pubblicare e abilitare la topologia</span><span class="sxs-lookup"><span data-stu-id="67967-156">Publish and enable the topology</span></span></p></td>
<td><p><span data-ttu-id="67967-157">Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="67967-157">Topology Builder</span></span></p>
<p><span data-ttu-id="67967-158">o</span><span class="sxs-lookup"><span data-stu-id="67967-158">-or-</span></span></p>
<p><span data-ttu-id="67967-159">Publish-CsTopology e Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="67967-159">Publish-CsTopology and Enable-CsTopology</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67967-160">Abilitare l'ultima topologia pubblicata</span><span class="sxs-lookup"><span data-stu-id="67967-160">Enable the last published topology</span></span></p></td>
<td><p><span data-ttu-id="67967-161">Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="67967-161">Enable-CsTopology</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67967-162">Reinstallare i componenti di Lync Server</span><span class="sxs-lookup"><span data-stu-id="67967-162">Reinstall Lync Server components</span></span></p></td>
<td><p><span data-ttu-id="67967-163">Configurazione di Lync Server</span><span class="sxs-lookup"><span data-stu-id="67967-163">Lync Server Setup</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="67967-164">Disponibile nella cartella di installazione di Lync Server o in un file multimediale in \setup\amd64\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="67967-164">Located in the Lync Server installation folder or media at \setup\amd64\Setup.exe.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67967-165">Ripristinare le informazioni sulla posizione (E9-1-1) dati (LIS. MDF)</span><span class="sxs-lookup"><span data-stu-id="67967-165">Restore location information (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="67967-166">Import-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="67967-166">Import-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67967-167">Ripristinare i dati utente permanenti (rtcxds. MDF)</span><span class="sxs-lookup"><span data-stu-id="67967-167">Restore persistent user data (Rtcxds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="67967-168">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="67967-168">Import-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67967-169">Ripristinare i dati di configurazione di Response Group (RgsConfig. MDF)</span><span class="sxs-lookup"><span data-stu-id="67967-169">Restore Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="67967-170">Import-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="67967-170">Import-CsRgsConfiguration</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="67967-171">Se la configurazione viene ripristinata in un pool appena distribuito che non contiene dati del gruppo di risposte nel database, è necessario usare l'opzione – OverwriteOwner.</span><span class="sxs-lookup"><span data-stu-id="67967-171">If the configuration is being restored in a newly deployed pool that has no Response Group data in the database, then you should use the –OverwriteOwner option.</span></span> <span data-ttu-id="67967-172">Usare questa opzione anche se i dati da ripristinare si trova in un pool con lo stesso nome di dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="67967-172">Use this option even if the data being restored is in a pool with the same fully qualified domain name (FQDN).</span></span> <span data-ttu-id="67967-173">In caso contrario, l'importazione non avrà esito positivo, a causa degli oggetti contatto per i gruppi di risposte già esistenti in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="67967-173">Otherwise, the import will not succeed, due to the contact objects to the Response Groups already existing in Active Directory.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67967-174">Ripristinare i database seguenti:</span><span class="sxs-lookup"><span data-stu-id="67967-174">Restore the following databases:</span></span></p>
<ul>
<li><p><span data-ttu-id="67967-175">Database di archiviazione (LcsLog. MDF)</span><span class="sxs-lookup"><span data-stu-id="67967-175">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="67967-176">Database di monitoraggio: database di record dettagli chiamata (LcsCDR. MDF) e database QoE (QoEMetrics. MDF)</span><span class="sxs-lookup"><span data-stu-id="67967-176">Monitoring databases: call detail record database (LcsCDR.mdf) and QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="67967-177">Strumenti di gestione di database di SQL Server</span><span class="sxs-lookup"><span data-stu-id="67967-177">SQL Server database management tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67967-178">Database di chat persistente (MGS. MDF)</span><span class="sxs-lookup"><span data-stu-id="67967-178">Persistent Chat database (Mgs.mdf)</span></span></p></td>
<td><p><span data-ttu-id="67967-179">Procedure di ripristino di SQL Server o Import-CsPersistentChatData.</span><span class="sxs-lookup"><span data-stu-id="67967-179">SQL Server restore procedures or Import-CsPersistentChatData.</span></span> <span data-ttu-id="67967-180">È possibile usare Import-CsPersistentChatData con un file creato da Export-CsPersistentChatData e i dati verranno importati nel database della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="67967-180">You can use Import-CsPersistentChatData with a file created by Export-CsPersistentChatData, and the data will be imported into the Persistent Chat database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a><span data-ttu-id="67967-181">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="67967-181">Required Permissions</span></span>

<span data-ttu-id="67967-182">Gli utenti devono essere membri del gruppo **RTCUniversalServerAdmins** per eseguire tutti i comandi descritti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="67967-182">Users must be a member of the **RTCUniversalServerAdmins** group to perform all the commands described in this topic.</span></span> <span data-ttu-id="67967-183">La maggior parte dei comandi di backup e ripristino non supporta il controllo di accesso basato sui ruoli (RBAC).</span><span class="sxs-lookup"><span data-stu-id="67967-183">Most backup and restore commands do not support role-based access control (RBAC).</span></span> <span data-ttu-id="67967-184">Due eccezioni sono i cmdlet per la chat persistente Export-CsPersistentChatData e Import-CsPersistentChatData, che devono essere eseguiti da un utente membro del gruppo CsPersistentChatAdministrator.</span><span class="sxs-lookup"><span data-stu-id="67967-184">Two exceptions are the Persistent Chat cmdlets Export-CsPersistentChatData and Import-CsPersistentChatData, which must be run by a user who is a member of the CsPersistentChatAdministrator group.</span></span> <span data-ttu-id="67967-185">Per eseguire la distribuzione guidata di Lync Server, un utente deve essere anche membro del gruppo di amministratori locale.</span><span class="sxs-lookup"><span data-stu-id="67967-185">To run Lync Server Deployment Wizard, a user must also be a member of the Local Adminstrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

