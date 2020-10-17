---
title: Lync Server 2013 topologie supportate
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported topologies
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425833(v=OCS.15)
ms:contentKeyID: 48183832
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4754881d2ed3205c4f06d5468001c6e45880278c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523963"
---
# <a name="supported-topologies-in-lync-server-2013"></a><span data-ttu-id="23d37-102">Topologie supportate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23d37-102">Supported topologies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23d37-103">_**Ultimo argomento modificato:** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="23d37-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="23d37-104">Lync Server 2013 supporta la distribuzione di siti in locale in un'organizzazione e l'integrazione di distribuzioni locali con distribuzioni di Lync Online, che è nota come distribuzione ibrida.</span><span class="sxs-lookup"><span data-stu-id="23d37-104">Lync Server 2013 supports deployment of sites on premises in an organization and integration of on-premises deployments with Lync Online deployments, which is known as a hybrid deployment.</span></span> <span data-ttu-id="23d37-105">In questo tipo di distribuzione alcuni utenti sono ospitati in locale, mentre altri online.</span><span class="sxs-lookup"><span data-stu-id="23d37-105">In a hybrid deployment, some users are homed on-premises and some users are homed online.</span></span>

<span data-ttu-id="23d37-106">Per le distribuzioni locali, Lync Server 2013 supporta la distribuzione di uno o più siti che possono essere ridimensionati per soddisfare i requisiti di disponibilità elevata e posizione.</span><span class="sxs-lookup"><span data-stu-id="23d37-106">For on-premises deployments, Lync Server 2013 supports deployment of one or more sites that can be scaled to meet high availability and location requirements.</span></span> <span data-ttu-id="23d37-107">È possibile strutturare tali siti e i relativi componenti in modo da soddisfare i requisiti di accesso e resilienza dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="23d37-107">You can structure these sites and their components to meet the access and resiliency requirements of your organization.</span></span>

<span data-ttu-id="23d37-108">Una distribuzione locale di Lync Server 2013 è costituita dai seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="23d37-108">A Lync Server 2013 on-premises deployment consists of the following:</span></span>

  - <span data-ttu-id="23d37-p103">La distribuzione deve includere almeno un sito centrale, noto anche come data center. In ogni sito centrale deve essere contenuto almeno un pool Enterprise Edition Front End o un server Standard Edition, costituiti come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="23d37-p103">Your deployment must include at least one central site (also known as a data center). Each central site must contain at least one Enterprise Edition Front End pool or one Standard Edition server. These consist of the following:</span></span>
    
      - <span data-ttu-id="23d37-112">Pool Enterprise Edition Front End, costituito da uno o più Front End Server (in genere almeno due per la scalabilità) e un server back-end separato.</span><span class="sxs-lookup"><span data-stu-id="23d37-112">Enterprise Edition Front End pool, which consists of one or more Front End Servers (typically, at least two Front End Servers for scalability) and a separate Back End Server.</span></span> <span data-ttu-id="23d37-113">Un pool Front end può contenere un massimo di dodici front end server.</span><span class="sxs-lookup"><span data-stu-id="23d37-113">A Front End pool can contain a maximum of twelve Front End Servers.</span></span> <span data-ttu-id="23d37-114">In presenza di più Front End Server è richiesto il bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="23d37-114">Load balancing is required for multiple Front End Servers.</span></span> <span data-ttu-id="23d37-115">Per il traffico SIP è consigliato il bilanciamento del carico DNS, ma è supportato anche il bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="23d37-115">For SIP traffic, we recommend DNS load balancing, but hardware load balancing is also supported.</span></span> <span data-ttu-id="23d37-116">Se si usa il bilanciamento del carico DNS per il traffico SIP, è comunque necessario un dispositivo di bilanciamento del carico hardware per il traffico HTTP.</span><span class="sxs-lookup"><span data-stu-id="23d37-116">If you use DNS load balancing for SIP traffic, you still need a hardware load balancer for HTTP traffic.</span></span> <span data-ttu-id="23d37-117">È consigliabile eseguire il mirroring di SQL Server per la disponibilità elevata dei database.</span><span class="sxs-lookup"><span data-stu-id="23d37-117">We recommend SQL Server mirroring for high availability of databases.</span></span> <span data-ttu-id="23d37-118">Il database back-end richiede un'istanza separata, ma è possibile collocare insieme a esso il database di Archiviazione, il database di Monitoraggio, il database Persistent Chat e il database di Conformità Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="23d37-118">The back-end database requires a separate instance, but you can collocate the archiving database, monitoring database, persistent chat database, and persistent chat compliance database with it.</span></span> <span data-ttu-id="23d37-119">Lync Server 2013 supporta l'utilizzo di un cluster condiviso per le condivisioni di file nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="23d37-119">Lync Server 2013 supports the use of a shared cluster for the file shares in your deployment.</span></span> <span data-ttu-id="23d37-120">Per informazioni dettagliate sui requisiti di archiviazione dei database, vedere [database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="23d37-120">For details about database storage requirements, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="23d37-121">Per informazioni dettagliate sui requisiti di archiviazione dei file, vedere [file Storage Support in Lync Server 2013](lync-server-2013-file-storage-support.md).</span><span class="sxs-lookup"><span data-stu-id="23d37-121">For details about file storage requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="23d37-122">Se si installano i database di Lync Server, è consigliabile valutare tutti i fattori che possono influire sulla disponibilità e sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="23d37-122">If you collocate Lync Server databases, we highly recommend assessing all factors that might affect availability and performance.</span></span> <span data-ttu-id="23d37-123">Per verificare le capacità di failover, è consigliabile testare tutti gli scenari di failover.</span><span class="sxs-lookup"><span data-stu-id="23d37-123">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>

        
        </div>
    
      - <span data-ttu-id="23d37-124">Server Standard Edition, che include un database di SQL Server Express collocato.</span><span class="sxs-lookup"><span data-stu-id="23d37-124">Standard Edition server, which includes a collocated SQL Server Express database.</span></span>

  - <span data-ttu-id="23d37-125">Nella distribuzione possono inoltre essere presenti uno o più siti di succursale associati a un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="23d37-125">Your deployment can also have one or more branch sites associated with a central site.</span></span>

<span data-ttu-id="23d37-126">In questa sezione vengono descritti i siti e i componenti di una distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="23d37-126">This section describes the sites and components of a Lync Server 2013 deployment.</span></span> <span data-ttu-id="23d37-127">Per informazioni dettagliate sul sito, la topologia e la pianificazione del componente di Lync Server 2013, vedere [nozioni di base sulla topologia che è necessario conoscere prima di pianificare Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) e le [topologie di riferimento in Lync Server 2013](lync-server-2013-reference-topologies.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="23d37-127">For details about Lync Server 2013 site, topology, and component planning, see [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) and [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="23d37-128">Per informazioni dettagliate sull'integrazione dei componenti delle versioni precedenti, vedere [supported Migration paths and Coesistence in Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="23d37-128">For details about integration of components of previous releases, see [Supported migration paths and coexistence scenarios in Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="23d37-129">I pool allungati non sono supportati per i ruoli front-end, Edge, Mediation e server Director.</span><span class="sxs-lookup"><span data-stu-id="23d37-129">Stretched pools are not supported for the Front End, Edge, Mediation, and Director server roles.</span></span>



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a><span data-ttu-id="23d37-130">Topologie e componenti di un sito centrale (in locale)</span><span class="sxs-lookup"><span data-stu-id="23d37-130">Central Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="23d37-131">Una topologia di un sito centrale deve includere un solo pool Front End o un solo server Standard Edition, tuttavia ogni sito centrale può includere anche gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="23d37-131">Although a central site topology must include one Front End pool or one Standard Edition server, each central site can also contain the following:</span></span>

  - <span data-ttu-id="23d37-p107">Più pool Front End, che possono trovarsi nello stesso dominio o in domini diversi. Tutti i Front End Server di un pool Front End e il relativo server back-end devono tuttavia trovarsi nello stesso dominio.</span><span class="sxs-lookup"><span data-stu-id="23d37-p107">Multiple Front End pools, which can be in the same domain or different domains. However, all Front End Servers in a Front End pool, and the Back End Server for that pool, must be in the same domain.</span></span>

  - <span data-ttu-id="23d37-134">Più server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="23d37-134">Multiple Standard Edition servers.</span></span>

  - <span data-ttu-id="23d37-135">Server Office Web Apps, utilizzato con Office Web Applications in Lync Server 2013 per gestire la condivisione e il rendering delle presentazioni di Microsoft PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="23d37-135">Office Web Apps Server, which is used with Office Web Applications in Lync Server 2013 to handle the sharing and rendering of Microsoft PowerPoint presentations.</span></span>

  - <span data-ttu-id="23d37-136">Un server perimetrale o un pool di Edge nella propria rete, se si desidera che la distribuzione supporti i partner federati, la connettività di messaggistica istantanea pubblica, un gateway XMPP (Extensible Messaging and Presence Protocol), l'accesso utente remoto, la partecipazione degli utenti anonimi alle riunioni o la messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="23d37-136">Edge Server or Edge pool in your perimeter network, if you want your deployment to support federated partners, public IM connectivity, an extensible messaging and presence protocol (XMPP) gateway, remote user access, participation of anonymous users in meetings, or Exchange Unified Messaging (UM).</span></span> <span data-ttu-id="23d37-137">Non è possibile collocare altri ruoli del server con un server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="23d37-137">You cannot collocate any other server role with an Edge Server.</span></span> <span data-ttu-id="23d37-138">È consigliabile usare il bilanciamento del carico DNS, se appropriato, ma è supportato anche il bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="23d37-138">We recommend DNS load balancing, where appropriate, but hardware load balancing is also supported.</span></span> <span data-ttu-id="23d37-139">L'interfaccia perimetrale interna e quella esterna devono utilizzare lo stesso tipo di bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="23d37-139">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="23d37-140">Non è possibile utilizzare il bilanciamento del carico DNS in un'interfaccia perimetrale e il bilanciamento del carico hardware nell'altra.</span><span class="sxs-lookup"><span data-stu-id="23d37-140">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span> <span data-ttu-id="23d37-141">Per informazioni dettagliate sui requisiti e il supporto per il bilanciamento del carico, vedere [Planning for External User Access in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) nella documentazione relativa alla pianificazione e [distribuzione di accesso utente esterno in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="23d37-141">For details about load balancing requirements and support, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="23d37-142">Mediation Server o pool, se si desidera supportare le conferenze telefoniche con accesso esterno o VoIP aziendale in un pool Front End nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="23d37-142">Mediation Server or pool, if you want to support Enterprise Voice or dial-in conferencing in a Front End pool at the central site.</span></span> <span data-ttu-id="23d37-143">A seconda del modo in cui si distribuisce il supporto VoIP aziendale, è possibile collocare il Mediation Server in un pool Front End (impostazione predefinita) oppure distribuire un server o un pool di Mediation autonomo.</span><span class="sxs-lookup"><span data-stu-id="23d37-143">Depending on how you deploy Enterprise Voice support, you can collocate the Mediation Server in a Front End pool (the default) or deploy a stand-alone Mediation Server or pool.</span></span> <span data-ttu-id="23d37-144">È possibile utilizzare il bilanciamento del carico DNS, hardware o applicazioni, se necessario, per distribuire il traffico da un peer gateway del pool di Mediation Server, tra cui un gateway PSTN, un IP-PBX o un SBC (Session Border Control) del trunk SIP. Per informazioni dettagliate sulla pianificazione della topologia del Mediation Server appropriato, vedere [Deployment Guidelines for Mediation Server in Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="23d37-144">You can use DNS, hardware, or application load balancing (when appropriate) to distribute traffic from a Mediation Server pool’s gateway peer, including a PSTN gateway, IP-PBX, or SIP trunk Session Border Control (SBC).For details about planning the appropriate Mediation Server topology, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="23d37-145">Server Chat persistente, se si desidera che gli utenti siano in grado di partecipare a conversazioni a più parti, basate su argomenti che persistono nel tempo.</span><span class="sxs-lookup"><span data-stu-id="23d37-145">Persistent Chat Server, if you want to users to be able to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="23d37-146">Per offrire maggiore capacità e maggiore affidabilità, la topologia può includere più computer che eseguono il server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="23d37-146">To provide more capacity and increased reliability, your topology can include multiple computers running Persistent Chat Server.</span></span> <span data-ttu-id="23d37-147">Non è possibile collocare il server Chat persistente con altri ruoli del server in un pool Enterprise.</span><span class="sxs-lookup"><span data-stu-id="23d37-147">You cannot collocate Persistent Chat Server with other server roles in an Enterprise pool.</span></span> <span data-ttu-id="23d37-148">Tuttavia, è possibile collocare il server Chat persistente in un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="23d37-148">However, you can collocate Persistent Chat Server on a Standard Edition server.</span></span> <span data-ttu-id="23d37-149">Persistent Chat richiede un database e, se si implementa la conformità a chat persistente, un database di conformità di chat persistente, ma i database possono essere collocati con il database di archiviazione, il database di monitoraggio o il server back-end di un pool Enterprise Edition front end.</span><span class="sxs-lookup"><span data-stu-id="23d37-149">Persistent chat requires a database and, if you implement persistent chat compliance, a persistent chat compliance database, but the databases can be collocated with the Archiving database, Monitoring database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="23d37-150">Per informazioni dettagliate sulla pianificazione della topologia del server Chat persistente, vedere [Planning for Persistent Chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="23d37-150">For details about planning the appropriate Persistent Chat Server topology, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="23d37-151">Monitoraggio, se si desidera supportare la raccolta dati per la qualità audio/video percepita dagli utenti (QoE) e la registrazione dettagli chiamata per le conferenze audio/video e il VoIP aziendale nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="23d37-151">Monitoring, if you want to support data collection for audio/video Quality of Experience (QoE) and call detail recording (CDR) for Enterprise Voice and A/V conferences in your deployment.</span></span> <span data-ttu-id="23d37-152">Facoltativamente, è possibile installare Microsoft System Center Operations Manager (in precedenza Microsoft Operations Manager), in cui vengono utilizzati i dati di monitoraggio CDR e QoE per generare avvisi quasi in tempo reale che mostrano l'integrità dell'affidabilità delle chiamate e la qualità dei supporti.</span><span class="sxs-lookup"><span data-stu-id="23d37-152">Optionally, you can install the Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which uses Monitoring CDR and QoE data to generate near real-time alerts that show the health of call reliability and media quality.</span></span> <span data-ttu-id="23d37-153">Quando viene distribuito, Monitoraggio viene collocato nei Front End Server o in un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="23d37-153">Monitoring, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="23d37-154">Monitoraggio richiede un database che può essere tuttavia collocato insieme al database di Archiviazione, al database Persistent Chat, al database di Conformità Persistent Chat o nel server back-end di un pool Enterprise Edition Front End.</span><span class="sxs-lookup"><span data-stu-id="23d37-154">Monitoring requires a database, but the database can be collocated with the Archiving database, persistent chat database, persistent chat compliance database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span>

  - <span data-ttu-id="23d37-155">Archiviazione, se si vuole archiviare le comunicazioni di messaggistica istantanea e il contenuto delle riunioni (per motivi di conformità) nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="23d37-155">Archiving, if you want to archive IM communications and meeting content (for compliance reasons) in your deployment.</span></span> <span data-ttu-id="23d37-156">Quando viene distribuita, Archiviazione viene collocata nei Front End Server o in un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="23d37-156">Archiving, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="23d37-157">L'archiviazione di archiviazione richiede la distribuzione di un database di archiviazione o l'integrazione con l'archiviazione di Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="23d37-157">Archiving storage requires either deployment of an Archiving database or integration with Exchange 2013 storage.</span></span> <span data-ttu-id="23d37-158">Se si utilizzano entrambi, ovvero la *modalità mista*, lo spazio di archiviazione di Exchange 2013 viene utilizzato per archiviare i dati di archiviazione per gli utenti ospitati in Exchange 2013 e il database di archiviazione viene utilizzato per archiviare i dati di tutti gli altri utenti della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="23d37-158">If you use both, which is known as *mixed mode*, Exchange 2013 storage is used to store archive data for users who are homed on Exchange 2013, and the Archiving database is used to archive data for all other users in your deployment.</span></span> <span data-ttu-id="23d37-159">Se è richiesto un database di archiviazione, questo può essere collocato nel database di Monitoraggio, nel database Persistent Chat, nel database di Conformità Persistent Chat o nel server back-end di un pool Enterprise Edition Front End.</span><span class="sxs-lookup"><span data-stu-id="23d37-159">If you require an Archiving database, the database can be collocated on the Monitoring database, persistent chat database, persistent chat compliance database, or on the Back End Server of a Front End pool.</span></span> <span data-ttu-id="23d37-160">Per informazioni dettagliate sulla pianificazione della topologia di archiviazione appropriata, vedere [Planning for archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="23d37-160">For details about planning the appropriate Archiving topology, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="23d37-161">Server Director o del pool di server Director, se si desidera semplificare la resilienza e il reindirizzamento delle richieste degli utenti di Lync 2013 al pool di casa dell'utente, che può essere un pool Enterprise Edition front end o uno Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="23d37-161">Director or Director pool, if you want to facilitate resiliency and redirection of Lync Server 2013 user requests to the user’s home pool, which can be either an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="23d37-162">È consigliabile distribuire un Director o un pool di server Director in ogni sito centrale che supporta l'accesso degli utenti esterni e in ogni sito centrale in cui vengono distribuiti uno o più pool Front End.</span><span class="sxs-lookup"><span data-stu-id="23d37-162">We recommend that you deploy a Director or Director pool in each central site that supports external user access and in each central site in which you deploy one or more Front End pools.</span></span> <span data-ttu-id="23d37-163">Ogni pool di server Director può includere un massimo di dieci Director.</span><span class="sxs-lookup"><span data-stu-id="23d37-163">Each Director pool can contain a maximum of ten Directors.</span></span> <span data-ttu-id="23d37-164">Non è possibile collocare un Director con altri ruoli del server.</span><span class="sxs-lookup"><span data-stu-id="23d37-164">A Director cannot be collocated with any other server role.</span></span> <span data-ttu-id="23d37-165">Per informazioni dettagliate sulla pianificazione della topologia del Director appropriata, vedere [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="23d37-165">For details about planning the appropriate Director topology, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="23d37-166">Proxy inverso, che non è un componente di Lync Server 2013, ma è obbligatorio se si desidera supportare la condivisione di contenuto Web per gli utenti federati o per il supporto del traffico per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="23d37-166">Reverse proxy, which is not a Lync Server 2013 component, but is required if you want to support sharing of web content for federated users or to support Mobility traffic.</span></span> <span data-ttu-id="23d37-167">Non è possibile collocare un server proxy inverso con qualsiasi ruolo del server Lync Server 2013, ma è possibile implementare il supporto del proxy inverso per una distribuzione di Lync Server 2013 configurando il supporto su un server proxy inverso esistente nell'organizzazione utilizzato per altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="23d37-167">You cannot collocate a reverse proxy server with any Lync Server 2013 server role, but you can implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span> <span data-ttu-id="23d37-168">Per informazioni dettagliate sui server proxy inversi, vedere [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="23d37-168">For details about reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="23d37-169">In Lync Server 2013, A/V Conferencing, monitoraggio e archiviazione eseguiti nei front end server e non sono più ruoli del server distinti.</span><span class="sxs-lookup"><span data-stu-id="23d37-169">In Lync Server 2013, A/V Conferencing, Monitoring, and Archiving run on Front End Servers and are no longer separate server roles.</span></span>



</div>

<span data-ttu-id="23d37-170">Tutti i pool Front End e i server Standard Edition distribuiti nel sito centrale condividono gli elementi seguenti distribuiti per il sito centrale:</span><span class="sxs-lookup"><span data-stu-id="23d37-170">All Front End pools and Standard Edition servers that you deploy at a central site share any of the following that you deploy for the central site:</span></span>

  - <span data-ttu-id="23d37-171">Director o pool di server Director</span><span class="sxs-lookup"><span data-stu-id="23d37-171">Director or Director pool</span></span>

  - <span data-ttu-id="23d37-172">Mediation Server autonomo o pool di Mediation Server</span><span class="sxs-lookup"><span data-stu-id="23d37-172">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="23d37-173">server Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="23d37-173">Office Web Apps Server</span></span>

  - <span data-ttu-id="23d37-174">Server perimetrale o pool di server perimetrali</span><span class="sxs-lookup"><span data-stu-id="23d37-174">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="23d37-175">Pool o server Persistent Chat</span><span class="sxs-lookup"><span data-stu-id="23d37-175">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="23d37-176">Monitoraggio</span><span class="sxs-lookup"><span data-stu-id="23d37-176">Monitoring</span></span>

  - <span data-ttu-id="23d37-177">Archiviazione</span><span class="sxs-lookup"><span data-stu-id="23d37-177">Archiving</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="23d37-178">Un server di messaggistica unificata di Exchange può essere implementato con la distribuzione di Lync Server 2013 se si desidera supportare l'integrazione della messaggistica unificata di Exchange 2013, ma non è un componente del sito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="23d37-178">An Exchange UM Server can be implemented with your Lync Server 2013 deployment if you want to support integration of Exchange 2013 Unified Messaging, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="23d37-179">Più siti centrali possono inoltre condividere gli elementi seguenti distribuiti in un sito centrale:</span><span class="sxs-lookup"><span data-stu-id="23d37-179">Multiple central sites can also share any of the following that you deploy in one central site:</span></span>

  - <span data-ttu-id="23d37-180">Mediation Server autonomo o pool di Mediation Server</span><span class="sxs-lookup"><span data-stu-id="23d37-180">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="23d37-181">Server perimetrale o pool di server perimetrali</span><span class="sxs-lookup"><span data-stu-id="23d37-181">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="23d37-182">Pool o server Persistent Chat</span><span class="sxs-lookup"><span data-stu-id="23d37-182">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="23d37-183">Archiviazione</span><span class="sxs-lookup"><span data-stu-id="23d37-183">Archiving</span></span>

  - <span data-ttu-id="23d37-184">Monitoraggio</span><span class="sxs-lookup"><span data-stu-id="23d37-184">Monitoring</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="23d37-185">Un server di messaggistica unificata di Exchange può essere implementato con la distribuzione di Lync Server 2013 e condiviso da più siti centrali, ma non è un componente del sito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="23d37-185">An Exchange UM Server can be implemented with your Lync Server 2013 deployment and shared by multiple central sites, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="23d37-186">Per informazioni dettagliate sui ruoli e le funzionalità del server Lync Server 2013, vedere [Server Roles in Lync server 2013](lync-server-2013-server-roles.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="23d37-186">For details about Lync Server 2013 server roles and functionality, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md) in the Planning documentation.</span></span>

<span data-ttu-id="23d37-187">Per un riepilogo del supporto della collocazione dei server di Lync Server 2013, vedere [supported server Collocation in Lync server 2013](lync-server-2013-supported-server-collocation.md).</span><span class="sxs-lookup"><span data-stu-id="23d37-187">For a summary of Lync Server 2013 server collocation support, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<span data-ttu-id="23d37-188">Oltre ai ruoli del server e alle funzionalità descritti in precedenza in questa sezione, Lync Server 2013 include componenti e opzioni aggiuntivi, che possono includere alcuni o tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="23d37-188">In addition to the server roles and functionality covered previously in this section, Lync Server 2013 has additional components and options, which can include some or all of the following:</span></span>

  - <span data-ttu-id="23d37-189">Firewall</span><span class="sxs-lookup"><span data-stu-id="23d37-189">Firewalls</span></span>

  - <span data-ttu-id="23d37-190">Gateway PSTN (con la distribuzione di VoIP aziendale)</span><span class="sxs-lookup"><span data-stu-id="23d37-190">PSTN gateways (if deploying Enterprise Voice)</span></span>

  - <span data-ttu-id="23d37-191">Server Messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="23d37-191">Exchange UM Server</span></span>

  - <span data-ttu-id="23d37-192">Bilanciamento del carico DNS</span><span class="sxs-lookup"><span data-stu-id="23d37-192">DNS load balancing</span></span>

  - <span data-ttu-id="23d37-193">Dispositivi di bilanciamento del carico hardware</span><span class="sxs-lookup"><span data-stu-id="23d37-193">Hardware load balancers</span></span>

  - <span data-ttu-id="23d37-194">Database di SQL Server</span><span class="sxs-lookup"><span data-stu-id="23d37-194">SQL Server databases</span></span>

  - <span data-ttu-id="23d37-195">Condivisioni file</span><span class="sxs-lookup"><span data-stu-id="23d37-195">File shares</span></span>

<span data-ttu-id="23d37-196">Per informazioni dettagliate su tutte le funzionalità, i componenti e le opzioni di Lync Server 2013, vedere la documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="23d37-196">For details about all of the Lync Server 2013 features, components, and options, see the Planning documentation.</span></span>

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a><span data-ttu-id="23d37-197">Topologie e componenti di un sito di succursale (in locale)</span><span class="sxs-lookup"><span data-stu-id="23d37-197">Branch Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="23d37-p115">Un sito di succursale è associato a un sito centrale e ogni Survivable Branch Appliance di un sito di succursale è associato a un pool Enterprise Edition Front End o a un server Standard Edition del sito centrale associato. Poiché i siti di succursale dipendono dal sito centrale per la maggior parte delle funzionalità, i componenti di un sito di succursale includono solo gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="23d37-p115">A branch site is associated with a central site, and each Survivable Branch Appliance in a branch site is associated with an Enterprise Edition Front End pool or a Standard Edition server in the associated central site. Branch sites depend on the central site for most of their functionality, so components at a branch site contain only the following:</span></span>

  - <span data-ttu-id="23d37-200">Survivable Branch Appliance, che combina un gateway PSTN (Public Switched Telephone Network) con alcune funzionalità di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="23d37-200">A Survivable Branch Appliance, which combines a public switched telephone network (PSTN) gateway with some Lync Server functionality.</span></span> <span data-ttu-id="23d37-201">Un Mediation Server può essere collocato con l'istanza del servizio di registrazione nel Survivable Branch Appliance ed è possibile distribuire un Mediation Server autonomo o un pool di Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="23d37-201">A Mediation Server can be collocated with the instance of the Registrar on the Survivable Branch Appliance, and you can deploy a stand-alone Mediation Server or pool of Mediation Servers.</span></span>

  - <span data-ttu-id="23d37-202">Survivable Branch Server, che è un server che esegue Windows Server in cui è installato Lync Server 2013 registrar e il software Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="23d37-202">A Survivable Branch Server, which is a server running Windows Server that has Lync Server 2013 Registrar and Mediation Server software installed.</span></span>

  - <span data-ttu-id="23d37-203">Un gateway PSTN autonomo (che non fa parte del Survivable Branch Appliance) e un Mediation Server autonomo.</span><span class="sxs-lookup"><span data-stu-id="23d37-203">A stand-alone PSTN gateway (not part of the Survivable Branch Appliance) and a stand-alone Mediation Server.</span></span>

<span data-ttu-id="23d37-204">I requisiti per i Survivable Branch Server sono gli stessi dei requisiti per qualsiasi ruolo del server Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="23d37-204">The requirements for Survivable Branch Servers are the same as the requirements for any Lync Server 2013 server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

