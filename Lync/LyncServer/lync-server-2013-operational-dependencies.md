---
title: 'Lync Server 2013: dipendenze operative'
description: 'Lync Server 2013: dipendenze operative.'
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
ms.openlocfilehash: 4e240981f5dfded7c27f123c8483794ea3ffedff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579192"
---
# <a name="operational-dependencies-in-lync-server-2013"></a><span data-ttu-id="ff864-103">Dipendenze operative in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff864-103">Operational dependencies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff864-104">_**Ultimo argomento modificato:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="ff864-104">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="ff864-105">L'architettura di riferimento descritta in questo documento consentirà di disporre di una distribuzione di Lync Server 2013 che non solo si adatta ai requisiti dell'organizzazione, ma è stata architettata secondo le procedure consigliate di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ff864-105">The Reference Architecture discussed in this document will help ensure that you have a Lync Server 2013 deployment that not only scales to the organization’s requirements but is architected as per Microsoft best practices.</span></span> <span data-ttu-id="ff864-106">È possibile che l'implementazione di Lync Server 2013 sia un servizio dinamico e, come qualsiasi altro servizio nell'organizzazione, richiede ancora il monitoraggio e la gestione proattiva per mantenere elevato il livello di disponibilità del servizio e la qualità del servizio per l'azienda.</span><span class="sxs-lookup"><span data-stu-id="ff864-106">Be that as it may the Lync Server 2013 implementation is a dynamic service and like any other service in the enterprise still requires monitoring and proactive management to maintain high level of service availability and service quality to the business.</span></span>

<span data-ttu-id="ff864-107">Dato che Lync Server 2013 diventa profondamente radicato nell'attività quotidiana dell'organizzazione, è importante che il servizio sia gestito da una gestione accurata e tangibile del livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="ff864-107">As Lync Server 2013 becomes deeply ingrained in the organization’s everyday business it is important that the service be managed by accurate and tangible service level management.</span></span> <span data-ttu-id="ff864-108">L'architettura di sistema di Lync può diventare complessa e molto integrata e per mantenere una gestione dei livelli di servizio efficace e stabilire SLA per Lync Server 2013 diventa fondamentale comprendere le dipendenze del sistema su altre piattaforme e server.</span><span class="sxs-lookup"><span data-stu-id="ff864-108">The Lync system architecture can become complex and very integrated and in order to maintain effective service level management and establish SLAs for Lync Server 2013 it becomes critical to understand the system’s dependencies on other platforms and servers.</span></span> <span data-ttu-id="ff864-109">Altrettanto importante è tenere presente che i servizi aziendali, ad esempio le applicazioni integrate vocali e UC, diventano dipendenti da Lync.</span><span class="sxs-lookup"><span data-stu-id="ff864-109">Equally important is to note which business services, such as voice and UC integrated applications, become dependent on Lync.</span></span>

<span data-ttu-id="ff864-110">Lync Server 2013 deve essere stabilito notando tutte le dipendenze suddette.</span><span class="sxs-lookup"><span data-stu-id="ff864-110">Lync Server 2013 must be established noting all the said dependencies.</span></span> <span data-ttu-id="ff864-111">La mappa dei servizi consentirà di formulare un SLA tra Lync e il relativo servizio dipendente e di fornire un punto di partenza per la negoziazione del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="ff864-111">The service map will allow you to formulate a SLA between Lync and its dependent service and provide a starting place for SLA negotiation.</span></span>

<span data-ttu-id="ff864-112">Nella tabella seguente sono elencati i servizi di dipendenza tipici per un'infrastruttura di Lync.</span><span class="sxs-lookup"><span data-stu-id="ff864-112">The following table lists the typical dependency services for a Lync infrastructure.</span></span> <span data-ttu-id="ff864-113">Ognuna di queste tecnologie deve disporre di un monitoraggio proattivo.</span><span class="sxs-lookup"><span data-stu-id="ff864-113">Each of these technologies should have its own proactive monitoring.</span></span>

### <a name="typical-dependency-services"></a><span data-ttu-id="ff864-114">Servizi di dipendenza tipici</span><span class="sxs-lookup"><span data-stu-id="ff864-114">Typical dependency services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff864-115">Servizio di dipendenza</span><span class="sxs-lookup"><span data-stu-id="ff864-115">Dependency Service</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff864-116">Sistemi operativi</span><span class="sxs-lookup"><span data-stu-id="ff864-116">Operating systems</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff864-117">Hardware del server</span><span class="sxs-lookup"><span data-stu-id="ff864-117">Server Hardware</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff864-118">Active Directory</span><span class="sxs-lookup"><span data-stu-id="ff864-118">Active Directory</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff864-119">Infrastruttura a chiave pubblica</span><span class="sxs-lookup"><span data-stu-id="ff864-119">Public Key Infrastructure</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff864-120">Domain Naming Service</span><span class="sxs-lookup"><span data-stu-id="ff864-120">Domain Naming Service</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff864-121">Servizi di database</span><span class="sxs-lookup"><span data-stu-id="ff864-121">Database Services</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff864-122">Servizi di archiviazione</span><span class="sxs-lookup"><span data-stu-id="ff864-122">Storage Services</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff864-123">Gestione del sistema – monitoraggio e distribuzione</span><span class="sxs-lookup"><span data-stu-id="ff864-123">System Management – Monitoring and distribution</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff864-124">Servizi di sicurezza-antivirus</span><span class="sxs-lookup"><span data-stu-id="ff864-124">Security Services - Antivirus</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff864-125">Infrastruttura di rete-Internet</span><span class="sxs-lookup"><span data-stu-id="ff864-125">Network Infrastructure - Internet</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff864-126">Infrastruttura di rete – interno (LAN/WAN)</span><span class="sxs-lookup"><span data-stu-id="ff864-126">Network Infrastructure – Internal (LAN/WAN)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff864-127">Infrastruttura di telefonia-IP-PBX e gateway</span><span class="sxs-lookup"><span data-stu-id="ff864-127">Telephony Infrastructure – IP-PBX and Gateways</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff864-128">Servizi cloud</span><span class="sxs-lookup"><span data-stu-id="ff864-128">Cloud Services</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ff864-129">Si presuppone che l'organizzazione sia operativamente matura nell'esercizio delle funzioni di base di gestione del livello di servizio, ad esempio la gestione delle modifiche, degli incidenti e delle rilasci come prescritto dal MOF.</span><span class="sxs-lookup"><span data-stu-id="ff864-129">It is assumed that the organization is operationally mature in exercising basic service level management functions such as change, incident and release management as prescribed by the MOF.</span></span> <span data-ttu-id="ff864-130">La soluzione Lync deve essere adottata da queste funzioni ed essere soggetta agli stessi processi di gestione operativi.</span><span class="sxs-lookup"><span data-stu-id="ff864-130">The Lync solution should be adopted by these functions and become subject to the same operational management processes.</span></span>

<span data-ttu-id="ff864-131">Basandosi sulle informazioni ottenute in alto, ora si ha una maggiore comprensione di ciò che può influire sul servizio Lync nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ff864-131">Building on the information obtained above we now have a greater understanding of what can impact the Lync service in the enterprise.</span></span> <span data-ttu-id="ff864-132">Per garantire la disponibilità e la qualità dei servizi di Lync Server 2013, è necessario che gli strumenti di monitoraggio seguenti accompagnino la distribuzione dell'architettura di riferimento:</span><span class="sxs-lookup"><span data-stu-id="ff864-132">To help ensure Lync Server 2013 service availability and quality, the following monitoring tools must accompany the reference architecture deployment:</span></span>

### <a name="monitoring-tools"></a><span data-ttu-id="ff864-133">Strumenti di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="ff864-133">Monitoring tools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff864-134">Componente</span><span class="sxs-lookup"><span data-stu-id="ff864-134">Component</span></span></th>
<th><span data-ttu-id="ff864-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ff864-135">Description</span></span></th>
<th><span data-ttu-id="ff864-136">Sito applicabile</span><span class="sxs-lookup"><span data-stu-id="ff864-136">Applicable Site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff864-137">Server di monitoraggio di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff864-137">Lync Server 2013 Monitoring Server</span></span></p></td>
<td><p><span data-ttu-id="ff864-138">Distribuire almeno un ruolo del server di monitoraggio di Lync Server 2013 per sito centrale e configurare il pacchetto di report su qualità di esperienza (QoE).</span><span class="sxs-lookup"><span data-stu-id="ff864-138">Deploy at least one Lync Server 2013 Monitoring Server role per Central site and configure Quality of Experience (QoE) Reporting Pack.</span></span></p>
<p><span data-ttu-id="ff864-139">Per ulteriori informazioni, vedere la documentazione relativa alla distribuzione di Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="ff864-139">Refer to the Lync Server 2013 Deployment documentation for further details:</span></span></p>
<p><span data-ttu-id="ff864-140"><a href="lync-server-2013-deploying-monitoring.md">Distribuzione del monitoraggio in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ff864-140"><a href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ff864-141">Siti centrali</span><span class="sxs-lookup"><span data-stu-id="ff864-141">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="ff864-142">Legare ogni pool all'istanza più vicina del ruolo Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="ff864-142">Tether each pool to its nearest instance of the Monitoring Server role.</span></span></p></td>
<td><p><span data-ttu-id="ff864-143">Siti centrali</span><span class="sxs-lookup"><span data-stu-id="ff864-143">Central sites</span></span></p>
<p><span data-ttu-id="ff864-144">Siti di succursale</span><span class="sxs-lookup"><span data-stu-id="ff864-144">Branch sites</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff864-145">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="ff864-145">System Center Operations Manager 2012</span></span></p></td>
<td><p><span data-ttu-id="ff864-146">System Center Operations Manager 2012 con Microsoft Lync Server 2013 Management Pack (MP) importato.</span><span class="sxs-lookup"><span data-stu-id="ff864-146">System Center Operations Manager 2012 with the Microsoft Lync Server 2013 Management Pack (MP) imported.</span></span></p>
<p><span data-ttu-id="ff864-147">Il Management Pack implementa il registro eventi tradizionale e la strumentazione basata sui contatori delle prestazioni viene utilizzata e abilitando la strumentazione appena disponibile in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ff864-147">The Management Pack implements traditional Event Log and Performance counter based instrumentation is utilized as well as enabling newly available instrumentation in Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="ff864-148">Siti centrali</span><span class="sxs-lookup"><span data-stu-id="ff864-148">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="ff864-149">Assicurarsi che l'individuazione centrale per l'individuazione di ruoli e componenti che devono essere monitorati sia completata automaticamente in base a uno script di individuazione centrale che legge il documento della topologia pubblicato nel database di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="ff864-149">Make sure that Central Discovery to discovery of roles and components that need to be monitored are automatically completed based on a central discovery script that reads the topology document published in Central Management Database.</span></span></p></td>
<td><p><span data-ttu-id="ff864-150">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="ff864-150">Central Site</span></span></p>
<p><span data-ttu-id="ff864-151">Sito di succursale</span><span class="sxs-lookup"><span data-stu-id="ff864-151">Branch Site</span></span></p>
<p><span data-ttu-id="ff864-152">Sito perimetrale</span><span class="sxs-lookup"><span data-stu-id="ff864-152">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="ff864-153">Distribuire gli agenti di System Centre Operations Manager 2007 a tutti i server distribuiti che eseguono Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff864-153">Deploy System Centre Operations Manager 2007 agents to all deployed servers running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="ff864-154">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="ff864-154">Central Site</span></span></p>
<p><span data-ttu-id="ff864-155">Sito di succursale</span><span class="sxs-lookup"><span data-stu-id="ff864-155">Branch Site</span></span></p>
<p><span data-ttu-id="ff864-156">Sito perimetrale</span><span class="sxs-lookup"><span data-stu-id="ff864-156">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="ff864-157">Verificare che gli avvisi con priorità siano configurati per la notifica:</span><span class="sxs-lookup"><span data-stu-id="ff864-157">Make sure Prioritized Alerts are configured for notification:</span></span></p>
<p><span data-ttu-id="ff864-158">Avvisi con priorità alta</span><span class="sxs-lookup"><span data-stu-id="ff864-158">High Priority Alerts</span></span></p>
<p><span data-ttu-id="ff864-159">Avvisi di priorità media</span><span class="sxs-lookup"><span data-stu-id="ff864-159">Medium Priority Alerts</span></span></p>
<p><span data-ttu-id="ff864-160">Altri avvisi.</span><span class="sxs-lookup"><span data-stu-id="ff864-160">Other Alerts.</span></span></p></td>
<td><p><span data-ttu-id="ff864-161">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="ff864-161">Central Site</span></span></p>
<p><span data-ttu-id="ff864-162">Sito di succursale</span><span class="sxs-lookup"><span data-stu-id="ff864-162">Branch Site</span></span></p>
<p><span data-ttu-id="ff864-163">Sito perimetrale</span><span class="sxs-lookup"><span data-stu-id="ff864-163">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="ff864-164">Configurare il monitoraggio delle porte per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ff864-164">Configure Port monitoring for your deployment.</span></span></p></td>
<td><p><span data-ttu-id="ff864-165">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="ff864-165">Central Site</span></span></p>
<p><span data-ttu-id="ff864-166">Sito di succursale</span><span class="sxs-lookup"><span data-stu-id="ff864-166">Branch Site</span></span></p>
<p><span data-ttu-id="ff864-167">Sito perimetrale</span><span class="sxs-lookup"><span data-stu-id="ff864-167">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="ff864-168">Configurare il monitoraggio degli URL per la distribuzione</span><span class="sxs-lookup"><span data-stu-id="ff864-168">Configure URL monitoring for your deployment</span></span></p></td>
<td><p><span data-ttu-id="ff864-169">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="ff864-169">Central Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff864-170">Integrazione di Lync e System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="ff864-170">Lync and System Center Operations Manager integration</span></span></p></td>
<td><p><span data-ttu-id="ff864-171">Distribuire l'affidabilità delle chiamate e la qualità multimediale MonitoringCall affidabilità e monitoraggio della qualità multimediale utilizzare il computer Monitoring Server come nodo Watcher per monitorare l'affidabilità delle chiamate e la qualità multimediale di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ff864-171">Deploy Call Reliability and Media Quality MonitoringCall reliability and media quality monitoring use the Monitoring Server computer as their watcher node to monitor call reliability and media quality of Lync Server.</span></span> <span data-ttu-id="ff864-172">Entrambe queste funzionalità eseguono una query sui database del Monitoring Server per eseguire l'analisi.</span><span class="sxs-lookup"><span data-stu-id="ff864-172">Both of these features query the Monitoring Server databases to do analysis.</span></span></p></td>
<td><p><span data-ttu-id="ff864-173">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="ff864-173">Central Site</span></span></p>
<p><span data-ttu-id="ff864-174">Sito di succursale</span><span class="sxs-lookup"><span data-stu-id="ff864-174">Branch Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="ff864-175">Verificare che le soglie di avviso per la qualità multimediale siano configurate correttamente.</span><span class="sxs-lookup"><span data-stu-id="ff864-175">Ensure Media Quality warning thresholds are accurately configured.</span></span> <span data-ttu-id="ff864-176">Nella tabella seguente vengono indicati i punteggi massimi di opinione della rete media per codec.</span><span class="sxs-lookup"><span data-stu-id="ff864-176">The following table indicates the maximum Network Mean Opinion Scores by Codec.</span></span> <span data-ttu-id="ff864-177">In produzione questi punteggi devono essere monitorati per un periodo stabilito e devono essere stabilite soglie accettabili in base ai punteggi di NMOS specifici dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ff864-177">In production these scores should be monitored for a set period and acceptable thresholds must be established based on the organization specific NMOS scores.</span></span></p></td>
<td><p><span data-ttu-id="ff864-178">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="ff864-178">Central Site</span></span></p>
<p><span data-ttu-id="ff864-179">Sito di succursale</span><span class="sxs-lookup"><span data-stu-id="ff864-179">Branch Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff864-180">Analizzatore delle transazioni sintetiche di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff864-180">Lync Server 2013 Synthetic Transaction Watcher</span></span></p></td>
<td><p><span data-ttu-id="ff864-181">Distribuire un server Lync dedicato come Watcher delle transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="ff864-181">Deploy a dedicated Lync Server to be a synthetic transaction watcher.</span></span></p>
<p><span data-ttu-id="ff864-182">Le transazioni sintetiche sono cmdlet di Lync Server 2013 di Windows PowerShell che vengono attivati automaticamente dal Management Pack su un intervallo predefinito.</span><span class="sxs-lookup"><span data-stu-id="ff864-182">Synthetic transactions are Lync Server 2013 Windows PowerShell cmdlets that are automatically triggered by the management pack on a predefined interval.</span></span> <span data-ttu-id="ff864-183">Queste operazioni vengono eseguite in un nodo di monitoraggio delle transazioni sintetico che è un server designato dall'amministratore responsabile dell'individuazione e dell'esecuzione dei token di servizio per ogni pool.</span><span class="sxs-lookup"><span data-stu-id="ff864-183">These are executed on a synthetic transaction watcher node which is an administrator designated server responsible for discovery and execution of STs for each pool.</span></span></p>
<p><span data-ttu-id="ff864-184">Non è consigliabile utilizzare un server Microsoft Lync Server 2013 esistente come nodo di Watcher delle transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="ff864-184">We do not recommend that you use an existing Microsoft Lync Server 2013 server as a synthetic transaction watcher node.</span></span> <span data-ttu-id="ff864-185">Ciò è dovuto ai requisiti di utilizzo della CPU e della memoria elevati per l'esecuzione delle STs.</span><span class="sxs-lookup"><span data-stu-id="ff864-185">This is due to the high CPU/memory usage requirements for running STs.</span></span> <span data-ttu-id="ff864-186">Utilizzare un nuovo computer server (o un server virtuale) per il nodo Watcher delle transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="ff864-186">Use a new server computer (or a virtual server) for the synthetic transaction watcher node.</span></span></p></td>
<td><p><span data-ttu-id="ff864-187">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="ff864-187">Central Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="ff864-188">Nodo di Watcher per la distribuzione di transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="ff864-188">Deploying synthetic transactions watcher node.</span></span></p>
<p><span data-ttu-id="ff864-189">Fare riferimento al documento MonitoringCS_withSCOM.docx dalla documentazione di UCTAP Connect.</span><span class="sxs-lookup"><span data-stu-id="ff864-189">Refer to the MonitoringCS_withSCOM.docx document from UCTAP connect documentation.</span></span></p></td>
<td><p><span data-ttu-id="ff864-190">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="ff864-190">Central Site</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a><span data-ttu-id="ff864-191">Massimi punteggi MOS di rete per codec</span><span class="sxs-lookup"><span data-stu-id="ff864-191">Maximum Network MOS scores per codec</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff864-192">Scenario</span><span class="sxs-lookup"><span data-stu-id="ff864-192">Scenario</span></span></th>
<th><span data-ttu-id="ff864-193">Codec</span><span class="sxs-lookup"><span data-stu-id="ff864-193">Codec</span></span></th>
<th><span data-ttu-id="ff864-194">Max NMOS</span><span class="sxs-lookup"><span data-stu-id="ff864-194">Max NMOS</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff864-195">Chiamata UC-UC</span><span class="sxs-lookup"><span data-stu-id="ff864-195">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="ff864-196">RTAudio WB</span><span class="sxs-lookup"><span data-stu-id="ff864-196">RTAudio WB</span></span></p></td>
<td><p><span data-ttu-id="ff864-197">4.10</span><span class="sxs-lookup"><span data-stu-id="ff864-197">4.10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff864-198">Chiamata UC-UC</span><span class="sxs-lookup"><span data-stu-id="ff864-198">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="ff864-199">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="ff864-199">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="ff864-200">2,95</span><span class="sxs-lookup"><span data-stu-id="ff864-200">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff864-201">Conferenza telefonica</span><span class="sxs-lookup"><span data-stu-id="ff864-201">Conference call</span></span></p></td>
<td><p><span data-ttu-id="ff864-202">Sirena</span><span class="sxs-lookup"><span data-stu-id="ff864-202">Siren</span></span></p></td>
<td><p><span data-ttu-id="ff864-203">3,72</span><span class="sxs-lookup"><span data-stu-id="ff864-203">3.72</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff864-204">Chiamata UC-PSTN</span><span class="sxs-lookup"><span data-stu-id="ff864-204">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="ff864-205">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="ff864-205">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="ff864-206">2,95</span><span class="sxs-lookup"><span data-stu-id="ff864-206">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff864-207">Chiamata UC-PSTN</span><span class="sxs-lookup"><span data-stu-id="ff864-207">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="ff864-208">G-711</span><span class="sxs-lookup"><span data-stu-id="ff864-208">G-711</span></span></p></td>
<td><p><span data-ttu-id="ff864-209">3,61</span><span class="sxs-lookup"><span data-stu-id="ff864-209">3.61</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ff864-210">Al di sopra delle attività di monitoraggio pro-attive precedenti, le attività di manutenzione devono essere eseguite per i siti centrali, perimetrali e di succursale su base giornaliera, settimanale e mensile ricorrenti, come definito nella Guida alle operazioni di Lync RA.</span><span class="sxs-lookup"><span data-stu-id="ff864-210">Over and above the previous pro-active monitoring activities, maintenance tasks should be executed for Central, Edge and Branch sites on a recurring daily, weekly and monthly basis as defined in the Lync RA Operations Guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

