---
title: Risoluzione dei problemi del gestore delle statistiche per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 'Riepilogo: leggere questo argomento per risolvere i problemi relativi alla distribuzione di Statistics Manager per Skype for Business Server.'
ms.openlocfilehash: ea3d6f66003841e893ebe2dcc5d3fe02d0da125b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821776"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="4dce6-103">Risoluzione dei problemi del gestore delle statistiche per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4dce6-103">Troubleshoot Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="4dce6-104">**Riepilogo:** Leggere questo argomento per risolvere i problemi relativi alla distribuzione di Statistics Manager per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4dce6-104">**Summary:** Read this topic to troubleshoot your deployment of Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="4dce6-105">In questo argomento viene descritto come risolvere i problemi relativi alla distribuzione di Gestione statistiche descrivendo gli eventi che potrebbero essere visualizzati nel registro eventi dell'applicazione e le azioni appropriate che è possibile intraprendere per rettificare l'evento.</span><span class="sxs-lookup"><span data-stu-id="4dce6-105">This topic describes how to troubleshoot your Statistics Manager deployment by describing events you might see in the application event log, and appropriate actions you might take to rectify the event.</span></span> <span data-ttu-id="4dce6-106">In questa sezione sono contenute le seguenti sezioni:</span><span class="sxs-lookup"><span data-stu-id="4dce6-106">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="4dce6-107">Eventi agente</span><span class="sxs-lookup"><span data-stu-id="4dce6-107">Agent events</span></span>](troubleshoot.md#BKMK_Agent)
    
- [<span data-ttu-id="4dce6-108">Eventi listener</span><span class="sxs-lookup"><span data-stu-id="4dce6-108">Listener events</span></span>](troubleshoot.md#BKMK_Listener)
    
- [<span data-ttu-id="4dce6-109">Problemi relativi ai siti Web</span><span class="sxs-lookup"><span data-stu-id="4dce6-109">Website issues</span></span>](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a><span data-ttu-id="4dce6-110">Eventi agente</span><span class="sxs-lookup"><span data-stu-id="4dce6-110">Agent events</span></span>
<span data-ttu-id="4dce6-111"><a name="BKMK_Agent"> </a></span><span class="sxs-lookup"><span data-stu-id="4dce6-111"><a name="BKMK_Agent"> </a></span></span>

- <span data-ttu-id="4dce6-112">**1000** - Impossibile impostare il limitatore del processore (oggetto processo) - Motivo sconosciuto</span><span class="sxs-lookup"><span data-stu-id="4dce6-112">**1000** — Unable to setup processor limiter (Job Object) — Unknown reason</span></span>
    
- <span data-ttu-id="4dce6-113">**1001-** La limitazione dei processi non è consentita nel processo (probabilmente già all'interno di un oggetto processo)</span><span class="sxs-lookup"><span data-stu-id="4dce6-113">**1001** — Process limiting isn't allowed on the process (probably already inside a Job Object)</span></span>
    
    <span data-ttu-id="4dce6-114">L'agente viene eseguito all'interno di un oggetto processo Windows per limitare automaticamente il footprint di memoria.</span><span class="sxs-lookup"><span data-stu-id="4dce6-114">The Agent runs inside of a Windows Job Object to automatically limit its memory footprint.</span></span> <span data-ttu-id="4dce6-115">Se l'agente non viene avviato e queste voci di evento sono presenti nel registro eventi, non è possibile creare un'istanza dell'oggetto processo nel server.</span><span class="sxs-lookup"><span data-stu-id="4dce6-115">If the agent will not start and these event entries are present in the event log, the Job Object is not able to be instantiated on the server.</span></span> <span data-ttu-id="4dce6-116">Per risolvere questo problema, è possibile rimuovere il limite di memoria superiore modificando un valore nel file di configurazione:</span><span class="sxs-lookup"><span data-stu-id="4dce6-116">To work around this, the upper memory limit can be removed by changing a value in the config file:</span></span>
    
  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    <span data-ttu-id="4dce6-117">Cercare "MaxProcessMemoryMB" e modificare il valore in "0" come illustrato:</span><span class="sxs-lookup"><span data-stu-id="4dce6-117">Search for "MaxProcessMemoryMB" and change the value to "0" as shown:</span></span>
    
  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > <span data-ttu-id="4dce6-118">Se viene apportata questa modifica, l'agente in genere continuerà a utilizzare 100 MB di memoria, ma non sarà forzatamente limitato a \< 300 MB come predefinito.</span><span class="sxs-lookup"><span data-stu-id="4dce6-118">If this change is made, the Agent will generally still consume \< 100 MB of memory, however it will not be forcefully limited to 300 MB as is the default.</span></span> <span data-ttu-id="4dce6-119">Se viene apportata questa modifica, è consigliabile monitorare attentamente l'utilizzo della memoria per assicurarsi che l'agente non utilizzi una grande quantità di memoria nel computer host.</span><span class="sxs-lookup"><span data-stu-id="4dce6-119">If this change is made, we recommend closely monitoring memory usage to ensure the Agent does not consume a large amount of memory on its host machine.</span></span> 
  
- <span data-ttu-id="4dce6-120">**2000** - Errore di inizializzazione del client</span><span class="sxs-lookup"><span data-stu-id="4dce6-120">**2000** — Client initialization failure</span></span>
    
- <span data-ttu-id="4dce6-121">**2001**- Non è stato possibile stabilire alcuna connessione al servizio in qualsiasi IP di origine</span><span class="sxs-lookup"><span data-stu-id="4dce6-121">**2001**— No connection could be made to the service on any source IP</span></span>
    
    <span data-ttu-id="4dce6-122">Se l'agente non riesce a connettersi al computer listener, controllare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="4dce6-122">If the Agent cannot connect to the Listener computer, check the following:</span></span>
    
    1. <span data-ttu-id="4dce6-123">Verificare che il servizio listener sia in esecuzione nel computer listener.</span><span class="sxs-lookup"><span data-stu-id="4dce6-123">Ensure the Listener service is running on the Listener computer.</span></span> <span data-ttu-id="4dce6-124">In caso contrario, verificare che Redis sia in esecuzione su tale server e quindi riavviare il servizio listener.</span><span class="sxs-lookup"><span data-stu-id="4dce6-124">If not, ensure Redis is running on that server and then restart the Listener service.</span></span>
        
        <span data-ttu-id="4dce6-125">Controllare il registro eventi di Gestione statistiche nel computer listener per verificare che non vi siano problemi con il servizio Listener di Gestione statistiche stesso.</span><span class="sxs-lookup"><span data-stu-id="4dce6-125">Check the Statistics Manager event log on the Listener computer to ensure there are no issues with the Statistics Manager Listener service itself.</span></span>
        
    2. <span data-ttu-id="4dce6-126">Utilizzare uno strumento di connettività, ad esempio telnet, per verificare la connettività dal computer agente al listener sulla porta corretta.</span><span class="sxs-lookup"><span data-stu-id="4dce6-126">Use a connectivity tool such as telnet to verify connectivity from the Agent computer to the Listener on the correct port.</span></span>
        
        <span data-ttu-id="4dce6-127">In caso contrario, verificare che la regola del firewall in ingresso sia abilitata nel computer listener per il tipo di rete a cui è connesso il computer listener (privato/pubblico/dominio).</span><span class="sxs-lookup"><span data-stu-id="4dce6-127">If not, make sure the incoming firewall rule is enabled on the Listener computer for the network type that the Listener computer is connected to (private/public/domain).</span></span> <span data-ttu-id="4dce6-128">Se il computer listener non fa parte di un dominio, la rete potrebbe essere elencata come pubblica e in tal caso le regole del firewall installate con Gestione statistiche non verranno applicate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4dce6-128">If the Listener computer is not joined to a domain, the network may be listed as public and in that case the firewall rules installed with Statistics Manager will not apply by default.</span></span>
    
- <span data-ttu-id="4dce6-129">**4000** - Errore durante il download delle informazioni sul server dal listener (motivo sconosciuto)</span><span class="sxs-lookup"><span data-stu-id="4dce6-129">**4000** — Failure to download Server Info from Listener (unknown reason)</span></span>
    
  - <span data-ttu-id="4dce6-130">**4001** - Server non trovato nella topologia listener</span><span class="sxs-lookup"><span data-stu-id="4dce6-130">**4001** — Server Not Found in Listener Topology</span></span>
    
    <span data-ttu-id="4dce6-131">Questo errore si verifica se il server si connette correttamente al listener, ma il server non è stato aggiunto alla topologia nella cache del listener.</span><span class="sxs-lookup"><span data-stu-id="4dce6-131">This error will occur if the server is successfully connecting to the Listener, but the server was not added to the topology in the Listener's cache.</span></span> <span data-ttu-id="4dce6-132">Opzioni di risoluzione:</span><span class="sxs-lookup"><span data-stu-id="4dce6-132">Resolution options:</span></span>
    
  - <span data-ttu-id="4dce6-133">Assicurarsi di aver seguito le istruzioni per l'importazione della topologia.</span><span class="sxs-lookup"><span data-stu-id="4dce6-133">Make sure you followed the instructions for importing the topology.</span></span> <span data-ttu-id="4dce6-134">Vedere [Importare la topologia.](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="4dce6-134">See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span> 
    
  - <span data-ttu-id="4dce6-135">Se l'agente si trova in un server non elencato nella topologia (ad esempio, i nodi in un cluster AlwaysOn di SQL), sarà necessario aggiungere l'agente manualmente seguendo le istruzioni in [Importare](deploy.md#BKMK_ImportTopology)la topologia.</span><span class="sxs-lookup"><span data-stu-id="4dce6-135">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="4dce6-136">**4002** - Password listener non valida</span><span class="sxs-lookup"><span data-stu-id="4dce6-136">**4002** — Invalid Listener Password</span></span>
    
    <span data-ttu-id="4dce6-137">La password crittografata che l'agente sta tentando di utilizzare non corrisponde alla password del servizio nel listener stesso.</span><span class="sxs-lookup"><span data-stu-id="4dce6-137">The encrypted password that the agent is attempting to use does not match the service password on the Listener itself.</span></span> <span data-ttu-id="4dce6-138">Disinstallare l'agente e reinstallarlo utilizzando la password del servizio corretta.</span><span class="sxs-lookup"><span data-stu-id="4dce6-138">Uninstall the Agent and re-install it using the correct service password.</span></span>
    
  - <span data-ttu-id="4dce6-139">**4003** - Certificate Thumbprint Mismatch</span><span class="sxs-lookup"><span data-stu-id="4dce6-139">**4003** — Certificate Thumbprint Mismatch</span></span>
    
    <span data-ttu-id="4dce6-140">L'identificazione personale del certificato data all'agente al momento dell'installazione non corrisponde all'identificazione personale nel certificato attualmente utilizzato dal listener e pertanto la connessione verrà rifiutata.</span><span class="sxs-lookup"><span data-stu-id="4dce6-140">The certificate thumbprint given to the Agent at install time does not match the thumbprint on the certificate the Listener is currently using and therefore the connection will be refused.</span></span> <span data-ttu-id="4dce6-141">Disinstallare l'agente e reinstallarlo utilizzando l'identificazione personale del certificato corretta.</span><span class="sxs-lookup"><span data-stu-id="4dce6-141">Uninstall the Agent and re-install it using the correct certificate thumbprint.</span></span>
    
  - <span data-ttu-id="4dce6-142">**4004** - Risposta non valida o HttpStatusCode</span><span class="sxs-lookup"><span data-stu-id="4dce6-142">**4004** — Invalid Response or HttpStatusCode</span></span>
    
    <span data-ttu-id="4dce6-143">Il listener non risponde con uno stato previsto.</span><span class="sxs-lookup"><span data-stu-id="4dce6-143">The Listener is not responding with an expected status.</span></span> 
    
  - <span data-ttu-id="4dce6-144">Se la connessione è proxy, controlla la configurazione del proxy.</span><span class="sxs-lookup"><span data-stu-id="4dce6-144">If the connection is proxied, check the proxy configuration.</span></span>
    
  - <span data-ttu-id="4dce6-145">Controllare il registro StatsMan del computer listener per verificare la presenza di problemi di configurazione.</span><span class="sxs-lookup"><span data-stu-id="4dce6-145">Check the Listener computer's StatsMan log for issues with its configuration.</span></span>
    
  - <span data-ttu-id="4dce6-146">**4005** - Impossibile de-serializzare il codice XML</span><span class="sxs-lookup"><span data-stu-id="4dce6-146">**4005** — Couldn't de-serialize the XML</span></span>
    
    <span data-ttu-id="4dce6-147">Le informazioni sul server nel server listener sono danneggiate o potrebbe esserci una mancata corrispondenza di versione tra l'agente e i computer listener.</span><span class="sxs-lookup"><span data-stu-id="4dce6-147">The server info on the Listener server is corrupt or there may be a version mismatch between the Agent and the Listener computers.</span></span> <span data-ttu-id="4dce6-148">Verificare che le versioni corrispondano e controllare la presenza di problemi nel registro eventi del listener.</span><span class="sxs-lookup"><span data-stu-id="4dce6-148">Ensure the versions match and check the Listener event log for issues.</span></span>
    
## <a name="listener-events"></a><span data-ttu-id="4dce6-149">Eventi listener</span><span class="sxs-lookup"><span data-stu-id="4dce6-149">Listener events</span></span>
<span data-ttu-id="4dce6-150"><a name="BKMK_Listener"> </a></span><span class="sxs-lookup"><span data-stu-id="4dce6-150"><a name="BKMK_Listener"> </a></span></span>

- <span data-ttu-id="4dce6-151">**10000** - Errore di avvio Motivo sconosciuto (irreversibile e il servizio si arresta/arresta in modo anomalo di conseguenza)</span><span class="sxs-lookup"><span data-stu-id="4dce6-151">**10000** — Startup failure Unknown reason (these are unrecoverable and the service will stop/crash as a result)</span></span>
    
  - <span data-ttu-id="4dce6-152">**10001** - Problema di configurazione</span><span class="sxs-lookup"><span data-stu-id="4dce6-152">**10001** — Configuration problem</span></span>
    
    <span data-ttu-id="4dce6-153">In genere ciò si verifica quando il file [listener_install_location]\PerfAgentListener.exe.config è stato modificato manualmente e non può essere letto dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4dce6-153">Generally this will occur when the [listener_install_location]\PerfAgentListener.exe.config file has been modified by hand and cannot be read by the application.</span></span>
    
  - <span data-ttu-id="4dce6-154">**10002** - Errore di inizializzazione del listener HTTP</span><span class="sxs-lookup"><span data-stu-id="4dce6-154">**10002** — HTTP Listener initialization error</span></span>
    
    <span data-ttu-id="4dce6-155">Questo evento viene in genere registrato quando l'elenco di controllo di accesso url non è stato impostato correttamente durante l'installazione o il certificato SSL non è valido.</span><span class="sxs-lookup"><span data-stu-id="4dce6-155">This event will generally be logged when the URL ACL has not been set properly during installation or the SSL Cert is invalid.</span></span> <span data-ttu-id="4dce6-156">Verificare che il certificato nella configurazione sia valido.</span><span class="sxs-lookup"><span data-stu-id="4dce6-156">Ensure the certificate in your configuration is valid.</span></span> <span data-ttu-id="4dce6-157">In caso contrario, reinstallare il listener in base alle istruzioni in [Deploy Statistics Manager.](deploy.md#BKMK_Deploy)</span><span class="sxs-lookup"><span data-stu-id="4dce6-157">If it is, reinstall the Listener according to the instructions in [Deploy Statistics Manager](deploy.md#BKMK_Deploy).</span></span>
    
  - <span data-ttu-id="4dce6-158">**10003** - Errore Redis</span><span class="sxs-lookup"><span data-stu-id="4dce6-158">**10003** — Redis failure</span></span>
    
  - <span data-ttu-id="4dce6-159">**10004** - Errore dell'infrastruttura di memorizzazione nella cache</span><span class="sxs-lookup"><span data-stu-id="4dce6-159">**10004** — Caching infrastructure failure</span></span>
    
  - <span data-ttu-id="4dce6-160">**10007** - Impostazioni (archiviate in redis)</span><span class="sxs-lookup"><span data-stu-id="4dce6-160">**10007** — Settings (stored in redis)</span></span>
    
    <span data-ttu-id="4dce6-161">Il listener non è stato in grado di contattare Redis o recuperare dati ben formati dalla cache e non è stato possibile avviarsi.</span><span class="sxs-lookup"><span data-stu-id="4dce6-161">The Listener could not contact Redis or retrieve well-formed data from the cache and could not start.</span></span> <span data-ttu-id="4dce6-162">Verificare che il servizio Redis sia avviato e configurato correttamente nel server.</span><span class="sxs-lookup"><span data-stu-id="4dce6-162">Ensure the Redis service is started and configured properly on the server.</span></span>
    
  - <span data-ttu-id="4dce6-163">**10005** - Recupero/analisi delle informazioni sul server</span><span class="sxs-lookup"><span data-stu-id="4dce6-163">**10005** — Server info retrieval/parsing</span></span>
    
    <span data-ttu-id="4dce6-164">Le informazioni sulla topologia nella cache Redis non sono valide.</span><span class="sxs-lookup"><span data-stu-id="4dce6-164">The topology information in the Redis cache is invalid.</span></span> <span data-ttu-id="4dce6-165">Prima di tutto, tenta di riavviare Redis e il listener.</span><span class="sxs-lookup"><span data-stu-id="4dce6-165">First, attempt to restart Redis and the Listener.</span></span> <span data-ttu-id="4dce6-166">Se l'errore persiste, vedere [Importare la topologia per](deploy.md#BKMK_ImportTopology) ricreare i dati della topologia.</span><span class="sxs-lookup"><span data-stu-id="4dce6-166">If the error persists, see [Import the topology](deploy.md#BKMK_ImportTopology) to recreate the topology data.</span></span>
    
- <span data-ttu-id="4dce6-167">**10100** - Interruzione del PING di Redis</span><span class="sxs-lookup"><span data-stu-id="4dce6-167">**10100** — Redis PING outage</span></span>
    
  - <span data-ttu-id="4dce6-168">**10101** - Interruzione continuata di Redis PING (ogni 60 secondi)</span><span class="sxs-lookup"><span data-stu-id="4dce6-168">**10101** — Redis PING continued outage (every 60 seconds)</span></span>
    
  - <span data-ttu-id="4dce6-169">**30100** - Redis PING outage restored</span><span class="sxs-lookup"><span data-stu-id="4dce6-169">**30100** — Redis PING outage restored</span></span>
    
    <span data-ttu-id="4dce6-170">Questi verranno registrati quando il listener non è in grado di connettersi a Redis.</span><span class="sxs-lookup"><span data-stu-id="4dce6-170">These will be logged when the Listener cannot connect to Redis.</span></span> <span data-ttu-id="4dce6-171">Assicurati che Redis sia avviato e che la connettività di rete tra Listener e Redis sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="4dce6-171">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="4dce6-172">**10200** - Interruzione della scrittura di Redis</span><span class="sxs-lookup"><span data-stu-id="4dce6-172">**10200** — Redis Write outage</span></span>
    
  - <span data-ttu-id="4dce6-173">**10201** - Interruzione di Redis Write continua (ogni 60 secondi)</span><span class="sxs-lookup"><span data-stu-id="4dce6-173">**10201** — Redis Write outage continued (every 60 seconds)</span></span>
    
  - <span data-ttu-id="4dce6-174">**30100** - Risoluzione dell'interruzione della scrittura di Redis</span><span class="sxs-lookup"><span data-stu-id="4dce6-174">**30100** — Redis Write outage resolved</span></span>
    
    <span data-ttu-id="4dce6-175">Questi verranno registrati quando il listener non è in grado di scrivere nella cache Redis.</span><span class="sxs-lookup"><span data-stu-id="4dce6-175">These will be logged when the Listener cannot write to the Redis cache.</span></span> <span data-ttu-id="4dce6-176">Assicurati che Redis sia avviato e che la connettività di rete tra Listener e Redis sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="4dce6-176">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="4dce6-177">**30000** - Avviato correttamente</span><span class="sxs-lookup"><span data-stu-id="4dce6-177">**30000** — Successfully started</span></span>
    
    <span data-ttu-id="4dce6-178">Registrato ogni volta che il listener viene avviato.</span><span class="sxs-lookup"><span data-stu-id="4dce6-178">Logged each time the Listener is started.</span></span>
    
- <span data-ttu-id="4dce6-179">**22000-** Inizializzazione dell'agente di gestione delle statistiche completata.</span><span class="sxs-lookup"><span data-stu-id="4dce6-179">**22000** — Initialization of Statistics Manager Agent succeeded.</span></span>
    
- <span data-ttu-id="4dce6-180">**23000** - Inizializzazione di EventLogQueryManager completata (prima volta o dopo un errore)</span><span class="sxs-lookup"><span data-stu-id="4dce6-180">**23000** — Initialization of EventLogQueryManager succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="4dce6-181">**24000** - Inizializzazione di serverinfo completata (prima volta o dopo un errore)</span><span class="sxs-lookup"><span data-stu-id="4dce6-181">**24000** — Initialization of serverinfo succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="4dce6-182">**25000** - Listener è di nuovo online dopo la mancata pubblicazione (o il primo post riuscito)</span><span class="sxs-lookup"><span data-stu-id="4dce6-182">**25000** — Listener is back online after failing to post (or first successful post)</span></span>
    
- <span data-ttu-id="4dce6-183">**5000** - Inizio del listener offline per l'inserimento di dati</span><span class="sxs-lookup"><span data-stu-id="4dce6-183">**5000** — Start of listener offline for posting data</span></span>
    
- <span data-ttu-id="4dce6-184">**5001** - Listener ancora offline per un periodo prolungato</span><span class="sxs-lookup"><span data-stu-id="4dce6-184">**5001** — Listener is still offline for an extended period</span></span>
    
    <span data-ttu-id="4dce6-185">Questi eventi possono essere utili per il monitoraggio,l'avviso/la cancellazione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="4dce6-185">These events can be useful for monitoring/alerting/clearing issues.</span></span>
    
## <a name="website-issues"></a><span data-ttu-id="4dce6-186">Problemi relativi ai siti Web</span><span class="sxs-lookup"><span data-stu-id="4dce6-186">Website issues</span></span>
<span data-ttu-id="4dce6-187"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="4dce6-187"><a name="BKMK_Website"> </a></span></span>

- <span data-ttu-id="4dce6-188">Richieste di accesso ripetitive in Chrome: si tratta di un bug risolto nella versione 1.1.</span><span class="sxs-lookup"><span data-stu-id="4dce6-188">Repetitive login prompts in Chrome - this was a bug that has been resolved in version 1.1.</span></span> <span data-ttu-id="4dce6-189">Assicurarsi di aver eseguito l'aggiornamento all'ultima versione di Gestione statistiche se vengono visualizzate richieste di accesso ripetute nel browser Chrome.</span><span class="sxs-lookup"><span data-stu-id="4dce6-189">Be sure you have upgraded to the latest version of Statistics Manager if you are seeing repeated login prompts in the Chrome browser.</span></span> <span data-ttu-id="4dce6-190">Per verificare la versione del sito Web in esecuzione:</span><span class="sxs-lookup"><span data-stu-id="4dce6-190">To verify the version of the website you are running:</span></span>
    
  - <span data-ttu-id="4dce6-191">In Esplora file apri (directory predefinita)</span><span class="sxs-lookup"><span data-stu-id="4dce6-191">In File Explorer, open (default directory)</span></span>
    
  - <span data-ttu-id="4dce6-192">Fai clic con il StatsManHubWebSite.dll clic con il pulsante destro del mouse e visualizzane le proprietà.</span><span class="sxs-lookup"><span data-stu-id="4dce6-192">Right click on StatsManHubWebSite.dll and view its properties.</span></span>
    
  - <span data-ttu-id="4dce6-193">Se non è possibile trovare un computer nella visualizzazione KHI Orizzontale o Dettagli contatore, verificare che sia membro di un sito e di un pool.</span><span class="sxs-lookup"><span data-stu-id="4dce6-193">If a computer cannot be found in the KHI Landscape view or the Counter Details view, make sure it is a member of a Site and a Pool.</span></span> <span data-ttu-id="4dce6-194">In caso contrario, non verrà visualizzato in tali visualizzazioni.</span><span class="sxs-lookup"><span data-stu-id="4dce6-194">If it is not, it will not appear in those views.</span></span> <span data-ttu-id="4dce6-195">Per informazioni sulla definizione di un sito e di un pool per un server nella topologia, vedere [Import the topology.](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="4dce6-195">For information about defining a site and pool for a server in the topology, see [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="4dce6-196">La versione del prodotto verrà visualizzata nei dettagli della descrizione.</span><span class="sxs-lookup"><span data-stu-id="4dce6-196">The product version will be shown in the Description details.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="4dce6-197">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="4dce6-197">For more information</span></span>
<span data-ttu-id="4dce6-198"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="4dce6-198"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="4dce6-199">Per ulteriori informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4dce6-199">For more information, see the following:</span></span>
  
- [<span data-ttu-id="4dce6-200">Pianificare il gestore delle statistiche per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4dce6-200">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="4dce6-201">Distribuire il gestore delle statistiche per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4dce6-201">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="4dce6-202">Aggiornare il gestore delle statistiche per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4dce6-202">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
