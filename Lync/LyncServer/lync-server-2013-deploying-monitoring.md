---
title: 'Lync Server 2013: distribuzione del monitoraggio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying monitoring
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398199(v=OCS.15)
ms:contentKeyID: 48183442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fd56d0c06c9c81eda8cd1d7ef64b57da3219f3e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531173"
---
# <a name="deploying-monitoring-in-lync-server-2013"></a><span data-ttu-id="8bf2c-102">Distribuzione del monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bf2c-102">Deploying monitoring in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bf2c-103">_**Ultimo argomento modificato:** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="8bf2c-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="8bf2c-104">Sono state apportate modifiche importanti all'infrastruttura di monitoraggio di Microsoft Lync Server 2013, a partire dal fatto che il ruolo Monitoring Server è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="8bf2c-104">Major changes have been made to the Microsoft Lync Server 2013 monitoring infrastructure, beginning with the fact that the Monitoring Server role has been deprecated.</span></span> <span data-ttu-id="8bf2c-105">Al posto di ruoli server Monitoring Server separati (che normalmente richiedono la configurazione di computer dedicati come server di monitoraggio nelle organizzazioni), i servizi di monitoraggio sono ora collocati sui singoli server front-end.</span><span class="sxs-lookup"><span data-stu-id="8bf2c-105">Instead of separate Monitoring Server roles (which typically required organizations to set up dedicated computers to act as Monitoring servers) monitoring services are now collocated on each Front End server.</span></span> <span data-ttu-id="8bf2c-106">Questa modifica, tra le altre cose, consente di:</span><span class="sxs-lookup"><span data-stu-id="8bf2c-106">Among other things, this change helps to:</span></span>

  - <span data-ttu-id="8bf2c-107">Ridurre il numero di ruoli del server necessari per l'implementazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bf2c-107">Decrease the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="8bf2c-108">In questo caso, il decremento del ruolo server Monitoring Server si traduce anche in una riduzione dei costi poiché non è più necessario mantenere server dedicati per il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="8bf2c-108">In this case, decrementing the Monitoring Server server role also helps to reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="8bf2c-109">Ridurre la complessità dell'installazione e dell'amministrazione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8bf2c-109">Reduce the complexity of Lync Server setup and administration.</span></span> <span data-ttu-id="8bf2c-110">Collocando automaticamente i servizi di monitoraggio su ogni server front-end, non è più necessario installare, configurare e gestire il ruolo Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="8bf2c-110">By automatically collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8bf2c-111">Il ruolo del server di archiviazione è stato deprecato anche in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bf2c-111">The Archiving Server role has also been deprecated in Lync Server 2013.</span></span> <span data-ttu-id="8bf2c-112">Analogamente ai servizi di monitoraggio, i servizi di archiviazione di Lync Server 2013 sono ora collocati in ogni Front End Server.</span><span class="sxs-lookup"><span data-stu-id="8bf2c-112">Like the monitoring services, Lync Server 2013 archiving services are now collocated on each Front End server.</span></span> <span data-ttu-id="8bf2c-113">È importante tenerlo presente semplicemente perché il monitoraggio e l'archiviazione spesso condividono la stessa istanza di database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8bf2c-113">This is important to note simply because monitoring and archiving often share the same SQL Server database instance.</span></span>



</div>

<span data-ttu-id="8bf2c-114">Come si potrebbe immaginare, queste modifiche hanno un impatto importante sulla modalità di installazione e gestione dei servizi di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="8bf2c-114">As you might expect, these changes have a major impact on how monitoring services are installed and managed.</span></span> <span data-ttu-id="8bf2c-115">Ad esempio, poiché il ruolo Monitoring Server non esiste più, il nodo Monitoring Server è stato rimosso dal generatore di topologie di Lync Server. Ciò significa che non è più possibile utilizzare la procedura guidata del nuovo Monitoring Server di generatore di topologie per aggiungere un nuovo server di monitoraggio alla topologia.</span><span class="sxs-lookup"><span data-stu-id="8bf2c-115">For example, because the Monitoring Server role no longer exists, the Monitoring Server node has been removed from the Lync Server Topology Builder; in turn, that means you no longer use Topology Builder's New Monitoring Server Wizard in order to add a new Monitoring Server to your topology.</span></span> <span data-ttu-id="8bf2c-116">La procedura guidata non esiste più. In genere, invece, vengono implementati i servizi di monitoraggio all'interno della topologia completando i due passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8bf2c-116">(That wizard no longer exists.) Instead, you will typically implement monitoring services within your topology by completing the following two steps:</span></span>

1.  <span data-ttu-id="8bf2c-117">Abilitazione del monitoraggio nello stesso momento in cui si configura un nuovo pool di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8bf2c-117">Enabling monitoring at the same time you set up a new Lync Server pool.</span></span> <span data-ttu-id="8bf2c-118">In Lync Server 2013, il monitoraggio è abilitato o disabilitato in base al pool. Si noti che è possibile abilitare il monitoraggio per un pool senza raccogliere effettivamente i dati di monitoraggio, un processo illustrato nella sezione Configurazione delle impostazioni di registrazione dettagli chiamata e qualità di esperienza di questa documentazione.</span><span class="sxs-lookup"><span data-stu-id="8bf2c-118">(In Lync Server 2013, monitoring is enabled or disabled on a pool-by-pool basis.) Note that you can enable monitoring for a pool without actually collecting monitoring data, a process explained in the Configuring Call Detail Recording and Quality of Experience Settings section of this documentation.</span></span>

2.  <span data-ttu-id="8bf2c-p107">Associazione di un archivio (database) di monitoraggio al nuovo pool. Tenere presente che un archivio di monitoraggio può essere associato a più pool. A seconda del numero di utenti ospitati nei pool di registrazione, questo comporta che non è necessario configurare un database di monitoraggio separato per ogni pool, ma un singolo archivio di monitoraggio può essere utilizzato da più pool.</span><span class="sxs-lookup"><span data-stu-id="8bf2c-p107">Associating a monitoring store (that is, a monitoring database) with the new pool. Note that a single monitoring store can be associated with multiple pools. Depending on the number of users homed on your Registrar pools, that means that you do not have to set up a separate monitoring database for each of your pools. Instead, single monitoring store can be used by multiple pools.</span></span>

<span data-ttu-id="8bf2c-p108">Sebbene spesso risulti più semplice abilitare il monitoraggio al momento della creazione di un nuovo pool, è anche possibile creare un nuovo pool con il monitoraggio disabilitato. In questo caso, è possibile abilitare il servizio in un secondo momento utilizzando il Generatore di topologie, che consente di attivare o disattivare il monitoraggio di topologie o di associare un pool a un diverso archivio di monitoraggio. Tenere presente che, sebbene non esista più il ruolo Monitoring Server, è comunque necessario creare uno o più archivi di monitoraggio, ovvero i database back-end utilizzati per archiviare i dati raccolti dal servizio di monitoraggio. Questi database back-end possono essere creati mediante Microsoft SQL Server 2008 R2 o Microsoft SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="8bf2c-p108">Although it's often easier to enable monitoring at the same time that you create a new pool, it's also possible to create a new pool with monitoring disabled. If you do that, you can later use Topology Builder to enable the service: Topology Builder provides a way to enable or disable monitoring for a pool, or to associate a pool with a different monitoring store. Keep in mind that even though there is no longer a Monitoring Server role you will still need to create one or more monitoring stores: backend databases used to store the data gathered by the monitoring service. These backend databases can be created using either Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8bf2c-127">Se è stato abilitato il monitoraggio per un pool, è possibile disabilitare il processo di raccolta dei dati di monitoraggio senza che sia necessario modificare la topologia: Lync Server Management Shell consente di disabilitare (e successivamente riabilitare) la raccolta dei dati di registrazione dettagli chiamata (CDR) o la qualità di esperienza (QoE).</span><span class="sxs-lookup"><span data-stu-id="8bf2c-127">If monitoring has been enabled for a pool you can disable the process of collecting monitoring data without having to change your topology: Lync Server Management Shell provides a way for you to disable (and then later re-enable) call detail recording (CDR) or Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="8bf2c-128">Per ulteriori informazioni, vedere la sezione relativa alla configurazione delle impostazioni di registrazione dettagli chiamata e QoE di questa documentazione.</span><span class="sxs-lookup"><span data-stu-id="8bf2c-128">For more information, see the Configuring Call Detail Recording and Quality of Experience Settings section of this document.</span></span>



</div>

<span data-ttu-id="8bf2c-129">Un altro importante miglioramento del monitoraggio in Lync Server 2013 è il fatto che i rapporti di monitoraggio di Lync Server ora supportano IPv6: i report che utilizzano il campo indirizzo IP visualizzeranno gli indirizzi IPv4 o IPv6 a seconda di quanto segue: 1) la query SQL utilizzata. e 2) dove l'indirizzo IPv6 è memorizzato o meno nel database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="8bf2c-129">One other important enhancement to monitoring in Lync Server 2013 is the fact that Lync Server Monitoring Reports now support IPv6: reports that use the IP Address field will display either IPv4 or IPv6 addresses depending on : 1) the SQL query being used; and, 2) where or not the IPv6 address is stored in the monitoring database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8bf2c-130">Verificare che il tipo di avvio del servizio SQL Server Agent sia automatico e che il servizio SQL Server Agent sia in esecuzione per l'istanza di SQL che contiene i database di monitoraggio, in modo che i processi di manutenzione di SQL Server di monitoraggio predefiniti possano essere eseguiti nella loro base pianificata sotto il controllo del servizio SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="8bf2c-130">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Monitoring databases, so that the Default Monitoring SQL Server Maintenance Jobs can run on their scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

<span data-ttu-id="8bf2c-131">In questa documentazione viene illustrato il processo di installazione e configurazione dei rapporti di monitoraggio e monitoraggio per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bf2c-131">This documentation walks you through the process of installing and configuring monitoring and Monitoring Reports for Lync Server 2013.</span></span> <span data-ttu-id="8bf2c-132">Sono fornite istruzioni dettagliate per le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="8bf2c-132">The documentation provides step-by-step instructions that will help you to:</span></span>

  - <span data-ttu-id="8bf2c-133">Abilitare il monitoraggio nella topologia e associare un archivio di monitoraggio a un pool Front End.</span><span class="sxs-lookup"><span data-stu-id="8bf2c-133">Enable monitoring in your topology and associate a monitoring store with a Front End pool.</span></span>

  - <span data-ttu-id="8bf2c-134">Installare SQL Server Reporting Services e i report di monitoraggio di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8bf2c-134">Install SQL Server Reporting Services and the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="8bf2c-135">I report di monitoraggio sono rapporti preconfigurati che forniscono visualizzazioni diverse nelle informazioni archiviate in un database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="8bf2c-135">Monitoring Reports are preconfigured reports that provide different views into the information stored in a monitoring database.</span></span>

  - <span data-ttu-id="8bf2c-136">Configurare la raccolta dei dati di registrazione dettagli chiamata (CDR) e qualità percepita dagli utenti (QoE).</span><span class="sxs-lookup"><span data-stu-id="8bf2c-136">Configure call detail recording (CDR) and Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="8bf2c-137">La registrazione dettagli chiamata consente di monitorare l'utilizzo delle funzionalità di Lync Server, ad esempio le chiamate telefoniche VoIP (Voice over IP). messaggistica istantanea (IM); trasferimenti di file; Servizi di conferenza audio/video (A/V); e sessioni di condivisione applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8bf2c-137">Call detail recording provides a way for you to track usage of Lync Server capabilities such as Voice over IP (VoIP) phone calls; instant messaging (IM); file transfers; audio/video (A/V) conferencing; and application sharing sessions.</span></span> <span data-ttu-id="8bf2c-138">Le metriche QoE tengono traccia della qualità delle chiamate audio e video effettuate nell'organizzazione, includendo informazioni quali il numero di pacchetti di rete persi, i rumori di fondo e la quantità di "instabilità" (differenze nel ritardo dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="8bf2c-138">QoE metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span>

  - <span data-ttu-id="8bf2c-139">Eliminare manualmente i record CDR e/o QoE dal database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="8bf2c-139">Manually purge CDR and/or QoE records from the monitoring database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

