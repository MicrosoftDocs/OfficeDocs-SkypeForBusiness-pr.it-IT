---
title: Note sulla versione di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cf95a95c02ad37abdbf88f235cff2f0d5b0459a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="release-notes-for-lync-server-2013"></a><span data-ttu-id="cdf4a-102">Note sulla versione per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdf4a-102">Release notes for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cdf4a-103">_**Ultimo argomento modificato:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="cdf4a-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="cdf4a-104">Note sulla versione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-104">Welcome to the Lync Server 2013 Release Notes.</span></span> <span data-ttu-id="cdf4a-105">Per informazioni sui problemi noti relativi a Lync Server 2013, vedere questo file.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-105">Refer to this file for information regarding known issues about Lync Server 2013.</span></span>

<div>

## <a name="about-this-document"></a><span data-ttu-id="cdf4a-106">Informazioni sul documento</span><span class="sxs-lookup"><span data-stu-id="cdf4a-106">About this document</span></span>

<span data-ttu-id="cdf4a-107">Questo documento contiene informazioni importanti che è necessario conoscere prima di distribuire e utilizzare Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-107">This document contains important information that you should know before you deploy and use Lync Server 2013.</span></span> <span data-ttu-id="cdf4a-108">Per informazioni dettagliate su Lync Server 2013, vedere la documentazione relativa a [Microsoft Lync server 2013](microsoft-lync-server-2013.md) .</span><span class="sxs-lookup"><span data-stu-id="cdf4a-108">For details about Lync Server 2013, refer to the [Microsoft Lync Server 2013](microsoft-lync-server-2013.md) documentation.</span></span>

<span data-ttu-id="cdf4a-109">In questo documento sono incluse le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-109">This document contains the following sections:</span></span>

  - <span data-ttu-id="cdf4a-110">Client Lync 2013</span><span class="sxs-lookup"><span data-stu-id="cdf4a-110">Lync 2013 client</span></span>

  - <span data-ttu-id="cdf4a-111">Lync Server</span><span class="sxs-lookup"><span data-stu-id="cdf4a-111">Lync Server</span></span>

  - <span data-ttu-id="cdf4a-112">Installazione</span><span class="sxs-lookup"><span data-stu-id="cdf4a-112">Installation</span></span>

  - <span data-ttu-id="cdf4a-113">Mobilità</span><span class="sxs-lookup"><span data-stu-id="cdf4a-113">Mobility</span></span>

  - <span data-ttu-id="cdf4a-114">Conferenza</span><span class="sxs-lookup"><span data-stu-id="cdf4a-114">Conferencing</span></span>

  - <span data-ttu-id="cdf4a-115">VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="cdf4a-115">Enterprise Voice</span></span>

  - <span data-ttu-id="cdf4a-116">Presenza</span><span class="sxs-lookup"><span data-stu-id="cdf4a-116">Presence</span></span>

  - <span data-ttu-id="cdf4a-117">Applicazione Response Group e applicazione Call Park</span><span class="sxs-lookup"><span data-stu-id="cdf4a-117">Response Group Application and Call Park Application</span></span>

  - <span data-ttu-id="cdf4a-118">Pannello di controllo di Lync Server, Generatore di topologie e Strumento di pianificazione</span><span class="sxs-lookup"><span data-stu-id="cdf4a-118">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

  - <span data-ttu-id="cdf4a-119">Localizzazione</span><span class="sxs-lookup"><span data-stu-id="cdf4a-119">Localization</span></span>

  - <span data-ttu-id="cdf4a-120">Copyright</span><span class="sxs-lookup"><span data-stu-id="cdf4a-120">Copyright</span></span>

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a><span data-ttu-id="cdf4a-121">Client Lync 2013</span><span class="sxs-lookup"><span data-stu-id="cdf4a-121">Lync 2013 client</span></span>

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a><span data-ttu-id="cdf4a-122">Il trasferimento di un file in un messaggio istantaneo ha esito negativo se il file è aperto in un'altra applicazione</span><span class="sxs-lookup"><span data-stu-id="cdf4a-122">Transferring a file in an instant message fails if the file is open in another application</span></span>

<span data-ttu-id="cdf4a-123">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-123">**Issue:**</span></span>

<span data-ttu-id="cdf4a-124">Se si tenta di trasferire un file, ad esempio un documento di Word, inserendolo in un messaggio istantaneo a un altro utente Lync, il trasferimento avrà esito positivo, ma potrebbe non essere in grado di trasferire il file.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-124">If you attempt to transfer a file, such as a Word document, by including it in an instant message to another Lync user, the transfer will appear to succeed but may actually fail to transfer the file.</span></span> <span data-ttu-id="cdf4a-125">Nel client Lync verrà visualizzata un'icona per il tipo di file, ma il file non può essere aperto dal destinatario previsto.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-125">An icon for the file type will be displayed in the Lync client, but the file cannot be opened by the intended receiver.</span></span> <span data-ttu-id="cdf4a-126">Non viene visualizzato alcun messaggio di errore che informa che il trasferimento non ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-126">No error message is displayed to inform you that the transfer was not successfull.</span></span>

<span data-ttu-id="cdf4a-127">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-127">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-128">Per ovviare a questo problema, chiudere il file o l'applicazione aperta che è aperta prima di tentare di trasferire il file in un messaggio istantaneo.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-128">To work around this issue, close the open file or application that has it open before attempting to transfer the file in an instant message.</span></span>

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="cdf4a-129">Lync Server</span><span class="sxs-lookup"><span data-stu-id="cdf4a-129">Lync Server</span></span>

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a><span data-ttu-id="cdf4a-130">Se la replica dei dati del servizio di archiviazione di Lync Server non riesce, gli amministratori dovranno controllare i contatori delle prestazioni per gli elementi di coda del servizio di archiviazione</span><span class="sxs-lookup"><span data-stu-id="cdf4a-130">If Lync Server Storage Service data replication fails, administrators will need to check performance counters for stale Storage Service queue items</span></span>

<span data-ttu-id="cdf4a-131">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-131">**Issue:**</span></span>

<span data-ttu-id="cdf4a-132">Il servizio di archiviazione di Lync Server utilizza Windows Fabric per la replica.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-132">The Lync Server Storage Service uses Windows Fabric for replication.</span></span> <span data-ttu-id="cdf4a-133">Se i dati vengono eliminati in un front end server primario, ma l'eliminazione di un server front-end secondario ha esito negativo, ad esempio se è presente un arresto o un errore imprevisto nel front end server, i dati possono essere lasciati indietro e "orfani".</span><span class="sxs-lookup"><span data-stu-id="cdf4a-133">If data is deleted on a primary Front End Server, but the deletion on a secondary Front End Server fails—for example, if there is an unexpected shutdown or error on the Front End Server—data can be left behind and "orphaned."</span></span> <span data-ttu-id="cdf4a-134">I dati orfani possono causare la riduzione dello spazio di unità e la riduzione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-134">The orphaned data can cause performance to degrade and waste drive space.</span></span>

<span data-ttu-id="cdf4a-135">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-135">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-136">Per ovviare a questo problema, se gli eventi\_Lyss\_DB\_Space\_used Error (ID = 32058) e\_Lyss\_DB\_Space\_used Critical (ID = 32059) vengono generati nel registro eventi, gli amministratori dovrebbero controllare il contatore delle prestazioni sul front end server in **ls: Lyss-servizio di archiviazione API** con nome **Lyss-Current numero di elementi di coda non aggiornati del servizio di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-136">To work around this issue, if the events LYSS\_DB\_SPACE\_USED\_ERROR (Id=32058) and LYSS\_DB\_SPACE\_USED\_CRITICAL (Id=32059) are generated in the event log, administrators should check the performance counter on the Front End Server under **LS:LYSS - Storage Service API** with a name of **LYSS - Current number of Storage Service stale queue items**.</span></span> <span data-ttu-id="cdf4a-137">Se il contatore delle prestazioni ha un valore elevato, ad esempio maggiore di 50000, l'amministratore deve eseguire lo strumento CleanuUpStorageServiceData. exe nel Resource Kit di Lync Server 2013, che eliminerà tutti i dati orfani dal pool.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-137">If this performance counter has a high value—for example, greater than 50,000—then the administrator should run the CleanuUpStorageServiceData.exe tool in the Lync Server 2013 Resource Kit, which will delete all orphaned data from the pool.</span></span> <span data-ttu-id="cdf4a-138">Per informazioni dettagliate sullo strumento, vedere la documentazione di Lync Server 2013 Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-138">For details about the tool, see the Lync Server 2013 Resource Kit documentation.</span></span>

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a><span data-ttu-id="cdf4a-139">Ogni volta che viene modificata la configurazione dell'indirizzo IP per un server o un pool, è necessario riavviare i servizi di Lync Server</span><span class="sxs-lookup"><span data-stu-id="cdf4a-139">Whenever the IP Address configuration is changed for a server or pool, Lync Server services need to be restarted</span></span>

<span data-ttu-id="cdf4a-140">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-140">**Issue:**</span></span>

<span data-ttu-id="cdf4a-141">Quando la configurazione dell'indirizzo IP viene modificata per una distribuzione di Lync Server 2013, ad esempio la modifica da IPv4 a stack doppio o da doppio stack a IPv6, non tutti i componenti server raccolgono la modifica della configurazione fino a quando non vengono riavviati i servizi.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-141">When the IP Address configuration is changed for a Lync Server 2013 deployment, such as changing from IPv4 to Dual Stack, or from Dual Stack to Ipv6, not all server components pick up the configuration change until the services are restarted.</span></span>

<span data-ttu-id="cdf4a-142">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-142">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-143">Per ovviare a questo problema, riavviare i servizi Lync Server dopo aver modificato la configurazione dell'indirizzo IP per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-143">To work around this issue, restart Lync Server services after changing the IP Address configuration for the deployment.</span></span> <span data-ttu-id="cdf4a-144">A tale scopo, eseguire i cmdlet seguenti in Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-144">To do so, run the following cmdlets in the Lync Server Management Shell:</span></span>

   ```PowerShell
    Stop-CsWindowsService -graceful
   ```

   ```PowerShell
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a><span data-ttu-id="cdf4a-145">Il cmdlet per le transazioni sintetiche per le conferenze telefoniche con accesso esterno non è più disponibile nel Management Pack di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdf4a-145">The dial-in conferencing synthetic transaction cmdlet is no longer available in the Lync Server 2013 Management Pack</span></span>

<span data-ttu-id="cdf4a-146">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-146">**Issue:**</span></span>

<span data-ttu-id="cdf4a-147">Il cmdlet di transazione sintetica per le conferenze telefoniche con accesso esterno **Test-CsDialInConferencing** non è più disponibile in Lync Server 2013 Management Pack.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-147">The dial-in conferencing synthetic transaction cmdlet **Test-CsDialInConferencing** is no longer available in the Lync Server 2013 Management Pack.</span></span>

<span data-ttu-id="cdf4a-148">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-148">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-149">Utilizzo del cmdlet di transazione sintetica per le conferenze telefoniche con accesso esterno **Test-CsDialInConferencing** è supportato solo internamente a un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-149">Use of the Dial-In Conferencing Synthetic Transaction cmdlet **Test-CsDialInConferencing** is supported only internally to an enterprise.</span></span>

<span data-ttu-id="cdf4a-150">Gli amministratori possono continuare a utilizzare il cmdlet in Lync Server Management Shell per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-150">Administrators may continue to use the cmdlet in Lync Server Management Shell for troubleshooting purposes.</span></span> <span data-ttu-id="cdf4a-151">Se necessario, un'organizzazione può anche sviluppare un Management Pack privato per eseguire il cmdlet internamente.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-151">If required, an enterprise can also develop a private management pack to run the cmdlet internally.</span></span>

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a><span data-ttu-id="cdf4a-152">Il servizio di registrazione centralizzato si interrompe se il traffico di rete viene interrotto quando i file di registro vengono copiati nella condivisione di rete</span><span class="sxs-lookup"><span data-stu-id="cdf4a-152">The Centralized Logging Service stops if network traffic is disrupted when log files are being copied to network share</span></span>

<span data-ttu-id="cdf4a-153">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-153">**Issue:**</span></span>

<span data-ttu-id="cdf4a-154">Quando il servizio di registrazione centralizzato è configurato per l'utilizzo di un percorso di rete (il valore del parametro CacheFileNetworkFolder del cmdlet **Get-CsClsConfiguration** è un percorso UNC valido), i file di registro memorizzati nella cache vengono copiati nella condivisione di rete.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-154">When the Centralized Logging Service is configured to use a network path (the value of the CacheFileNetworkFolder parameter of the **Get-CsClsConfiguration** cmdlet is a valid UNC path), cached log files are copied to the network share.</span></span> <span data-ttu-id="cdf4a-155">Se si verifica un'interruzione del traffico di rete durante la copia dei file, si verificherà un'eccezione che provocherà l'arresto del servizio di registrazione centralizzato.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-155">If there is a disruption in network traffic while the files are being copied, an exception will occur that will cause the centralized logging service to stop.</span></span>

<span data-ttu-id="cdf4a-156">Il servizio è configurato per il riavvio automatico fino a tre volte, quindi il servizio si riprenderà dalle prime tre eccezioni.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-156">The service is configured to automatically restart up to three times, so the service will recover from the first three exceptions.</span></span>

<span data-ttu-id="cdf4a-157">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-157">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-158">Non esiste alcuna soluzione per questo problema.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-158">There is no workaround for this issue.</span></span> <span data-ttu-id="cdf4a-159">Per identificare il problema, monitorare il registro eventi per l'ID evento 7031 da "Service Control Manager" che registra quando il servizio "Lync Server di registrazione centralizzata" ha terminato in modo imprevisto.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-159">To identify the issue, monitor the event log for Event ID 7031 from the "Service Control Manager" that logs when the "Lync Server Centralized Logging Service Agent" service has terminated unexpectedly.</span></span> <span data-ttu-id="cdf4a-160">Se questo accade più di tre volte, riavviare manualmente il servizio utilizzando il cmdlet **Start-CsWindowService** .</span><span class="sxs-lookup"><span data-stu-id="cdf4a-160">If this happens more than three times, manually restart the service by using the **Start-CsWindowService** cmdlet.</span></span>

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a><span data-ttu-id="cdf4a-161">Gli elementi della coda del servizio di archiviazione devono essere importati manualmente</span><span class="sxs-lookup"><span data-stu-id="cdf4a-161">Storage Service Queue Items need to be imported manually</span></span>

<span data-ttu-id="cdf4a-162">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-162">**Issue:**</span></span>

<span data-ttu-id="cdf4a-163">Lync Server 2013 archivia i dati relativi alle conferenze e alla messaggistica istantanea, ad esempio i messaggi archiviati e la registrazione dettagli chiamata (CDR), in un database di ogni Front End Server.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-163">Lync Server 2013 stores data about conferencing and instant messaging, such as archived messages and call detail recording (CDR), on a database on each Front End Server.</span></span> <span data-ttu-id="cdf4a-164">I dati vengono archiviati nel database mentre vengono elaborati prima di essere recapitati alla destinazione prevista.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-164">The data is stored in the database while it is being processed before being delivered to the intended destination.</span></span> <span data-ttu-id="cdf4a-165">Per migliorare le prestazioni, Lync Server 2013 Esporta periodicamente gli elementi della coda dal database locale che non vengono elaborati per un periodo di tempo prolungato e li salva nell'archivio file.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-165">To improve performance, Lync Server 2013 periodically exports the queue items from the local database that are not processed for an extended period of time, and saves them on the file store.</span></span> <span data-ttu-id="cdf4a-166">Se l'archivio file non è disponibile, gli elementi vengono archiviati in ogni Front End Server.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-166">If the file store is unavailable, the items are stored on each Front End Server.</span></span> <span data-ttu-id="cdf4a-167">La stessa operazione si verifica per evitare la perdita di dati durante il failover del pool.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-167">The same operation occurs to prevent data loss during pool failover.</span></span>

<span data-ttu-id="cdf4a-168">Durante l'operazione di esportazione, il servizio di archiviazione di Lync Server registra ogni fase del registro eventi con gli ID evento di 32075 (viene avviata l'operazione full Flush), 32076 (Full Flush è stato completato), 32082 (livello di manutenzione Flush è iniziato), 32083 (livello di manutenzione Flush completata), 32089 (si è verificato un errore a causa del riempimento del database).</span><span class="sxs-lookup"><span data-stu-id="cdf4a-168">During the export operation, the Lync Server Storage Service records every stage in the event log with event IDs of 32075 (full flush operation is started), 32076 (full flush is completed), 32082 (maintenance level flush is started), 32083 (maintenance level flush is completed), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="cdf4a-169">Questi dati non verranno automaticamente riportati nel sistema in modo da essere elaborati e recapitati alla destinazione finale (SQL Server o Exchange Server).</span><span class="sxs-lookup"><span data-stu-id="cdf4a-169">This data will not automatically be imported back to the system to be processed and delivered to its final destination (SQL Server or Exchange Server).</span></span>

<span data-ttu-id="cdf4a-170">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-170">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-171">Per importare i dati nel sistema, gli amministratori dovranno utilizzare lo strumento ImportStorageServiceData in Lync Server Resource Kit, che consente di aggiungere i dati di nuovo nel sistema per essere elaborati e recapitati alla destinazione finale.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-171">To import the data to the system, administrators will need to use the ImportStorageServiceData tool in the Lync Server Resource Kit, which will add the data back into the system to be processed and delivered to its final destination.</span></span>

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a><span data-ttu-id="cdf4a-172">Le ricerche delle query Web della Rubrica non avranno esito positivo se il valore predefinito di UseNormalizationRules viene impostato su false.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-172">Address Book Web Query searches will fail if the default value for UseNormalizationRules is changed to False</span></span>

<span data-ttu-id="cdf4a-173">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-173">**Issue:**</span></span>

<span data-ttu-id="cdf4a-174">Se il valore predefinito di UseNormalizationRules viene impostato su false, le ricerche di query Web della Rubrica non avranno esito positivo.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-174">If the default value for UseNormalizationRules is changed to False, Address Book Web Query searches will fail.</span></span> <span data-ttu-id="cdf4a-175">Dopo la modifica del valore predefinito, gli utenti di Lync client non saranno in grado di utilizzare la query Web della Rubrica di Lync per cercare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-175">After the default value is changed, Lync Client users will not be able to use Lync Address Book web query to search for users.</span></span>

<span data-ttu-id="cdf4a-176">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-176">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-177">Se il valore predefinito per UseNormalizationRules è impostato su false in modo che gli utenti possano utilizzare i numeri di telefono definiti in servizi di dominio Active Directory senza Lync Server 2013 che applica le regole di normalizzazione, risolvere il problema eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-177">If the default value for UseNormalizationRules is set to False so that users can use phone numbers as defined in Active Directory Domain Services without Lync Server 2013 applying normalization rules, work around this issue by doing the following:</span></span>

1.  <span data-ttu-id="cdf4a-178">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-178">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="cdf4a-179">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-179">Do one of the following:</span></span>
    
      - <span data-ttu-id="cdf4a-180">Se la distribuzione include solo server Lync Server 2013, eseguire il seguente cmdlet a livello globale per modificare i valori di UseNormalizationRules e IgnoreGenericRules su true:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-180">If your deployment includes only Lync Server 2013 servers, run the following cmdlet at the global level to change the values for UseNormalizationRules and IgnoreGenericRules to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="cdf4a-181">Se nella distribuzione è inclusa una combinazione di Lync Server 2013 e Lync Server 2010 o Office Communications Server 2007 R2, eseguire il cmdlet seguente e assegnarlo a ogni pool Lync Server 2013 nella topologia:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-181">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="cdf4a-182">Attendere che la replica CMS venga eseguita in tutti i pool.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-182">Wait for CMS replication to occur on all pools.</span></span>

4.  <span data-ttu-id="cdf4a-183">Modificare il file delle regole di normalizzazione del telefono per la distribuzione per cancellare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-183">Modify the phone normalization rules file for your deployment to clear the content.</span></span> <span data-ttu-id="cdf4a-184">Il file si trova nella condivisione file di ogni pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-184">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="cdf4a-185">Se il file non è presente, creare un file vuoto denominato "\_società numeri\_\_di telefono di\_normalizzazione Rules. txt".</span><span class="sxs-lookup"><span data-stu-id="cdf4a-185">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt."</span></span>

5.  <span data-ttu-id="cdf4a-186">Attendere alcuni minuti per tutti i pool Front end per leggere i nuovi file.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-186">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="cdf4a-187">Eseguire il cmdlet seguente in ogni pool di Lync Server 2013 nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-187">Run the following cmdlet on each Lync Server 2013 pool in your deployment.</span></span>
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a><span data-ttu-id="cdf4a-188">L'evento di errore 21054 del server della Rubrica viene generato una volta al giorno per ogni pool Lync 2013</span><span class="sxs-lookup"><span data-stu-id="cdf4a-188">Address Book Server error event 21054 is generated once daily for each Lync 2013 pool</span></span>

<span data-ttu-id="cdf4a-189">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-189">**Issue:**</span></span>

<span data-ttu-id="cdf4a-190">Lync Server 2013 Address Book Server genererà l'evento di errore 21054 una volta al giorno quando si eseguono le operazioni di manutenzione giornaliera.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-190">Lync Server 2013 Address Book Server will generate error event 21054 once every day when performing daily maintenance.</span></span> <span data-ttu-id="cdf4a-191">L'errore viene generato anche ogni volta che un amministratore esegue il cmdlet **Update-csAddressBook** , anche quando l'aggiornamento ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-191">The error is also generated every time an administrator runs the **Update-csAddressBook** cmdlet, even when the update is successful.</span></span> <span data-ttu-id="cdf4a-192">Tuttavia, questo evento di errore può essere ignorato senza problemi quando l'aggiornamento ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-192">However, this error event can safely be ignored when the update is successful.</span></span>

<span data-ttu-id="cdf4a-193">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-193">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-194">Quando si verifica questo evento di errore, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-194">When you encounter this error event, run the following cmdlet:</span></span>

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

<span data-ttu-id="cdf4a-195">Se il cmdlet segnala che non sono presenti oggetti non indicizzati o abbandonati, l'evento di errore 21054 può essere ignorato senza problemi.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-195">If the cmdlet reports that there are no unindexed or abandoned objects, the error event 21054 can be safely ignored.</span></span>

<span data-ttu-id="cdf4a-196">Inoltre, l'indicatore di integrità chiave (KHI) "gli utenti della rubrica correttamente indicizzati" deve essere disattivato in System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-196">Additionally, the Key Health Indicator (KHI) "Address Book Users Correctly Indexed" should be turned off in System Center Operations Manager.</span></span>

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a><span data-ttu-id="cdf4a-197">Le richieste potrebbero non riuscire quando IPv6 è configurato in un pool di server perimetrali</span><span class="sxs-lookup"><span data-stu-id="cdf4a-197">Requests may fail when IPv6 is configured on an Edge pool</span></span>

<span data-ttu-id="cdf4a-198">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-198">**Issue:**</span></span>

<span data-ttu-id="cdf4a-199">Quando IPv6 è configurato in un pool di server perimetrali, alcune richieste al pool di server perimetrali potrebbero avere esito negativo.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-199">When IPv6 is configured on an Edge pool, some requests to the Edge pool may fail.</span></span>

<span data-ttu-id="cdf4a-200">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-200">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-201">Per ovviare a questo problema, non configurare un pool di server perimetrali con IPv6.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-201">To work around this issue, do not configure an Edge pool with IPv6.</span></span>

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a><span data-ttu-id="cdf4a-202">Il cmdlet Invoke-csPoolFailback potrebbe avere esito negativo durante il failback del pool</span><span class="sxs-lookup"><span data-stu-id="cdf4a-202">The invoke-csPoolFailback cmdlet may fail during pool failback</span></span>

<span data-ttu-id="cdf4a-203">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-203">**Issue:**</span></span>

<span data-ttu-id="cdf4a-204">Quando si tenta di eseguire il failover di un pool, il cmdlet **Invoke-csPoolFailback** potrebbe avere esito negativo con l'errore "Impossibile completare il processo di idratazione dopo ripetuti tentativi".</span><span class="sxs-lookup"><span data-stu-id="cdf4a-204">When attempting to fail back a pool, the **invoke-csPoolFailback** cmdlet may fail with the error, "Failed to complete hydration process after repeated attempts."</span></span>

<span data-ttu-id="cdf4a-205">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-205">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-206">Per ovviare a questo problema, eseguire di nuovo il cmdlet e attendere che il cmdlet abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-206">To work around this issue, run the cmdlet again, and wait until the cmdlet succeeds.</span></span> <span data-ttu-id="cdf4a-207">Tenere presente che il processo di failback può richiedere alcuni minuti per il completamento.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-207">Note that the failback process can take several minutes to complete.</span></span> <span data-ttu-id="cdf4a-208">Possono essere necessari fino a 60 minuti per un pool con 20.000 utenti.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-208">It may take up to 60 minutes for a pool with 20,000 users.</span></span>

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a><span data-ttu-id="cdf4a-209">La perdita di dati può verificarsi quando si aggiunge un front end server a un pool già esistente, ovvero ibrido, Skype for business online</span><span class="sxs-lookup"><span data-stu-id="cdf4a-209">Data loss may occur when you add a Front End Server to an already established pool – Hybrid, Skype for Business Online</span></span>

<span data-ttu-id="cdf4a-210">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-210">**Issue:**</span></span>

<span data-ttu-id="cdf4a-211">È possibile che si verifichi questo problema in un ambiente in cui un pool ha più di un front end server e si riavvia uno dei Front End Server oppure si aggiunge un nuovo front end server che precedentemente non faceva parte del pool.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-211">You may encounter this issue in an environment where a pool has more than one Front End Server, and you either restart one of the Front End Servers, or add a new Front End Server that was not previously part of the pool.</span></span>

<span data-ttu-id="cdf4a-212">Gli utenti i cui dati vengono archiviati possono riscontrare una perdita di dati fino a quando non viene stabilita una distribuzione stabile dell'archiviazione dei dati per il pool.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-212">Users whose data is being archived may experience data loss until a stable distribution of data archiving is established for the pool.</span></span> <span data-ttu-id="cdf4a-213">Questo periodo di potenziale perdita di dati è limitato a 15 minuti per le conversazioni da persona a persona e a 30 minuti per le conferenze.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-213">This period of potential data loss is limited to 15 minutes for person-to-person conversations, and 30 minutes for conferences.</span></span>

<span data-ttu-id="cdf4a-214">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-214">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-215">Quando si esegue la manutenzione, invece di avviare Front End Server nel pool uno alla volta, è necessario eseguire il failover del pool in un altro pool e quindi effettuare le attività di manutenzione nei server.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-215">When you perform maintenance, instead of starting Front End Servers in the pool one by one, you should fail over the pool to another pool, and then perform maintenance tasks on the servers.</span></span> <span data-ttu-id="cdf4a-216">È inoltre possibile rendere il servizio non disponibile prima di eseguire le attività di manutenzione e quindi ripristinare la disponibilità al termine della manutenzione.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-216">You can also make the service unavailable before performing maintenance tasks, and then restore availability when maintenance is complete.</span></span>

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a><span data-ttu-id="cdf4a-217">Gli amministratori non possono ottenere il numero di licenziatari utilizzando il cmdlet Get-CsClientAccessLicense</span><span class="sxs-lookup"><span data-stu-id="cdf4a-217">Administrators cannot get licensee count by using the Get-CsClientAccessLicense cmdlet</span></span>

<span data-ttu-id="cdf4a-218">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-218">**Issue:**</span></span>

<span data-ttu-id="cdf4a-219">Gli amministratori non possono ottenere un utilizzo accurato della licenza client utilizzando il cmdlet **Get-CsClientAccessLicense** .</span><span class="sxs-lookup"><span data-stu-id="cdf4a-219">Administrators cannot get accurate client license usage by using the **Get-CsClientAccessLicense** cmdlet.</span></span>

<span data-ttu-id="cdf4a-220">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-220">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-221">Per controllare il tipo di licenza del server, è possibile eseguire il cmdlet **Get-CsService** per recuperare i nomi di dominio completi (FDQNs) di tutti i database.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-221">To check the server license type, you can run the **Get-CsService** cmdlet to retrieve the fully qualified domain names (FDQNs) of all databases.</span></span> <span data-ttu-id="cdf4a-222">Se il nome di dominio completo del server front end è uguale al nome di dominio completo del database back-end, la licenza è una licenza Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-222">If the FQDN of the Front End Server is the same as the FQDN of the back-end database, the license is a Standard edition license.</span></span> <span data-ttu-id="cdf4a-223">In caso contrario, la licenza è una licenza Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-223">Otherwise, the license is an Enterprise edition license.</span></span>

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a><span data-ttu-id="cdf4a-224">Il numero del Licenziatario client non è stato segnalato accuratamente</span><span class="sxs-lookup"><span data-stu-id="cdf4a-224">Client licensee count is not accurately reported</span></span>

<span data-ttu-id="cdf4a-225">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-225">**Issue:**</span></span>

<span data-ttu-id="cdf4a-226">Quando si determinano i conteggi delle licenze client, è possibile che si verifichino le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-226">When determining client license counts, you may experience the following conditions:</span></span>

1.  <span data-ttu-id="cdf4a-227">**Conteggio delle licenze non accurato per gli utenti mobili**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-227">**Inaccurate license count for mobile users**</span></span>
    
    <span data-ttu-id="cdf4a-228">Il conteggio delle licenze si basa sul numero di indirizzi IP univoci per gli utenti basati su dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-228">The license count is based on the number of unique IP addresses for device-based users.</span></span> <span data-ttu-id="cdf4a-229">Il numero di licenze sarà limitato nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-229">The license count will be limited in the following ways:</span></span>
    
      - <span data-ttu-id="cdf4a-230">Le licenze verranno contate se l'indirizzo IP dell'utente cambia durante le sessioni di Lync.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-230">Licenses will be overcounted if the IP address for the user changes during Lync sessions.</span></span> <span data-ttu-id="cdf4a-231">Ciò può verificarsi quando un utente si connette a Lync Server da più di una posizione con un client desktop.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-231">This can occur when a user connects to Lync Server from more than one location with a desktop client.</span></span>
    
      - <span data-ttu-id="cdf4a-232">Le licenze verranno sottovalutate se un utente si connette a un client per dispositivi mobili, perché non è possibile determinare l'indirizzo IP per il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-232">Licenses will be undercounted if a user connects with a mobile client, because the IP address for the device cannot be determined.</span></span>

2.  <span data-ttu-id="cdf4a-233">**Le licenze vengono conteggiate due volte per le chiamate PSTN (Public Switched Telephone Network) al client Lync, le chiamate client Lync alle linee PSTN e le chiamate Lync inoltrate a linee PSTN**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-233">**Licenses are counted twice for public switched telephone network (PSTN) calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="cdf4a-234">Negli scenari seguenti verranno conteggiate due licenze aggiuntive invece di una, in quanto il numero di telefono e l'utente di Lync vengono conteggiati per determinare il numero di licenze utilizzate.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-234">In the following scenarios, two additional licenses will be counted instead of one because both the phone number and the Lync user are counted to determine the number of licenses used.</span></span> <span data-ttu-id="cdf4a-235">Per ottenere dati di licenza accurati, rimuovere manualmente le licenze generate da un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-235">To obtain accurate licensing data, manually remove the licenses generated by a phone number.</span></span>
    
      - <span data-ttu-id="cdf4a-236">Una telefonata PSTN a Lync</span><span class="sxs-lookup"><span data-stu-id="cdf4a-236">A PSTN phone call to Lync</span></span>
    
      - <span data-ttu-id="cdf4a-237">Una chiamata Lync a una linea PSTN</span><span class="sxs-lookup"><span data-stu-id="cdf4a-237">A Lync call to a PSTN line</span></span>
    
      - <span data-ttu-id="cdf4a-238">Chiamata PSTN a Lync e quindi Lync inoltra la chiamata a una linea PSTN.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-238">A PSTN call to Lync, and then Lync forwards the call to a PSTN line.</span></span> <span data-ttu-id="cdf4a-239">Viene conteggiata una delle linee PSTN.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-239">One of the PSTN lines will be counted.</span></span>

3.  <span data-ttu-id="cdf4a-240">**Non viene conteggiata una licenza per un telefono Lync connesso**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-240">**A license will not be counted for a logged-on Lync phone**</span></span>
    
    <span data-ttu-id="cdf4a-241">Quando un utente utilizza un telefono con certificazione Lync, se il telefono entra e rimane connesso, mantenendo lo stato di accesso, il telefono non verrà conteggiato come utilizzo di una licenza se la query per le licenze si verifica dopo che il telefono è connesso.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-241">When a user uses a Lync-certified phone, if the phone logs in and stays connected, which retains its logon status, the phone will not be counted as using a license if the query for licenses occurs after the phone logged in.</span></span>

4.  <span data-ttu-id="cdf4a-242">**Licenze conteggiate per i telefoni PSTN che partecipano alle conferenze**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-242">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="cdf4a-243">Quando un utente entra a far parte di una conferenza con un telefono PSTN, viene conteggiata una licenza per partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-243">When a user joins a conference with a PSTN phone, a license will inaccurately be counted for joining the conference.</span></span> <span data-ttu-id="cdf4a-244">Tuttavia, non è necessaria alcuna licenza per partecipare a una conferenza con un telefono PSTN.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-244">However, no license is needed to join a conference with a PSTN phone.</span></span>

<span data-ttu-id="cdf4a-245">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-245">**Workaround:**</span></span>

1.  <span data-ttu-id="cdf4a-246">**Conteggio delle licenze non accurato per gli utenti mobili**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-246">**Inaccurate license count for mobile users**</span></span>
    
      - <span data-ttu-id="cdf4a-247">È possibile identificare manualmente gli indirizzi IP che appartengono allo stesso dispositivo e quindi rimuoverne uno nel conteggio delle licenze.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-247">You can manually identify the IP addresses that belong to the same device and then remove one of them in the license count.</span></span>
    
      - <span data-ttu-id="cdf4a-248">Non esiste alcuna soluzione per questo problema con i dispositivi mobili che si connettono al client Lync.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-248">There is no workaround for this issue with mobile devices connecting with Lync client.</span></span>

2.  <span data-ttu-id="cdf4a-249">**Le licenze vengono conteggiate due volte per le chiamate PSTN al client Lync, le chiamate client Lync alle linee PSTN e le chiamate Lync inoltrate a linee PSTN**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-249">**Licenses are counted twice for PSTN calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="cdf4a-250">Sarà necessario identificare manualmente il numero di telefono PSTN e rimuovere il conteggio delle licenze generato.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-250">You will need to manually identify the PSTN phone number and remove the license count generated for it.</span></span>

3.  <span data-ttu-id="cdf4a-251">**Non viene conteggiata una licenza per un telefono Lync connesso**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-251">**A license will not be counted for a logged-in Lync phone**</span></span>
    
    <span data-ttu-id="cdf4a-252">È possibile configurare il telefono Lync per disconnettersi e quindi eseguire di nuovo l'accesso, a intervalli regolari, ad esempio ogni 3 mesi.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-252">You can configure the Lync phone to log off, and then log on again, at a regular interval, such as every 3 months.</span></span>

4.  <span data-ttu-id="cdf4a-253">**Licenze conteggiate per i telefoni PSTN che partecipano alle conferenze**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-253">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="cdf4a-254">È possibile identificare manualmente il numero di telefono PSTN utilizzato per partecipare alla conferenza e rimuovere la licenza generata dal numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-254">You can manually identify the PSTN phone number that is used to join the conference and remove the license generated by the phone number.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a><span data-ttu-id="cdf4a-255">Il pannello di controllo di Lync Server smette di funzionare in un ambiente VMware dopo l'aggiornamento a Silverlight 5</span><span class="sxs-lookup"><span data-stu-id="cdf4a-255">The Lync Server Control Panel stops working in a VMware environment after upgrading to Silverlight 5</span></span>

<span data-ttu-id="cdf4a-256">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-256">**Issue:**</span></span>

<span data-ttu-id="cdf4a-257">Se si utilizza il pannello di controllo di Lync Server in un ambiente VMware, è possibile che il pannello di controllo di Lync Server smetta di funzionare dopo l'aggiornamento di Microsoft Silverlight alla versione 5.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-257">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Microsoft Silverlight to version 5.</span></span>

<span data-ttu-id="cdf4a-258">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-258">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-259">Per risolvere questo problema, effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-259">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="cdf4a-260">Disinstallare Silverlight 5 e installare Silverlight 4 da [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156).</span><span class="sxs-lookup"><span data-stu-id="cdf4a-260">Uninstall Silverlight 5, and install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156).</span></span>

  - <span data-ttu-id="cdf4a-261">Accedere al pannello di controllo di Lync Server da un computer che non sia un computer virtuale VMware.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-261">Access the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="cdf4a-262">A tale scopo, è possibile avviare il pannello di controllo di Lync Server dal menu **Start** di Windows nel server, se gli strumenti di amministrazione di Lync Server sono installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-262">To do so, you can start the Lync Server Control Panel from the Windows **Start** menu on the server, if the Lync Server Administration tools are installed on the computer.</span></span>
    
    <span data-ttu-id="cdf4a-263">È inoltre possibile accedere al pannello di controllo di Lync Server tramite un Web browser.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-263">You can also access the Lync Server Control Panel by using a web browser.</span></span> <span data-ttu-id="cdf4a-264">L'URL sarà\<simile a FQDN\_\_\>del pool di front-end di https:///CSCP.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-264">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a><span data-ttu-id="cdf4a-265">Le informazioni degli utenti nel servizio Rubrica non vengono aggiornate dopo che il nome distinto per l'utente è stato modificato in Active Directory</span><span class="sxs-lookup"><span data-stu-id="cdf4a-265">User information in the Address Book Service is not updated after the distinguished name for the user is modified in Active Directory</span></span>

<span data-ttu-id="cdf4a-266">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-266">**Issue:**</span></span>

<span data-ttu-id="cdf4a-267">Se il nome distinto di un utente (noto anche come DN) viene modificato in servizi di dominio Active Directory, eventuali modifiche aggiuntive non verranno aggiornate nel servizio Rubrica (ABS).</span><span class="sxs-lookup"><span data-stu-id="cdf4a-267">If a user’s distinguished name (also known as DN) is changed in Active Directory Domain Services, any additional changes will not be updated in the Address Book Service (ABS).</span></span> <span data-ttu-id="cdf4a-268">Questo non ha effetto sull'accesso o sulla presenza dell'utente, ma impedirà la comunicazione per l'utente se viene modificato anche l'indirizzo SIP, in quanto le ricerche restituiranno un indirizzo SIP obsoleto.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-268">This does not affect sign-in or presence for the user, but it will prevent communication for the user if the SIP address is also changed, because searches will return an outdated SIP address.</span></span>

<span data-ttu-id="cdf4a-269">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-269">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-270">Per ovviare a questo problema, non modificare il DN di un utente.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-270">To work around this issue, do not change a user’s DN.</span></span> <span data-ttu-id="cdf4a-271">Se si ripristina il nome distinto per l'utente al valore precedente, gli aggiornamenti verranno riflessi nel servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-271">If you revert the DN for the user to the previous value, updates will be reflected in the Address Book Service.</span></span>

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a><span data-ttu-id="cdf4a-272">Installazione</span><span class="sxs-lookup"><span data-stu-id="cdf4a-272">Installation</span></span>

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a><span data-ttu-id="cdf4a-273">L'utilizzo di caratteri non ASCII può comportare la mancata avvio di Lync Server</span><span class="sxs-lookup"><span data-stu-id="cdf4a-273">Using non-ASCII characters may result in Lync server failing to start</span></span>

<span data-ttu-id="cdf4a-274">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-274">**Issue:**</span></span>

<span data-ttu-id="cdf4a-275">Il programma di installazione avrà esito negativo se il nome della cartella di destinazione include caratteri non ASCII (inclusi UNICODE, set di caratteri a doppio byte (DBCS), UTF-8 e UTF-16).</span><span class="sxs-lookup"><span data-stu-id="cdf4a-275">Setup will fail if the destination folder name includes non-ASCII characters (including UNICODE, double-byte character set (DBCS), UTF-8, and UTF-16).</span></span> <span data-ttu-id="cdf4a-276">Inoltre, il programma di installazione può avere esito positivo, ma il server non verrà avviato se i caratteri non ASCII sono contenuti in una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-276">In addition, Setup may succeed but the server will not start if non-ASCII characters are contained in any of the following:</span></span>

  - <span data-ttu-id="cdf4a-277">Nome computer</span><span class="sxs-lookup"><span data-stu-id="cdf4a-277">Computer name</span></span>

  - <span data-ttu-id="cdf4a-278">Nome di dominio</span><span class="sxs-lookup"><span data-stu-id="cdf4a-278">Domain name</span></span>

  - <span data-ttu-id="cdf4a-279">Nome utente</span><span class="sxs-lookup"><span data-stu-id="cdf4a-279">User name</span></span>

  - <span data-ttu-id="cdf4a-280">URI SIP dell'utente</span><span class="sxs-lookup"><span data-stu-id="cdf4a-280">User SIP URI</span></span>

  - <span data-ttu-id="cdf4a-281">Nome dell'account del servizio</span><span class="sxs-lookup"><span data-stu-id="cdf4a-281">Service account name</span></span>

<span data-ttu-id="cdf4a-282">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-282">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-283">Utilizzare solo caratteri ASCII nel nome della cartella di destinazione, del nome del computer, del nome di dominio, del nome utente, dell'URI SIP dell'utente e dei nomi degli account di servizio.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-283">Use only ASCII characters in the destination folder name, computer name, domain name, user name, user SIP URI, and service account names.</span></span>

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a><span data-ttu-id="cdf4a-284">L'hotfix per "danneggiamento dell'heap si verifica quando un modulo chiama il metodo InsertEntityBody in IIS 7,5" deve essere installato prima di installare Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdf4a-284">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" must be installed prior to installing Lync Server 2013</span></span>

<span data-ttu-id="cdf4a-285">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-285">**Issue:**</span></span>

<span data-ttu-id="cdf4a-286">L'hotfix per "danneggiamento dell'heap si verifica quando un modulo chiama il metodo InsertEntityBody in IIS[https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)7,5" (), descritto nell'articolo 264886[https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)della Microsoft Knowledge base, deve essere installato prima di installare Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-286">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" ([https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)), described in Microsoft Knowledge Base article 264886 ([https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)), must be installed prior to installing Lync Server 2013.</span></span>

<span data-ttu-id="cdf4a-287">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-287">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-288">Scaricare e installare l'hotfix dall'area download Microsoft all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602).</span><span class="sxs-lookup"><span data-stu-id="cdf4a-288">Download and install the hotfix from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602).</span></span>

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a><span data-ttu-id="cdf4a-289">Lync Server 2013 non è in grado di installare la versione di Windows Server 2012 OS RTM di ITA</span><span class="sxs-lookup"><span data-stu-id="cdf4a-289">Lync Server 2013 fails to install on ITA Windows Server 2012 OS RTM version</span></span>

<span data-ttu-id="cdf4a-290">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-290">**Issue:**</span></span>

<span data-ttu-id="cdf4a-291">L'installazione di Lync Server 2013 ha esito negativo su ITA Windows Server 2012 a causa di un errore di installazione di Windows Fabric.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-291">Lync Server 2013 installation fails on ITA Windows Server 2012 due to Windows Fabric installation failing.</span></span>

<span data-ttu-id="cdf4a-292">L'installazione di Windows Fabric ha esito negativo perché le tracce Fabric vengono create con il formato ora HH: MM: SS.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-292">Windows Fabric installation fails because fabric traces are created with the time format of HH:MM:SS.</span></span> <span data-ttu-id="cdf4a-293">Tuttavia, in ITA Windows Server, il formato dell'ora è HH. MM.SS.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-293">However, in ITA Windows Server, the time format is HH.MM.SS.</span></span>

<span data-ttu-id="cdf4a-294">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-294">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-295">Per ovviare a questo problema, aggiornare il registro di sistema prima di installare Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-295">To work around this issue, update the system registry before installing Lync Server 2013.</span></span> <span data-ttu-id="cdf4a-296">La chiave del registro di sistema che deve essere aggiornata è\_:\\gli utenti di HKEY. STimeFormat\\internazionale\\del\\pannello di controllo predefinito.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-296">The registry key that needs to be updated is: HKEY\_USERS\\.DEFAULT\\Control Panel\\International\\sTimeFormat.</span></span> <span data-ttu-id="cdf4a-297">Per modificare il valore di sTimeFormat in HH: mm: SS, utilizzare l'interfaccia della riga di comando di Windows PowerShell come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-297">Change the value of sTimeFormat to HH:mm:ss by using the Windows PowerShell command-line interface as follows:</span></span>

1.  <span data-ttu-id="cdf4a-298">Avviare Windows PowerShell ed eseguire i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-298">Start Windows PowerShell and run the following cmdlets:</span></span>
    
       ```PowerShell
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```PowerShell
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  <span data-ttu-id="cdf4a-299">Per visualizzare il valore corrente, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-299">To view the current value, run the following cmdlet:</span></span>
    
        Get-itemproperty $a -Name sTimeFormat
    
    <span data-ttu-id="cdf4a-300">Prendere nota del valore corrente per sTimeFormat in modo che possa essere ripristinato al termine dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-300">Make note of the current value for sTimeFormat so it can be restored after the installation is complete.</span></span>

3.  <span data-ttu-id="cdf4a-301">Per impostare il nuovo valore, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-301">To set to new value, run the following cmdlet:</span></span>
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  <span data-ttu-id="cdf4a-302">Dopo che Lync Server 2013 è stato installato correttamente, ripristinare il valore originale di sTimeFormat eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-302">After Lync Server 2013 has been successfully installed, restore the original value for the sTimeFormat by running the following cmdlet:</span></span>
    
        - <span data-ttu-id="cdf4a-303">Set-ItemProperty $a-Name sTimeFormat-value "<valore annotato al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-303">Set-ItemProperty $a -Name sTimeFormat -Value "<Value noted down in Step 3.</span></span> <span data-ttu-id="cdf4a-304">sopra> "</span><span class="sxs-lookup"><span data-stu-id="cdf4a-304">above>"</span></span>

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a><span data-ttu-id="cdf4a-305">Mobilità</span><span class="sxs-lookup"><span data-stu-id="cdf4a-305">Mobility</span></span>

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a><span data-ttu-id="cdf4a-306">Problemi relativi ai client mobili durante il processo di failover del server</span><span class="sxs-lookup"><span data-stu-id="cdf4a-306">Issues for mobile clients during the server failover process</span></span>

<span data-ttu-id="cdf4a-307">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-307">**Issue:**</span></span>

<span data-ttu-id="cdf4a-308">Quando un server Lync ha esito negativo e il processo di failover inizia, i problemi seguenti possono influire sugli utenti dei client mobili:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-308">When a Lync Server fails and the failover process begins, the following issues may affect mobile client users:</span></span>

  - <span data-ttu-id="cdf4a-309">Nessuna chiamata o segnale di Lync in arrivo per un massimo di 10 minuti dopo l'inizio del failover.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-309">No incoming Lync call or signal for up to 10 minutes after failover begins.</span></span>

  - <span data-ttu-id="cdf4a-310">Non è in grado di accettare le richieste chat in arrivo</span><span class="sxs-lookup"><span data-stu-id="cdf4a-310">Cannot accept incoming Chat requests</span></span>

  - <span data-ttu-id="cdf4a-311">Non è possibile partecipare a riunioni se il server non riuscito è il server principale dell'utente</span><span class="sxs-lookup"><span data-stu-id="cdf4a-311">Cannot join meetings if the failed server is the home server for the user</span></span>

<span data-ttu-id="cdf4a-312">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-312">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-313">Non esiste alcuna soluzione per questo problema.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-313">There is no workaround for this issue.</span></span> <span data-ttu-id="cdf4a-314">Una volta completata la procedura di failover, la funzionalità normale verrà ripristinata.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-314">Normal functionality will be restored once the failover process is complete.</span></span>

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a><span data-ttu-id="cdf4a-315">Se un utente mobile rifiuta una chiamata in arrivo da un altro endpoint Lync, la chiamata viene visualizzata come una conversione persa nei client mobili di Lync</span><span class="sxs-lookup"><span data-stu-id="cdf4a-315">If a mobile user declines an incoming call from another Lync endpoint, the call is displayed as a missed conversion on Lync Mobile clients</span></span>

<span data-ttu-id="cdf4a-316">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-316">**Issue:**</span></span>

<span data-ttu-id="cdf4a-317">Se un utente mobile rifiuta una chiamata in arrivo e la chiamata ha avuto origine da un altro endpoint Lync, la chiamata viene visualizzata come una conversazione persa nel client mobile di Lync anziché una chiamata nell'elenco delle chiamate di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-317">If a mobile user declines an incoming call, and the call originated from another Lync endpoint, the call is displayed as a missed conversation in the Lync Mobile client instead of a call in the device call list.</span></span>

<span data-ttu-id="cdf4a-318">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-318">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-319">Non esiste alcuna soluzione per questo problema.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-319">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a><span data-ttu-id="cdf4a-320">Il client per dispositivi mobili potrebbe non visualizzare il nome visualizzato di un contatto federato durante la ricerca di contatti</span><span class="sxs-lookup"><span data-stu-id="cdf4a-320">The mobile client may not display a federated contact’s display name when searching for contacts</span></span>

<span data-ttu-id="cdf4a-321">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-321">**Issue:**</span></span>

<span data-ttu-id="cdf4a-322">Il nome visualizzato per i contatti federati potrebbe non essere visualizzato in alcuni scenari, ad esempio durante la ricerca di un contatto federato nell'elenco dei contatti.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-322">The display name for federated contacts may not be displayed in some scenarios, such as when searching for a federated contact in the contact list.</span></span> <span data-ttu-id="cdf4a-323">Questo problema può verificarsi quando non è presente alcuna sottoscrizione di presenza attiva per il contatto dal client di Lync mobile.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-323">This can occur when the there is no active presence subscription for the contact from the Lync mobile client.</span></span>

<span data-ttu-id="cdf4a-324">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-324">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-325">Non esiste alcuna soluzione per questo problema.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-325">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a><span data-ttu-id="cdf4a-326">Nel client per dispositivi mobili, le informazioni sull'invito e sul timestamp sono mancanti da una conversazione persa che è un invito a una conferenza</span><span class="sxs-lookup"><span data-stu-id="cdf4a-326">In the mobile client, invitee and timestamp information are missing from a missed conversation that is an invitation to a conference</span></span>

<span data-ttu-id="cdf4a-327">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-327">**Issue:**</span></span>

<span data-ttu-id="cdf4a-328">Nel client per dispositivi mobili, quando una conversazione persa è un invito a una conferenza, le informazioni sull'invito e sul timestamp sono mancanti dal messaggio di conversazione persa.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-328">In the mobile client, when a missed conversation is an invitation to a conference, the invitee and timestamp information is missing from the missed conversation message.</span></span>

<span data-ttu-id="cdf4a-329">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-329">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-330">Non esiste alcuna soluzione per questo problema.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-330">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a><span data-ttu-id="cdf4a-331">Gli utenti di client mobili che effettuano chiamate tramite VoIP non sono in grado di lasciare la segreteria telefonica per gli utenti la cui segreteria telefonica è configurata in Exchange 2010 o versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="cdf4a-331">Mobile client users making calls using VoIP are not be able to leave voice mail for users whose voice mail is configured in Exchange 2010 or earlier versions</span></span>

<span data-ttu-id="cdf4a-332">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-332">**Issue:**</span></span>

<span data-ttu-id="cdf4a-333">Se un utente di client mobili utilizza VoIP per effettuare chiamate, l'utente non sarà in grado di lasciare messaggi di segreteria telefonica per gli utenti configurati per l'utilizzo della segreteria telefonica in Microsoft Exchange Server 2007 o Microsoft Exchange Server 2010.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-333">If a mobile client user is using VoIP to place calls, the user will not be able to leave voice mail messages for users configured to use voice mail in Microsoft Exchange Server 2007 or Microsoft Exchange Server 2010.</span></span>

<span data-ttu-id="cdf4a-334">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-334">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-335">Per ovviare a questo problema, utilizzare Exchange 2010 con SP1 o versione successiva di Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-335">To work around this issue, use Exchange 2010 with SP1 or later version of Microsoft Exchange Server.</span></span>

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a><span data-ttu-id="cdf4a-336">Quando si utilizza il blocco con l'URL per la configurazione della versione client sui client mobili, potrebbe essere visualizzato un messaggio di errore non corretto</span><span class="sxs-lookup"><span data-stu-id="cdf4a-336">When using Block with URL for Client Version Configuration on mobile clients, an incorrect error message may be displayed</span></span>

<span data-ttu-id="cdf4a-337">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-337">**Issue:**</span></span>

<span data-ttu-id="cdf4a-338">Quando si utilizza il **blocco con l'URL** per la configurazione della versione client nei client mobili, è possibile che venga visualizzato un messaggio di errore non corretto quando la versione client non è supportata.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-338">When using **Block with URL** for Client Version Configuration on mobile clients, an incorrect error message may be displayed when the client version is not supported.</span></span>

<span data-ttu-id="cdf4a-339">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-339">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-340">Per ovviare a questo problema, configurare la configurazione della versione client in modo da utilizzare **Block** anziché **Block con URL**.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-340">To work around this issue, configure Client Version Configuration to use **Block** instead of **Block with URL**.</span></span>

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a><span data-ttu-id="cdf4a-341">Conferenza</span><span class="sxs-lookup"><span data-stu-id="cdf4a-341">Conferencing</span></span>

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a><span data-ttu-id="cdf4a-342">Il software antivirus in esecuzione nei server front end di Lync Server 2013 può causare il riciclo dei domini applicazione, che interrompe temporaneamente il servizio per Lync Web App 2013, Lync Mobile 2010 e i client Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="cdf4a-342">Antivirus software running on Lync Server 2013 Front End Servers can cause Application Domain recycling, which temporarily interrupts service for Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013 clients</span></span>

<span data-ttu-id="cdf4a-343">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-343">**Issue:**</span></span>

<span data-ttu-id="cdf4a-344">Il software antivirus può attivare il riavvio del dominio dell'applicazione, che può comportare la perdita dello stato del servizio Lync Mobility Service 2013 e delle applicazioni client API Web per le comunicazioni unificate (Lync Web App 2013, Lync Mobile 2010 e Lync Mobile 2013).</span><span class="sxs-lookup"><span data-stu-id="cdf4a-344">Antivirus software can trigger application domain restarts, which can result in Lync Mobility Service 2013 and unified communications (UC) Web API client applications (Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013) to lose their state.</span></span>

<span data-ttu-id="cdf4a-345">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-345">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-346">Per ovviare a questo problema, escludere le cartelle contenenti componenti Web e .NET Framework dall'analisi antivirus.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-346">To work around this issue, exclude the folders containing Web components and .NET framework from antivirus scanning.</span></span> <span data-ttu-id="cdf4a-347">Per ulteriori informazioni, vedere l'articolo 312592 della Microsoft Knowledge Base "PRB: riavviamenti di applicazioni casuali con" applicazione di riavvio "in ASP.NET, [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592)" at.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-347">For details, see Microsoft Knowledge Base article 312592, "PRB: Random application restarts with 'Application is restarting' error in ASP.NET," at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592).</span></span>

<span data-ttu-id="cdf4a-348">Le cartelle seguenti devono essere escluse:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-348">The following folders should be excluded:</span></span>

  - <span data-ttu-id="cdf4a-349">% ProgramFiles%\\Microsoft Lync Server 2013\\Web\\Components\\MCX EXT</span><span class="sxs-lookup"><span data-stu-id="cdf4a-349">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Ext</span></span>

  - <span data-ttu-id="cdf4a-350">% ProgramFiles%\\Microsoft Lync Server 2013\\Web\\Components\\MCX int</span><span class="sxs-lookup"><span data-stu-id="cdf4a-350">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Int</span></span>

  - <span data-ttu-id="cdf4a-351">% ProgramFiles%\\Microsoft Lync Server 2013\\Web\\Components\\UCWA int</span><span class="sxs-lookup"><span data-stu-id="cdf4a-351">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Int</span></span>

  - <span data-ttu-id="cdf4a-352">% ProgramFiles%\\Microsoft Lync Server 2013\\Web\\Components\\UCWA EXT</span><span class="sxs-lookup"><span data-stu-id="cdf4a-352">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Ext</span></span>

  - <span data-ttu-id="cdf4a-353">% WINDIR%\\Microsoft.NET\\Framework64\\v 4.0.30319\\config</span><span class="sxs-lookup"><span data-stu-id="cdf4a-353">%Windir%\\Microsoft.NET\\Framework64\\v4.0.30319\\Config</span></span>

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a><span data-ttu-id="cdf4a-354">I controlli ActiveX o il supporto nativo di XMLHTTP devono essere abilitati in Windows Internet Explorer per partecipare a conferenze con esito positivo</span><span class="sxs-lookup"><span data-stu-id="cdf4a-354">ActiveX Controls or native XMLHTTP support must be enabled in Windows Internet Explorer to successfully join conferences</span></span>

<span data-ttu-id="cdf4a-355">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-355">**Issue:**</span></span>

<span data-ttu-id="cdf4a-356">Se un utente ha disabilitato sia i controlli ActiveX sia il supporto nativo di XMLHTTP nelle impostazioni del browser Internet di Windows Internet Explorer, l'utente non sarà in grado di partecipare a una riunione se Internet Explorer è selezionato come browser predefinito.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-356">If a user has disabled both ActiveX Controls and native XMLHTTP support in Windows Internet Explorer Internet browser settings, the user will not be able to join a meeting if Internet Explorer is selected as the default browser.</span></span>

<span data-ttu-id="cdf4a-357">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-357">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-358">Abilitare i controlli ActiveX o "supporto nativo di XMLHTTP" in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-358">Enable either ActiveX Controls or "native XMLHTTP support" in Internet Explorer.</span></span>

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a><span data-ttu-id="cdf4a-359">Il servizio Web Conferencing di Lync Server non può essere ripristinato dalla modalità critica</span><span class="sxs-lookup"><span data-stu-id="cdf4a-359">Lync Server Web Conferencing service cannot recover from critical mode</span></span>

<span data-ttu-id="cdf4a-360">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-360">**Issue:**</span></span>

<span data-ttu-id="cdf4a-361">Se la modalità critica è attivata per l'archiviazione, in caso di errori di sistema, la modalità critica inizierà e le conferenze non funzioneranno più per i partecipanti.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-361">If critical mode is turned for archiving, in case of system failures, critical mode will start and the conferences will no longer work for the participants.</span></span> <span data-ttu-id="cdf4a-362">Dopo che l'amministratore ha risolto gli errori del sistema, ad esempio la risoluzione di un problema di database, il servizio di conferenza dati non viene ripristinato automaticamente e l'amministratore deve riavviare manualmente il servizio di conferenza per le conferenze da riprendere.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-362">After the administrator fixes the system failures (such as fixing a database issue), the data conferencing service doesn't automatically recover, and the administrator must manually restart the conferencing service for conferencing to resume.</span></span>

<span data-ttu-id="cdf4a-363">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-363">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-364">Un amministratore deve riavviare manualmente il servizio di conferenza dopo che è stato risolto il problema del sistema.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-364">An administrator needs to manually restart the conferencing service after the system failure is fixed.</span></span>

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a><span data-ttu-id="cdf4a-365">Il servizio Web Conferencing ignora il proxy HTTP per i server Office Web App esterni</span><span class="sxs-lookup"><span data-stu-id="cdf4a-365">Web Conferencing service ignores the HTTP proxy for external Office Web App Servers</span></span>

<span data-ttu-id="cdf4a-366">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-366">**Issue:**</span></span>

<span data-ttu-id="cdf4a-367">Se è stato distribuito un server Office Web Apps esterno al servizio Web Conferencing (ovvero un server che non è presente nella rete aziendale interna) in Internet, la rete perimetrale e il servizio Web Conferencing richiede un proxy HTTP per connettersi a questo, il L'individuazione del server Office Web Apps avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-367">If you have deployed an Office Web Apps Server external to the Web Conferencing service (that is, a server that is not in the internal corporate network) in the Internet, perimeter network, and the Web Conferencing service requires an HTTP proxy to connect to this, the Office Web Apps Server discovery will fail.</span></span> <span data-ttu-id="cdf4a-368">Il servizio Web Conferencing ignora l'impostazione del proxy HTTP, come definito in Generatore di topologie per il programma di installazione del server Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-368">The Web Conferencing service ignores the HTTP proxy setting, as defined in Topology Builder for Office Web Apps Server setup.</span></span> <span data-ttu-id="cdf4a-369">Di conseguenza, il client Lync non sarà in grado di eseguire la condivisione di Microsoft PowerPoint 2010 con altri partecipanti alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-369">As a result, the Lync client will not be able to do Microsoft PowerPoint 2010 sharing with other participants in the conference.</span></span> <span data-ttu-id="cdf4a-370">Se si sta installando Lync Server in locale e si configura anche il server Office Web Apps in locale nella rete interna, non è necessaria una configurazione proxy.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-370">If you are installing Lync Server on-premises and also configure Office Web Apps Server on-premises in the internal network, a proxy configuration is not required.</span></span>

<span data-ttu-id="cdf4a-371">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-371">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-372">L'unica soluzione alternativa consiste nel non disporre di una configurazione di distribuzione che richiede l'utilizzo del proxy HTTP per comunicare con un server Office Web Apps esterno.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-372">The only workaround is to not have a deployment configuration that requires the use of HTTP proxy to communicate with an external Office Web Apps Server.</span></span>

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a><span data-ttu-id="cdf4a-373">L'aggiunta di video a una conferenza di un provider di servizi di audioconferenza non è supportata</span><span class="sxs-lookup"><span data-stu-id="cdf4a-373">Adding video to an audio conferencing provider conference is not supported</span></span>

<span data-ttu-id="cdf4a-374">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-374">**Issue:**</span></span>

<span data-ttu-id="cdf4a-375">L'aggiunta di un video non è supportata se l'utente è aggiunto a una conferenza di un provider di servizi di audioconferenza per l'audio.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-375">Adding a video is not supported if the user is joined to an audio conferencing provider conference for audio.</span></span>

<span data-ttu-id="cdf4a-376">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-376">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-377">Non esiste alcuna soluzione per questo problema.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-377">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a><span data-ttu-id="cdf4a-378">Topologie con IPv6 abilitato forzare l'aggiornamento automatico del plug-in Silverlight di Lync Web App per garantire che le funzionalità di condivisione dello schermo possano funzionare da Lync Web App</span><span class="sxs-lookup"><span data-stu-id="cdf4a-378">Topologies with IPv6 enabled force the Lync Web App Silverlight plug-in auto-update to ensure screen sharing functionality can work from Lync Web App</span></span>

<span data-ttu-id="cdf4a-379">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-379">**Issue:**</span></span>

<span data-ttu-id="cdf4a-380">Quando una topologia è configurata con IPv6 abilitato, gli utenti non possono condividere la propria schermata dal client Lync Web App se è già installata una versione precedente del plug-in di condivisione dello schermo.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-380">When a topology is configured with IPv6 enabled, users cannot share their screen from the Lync Web App client if an earlier version of the screen-sharing plug-in is already installed.</span></span>

<span data-ttu-id="cdf4a-381">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-381">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-382">Per forzare un aggiornamento alla versione più recente del plug-in di condivisione dello schermo quando si accede a una riunione tramite Lync Web App, modificare il valore di **MinSupportedBuildVersion** da "4.0.7457.0" a "4.0.7577.380" in entrambi i file seguenti:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-382">To force an update to the most recent version of the screen-sharing plug-in when joining meeting via Lync Web App, modify the value of **MinSupportedBuildVersion** from "4.0.7457.0" to "4.0.7577.380" in both of the following files:</span></span>

  - <span data-ttu-id="cdf4a-383">% ProgramFiles%\\Microsoft Lync Server 15\\Web\\Components\\REACH\\int\\plugins\\client ReachAppShPluginProperties. XML</span><span class="sxs-lookup"><span data-stu-id="cdf4a-383">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Int\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

  - <span data-ttu-id="cdf4a-384">% ProgramFiles%\\Microsoft Lync Server 15\\Web\\Components\\REACH\\ext\\client\\plugins ReachAppShPluginProperties. XML</span><span class="sxs-lookup"><span data-stu-id="cdf4a-384">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Ext\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a><span data-ttu-id="cdf4a-385">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="cdf4a-385">Enterprise Voice</span></span>

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a><span data-ttu-id="cdf4a-386">In alcuni casi, un client Lync in esecuzione su un computer configurato per l'utilizzo di IPv4 e IPv6 dual stack potrebbe non supportare funzionalità che si basano sulla subnet IP del computer, ad esempio E911, bypass multimediale, controllo di ammissione di chiamata e routing basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="cdf4a-386">In some cases, a Lync client running on a computer configured to use IPv4 and IPv6 dual stack might not support capabilities that rely in the IP subnet of the computer such as E911, Media Bypass, Call Admission Control and Location Based Routing</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="cdf4a-387">Le informazioni contenute in questa sezione riguardano gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-387">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="cdf4a-388">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-388">**Issue:**</span></span>

<span data-ttu-id="cdf4a-389">Quando un client Lync è in esecuzione in un computer abilitato per IPv4 e IPv6 dual stack e basato sulla risoluzione DNS del server proxy, il client può utilizzare l'indirizzo IPv6 del computer per l'accesso.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-389">When a Lync client is running on a computer that is enabled for IPv4 and IPv6 dual stack and based on the DNS resolution of the proxy server, the client may use the IPv6 address of the computer to sign in.</span></span> <span data-ttu-id="cdf4a-390">Dopo tale operazione, il client Lync supporterà solo le funzionalità supportate per IPv6, che esclude E911, il bypass multimediale, il controllo di ammissione di chiamata e il routing in base alla posizione.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-390">After doing so, the Lync Client will support only the capabilities supported for IPv6, which excludes E911, Media Bypass, Call Admission Control and Location Based Routing.</span></span>

<span data-ttu-id="cdf4a-391">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-391">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-392">Per ovviare a questo problema, disabilitare il supporto IPv6 sul computer client.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-392">To work around this issue, disable IPv6 support on the client computer.</span></span>

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a><span data-ttu-id="cdf4a-393">Se VoIP aziendale non è configurato per un utente, l'utente dovrà utilizzare il formato E164 per effettuare una chiamata in uscita da una conferenza.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-393">If Enterprise Voice is not configured for a user, the user will need to use E164 format to dial out from a conference</span></span>

<span data-ttu-id="cdf4a-394">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-394">**Issue:**</span></span>

<span data-ttu-id="cdf4a-395">Se VoIP aziendale non è configurato per un utente, sarà necessario utilizzare il formato E164 per effettuare una chiamata in uscita da una conferenza.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-395">If Enterprise Voice is not configured for a user, that user will need to use the E164 format to successfully dial out from a conference.</span></span> <span data-ttu-id="cdf4a-396">Se non si utilizza il formato E164, l'utente non sarà in grado di eseguire la chiamata in uscita dalla conferenza.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-396">If the E164 format is not used, the user will not be able to dial out from the conference.</span></span>

<span data-ttu-id="cdf4a-397">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-397">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-398">Per ovviare a questo problema, gli utenti che non sono abilitati per VoIP aziendale devono eseguire la chiamata in uscita da una conferenza utilizzando numeri nel formato E164.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-398">To work around this issue, users who are not enabled for Enterprise Voice should dial out from a conference by using numbers in the E164 format.</span></span>

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a><span data-ttu-id="cdf4a-399">Presenza</span><span class="sxs-lookup"><span data-stu-id="cdf4a-399">Presence</span></span>

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a><span data-ttu-id="cdf4a-400">Se un utente ha selezionato "blocca tutti gli inviti e le comunicazioni" mentre l'archivio contatti unificato è attivato per l'utente, lo stato presenza non è rifiutato quando dovrebbe esserlo.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-400">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be</span></span>

<span data-ttu-id="cdf4a-401">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-401">**Issue:**</span></span>

<span data-ttu-id="cdf4a-402">Se un utente ha selezionato "blocca tutti gli inviti e le comunicazioni" mentre l'archivio contatti unificato è attivato per l'utente, lo stato presenza non è rifiutato quando dovrebbe esserlo.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-402">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be.</span></span>

<span data-ttu-id="cdf4a-403">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-403">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-404">Per ovviare a questo problema, è possibile disattivare l'archivio contatti unificato per l'utente.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-404">To work around this issue, you can turn off the unified contact store for the user.</span></span> <span data-ttu-id="cdf4a-405">A tale scopo, eseguire i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-405">To do so, run the following cmdlets:</span></span>

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

<span data-ttu-id="cdf4a-406">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-406">For example:</span></span>

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a><span data-ttu-id="cdf4a-407">Gli utenti di Office Communications Server 2007 R2 ospitati in locale non sono in grado di visualizzare lo stato di presenza degli utenti di Skype for business online nelle distribuzioni ibride-ibrido</span><span class="sxs-lookup"><span data-stu-id="cdf4a-407">Office Communications Server 2007 R2 users homed on-premises are not able to see the Presence status of Skype for Business Online users in hybrid deployments - Hybrid</span></span>

<span data-ttu-id="cdf4a-408">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-408">**Issue:**</span></span>

<span data-ttu-id="cdf4a-409">È possibile che il problema si verifichi in una distribuzione ibrida quando si utilizza un Director di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-409">The issue may occur in a hybrid deployment when you are using a Lync Server 2013 Director.</span></span>

<span data-ttu-id="cdf4a-410">Lo stato di presenza per gli utenti ospitati in Skype for business online viene visualizzato come presenza sconosciuta per gli utenti locali.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-410">Presence status for users homed to Skype for Business Online is displayed as Presence Unknown for on-premises users.</span></span> <span data-ttu-id="cdf4a-411">Inoltre, gli utenti ospitati in Skype for business online non sono in grado di visualizzare lo stato di presenza per gli utenti locali di Office Communications Server R2.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-411">Also, users homed to Skype for Business Online are not able to see presence status for Office Communications Server R2 on-premises users.</span></span>

<span data-ttu-id="cdf4a-412">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-412">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-413">Per ovviare a questo problema, cambiare il server principale (msRTCSIP-presencehomeserver) degli utenti di Skype for business online in modo che puntino a un pool locale di Lync Server 2013 anziché al server Director di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-413">To partially work around this issue, change the Home Server (msrtcsip-presencehomeserver) of the Skype for Business Online users to point to a Lync Server 2013 on-premises pool instead of the Lync Server 2013 Director.</span></span> <span data-ttu-id="cdf4a-414">È possibile modificare questa impostazione nel front end server locale.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-414">You can modify this setting on the on-premises Front End Server.</span></span>

<span data-ttu-id="cdf4a-415">Questa soluzione consente di visualizzare correttamente lo stato di presenza degli utenti ospitati in Office Communications Server 2007 R2 per gli utenti di Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-415">This workaround will correctly display the Presence status of users homed to Office Communications Server 2007 R2 to Skype for Business Online users.</span></span>

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a><span data-ttu-id="cdf4a-416">Applicazione Response Group, applicazione Parcheggio di chiamata e raccolta di chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="cdf4a-416">Response Group application, Call Park application, and Group Call Pickup</span></span>

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a><span data-ttu-id="cdf4a-417">Un chiamante potrebbe udire un secondo di musica in attesa durante la creazione di una chiamata con la parte di recupero</span><span class="sxs-lookup"><span data-stu-id="cdf4a-417">A caller might hear one second of music-on-hold during the establishment of a call with the retrieving party</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="cdf4a-418">Le informazioni contenute in questa sezione riguardano gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-418">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="cdf4a-419">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-419">**Issue:**</span></span>

<span data-ttu-id="cdf4a-420">Quando viene recuperata una chiamata tramite il prelievo delle chiamate di gruppo, il chiamante può udire un secondo di musica durante l'esecuzione della chiamata con la parte Retriever.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-420">When a call is retrieved via Group Call Pickup, the caller might hear one second of music-on-hold during the establishment of the call with the retriever party.</span></span>

<span data-ttu-id="cdf4a-421">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-421">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-422">Non esiste alcuna soluzione per questo problema.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-422">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a><span data-ttu-id="cdf4a-423">Un agente di Response Group può accedere e disconnettersi tramite una console di agente Lync Server 2010 ai soli gruppi di agenti formali di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-423">A Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only</span></span>

<span data-ttu-id="cdf4a-424">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-424">**Issue:**</span></span>

<span data-ttu-id="cdf4a-425">Un agente di Response Group di Lync Server 2013 può accedere e disconnettersi tramite una console di agente di Lync Server 2010 ai soli gruppi di agenti formali di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-425">A Lync Server 2013 Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only.</span></span> <span data-ttu-id="cdf4a-426">Nella console di agente Lync Server 2010 gli utenti possono visualizzare solo il Response Group di Lync Server 2010 a cui appartengono.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-426">In the Lync Server 2010 Agent Console, users can see only the Lync Server 2010 Response Group that they belong to.</span></span> <span data-ttu-id="cdf4a-427">Non è possibile visualizzare nessuno dei gruppi di risposta di Lync Server 2013 a cui appartengono.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-427">They cannot see any of the Lync Server 2013 Response Groups that they belong to.</span></span>

<span data-ttu-id="cdf4a-428">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-428">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-429">Se l'agente Response Group è un utente di Lync Server 2013 e parte di un gruppo di agenti formali di Lync Server 2013, l'utente deve accedere alla console di agente di Lync Server 2013 direttamente tramite un collegamento Web in un browser per accedere e disconnettersi dai gruppi di agenti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-429">If the Response Group agent is a Lync Server 2013 user, and part of a Lync Server 2013 formal Agent Group, the user must access the Lync Server 2013 Agent Console directly via a web link in a browser to sign in to and sign out from Lync Server 2013 Agent Groups.</span></span>

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a><span data-ttu-id="cdf4a-430">Un agente di Response Group di Lync Server 2010 non è in grado di effettuare chiamate per conto di un Response Group di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdf4a-430">A Lync Server 2010 Response Group agent cannot place calls on behalf of a Lync Server 2013 Response Group</span></span>

<span data-ttu-id="cdf4a-431">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-431">**Issue:**</span></span>

<span data-ttu-id="cdf4a-432">Un utente di Lync Server 2010 che è un agente di un Response Group di Lync Server 2013 non è in grado di effettuare una chiamata per conto del Response Group.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-432">A Lync Server 2010 user who is an Agent of a Lync Server 2013 Response Group is not able to place a call on behalf of the Response Group.</span></span> <span data-ttu-id="cdf4a-433">Il Response Group di Lync Server 2013 non sarà disponibile nel client Lync per effettuare una chiamata.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-433">The Lync Server 2013 Response Group will not be available in the Lync Client to place a call.</span></span>

<span data-ttu-id="cdf4a-434">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-434">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-435">Per ovviare a questo problema, è necessario spostare l'utente di Lync Server 2010 in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-435">To work around this issue, you must move the Lync Server 2010 user to Lync Server 2013.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a><span data-ttu-id="cdf4a-436">La rimozione di un Response Group da Lync Server 2010 dopo che è stata eseguita la migrazione a Lync Server 2013 impedirà al Response Group di accettare le chiamate in arrivo</span><span class="sxs-lookup"><span data-stu-id="cdf4a-436">Removing a Response Group from Lync Server 2010 after it has been migrated to Lync Server 2013 will prevent the Response Group from accepting any incoming calls</span></span>

<span data-ttu-id="cdf4a-437">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-437">**Issue:**</span></span>

<span data-ttu-id="cdf4a-438">Se un Response Group di cui è stata eseguita la migrazione da Lync Server 2010 a Lync Server 2013 è stato rimosso da Lync Server 2010 tramite il pannello di controllo di Lync Server o Lync Server Management Shell, il Response Group in Lync Server 2013 smetterà di ricevere chiamate in arrivo.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-438">If a Response Group that has been migrated from Lync Server 2010 to Lync Server 2013 is removed from Lync Server 2010 through the Lync Server Control Panel or the Lync Server Management Shell, the Response Group in Lync Server 2013 will stop receiving any incoming calls.</span></span>

<span data-ttu-id="cdf4a-439">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-439">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-440">Per ovviare a questo problema, non rimuovere i Response Group da Lync Server 2010 che sono stati migrati da Lync Server 2010 a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-440">To work around this issue, do not remove any Response Groups from Lync Server 2010 that have been migrated from Lync Server 2010 to Lync Server 2013.</span></span>

<span data-ttu-id="cdf4a-441">Se il Response Group è già stato rimosso, è necessario ridistribuirlo in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-441">If the Response Group has already been removed, you should redeploy it in Lync Server 2013.</span></span>

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a><span data-ttu-id="cdf4a-442">Quando un nuovo flusso di lavoro gestito è impostato su inattivo al momento della creazione, la distribuzione del flusso di lavoro avrà esito negativo</span><span class="sxs-lookup"><span data-stu-id="cdf4a-442">When a new managed workflow is set to inactive when created, deployment of the workflow will fail</span></span>

<span data-ttu-id="cdf4a-443">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-443">**Issue:**</span></span>

<span data-ttu-id="cdf4a-444">Quando un nuovo flusso di lavoro gestito è impostato su inattivo al momento della creazione, la distribuzione del flusso di lavoro avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-444">When a new managed workflow is set to inactive when created, deployment of the workflow will fail.</span></span> <span data-ttu-id="cdf4a-445">Questo problema si verifica quando il flusso di lavoro è impostato su inattivo quando viene creato, ma non influisce su un flusso di lavoro modificato per impostarlo su inattivo dopo che è stato distribuito.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-445">This issue is encountered when the workflow is set to inactive when created, but does not affect a workflow that is edited to set it to inactive after is has been deployed.</span></span>

<span data-ttu-id="cdf4a-446">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-446">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-447">Durante la creazione e la distribuzione di un flusso di lavoro, impostare il flusso di lavoro come attivo e quindi distribuirlo.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-447">When creating and deploying a workflow, set the workflow as active and then deploy it.</span></span> <span data-ttu-id="cdf4a-448">Dopo la distribuzione del flusso di lavoro, è possibile modificare il flusso di lavoro e impostarlo su inattivo.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-448">After the workflow is successfully deployed, the workflow can be edited and set to inactive.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a><span data-ttu-id="cdf4a-449">Se il Response Group è stato importato nel pool di backup, la rimozione di un Response Group dal pool del proprietario impedirà al gruppo di risposta del pool di backup di accettare le chiamate in arrivo durante il failover.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-449">Removing a Response Group from the Owner pool will prevent the Response Group of the Backup pool from accepting any incoming calls during failover if the Response Group has been imported to the Backup pool</span></span>

<span data-ttu-id="cdf4a-450">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-450">**Issue:**</span></span>

<span data-ttu-id="cdf4a-451">Se un Response Group di proprietà del pool primario è stato importato nel pool di backup senza sovrascrivere il proprietario e il Response Group è stato rimosso dal pool di proprietari, il Response Group nel pool di backup non accetterà chiamate in arrivo durante il failover.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-451">If a Response Group that is owned by the primary pool has been imported to the backup pool without overwriting the owner, and the Response Group is removed from the owner pool, the Response Group in the Backup pool will not accept any incoming calls during failover.</span></span>

<span data-ttu-id="cdf4a-452">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-452">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-453">Sarà necessario ridistribuire il Response Group nel pool primario.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-453">You will need to redeploy the Response Group in the Primary pool.</span></span> <span data-ttu-id="cdf4a-454">Sarà quindi necessario esportare la configurazione di Response Group dal pool primario e importarla di nuovo nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-454">You will then need to export the Response Group configuration from the Primary pool and import it to the Backup pool again.</span></span>

<span data-ttu-id="cdf4a-455">È inoltre possibile ricreare il Response Group nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-455">You can also recreate the Response Group in the Backup pool.</span></span> <span data-ttu-id="cdf4a-456">In questo caso, il pool di backup sarà il pool proprietario del Response Group.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-456">In this case, the Backup pool will be the owner pool of the Response Group.</span></span>

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a><span data-ttu-id="cdf4a-457">Non è possibile recuperare una chiamata parcheggiata dall'applicazione Parcheggio di chiamata se la richiesta di recupero viene fatta per conto di un Response Group</span><span class="sxs-lookup"><span data-stu-id="cdf4a-457">A parked call can't be retrieved from the Call Park application if the retrieve request is done on behalf of a Response Group</span></span>

<span data-ttu-id="cdf4a-458">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-458">**Issue:**</span></span>

<span data-ttu-id="cdf4a-459">Quando si verificano le condizioni seguenti, una richiesta di recupero per una chiamata parcheggiata avrà esito negativo:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-459">When the following conditions are true, a retrieve request for a parked call will fail:</span></span>

  - <span data-ttu-id="cdf4a-460">Un agente fa parte di un Response Group anonimo</span><span class="sxs-lookup"><span data-stu-id="cdf4a-460">An agent is part of an anonymous Response Group</span></span>

  - <span data-ttu-id="cdf4a-461">L'agente tenta di recuperare una chiamata parcheggiata dall'applicazione Parcheggio di chiamata tramite il Response Group anonimo</span><span class="sxs-lookup"><span data-stu-id="cdf4a-461">The agent attempts to retrieve a parked call from the Call Park application through the anonymous Response Group</span></span>

  - <span data-ttu-id="cdf4a-462">L'agente tenta di recuperare la chiamata componendo il numero dell'orbita tramite l'opzione chiama per conto di o tramite la stessa opzione nel client di operatore di Lync</span><span class="sxs-lookup"><span data-stu-id="cdf4a-462">The agent attempts to retrieve the call by dialing the orbit number through the Call On Behalf option or through the same option in the Lync attendant client</span></span>

<span data-ttu-id="cdf4a-463">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-463">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-464">Non vi sono soluzioni alternative per questo problema.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-464">There are no workarounds for this issue.</span></span> <span data-ttu-id="cdf4a-465">La chiamata parcheggiata deve essere recuperata senza farlo per conto di un Response Group.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-465">The parked call should be retrieved without doing so on behalf of a Response Group.</span></span>

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a><span data-ttu-id="cdf4a-466">Pannello di controllo di Lync Server, Generatore di topologie e Strumento di pianificazione</span><span class="sxs-lookup"><span data-stu-id="cdf4a-466">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

<div>

## <a name="planning-tool-limitations"></a><span data-ttu-id="cdf4a-467">Limitazioni dello strumento di pianificazione</span><span class="sxs-lookup"><span data-stu-id="cdf4a-467">Planning Tool Limitations</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="cdf4a-468">Le informazioni contenute in questa sezione riguardano gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-468">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="cdf4a-469">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-469">**Issue:**</span></span>

<span data-ttu-id="cdf4a-470">Durante la pianificazione della distribuzione, lo strumento di pianificazione presenta le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-470">The Planning Tool has the following limitations when planning for your deployment:</span></span>

  - <span data-ttu-id="cdf4a-471">È supportato un massimo di 10 siti centrali</span><span class="sxs-lookup"><span data-stu-id="cdf4a-471">There is a maximum of 10 central sites supported</span></span>

  - <span data-ttu-id="cdf4a-472">Ogni sito centrale può avere un massimo di 14 siti di succursale</span><span class="sxs-lookup"><span data-stu-id="cdf4a-472">Each central site can have a maximum of 14 branch sites</span></span>

  - <span data-ttu-id="cdf4a-473">Ogni sito centrale può avere un massimo di 240.000 utenti</span><span class="sxs-lookup"><span data-stu-id="cdf4a-473">Each central site can have a maximum of 240,000 users</span></span>

<span data-ttu-id="cdf4a-474">Inoltre, quando si calcola la topologia consigliata, lo strumento di pianificazione non include i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-474">In addition, the Planning Tool does not include values for the following when calculating the recommended topology:</span></span>

  - <span data-ttu-id="cdf4a-475">Il numero di utenti ospitati online</span><span class="sxs-lookup"><span data-stu-id="cdf4a-475">The number of users that are homed online</span></span>

  - <span data-ttu-id="cdf4a-476">La percentuale di utenti abilitati per la Federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="cdf4a-476">The percentage of users that are enabled for XMPP federation</span></span>

  - <span data-ttu-id="cdf4a-477">Percentuale di utenti che utilizzano Lync Web App</span><span class="sxs-lookup"><span data-stu-id="cdf4a-477">Percentage of users that are using Lync Web App</span></span>

<span data-ttu-id="cdf4a-478">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-478">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-479">Non esiste alcuna soluzione per questi problemi.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-479">There is no workaround for these issues.</span></span> <span data-ttu-id="cdf4a-480">Per ulteriori informazioni sullo strumento di pianificazione, vedere [progettazione della topologia per Lync Server 2013 mediante lo strumento di pianificazione](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span><span class="sxs-lookup"><span data-stu-id="cdf4a-480">For more information about the Planning Tool, see [Designing the topology for Lync Server 2013 by using the Planning Tool](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span></span>

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a><span data-ttu-id="cdf4a-481">Lo strumento di pianificazione potrebbe non utilizzare gli indirizzi IP definiti in precedenza per la rete perimetrale quando si aggiornano le opzioni</span><span class="sxs-lookup"><span data-stu-id="cdf4a-481">Planning Tool may not use previously defined IP addresses for the Edge network when updating options</span></span>

<span data-ttu-id="cdf4a-482">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-482">**Issue:**</span></span>

<span data-ttu-id="cdf4a-483">Dopo aver completato la progettazione utilizzando lo strumento di pianificazione, se si apportano modifiche alle opzioni di rete Edge, è possibile aggiungere indirizzi IP aggiuntivi alla struttura anziché aggiornare gli indirizzi IP esistenti.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-483">After you complete your design using the Planning Tool, if you make changes to the Edge Network options, additional IP addresses may be added to the design instead of updating the existing IP addresses.</span></span> <span data-ttu-id="cdf4a-484">Ciò può verificarsi quando si visualizzano i dettagli del diagramma della rete perimetrale, selezionare **fare clic qui per aggiornare le opzioni**e quindi nella finestra di dialogo Opzioni di configurazione selezionare rete perimetrale seleziona **desidero utilizzare gli stessi nomi FQDN e indirizzi IP, ma porte diverse per i servizi perimetrali nel server perimetrale**.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-484">This can occur when you are viewing the details of the Edge Network Diagram, select **Click here to update your options**, and then, on the Configuration Options dialog, you select Edge Network select **I want to use the same FQDNs and IP addresses, but different ports for the edge services on my Edge Server**.</span></span> <span data-ttu-id="cdf4a-485">L'applicazione di eventuali modifiche può comportare l'aggiunta di nuovi indirizzi IP e server perimetrali alla struttura.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-485">Applying any changes may result in new IP addresses and Edge servers being added to the design.</span></span>

<span data-ttu-id="cdf4a-486">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-486">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-487">Non esiste alcuna soluzione per questo problema in questo momento.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-487">There is no workaround for this issue at this time.</span></span>

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a><span data-ttu-id="cdf4a-488">Nel pannello di controllo di Lync Server, "spostare tutti gli utenti nel pool" potrebbe non funzionare come previsto</span><span class="sxs-lookup"><span data-stu-id="cdf4a-488">In Lync Server Control Panel, "Move all users to pool" may not work as expected</span></span>

<span data-ttu-id="cdf4a-489">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-489">**Issue:**</span></span>

<span data-ttu-id="cdf4a-490">Quando si utilizza il pannello di controllo di Lync Server per spostare tutti gli utenti da un pool a un altro in un ambiente di Active Directory complesso, ad esempio uno con più controller di dominio e domini padre/figlio, potrebbe essere restituito un messaggio di errore che indica che l'utente specificato non è un utente legacy, utilizzare invece il cmdlet Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-490">When using the Lync Server Control Panel to move all users from one pool to another pool in a complex Active Directory environment, such as one with multiple Domain Controllers and parent/child domains, an error message may be returned that states, “Specified user is not a legacy user, use Move-CsUser cmdlet instead.”</span></span> <span data-ttu-id="cdf4a-491">Questo è il risultato di tempi di replica più lunghi in ambienti di Active Directory complessi.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-491">This is a result of longer replication times in complex Active Directory environments.</span></span>

<span data-ttu-id="cdf4a-492">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-492">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-493">Per risolvere questo problema, effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-493">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="cdf4a-494">Utilizzare filtri nel pannello di controllo di Lync Server per cercare gli utenti legacy, selezionarli e quindi utilizzare il **comando Sposta utenti selezionati nel pool** anziché **spostare tutti gli utenti nel pool**.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-494">Use filters in the Lync Server Control Panel to search for legacy users, select those users, and then use the **Move selected users to pool command** instead of **Move all users to pool**.</span></span>

  - <span data-ttu-id="cdf4a-495">Utilizzare Lync Server Management Shell per spostare gli utenti legacy in batch utilizzando i cmdlet di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-495">Use the Lync Server Management Shell to move legacy users in batches by using Lync Server cmdlets.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a><span data-ttu-id="cdf4a-496">Il pannello di controllo di Lync Server smette di funzionare in un ambiente VMware dopo che il plug-in del browser Microsoft Silverlight è stato aggiornato alla versione 5</span><span class="sxs-lookup"><span data-stu-id="cdf4a-496">The Lync Server Control Panel stops working in a VMware environment after the Microsoft Silverlight browser plug-in is updated to version 5</span></span>

<span data-ttu-id="cdf4a-497">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-497">**Issue:**</span></span>

<span data-ttu-id="cdf4a-498">Se si utilizza il pannello di controllo di Lync Server in un ambiente VMware, è possibile che il pannello di controllo di Lync Server smetta di funzionare dopo aver aggiornato Silverlight alla versione 5.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-498">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Silverlight to version 5.</span></span>

<span data-ttu-id="cdf4a-499">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-499">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-500">Per risolvere questo problema, effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-500">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="cdf4a-501">Disinstallare Silverlight 5 e quindi installare Silverlight 4 da [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0).</span><span class="sxs-lookup"><span data-stu-id="cdf4a-501">Uninstall Silverlight 5, and then install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0).</span></span>

  - <span data-ttu-id="cdf4a-502">Aprire il pannello di controllo di Lync Server da un computer che non sia un computer virtuale VMware.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-502">Open the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="cdf4a-503">Per aprire il pannello di controllo di Lync Server da un computer remoto, installare gli strumenti di amministrazione di Lync Server nel computer e quindi avviare il pannello di controllo di Lync Server dal menu **Start** di Windows.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-503">To open the Lync Server Control Panel from a remote computer, install Lync Server Administration tools on the computer, and then start the Lync Server Control Panel from the Windows **Start** menu.</span></span>
    
    <span data-ttu-id="cdf4a-504">È inoltre possibile aprire il pannello di controllo di Lync Server digitando l'URL in un Web browser.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-504">You can also open the Lync Server Control Panel by entering the URL in a web browser.</span></span> <span data-ttu-id="cdf4a-505">L'URL sarà\<simile a FQDN\_\_\>del pool di front-end di https:///CSCP.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-505">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a><span data-ttu-id="cdf4a-506">Un amministratore non è in grado di eseguire il cmdlet Uninstall-csMirrorDB dopo aver rimosso il database del mirroring in Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="cdf4a-506">An administrator cannot run the Uninstall-csMirrorDB cmdlet after removing the mirroring database in Topology Builder</span></span>

<span data-ttu-id="cdf4a-507">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-507">**Issue:**</span></span>

<span data-ttu-id="cdf4a-508">Quando un amministratore disabilita un database del mirroring in Generatore di topologie e quindi Elimina il database del mirroring in Generatore di topologie, nell'elenco da fare viene visualizzato un messaggio che consente all'amministratore di eseguire il cmdlet **Uninstall-csMirrorDatabase** per rimuovere il mirroring da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-508">When an administrator disables a mirroring database in Topology Builder, and then deletes the mirroring database in Topology Builder, a message is displayed in the To do list for the administrator to run the **Uninstall-csMirrorDatabase** cmdlet to remove mirroring from SQL Server.</span></span> <span data-ttu-id="cdf4a-509">Quando l'amministratore tenta di eseguire il cmdlet, ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-509">When the administrator attempts to run the cmdlet, it fails.</span></span>

<span data-ttu-id="cdf4a-510">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-510">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-511">Per rimuovere il mirroring SQL di un pool in Generatore di topologie, è innanzitutto necessario utilizzare un cmdlet per rimuovere il mirror in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-511">To remove SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server.</span></span> <span data-ttu-id="cdf4a-512">È quindi possibile utilizzare Generatore di topologie per rimuovere il mirror dalla topologia.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-512">You can then use Topology Builder to remove the mirror from the topology.</span></span> <span data-ttu-id="cdf4a-513">Per rimuovere il mirror in SQL Server, utilizzare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-513">To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="cdf4a-514">Ad esempio, per rimuovere il mirroring e rilasciare i database per i database degli utenti, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-514">For example, to remove mirroring and drop the databases for the user databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="cdf4a-515">Il parametro *DropExistingDatabasesOnMirror* consente di eliminare dal mirror i database coinvolti.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-515">The *DropExistingDatabasesOnMirror* parameter causes the affected databases to be deleted from the mirror.</span></span> <span data-ttu-id="cdf4a-516">Per rimuovere il mirror dalla topology, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-516">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="cdf4a-517">In Generatore di topologie, fare clic con il pulsante destro del mouse sul pool e quindi scegliere **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-517">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="cdf4a-518">Cancellare il **mirroring dell'archivio SQL** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-518">Clear **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="cdf4a-519">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-519">Publish the topology.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="cdf4a-520">Ogni volta che si apportano modifiche a una relazione di mirroring del database back-end, è necessario riavviare tutti i Front End Server nel pool.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-520">Whenever you make a change to a back-end database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span>



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a><span data-ttu-id="cdf4a-521">Gli errori di convalida vengono restituiti in Generatore di topologie quando un amministratore tenta di rimuovere una distribuzione con un pool Front end a cui è associato un archivio di controllo.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-521">Validation errors are returned in Topology Builder when an administrator attempts to remove a deployment with a Front End pool that has an associated witness store</span></span>

<span data-ttu-id="cdf4a-522">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-522">**Issue:**</span></span>

<span data-ttu-id="cdf4a-523">Se un amministratore tenta di utilizzare il comando **Rimuovi distribuzione** in Generatore di topologie per rimuovere una distribuzione che include un pool Front end con un archivio di controllo associato, viene visualizzato un errore di convalida in Generatore di topologie e l'azione non verrà eseguita.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-523">If an administrator attempts to use the **Remove Deployment** command in Topology Builder to remove a deployment that includes a Front End pool with an associated witness store, a validation error is displayed in Topology Builder and the action will not proceed.</span></span>

<span data-ttu-id="cdf4a-524">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-524">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-525">Per risolvere questo problema, effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-525">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="cdf4a-526">Rimuovere l'archivio di controllo prima di tentare di rimuovere la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-526">Remove the witness store before attempting to remove the deployment.</span></span>

  - <span data-ttu-id="cdf4a-527">Aggiungere un archivio di controllo per il pool Front end e quindi rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-527">Add a witness store for the Front End pool and then remove it.</span></span>

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a><span data-ttu-id="cdf4a-528">Le informazioni sulla distribuzione del server Chat persistente sono incoerenti tra lo strumento di pianificazione e il generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="cdf4a-528">Persistent Chat Server deployment information is inconsistent between the Planning Tool and Topology Builder</span></span>

<span data-ttu-id="cdf4a-529">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-529">**Issue:**</span></span>

<span data-ttu-id="cdf4a-530">Quando Lync Server 2013, lo strumento di pianificazione genera il diagramma della topologia del sito per una distribuzione di server Chat persistente con ripristino di emergenza abilitato, il diagramma della topologia del sito include più siti (fisici), con i server di chat persistente assegnati equamente a ogni sito.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-530">When the Lync Server 2013, Planning Tool outputs the site topology diagram for a Persistent Chat Server deployment with disaster recovery enabled, the site topology diagram includes multiple (physical) sites, with evenly assigned Persistent Chat Servers at each site.</span></span> <span data-ttu-id="cdf4a-531">In Generatore di topologie, tutti i server di chat persistente sono rappresentati come appartenenti a un singolo sito (logico) e sono elencati nello stesso nodo del pool di Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-531">In Topology Builder, all Persistent Chat Servers are represented as belonging to a single (logical) site, and are listed under the same Persistent Chat Server pool node.</span></span>

<span data-ttu-id="cdf4a-532">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-532">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-533">Attualmente, non si dispone di una soluzione alternativa per questo problema.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-533">Currently, we do not have a workaround for this issue.</span></span> <span data-ttu-id="cdf4a-534">L'utente deve analizzare l'output dello strumento di pianificazione per la distribuzione del server Chat persistente e modificare il piano per soddisfare le proprie esigenze specifiche.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-534">The user should analyze the output of the Planning Tool for the Persistent Chat Server deployment, and modify the plan to meet their specific needs.</span></span>

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a><span data-ttu-id="cdf4a-535">Localizzazione</span><span class="sxs-lookup"><span data-stu-id="cdf4a-535">Localization</span></span>

<div>

## <a name="monitoring"></a><span data-ttu-id="cdf4a-536">Monitoraggio</span><span class="sxs-lookup"><span data-stu-id="cdf4a-536">Monitoring</span></span>

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a><span data-ttu-id="cdf4a-537">La procedura guidata per la distribuzione dei rapporti di monitoraggio Visualizza caratteri non corretti in determinate circostanze quando si utilizza la versione dell'Asia orientale di Lync Server</span><span class="sxs-lookup"><span data-stu-id="cdf4a-537">The Deploy Monitoring Reports wizard displays incorrect characters under certain circumstances when using the East Asian version of Lync Server</span></span>

<span data-ttu-id="cdf4a-538">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-538">**Issue:**</span></span>

<span data-ttu-id="cdf4a-539">Quando si utilizza una versione dell'Asia orientale di Lync Server 2013, ad esempio cinese (semplificato), cinese (tradizionale), giapponese o coreano, in un sistema operativo in cui le impostazioni locali del sistema non sono impostate su una lingua dell'Asia orientale, la procedura guidata per la distribuzione dei rapporti di monitoraggio visualizzare i punti interrogativi o altri caratteri invece dei messaggi localizzati.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-539">When using an East Asian version of Lync Server 2013—for example, Chinese (Simplified), Chinese (Traditional), Japanese, or Korean—on an operating system that has the system locale not set to an East Asian language, the Deploy Monitoring Reports wizard will display question marks or other characters instead of localized messages.</span></span>

<span data-ttu-id="cdf4a-540">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-540">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-541">Per risolvere il problema, impostare le impostazioni locali per il sistema operativo e Lync Server 2013 sulla stessa lingua, in cui verranno visualizzati correttamente tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-541">To correct this issue, set the locale for the operating system and Lync Server 2013 to the same language, which will display all messages correctly.</span></span>

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="cdf4a-542">Pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="cdf4a-542">Lync Server Control Panel</span></span>

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a><span data-ttu-id="cdf4a-543">In alcuni casi, il primo elemento nella barra di spostamento superiore in una pagina del pannello di controllo di Lync Server scompare quando si fa clic sull'ultimo elemento della barra di spostamento superiore</span><span class="sxs-lookup"><span data-stu-id="cdf4a-543">In certain cases, the first item in the top navigation bar on a page of Lync Server Control Panel disappears when the last item in the top navigation bar is clicked</span></span>

<span data-ttu-id="cdf4a-544">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-544">**Issue:**</span></span>

<span data-ttu-id="cdf4a-545">Esistono tre casi noti in cui se si fa clic sull'ultimo elemento nella barra di spostamento superiore in una pagina del pannello di controllo di Lync Server, il primo elemento nella barra di spostamento superiore scomparirà:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-545">There are three known cases where clicking the last item in the top navigation bar on a page of the Lync Server Control Panel will cause the first item in the top navigation bar to disappear:</span></span>

  - <span data-ttu-id="cdf4a-546">Nella versione francese della pagina "Féderation et accès externe", l'elemento "Stratégie accès externe" scomparirà quando si fa clic su "Partenaires fédérés XMPP".</span><span class="sxs-lookup"><span data-stu-id="cdf4a-546">In the French of version, on the page "Féderation et accès externe," the item "Stratégie d'accès externe" will disappear when "Partenaires fédérés XMPP" is clicked.</span></span>

  - <span data-ttu-id="cdf4a-547">Nella versione in lingua tedesca, nella pagina "client", l'elemento "Clientversionskonfiguration" scompare quando si fa clic su "se".</span><span class="sxs-lookup"><span data-stu-id="cdf4a-547">In the German version, on the "Clients" page, the item "Clientversionskonfiguration" disappears when "Pushbenachrichtigungskonfiguration" is clicked.</span></span>

  - <span data-ttu-id="cdf4a-548">Nella versione russa, nella pagina "Конфигурация сети", la voce "Глобально" scompare quando si fa clic su "Маршрут региона".</span><span class="sxs-lookup"><span data-stu-id="cdf4a-548">In the Russian version, on "Конфигурация сети" page, the item "Глобально" disappears when "Маршрут региона" is clicked.</span></span>

<span data-ttu-id="cdf4a-549">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-549">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-550">Per ovviare a questo problema, aggiornare la pagina del pannello di controllo di Lync Server nel browser.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-550">To work around this issue, refresh the page of the Lync Server Control Panel in your browser.</span></span> <span data-ttu-id="cdf4a-551">La pagina verrà caricata nel browser con tutti gli elementi nella barra di spostamento superiore visualizzata.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-551">The page will load in the browser with all of the items in the top navigation bar displayed.</span></span>

</div>

</div>

<div>

## <a name="address-book"></a><span data-ttu-id="cdf4a-552">Rubrica</span><span class="sxs-lookup"><span data-stu-id="cdf4a-552">Address Book</span></span>

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a><span data-ttu-id="cdf4a-553">L'indicizzazione nella Rubrica non funziona come previsto in alcune lingue</span><span class="sxs-lookup"><span data-stu-id="cdf4a-553">Indexing in the Address Book does not work as expected in some languages</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="cdf4a-554">Le informazioni contenute in questa sezione riguardano gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-554">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="cdf4a-555">Se le proprietà di un utente contengono un campo indicizzato e questo campo contiene solo caratteri che non possono essere indicizzati, l'utente non verrà visualizzato nelle ricerche eseguite nella rubrica.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-555">If a user’s properties contain an indexed field, and that field contains only characters that cannot be indexed, then the user will not appear in searches performed in the Address Book.</span></span>

<span data-ttu-id="cdf4a-556">Non è possibile indicizzare i caratteri e le impostazioni locali seguenti:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-556">The following characters and locales cannot be indexed:</span></span>

  - <span data-ttu-id="cdf4a-557">Caratteri cirillici, greci e armeni in maiuscolo</span><span class="sxs-lookup"><span data-stu-id="cdf4a-557">Upper-case Cyrillic, Greek, and Armenian characters</span></span>

  - <span data-ttu-id="cdf4a-558">Caratteri accentati in maiuscolo</span><span class="sxs-lookup"><span data-stu-id="cdf4a-558">Upper-case accented characters</span></span>

  - <span data-ttu-id="cdf4a-559">Thai</span><span class="sxs-lookup"><span data-stu-id="cdf4a-559">Thai</span></span>

  - <span data-ttu-id="cdf4a-560">Lao</span><span class="sxs-lookup"><span data-stu-id="cdf4a-560">Lao</span></span>

  - <span data-ttu-id="cdf4a-561">Myanmar</span><span class="sxs-lookup"><span data-stu-id="cdf4a-561">Myanmar</span></span>

  - <span data-ttu-id="cdf4a-562">Devanagari</span><span class="sxs-lookup"><span data-stu-id="cdf4a-562">Devanagari</span></span>

  - <span data-ttu-id="cdf4a-563">Etiope</span><span class="sxs-lookup"><span data-stu-id="cdf4a-563">Ethiopic</span></span>

  - <span data-ttu-id="cdf4a-564">Tibetano</span><span class="sxs-lookup"><span data-stu-id="cdf4a-564">Tibetan</span></span>

  - <span data-ttu-id="cdf4a-565">Bengali</span><span class="sxs-lookup"><span data-stu-id="cdf4a-565">Bengali</span></span>

  - <span data-ttu-id="cdf4a-566">Gujarati</span><span class="sxs-lookup"><span data-stu-id="cdf4a-566">Gujarati</span></span>

  - <span data-ttu-id="cdf4a-567">Telugu</span><span class="sxs-lookup"><span data-stu-id="cdf4a-567">Telugu</span></span>

  - <span data-ttu-id="cdf4a-568">Tutti gli altri script indiani</span><span class="sxs-lookup"><span data-stu-id="cdf4a-568">All other Indic scripts</span></span>

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a><span data-ttu-id="cdf4a-569">Lync Web App, utilità di pianificazione Web e componenti Web</span><span class="sxs-lookup"><span data-stu-id="cdf4a-569">Lync Web App, Web Scheduler, and Web components</span></span>

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a><span data-ttu-id="cdf4a-570">Il fallback della lingua per alcune lingue in Lync Web Scheduler, accesso esterno, Join Launcher, Persistent Chat Room Management e OCTab potrebbe non funzionare come previsto</span><span class="sxs-lookup"><span data-stu-id="cdf4a-570">Language fallback for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab might not work as expected</span></span>

<span data-ttu-id="cdf4a-571">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-571">**Issue:**</span></span>

<span data-ttu-id="cdf4a-572">Quando si selezionano impostazioni locali neutre in un Web browser (in Internet Explorer, ad esempio, il nome della lingua senza ulteriori specifiche, \[come\]"norvegese no", anziché le impostazioni locali che specificano la lingua, lo script e le impostazioni locali (ad esempio \["norvegese,\]Bokmål (Norvegia) NB-no") potrebbe causare un comportamento di visualizzazione imprevisto per alcune lingue in Lync Web Scheduler, accesso esterno, Join Launcher, Persistent Chat Room Management e OCTab.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-572">When selecting a neutral locale in a web browser (in Internet Explorer, for example, the language name without further specification, like "Norwegian \[no\]") instead of a locale specifying language, script and locale (such as "Norwegian, Bokmål (Norway) \[nb-NO\]") might lead to unexpected display behavior for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab.</span></span> <span data-ttu-id="cdf4a-573">Ad esempio, gli utenti potrebbero visualizzare la pagina in lingua inglese quando viene selezionata una delle lingue seguenti:</span><span class="sxs-lookup"><span data-stu-id="cdf4a-573">For example, users might see the English page when one of the following languages is selected:</span></span>

  - <span data-ttu-id="cdf4a-574">Norvegese</span><span class="sxs-lookup"><span data-stu-id="cdf4a-574">Norwegian</span></span>

  - <span data-ttu-id="cdf4a-575">Portoghese</span><span class="sxs-lookup"><span data-stu-id="cdf4a-575">Portuguese</span></span>

  - <span data-ttu-id="cdf4a-576">Serbo</span><span class="sxs-lookup"><span data-stu-id="cdf4a-576">Serbian</span></span>

<span data-ttu-id="cdf4a-577">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-577">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-578">Se si desidera selezionare una lingua con impostazioni locali neutre, assicurarsi sempre di aggiungere la lingua a una determinata lingua (con codice di script e/o di paese) come ulteriore linguaggio nell'elenco delle preferenze della lingua del browser.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-578">If you want to select a language with a neutral locale, always make sure that you also add the language with a specific locale (with script and/or country code) as an additional language in your browser's language preference list.</span></span>

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a><span data-ttu-id="cdf4a-579">È disponibile un supporto limitato per le impostazioni locali azeri e Usbeco quando si utilizza Lync Web Scheduler, accesso esterno, Join Launcher, gestione chat room Persistent e OCTab in alcuni Web browser</span><span class="sxs-lookup"><span data-stu-id="cdf4a-579">There is limited support for Azeri and Uzbek locales when using Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab in some web browsers</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="cdf4a-580">Le informazioni contenute in questa sezione riguardano gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-580">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="cdf4a-581">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-581">**Issue:**</span></span>

<span data-ttu-id="cdf4a-582">Quando si utilizza Internet Explorer 8 o Internet Explorer 9 e si imposta la lingua del browser su Azero (alfabeto latino) o Usbeco (alfabeto latino), le pagine di avvio di accesso esterno e join verranno visualizzate in inglese o nella lingua preferita impostata nel browser.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-582">When you use Internet Explorer 8 or Internet Explorer 9, and set the browser language to Azeri (Latin) or Uzbek (Latin), the Dial-in and Join Launcher pages will be displayed in English or the preferred language set in the browser.</span></span>

<span data-ttu-id="cdf4a-583">Quando si utilizzano i browser Firefox o Chrome e si imposta la lingua del browser su Azero (alfabeto latino) o Usbeco (alfabeto latino), Lync Web App, Lync Web Scheduler e RGS OCTab verranno visualizzati in inglese o la lingua preferita per il browser.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-583">When you use Firefox or Chrome browsers, and you set the browser language to Azeri (Latin) or Uzbek (Latin), the Lync Web App, Lync Web Scheduler, and RGS OCTab will be shown in English or the preferred language set for the browser.</span></span>

<span data-ttu-id="cdf4a-584">Le impostazioni locali dell'Uzbeco (alfabeto latino) non sono supportate nel browser Safari.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-584">The Uzbek (Latin) locale is not supported in the Safari browser.</span></span>

<span data-ttu-id="cdf4a-585">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-585">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-586">Non esiste una soluzione alternativa per questi problemi.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-586">There is not workaround for these issues.</span></span>

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a><span data-ttu-id="cdf4a-587">La freccia a discesa mancante per l'elenco "partecipa a riunione da" nella versione rumena di Lync Web App</span><span class="sxs-lookup"><span data-stu-id="cdf4a-587">The drop-down arrow is missing for "Join meeting from" list in the Romanian version of Lync Web App</span></span>

<span data-ttu-id="cdf4a-588">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-588">**Issue:**</span></span>

<span data-ttu-id="cdf4a-589">Quando un utente che utilizza la versione rumena di Lync Web App esegue i passaggi seguenti, la freccia a discesa non viene visualizzata per l'elenco a discesa **partecipa a riunione** :</span><span class="sxs-lookup"><span data-stu-id="cdf4a-589">When a user who is using the Romanian version of Lync Web App performs the following steps, the drop-down arrow is not displayed for **Join meeting** in drop-down list:</span></span>

1.  <span data-ttu-id="cdf4a-590">Selezionare **Ricordami su questo computer** nella scheda **generale** .</span><span class="sxs-lookup"><span data-stu-id="cdf4a-590">Select **Remember me on this computer** on the **General** tab.</span></span>

2.  <span data-ttu-id="cdf4a-591">Selezionare la scheda **telefono** .</span><span class="sxs-lookup"><span data-stu-id="cdf4a-591">Select the **Phone** tab.</span></span>

3.  <span data-ttu-id="cdf4a-592">Fare clic sull'elenco a discesa per **partecipare a una riunione**.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-592">Click the drop-down list for **Join meeting from**.</span></span>
    
    <span data-ttu-id="cdf4a-593">Gli utenti non vedranno una freccia che indica che sono disponibili altre opzioni rispetto all'impostazione predefinita di **Lync Web App**, tra cui: **non aggiungere audio** (in Romeno, "nu se asociaža la Componenta audio") e **nuovo numero**"(in Romeno," Număr Nou ").</span><span class="sxs-lookup"><span data-stu-id="cdf4a-593">Users will not see an arrow that indicates that there are more options than the default **Lync Web App**, which include: **Don't join audio** (in Romanian, "Nu se asociaža la componenta audio") and **New number**" (in Romanian, "Număr nou").</span></span>

<span data-ttu-id="cdf4a-594">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-594">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-595">Anche se la freccia di questo elenco a discesa non è visualizzata, gli utenti possono comunque selezionare le impostazioni aggiuntive nell'elenco facendo clic sul valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-595">Even though the arrow for this drop-down list is not displayed, users can still select the additional settings in the list by clicking on the default value.</span></span>

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a><span data-ttu-id="cdf4a-596">Quando si utilizza la versione turca di Lync Web Scheduler, non è possibile salvare una riunione quando si utilizza l'opzione "persone scelte dall'utente" in "chi è un relatore"</span><span class="sxs-lookup"><span data-stu-id="cdf4a-596">When using the Turkish version of Lync Web Scheduler, a meeting cannot be saved when using the "People I choose" option under "Who is a presenter"</span></span>

<span data-ttu-id="cdf4a-597">**Problema**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-597">**Issue:**</span></span>

<span data-ttu-id="cdf4a-598">Quando si crea o si modifica una riunione nella versione turca dell'utilità di pianificazione Web di Lync, l'opzione "persone scelte" in "chi è un relatore" non è supportata.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-598">When creating or editing a meeting in the Turkish version of the Lync Web Scheduler, the option "People I choose" under "Who is a presenter" is not supported.</span></span> <span data-ttu-id="cdf4a-599">Quando questa opzione è selezionata, la riunione non può essere salvata.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-599">When this option is selected, the meeting can't be saved.</span></span> <span data-ttu-id="cdf4a-600">Viene invece visualizzato un messaggio di errore che indica che non è possibile rendere relatori una o più persone.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-600">Instead, an error message appears, indicating that one or more people cannot be made presenters.</span></span>

<span data-ttu-id="cdf4a-601">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="cdf4a-601">**Workaround:**</span></span>

<span data-ttu-id="cdf4a-602">Per ovviare a questo problema, gli utenti possono utilizzare l'opzione predefinita "persone della mia azienda" o qualsiasi altra scelta, ad esempio "solo organizzatore" o "tutti compresi quelli esterni alla propria azienda".</span><span class="sxs-lookup"><span data-stu-id="cdf4a-602">To work around this issue, users can use the default option of "People from my company," or any other choice, such as "Only Organizer" or "Everyone including people outside of my company."</span></span> <span data-ttu-id="cdf4a-603">L'organizzatore può abbassare di livello o promuovere i ruoli corretti in un secondo momento, dopo aver partecipato alla riunione.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-603">The organizer can demote or promote people to their correct roles later, after they have joined the meeting.</span></span>

<span data-ttu-id="cdf4a-604">In alternativa, gli utenti che capiscono un'altra lingua possono cambiare la selezione della lingua nel browser in una delle altre lingue supportate da 43 e tentare di utilizzare l'opzione "persone scelte dall'utente".</span><span class="sxs-lookup"><span data-stu-id="cdf4a-604">Alternatively, users who understand another language can change the language selection in their browser to one of the other 43 supported languages and attempt to use the “People I choose” option.</span></span>

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a><span data-ttu-id="cdf4a-605">Copyright</span><span class="sxs-lookup"><span data-stu-id="cdf4a-605">Copyright</span></span>

<span data-ttu-id="cdf4a-606">Questo documento supporta una versione preliminare di un prodotto software che può essere modificato in modo sostanziale prima del rilascio finale commerciale ed è l'informazione riservata e proprietaria di Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-606">This document supports a preliminary release of a software product that may be changed substantially prior to final commercial release, and is the confidential and proprietary information of Microsoft Corporation.</span></span> <span data-ttu-id="cdf4a-607">Viene divulgato in base a un accordo di non divulgazione tra il destinatario e Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-607">It is disclosed pursuant to a non-disclosure agreement between the recipient and Microsoft.</span></span> <span data-ttu-id="cdf4a-608">Microsoft esclude ogni garanzia espressa o implicita in questo documento.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-608">This document is provided for informational purposes only and Microsoft makes no warranties, either express or implied, in this document.</span></span> <span data-ttu-id="cdf4a-609">Le informazioni contenute in questo documento, tra cui l'URL e altri riferimenti al sito Internet, sono soggette a modifiche senza preavviso.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-609">Information in this document, including URL and other Internet website references, is subject to change without notice.</span></span> <span data-ttu-id="cdf4a-610">I rischi conseguenti all'uso o ai risultati dell'uso di questo documento sono a carico degli utenti.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-610">The entire risk of the use or the results from the use of this document remains with the user.</span></span> <span data-ttu-id="cdf4a-611">Se non diversamente specificato, le società, le organizzazioni, i prodotti, i nomi di dominio, gli indirizzi di posta elettronica, i loghi, le persone, i luoghi e gli eventi descritti negli esempi riportati sono fittizi.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-611">Unless otherwise noted, the companies, organizations, products, domain names, email addresses, logos, people, places, and events depicted in examples herein are fictitious.</span></span> <span data-ttu-id="cdf4a-612">Nessuna associazione con una società, un'organizzazione, un prodotto, un nome di dominio, un indirizzo di posta elettronica, un logo, una persona, un luogo o un evento reale è intenzionale o deve essere dedotto.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-612">No association with any real company, organization, product, domain name, email address, logo, person, place, or event is intended or should be inferred.</span></span> <span data-ttu-id="cdf4a-613">Il rispetto di tutte le applicabili leggi in materia di copyright è esclusivamente a carico dell'utente.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-613">Complying with all applicable copyright laws is the responsibility of the user.</span></span> <span data-ttu-id="cdf4a-614">Fermi restando tutti i diritti coperti da copyright, nessuna parte di questo documento potrà comunque essere riprodotta o inserita in un sistema di riproduzione o trasmessa in qualsiasi forma e con qualsiasi mezzo (in formato elettronico, meccanico, su fotocopia, come registrazione o altro) per qualsiasi scopo, senza il permesso scritto di Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-614">Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.</span></span>

<span data-ttu-id="cdf4a-p162">Microsoft può essere titolare di brevetti, domande di brevetto, marchi, copyright o altri diritti di proprietà intellettuale relativi all'oggetto del presente documento. Salvo quanto espressamente previsto in un contratto scritto di licenza Microsoft, la consegna del presente documento non implica la concessione di alcuna licenza su tali brevetti, marchi, copyright o altra proprietà intellettuale.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-p162">Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document. Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.</span></span>

<span data-ttu-id="cdf4a-617">© 2012 Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-617">© 2012 Microsoft Corporation.</span></span> <span data-ttu-id="cdf4a-618">Tutti i diritti riservati.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-618">All rights reserved.</span></span>

<span data-ttu-id="cdf4a-619">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook e SQL Server sono marchi o marchi registrati di Microsoft Corporation negli Stati Uniti e/o negli altri paesi/aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-619">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook, and SQL Server are either registered trademarks or trademarks of Microsoft Corporation in the United States and/or other countries/regions.</span></span>

<span data-ttu-id="cdf4a-620">Tutti gli altri marchi citati nel presente documento sono di proprietà dei rispettivi titolari.</span><span class="sxs-lookup"><span data-stu-id="cdf4a-620">All other trademarks are property of their respective owners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

