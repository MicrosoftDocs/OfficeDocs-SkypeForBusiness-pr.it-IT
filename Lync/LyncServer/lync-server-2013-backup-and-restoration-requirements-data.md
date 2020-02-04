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
ms.openlocfilehash: a9b9f077e0f9d7c4137844b2cba352b096fdb564
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a><span data-ttu-id="44e35-102">Requisiti di backup e ripristino in Lync Server 2013: dati</span><span class="sxs-lookup"><span data-stu-id="44e35-102">Backup and restoration requirements in Lync Server 2013: data</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44e35-103">_**Argomento Ultima modifica:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="44e35-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="44e35-104">Lync Server usa le impostazioni e le informazioni di configurazione archiviate nei database e i dati archiviati in database e archivi di file.</span><span class="sxs-lookup"><span data-stu-id="44e35-104">Lync Server uses settings and configuration information that are stored in databases, and data that is stored in databases and file stores.</span></span> <span data-ttu-id="44e35-105">In questo argomento vengono descritti i dati di cui è necessario eseguire il backup per poter ripristinare il servizio se l'organizzazione avverte un errore o un'interruzione, oltre a identificare anche i dati e i componenti usati da Lync Server che è necessario eseguire il backup separatamente.</span><span class="sxs-lookup"><span data-stu-id="44e35-105">This topic describes the data that you need to back up to be able to restore service if your organization experiences a failure or outage, and also identifies the data and components used by Lync Server that you need to back up separately.</span></span>

<div>

## <a name="settings-and-configuration-requirements"></a><span data-ttu-id="44e35-106">Requisiti per le impostazioni e la configurazione</span><span class="sxs-lookup"><span data-stu-id="44e35-106">Settings and Configuration Requirements</span></span>

<span data-ttu-id="44e35-107">Questo argomento include le procedure per il backup e il ripristino delle impostazioni e delle informazioni di configurazione necessarie per il ripristino del servizio Lync Server.</span><span class="sxs-lookup"><span data-stu-id="44e35-107">This topic includes procedures for backing up and restoring the settings and configuration information that is required for recovery of Lync Server service.</span></span> <span data-ttu-id="44e35-108">Le informazioni di configurazione si trovano nell'Central Management Store o in un altro database back-end o in un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="44e35-108">The configuration information is located in the Central Management store or on another back-end database or on Standard Edition server.</span></span>

<span data-ttu-id="44e35-109">La tabella seguente identifica le impostazioni e le informazioni di configurazione necessarie per eseguire il backup e il ripristino.</span><span class="sxs-lookup"><span data-stu-id="44e35-109">The following table identifies the settings and configuration information that you need to back up and restore.</span></span>

### <a name="settings-and-configuration-data"></a><span data-ttu-id="44e35-110">Impostazioni e dati di configurazione</span><span class="sxs-lookup"><span data-stu-id="44e35-110">Settings and Configuration Data</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44e35-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="44e35-111">Type of data</span></span></th>
<th><span data-ttu-id="44e35-112">Dove archiviato</span><span class="sxs-lookup"><span data-stu-id="44e35-112">Where stored</span></span></th>
<th><span data-ttu-id="44e35-113">Descrizione/quando eseguire il backup</span><span class="sxs-lookup"><span data-stu-id="44e35-113">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44e35-114">Informazioni sulla configurazione della topologia</span><span class="sxs-lookup"><span data-stu-id="44e35-114">Topology configuration information</span></span></p></td>
<td><p><span data-ttu-id="44e35-115">Central Management store (database: XDS. MDF)</span><span class="sxs-lookup"><span data-stu-id="44e35-115">Central Management store (database: Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="44e35-116">Impostazioni di topologia, criteri e configurazione.</span><span class="sxs-lookup"><span data-stu-id="44e35-116">Topology, policy, and configuration settings.</span></span></p>
<p><span data-ttu-id="44e35-117">Eseguire il backup con i controlli regolari e dopo avere usato il pannello di controllo di Lync Server o i cmdlet per modificare la configurazione o i criteri.</span><span class="sxs-lookup"><span data-stu-id="44e35-117">Back up with your regular backups and after you use Lync Server Control Panel or cmdlets to modify your configuration or policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e35-118">Informazioni sulla posizione</span><span class="sxs-lookup"><span data-stu-id="44e35-118">Location information</span></span></p></td>
<td><p><span data-ttu-id="44e35-119">Central Management store (database: LIS. MDF)</span><span class="sxs-lookup"><span data-stu-id="44e35-119">Central Management store (database: Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="44e35-120">Informazioni sulla configurazione di Enterprise Voice Enhanced 9-1-1 (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="44e35-120">Enterprise Voice Enhanced 9-1-1 (E9-1-1) configuration information.</span></span> <span data-ttu-id="44e35-121">Queste informazioni sono in genere statiche.</span><span class="sxs-lookup"><span data-stu-id="44e35-121">This information is generally static.</span></span></p>
<p><span data-ttu-id="44e35-122">Eseguire il backup con i normali sostegni.</span><span class="sxs-lookup"><span data-stu-id="44e35-122">Back up with your regular backups.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e35-123">Informazioni sulla configurazione di Response Group</span><span class="sxs-lookup"><span data-stu-id="44e35-123">Response Group configuration information</span></span></p></td>
<td><p><span data-ttu-id="44e35-124">Server back-end o server Standard Edition (database: RgsConfig. MDF)</span><span class="sxs-lookup"><span data-stu-id="44e35-124">Back End Server or Standard Edition server (database: RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="44e35-125">Gruppi di agenti di Response Group, code e flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="44e35-125">Response Group agent groups, queues, and workflows.</span></span></p>
<p><span data-ttu-id="44e35-126">Eseguire il backup con i normali sostegni e dopo aver aggiunto o modificato i gruppi di agenti, le code o i flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="44e35-126">Back up with your regular backups and after you add or change agent groups, queues, or workflows.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a><span data-ttu-id="44e35-127">Requisiti per i dati</span><span class="sxs-lookup"><span data-stu-id="44e35-127">Data Requirements</span></span>

<span data-ttu-id="44e35-128">Ecco un elenco dei dati di Lync Server di cui è necessario eseguire il backup in modo da poter ripristinare il servizio Lync Server in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="44e35-128">Here is a list of the Lync Server data that you need to back up so that you can restore Lync Server service in the event of a failure.</span></span>

<span data-ttu-id="44e35-129">Tieni presente che alcuni tipi di dati non sono necessari per il ripristino.</span><span class="sxs-lookup"><span data-stu-id="44e35-129">Note that some types of data are not required for recovery.</span></span> <span data-ttu-id="44e35-130">Questo argomento non contiene procedure per il backup di questi tipi di dati, che includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="44e35-130">This topic does not contain procedures for backing up these types of data, which include the following:</span></span>

  - <span data-ttu-id="44e35-131">Dati utente temporanei, ad esempio endpoint e abbonamenti, server di conferenza attiva e Stati di conferenza transitori (database: RtcDyn. MDF)</span><span class="sxs-lookup"><span data-stu-id="44e35-131">Transient user data, such as endpoints and subscriptions, active conferencing servers, and transient conferencing states (database: RtcDyn.mdf)</span></span>

  - <span data-ttu-id="44e35-132">Dati della Rubrica (database: RtcAb. mdf e Rtcab1. MDF).</span><span class="sxs-lookup"><span data-stu-id="44e35-132">Address Book data (databases: Rtcab.mdf and Rtcab1.mdf).</span></span> <span data-ttu-id="44e35-133">Il database della Rubrica viene rigenerato automaticamente da servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="44e35-133">The Address Book database is regenerated automatically from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="44e35-134">Informazioni dinamiche per l'applicazione Call Park (database: CpsDyn. MDF)</span><span class="sxs-lookup"><span data-stu-id="44e35-134">Dynamic information for the Call Park application (database: CpsDyn.mdf)</span></span>

  - <span data-ttu-id="44e35-135">Dati del gruppo di risposta temporaneo, ad esempio lo stato di accesso dell'agente e le informazioni di attesa delle chiamate (database: RgsDyn. MDF)</span><span class="sxs-lookup"><span data-stu-id="44e35-135">Transient Response Group data, such as agent sign-in state and call waiting information (database: RgsDyn.mdf)</span></span>

  - <span data-ttu-id="44e35-136">Database di conformità per la chat persistente (database: MgcComp. MDF).</span><span class="sxs-lookup"><span data-stu-id="44e35-136">The compliance database for Persistent Chat (database: MgcComp.mdf).</span></span> <span data-ttu-id="44e35-137">Se è abilitata la conformità della chat persistente, le informazioni nel database di conformità della chat persistente sono transitorie purché si disponga di un adapter configurato per leggere le informazioni dal database e convertirlo in un formato alternativo.</span><span class="sxs-lookup"><span data-stu-id="44e35-137">If you have Persistent Chat compliance enabled, the information in the Persistent Chat Compliance database is transient as long as you have an adapter configured to read information from the database and convert it to an alternate format.</span></span> <span data-ttu-id="44e35-138">Il database di conformità per la chat persistente viene quindi considerato temporaneo.</span><span class="sxs-lookup"><span data-stu-id="44e35-138">Hence the compliance database for Persistent Chat is considered transient.</span></span>
    
    <span data-ttu-id="44e35-139">Il server di chat persistente di Lync Server 2013 viene fornito con un adattatore XML.</span><span class="sxs-lookup"><span data-stu-id="44e35-139">Lync Server 2013 Persistent Chat Server ships with an XML adapter.</span></span> <span data-ttu-id="44e35-140">È anche possibile installare adapter personalizzati che accettano questi dati e lo spostano in altre origini, ad esempio gli archivi ospitati di Exchange.</span><span class="sxs-lookup"><span data-stu-id="44e35-140">You can also install custom adapters that take this data and move it to other sources, such as Exchange Hosted Archives.</span></span>

<span data-ttu-id="44e35-141">La tabella seguente identifica i dati necessari per eseguire il backup e il ripristino.</span><span class="sxs-lookup"><span data-stu-id="44e35-141">The following table identifies the data that you need to back up and restore.</span></span>

### <a name="data-stored-in-databases"></a><span data-ttu-id="44e35-142">Dati archiviati nei database</span><span class="sxs-lookup"><span data-stu-id="44e35-142">Data Stored in Databases</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44e35-143">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="44e35-143">Type of data</span></span></th>
<th><span data-ttu-id="44e35-144">Dove archiviato</span><span class="sxs-lookup"><span data-stu-id="44e35-144">Where stored</span></span></th>
<th><span data-ttu-id="44e35-145">Descrizione/quando eseguire il backup</span><span class="sxs-lookup"><span data-stu-id="44e35-145">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44e35-146">Dati utente permanenti</span><span class="sxs-lookup"><span data-stu-id="44e35-146">Persistent user data</span></span></p></td>
<td><p><span data-ttu-id="44e35-147">Server back-end o server Standard Edition (database: RTCXDS. MDF)</span><span class="sxs-lookup"><span data-stu-id="44e35-147">Back End Server or Standard Edition server (database: RTCXDS.mdf)</span></span></p></td>
<td><p><span data-ttu-id="44e35-148">Diritti utente, elenchi contatti utente, dati server o pool, conferenze pianificate e così via.</span><span class="sxs-lookup"><span data-stu-id="44e35-148">User rights, user Contacts lists, server or pool data, scheduled conferences, and so on.</span></span> <span data-ttu-id="44e35-149">Questi dati utente non includono il contenuto caricato in una conferenza.</span><span class="sxs-lookup"><span data-stu-id="44e35-149">This user data does not include content uploaded to a conference.</span></span></p>
<p><span data-ttu-id="44e35-150">Eseguire il backup con i normali sostegni.</span><span class="sxs-lookup"><span data-stu-id="44e35-150">Back up with your regular backups.</span></span> <span data-ttu-id="44e35-151">Queste informazioni sono dinamiche, ma la perdita di aggiornamenti non è catastrofica per Lync Server se è necessario ripristinare l'ultimo backup normale.</span><span class="sxs-lookup"><span data-stu-id="44e35-151">This information is dynamic, but the loss of updates is not catastrophic to Lync Server if you need to restore to your last regular backup.</span></span> <span data-ttu-id="44e35-152">Se gli elenchi di contatti sono fondamentali per l'organizzazione, è possibile eseguire il backup dei dati più frequentemente.</span><span class="sxs-lookup"><span data-stu-id="44e35-152">If Contacts lists are critical to your organization, you can back up this data more frequently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e35-153">Archiviazione dei dati</span><span class="sxs-lookup"><span data-stu-id="44e35-153">Archiving data</span></span></p></td>
<td><p><span data-ttu-id="44e35-154">Database di archiviazione (database: LcsLog. MDF)</span><span class="sxs-lookup"><span data-stu-id="44e35-154">Archiving database (database: LcsLog.mdf)</span></span></p>
<p><span data-ttu-id="44e35-155">Questi dati possono essere archiviati in Exchange 2013, se è stata abilitata l'opzione di integrazione di Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="44e35-155">This data may be stored on Exchange 2013, if you have enabled the Microsoft Exchange integration option.</span></span> <span data-ttu-id="44e35-156">In caso contrario, questi dati vengono conservati in un database di archiviazione di Lync Server, che può essere collocato in un altro database di Lync Server o autonomo in un server di database separato.</span><span class="sxs-lookup"><span data-stu-id="44e35-156">Otherwise, this data is kept in a Lync Server Archiving database, which may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="44e35-157">Messaggistica istantanea (IM) e contenuto della riunione.</span><span class="sxs-lookup"><span data-stu-id="44e35-157">Instant messaging (IM) and meeting content.</span></span></p>
<p><span data-ttu-id="44e35-158">Questi dati non sono fondamentali per Lync Server, ma può essere fondamentale per l'organizzazione per scopi normativi.</span><span class="sxs-lookup"><span data-stu-id="44e35-158">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="44e35-159">Determinare di conseguenza la pianificazione di backup.</span><span class="sxs-lookup"><span data-stu-id="44e35-159">Determine your back up schedule accordingly.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e35-160">Monitoraggio dei dati</span><span class="sxs-lookup"><span data-stu-id="44e35-160">Monitoring data</span></span></p></td>
<td><p><span data-ttu-id="44e35-161">Monitoraggio di database (LcsCDR. mdf e QoeMetrics. MDF)</span><span class="sxs-lookup"><span data-stu-id="44e35-161">Monitoring databases (LcsCDR.mdf and QoeMetrics.mdf)</span></span></p>
<p><span data-ttu-id="44e35-162">Questi database possono essere collocati in un altro database di Lync Server o autonomo in un server di database separato.</span><span class="sxs-lookup"><span data-stu-id="44e35-162">These databases may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="44e35-163">Record dettagli chiamata (LcsCDR. MDF) e metriche di qualità delle esperienze (QoE) (QoeMetrics. MDF).</span><span class="sxs-lookup"><span data-stu-id="44e35-163">Call detail records (LcsCDR.mdf) and Quality of Experience (QoE) metrics (QoeMetrics.mdf).</span></span></p>
<p><span data-ttu-id="44e35-164">I record dettagli chiamata sono dinamici e possono essere critici per l'azienda.</span><span class="sxs-lookup"><span data-stu-id="44e35-164">Call detail records are dynamic and may be critical to your business.</span></span> <span data-ttu-id="44e35-165">Determinare la pianificazione del backup considerando se sono necessari questi record per motivi di regolamentazione.</span><span class="sxs-lookup"><span data-stu-id="44e35-165">Determine your back up schedule by considering whether you need these records for regulatory reasons.</span></span></p>
<p><span data-ttu-id="44e35-166">Le informazioni sulla qualità delle esperienze sono dinamiche.</span><span class="sxs-lookup"><span data-stu-id="44e35-166">Quality of experience information is dynamic.</span></span> <span data-ttu-id="44e35-167">La perdita di dati QoE non è fondamentale per l'operazione di Lync Server, ma può essere fondamentale per l'azienda.</span><span class="sxs-lookup"><span data-stu-id="44e35-167">Loss of QoE data is not critical for the operation of Lync Server, but it may be critical to your business.</span></span> <span data-ttu-id="44e35-168">Determinare la pianificazione del backup in base alla criticità di queste informazioni per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="44e35-168">Determine your back up schedule based on how critical this information is to your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e35-169">Dati della chat persistente</span><span class="sxs-lookup"><span data-stu-id="44e35-169">Persistent Chat data</span></span></p></td>
<td><p><span data-ttu-id="44e35-170">Database di chat persistente (MGD. MDF).</span><span class="sxs-lookup"><span data-stu-id="44e35-170">Persistent Chat database (mgd.mdf).</span></span></p>
<p><span data-ttu-id="44e35-171">Questo database può essere collocato in un altro database di Lync Server o autonomo in un server di database separato.</span><span class="sxs-lookup"><span data-stu-id="44e35-171">This database may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="44e35-172">I dati della chat persistente sono contenuti di chat effettivi pubblicati nelle chat room.</span><span class="sxs-lookup"><span data-stu-id="44e35-172">Persistent Chat Data is actual chat content being posted in chat rooms.</span></span> <span data-ttu-id="44e35-173">Questi dati sono spesso critici per gli affari.</span><span class="sxs-lookup"><span data-stu-id="44e35-173">This data is often business critical.</span></span></p>
<p><span data-ttu-id="44e35-174">È possibile scegliere di usare il backup di SQL Server oppure esportare il database usando il cmdlet <strong>Export-CsPersistentChatData</strong> fornito in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="44e35-174">You can choose to use SQL Server backup, or export the database by using the <strong>Export-CsPersistentChatData</strong> cmdlet that is provided in Lync Server.</span></span> <span data-ttu-id="44e35-175">Per il ripristino dei dati, è possibile importare e ripristinare il database fino al punto dell'ultimo backup completo, quindi non è possibile ripristinare il database fino al punto di errore.</span><span class="sxs-lookup"><span data-stu-id="44e35-175">For recovery of the data, you can import and restore the database to the point of the last full backup, which means you cannot restore the database to the point of failure.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a><span data-ttu-id="44e35-176">Requisiti per l'archiviazione dei file</span><span class="sxs-lookup"><span data-stu-id="44e35-176">File Store Data Requirements</span></span>

<span data-ttu-id="44e35-177">In una distribuzione di Enterprise Edition, il file Store di Lync Server si trova in genere in un file server.</span><span class="sxs-lookup"><span data-stu-id="44e35-177">In an Enterprise Edition deployment, the Lync Server file store is typically located on a file server.</span></span> <span data-ttu-id="44e35-178">In una distribuzione Standard Edition, il file Store di Lync Server si trova per impostazione predefinita nel server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="44e35-178">In a Standard Edition deployment, the Lync Server file store is located by default on the Standard Edition server.</span></span> <span data-ttu-id="44e35-179">In genere, esiste un archivio file di Lync Server condiviso per un sito.</span><span class="sxs-lookup"><span data-stu-id="44e35-179">Typically, there is one Lync Server file store that is shared for a site.</span></span> <span data-ttu-id="44e35-180">L'archivio di file della chat persistente usa la stessa condivisione di file dell'archivio di file di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="44e35-180">The Persistent Chat file store uses the same file share as the Lync Server file store.</span></span>

<span data-ttu-id="44e35-181">I percorsi di archiviazione file sono \\ \\identificati come nome condivisione server\\.</span><span class="sxs-lookup"><span data-stu-id="44e35-181">File store locations are identified as \\\\server\\share name.</span></span> <span data-ttu-id="44e35-182">Per trovare le posizioni specifiche degli archivi di file, aprire Generatore di topologie e cercare nel nodo **archivi file** .</span><span class="sxs-lookup"><span data-stu-id="44e35-182">To find the specific locations of your file stores, open Topology Builder and look in the **File stores** node.</span></span>

<span data-ttu-id="44e35-183">La tabella seguente identifica gli archivi di file necessari per eseguire il backup e il ripristino.</span><span class="sxs-lookup"><span data-stu-id="44e35-183">The following table identifies the file stores you need to back up and restore.</span></span>

### <a name="file-stores"></a><span data-ttu-id="44e35-184">Archivi di file</span><span class="sxs-lookup"><span data-stu-id="44e35-184">File Stores</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44e35-185">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="44e35-185">Type of data</span></span></th>
<th><span data-ttu-id="44e35-186">Dove archiviato</span><span class="sxs-lookup"><span data-stu-id="44e35-186">Where stored</span></span></th>
<th><span data-ttu-id="44e35-187">Descrizione/quando eseguire il backup</span><span class="sxs-lookup"><span data-stu-id="44e35-187">Description / when to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44e35-188">Archivio file di Lync Server</span><span class="sxs-lookup"><span data-stu-id="44e35-188">Lync Server file store</span></span></p></td>
<td><p><span data-ttu-id="44e35-189">In genere in un file server, un cluster di file o un server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="44e35-189">Typically on a file server, file cluster, or a Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="44e35-190">Contenuto della riunione, riunione dei metadati del contenuto, registri della conformità delle riunioni, file di dati dell'applicazione, file di aggiornamento per gli aggiornamenti dei dispositivi, file audio per il gruppo di risposte, parcheggio delle chiamate e applicazioni di annunci e file inseriti nelle chat room permanenti.</span><span class="sxs-lookup"><span data-stu-id="44e35-190">Meeting content, meeting content metadata, meeting compliance logs, application data files, update files for device updates, audio files for Response Group, Call Park, and Announcement applications, and files posted into Persistent Chat rooms.</span></span></p>
<p><span data-ttu-id="44e35-191">Eseguire il backup con i normali sostegni.</span><span class="sxs-lookup"><span data-stu-id="44e35-191">Back up with your regular backups.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a><span data-ttu-id="44e35-192">Requisiti di backup aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="44e35-192">Additional Backup Requirements</span></span>

<span data-ttu-id="44e35-193">Per garantire la possibilità di ripristinare i servizi Lync Server in caso di errore, è necessario eseguire il backup di alcuni componenti necessari che non fanno parte di Lync Server stesso.</span><span class="sxs-lookup"><span data-stu-id="44e35-193">To help ensure your ability to restore Lync Server services in the event of a failure, you must back up some necessary components that are not part of Lync Server itself.</span></span> <span data-ttu-id="44e35-194">I componenti seguenti non vengono sottoposte a backup o ripristinati come parte del processo di backup e ripristino di Lync Server descritto in questo documento:</span><span class="sxs-lookup"><span data-stu-id="44e35-194">The following components are not backed up or restored as part of the Lync Server backup and restoration process described in this document:</span></span>

  - <span data-ttu-id="44e35-195">**Servizi di dominio Active Directory**   che è necessario eseguire il backup di Active Directory con gli strumenti attivi per il backup di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="44e35-195">**Active Directory Domain Services**   You need to back up AD DS by using Active Directory tools at the same time that you back up Lync Server.</span></span> <span data-ttu-id="44e35-196">È importante garantire la sincronizzazione di Active Directory con Lync Server, per evitare problemi che si verificano quando Lync Server si aspetta che gli oggetti contatto non corrispondano a quelli in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="44e35-196">It is important to keep AD DS synchronized with Lync Server, to avoid problems that can occur when Lync Server expects contact objects that do not match those in AD DS.</span></span> <span data-ttu-id="44e35-197">In servizi di dominio Active Directory vengono archiviate le impostazioni seguenti usate da Lync Server:</span><span class="sxs-lookup"><span data-stu-id="44e35-197">AD DS stores the following settings which are used by Lync Server:</span></span>
    
      - <span data-ttu-id="44e35-198">URI SIP utente e altre impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="44e35-198">User SIP URI and other user settings.</span></span>
    
      - <span data-ttu-id="44e35-199">Contattare gli oggetti per le applicazioni, ad esempio Response Group e Attendant.</span><span class="sxs-lookup"><span data-stu-id="44e35-199">Contact objects for applications such as Response Group and Conferencing Attendant.</span></span>
    
      - <span data-ttu-id="44e35-200">Un puntatore all'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="44e35-200">A pointer to the Central Management Store.</span></span>
    
      - <span data-ttu-id="44e35-201">Account di autenticazione Kerberos (un oggetto computer facoltativo) e gruppi di sicurezza di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="44e35-201">Kerberos Authentication Account (an optional computer object) and Lync Server security groups.</span></span>
    
    <span data-ttu-id="44e35-202">Per informazioni dettagliate su come eseguire il backup e il ripristino di servizi di dominio Active Directory in Windows Server 2008, vedere "Guida introduttiva a [http://go.microsoft.com/fwlink/p/?linkId=209105](http://go.microsoft.com/fwlink/p/?linkid=209105)backup e ripristino di servizi di dominio Active Directory".</span><span class="sxs-lookup"><span data-stu-id="44e35-202">For details about backing up and restoring AD DS in Windows Server 2008, see "AD DS Backup and Recovery Step-by-Step Guide" at [http://go.microsoft.com/fwlink/p/?linkId=209105](http://go.microsoft.com/fwlink/p/?linkid=209105).</span></span>

  - <span data-ttu-id="44e35-203">**Autorità di certificazione e certificati**   usare i criteri dell'organizzazione per eseguire il backup dell'autorità di certificazione (CA) e dei certificati.</span><span class="sxs-lookup"><span data-stu-id="44e35-203">**Certification authority and certificates**   Use your organization's policy for backing up your certification authority (CA) and certificates.</span></span> <span data-ttu-id="44e35-204">Se si usano chiavi private esportabili, è possibile eseguire il backup del certificato e della chiave privata e quindi esportarle se si usano le procedure descritte in questo documento per ripristinare Lync Server.</span><span class="sxs-lookup"><span data-stu-id="44e35-204">If you use exportable private keys, you can back up the certificate and the private key, and then export them if you use the procedures in this document to restore Lync Server.</span></span> <span data-ttu-id="44e35-205">Se si usa una CA interna, è possibile eseguire di nuovo la registrazione se è necessario ripristinare Lync Server.</span><span class="sxs-lookup"><span data-stu-id="44e35-205">If you use an internal CA, you can re-enroll if you need to restore Lync Server.</span></span> <span data-ttu-id="44e35-206">È importante mantenere la chiave privata in un percorso sicuro in cui sarà disponibile se un computer non riesce.</span><span class="sxs-lookup"><span data-stu-id="44e35-206">It is important that you retain the private key in a secure location where it will be available if a computer fails.</span></span>

  - <span data-ttu-id="44e35-207">**System Center Operations Manager**   se si usa Microsoft System Center Operations Manager (in precedenza Microsoft Operations Manager) per monitorare la distribuzione di Lync Server, è possibile eseguire facoltativamente il backup dei dati creati durante il monitoraggio di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="44e35-207">**System Center Operations Manager**   If you use Microsoft System Center Operations Manager (formerly Microsoft Operations Manager) to monitor your Lync Server deployment, you can optionally back up the data it creates while it is monitoring Lync Server.</span></span> <span data-ttu-id="44e35-208">Usare il processo di backup standard di SQL Server per eseguire il backup dei file di System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="44e35-208">Use your standard SQL Server backup process to back up System Center Operations Manager files.</span></span> <span data-ttu-id="44e35-209">Questi file non vengono ripristinati durante il ripristino.</span><span class="sxs-lookup"><span data-stu-id="44e35-209">These files are not restored during recovery.</span></span>

  - <span data-ttu-id="44e35-210">**Configurazione del gateway PSTN (Public Switched Telephone Network)**   se si usano Enterprise Voice o Survivable Branch Appliances, è necessario eseguire il backup della configurazione del gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="44e35-210">**Public switched telephone network (PSTN) gateway configuration**   If you use Enterprise Voice or Survivable Branch Appliances, you need to back up the PSTN gateway configuration.</span></span> <span data-ttu-id="44e35-211">Vedere il fornitore per informazioni dettagliate su come eseguire il backup e il ripristino delle configurazioni dei gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="44e35-211">See your vendor for details about backing up and restoring PSTN gateway configurations.</span></span>

  - <span data-ttu-id="44e35-212">**Versioni coesistenti di Lync Server o Office Communications Server**   se la distribuzione di Lync Server 2013 è coesistente con Lync Server 2010 o una versione precedente di Office Communications Server, non è possibile usare le procedure descritte in questo documento per eseguire il backup o il ripristino della versione precedente.</span><span class="sxs-lookup"><span data-stu-id="44e35-212">**Coexisting versions of Lync Server or Office Communications Server**   If your Lync Server 2013 deployment coexists with Lync Server 2010 or an earlier version of Office Communications Server, you can’t use the procedures in this document for backing up or restoring the earlier version.</span></span> <span data-ttu-id="44e35-213">Devi invece usare le procedure di backup e ripristino documentate in modo specifico per la versione precedente.</span><span class="sxs-lookup"><span data-stu-id="44e35-213">Instead, you must use the backup and restoration procedures documented specifically for your earlier version.</span></span> <span data-ttu-id="44e35-214">Per informazioni dettagliate su come eseguire il backup e il ripristino di Lync [http://go.microsoft.com/fwlink/p/?linkId=265417](http://go.microsoft.com/fwlink/p/?linkid=265417) Server 2010, vedere.</span><span class="sxs-lookup"><span data-stu-id="44e35-214">For details about backing up and restoring Lync Server 2010, see [http://go.microsoft.com/fwlink/p/?linkId=265417](http://go.microsoft.com/fwlink/p/?linkid=265417) .</span></span> <span data-ttu-id="44e35-215">Per informazioni dettagliate su come eseguire il backup e il ripristino di Microsoft Office Communications Server [http://go.microsoft.com/fwlink/p/?linkId=168162](http://go.microsoft.com/fwlink/p/?linkid=168162)2007 R2, vedere.</span><span class="sxs-lookup"><span data-stu-id="44e35-215">For details about backing up and restoring Microsoft Office Communications Server 2007 R2, see [http://go.microsoft.com/fwlink/p/?linkId=168162](http://go.microsoft.com/fwlink/p/?linkid=168162).</span></span>

  - <span data-ttu-id="44e35-216">**Informazioni sull'infrastruttura**   necessarie per eseguire il backup di informazioni sull'infrastruttura, ad esempio la configurazione del firewall, la configurazione del bilanciamento del carico, la configurazione di Internet Information Services (IIS), i record DNS (Domain Name System) e gli indirizzi IP e la configurazione DHCP (Dynamic Host Configuration Protocol).</span><span class="sxs-lookup"><span data-stu-id="44e35-216">**Infrastructure information**   You need to back up information about your infrastructure, such as your firewall configuration, load balancing configuration, Internet Information Services (IIS) configuration, Domain Name System (DNS) records and IP addresses, and Dynamic Host Configuration Protocol (DHCP) configuration.</span></span> <span data-ttu-id="44e35-217">Per informazioni dettagliate su come eseguire il backup di questi componenti, consultare i rispettivi fornitori.</span><span class="sxs-lookup"><span data-stu-id="44e35-217">For details about backing up these components, check with their respective vendors.</span></span>

  - <span data-ttu-id="44e35-218">**Microsoft Exchange ed Exchange Unified Messaging (UM)**   backup e ripristino della messaggistica unificata di Microsoft Exchange e Exchange come descritto nella documentazione di Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="44e35-218">**Microsoft Exchange and Exchange Unified Messaging (UM)**   Backup and restore Microsoft Exchange and Exchange UM as described in the Microsoft Exchange documentation.</span></span> <span data-ttu-id="44e35-219">Per informazioni dettagliate su come eseguire il backup e il ripristino di Exchange [http://go.microsoft.com/fwlink/?LinkId=285384](http://go.microsoft.com/fwlink/?linkid=285384)Server 2013, vedere.</span><span class="sxs-lookup"><span data-stu-id="44e35-219">For details about backing up and restoring Exchange Server 2013, see [http://go.microsoft.com/fwlink/?LinkId=285384](http://go.microsoft.com/fwlink/?linkid=285384).</span></span> <span data-ttu-id="44e35-220">Per informazioni dettagliate su come eseguire il backup e il ripristino di Exchange [http://go.microsoft.com/fwlink/p/?linkId=209179](http://go.microsoft.com/fwlink/p/?linkid=209179)Server 2010, vedere.</span><span class="sxs-lookup"><span data-stu-id="44e35-220">For details about backing up and restoring Exchange Server 2010, see [http://go.microsoft.com/fwlink/p/?linkId=209179](http://go.microsoft.com/fwlink/p/?linkid=209179).</span></span>
    
    <span data-ttu-id="44e35-221">Si noti che Lync Server 2013 introduce la possibilità di avere elenchi di contatti utente, foto degli utenti ad alta definizione e archiviazione dei dati archiviati in Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="44e35-221">Note that Lync Server 2013 introduces the ability to have user contact lists, high definition user photos, and archiving data stored in Exchange 2013.</span></span> <span data-ttu-id="44e35-222">Vedere l'elenco seguente per informazioni su come eseguire il backup di questi tipi di dati:</span><span class="sxs-lookup"><span data-stu-id="44e35-222">See the following list to see how to back up these types of data:</span></span>
    
      - <span data-ttu-id="44e35-223">Le **foto ad alta definizione** vengono supportate come parte del backup di Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="44e35-223">**High definition photos** are backed up as part of the Exchange Server backup.</span></span>
    
      - <span data-ttu-id="44e35-224">L' **archivio contatti unificato** è stato introdotto in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="44e35-224">**Unified contact store** is introduced in Lync Server 2013.</span></span> <span data-ttu-id="44e35-225">L'archivio contatti unificato consente agli utenti di conservare tutte le informazioni di contatto in Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="44e35-225">Unified contact store enables users to keep all their contact information in Exchange 2013.</span></span>
        
        <span data-ttu-id="44e35-226">È necessario assicurarsi che i backup siano aggiornati per gli utenti in termini di archiviazione dei contatti utente nell'archivio contatti unificato o nel server back-end Lync.</span><span class="sxs-lookup"><span data-stu-id="44e35-226">You should make sure that backups are up-to-date for users in terms of whether their user contacts are stored in the unified contact store or on the Lync Back End Server.</span></span> <span data-ttu-id="44e35-227">Gli scenari seguenti illustrano dove la migrazione dei contatti utente all'archivio contatti unificato può causare problemi per il processo di backup e ripristino.</span><span class="sxs-lookup"><span data-stu-id="44e35-227">The following scenarios illustrate where migrating user contacts to the unified contact store can cause issues for the backup and restore process.</span></span>
        
        <span data-ttu-id="44e35-228">**Scenario 1:** I contatti utente vengono migrati nell'archivio contatti unificato e viene eseguito un ripristino da un backup di Lync Server effettuato prima della migrazione dei contatti utente.</span><span class="sxs-lookup"><span data-stu-id="44e35-228">**Scenario 1:** User contacts are migrated to the unified contact store, and a restore is performed from a Lync Server backup taken prior to the migration of user contacts.</span></span> <span data-ttu-id="44e35-229">In questo scenario, l'utente avrà uno stato di contatti obsoleti per un massimo di un giorno fino a quando l'attività di migrazione di Lync Server inizierà a eseguire la migrazione dei contatti utente a Exchange.</span><span class="sxs-lookup"><span data-stu-id="44e35-229">In this scenario, the user will have a state of outdated contacts for up to one day until Lync Server Migration Task begins migrating user contacts to Exchange.</span></span> <span data-ttu-id="44e35-230">Tieni presente che, poiché i contatti utente sono stati precedentemente migrati nell'archivio contatti unificato, verranno usate le informazioni di contatto di Exchange.</span><span class="sxs-lookup"><span data-stu-id="44e35-230">(Note that because the user contacts were previously migrated to the unified contact store, the Exchange contact information will be used).</span></span> <span data-ttu-id="44e35-231">In questo scenario non è necessario alcun intervento dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="44e35-231">No administrator intervention is needed in this scenario.</span></span>
        
        <span data-ttu-id="44e35-232">**Scenario 2:** I contatti degli utenti sono stati archiviati in precedenza nell'archivio contatti unificato, ma sono stati ripristinati.</span><span class="sxs-lookup"><span data-stu-id="44e35-232">**Scenario 2:** User contacts were previously stored in the unified contact store, but then rolled back.</span></span> <span data-ttu-id="44e35-233">Un ripristino viene eseguito da un backup di Lync Server acquisito quando i contatti utente sono stati archiviati nell'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="44e35-233">A restore is performed from a Lync Server backup taken when the user contacts were stored in the unified contact store.</span></span> <span data-ttu-id="44e35-234">In questo scenario, un messaggio di `Error: Incorrect Exchange Version` errore nei registri del server client o Lyss può indicare che si tratta di un problema.</span><span class="sxs-lookup"><span data-stu-id="44e35-234">In this scenario, an error message of `Error: Incorrect Exchange Version` in the client or Lyss server logs may indicate this as an issue.</span></span> <span data-ttu-id="44e35-235">L'utente potrà accedere all'elenco contatti in Lync 2013 direttamente da Exchange, ma lo stato del client non corrisponde allo stato del server Lync.</span><span class="sxs-lookup"><span data-stu-id="44e35-235">The user will be able to access their contact list in Lync 2013 directly from Exchange, but client’s state will not match the Lync Server state.</span></span> <span data-ttu-id="44e35-236">Per risolvere questo problema, un amministratore dovrà eseguire i cmdlet **Invoke-CsUCSRollback** per gli utenti interessati.</span><span class="sxs-lookup"><span data-stu-id="44e35-236">To fix this, an administrator will need to run the **Invoke-CsUCSRollback** cmdlets for the affected users.</span></span>
    
      - <span data-ttu-id="44e35-237">**I dati di archiviazione** possono essere archiviati in Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="44e35-237">**Archiving Data** can be stored in Exchange 2013.</span></span> <span data-ttu-id="44e35-238">Questi dati non sono fondamentali per Lync Server, ma può essere fondamentale per l'organizzazione per scopi normativi.</span><span class="sxs-lookup"><span data-stu-id="44e35-238">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="44e35-239">Se l'archiviazione dei dati è archiviata in Exchange ed è fondamentale per l'organizzazione, seguire le procedure di backup e ripristino di Exchange.</span><span class="sxs-lookup"><span data-stu-id="44e35-239">If archiving data is stored in Exchange and is critical to your organization, then follow Exchange backup and restore procedures.</span></span> <span data-ttu-id="44e35-240">Tieni presente che l'archiviazione dei dati archiviati in Exchange non può essere spostata di nuovo in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="44e35-240">Note that archiving data stored in Exchange cannot be moved back to Lync Server.</span></span> <span data-ttu-id="44e35-241">Inoltre, non è possibile trasferire i dati già archiviati nel database di archiviazione di Lync in Exchange.</span><span class="sxs-lookup"><span data-stu-id="44e35-241">Additionally, there is no way to move data already stored in the Lync archiving database to Exchange.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

