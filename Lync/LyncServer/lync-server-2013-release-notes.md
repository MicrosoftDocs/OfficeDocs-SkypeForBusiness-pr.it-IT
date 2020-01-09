---
title: 'Lync Server 2013: Note sulla versione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf5eadb591b7e198ee75ff197b3836673ae0ecc3
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="release-notes-for-lync-server-2013"></a><span data-ttu-id="8fdd4-102">Note sulla versione per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8fdd4-102">Release notes for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fdd4-103">_**Argomento Ultima modifica:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="8fdd4-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="8fdd4-104">Introduzione alle note sulla versione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-104">Welcome to the Lync Server 2013 Release Notes.</span></span> <span data-ttu-id="8fdd4-105">Per informazioni sui problemi noti relativi a Lync Server 2013, vedere questo file.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-105">Refer to this file for information regarding known issues about Lync Server 2013.</span></span>

<div>

## <a name="about-this-document"></a><span data-ttu-id="8fdd4-106">Informazioni sul documento</span><span class="sxs-lookup"><span data-stu-id="8fdd4-106">About this document</span></span>

<span data-ttu-id="8fdd4-107">Questo documento contiene informazioni importanti che è necessario conoscere prima di distribuire e utilizzare Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-107">This document contains important information that you should know before you deploy and use Lync Server 2013.</span></span> <span data-ttu-id="8fdd4-108">Per informazioni dettagliate su Lync Server 2013, vedere la documentazione di [Microsoft Lync server 2013](microsoft-lync-server-2013.md) .</span><span class="sxs-lookup"><span data-stu-id="8fdd4-108">For details about Lync Server 2013, refer to the [Microsoft Lync Server 2013](microsoft-lync-server-2013.md) documentation.</span></span>

<span data-ttu-id="8fdd4-109">Questo documento contiene le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-109">This document contains the following sections:</span></span>

  - <span data-ttu-id="8fdd4-110">Client Lync 2013</span><span class="sxs-lookup"><span data-stu-id="8fdd4-110">Lync 2013 client</span></span>

  - <span data-ttu-id="8fdd4-111">Lync Server</span><span class="sxs-lookup"><span data-stu-id="8fdd4-111">Lync Server</span></span>

  - <span data-ttu-id="8fdd4-112">Installazione</span><span class="sxs-lookup"><span data-stu-id="8fdd4-112">Installation</span></span>

  - <span data-ttu-id="8fdd4-113">Mobilità</span><span class="sxs-lookup"><span data-stu-id="8fdd4-113">Mobility</span></span>

  - <span data-ttu-id="8fdd4-114">Servizi di conferenza</span><span class="sxs-lookup"><span data-stu-id="8fdd4-114">Conferencing</span></span>

  - <span data-ttu-id="8fdd4-115">VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="8fdd4-115">Enterprise Voice</span></span>

  - <span data-ttu-id="8fdd4-116">Icone di presenza</span><span class="sxs-lookup"><span data-stu-id="8fdd4-116">Presence</span></span>

  - <span data-ttu-id="8fdd4-117">Applicazione Response Group e applicazione Parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="8fdd4-117">Response Group Application and Call Park Application</span></span>

  - <span data-ttu-id="8fdd4-118">Pannello di controllo, Generatore di topologie e Strumento di pianificazione di Lync Server</span><span class="sxs-lookup"><span data-stu-id="8fdd4-118">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

  - <span data-ttu-id="8fdd4-119">Localizzazione</span><span class="sxs-lookup"><span data-stu-id="8fdd4-119">Localization</span></span>

  - <span data-ttu-id="8fdd4-120">Copyright</span><span class="sxs-lookup"><span data-stu-id="8fdd4-120">Copyright</span></span>

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a><span data-ttu-id="8fdd4-121">Client Lync 2013</span><span class="sxs-lookup"><span data-stu-id="8fdd4-121">Lync 2013 client</span></span>

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a><span data-ttu-id="8fdd4-122">Il trasferimento di un file in un messaggio istantaneo non riesce se il file è aperto in un'altra applicazione</span><span class="sxs-lookup"><span data-stu-id="8fdd4-122">Transferring a file in an instant message fails if the file is open in another application</span></span>

<span data-ttu-id="8fdd4-123">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-123">**Issue:**</span></span>

<span data-ttu-id="8fdd4-124">Se si tenta di trasferire un file, ad esempio un documento di Word, inserendolo in un messaggio istantaneo a un altro utente di Lync, il trasferimento verrà visualizzato correttamente, ma potrebbe effettivamente non riuscire a trasferire il file.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-124">If you attempt to transfer a file, such as a Word document, by including it in an instant message to another Lync user, the transfer will appear to succeed but may actually fail to transfer the file.</span></span> <span data-ttu-id="8fdd4-125">Un'icona per il tipo di file verrà visualizzata nel client Lync, ma il file non può essere aperto dal destinatario previsto.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-125">An icon for the file type will be displayed in the Lync client, but the file cannot be opened by the intended receiver.</span></span> <span data-ttu-id="8fdd4-126">Non viene visualizzato alcun messaggio di errore che informa che il trasferimento non è stato eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-126">No error message is displayed to inform you that the transfer was not successfull.</span></span>

<span data-ttu-id="8fdd4-127">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-127">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-128">Per risolvere il problema, chiudere il file aperto o l'applicazione aperto prima di provare a trasferire il file in un messaggio istantaneo.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-128">To work around this issue, close the open file or application that has it open before attempting to transfer the file in an instant message.</span></span>

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="8fdd4-129">Lync Server</span><span class="sxs-lookup"><span data-stu-id="8fdd4-129">Lync Server</span></span>

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a><span data-ttu-id="8fdd4-130">Se la replica dei dati del servizio di archiviazione di Lync Server non riesce, gli amministratori dovranno verificare i contatori delle prestazioni per gli elementi della coda del servizio di archiviazione</span><span class="sxs-lookup"><span data-stu-id="8fdd4-130">If Lync Server Storage Service data replication fails, administrators will need to check performance counters for stale Storage Service queue items</span></span>

<span data-ttu-id="8fdd4-131">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-131">**Issue:**</span></span>

<span data-ttu-id="8fdd4-132">Il servizio di archiviazione di Lync Server usa il tessuto Windows per la replica.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-132">The Lync Server Storage Service uses Windows Fabric for replication.</span></span> <span data-ttu-id="8fdd4-133">Se i dati vengono eliminati in un server front-end principale, ma l'eliminazione in un server front-end secondario non riesce, ad esempio se si verifica un arresto o un errore imprevisto nel server front-end, i dati possono essere lasciati indietro e "orfani".</span><span class="sxs-lookup"><span data-stu-id="8fdd4-133">If data is deleted on a primary Front End Server, but the deletion on a secondary Front End Server fails—for example, if there is an unexpected shutdown or error on the Front End Server—data can be left behind and "orphaned."</span></span> <span data-ttu-id="8fdd4-134">I dati orfani possono causare prestazioni in grado di degradare e sprecare spazio su disco.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-134">The orphaned data can cause performance to degrade and waste drive space.</span></span>

<span data-ttu-id="8fdd4-135">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-135">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-136">Per aggirare il problema, se gli eventi LYSS\_DB\_Space\_used\_Error (ID = 32058) e Lyss\_DB\_Space\_used\_Critical (ID = 32059) vengono generati nel log eventi, gli amministratori dovrebbero controllare il contatore delle prestazioni nel server front-end in **ls: Lyss-API del servizio** di archiviazione con un nome di **Lyss-numero corrente di elementi della coda non aggiornati del servizio di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-136">To work around this issue, if the events LYSS\_DB\_SPACE\_USED\_ERROR (Id=32058) and LYSS\_DB\_SPACE\_USED\_CRITICAL (Id=32059) are generated in the event log, administrators should check the performance counter on the Front End Server under **LS:LYSS - Storage Service API** with a name of **LYSS - Current number of Storage Service stale queue items**.</span></span> <span data-ttu-id="8fdd4-137">Se questo contatore delle prestazioni ha un valore elevato, ad esempio maggiore di 50000, l'amministratore deve eseguire lo strumento CleanuUpStorageServiceData. exe nel Resource Kit di Lync Server 2013, che eliminerà tutti i dati orfani dal pool.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-137">If this performance counter has a high value—for example, greater than 50,000—then the administrator should run the CleanuUpStorageServiceData.exe tool in the Lync Server 2013 Resource Kit, which will delete all orphaned data from the pool.</span></span> <span data-ttu-id="8fdd4-138">Per informazioni dettagliate sullo strumento, vedere la documentazione di Lync Server 2013 Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-138">For details about the tool, see the Lync Server 2013 Resource Kit documentation.</span></span>

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a><span data-ttu-id="8fdd4-139">Ogni volta che viene modificata la configurazione di un indirizzo IP per un server o un pool, è necessario riavviare i servizi di Lync Server</span><span class="sxs-lookup"><span data-stu-id="8fdd4-139">Whenever the IP Address configuration is changed for a server or pool, Lync Server services need to be restarted</span></span>

<span data-ttu-id="8fdd4-140">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-140">**Issue:**</span></span>

<span data-ttu-id="8fdd4-141">Quando la configurazione dell'indirizzo IP viene modificata per una distribuzione di Lync Server 2013, ad esempio la modifica da IPv4 a dual stack o da doppio stack a IPv6, non tutti i componenti del server prelevano la modifica della configurazione finché i servizi non vengono riavviati.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-141">When the IP Address configuration is changed for a Lync Server 2013 deployment, such as changing from IPv4 to Dual Stack, or from Dual Stack to Ipv6, not all server components pick up the configuration change until the services are restarted.</span></span>

<span data-ttu-id="8fdd4-142">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-142">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-143">Per risolvere il problema, riavviare i servizi Lync Server dopo la modifica della configurazione dell'indirizzo IP per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-143">To work around this issue, restart Lync Server services after changing the IP Address configuration for the deployment.</span></span> <span data-ttu-id="8fdd4-144">A questo scopo, eseguire i cmdlet seguenti in Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-144">To do so, run the following cmdlets in the Lync Server Management Shell:</span></span>

   ```PowerShell
    Stop-CsWindowsService -graceful
   ```

   ```PowerShell
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a><span data-ttu-id="8fdd4-145">Il cmdlet di transazione sintetica per i servizi di conferenza telefonica con accesso esterno non è più disponibile in Lync Server 2013 Management Pack</span><span class="sxs-lookup"><span data-stu-id="8fdd4-145">The dial-in conferencing synthetic transaction cmdlet is no longer available in the Lync Server 2013 Management Pack</span></span>

<span data-ttu-id="8fdd4-146">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-146">**Issue:**</span></span>

<span data-ttu-id="8fdd4-147">Il cmdlet di transazione sintetica per le conferenze telefoniche con accesso esterno **Test-CsDialInConferencing** non è più disponibile nel Management Pack di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-147">The dial-in conferencing synthetic transaction cmdlet **Test-CsDialInConferencing** is no longer available in the Lync Server 2013 Management Pack.</span></span>

<span data-ttu-id="8fdd4-148">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-148">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-149">Uso del cmdlet di transazione sintetica per le conferenze telefoniche con accesso esterno **Test-CsDialInConferencing** è supportato solo internamente a un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-149">Use of the Dial-In Conferencing Synthetic Transaction cmdlet **Test-CsDialInConferencing** is supported only internally to an enterprise.</span></span>

<span data-ttu-id="8fdd4-150">Gli amministratori possono continuare a usare il cmdlet in Lync Server Management Shell per scopi di risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-150">Administrators may continue to use the cmdlet in Lync Server Management Shell for troubleshooting purposes.</span></span> <span data-ttu-id="8fdd4-151">Se necessario, un'organizzazione può anche sviluppare un Management Pack privato per eseguire il cmdlet internamente.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-151">If required, an enterprise can also develop a private management pack to run the cmdlet internally.</span></span>

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a><span data-ttu-id="8fdd4-152">Il servizio di registrazione centralizzato si arresta se il traffico di rete viene interrotto quando i file di log vengono copiati in condivisione di rete</span><span class="sxs-lookup"><span data-stu-id="8fdd4-152">The Centralized Logging Service stops if network traffic is disrupted when log files are being copied to network share</span></span>

<span data-ttu-id="8fdd4-153">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-153">**Issue:**</span></span>

<span data-ttu-id="8fdd4-154">Quando il servizio di registrazione centralizzato è configurato per l'uso di un percorso di rete (il valore del parametro CacheFileNetworkFolder del cmdlet **Get-CsClsConfiguration** è un percorso UNC valido), i file di log memorizzati nella cache vengono copiati nella condivisione di rete.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-154">When the Centralized Logging Service is configured to use a network path (the value of the CacheFileNetworkFolder parameter of the **Get-CsClsConfiguration** cmdlet is a valid UNC path), cached log files are copied to the network share.</span></span> <span data-ttu-id="8fdd4-155">Se si verificano interruzioni nel traffico di rete mentre i file vengono copiati, si verificherà un'eccezione che causerà l'interruzione del servizio di registrazione centralizzata.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-155">If there is a disruption in network traffic while the files are being copied, an exception will occur that will cause the centralized logging service to stop.</span></span>

<span data-ttu-id="8fdd4-156">Il servizio è configurato per il riavvio automatico di un massimo di tre volte, in modo che il servizio recuperi le prime tre eccezioni.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-156">The service is configured to automatically restart up to three times, so the service will recover from the first three exceptions.</span></span>

<span data-ttu-id="8fdd4-157">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-157">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-158">Non c'è soluzione alternativa per questo problema.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-158">There is no workaround for this issue.</span></span> <span data-ttu-id="8fdd4-159">Per identificare il problema, monitorare il log eventi per l'ID evento 7031 da "Gestione controllo servizi" che registra quando il servizio "Lync Server Central Logging Service Agent" ha terminato in modo imprevisto.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-159">To identify the issue, monitor the event log for Event ID 7031 from the "Service Control Manager" that logs when the "Lync Server Centralized Logging Service Agent" service has terminated unexpectedly.</span></span> <span data-ttu-id="8fdd4-160">Se si verificano più di tre volte, riavviare manualmente il servizio usando il cmdlet **Start-CsWindowService** .</span><span class="sxs-lookup"><span data-stu-id="8fdd4-160">If this happens more than three times, manually restart the service by using the **Start-CsWindowService** cmdlet.</span></span>

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a><span data-ttu-id="8fdd4-161">Gli elementi della coda del servizio di archiviazione devono essere importati manualmente</span><span class="sxs-lookup"><span data-stu-id="8fdd4-161">Storage Service Queue Items need to be imported manually</span></span>

<span data-ttu-id="8fdd4-162">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-162">**Issue:**</span></span>

<span data-ttu-id="8fdd4-163">Lync Server 2013 archivia i dati relativi alle conferenze e alla messaggistica istantanea, ad esempio i messaggi archiviati e la registrazione dei dettagli delle chiamate (CDR), in un database di ogni server front-end.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-163">Lync Server 2013 stores data about conferencing and instant messaging, such as archived messages and call detail recording (CDR), on a database on each Front End Server.</span></span> <span data-ttu-id="8fdd4-164">I dati vengono archiviati nel database mentre vengono elaborati prima di essere recapitati alla destinazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-164">The data is stored in the database while it is being processed before being delivered to the intended destination.</span></span> <span data-ttu-id="8fdd4-165">Per migliorare le prestazioni, Lync Server 2013 Esporta periodicamente gli elementi della coda dal database locale che non vengono elaborati per un periodo di tempo prolungato e li salva nell'archivio file.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-165">To improve performance, Lync Server 2013 periodically exports the queue items from the local database that are not processed for an extended period of time, and saves them on the file store.</span></span> <span data-ttu-id="8fdd4-166">Se l'archivio file non è disponibile, gli elementi vengono archiviati in ogni server front-end.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-166">If the file store is unavailable, the items are stored on each Front End Server.</span></span> <span data-ttu-id="8fdd4-167">La stessa operazione si verifica per evitare la perdita di dati durante il failover del pool.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-167">The same operation occurs to prevent data loss during pool failover.</span></span>

<span data-ttu-id="8fdd4-168">Durante l'operazione di esportazione, il servizio di archiviazione di Lync Server registra ogni fase del log eventi con gli ID evento di 32075 (viene avviata l'operazione di svuotamento completo), 32076 (il colore completo è completato), 32082 (livello di manutenzione a filo), 32083 (livello di manutenzione a filo) è completato), 32089 (lo svuotamento si è verificato a causa della compilazione del database).</span><span class="sxs-lookup"><span data-stu-id="8fdd4-168">During the export operation, the Lync Server Storage Service records every stage in the event log with event IDs of 32075 (full flush operation is started), 32076 (full flush is completed), 32082 (maintenance level flush is started), 32083 (maintenance level flush is completed), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="8fdd4-169">Questi dati non verranno automaticamente importati nel sistema per essere elaborati e recapitati alla destinazione finale (SQL Server o Exchange Server).</span><span class="sxs-lookup"><span data-stu-id="8fdd4-169">This data will not automatically be imported back to the system to be processed and delivered to its final destination (SQL Server or Exchange Server).</span></span>

<span data-ttu-id="8fdd4-170">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-170">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-171">Per importare i dati nel sistema, gli amministratori dovranno usare lo strumento ImportStorageServiceData nel Resource Kit di Lync Server, che aggiungerà di nuovo i dati nel sistema per essere elaborati e recapitati alla destinazione finale.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-171">To import the data to the system, administrators will need to use the ImportStorageServiceData tool in the Lync Server Resource Kit, which will add the data back into the system to be processed and delivered to its final destination.</span></span>

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a><span data-ttu-id="8fdd4-172">Le ricerche tramite query Web della Rubrica non avranno esito negativo se il valore predefinito per UseNormalizationRules viene modificato in falso</span><span class="sxs-lookup"><span data-stu-id="8fdd4-172">Address Book Web Query searches will fail if the default value for UseNormalizationRules is changed to False</span></span>

<span data-ttu-id="8fdd4-173">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-173">**Issue:**</span></span>

<span data-ttu-id="8fdd4-174">Se il valore predefinito per UseNormalizationRules è impostato su false, le ricerche di query Web della Rubrica non avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-174">If the default value for UseNormalizationRules is changed to False, Address Book Web Query searches will fail.</span></span> <span data-ttu-id="8fdd4-175">Dopo la modifica del valore predefinito, gli utenti del client Lync non saranno in grado di usare la query Web della Rubrica Lync per cercare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-175">After the default value is changed, Lync Client users will not be able to use Lync Address Book web query to search for users.</span></span>

<span data-ttu-id="8fdd4-176">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-176">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-177">Se il valore predefinito per UseNormalizationRules è impostato su false, in modo che gli utenti possano usare i numeri di telefono definiti in servizi di dominio Active Directory senza Lync Server 2013 applicando regole di normalizzazione, aggirare il problema eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-177">If the default value for UseNormalizationRules is set to False so that users can use phone numbers as defined in Active Directory Domain Services without Lync Server 2013 applying normalization rules, work around this issue by doing the following:</span></span>

1.  <span data-ttu-id="8fdd4-178">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-178">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8fdd4-179">Esegui una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-179">Do one of the following:</span></span>
    
      - <span data-ttu-id="8fdd4-180">Se la distribuzione include solo server Lync Server 2013, eseguire il cmdlet seguente a livello globale per modificare i valori di UseNormalizationRules e IgnoreGenericRules in true:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-180">If your deployment includes only Lync Server 2013 servers, run the following cmdlet at the global level to change the values for UseNormalizationRules and IgnoreGenericRules to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="8fdd4-181">Se la distribuzione include una combinazione di Lync Server 2013 e Lync Server 2010 o Office Communications Server 2007 R2, eseguire il cmdlet seguente e assegnarlo a ogni pool di Lync Server 2013 nella topologia:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-181">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="8fdd4-182">Attendere che la replica di CMS si verifichi in tutti i pool.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-182">Wait for CMS replication to occur on all pools.</span></span>

4.  <span data-ttu-id="8fdd4-183">Modificare il file delle regole di normalizzazione del telefono per la distribuzione per cancellare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-183">Modify the phone normalization rules file for your deployment to clear the content.</span></span> <span data-ttu-id="8fdd4-184">Il file si trova nella condivisione file di ogni pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-184">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="8fdd4-185">Se il file non è presente, creare un file vuoto denominato "regole di\_\_normalizzazione\_\_del numero di telefono aziendale. txt".</span><span class="sxs-lookup"><span data-stu-id="8fdd4-185">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt."</span></span>

5.  <span data-ttu-id="8fdd4-186">Attendere diversi minuti per tutti i pool di front-end per leggere i nuovi file.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-186">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="8fdd4-187">Eseguire il cmdlet seguente in ogni pool di Lync Server 2013 della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-187">Run the following cmdlet on each Lync Server 2013 pool in your deployment.</span></span>
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a><span data-ttu-id="8fdd4-188">Evento di errore 21054 del server della Rubrica viene generato una volta al giorno per ogni pool Lync 2013</span><span class="sxs-lookup"><span data-stu-id="8fdd4-188">Address Book Server error event 21054 is generated once daily for each Lync 2013 pool</span></span>

<span data-ttu-id="8fdd4-189">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-189">**Issue:**</span></span>

<span data-ttu-id="8fdd4-190">Lync Server 2013 Address Book Server genera l'evento di errore 21054 una volta al giorno durante l'esecuzione della manutenzione giornaliera.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-190">Lync Server 2013 Address Book Server will generate error event 21054 once every day when performing daily maintenance.</span></span> <span data-ttu-id="8fdd4-191">L'errore viene generato anche ogni volta che un amministratore esegue il cmdlet **Update-csAddressBook** , anche quando l'aggiornamento è riuscito.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-191">The error is also generated every time an administrator runs the **Update-csAddressBook** cmdlet, even when the update is successful.</span></span> <span data-ttu-id="8fdd4-192">Tuttavia, questo evento di errore può essere ignorato in modo sicuro quando l'aggiornamento è riuscito.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-192">However, this error event can safely be ignored when the update is successful.</span></span>

<span data-ttu-id="8fdd4-193">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-193">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-194">Quando si verifica questo evento di errore, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-194">When you encounter this error event, run the following cmdlet:</span></span>

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

<span data-ttu-id="8fdd4-195">Se il cmdlet segnala che non sono presenti oggetti non indicizzati o abbandonati, l'evento di errore 21054 può essere ignorato in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-195">If the cmdlet reports that there are no unindexed or abandoned objects, the error event 21054 can be safely ignored.</span></span>

<span data-ttu-id="8fdd4-196">Inoltre, l'indicatore di integrità chiave (KHI) "utenti della rubrica correttamente indicizzati" deve essere disattivato in System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-196">Additionally, the Key Health Indicator (KHI) "Address Book Users Correctly Indexed" should be turned off in System Center Operations Manager.</span></span>

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a><span data-ttu-id="8fdd4-197">Le richieste potrebbero non riuscire quando IPv6 è configurato in un pool di Edge</span><span class="sxs-lookup"><span data-stu-id="8fdd4-197">Requests may fail when IPv6 is configured on an Edge pool</span></span>

<span data-ttu-id="8fdd4-198">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-198">**Issue:**</span></span>

<span data-ttu-id="8fdd4-199">Quando IPv6 è configurato in un pool di Edge, alcune richieste al pool Edge potrebbero non riuscire.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-199">When IPv6 is configured on an Edge pool, some requests to the Edge pool may fail.</span></span>

<span data-ttu-id="8fdd4-200">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-200">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-201">Per risolvere il problema, non configurare un pool di Edge con IPv6.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-201">To work around this issue, do not configure an Edge pool with IPv6.</span></span>

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a><span data-ttu-id="8fdd4-202">Il cmdlet Invoke-csPoolFailback potrebbe non riuscire durante il failback del pool</span><span class="sxs-lookup"><span data-stu-id="8fdd4-202">The invoke-csPoolFailback cmdlet may fail during pool failback</span></span>

<span data-ttu-id="8fdd4-203">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-203">**Issue:**</span></span>

<span data-ttu-id="8fdd4-204">Quando si tenta di non eseguire il backup di un pool, il cmdlet **Invoke-csPoolFailback** potrebbe non riuscire con l'errore "non è possibile completare il processo di idratazione dopo ripetuti tentativi".</span><span class="sxs-lookup"><span data-stu-id="8fdd4-204">When attempting to fail back a pool, the **invoke-csPoolFailback** cmdlet may fail with the error, "Failed to complete hydration process after repeated attempts."</span></span>

<span data-ttu-id="8fdd4-205">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-205">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-206">Per risolvere il problema, eseguire di nuovo il cmdlet e attendere che il cmdlet abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-206">To work around this issue, run the cmdlet again, and wait until the cmdlet succeeds.</span></span> <span data-ttu-id="8fdd4-207">Tieni presente che il processo di failback può richiedere diversi minuti per il completamento.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-207">Note that the failback process can take several minutes to complete.</span></span> <span data-ttu-id="8fdd4-208">Potrebbe essere necessario un massimo di 60 minuti per un pool con utenti di 20.000.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-208">It may take up to 60 minutes for a pool with 20,000 users.</span></span>

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a><span data-ttu-id="8fdd4-209">La perdita di dati può verificarsi quando si aggiunge un server front-end a un pool già esistente-Hybrid, Skype for business online</span><span class="sxs-lookup"><span data-stu-id="8fdd4-209">Data loss may occur when you add a Front End Server to an already established pool – Hybrid, Skype for Business Online</span></span>

<span data-ttu-id="8fdd4-210">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-210">**Issue:**</span></span>

<span data-ttu-id="8fdd4-211">Questo problema può verificarsi in un ambiente in cui un pool ha più di un server front-end e si riavvia uno dei server front-end oppure si aggiunge un nuovo server front-end che in precedenza non faceva parte del pool.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-211">You may encounter this issue in an environment where a pool has more than one Front End Server, and you either restart one of the Front End Servers, or add a new Front End Server that was not previously part of the pool.</span></span>

<span data-ttu-id="8fdd4-212">Gli utenti i cui dati vengono archiviati possono verificare la perdita di dati fino a quando non viene stabilita una distribuzione stabile dell'archiviazione dei dati per il pool.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-212">Users whose data is being archived may experience data loss until a stable distribution of data archiving is established for the pool.</span></span> <span data-ttu-id="8fdd4-213">Questo periodo di potenziale perdita di dati è limitato a 15 minuti per le conversazioni tra persone e 30 minuti per le conferenze.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-213">This period of potential data loss is limited to 15 minutes for person-to-person conversations, and 30 minutes for conferences.</span></span>

<span data-ttu-id="8fdd4-214">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-214">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-215">Quando si esegue la manutenzione, invece di avviare i server front-end nel pool uno alla volta, è consigliabile eseguire il failover del pool in un altro pool e quindi svolgere le attività di manutenzione nei server.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-215">When you perform maintenance, instead of starting Front End Servers in the pool one by one, you should fail over the pool to another pool, and then perform maintenance tasks on the servers.</span></span> <span data-ttu-id="8fdd4-216">È anche possibile rendere il servizio non disponibile prima di eseguire attività di manutenzione e quindi ripristinare la disponibilità al termine della manutenzione.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-216">You can also make the service unavailable before performing maintenance tasks, and then restore availability when maintenance is complete.</span></span>

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a><span data-ttu-id="8fdd4-217">Gli amministratori non possono ottenere il conteggio delle licenze usando il cmdlet Get-CsClientAccessLicense</span><span class="sxs-lookup"><span data-stu-id="8fdd4-217">Administrators cannot get licensee count by using the Get-CsClientAccessLicense cmdlet</span></span>

<span data-ttu-id="8fdd4-218">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-218">**Issue:**</span></span>

<span data-ttu-id="8fdd4-219">Gli amministratori non possono ottenere un uso accurato della licenza client usando il cmdlet **Get-CsClientAccessLicense** .</span><span class="sxs-lookup"><span data-stu-id="8fdd4-219">Administrators cannot get accurate client license usage by using the **Get-CsClientAccessLicense** cmdlet.</span></span>

<span data-ttu-id="8fdd4-220">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-220">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-221">Per controllare il tipo di licenza del server, è possibile eseguire il cmdlet **Get-CsService** per recuperare i nomi di dominio completi (FDQNs) di tutti i database.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-221">To check the server license type, you can run the **Get-CsService** cmdlet to retrieve the fully qualified domain names (FDQNs) of all databases.</span></span> <span data-ttu-id="8fdd4-222">Se il nome di dominio completo del server front-end è uguale al nome di dominio completo del database back-end, la licenza è una licenza Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-222">If the FQDN of the Front End Server is the same as the FQDN of the back-end database, the license is a Standard edition license.</span></span> <span data-ttu-id="8fdd4-223">In caso contrario, la licenza è una licenza di Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-223">Otherwise, the license is an Enterprise edition license.</span></span>

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a><span data-ttu-id="8fdd4-224">Il conteggio delle licenze client non viene segnalato in modo accurato</span><span class="sxs-lookup"><span data-stu-id="8fdd4-224">Client licensee count is not accurately reported</span></span>

<span data-ttu-id="8fdd4-225">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-225">**Issue:**</span></span>

<span data-ttu-id="8fdd4-226">Quando si determina il conteggio delle licenze client, è possibile che si verifichino le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-226">When determining client license counts, you may experience the following conditions:</span></span>

1.  <span data-ttu-id="8fdd4-227">**Conteggio delle licenze impreciso per gli utenti di dispositivi mobili**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-227">**Inaccurate license count for mobile users**</span></span>
    
    <span data-ttu-id="8fdd4-228">Il conteggio delle licenze si basa sul numero di indirizzi IP univoci per gli utenti basati su dispositivi.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-228">The license count is based on the number of unique IP addresses for device-based users.</span></span> <span data-ttu-id="8fdd4-229">Il conteggio delle licenze sarà limitato nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-229">The license count will be limited in the following ways:</span></span>
    
      - <span data-ttu-id="8fdd4-230">Se l'indirizzo IP per l'utente cambia durante le sessioni di Lync, verranno conteggiate le licenze.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-230">Licenses will be overcounted if the IP address for the user changes during Lync sessions.</span></span> <span data-ttu-id="8fdd4-231">Questo problema può verificarsi quando un utente si connette a Lync Server da più di una posizione con un client desktop.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-231">This can occur when a user connects to Lync Server from more than one location with a desktop client.</span></span>
    
      - <span data-ttu-id="8fdd4-232">Le licenze verranno sottovalutate se un utente si connette a un client per dispositivi mobili, perché non è possibile determinare l'indirizzo IP per il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-232">Licenses will be undercounted if a user connects with a mobile client, because the IP address for the device cannot be determined.</span></span>

2.  <span data-ttu-id="8fdd4-233">**Le licenze vengono conteggiate due volte per le chiamate PSTN (Public Switched Telephone Network) a client Lync, le chiamate client Lync alle linee PSTN e le chiamate Lync inoltrate alle linee PSTN**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-233">**Licenses are counted twice for public switched telephone network (PSTN) calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="8fdd4-234">Negli scenari seguenti verranno conteggiate due licenze aggiuntive anziché una, perché vengono conteggiati sia il numero di telefono che l'utente di Lync per determinare il numero di licenze usate.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-234">In the following scenarios, two additional licenses will be counted instead of one because both the phone number and the Lync user are counted to determine the number of licenses used.</span></span> <span data-ttu-id="8fdd4-235">Per ottenere dati di licenza accurati, rimuovere manualmente le licenze generate da un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-235">To obtain accurate licensing data, manually remove the licenses generated by a phone number.</span></span>
    
      - <span data-ttu-id="8fdd4-236">Una telefonata PSTN a Lync</span><span class="sxs-lookup"><span data-stu-id="8fdd4-236">A PSTN phone call to Lync</span></span>
    
      - <span data-ttu-id="8fdd4-237">Una chiamata Lync a una linea PSTN</span><span class="sxs-lookup"><span data-stu-id="8fdd4-237">A Lync call to a PSTN line</span></span>
    
      - <span data-ttu-id="8fdd4-238">Una chiamata PSTN a Lync e quindi Lync inoltra la chiamata a una linea PSTN.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-238">A PSTN call to Lync, and then Lync forwards the call to a PSTN line.</span></span> <span data-ttu-id="8fdd4-239">Verrà conteggiata una delle righe PSTN.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-239">One of the PSTN lines will be counted.</span></span>

3.  <span data-ttu-id="8fdd4-240">**Una licenza non verrà conteggiata per un telefono Lync connesso**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-240">**A license will not be counted for a logged-on Lync phone**</span></span>
    
    <span data-ttu-id="8fdd4-241">Quando un utente usa un telefono con certificazione Lync, se il telefono si connette e rimane connesso, che mantiene lo stato di accesso, il telefono non verrà conteggiato come utilizzo di una licenza se la query per le licenze si verifica dopo l'accesso del telefono.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-241">When a user uses a Lync-certified phone, if the phone logs in and stays connected, which retains its logon status, the phone will not be counted as using a license if the query for licenses occurs after the phone logged in.</span></span>

4.  <span data-ttu-id="8fdd4-242">**Licenze contate per i telefoni PSTN che partecipano a conferenze**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-242">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="8fdd4-243">Quando un utente partecipa a una conferenza con un telefono PSTN, la licenza verrà conteggiata in modo impreciso per partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-243">When a user joins a conference with a PSTN phone, a license will inaccurately be counted for joining the conference.</span></span> <span data-ttu-id="8fdd4-244">Tuttavia, non è necessaria alcuna licenza per partecipare a una conferenza con un telefono PSTN.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-244">However, no license is needed to join a conference with a PSTN phone.</span></span>

<span data-ttu-id="8fdd4-245">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-245">**Workaround:**</span></span>

1.  <span data-ttu-id="8fdd4-246">**Conteggio delle licenze impreciso per gli utenti di dispositivi mobili**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-246">**Inaccurate license count for mobile users**</span></span>
    
      - <span data-ttu-id="8fdd4-247">È possibile identificare manualmente gli indirizzi IP che appartengono allo stesso dispositivo e quindi rimuoverne uno nel conteggio delle licenze.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-247">You can manually identify the IP addresses that belong to the same device and then remove one of them in the license count.</span></span>
    
      - <span data-ttu-id="8fdd4-248">Non esiste alcuna soluzione alternativa per questo problema con i dispositivi mobili che si connettono al client Lync.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-248">There is no workaround for this issue with mobile devices connecting with Lync client.</span></span>

2.  <span data-ttu-id="8fdd4-249">**Le licenze vengono conteggiate due volte per le chiamate PSTN al client Lync, le chiamate client Lync alle linee PSTN e le chiamate Lync inoltrate alle linee PSTN**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-249">**Licenses are counted twice for PSTN calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="8fdd4-250">Sarà necessario identificare manualmente il numero di telefono PSTN e rimuovere il conteggio delle licenze generato per l'utente.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-250">You will need to manually identify the PSTN phone number and remove the license count generated for it.</span></span>

3.  <span data-ttu-id="8fdd4-251">**Una licenza non verrà conteggiata per un telefono Lync connesso**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-251">**A license will not be counted for a logged-in Lync phone**</span></span>
    
    <span data-ttu-id="8fdd4-252">È possibile configurare il telefono Lync per disconnettersi e quindi accedere di nuovo a intervalli regolari, ad esempio ogni 3 mesi.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-252">You can configure the Lync phone to log off, and then log on again, at a regular interval, such as every 3 months.</span></span>

4.  <span data-ttu-id="8fdd4-253">**Licenze contate per i telefoni PSTN che partecipano a conferenze**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-253">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="8fdd4-254">È possibile identificare manualmente il numero di telefono PSTN usato per partecipare alla conferenza e rimuovere la licenza generata dal numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-254">You can manually identify the PSTN phone number that is used to join the conference and remove the license generated by the phone number.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a><span data-ttu-id="8fdd4-255">Il pannello di controllo di Lync Server smette di funzionare in un ambiente VMware dopo l'aggiornamento a Silverlight 5</span><span class="sxs-lookup"><span data-stu-id="8fdd4-255">The Lync Server Control Panel stops working in a VMware environment after upgrading to Silverlight 5</span></span>

<span data-ttu-id="8fdd4-256">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-256">**Issue:**</span></span>

<span data-ttu-id="8fdd4-257">Se si usa il pannello di controllo di Lync Server in un ambiente VMware, il pannello di controllo di Lync Server potrebbe smettere di funzionare dopo l'aggiornamento di Microsoft Silverlight alla versione 5.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-257">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Microsoft Silverlight to version 5.</span></span>

<span data-ttu-id="8fdd4-258">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-258">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-259">Per risolvere il problema, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-259">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="8fdd4-260">Disinstallare Silverlight 5 e installare Silverlight 4 da [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156).</span><span class="sxs-lookup"><span data-stu-id="8fdd4-260">Uninstall Silverlight 5, and install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156).</span></span>

  - <span data-ttu-id="8fdd4-261">Accedere al pannello di controllo di Lync Server da un computer che non è un computer virtuale VMware.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-261">Access the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="8fdd4-262">A questo scopo, è possibile avviare il pannello di controllo di Lync Server dal menu **Start** di Windows sul server, se nel computer sono installati gli strumenti di amministrazione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-262">To do so, you can start the Lync Server Control Panel from the Windows **Start** menu on the server, if the Lync Server Administration tools are installed on the computer.</span></span>
    
    <span data-ttu-id="8fdd4-263">È anche possibile accedere al pannello di controllo di Lync Server tramite un Web browser.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-263">You can also access the Lync Server Control Panel by using a web browser.</span></span> <span data-ttu-id="8fdd4-264">L'URL sarà\<simile a FQDN\_\_\>del pool di frontend https:///CSCP.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-264">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a><span data-ttu-id="8fdd4-265">Le informazioni utente nel servizio Rubrica non vengono aggiornate dopo la modifica del nome distinto per l'utente in Active Directory</span><span class="sxs-lookup"><span data-stu-id="8fdd4-265">User information in the Address Book Service is not updated after the distinguished name for the user is modified in Active Directory</span></span>

<span data-ttu-id="8fdd4-266">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-266">**Issue:**</span></span>

<span data-ttu-id="8fdd4-267">Se il nome distinto di un utente (noto anche come DN) viene modificato in servizi di dominio Active Directory, le eventuali modifiche aggiuntive non verranno aggiornate nel servizio Rubrica (ABS).</span><span class="sxs-lookup"><span data-stu-id="8fdd4-267">If a user’s distinguished name (also known as DN) is changed in Active Directory Domain Services, any additional changes will not be updated in the Address Book Service (ABS).</span></span> <span data-ttu-id="8fdd4-268">Questa operazione non ha alcun effetto sull'accesso o sulla presenza per l'utente, ma impedirà la comunicazione per l'utente se viene modificato anche l'indirizzo SIP, perché la ricerca restituirà un indirizzo SIP obsoleto.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-268">This does not affect sign-in or presence for the user, but it will prevent communication for the user if the SIP address is also changed, because searches will return an outdated SIP address.</span></span>

<span data-ttu-id="8fdd4-269">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-269">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-270">Per risolvere il problema, non modificare il DN di un utente.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-270">To work around this issue, do not change a user’s DN.</span></span> <span data-ttu-id="8fdd4-271">Se si ripristina il DN per l'utente con il valore precedente, gli aggiornamenti verranno riflessi nel servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-271">If you revert the DN for the user to the previous value, updates will be reflected in the Address Book Service.</span></span>

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a><span data-ttu-id="8fdd4-272">Installazione</span><span class="sxs-lookup"><span data-stu-id="8fdd4-272">Installation</span></span>

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a><span data-ttu-id="8fdd4-273">L'uso di caratteri non ASCII può causare il mancato avvio di Lync Server</span><span class="sxs-lookup"><span data-stu-id="8fdd4-273">Using non-ASCII characters may result in Lync server failing to start</span></span>

<span data-ttu-id="8fdd4-274">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-274">**Issue:**</span></span>

<span data-ttu-id="8fdd4-275">Il programma di installazione non riesce se il nome della cartella di destinazione include caratteri non ASCII (inclusi UNICODE, set di caratteri a doppio byte (DBCS), UTF-8 e UTF-16).</span><span class="sxs-lookup"><span data-stu-id="8fdd4-275">Setup will fail if the destination folder name includes non-ASCII characters (including UNICODE, double-byte character set (DBCS), UTF-8, and UTF-16).</span></span> <span data-ttu-id="8fdd4-276">Inoltre, la configurazione può avere esito positivo, ma il server non si avvia se i caratteri non ASCII sono contenuti in uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-276">In addition, Setup may succeed but the server will not start if non-ASCII characters are contained in any of the following:</span></span>

  - <span data-ttu-id="8fdd4-277">Nome computer</span><span class="sxs-lookup"><span data-stu-id="8fdd4-277">Computer name</span></span>

  - <span data-ttu-id="8fdd4-278">Nome di dominio</span><span class="sxs-lookup"><span data-stu-id="8fdd4-278">Domain name</span></span>

  - <span data-ttu-id="8fdd4-279">Nome utente</span><span class="sxs-lookup"><span data-stu-id="8fdd4-279">User name</span></span>

  - <span data-ttu-id="8fdd4-280">URI SIP utente</span><span class="sxs-lookup"><span data-stu-id="8fdd4-280">User SIP URI</span></span>

  - <span data-ttu-id="8fdd4-281">Nome dell'account del servizio</span><span class="sxs-lookup"><span data-stu-id="8fdd4-281">Service account name</span></span>

<span data-ttu-id="8fdd4-282">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-282">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-283">Usare solo caratteri ASCII nel nome della cartella di destinazione, il nome del computer, il nome di dominio, il nome utente, l'URI SIP dell'utente e i nomi degli account del servizio.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-283">Use only ASCII characters in the destination folder name, computer name, domain name, user name, user SIP URI, and service account names.</span></span>

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a><span data-ttu-id="8fdd4-284">L'hotfix per "danneggiamento dell'heap si verifica quando un modulo chiama il metodo InsertEntityBody in IIS 7,5" deve essere installato prima di installare Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8fdd4-284">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" must be installed prior to installing Lync Server 2013</span></span>

<span data-ttu-id="8fdd4-285">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-285">**Issue:**</span></span>

<span data-ttu-id="8fdd4-286">L'hotfix per "danneggiamento dell'heap si verifica quando un modulo chiama il metodo InsertEntityBody in IIS[https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)7,5" (), descritto nell'articolo della Microsoft[https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)Knowledge base 264886 (), deve essere installato prima di installare Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-286">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" ([https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)), described in Microsoft Knowledge Base article 264886 ([https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)), must be installed prior to installing Lync Server 2013.</span></span>

<span data-ttu-id="8fdd4-287">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-287">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-288">Scaricare e installare l'hotfix dall'area download Microsoft [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602).</span><span class="sxs-lookup"><span data-stu-id="8fdd4-288">Download and install the hotfix from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602).</span></span>

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a><span data-ttu-id="8fdd4-289">Lync Server 2013 non riesce a installare in un sistema operativo ITA Windows Server 2012 versione RTM</span><span class="sxs-lookup"><span data-stu-id="8fdd4-289">Lync Server 2013 fails to install on ITA Windows Server 2012 OS RTM version</span></span>

<span data-ttu-id="8fdd4-290">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-290">**Issue:**</span></span>

<span data-ttu-id="8fdd4-291">L'installazione di Lync Server 2013 non riesce su ITA Windows Server 2012 a causa di un errore di installazione in tessuto Windows.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-291">Lync Server 2013 installation fails on ITA Windows Server 2012 due to Windows Fabric installation failing.</span></span>

<span data-ttu-id="8fdd4-292">L'installazione di un tessuto Windows non riesce perché le tracce tessuto vengono create con il formato ora di HH: MM: SS.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-292">Windows Fabric installation fails because fabric traces are created with the time format of HH:MM:SS.</span></span> <span data-ttu-id="8fdd4-293">Tuttavia, in ITA Windows Server, il formato dell'ora è HH. MM.SS.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-293">However, in ITA Windows Server, the time format is HH.MM.SS.</span></span>

<span data-ttu-id="8fdd4-294">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-294">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-295">Per risolvere il problema, aggiornare il registro di sistema prima di installare Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-295">To work around this issue, update the system registry before installing Lync Server 2013.</span></span> <span data-ttu-id="8fdd4-296">La chiave del registro di sistema che deve essere aggiornata è\_:\\gli utenti di HKEY. Pannello\\\\di controllo predefinito\\sTimeFormat internazionale.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-296">The registry key that needs to be updated is: HKEY\_USERS\\.DEFAULT\\Control Panel\\International\\sTimeFormat.</span></span> <span data-ttu-id="8fdd4-297">Modificare il valore di sTimeFormat in HH: mm: SS usando l'interfaccia della riga di comando di Windows PowerShell come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-297">Change the value of sTimeFormat to HH:mm:ss by using the Windows PowerShell command-line interface as follows:</span></span>

1.  <span data-ttu-id="8fdd4-298">Avviare Windows PowerShell ed eseguire i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-298">Start Windows PowerShell and run the following cmdlets:</span></span>
    
       ```PowerShell
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```PowerShell
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  <span data-ttu-id="8fdd4-299">Per visualizzare il valore corrente, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-299">To view the current value, run the following cmdlet:</span></span>
    
        Get-itemproperty $a -Name sTimeFormat
    
    <span data-ttu-id="8fdd4-300">Prendere nota del valore corrente di sTimeFormat in modo che possa essere ripristinato al termine dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-300">Make note of the current value for sTimeFormat so it can be restored after the installation is complete.</span></span>

3.  <span data-ttu-id="8fdd4-301">Per impostare su nuovo valore, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-301">To set to new value, run the following cmdlet:</span></span>
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  <span data-ttu-id="8fdd4-302">Dopo che Lync Server 2013 è stato installato correttamente, ripristinare il valore originale per sTimeFormat eseguendo il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-302">After Lync Server 2013 has been successfully installed, restore the original value for the sTimeFormat by running the following cmdlet:</span></span>
    
        - <span data-ttu-id="8fdd4-303">Set-ItemProperty $a-Name sTimeFormat-value "<valore annotato al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-303">Set-ItemProperty $a -Name sTimeFormat -Value "<Value noted down in Step 3.</span></span> <span data-ttu-id="8fdd4-304">sopra> "</span><span class="sxs-lookup"><span data-stu-id="8fdd4-304">above>"</span></span>

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a><span data-ttu-id="8fdd4-305">Mobilità</span><span class="sxs-lookup"><span data-stu-id="8fdd4-305">Mobility</span></span>

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a><span data-ttu-id="8fdd4-306">Problemi per i client mobili durante il processo di failover del server</span><span class="sxs-lookup"><span data-stu-id="8fdd4-306">Issues for mobile clients during the server failover process</span></span>

<span data-ttu-id="8fdd4-307">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-307">**Issue:**</span></span>

<span data-ttu-id="8fdd4-308">Quando un server Lync non riesce e il processo di failover inizia, i problemi seguenti possono influire sugli utenti del client mobile:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-308">When a Lync Server fails and the failover process begins, the following issues may affect mobile client users:</span></span>

  - <span data-ttu-id="8fdd4-309">Nessuna chiamata Lync in arrivo o segnale per un massimo di 10 minuti dopo l'inizio del failover.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-309">No incoming Lync call or signal for up to 10 minutes after failover begins.</span></span>

  - <span data-ttu-id="8fdd4-310">Non è possibile accettare le richieste di chat in arrivo</span><span class="sxs-lookup"><span data-stu-id="8fdd4-310">Cannot accept incoming Chat requests</span></span>

  - <span data-ttu-id="8fdd4-311">Non è possibile partecipare alle riunioni se il server non riuscito è il server principale per l'utente</span><span class="sxs-lookup"><span data-stu-id="8fdd4-311">Cannot join meetings if the failed server is the home server for the user</span></span>

<span data-ttu-id="8fdd4-312">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-312">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-313">Non c'è soluzione alternativa per questo problema.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-313">There is no workaround for this issue.</span></span> <span data-ttu-id="8fdd4-314">La funzionalità normale verrà ripristinata al termine del processo di failover.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-314">Normal functionality will be restored once the failover process is complete.</span></span>

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a><span data-ttu-id="8fdd4-315">Se un utente mobile rifiuta una chiamata in arrivo da un altro endpoint Lync, la chiamata viene visualizzata come conversione mancata nei client mobili di Lync</span><span class="sxs-lookup"><span data-stu-id="8fdd4-315">If a mobile user declines an incoming call from another Lync endpoint, the call is displayed as a missed conversion on Lync Mobile clients</span></span>

<span data-ttu-id="8fdd4-316">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-316">**Issue:**</span></span>

<span data-ttu-id="8fdd4-317">Se un utente mobile rifiuta una chiamata in arrivo e la chiamata ha avuto origine da un altro endpoint Lync, la chiamata viene visualizzata come conversazione persa nel client mobile di Lync invece che in una chiamata nell'elenco delle chiamate di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-317">If a mobile user declines an incoming call, and the call originated from another Lync endpoint, the call is displayed as a missed conversation in the Lync Mobile client instead of a call in the device call list.</span></span>

<span data-ttu-id="8fdd4-318">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-318">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-319">Non c'è soluzione alternativa per questo problema.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-319">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a><span data-ttu-id="8fdd4-320">Il client per dispositivi mobili potrebbe non visualizzare il nome visualizzato di un contatto federato durante la ricerca di contatti</span><span class="sxs-lookup"><span data-stu-id="8fdd4-320">The mobile client may not display a federated contact’s display name when searching for contacts</span></span>

<span data-ttu-id="8fdd4-321">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-321">**Issue:**</span></span>

<span data-ttu-id="8fdd4-322">Il nome visualizzato per i contatti federati potrebbe non essere visualizzato in alcuni scenari, ad esempio durante la ricerca di un contatto federato nell'elenco contatti.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-322">The display name for federated contacts may not be displayed in some scenarios, such as when searching for a federated contact in the contact list.</span></span> <span data-ttu-id="8fdd4-323">Questo problema può verificarsi quando non esiste un abbonamento a presenza attiva per il contatto dal client di Lync mobile.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-323">This can occur when the there is no active presence subscription for the contact from the Lync mobile client.</span></span>

<span data-ttu-id="8fdd4-324">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-324">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-325">Non c'è soluzione alternativa per questo problema.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-325">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a><span data-ttu-id="8fdd4-326">Nel client mobile, le informazioni sull'invito e il timestamp mancano da una conversazione persa che è un invito a una conferenza</span><span class="sxs-lookup"><span data-stu-id="8fdd4-326">In the mobile client, invitee and timestamp information are missing from a missed conversation that is an invitation to a conference</span></span>

<span data-ttu-id="8fdd4-327">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-327">**Issue:**</span></span>

<span data-ttu-id="8fdd4-328">Nel client per dispositivi mobili, quando una conversazione persa è un invito a una conferenza, le informazioni sull'invito e il timestamp mancano nel messaggio di conversazione persa.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-328">In the mobile client, when a missed conversation is an invitation to a conference, the invitee and timestamp information is missing from the missed conversation message.</span></span>

<span data-ttu-id="8fdd4-329">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-329">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-330">Non c'è soluzione alternativa per questo problema.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-330">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a><span data-ttu-id="8fdd4-331">Gli utenti di client mobili che effettuano chiamate tramite VoIP non possono uscire dalla segreteria telefonica per gli utenti la cui segreteria telefonica è configurata in Exchange 2010 o versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="8fdd4-331">Mobile client users making calls using VoIP are not be able to leave voice mail for users whose voice mail is configured in Exchange 2010 or earlier versions</span></span>

<span data-ttu-id="8fdd4-332">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-332">**Issue:**</span></span>

<span data-ttu-id="8fdd4-333">Se un utente di client per dispositivi mobili USA VoIP per effettuare chiamate, l'utente non potrà uscire dalla segreteria telefonica per gli utenti configurati per l'uso della segreteria telefonica in Microsoft Exchange Server 2007 o in Microsoft Exchange Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-333">If a mobile client user is using VoIP to place calls, the user will not be able to leave voice mail messages for users configured to use voice mail in Microsoft Exchange Server 2007 or Microsoft Exchange Server 2010.</span></span>

<span data-ttu-id="8fdd4-334">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-334">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-335">Per risolvere il problema, usare Exchange 2010 con SP1 o versione successiva di Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-335">To work around this issue, use Exchange 2010 with SP1 or later version of Microsoft Exchange Server.</span></span>

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a><span data-ttu-id="8fdd4-336">Quando si usa il blocco con l'URL per la configurazione della versione client nei client mobili, potrebbe essere visualizzato un messaggio di errore non corretto</span><span class="sxs-lookup"><span data-stu-id="8fdd4-336">When using Block with URL for Client Version Configuration on mobile clients, an incorrect error message may be displayed</span></span>

<span data-ttu-id="8fdd4-337">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-337">**Issue:**</span></span>

<span data-ttu-id="8fdd4-338">Quando si usa il **blocco con l'URL** per la configurazione della versione client nei client mobili, potrebbe essere visualizzato un messaggio di errore non corretto quando la versione client non è supportata.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-338">When using **Block with URL** for Client Version Configuration on mobile clients, an incorrect error message may be displayed when the client version is not supported.</span></span>

<span data-ttu-id="8fdd4-339">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-339">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-340">Per risolvere il problema, configurare la configurazione della versione client per l'uso di **Block** invece di **Block con URL**.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-340">To work around this issue, configure Client Version Configuration to use **Block** instead of **Block with URL**.</span></span>

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a><span data-ttu-id="8fdd4-341">Servizi di conferenza</span><span class="sxs-lookup"><span data-stu-id="8fdd4-341">Conferencing</span></span>

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a><span data-ttu-id="8fdd4-342">Il software antivirus in esecuzione nei server front end di Lync Server 2013 può causare il riciclo di domini applicazione, che interrompe temporaneamente il servizio per Lync Web App 2013, Lync Mobile 2010 e i client di Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="8fdd4-342">Antivirus software running on Lync Server 2013 Front End Servers can cause Application Domain recycling, which temporarily interrupts service for Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013 clients</span></span>

<span data-ttu-id="8fdd4-343">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-343">**Issue:**</span></span>

<span data-ttu-id="8fdd4-344">Il software antivirus può attivare il riavvio del dominio dell'applicazione, che può comportare la perdita del proprio stato nelle applicazioni client API Web di 2013 Lync (Lync Web App 2013, Lync Mobile 2010 e Lync Mobile 2013).</span><span class="sxs-lookup"><span data-stu-id="8fdd4-344">Antivirus software can trigger application domain restarts, which can result in Lync Mobility Service 2013 and unified communications (UC) Web API client applications (Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013) to lose their state.</span></span>

<span data-ttu-id="8fdd4-345">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-345">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-346">Per risolvere il problema, escludere le cartelle che contengono componenti Web e .NET Framework da analisi antivirus.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-346">To work around this issue, exclude the folders containing Web components and .NET framework from antivirus scanning.</span></span> <span data-ttu-id="8fdd4-347">Per informazioni dettagliate, vedere l'articolo 312592 della Microsoft Knowledge Base "PRB: riavvii di un'applicazione casuale con" l'applicazione sta riavviando " [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592)errore in ASP.NET," at.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-347">For details, see Microsoft Knowledge Base article 312592, "PRB: Random application restarts with 'Application is restarting' error in ASP.NET," at [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592).</span></span>

<span data-ttu-id="8fdd4-348">Le cartelle seguenti devono essere escluse:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-348">The following folders should be excluded:</span></span>

  - <span data-ttu-id="8fdd4-349">% ProgramFiles%\\Microsoft Lync Server 2013\\Web\\Components\\MCX EXT</span><span class="sxs-lookup"><span data-stu-id="8fdd4-349">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Ext</span></span>

  - <span data-ttu-id="8fdd4-350">% ProgramFiles%\\Microsoft Lync Server 2013\\Web\\Components\\MCX int</span><span class="sxs-lookup"><span data-stu-id="8fdd4-350">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Int</span></span>

  - <span data-ttu-id="8fdd4-351">% ProgramFiles%\\Microsoft Lync Server 2013\\Web\\Components\\UCWA int</span><span class="sxs-lookup"><span data-stu-id="8fdd4-351">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Int</span></span>

  - <span data-ttu-id="8fdd4-352">% ProgramFiles%\\Microsoft Lync Server 2013\\Web\\Components\\UCWA EXT</span><span class="sxs-lookup"><span data-stu-id="8fdd4-352">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Ext</span></span>

  - <span data-ttu-id="8fdd4-353">% WINDIR%\\Microsoft.NET\\Framework64\\v 4.0.30319\\config</span><span class="sxs-lookup"><span data-stu-id="8fdd4-353">%Windir%\\Microsoft.NET\\Framework64\\v4.0.30319\\Config</span></span>

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a><span data-ttu-id="8fdd4-354">I controlli ActiveX o il supporto XMLHTTP nativo devono essere abilitati in Windows Internet Explorer per partecipare correttamente alle conferenze</span><span class="sxs-lookup"><span data-stu-id="8fdd4-354">ActiveX Controls or native XMLHTTP support must be enabled in Windows Internet Explorer to successfully join conferences</span></span>

<span data-ttu-id="8fdd4-355">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-355">**Issue:**</span></span>

<span data-ttu-id="8fdd4-356">Se un utente ha disabilitato sia i controlli ActiveX che il supporto XMLHTTP nativo nelle impostazioni del browser Internet di Windows Internet Explorer, l'utente non sarà in grado di partecipare a una riunione se Internet Explorer è selezionato come browser predefinito.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-356">If a user has disabled both ActiveX Controls and native XMLHTTP support in Windows Internet Explorer Internet browser settings, the user will not be able to join a meeting if Internet Explorer is selected as the default browser.</span></span>

<span data-ttu-id="8fdd4-357">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-357">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-358">Abilitare i controlli ActiveX o "supporto XMLHTTP nativo" in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-358">Enable either ActiveX Controls or "native XMLHTTP support" in Internet Explorer.</span></span>

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a><span data-ttu-id="8fdd4-359">Il servizio di conferenza Web di Lync Server non può essere recuperato dalla modalità critica</span><span class="sxs-lookup"><span data-stu-id="8fdd4-359">Lync Server Web Conferencing service cannot recover from critical mode</span></span>

<span data-ttu-id="8fdd4-360">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-360">**Issue:**</span></span>

<span data-ttu-id="8fdd4-361">Se la modalità critica viene attivata per l'archiviazione, in caso di errori di sistema, verrà avviata la modalità critica e le conferenze non funzioneranno più per i partecipanti.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-361">If critical mode is turned for archiving, in case of system failures, critical mode will start and the conferences will no longer work for the participants.</span></span> <span data-ttu-id="8fdd4-362">Dopo che l'amministratore ha risolto gli errori di sistema, ad esempio la risoluzione di un problema di database, il servizio di conferenza dati non viene ripristinato automaticamente e l'amministratore deve riavviare manualmente il servizio di conferenza per la ripresa dei servizi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-362">After the administrator fixes the system failures (such as fixing a database issue), the data conferencing service doesn't automatically recover, and the administrator must manually restart the conferencing service for conferencing to resume.</span></span>

<span data-ttu-id="8fdd4-363">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-363">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-364">Un amministratore deve riavviare manualmente il servizio di conferenza telefonica dopo che l'errore di sistema è stato risolto.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-364">An administrator needs to manually restart the conferencing service after the system failure is fixed.</span></span>

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a><span data-ttu-id="8fdd4-365">Il servizio Web Conferencing ignora il proxy HTTP per i server esterni di Office Web App</span><span class="sxs-lookup"><span data-stu-id="8fdd4-365">Web Conferencing service ignores the HTTP proxy for external Office Web App Servers</span></span>

<span data-ttu-id="8fdd4-366">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-366">**Issue:**</span></span>

<span data-ttu-id="8fdd4-367">Se è stato distribuito un server di Office Web Apps esterno al servizio di Web Conferencing (ovvero un server non presente nella rete aziendale interna) in Internet, la rete perimetrale e il servizio di Web Conferencing richiede un proxy HTTP per connettersi a questo, il L'individuazione di Office Web Apps Server non riuscirà.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-367">If you have deployed an Office Web Apps Server external to the Web Conferencing service (that is, a server that is not in the internal corporate network) in the Internet, perimeter network, and the Web Conferencing service requires an HTTP proxy to connect to this, the Office Web Apps Server discovery will fail.</span></span> <span data-ttu-id="8fdd4-368">Il servizio Web Conferencing ignora l'impostazione proxy HTTP, come definito in Generatore di topologia per la configurazione del server Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-368">The Web Conferencing service ignores the HTTP proxy setting, as defined in Topology Builder for Office Web Apps Server setup.</span></span> <span data-ttu-id="8fdd4-369">Di conseguenza, il client Lync non sarà in grado di eseguire la condivisione di Microsoft PowerPoint 2010 con altri partecipanti alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-369">As a result, the Lync client will not be able to do Microsoft PowerPoint 2010 sharing with other participants in the conference.</span></span> <span data-ttu-id="8fdd4-370">Se si sta installando Lync Server locale e si configura anche il server Office Web Apps locale nella rete interna, non è necessaria una configurazione proxy.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-370">If you are installing Lync Server on-premises and also configure Office Web Apps Server on-premises in the internal network, a proxy configuration is not required.</span></span>

<span data-ttu-id="8fdd4-371">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-371">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-372">L'unica soluzione alternativa consiste nel non avere una configurazione di distribuzione che richieda l'uso del proxy HTTP per comunicare con un server esterno di Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-372">The only workaround is to not have a deployment configuration that requires the use of HTTP proxy to communicate with an external Office Web Apps Server.</span></span>

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a><span data-ttu-id="8fdd4-373">L'aggiunta di video a una conferenza del provider di servizi di audioconferenza non è supportata</span><span class="sxs-lookup"><span data-stu-id="8fdd4-373">Adding video to an audio conferencing provider conference is not supported</span></span>

<span data-ttu-id="8fdd4-374">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-374">**Issue:**</span></span>

<span data-ttu-id="8fdd4-375">L'aggiunta di un video non è supportata se l'utente è associato a una conferenza per l'audio di un provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-375">Adding a video is not supported if the user is joined to an audio conferencing provider conference for audio.</span></span>

<span data-ttu-id="8fdd4-376">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-376">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-377">Non c'è soluzione alternativa per questo problema.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-377">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a><span data-ttu-id="8fdd4-378">Le topologie con IPv6 sono abilitate per forzare l'aggiornamento automatico del plug-in Silverlight Web App per garantire la funzionalità di condivisione dello schermo da Lync Web App</span><span class="sxs-lookup"><span data-stu-id="8fdd4-378">Topologies with IPv6 enabled force the Lync Web App Silverlight plug-in auto-update to ensure screen sharing functionality can work from Lync Web App</span></span>

<span data-ttu-id="8fdd4-379">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-379">**Issue:**</span></span>

<span data-ttu-id="8fdd4-380">Quando una topologia è configurata con IPv6 enabled, gli utenti non possono condividere lo schermo dal client Lync Web App se è già installata una versione precedente del plug-in di condivisione dello schermo.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-380">When a topology is configured with IPv6 enabled, users cannot share their screen from the Lync Web App client if an earlier version of the screen-sharing plug-in is already installed.</span></span>

<span data-ttu-id="8fdd4-381">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-381">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-382">Per forzare un aggiornamento alla versione più recente del plug-in di condivisione dello schermo quando si partecipa a una riunione tramite Lync Web App, modificare il valore di **MinSupportedBuildVersion** da "4.0.7457.0" a "4.0.7577.380" in entrambi i file seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-382">To force an update to the most recent version of the screen-sharing plug-in when joining meeting via Lync Web App, modify the value of **MinSupportedBuildVersion** from "4.0.7457.0" to "4.0.7577.380" in both of the following files:</span></span>

  - <span data-ttu-id="8fdd4-383">% ProgramFiles%\\Microsoft Lync Server 15\\Web\\Components\\REACH\\int\\client\\plugins ReachAppShPluginProperties. XML</span><span class="sxs-lookup"><span data-stu-id="8fdd4-383">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Int\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

  - <span data-ttu-id="8fdd4-384">% ProgramFiles%\\Microsoft Lync Server 15\\Web\\Components\\REACH\\ext\\client\\plugins ReachAppShPluginProperties. XML</span><span class="sxs-lookup"><span data-stu-id="8fdd4-384">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Ext\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a><span data-ttu-id="8fdd4-385">VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="8fdd4-385">Enterprise Voice</span></span>

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a><span data-ttu-id="8fdd4-386">In alcuni casi, un client Lync eseguito in un computer configurato per l'uso di IPv4 e IPv6 dual stack potrebbe non supportare funzionalità che si basano sulla subnet IP del computer, ad esempio E911, bypass multimediale, controllo di ammissione alle chiamate e routing basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="8fdd4-386">In some cases, a Lync client running on a computer configured to use IPv4 and IPv6 dual stack might not support capabilities that rely in the IP subnet of the computer such as E911, Media Bypass, Call Admission Control and Location Based Routing</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="8fdd4-387">Le informazioni in questa sezione riguardano gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-387">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="8fdd4-388">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-388">**Issue:**</span></span>

<span data-ttu-id="8fdd4-389">Quando un client Lync viene eseguito in un computer abilitato per lo stack duale IPv4 e IPv6 e in base alla risoluzione DNS del server proxy, il client può usare l'indirizzo IPv6 del computer per l'accesso.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-389">When a Lync client is running on a computer that is enabled for IPv4 and IPv6 dual stack and based on the DNS resolution of the proxy server, the client may use the IPv6 address of the computer to sign in.</span></span> <span data-ttu-id="8fdd4-390">Dopo aver eseguito questa operazione, il client Lync supporterà solo le funzionalità supportate per IPv6, che escludono E911, il bypass multimediale, il controllo dell'ammissione alle chiamate e il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-390">After doing so, the Lync Client will support only the capabilities supported for IPv6, which excludes E911, Media Bypass, Call Admission Control and Location Based Routing.</span></span>

<span data-ttu-id="8fdd4-391">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-391">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-392">Per risolvere il problema, disabilitare il supporto IPv6 nel computer client.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-392">To work around this issue, disable IPv6 support on the client computer.</span></span>

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a><span data-ttu-id="8fdd4-393">Se Enterprise Voice non è configurato per un utente, l'utente dovrà usare il formato E164 per effettuare la chiamata da una conferenza</span><span class="sxs-lookup"><span data-stu-id="8fdd4-393">If Enterprise Voice is not configured for a user, the user will need to use E164 format to dial out from a conference</span></span>

<span data-ttu-id="8fdd4-394">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-394">**Issue:**</span></span>

<span data-ttu-id="8fdd4-395">Se Enterprise Voice non è configurato per un utente, l'utente dovrà usare il formato E164 per effettuare la chiamata in uscita da una conferenza.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-395">If Enterprise Voice is not configured for a user, that user will need to use the E164 format to successfully dial out from a conference.</span></span> <span data-ttu-id="8fdd4-396">Se non si usa il formato E164, l'utente non sarà in grado di effettuare la chiamata fuori dalla conferenza.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-396">If the E164 format is not used, the user will not be able to dial out from the conference.</span></span>

<span data-ttu-id="8fdd4-397">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-397">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-398">Per risolvere il problema, gli utenti che non sono abilitati per VoIP aziendale devono eseguire la chiamata da una conferenza usando i numeri nel formato E164.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-398">To work around this issue, users who are not enabled for Enterprise Voice should dial out from a conference by using numbers in the E164 format.</span></span>

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a><span data-ttu-id="8fdd4-399">Icone di presenza</span><span class="sxs-lookup"><span data-stu-id="8fdd4-399">Presence</span></span>

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a><span data-ttu-id="8fdd4-400">Se un utente ha selezionato "blocca tutti gli inviti e le comunicazioni" mentre l'archivio contatti unificato è attivato per l'utente, lo stato presenza non viene rifiutato quando deve essere</span><span class="sxs-lookup"><span data-stu-id="8fdd4-400">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be</span></span>

<span data-ttu-id="8fdd4-401">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-401">**Issue:**</span></span>

<span data-ttu-id="8fdd4-402">Se un utente ha selezionato "blocca tutti gli inviti e le comunicazioni" mentre l'archivio contatti unificato è attivato per l'utente, lo stato presenza non viene rifiutato quando necessario.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-402">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be.</span></span>

<span data-ttu-id="8fdd4-403">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-403">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-404">Per risolvere il problema, è possibile disattivare l'archivio contatti unificato per l'utente.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-404">To work around this issue, you can turn off the unified contact store for the user.</span></span> <span data-ttu-id="8fdd4-405">A questo scopo, eseguire i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-405">To do so, run the following cmdlets:</span></span>

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

<span data-ttu-id="8fdd4-406">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-406">For example:</span></span>

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a><span data-ttu-id="8fdd4-407">Gli utenti di Office Communications Server 2007 R2 ospitati in locale non sono in grado di visualizzare lo stato presenza degli utenti di Skype for business online nelle distribuzioni ibride-Hybrid</span><span class="sxs-lookup"><span data-stu-id="8fdd4-407">Office Communications Server 2007 R2 users homed on-premises are not able to see the Presence status of Skype for Business Online users in hybrid deployments - Hybrid</span></span>

<span data-ttu-id="8fdd4-408">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-408">**Issue:**</span></span>

<span data-ttu-id="8fdd4-409">Il problema potrebbe verificarsi in una distribuzione ibrida quando si usa un amministratore di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-409">The issue may occur in a hybrid deployment when you are using a Lync Server 2013 Director.</span></span>

<span data-ttu-id="8fdd4-410">Lo stato presenza per gli utenti ospitati in Skype for business online viene visualizzato come presenza sconosciuta per gli utenti locali.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-410">Presence status for users homed to Skype for Business Online is displayed as Presence Unknown for on-premises users.</span></span> <span data-ttu-id="8fdd4-411">Inoltre, gli utenti ospitati in Skype for business online non sono in grado di visualizzare lo stato presenza per gli utenti locali di Office Communications Server R2.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-411">Also, users homed to Skype for Business Online are not able to see presence status for Office Communications Server R2 on-premises users.</span></span>

<span data-ttu-id="8fdd4-412">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-412">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-413">Per aggirare parzialmente il problema, cambiare il server principale (msRTCSIP-presencehomeserver) degli utenti di Skype for business online in un pool locale di Lync Server 2013 invece che nel Lync Server 2013 Director.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-413">To partially work around this issue, change the Home Server (msrtcsip-presencehomeserver) of the Skype for Business Online users to point to a Lync Server 2013 on-premises pool instead of the Lync Server 2013 Director.</span></span> <span data-ttu-id="8fdd4-414">È possibile modificare questa impostazione nel server front-end locale.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-414">You can modify this setting on the on-premises Front End Server.</span></span>

<span data-ttu-id="8fdd4-415">Questa soluzione alternativa visualizzerà correttamente lo stato presenza degli utenti ospitati in Office Communications Server 2007 R2 per gli utenti di Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-415">This workaround will correctly display the Presence status of users homed to Office Communications Server 2007 R2 to Skype for Business Online users.</span></span>

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a><span data-ttu-id="8fdd4-416">Response Group Application, Call Park Application e pick-up delle chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="8fdd4-416">Response Group application, Call Park application, and Group Call Pickup</span></span>

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a><span data-ttu-id="8fdd4-417">Un chiamante potrebbe sentire un secondo di musica in attesa durante l'istituzione di una chiamata con il gruppo di recupero</span><span class="sxs-lookup"><span data-stu-id="8fdd4-417">A caller might hear one second of music-on-hold during the establishment of a call with the retrieving party</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="8fdd4-418">Le informazioni in questa sezione riguardano gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-418">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="8fdd4-419">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-419">**Issue:**</span></span>

<span data-ttu-id="8fdd4-420">Quando viene recuperata una chiamata tramite raccolta chiamate di gruppo, il chiamante potrebbe sentire un secondo di musica in attesa durante l'istituzione della chiamata con la parte del recuperatore.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-420">When a call is retrieved via Group Call Pickup, the caller might hear one second of music-on-hold during the establishment of the call with the retriever party.</span></span>

<span data-ttu-id="8fdd4-421">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-421">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-422">Non c'è soluzione alternativa per questo problema.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-422">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a><span data-ttu-id="8fdd4-423">Un agente del gruppo di risposte può accedere e disconnettersi tramite una console di agente di Lync Server 2010 ai gruppi di agenti formali di Lync Server 2010 solo</span><span class="sxs-lookup"><span data-stu-id="8fdd4-423">A Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only</span></span>

<span data-ttu-id="8fdd4-424">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-424">**Issue:**</span></span>

<span data-ttu-id="8fdd4-425">Un agente del gruppo di risposte di Lync Server 2013 può accedere e disconnettersi tramite una console di agente di Lync Server 2010 solo ai gruppi di agenti formali di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-425">A Lync Server 2013 Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only.</span></span> <span data-ttu-id="8fdd4-426">Nella console agente di Lync Server 2010 gli utenti possono visualizzare solo il gruppo di risposte di Lync Server 2010 a cui appartengono.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-426">In the Lync Server 2010 Agent Console, users can see only the Lync Server 2010 Response Group that they belong to.</span></span> <span data-ttu-id="8fdd4-427">Non possono vedere i gruppi di risposte di Lync Server 2013 a cui appartengono.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-427">They cannot see any of the Lync Server 2013 Response Groups that they belong to.</span></span>

<span data-ttu-id="8fdd4-428">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-428">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-429">Se l'agente di Response Group è un utente di Lync Server 2013 e fa parte di un gruppo di agenti formali di Lync Server 2013, l'utente deve accedere alla console di agente di Lync Server 2013 direttamente tramite un collegamento Web in un browser per accedere e disconnettersi dai gruppi di agenti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-429">If the Response Group agent is a Lync Server 2013 user, and part of a Lync Server 2013 formal Agent Group, the user must access the Lync Server 2013 Agent Console directly via a web link in a browser to sign in to and sign out from Lync Server 2013 Agent Groups.</span></span>

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a><span data-ttu-id="8fdd4-430">Un agente del gruppo di risposte di Lync Server 2010 non può inserire chiamate per conto di un gruppo di risposte di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8fdd4-430">A Lync Server 2010 Response Group agent cannot place calls on behalf of a Lync Server 2013 Response Group</span></span>

<span data-ttu-id="8fdd4-431">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-431">**Issue:**</span></span>

<span data-ttu-id="8fdd4-432">Un utente di Lync Server 2010 che è un agente di un gruppo di risposte di Lync Server 2013 non è in grado di effettuare una chiamata per conto del gruppo di risposta.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-432">A Lync Server 2010 user who is an Agent of a Lync Server 2013 Response Group is not able to place a call on behalf of the Response Group.</span></span> <span data-ttu-id="8fdd4-433">Il gruppo di risposte di Lync Server 2013 non sarà disponibile nel client Lync per effettuare una chiamata.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-433">The Lync Server 2013 Response Group will not be available in the Lync Client to place a call.</span></span>

<span data-ttu-id="8fdd4-434">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-434">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-435">Per risolvere il problema, è necessario spostare l'utente di Lync Server 2010 in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-435">To work around this issue, you must move the Lync Server 2010 user to Lync Server 2013.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a><span data-ttu-id="8fdd4-436">La rimozione di un gruppo di risposte da Lync Server 2010 dopo la migrazione a Lync Server 2013 impedirà al gruppo di risposte di accettare le chiamate in arrivo</span><span class="sxs-lookup"><span data-stu-id="8fdd4-436">Removing a Response Group from Lync Server 2010 after it has been migrated to Lync Server 2013 will prevent the Response Group from accepting any incoming calls</span></span>

<span data-ttu-id="8fdd4-437">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-437">**Issue:**</span></span>

<span data-ttu-id="8fdd4-438">Se un gruppo di risposte di cui è stata eseguita la migrazione da Lync Server 2010 a Lync Server 2013 viene rimosso da Lync Server 2010 tramite il pannello di controllo di Lync Server o Lync Server Management Shell, il gruppo di risposte in Lync Server 2013 smetterà di ricevere le chiamate in arrivo.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-438">If a Response Group that has been migrated from Lync Server 2010 to Lync Server 2013 is removed from Lync Server 2010 through the Lync Server Control Panel or the Lync Server Management Shell, the Response Group in Lync Server 2013 will stop receiving any incoming calls.</span></span>

<span data-ttu-id="8fdd4-439">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-439">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-440">Per risolvere il problema, non rimuovere i gruppi di risposta da Lync Server 2010 migrati da Lync Server 2010 a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-440">To work around this issue, do not remove any Response Groups from Lync Server 2010 that have been migrated from Lync Server 2010 to Lync Server 2013.</span></span>

<span data-ttu-id="8fdd4-441">Se il gruppo di risposte è già stato rimosso, è necessario ridistribuirlo in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-441">If the Response Group has already been removed, you should redeploy it in Lync Server 2013.</span></span>

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a><span data-ttu-id="8fdd4-442">Quando un nuovo flusso di lavoro gestito viene impostato su inattivo quando viene creato, la distribuzione del flusso di lavoro avrà esito negativo</span><span class="sxs-lookup"><span data-stu-id="8fdd4-442">When a new managed workflow is set to inactive when created, deployment of the workflow will fail</span></span>

<span data-ttu-id="8fdd4-443">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-443">**Issue:**</span></span>

<span data-ttu-id="8fdd4-444">Quando un nuovo flusso di lavoro gestito viene impostato su inattivo al momento della creazione, la distribuzione del flusso di lavoro avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-444">When a new managed workflow is set to inactive when created, deployment of the workflow will fail.</span></span> <span data-ttu-id="8fdd4-445">Questo problema si verifica quando il flusso di lavoro è impostato su inattivo quando viene creato, ma non influisce su un flusso di lavoro modificato per impostarlo su inattivo dopo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-445">This issue is encountered when the workflow is set to inactive when created, but does not affect a workflow that is edited to set it to inactive after is has been deployed.</span></span>

<span data-ttu-id="8fdd4-446">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-446">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-447">Quando si crea e si distribuisce un flusso di lavoro, è possibile impostare il flusso di lavoro come attivo e quindi distribuirlo.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-447">When creating and deploying a workflow, set the workflow as active and then deploy it.</span></span> <span data-ttu-id="8fdd4-448">Dopo che il flusso di lavoro è stato distribuito correttamente, il flusso di lavoro può essere modificato e impostato su inattivo.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-448">After the workflow is successfully deployed, the workflow can be edited and set to inactive.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a><span data-ttu-id="8fdd4-449">La rimozione di un gruppo di risposte dal pool di proprietari impedirà al gruppo di risposte del pool di backup di accettare le chiamate in arrivo durante il failover se il gruppo di risposte è stato importato nel pool di backup</span><span class="sxs-lookup"><span data-stu-id="8fdd4-449">Removing a Response Group from the Owner pool will prevent the Response Group of the Backup pool from accepting any incoming calls during failover if the Response Group has been imported to the Backup pool</span></span>

<span data-ttu-id="8fdd4-450">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-450">**Issue:**</span></span>

<span data-ttu-id="8fdd4-451">Se un gruppo di risposte di proprietà del pool principale è stato importato nel pool di backup senza sovrascrivere il proprietario e il gruppo di risposte viene rimosso dal pool di proprietari, il gruppo di risposte nel pool di backup non accetterà le chiamate in arrivo durante il failover.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-451">If a Response Group that is owned by the primary pool has been imported to the backup pool without overwriting the owner, and the Response Group is removed from the owner pool, the Response Group in the Backup pool will not accept any incoming calls during failover.</span></span>

<span data-ttu-id="8fdd4-452">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-452">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-453">Sarà necessario ridistribuire il gruppo di risposte nel pool principale.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-453">You will need to redeploy the Response Group in the Primary pool.</span></span> <span data-ttu-id="8fdd4-454">Sarà quindi necessario esportare la configurazione del gruppo di risposte dal pool principale e importarla di nuovo nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-454">You will then need to export the Response Group configuration from the Primary pool and import it to the Backup pool again.</span></span>

<span data-ttu-id="8fdd4-455">È anche possibile ricreare il gruppo di risposte nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-455">You can also recreate the Response Group in the Backup pool.</span></span> <span data-ttu-id="8fdd4-456">In questo caso, il pool di backup sarà il pool di proprietari del gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-456">In this case, the Backup pool will be the owner pool of the Response Group.</span></span>

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a><span data-ttu-id="8fdd4-457">Una chiamata parcheggiata non può essere recuperata dall'applicazione Call Park se la richiesta di recupero viene eseguita per conto di un gruppo di risposte</span><span class="sxs-lookup"><span data-stu-id="8fdd4-457">A parked call can't be retrieved from the Call Park application if the retrieve request is done on behalf of a Response Group</span></span>

<span data-ttu-id="8fdd4-458">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-458">**Issue:**</span></span>

<span data-ttu-id="8fdd4-459">Quando le condizioni seguenti sono vere, una richiesta di recupero per una chiamata parcheggiata avrà esito negativo:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-459">When the following conditions are true, a retrieve request for a parked call will fail:</span></span>

  - <span data-ttu-id="8fdd4-460">Un agente fa parte di un gruppo di risposte Anonimo</span><span class="sxs-lookup"><span data-stu-id="8fdd4-460">An agent is part of an anonymous Response Group</span></span>

  - <span data-ttu-id="8fdd4-461">L'agente tenta di recuperare una chiamata parcheggiata dall'applicazione Call Park tramite il gruppo di risposte Anonimo</span><span class="sxs-lookup"><span data-stu-id="8fdd4-461">The agent attempts to retrieve a parked call from the Call Park application through the anonymous Response Group</span></span>

  - <span data-ttu-id="8fdd4-462">L'agente tenta di recuperare la chiamata componendo il numero dell'orbita tramite l'opzione chiama per conto o tramite la stessa opzione nel client dell'operatore di Lync</span><span class="sxs-lookup"><span data-stu-id="8fdd4-462">The agent attempts to retrieve the call by dialing the orbit number through the Call On Behalf option or through the same option in the Lync attendant client</span></span>

<span data-ttu-id="8fdd4-463">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-463">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-464">Non esistono soluzioni alternative per questo problema.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-464">There are no workarounds for this issue.</span></span> <span data-ttu-id="8fdd4-465">La chiamata parcheggiata deve essere recuperata senza farlo per conto di un gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-465">The parked call should be retrieved without doing so on behalf of a Response Group.</span></span>

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a><span data-ttu-id="8fdd4-466">Pannello di controllo, Generatore di topologie e Strumento di pianificazione di Lync Server</span><span class="sxs-lookup"><span data-stu-id="8fdd4-466">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

<div>

## <a name="planning-tool-limitations"></a><span data-ttu-id="8fdd4-467">Limitazioni dello strumento di pianificazione</span><span class="sxs-lookup"><span data-stu-id="8fdd4-467">Planning Tool Limitations</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="8fdd4-468">Le informazioni in questa sezione riguardano gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-468">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="8fdd4-469">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-469">**Issue:**</span></span>

<span data-ttu-id="8fdd4-470">Lo strumento di pianificazione presenta le limitazioni seguenti per la pianificazione della distribuzione:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-470">The Planning Tool has the following limitations when planning for your deployment:</span></span>

  - <span data-ttu-id="8fdd4-471">È supportato un massimo di 10 siti centrali</span><span class="sxs-lookup"><span data-stu-id="8fdd4-471">There is a maximum of 10 central sites supported</span></span>

  - <span data-ttu-id="8fdd4-472">Ogni sito centrale può avere un massimo di 14 siti di succursale</span><span class="sxs-lookup"><span data-stu-id="8fdd4-472">Each central site can have a maximum of 14 branch sites</span></span>

  - <span data-ttu-id="8fdd4-473">Ogni sito centrale può avere un massimo di 240.000 utenti</span><span class="sxs-lookup"><span data-stu-id="8fdd4-473">Each central site can have a maximum of 240,000 users</span></span>

<span data-ttu-id="8fdd4-474">Inoltre, quando si calcola la topologia consigliata, lo strumento di pianificazione non include i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-474">In addition, the Planning Tool does not include values for the following when calculating the recommended topology:</span></span>

  - <span data-ttu-id="8fdd4-475">Numero di utenti ospitati online</span><span class="sxs-lookup"><span data-stu-id="8fdd4-475">The number of users that are homed online</span></span>

  - <span data-ttu-id="8fdd4-476">Percentuale di utenti abilitati per la Federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="8fdd4-476">The percentage of users that are enabled for XMPP federation</span></span>

  - <span data-ttu-id="8fdd4-477">Percentuale di utenti che usano Lync Web App</span><span class="sxs-lookup"><span data-stu-id="8fdd4-477">Percentage of users that are using Lync Web App</span></span>

<span data-ttu-id="8fdd4-478">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-478">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-479">Per questi problemi non è disponibile alcuna soluzione alternativa.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-479">There is no workaround for these issues.</span></span> <span data-ttu-id="8fdd4-480">Per altre informazioni sullo strumento di pianificazione, vedere [progettazione della topologia di Lync Server 2013 tramite lo strumento pianificazione](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span><span class="sxs-lookup"><span data-stu-id="8fdd4-480">For more information about the Planning Tool, see [Designing the topology for Lync Server 2013 by using the Planning Tool](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span></span>

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a><span data-ttu-id="8fdd4-481">Lo strumento di pianificazione potrebbe non usare gli indirizzi IP definiti in precedenza per la rete Edge durante l'aggiornamento delle opzioni</span><span class="sxs-lookup"><span data-stu-id="8fdd4-481">Planning Tool may not use previously defined IP addresses for the Edge network when updating options</span></span>

<span data-ttu-id="8fdd4-482">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-482">**Issue:**</span></span>

<span data-ttu-id="8fdd4-483">Dopo aver completato la progettazione usando lo strumento di pianificazione, se si apportano modifiche alle opzioni di rete Edge, gli indirizzi IP aggiuntivi potrebbero essere aggiunti alla struttura anziché aggiornare gli indirizzi IP esistenti.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-483">After you complete your design using the Planning Tool, if you make changes to the Edge Network options, additional IP addresses may be added to the design instead of updating the existing IP addresses.</span></span> <span data-ttu-id="8fdd4-484">Questo problema può verificarsi quando si visualizzano i dettagli del diagramma reticolare, selezionare **fare clic qui per aggiornare le opzioni**e quindi nella finestra di dialogo Opzioni di configurazione selezionare rete Edge selezionare si **vogliono usare gli stessi FQDN e gli stessi indirizzi IP, ma le diverse porte per i servizi Edge nel server perimetrale**.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-484">This can occur when you are viewing the details of the Edge Network Diagram, select **Click here to update your options**, and then, on the Configuration Options dialog, you select Edge Network select **I want to use the same FQDNs and IP addresses, but different ports for the edge services on my Edge Server**.</span></span> <span data-ttu-id="8fdd4-485">L'applicazione di eventuali modifiche può causare l'aggiunta di nuovi indirizzi IP e Edge Server alla struttura.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-485">Applying any changes may result in new IP addresses and Edge servers being added to the design.</span></span>

<span data-ttu-id="8fdd4-486">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-486">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-487">Al momento non esiste alcuna soluzione alternativa per questo problema.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-487">There is no workaround for this issue at this time.</span></span>

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a><span data-ttu-id="8fdd4-488">Nel pannello di controllo di Lync Server il comando "porta tutti gli utenti al pool" potrebbe non funzionare come previsto</span><span class="sxs-lookup"><span data-stu-id="8fdd4-488">In Lync Server Control Panel, "Move all users to pool" may not work as expected</span></span>

<span data-ttu-id="8fdd4-489">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-489">**Issue:**</span></span>

<span data-ttu-id="8fdd4-490">Quando si usa il pannello di controllo di Lync Server per trasferire tutti gli utenti da un pool a un altro in un ambiente di Active Directory complesso, ad esempio uno con più controller di dominio e domini padre/figlio, potrebbe essere restituito un messaggio di errore che indica che "l'utente specificato non è un utente legacy, USA invece il cmdlet Move-CsUser".</span><span class="sxs-lookup"><span data-stu-id="8fdd4-490">When using the Lync Server Control Panel to move all users from one pool to another pool in a complex Active Directory environment, such as one with multiple Domain Controllers and parent/child domains, an error message may be returned that states, “Specified user is not a legacy user, use Move-CsUser cmdlet instead.”</span></span> <span data-ttu-id="8fdd4-491">Questo è il risultato di tempi di replica più lunghi in ambienti Active Directory complessi.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-491">This is a result of longer replication times in complex Active Directory environments.</span></span>

<span data-ttu-id="8fdd4-492">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-492">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-493">Per risolvere il problema, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-493">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="8fdd4-494">Usare i filtri nel pannello di controllo di Lync Server per cercare utenti legacy, selezionare questi utenti e quindi usare il **comando Sposta utenti selezionati in pool** invece di **Sposta tutti gli utenti in pool**.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-494">Use filters in the Lync Server Control Panel to search for legacy users, select those users, and then use the **Move selected users to pool command** instead of **Move all users to pool**.</span></span>

  - <span data-ttu-id="8fdd4-495">Usare Lync Server Management Shell per trasferire gli utenti legacy in batch usando i cmdlet di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-495">Use the Lync Server Management Shell to move legacy users in batches by using Lync Server cmdlets.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a><span data-ttu-id="8fdd4-496">Il pannello di controllo di Lync Server smette di funzionare in un ambiente VMware dopo che il plug-in del browser Microsoft Silverlight è stato aggiornato alla versione 5</span><span class="sxs-lookup"><span data-stu-id="8fdd4-496">The Lync Server Control Panel stops working in a VMware environment after the Microsoft Silverlight browser plug-in is updated to version 5</span></span>

<span data-ttu-id="8fdd4-497">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-497">**Issue:**</span></span>

<span data-ttu-id="8fdd4-498">Se si usa il pannello di controllo di Lync Server in un ambiente VMware, il pannello di controllo di Lync Server potrebbe smettere di funzionare dopo l'aggiornamento di Silverlight alla versione 5.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-498">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Silverlight to version 5.</span></span>

<span data-ttu-id="8fdd4-499">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-499">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-500">Per risolvere il problema, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-500">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="8fdd4-501">Disinstallare Silverlight 5 e quindi installare Silverlight 4 da [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0).</span><span class="sxs-lookup"><span data-stu-id="8fdd4-501">Uninstall Silverlight 5, and then install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0).</span></span>

  - <span data-ttu-id="8fdd4-502">Aprire il pannello di controllo di Lync Server da un computer che non è un computer virtuale VMware.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-502">Open the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="8fdd4-503">Per aprire il pannello di controllo di Lync Server da un computer remoto, installare gli strumenti di amministrazione di Lync Server nel computer e quindi avviare il pannello di controllo di Lync Server dal menu **Start** di Windows.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-503">To open the Lync Server Control Panel from a remote computer, install Lync Server Administration tools on the computer, and then start the Lync Server Control Panel from the Windows **Start** menu.</span></span>
    
    <span data-ttu-id="8fdd4-504">È anche possibile aprire il pannello di controllo di Lync Server immettendo l'URL in un Web browser.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-504">You can also open the Lync Server Control Panel by entering the URL in a web browser.</span></span> <span data-ttu-id="8fdd4-505">L'URL sarà\<simile a FQDN\_\_\>del pool di frontend https:///CSCP.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-505">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a><span data-ttu-id="8fdd4-506">Un amministratore non può eseguire il cmdlet Uninstall-csMirrorDB dopo aver rimosso il database di mirroring in Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="8fdd4-506">An administrator cannot run the Uninstall-csMirrorDB cmdlet after removing the mirroring database in Topology Builder</span></span>

<span data-ttu-id="8fdd4-507">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-507">**Issue:**</span></span>

<span data-ttu-id="8fdd4-508">Quando un amministratore disabilita un database di mirroring in Generatore di topologie e quindi Elimina il database di mirroring in Generatore di topologia, viene visualizzato un messaggio nell'elenco da fare per l'amministratore per eseguire il cmdlet **Uninstall-csMirrorDatabase** per rimuovere il mirroring da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-508">When an administrator disables a mirroring database in Topology Builder, and then deletes the mirroring database in Topology Builder, a message is displayed in the To do list for the administrator to run the **Uninstall-csMirrorDatabase** cmdlet to remove mirroring from SQL Server.</span></span> <span data-ttu-id="8fdd4-509">Quando l'amministratore tenta di eseguire il cmdlet, non riesce.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-509">When the administrator attempts to run the cmdlet, it fails.</span></span>

<span data-ttu-id="8fdd4-510">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-510">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-511">Per rimuovere il mirroring SQL di un pool in Generatore di topologia, è necessario prima di tutto usare un cmdlet per rimuovere il mirror in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-511">To remove SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server.</span></span> <span data-ttu-id="8fdd4-512">Puoi quindi usare generatore di topologia per rimuovere il mirror dalla topologia.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-512">You can then use Topology Builder to remove the mirror from the topology.</span></span> <span data-ttu-id="8fdd4-513">Per rimuovere il mirror in SQL Server, usare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-513">To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="8fdd4-514">Ad esempio, per rimuovere il mirroring e rilasciare i database per i database degli utenti, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-514">For example, to remove mirroring and drop the databases for the user databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="8fdd4-515">Il parametro *DropExistingDatabasesOnMirror* fa sì che i database interessati vengano eliminati dallo specchio.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-515">The *DropExistingDatabasesOnMirror* parameter causes the affected databases to be deleted from the mirror.</span></span> <span data-ttu-id="8fdd4-516">Quindi, per rimuovere il mirror dalla topologia, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-516">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="8fdd4-517">In Generatore di topologie fare clic con il pulsante destro del mouse sul pool e scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-517">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="8fdd4-518">Deselezionare **Abilita mirroring di SQL Store** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-518">Clear **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="8fdd4-519">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-519">Publish the topology.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="8fdd4-520">Ogni volta che si apporta una modifica a una relazione di mirroring del database back-end, è necessario riavviare tutti i server front-end nel pool.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-520">Whenever you make a change to a back-end database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span>



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a><span data-ttu-id="8fdd4-521">Gli errori di convalida vengono restituiti in Generatore di topologia quando un amministratore tenta di rimuovere una distribuzione con un pool Front-end che include un archivio dei testimoni associato</span><span class="sxs-lookup"><span data-stu-id="8fdd4-521">Validation errors are returned in Topology Builder when an administrator attempts to remove a deployment with a Front End pool that has an associated witness store</span></span>

<span data-ttu-id="8fdd4-522">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-522">**Issue:**</span></span>

<span data-ttu-id="8fdd4-523">Se un amministratore tenta di usare il comando **Rimuovi distribuzione** in Generatore di topologia per rimuovere una distribuzione che include un pool Front-end con un archivio dei testimoni associato, viene visualizzato un errore di convalida in Generatore di topologia e l'azione non procederà.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-523">If an administrator attempts to use the **Remove Deployment** command in Topology Builder to remove a deployment that includes a Front End pool with an associated witness store, a validation error is displayed in Topology Builder and the action will not proceed.</span></span>

<span data-ttu-id="8fdd4-524">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-524">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-525">Per risolvere il problema, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-525">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="8fdd4-526">Rimuovere l'archivio dei testimoni prima di provare a rimuovere la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-526">Remove the witness store before attempting to remove the deployment.</span></span>

  - <span data-ttu-id="8fdd4-527">Aggiungere un archivio dei testimoni per il pool Front-end e quindi rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-527">Add a witness store for the Front End pool and then remove it.</span></span>

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a><span data-ttu-id="8fdd4-528">Le informazioni di distribuzione del server di chat persistenti non sono coerenti tra lo strumento pianificazione e il generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="8fdd4-528">Persistent Chat Server deployment information is inconsistent between the Planning Tool and Topology Builder</span></span>

<span data-ttu-id="8fdd4-529">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-529">**Issue:**</span></span>

<span data-ttu-id="8fdd4-530">Quando Lync Server 2013, lo strumento di pianificazione restituisce il diagramma della topologia del sito per una distribuzione del server di chat persistente con il ripristino di emergenza abilitato, il diagramma della topologia del sito include più siti (fisici), con i server di chat persistenti assegnati equamente a ogni sito.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-530">When the Lync Server 2013, Planning Tool outputs the site topology diagram for a Persistent Chat Server deployment with disaster recovery enabled, the site topology diagram includes multiple (physical) sites, with evenly assigned Persistent Chat Servers at each site.</span></span> <span data-ttu-id="8fdd4-531">In Generatore di topologie tutti i server di chat persistenti sono rappresentati come appartenenti a un singolo sito (logico) e sono elencati nello stesso nodo del pool di server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-531">In Topology Builder, all Persistent Chat Servers are represented as belonging to a single (logical) site, and are listed under the same Persistent Chat Server pool node.</span></span>

<span data-ttu-id="8fdd4-532">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-532">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-533">Al momento non è disponibile una soluzione alternativa per questo problema.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-533">Currently, we do not have a workaround for this issue.</span></span> <span data-ttu-id="8fdd4-534">L'utente dovrebbe analizzare l'output dello strumento di pianificazione per la distribuzione del server di chat persistente e modificare il piano in base alle specifiche esigenze.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-534">The user should analyze the output of the Planning Tool for the Persistent Chat Server deployment, and modify the plan to meet their specific needs.</span></span>

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a><span data-ttu-id="8fdd4-535">Localizzazione</span><span class="sxs-lookup"><span data-stu-id="8fdd4-535">Localization</span></span>

<div>

## <a name="monitoring"></a><span data-ttu-id="8fdd4-536">Monitoraggio</span><span class="sxs-lookup"><span data-stu-id="8fdd4-536">Monitoring</span></span>

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a><span data-ttu-id="8fdd4-537">La procedura guidata Distribuisci report di monitoraggio consente di visualizzare caratteri non corretti in determinate circostanze quando si usa la versione asiatica di Lync Server</span><span class="sxs-lookup"><span data-stu-id="8fdd4-537">The Deploy Monitoring Reports wizard displays incorrect characters under certain circumstances when using the East Asian version of Lync Server</span></span>

<span data-ttu-id="8fdd4-538">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-538">**Issue:**</span></span>

<span data-ttu-id="8fdd4-539">Quando si usa una versione dell'Asia orientale di Lync Server 2013, ad esempio cinese (semplificato), cinese (tradizionale), giapponese o coreano, in un sistema operativo in cui le impostazioni locali del sistema non sono impostate su una lingua dell'Asia orientale, la procedura guidata Distribuisci rapporti di monitoraggio verrà visualizzare i punti interrogativi o altri caratteri anziché i messaggi localizzati.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-539">When using an East Asian version of Lync Server 2013—for example, Chinese (Simplified), Chinese (Traditional), Japanese, or Korean—on an operating system that has the system locale not set to an East Asian language, the Deploy Monitoring Reports wizard will display question marks or other characters instead of localized messages.</span></span>

<span data-ttu-id="8fdd4-540">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-540">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-541">Per risolvere il problema, impostare le impostazioni locali per il sistema operativo e Lync Server 2013 sulla stessa lingua, che visualizzerà tutti i messaggi in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-541">To correct this issue, set the locale for the operating system and Lync Server 2013 to the same language, which will display all messages correctly.</span></span>

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="8fdd4-542">Pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="8fdd4-542">Lync Server Control Panel</span></span>

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a><span data-ttu-id="8fdd4-543">In alcuni casi, il primo elemento nella barra di spostamento superiore in una pagina del pannello di controllo di Lync Server scompare quando si fa clic sull'ultimo elemento nella barra di spostamento superiore</span><span class="sxs-lookup"><span data-stu-id="8fdd4-543">In certain cases, the first item in the top navigation bar on a page of Lync Server Control Panel disappears when the last item in the top navigation bar is clicked</span></span>

<span data-ttu-id="8fdd4-544">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-544">**Issue:**</span></span>

<span data-ttu-id="8fdd4-545">Esistono tre casi noti in cui fare clic sull'ultimo elemento nella barra di spostamento superiore in una pagina del pannello di controllo di Lync Server causerà la scomparsa del primo elemento nella barra di spostamento superiore:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-545">There are three known cases where clicking the last item in the top navigation bar on a page of the Lync Server Control Panel will cause the first item in the top navigation bar to disappear:</span></span>

  - <span data-ttu-id="8fdd4-546">Nel francese della versione, nella pagina "Féderation et accès externe", l'elemento "Stratégie accès externe" scomparirà quando si fa clic su "Partenaires fédérés XMPP".</span><span class="sxs-lookup"><span data-stu-id="8fdd4-546">In the French of version, on the page "Féderation et accès externe," the item "Stratégie d'accès externe" will disappear when "Partenaires fédérés XMPP" is clicked.</span></span>

  - <span data-ttu-id="8fdd4-547">Nella pagina "clients" della versione tedesca l'elemento "Clientversionskonfiguration" scompare quando viene fatto clic su "Pushbenachrichtigungskonfiguration".</span><span class="sxs-lookup"><span data-stu-id="8fdd4-547">In the German version, on the "Clients" page, the item "Clientversionskonfiguration" disappears when "Pushbenachrichtigungskonfiguration" is clicked.</span></span>

  - <span data-ttu-id="8fdd4-548">Nella pagina "Конфигурация сети" della versione russa l'elemento "Глобально" scompare quando viene fatto clic su "Маршрут региона".</span><span class="sxs-lookup"><span data-stu-id="8fdd4-548">In the Russian version, on "Конфигурация сети" page, the item "Глобально" disappears when "Маршрут региона" is clicked.</span></span>

<span data-ttu-id="8fdd4-549">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-549">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-550">Per risolvere il problema, aggiornare la pagina del pannello di controllo di Lync Server nel browser.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-550">To work around this issue, refresh the page of the Lync Server Control Panel in your browser.</span></span> <span data-ttu-id="8fdd4-551">La pagina verrà caricata nel browser con tutti gli elementi nella barra di spostamento superiore visualizzata.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-551">The page will load in the browser with all of the items in the top navigation bar displayed.</span></span>

</div>

</div>

<div>

## <a name="address-book"></a><span data-ttu-id="8fdd4-552">Rubrica</span><span class="sxs-lookup"><span data-stu-id="8fdd4-552">Address Book</span></span>

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a><span data-ttu-id="8fdd4-553">L'indicizzazione nella Rubrica non funziona come previsto in alcune lingue</span><span class="sxs-lookup"><span data-stu-id="8fdd4-553">Indexing in the Address Book does not work as expected in some languages</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="8fdd4-554">Le informazioni in questa sezione riguardano gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-554">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="8fdd4-555">Se le proprietà di un utente contengono un campo indicizzato e tale campo contiene solo caratteri che non è possibile indicizzare, l'utente non verrà visualizzato nelle ricerche eseguite nella rubrica.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-555">If a user’s properties contain an indexed field, and that field contains only characters that cannot be indexed, then the user will not appear in searches performed in the Address Book.</span></span>

<span data-ttu-id="8fdd4-556">Non è possibile indicizzare i caratteri e le impostazioni locali seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-556">The following characters and locales cannot be indexed:</span></span>

  - <span data-ttu-id="8fdd4-557">Caratteri cirillici maiuscoli, greci e armeni</span><span class="sxs-lookup"><span data-stu-id="8fdd4-557">Upper-case Cyrillic, Greek, and Armenian characters</span></span>

  - <span data-ttu-id="8fdd4-558">Caratteri accentati in maiuscolo</span><span class="sxs-lookup"><span data-stu-id="8fdd4-558">Upper-case accented characters</span></span>

  - <span data-ttu-id="8fdd4-559">Tailandese</span><span class="sxs-lookup"><span data-stu-id="8fdd4-559">Thai</span></span>

  - <span data-ttu-id="8fdd4-560">Lao</span><span class="sxs-lookup"><span data-stu-id="8fdd4-560">Lao</span></span>

  - <span data-ttu-id="8fdd4-561">Myanmar</span><span class="sxs-lookup"><span data-stu-id="8fdd4-561">Myanmar</span></span>

  - <span data-ttu-id="8fdd4-562">Devanagari</span><span class="sxs-lookup"><span data-stu-id="8fdd4-562">Devanagari</span></span>

  - <span data-ttu-id="8fdd4-563">Etiope</span><span class="sxs-lookup"><span data-stu-id="8fdd4-563">Ethiopic</span></span>

  - <span data-ttu-id="8fdd4-564">Tibetano</span><span class="sxs-lookup"><span data-stu-id="8fdd4-564">Tibetan</span></span>

  - <span data-ttu-id="8fdd4-565">Bengali</span><span class="sxs-lookup"><span data-stu-id="8fdd4-565">Bengali</span></span>

  - <span data-ttu-id="8fdd4-566">Gujarati</span><span class="sxs-lookup"><span data-stu-id="8fdd4-566">Gujarati</span></span>

  - <span data-ttu-id="8fdd4-567">Telugu</span><span class="sxs-lookup"><span data-stu-id="8fdd4-567">Telugu</span></span>

  - <span data-ttu-id="8fdd4-568">Tutti gli altri alfabeti indiani</span><span class="sxs-lookup"><span data-stu-id="8fdd4-568">All other Indic scripts</span></span>

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a><span data-ttu-id="8fdd4-569">Lync Web App, Web Scheduler e Web Components</span><span class="sxs-lookup"><span data-stu-id="8fdd4-569">Lync Web App, Web Scheduler, and Web components</span></span>

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a><span data-ttu-id="8fdd4-570">Il fallback della lingua per alcune lingue in Lync Web Scheduler, Dial-in, Launcher join, gestione chat room persistente e OCTab potrebbe non funzionare come previsto</span><span class="sxs-lookup"><span data-stu-id="8fdd4-570">Language fallback for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab might not work as expected</span></span>

<span data-ttu-id="8fdd4-571">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-571">**Issue:**</span></span>

<span data-ttu-id="8fdd4-572">Quando si selezionano impostazioni locali neutre in un Web browser (in Internet Explorer, il nome della lingua, ad esempio, senza ulteriori specifiche \[,\]come "Norwegian no", anziché le impostazioni locali che specificano la lingua, lo script e le impostazioni locali, ad \[esempio "norvegese\], Bokmål (Norvegia) NB-no"), potrebbe determinare un comportamento di visualizzazione imprevisto per alcune lingue in Lync Web Scheduler, accesso esterno, avvio di join, gestione chat room e OCTab.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-572">When selecting a neutral locale in a web browser (in Internet Explorer, for example, the language name without further specification, like "Norwegian \[no\]") instead of a locale specifying language, script and locale (such as "Norwegian, Bokmål (Norway) \[nb-NO\]") might lead to unexpected display behavior for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab.</span></span> <span data-ttu-id="8fdd4-573">Ad esempio, gli utenti potrebbero vedere la pagina inglese quando è selezionata una delle lingue seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-573">For example, users might see the English page when one of the following languages is selected:</span></span>

  - <span data-ttu-id="8fdd4-574">Norvegese</span><span class="sxs-lookup"><span data-stu-id="8fdd4-574">Norwegian</span></span>

  - <span data-ttu-id="8fdd4-575">Portoghese</span><span class="sxs-lookup"><span data-stu-id="8fdd4-575">Portuguese</span></span>

  - <span data-ttu-id="8fdd4-576">Serbo</span><span class="sxs-lookup"><span data-stu-id="8fdd4-576">Serbian</span></span>

<span data-ttu-id="8fdd4-577">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-577">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-578">Se si vuole selezionare una lingua con impostazioni locali neutre, assicurarsi sempre di aggiungere anche la lingua con impostazioni locali specifiche (con script e/o codice paese) come lingua aggiuntiva nell'elenco delle preferenze di lingua del browser.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-578">If you want to select a language with a neutral locale, always make sure that you also add the language with a specific locale (with script and/or country code) as an additional language in your browser's language preference list.</span></span>

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a><span data-ttu-id="8fdd4-579">È disponibile un supporto limitato per le impostazioni locali azeri e Usbeco quando si usa Lync Web Scheduler, accesso esterno, avvio di join, gestione di chat room persistente e OCTab in alcuni Web browser</span><span class="sxs-lookup"><span data-stu-id="8fdd4-579">There is limited support for Azeri and Uzbek locales when using Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab in some web browsers</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="8fdd4-580">Le informazioni in questa sezione riguardano gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-580">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="8fdd4-581">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-581">**Issue:**</span></span>

<span data-ttu-id="8fdd4-582">Quando si usa Internet Explorer 8 o Internet Explorer 9 e si imposta la lingua del browser su Azero (alfabeto latino) o Uzbeco (alfabeto latino), le pagine di avvio di accesso esterno e di join verranno visualizzate in inglese o nella lingua preferita impostata nel browser.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-582">When you use Internet Explorer 8 or Internet Explorer 9, and set the browser language to Azeri (Latin) or Uzbek (Latin), the Dial-in and Join Launcher pages will be displayed in English or the preferred language set in the browser.</span></span>

<span data-ttu-id="8fdd4-583">Quando si usano browser Firefox o Chrome e si imposta la lingua del browser su Azero (alfabeto latino) o Uzbeco (alfabeto latino), Lync Web App, Lync Web Scheduler e RGS OCTab verranno visualizzati in inglese o nella lingua preferita impostata per il browser.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-583">When you use Firefox or Chrome browsers, and you set the browser language to Azeri (Latin) or Uzbek (Latin), the Lync Web App, Lync Web Scheduler, and RGS OCTab will be shown in English or the preferred language set for the browser.</span></span>

<span data-ttu-id="8fdd4-584">Le impostazioni locali dell'Uzbeco (alfabeto latino) non sono supportate nel browser Safari.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-584">The Uzbek (Latin) locale is not supported in the Safari browser.</span></span>

<span data-ttu-id="8fdd4-585">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-585">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-586">Non c'è soluzione alternativa per questi problemi.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-586">There is not workaround for these issues.</span></span>

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a><span data-ttu-id="8fdd4-587">La freccia a discesa mancante per l'elenco "partecipa a riunione da" nella versione rumena di Lync Web App</span><span class="sxs-lookup"><span data-stu-id="8fdd4-587">The drop-down arrow is missing for "Join meeting from" list in the Romanian version of Lync Web App</span></span>

<span data-ttu-id="8fdd4-588">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-588">**Issue:**</span></span>

<span data-ttu-id="8fdd4-589">Quando un utente che usa la versione rumena di Lync Web App esegue i passaggi seguenti, la freccia a discesa non viene visualizzata per partecipare a una **riunione** nell'elenco a discesa:</span><span class="sxs-lookup"><span data-stu-id="8fdd4-589">When a user who is using the Romanian version of Lync Web App performs the following steps, the drop-down arrow is not displayed for **Join meeting** in drop-down list:</span></span>

1.  <span data-ttu-id="8fdd4-590">Selezionare **memorizza nel computer** nella scheda **generale** .</span><span class="sxs-lookup"><span data-stu-id="8fdd4-590">Select **Remember me on this computer** on the **General** tab.</span></span>

2.  <span data-ttu-id="8fdd4-591">Selezionare la scheda **telefono** .</span><span class="sxs-lookup"><span data-stu-id="8fdd4-591">Select the **Phone** tab.</span></span>

3.  <span data-ttu-id="8fdd4-592">Fare clic sull'elenco a discesa per **partecipare a una riunione**.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-592">Click the drop-down list for **Join meeting from**.</span></span>
    
    <span data-ttu-id="8fdd4-593">Gli utenti non vedranno una freccia che indica che sono disponibili più opzioni rispetto a quella predefinita di **Lync Web App**, che includono: **non partecipare all'audio** (in Romeno, "nu se asociaža la Componenta audio") e **nuovo numero**"(in Romeno" Număr Nou ").</span><span class="sxs-lookup"><span data-stu-id="8fdd4-593">Users will not see an arrow that indicates that there are more options than the default **Lync Web App**, which include: **Don't join audio** (in Romanian, "Nu se asociaža la componenta audio") and **New number**" (in Romanian, "Număr nou").</span></span>

<span data-ttu-id="8fdd4-594">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-594">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-595">Anche se la freccia dell'elenco a discesa non viene visualizzata, gli utenti possono comunque selezionare le impostazioni aggiuntive nell'elenco facendo clic sul valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-595">Even though the arrow for this drop-down list is not displayed, users can still select the additional settings in the list by clicking on the default value.</span></span>

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a><span data-ttu-id="8fdd4-596">Quando si usa la versione turca di Lync Web Scheduler, non è possibile salvare una riunione quando si usa l'opzione "persone che scelgo" in "chi è un relatore"</span><span class="sxs-lookup"><span data-stu-id="8fdd4-596">When using the Turkish version of Lync Web Scheduler, a meeting cannot be saved when using the "People I choose" option under "Who is a presenter"</span></span>

<span data-ttu-id="8fdd4-597">**Problema**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-597">**Issue:**</span></span>

<span data-ttu-id="8fdd4-598">Quando si crea o si modifica una riunione nella versione turca di Lync Web Scheduler, l'opzione "utenti scelti" in "chi è un relatore" non è supportata.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-598">When creating or editing a meeting in the Turkish version of the Lync Web Scheduler, the option "People I choose" under "Who is a presenter" is not supported.</span></span> <span data-ttu-id="8fdd4-599">Quando questa opzione è selezionata, la riunione non può essere salvata.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-599">When this option is selected, the meeting can't be saved.</span></span> <span data-ttu-id="8fdd4-600">Viene invece visualizzato un messaggio di errore che indica che non è possibile rendere relatori una o più persone.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-600">Instead, an error message appears, indicating that one or more people cannot be made presenters.</span></span>

<span data-ttu-id="8fdd4-601">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="8fdd4-601">**Workaround:**</span></span>

<span data-ttu-id="8fdd4-602">Per risolvere il problema, gli utenti possono usare l'opzione predefinita "persone della mia azienda" o qualsiasi altra scelta, ad esempio "solo organizzatore" o "tutti, incluse le persone esterne alla mia azienda".</span><span class="sxs-lookup"><span data-stu-id="8fdd4-602">To work around this issue, users can use the default option of "People from my company," or any other choice, such as "Only Organizer" or "Everyone including people outside of my company."</span></span> <span data-ttu-id="8fdd4-603">L'organizzatore può abbassare di livello o promuovere i ruoli corretti in un secondo momento, dopo aver partecipato alla riunione.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-603">The organizer can demote or promote people to their correct roles later, after they have joined the meeting.</span></span>

<span data-ttu-id="8fdd4-604">In alternativa, gli utenti che conoscono un'altra lingua possono modificare la selezione della lingua nel browser in una delle altre lingue supportate da 43 e provare a usare l'opzione "persone che scelgo".</span><span class="sxs-lookup"><span data-stu-id="8fdd4-604">Alternatively, users who understand another language can change the language selection in their browser to one of the other 43 supported languages and attempt to use the “People I choose” option.</span></span>

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a><span data-ttu-id="8fdd4-605">Copyright</span><span class="sxs-lookup"><span data-stu-id="8fdd4-605">Copyright</span></span>

<span data-ttu-id="8fdd4-606">Questo documento supporta una versione preliminare di un prodotto software che può essere modificato in modo sostanziale prima del rilascio finale commerciale ed è l'informazione riservata e proprietaria di Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-606">This document supports a preliminary release of a software product that may be changed substantially prior to final commercial release, and is the confidential and proprietary information of Microsoft Corporation.</span></span> <span data-ttu-id="8fdd4-607">Viene divulgato in base a un accordo di non divulgazione tra il destinatario e Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-607">It is disclosed pursuant to a non-disclosure agreement between the recipient and Microsoft.</span></span> <span data-ttu-id="8fdd4-608">Questo documento viene fornito solo a scopo informativo e Microsoft non rilascia garanzie, espresse o implicite, in questo documento.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-608">This document is provided for informational purposes only and Microsoft makes no warranties, either express or implied, in this document.</span></span> <span data-ttu-id="8fdd4-609">Le informazioni contenute in questo documento, incluso l'URL e altri riferimenti al sito Web Internet, sono soggette a modifiche senza preavviso.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-609">Information in this document, including URL and other Internet website references, is subject to change without notice.</span></span> <span data-ttu-id="8fdd4-610">L'intero rischio dell'uso o dei risultati dell'uso di questo documento rimane con l'utente.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-610">The entire risk of the use or the results from the use of this document remains with the user.</span></span> <span data-ttu-id="8fdd4-611">Se non diversamente specificato, le società, le organizzazioni, i prodotti, i nomi di dominio, gli indirizzi di posta elettronica, i loghi, le persone, i luoghi e gli eventi descritti in questi esempi sono fittizi.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-611">Unless otherwise noted, the companies, organizations, products, domain names, email addresses, logos, people, places, and events depicted in examples herein are fictitious.</span></span> <span data-ttu-id="8fdd4-612">Nessuna associazione con una società, un'organizzazione, un prodotto, un nome di dominio, un indirizzo di posta elettronica, un logo, una persona, un luogo o un evento reali è destinato o dovrebbe essere dedotto.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-612">No association with any real company, organization, product, domain name, email address, logo, person, place, or event is intended or should be inferred.</span></span> <span data-ttu-id="8fdd4-613">Rispettare tutte le leggi sul copyright applicabili è responsabilità dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-613">Complying with all applicable copyright laws is the responsibility of the user.</span></span> <span data-ttu-id="8fdd4-614">Senza limitare i diritti in diritto d'autore, nessuna parte di questo documento può essere riprodotta, archiviata o introdotta in un sistema di recupero o trasmessa in qualsiasi forma o con qualsiasi mezzo (elettronica, meccanica, fotocopie, registrazione o altro) o per qualsiasi scopo. senza l'espressa autorizzazione scritta di Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-614">Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.</span></span>

<span data-ttu-id="8fdd4-615">Microsoft può avere brevetti, applicazioni di brevetto, marchi, copyright o altri diritti di proprietà intellettuale che coprono argomenti in questo documento.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-615">Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document.</span></span> <span data-ttu-id="8fdd4-616">Fatta eccezione per quanto espressamente specificato in un contratto di licenza scritta da Microsoft, l'arredamento di questo documento non offre alcuna licenza per questi brevetti, marchi, copyright o altre proprietà intellettuali.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-616">Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.</span></span>

<span data-ttu-id="8fdd4-617">© 2012 Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-617">© 2012 Microsoft Corporation.</span></span> <span data-ttu-id="8fdd4-618">Tutti i diritti riservati.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-618">All rights reserved.</span></span>

<span data-ttu-id="8fdd4-619">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook e SQL Server sono marchi registrati o marchi di Microsoft Corporation negli Stati Uniti e/o in altri paesi/aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-619">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook, and SQL Server are either registered trademarks or trademarks of Microsoft Corporation in the United States and/or other countries/regions.</span></span>

<span data-ttu-id="8fdd4-620">Tutti gli altri marchi sono proprietà dei rispettivi proprietari.</span><span class="sxs-lookup"><span data-stu-id="8fdd4-620">All other trademarks are property of their respective owners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

