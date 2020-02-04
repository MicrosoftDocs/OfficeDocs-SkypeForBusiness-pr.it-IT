---
title: 'Lync Server 2013: Topologie supportate'
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
ms.openlocfilehash: 0f200cde348d1fbdc931daa25abef28aec804a1b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-topologies-in-lync-server-2013"></a><span data-ttu-id="f793f-102">Topologie supportate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f793f-102">Supported topologies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f793f-103">_**Argomento Ultima modifica:** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="f793f-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="f793f-104">Lync Server 2013 supporta la distribuzione di siti in locale in un'organizzazione e l'integrazione di distribuzioni locali con distribuzioni di Lync Online, nota come distribuzione ibrida.</span><span class="sxs-lookup"><span data-stu-id="f793f-104">Lync Server 2013 supports deployment of sites on premises in an organization and integration of on-premises deployments with Lync Online deployments, which is known as a hybrid deployment.</span></span> <span data-ttu-id="f793f-105">In una distribuzione ibrida alcuni utenti vengono ospitati in locale e alcuni utenti sono ospitati online.</span><span class="sxs-lookup"><span data-stu-id="f793f-105">In a hybrid deployment, some users are homed on-premises and some users are homed online.</span></span>

<span data-ttu-id="f793f-106">Per le distribuzioni locali, Lync Server 2013 supporta la distribuzione di uno o più siti che possono essere ridimensionati per soddisfare i requisiti di disponibilità e posizione elevati.</span><span class="sxs-lookup"><span data-stu-id="f793f-106">For on-premises deployments, Lync Server 2013 supports deployment of one or more sites that can be scaled to meet high availability and location requirements.</span></span> <span data-ttu-id="f793f-107">È possibile strutturare questi siti e i relativi componenti in modo che soddisfino i requisiti di accesso e resilienza dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f793f-107">You can structure these sites and their components to meet the access and resiliency requirements of your organization.</span></span>

<span data-ttu-id="f793f-108">Una distribuzione locale di Lync Server 2013 è composta dalle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f793f-108">A Lync Server 2013 on-premises deployment consists of the following:</span></span>

  - <span data-ttu-id="f793f-109">La distribuzione deve includere almeno un sito centrale (noto anche come centro dati).</span><span class="sxs-lookup"><span data-stu-id="f793f-109">Your deployment must include at least one central site (also known as a data center).</span></span> <span data-ttu-id="f793f-110">Ogni sito centrale deve contenere almeno un pool Front-end Enterprise Edition o un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f793f-110">Each central site must contain at least one Enterprise Edition Front End pool or one Standard Edition server.</span></span> <span data-ttu-id="f793f-111">Queste sono costituite dalle seguenti:</span><span class="sxs-lookup"><span data-stu-id="f793f-111">These consist of the following:</span></span>
    
      - <span data-ttu-id="f793f-112">Pool Front end Enterprise Edition, costituito da uno o più server front-end (in genere, almeno due server front-end per la scalabilità) e un server back-end separato.</span><span class="sxs-lookup"><span data-stu-id="f793f-112">Enterprise Edition Front End pool, which consists of one or more Front End Servers (typically, at least two Front End Servers for scalability) and a separate Back End Server.</span></span> <span data-ttu-id="f793f-113">Un pool Front-end può contenere un massimo di dodici server front-end.</span><span class="sxs-lookup"><span data-stu-id="f793f-113">A Front End pool can contain a maximum of twelve Front End Servers.</span></span> <span data-ttu-id="f793f-114">Il bilanciamento del carico è necessario per più server front-end.</span><span class="sxs-lookup"><span data-stu-id="f793f-114">Load balancing is required for multiple Front End Servers.</span></span> <span data-ttu-id="f793f-115">Per il traffico SIP, è consigliabile il bilanciamento del carico DNS, ma è supportato anche il bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="f793f-115">For SIP traffic, we recommend DNS load balancing, but hardware load balancing is also supported.</span></span> <span data-ttu-id="f793f-116">Se si usa il bilanciamento del carico DNS per il traffico SIP, è comunque necessario un servizio di bilanciamento del carico hardware per il traffico HTTP.</span><span class="sxs-lookup"><span data-stu-id="f793f-116">If you use DNS load balancing for SIP traffic, you still need a hardware load balancer for HTTP traffic.</span></span> <span data-ttu-id="f793f-117">È consigliabile il mirroring di SQL Server per l'elevata disponibilità dei database.</span><span class="sxs-lookup"><span data-stu-id="f793f-117">We recommend SQL Server mirroring for high availability of databases.</span></span> <span data-ttu-id="f793f-118">Il database back-end richiede un'istanza distinta, ma è possibile collocare il database di archiviazione, il database di monitoraggio, il database di chat persistente e il database di conformità della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f793f-118">The back-end database requires a separate instance, but you can collocate the archiving database, monitoring database, persistent chat database, and persistent chat compliance database with it.</span></span> <span data-ttu-id="f793f-119">Lync Server 2013 supporta l'uso di un cluster condiviso per le condivisioni file nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f793f-119">Lync Server 2013 supports the use of a shared cluster for the file shares in your deployment.</span></span> <span data-ttu-id="f793f-120">Per informazioni dettagliate sui requisiti di archiviazione del database, vedere [supporto software per database in Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="f793f-120">For details about database storage requirements, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="f793f-121">Per informazioni dettagliate sui requisiti di archiviazione dei file, vedere Supporto per l' [archiviazione dei file in Lync Server 2013](lync-server-2013-file-storage-support.md).</span><span class="sxs-lookup"><span data-stu-id="f793f-121">For details about file storage requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="f793f-122">Se si collocano i database di Lync Server, è consigliabile valutare tutti i fattori che possono influire sulla disponibilità e sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="f793f-122">If you collocate Lync Server databases, we highly recommend assessing all factors that might affect availability and performance.</span></span> <span data-ttu-id="f793f-123">Per verificare le funzionalità di failover, è consigliabile testare tutti i possibili scenari.</span><span class="sxs-lookup"><span data-stu-id="f793f-123">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>

        
        </div>
    
      - <span data-ttu-id="f793f-124">Server Standard Edition, che include un database SQL Server Express collocato.</span><span class="sxs-lookup"><span data-stu-id="f793f-124">Standard Edition server, which includes a collocated SQL Server Express database.</span></span>

  - <span data-ttu-id="f793f-125">La distribuzione può anche avere uno o più siti di succursale associati a un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="f793f-125">Your deployment can also have one or more branch sites associated with a central site.</span></span>

<span data-ttu-id="f793f-126">In questa sezione vengono descritti i siti e i componenti di una distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f793f-126">This section describes the sites and components of a Lync Server 2013 deployment.</span></span> <span data-ttu-id="f793f-127">Per informazioni dettagliate sul sito, la topologia e la pianificazione dei componenti di Lync Server 2013, vedere [nozioni di base sulla topologia prima della pianificazione di Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) e delle topologie [di riferimento in Lync Server 2013](lync-server-2013-reference-topologies.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="f793f-127">For details about Lync Server 2013 site, topology, and component planning, see [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) and [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="f793f-128">Per informazioni dettagliate sull'integrazione dei componenti delle versioni precedenti, vedere [percorsi di migrazione supportati e scenari di coesistenza in Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="f793f-128">For details about integration of components of previous releases, see [Supported migration paths and coexistence scenarios in Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f793f-129">I pool allungati non sono supportati per i ruoli server front-end, Edge, Mediation e Director.</span><span class="sxs-lookup"><span data-stu-id="f793f-129">Stretched pools are not supported for the Front End, Edge, Mediation, and Director server roles.</span></span>



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a><span data-ttu-id="f793f-130">Topologie e componenti del sito centrale (locale)</span><span class="sxs-lookup"><span data-stu-id="f793f-130">Central Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="f793f-131">Anche se la topologia di un sito centrale deve includere un pool Front-end o un server Standard Edition, ogni sito centrale può contenere anche le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f793f-131">Although a central site topology must include one Front End pool or one Standard Edition server, each central site can also contain the following:</span></span>

  - <span data-ttu-id="f793f-132">Più pool Front-End, che possono essere nello stesso dominio o in domini diversi.</span><span class="sxs-lookup"><span data-stu-id="f793f-132">Multiple Front End pools, which can be in the same domain or different domains.</span></span> <span data-ttu-id="f793f-133">Tuttavia, tutti i server front-end in un pool Front-end e il server back-end per il pool devono essere nello stesso dominio.</span><span class="sxs-lookup"><span data-stu-id="f793f-133">However, all Front End Servers in a Front End pool, and the Back End Server for that pool, must be in the same domain.</span></span>

  - <span data-ttu-id="f793f-134">Più server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f793f-134">Multiple Standard Edition servers.</span></span>

  - <span data-ttu-id="f793f-135">Office Web Apps Server, usato con le applicazioni Web di Office in Lync Server 2013 per gestire la condivisione e il rendering delle presentazioni di Microsoft PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="f793f-135">Office Web Apps Server, which is used with Office Web Applications in Lync Server 2013 to handle the sharing and rendering of Microsoft PowerPoint presentations.</span></span>

  - <span data-ttu-id="f793f-136">Edge Server o pool di Edge nella rete perimetrale, se si vuole che la distribuzione supporti i partner federati, la connettività di messaggistica istantanea pubblica, un gateway XMPP (Extensible Messaging and Presence Protocol), l'accesso degli utenti remoti, la partecipazione di un utente anonimo alle riunioni, o messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="f793f-136">Edge Server or Edge pool in your perimeter network, if you want your deployment to support federated partners, public IM connectivity, an extensible messaging and presence protocol (XMPP) gateway, remote user access, participation of anonymous users in meetings, or Exchange Unified Messaging (UM).</span></span> <span data-ttu-id="f793f-137">Non è possibile collocare qualsiasi altro ruolo del server con un server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="f793f-137">You cannot collocate any other server role with an Edge Server.</span></span> <span data-ttu-id="f793f-138">È consigliabile supportare il bilanciamento del carico DNS, se necessario, ma anche il bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="f793f-138">We recommend DNS load balancing, where appropriate, but hardware load balancing is also supported.</span></span> <span data-ttu-id="f793f-139">L'interfaccia perimetrale interna e l'interfaccia perimetrale esterna devono usare lo stesso tipo di bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="f793f-139">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="f793f-140">Non è possibile usare il bilanciamento del carico DNS in un'interfaccia perimetrale e il bilanciamento del carico hardware nell'altra.</span><span class="sxs-lookup"><span data-stu-id="f793f-140">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span> <span data-ttu-id="f793f-141">Per informazioni dettagliate sui requisiti di bilanciamento del carico e sul supporto, vedere [pianificazione per l'accesso degli utenti esterni in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) nella documentazione relativa alla pianificazione e [distribuzione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f793f-141">For details about load balancing requirements and support, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="f793f-142">Mediation Server o pool, se si vuole supportare i servizi di conferenza telefonica aziendale o le conferenze telefoniche con accesso esterno in un pool Front-end presso il sito centrale.</span><span class="sxs-lookup"><span data-stu-id="f793f-142">Mediation Server or pool, if you want to support Enterprise Voice or dial-in conferencing in a Front End pool at the central site.</span></span> <span data-ttu-id="f793f-143">A seconda di come si distribuisce il supporto VoIP aziendale, è possibile collocare il Mediation Server in un pool Front-End (impostazione predefinita) oppure distribuire un server di mediazione autonomo o un pool.</span><span class="sxs-lookup"><span data-stu-id="f793f-143">Depending on how you deploy Enterprise Voice support, you can collocate the Mediation Server in a Front End pool (the default) or deploy a stand-alone Mediation Server or pool.</span></span> <span data-ttu-id="f793f-144">È possibile usare il bilanciamento del carico del DNS, dell'hardware o dell'applicazione (se necessario) per distribuire il traffico da un peer del gateway del pool di Mediation Server, incluso un gateway PSTN, un IP-PBX o un SBC. Per informazioni dettagliate sulla pianificazione della topologia di Mediation Server appropriata, vedere [linee guida per la distribuzione di Mediation Server in Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="f793f-144">You can use DNS, hardware, or application load balancing (when appropriate) to distribute traffic from a Mediation Server pool’s gateway peer, including a PSTN gateway, IP-PBX, or SIP trunk Session Border Control (SBC).For details about planning the appropriate Mediation Server topology, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="f793f-145">Server di chat persistente, se si vuole consentire agli utenti di partecipare a conversazioni multiparte, basate su argomenti che persistono nel tempo.</span><span class="sxs-lookup"><span data-stu-id="f793f-145">Persistent Chat Server, if you want to users to be able to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="f793f-146">Per ottenere maggiore capacità e maggiore affidabilità, la topologia può includere più computer che eseguono il server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f793f-146">To provide more capacity and increased reliability, your topology can include multiple computers running Persistent Chat Server.</span></span> <span data-ttu-id="f793f-147">Non è possibile collocare il server di chat persistente con altri ruoli del server in un pool aziendale.</span><span class="sxs-lookup"><span data-stu-id="f793f-147">You cannot collocate Persistent Chat Server with other server roles in an Enterprise pool.</span></span> <span data-ttu-id="f793f-148">È tuttavia possibile collocare il server di chat persistente in un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f793f-148">However, you can collocate Persistent Chat Server on a Standard Edition server.</span></span> <span data-ttu-id="f793f-149">La chat persistente richiede un database e, se implementi la conformità della chat persistente, un database di conformità della chat persistente, ma i database possono essere collocati nel database di archiviazione, nel database di monitoraggio o nel server back-end di un'edizione aziendale Pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="f793f-149">Persistent chat requires a database and, if you implement persistent chat compliance, a persistent chat compliance database, but the databases can be collocated with the Archiving database, Monitoring database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="f793f-150">Per informazioni dettagliate sulla pianificazione della topologia del server di chat persistente appropriata, vedere [pianificazione del server di chat persistente in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="f793f-150">For details about planning the appropriate Persistent Chat Server topology, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="f793f-151">Monitoraggio, se si vuole supportare la raccolta di dati per la qualità audio/video (QoE) e la registrazione dei dettagli delle chiamate (CDR) per le conferenze VoIP aziendale e A/V nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f793f-151">Monitoring, if you want to support data collection for audio/video Quality of Experience (QoE) and call detail recording (CDR) for Enterprise Voice and A/V conferences in your deployment.</span></span> <span data-ttu-id="f793f-152">Facoltativamente, è possibile installare Microsoft System Center Operations Manager (in precedenza Microsoft Operations Manager), che usa il monitoraggio dei dati CDR e QoE per generare avvisi in tempo reale che mostrano lo stato di affidabilità delle chiamate e la qualità dei contenuti multimediali.</span><span class="sxs-lookup"><span data-stu-id="f793f-152">Optionally, you can install the Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which uses Monitoring CDR and QoE data to generate near real-time alerts that show the health of call reliability and media quality.</span></span> <span data-ttu-id="f793f-153">Il monitoraggio, quando viene distribuito, è collocato nei server front-end o in un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f793f-153">Monitoring, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="f793f-154">Il monitoraggio richiede un database, ma il database può essere collocato nel database di archiviazione, nel database di chat persistente, nel database di conformità della chat persistente o nel server back-end di un pool di front-end Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="f793f-154">Monitoring requires a database, but the database can be collocated with the Archiving database, persistent chat database, persistent chat compliance database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span>

  - <span data-ttu-id="f793f-155">Archiviazione, se si vuole archiviare le comunicazioni di messaggistica istantanea e il contenuto della riunione (per motivi di conformità) nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f793f-155">Archiving, if you want to archive IM communications and meeting content (for compliance reasons) in your deployment.</span></span> <span data-ttu-id="f793f-156">L'archiviazione, quando viene distribuita, è collocata nei server front-end o in un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f793f-156">Archiving, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="f793f-157">Lo spazio di archiviazione richiede la distribuzione di un database di archiviazione o l'integrazione con lo spazio di archiviazione di Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="f793f-157">Archiving storage requires either deployment of an Archiving database or integration with Exchange 2013 storage.</span></span> <span data-ttu-id="f793f-158">Se si usano entrambi, che è noto come *modalità mista*, lo spazio di archiviazione di Exchange 2013 viene usato per archiviare i dati di archiviazione per gli utenti residenti in Exchange 2013 e il database di archiviazione viene usato per archiviare i dati per tutti gli altri utenti della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f793f-158">If you use both, which is known as *mixed mode*, Exchange 2013 storage is used to store archive data for users who are homed on Exchange 2013, and the Archiving database is used to archive data for all other users in your deployment.</span></span> <span data-ttu-id="f793f-159">Se è necessario un database di archiviazione, il database può essere collocato nel database di monitoraggio, nel database di chat persistente, nel database di conformità della chat persistente o nel server back-end di un pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="f793f-159">If you require an Archiving database, the database can be collocated on the Monitoring database, persistent chat database, persistent chat compliance database, or on the Back End Server of a Front End pool.</span></span> <span data-ttu-id="f793f-160">Per informazioni dettagliate sulla pianificazione della topologia di archiviazione appropriata, vedere [pianificazione dell'archiviazione in Lync Server 2013](lync-server-2013-planning-for-archiving.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="f793f-160">For details about planning the appropriate Archiving topology, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="f793f-161">Pool di Director o Director, se si vuole semplificare la resilienza e il reindirizzamento delle richieste degli utenti di Lync Server 2013 al pool Home dell'utente, che può essere un pool di front-end Enterprise Edition o un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f793f-161">Director or Director pool, if you want to facilitate resiliency and redirection of Lync Server 2013 user requests to the user’s home pool, which can be either an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="f793f-162">È consigliabile distribuire un pool di Director o Director in ogni sito centrale che supporta l'accesso degli utenti esterni e in ogni sito centrale in cui vengono distribuiti uno o più pool di front-end.</span><span class="sxs-lookup"><span data-stu-id="f793f-162">We recommend that you deploy a Director or Director pool in each central site that supports external user access and in each central site in which you deploy one or more Front End pools.</span></span> <span data-ttu-id="f793f-163">Ogni pool di Director può contenere un massimo di dieci direttori.</span><span class="sxs-lookup"><span data-stu-id="f793f-163">Each Director pool can contain a maximum of ten Directors.</span></span> <span data-ttu-id="f793f-164">Un amministratore non può essere collocato in un altro ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="f793f-164">A Director cannot be collocated with any other server role.</span></span> <span data-ttu-id="f793f-165">Per informazioni dettagliate sulla pianificazione della topologia di Director appropriata, vedere [scenari per il Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="f793f-165">For details about planning the appropriate Director topology, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="f793f-166">Proxy inverso, che non è un componente 2013 di Lync Server, ma è obbligatorio se si vuole supportare la condivisione di contenuto Web per gli utenti federati o per supportare il traffico di mobilità.</span><span class="sxs-lookup"><span data-stu-id="f793f-166">Reverse proxy, which is not a Lync Server 2013 component, but is required if you want to support sharing of web content for federated users or to support Mobility traffic.</span></span> <span data-ttu-id="f793f-167">Non è possibile collocare un server proxy inverso con qualsiasi ruolo del server Lync Server 2013, ma è possibile implementare il supporto del proxy inverso per una distribuzione di Lync Server 2013 configurando il supporto di un server proxy inverso esistente nell'organizzazione usato per altri applicazioni.</span><span class="sxs-lookup"><span data-stu-id="f793f-167">You cannot collocate a reverse proxy server with any Lync Server 2013 server role, but you can implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span> <span data-ttu-id="f793f-168">Per informazioni dettagliate sui server proxy inverso, vedere [configurazione dei server proxy inversa per Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f793f-168">For details about reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f793f-169">In Lync Server 2013, i servizi di conferenza A/V, il monitoraggio e l'archiviazione vengono eseguiti nei server front-end e non sono più ruoli server distinti.</span><span class="sxs-lookup"><span data-stu-id="f793f-169">In Lync Server 2013, A/V Conferencing, Monitoring, and Archiving run on Front End Servers and are no longer separate server roles.</span></span>



</div>

<span data-ttu-id="f793f-170">Tutti i pool Front-end e i server Standard Edition distribuiti in un sito centrale condividono una delle operazioni seguenti distribuite per il sito centrale:</span><span class="sxs-lookup"><span data-stu-id="f793f-170">All Front End pools and Standard Edition servers that you deploy at a central site share any of the following that you deploy for the central site:</span></span>

  - <span data-ttu-id="f793f-171">Pool di Director o Director</span><span class="sxs-lookup"><span data-stu-id="f793f-171">Director or Director pool</span></span>

  - <span data-ttu-id="f793f-172">Mediation Server o pool autonomo</span><span class="sxs-lookup"><span data-stu-id="f793f-172">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="f793f-173">Server Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="f793f-173">Office Web Apps Server</span></span>

  - <span data-ttu-id="f793f-174">Edge Server o pool di Edge</span><span class="sxs-lookup"><span data-stu-id="f793f-174">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="f793f-175">Server o pool di chat persistente</span><span class="sxs-lookup"><span data-stu-id="f793f-175">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="f793f-176">Monitoraggio</span><span class="sxs-lookup"><span data-stu-id="f793f-176">Monitoring</span></span>

  - <span data-ttu-id="f793f-177">Archiviazione</span><span class="sxs-lookup"><span data-stu-id="f793f-177">Archiving</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f793f-178">Se si vuole supportare l'integrazione della messaggistica unificata di Exchange 2013, è possibile implementare un server Messaggistica unificata di Exchange con la distribuzione di Lync Server 2013, ma non è un componente del sito di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f793f-178">An Exchange UM Server can be implemented with your Lync Server 2013 deployment if you want to support integration of Exchange 2013 Unified Messaging, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="f793f-179">Più siti centrali possono anche condividere una delle operazioni seguenti distribuite in un unico sito centrale:</span><span class="sxs-lookup"><span data-stu-id="f793f-179">Multiple central sites can also share any of the following that you deploy in one central site:</span></span>

  - <span data-ttu-id="f793f-180">Mediation Server o pool autonomo</span><span class="sxs-lookup"><span data-stu-id="f793f-180">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="f793f-181">Edge Server o pool di Edge</span><span class="sxs-lookup"><span data-stu-id="f793f-181">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="f793f-182">Server o pool di chat persistente</span><span class="sxs-lookup"><span data-stu-id="f793f-182">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="f793f-183">Archiviazione</span><span class="sxs-lookup"><span data-stu-id="f793f-183">Archiving</span></span>

  - <span data-ttu-id="f793f-184">Monitoraggio</span><span class="sxs-lookup"><span data-stu-id="f793f-184">Monitoring</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f793f-185">Un server di messaggistica unificata di Exchange può essere implementato con la distribuzione di Lync Server 2013 e condiviso da più siti centrali, ma non è un componente del sito di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f793f-185">An Exchange UM Server can be implemented with your Lync Server 2013 deployment and shared by multiple central sites, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="f793f-186">Per informazioni dettagliate sui ruoli e le funzionalità del server Lync Server 2013, vedere ruoli del server [in Lync server 2013](lync-server-2013-server-roles.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="f793f-186">For details about Lync Server 2013 server roles and functionality, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md) in the Planning documentation.</span></span>

<span data-ttu-id="f793f-187">Per un riepilogo del supporto della collocazione dei server di Lync Server 2013, vedere [collocazione del server supportata in Lync server 2013](lync-server-2013-supported-server-collocation.md).</span><span class="sxs-lookup"><span data-stu-id="f793f-187">For a summary of Lync Server 2013 server collocation support, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<span data-ttu-id="f793f-188">Oltre ai ruoli e alle funzionalità del server descritti in precedenza in questa sezione, Lync Server 2013 include componenti e opzioni aggiuntivi, che possono includere alcuni o tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f793f-188">In addition to the server roles and functionality covered previously in this section, Lync Server 2013 has additional components and options, which can include some or all of the following:</span></span>

  - <span data-ttu-id="f793f-189">Firewall</span><span class="sxs-lookup"><span data-stu-id="f793f-189">Firewalls</span></span>

  - <span data-ttu-id="f793f-190">Gateway PSTN (se si distribuisce VoIP aziendale)</span><span class="sxs-lookup"><span data-stu-id="f793f-190">PSTN gateways (if deploying Enterprise Voice)</span></span>

  - <span data-ttu-id="f793f-191">Server Messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="f793f-191">Exchange UM Server</span></span>

  - <span data-ttu-id="f793f-192">Bilanciamento del carico DNS</span><span class="sxs-lookup"><span data-stu-id="f793f-192">DNS load balancing</span></span>

  - <span data-ttu-id="f793f-193">Dispositivi di bilanciamento del carico hardware</span><span class="sxs-lookup"><span data-stu-id="f793f-193">Hardware load balancers</span></span>

  - <span data-ttu-id="f793f-194">Database di SQL Server</span><span class="sxs-lookup"><span data-stu-id="f793f-194">SQL Server databases</span></span>

  - <span data-ttu-id="f793f-195">Condivisioni file</span><span class="sxs-lookup"><span data-stu-id="f793f-195">File shares</span></span>

<span data-ttu-id="f793f-196">Per informazioni dettagliate su tutte le caratteristiche, i componenti e le opzioni di Lync Server 2013, vedere la documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="f793f-196">For details about all of the Lync Server 2013 features, components, and options, see the Planning documentation.</span></span>

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a><span data-ttu-id="f793f-197">Topologie e componenti del sito di succursale (locale)</span><span class="sxs-lookup"><span data-stu-id="f793f-197">Branch Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="f793f-198">Un sito di succursale è associato a un sito centrale e ogni appliance Survivable Branch in un sito di succursale è associato a un pool di front end Enterprise Edition o a un server Standard Edition nel sito centrale associato.</span><span class="sxs-lookup"><span data-stu-id="f793f-198">A branch site is associated with a central site, and each Survivable Branch Appliance in a branch site is associated with an Enterprise Edition Front End pool or a Standard Edition server in the associated central site.</span></span> <span data-ttu-id="f793f-199">I siti di succursale dipendono dal sito centrale per la maggior parte delle loro funzionalità, quindi i componenti in un sito di succursale contengono solo i seguenti:</span><span class="sxs-lookup"><span data-stu-id="f793f-199">Branch sites depend on the central site for most of their functionality, so components at a branch site contain only the following:</span></span>

  - <span data-ttu-id="f793f-200">Un Survivable Branch Appliance, che combina un gateway PSTN (Public Switched Telephone Network) con alcune funzionalità di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f793f-200">A Survivable Branch Appliance, which combines a public switched telephone network (PSTN) gateway with some Lync Server functionality.</span></span> <span data-ttu-id="f793f-201">Un Mediation Server può essere collocato con l'istanza del registrar in Survivable Branch Appliance ed è possibile distribuire un server di mediazione autonomo o un pool di server di mediazione.</span><span class="sxs-lookup"><span data-stu-id="f793f-201">A Mediation Server can be collocated with the instance of the Registrar on the Survivable Branch Appliance, and you can deploy a stand-alone Mediation Server or pool of Mediation Servers.</span></span>

  - <span data-ttu-id="f793f-202">Un Survivable Branch Server, un server che utilizza Windows Server che include il software di registrazione e mediazione server di Lync Server 2013 installato.</span><span class="sxs-lookup"><span data-stu-id="f793f-202">A Survivable Branch Server, which is a server running Windows Server that has Lync Server 2013 Registrar and Mediation Server software installed.</span></span>

  - <span data-ttu-id="f793f-203">Un gateway PSTN autonomo (non incluso in Survivable Branch Appliance) e un Mediation Server autonomo.</span><span class="sxs-lookup"><span data-stu-id="f793f-203">A stand-alone PSTN gateway (not part of the Survivable Branch Appliance) and a stand-alone Mediation Server.</span></span>

<span data-ttu-id="f793f-204">I requisiti per i Survivable Branch Server corrispondono ai requisiti per qualsiasi ruolo del server Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f793f-204">The requirements for Survivable Branch Servers are the same as the requirements for any Lync Server 2013 server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

