---
title: 'Lync Server 2013: disposizione dei file di registro e di dati di SQL Server'
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
ms.openlocfilehash: 3f536f2d67010856259abf6b98936cd9e096fc93
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509623"
---
# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a><span data-ttu-id="a84e2-102">Disposizione dei file di registro e di dati di SQL Server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a84e2-102">SQL Server data and log file placement for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a84e2-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="a84e2-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="a84e2-104">Durante la pianificazione e la distribuzione di Microsoft SQL Server 2012 o Microsoft SQL Server 2008 R2 SP1 per il pool Front End di Lync Server 2013, è importante considerare la disposizione dei file di dati e di registro su dischi rigidi fisici per le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="a84e2-104">During the planning and deployment of Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2 SP1 for your Lync Server 2013 Front End pool, an important consideration is the placement of data and log files onto physical hard disks for performance.</span></span> <span data-ttu-id="a84e2-105">La configurazione del disco consigliata consiste nell'implementazione di un set RAID 1 + 0 con 6 mandrini.</span><span class="sxs-lookup"><span data-stu-id="a84e2-105">The recommended disk configuration is to implement a 1+0 RAID set using 6 spindles.</span></span> <span data-ttu-id="a84e2-106">Se si inseriscono tutti i file di database e di registro utilizzati dal pool Front end e i ruoli del server e i servizi associati (ovvero archiviazione e Monitoring Server, Lync Server Response Group Service, Lync Server Call Park Service) sul set di unità RAID tramite la distribuzione guidata di Lync Server, si verificherà una configurazione che è stata testata per una buona prestazione.</span><span class="sxs-lookup"><span data-stu-id="a84e2-106">Placing all database and log files that are used by the Front End pool and associated server roles and services (that is, Archiving and Monitoring Server, Lync Server Response Group service, Lync Server Call Park service) onto the RAID drive set using the Lync Server Deployment Wizard will result in a configuration that has been tested for good performance.</span></span> <span data-ttu-id="a84e2-107">I file di database e la relativa funzione vengono spiegati in dettaglio nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="a84e2-107">The database files and what they are responsible for is detailed in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a84e2-108">Se i criteri e le configurazioni di SQL Server richiedono un'installazione più specializzata, è possibile installare il database e i file di registro in qualsiasi percorso predefinito utilizzando Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a84e2-108">If your policies and SQL Server configurations require a more specialized installation, the database and log files can be installed to any pre-defined location using the Lync Server Management Shell.</span></span> <span data-ttu-id="a84e2-109">Per ulteriori informazioni, vedere <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">installazione di database mediante Lync Server Management Shell in Lync server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="a84e2-109">See <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Database installation using Lync Server Management Shell in Lync Server 2013</A> for more details.</span></span>



</div>

### <a name="data-and-log-files-for-central-management-store"></a><span data-ttu-id="a84e2-110">File di dati e di registro per l'archivio di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="a84e2-110">Data and Log Files for Central Management Store</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a84e2-111">File di database dell'archivio di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="a84e2-111">Central Management store database files</span></span></th>
<th><span data-ttu-id="a84e2-112">Scopi del file di dati o del registro</span><span class="sxs-lookup"><span data-stu-id="a84e2-112">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a84e2-113">XDS. ldf</span><span class="sxs-lookup"><span data-stu-id="a84e2-113">Xds.ldf</span></span></p></td>
<td><p><span data-ttu-id="a84e2-114">File di registro delle transazioni per l'archivio di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="a84e2-114">Transaction log file for the Central Management store</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a84e2-115">XDS. MDF</span><span class="sxs-lookup"><span data-stu-id="a84e2-115">Xds.mdf</span></span></p></td>
<td><p><span data-ttu-id="a84e2-116">Gestisce la configurazione della topologia di Lync Server 2013 corrente, come definito e pubblicato da generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="a84e2-116">Maintains the configuration of the current Lync Server 2013 topology, as defined and published by Topology Builder</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a84e2-117">LIS. MDF</span><span class="sxs-lookup"><span data-stu-id="a84e2-117">Lis.mdf</span></span></p></td>
<td><p><span data-ttu-id="a84e2-118">File di dati del servizio informazioni percorso</span><span class="sxs-lookup"><span data-stu-id="a84e2-118">Location Information service data file</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a84e2-119">LIS. ldf</span><span class="sxs-lookup"><span data-stu-id="a84e2-119">Lis.ldf</span></span></p></td>
<td><p><span data-ttu-id="a84e2-120">Log delle transazioni per il file di dati del servizio informazioni percorso</span><span class="sxs-lookup"><span data-stu-id="a84e2-120">Transaction log for the Location Information service data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a><span data-ttu-id="a84e2-121">File di dati e di registro per utenti, conferenze e Rubrica</span><span class="sxs-lookup"><span data-stu-id="a84e2-121">Data and Log files for User, Conferencing, and Address Book</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a84e2-122">File di database di base di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a84e2-122">Core Lync Server 2013 database files</span></span></th>
<th><span data-ttu-id="a84e2-123">Scopi del file di dati o del registro</span><span class="sxs-lookup"><span data-stu-id="a84e2-123">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a84e2-124">RTC. MDF</span><span class="sxs-lookup"><span data-stu-id="a84e2-124">Rtc.mdf</span></span></p></td>
<td><p><span data-ttu-id="a84e2-125">Dati utente permanenti (ad esempio, elenchi di controllo di accesso (ACL, Access Control List), contatti, conferenze pianificate</span><span class="sxs-lookup"><span data-stu-id="a84e2-125">Persistent user data (for example, access control lists (ACLs), contacts, scheduled conferences)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a84e2-126">RTC. ldf</span><span class="sxs-lookup"><span data-stu-id="a84e2-126">Rtc.ldf</span></span></p></td>
<td><p><span data-ttu-id="a84e2-127">Log delle transazioni per i dati RTC</span><span class="sxs-lookup"><span data-stu-id="a84e2-127">Transaction log for Rtc data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a84e2-128">RTCDyn. MDF</span><span class="sxs-lookup"><span data-stu-id="a84e2-128">Rtcdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="a84e2-129">Mantiene i dati utente temporanei (dati di runtime di presenza)</span><span class="sxs-lookup"><span data-stu-id="a84e2-129">Maintains transient user data (presence runtime data)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a84e2-130">RTCDyn. ldf</span><span class="sxs-lookup"><span data-stu-id="a84e2-130">Rtcdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="a84e2-131">Log delle transazioni per i dati di RTCDyn</span><span class="sxs-lookup"><span data-stu-id="a84e2-131">Transaction log for Rtcdyn data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a84e2-132">Rtcab. MDF</span><span class="sxs-lookup"><span data-stu-id="a84e2-132">Rtcab.mdf</span></span></p></td>
<td><p><span data-ttu-id="a84e2-133">Il database della rubrica per la comunicazione in tempo reale è l'archivio di SQL Server in cui sono memorizzate le informazioni per il servizio Rubrica</span><span class="sxs-lookup"><span data-stu-id="a84e2-133">Real-time communications (RTC) address book database is the SQL Server repository where Address Book service information is stored</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a84e2-134">Rtcab. ldf</span><span class="sxs-lookup"><span data-stu-id="a84e2-134">Rtcab.ldf</span></span></p></td>
<td><p><span data-ttu-id="a84e2-135">Registro delle transazioni per il servizio Rubrica</span><span class="sxs-lookup"><span data-stu-id="a84e2-135">Transaction log for Address Book Service</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a84e2-136">RTCLocal. mdb</span><span class="sxs-lookup"><span data-stu-id="a84e2-136">Rtclocal.mdb</span></span></p></td>
<td><p><span data-ttu-id="a84e2-137">Ospita la directory conferenze</span><span class="sxs-lookup"><span data-stu-id="a84e2-137">Hosts the conference directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a84e2-138">Rtcxds. MDF</span><span class="sxs-lookup"><span data-stu-id="a84e2-138">Rtcxds.mdf</span></span></p></td>
<td><p><span data-ttu-id="a84e2-139">Gestisce il backup per i dati utente</span><span class="sxs-lookup"><span data-stu-id="a84e2-139">Maintains the backup for user data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a84e2-140">Rtcxds. ldf</span><span class="sxs-lookup"><span data-stu-id="a84e2-140">Rtcxds.ldf</span></span></p></td>
<td><p><span data-ttu-id="a84e2-141">Log delle transazioni per i dati di rtcxds</span><span class="sxs-lookup"><span data-stu-id="a84e2-141">Transaction log for Rtcxds data</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a><span data-ttu-id="a84e2-142">File di dati e di registro per Parcheggio di chiamata e Response Group</span><span class="sxs-lookup"><span data-stu-id="a84e2-142">Data and Log Files for Call Park and Response Group</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a84e2-143">Database dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="a84e2-143">Application database</span></span></th>
<th><span data-ttu-id="a84e2-144">Scopi del file di dati o del registro</span><span class="sxs-lookup"><span data-stu-id="a84e2-144">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a84e2-145">Cpsdyn. MDF</span><span class="sxs-lookup"><span data-stu-id="a84e2-145">Cpsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="a84e2-146">Database delle informazioni dinamiche per l'applicazione Parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="a84e2-146">Dynamic information database for the Call Park application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a84e2-147">Cpsdyn. ldf</span><span class="sxs-lookup"><span data-stu-id="a84e2-147">Cpsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="a84e2-148">Log delle transazioni per il file di dati dell'applicazione Parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="a84e2-148">Transaction log for Call Park application data file</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a84e2-149">Rgsconfig. MDF</span><span class="sxs-lookup"><span data-stu-id="a84e2-149">Rgsconfig.mdf</span></span></p></td>
<td><p><span data-ttu-id="a84e2-150">File di dati del servizio Response Group di Lync Server per la configurazione dei servizi</span><span class="sxs-lookup"><span data-stu-id="a84e2-150">Lync Server Response Group service data file for the configuration of the services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a84e2-151">Rgsconfig. ldf</span><span class="sxs-lookup"><span data-stu-id="a84e2-151">Rgsconfig.ldf</span></span></p></td>
<td><p><span data-ttu-id="a84e2-152">File di registro delle transazioni per la configurazione dell'applicazione Response Group</span><span class="sxs-lookup"><span data-stu-id="a84e2-152">Transaction log file for the Response Group application configuration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a84e2-153">Rgsdyn. MDF</span><span class="sxs-lookup"><span data-stu-id="a84e2-153">Rgsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="a84e2-154">File di dati del servizio Response Group per le operazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="a84e2-154">Response Group service data file for runtime operations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a84e2-155">Rgsdyn. ldf</span><span class="sxs-lookup"><span data-stu-id="a84e2-155">Rgsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="a84e2-156">Registro delle transazioni per il file di dati del runtime del servizio Response Group</span><span class="sxs-lookup"><span data-stu-id="a84e2-156">Transaction log for the Response Group service runtime data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a><span data-ttu-id="a84e2-157">File di dati e di registro per il server di archiviazione e Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="a84e2-157">Data and Log Files for Archiving and Monitoring Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a84e2-158">File dei database di archiviazione e monitoraggio</span><span class="sxs-lookup"><span data-stu-id="a84e2-158">Archiving and Monitoring database files</span></span></th>
<th><span data-ttu-id="a84e2-159">Scopi del file di dati o del registro</span><span class="sxs-lookup"><span data-stu-id="a84e2-159">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a84e2-160">LcsCdr. MDF</span><span class="sxs-lookup"><span data-stu-id="a84e2-160">LcsCdr.mdf</span></span></p></td>
<td><p><span data-ttu-id="a84e2-161">Archivio dati per il processo di registrazione dettagli chiamata (CDR) del Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="a84e2-161">Data store for the call detail recording (CDR) process of the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a84e2-162">LcsCdr. ldf</span><span class="sxs-lookup"><span data-stu-id="a84e2-162">LcsCdr.ldf</span></span></p></td>
<td><p><span data-ttu-id="a84e2-163">Registro delle transazioni per i dati di registrazione dettagli chiamata</span><span class="sxs-lookup"><span data-stu-id="a84e2-163">Transaction log for call detail recording (CDR) data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a84e2-164">QoEMetrics. MDF</span><span class="sxs-lookup"><span data-stu-id="a84e2-164">QoEMetrics.mdf</span></span></p></td>
<td><p><span data-ttu-id="a84e2-165">File di dati di qualità di esperienza memorizzato dal Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="a84e2-165">Quality of Experience data file stored from the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a84e2-166">QoEMetrics. ldf</span><span class="sxs-lookup"><span data-stu-id="a84e2-166">QoEMetrics.ldf</span></span></p></td>
<td><p><span data-ttu-id="a84e2-167">Registro delle transazioni per i dati di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="a84e2-167">Transaction log for Monitoring data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a84e2-168">LcsLog. MDF</span><span class="sxs-lookup"><span data-stu-id="a84e2-168">Lcslog.mdf</span></span></p></td>
<td><p><span data-ttu-id="a84e2-169">File di dati per la conservazione dei dati di messaggistica istantanea e delle conferenze in un server di archiviazione</span><span class="sxs-lookup"><span data-stu-id="a84e2-169">Data file for the retention of instant messaging and conferencing data on an Archiving Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a84e2-170">LcsLog. ldf</span><span class="sxs-lookup"><span data-stu-id="a84e2-170">Lcslog.ldf</span></span></p></td>
<td><p><span data-ttu-id="a84e2-171">Registro delle transazioni per l'archiviazione dei dati</span><span class="sxs-lookup"><span data-stu-id="a84e2-171">Transaction log for Archiving data</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a84e2-p103">In questo argomento si fa riferimento a set di dischi e RAID. Si noti che per la configurazione delle risorse di SQL Server, i riferimenti a un disco indicano un singolo dispositivo hardware. Un'unità disco rigido con due partizioni, una per i file di registro e l'altra per i file di dati, non equivale a due dischi ognuno dedicato ai file di registro o ai file di dati.</span><span class="sxs-lookup"><span data-stu-id="a84e2-p103">In this topic, references are made to disk and to RAID set. Note that in the configuration of SQL Server resources, referring to a disk means a single hardware device. A hard disk drive with two partitions, one holding log files and the other partition holding data files, is not the same as two disks, each dedicated to either log or data files.</span></span>

<span data-ttu-id="a84e2-175">Per quanto riguarda i set RAID, esistono numerose tecnologie RAID diverse da vari fornitori.</span><span class="sxs-lookup"><span data-stu-id="a84e2-175">In reference to RAID sets, there are a number of different RAID technologies from various vendors.</span></span> <span data-ttu-id="a84e2-176">Con la proliferazione delle reti SAN (Storage Area Network), inoltre, i set RAID dedicati a un singolo sistema sono più rari.</span><span class="sxs-lookup"><span data-stu-id="a84e2-176">And, with the proliferation of storage area networks (SAN), RAID sets dedicated to a single system are rarer.</span></span> <span data-ttu-id="a84e2-177">È consigliabile consultare il fornitore RAID o SAN per determinare quale sia la configurazione migliore per il layout del disco durante la configurazione delle prestazioni di SQL Server con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a84e2-177">You should consult with your RAID or SAN vendor to determine what the best configuration is for your disk layout when configuring for SQL Server performance with Lync Server 2013.</span></span>

<span data-ttu-id="a84e2-178">Si noti inoltre che non tutte le unità disco vengono create in modo uguale e alcune offrono prestazioni migliori di altre.</span><span class="sxs-lookup"><span data-stu-id="a84e2-178">Note also that not all disk drives are created equally; some perform better than others.</span></span> <span data-ttu-id="a84e2-179">Anche unità dello stesso produttore possono offrire prestazioni variabili a seconda di velocità di rotazione, dimensioni della cache hardware e altri fattori.</span><span class="sxs-lookup"><span data-stu-id="a84e2-179">Even drives from the same manufacturer can vary in performance because of rotational speed, hardware cache size, and other factors.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

