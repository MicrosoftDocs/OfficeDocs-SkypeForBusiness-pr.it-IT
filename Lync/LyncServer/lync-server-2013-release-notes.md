---
title: Note sulla versione di Lync Server 2013
description: Note sulla versione di Lync Server 2013.
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
ms.openlocfilehash: 33fabb0912d7ea3defd91014df732368eced909e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555872"
---
# <a name="release-notes-for-lync-server-2013"></a><span data-ttu-id="5e2d6-103">Note sulla versione per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e2d6-103">Release notes for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e2d6-104">_**Ultimo argomento modificato:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="5e2d6-104">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="5e2d6-105">Note sulla versione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-105">Welcome to the Lync Server 2013 Release Notes.</span></span> <span data-ttu-id="5e2d6-106">Per informazioni sui problemi noti relativi a Lync Server 2013, vedere questo file.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-106">Refer to this file for information regarding known issues about Lync Server 2013.</span></span>

<div>

## <a name="about-this-document"></a><span data-ttu-id="5e2d6-107">Informazioni sul documento</span><span class="sxs-lookup"><span data-stu-id="5e2d6-107">About this document</span></span>

<span data-ttu-id="5e2d6-108">Questo documento contiene informazioni importanti che è necessario conoscere prima di distribuire e utilizzare Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-108">This document contains important information that you should know before you deploy and use Lync Server 2013.</span></span> <span data-ttu-id="5e2d6-109">Per informazioni dettagliate su Lync Server 2013, vedere la documentazione relativa a [Microsoft Lync server 2013](microsoft-lync-server-2013.md) .</span><span class="sxs-lookup"><span data-stu-id="5e2d6-109">For details about Lync Server 2013, refer to the [Microsoft Lync Server 2013](microsoft-lync-server-2013.md) documentation.</span></span>

<span data-ttu-id="5e2d6-110">In questo documento sono incluse le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-110">This document contains the following sections:</span></span>

  - <span data-ttu-id="5e2d6-111">Client Lync 2013</span><span class="sxs-lookup"><span data-stu-id="5e2d6-111">Lync 2013 client</span></span>

  - <span data-ttu-id="5e2d6-112">Lync Server</span><span class="sxs-lookup"><span data-stu-id="5e2d6-112">Lync Server</span></span>

  - <span data-ttu-id="5e2d6-113">Installazione</span><span class="sxs-lookup"><span data-stu-id="5e2d6-113">Installation</span></span>

  - <span data-ttu-id="5e2d6-114">Mobilità</span><span class="sxs-lookup"><span data-stu-id="5e2d6-114">Mobility</span></span>

  - <span data-ttu-id="5e2d6-115">Conferenze</span><span class="sxs-lookup"><span data-stu-id="5e2d6-115">Conferencing</span></span>

  - <span data-ttu-id="5e2d6-116">VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="5e2d6-116">Enterprise Voice</span></span>

  - <span data-ttu-id="5e2d6-117">Presenza</span><span class="sxs-lookup"><span data-stu-id="5e2d6-117">Presence</span></span>

  - <span data-ttu-id="5e2d6-118">Applicazione Response Group e applicazione Call Park</span><span class="sxs-lookup"><span data-stu-id="5e2d6-118">Response Group Application and Call Park Application</span></span>

  - <span data-ttu-id="5e2d6-119">Pannello di controllo di Lync Server, Generatore di topologie e Strumento di pianificazione</span><span class="sxs-lookup"><span data-stu-id="5e2d6-119">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

  - <span data-ttu-id="5e2d6-120">Localizzazione</span><span class="sxs-lookup"><span data-stu-id="5e2d6-120">Localization</span></span>

  - <span data-ttu-id="5e2d6-121">Copyright</span><span class="sxs-lookup"><span data-stu-id="5e2d6-121">Copyright</span></span>

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a><span data-ttu-id="5e2d6-122">Client Lync 2013</span><span class="sxs-lookup"><span data-stu-id="5e2d6-122">Lync 2013 client</span></span>

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a><span data-ttu-id="5e2d6-123">Il trasferimento di un file in un messaggio istantaneo ha esito negativo se il file è aperto in un'altra applicazione</span><span class="sxs-lookup"><span data-stu-id="5e2d6-123">Transferring a file in an instant message fails if the file is open in another application</span></span>

<span data-ttu-id="5e2d6-124">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-124">**Issue:**</span></span>

<span data-ttu-id="5e2d6-125">Se si tenta di trasferire un file, ad esempio un documento di Word, inserendolo in un messaggio istantaneo a un altro utente Lync, il trasferimento avrà esito positivo, ma potrebbe non essere in grado di trasferire il file.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-125">If you attempt to transfer a file, such as a Word document, by including it in an instant message to another Lync user, the transfer will appear to succeed but may actually fail to transfer the file.</span></span> <span data-ttu-id="5e2d6-126">Nel client Lync verrà visualizzata un'icona per il tipo di file, ma il file non può essere aperto dal destinatario previsto.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-126">An icon for the file type will be displayed in the Lync client, but the file cannot be opened by the intended receiver.</span></span> <span data-ttu-id="5e2d6-127">Non viene visualizzato alcun messaggio di errore che informa che il trasferimento non ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-127">No error message is displayed to inform you that the transfer was not successfull.</span></span>

<span data-ttu-id="5e2d6-128">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-128">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-129">Per ovviare a questo problema, chiudere il file o l'applicazione aperta che è aperta prima di tentare di trasferire il file in un messaggio istantaneo.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-129">To work around this issue, close the open file or application that has it open before attempting to transfer the file in an instant message.</span></span>

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="5e2d6-130">Lync Server</span><span class="sxs-lookup"><span data-stu-id="5e2d6-130">Lync Server</span></span>

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a><span data-ttu-id="5e2d6-131">Se la replica dei dati del servizio di archiviazione di Lync Server non riesce, gli amministratori dovranno controllare i contatori delle prestazioni per gli elementi di coda del servizio di archiviazione</span><span class="sxs-lookup"><span data-stu-id="5e2d6-131">If Lync Server Storage Service data replication fails, administrators will need to check performance counters for stale Storage Service queue items</span></span>

<span data-ttu-id="5e2d6-132">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-132">**Issue:**</span></span>

<span data-ttu-id="5e2d6-133">Il servizio di archiviazione di Lync Server utilizza Windows Fabric per la replica.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-133">The Lync Server Storage Service uses Windows Fabric for replication.</span></span> <span data-ttu-id="5e2d6-134">Se i dati vengono eliminati in un front end server primario, ma l'eliminazione di un server front-end secondario ha esito negativo, ad esempio se è presente un arresto o un errore imprevisto nel front end server, i dati possono essere lasciati indietro e "orfani".</span><span class="sxs-lookup"><span data-stu-id="5e2d6-134">If data is deleted on a primary Front End Server, but the deletion on a secondary Front End Server fails—for example, if there is an unexpected shutdown or error on the Front End Server—data can be left behind and "orphaned."</span></span> <span data-ttu-id="5e2d6-135">I dati orfani possono causare la riduzione dello spazio di unità e la riduzione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-135">The orphaned data can cause performance to degrade and waste drive space.</span></span>

<span data-ttu-id="5e2d6-136">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-136">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-137">Per ovviare a questo problema, se gli eventi LYSS \_ DB \_ Space \_ used \_ Error (ID = 32058) e Lyss \_ DB \_ Space \_ used \_ Critical (ID = 32059) vengono generati nel registro eventi, gli amministratori dovrebbero controllare il contatore delle prestazioni sul front end server in **ls: Lyss-servizio di archiviazione API** con nome **Lyss-Current numero di elementi di coda non aggiornati del servizio di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-137">To work around this issue, if the events LYSS\_DB\_SPACE\_USED\_ERROR (Id=32058) and LYSS\_DB\_SPACE\_USED\_CRITICAL (Id=32059) are generated in the event log, administrators should check the performance counter on the Front End Server under **LS:LYSS - Storage Service API** with a name of **LYSS - Current number of Storage Service stale queue items**.</span></span> <span data-ttu-id="5e2d6-138">Se il contatore delle prestazioni ha un valore elevato, ad esempio maggiore di 50000, l'amministratore deve eseguire lo strumento di CleanuUpStorageServiceData.exe nel Resource Kit di Lync Server 2013, che eliminerà tutti i dati orfani dal pool.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-138">If this performance counter has a high value—for example, greater than 50,000—then the administrator should run the CleanuUpStorageServiceData.exe tool in the Lync Server 2013 Resource Kit, which will delete all orphaned data from the pool.</span></span> <span data-ttu-id="5e2d6-139">Per informazioni dettagliate sullo strumento, vedere la documentazione di Lync Server 2013 Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-139">For details about the tool, see the Lync Server 2013 Resource Kit documentation.</span></span>

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a><span data-ttu-id="5e2d6-140">Ogni volta che viene modificata la configurazione dell'indirizzo IP per un server o un pool, è necessario riavviare i servizi di Lync Server</span><span class="sxs-lookup"><span data-stu-id="5e2d6-140">Whenever the IP Address configuration is changed for a server or pool, Lync Server services need to be restarted</span></span>

<span data-ttu-id="5e2d6-141">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-141">**Issue:**</span></span>

<span data-ttu-id="5e2d6-142">Quando la configurazione dell'indirizzo IP viene modificata per una distribuzione di Lync Server 2013, ad esempio la modifica da IPv4 a stack doppio o da doppio stack a IPv6, non tutti i componenti server raccolgono la modifica della configurazione fino a quando non vengono riavviati i servizi.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-142">When the IP Address configuration is changed for a Lync Server 2013 deployment, such as changing from IPv4 to Dual Stack, or from Dual Stack to Ipv6, not all server components pick up the configuration change until the services are restarted.</span></span>

<span data-ttu-id="5e2d6-143">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-143">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-144">Per ovviare a questo problema, riavviare i servizi Lync Server dopo aver modificato la configurazione dell'indirizzo IP per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-144">To work around this issue, restart Lync Server services after changing the IP Address configuration for the deployment.</span></span> <span data-ttu-id="5e2d6-145">A tale scopo, eseguire i cmdlet seguenti in Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-145">To do so, run the following cmdlets in the Lync Server Management Shell:</span></span>

   ```PowerShell
    Stop-CsWindowsService -graceful
   ```

   ```PowerShell
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a><span data-ttu-id="5e2d6-146">Il cmdlet per le transazioni sintetiche per le conferenze telefoniche con accesso esterno non è più disponibile nel Management Pack di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e2d6-146">The dial-in conferencing synthetic transaction cmdlet is no longer available in the Lync Server 2013 Management Pack</span></span>

<span data-ttu-id="5e2d6-147">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-147">**Issue:**</span></span>

<span data-ttu-id="5e2d6-148">Il cmdlet di transazione sintetica per le conferenze telefoniche con accesso esterno **Test-CsDialInConferencing** non è più disponibile in Lync Server 2013 Management Pack.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-148">The dial-in conferencing synthetic transaction cmdlet **Test-CsDialInConferencing** is no longer available in the Lync Server 2013 Management Pack.</span></span>

<span data-ttu-id="5e2d6-149">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-149">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-150">Utilizzo del cmdlet di transazione sintetica per le conferenze telefoniche con accesso esterno **Test-CsDialInConferencing** è supportato solo internamente a un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-150">Use of the Dial-In Conferencing Synthetic Transaction cmdlet **Test-CsDialInConferencing** is supported only internally to an enterprise.</span></span>

<span data-ttu-id="5e2d6-151">Gli amministratori possono continuare a utilizzare il cmdlet in Lync Server Management Shell per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-151">Administrators may continue to use the cmdlet in Lync Server Management Shell for troubleshooting purposes.</span></span> <span data-ttu-id="5e2d6-152">Se necessario, un'organizzazione può anche sviluppare un Management Pack privato per eseguire il cmdlet internamente.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-152">If required, an enterprise can also develop a private management pack to run the cmdlet internally.</span></span>

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a><span data-ttu-id="5e2d6-153">Il servizio di registrazione centralizzato si interrompe se il traffico di rete viene interrotto quando i file di registro vengono copiati nella condivisione di rete</span><span class="sxs-lookup"><span data-stu-id="5e2d6-153">The Centralized Logging Service stops if network traffic is disrupted when log files are being copied to network share</span></span>

<span data-ttu-id="5e2d6-154">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-154">**Issue:**</span></span>

<span data-ttu-id="5e2d6-155">Quando il servizio di registrazione centralizzato è configurato per l'utilizzo di un percorso di rete (il valore del parametro CacheFileNetworkFolder del cmdlet **Get-CsClsConfiguration** è un percorso UNC valido), i file di registro memorizzati nella cache vengono copiati nella condivisione di rete.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-155">When the Centralized Logging Service is configured to use a network path (the value of the CacheFileNetworkFolder parameter of the **Get-CsClsConfiguration** cmdlet is a valid UNC path), cached log files are copied to the network share.</span></span> <span data-ttu-id="5e2d6-156">Se si verifica un'interruzione del traffico di rete durante la copia dei file, si verificherà un'eccezione che provocherà l'arresto del servizio di registrazione centralizzato.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-156">If there is a disruption in network traffic while the files are being copied, an exception will occur that will cause the centralized logging service to stop.</span></span>

<span data-ttu-id="5e2d6-157">Il servizio è configurato per il riavvio automatico fino a tre volte, quindi il servizio si riprenderà dalle prime tre eccezioni.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-157">The service is configured to automatically restart up to three times, so the service will recover from the first three exceptions.</span></span>

<span data-ttu-id="5e2d6-158">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-158">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-159">Non esiste alcuna soluzione per questo problema.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-159">There is no workaround for this issue.</span></span> <span data-ttu-id="5e2d6-160">Per identificare il problema, monitorare il registro eventi per l'ID evento 7031 da "Service Control Manager" che registra quando il servizio "Lync Server di registrazione centralizzata" ha terminato in modo imprevisto.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-160">To identify the issue, monitor the event log for Event ID 7031 from the "Service Control Manager" that logs when the "Lync Server Centralized Logging Service Agent" service has terminated unexpectedly.</span></span> <span data-ttu-id="5e2d6-161">Se questo accade più di tre volte, riavviare manualmente il servizio utilizzando il cmdlet **Start-CsWindowService** .</span><span class="sxs-lookup"><span data-stu-id="5e2d6-161">If this happens more than three times, manually restart the service by using the **Start-CsWindowService** cmdlet.</span></span>

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a><span data-ttu-id="5e2d6-162">Gli elementi della coda del servizio di archiviazione devono essere importati manualmente</span><span class="sxs-lookup"><span data-stu-id="5e2d6-162">Storage Service Queue Items need to be imported manually</span></span>

<span data-ttu-id="5e2d6-163">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-163">**Issue:**</span></span>

<span data-ttu-id="5e2d6-164">Lync Server 2013 archivia i dati relativi alle conferenze e alla messaggistica istantanea, ad esempio i messaggi archiviati e la registrazione dettagli chiamata (CDR), in un database di ogni Front End Server.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-164">Lync Server 2013 stores data about conferencing and instant messaging, such as archived messages and call detail recording (CDR), on a database on each Front End Server.</span></span> <span data-ttu-id="5e2d6-165">I dati vengono archiviati nel database mentre vengono elaborati prima di essere recapitati alla destinazione prevista.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-165">The data is stored in the database while it is being processed before being delivered to the intended destination.</span></span> <span data-ttu-id="5e2d6-166">Per migliorare le prestazioni, Lync Server 2013 Esporta periodicamente gli elementi della coda dal database locale che non vengono elaborati per un periodo di tempo prolungato e li salva nell'archivio file.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-166">To improve performance, Lync Server 2013 periodically exports the queue items from the local database that are not processed for an extended period of time, and saves them on the file store.</span></span> <span data-ttu-id="5e2d6-167">Se l'archivio file non è disponibile, gli elementi vengono archiviati in ogni Front End Server.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-167">If the file store is unavailable, the items are stored on each Front End Server.</span></span> <span data-ttu-id="5e2d6-168">La stessa operazione si verifica per evitare la perdita di dati durante il failover del pool.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-168">The same operation occurs to prevent data loss during pool failover.</span></span>

<span data-ttu-id="5e2d6-169">Durante l'operazione di esportazione, il servizio di archiviazione Lync Server registra ogni fase del registro eventi con gli ID evento di 32075 (viene avviata l'operazione full Flush), 32076 (Full Flush è stato completato), 32082 (il livello di manutenzione è iniziato), 32083 (il livello di manutenzione è stato completato), 32089 (si è verificato un errore a causa del riempimento del database).</span><span class="sxs-lookup"><span data-stu-id="5e2d6-169">During the export operation, the Lync Server Storage Service records every stage in the event log with event IDs of 32075 (full flush operation is started), 32076 (full flush is completed), 32082 (maintenance level flush is started), 32083 (maintenance level flush is completed), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="5e2d6-170">Questi dati non verranno automaticamente riportati nel sistema in modo da essere elaborati e recapitati alla destinazione finale (SQL Server o Exchange Server).</span><span class="sxs-lookup"><span data-stu-id="5e2d6-170">This data will not automatically be imported back to the system to be processed and delivered to its final destination (SQL Server or Exchange Server).</span></span>

<span data-ttu-id="5e2d6-171">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-171">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-172">Per importare i dati nel sistema, gli amministratori dovranno utilizzare lo strumento ImportStorageServiceData in Lync Server Resource Kit, che consente di aggiungere i dati di nuovo nel sistema per essere elaborati e recapitati alla destinazione finale.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-172">To import the data to the system, administrators will need to use the ImportStorageServiceData tool in the Lync Server Resource Kit, which will add the data back into the system to be processed and delivered to its final destination.</span></span>

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a><span data-ttu-id="5e2d6-173">Le ricerche delle query Web della Rubrica non avranno esito positivo se il valore predefinito di UseNormalizationRules viene impostato su false.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-173">Address Book Web Query searches will fail if the default value for UseNormalizationRules is changed to False</span></span>

<span data-ttu-id="5e2d6-174">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-174">**Issue:**</span></span>

<span data-ttu-id="5e2d6-175">Se il valore predefinito di UseNormalizationRules viene impostato su false, le ricerche di query Web della Rubrica non avranno esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-175">If the default value for UseNormalizationRules is changed to False, Address Book Web Query searches will fail.</span></span> <span data-ttu-id="5e2d6-176">Dopo la modifica del valore predefinito, gli utenti di Lync client non saranno in grado di utilizzare la query Web della Rubrica di Lync per cercare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-176">After the default value is changed, Lync Client users will not be able to use Lync Address Book web query to search for users.</span></span>

<span data-ttu-id="5e2d6-177">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-177">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-178">Se il valore predefinito per UseNormalizationRules è impostato su false in modo che gli utenti possano utilizzare i numeri di telefono definiti in servizi di dominio Active Directory senza Lync Server 2013 che applica le regole di normalizzazione, risolvere il problema eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-178">If the default value for UseNormalizationRules is set to False so that users can use phone numbers as defined in Active Directory Domain Services without Lync Server 2013 applying normalization rules, work around this issue by doing the following:</span></span>

1.  <span data-ttu-id="5e2d6-179">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-179">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="5e2d6-180">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-180">Do one of the following:</span></span>
    
      - <span data-ttu-id="5e2d6-181">Se la distribuzione include solo server Lync Server 2013, eseguire il seguente cmdlet a livello globale per modificare i valori di UseNormalizationRules e IgnoreGenericRules su true:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-181">If your deployment includes only Lync Server 2013 servers, run the following cmdlet at the global level to change the values for UseNormalizationRules and IgnoreGenericRules to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="5e2d6-182">Se nella distribuzione è inclusa una combinazione di Lync Server 2013 e Lync Server 2010 o Office Communications Server 2007 R2, eseguire il cmdlet seguente e assegnarlo a ogni pool Lync Server 2013 nella topologia:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-182">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="5e2d6-183">Attendere che la replica CMS venga eseguita in tutti i pool.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-183">Wait for CMS replication to occur on all pools.</span></span>

4.  <span data-ttu-id="5e2d6-184">Modificare il file delle regole di normalizzazione del telefono per la distribuzione per cancellare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-184">Modify the phone normalization rules file for your deployment to clear the content.</span></span> <span data-ttu-id="5e2d6-185">Il file si trova nella condivisione file di ogni pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-185">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="5e2d6-186">Se il file non è presente, creare un file vuoto denominato "società di \_ \_ normalizzazione numeri di telefono \_ \_Rules.txt".</span><span class="sxs-lookup"><span data-stu-id="5e2d6-186">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt."</span></span>

5.  <span data-ttu-id="5e2d6-187">Attendere alcuni minuti per tutti i pool Front end per leggere i nuovi file.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-187">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="5e2d6-188">Eseguire il cmdlet seguente in ogni pool di Lync Server 2013 nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-188">Run the following cmdlet on each Lync Server 2013 pool in your deployment.</span></span>
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a><span data-ttu-id="5e2d6-189">L'evento di errore 21054 del server della Rubrica viene generato una volta al giorno per ogni pool Lync 2013</span><span class="sxs-lookup"><span data-stu-id="5e2d6-189">Address Book Server error event 21054 is generated once daily for each Lync 2013 pool</span></span>

<span data-ttu-id="5e2d6-190">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-190">**Issue:**</span></span>

<span data-ttu-id="5e2d6-191">Lync Server 2013 Address Book Server genererà l'evento di errore 21054 una volta al giorno quando si eseguono le operazioni di manutenzione giornaliera.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-191">Lync Server 2013 Address Book Server will generate error event 21054 once every day when performing daily maintenance.</span></span> <span data-ttu-id="5e2d6-192">L'errore viene generato anche ogni volta che un amministratore esegue il cmdlet **Update-csAddressBook** , anche quando l'aggiornamento ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-192">The error is also generated every time an administrator runs the **Update-csAddressBook** cmdlet, even when the update is successful.</span></span> <span data-ttu-id="5e2d6-193">Tuttavia, questo evento di errore può essere ignorato senza problemi quando l'aggiornamento ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-193">However, this error event can safely be ignored when the update is successful.</span></span>

<span data-ttu-id="5e2d6-194">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-194">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-195">Quando si verifica questo evento di errore, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-195">When you encounter this error event, run the following cmdlet:</span></span>

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

<span data-ttu-id="5e2d6-196">Se il cmdlet segnala che non sono presenti oggetti non indicizzati o abbandonati, l'evento di errore 21054 può essere ignorato senza problemi.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-196">If the cmdlet reports that there are no unindexed or abandoned objects, the error event 21054 can be safely ignored.</span></span>

<span data-ttu-id="5e2d6-197">Inoltre, l'indicatore di integrità chiave (KHI) "gli utenti della rubrica correttamente indicizzati" deve essere disattivato in System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-197">Additionally, the Key Health Indicator (KHI) "Address Book Users Correctly Indexed" should be turned off in System Center Operations Manager.</span></span>

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a><span data-ttu-id="5e2d6-198">Le richieste potrebbero non riuscire quando IPv6 è configurato in un pool di server perimetrali</span><span class="sxs-lookup"><span data-stu-id="5e2d6-198">Requests may fail when IPv6 is configured on an Edge pool</span></span>

<span data-ttu-id="5e2d6-199">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-199">**Issue:**</span></span>

<span data-ttu-id="5e2d6-200">Quando IPv6 è configurato in un pool di server perimetrali, alcune richieste al pool di server perimetrali potrebbero avere esito negativo.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-200">When IPv6 is configured on an Edge pool, some requests to the Edge pool may fail.</span></span>

<span data-ttu-id="5e2d6-201">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-201">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-202">Per ovviare a questo problema, non configurare un pool di server perimetrali con IPv6.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-202">To work around this issue, do not configure an Edge pool with IPv6.</span></span>

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a><span data-ttu-id="5e2d6-203">Il cmdlet Invoke-csPoolFailback potrebbe avere esito negativo durante il failback del pool</span><span class="sxs-lookup"><span data-stu-id="5e2d6-203">The invoke-csPoolFailback cmdlet may fail during pool failback</span></span>

<span data-ttu-id="5e2d6-204">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-204">**Issue:**</span></span>

<span data-ttu-id="5e2d6-205">Quando si tenta di eseguire il failover di un pool, il cmdlet **Invoke-csPoolFailback** potrebbe avere esito negativo con l'errore "Impossibile completare il processo di idratazione dopo ripetuti tentativi".</span><span class="sxs-lookup"><span data-stu-id="5e2d6-205">When attempting to fail back a pool, the **invoke-csPoolFailback** cmdlet may fail with the error, "Failed to complete hydration process after repeated attempts."</span></span>

<span data-ttu-id="5e2d6-206">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-206">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-207">Per ovviare a questo problema, eseguire di nuovo il cmdlet e attendere che il cmdlet abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-207">To work around this issue, run the cmdlet again, and wait until the cmdlet succeeds.</span></span> <span data-ttu-id="5e2d6-208">Tenere presente che il processo di failback può richiedere alcuni minuti per il completamento.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-208">Note that the failback process can take several minutes to complete.</span></span> <span data-ttu-id="5e2d6-209">Possono essere necessari fino a 60 minuti per un pool con 20.000 utenti.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-209">It may take up to 60 minutes for a pool with 20,000 users.</span></span>

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a><span data-ttu-id="5e2d6-210">La perdita di dati può verificarsi quando si aggiunge un front end server a un pool già esistente, ovvero ibrido, Skype for business online</span><span class="sxs-lookup"><span data-stu-id="5e2d6-210">Data loss may occur when you add a Front End Server to an already established pool – Hybrid, Skype for Business Online</span></span>

<span data-ttu-id="5e2d6-211">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-211">**Issue:**</span></span>

<span data-ttu-id="5e2d6-212">È possibile che si verifichi questo problema in un ambiente in cui un pool ha più di un front end server e si riavvia uno dei Front End Server oppure si aggiunge un nuovo front end server che precedentemente non faceva parte del pool.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-212">You may encounter this issue in an environment where a pool has more than one Front End Server, and you either restart one of the Front End Servers, or add a new Front End Server that was not previously part of the pool.</span></span>

<span data-ttu-id="5e2d6-213">Gli utenti i cui dati vengono archiviati possono riscontrare una perdita di dati fino a quando non viene stabilita una distribuzione stabile dell'archiviazione dei dati per il pool.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-213">Users whose data is being archived may experience data loss until a stable distribution of data archiving is established for the pool.</span></span> <span data-ttu-id="5e2d6-214">Questo periodo di potenziale perdita di dati è limitato a 15 minuti per le conversazioni da persona a persona e a 30 minuti per le conferenze.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-214">This period of potential data loss is limited to 15 minutes for person-to-person conversations, and 30 minutes for conferences.</span></span>

<span data-ttu-id="5e2d6-215">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-215">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-216">Quando si esegue la manutenzione, invece di avviare Front End Server nel pool uno alla volta, è necessario eseguire il failover del pool in un altro pool e quindi effettuare le attività di manutenzione nei server.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-216">When you perform maintenance, instead of starting Front End Servers in the pool one by one, you should fail over the pool to another pool, and then perform maintenance tasks on the servers.</span></span> <span data-ttu-id="5e2d6-217">È inoltre possibile rendere il servizio non disponibile prima di eseguire le attività di manutenzione e quindi ripristinare la disponibilità al termine della manutenzione.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-217">You can also make the service unavailable before performing maintenance tasks, and then restore availability when maintenance is complete.</span></span>

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a><span data-ttu-id="5e2d6-218">Gli amministratori non possono ottenere il numero di licenziatari utilizzando il cmdlet Get-CsClientAccessLicense</span><span class="sxs-lookup"><span data-stu-id="5e2d6-218">Administrators cannot get licensee count by using the Get-CsClientAccessLicense cmdlet</span></span>

<span data-ttu-id="5e2d6-219">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-219">**Issue:**</span></span>

<span data-ttu-id="5e2d6-220">Gli amministratori non possono ottenere un utilizzo accurato della licenza client utilizzando il cmdlet **Get-CsClientAccessLicense** .</span><span class="sxs-lookup"><span data-stu-id="5e2d6-220">Administrators cannot get accurate client license usage by using the **Get-CsClientAccessLicense** cmdlet.</span></span>

<span data-ttu-id="5e2d6-221">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-221">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-222">Per controllare il tipo di licenza del server, è possibile eseguire il cmdlet **Get-CsService** per recuperare i nomi di dominio completi (FDQNs) di tutti i database.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-222">To check the server license type, you can run the **Get-CsService** cmdlet to retrieve the fully qualified domain names (FDQNs) of all databases.</span></span> <span data-ttu-id="5e2d6-223">Se il nome di dominio completo del server front end è uguale al nome di dominio completo del database back-end, la licenza è una licenza Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-223">If the FQDN of the Front End Server is the same as the FQDN of the back-end database, the license is a Standard edition license.</span></span> <span data-ttu-id="5e2d6-224">In caso contrario, la licenza è una licenza Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-224">Otherwise, the license is an Enterprise edition license.</span></span>

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a><span data-ttu-id="5e2d6-225">Il numero del Licenziatario client non è stato segnalato accuratamente</span><span class="sxs-lookup"><span data-stu-id="5e2d6-225">Client licensee count is not accurately reported</span></span>

<span data-ttu-id="5e2d6-226">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-226">**Issue:**</span></span>

<span data-ttu-id="5e2d6-227">Quando si determinano i conteggi delle licenze client, è possibile che si verifichino le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-227">When determining client license counts, you may experience the following conditions:</span></span>

1.  <span data-ttu-id="5e2d6-228">**Conteggio delle licenze non accurato per gli utenti mobili**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-228">**Inaccurate license count for mobile users**</span></span>
    
    <span data-ttu-id="5e2d6-229">Il conteggio delle licenze si basa sul numero di indirizzi IP univoci per gli utenti basati su dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-229">The license count is based on the number of unique IP addresses for device-based users.</span></span> <span data-ttu-id="5e2d6-230">Il numero di licenze sarà limitato nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-230">The license count will be limited in the following ways:</span></span>
    
      - <span data-ttu-id="5e2d6-231">Le licenze verranno contate se l'indirizzo IP dell'utente cambia durante le sessioni di Lync.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-231">Licenses will be overcounted if the IP address for the user changes during Lync sessions.</span></span> <span data-ttu-id="5e2d6-232">Ciò può verificarsi quando un utente si connette a Lync Server da più di una posizione con un client desktop.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-232">This can occur when a user connects to Lync Server from more than one location with a desktop client.</span></span>
    
      - <span data-ttu-id="5e2d6-233">Le licenze verranno sottovalutate se un utente si connette a un client per dispositivi mobili, perché non è possibile determinare l'indirizzo IP per il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-233">Licenses will be undercounted if a user connects with a mobile client, because the IP address for the device cannot be determined.</span></span>

2.  <span data-ttu-id="5e2d6-234">**Le licenze vengono conteggiate due volte per le chiamate PSTN (Public Switched Telephone Network) al client Lync, le chiamate client Lync alle linee PSTN e le chiamate Lync inoltrate a linee PSTN**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-234">**Licenses are counted twice for public switched telephone network (PSTN) calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="5e2d6-235">Negli scenari seguenti verranno conteggiate due licenze aggiuntive invece di una, in quanto il numero di telefono e l'utente di Lync vengono conteggiati per determinare il numero di licenze utilizzate.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-235">In the following scenarios, two additional licenses will be counted instead of one because both the phone number and the Lync user are counted to determine the number of licenses used.</span></span> <span data-ttu-id="5e2d6-236">Per ottenere dati di licenza accurati, rimuovere manualmente le licenze generate da un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-236">To obtain accurate licensing data, manually remove the licenses generated by a phone number.</span></span>
    
      - <span data-ttu-id="5e2d6-237">Una telefonata PSTN a Lync</span><span class="sxs-lookup"><span data-stu-id="5e2d6-237">A PSTN phone call to Lync</span></span>
    
      - <span data-ttu-id="5e2d6-238">Una chiamata Lync a una linea PSTN</span><span class="sxs-lookup"><span data-stu-id="5e2d6-238">A Lync call to a PSTN line</span></span>
    
      - <span data-ttu-id="5e2d6-239">Chiamata PSTN a Lync e quindi Lync inoltra la chiamata a una linea PSTN.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-239">A PSTN call to Lync, and then Lync forwards the call to a PSTN line.</span></span> <span data-ttu-id="5e2d6-240">Viene conteggiata una delle linee PSTN.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-240">One of the PSTN lines will be counted.</span></span>

3.  <span data-ttu-id="5e2d6-241">**Non viene conteggiata una licenza per un telefono Lync connesso**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-241">**A license will not be counted for a logged-on Lync phone**</span></span>
    
    <span data-ttu-id="5e2d6-242">Quando un utente utilizza un telefono con certificazione Lync, se il telefono entra e rimane connesso, mantenendo lo stato di accesso, il telefono non verrà conteggiato come utilizzo di una licenza se la query per le licenze si verifica dopo che il telefono è connesso.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-242">When a user uses a Lync-certified phone, if the phone logs in and stays connected, which retains its logon status, the phone will not be counted as using a license if the query for licenses occurs after the phone logged in.</span></span>

4.  <span data-ttu-id="5e2d6-243">**Licenze conteggiate per i telefoni PSTN che partecipano alle conferenze**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-243">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="5e2d6-244">Quando un utente entra a far parte di una conferenza con un telefono PSTN, viene conteggiata una licenza per partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-244">When a user joins a conference with a PSTN phone, a license will inaccurately be counted for joining the conference.</span></span> <span data-ttu-id="5e2d6-245">Tuttavia, non è necessaria alcuna licenza per partecipare a una conferenza con un telefono PSTN.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-245">However, no license is needed to join a conference with a PSTN phone.</span></span>

<span data-ttu-id="5e2d6-246">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-246">**Workaround:**</span></span>

1.  <span data-ttu-id="5e2d6-247">**Conteggio delle licenze non accurato per gli utenti mobili**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-247">**Inaccurate license count for mobile users**</span></span>
    
      - <span data-ttu-id="5e2d6-248">È possibile identificare manualmente gli indirizzi IP che appartengono allo stesso dispositivo e quindi rimuoverne uno nel conteggio delle licenze.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-248">You can manually identify the IP addresses that belong to the same device and then remove one of them in the license count.</span></span>
    
      - <span data-ttu-id="5e2d6-249">Non esiste alcuna soluzione per questo problema con i dispositivi mobili che si connettono al client Lync.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-249">There is no workaround for this issue with mobile devices connecting with Lync client.</span></span>

2.  <span data-ttu-id="5e2d6-250">**Le licenze vengono conteggiate due volte per le chiamate PSTN al client Lync, le chiamate client Lync alle linee PSTN e le chiamate Lync inoltrate a linee PSTN**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-250">**Licenses are counted twice for PSTN calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="5e2d6-251">Sarà necessario identificare manualmente il numero di telefono PSTN e rimuovere il conteggio delle licenze generato.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-251">You will need to manually identify the PSTN phone number and remove the license count generated for it.</span></span>

3.  <span data-ttu-id="5e2d6-252">**Non viene conteggiata una licenza per un telefono Lync connesso**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-252">**A license will not be counted for a logged-in Lync phone**</span></span>
    
    <span data-ttu-id="5e2d6-253">È possibile configurare il telefono Lync per disconnettersi e quindi eseguire di nuovo l'accesso, a intervalli regolari, ad esempio ogni 3 mesi.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-253">You can configure the Lync phone to log off, and then log on again, at a regular interval, such as every 3 months.</span></span>

4.  <span data-ttu-id="5e2d6-254">**Licenze conteggiate per i telefoni PSTN che partecipano alle conferenze**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-254">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="5e2d6-255">È possibile identificare manualmente il numero di telefono PSTN utilizzato per partecipare alla conferenza e rimuovere la licenza generata dal numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-255">You can manually identify the PSTN phone number that is used to join the conference and remove the license generated by the phone number.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a><span data-ttu-id="5e2d6-256">Il pannello di controllo di Lync Server smette di funzionare in un ambiente VMware dopo l'aggiornamento a Silverlight 5</span><span class="sxs-lookup"><span data-stu-id="5e2d6-256">The Lync Server Control Panel stops working in a VMware environment after upgrading to Silverlight 5</span></span>

<span data-ttu-id="5e2d6-257">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-257">**Issue:**</span></span>

<span data-ttu-id="5e2d6-258">Se si utilizza il pannello di controllo di Lync Server in un ambiente VMware, è possibile che il pannello di controllo di Lync Server smetta di funzionare dopo l'aggiornamento di Microsoft Silverlight alla versione 5.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-258">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Microsoft Silverlight to version 5.</span></span>

<span data-ttu-id="5e2d6-259">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-259">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-260">Per risolvere questo problema, effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-260">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="5e2d6-261">Disinstallare Silverlight 5 e installare Silverlight 4 da [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156) .</span><span class="sxs-lookup"><span data-stu-id="5e2d6-261">Uninstall Silverlight 5, and install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156).</span></span>

  - <span data-ttu-id="5e2d6-262">Accedere al pannello di controllo di Lync Server da un computer che non sia un computer virtuale VMware.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-262">Access the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="5e2d6-263">A tale scopo, è possibile avviare il pannello di controllo di Lync Server dal menu **Start** di Windows nel server, se gli strumenti di amministrazione di Lync Server sono installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-263">To do so, you can start the Lync Server Control Panel from the Windows **Start** menu on the server, if the Lync Server Administration tools are installed on the computer.</span></span>
    
    <span data-ttu-id="5e2d6-264">È inoltre possibile accedere al pannello di controllo di Lync Server tramite un Web browser.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-264">You can also access the Lync Server Control Panel by using a web browser.</span></span> <span data-ttu-id="5e2d6-265">L'URL sarà simile a https:// \<frontend\_pool\_fqdn\> /CSCP.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-265">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a><span data-ttu-id="5e2d6-266">Le informazioni degli utenti nel servizio Rubrica non vengono aggiornate dopo che il nome distinto per l'utente è stato modificato in Active Directory</span><span class="sxs-lookup"><span data-stu-id="5e2d6-266">User information in the Address Book Service is not updated after the distinguished name for the user is modified in Active Directory</span></span>

<span data-ttu-id="5e2d6-267">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-267">**Issue:**</span></span>

<span data-ttu-id="5e2d6-268">Se il nome distinto di un utente (noto anche come DN) viene modificato in servizi di dominio Active Directory, eventuali modifiche aggiuntive non verranno aggiornate nel servizio Rubrica (ABS).</span><span class="sxs-lookup"><span data-stu-id="5e2d6-268">If a user’s distinguished name (also known as DN) is changed in Active Directory Domain Services, any additional changes will not be updated in the Address Book Service (ABS).</span></span> <span data-ttu-id="5e2d6-269">Questo non ha effetto sull'accesso o sulla presenza dell'utente, ma impedirà la comunicazione per l'utente se viene modificato anche l'indirizzo SIP, in quanto le ricerche restituiranno un indirizzo SIP obsoleto.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-269">This does not affect sign-in or presence for the user, but it will prevent communication for the user if the SIP address is also changed, because searches will return an outdated SIP address.</span></span>

<span data-ttu-id="5e2d6-270">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-270">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-271">Per ovviare a questo problema, non modificare il DN di un utente.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-271">To work around this issue, do not change a user’s DN.</span></span> <span data-ttu-id="5e2d6-272">Se si ripristina il nome distinto per l'utente al valore precedente, gli aggiornamenti verranno riflessi nel servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-272">If you revert the DN for the user to the previous value, updates will be reflected in the Address Book Service.</span></span>

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a><span data-ttu-id="5e2d6-273">Installazione</span><span class="sxs-lookup"><span data-stu-id="5e2d6-273">Installation</span></span>

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a><span data-ttu-id="5e2d6-274">L'utilizzo di caratteri non ASCII può comportare la mancata avvio di Lync Server</span><span class="sxs-lookup"><span data-stu-id="5e2d6-274">Using non-ASCII characters may result in Lync server failing to start</span></span>

<span data-ttu-id="5e2d6-275">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-275">**Issue:**</span></span>

<span data-ttu-id="5e2d6-276">Il programma di installazione avrà esito negativo se il nome della cartella di destinazione include caratteri non ASCII (inclusi UNICODE, set di caratteri a doppio byte (DBCS), UTF-8 e UTF-16).</span><span class="sxs-lookup"><span data-stu-id="5e2d6-276">Setup will fail if the destination folder name includes non-ASCII characters (including UNICODE, double-byte character set (DBCS), UTF-8, and UTF-16).</span></span> <span data-ttu-id="5e2d6-277">Inoltre, il programma di installazione può avere esito positivo, ma il server non verrà avviato se i caratteri non ASCII sono contenuti in una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-277">In addition, Setup may succeed but the server will not start if non-ASCII characters are contained in any of the following:</span></span>

  - <span data-ttu-id="5e2d6-278">Nome computer</span><span class="sxs-lookup"><span data-stu-id="5e2d6-278">Computer name</span></span>

  - <span data-ttu-id="5e2d6-279">Nome di dominio</span><span class="sxs-lookup"><span data-stu-id="5e2d6-279">Domain name</span></span>

  - <span data-ttu-id="5e2d6-280">Nome utente</span><span class="sxs-lookup"><span data-stu-id="5e2d6-280">User name</span></span>

  - <span data-ttu-id="5e2d6-281">URI SIP dell'utente</span><span class="sxs-lookup"><span data-stu-id="5e2d6-281">User SIP URI</span></span>

  - <span data-ttu-id="5e2d6-282">Nome dell'account del servizio</span><span class="sxs-lookup"><span data-stu-id="5e2d6-282">Service account name</span></span>

<span data-ttu-id="5e2d6-283">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-283">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-284">Utilizzare solo caratteri ASCII nel nome della cartella di destinazione, del nome del computer, del nome di dominio, del nome utente, dell'URI SIP dell'utente e dei nomi degli account di servizio.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-284">Use only ASCII characters in the destination folder name, computer name, domain name, user name, user SIP URI, and service account names.</span></span>

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a><span data-ttu-id="5e2d6-285">L'hotfix per "danneggiamento dell'heap si verifica quando un modulo chiama il metodo InsertEntityBody in IIS 7,5" deve essere installato prima di installare Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e2d6-285">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" must be installed prior to installing Lync Server 2013</span></span>

<span data-ttu-id="5e2d6-286">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-286">**Issue:**</span></span>

<span data-ttu-id="5e2d6-287">L'hotfix per "danneggiamento dell'heap si verifica quando un modulo chiama il metodo InsertEntityBody in IIS 7,5" ( [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602) ), descritto nell'articolo 264886 della Microsoft Knowledge base [https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603) , deve essere installato prima di installare Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-287">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" ([https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)), described in Microsoft Knowledge Base article 264886 ([https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)), must be installed prior to installing Lync Server 2013.</span></span>

<span data-ttu-id="5e2d6-288">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-288">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-289">Scaricare e installare l'hotfix dall'area download Microsoft all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602) .</span><span class="sxs-lookup"><span data-stu-id="5e2d6-289">Download and install the hotfix from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602).</span></span>

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a><span data-ttu-id="5e2d6-290">Lync Server 2013 non è in grado di installare la versione di Windows Server 2012 OS RTM di ITA</span><span class="sxs-lookup"><span data-stu-id="5e2d6-290">Lync Server 2013 fails to install on ITA Windows Server 2012 OS RTM version</span></span>

<span data-ttu-id="5e2d6-291">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-291">**Issue:**</span></span>

<span data-ttu-id="5e2d6-292">L'installazione di Lync Server 2013 ha esito negativo su ITA Windows Server 2012 a causa di un errore di installazione di Windows Fabric.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-292">Lync Server 2013 installation fails on ITA Windows Server 2012 due to Windows Fabric installation failing.</span></span>

<span data-ttu-id="5e2d6-293">L'installazione di Windows Fabric ha esito negativo perché le tracce Fabric vengono create con il formato ora HH: MM: SS.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-293">Windows Fabric installation fails because fabric traces are created with the time format of HH:MM:SS.</span></span> <span data-ttu-id="5e2d6-294">Tuttavia, in ITA Windows Server, il formato dell'ora è HH. MM.SS.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-294">However, in ITA Windows Server, the time format is HH.MM.SS.</span></span>

<span data-ttu-id="5e2d6-295">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-295">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-296">Per ovviare a questo problema, aggiornare il registro di sistema prima di installare Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-296">To work around this issue, update the system registry before installing Lync Server 2013.</span></span> <span data-ttu-id="5e2d6-297">La chiave del registro di sistema che deve essere aggiornata è: \_ gli utenti di HKEY \\ . \\STimeFormat internazionale del pannello di controllo predefinito \\ \\ .</span><span class="sxs-lookup"><span data-stu-id="5e2d6-297">The registry key that needs to be updated is: HKEY\_USERS\\.DEFAULT\\Control Panel\\International\\sTimeFormat.</span></span> <span data-ttu-id="5e2d6-298">Per modificare il valore di sTimeFormat in HH: mm: SS, utilizzare l'interfaccia della riga di comando di Windows PowerShell come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-298">Change the value of sTimeFormat to HH:mm:ss by using the Windows PowerShell command-line interface as follows:</span></span>

1.  <span data-ttu-id="5e2d6-299">Avviare Windows PowerShell ed eseguire i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-299">Start Windows PowerShell and run the following cmdlets:</span></span>
    
       ```PowerShell
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```PowerShell
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  <span data-ttu-id="5e2d6-300">Per visualizzare il valore corrente, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-300">To view the current value, run the following cmdlet:</span></span>
    
        Get-itemproperty $a -Name sTimeFormat
    
    <span data-ttu-id="5e2d6-301">Prendere nota del valore corrente per sTimeFormat in modo che possa essere ripristinato al termine dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-301">Make note of the current value for sTimeFormat so it can be restored after the installation is complete.</span></span>

3.  <span data-ttu-id="5e2d6-302">Per impostare il nuovo valore, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-302">To set to new value, run the following cmdlet:</span></span>
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  <span data-ttu-id="5e2d6-303">Dopo che Lync Server 2013 è stato installato correttamente, ripristinare il valore originale di sTimeFormat eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-303">After Lync Server 2013 has been successfully installed, restore the original value for the sTimeFormat by running the following cmdlet:</span></span>
    
        - <span data-ttu-id="5e2d6-304">Set-ItemProperty $a-Name sTimeFormat-value "<valore annotato al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-304">Set-ItemProperty $a -Name sTimeFormat -Value "<Value noted down in Step 3.</span></span> <span data-ttu-id="5e2d6-305">sopra> "</span><span class="sxs-lookup"><span data-stu-id="5e2d6-305">above>"</span></span>

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a><span data-ttu-id="5e2d6-306">Mobilità</span><span class="sxs-lookup"><span data-stu-id="5e2d6-306">Mobility</span></span>

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a><span data-ttu-id="5e2d6-307">Problemi relativi ai client mobili durante il processo di failover del server</span><span class="sxs-lookup"><span data-stu-id="5e2d6-307">Issues for mobile clients during the server failover process</span></span>

<span data-ttu-id="5e2d6-308">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-308">**Issue:**</span></span>

<span data-ttu-id="5e2d6-309">Quando un server Lync ha esito negativo e il processo di failover inizia, i problemi seguenti possono influire sugli utenti dei client mobili:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-309">When a Lync Server fails and the failover process begins, the following issues may affect mobile client users:</span></span>

  - <span data-ttu-id="5e2d6-310">Nessuna chiamata o segnale di Lync in arrivo per un massimo di 10 minuti dopo l'inizio del failover.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-310">No incoming Lync call or signal for up to 10 minutes after failover begins.</span></span>

  - <span data-ttu-id="5e2d6-311">Non è in grado di accettare le richieste chat in arrivo</span><span class="sxs-lookup"><span data-stu-id="5e2d6-311">Cannot accept incoming Chat requests</span></span>

  - <span data-ttu-id="5e2d6-312">Non è possibile partecipare a riunioni se il server non riuscito è il server principale dell'utente</span><span class="sxs-lookup"><span data-stu-id="5e2d6-312">Cannot join meetings if the failed server is the home server for the user</span></span>

<span data-ttu-id="5e2d6-313">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-313">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-314">Non esiste alcuna soluzione per questo problema.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-314">There is no workaround for this issue.</span></span> <span data-ttu-id="5e2d6-315">Una volta completata la procedura di failover, la funzionalità normale verrà ripristinata.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-315">Normal functionality will be restored once the failover process is complete.</span></span>

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a><span data-ttu-id="5e2d6-316">Se un utente mobile rifiuta una chiamata in arrivo da un altro endpoint Lync, la chiamata viene visualizzata come una conversione persa nei client mobili di Lync</span><span class="sxs-lookup"><span data-stu-id="5e2d6-316">If a mobile user declines an incoming call from another Lync endpoint, the call is displayed as a missed conversion on Lync Mobile clients</span></span>

<span data-ttu-id="5e2d6-317">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-317">**Issue:**</span></span>

<span data-ttu-id="5e2d6-318">Se un utente mobile rifiuta una chiamata in arrivo e la chiamata ha avuto origine da un altro endpoint Lync, la chiamata viene visualizzata come una conversazione persa nel client mobile di Lync anziché una chiamata nell'elenco delle chiamate di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-318">If a mobile user declines an incoming call, and the call originated from another Lync endpoint, the call is displayed as a missed conversation in the Lync Mobile client instead of a call in the device call list.</span></span>

<span data-ttu-id="5e2d6-319">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-319">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-320">Non esiste alcuna soluzione per questo problema.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-320">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a><span data-ttu-id="5e2d6-321">Il client per dispositivi mobili potrebbe non visualizzare il nome visualizzato di un contatto federato durante la ricerca di contatti</span><span class="sxs-lookup"><span data-stu-id="5e2d6-321">The mobile client may not display a federated contact’s display name when searching for contacts</span></span>

<span data-ttu-id="5e2d6-322">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-322">**Issue:**</span></span>

<span data-ttu-id="5e2d6-323">Il nome visualizzato per i contatti federati potrebbe non essere visualizzato in alcuni scenari, ad esempio durante la ricerca di un contatto federato nell'elenco dei contatti.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-323">The display name for federated contacts may not be displayed in some scenarios, such as when searching for a federated contact in the contact list.</span></span> <span data-ttu-id="5e2d6-324">Questo problema può verificarsi quando non è presente alcuna sottoscrizione di presenza attiva per il contatto dal client di Lync mobile.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-324">This can occur when the there is no active presence subscription for the contact from the Lync mobile client.</span></span>

<span data-ttu-id="5e2d6-325">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-325">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-326">Non esiste alcuna soluzione per questo problema.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-326">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a><span data-ttu-id="5e2d6-327">Nel client per dispositivi mobili, le informazioni sull'invito e sul timestamp sono mancanti da una conversazione persa che è un invito a una conferenza</span><span class="sxs-lookup"><span data-stu-id="5e2d6-327">In the mobile client, invitee and timestamp information are missing from a missed conversation that is an invitation to a conference</span></span>

<span data-ttu-id="5e2d6-328">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-328">**Issue:**</span></span>

<span data-ttu-id="5e2d6-329">Nel client per dispositivi mobili, quando una conversazione persa è un invito a una conferenza, le informazioni sull'invito e sul timestamp sono mancanti dal messaggio di conversazione persa.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-329">In the mobile client, when a missed conversation is an invitation to a conference, the invitee and timestamp information is missing from the missed conversation message.</span></span>

<span data-ttu-id="5e2d6-330">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-330">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-331">Non esiste alcuna soluzione per questo problema.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-331">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a><span data-ttu-id="5e2d6-332">Gli utenti di client mobili che effettuano chiamate tramite VoIP non sono in grado di lasciare la segreteria telefonica per gli utenti la cui segreteria telefonica è configurata in Exchange 2010 o versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="5e2d6-332">Mobile client users making calls using VoIP are not be able to leave voice mail for users whose voice mail is configured in Exchange 2010 or earlier versions</span></span>

<span data-ttu-id="5e2d6-333">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-333">**Issue:**</span></span>

<span data-ttu-id="5e2d6-334">Se un utente di client mobili utilizza VoIP per effettuare chiamate, l'utente non sarà in grado di lasciare messaggi di segreteria telefonica per gli utenti configurati per l'utilizzo della segreteria telefonica in Microsoft Exchange Server 2007 o Microsoft Exchange Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-334">If a mobile client user is using VoIP to place calls, the user will not be able to leave voice mail messages for users configured to use voice mail in Microsoft Exchange Server 2007 or Microsoft Exchange Server 2010.</span></span>

<span data-ttu-id="5e2d6-335">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-335">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-336">Per ovviare a questo problema, utilizzare Exchange 2010 con SP1 o versione successiva di Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-336">To work around this issue, use Exchange 2010 with SP1 or later version of Microsoft Exchange Server.</span></span>

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a><span data-ttu-id="5e2d6-337">Quando si utilizza il blocco con l'URL per la configurazione della versione client sui client mobili, potrebbe essere visualizzato un messaggio di errore non corretto</span><span class="sxs-lookup"><span data-stu-id="5e2d6-337">When using Block with URL for Client Version Configuration on mobile clients, an incorrect error message may be displayed</span></span>

<span data-ttu-id="5e2d6-338">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-338">**Issue:**</span></span>

<span data-ttu-id="5e2d6-339">Quando si utilizza il **blocco con l'URL** per la configurazione della versione client nei client mobili, è possibile che venga visualizzato un messaggio di errore non corretto quando la versione client non è supportata.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-339">When using **Block with URL** for Client Version Configuration on mobile clients, an incorrect error message may be displayed when the client version is not supported.</span></span>

<span data-ttu-id="5e2d6-340">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-340">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-341">Per ovviare a questo problema, configurare la configurazione della versione client in modo da utilizzare **Block** anziché **Block con URL**.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-341">To work around this issue, configure Client Version Configuration to use **Block** instead of **Block with URL**.</span></span>

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a><span data-ttu-id="5e2d6-342">Conferenze</span><span class="sxs-lookup"><span data-stu-id="5e2d6-342">Conferencing</span></span>

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a><span data-ttu-id="5e2d6-343">Il software antivirus in esecuzione nei server front end di Lync Server 2013 può causare il riciclo dei domini applicazione, che interrompe temporaneamente il servizio per Lync Web App 2013, Lync Mobile 2010 e i client Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="5e2d6-343">Antivirus software running on Lync Server 2013 Front End Servers can cause Application Domain recycling, which temporarily interrupts service for Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013 clients</span></span>

<span data-ttu-id="5e2d6-344">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-344">**Issue:**</span></span>

<span data-ttu-id="5e2d6-345">Il software antivirus può attivare il riavvio del dominio dell'applicazione, che può comportare la perdita dello stato del servizio Lync Mobility Service 2013 e delle applicazioni client API Web per le comunicazioni unificate (Lync Web App 2013, Lync Mobile 2010 e Lync Mobile 2013).</span><span class="sxs-lookup"><span data-stu-id="5e2d6-345">Antivirus software can trigger application domain restarts, which can result in Lync Mobility Service 2013 and unified communications (UC) Web API client applications (Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013) to lose their state.</span></span>

<span data-ttu-id="5e2d6-346">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-346">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-347">Per ovviare a questo problema, escludere le cartelle contenenti componenti Web e .NET Framework dall'analisi antivirus.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-347">To work around this issue, exclude the folders containing Web components and .NET framework from antivirus scanning.</span></span> <span data-ttu-id="5e2d6-348">Per ulteriori informazioni, vedere l'articolo 312592 della Microsoft Knowledge Base "PRB: riavviamenti di applicazioni casuali con" applicazione di riavvio "in ASP.NET," at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592) .</span><span class="sxs-lookup"><span data-stu-id="5e2d6-348">For details, see Microsoft Knowledge Base article 312592, "PRB: Random application restarts with 'Application is restarting' error in ASP.NET," at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592).</span></span>

<span data-ttu-id="5e2d6-349">Le cartelle seguenti devono essere escluse:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-349">The following folders should be excluded:</span></span>

  - <span data-ttu-id="5e2d6-350">% ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web Components \\ MCX \\ ext</span><span class="sxs-lookup"><span data-stu-id="5e2d6-350">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Ext</span></span>

  - <span data-ttu-id="5e2d6-351">% ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web Components \\ MCX \\ int</span><span class="sxs-lookup"><span data-stu-id="5e2d6-351">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Int</span></span>

  - <span data-ttu-id="5e2d6-352">% ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web Components \\ UCWA \\ int</span><span class="sxs-lookup"><span data-stu-id="5e2d6-352">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Int</span></span>

  - <span data-ttu-id="5e2d6-353">% ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web Components \\ UCWA \\ ext</span><span class="sxs-lookup"><span data-stu-id="5e2d6-353">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Ext</span></span>

  - <span data-ttu-id="5e2d6-354">% WINDIR% \\ Microsoft.NET \\ Framework64 \\ v 4.0.30319 \\ config</span><span class="sxs-lookup"><span data-stu-id="5e2d6-354">%Windir%\\Microsoft.NET\\Framework64\\v4.0.30319\\Config</span></span>

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a><span data-ttu-id="5e2d6-355">I controlli ActiveX o il supporto nativo di XMLHTTP devono essere abilitati in Windows Internet Explorer per partecipare a conferenze con esito positivo</span><span class="sxs-lookup"><span data-stu-id="5e2d6-355">ActiveX Controls or native XMLHTTP support must be enabled in Windows Internet Explorer to successfully join conferences</span></span>

<span data-ttu-id="5e2d6-356">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-356">**Issue:**</span></span>

<span data-ttu-id="5e2d6-357">Se un utente ha disabilitato sia i controlli ActiveX sia il supporto nativo di XMLHTTP nelle impostazioni del browser Internet di Windows Internet Explorer, l'utente non sarà in grado di partecipare a una riunione se Internet Explorer è selezionato come browser predefinito.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-357">If a user has disabled both ActiveX Controls and native XMLHTTP support in Windows Internet Explorer Internet browser settings, the user will not be able to join a meeting if Internet Explorer is selected as the default browser.</span></span>

<span data-ttu-id="5e2d6-358">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-358">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-359">Abilitare i controlli ActiveX o "supporto nativo di XMLHTTP" in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-359">Enable either ActiveX Controls or "native XMLHTTP support" in Internet Explorer.</span></span>

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a><span data-ttu-id="5e2d6-360">Il servizio Web Conferencing di Lync Server non può essere ripristinato dalla modalità critica</span><span class="sxs-lookup"><span data-stu-id="5e2d6-360">Lync Server Web Conferencing service cannot recover from critical mode</span></span>

<span data-ttu-id="5e2d6-361">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-361">**Issue:**</span></span>

<span data-ttu-id="5e2d6-362">Se la modalità critica è attivata per l'archiviazione, in caso di errori di sistema, la modalità critica inizierà e le conferenze non funzioneranno più per i partecipanti.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-362">If critical mode is turned for archiving, in case of system failures, critical mode will start and the conferences will no longer work for the participants.</span></span> <span data-ttu-id="5e2d6-363">Dopo che l'amministratore ha risolto gli errori del sistema, ad esempio la risoluzione di un problema di database, il servizio di conferenza dati non viene ripristinato automaticamente e l'amministratore deve riavviare manualmente il servizio di conferenza per le conferenze da riprendere.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-363">After the administrator fixes the system failures (such as fixing a database issue), the data conferencing service doesn't automatically recover, and the administrator must manually restart the conferencing service for conferencing to resume.</span></span>

<span data-ttu-id="5e2d6-364">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-364">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-365">Un amministratore deve riavviare manualmente il servizio di conferenza dopo che è stato risolto il problema del sistema.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-365">An administrator needs to manually restart the conferencing service after the system failure is fixed.</span></span>

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a><span data-ttu-id="5e2d6-366">Il servizio Web Conferencing ignora il proxy HTTP per i server Office Web App esterni</span><span class="sxs-lookup"><span data-stu-id="5e2d6-366">Web Conferencing service ignores the HTTP proxy for external Office Web App Servers</span></span>

<span data-ttu-id="5e2d6-367">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-367">**Issue:**</span></span>

<span data-ttu-id="5e2d6-368">Se è stato distribuito un server Office Web Apps esterno al servizio Web Conferencing (ovvero un server che non è presente nella rete aziendale interna) in Internet, la rete perimetrale e il servizio Web Conferencing richiede un proxy HTTP per la connessione, l'individuazione del server Office Web Apps avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-368">If you have deployed an Office Web Apps Server external to the Web Conferencing service (that is, a server that is not in the internal corporate network) in the Internet, perimeter network, and the Web Conferencing service requires an HTTP proxy to connect to this, the Office Web Apps Server discovery will fail.</span></span> <span data-ttu-id="5e2d6-369">Il servizio Web Conferencing ignora l'impostazione del proxy HTTP, come definito in Generatore di topologie per il programma di installazione del server Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-369">The Web Conferencing service ignores the HTTP proxy setting, as defined in Topology Builder for Office Web Apps Server setup.</span></span> <span data-ttu-id="5e2d6-370">Di conseguenza, il client Lync non sarà in grado di eseguire la condivisione di Microsoft PowerPoint 2010 con altri partecipanti alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-370">As a result, the Lync client will not be able to do Microsoft PowerPoint 2010 sharing with other participants in the conference.</span></span> <span data-ttu-id="5e2d6-371">Se si sta installando Lync Server in locale e si configura anche il server Office Web Apps in locale nella rete interna, non è necessaria una configurazione proxy.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-371">If you are installing Lync Server on-premises and also configure Office Web Apps Server on-premises in the internal network, a proxy configuration is not required.</span></span>

<span data-ttu-id="5e2d6-372">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-372">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-373">L'unica soluzione alternativa consiste nel non disporre di una configurazione di distribuzione che richiede l'utilizzo del proxy HTTP per comunicare con un server Office Web Apps esterno.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-373">The only workaround is to not have a deployment configuration that requires the use of HTTP proxy to communicate with an external Office Web Apps Server.</span></span>

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a><span data-ttu-id="5e2d6-374">L'aggiunta di video a una conferenza di un provider di servizi di audioconferenza non è supportata</span><span class="sxs-lookup"><span data-stu-id="5e2d6-374">Adding video to an audio conferencing provider conference is not supported</span></span>

<span data-ttu-id="5e2d6-375">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-375">**Issue:**</span></span>

<span data-ttu-id="5e2d6-376">L'aggiunta di un video non è supportata se l'utente è aggiunto a una conferenza di un provider di servizi di audioconferenza per l'audio.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-376">Adding a video is not supported if the user is joined to an audio conferencing provider conference for audio.</span></span>

<span data-ttu-id="5e2d6-377">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-377">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-378">Non esiste alcuna soluzione per questo problema.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-378">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a><span data-ttu-id="5e2d6-379">Topologie con IPv6 abilitato forzare l'aggiornamento automatico del plug-in Silverlight di Lync Web App per garantire che le funzionalità di condivisione dello schermo possano funzionare da Lync Web App</span><span class="sxs-lookup"><span data-stu-id="5e2d6-379">Topologies with IPv6 enabled force the Lync Web App Silverlight plug-in auto-update to ensure screen sharing functionality can work from Lync Web App</span></span>

<span data-ttu-id="5e2d6-380">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-380">**Issue:**</span></span>

<span data-ttu-id="5e2d6-381">Quando una topologia è configurata con IPv6 abilitato, gli utenti non possono condividere la propria schermata dal client Lync Web App se è già installata una versione precedente del plug-in di condivisione dello schermo.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-381">When a topology is configured with IPv6 enabled, users cannot share their screen from the Lync Web App client if an earlier version of the screen-sharing plug-in is already installed.</span></span>

<span data-ttu-id="5e2d6-382">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-382">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-383">Per forzare un aggiornamento alla versione più recente del plug-in di condivisione dello schermo quando si accede a una riunione tramite Lync Web App, modificare il valore di **MinSupportedBuildVersion** da "4.0.7457.0" a "4.0.7577.380" in entrambi i file seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-383">To force an update to the most recent version of the screen-sharing plug-in when joining meeting via Lync Web App, modify the value of **MinSupportedBuildVersion** from "4.0.7457.0" to "4.0.7577.380" in both of the following files:</span></span>

  - <span data-ttu-id="5e2d6-384">% ProgramFiles% \\ Microsoft Lync Server 15 \\ Web Components \\ raggiungere i \\ \\ plugin client int \\ \\ReachAppShPluginProperties.xml</span><span class="sxs-lookup"><span data-stu-id="5e2d6-384">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Int\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

  - <span data-ttu-id="5e2d6-385">% ProgramFiles% \\ Microsoft Lync Server 15 \\ Web Components raggiungere i plug-in \\ \\ \\ client ext \\ \\ReachAppShPluginProperties.xml</span><span class="sxs-lookup"><span data-stu-id="5e2d6-385">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Ext\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a><span data-ttu-id="5e2d6-386">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="5e2d6-386">Enterprise Voice</span></span>

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a><span data-ttu-id="5e2d6-387">In alcuni casi, un client Lync in esecuzione su un computer configurato per l'utilizzo di IPv4 e IPv6 dual stack potrebbe non supportare funzionalità che si basano sulla subnet IP del computer, ad esempio E911, bypass multimediale, controllo di ammissione di chiamata e routing basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="5e2d6-387">In some cases, a Lync client running on a computer configured to use IPv4 and IPv6 dual stack might not support capabilities that rely in the IP subnet of the computer such as E911, Media Bypass, Call Admission Control and Location Based Routing</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="5e2d6-388">Le informazioni contenute in questa sezione riguardano gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-388">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="5e2d6-389">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-389">**Issue:**</span></span>

<span data-ttu-id="5e2d6-390">Quando un client Lync è in esecuzione in un computer abilitato per IPv4 e IPv6 dual stack e basato sulla risoluzione DNS del server proxy, il client può utilizzare l'indirizzo IPv6 del computer per l'accesso.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-390">When a Lync client is running on a computer that is enabled for IPv4 and IPv6 dual stack and based on the DNS resolution of the proxy server, the client may use the IPv6 address of the computer to sign in.</span></span> <span data-ttu-id="5e2d6-391">Dopo tale operazione, il client Lync supporterà solo le funzionalità supportate per IPv6, che esclude E911, il bypass multimediale, il controllo di ammissione di chiamata e il routing in base alla posizione.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-391">After doing so, the Lync Client will support only the capabilities supported for IPv6, which excludes E911, Media Bypass, Call Admission Control and Location Based Routing.</span></span>

<span data-ttu-id="5e2d6-392">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-392">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-393">Per ovviare a questo problema, disabilitare il supporto IPv6 sul computer client.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-393">To work around this issue, disable IPv6 support on the client computer.</span></span>

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a><span data-ttu-id="5e2d6-394">Se VoIP aziendale non è configurato per un utente, l'utente dovrà utilizzare il formato E164 per effettuare una chiamata in uscita da una conferenza.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-394">If Enterprise Voice is not configured for a user, the user will need to use E164 format to dial out from a conference</span></span>

<span data-ttu-id="5e2d6-395">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-395">**Issue:**</span></span>

<span data-ttu-id="5e2d6-396">Se VoIP aziendale non è configurato per un utente, sarà necessario utilizzare il formato E164 per effettuare una chiamata in uscita da una conferenza.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-396">If Enterprise Voice is not configured for a user, that user will need to use the E164 format to successfully dial out from a conference.</span></span> <span data-ttu-id="5e2d6-397">Se non si utilizza il formato E164, l'utente non sarà in grado di eseguire la chiamata in uscita dalla conferenza.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-397">If the E164 format is not used, the user will not be able to dial out from the conference.</span></span>

<span data-ttu-id="5e2d6-398">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-398">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-399">Per ovviare a questo problema, gli utenti che non sono abilitati per VoIP aziendale devono eseguire la chiamata in uscita da una conferenza utilizzando numeri nel formato E164.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-399">To work around this issue, users who are not enabled for Enterprise Voice should dial out from a conference by using numbers in the E164 format.</span></span>

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a><span data-ttu-id="5e2d6-400">Presenza</span><span class="sxs-lookup"><span data-stu-id="5e2d6-400">Presence</span></span>

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a><span data-ttu-id="5e2d6-401">Se un utente ha selezionato "blocca tutti gli inviti e le comunicazioni" mentre l'archivio contatti unificato è attivato per l'utente, lo stato presenza non è rifiutato quando dovrebbe esserlo.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-401">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be</span></span>

<span data-ttu-id="5e2d6-402">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-402">**Issue:**</span></span>

<span data-ttu-id="5e2d6-403">Se un utente ha selezionato "blocca tutti gli inviti e le comunicazioni" mentre l'archivio contatti unificato è attivato per l'utente, lo stato presenza non è rifiutato quando dovrebbe esserlo.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-403">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be.</span></span>

<span data-ttu-id="5e2d6-404">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-404">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-405">Per ovviare a questo problema, è possibile disattivare l'archivio contatti unificato per l'utente.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-405">To work around this issue, you can turn off the unified contact store for the user.</span></span> <span data-ttu-id="5e2d6-406">A tale scopo, eseguire i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-406">To do so, run the following cmdlets:</span></span>

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

<span data-ttu-id="5e2d6-407">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-407">For example:</span></span>

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a><span data-ttu-id="5e2d6-408">Gli utenti di Office Communications Server 2007 R2 ospitati in locale non sono in grado di visualizzare lo stato di presenza degli utenti di Skype for business online nelle distribuzioni ibride-ibrido</span><span class="sxs-lookup"><span data-stu-id="5e2d6-408">Office Communications Server 2007 R2 users homed on-premises are not able to see the Presence status of Skype for Business Online users in hybrid deployments - Hybrid</span></span>

<span data-ttu-id="5e2d6-409">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-409">**Issue:**</span></span>

<span data-ttu-id="5e2d6-410">È possibile che il problema si verifichi in una distribuzione ibrida quando si utilizza un Director di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-410">The issue may occur in a hybrid deployment when you are using a Lync Server 2013 Director.</span></span>

<span data-ttu-id="5e2d6-411">Lo stato di presenza per gli utenti ospitati in Skype for business online viene visualizzato come presenza sconosciuta per gli utenti locali.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-411">Presence status for users homed to Skype for Business Online is displayed as Presence Unknown for on-premises users.</span></span> <span data-ttu-id="5e2d6-412">Inoltre, gli utenti ospitati in Skype for business online non sono in grado di visualizzare lo stato di presenza per gli utenti locali di Office Communications Server R2.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-412">Also, users homed to Skype for Business Online are not able to see presence status for Office Communications Server R2 on-premises users.</span></span>

<span data-ttu-id="5e2d6-413">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-413">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-414">Per ovviare a questo problema, cambiare il server principale (msRTCSIP-presencehomeserver) degli utenti di Skype for business online in modo che puntino a un pool locale di Lync Server 2013 anziché al server Director di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-414">To partially work around this issue, change the Home Server (msrtcsip-presencehomeserver) of the Skype for Business Online users to point to a Lync Server 2013 on-premises pool instead of the Lync Server 2013 Director.</span></span> <span data-ttu-id="5e2d6-415">È possibile modificare questa impostazione nel front end server locale.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-415">You can modify this setting on the on-premises Front End Server.</span></span>

<span data-ttu-id="5e2d6-416">Questa soluzione consente di visualizzare correttamente lo stato di presenza degli utenti ospitati in Office Communications Server 2007 R2 per gli utenti di Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-416">This workaround will correctly display the Presence status of users homed to Office Communications Server 2007 R2 to Skype for Business Online users.</span></span>

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a><span data-ttu-id="5e2d6-417">Applicazione Response Group, applicazione Parcheggio di chiamata e raccolta di chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="5e2d6-417">Response Group application, Call Park application, and Group Call Pickup</span></span>

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a><span data-ttu-id="5e2d6-418">Un chiamante potrebbe udire un secondo di musica in attesa durante la creazione di una chiamata con la parte di recupero</span><span class="sxs-lookup"><span data-stu-id="5e2d6-418">A caller might hear one second of music-on-hold during the establishment of a call with the retrieving party</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="5e2d6-419">Le informazioni contenute in questa sezione riguardano gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-419">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="5e2d6-420">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-420">**Issue:**</span></span>

<span data-ttu-id="5e2d6-421">Quando viene recuperata una chiamata tramite il prelievo delle chiamate di gruppo, il chiamante può udire un secondo di musica durante l'esecuzione della chiamata con la parte Retriever.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-421">When a call is retrieved via Group Call Pickup, the caller might hear one second of music-on-hold during the establishment of the call with the retriever party.</span></span>

<span data-ttu-id="5e2d6-422">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-422">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-423">Non esiste alcuna soluzione per questo problema.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-423">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a><span data-ttu-id="5e2d6-424">Un agente di Response Group può accedere e disconnettersi tramite una console di agente Lync Server 2010 ai soli gruppi di agenti formali di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-424">A Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only</span></span>

<span data-ttu-id="5e2d6-425">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-425">**Issue:**</span></span>

<span data-ttu-id="5e2d6-426">Un agente di Response Group di Lync Server 2013 può accedere e disconnettersi tramite una console di agente di Lync Server 2010 ai soli gruppi di agenti formali di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-426">A Lync Server 2013 Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only.</span></span> <span data-ttu-id="5e2d6-427">Nella console di agente Lync Server 2010 gli utenti possono visualizzare solo il Response Group di Lync Server 2010 a cui appartengono.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-427">In the Lync Server 2010 Agent Console, users can see only the Lync Server 2010 Response Group that they belong to.</span></span> <span data-ttu-id="5e2d6-428">Non è possibile visualizzare nessuno dei gruppi di risposta di Lync Server 2013 a cui appartengono.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-428">They cannot see any of the Lync Server 2013 Response Groups that they belong to.</span></span>

<span data-ttu-id="5e2d6-429">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-429">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-430">Se l'agente Response Group è un utente di Lync Server 2013 e parte di un gruppo di agenti formali di Lync Server 2013, l'utente deve accedere alla console di agente di Lync Server 2013 direttamente tramite un collegamento Web in un browser per accedere e disconnettersi dai gruppi di agenti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-430">If the Response Group agent is a Lync Server 2013 user, and part of a Lync Server 2013 formal Agent Group, the user must access the Lync Server 2013 Agent Console directly via a web link in a browser to sign in to and sign out from Lync Server 2013 Agent Groups.</span></span>

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a><span data-ttu-id="5e2d6-431">Un agente di Response Group di Lync Server 2010 non è in grado di effettuare chiamate per conto di un Response Group di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e2d6-431">A Lync Server 2010 Response Group agent cannot place calls on behalf of a Lync Server 2013 Response Group</span></span>

<span data-ttu-id="5e2d6-432">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-432">**Issue:**</span></span>

<span data-ttu-id="5e2d6-433">Un utente di Lync Server 2010 che è un agente di un Response Group di Lync Server 2013 non è in grado di effettuare una chiamata per conto del Response Group.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-433">A Lync Server 2010 user who is an Agent of a Lync Server 2013 Response Group is not able to place a call on behalf of the Response Group.</span></span> <span data-ttu-id="5e2d6-434">Il Response Group di Lync Server 2013 non sarà disponibile nel client Lync per effettuare una chiamata.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-434">The Lync Server 2013 Response Group will not be available in the Lync Client to place a call.</span></span>

<span data-ttu-id="5e2d6-435">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-435">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-436">Per ovviare a questo problema, è necessario spostare l'utente di Lync Server 2010 in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-436">To work around this issue, you must move the Lync Server 2010 user to Lync Server 2013.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a><span data-ttu-id="5e2d6-437">La rimozione di un Response Group da Lync Server 2010 dopo che è stata eseguita la migrazione a Lync Server 2013 impedirà al Response Group di accettare le chiamate in arrivo</span><span class="sxs-lookup"><span data-stu-id="5e2d6-437">Removing a Response Group from Lync Server 2010 after it has been migrated to Lync Server 2013 will prevent the Response Group from accepting any incoming calls</span></span>

<span data-ttu-id="5e2d6-438">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-438">**Issue:**</span></span>

<span data-ttu-id="5e2d6-439">Se un Response Group di cui è stata eseguita la migrazione da Lync Server 2010 a Lync Server 2013 è stato rimosso da Lync Server 2010 tramite il pannello di controllo di Lync Server o Lync Server Management Shell, il Response Group in Lync Server 2013 smetterà di ricevere chiamate in arrivo.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-439">If a Response Group that has been migrated from Lync Server 2010 to Lync Server 2013 is removed from Lync Server 2010 through the Lync Server Control Panel or the Lync Server Management Shell, the Response Group in Lync Server 2013 will stop receiving any incoming calls.</span></span>

<span data-ttu-id="5e2d6-440">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-440">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-441">Per ovviare a questo problema, non rimuovere i Response Group da Lync Server 2010 che sono stati migrati da Lync Server 2010 a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-441">To work around this issue, do not remove any Response Groups from Lync Server 2010 that have been migrated from Lync Server 2010 to Lync Server 2013.</span></span>

<span data-ttu-id="5e2d6-442">Se il Response Group è già stato rimosso, è necessario ridistribuirlo in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-442">If the Response Group has already been removed, you should redeploy it in Lync Server 2013.</span></span>

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a><span data-ttu-id="5e2d6-443">Quando un nuovo flusso di lavoro gestito è impostato su inattivo al momento della creazione, la distribuzione del flusso di lavoro avrà esito negativo</span><span class="sxs-lookup"><span data-stu-id="5e2d6-443">When a new managed workflow is set to inactive when created, deployment of the workflow will fail</span></span>

<span data-ttu-id="5e2d6-444">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-444">**Issue:**</span></span>

<span data-ttu-id="5e2d6-445">Quando un nuovo flusso di lavoro gestito è impostato su inattivo al momento della creazione, la distribuzione del flusso di lavoro avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-445">When a new managed workflow is set to inactive when created, deployment of the workflow will fail.</span></span> <span data-ttu-id="5e2d6-446">Questo problema si verifica quando il flusso di lavoro è impostato su inattivo quando viene creato, ma non influisce su un flusso di lavoro modificato per impostarlo su inattivo dopo che è stato distribuito.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-446">This issue is encountered when the workflow is set to inactive when created, but does not affect a workflow that is edited to set it to inactive after is has been deployed.</span></span>

<span data-ttu-id="5e2d6-447">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-447">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-448">Durante la creazione e la distribuzione di un flusso di lavoro, impostare il flusso di lavoro come attivo e quindi distribuirlo.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-448">When creating and deploying a workflow, set the workflow as active and then deploy it.</span></span> <span data-ttu-id="5e2d6-449">Dopo la distribuzione del flusso di lavoro, è possibile modificare il flusso di lavoro e impostarlo su inattivo.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-449">After the workflow is successfully deployed, the workflow can be edited and set to inactive.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a><span data-ttu-id="5e2d6-450">Se il Response Group è stato importato nel pool di backup, la rimozione di un Response Group dal pool del proprietario impedirà al gruppo di risposta del pool di backup di accettare le chiamate in arrivo durante il failover.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-450">Removing a Response Group from the Owner pool will prevent the Response Group of the Backup pool from accepting any incoming calls during failover if the Response Group has been imported to the Backup pool</span></span>

<span data-ttu-id="5e2d6-451">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-451">**Issue:**</span></span>

<span data-ttu-id="5e2d6-452">Se un Response Group di proprietà del pool primario è stato importato nel pool di backup senza sovrascrivere il proprietario e il Response Group è stato rimosso dal pool di proprietari, il Response Group nel pool di backup non accetterà chiamate in arrivo durante il failover.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-452">If a Response Group that is owned by the primary pool has been imported to the backup pool without overwriting the owner, and the Response Group is removed from the owner pool, the Response Group in the Backup pool will not accept any incoming calls during failover.</span></span>

<span data-ttu-id="5e2d6-453">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-453">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-454">Sarà necessario ridistribuire il Response Group nel pool primario.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-454">You will need to redeploy the Response Group in the Primary pool.</span></span> <span data-ttu-id="5e2d6-455">Sarà quindi necessario esportare la configurazione di Response Group dal pool primario e importarla di nuovo nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-455">You will then need to export the Response Group configuration from the Primary pool and import it to the Backup pool again.</span></span>

<span data-ttu-id="5e2d6-456">È inoltre possibile ricreare il Response Group nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-456">You can also recreate the Response Group in the Backup pool.</span></span> <span data-ttu-id="5e2d6-457">In questo caso, il pool di backup sarà il pool proprietario del Response Group.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-457">In this case, the Backup pool will be the owner pool of the Response Group.</span></span>

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a><span data-ttu-id="5e2d6-458">Non è possibile recuperare una chiamata parcheggiata dall'applicazione Parcheggio di chiamata se la richiesta di recupero viene fatta per conto di un Response Group</span><span class="sxs-lookup"><span data-stu-id="5e2d6-458">A parked call can't be retrieved from the Call Park application if the retrieve request is done on behalf of a Response Group</span></span>

<span data-ttu-id="5e2d6-459">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-459">**Issue:**</span></span>

<span data-ttu-id="5e2d6-460">Quando si verificano le condizioni seguenti, una richiesta di recupero per una chiamata parcheggiata avrà esito negativo:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-460">When the following conditions are true, a retrieve request for a parked call will fail:</span></span>

  - <span data-ttu-id="5e2d6-461">Un agente fa parte di un Response Group anonimo</span><span class="sxs-lookup"><span data-stu-id="5e2d6-461">An agent is part of an anonymous Response Group</span></span>

  - <span data-ttu-id="5e2d6-462">L'agente tenta di recuperare una chiamata parcheggiata dall'applicazione Parcheggio di chiamata tramite il Response Group anonimo</span><span class="sxs-lookup"><span data-stu-id="5e2d6-462">The agent attempts to retrieve a parked call from the Call Park application through the anonymous Response Group</span></span>

  - <span data-ttu-id="5e2d6-463">L'agente tenta di recuperare la chiamata componendo il numero dell'orbita tramite l'opzione chiama per conto di o tramite la stessa opzione nel client di operatore di Lync</span><span class="sxs-lookup"><span data-stu-id="5e2d6-463">The agent attempts to retrieve the call by dialing the orbit number through the Call On Behalf option or through the same option in the Lync attendant client</span></span>

<span data-ttu-id="5e2d6-464">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-464">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-465">Non vi sono soluzioni alternative per questo problema.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-465">There are no workarounds for this issue.</span></span> <span data-ttu-id="5e2d6-466">La chiamata parcheggiata deve essere recuperata senza farlo per conto di un Response Group.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-466">The parked call should be retrieved without doing so on behalf of a Response Group.</span></span>

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a><span data-ttu-id="5e2d6-467">Pannello di controllo di Lync Server, Generatore di topologie e Strumento di pianificazione</span><span class="sxs-lookup"><span data-stu-id="5e2d6-467">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

<div>

## <a name="planning-tool-limitations"></a><span data-ttu-id="5e2d6-468">Limitazioni dello strumento di pianificazione</span><span class="sxs-lookup"><span data-stu-id="5e2d6-468">Planning Tool Limitations</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="5e2d6-469">Le informazioni contenute in questa sezione riguardano gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-469">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="5e2d6-470">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-470">**Issue:**</span></span>

<span data-ttu-id="5e2d6-471">Durante la pianificazione della distribuzione, lo strumento di pianificazione presenta le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-471">The Planning Tool has the following limitations when planning for your deployment:</span></span>

  - <span data-ttu-id="5e2d6-472">È supportato un massimo di 10 siti centrali</span><span class="sxs-lookup"><span data-stu-id="5e2d6-472">There is a maximum of 10 central sites supported</span></span>

  - <span data-ttu-id="5e2d6-473">Ogni sito centrale può avere un massimo di 14 siti di succursale</span><span class="sxs-lookup"><span data-stu-id="5e2d6-473">Each central site can have a maximum of 14 branch sites</span></span>

  - <span data-ttu-id="5e2d6-474">Ogni sito centrale può avere un massimo di 240.000 utenti</span><span class="sxs-lookup"><span data-stu-id="5e2d6-474">Each central site can have a maximum of 240,000 users</span></span>

<span data-ttu-id="5e2d6-475">Inoltre, quando si calcola la topologia consigliata, lo strumento di pianificazione non include i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-475">In addition, the Planning Tool does not include values for the following when calculating the recommended topology:</span></span>

  - <span data-ttu-id="5e2d6-476">Il numero di utenti ospitati online</span><span class="sxs-lookup"><span data-stu-id="5e2d6-476">The number of users that are homed online</span></span>

  - <span data-ttu-id="5e2d6-477">La percentuale di utenti abilitati per la Federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="5e2d6-477">The percentage of users that are enabled for XMPP federation</span></span>

  - <span data-ttu-id="5e2d6-478">Percentuale di utenti che utilizzano Lync Web App</span><span class="sxs-lookup"><span data-stu-id="5e2d6-478">Percentage of users that are using Lync Web App</span></span>

<span data-ttu-id="5e2d6-479">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-479">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-480">Non esiste alcuna soluzione per questi problemi.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-480">There is no workaround for these issues.</span></span> <span data-ttu-id="5e2d6-481">Per ulteriori informazioni sullo strumento di pianificazione, vedere [progettazione della topologia per Lync Server 2013 mediante lo strumento di pianificazione](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span><span class="sxs-lookup"><span data-stu-id="5e2d6-481">For more information about the Planning Tool, see [Designing the topology for Lync Server 2013 by using the Planning Tool](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span></span>

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a><span data-ttu-id="5e2d6-482">Lo strumento di pianificazione potrebbe non utilizzare gli indirizzi IP definiti in precedenza per la rete perimetrale quando si aggiornano le opzioni</span><span class="sxs-lookup"><span data-stu-id="5e2d6-482">Planning Tool may not use previously defined IP addresses for the Edge network when updating options</span></span>

<span data-ttu-id="5e2d6-483">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-483">**Issue:**</span></span>

<span data-ttu-id="5e2d6-484">Dopo aver completato la progettazione utilizzando lo strumento di pianificazione, se si apportano modifiche alle opzioni di rete Edge, è possibile aggiungere indirizzi IP aggiuntivi alla struttura anziché aggiornare gli indirizzi IP esistenti.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-484">After you complete your design using the Planning Tool, if you make changes to the Edge Network options, additional IP addresses may be added to the design instead of updating the existing IP addresses.</span></span> <span data-ttu-id="5e2d6-485">Ciò può verificarsi quando si visualizzano i dettagli del diagramma della rete perimetrale, selezionare **fare clic qui per aggiornare le opzioni**e quindi nella finestra di dialogo Opzioni di configurazione selezionare rete perimetrale seleziona **desidero utilizzare gli stessi nomi FQDN e indirizzi IP, ma porte diverse per i servizi perimetrali nel server perimetrale**.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-485">This can occur when you are viewing the details of the Edge Network Diagram, select **Click here to update your options**, and then, on the Configuration Options dialog, you select Edge Network select **I want to use the same FQDNs and IP addresses, but different ports for the edge services on my Edge Server**.</span></span> <span data-ttu-id="5e2d6-486">L'applicazione di eventuali modifiche può comportare l'aggiunta di nuovi indirizzi IP e server perimetrali alla struttura.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-486">Applying any changes may result in new IP addresses and Edge servers being added to the design.</span></span>

<span data-ttu-id="5e2d6-487">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-487">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-488">Non esiste alcuna soluzione per questo problema in questo momento.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-488">There is no workaround for this issue at this time.</span></span>

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a><span data-ttu-id="5e2d6-489">Nel pannello di controllo di Lync Server, "spostare tutti gli utenti nel pool" potrebbe non funzionare come previsto</span><span class="sxs-lookup"><span data-stu-id="5e2d6-489">In Lync Server Control Panel, "Move all users to pool" may not work as expected</span></span>

<span data-ttu-id="5e2d6-490">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-490">**Issue:**</span></span>

<span data-ttu-id="5e2d6-491">Quando si utilizza il pannello di controllo di Lync Server per spostare tutti gli utenti da un pool a un altro in un ambiente di Active Directory complesso, ad esempio uno con più controller di dominio e domini padre/figlio, è possibile che venga restituito un messaggio di errore che indica che "l'utente specificato non è un utente legacy, utilizza invece Move-CsUser cmdlet".</span><span class="sxs-lookup"><span data-stu-id="5e2d6-491">When using the Lync Server Control Panel to move all users from one pool to another pool in a complex Active Directory environment, such as one with multiple Domain Controllers and parent/child domains, an error message may be returned that states, “Specified user is not a legacy user, use Move-CsUser cmdlet instead.”</span></span> <span data-ttu-id="5e2d6-492">Questo è il risultato di tempi di replica più lunghi in ambienti di Active Directory complessi.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-492">This is a result of longer replication times in complex Active Directory environments.</span></span>

<span data-ttu-id="5e2d6-493">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-493">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-494">Per risolvere questo problema, effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-494">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="5e2d6-495">Utilizzare filtri nel pannello di controllo di Lync Server per cercare gli utenti legacy, selezionarli e quindi utilizzare il **comando Sposta utenti selezionati nel pool** anziché **spostare tutti gli utenti nel pool**.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-495">Use filters in the Lync Server Control Panel to search for legacy users, select those users, and then use the **Move selected users to pool command** instead of **Move all users to pool**.</span></span>

  - <span data-ttu-id="5e2d6-496">Utilizzare Lync Server Management Shell per spostare gli utenti legacy in batch utilizzando i cmdlet di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-496">Use the Lync Server Management Shell to move legacy users in batches by using Lync Server cmdlets.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a><span data-ttu-id="5e2d6-497">Il pannello di controllo di Lync Server smette di funzionare in un ambiente VMware dopo che il plug-in del browser Microsoft Silverlight è stato aggiornato alla versione 5</span><span class="sxs-lookup"><span data-stu-id="5e2d6-497">The Lync Server Control Panel stops working in a VMware environment after the Microsoft Silverlight browser plug-in is updated to version 5</span></span>

<span data-ttu-id="5e2d6-498">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-498">**Issue:**</span></span>

<span data-ttu-id="5e2d6-499">Se si utilizza il pannello di controllo di Lync Server in un ambiente VMware, è possibile che il pannello di controllo di Lync Server smetta di funzionare dopo aver aggiornato Silverlight alla versione 5.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-499">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Silverlight to version 5.</span></span>

<span data-ttu-id="5e2d6-500">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-500">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-501">Per risolvere questo problema, effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-501">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="5e2d6-502">Disinstallare Silverlight 5 e quindi installare Silverlight 4 da [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0) .</span><span class="sxs-lookup"><span data-stu-id="5e2d6-502">Uninstall Silverlight 5, and then install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0).</span></span>

  - <span data-ttu-id="5e2d6-503">Aprire il pannello di controllo di Lync Server da un computer che non sia un computer virtuale VMware.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-503">Open the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="5e2d6-504">Per aprire il pannello di controllo di Lync Server da un computer remoto, installare gli strumenti di amministrazione di Lync Server nel computer e quindi avviare il pannello di controllo di Lync Server dal menu **Start** di Windows.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-504">To open the Lync Server Control Panel from a remote computer, install Lync Server Administration tools on the computer, and then start the Lync Server Control Panel from the Windows **Start** menu.</span></span>
    
    <span data-ttu-id="5e2d6-505">È inoltre possibile aprire il pannello di controllo di Lync Server digitando l'URL in un Web browser.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-505">You can also open the Lync Server Control Panel by entering the URL in a web browser.</span></span> <span data-ttu-id="5e2d6-506">L'URL sarà simile a https:// \<frontend\_pool\_fqdn\> /CSCP.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-506">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a><span data-ttu-id="5e2d6-507">Un amministratore non è in grado di eseguire il cmdlet Uninstall-csMirrorDB dopo aver rimosso il database del mirroring in Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="5e2d6-507">An administrator cannot run the Uninstall-csMirrorDB cmdlet after removing the mirroring database in Topology Builder</span></span>

<span data-ttu-id="5e2d6-508">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-508">**Issue:**</span></span>

<span data-ttu-id="5e2d6-509">Quando un amministratore disabilita un database del mirroring in Generatore di topologie e quindi Elimina il database del mirroring in Generatore di topologie, nell'elenco da fare viene visualizzato un messaggio che consente all'amministratore di eseguire il cmdlet **Uninstall-csMirrorDatabase** per rimuovere il mirroring da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-509">When an administrator disables a mirroring database in Topology Builder, and then deletes the mirroring database in Topology Builder, a message is displayed in the To do list for the administrator to run the **Uninstall-csMirrorDatabase** cmdlet to remove mirroring from SQL Server.</span></span> <span data-ttu-id="5e2d6-510">Quando l'amministratore tenta di eseguire il cmdlet, ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-510">When the administrator attempts to run the cmdlet, it fails.</span></span>

<span data-ttu-id="5e2d6-511">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-511">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-512">Per rimuovere il mirroring SQL di un pool in Generatore di topologie, è innanzitutto necessario utilizzare un cmdlet per rimuovere il mirror in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-512">To remove SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server.</span></span> <span data-ttu-id="5e2d6-513">È quindi possibile utilizzare Generatore di topologie per rimuovere il mirror dalla topologia.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-513">You can then use Topology Builder to remove the mirror from the topology.</span></span> <span data-ttu-id="5e2d6-514">Per rimuovere il mirror in SQL Server, utilizzare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-514">To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="5e2d6-515">Ad esempio, per rimuovere il mirroring e rilasciare i database per i database degli utenti, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-515">For example, to remove mirroring and drop the databases for the user databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="5e2d6-516">Il parametro *DropExistingDatabasesOnMirror* consente di eliminare dal mirror i database coinvolti.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-516">The *DropExistingDatabasesOnMirror* parameter causes the affected databases to be deleted from the mirror.</span></span> <span data-ttu-id="5e2d6-517">Per rimuovere il mirror dalla topology, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-517">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="5e2d6-518">In Generatore di topologie, fare clic con il pulsante destro del mouse sul pool e quindi scegliere **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-518">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="5e2d6-519">Cancellare il **mirroring dell'archivio SQL** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-519">Clear **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="5e2d6-520">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-520">Publish the topology.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="5e2d6-521">Ogni volta che si apportano modifiche a una relazione di mirroring del database back-end, è necessario riavviare tutti i Front End Server nel pool.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-521">Whenever you make a change to a back-end database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span>



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a><span data-ttu-id="5e2d6-522">Gli errori di convalida vengono restituiti in Generatore di topologie quando un amministratore tenta di rimuovere una distribuzione con un pool Front end a cui è associato un archivio di controllo.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-522">Validation errors are returned in Topology Builder when an administrator attempts to remove a deployment with a Front End pool that has an associated witness store</span></span>

<span data-ttu-id="5e2d6-523">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-523">**Issue:**</span></span>

<span data-ttu-id="5e2d6-524">Se un amministratore tenta di utilizzare il comando **Rimuovi distribuzione** in Generatore di topologie per rimuovere una distribuzione che include un pool Front end con un archivio di controllo associato, viene visualizzato un errore di convalida in Generatore di topologie e l'azione non verrà eseguita.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-524">If an administrator attempts to use the **Remove Deployment** command in Topology Builder to remove a deployment that includes a Front End pool with an associated witness store, a validation error is displayed in Topology Builder and the action will not proceed.</span></span>

<span data-ttu-id="5e2d6-525">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-525">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-526">Per risolvere questo problema, effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-526">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="5e2d6-527">Rimuovere l'archivio di controllo prima di tentare di rimuovere la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-527">Remove the witness store before attempting to remove the deployment.</span></span>

  - <span data-ttu-id="5e2d6-528">Aggiungere un archivio di controllo per il pool Front end e quindi rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-528">Add a witness store for the Front End pool and then remove it.</span></span>

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a><span data-ttu-id="5e2d6-529">Le informazioni sulla distribuzione del server Chat persistente sono incoerenti tra lo strumento di pianificazione e il generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="5e2d6-529">Persistent Chat Server deployment information is inconsistent between the Planning Tool and Topology Builder</span></span>

<span data-ttu-id="5e2d6-530">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-530">**Issue:**</span></span>

<span data-ttu-id="5e2d6-531">Quando Lync Server 2013, lo strumento di pianificazione genera il diagramma della topologia del sito per una distribuzione di server Chat persistente con ripristino di emergenza abilitato, il diagramma della topologia del sito include più siti (fisici), con i server di chat persistente assegnati equamente in ogni sito.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-531">When the Lync Server 2013, Planning Tool outputs the site topology diagram for a Persistent Chat Server deployment with disaster recovery enabled, the site topology diagram includes multiple (physical) sites, with evenly assigned Persistent Chat Servers at each site.</span></span> <span data-ttu-id="5e2d6-532">In Generatore di topologie, tutti i server di chat persistente sono rappresentati come appartenenti a un singolo sito (logico) e sono elencati nello stesso nodo del pool di Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-532">In Topology Builder, all Persistent Chat Servers are represented as belonging to a single (logical) site, and are listed under the same Persistent Chat Server pool node.</span></span>

<span data-ttu-id="5e2d6-533">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-533">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-534">Attualmente, non si dispone di una soluzione alternativa per questo problema.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-534">Currently, we do not have a workaround for this issue.</span></span> <span data-ttu-id="5e2d6-535">L'utente deve analizzare l'output dello strumento di pianificazione per la distribuzione del server Chat persistente e modificare il piano per soddisfare le proprie esigenze specifiche.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-535">The user should analyze the output of the Planning Tool for the Persistent Chat Server deployment, and modify the plan to meet their specific needs.</span></span>

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a><span data-ttu-id="5e2d6-536">Localizzazione</span><span class="sxs-lookup"><span data-stu-id="5e2d6-536">Localization</span></span>

<div>

## <a name="monitoring"></a><span data-ttu-id="5e2d6-537">Monitoraggio</span><span class="sxs-lookup"><span data-stu-id="5e2d6-537">Monitoring</span></span>

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a><span data-ttu-id="5e2d6-538">La procedura guidata per la distribuzione dei rapporti di monitoraggio Visualizza caratteri non corretti in determinate circostanze quando si utilizza la versione dell'Asia orientale di Lync Server</span><span class="sxs-lookup"><span data-stu-id="5e2d6-538">The Deploy Monitoring Reports wizard displays incorrect characters under certain circumstances when using the East Asian version of Lync Server</span></span>

<span data-ttu-id="5e2d6-539">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-539">**Issue:**</span></span>

<span data-ttu-id="5e2d6-540">Quando si utilizza una versione dell'Asia orientale di Lync Server 2013, ad esempio cinese (semplificato), cinese (tradizionale), giapponese o coreano, in un sistema operativo in cui le impostazioni locali del sistema non sono impostate su una lingua dell'Asia orientale, la procedura guidata Deploy Monitoring Reports visualizzerà i punti interrogativi o altri caratteri invece dei messaggi localizzati.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-540">When using an East Asian version of Lync Server 2013—for example, Chinese (Simplified), Chinese (Traditional), Japanese, or Korean—on an operating system that has the system locale not set to an East Asian language, the Deploy Monitoring Reports wizard will display question marks or other characters instead of localized messages.</span></span>

<span data-ttu-id="5e2d6-541">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-541">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-542">Per risolvere il problema, impostare le impostazioni locali per il sistema operativo e Lync Server 2013 sulla stessa lingua, in cui verranno visualizzati correttamente tutti i messaggi.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-542">To correct this issue, set the locale for the operating system and Lync Server 2013 to the same language, which will display all messages correctly.</span></span>

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="5e2d6-543">Pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="5e2d6-543">Lync Server Control Panel</span></span>

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a><span data-ttu-id="5e2d6-544">In alcuni casi, il primo elemento nella barra di spostamento superiore in una pagina del pannello di controllo di Lync Server scompare quando si fa clic sull'ultimo elemento della barra di spostamento superiore</span><span class="sxs-lookup"><span data-stu-id="5e2d6-544">In certain cases, the first item in the top navigation bar on a page of Lync Server Control Panel disappears when the last item in the top navigation bar is clicked</span></span>

<span data-ttu-id="5e2d6-545">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-545">**Issue:**</span></span>

<span data-ttu-id="5e2d6-546">Esistono tre casi noti in cui se si fa clic sull'ultimo elemento nella barra di spostamento superiore in una pagina del pannello di controllo di Lync Server, il primo elemento nella barra di spostamento superiore scomparirà:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-546">There are three known cases where clicking the last item in the top navigation bar on a page of the Lync Server Control Panel will cause the first item in the top navigation bar to disappear:</span></span>

  - <span data-ttu-id="5e2d6-547">Nella versione francese della pagina "Féderation et accès externe", l'elemento "Stratégie accès externe" scomparirà quando si fa clic su "Partenaires fédérés XMPP".</span><span class="sxs-lookup"><span data-stu-id="5e2d6-547">In the French of version, on the page "Féderation et accès externe," the item "Stratégie d'accès externe" will disappear when "Partenaires fédérés XMPP" is clicked.</span></span>

  - <span data-ttu-id="5e2d6-548">Nella versione in lingua tedesca, nella pagina "client", l'elemento "Clientversionskonfiguration" scompare quando si fa clic su "se".</span><span class="sxs-lookup"><span data-stu-id="5e2d6-548">In the German version, on the "Clients" page, the item "Clientversionskonfiguration" disappears when "Pushbenachrichtigungskonfiguration" is clicked.</span></span>

  - <span data-ttu-id="5e2d6-549">Nella versione russa, nella pagina "Конфигурация сети", la voce "Глобально" scompare quando si fa clic su "Маршрут региона".</span><span class="sxs-lookup"><span data-stu-id="5e2d6-549">In the Russian version, on "Конфигурация сети" page, the item "Глобально" disappears when "Маршрут региона" is clicked.</span></span>

<span data-ttu-id="5e2d6-550">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-550">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-551">Per ovviare a questo problema, aggiornare la pagina del pannello di controllo di Lync Server nel browser.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-551">To work around this issue, refresh the page of the Lync Server Control Panel in your browser.</span></span> <span data-ttu-id="5e2d6-552">La pagina verrà caricata nel browser con tutti gli elementi nella barra di spostamento superiore visualizzata.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-552">The page will load in the browser with all of the items in the top navigation bar displayed.</span></span>

</div>

</div>

<div>

## <a name="address-book"></a><span data-ttu-id="5e2d6-553">Rubrica</span><span class="sxs-lookup"><span data-stu-id="5e2d6-553">Address Book</span></span>

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a><span data-ttu-id="5e2d6-554">L'indicizzazione nella Rubrica non funziona come previsto in alcune lingue</span><span class="sxs-lookup"><span data-stu-id="5e2d6-554">Indexing in the Address Book does not work as expected in some languages</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="5e2d6-555">Le informazioni contenute in questa sezione riguardano gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-555">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="5e2d6-556">Se le proprietà di un utente contengono un campo indicizzato e questo campo contiene solo caratteri che non possono essere indicizzati, l'utente non verrà visualizzato nelle ricerche eseguite nella rubrica.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-556">If a user’s properties contain an indexed field, and that field contains only characters that cannot be indexed, then the user will not appear in searches performed in the Address Book.</span></span>

<span data-ttu-id="5e2d6-557">Non è possibile indicizzare i caratteri e le impostazioni locali seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-557">The following characters and locales cannot be indexed:</span></span>

  - <span data-ttu-id="5e2d6-558">Caratteri cirillici, greci e armeni in maiuscolo</span><span class="sxs-lookup"><span data-stu-id="5e2d6-558">Upper-case Cyrillic, Greek, and Armenian characters</span></span>

  - <span data-ttu-id="5e2d6-559">Caratteri accentati in maiuscolo</span><span class="sxs-lookup"><span data-stu-id="5e2d6-559">Upper-case accented characters</span></span>

  - <span data-ttu-id="5e2d6-560">Thai</span><span class="sxs-lookup"><span data-stu-id="5e2d6-560">Thai</span></span>

  - <span data-ttu-id="5e2d6-561">Lao</span><span class="sxs-lookup"><span data-stu-id="5e2d6-561">Lao</span></span>

  - <span data-ttu-id="5e2d6-562">Myanmar</span><span class="sxs-lookup"><span data-stu-id="5e2d6-562">Myanmar</span></span>

  - <span data-ttu-id="5e2d6-563">Devanagari</span><span class="sxs-lookup"><span data-stu-id="5e2d6-563">Devanagari</span></span>

  - <span data-ttu-id="5e2d6-564">Etiope</span><span class="sxs-lookup"><span data-stu-id="5e2d6-564">Ethiopic</span></span>

  - <span data-ttu-id="5e2d6-565">Tibetano</span><span class="sxs-lookup"><span data-stu-id="5e2d6-565">Tibetan</span></span>

  - <span data-ttu-id="5e2d6-566">Bengali</span><span class="sxs-lookup"><span data-stu-id="5e2d6-566">Bengali</span></span>

  - <span data-ttu-id="5e2d6-567">Gujarati</span><span class="sxs-lookup"><span data-stu-id="5e2d6-567">Gujarati</span></span>

  - <span data-ttu-id="5e2d6-568">Telugu</span><span class="sxs-lookup"><span data-stu-id="5e2d6-568">Telugu</span></span>

  - <span data-ttu-id="5e2d6-569">Tutti gli altri script indiani</span><span class="sxs-lookup"><span data-stu-id="5e2d6-569">All other Indic scripts</span></span>

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a><span data-ttu-id="5e2d6-570">Lync Web App, utilità di pianificazione Web e componenti Web</span><span class="sxs-lookup"><span data-stu-id="5e2d6-570">Lync Web App, Web Scheduler, and Web components</span></span>

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a><span data-ttu-id="5e2d6-571">Il fallback della lingua per alcune lingue in Lync Web Scheduler, accesso esterno, Join Launcher, Persistent Chat Room Management e OCTab potrebbe non funzionare come previsto</span><span class="sxs-lookup"><span data-stu-id="5e2d6-571">Language fallback for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab might not work as expected</span></span>

<span data-ttu-id="5e2d6-572">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-572">**Issue:**</span></span>

<span data-ttu-id="5e2d6-573">Quando si selezionano impostazioni locali neutre in un Web browser (in Internet Explorer, ad esempio, il nome della lingua senza ulteriori specifiche, come "norvegese \[ No \] ", anziché le impostazioni locali che specificano la lingua, lo script e le impostazioni locali (ad esempio "norvegese, Bokmål (Norvegia) \[ NB-No \] ") potrebbe causare un comportamento di visualizzazione imprevisto per alcune lingue in Lync Web Scheduler, accesso esterno, Join Launcher, Persistent Chat Room Management e OCTab.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-573">When selecting a neutral locale in a web browser (in Internet Explorer, for example, the language name without further specification, like "Norwegian \[no\]") instead of a locale specifying language, script and locale (such as "Norwegian, Bokmål (Norway) \[nb-NO\]") might lead to unexpected display behavior for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab.</span></span> <span data-ttu-id="5e2d6-574">Ad esempio, gli utenti potrebbero visualizzare la pagina in lingua inglese quando viene selezionata una delle lingue seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e2d6-574">For example, users might see the English page when one of the following languages is selected:</span></span>

  - <span data-ttu-id="5e2d6-575">Norvegese</span><span class="sxs-lookup"><span data-stu-id="5e2d6-575">Norwegian</span></span>

  - <span data-ttu-id="5e2d6-576">Portoghese</span><span class="sxs-lookup"><span data-stu-id="5e2d6-576">Portuguese</span></span>

  - <span data-ttu-id="5e2d6-577">Serbo</span><span class="sxs-lookup"><span data-stu-id="5e2d6-577">Serbian</span></span>

<span data-ttu-id="5e2d6-578">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-578">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-579">Se si desidera selezionare una lingua con impostazioni locali neutre, assicurarsi sempre di aggiungere la lingua a una determinata lingua (con codice di script e/o di paese) come ulteriore linguaggio nell'elenco delle preferenze della lingua del browser.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-579">If you want to select a language with a neutral locale, always make sure that you also add the language with a specific locale (with script and/or country code) as an additional language in your browser's language preference list.</span></span>

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a><span data-ttu-id="5e2d6-580">È disponibile un supporto limitato per le impostazioni locali azeri e Usbeco quando si utilizza Lync Web Scheduler, accesso esterno, Join Launcher, gestione chat room Persistent e OCTab in alcuni Web browser</span><span class="sxs-lookup"><span data-stu-id="5e2d6-580">There is limited support for Azeri and Uzbek locales when using Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab in some web browsers</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="5e2d6-581">Le informazioni contenute in questa sezione riguardano gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-581">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="5e2d6-582">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-582">**Issue:**</span></span>

<span data-ttu-id="5e2d6-583">Quando si utilizza Internet Explorer 8 o Internet Explorer 9 e si imposta la lingua del browser su Azero (alfabeto latino) o Usbeco (alfabeto latino), le pagine di avvio di accesso esterno e join verranno visualizzate in inglese o nella lingua preferita impostata nel browser.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-583">When you use Internet Explorer 8 or Internet Explorer 9, and set the browser language to Azeri (Latin) or Uzbek (Latin), the Dial-in and Join Launcher pages will be displayed in English or the preferred language set in the browser.</span></span>

<span data-ttu-id="5e2d6-584">Quando si utilizzano i browser Firefox o Chrome e si imposta la lingua del browser su Azero (alfabeto latino) o Usbeco (alfabeto latino), Lync Web App, Lync Web Scheduler e RGS OCTab verranno visualizzati in inglese o la lingua preferita per il browser.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-584">When you use Firefox or Chrome browsers, and you set the browser language to Azeri (Latin) or Uzbek (Latin), the Lync Web App, Lync Web Scheduler, and RGS OCTab will be shown in English or the preferred language set for the browser.</span></span>

<span data-ttu-id="5e2d6-585">Le impostazioni locali dell'Uzbeco (alfabeto latino) non sono supportate nel browser Safari.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-585">The Uzbek (Latin) locale is not supported in the Safari browser.</span></span>

<span data-ttu-id="5e2d6-586">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-586">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-587">Non esiste una soluzione alternativa per questi problemi.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-587">There is not workaround for these issues.</span></span>

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a><span data-ttu-id="5e2d6-588">La freccia a discesa mancante per l'elenco "partecipa a riunione da" nella versione rumena di Lync Web App</span><span class="sxs-lookup"><span data-stu-id="5e2d6-588">The drop-down arrow is missing for "Join meeting from" list in the Romanian version of Lync Web App</span></span>

<span data-ttu-id="5e2d6-589">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-589">**Issue:**</span></span>

<span data-ttu-id="5e2d6-590">Quando un utente che utilizza la versione rumena di Lync Web App esegue i passaggi seguenti, la freccia a discesa non viene visualizzata per l'elenco a discesa **partecipa a riunione** :</span><span class="sxs-lookup"><span data-stu-id="5e2d6-590">When a user who is using the Romanian version of Lync Web App performs the following steps, the drop-down arrow is not displayed for **Join meeting** in drop-down list:</span></span>

1.  <span data-ttu-id="5e2d6-591">Selezionare **Ricordami su questo computer** nella scheda **generale** .</span><span class="sxs-lookup"><span data-stu-id="5e2d6-591">Select **Remember me on this computer** on the **General** tab.</span></span>

2.  <span data-ttu-id="5e2d6-592">Selezionare la scheda **telefono** .</span><span class="sxs-lookup"><span data-stu-id="5e2d6-592">Select the **Phone** tab.</span></span>

3.  <span data-ttu-id="5e2d6-593">Fare clic sull'elenco a discesa per **partecipare a una riunione**.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-593">Click the drop-down list for **Join meeting from**.</span></span>
    
    <span data-ttu-id="5e2d6-594">Gli utenti non vedranno una freccia che indica che sono disponibili altre opzioni rispetto all'impostazione predefinita di **Lync Web App**, tra cui: **non aggiungere audio** (in Romeno, "nu se asociaža la Componenta audio") e **nuovo numero**"(in Romeno," Număr Nou ").</span><span class="sxs-lookup"><span data-stu-id="5e2d6-594">Users will not see an arrow that indicates that there are more options than the default **Lync Web App**, which include: **Don't join audio** (in Romanian, "Nu se asociaža la componenta audio") and **New number**" (in Romanian, "Număr nou").</span></span>

<span data-ttu-id="5e2d6-595">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-595">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-596">Anche se la freccia di questo elenco a discesa non è visualizzata, gli utenti possono comunque selezionare le impostazioni aggiuntive nell'elenco facendo clic sul valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-596">Even though the arrow for this drop-down list is not displayed, users can still select the additional settings in the list by clicking on the default value.</span></span>

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a><span data-ttu-id="5e2d6-597">Quando si utilizza la versione turca di Lync Web Scheduler, non è possibile salvare una riunione quando si utilizza l'opzione "persone scelte dall'utente" in "chi è un relatore"</span><span class="sxs-lookup"><span data-stu-id="5e2d6-597">When using the Turkish version of Lync Web Scheduler, a meeting cannot be saved when using the "People I choose" option under "Who is a presenter"</span></span>

<span data-ttu-id="5e2d6-598">**Problema**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-598">**Issue:**</span></span>

<span data-ttu-id="5e2d6-599">Quando si crea o si modifica una riunione nella versione turca dell'utilità di pianificazione Web di Lync, l'opzione "persone scelte" in "chi è un relatore" non è supportata.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-599">When creating or editing a meeting in the Turkish version of the Lync Web Scheduler, the option "People I choose" under "Who is a presenter" is not supported.</span></span> <span data-ttu-id="5e2d6-600">Quando questa opzione è selezionata, la riunione non può essere salvata.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-600">When this option is selected, the meeting can't be saved.</span></span> <span data-ttu-id="5e2d6-601">Viene invece visualizzato un messaggio di errore che indica che non è possibile rendere relatori una o più persone.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-601">Instead, an error message appears, indicating that one or more people cannot be made presenters.</span></span>

<span data-ttu-id="5e2d6-602">**Soluzione alternativa**</span><span class="sxs-lookup"><span data-stu-id="5e2d6-602">**Workaround:**</span></span>

<span data-ttu-id="5e2d6-603">Per ovviare a questo problema, gli utenti possono utilizzare l'opzione predefinita "persone della mia azienda" o qualsiasi altra scelta, ad esempio "solo organizzatore" o "tutti compresi quelli esterni alla propria azienda".</span><span class="sxs-lookup"><span data-stu-id="5e2d6-603">To work around this issue, users can use the default option of "People from my company," or any other choice, such as "Only Organizer" or "Everyone including people outside of my company."</span></span> <span data-ttu-id="5e2d6-604">L'organizzatore può abbassare di livello o promuovere i ruoli corretti in un secondo momento, dopo aver partecipato alla riunione.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-604">The organizer can demote or promote people to their correct roles later, after they have joined the meeting.</span></span>

<span data-ttu-id="5e2d6-605">In alternativa, gli utenti che capiscono un'altra lingua possono cambiare la selezione della lingua nel browser in una delle altre lingue supportate da 43 e tentare di utilizzare l'opzione "persone scelte dall'utente".</span><span class="sxs-lookup"><span data-stu-id="5e2d6-605">Alternatively, users who understand another language can change the language selection in their browser to one of the other 43 supported languages and attempt to use the “People I choose” option.</span></span>

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a><span data-ttu-id="5e2d6-606">Copyright</span><span class="sxs-lookup"><span data-stu-id="5e2d6-606">Copyright</span></span>

<span data-ttu-id="5e2d6-607">Questo documento supporta una versione preliminare di un prodotto software che può essere modificato in modo sostanziale prima del rilascio finale commerciale ed è l'informazione riservata e proprietaria di Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-607">This document supports a preliminary release of a software product that may be changed substantially prior to final commercial release, and is the confidential and proprietary information of Microsoft Corporation.</span></span> <span data-ttu-id="5e2d6-608">Viene divulgato in base a un accordo di non divulgazione tra il destinatario e Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-608">It is disclosed pursuant to a non-disclosure agreement between the recipient and Microsoft.</span></span> <span data-ttu-id="5e2d6-609">Microsoft esclude ogni garanzia espressa o implicita in questo documento.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-609">This document is provided for informational purposes only and Microsoft makes no warranties, either express or implied, in this document.</span></span> <span data-ttu-id="5e2d6-610">Le informazioni contenute in questo documento, tra cui l'URL e altri riferimenti al sito Internet, sono soggette a modifiche senza preavviso.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-610">Information in this document, including URL and other Internet website references, is subject to change without notice.</span></span> <span data-ttu-id="5e2d6-611">I rischi conseguenti all'uso o ai risultati dell'uso di questo documento sono a carico degli utenti.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-611">The entire risk of the use or the results from the use of this document remains with the user.</span></span> <span data-ttu-id="5e2d6-612">Se non diversamente specificato, le società, le organizzazioni, i prodotti, i nomi di dominio, gli indirizzi di posta elettronica, i loghi, le persone, i luoghi e gli eventi descritti negli esempi riportati sono fittizi.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-612">Unless otherwise noted, the companies, organizations, products, domain names, email addresses, logos, people, places, and events depicted in examples herein are fictitious.</span></span> <span data-ttu-id="5e2d6-613">Nessuna associazione con una società, un'organizzazione, un prodotto, un nome di dominio, un indirizzo di posta elettronica, un logo, una persona, un luogo o un evento reale è intenzionale o deve essere dedotto.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-613">No association with any real company, organization, product, domain name, email address, logo, person, place, or event is intended or should be inferred.</span></span> <span data-ttu-id="5e2d6-614">Il rispetto di tutte le applicabili leggi in materia di copyright è esclusivamente a carico dell'utente.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-614">Complying with all applicable copyright laws is the responsibility of the user.</span></span> <span data-ttu-id="5e2d6-615">Fermi restando tutti i diritti coperti da copyright, nessuna parte di questo documento potrà comunque essere riprodotta o inserita in un sistema di riproduzione o trasmessa in qualsiasi forma e con qualsiasi mezzo (in formato elettronico, meccanico, su fotocopia, come registrazione o altro) per qualsiasi scopo, senza il permesso scritto di Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-615">Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.</span></span>

<span data-ttu-id="5e2d6-p162">Microsoft può essere titolare di brevetti, domande di brevetto, marchi, copyright o altri diritti di proprietà intellettuale relativi all'oggetto del presente documento. Salvo quanto espressamente previsto in un contratto scritto di licenza Microsoft, la consegna del presente documento non implica la concessione di alcuna licenza su tali brevetti, marchi, copyright o altra proprietà intellettuale.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-p162">Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document. Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.</span></span>

<span data-ttu-id="5e2d6-618">© 2012 Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-618">© 2012 Microsoft Corporation.</span></span> <span data-ttu-id="5e2d6-619">Tutti i diritti riservati.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-619">All rights reserved.</span></span>

<span data-ttu-id="5e2d6-620">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook e SQL Server sono marchi o marchi registrati di Microsoft Corporation negli Stati Uniti e/o negli altri paesi/aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-620">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook, and SQL Server are either registered trademarks or trademarks of Microsoft Corporation in the United States and/or other countries/regions.</span></span>

<span data-ttu-id="5e2d6-621">Tutti gli altri marchi citati nel presente documento sono di proprietà dei rispettivi titolari.</span><span class="sxs-lookup"><span data-stu-id="5e2d6-621">All other trademarks are property of their respective owners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

