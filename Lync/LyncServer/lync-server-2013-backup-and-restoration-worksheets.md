---
title: 'Lync Server 2013: fogli di lavoro di backup e ripristino'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration worksheets
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202169(v=OCS.15)
ms:contentKeyID: 51541460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 390d6289daf8075c873e90319642f0e74b61d835
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a><span data-ttu-id="cdcf7-102">Fogli di lavoro di backup e ripristino per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdcf7-102">Backup and restoration worksheets for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cdcf7-103">_**Argomento Ultima modifica:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="cdcf7-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="cdcf7-104">Il piano di backup e ripristino per l'organizzazione deve contenere informazioni dettagliate su come e quando eseguire il backup di dati e impostazioni.</span><span class="sxs-lookup"><span data-stu-id="cdcf7-104">The backup and restoration plan for your organization should contain details about how and when you back up data and settings.</span></span> <span data-ttu-id="cdcf7-105">È possibile usare i fogli di lavoro presentati in questo articolo per documentare queste informazioni per la distribuzione specifica e per i requisiti di backup e ripristino dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cdcf7-105">You can use the worksheets presented here to help you document this information for your specific deployment and for your organization's backup and restoration requirements.</span></span>

<span data-ttu-id="cdcf7-106">Usare i fogli di lavoro seguenti per registrare le informazioni necessarie per eseguire il backup e il ripristino di database, archivio file e informazioni sulle impostazioni per un pool di Lync Server o un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="cdcf7-106">Use the following worksheets to record the information that you need to back up and restore database, File Store, and settings information for a Lync Server pool or Standard Edition server.</span></span> <span data-ttu-id="cdcf7-107">Conservare una o più copie di questi fogli di lavoro in una posizione sicura in modo che siano facilmente accessibili se è necessario ripristinare Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cdcf7-107">Keep one or more copies of these worksheets in a secure location so that they are readily accessible if you need to restore Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cdcf7-108">I fogli di lavoro in questa sezione coprono solo le informazioni necessarie per ripristinare i dati e le impostazioni dei database e server di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cdcf7-108">The worksheets in this section cover only the information that is required to restore the data and settings of Lync Server databases and servers.</span></span> <span data-ttu-id="cdcf7-109">Se è necessario documentare altre informazioni di ripristino, ad esempio le informazioni per la reinstallazione di sistemi operativi e altro software, usare i piani di distribuzione dell'organizzazione e i piani di backup e ripristino per rispondere a tali requisiti.</span><span class="sxs-lookup"><span data-stu-id="cdcf7-109">If you need to document other restoration information, such as the information for reinstalling operating systems and other software, use your organization's deployment plans and backup and restoration plans to address those requirements.</span></span>



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a><span data-ttu-id="cdcf7-110">Foglio di lavoro backup e ripristino di database</span><span class="sxs-lookup"><span data-stu-id="cdcf7-110">Database Backup and Restoration Worksheet</span></span>

<span data-ttu-id="cdcf7-111">Usare la tabella seguente per registrare le informazioni necessarie per eseguire il backup e ripristinare i database di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cdcf7-111">Use the following table to record the information that you need to back up and restore Lync Server databases.</span></span>

### <a name="database-information-for-backup-and-restoration"></a><span data-ttu-id="cdcf7-112">Informazioni sul database per il backup e il ripristino</span><span class="sxs-lookup"><span data-stu-id="cdcf7-112">Database Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cdcf7-113">Database</span><span class="sxs-lookup"><span data-stu-id="cdcf7-113">Database</span></span></th>
<th><span data-ttu-id="cdcf7-114">Nome server (FQDN)</span><span class="sxs-lookup"><span data-stu-id="cdcf7-114">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="cdcf7-115">Pianificazione del backup</span><span class="sxs-lookup"><span data-stu-id="cdcf7-115">Backup schedule</span></span></th>
<th><span data-ttu-id="cdcf7-116">Strumento di backup del database</span><span class="sxs-lookup"><span data-stu-id="cdcf7-116">Database backup tool</span></span></th>
<th><span data-ttu-id="cdcf7-117">Set di backup</span><span class="sxs-lookup"><span data-stu-id="cdcf7-117">Backup set</span></span></th>
<th><span data-ttu-id="cdcf7-118">Destinazione di backup</span><span class="sxs-lookup"><span data-stu-id="cdcf7-118">Backup destination</span></span></th>
<th><span data-ttu-id="cdcf7-119">Note</span><span class="sxs-lookup"><span data-stu-id="cdcf7-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cdcf7-120">Database RTC sul server back-end per i dati utente</span><span class="sxs-lookup"><span data-stu-id="cdcf7-120">Rtc database on Back End Server for user data</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="cdcf7-121">Cmdlet <strong>Export-CsUserData</strong></span><span class="sxs-lookup"><span data-stu-id="cdcf7-121"><strong>Export-CsUserData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="cdcf7-122">Nome</span><span class="sxs-lookup"><span data-stu-id="cdcf7-122">Name:</span></span></p>
<p><span data-ttu-id="cdcf7-123">Scadenza</span><span class="sxs-lookup"><span data-stu-id="cdcf7-123">Expiration:</span></span></p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdcf7-124">Database di LcsLog (nome predefinito) in archiviazione del server di database</span><span class="sxs-lookup"><span data-stu-id="cdcf7-124">LcsLog (default name) database on Archiving database server</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cdcf7-125">Strumento di gestione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="cdcf7-125">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="cdcf7-126">Nome</span><span class="sxs-lookup"><span data-stu-id="cdcf7-126">Name:</span></span></p>
<p><span data-ttu-id="cdcf7-127">Scadenza</span><span class="sxs-lookup"><span data-stu-id="cdcf7-127">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdcf7-128">Database di LcsCdr per il monitoraggio del server di database per record dettagli chiamata (CDRs)</span><span class="sxs-lookup"><span data-stu-id="cdcf7-128">LcsCdr database on Monitoring database server for call detail records (CDRs)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cdcf7-129">Strumento di gestione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="cdcf7-129">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="cdcf7-130">Nome</span><span class="sxs-lookup"><span data-stu-id="cdcf7-130">Name:</span></span></p>
<p><span data-ttu-id="cdcf7-131">Scadenza</span><span class="sxs-lookup"><span data-stu-id="cdcf7-131">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdcf7-132">Database di QoEMetrics sul server di database di monitoraggio per i dati di qualità dell'esperienza (QoE)</span><span class="sxs-lookup"><span data-stu-id="cdcf7-132">QoEMetrics database on Monitoring database server for Quality of Experience (QoE) data</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cdcf7-133">Strumento di gestione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="cdcf7-133">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="cdcf7-134">Nome</span><span class="sxs-lookup"><span data-stu-id="cdcf7-134">Name:</span></span></p>
<p><span data-ttu-id="cdcf7-135">Scadenza</span><span class="sxs-lookup"><span data-stu-id="cdcf7-135">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdcf7-136">Database di chat persistente</span><span class="sxs-lookup"><span data-stu-id="cdcf7-136">Persistent Chat Database</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="cdcf7-137">Strumento di gestione di SQL Server o cmdlet <strong>Export-CsPersistentChatData</strong></span><span class="sxs-lookup"><span data-stu-id="cdcf7-137">SQL Server management tool or <strong>Export-CsPersistentChatData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="cdcf7-138">Nome</span><span class="sxs-lookup"><span data-stu-id="cdcf7-138">Name:</span></span></p>
<p><span data-ttu-id="cdcf7-139">Scadenza</span><span class="sxs-lookup"><span data-stu-id="cdcf7-139">Expiration:</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cdcf7-140">Non è necessario alcun backup o ripristino dei database seguenti:</span><span class="sxs-lookup"><span data-stu-id="cdcf7-140">No backup or restoration is required of the following databases:</span></span>

  - <span data-ttu-id="cdcf7-141">RTCDyn.</span><span class="sxs-lookup"><span data-stu-id="cdcf7-141">Rtcdyn.</span></span> <span data-ttu-id="cdcf7-142">I dati utente temporanei in questo database non sono necessari per il ripristino del servizio.</span><span class="sxs-lookup"><span data-stu-id="cdcf7-142">The transient user data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="cdcf7-143">RTCAb.</span><span class="sxs-lookup"><span data-stu-id="cdcf7-143">Rtcab.</span></span> <span data-ttu-id="cdcf7-144">Il database della Rubrica viene ricreato automaticamente dall'elenco indirizzi globale (GAL) in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cdcf7-144">The Address Book database is automatically recreated from the Global Address List (GAL) in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="cdcf7-145">Rgsdyn.</span><span class="sxs-lookup"><span data-stu-id="cdcf7-145">Rgsdyn.</span></span> <span data-ttu-id="cdcf7-146">I dati del servizio Response Group temporaneo in questo database non sono necessari per il ripristino del servizio.</span><span class="sxs-lookup"><span data-stu-id="cdcf7-146">The transient Response Group service data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="cdcf7-147">Cpsdyn.</span><span class="sxs-lookup"><span data-stu-id="cdcf7-147">Cpsdyn.</span></span> <span data-ttu-id="cdcf7-148">Le informazioni dinamiche per l'applicazione per il parcheggio delle chiamate non sono necessarie per il ripristino del servizio.</span><span class="sxs-lookup"><span data-stu-id="cdcf7-148">The dynamic information for the Call Park application is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="cdcf7-149">MgcComp.</span><span class="sxs-lookup"><span data-stu-id="cdcf7-149">MgcComp.</span></span> <span data-ttu-id="cdcf7-150">Il database di conformità per la chat persistente non è necessario per il ripristino del servizio.</span><span class="sxs-lookup"><span data-stu-id="cdcf7-150">The compliance database for Persistent Chat is not necessary for restoration of service.</span></span>

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a><span data-ttu-id="cdcf7-151">Foglio di lavoro backup e ripristino del file Store</span><span class="sxs-lookup"><span data-stu-id="cdcf7-151">File Store Backup and Restoration Worksheet</span></span>

<span data-ttu-id="cdcf7-152">Usare la tabella seguente per registrare le informazioni necessarie per eseguire il backup e ripristinare gli archivi di file.</span><span class="sxs-lookup"><span data-stu-id="cdcf7-152">Use the following table to record the information that you need to back up and restore the File Stores.</span></span> <span data-ttu-id="cdcf7-153">Gli archivi di file contengono dati, ad esempio i metadati del contenuto della riunione, i registri di conformità delle riunioni, i registri di aggiornamento per gli aggiornamenti dei dispositivi e i file audio per il Response Group, il parcheggio delle chiamate e le applicazioni</span><span class="sxs-lookup"><span data-stu-id="cdcf7-153">File Stores contain data such as meeting content metadata, meeting compliance logs, update logs for device updates, and audio files for the Response Group, Call Park, and Announcement applications.</span></span>

### <a name="file-store-information-for-backup-and-restoration"></a><span data-ttu-id="cdcf7-154">Informazioni sull'archiviazione dei file per il backup e il ripristino</span><span class="sxs-lookup"><span data-stu-id="cdcf7-154">File Store Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cdcf7-155">Contenuto</span><span class="sxs-lookup"><span data-stu-id="cdcf7-155">Content</span></span></th>
<th><span data-ttu-id="cdcf7-156">Nome server (FQDN)</span><span class="sxs-lookup"><span data-stu-id="cdcf7-156">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="cdcf7-157">Pianificazione del backup</span><span class="sxs-lookup"><span data-stu-id="cdcf7-157">Backup schedule</span></span></th>
<th><span data-ttu-id="cdcf7-158">Strumento backup file System</span><span class="sxs-lookup"><span data-stu-id="cdcf7-158">File system backup tool</span></span></th>
<th><span data-ttu-id="cdcf7-159">Condivisione file di cui eseguire il backup \*</span><span class="sxs-lookup"><span data-stu-id="cdcf7-159">File share to be backed up \*</span></span></th>
<th><span data-ttu-id="cdcf7-160">Destinazione di backup</span><span class="sxs-lookup"><span data-stu-id="cdcf7-160">Backup destination</span></span></th>
<th><span data-ttu-id="cdcf7-161">Note</span><span class="sxs-lookup"><span data-stu-id="cdcf7-161">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cdcf7-162">Archivio file di Lync Server</span><span class="sxs-lookup"><span data-stu-id="cdcf7-162">Lync Server File Store</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="cdcf7-163">Strumento di backup standard, ad esempio Robocopy</span><span class="sxs-lookup"><span data-stu-id="cdcf7-163">Standard backup tool, such as Robocopy</span></span></p></td>
<td><p><span data-ttu-id="cdcf7-164">In file server per Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="cdcf7-164">On file server for Enterprise Edition.</span></span> <span data-ttu-id="cdcf7-165">In Standard Edition per impostazione predefinita, per la distribuzione di Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="cdcf7-165">On Standard Edition by default, for Standard Edition deployment.</span></span> <span data-ttu-id="cdcf7-166">In genere, una per ogni sito.</span><span class="sxs-lookup"><span data-stu-id="cdcf7-166">Typically, one per site.</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cdcf7-167">Non è necessario eseguire il backup dei file denominati <strong>meeting. Active</strong> .</span><span class="sxs-lookup"><span data-stu-id="cdcf7-167">Files named <strong>Meeting.Active</strong> should not be backed up.</span></span> <span data-ttu-id="cdcf7-168">Questi file sono in uso e sono bloccati durante una riunione.</span><span class="sxs-lookup"><span data-stu-id="cdcf7-168">These files are in use and are locked while a meeting takes place.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a><span data-ttu-id="cdcf7-169">Foglio di lavoro backup e ripristino delle impostazioni</span><span class="sxs-lookup"><span data-stu-id="cdcf7-169">Settings Backup and Restoration Worksheet</span></span>

<span data-ttu-id="cdcf7-170">Usare la tabella seguente per registrare le informazioni necessarie per eseguire il backup e il ripristino delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="cdcf7-170">Use the following table to record the information that you need to back up and restore settings.</span></span>

### <a name="settings-information-for-backup-and-restoration"></a><span data-ttu-id="cdcf7-171">Informazioni sulle impostazioni per il backup e il ripristino</span><span class="sxs-lookup"><span data-stu-id="cdcf7-171">Settings Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cdcf7-172">Database</span><span class="sxs-lookup"><span data-stu-id="cdcf7-172">Database</span></span></th>
<th><span data-ttu-id="cdcf7-173">Nome server (FQDN)</span><span class="sxs-lookup"><span data-stu-id="cdcf7-173">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="cdcf7-174">Pianificazione del backup</span><span class="sxs-lookup"><span data-stu-id="cdcf7-174">Backup schedule</span></span></th>
<th><span data-ttu-id="cdcf7-175">Strumento di backup</span><span class="sxs-lookup"><span data-stu-id="cdcf7-175">Backup tool</span></span></th>
<th><span data-ttu-id="cdcf7-176">Nome file di configurazione (con estensione XML)</span><span class="sxs-lookup"><span data-stu-id="cdcf7-176">Configuration file (.xml) name</span></span></th>
<th><span data-ttu-id="cdcf7-177">Percorso di backup</span><span class="sxs-lookup"><span data-stu-id="cdcf7-177">Backup location</span></span></th>
<th><span data-ttu-id="cdcf7-178">Note</span><span class="sxs-lookup"><span data-stu-id="cdcf7-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cdcf7-179">Database XDS in Central Management store per la configurazione della topologia (globale)</span><span class="sxs-lookup"><span data-stu-id="cdcf7-179">Xds database in Central Management store for topology configuration (global)</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="cdcf7-180">Cmdlet <strong>Export-CsConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="cdcf7-180"><strong>Export-CsConfiguration</strong> cmdlet</span></span></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdcf7-181">Database LIS in Central Management store per le informazioni sulla posizione di E9-1-1 (globale)</span><span class="sxs-lookup"><span data-stu-id="cdcf7-181">Lis database in Central Management store for E9-1-1 location information (global)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cdcf7-182">Cmdlet <strong>Export-CsLisConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="cdcf7-182"><strong>Export-CsLisConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdcf7-183">Database di RgsConfig nel server back-end per la configurazione del gruppo di risposte (pool)</span><span class="sxs-lookup"><span data-stu-id="cdcf7-183">RgsConfig database on Back End Server for Response Group configuration (pool)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cdcf7-184">Cmdlet <strong>Export-CsRgsConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="cdcf7-184"><strong>Export-CsRgsConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

