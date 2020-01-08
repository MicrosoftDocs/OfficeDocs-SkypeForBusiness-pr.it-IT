---
title: 'Lync Server 2013: distribuzione del monitoraggio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying monitoring
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398199(v=OCS.15)
ms:contentKeyID: 48183442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 584b99b6e5fad72a07a35b748ab9bafa4116701a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-monitoring-in-lync-server-2013"></a><span data-ttu-id="2868c-102">Distribuzione del monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2868c-102">Deploying monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2868c-103">_**Argomento Ultima modifica:** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="2868c-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="2868c-104">Sono state apportate modifiche importanti all'infrastruttura di monitoraggio di Microsoft Lync Server 2013, a partire dal fatto che il ruolo del server di monitoraggio è deprecato.</span><span class="sxs-lookup"><span data-stu-id="2868c-104">Major changes have been made to the Microsoft Lync Server 2013 monitoring infrastructure, beginning with the fact that the Monitoring Server role has been deprecated.</span></span> <span data-ttu-id="2868c-105">Invece dei ruoli distinti del server di monitoraggio (che in genere richiedevano alle organizzazioni di configurare computer dedicati per fungere da server di monitoraggio), i servizi di monitoraggio sono ora collocati in ogni server front-end.</span><span class="sxs-lookup"><span data-stu-id="2868c-105">Instead of separate Monitoring Server roles (which typically required organizations to set up dedicated computers to act as Monitoring servers) monitoring services are now collocated on each Front End server.</span></span> <span data-ttu-id="2868c-106">Tra le altre cose, questa modifica consente di:</span><span class="sxs-lookup"><span data-stu-id="2868c-106">Among other things, this change helps to:</span></span>

  - <span data-ttu-id="2868c-107">Ridurre il numero di ruoli del server necessari per l'implementazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2868c-107">Decrease the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="2868c-108">In questo caso, il decremento del ruolo del server di monitoraggio consente anche di ridurre i costi eliminando la necessità di gestire server dedicati per il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="2868c-108">In this case, decrementing the Monitoring Server server role also helps to reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="2868c-109">Ridurre la complessità della configurazione e dell'amministrazione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2868c-109">Reduce the complexity of Lync Server setup and administration.</span></span> <span data-ttu-id="2868c-110">La collocazione automatica dei servizi di monitoraggio in ogni server front-end non è più necessario installare, configurare e gestire il ruolo del server di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="2868c-110">By automatically collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2868c-111">Il ruolo del server di archiviazione è stato deprecato anche in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2868c-111">The Archiving Server role has also been deprecated in Lync Server 2013.</span></span> <span data-ttu-id="2868c-112">Come i servizi di monitoraggio, i servizi di archiviazione di Lync Server 2013 sono ora collocati in ogni server front-end.</span><span class="sxs-lookup"><span data-stu-id="2868c-112">Like the monitoring services, Lync Server 2013 archiving services are now collocated on each Front End server.</span></span> <span data-ttu-id="2868c-113">Questa operazione è importante da notare semplicemente perché il monitoraggio e l'archiviazione condividono spesso la stessa istanza di database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2868c-113">This is important to note simply because monitoring and archiving often share the same SQL Server database instance.</span></span>



</div>

<span data-ttu-id="2868c-114">Come si può prevedere, queste modifiche hanno un impatto importante sul modo in cui vengono installati e gestiti i servizi di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="2868c-114">As you might expect, these changes have a major impact on how monitoring services are installed and managed.</span></span> <span data-ttu-id="2868c-115">Poiché il ruolo del server di monitoraggio non esiste più, ad esempio, il nodo server di monitoraggio è stato rimosso dal generatore di topologia di Lync Server. a sua volta, questo significa che non è più possibile usare la procedura guidata nuovo server di monitoraggio di generatore di topologia per aggiungere un nuovo server di monitoraggio alla topologia.</span><span class="sxs-lookup"><span data-stu-id="2868c-115">For example, because the Monitoring Server role no longer exists, the Monitoring Server node has been removed from the Lync Server Topology Builder; in turn, that means you no longer use Topology Builder's New Monitoring Server Wizard in order to add a new Monitoring Server to your topology.</span></span> <span data-ttu-id="2868c-116">(La procedura guidata non esiste più) Al contrario, in genere implementiamo i servizi di monitoraggio all'interno della topologia completando i due passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2868c-116">(That wizard no longer exists.) Instead, you will typically implement monitoring services within your topology by completing the following two steps:</span></span>

1.  <span data-ttu-id="2868c-117">Abilitazione del monitoraggio contemporaneamente alla configurazione di un nuovo pool di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2868c-117">Enabling monitoring at the same time you set up a new Lync Server pool.</span></span> <span data-ttu-id="2868c-118">In Lync Server 2013 il monitoraggio viene abilitato o disabilitato in base al pool. Tieni presente che puoi abilitare il monitoraggio per un pool senza raccogliere effettivamente i dati di monitoraggio, un processo spiegato nella sezione configurazione della registrazione dei dettagli delle chiamate e della qualità delle impostazioni dell'esperienza di questa documentazione.</span><span class="sxs-lookup"><span data-stu-id="2868c-118">(In Lync Server 2013, monitoring is enabled or disabled on a pool-by-pool basis.) Note that you can enable monitoring for a pool without actually collecting monitoring data, a process explained in the Configuring Call Detail Recording and Quality of Experience Settings section of this documentation.</span></span>

2.  <span data-ttu-id="2868c-119">Associazione di un archivio di monitoraggio (ovvero un database di monitoraggio) con il nuovo pool.</span><span class="sxs-lookup"><span data-stu-id="2868c-119">Associating a monitoring store (that is, a monitoring database) with the new pool.</span></span> <span data-ttu-id="2868c-120">Tieni presente che un singolo archivio di monitoraggio può essere associato a più pool.</span><span class="sxs-lookup"><span data-stu-id="2868c-120">Note that a single monitoring store can be associated with multiple pools.</span></span> <span data-ttu-id="2868c-121">A seconda del numero di utenti ospitati nei pool di registrar, significa che non è necessario configurare un database di monitoraggio separato per ogni pool.</span><span class="sxs-lookup"><span data-stu-id="2868c-121">Depending on the number of users homed on your Registrar pools, that means that you do not have to set up a separate monitoring database for each of your pools.</span></span> <span data-ttu-id="2868c-122">Un singolo archivio di monitoraggio può invece essere usato da più pool.</span><span class="sxs-lookup"><span data-stu-id="2868c-122">Instead, single monitoring store can be used by multiple pools.</span></span>

<span data-ttu-id="2868c-123">Anche se spesso è più semplice abilitare il monitoraggio quando si crea un nuovo pool, è anche possibile creare un nuovo pool con il monitoraggio disabilitato.</span><span class="sxs-lookup"><span data-stu-id="2868c-123">Although it's often easier to enable monitoring at the same time that you create a new pool, it's also possible to create a new pool with monitoring disabled.</span></span> <span data-ttu-id="2868c-124">In questo caso, puoi usare il generatore di topologie in seguito per abilitare il servizio: generatore di topologie consente di abilitare o disabilitare il monitoraggio per un pool o di associare un pool a un altro archivio di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="2868c-124">If you do that, you can later use Topology Builder to enable the service: Topology Builder provides a way to enable or disable monitoring for a pool, or to associate a pool with a different monitoring store.</span></span> <span data-ttu-id="2868c-125">Tenere presente che, anche se non è più presente un ruolo di monitoraggio del server, sarà comunque necessario creare uno o più archivi di monitoraggio: i database di backend usati per archiviare i dati raccolti dal servizio di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="2868c-125">Keep in mind that even though there is no longer a Monitoring Server role you will still need to create one or more monitoring stores: backend databases used to store the data gathered by the monitoring service.</span></span> <span data-ttu-id="2868c-126">Questi database back-end possono essere creati usando Microsoft SQL Server 2008 R2 o Microsoft SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="2868c-126">These backend databases can be created using either Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2868c-127">Se il monitoraggio è stato abilitato per un pool, è possibile disabilitare il processo di raccolta dei dati di monitoraggio senza dover modificare la topologia: Lync Server Management Shell consente di disabilitare (e quindi riabilitare) la registrazione dettagli chiamata (CDR) o la qualità raccolta dati di Experience (QoE).</span><span class="sxs-lookup"><span data-stu-id="2868c-127">If monitoring has been enabled for a pool you can disable the process of collecting monitoring data without having to change your topology: Lync Server Management Shell provides a way for you to disable (and then later re-enable) call detail recording (CDR) or Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="2868c-128">Per altre informazioni, vedere la sezione configurazione della registrazione dei dettagli delle chiamate e della qualità delle impostazioni dell'esperienza di questo documento.</span><span class="sxs-lookup"><span data-stu-id="2868c-128">For more information, see the Configuring Call Detail Recording and Quality of Experience Settings section of this document.</span></span>



</div>

<span data-ttu-id="2868c-129">Un altro importante miglioramento per il monitoraggio in Lync Server 2013 è il fatto che i report di monitoraggio di Lync Server ora supportano IPv6: i report che usano il campo indirizzo IP visualizzeranno indirizzi IPv4 o IPv6 in base a: 1) la query SQL in uso; e 2) dove l'indirizzo IPv6 viene archiviato o meno nel database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="2868c-129">One other important enhancement to monitoring in Lync Server 2013 is the fact that Lync Server Monitoring Reports now support IPv6: reports that use the IP Address field will display either IPv4 or IPv6 addresses depending on : 1) the SQL query being used; and, 2) where or not the IPv6 address is stored in the monitoring database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2868c-130">Verificare che il tipo di avvio del servizio di SQL Server Agent sia automatico e che il servizio SQL Server Agent sia in esecuzione per l'istanza SQL che tiene i database di monitoraggio, in modo che i processi di manutenzione di SQL Server di monitoraggio predefiniti possano essere eseguiti nella loro base pianificata sotto il controllo del servizio agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2868c-130">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Monitoring databases, so that the Default Monitoring SQL Server Maintenance Jobs can run on their scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

<span data-ttu-id="2868c-131">Questa documentazione illustra il processo di installazione e configurazione dei report di monitoraggio e monitoraggio per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2868c-131">This documentation walks you through the process of installing and configuring monitoring and Monitoring Reports for Lync Server 2013.</span></span> <span data-ttu-id="2868c-132">La documentazione include istruzioni dettagliate che ti aiuteranno a:</span><span class="sxs-lookup"><span data-stu-id="2868c-132">The documentation provides step-by-step instructions that will help you to:</span></span>

  - <span data-ttu-id="2868c-133">Abilitare il monitoraggio nella topologia e associare un archivio di monitoraggio a un pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="2868c-133">Enable monitoring in your topology and associate a monitoring store with a Front End pool.</span></span>

  - <span data-ttu-id="2868c-134">Installare SQL Server Reporting Services e i report di monitoraggio di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2868c-134">Install SQL Server Reporting Services and the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="2868c-135">I report di monitoraggio sono report preconfigurati che contengono visualizzazioni diverse delle informazioni archiviate in un database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="2868c-135">Monitoring Reports are preconfigured reports that provide different views into the information stored in a monitoring database.</span></span>

  - <span data-ttu-id="2868c-136">Configurare la raccolta di dati per la registrazione dei dettagli delle chiamate (CDR) e la qualità dell'esperienza (QoE).</span><span class="sxs-lookup"><span data-stu-id="2868c-136">Configure call detail recording (CDR) and Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="2868c-137">La registrazione dei dettagli delle chiamate consente di tenere traccia dell'uso delle funzionalità di Lync Server, ad esempio chiamate telefoniche VoIP (Voice over IP). messaggistica istantanea (IM); trasferimenti di file; Servizi di conferenza audio/video (A/V); e sessioni di condivisione applicazioni.</span><span class="sxs-lookup"><span data-stu-id="2868c-137">Call detail recording provides a way for you to track usage of Lync Server capabilities such as Voice over IP (VoIP) phone calls; instant messaging (IM); file transfers; audio/video (A/V) conferencing; and application sharing sessions.</span></span> <span data-ttu-id="2868c-138">Le metriche QoE tengono traccia della qualità delle chiamate audio e video effettuate nell'organizzazione, inclusi i problemi relativi al numero di pacchetti di rete persi, al rumore di fondo e alla quantità di "jitter" (differenze nel ritardo del pacchetto).</span><span class="sxs-lookup"><span data-stu-id="2868c-138">QoE metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span>

  - <span data-ttu-id="2868c-139">Eliminare manualmente i record CDR e/o QoE dal database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="2868c-139">Manually purge CDR and/or QoE records from the monitoring database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

