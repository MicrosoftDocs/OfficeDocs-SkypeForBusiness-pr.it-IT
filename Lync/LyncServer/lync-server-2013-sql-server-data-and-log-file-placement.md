---
title: 'Lync Server 2013: Posizionamento dei file di log e dei file di dati di SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SQL Server data and log file placement
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48184395
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 197141ea62307631eab206fce5403d25b4d89583
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764442"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a><span data-ttu-id="7a848-102">Posizionamento dei file di log e dei file di dati di SQL Server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a848-102">SQL Server data and log file placement for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a848-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="7a848-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="7a848-104">Durante la pianificazione e la distribuzione di Microsoft SQL Server 2012 o Microsoft SQL Server 2008 R2 SP1 per il pool di front end di Lync Server 2013, è importante considerare la posizione dei dati e i file di log sui dischi rigidi fisici per le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="7a848-104">During the planning and deployment of Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2 SP1 for your Lync Server 2013 Front End pool, an important consideration is the placement of data and log files onto physical hard disks for performance.</span></span> <span data-ttu-id="7a848-105">La configurazione del disco consigliata consiste nell'implementare un set RAID da 1 + 0 con 6 fusi.</span><span class="sxs-lookup"><span data-stu-id="7a848-105">The recommended disk configuration is to implement a 1+0 RAID set using 6 spindles.</span></span> <span data-ttu-id="7a848-106">Posizionare tutti i file di database e di log usati dal pool Front-end e i ruoli e i servizi del server associato, ovvero l'archiviazione e il server di monitoraggio, il servizio di Response Group di Lync Server, il servizio di parcheggio di Lync Server, nel set di unità RAID tramite Lync Server La distribuzione guidata comporterà una configurazione che è stata testata per una buona prestazione.</span><span class="sxs-lookup"><span data-stu-id="7a848-106">Placing all database and log files that are used by the Front End pool and associated server roles and services (that is, Archiving and Monitoring Server, Lync Server Response Group service, Lync Server Call Park service) onto the RAID drive set using the Lync Server Deployment Wizard will result in a configuration that has been tested for good performance.</span></span> <span data-ttu-id="7a848-107">I file di database e i relativi responsabili sono dettagliati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7a848-107">The database files and what they are responsible for is detailed in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a848-108">Se i criteri e le configurazioni di SQL Server richiedono un'installazione più specializzata, il database e i file di log possono essere installati in qualsiasi posizione predefinita tramite Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7a848-108">If your policies and SQL Server configurations require a more specialized installation, the database and log files can be installed to any pre-defined location using the Lync Server Management Shell.</span></span> <span data-ttu-id="7a848-109">Per altre informazioni, vedere <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">installazione di database tramite Lync Server Management Shell in Lync server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="7a848-109">See <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Database installation using Lync Server Management Shell in Lync Server 2013</A> for more details.</span></span>



</div>

### <a name="data-and-log-files-for-central-management-store"></a><span data-ttu-id="7a848-110">File di dati e di log per Central Management store</span><span class="sxs-lookup"><span data-stu-id="7a848-110">Data and Log Files for Central Management Store</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7a848-111">File di database di Central Management store</span><span class="sxs-lookup"><span data-stu-id="7a848-111">Central Management store database files</span></span></th>
<th><span data-ttu-id="7a848-112">Scopo del file di dati o del log</span><span class="sxs-lookup"><span data-stu-id="7a848-112">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7a848-113">XDS. ldf</span><span class="sxs-lookup"><span data-stu-id="7a848-113">Xds.ldf</span></span></p></td>
<td><p><span data-ttu-id="7a848-114">File di log delle transazioni per l'archivio di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="7a848-114">Transaction log file for the Central Management store</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a848-115">XDS. MDF</span><span class="sxs-lookup"><span data-stu-id="7a848-115">Xds.mdf</span></span></p></td>
<td><p><span data-ttu-id="7a848-116">Gestisce la configurazione della topologia di Lync Server 2013 corrente, come definita e pubblicata da generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="7a848-116">Maintains the configuration of the current Lync Server 2013 topology, as defined and published by Topology Builder</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a848-117">LIS. MDF</span><span class="sxs-lookup"><span data-stu-id="7a848-117">Lis.mdf</span></span></p></td>
<td><p><span data-ttu-id="7a848-118">File di dati del servizio informazioni sulla posizione</span><span class="sxs-lookup"><span data-stu-id="7a848-118">Location Information service data file</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a848-119">LIS. ldf</span><span class="sxs-lookup"><span data-stu-id="7a848-119">Lis.ldf</span></span></p></td>
<td><p><span data-ttu-id="7a848-120">Log delle transazioni per il file di dati del servizio informazioni sulla posizione</span><span class="sxs-lookup"><span data-stu-id="7a848-120">Transaction log for the Location Information service data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a><span data-ttu-id="7a848-121">File di dati e di log per gli utenti, i servizi di conferenza e la Rubrica</span><span class="sxs-lookup"><span data-stu-id="7a848-121">Data and Log files for User, Conferencing, and Address Book</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7a848-122">File di database di base di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a848-122">Core Lync Server 2013 database files</span></span></th>
<th><span data-ttu-id="7a848-123">Scopo del file di dati o del log</span><span class="sxs-lookup"><span data-stu-id="7a848-123">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7a848-124">RTC. MDF</span><span class="sxs-lookup"><span data-stu-id="7a848-124">Rtc.mdf</span></span></p></td>
<td><p><span data-ttu-id="7a848-125">Dati utente permanenti (ad esempio, elenchi di controllo di accesso (ACL), contatti, conferenze pianificate)</span><span class="sxs-lookup"><span data-stu-id="7a848-125">Persistent user data (for example, access control lists (ACLs), contacts, scheduled conferences)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a848-126">RTC. ldf</span><span class="sxs-lookup"><span data-stu-id="7a848-126">Rtc.ldf</span></span></p></td>
<td><p><span data-ttu-id="7a848-127">Log delle transazioni per i dati RTC</span><span class="sxs-lookup"><span data-stu-id="7a848-127">Transaction log for Rtc data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a848-128">RTCDyn. MDF</span><span class="sxs-lookup"><span data-stu-id="7a848-128">Rtcdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="7a848-129">Gestisce i dati utente temporanei (dati di runtime di presenza)</span><span class="sxs-lookup"><span data-stu-id="7a848-129">Maintains transient user data (presence runtime data)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a848-130">RTCDyn. ldf</span><span class="sxs-lookup"><span data-stu-id="7a848-130">Rtcdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="7a848-131">Log delle transazioni per i dati di RTCDyn</span><span class="sxs-lookup"><span data-stu-id="7a848-131">Transaction log for Rtcdyn data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a848-132">Rtcab. MDF</span><span class="sxs-lookup"><span data-stu-id="7a848-132">Rtcab.mdf</span></span></p></td>
<td><p><span data-ttu-id="7a848-133">Il database della Rubrica di comunicazioni in tempo reale (RTC) è il repository di SQL Server in cui sono archiviate le informazioni sul servizio Rubrica</span><span class="sxs-lookup"><span data-stu-id="7a848-133">Real-time communications (RTC) address book database is the SQL Server repository where Address Book service information is stored</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a848-134">Rtcab. ldf</span><span class="sxs-lookup"><span data-stu-id="7a848-134">Rtcab.ldf</span></span></p></td>
<td><p><span data-ttu-id="7a848-135">Log delle transazioni per il servizio Rubrica</span><span class="sxs-lookup"><span data-stu-id="7a848-135">Transaction log for Address Book Service</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a848-136">RTCLocal. mdb</span><span class="sxs-lookup"><span data-stu-id="7a848-136">Rtclocal.mdb</span></span></p></td>
<td><p><span data-ttu-id="7a848-137">Ospita la directory conferenza</span><span class="sxs-lookup"><span data-stu-id="7a848-137">Hosts the conference directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a848-138">Rtcxds. MDF</span><span class="sxs-lookup"><span data-stu-id="7a848-138">Rtcxds.mdf</span></span></p></td>
<td><p><span data-ttu-id="7a848-139">Mantiene il backup dei dati degli utenti</span><span class="sxs-lookup"><span data-stu-id="7a848-139">Maintains the backup for user data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a848-140">Rtcxds. ldf</span><span class="sxs-lookup"><span data-stu-id="7a848-140">Rtcxds.ldf</span></span></p></td>
<td><p><span data-ttu-id="7a848-141">Log delle transazioni per i dati di rtcxds</span><span class="sxs-lookup"><span data-stu-id="7a848-141">Transaction log for Rtcxds data</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a><span data-ttu-id="7a848-142">File di dati e di log per il gruppo di chiamate e Response Park</span><span class="sxs-lookup"><span data-stu-id="7a848-142">Data and Log Files for Call Park and Response Group</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7a848-143">Database dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="7a848-143">Application database</span></span></th>
<th><span data-ttu-id="7a848-144">Scopo del file di dati o del log</span><span class="sxs-lookup"><span data-stu-id="7a848-144">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7a848-145">Cpsdyn. MDF</span><span class="sxs-lookup"><span data-stu-id="7a848-145">Cpsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="7a848-146">Database di informazioni dinamiche per l'applicazione Call Park</span><span class="sxs-lookup"><span data-stu-id="7a848-146">Dynamic information database for the Call Park application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a848-147">Cpsdyn. ldf</span><span class="sxs-lookup"><span data-stu-id="7a848-147">Cpsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="7a848-148">Log delle transazioni per il file di dati dell'applicazione Call Park</span><span class="sxs-lookup"><span data-stu-id="7a848-148">Transaction log for Call Park application data file</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a848-149">Rgsconfig. MDF</span><span class="sxs-lookup"><span data-stu-id="7a848-149">Rgsconfig.mdf</span></span></p></td>
<td><p><span data-ttu-id="7a848-150">File di dati del servizio Response Group di Lync Server per la configurazione dei servizi</span><span class="sxs-lookup"><span data-stu-id="7a848-150">Lync Server Response Group service data file for the configuration of the services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a848-151">Rgsconfig. ldf</span><span class="sxs-lookup"><span data-stu-id="7a848-151">Rgsconfig.ldf</span></span></p></td>
<td><p><span data-ttu-id="7a848-152">File di log delle transazioni per la configurazione dell'Response Group Application</span><span class="sxs-lookup"><span data-stu-id="7a848-152">Transaction log file for the Response Group application configuration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a848-153">Rgsdyn. MDF</span><span class="sxs-lookup"><span data-stu-id="7a848-153">Rgsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="7a848-154">File di dati del servizio Response Group per le operazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="7a848-154">Response Group service data file for runtime operations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a848-155">Rgsdyn. ldf</span><span class="sxs-lookup"><span data-stu-id="7a848-155">Rgsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="7a848-156">Log delle transazioni per il file di dati runtime del servizio Response Group</span><span class="sxs-lookup"><span data-stu-id="7a848-156">Transaction log for the Response Group service runtime data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a><span data-ttu-id="7a848-157">File di dati e log per l'archiviazione e il monitoraggio del server</span><span class="sxs-lookup"><span data-stu-id="7a848-157">Data and Log Files for Archiving and Monitoring Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7a848-158">Archiviazione e monitoraggio dei file di database</span><span class="sxs-lookup"><span data-stu-id="7a848-158">Archiving and Monitoring database files</span></span></th>
<th><span data-ttu-id="7a848-159">Scopo del file di dati o del log</span><span class="sxs-lookup"><span data-stu-id="7a848-159">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7a848-160">LcsCdr. MDF</span><span class="sxs-lookup"><span data-stu-id="7a848-160">LcsCdr.mdf</span></span></p></td>
<td><p><span data-ttu-id="7a848-161">Archivio dati per il processo di registrazione dei dettagli delle chiamate (CDR) del server di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="7a848-161">Data store for the call detail recording (CDR) process of the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a848-162">LcsCdr. ldf</span><span class="sxs-lookup"><span data-stu-id="7a848-162">LcsCdr.ldf</span></span></p></td>
<td><p><span data-ttu-id="7a848-163">Log delle transazioni per i dati di registrazione dei dettagli delle chiamate (CDR)</span><span class="sxs-lookup"><span data-stu-id="7a848-163">Transaction log for call detail recording (CDR) data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a848-164">QoEMetrics. MDF</span><span class="sxs-lookup"><span data-stu-id="7a848-164">QoEMetrics.mdf</span></span></p></td>
<td><p><span data-ttu-id="7a848-165">File di dati di qualità dell'esperienza archiviato nel server di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="7a848-165">Quality of Experience data file stored from the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a848-166">QoEMetrics. ldf</span><span class="sxs-lookup"><span data-stu-id="7a848-166">QoEMetrics.ldf</span></span></p></td>
<td><p><span data-ttu-id="7a848-167">Log delle transazioni per il monitoraggio dei dati</span><span class="sxs-lookup"><span data-stu-id="7a848-167">Transaction log for Monitoring data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a848-168">LcsLog. MDF</span><span class="sxs-lookup"><span data-stu-id="7a848-168">Lcslog.mdf</span></span></p></td>
<td><p><span data-ttu-id="7a848-169">File di dati per il mantenimento dei dati di messaggistica istantanea e di conferenza in un server di archiviazione</span><span class="sxs-lookup"><span data-stu-id="7a848-169">Data file for the retention of instant messaging and conferencing data on an Archiving Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a848-170">LcsLog. ldf</span><span class="sxs-lookup"><span data-stu-id="7a848-170">Lcslog.ldf</span></span></p></td>
<td><p><span data-ttu-id="7a848-171">Log delle transazioni per l'archiviazione dei dati</span><span class="sxs-lookup"><span data-stu-id="7a848-171">Transaction log for Archiving data</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7a848-172">In questo argomento vengono eseguiti i riferimenti al disco e al set RAID.</span><span class="sxs-lookup"><span data-stu-id="7a848-172">In this topic, references are made to disk and to RAID set.</span></span> <span data-ttu-id="7a848-173">Tieni presente che nella configurazione delle risorse di SQL Server il riferimento a un disco indica un singolo dispositivo hardware.</span><span class="sxs-lookup"><span data-stu-id="7a848-173">Note that in the configuration of SQL Server resources, referring to a disk means a single hardware device.</span></span> <span data-ttu-id="7a848-174">Un'unità disco rigido con due partizioni, una che tiene i file di log e gli altri file di dati della partizione, non è uguale a due dischi, ognuno dedicato ai file di log o di dati.</span><span class="sxs-lookup"><span data-stu-id="7a848-174">A hard disk drive with two partitions, one holding log files and the other partition holding data files, is not the same as two disks, each dedicated to either log or data files.</span></span>

<span data-ttu-id="7a848-175">In riferimento a set di RAID è disponibile una serie di tecnologie RAID diverse da diversi fornitori.</span><span class="sxs-lookup"><span data-stu-id="7a848-175">In reference to RAID sets, there are a number of different RAID technologies from various vendors.</span></span> <span data-ttu-id="7a848-176">E, con la proliferazione delle reti di archiviazione (SAN), i set RAID dedicati a un singolo sistema sono più rari.</span><span class="sxs-lookup"><span data-stu-id="7a848-176">And, with the proliferation of storage area networks (SAN), RAID sets dedicated to a single system are rarer.</span></span> <span data-ttu-id="7a848-177">Per determinare qual è la configurazione migliore per il layout del disco durante la configurazione delle prestazioni di SQL Server con Lync Server 2013, è consigliabile consultarsi con il proprio fornitore RAID o SAN.</span><span class="sxs-lookup"><span data-stu-id="7a848-177">You should consult with your RAID or SAN vendor to determine what the best configuration is for your disk layout when configuring for SQL Server performance with Lync Server 2013.</span></span>

<span data-ttu-id="7a848-178">Si noti inoltre che non tutte le unità disco vengono create equamente; alcune prestazioni sono migliori di altre.</span><span class="sxs-lookup"><span data-stu-id="7a848-178">Note also that not all disk drives are created equally; some perform better than others.</span></span> <span data-ttu-id="7a848-179">Anche le unità dello stesso produttore possono variare in base alle prestazioni a causa della velocità di rotazione, della dimensione della cache hardware e di altri fattori.</span><span class="sxs-lookup"><span data-stu-id="7a848-179">Even drives from the same manufacturer can vary in performance because of rotational speed, hardware cache size, and other factors.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

