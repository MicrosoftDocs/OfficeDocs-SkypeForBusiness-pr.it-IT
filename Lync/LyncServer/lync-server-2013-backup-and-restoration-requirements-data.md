---
title: 'Lync Server 2013: requisiti di backup e ripristino: dati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: data'
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202194(v=OCS.15)
ms:contentKeyID: 51541526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8431e16e976f0ad189205f0c42c04d50e6936e90
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527043"
---
# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a><span data-ttu-id="34ce5-102">Requisiti di backup e ripristino in Lync Server 2013: data</span><span class="sxs-lookup"><span data-stu-id="34ce5-102">Backup and restoration requirements in Lync Server 2013: data</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34ce5-103">_**Ultimo argomento modificato:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="34ce5-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="34ce5-104">Lync Server utilizza le impostazioni e le informazioni di configurazione archiviate nei database e i dati archiviati nei database e nei file archiviati.</span><span class="sxs-lookup"><span data-stu-id="34ce5-104">Lync Server uses settings and configuration information that are stored in databases, and data that is stored in databases and file stores.</span></span> <span data-ttu-id="34ce5-105">In questo argomento vengono descritti i dati di cui è necessario eseguire il backup per poter ripristinare il servizio se l'organizzazione avverte un errore o un'interruzione e identifica anche i dati e i componenti utilizzati da Lync Server di cui è necessario eseguire il backup separatamente.</span><span class="sxs-lookup"><span data-stu-id="34ce5-105">This topic describes the data that you need to back up to be able to restore service if your organization experiences a failure or outage, and also identifies the data and components used by Lync Server that you need to back up separately.</span></span>

<div>

## <a name="settings-and-configuration-requirements"></a><span data-ttu-id="34ce5-106">Requisiti di impostazioni e dati di configurazione</span><span class="sxs-lookup"><span data-stu-id="34ce5-106">Settings and Configuration Requirements</span></span>

<span data-ttu-id="34ce5-107">In questo argomento sono incluse le procedure per il backup e il ripristino delle impostazioni e delle informazioni di configurazione necessarie per il ripristino del servizio Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34ce5-107">This topic includes procedures for backing up and restoring the settings and configuration information that is required for recovery of Lync Server service.</span></span> <span data-ttu-id="34ce5-108">Le informazioni di configurazione si trovano nell'archivio di gestione centrale o in un altro database back-end o nel server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="34ce5-108">The configuration information is located in the Central Management store or on another back-end database or on Standard Edition server.</span></span>

<span data-ttu-id="34ce5-109">Nella tabella seguente vengono identificate le impostazioni e le informazioni di configurazione necessarie per eseguire il backup e il ripristino.</span><span class="sxs-lookup"><span data-stu-id="34ce5-109">The following table identifies the settings and configuration information that you need to back up and restore.</span></span>

### <a name="settings-and-configuration-data"></a><span data-ttu-id="34ce5-110">Impostazioni e dati di configurazione</span><span class="sxs-lookup"><span data-stu-id="34ce5-110">Settings and Configuration Data</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34ce5-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="34ce5-111">Type of data</span></span></th>
<th><span data-ttu-id="34ce5-112">Dove sono archiviati</span><span class="sxs-lookup"><span data-stu-id="34ce5-112">Where stored</span></span></th>
<th><span data-ttu-id="34ce5-113">Descrizione/Quando eseguire il backup</span><span class="sxs-lookup"><span data-stu-id="34ce5-113">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34ce5-114">Informazioni di configurazione della topologia</span><span class="sxs-lookup"><span data-stu-id="34ce5-114">Topology configuration information</span></span></p></td>
<td><p><span data-ttu-id="34ce5-115">Archivio di gestione centrale (database: XDS. MDF)</span><span class="sxs-lookup"><span data-stu-id="34ce5-115">Central Management store (database: Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="34ce5-116">Impostazioni relative a topologia, criteri e configurazione.</span><span class="sxs-lookup"><span data-stu-id="34ce5-116">Topology, policy, and configuration settings.</span></span></p>
<p><span data-ttu-id="34ce5-117">Eseguire il backup con i controlli regolari e dopo aver utilizzato il pannello di controllo di Lync Server o i cmdlet per modificare la configurazione o i criteri.</span><span class="sxs-lookup"><span data-stu-id="34ce5-117">Back up with your regular backups and after you use Lync Server Control Panel or cmdlets to modify your configuration or policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34ce5-118">Informazioni sulle posizioni</span><span class="sxs-lookup"><span data-stu-id="34ce5-118">Location information</span></span></p></td>
<td><p><span data-ttu-id="34ce5-119">Archivio di gestione centrale (database: LIS. MDF)</span><span class="sxs-lookup"><span data-stu-id="34ce5-119">Central Management store (database: Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="34ce5-p103">Informazioni sulla configurazione del servizio Enhanced 9-1-1 (E9-1-1) di VoIP aziendale. Queste informazioni sono in genere statiche.</span><span class="sxs-lookup"><span data-stu-id="34ce5-p103">Enterprise Voice Enhanced 9-1-1 (E9-1-1) configuration information. This information is generally static.</span></span></p>
<p><span data-ttu-id="34ce5-122">Eseguire il backup in occasione dei backup regolari.</span><span class="sxs-lookup"><span data-stu-id="34ce5-122">Back up with your regular backups.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34ce5-123">Informazioni di configurazione di Response Group</span><span class="sxs-lookup"><span data-stu-id="34ce5-123">Response Group configuration information</span></span></p></td>
<td><p><span data-ttu-id="34ce5-124">Server back-end server o Standard Edition (database: RgsConfig. MDF)</span><span class="sxs-lookup"><span data-stu-id="34ce5-124">Back End Server or Standard Edition server (database: RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="34ce5-125">Gruppi di agenti, code e flussi di lavoro di Response Group.</span><span class="sxs-lookup"><span data-stu-id="34ce5-125">Response Group agent groups, queues, and workflows.</span></span></p>
<p><span data-ttu-id="34ce5-126">Eseguire il backup in occasione dei backup regolari e dopo aver aggiunto o modificato gruppi di agenti, code o flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="34ce5-126">Back up with your regular backups and after you add or change agent groups, queues, or workflows.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a><span data-ttu-id="34ce5-127">Requisiti dei dati</span><span class="sxs-lookup"><span data-stu-id="34ce5-127">Data Requirements</span></span>

<span data-ttu-id="34ce5-128">Di seguito è indicato un elenco dei dati di Lync Server di cui è necessario eseguire il backup in modo che sia possibile ripristinare il servizio Lync Server in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="34ce5-128">Here is a list of the Lync Server data that you need to back up so that you can restore Lync Server service in the event of a failure.</span></span>

<span data-ttu-id="34ce5-129">Tenere presente che alcuni tipi di dati non sono necessari per il ripristino.</span><span class="sxs-lookup"><span data-stu-id="34ce5-129">Note that some types of data are not required for recovery.</span></span> <span data-ttu-id="34ce5-130">Questo argomento non contiene le procedure per eseguire il backup di questi tipi di dati, inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="34ce5-130">This topic does not contain procedures for backing up these types of data, which include the following:</span></span>

  - <span data-ttu-id="34ce5-131">Dati utente temporanei, ad esempio endpoint e sottoscrizioni, server per conferenze attivi e stati di conferenza transitori (database: RtcDyn.mdf)</span><span class="sxs-lookup"><span data-stu-id="34ce5-131">Transient user data, such as endpoints and subscriptions, active conferencing servers, and transient conferencing states (database: RtcDyn.mdf)</span></span>

  - <span data-ttu-id="34ce5-132">Dati della Rubrica (database: RtcAb. mdf e Rtcab1. MDF).</span><span class="sxs-lookup"><span data-stu-id="34ce5-132">Address Book data (databases: Rtcab.mdf and Rtcab1.mdf).</span></span> <span data-ttu-id="34ce5-133">Il database della Rubrica viene rigenerato automaticamente da servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="34ce5-133">The Address Book database is regenerated automatically from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="34ce5-134">Informazioni dinamiche per l'applicazione Parcheggio di chiamata (database: CpsDyn. MDF)</span><span class="sxs-lookup"><span data-stu-id="34ce5-134">Dynamic information for the Call Park application (database: CpsDyn.mdf)</span></span>

  - <span data-ttu-id="34ce5-135">Dati dei Response Group transitori, ad esempio lo stato di accesso dell'agente e le informazioni di attesa delle chiamate (database: RgsDyn. MDF)</span><span class="sxs-lookup"><span data-stu-id="34ce5-135">Transient Response Group data, such as agent sign-in state and call waiting information (database: RgsDyn.mdf)</span></span>

  - <span data-ttu-id="34ce5-136">Il database di conformità per la chat persistente (database: MgcComp. MDF).</span><span class="sxs-lookup"><span data-stu-id="34ce5-136">The compliance database for Persistent Chat (database: MgcComp.mdf).</span></span> <span data-ttu-id="34ce5-137">Se si dispone della conformità di Persistent Chat abilitata, le informazioni nel database di conformità di Persistent Chat sono transitorie finché si dispone di un adattatore configurato per leggere informazioni dal database e convertirlo in un formato alternativo.</span><span class="sxs-lookup"><span data-stu-id="34ce5-137">If you have Persistent Chat compliance enabled, the information in the Persistent Chat Compliance database is transient as long as you have an adapter configured to read information from the database and convert it to an alternate format.</span></span> <span data-ttu-id="34ce5-138">Di conseguenza, il database di conformità per la chat persistente è considerato temporaneo.</span><span class="sxs-lookup"><span data-stu-id="34ce5-138">Hence the compliance database for Persistent Chat is considered transient.</span></span>
    
    <span data-ttu-id="34ce5-139">Lync Server 2013 Persistent Chat Server viene fornito con un adattatore XML.</span><span class="sxs-lookup"><span data-stu-id="34ce5-139">Lync Server 2013 Persistent Chat Server ships with an XML adapter.</span></span> <span data-ttu-id="34ce5-140">È inoltre possibile installare adattatori personalizzati che consentono di utilizzare i dati e spostarli in altre origini, ad esempio gli archivi ospitati di Exchange.</span><span class="sxs-lookup"><span data-stu-id="34ce5-140">You can also install custom adapters that take this data and move it to other sources, such as Exchange Hosted Archives.</span></span>

<span data-ttu-id="34ce5-141">Nella tabella seguente vengono identificati i dati di cui è necessario eseguire il backup e il ripristino.</span><span class="sxs-lookup"><span data-stu-id="34ce5-141">The following table identifies the data that you need to back up and restore.</span></span>

### <a name="data-stored-in-databases"></a><span data-ttu-id="34ce5-142">Dati archiviati in database</span><span class="sxs-lookup"><span data-stu-id="34ce5-142">Data Stored in Databases</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34ce5-143">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="34ce5-143">Type of data</span></span></th>
<th><span data-ttu-id="34ce5-144">Dove sono archiviati</span><span class="sxs-lookup"><span data-stu-id="34ce5-144">Where stored</span></span></th>
<th><span data-ttu-id="34ce5-145">Descrizione/Quando eseguire il backup</span><span class="sxs-lookup"><span data-stu-id="34ce5-145">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34ce5-146">Dati utente permanenti</span><span class="sxs-lookup"><span data-stu-id="34ce5-146">Persistent user data</span></span></p></td>
<td><p><span data-ttu-id="34ce5-147">Server back-end server o Standard Edition (database: RTCXDS. MDF)</span><span class="sxs-lookup"><span data-stu-id="34ce5-147">Back End Server or Standard Edition server (database: RTCXDS.mdf)</span></span></p></td>
<td><p><span data-ttu-id="34ce5-148">Diritti utente, elenchi Contatti, dati di server o pool, conferenze pianificate e così via.</span><span class="sxs-lookup"><span data-stu-id="34ce5-148">User rights, user Contacts lists, server or pool data, scheduled conferences, and so on.</span></span> <span data-ttu-id="34ce5-149">Questi dati utente non includono il contenuto caricato in una conferenza.</span><span class="sxs-lookup"><span data-stu-id="34ce5-149">This user data does not include content uploaded to a conference.</span></span></p>
<p><span data-ttu-id="34ce5-150">Eseguire il backup in occasione dei backup regolari.</span><span class="sxs-lookup"><span data-stu-id="34ce5-150">Back up with your regular backups.</span></span> <span data-ttu-id="34ce5-151">Queste informazioni sono dinamiche, ma la perdita di aggiornamenti non è catastrofica per Lync Server, se è necessario ripristinare l'ultimo backup regolare.</span><span class="sxs-lookup"><span data-stu-id="34ce5-151">This information is dynamic, but the loss of updates is not catastrophic to Lync Server if you need to restore to your last regular backup.</span></span> <span data-ttu-id="34ce5-152">Se gli elenchi Contatti sono critici per l'organizzazione, è possibile eseguire il backup di questi dati più di frequente.</span><span class="sxs-lookup"><span data-stu-id="34ce5-152">If Contacts lists are critical to your organization, you can back up this data more frequently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34ce5-153">Dati di archiviazione</span><span class="sxs-lookup"><span data-stu-id="34ce5-153">Archiving data</span></span></p></td>
<td><p><span data-ttu-id="34ce5-154">Database di archiviazione (database: LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="34ce5-154">Archiving database (database: LcsLog.mdf)</span></span></p>
<p><span data-ttu-id="34ce5-155">Questi dati possono essere archiviati in Exchange 2013, se è stata abilitata l'opzione di integrazione di Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="34ce5-155">This data may be stored on Exchange 2013, if you have enabled the Microsoft Exchange integration option.</span></span> <span data-ttu-id="34ce5-156">In caso contrario, i dati vengono conservati in un database di archiviazione di Lync Server, che può essere collocato con un altro database di Lync Server o autonomo in un server di database separato.</span><span class="sxs-lookup"><span data-stu-id="34ce5-156">Otherwise, this data is kept in a Lync Server Archiving database, which may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="34ce5-157">Contenuto di messaggistica istantanea e riunioni.</span><span class="sxs-lookup"><span data-stu-id="34ce5-157">Instant messaging (IM) and meeting content.</span></span></p>
<p><span data-ttu-id="34ce5-158">Questi dati non sono fondamentali per Lync Server, ma possono essere fondamentali per l'organizzazione a fini normativi.</span><span class="sxs-lookup"><span data-stu-id="34ce5-158">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="34ce5-159">Stabilire la pianificazione dei backup di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="34ce5-159">Determine your back up schedule accordingly.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34ce5-160">Dati di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="34ce5-160">Monitoring data</span></span></p></td>
<td><p><span data-ttu-id="34ce5-161">Database di monitoraggio (LcsCDR.mdf e QoeMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="34ce5-161">Monitoring databases (LcsCDR.mdf and QoeMetrics.mdf)</span></span></p>
<p><span data-ttu-id="34ce5-162">Tali database possono essere collocati in un altro database di Lync Server o autonomo in un server di database separato.</span><span class="sxs-lookup"><span data-stu-id="34ce5-162">These databases may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="34ce5-163">Record dettagli chiamata (LcsCDR. MDF) e metriche sulla qualità delle esperienze (QoE) (QoeMetrics. MDF).</span><span class="sxs-lookup"><span data-stu-id="34ce5-163">Call detail records (LcsCDR.mdf) and Quality of Experience (QoE) metrics (QoeMetrics.mdf).</span></span></p>
<p><span data-ttu-id="34ce5-p112">La registrazione dettagli chiamata contiene dati dinamici che possono essere critici per l'azienda. Stabilire la pianificazione dei backup valutando se questi record sono necessari o meno per motivi di regolamentazione.</span><span class="sxs-lookup"><span data-stu-id="34ce5-p112">Call detail records are dynamic and may be critical to your business. Determine your back up schedule by considering whether you need these records for regulatory reasons.</span></span></p>
<p><span data-ttu-id="34ce5-166">Le informazioni su QoE sono dinamiche.</span><span class="sxs-lookup"><span data-stu-id="34ce5-166">Quality of experience information is dynamic.</span></span> <span data-ttu-id="34ce5-167">La perdita di dati QoE non è critica per il funzionamento di Lync Server, ma può essere fondamentale per la propria azienda.</span><span class="sxs-lookup"><span data-stu-id="34ce5-167">Loss of QoE data is not critical for the operation of Lync Server, but it may be critical to your business.</span></span> <span data-ttu-id="34ce5-168">Stabilire la pianificazione dei backup in base al grado di criticità delle informazioni per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="34ce5-168">Determine your back up schedule based on how critical this information is to your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34ce5-169">Dati di chat persistente</span><span class="sxs-lookup"><span data-stu-id="34ce5-169">Persistent Chat data</span></span></p></td>
<td><p><span data-ttu-id="34ce5-170">Database di chat persistente (MGD. MDF).</span><span class="sxs-lookup"><span data-stu-id="34ce5-170">Persistent Chat database (mgd.mdf).</span></span></p>
<p><span data-ttu-id="34ce5-171">Questo database può essere collocato con un altro database di Lync Server o autonomo in un server di database separato.</span><span class="sxs-lookup"><span data-stu-id="34ce5-171">This database may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="34ce5-172">I dati di chat persistente sono contenuti di chat effettivamente pubblicati nelle chat room.</span><span class="sxs-lookup"><span data-stu-id="34ce5-172">Persistent Chat Data is actual chat content being posted in chat rooms.</span></span> <span data-ttu-id="34ce5-173">Questi dati sono spesso importanti per le aziende.</span><span class="sxs-lookup"><span data-stu-id="34ce5-173">This data is often business critical.</span></span></p>
<p><span data-ttu-id="34ce5-174">È possibile scegliere di utilizzare il backup di SQL Server o di esportare il database utilizzando il cmdlet <strong>Export-CsPersistentChatData</strong> fornito in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34ce5-174">You can choose to use SQL Server backup, or export the database by using the <strong>Export-CsPersistentChatData</strong> cmdlet that is provided in Lync Server.</span></span> <span data-ttu-id="34ce5-175">Per il ripristino dei dati, è possibile importare e ripristinare il database fino al punto in cui si trova l'ultimo backup completo, il che significa che non è possibile ripristinare il database fino al punto di errore.</span><span class="sxs-lookup"><span data-stu-id="34ce5-175">For recovery of the data, you can import and restore the database to the point of the last full backup, which means you cannot restore the database to the point of failure.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a><span data-ttu-id="34ce5-176">Requisiti dei dati dell'archivio file</span><span class="sxs-lookup"><span data-stu-id="34ce5-176">File Store Data Requirements</span></span>

<span data-ttu-id="34ce5-177">In una distribuzione di Enterprise Edition, l'archivio file di Lync Server è in genere posizionato in un file server.</span><span class="sxs-lookup"><span data-stu-id="34ce5-177">In an Enterprise Edition deployment, the Lync Server file store is typically located on a file server.</span></span> <span data-ttu-id="34ce5-178">In una distribuzione di Standard Edition, l'archivio file di Lync Server si trova per impostazione predefinita nel server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="34ce5-178">In a Standard Edition deployment, the Lync Server file store is located by default on the Standard Edition server.</span></span> <span data-ttu-id="34ce5-179">In genere, è presente un archivio file di Lync Server condiviso per un sito.</span><span class="sxs-lookup"><span data-stu-id="34ce5-179">Typically, there is one Lync Server file store that is shared for a site.</span></span> <span data-ttu-id="34ce5-180">L'archivio file di chat persistente utilizza la stessa condivisione file dell'archivio file di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34ce5-180">The Persistent Chat file store uses the same file share as the Lync Server file store.</span></span>

<span data-ttu-id="34ce5-181">Le posizioni dell'archivio file sono identificate come \\ \\ nome della condivisione del server \\ .</span><span class="sxs-lookup"><span data-stu-id="34ce5-181">File store locations are identified as \\\\server\\share name.</span></span> <span data-ttu-id="34ce5-182">Per trovare le posizioni specifiche degli archivi di file, aprire Generatore di topologie e cercare nel nodo **archivi file** .</span><span class="sxs-lookup"><span data-stu-id="34ce5-182">To find the specific locations of your file stores, open Topology Builder and look in the **File stores** node.</span></span>

<span data-ttu-id="34ce5-183">Nella tabella seguente sono identificati gli archivi file di cui è necessario eseguire il backup e il ripristino.</span><span class="sxs-lookup"><span data-stu-id="34ce5-183">The following table identifies the file stores you need to back up and restore.</span></span>

### <a name="file-stores"></a><span data-ttu-id="34ce5-184">Archivi file</span><span class="sxs-lookup"><span data-stu-id="34ce5-184">File Stores</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34ce5-185">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="34ce5-185">Type of data</span></span></th>
<th><span data-ttu-id="34ce5-186">Dove sono archiviati</span><span class="sxs-lookup"><span data-stu-id="34ce5-186">Where stored</span></span></th>
<th><span data-ttu-id="34ce5-187">Descrizione/Quando eseguire il backup</span><span class="sxs-lookup"><span data-stu-id="34ce5-187">Description / when to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34ce5-188">Archivio file di Lync Server</span><span class="sxs-lookup"><span data-stu-id="34ce5-188">Lync Server file store</span></span></p></td>
<td><p><span data-ttu-id="34ce5-189">In genere in un file server, in un cluster di file o in un server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="34ce5-189">Typically on a file server, file cluster, or a Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="34ce5-190">Soddisfare le riunioni, soddisfare i metadati del contenuto, registrare i registri di conformità, i file di dati dell'applicazione, aggiornare i file per gli aggiornamenti dei dispositivi, i file audio per Response Group, il parcheggio di chiamata e le applicazioni di annuncio e i file inseriti nelle chat persistenti.</span><span class="sxs-lookup"><span data-stu-id="34ce5-190">Meeting content, meeting content metadata, meeting compliance logs, application data files, update files for device updates, audio files for Response Group, Call Park, and Announcement applications, and files posted into Persistent Chat rooms.</span></span></p>
<p><span data-ttu-id="34ce5-191">Eseguire il backup in occasione dei backup regolari.</span><span class="sxs-lookup"><span data-stu-id="34ce5-191">Back up with your regular backups.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a><span data-ttu-id="34ce5-192">Altri requisiti di backup</span><span class="sxs-lookup"><span data-stu-id="34ce5-192">Additional Backup Requirements</span></span>

<span data-ttu-id="34ce5-193">Per garantire la possibilità di ripristinare i servizi di Lync Server in caso di errore, è necessario eseguire il backup di alcuni componenti necessari che non fanno parte di Lync Server stesso.</span><span class="sxs-lookup"><span data-stu-id="34ce5-193">To help ensure your ability to restore Lync Server services in the event of a failure, you must back up some necessary components that are not part of Lync Server itself.</span></span> <span data-ttu-id="34ce5-194">Non è possibile eseguire il backup o il ripristino dei componenti seguenti nell'ambito del processo di backup e ripristino di Lync Server descritto in questo documento:</span><span class="sxs-lookup"><span data-stu-id="34ce5-194">The following components are not backed up or restored as part of the Lync Server backup and restoration process described in this document:</span></span>

  - <span data-ttu-id="34ce5-195">Servizi di dominio **Active Directory**     È necessario eseguire il backup di AD DS utilizzando gli strumenti di Active Directory contemporaneamente all'esecuzione del backup di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34ce5-195">**Active Directory Domain Services**   You need to back up AD DS by using Active Directory tools at the same time that you back up Lync Server.</span></span> <span data-ttu-id="34ce5-196">È importante mantenere servizi di dominio Active Directory sincronizzati con Lync Server, al fine di evitare problemi che possono verificarsi quando Lync Server prevede che gli oggetti contatto che non corrispondono a quelli in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="34ce5-196">It is important to keep AD DS synchronized with Lync Server, to avoid problems that can occur when Lync Server expects contact objects that do not match those in AD DS.</span></span> <span data-ttu-id="34ce5-197">Servizi di dominio Active Directory archivia le impostazioni seguenti che vengono utilizzate da Lync Server:</span><span class="sxs-lookup"><span data-stu-id="34ce5-197">AD DS stores the following settings which are used by Lync Server:</span></span>
    
      - <span data-ttu-id="34ce5-198">URI SIP dell'utente e altre impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="34ce5-198">User SIP URI and other user settings.</span></span>
    
      - <span data-ttu-id="34ce5-199">Oggetti contatto per applicazioni quali Response Group e operatore conferenza.</span><span class="sxs-lookup"><span data-stu-id="34ce5-199">Contact objects for applications such as Response Group and Conferencing Attendant.</span></span>
    
      - <span data-ttu-id="34ce5-200">Puntatore all'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="34ce5-200">A pointer to the Central Management Store.</span></span>
    
      - <span data-ttu-id="34ce5-201">Account di autenticazione Kerberos (un oggetto computer facoltativo) e gruppi di sicurezza di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34ce5-201">Kerberos Authentication Account (an optional computer object) and Lync Server security groups.</span></span>
    
    <span data-ttu-id="34ce5-202">Per informazioni dettagliate su come eseguire il backup e il ripristino di servizi di dominio Active Directory in Windows Server 2008, vedere "Guida dettagliata su backup e ripristino di servizi di dominio Active Directory" all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=209105](https://go.microsoft.com/fwlink/p/?linkid=209105) .</span><span class="sxs-lookup"><span data-stu-id="34ce5-202">For details about backing up and restoring AD DS in Windows Server 2008, see "AD DS Backup and Recovery Step-by-Step Guide" at [https://go.microsoft.com/fwlink/p/?linkId=209105](https://go.microsoft.com/fwlink/p/?linkid=209105).</span></span>

  - <span data-ttu-id="34ce5-203">**Autorità di certificazione e certificati**     Utilizzare i criteri dell'organizzazione per il backup dell'autorità di certificazione (CA) e dei certificati.</span><span class="sxs-lookup"><span data-stu-id="34ce5-203">**Certification authority and certificates**   Use your organization's policy for backing up your certification authority (CA) and certificates.</span></span> <span data-ttu-id="34ce5-204">Se si utilizzano le chiavi private esportabili, è possibile eseguire il backup del certificato e della chiave privata e quindi esportarle se si utilizzano le procedure descritte in questo documento per ripristinare Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34ce5-204">If you use exportable private keys, you can back up the certificate and the private key, and then export them if you use the procedures in this document to restore Lync Server.</span></span> <span data-ttu-id="34ce5-205">Se si utilizza un'autorità di certificazione interna, è possibile eseguire di nuovo la registrazione se è necessario ripristinare Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34ce5-205">If you use an internal CA, you can re-enroll if you need to restore Lync Server.</span></span> <span data-ttu-id="34ce5-206">È importante conservare la chiave privata in un posto sicuro dove sarà disponibile in caso di problemi con un computer.</span><span class="sxs-lookup"><span data-stu-id="34ce5-206">It is important that you retain the private key in a secure location where it will be available if a computer fails.</span></span>

  - <span data-ttu-id="34ce5-207">**System Center Operations Manager**     Se si utilizza Microsoft System Center Operations Manager (in precedenza Microsoft Operations Manager) per monitorare la distribuzione di Lync Server, è possibile, facoltativamente, eseguire il backup dei dati creati durante il monitoraggio di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34ce5-207">**System Center Operations Manager**   If you use Microsoft System Center Operations Manager (formerly Microsoft Operations Manager) to monitor your Lync Server deployment, you can optionally back up the data it creates while it is monitoring Lync Server.</span></span> <span data-ttu-id="34ce5-208">Utilizzare il processo di backup standard di SQL Server per eseguire il backup dei file di System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="34ce5-208">Use your standard SQL Server backup process to back up System Center Operations Manager files.</span></span> <span data-ttu-id="34ce5-209">Questi file non vengono ripristinati durante il recupero.</span><span class="sxs-lookup"><span data-stu-id="34ce5-209">These files are not restored during recovery.</span></span>

  - <span data-ttu-id="34ce5-210">**Configurazione del gateway PSTN (Public Switched Telephone Network)**     Se si utilizzano VoIP aziendale o Survivable Branch Appliance, è necessario eseguire il backup della configurazione del gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="34ce5-210">**Public switched telephone network (PSTN) gateway configuration**   If you use Enterprise Voice or Survivable Branch Appliances, you need to back up the PSTN gateway configuration.</span></span> <span data-ttu-id="34ce5-211">Per informazioni dettagliate sul backup e il ripristino delle configurazioni di gateway PSTN, contattare il fornitore.</span><span class="sxs-lookup"><span data-stu-id="34ce5-211">See your vendor for details about backing up and restoring PSTN gateway configurations.</span></span>

  - <span data-ttu-id="34ce5-212">**Versioni coesistenti di Lync Server o Office Communications Server**     Se la distribuzione di Lync Server 2013 è coesistente con Lync Server 2010 o una versione precedente di Office Communications Server, non è possibile utilizzare le procedure descritte in questo documento per eseguire il backup o il ripristino della versione precedente.</span><span class="sxs-lookup"><span data-stu-id="34ce5-212">**Coexisting versions of Lync Server or Office Communications Server**   If your Lync Server 2013 deployment coexists with Lync Server 2010 or an earlier version of Office Communications Server, you can’t use the procedures in this document for backing up or restoring the earlier version.</span></span> <span data-ttu-id="34ce5-213">È invece necessario utilizzare le procedure documentate specificamente per la versione precedente.</span><span class="sxs-lookup"><span data-stu-id="34ce5-213">Instead, you must use the backup and restoration procedures documented specifically for your earlier version.</span></span> <span data-ttu-id="34ce5-214">Per informazioni dettagliate su come eseguire il backup e il ripristino di Lync Server 2010, vedere [https://go.microsoft.com/fwlink/p/?linkId=265417](https://go.microsoft.com/fwlink/p/?linkid=265417) .</span><span class="sxs-lookup"><span data-stu-id="34ce5-214">For details about backing up and restoring Lync Server 2010, see [https://go.microsoft.com/fwlink/p/?linkId=265417](https://go.microsoft.com/fwlink/p/?linkid=265417) .</span></span> <span data-ttu-id="34ce5-215">Per informazioni dettagliate su come eseguire il backup e il ripristino di Microsoft Office Communications Server 2007 R2, vedere [https://go.microsoft.com/fwlink/p/?linkId=168162](https://go.microsoft.com/fwlink/p/?linkid=168162) .</span><span class="sxs-lookup"><span data-stu-id="34ce5-215">For details about backing up and restoring Microsoft Office Communications Server 2007 R2, see [https://go.microsoft.com/fwlink/p/?linkId=168162](https://go.microsoft.com/fwlink/p/?linkid=168162).</span></span>

  - <span data-ttu-id="34ce5-216">**Informazioni sull'infrastruttura**     È necessario eseguire il backup delle informazioni relative all'infrastruttura, ad esempio la configurazione del firewall, la configurazione del bilanciamento del carico, la configurazione di Internet Information Services (IIS), i record DNS (Domain Name System) e gli indirizzi IP e la configurazione DHCP (Dynamic Host Configuration Protocol).</span><span class="sxs-lookup"><span data-stu-id="34ce5-216">**Infrastructure information**   You need to back up information about your infrastructure, such as your firewall configuration, load balancing configuration, Internet Information Services (IIS) configuration, Domain Name System (DNS) records and IP addresses, and Dynamic Host Configuration Protocol (DHCP) configuration.</span></span> <span data-ttu-id="34ce5-217">Per informazioni dettagliate sul backup di questi componenti, contattare i rispettivi fornitori.</span><span class="sxs-lookup"><span data-stu-id="34ce5-217">For details about backing up these components, check with their respective vendors.</span></span>

  - <span data-ttu-id="34ce5-218">Messaggistica unificata **di Microsoft Exchange e Exchange**     Eseguire il backup e il ripristino della messaggistica unificata di Microsoft Exchange e Exchange come descritto nella documentazione di Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="34ce5-218">**Microsoft Exchange and Exchange Unified Messaging (UM)**   Backup and restore Microsoft Exchange and Exchange UM as described in the Microsoft Exchange documentation.</span></span> <span data-ttu-id="34ce5-219">Per informazioni dettagliate su come eseguire il backup e il ripristino di Exchange Server 2013, vedere [https://go.microsoft.com/fwlink/?LinkId=285384](https://go.microsoft.com/fwlink/?linkid=285384) .</span><span class="sxs-lookup"><span data-stu-id="34ce5-219">For details about backing up and restoring Exchange Server 2013, see [https://go.microsoft.com/fwlink/?LinkId=285384](https://go.microsoft.com/fwlink/?linkid=285384).</span></span> <span data-ttu-id="34ce5-220">Per informazioni dettagliate su come eseguire il backup e il ripristino di Exchange Server 2010, vedere [https://go.microsoft.com/fwlink/p/?linkId=209179](https://go.microsoft.com/fwlink/p/?linkid=209179) .</span><span class="sxs-lookup"><span data-stu-id="34ce5-220">For details about backing up and restoring Exchange Server 2010, see [https://go.microsoft.com/fwlink/p/?linkId=209179](https://go.microsoft.com/fwlink/p/?linkid=209179).</span></span>
    
    <span data-ttu-id="34ce5-221">Si noti che Lync Server 2013 introduce la possibilità di disporre di elenchi di contatti utente, foto utente ad alta definizione e dati di archiviazione archiviati in Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="34ce5-221">Note that Lync Server 2013 introduces the ability to have user contact lists, high definition user photos, and archiving data stored in Exchange 2013.</span></span> <span data-ttu-id="34ce5-222">Vedere l'elenco seguente per vedere come eseguire il backup di questi tipi di dati:</span><span class="sxs-lookup"><span data-stu-id="34ce5-222">See the following list to see how to back up these types of data:</span></span>
    
      - <span data-ttu-id="34ce5-223">Le **foto ad alta definizione** vengono copiate come parte del backup di Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="34ce5-223">**High definition photos** are backed up as part of the Exchange Server backup.</span></span>
    
      - <span data-ttu-id="34ce5-224">L' **archivio contatti unificato** è stato introdotto in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="34ce5-224">**Unified contact store** is introduced in Lync Server 2013.</span></span> <span data-ttu-id="34ce5-225">Archivio contatti unificato consente agli utenti di mantenere tutte le informazioni di contatto in Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="34ce5-225">Unified contact store enables users to keep all their contact information in Exchange 2013.</span></span>
        
        <span data-ttu-id="34ce5-226">È necessario verificare che i backup siano aggiornati per gli utenti in termini di archiviazione dei contatti utente nell'archivio contatti unificato o nel server back-end Lync.</span><span class="sxs-lookup"><span data-stu-id="34ce5-226">You should make sure that backups are up-to-date for users in terms of whether their user contacts are stored in the unified contact store or on the Lync Back End Server.</span></span> <span data-ttu-id="34ce5-227">Negli scenari seguenti vengono illustrati i casi in cui la migrazione dei contatti utente all'archivio contatti unificato può causare problemi per il processo di backup e ripristino.</span><span class="sxs-lookup"><span data-stu-id="34ce5-227">The following scenarios illustrate where migrating user contacts to the unified contact store can cause issues for the backup and restore process.</span></span>
        
        <span data-ttu-id="34ce5-228">**Scenario 1:** I contatti utente vengono migrati nell'archivio contatti unificato e viene eseguito un ripristino da un backup di Lync Server effettuato prima della migrazione dei contatti utente.</span><span class="sxs-lookup"><span data-stu-id="34ce5-228">**Scenario 1:** User contacts are migrated to the unified contact store, and a restore is performed from a Lync Server backup taken prior to the migration of user contacts.</span></span> <span data-ttu-id="34ce5-229">In questo scenario, l'utente avrà uno stato di contatti obsoleti fino a un giorno fino a quando l'attività di migrazione di Lync Server inizierà la migrazione dei contatti utente a Exchange.</span><span class="sxs-lookup"><span data-stu-id="34ce5-229">In this scenario, the user will have a state of outdated contacts for up to one day until Lync Server Migration Task begins migrating user contacts to Exchange.</span></span> <span data-ttu-id="34ce5-230">Si noti che, poiché i contatti dell'utente sono stati precedentemente migrati nell'archivio contatti unificato, verranno utilizzate le informazioni sui contatti di Exchange.</span><span class="sxs-lookup"><span data-stu-id="34ce5-230">(Note that because the user contacts were previously migrated to the unified contact store, the Exchange contact information will be used).</span></span> <span data-ttu-id="34ce5-231">In questo scenario non sono necessari interventi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="34ce5-231">No administrator intervention is needed in this scenario.</span></span>
        
        <span data-ttu-id="34ce5-232">**Scenario 2:** I contatti utente sono stati precedentemente archiviati nell'archivio contatti unificato, ma quindi sono stati ripristinati.</span><span class="sxs-lookup"><span data-stu-id="34ce5-232">**Scenario 2:** User contacts were previously stored in the unified contact store, but then rolled back.</span></span> <span data-ttu-id="34ce5-233">Viene eseguito un ripristino da un backup di Lync Server utilizzato quando i contatti dell'utente sono stati archiviati nell'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="34ce5-233">A restore is performed from a Lync Server backup taken when the user contacts were stored in the unified contact store.</span></span> <span data-ttu-id="34ce5-234">In questo scenario, un messaggio di errore `Error: Incorrect Exchange Version` nei registri del server client o Lyss può indicare che si tratta di un problema.</span><span class="sxs-lookup"><span data-stu-id="34ce5-234">In this scenario, an error message of `Error: Incorrect Exchange Version` in the client or Lyss server logs may indicate this as an issue.</span></span> <span data-ttu-id="34ce5-235">L'utente sarà in grado di accedere all'elenco dei contatti in Lync 2013 direttamente da Exchange, ma lo stato del client non corrisponderà allo stato di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34ce5-235">The user will be able to access their contact list in Lync 2013 directly from Exchange, but client’s state will not match the Lync Server state.</span></span> <span data-ttu-id="34ce5-236">Per risolvere questo errore, è necessario che un amministratore esegua i cmdlet **Invoke-CsUCSRollback** per gli utenti coinvolti.</span><span class="sxs-lookup"><span data-stu-id="34ce5-236">To fix this, an administrator will need to run the **Invoke-CsUCSRollback** cmdlets for the affected users.</span></span>
    
      - <span data-ttu-id="34ce5-237">È possibile archiviare **i dati di archiviazione** in Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="34ce5-237">**Archiving Data** can be stored in Exchange 2013.</span></span> <span data-ttu-id="34ce5-238">Questi dati non sono fondamentali per Lync Server, ma possono essere fondamentali per l'organizzazione a fini normativi.</span><span class="sxs-lookup"><span data-stu-id="34ce5-238">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="34ce5-239">Se i dati di archiviazione sono archiviati in Exchange ed è importante per l'organizzazione, seguire le procedure di backup e ripristino di Exchange.</span><span class="sxs-lookup"><span data-stu-id="34ce5-239">If archiving data is stored in Exchange and is critical to your organization, then follow Exchange backup and restore procedures.</span></span> <span data-ttu-id="34ce5-240">Si noti che i dati di archiviazione archiviati in Exchange non possono essere spostati di nuovo in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34ce5-240">Note that archiving data stored in Exchange cannot be moved back to Lync Server.</span></span> <span data-ttu-id="34ce5-241">Inoltre, non esiste alcun modo per spostare i dati già archiviati nel database di archiviazione Lync in Exchange.</span><span class="sxs-lookup"><span data-stu-id="34ce5-241">Additionally, there is no way to move data already stored in the Lync archiving database to Exchange.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

