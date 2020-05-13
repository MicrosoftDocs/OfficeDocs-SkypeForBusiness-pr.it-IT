---
title: 'Lync Server 2013: nuove funzionalità del server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Persistent Chat Server features
ms:assetid: c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412965(v=OCS.15)
ms:contentKeyID: 48185341
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6203e6a7ee99f4b080fa93976a2a937e62fe9d3c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a><span data-ttu-id="83b22-102">Nuove funzionalità del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83b22-102">New Persistent Chat Server features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83b22-103">_**Ultimo argomento modificato:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="83b22-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="83b22-104">Lync Server 2013, il server Chat persistente consente di partecipare a conversazioni a più parti, basate su argomenti che persistono nel tempo.</span><span class="sxs-lookup"><span data-stu-id="83b22-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="83b22-105">Il server Chat persistente può aiutare l'organizzazione a eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="83b22-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="83b22-106">Migliorare le comunicazioni tra team interfunzionali e distribuiti in zone geografiche diverse</span><span class="sxs-lookup"><span data-stu-id="83b22-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="83b22-107">Ampliare la condivisione delle informazioni e la partecipazione</span><span class="sxs-lookup"><span data-stu-id="83b22-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="83b22-108">Migliorare le comunicazioni con l'organizzazione estesa</span><span class="sxs-lookup"><span data-stu-id="83b22-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="83b22-109">Ridurre il sovraccarico di informazioni</span><span class="sxs-lookup"><span data-stu-id="83b22-109">Reduce information overload</span></span>

  - <span data-ttu-id="83b22-110">Migliorare la consapevolezza delle informazioni</span><span class="sxs-lookup"><span data-stu-id="83b22-110">Improve information awareness</span></span>

  - <span data-ttu-id="83b22-111">Migliorare la diffusione di informazioni e conoscenze importanti</span><span class="sxs-lookup"><span data-stu-id="83b22-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="83b22-112">Lync Server 2013, il server Chat persistente non è disponibile in Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="83b22-112">Lync Server 2013, Persistent Chat Server is not available in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="83b22-113">In questo momento, è disponibile solo per i clienti di Lync 2013 locali.</span><span class="sxs-lookup"><span data-stu-id="83b22-113">At this time, it is available only to on-premise Lync 2013 customers.</span></span>

<span data-ttu-id="83b22-114">In Lync 2013, la funzionalità chat persistente è integrata nel client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="83b22-114">In Lync 2013, Persistent Chat functionality is integrated into the Lync 2013 client.</span></span> <span data-ttu-id="83b22-115">Di conseguenza, gli utenti possono accedere a messaggistica istantanea/presenza, audio/video, conferenze e chat persistente tutti nel client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="83b22-115">As a result, users have access to Instant Messaging/Presence, Audio/Video, Conferencing, and Persistent Chat all in the Lync 2013 client.</span></span> <span data-ttu-id="83b22-116">Per ulteriori informazioni sul client Lync 2013, vedere <https://go.microsoft.com/fwlink/p/?linkid=270877> .</span><span class="sxs-lookup"><span data-stu-id="83b22-116">For more information about the Lync 2013 client, see <https://go.microsoft.com/fwlink/p/?linkid=270877>.</span></span>

<span data-ttu-id="83b22-117">In questo argomento vengono descritte le modifiche apportate alla caratteristica tra la nuova versione di Lync Server 2013, il server Chat persistente e la versione precedente (Microsoft Lync Server 2010, Group Chat), tra cui:</span><span class="sxs-lookup"><span data-stu-id="83b22-117">This topic describes feature changes between the new version of Lync Server 2013, Persistent Chat Server and the previous version (Microsoft Lync Server 2010, Group Chat), including:</span></span>

  - <span data-ttu-id="83b22-118">Fornire un'esperienza amministrativa nel pannello di controllo di Lync Server ed eliminare lo strumento di amministrazione di Group Chat</span><span class="sxs-lookup"><span data-stu-id="83b22-118">Provide an administrative experience in Lync Server Control Panel, and eliminate the Group Chat Admin Tool</span></span>

  - <span data-ttu-id="83b22-119">Integrazione delle impostazioni di configurazione per il server Chat persistente in Generatore di topologie eliminando lo strumento di configurazione di Group Chat</span><span class="sxs-lookup"><span data-stu-id="83b22-119">Integrate configuration settings for Persistent Chat Server into Topology Builder by eliminating the Group Chat Configuration tool</span></span>

  - <span data-ttu-id="83b22-120">Semplificare la migrazione e l'aggiornamento dalle versioni precedenti del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="83b22-120">Ease migration and upgrade from previous versions of Persistent Chat Server</span></span>

  - <span data-ttu-id="83b22-121">Fornire soluzioni di disponibilità elevata e ripristino di emergenza</span><span class="sxs-lookup"><span data-stu-id="83b22-121">Provide high availability and disaster recovery solutions</span></span>

<span data-ttu-id="83b22-122">Per ulteriori informazioni sulla versione più recente del server Chat persistente, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="83b22-122">For additional details about the latest version of Persistent Chat Server, see the following:</span></span>

  - <span data-ttu-id="83b22-123">La guida per la chat persistente in <https://go.microsoft.com/fwlink/p/?linkid=270945> cui viene fornito un elenco dettagliato delle funzionalità di chat persistente, il loro funzionamento e come utilizzarle durante l'esecuzione del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="83b22-123">The Persistent Chat Help at <https://go.microsoft.com/fwlink/p/?linkid=270945> which provides a detailed list of Persistent Chat features, how they work, and how to use them while running Persistent Chat Server.</span></span>

  - <span data-ttu-id="83b22-124">La [pianificazione del server Chat persistente in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) nella documentazione relativa alla pianificazione [distribuzione del server Chat persistente in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) nella documentazione relativa alla distribuzione, [migrazione da Lync Server 2010, Group chat o Office Communications Server 2007 R2 group chat a Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) nella documentazione relativa alla migrazione e [gestione di Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) nella documentazione relativa alle operazioni, che forniscono tutte le istruzioni per la configurazione del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="83b22-124">The [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation, [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) in the Migration documentation, and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) in the Operations documentation, all of which provide instructions for setting up Persistent Chat Server.</span></span>

  - <span data-ttu-id="83b22-125">Il file di documentazione. msi del server di chat persistente (file di Windows Installer) consente agli utenti di accedere alla documentazione offline completa sul server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="83b22-125">The Persistent Chat Server Documentation.msi file (Windows Installer file) lets users access comprehensive offline documentation about Persistent Chat Server.</span></span>

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a><span data-ttu-id="83b22-126">Modifiche alla topologia chiave per il server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="83b22-126">Key Topology Changes for Persistent Chat Server</span></span>

<span data-ttu-id="83b22-127">Di seguito sono riportate le seguenti modifiche di alto livello per il server Chat persistente:</span><span class="sxs-lookup"><span data-stu-id="83b22-127">The following high-level changes for Persistent Chat Server include:</span></span>

<span data-ttu-id="83b22-128">Il server Chat persistente è ora un ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="83b22-128">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="83b22-129">In Microsoft Lync Server 2010, Group Chat Server era un'applicazione attendibile di terze parti per Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="83b22-129">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="83b22-130">È possibile aggiungere la chat persistente alla topologia di Lync Server 2013 utilizzando Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="83b22-130">Persistent Chat can be added to your Lync Server 2013 topology by using Topology Builder.</span></span> <span data-ttu-id="83b22-131">In Lync Server 2013, la funzionalità del server Chat persistente viene implementata utilizzando tre nuovi ruoli del server:</span><span class="sxs-lookup"><span data-stu-id="83b22-131">In Lync Server 2013, Persistent Chat Server functionality is implemented by using three new server roles:</span></span>

  - <span data-ttu-id="83b22-132">**PersistentChatService:** Si tratta del ruolo front-end per la chat persistente.</span><span class="sxs-lookup"><span data-stu-id="83b22-132">**PersistentChatService:** This is the front end role for Persistent Chat.</span></span> <span data-ttu-id="83b22-133">Nelle distribuzioni standard Edition, il ruolo del servizio server Chat persistente è collocato nel server Standard Edition distribuito dal programma di avvio automatico, come qualsiasi altro ruolo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83b22-133">In Standard Edition deployments, Persistent Chat Server Service Role is collocated on the Standard Edition server deployed by Bootstrapper, like any other Lync Server role.</span></span> <span data-ttu-id="83b22-134">Nelle distribuzioni di Enterprise Edition, il ruolo del servizio chat persistente è distribuito in computer autonomi da parte del programma di avvio automatico, come qualsiasi altro ruolo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83b22-134">In Enterprise Edition deployments, Persistent Chat Service Role is deployed on stand-alone computers by Bootstrapper, like any other Lync Server role.</span></span>

  - <span data-ttu-id="83b22-135">**PersistentChatStore:** Server back-end che corrisponde al database del contenuto di chat persistente, in cui è archiviato tutto il contenuto della chat.</span><span class="sxs-lookup"><span data-stu-id="83b22-135">**PersistentChatStore:** Back End Server that corresponds to the Persistent Chat content database, where all the chat content is stored.</span></span>

  - <span data-ttu-id="83b22-136">**PersistentChatComplianceStore:** Ruolo del server back-end corrispondente al database di conformità di Persistent Chat, in cui vengono archiviati tutti gli eventi di conformità.</span><span class="sxs-lookup"><span data-stu-id="83b22-136">**PersistentChatComplianceStore:** Back End Server role that corresponds to the Persistent Chat Compliance database, where all compliance events are stored.</span></span>

<span data-ttu-id="83b22-137">Questi ruoli del server Chat persistente sono facoltativi e vengono installati solo dai clienti che desiderano una funzionalità completa del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="83b22-137">These Persistent Chat Server roles are optional, and are installed only by customers who want comprehensive Persistent Chat Server functionality.</span></span> <span data-ttu-id="83b22-138">Il ruolo **PersistentChatComplianceStore** è necessario solo se si sceglie di distribuire la conformità Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="83b22-138">The **PersistentChatComplianceStore** role is needed only if you choose to deploy Persistent Chat Compliance.</span></span>

<span data-ttu-id="83b22-139">Il ruolo **PersistentChatService** esegue due servizi:</span><span class="sxs-lookup"><span data-stu-id="83b22-139">The **PersistentChatService** role runs two services:</span></span>

  - <span data-ttu-id="83b22-140">Servizio chat persistente</span><span class="sxs-lookup"><span data-stu-id="83b22-140">Persistent Chat service</span></span>

  - <span data-ttu-id="83b22-141">Servizio di conformità chat persistente</span><span class="sxs-lookup"><span data-stu-id="83b22-141">Persistent Chat Compliance service</span></span>

<span data-ttu-id="83b22-142">L'esecuzione di questi servizi su ogni server Chat persistente garantisce una disponibilità elevata per questi servizi in un pool di server Chat persistente multiserver.</span><span class="sxs-lookup"><span data-stu-id="83b22-142">Having these services run on each Persistent Chat Server provides high availability for these services in a multiserver Persistent Chat Server pool.</span></span>

<span data-ttu-id="83b22-143">Inoltre, per supportare il caricamento e il download dei file nelle chat room persistent, il server Chat persistente include un servizio Web.</span><span class="sxs-lookup"><span data-stu-id="83b22-143">Additionally, to support the file upload and download in Persistent Chat rooms, Persistent Chat Server includes a web service.</span></span> <span data-ttu-id="83b22-144">In precedenza, il servizio è stato collocato nel server Chat persistente, Front End Server e Internet Information Services (IIS) richiesto per l'installazione come prerequisito.</span><span class="sxs-lookup"><span data-stu-id="83b22-144">Previously, this service was collocated on the Persistent Chat Server, Front End Server and required Internet Information Services (IIS) to be installed as a prerequisite.</span></span> <span data-ttu-id="83b22-145">In Lync Server 2013 Persistent Chat Server, il servizio Web caricamento/download file è collocato con il front end server Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="83b22-145">In Lync Server 2013 Persistent Chat Server, the File Upload/Download web service is collocated with the Lync Server 2013 Front End Server.</span></span> <span data-ttu-id="83b22-146">Come effetto collaterale, Internet Information Services (IIS) non è più un prerequisito per il server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="83b22-146">As a side effect, Internet Information Services (IIS) is no longer a prerequisite for Persistent Chat Server.</span></span> <span data-ttu-id="83b22-147">Il servizio Web caricamento/scaricamento file è identificato come **PersistentChat** in Gestione Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="83b22-147">The File Upload/Download web service is identified as **PersistentChat** in the Internet Information Services (IIS) Manager.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="83b22-148">Il ruolo <STRONG>PersistentChatService</STRONG> può essere eseguito nello stesso server di un server front-end di Lync Server 2013 solo se il front end server è un server front end &nbsp; Standard Edition &nbsp; .</span><span class="sxs-lookup"><span data-stu-id="83b22-148">The <STRONG>PersistentChatService</STRONG> role can run on the same server as a Lync Server 2013&nbsp;Front End Server only if that Front End Server is a Standard Edition&nbsp;Front End Server.</span></span> <span data-ttu-id="83b22-149">Il ruolo <STRONG>PersistentChatService</STRONG> non può essere eseguito indipendentemente da un &nbsp; server front-end di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="83b22-149">The <STRONG>PersistentChatService</STRONG> role cannot run independently of a Lync Server 2013&nbsp;Front End Server.</span></span> <span data-ttu-id="83b22-150">Può essere installato solo nel contesto di una distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="83b22-150">It can be installed only in the context of a Lync Server 2013 deployment.</span></span>



</div>

<span data-ttu-id="83b22-151">Nel server Chat persistente, il servizio di ricerca è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="83b22-151">In Persistent Chat Server, Lookup service has been eliminated.</span></span> <span data-ttu-id="83b22-152">In Lync Server 2010, Group Chat, il servizio di ricerca è stato eseguito su ogni server front-end di Group Chat Server e ha eseguito il routing su uno dei server di canale.</span><span class="sxs-lookup"><span data-stu-id="83b22-152">In Lync Server 2010, Group Chat, the Lookup service ran on every Group Chat Server Front End Server, and performed routing to one of the Channel Servers.</span></span> <span data-ttu-id="83b22-153">Lync Server 2013 si basa sul routing tramite gli oggetti contatto, in cui ogni pool di server Chat persistente è rappresentato da un oggetto contatto utilizzato dai Front End Server Lync Server per identificare e instradare le richieste a un pool di server Chat persistente appropriato e a uno dei computer in cui è in esecuzione il server Chat persistente nel pool.</span><span class="sxs-lookup"><span data-stu-id="83b22-153">Lync Server 2013 relies on routing by using contact objects, where each Persistent Chat Server pool is represented by a contact object that is used by the Lync Server Front End Servers to identify and route requests to an appropriate Persistent Chat Server pool, and to one of the computers running Persistent Chat Server in the pool.</span></span>

<span data-ttu-id="83b22-154">In Lync Server 2013, sono disponibili modifiche del servizio conformità:</span><span class="sxs-lookup"><span data-stu-id="83b22-154">In Lync Server 2013, there are Compliance service modifications:</span></span>

  - <span data-ttu-id="83b22-155">In Lync Server 2010, il servizio di conformità ha eseguito la versione autonoma (non collocata) e solo su un server singolo.</span><span class="sxs-lookup"><span data-stu-id="83b22-155">In Lync Server 2010, the Compliance service ran stand-alone (non-collocated), and only on a single server.</span></span> <span data-ttu-id="83b22-156">Il servizio di conformità è ora in esecuzione su tutti i front end server di Persistent Chat, insieme al servizio chat persistente e fornisce quindi la disponibilità elevata in un pool di server Chat persistente multiserver.</span><span class="sxs-lookup"><span data-stu-id="83b22-156">The Compliance service now runs on all the Persistent Chat Server Front End Servers, alongside the Persistent Chat service, and thereby provides high availability in a multiserver Persistent Chat Server pool.</span></span> <span data-ttu-id="83b22-157">Una singola scheda di conformità può essere configurata in modo da estrarre i dati dal database di conformità e in uno degli altri sistemi (file XML, archivi ospitati da Exchange e così via).</span><span class="sxs-lookup"><span data-stu-id="83b22-157">A single compliance adapter can be configured to extract data from the compliance database and into one of the other systems (XML file, Exchange-hosted archives, and so on).</span></span> <span data-ttu-id="83b22-158">Il server Chat persistente include un adattatore XML.</span><span class="sxs-lookup"><span data-stu-id="83b22-158">Persistent Chat Server includes an XML adapter.</span></span>

  - <span data-ttu-id="83b22-159">La coda di Accodamento messaggi (nota anche come MSMQ) condivisa dal servizio chat persistente e il servizio di conformità su ogni server front-end Persistent Chat Server è ora una coda privata condivisa solo dai due servizi.</span><span class="sxs-lookup"><span data-stu-id="83b22-159">The Message Queuing (also known as MSMQ) queue that is shared by the Persistent Chat service and the Compliance service on each Persistent Chat Server Front End Server is now a private queue shared only by the two services.</span></span> <span data-ttu-id="83b22-160">Tutti i servizi di conformità scrivono nello stesso database back-end di conformità.</span><span class="sxs-lookup"><span data-stu-id="83b22-160">All compliance services write to the same Compliance Back End database.</span></span> <span data-ttu-id="83b22-161">Sono inoltre tutte lette da tale database, allo scopo di inviare i dati all'istanza dell'adapter.</span><span class="sxs-lookup"><span data-stu-id="83b22-161">They also all read from that database, for the purpose of sending the data to their instance of the adapter.</span></span> <span data-ttu-id="83b22-162">Il server back-end Compliance è rappresentato come nuovo ruolo del server back-end.</span><span class="sxs-lookup"><span data-stu-id="83b22-162">The Compliance Back End Server is represented as a new Back End Server role.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="83b22-163">Come nelle versioni precedenti, tutti i dati di conformità vengono elaborati solo una volta.</span><span class="sxs-lookup"><span data-stu-id="83b22-163">As in previous versions, all compliance data is processed only once.</span></span> <span data-ttu-id="83b22-164">I dati possono essere elaborati da una qualsiasi delle istanze degli adattatori richiamate dal servizio di conformità in esecuzione sui vari computer server di chat persistente di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="83b22-164">The data may be processed by any of the adapter instances invoked by the compliance service running on the various Lync Server 2013, Persistent Chat Server computers.</span></span> <span data-ttu-id="83b22-165">Nel server Chat persistente, una qualsiasi delle istanze dell'adapter potrebbe elaborare i dati.</span><span class="sxs-lookup"><span data-stu-id="83b22-165">In Persistent Chat Server, any one of the adapter instances could process the data.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="83b22-166">Per informazioni sull'installazione di Accodamento messaggi, vedere <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">installare i sistemi operativi e il software prerequisito nei server per Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="83b22-166">For information about installing Message Queuing, see <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Install operating systems and prerequisite software on servers for Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="83b22-167">In Lync Server 2013, sono disponibili miglioramenti sia per la disponibilità elevata che per il ripristino di emergenza:</span><span class="sxs-lookup"><span data-stu-id="83b22-167">In Lync Server 2013, there are improvements in both high availability and disaster recovery:</span></span>

  - <span data-ttu-id="83b22-168">Miglioramenti a disponibilità elevata: il mirroring di SQL Server viene utilizzato per garantire la disponibilità elevata per il database del contenuto del server Chat persistente e il database di conformità di Persistent Chat all'interno di un Data Center (nel sito).</span><span class="sxs-lookup"><span data-stu-id="83b22-168">High availability improvements: SQL Server mirroring is used to provide high availability for the Persistent Chat Server content database and Persistent Chat compliance database within a data center (in-site).</span></span>

  - <span data-ttu-id="83b22-169">Miglioramenti al ripristino di emergenza: il server Chat persistente supporta un'architettura del pool estesa che consente di estendere un singolo pool di server Chat persistente tra due siti, ovvero un singolo pool logico nella topologia, con i server del pool che si trovano fisicamente su due siti.</span><span class="sxs-lookup"><span data-stu-id="83b22-169">Disaster recovery improvements: Persistent Chat Server supports a stretched pool architecture that enables a single Persistent Chat Server pool to be stretched across two sites (that is, a single logical pool in the topology, with servers in the pool physically located across two sites).</span></span> <span data-ttu-id="83b22-170">Il log shipping di SQL Server viene utilizzato per il ripristino di emergenza tra siti.</span><span class="sxs-lookup"><span data-stu-id="83b22-170">SQL Server Log Shipping is used for cross-site disaster recovery.</span></span>

<span data-ttu-id="83b22-171">Per ulteriori informazioni sulla disponibilità elevata e il ripristino di emergenza, vedere [Configuring Persistent Chat Server for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="83b22-171">For more information about high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a><span data-ttu-id="83b22-172">Modifiche principali dell'amministrazione e della gestione per il server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="83b22-172">Key Administration and Management Changes for Persistent Chat Server</span></span>

<span data-ttu-id="83b22-173">Lync Server 2013 ha semplificato l'amministrazione e la gestione del server Chat persistente fornendo:</span><span class="sxs-lookup"><span data-stu-id="83b22-173">Lync Server 2013 has made it easier to administer and manage Persistent Chat Server by providing:</span></span>

  - <span data-ttu-id="83b22-174">Amministrazione e gestione unificata.</span><span class="sxs-lookup"><span data-stu-id="83b22-174">Unified administration and management.</span></span> <span data-ttu-id="83b22-175">Lync Server 2013 facilita la gestione e l'amministrazione del server Chat persistente tramite gli strumenti già noti agli amministratori di Lync.</span><span class="sxs-lookup"><span data-stu-id="83b22-175">Lync Server 2013 makes it easier to manage and administer Persistent Chat Server by using tools that are already familiar to Lync administrators.</span></span> <span data-ttu-id="83b22-176">Il server Chat persistente include un'esperienza dell'interfaccia utente amministrativa integrata con il pannello di controllo di Lync Server, che consente di risolvere i problemi relativi alle prestazioni con le versioni precedenti dell'interfaccia utente di Group Chat Server.</span><span class="sxs-lookup"><span data-stu-id="83b22-176">Persistent Chat Server includes an administrative user interface experience that is integrated with the Lync Server Control Panel, which addresses performance issues with the previous versions of the Group Chat Server user interface.</span></span> <span data-ttu-id="83b22-177">Inoltre, il server Chat persistente include un insieme di cmdlet di Windows PowerShell per amministrare e gestire le categorie del server Chat persistente, le sale del server Chat persistente (tra cui l'eliminazione di sale e l'eliminazione di contenuto obsoleto) e i componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="83b22-177">Also, Persistent Chat Server includes a collection of Windows PowerShell cmdlets to administer and manage Persistent Chat Server categories, Persistent Chat Server rooms (including deleting rooms and purging obsolete content), and add-ins.</span></span>

  - <span data-ttu-id="83b22-178">Modello di amministrazione semplificato.</span><span class="sxs-lookup"><span data-stu-id="83b22-178">Simplified administration model.</span></span> <span data-ttu-id="83b22-179">Lync Server 2013 è stato modificato e semplificato il modello del server Chat persistente affrontando i seguenti requisiti principali del cliente:</span><span class="sxs-lookup"><span data-stu-id="83b22-179">Lync Server 2013 has changed and simplified the Persistent Chat Server model by addressing the following key customer requirements:</span></span>
    
      - <span data-ttu-id="83b22-180">Rimuovere le gerarchie nidificate complesse degli ambiti e delle categorie.</span><span class="sxs-lookup"><span data-stu-id="83b22-180">Remove the complex nested hierarchies of scopes and categories.</span></span>
    
      - <span data-ttu-id="83b22-181">Supporto per definire gli elenchi negati e gli elenchi consentiti (ambiti) per i clienti di MindAlign correnti che stanno pianificando la migrazione al server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="83b22-181">Support to define deny lists as well as allowed lists (scopes) for current MindAlign customers who are planning to migrate to Persistent Chat Server.</span></span>

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a><span data-ttu-id="83b22-182">Cosa c'è di diverso nei ruoli degli utenti dalle versioni precedenti di Group Chat Server?</span><span class="sxs-lookup"><span data-stu-id="83b22-182">What’s Different about User Roles from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="83b22-183">Lync Server 2010, Group Chat aveva un ruolo di amministratore utente, un ruolo di amministratore della chat room e un ruolo di amministratore di Lync Server in grado di gestire i componenti aggiuntivi. il server Chat persistente fornisce semplicemente un ruolo amministratore di chat persistente (simile ad altri ruoli di controllo di accesso basato sul ruolo di Lync Server).</span><span class="sxs-lookup"><span data-stu-id="83b22-183">Lync Server 2010, Group Chat had a user administrator role, a chat room administrator role and a Lync Server administrator role that could manage add-ins. Persistent Chat Server simply provides a Persistent Chat Administrator role (which is similar to other Lync Server role-based access control (RBAC) roles).</span></span> <span data-ttu-id="83b22-184">Chiunque sia membro di questo ruolo RBAC può gestire le chat room, i componenti aggiuntivi e le categorie (e quindi ottenere l'accesso degli utenti per queste categorie) e la configurazione del pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="83b22-184">Anyone who is a member of this RBAC role can manage chat rooms, add-ins, and categories (and therefore gain user access for these categories), and configuration of the Persistent Chat Server pool.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a><span data-ttu-id="83b22-185">Che cos'è diverse categorie di chat room dalle versioni precedenti di Group Chat Server?</span><span class="sxs-lookup"><span data-stu-id="83b22-185">What’s Different about Chat Room Categories from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="83b22-186">Le categorie delle chat room non possono più essere annidate e la categoria radice non può più essere modificata.</span><span class="sxs-lookup"><span data-stu-id="83b22-186">Chat room categories can no longer be nested, and the root category can no longer be modified.</span></span> <span data-ttu-id="83b22-187">AllowedMembers/DeniedMembers è costituito da un ambito utilizzato nelle versioni legacy di Group Chat Server (eccetto per il fatto che non supportava la specifica di un elenco negato).</span><span class="sxs-lookup"><span data-stu-id="83b22-187">AllowedMembers/DeniedMembers comprise what a scope used to be in legacy Group Chat Server versions (except that it didn’t support specifying a Denied list).</span></span> <span data-ttu-id="83b22-188">Gli ambiti non possono più essere ignorati, perché non sono presenti categorie nidificate.</span><span class="sxs-lookup"><span data-stu-id="83b22-188">Scopes can no longer be overridden, because there are no nested categories.</span></span> <span data-ttu-id="83b22-189">Un amministratore di chat persistente in Lync Server 2013 è in grado di creare e gestire le categorie delle chat room.</span><span class="sxs-lookup"><span data-stu-id="83b22-189">A Persistent Chat Administrator in Lync Server 2013 can create and manage chat room categories.</span></span> <span data-ttu-id="83b22-190">Durante la creazione e la gestione delle categorie di chat room, un amministratore di chat persistente può configurare le entità (gruppi/contenitori/utenti di Active Directory) che hanno accesso ai membri/creatori delle chat room di una categoria specifica.</span><span class="sxs-lookup"><span data-stu-id="83b22-190">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="83b22-191">Un amministratore di chat persistente può anche aggiungere DeniedMembers a una categoria e queste diventano esclusioni esplicite per l'elenco consentiti.</span><span class="sxs-lookup"><span data-stu-id="83b22-191">A Persistent Chat Administrator can also add DeniedMembers to a category, and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="83b22-192">I Membri non consentiti hanno la priorità rispetto al contenuto dei Membri consentiti.</span><span class="sxs-lookup"><span data-stu-id="83b22-192">DeniedMembers override what’s in AllowedMembers.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a><span data-ttu-id="83b22-193">Quali sono le differenze tra le proprietà delle chat room delle versioni precedenti di Group Chat Server?</span><span class="sxs-lookup"><span data-stu-id="83b22-193">What’s Different about Chat Room Properties from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="83b22-194">In Lync Server 2013, Persistent Chat Server esiste un nuovo concetto di chat room aperta.</span><span class="sxs-lookup"><span data-stu-id="83b22-194">A new concept of open chat rooms exists in Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="83b22-195">Tutti i membri consentiti possono partecipare alla chat room, senza l'appartenenza esclusiva.</span><span class="sxs-lookup"><span data-stu-id="83b22-195">All allowed members can join the chat room, without exclusive membership.</span></span>

<span data-ttu-id="83b22-196">Sono state eliminate le seguenti proprietà della chat room incluse nelle versioni precedenti del server Chat persistente:</span><span class="sxs-lookup"><span data-stu-id="83b22-196">The following chat room properties that were included in previous versions of Persistent Chat Server have been eliminated:</span></span>

  - <span data-ttu-id="83b22-197">Topic: una sala ora contiene solo una descrizione.</span><span class="sxs-lookup"><span data-stu-id="83b22-197">Topic: A Room now only has a Description.</span></span>

  - <span data-ttu-id="83b22-198">Creare un nuovo elenco di membri: nel server Chat persistente tutte le chat room iniziano con l'appartenenza vuota (e possono essere massimizzate a un'appartenenza uguale ai membri consentiti).</span><span class="sxs-lookup"><span data-stu-id="83b22-198">Create New Member list: In Persistent Chat Server, all chat rooms start with empty membership (and can maximize to a membership equaling the Allowed Members).</span></span>

  - <span data-ttu-id="83b22-199">Caricamento file: utilizzato per essere un'impostazione per chat room per controllare se i file di caricamento/download sono stati consentiti.</span><span class="sxs-lookup"><span data-stu-id="83b22-199">File Upload: Used to be a setting per chat room to control whether file upload/downloads were allowed.</span></span> <span data-ttu-id="83b22-200">Questo è ora impostato solo il livello di categoria e si applica a tutte le sale di quella categoria.</span><span class="sxs-lookup"><span data-stu-id="83b22-200">This is now set only the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="83b22-201">Cronologia chat: utilizzata come impostazione per la chat room per controllare se la cronologia della chat è stata abilitata, ma è ora impostata solo a livello di categoria e si applica a tutte le sale di quella categoria.</span><span class="sxs-lookup"><span data-stu-id="83b22-201">Chat History: Used to be a setting per chat room to control if Chat History was enabled, but is now set only at the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="83b22-202">Invita: una sala eredita sempre l'impostazione invita per la categoria; oppure può essere disattivata nella sala.</span><span class="sxs-lookup"><span data-stu-id="83b22-202">Invites: A room always inherits the Invites setting for the category; or it can be turned off on the room.</span></span> <span data-ttu-id="83b22-203">Una chat room non può essere attivata se la categoria è stata precedentemente impostata su inviti.</span><span class="sxs-lookup"><span data-stu-id="83b22-203">A room cannot turn on Invites if the category was previously set to Invites off.</span></span>

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a><span data-ttu-id="83b22-204">Quali sono le differenze relative ai criteri delle versioni precedenti di Group Chat Server?</span><span class="sxs-lookup"><span data-stu-id="83b22-204">What’s Different about Policies from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="83b22-205">Il server Chat persistente ha un nuovo criterio di Lync abilitato con chat persistente, per le impostazioni utente/pool/sito/globale.</span><span class="sxs-lookup"><span data-stu-id="83b22-205">Persistent Chat Server has a new Lync policy enabled with Persistent Chat, per user/pool/site/global settings.</span></span> <span data-ttu-id="83b22-206">Nel client Lync 2013, l'ambiente di chat persistente è disponibile solo per gli utenti abilitati dal criterio per la chat persistente (direttamente o tramite l'impostazione pool/site/Global).</span><span class="sxs-lookup"><span data-stu-id="83b22-206">In the Lync 2013 client, the Persistent Chat environment is available only for users who are enabled by policy for Persistent Chat (either directly or through the pool/site/global setting).</span></span>

<span data-ttu-id="83b22-207">Le versioni precedenti di Group Chat Server non disponevano di criteri integrati nei criteri di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83b22-207">Previous versions of Group Chat Server did not have any policies integrated into the Lync Server policies.</span></span> <span data-ttu-id="83b22-208">Per ogni utente e per categoria/sala base, utilizzando la funzionalità **può caricare i file** per utente, è possibile rendere l'utente un amministratore utente, un amministratore di chat room o configurare la capacità dell'utente di caricare i file.</span><span class="sxs-lookup"><span data-stu-id="83b22-208">On a per user and per category/room basis, by using the **Can Upload Files** per user feature, you could make the user a User administrator, a chat room administrator, or configure the user’s ability to upload files.</span></span> <span data-ttu-id="83b22-209">La caratteristica di **caricamento dei file** del server Chat persistente è solo per categoria.</span><span class="sxs-lookup"><span data-stu-id="83b22-209">The Persistent Chat Server **File Upload** feature is just per category.</span></span>

</div>

<div>

## <a name="logging"></a><span data-ttu-id="83b22-210">Registrazione</span><span class="sxs-lookup"><span data-stu-id="83b22-210">Logging</span></span>

<span data-ttu-id="83b22-211">La registrazione per il server Chat persistente e System Center Operations Manager è integrata nella registrazione di traccia di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="83b22-211">Logging for Persistent Chat Server and System Center Operations Manager is integrated into the Lync Server 2013 trace logging.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="83b22-212">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83b22-212">See Also</span></span>


[<span data-ttu-id="83b22-213">Pianificazione del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83b22-213">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
