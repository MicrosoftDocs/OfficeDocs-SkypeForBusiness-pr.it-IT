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
ms.openlocfilehash: 26e7de821dee778d4b0b1e9aa105669635abaf6c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="operational-dependencies-in-lync-server-2013"></a><span data-ttu-id="a2c68-102">Dipendenze operative in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2c68-102">Operational dependencies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2c68-103">_**Argomento Ultima modifica:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="a2c68-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="a2c68-104">L'architettura di riferimento discussa in questo documento consentirà di avere una distribuzione di Lync Server 2013 che non solo si adatta ai requisiti dell'organizzazione, ma è stata architettata come per le procedure consigliate Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a2c68-104">The Reference Architecture discussed in this document will help ensure that you have a Lync Server 2013 deployment that not only scales to the organization’s requirements but is architected as per Microsoft best practices.</span></span> <span data-ttu-id="a2c68-105">Sia che l'implementazione di Lync Server 2013 sia un servizio dinamico e, come tutti gli altri servizi dell'organizzazione, richiede ancora il monitoraggio e la gestione proattiva per mantenere un livello elevato di disponibilità del servizio e qualità dei servizi per l'azienda.</span><span class="sxs-lookup"><span data-stu-id="a2c68-105">Be that as it may the Lync Server 2013 implementation is a dynamic service and like any other service in the enterprise still requires monitoring and proactive management to maintain high level of service availability and service quality to the business.</span></span>

<span data-ttu-id="a2c68-106">Dato che Lync Server 2013 diventa profondamente radicato nell'attività quotidiana dell'organizzazione, è importante che il servizio sia gestito da una gestione accurata e tangibile dei livelli di servizio.</span><span class="sxs-lookup"><span data-stu-id="a2c68-106">As Lync Server 2013 becomes deeply ingrained in the organization’s everyday business it is important that the service be managed by accurate and tangible service level management.</span></span> <span data-ttu-id="a2c68-107">L'architettura di sistema di Lync può diventare complessa e molto integrata e per mantenere una gestione efficace dei livelli di servizio e stabilire gli SLA per Lync Server 2013 diventa fondamentale comprendere le dipendenze del sistema in altre piattaforme e server.</span><span class="sxs-lookup"><span data-stu-id="a2c68-107">The Lync system architecture can become complex and very integrated and in order to maintain effective service level management and establish SLAs for Lync Server 2013 it becomes critical to understand the system’s dependencies on other platforms and servers.</span></span> <span data-ttu-id="a2c68-108">Altrettanto importante è tenere presente che i servizi commerciali, come la voce e le applicazioni integrate UC, diventano dipendenti da Lync.</span><span class="sxs-lookup"><span data-stu-id="a2c68-108">Equally important is to note which business services, such as voice and UC integrated applications, become dependent on Lync.</span></span>

<span data-ttu-id="a2c68-109">Lync Server 2013 deve essere stabilito notando tutte le dipendenze suddette.</span><span class="sxs-lookup"><span data-stu-id="a2c68-109">Lync Server 2013 must be established noting all the said dependencies.</span></span> <span data-ttu-id="a2c68-110">La mappa dei servizi consente di formulare un contratto di SLA tra Lync e il servizio dipendente e di creare un punto di partenza per la negoziazione di SLA.</span><span class="sxs-lookup"><span data-stu-id="a2c68-110">The service map will allow you to formulate a SLA between Lync and its dependent service and provide a starting place for SLA negotiation.</span></span>

<span data-ttu-id="a2c68-111">La tabella seguente elenca i servizi di dipendenza tipici per un'infrastruttura Lync.</span><span class="sxs-lookup"><span data-stu-id="a2c68-111">The following table lists the typical dependency services for a Lync infrastructure.</span></span> <span data-ttu-id="a2c68-112">Ognuna di queste tecnologie dovrebbe avere il proprio monitoraggio proattivo.</span><span class="sxs-lookup"><span data-stu-id="a2c68-112">Each of these technologies should have its own proactive monitoring.</span></span>

### <a name="typical-dependency-services"></a><span data-ttu-id="a2c68-113">Servizi di dipendenza tipici</span><span class="sxs-lookup"><span data-stu-id="a2c68-113">Typical dependency services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a2c68-114">Servizio di dipendenza</span><span class="sxs-lookup"><span data-stu-id="a2c68-114">Dependency Service</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2c68-115">Sistemi operativi</span><span class="sxs-lookup"><span data-stu-id="a2c68-115">Operating systems</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c68-116">Hardware del server</span><span class="sxs-lookup"><span data-stu-id="a2c68-116">Server Hardware</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c68-117">Active Directory</span><span class="sxs-lookup"><span data-stu-id="a2c68-117">Active Directory</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c68-118">Infrastruttura a chiave pubblica</span><span class="sxs-lookup"><span data-stu-id="a2c68-118">Public Key Infrastructure</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c68-119">Servizio di denominazione dei domini</span><span class="sxs-lookup"><span data-stu-id="a2c68-119">Domain Naming Service</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c68-120">Servizi di database</span><span class="sxs-lookup"><span data-stu-id="a2c68-120">Database Services</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c68-121">Servizi di archiviazione</span><span class="sxs-lookup"><span data-stu-id="a2c68-121">Storage Services</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c68-122">Gestione di sistemi-monitoraggio e distribuzione</span><span class="sxs-lookup"><span data-stu-id="a2c68-122">System Management – Monitoring and distribution</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c68-123">Servizi di sicurezza-antivirus</span><span class="sxs-lookup"><span data-stu-id="a2c68-123">Security Services - Antivirus</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c68-124">Infrastruttura di rete-Internet</span><span class="sxs-lookup"><span data-stu-id="a2c68-124">Network Infrastructure - Internet</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c68-125">Infrastruttura di rete-interno (LAN/WAN)</span><span class="sxs-lookup"><span data-stu-id="a2c68-125">Network Infrastructure – Internal (LAN/WAN)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c68-126">Infrastruttura di telefonia-IP-PBX e gateway</span><span class="sxs-lookup"><span data-stu-id="a2c68-126">Telephony Infrastructure – IP-PBX and Gateways</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c68-127">Servizi cloud</span><span class="sxs-lookup"><span data-stu-id="a2c68-127">Cloud Services</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a2c68-128">Si presuppone che l'organizzazione sia operativamente matura nell'esercizio di funzioni di base per la gestione dei livelli di servizio, come la gestione delle modifiche, degli incidenti e delle versioni, come prescritto da MOF.</span><span class="sxs-lookup"><span data-stu-id="a2c68-128">It is assumed that the organization is operationally mature in exercising basic service level management functions such as change, incident and release management as prescribed by the MOF.</span></span> <span data-ttu-id="a2c68-129">La soluzione Lync deve essere adottata da queste funzioni e diventare soggetta agli stessi processi di gestione operativa.</span><span class="sxs-lookup"><span data-stu-id="a2c68-129">The Lync solution should be adopted by these functions and become subject to the same operational management processes.</span></span>

<span data-ttu-id="a2c68-130">Basandosi sulle informazioni ottenute in precedenza, ora abbiamo una maggiore comprensione di ciò che può influire sul servizio Lync nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a2c68-130">Building on the information obtained above we now have a greater understanding of what can impact the Lync service in the enterprise.</span></span> <span data-ttu-id="a2c68-131">Per garantire la disponibilità e la qualità dei servizi di Lync Server 2013, gli strumenti di monitoraggio seguenti devono accompagnare la distribuzione dell'architettura di riferimento:</span><span class="sxs-lookup"><span data-stu-id="a2c68-131">To help ensure Lync Server 2013 service availability and quality, the following monitoring tools must accompany the reference architecture deployment:</span></span>

### <a name="monitoring-tools"></a><span data-ttu-id="a2c68-132">Strumenti di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="a2c68-132">Monitoring tools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a2c68-133">Componente</span><span class="sxs-lookup"><span data-stu-id="a2c68-133">Component</span></span></th>
<th><span data-ttu-id="a2c68-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a2c68-134">Description</span></span></th>
<th><span data-ttu-id="a2c68-135">Sito applicabile</span><span class="sxs-lookup"><span data-stu-id="a2c68-135">Applicable Site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2c68-136">Server di monitoraggio di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2c68-136">Lync Server 2013 Monitoring Server</span></span></p></td>
<td><p><span data-ttu-id="a2c68-137">Distribuire almeno un ruolo del server di monitoraggio di Lync Server 2013 per sito centrale e configurare il pacchetto di report di qualità dell'esperienza (QoE).</span><span class="sxs-lookup"><span data-stu-id="a2c68-137">Deploy at least one Lync Server 2013 Monitoring Server role per Central site and configure Quality of Experience (QoE) Reporting Pack.</span></span></p>
<p><span data-ttu-id="a2c68-138">Per ulteriori informazioni, vedere la documentazione relativa alla distribuzione di Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="a2c68-138">Refer to the Lync Server 2013 Deployment documentation for further details:</span></span></p>
<p><span data-ttu-id="a2c68-139"><a href="lync-server-2013-deploying-monitoring.md">Distribuzione del monitoraggio in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a2c68-139"><a href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a2c68-140">Siti centrali</span><span class="sxs-lookup"><span data-stu-id="a2c68-140">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a2c68-141">Legare ogni pool all'istanza più vicina del ruolo del server di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="a2c68-141">Tether each pool to its nearest instance of the Monitoring Server role.</span></span></p></td>
<td><p><span data-ttu-id="a2c68-142">Siti centrali</span><span class="sxs-lookup"><span data-stu-id="a2c68-142">Central sites</span></span></p>
<p><span data-ttu-id="a2c68-143">Siti di succursale</span><span class="sxs-lookup"><span data-stu-id="a2c68-143">Branch sites</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c68-144">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="a2c68-144">System Center Operations Manager 2012</span></span></p></td>
<td><p><span data-ttu-id="a2c68-145">System Center Operations Manager 2012 con il Microsoft Lync Server 2013 Management Pack (MP) importato.</span><span class="sxs-lookup"><span data-stu-id="a2c68-145">System Center Operations Manager 2012 with the Microsoft Lync Server 2013 Management Pack (MP) imported.</span></span></p>
<p><span data-ttu-id="a2c68-146">Il Management Pack implementa il registro eventi tradizionale e la strumentazione basata su contatori delle prestazioni viene utilizzata oltre a consentire la strumentazione appena disponibile in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a2c68-146">The Management Pack implements traditional Event Log and Performance counter based instrumentation is utilized as well as enabling newly available instrumentation in Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="a2c68-147">Siti centrali</span><span class="sxs-lookup"><span data-stu-id="a2c68-147">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a2c68-148">Verificare che l'individuazione centralizzata dell'individuazione di ruoli e componenti da monitorare venga completata automaticamente in base a uno script di individuazione centralizzato che legge il documento di topologia pubblicato nel database di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="a2c68-148">Make sure that Central Discovery to discovery of roles and components that need to be monitored are automatically completed based on a central discovery script that reads the topology document published in Central Management Database.</span></span></p></td>
<td><p><span data-ttu-id="a2c68-149">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="a2c68-149">Central Site</span></span></p>
<p><span data-ttu-id="a2c68-150">Sito filiale</span><span class="sxs-lookup"><span data-stu-id="a2c68-150">Branch Site</span></span></p>
<p><span data-ttu-id="a2c68-151">Sito Edge</span><span class="sxs-lookup"><span data-stu-id="a2c68-151">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="a2c68-152">Distribuire gli agenti di System Centre Operations Manager 2007 a tutti i server distribuiti che utilizzano Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a2c68-152">Deploy System Centre Operations Manager 2007 agents to all deployed servers running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="a2c68-153">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="a2c68-153">Central Site</span></span></p>
<p><span data-ttu-id="a2c68-154">Sito filiale</span><span class="sxs-lookup"><span data-stu-id="a2c68-154">Branch Site</span></span></p>
<p><span data-ttu-id="a2c68-155">Sito Edge</span><span class="sxs-lookup"><span data-stu-id="a2c68-155">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a2c68-156">Verificare che gli avvisi con priorità siano configurati per la notifica:</span><span class="sxs-lookup"><span data-stu-id="a2c68-156">Make sure Prioritized Alerts are configured for notification:</span></span></p>
<p><span data-ttu-id="a2c68-157">Avvisi con priorità alta</span><span class="sxs-lookup"><span data-stu-id="a2c68-157">High Priority Alerts</span></span></p>
<p><span data-ttu-id="a2c68-158">Avvisi di priorità media</span><span class="sxs-lookup"><span data-stu-id="a2c68-158">Medium Priority Alerts</span></span></p>
<p><span data-ttu-id="a2c68-159">Altri avvisi.</span><span class="sxs-lookup"><span data-stu-id="a2c68-159">Other Alerts.</span></span></p></td>
<td><p><span data-ttu-id="a2c68-160">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="a2c68-160">Central Site</span></span></p>
<p><span data-ttu-id="a2c68-161">Sito filiale</span><span class="sxs-lookup"><span data-stu-id="a2c68-161">Branch Site</span></span></p>
<p><span data-ttu-id="a2c68-162">Sito Edge</span><span class="sxs-lookup"><span data-stu-id="a2c68-162">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="a2c68-163">Configurare il monitoraggio della porta per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a2c68-163">Configure Port monitoring for your deployment.</span></span></p></td>
<td><p><span data-ttu-id="a2c68-164">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="a2c68-164">Central Site</span></span></p>
<p><span data-ttu-id="a2c68-165">Sito filiale</span><span class="sxs-lookup"><span data-stu-id="a2c68-165">Branch Site</span></span></p>
<p><span data-ttu-id="a2c68-166">Sito Edge</span><span class="sxs-lookup"><span data-stu-id="a2c68-166">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a2c68-167">Configurare il monitoraggio degli URL per la distribuzione</span><span class="sxs-lookup"><span data-stu-id="a2c68-167">Configure URL monitoring for your deployment</span></span></p></td>
<td><p><span data-ttu-id="a2c68-168">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="a2c68-168">Central Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c68-169">Integrazione di Lync e System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="a2c68-169">Lync and System Center Operations Manager integration</span></span></p></td>
<td><p><span data-ttu-id="a2c68-170">Distribuire l'affidabilità delle chiamate e la qualità dei contenuti multimediali MonitoringCall monitoraggio della qualità dei contenuti multimediali usare il computer server di monitoraggio come nodo Watcher per monitorare l'affidabilità delle chiamate e la qualità dei contenuti multimediali di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a2c68-170">Deploy Call Reliability and Media Quality MonitoringCall reliability and media quality monitoring use the Monitoring Server computer as their watcher node to monitor call reliability and media quality of Lync Server.</span></span> <span data-ttu-id="a2c68-171">Entrambe le funzionalità eseguono query sui database del server di monitoraggio per eseguire l'analisi.</span><span class="sxs-lookup"><span data-stu-id="a2c68-171">Both of these features query the Monitoring Server databases to do analysis.</span></span></p></td>
<td><p><span data-ttu-id="a2c68-172">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="a2c68-172">Central Site</span></span></p>
<p><span data-ttu-id="a2c68-173">Sito filiale</span><span class="sxs-lookup"><span data-stu-id="a2c68-173">Branch Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a2c68-174">Verificare che le soglie di avviso per la qualità multimediale siano configurate accuratamente.</span><span class="sxs-lookup"><span data-stu-id="a2c68-174">Ensure Media Quality warning thresholds are accurately configured.</span></span> <span data-ttu-id="a2c68-175">La tabella seguente indica i punteggi di opinione della rete massima per codec.</span><span class="sxs-lookup"><span data-stu-id="a2c68-175">The following table indicates the maximum Network Mean Opinion Scores by Codec.</span></span> <span data-ttu-id="a2c68-176">Nella produzione questi punteggi devono essere controllati per un periodo impostato e le soglie accettabili devono essere stabilite in base ai punteggi NMOS specifici dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a2c68-176">In production these scores should be monitored for a set period and acceptable thresholds must be established based on the organization specific NMOS scores.</span></span></p></td>
<td><p><span data-ttu-id="a2c68-177">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="a2c68-177">Central Site</span></span></p>
<p><span data-ttu-id="a2c68-178">Sito filiale</span><span class="sxs-lookup"><span data-stu-id="a2c68-178">Branch Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c68-179">Monitoraggio delle transazioni sintetiche di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2c68-179">Lync Server 2013 Synthetic Transaction Watcher</span></span></p></td>
<td><p><span data-ttu-id="a2c68-180">Distribuire un server Lync dedicato come Watcher delle transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="a2c68-180">Deploy a dedicated Lync Server to be a synthetic transaction watcher.</span></span></p>
<p><span data-ttu-id="a2c68-181">Le transazioni sintetiche sono cmdlet di Windows PowerShell di Lync Server 2013 attivati automaticamente dal Management Pack in base a un intervallo predefinito.</span><span class="sxs-lookup"><span data-stu-id="a2c68-181">Synthetic transactions are Lync Server 2013 Windows PowerShell cmdlets that are automatically triggered by the management pack on a predefined interval.</span></span> <span data-ttu-id="a2c68-182">Queste operazioni vengono eseguite in un nodo di Watcher delle transazioni sintetiche che è un server designato dall'amministratore responsabile dell'individuazione e dell'esecuzione del servizio STs per ogni pool.</span><span class="sxs-lookup"><span data-stu-id="a2c68-182">These are executed on a synthetic transaction watcher node which is an administrator designated server responsible for discovery and execution of STs for each pool.</span></span></p>
<p><span data-ttu-id="a2c68-183">Non è consigliabile usare un server Microsoft Lync Server 2013 esistente come nodo di Watcher delle transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="a2c68-183">We do not recommend that you use an existing Microsoft Lync Server 2013 server as a synthetic transaction watcher node.</span></span> <span data-ttu-id="a2c68-184">Ciò è dovuto ai requisiti di utilizzo della CPU e della memoria elevati per l'uso di STs.</span><span class="sxs-lookup"><span data-stu-id="a2c68-184">This is due to the high CPU/memory usage requirements for running STs.</span></span> <span data-ttu-id="a2c68-185">Usare un nuovo computer server (o un server virtuale) per il nodo di Watcher delle transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="a2c68-185">Use a new server computer (or a virtual server) for the synthetic transaction watcher node.</span></span></p></td>
<td><p><span data-ttu-id="a2c68-186">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="a2c68-186">Central Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a2c68-187">Distribuzione di nodi di Watcher delle transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="a2c68-187">Deploying synthetic transactions watcher node.</span></span></p>
<p><span data-ttu-id="a2c68-188">Fare riferimento al documento MonitoringCS_withSCOM. docx dalla documentazione di UCTAP Connect.</span><span class="sxs-lookup"><span data-stu-id="a2c68-188">Refer to the MonitoringCS_withSCOM.docx document from UCTAP connect documentation.</span></span></p></td>
<td><p><span data-ttu-id="a2c68-189">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="a2c68-189">Central Site</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a><span data-ttu-id="a2c68-190">Punteggi massimi MOS di rete per codec</span><span class="sxs-lookup"><span data-stu-id="a2c68-190">Maximum Network MOS scores per codec</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a2c68-191">Scenario</span><span class="sxs-lookup"><span data-stu-id="a2c68-191">Scenario</span></span></th>
<th><span data-ttu-id="a2c68-192">Codec</span><span class="sxs-lookup"><span data-stu-id="a2c68-192">Codec</span></span></th>
<th><span data-ttu-id="a2c68-193">Max NMOS</span><span class="sxs-lookup"><span data-stu-id="a2c68-193">Max NMOS</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2c68-194">Chiamata UC-UC</span><span class="sxs-lookup"><span data-stu-id="a2c68-194">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="a2c68-195">RTAudio WB</span><span class="sxs-lookup"><span data-stu-id="a2c68-195">RTAudio WB</span></span></p></td>
<td><p><span data-ttu-id="a2c68-196">4,10</span><span class="sxs-lookup"><span data-stu-id="a2c68-196">4.10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c68-197">Chiamata UC-UC</span><span class="sxs-lookup"><span data-stu-id="a2c68-197">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="a2c68-198">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="a2c68-198">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="a2c68-199">2,95</span><span class="sxs-lookup"><span data-stu-id="a2c68-199">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c68-200">Conferenza telefonica</span><span class="sxs-lookup"><span data-stu-id="a2c68-200">Conference call</span></span></p></td>
<td><p><span data-ttu-id="a2c68-201">Sirena</span><span class="sxs-lookup"><span data-stu-id="a2c68-201">Siren</span></span></p></td>
<td><p><span data-ttu-id="a2c68-202">3,72</span><span class="sxs-lookup"><span data-stu-id="a2c68-202">3.72</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2c68-203">Chiamata UC-PSTN</span><span class="sxs-lookup"><span data-stu-id="a2c68-203">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="a2c68-204">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="a2c68-204">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="a2c68-205">2,95</span><span class="sxs-lookup"><span data-stu-id="a2c68-205">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2c68-206">Chiamata UC-PSTN</span><span class="sxs-lookup"><span data-stu-id="a2c68-206">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="a2c68-207">G-711</span><span class="sxs-lookup"><span data-stu-id="a2c68-207">G-711</span></span></p></td>
<td><p><span data-ttu-id="a2c68-208">3,61</span><span class="sxs-lookup"><span data-stu-id="a2c68-208">3.61</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a2c68-209">Oltre alle attività di monitoraggio pro-attive precedenti, le attività di manutenzione devono essere eseguite per i siti centrali, perimetrali e di succursale su base giornaliera, settimanale e mensile ricorrenti, come definito nella Guida operativa di Lync RA.</span><span class="sxs-lookup"><span data-stu-id="a2c68-209">Over and above the previous pro-active monitoring activities, maintenance tasks should be executed for Central, Edge and Branch sites on a recurring daily, weekly and monthly basis as defined in the Lync RA Operations Guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

