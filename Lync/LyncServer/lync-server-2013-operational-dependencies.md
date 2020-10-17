---
title: 'Lync Server 2013: dipendenze operative'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Operational dependencies
ms:assetid: 450b6be2-7fb3-47d7-8b0b-c05faa331e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720559(v=OCS.15)
ms:contentKeyID: 63969597
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e506fbbe204b7248396c25c3728556c61681cbf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526573"
---
# <a name="operational-dependencies-in-lync-server-2013"></a><span data-ttu-id="c8739-102">Dipendenze operative in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8739-102">Operational dependencies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8739-103">_**Ultimo argomento modificato:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="c8739-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="c8739-104">L'architettura di riferimento descritta in questo documento consentirà di disporre di una distribuzione di Lync Server 2013 che non solo si adatta ai requisiti dell'organizzazione, ma è stata architettata secondo le procedure consigliate di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c8739-104">The Reference Architecture discussed in this document will help ensure that you have a Lync Server 2013 deployment that not only scales to the organization’s requirements but is architected as per Microsoft best practices.</span></span> <span data-ttu-id="c8739-105">È possibile che l'implementazione di Lync Server 2013 sia un servizio dinamico e, come qualsiasi altro servizio nell'organizzazione, richiede ancora il monitoraggio e la gestione proattiva per mantenere elevato il livello di disponibilità del servizio e la qualità del servizio per l'azienda.</span><span class="sxs-lookup"><span data-stu-id="c8739-105">Be that as it may the Lync Server 2013 implementation is a dynamic service and like any other service in the enterprise still requires monitoring and proactive management to maintain high level of service availability and service quality to the business.</span></span>

<span data-ttu-id="c8739-106">Dato che Lync Server 2013 diventa profondamente radicato nell'attività quotidiana dell'organizzazione, è importante che il servizio sia gestito da una gestione accurata e tangibile del livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="c8739-106">As Lync Server 2013 becomes deeply ingrained in the organization’s everyday business it is important that the service be managed by accurate and tangible service level management.</span></span> <span data-ttu-id="c8739-107">L'architettura di sistema di Lync può diventare complessa e molto integrata e per mantenere una gestione dei livelli di servizio efficace e stabilire SLA per Lync Server 2013 diventa fondamentale comprendere le dipendenze del sistema su altre piattaforme e server.</span><span class="sxs-lookup"><span data-stu-id="c8739-107">The Lync system architecture can become complex and very integrated and in order to maintain effective service level management and establish SLAs for Lync Server 2013 it becomes critical to understand the system’s dependencies on other platforms and servers.</span></span> <span data-ttu-id="c8739-108">Altrettanto importante è tenere presente che i servizi aziendali, ad esempio le applicazioni integrate vocali e UC, diventano dipendenti da Lync.</span><span class="sxs-lookup"><span data-stu-id="c8739-108">Equally important is to note which business services, such as voice and UC integrated applications, become dependent on Lync.</span></span>

<span data-ttu-id="c8739-109">Lync Server 2013 deve essere stabilito notando tutte le dipendenze suddette.</span><span class="sxs-lookup"><span data-stu-id="c8739-109">Lync Server 2013 must be established noting all the said dependencies.</span></span> <span data-ttu-id="c8739-110">La mappa dei servizi consentirà di formulare un SLA tra Lync e il relativo servizio dipendente e di fornire un punto di partenza per la negoziazione del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="c8739-110">The service map will allow you to formulate a SLA between Lync and its dependent service and provide a starting place for SLA negotiation.</span></span>

<span data-ttu-id="c8739-111">Nella tabella seguente sono elencati i servizi di dipendenza tipici per un'infrastruttura di Lync.</span><span class="sxs-lookup"><span data-stu-id="c8739-111">The following table lists the typical dependency services for a Lync infrastructure.</span></span> <span data-ttu-id="c8739-112">Ognuna di queste tecnologie deve disporre di un monitoraggio proattivo.</span><span class="sxs-lookup"><span data-stu-id="c8739-112">Each of these technologies should have its own proactive monitoring.</span></span>

### <a name="typical-dependency-services"></a><span data-ttu-id="c8739-113">Servizi di dipendenza tipici</span><span class="sxs-lookup"><span data-stu-id="c8739-113">Typical dependency services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8739-114">Servizio di dipendenza</span><span class="sxs-lookup"><span data-stu-id="c8739-114">Dependency Service</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8739-115">Sistemi operativi</span><span class="sxs-lookup"><span data-stu-id="c8739-115">Operating systems</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8739-116">Hardware del server</span><span class="sxs-lookup"><span data-stu-id="c8739-116">Server Hardware</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8739-117">Active Directory</span><span class="sxs-lookup"><span data-stu-id="c8739-117">Active Directory</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8739-118">Infrastruttura a chiave pubblica</span><span class="sxs-lookup"><span data-stu-id="c8739-118">Public Key Infrastructure</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8739-119">Domain Naming Service</span><span class="sxs-lookup"><span data-stu-id="c8739-119">Domain Naming Service</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8739-120">Servizi di database</span><span class="sxs-lookup"><span data-stu-id="c8739-120">Database Services</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8739-121">Servizi di archiviazione</span><span class="sxs-lookup"><span data-stu-id="c8739-121">Storage Services</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8739-122">Gestione del sistema – monitoraggio e distribuzione</span><span class="sxs-lookup"><span data-stu-id="c8739-122">System Management – Monitoring and distribution</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8739-123">Servizi di sicurezza-antivirus</span><span class="sxs-lookup"><span data-stu-id="c8739-123">Security Services - Antivirus</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8739-124">Infrastruttura di rete-Internet</span><span class="sxs-lookup"><span data-stu-id="c8739-124">Network Infrastructure - Internet</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8739-125">Infrastruttura di rete – interno (LAN/WAN)</span><span class="sxs-lookup"><span data-stu-id="c8739-125">Network Infrastructure – Internal (LAN/WAN)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8739-126">Infrastruttura di telefonia-IP-PBX e gateway</span><span class="sxs-lookup"><span data-stu-id="c8739-126">Telephony Infrastructure – IP-PBX and Gateways</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8739-127">Servizi cloud</span><span class="sxs-lookup"><span data-stu-id="c8739-127">Cloud Services</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c8739-128">Si presuppone che l'organizzazione sia operativamente matura nell'esercizio delle funzioni di base di gestione del livello di servizio, ad esempio la gestione delle modifiche, degli incidenti e delle rilasci come prescritto dal MOF.</span><span class="sxs-lookup"><span data-stu-id="c8739-128">It is assumed that the organization is operationally mature in exercising basic service level management functions such as change, incident and release management as prescribed by the MOF.</span></span> <span data-ttu-id="c8739-129">La soluzione Lync deve essere adottata da queste funzioni ed essere soggetta agli stessi processi di gestione operativi.</span><span class="sxs-lookup"><span data-stu-id="c8739-129">The Lync solution should be adopted by these functions and become subject to the same operational management processes.</span></span>

<span data-ttu-id="c8739-130">Basandosi sulle informazioni ottenute in alto, ora si ha una maggiore comprensione di ciò che può influire sul servizio Lync nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c8739-130">Building on the information obtained above we now have a greater understanding of what can impact the Lync service in the enterprise.</span></span> <span data-ttu-id="c8739-131">Per garantire la disponibilità e la qualità dei servizi di Lync Server 2013, è necessario che gli strumenti di monitoraggio seguenti accompagnino la distribuzione dell'architettura di riferimento:</span><span class="sxs-lookup"><span data-stu-id="c8739-131">To help ensure Lync Server 2013 service availability and quality, the following monitoring tools must accompany the reference architecture deployment:</span></span>

### <a name="monitoring-tools"></a><span data-ttu-id="c8739-132">Strumenti di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="c8739-132">Monitoring tools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8739-133">Componente</span><span class="sxs-lookup"><span data-stu-id="c8739-133">Component</span></span></th>
<th><span data-ttu-id="c8739-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8739-134">Description</span></span></th>
<th><span data-ttu-id="c8739-135">Sito applicabile</span><span class="sxs-lookup"><span data-stu-id="c8739-135">Applicable Site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8739-136">Server di monitoraggio di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8739-136">Lync Server 2013 Monitoring Server</span></span></p></td>
<td><p><span data-ttu-id="c8739-137">Distribuire almeno un ruolo del server di monitoraggio di Lync Server 2013 per sito centrale e configurare il pacchetto di report su qualità di esperienza (QoE).</span><span class="sxs-lookup"><span data-stu-id="c8739-137">Deploy at least one Lync Server 2013 Monitoring Server role per Central site and configure Quality of Experience (QoE) Reporting Pack.</span></span></p>
<p><span data-ttu-id="c8739-138">Per ulteriori informazioni, vedere la documentazione relativa alla distribuzione di Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="c8739-138">Refer to the Lync Server 2013 Deployment documentation for further details:</span></span></p>
<p><span data-ttu-id="c8739-139"><a href="lync-server-2013-deploying-monitoring.md">Distribuzione del monitoraggio in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c8739-139"><a href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c8739-140">Siti centrali</span><span class="sxs-lookup"><span data-stu-id="c8739-140">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="c8739-141">Legare ogni pool all'istanza più vicina del ruolo Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="c8739-141">Tether each pool to its nearest instance of the Monitoring Server role.</span></span></p></td>
<td><p><span data-ttu-id="c8739-142">Siti centrali</span><span class="sxs-lookup"><span data-stu-id="c8739-142">Central sites</span></span></p>
<p><span data-ttu-id="c8739-143">Siti di succursale</span><span class="sxs-lookup"><span data-stu-id="c8739-143">Branch sites</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8739-144">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="c8739-144">System Center Operations Manager 2012</span></span></p></td>
<td><p><span data-ttu-id="c8739-145">System Center Operations Manager 2012 con Microsoft Lync Server 2013 Management Pack (MP) importato.</span><span class="sxs-lookup"><span data-stu-id="c8739-145">System Center Operations Manager 2012 with the Microsoft Lync Server 2013 Management Pack (MP) imported.</span></span></p>
<p><span data-ttu-id="c8739-146">Il Management Pack implementa il registro eventi tradizionale e la strumentazione basata sui contatori delle prestazioni viene utilizzata e abilitando la strumentazione appena disponibile in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c8739-146">The Management Pack implements traditional Event Log and Performance counter based instrumentation is utilized as well as enabling newly available instrumentation in Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="c8739-147">Siti centrali</span><span class="sxs-lookup"><span data-stu-id="c8739-147">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="c8739-148">Assicurarsi che l'individuazione centrale per l'individuazione di ruoli e componenti che devono essere monitorati sia completata automaticamente in base a uno script di individuazione centrale che legge il documento della topologia pubblicato nel database di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="c8739-148">Make sure that Central Discovery to discovery of roles and components that need to be monitored are automatically completed based on a central discovery script that reads the topology document published in Central Management Database.</span></span></p></td>
<td><p><span data-ttu-id="c8739-149">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="c8739-149">Central Site</span></span></p>
<p><span data-ttu-id="c8739-150">Sito di succursale</span><span class="sxs-lookup"><span data-stu-id="c8739-150">Branch Site</span></span></p>
<p><span data-ttu-id="c8739-151">Sito perimetrale</span><span class="sxs-lookup"><span data-stu-id="c8739-151">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="c8739-152">Distribuire gli agenti di System Centre Operations Manager 2007 a tutti i server distribuiti che eseguono Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c8739-152">Deploy System Centre Operations Manager 2007 agents to all deployed servers running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="c8739-153">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="c8739-153">Central Site</span></span></p>
<p><span data-ttu-id="c8739-154">Sito di succursale</span><span class="sxs-lookup"><span data-stu-id="c8739-154">Branch Site</span></span></p>
<p><span data-ttu-id="c8739-155">Sito perimetrale</span><span class="sxs-lookup"><span data-stu-id="c8739-155">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="c8739-156">Verificare che gli avvisi con priorità siano configurati per la notifica:</span><span class="sxs-lookup"><span data-stu-id="c8739-156">Make sure Prioritized Alerts are configured for notification:</span></span></p>
<p><span data-ttu-id="c8739-157">Avvisi con priorità alta</span><span class="sxs-lookup"><span data-stu-id="c8739-157">High Priority Alerts</span></span></p>
<p><span data-ttu-id="c8739-158">Avvisi di priorità media</span><span class="sxs-lookup"><span data-stu-id="c8739-158">Medium Priority Alerts</span></span></p>
<p><span data-ttu-id="c8739-159">Altri avvisi.</span><span class="sxs-lookup"><span data-stu-id="c8739-159">Other Alerts.</span></span></p></td>
<td><p><span data-ttu-id="c8739-160">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="c8739-160">Central Site</span></span></p>
<p><span data-ttu-id="c8739-161">Sito di succursale</span><span class="sxs-lookup"><span data-stu-id="c8739-161">Branch Site</span></span></p>
<p><span data-ttu-id="c8739-162">Sito perimetrale</span><span class="sxs-lookup"><span data-stu-id="c8739-162">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="c8739-163">Configurare il monitoraggio delle porte per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c8739-163">Configure Port monitoring for your deployment.</span></span></p></td>
<td><p><span data-ttu-id="c8739-164">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="c8739-164">Central Site</span></span></p>
<p><span data-ttu-id="c8739-165">Sito di succursale</span><span class="sxs-lookup"><span data-stu-id="c8739-165">Branch Site</span></span></p>
<p><span data-ttu-id="c8739-166">Sito perimetrale</span><span class="sxs-lookup"><span data-stu-id="c8739-166">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="c8739-167">Configurare il monitoraggio degli URL per la distribuzione</span><span class="sxs-lookup"><span data-stu-id="c8739-167">Configure URL monitoring for your deployment</span></span></p></td>
<td><p><span data-ttu-id="c8739-168">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="c8739-168">Central Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8739-169">Integrazione di Lync e System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="c8739-169">Lync and System Center Operations Manager integration</span></span></p></td>
<td><p><span data-ttu-id="c8739-170">Distribuire l'affidabilità delle chiamate e la qualità multimediale MonitoringCall affidabilità e monitoraggio della qualità multimediale utilizzare il computer Monitoring Server come nodo Watcher per monitorare l'affidabilità delle chiamate e la qualità multimediale di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c8739-170">Deploy Call Reliability and Media Quality MonitoringCall reliability and media quality monitoring use the Monitoring Server computer as their watcher node to monitor call reliability and media quality of Lync Server.</span></span> <span data-ttu-id="c8739-171">Entrambe queste funzionalità eseguono una query sui database del Monitoring Server per eseguire l'analisi.</span><span class="sxs-lookup"><span data-stu-id="c8739-171">Both of these features query the Monitoring Server databases to do analysis.</span></span></p></td>
<td><p><span data-ttu-id="c8739-172">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="c8739-172">Central Site</span></span></p>
<p><span data-ttu-id="c8739-173">Sito di succursale</span><span class="sxs-lookup"><span data-stu-id="c8739-173">Branch Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="c8739-174">Verificare che le soglie di avviso per la qualità multimediale siano configurate correttamente.</span><span class="sxs-lookup"><span data-stu-id="c8739-174">Ensure Media Quality warning thresholds are accurately configured.</span></span> <span data-ttu-id="c8739-175">Nella tabella seguente vengono indicati i punteggi massimi di opinione della rete media per codec.</span><span class="sxs-lookup"><span data-stu-id="c8739-175">The following table indicates the maximum Network Mean Opinion Scores by Codec.</span></span> <span data-ttu-id="c8739-176">In produzione questi punteggi devono essere monitorati per un periodo stabilito e devono essere stabilite soglie accettabili in base ai punteggi di NMOS specifici dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c8739-176">In production these scores should be monitored for a set period and acceptable thresholds must be established based on the organization specific NMOS scores.</span></span></p></td>
<td><p><span data-ttu-id="c8739-177">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="c8739-177">Central Site</span></span></p>
<p><span data-ttu-id="c8739-178">Sito di succursale</span><span class="sxs-lookup"><span data-stu-id="c8739-178">Branch Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8739-179">Analizzatore delle transazioni sintetiche di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8739-179">Lync Server 2013 Synthetic Transaction Watcher</span></span></p></td>
<td><p><span data-ttu-id="c8739-180">Distribuire un server Lync dedicato come Watcher delle transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="c8739-180">Deploy a dedicated Lync Server to be a synthetic transaction watcher.</span></span></p>
<p><span data-ttu-id="c8739-181">Le transazioni sintetiche sono cmdlet di Lync Server 2013 di Windows PowerShell che vengono attivati automaticamente dal Management Pack su un intervallo predefinito.</span><span class="sxs-lookup"><span data-stu-id="c8739-181">Synthetic transactions are Lync Server 2013 Windows PowerShell cmdlets that are automatically triggered by the management pack on a predefined interval.</span></span> <span data-ttu-id="c8739-182">Queste operazioni vengono eseguite in un nodo di monitoraggio delle transazioni sintetico che è un server designato dall'amministratore responsabile dell'individuazione e dell'esecuzione dei token di servizio per ogni pool.</span><span class="sxs-lookup"><span data-stu-id="c8739-182">These are executed on a synthetic transaction watcher node which is an administrator designated server responsible for discovery and execution of STs for each pool.</span></span></p>
<p><span data-ttu-id="c8739-183">Non è consigliabile utilizzare un server Microsoft Lync Server 2013 esistente come nodo di Watcher delle transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="c8739-183">We do not recommend that you use an existing Microsoft Lync Server 2013 server as a synthetic transaction watcher node.</span></span> <span data-ttu-id="c8739-184">Ciò è dovuto ai requisiti di utilizzo della CPU e della memoria elevati per l'esecuzione delle STs.</span><span class="sxs-lookup"><span data-stu-id="c8739-184">This is due to the high CPU/memory usage requirements for running STs.</span></span> <span data-ttu-id="c8739-185">Utilizzare un nuovo computer server (o un server virtuale) per il nodo Watcher delle transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="c8739-185">Use a new server computer (or a virtual server) for the synthetic transaction watcher node.</span></span></p></td>
<td><p><span data-ttu-id="c8739-186">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="c8739-186">Central Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="c8739-187">Nodo di Watcher per la distribuzione di transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="c8739-187">Deploying synthetic transactions watcher node.</span></span></p>
<p><span data-ttu-id="c8739-188">Fare riferimento al documento MonitoringCS_withSCOM.docx dalla documentazione di UCTAP Connect.</span><span class="sxs-lookup"><span data-stu-id="c8739-188">Refer to the MonitoringCS_withSCOM.docx document from UCTAP connect documentation.</span></span></p></td>
<td><p><span data-ttu-id="c8739-189">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="c8739-189">Central Site</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a><span data-ttu-id="c8739-190">Massimi punteggi MOS di rete per codec</span><span class="sxs-lookup"><span data-stu-id="c8739-190">Maximum Network MOS scores per codec</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8739-191">Scenario</span><span class="sxs-lookup"><span data-stu-id="c8739-191">Scenario</span></span></th>
<th><span data-ttu-id="c8739-192">Codec</span><span class="sxs-lookup"><span data-stu-id="c8739-192">Codec</span></span></th>
<th><span data-ttu-id="c8739-193">Max NMOS</span><span class="sxs-lookup"><span data-stu-id="c8739-193">Max NMOS</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8739-194">Chiamata UC-UC</span><span class="sxs-lookup"><span data-stu-id="c8739-194">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="c8739-195">RTAudio WB</span><span class="sxs-lookup"><span data-stu-id="c8739-195">RTAudio WB</span></span></p></td>
<td><p><span data-ttu-id="c8739-196">4.10</span><span class="sxs-lookup"><span data-stu-id="c8739-196">4.10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8739-197">Chiamata UC-UC</span><span class="sxs-lookup"><span data-stu-id="c8739-197">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="c8739-198">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="c8739-198">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="c8739-199">2,95</span><span class="sxs-lookup"><span data-stu-id="c8739-199">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8739-200">Conferenza telefonica</span><span class="sxs-lookup"><span data-stu-id="c8739-200">Conference call</span></span></p></td>
<td><p><span data-ttu-id="c8739-201">Sirena</span><span class="sxs-lookup"><span data-stu-id="c8739-201">Siren</span></span></p></td>
<td><p><span data-ttu-id="c8739-202">3,72</span><span class="sxs-lookup"><span data-stu-id="c8739-202">3.72</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8739-203">Chiamata UC-PSTN</span><span class="sxs-lookup"><span data-stu-id="c8739-203">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="c8739-204">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="c8739-204">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="c8739-205">2,95</span><span class="sxs-lookup"><span data-stu-id="c8739-205">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8739-206">Chiamata UC-PSTN</span><span class="sxs-lookup"><span data-stu-id="c8739-206">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="c8739-207">G-711</span><span class="sxs-lookup"><span data-stu-id="c8739-207">G-711</span></span></p></td>
<td><p><span data-ttu-id="c8739-208">3,61</span><span class="sxs-lookup"><span data-stu-id="c8739-208">3.61</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c8739-209">Al di sopra delle attività di monitoraggio pro-attive precedenti, le attività di manutenzione devono essere eseguite per i siti centrali, perimetrali e di succursale su base giornaliera, settimanale e mensile ricorrenti, come definito nella Guida alle operazioni di Lync RA.</span><span class="sxs-lookup"><span data-stu-id="c8739-209">Over and above the previous pro-active monitoring activities, maintenance tasks should be executed for Central, Edge and Branch sites on a recurring daily, weekly and monthly basis as defined in the Lync RA Operations Guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

