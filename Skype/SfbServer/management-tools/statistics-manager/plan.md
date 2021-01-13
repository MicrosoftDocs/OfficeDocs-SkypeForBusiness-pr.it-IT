---
title: Pianificare il gestore delle statistiche per Skype for Business Server
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
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Riepilogo: leggere questo argomento per informazioni sulla gestione delle statistiche per Skype for Business Server.'
ms.openlocfilehash: cdc536abcbd1bd98c4a3c7ce974247a716865582
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821826"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="5bca4-103">Pianificare il gestore delle statistiche per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5bca4-103">Plan for Statistics Manager for Skype for Business Server</span></span>

<span data-ttu-id="5bca4-104">**Riepilogo:** Leggere questo argomento per informazioni su gestione delle statistiche per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5bca4-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server.</span></span>

 <span data-ttu-id="5bca4-105">La gestione delle statistiche per Skype for Business Server è uno strumento potente che consente di visualizzare i dati di integrità e prestazioni di Skype for Business Server in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="5bca4-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="5bca4-106">È possibile eseguire il polling dei dati delle prestazioni tra centinaia di server ogni pochi secondi e visualizzare i risultati immediatamente nel sito Web di gestione delle statistiche.</span><span class="sxs-lookup"><span data-stu-id="5bca4-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>

<span data-ttu-id="5bca4-107">È possibile utilizzare Gestione statistiche per identificare i problemi di prestazioni in esecuzione, visualizzare i risultati di una modifica pianificata per l'ambiente, monitorare la risoluzione delle interruzioni e molto altro ancora.</span><span class="sxs-lookup"><span data-stu-id="5bca4-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="5bca4-108">Fuori dalla casella, gestione statistiche è configurato con le soglie di indicatore di integrità chiave (KHI) e può essere personalizzato in base alle esigenze specifiche della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5bca4-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span>

<span data-ttu-id="5bca4-109">È possibile distribuire Gestione statistiche in una distribuzione locale in cui un singolo server ospita tutti i componenti di gestione delle statistiche sul server.</span><span class="sxs-lookup"><span data-stu-id="5bca4-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="5bca4-110">Per ulteriori informazioni sulla distribuzione di gestione statistiche, vedere [deploy Statistics Manager for Skype for Business Server](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="5bca4-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span> <span data-ttu-id="5bca4-111">Se si dispone già di una distribuzione di gestione delle statistiche esistente, ma non è ancora stato eseguito l'aggiornamento alla versione 2,0, vedere [What ' s New in release 2,0](plan.md#BKMK_WhatsNew) e [upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="5bca4-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 2.0, see [What's new in Release 2.0](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

<span data-ttu-id="5bca4-112">In questa sezione sono contenute le seguenti sezioni:</span><span class="sxs-lookup"><span data-stu-id="5bca4-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="5bca4-113">Caratteristiche e funzionalità</span><span class="sxs-lookup"><span data-stu-id="5bca4-113">Features and capabilities</span></span>](plan.md#BKMK_Features)

- [<span data-ttu-id="5bca4-114">Novità della versione 2,0</span><span class="sxs-lookup"><span data-stu-id="5bca4-114">What's new in Release 2.0</span></span>](plan.md#BKMK_WhatsNew)

- [<span data-ttu-id="5bca4-115">Componenti</span><span class="sxs-lookup"><span data-stu-id="5bca4-115">Components</span></span>](plan.md#BKMK_Components)

- [<span data-ttu-id="5bca4-116">Distribuzione in locale</span><span class="sxs-lookup"><span data-stu-id="5bca4-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)

- [<span data-ttu-id="5bca4-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5bca4-117">Requirements</span></span>](plan.md#BKMK_Requirements)

- [<span data-ttu-id="5bca4-118">Considerazioni sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="5bca4-118">Security considerations</span></span>](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a><span data-ttu-id="5bca4-119">Caratteristiche e funzionalità</span><span class="sxs-lookup"><span data-stu-id="5bca4-119">Features and capabilities</span></span>
<span data-ttu-id="5bca4-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="5bca4-120"><a name="BKMK_Features"> </a></span></span>

<span data-ttu-id="5bca4-121">Gestione statistiche consente di:</span><span class="sxs-lookup"><span data-stu-id="5bca4-121">Statistics Manager allows you to:</span></span>

- <span data-ttu-id="5bca4-122">Visualizzare i dati non elaborati per tutti i server in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="5bca4-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="5bca4-123">I dati vengono campionati a una velocità molto elevata e inviati al sito Web in meno di un secondo.</span><span class="sxs-lookup"><span data-stu-id="5bca4-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>

- <span data-ttu-id="5bca4-124">Visualizzare i dati aggregati per un ruolo specifico. ad esempio, Front End Server, Mediation Server, Edge Server e così via.</span><span class="sxs-lookup"><span data-stu-id="5bca4-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>

- <span data-ttu-id="5bca4-125">Eseguire il drill-down per visualizzare i dati relativi a siti specifici, pool specifici all'interno del sito e quindi Server specifici all'interno del pool.</span><span class="sxs-lookup"><span data-stu-id="5bca4-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>

- <span data-ttu-id="5bca4-126">Creare grafici personalizzati in modo che i contatori scelti vengano visualizzati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="5bca4-126">Create custom charts so that chosen counters are shown by default.</span></span>

- <span data-ttu-id="5bca4-127">Eseguire lo zoom e la panoramica sugli assi x e y o solo sull'asse x.</span><span class="sxs-lookup"><span data-stu-id="5bca4-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>

- <span data-ttu-id="5bca4-128">Utilizzare gli intervalli di date o i punti nel tempo per filtrare i dati.</span><span class="sxs-lookup"><span data-stu-id="5bca4-128">Use date ranges or points in time to filter data.</span></span>

- <span data-ttu-id="5bca4-129">Visualizzare le prestazioni del server in base a indicatori di integrità chiave stabiliti (KHIs).</span><span class="sxs-lookup"><span data-stu-id="5bca4-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="5bca4-130">KHIs rappresenta un insieme di contatori delle prestazioni con un intervallo integro definito.</span><span class="sxs-lookup"><span data-stu-id="5bca4-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span>

- <span data-ttu-id="5bca4-131">Visualizzare le metriche dettagliate per ogni contatore.</span><span class="sxs-lookup"><span data-stu-id="5bca4-131">View detailed metrics for each counter.</span></span>

- <span data-ttu-id="5bca4-132">Confrontare i dati tra più popolazioni o server.</span><span class="sxs-lookup"><span data-stu-id="5bca4-132">Compare data across multiple populations or servers.</span></span>

- <span data-ttu-id="5bca4-133">Visualizzare i report dei contatori latenti per identificare gli agenti che non segnalano i dati correnti al servizio dashboard.</span><span class="sxs-lookup"><span data-stu-id="5bca4-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>

- <span data-ttu-id="5bca4-134">Salvare una determinata istanza di dati del grafico in un file.</span><span class="sxs-lookup"><span data-stu-id="5bca4-134">Save a particular instance of chart data to a file.</span></span>

- <span data-ttu-id="5bca4-135">Visualizzare KHIs in tempo reale, inclusi gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="5bca4-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="5bca4-136">Se la visualizzazione cronologia è abilitata, vengono visualizzati solo i nuovi errori.</span><span class="sxs-lookup"><span data-stu-id="5bca4-136">If the history view is enabled, only new failures are shown.</span></span>

  - <span data-ttu-id="5bca4-137">Visualizzazione di tutti i KHIs in una sola volta</span><span class="sxs-lookup"><span data-stu-id="5bca4-137">View all KHIs at one time</span></span>

  - <span data-ttu-id="5bca4-138">Visualizzazione di KHIs per server (visualizzazione orizzontale)</span><span class="sxs-lookup"><span data-stu-id="5bca4-138">View KHIs by server (Landscape view)</span></span>

  - <span data-ttu-id="5bca4-139">Visualizzazione delle definizioni di KHI</span><span class="sxs-lookup"><span data-stu-id="5bca4-139">View KHI definitions</span></span>

## <a name="whats-new-in-release-20"></a><span data-ttu-id="5bca4-140">Novità della versione 2,0</span><span class="sxs-lookup"><span data-stu-id="5bca4-140">What's new in Release 2.0</span></span>
<span data-ttu-id="5bca4-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="5bca4-141"><a name="BKMK_WhatsNew"> </a></span></span>

<span data-ttu-id="5bca4-142">Di seguito vengono descritte le novità della versione 2,0.</span><span class="sxs-lookup"><span data-stu-id="5bca4-142">The following describes what's new in Release 2.0.</span></span> <span data-ttu-id="5bca4-143">Se si dispone di una distribuzione esistente di gestione statistiche e non è ancora stato eseguito l'aggiornamento, vedere [upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="5bca4-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

- <span data-ttu-id="5bca4-144">Sono state aggiunte visualizzazioni dello scenario per i supporti perimetrali, l'integrità dei tessuti, il failover del pool e gli scenari di registrazione.</span><span class="sxs-lookup"><span data-stu-id="5bca4-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>

- <span data-ttu-id="5bca4-145">Sono stati aggiunti numerosi nuovi contatori per SQL Server, più contatori di utilizzo di Skype for business e così via.</span><span class="sxs-lookup"><span data-stu-id="5bca4-145">Many new counters have been added for SQL servers, more Skype for Business usage counters, and so on.</span></span>

- <span data-ttu-id="5bca4-146">Integrazione dei nodi Watcher per l'agente di gestione delle statistiche-se l'agente è installato in un nodo Watcher, riporterà le statistiche sulle transazioni sintetiche come contatori di nuovo in gestione statistiche.</span><span class="sxs-lookup"><span data-stu-id="5bca4-146">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>

- <span data-ttu-id="5bca4-147">Numerosi miglioramenti relativi a prestazioni e affidabilità.</span><span class="sxs-lookup"><span data-stu-id="5bca4-147">Numerous reliability and performance improvements.</span></span>

<span data-ttu-id="5bca4-148">Per verificare la versione del sito Web di gestione delle statistiche in esecuzione:</span><span class="sxs-lookup"><span data-stu-id="5bca4-148">To verify the version of the Statistics Manager Website you are running:</span></span>

- <span data-ttu-id="5bca4-149">In Esplora file aprire (directory predefinita) C:\Program Skype for Business Server stats WebSite\bin</span><span class="sxs-lookup"><span data-stu-id="5bca4-149">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>

- <span data-ttu-id="5bca4-150">Fare clic con il pulsante destro del mouse su StatsManHubWebSite.dll e visualizzare le proprietà</span><span class="sxs-lookup"><span data-stu-id="5bca4-150">Right click on StatsManHubWebSite.dll and view its properties</span></span>

- <span data-ttu-id="5bca4-151">La versione del prodotto verrà visualizzata nei dettagli della descrizione.</span><span class="sxs-lookup"><span data-stu-id="5bca4-151">The product version will be shown in the Description details.</span></span>

## <a name="components"></a><span data-ttu-id="5bca4-152">Componenti</span><span class="sxs-lookup"><span data-stu-id="5bca4-152">Components</span></span>
<span data-ttu-id="5bca4-153"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="5bca4-153"><a name="BKMK_Components"> </a></span></span>

<span data-ttu-id="5bca4-154">Gestione statistiche è costituito dai componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5bca4-154">Statistics Manager consists of the following components:</span></span>

- <span data-ttu-id="5bca4-155">**Agente.**</span><span class="sxs-lookup"><span data-stu-id="5bca4-155">**Agent.**</span></span> <span data-ttu-id="5bca4-156">Agente Lightweight che viene eseguito in ogni server monitorato.</span><span class="sxs-lookup"><span data-stu-id="5bca4-156">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="5bca4-157">L'agente consente il polling ad alta velocità configurabile dei contatori delle prestazioni con l'aggregazione locale.</span><span class="sxs-lookup"><span data-stu-id="5bca4-157">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>

- <span data-ttu-id="5bca4-158">**Listener.**</span><span class="sxs-lookup"><span data-stu-id="5bca4-158">**Listener.**</span></span> <span data-ttu-id="5bca4-159">API lato server che riceve i dati da tutti gli agenti e aggrega i dati tra le popolazioni.</span><span class="sxs-lookup"><span data-stu-id="5bca4-159">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>

- <span data-ttu-id="5bca4-160">**Hub.**</span><span class="sxs-lookup"><span data-stu-id="5bca4-160">**Hub.**</span></span> <span data-ttu-id="5bca4-161">Funge da API client per il sistema, viene eseguito nei server Web e fornisce aggiornamenti dei dati in tempo reale ai client connessi tramite il sito Web.</span><span class="sxs-lookup"><span data-stu-id="5bca4-161">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="5bca4-162">(L'hub viene installato automaticamente come parte del sito Web MSI).</span><span class="sxs-lookup"><span data-stu-id="5bca4-162">(The Hub is automatically installed as part of the Website msi.)</span></span>

- <span data-ttu-id="5bca4-163">**Sito Web.**</span><span class="sxs-lookup"><span data-stu-id="5bca4-163">**Website.**</span></span> <span data-ttu-id="5bca4-164">Interfaccia utente che unisce tutte le funzionalità disponibili nel sistema.</span><span class="sxs-lookup"><span data-stu-id="5bca4-164">A user interface that pulls together all the features available in the system.</span></span>

<span data-ttu-id="5bca4-165">Inoltre, gestione statistiche richiede **ReDim**, un server di struttura dati open source per la memorizzazione nella cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="5bca4-165">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="5bca4-166">Per ulteriori informazioni sul download delle redini, vedere [deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span><span class="sxs-lookup"><span data-stu-id="5bca4-166">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>

## <a name="on-premises-deployment"></a><span data-ttu-id="5bca4-167">Distribuzione in locale</span><span class="sxs-lookup"><span data-stu-id="5bca4-167">On-premises deployment</span></span>
<span data-ttu-id="5bca4-168"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="5bca4-168"><a name="BKMK_DeploymentOptions"> </a></span></span>

<span data-ttu-id="5bca4-169">In una distribuzione locale, un singolo server ospita tutti i componenti di gestione delle statistiche sul server.</span><span class="sxs-lookup"><span data-stu-id="5bca4-169">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span>

<span data-ttu-id="5bca4-170">Nel diagramma seguente viene illustrata una distribuzione locale, in cui il sito Web di gestione delle statistiche, l'hub, l'ascoltatore e il sistema di memorizzazione nella cache di ReDim sono ospitati in un singolo computer.</span><span class="sxs-lookup"><span data-stu-id="5bca4-170">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="5bca4-171">Gestione statistiche sta monitorando tre server Skype for business, ognuno dei quali ha un singolo agente per la trasmissione dei dati al listener.</span><span class="sxs-lookup"><span data-stu-id="5bca4-171">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="5bca4-172">Gli utenti si connettono a un singolo sito Web per visualizzare tutti i dati aggregati da Gestione statistiche:</span><span class="sxs-lookup"><span data-stu-id="5bca4-172">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>

![Distribuzione in locale di stats Manager](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a><span data-ttu-id="5bca4-174">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5bca4-174">Requirements</span></span>
<span data-ttu-id="5bca4-175"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="5bca4-175"><a name="BKMK_Requirements"> </a></span></span>

<span data-ttu-id="5bca4-176">Prima di distribuire Gestione statistiche, è necessario prendere in considerazione i seguenti requisiti software, di rete e hardware.</span><span class="sxs-lookup"><span data-stu-id="5bca4-176">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="5bca4-177">Requisiti software</span><span class="sxs-lookup"><span data-stu-id="5bca4-177">Software requirements</span></span>

- <span data-ttu-id="5bca4-178">Windows Server 2016 e 2019</span><span class="sxs-lookup"><span data-stu-id="5bca4-178">Windows Server 2016 and 2019</span></span>

- <span data-ttu-id="5bca4-179">IIS (installazione automatica)</span><span class="sxs-lookup"><span data-stu-id="5bca4-179">IIS (automatically installed)</span></span>

- <span data-ttu-id="5bca4-180">Redis</span><span class="sxs-lookup"><span data-stu-id="5bca4-180">Redis</span></span>

- <span data-ttu-id="5bca4-181">Servizi di gestione delle statistiche (installati automaticamente)</span><span class="sxs-lookup"><span data-stu-id="5bca4-181">Statistics Manager services (automatically installed)</span></span>

- <span data-ttu-id="5bca4-182">PSExec-obbligatorio per la distribuzione di agenti remoti</span><span class="sxs-lookup"><span data-stu-id="5bca4-182">PSExec - Required to do remote agent deployment</span></span>

- <span data-ttu-id="5bca4-183">.NET 4,5 (incluso con 2012 R2)-obbligatorio per gli agenti e i componenti sul server</span><span class="sxs-lookup"><span data-stu-id="5bca4-183">.NET 4.5 (included with 2012 R2) - Required for agents and server-side components</span></span>
- <span data-ttu-id="5bca4-184">Scaricare il [Server Skype for business, Real-Time gestione delle statistiche (64 bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span><span class="sxs-lookup"><span data-stu-id="5bca4-184">Download the [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="5bca4-185">Requisiti di rete</span><span class="sxs-lookup"><span data-stu-id="5bca4-185">Networking requirements</span></span>


|<span data-ttu-id="5bca4-186">**Server di hosting**</span><span class="sxs-lookup"><span data-stu-id="5bca4-186">**Hosting server**</span></span>|<span data-ttu-id="5bca4-187">**Agents**</span><span class="sxs-lookup"><span data-stu-id="5bca4-187">**Agents**</span></span>|<span data-ttu-id="5bca4-188">**Listener**</span><span class="sxs-lookup"><span data-stu-id="5bca4-188">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5bca4-189">Minima rete Gigabit full duplex.</span><span class="sxs-lookup"><span data-stu-id="5bca4-189">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="5bca4-190">Porta TCP in uscita 8443 (numero di porta personalizzabile) per comunicare con il listener.</span><span class="sxs-lookup"><span data-stu-id="5bca4-190">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="5bca4-191">La porta del listener deve essere la stessa su tutti i server.</span><span class="sxs-lookup"><span data-stu-id="5bca4-191">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="5bca4-192">La porta TCP in ingresso 80 o 443 aperta per ospitare il sito Web.</span><span class="sxs-lookup"><span data-stu-id="5bca4-192">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="5bca4-193">Porta TCP in ingresso 8443 (numero di porta personalizzabile) per gli agenti per comunicare con esso.</span><span class="sxs-lookup"><span data-stu-id="5bca4-193">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||

<span data-ttu-id="5bca4-194">Durante l'installazione, vengono create automaticamente le porte del firewall per il listener e il sito Web.</span><span class="sxs-lookup"><span data-stu-id="5bca4-194">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="5bca4-195">Per gli agenti, l'installazione presuppone che le connessioni TCP in uscita siano consentite per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="5bca4-195">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>

### <a name="hardware-requirements"></a><span data-ttu-id="5bca4-196">Requisiti hardware</span><span class="sxs-lookup"><span data-stu-id="5bca4-196">Hardware requirements</span></span>

<span data-ttu-id="5bca4-197">In una distribuzione locale, in cui un singolo server ospita tutti i componenti di gestione delle statistiche sul server, un server con 16 GB di RAM e 4 CPU dovrebbe essere in grado di supportare circa 150 campioni al secondo in media.</span><span class="sxs-lookup"><span data-stu-id="5bca4-197">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="5bca4-198">Per determinare il numero di contatori/agenti che è possibile supportare, utilizzare il calcolo seguente:</span><span class="sxs-lookup"><span data-stu-id="5bca4-198">To determine how many counters/agents you can support, use the following calculation:</span></span>

<span data-ttu-id="5bca4-199">100 server \* 80 contatori \* 1 campione al minuto da ogni agente/60 secondi = ~ 133 campioni al secondo.</span><span class="sxs-lookup"><span data-stu-id="5bca4-199">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="5bca4-200">Considerazioni sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="5bca4-200">Security considerations</span></span>
<span data-ttu-id="5bca4-201"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="5bca4-201"><a name="BKMK_Security"> </a></span></span>

<span data-ttu-id="5bca4-202">Tutto il traffico tra i server è crittografato.</span><span class="sxs-lookup"><span data-stu-id="5bca4-202">All traffic between servers is encrypted.</span></span>

- <span data-ttu-id="5bca4-203">Il traffico HTTPS crittografato verrà inviato tramite la porta 8443 (per impostazione predefinita) dall'agente al server listener.</span><span class="sxs-lookup"><span data-stu-id="5bca4-203">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>

- <span data-ttu-id="5bca4-204">L'agente verificherà l'identificazione personale SSL sul server per assicurarsi che il server listener sia il destinatario previsto.</span><span class="sxs-lookup"><span data-stu-id="5bca4-204">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="5bca4-205">Si noti che l'agente utilizza la verifica dell'identificazione personale del certificato (anziché la verifica della catena).</span><span class="sxs-lookup"><span data-stu-id="5bca4-205">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="5bca4-206">La convalida del certificato non sarà completa perché è possibile utilizzare certificati autofirmati.</span><span class="sxs-lookup"><span data-stu-id="5bca4-206">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>

- <span data-ttu-id="5bca4-207">Dopo che l'agente è stato soddisfatto, il listener è autentico, una password verrà presentata dall'agente che viene quindi verificata dal listener.</span><span class="sxs-lookup"><span data-stu-id="5bca4-207">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span>

- <span data-ttu-id="5bca4-208">L'agente inizia a trasmettere i dati sulle prestazioni tramite la connessione al listener.</span><span class="sxs-lookup"><span data-stu-id="5bca4-208">The Agent begins transmitting performance data over the connection to the Listener.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="5bca4-209">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="5bca4-209">For more information</span></span>
<span data-ttu-id="5bca4-210"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="5bca4-210"><a name="BKMK_Security"> </a></span></span>

<span data-ttu-id="5bca4-211">Per ulteriori informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5bca4-211">For more information, see the following:</span></span>

- [<span data-ttu-id="5bca4-212">Distribuire il gestore delle statistiche per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5bca4-212">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)

- [<span data-ttu-id="5bca4-213">Aggiornare il gestore delle statistiche per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5bca4-213">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)

- [<span data-ttu-id="5bca4-214">Risoluzione dei problemi del gestore delle statistiche per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5bca4-214">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
