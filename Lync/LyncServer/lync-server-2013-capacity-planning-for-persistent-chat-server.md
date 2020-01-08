---
title: 'Lync Server 2013: pianificazione della capacità per il server di chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Persistent Chat Server
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615006(v=OCS.15)
ms:contentKeyID: 48184580
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7af60947a1132d26d5e8ba015d54cdbea80b8b54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="24a00-102">Pianificazione della capacità per il server di chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24a00-102">Capacity planning for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24a00-103">_**Argomento Ultima modifica:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="24a00-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="24a00-104">Il server di chat persistente può eseguire una chat in tempo reale multiutente che può essere mantenuta per il recupero e la ricerca futuri.</span><span class="sxs-lookup"><span data-stu-id="24a00-104">Persistent Chat Server can perform multi-user real-time chat that can persist for future retrieval and search.</span></span> <span data-ttu-id="24a00-105">A differenza della messaggistica istantanea di gruppo che viene salvata nella cassetta postale di un utente se è configurata la cronologia delle conversazioni, una sessione del server di chat persistente rimane aperta più a lungo e il contenuto viene salvato in un server, insieme ai messaggi, ai file, agli URL e ad altri dati che fanno parte di un conversazione in corso.</span><span class="sxs-lookup"><span data-stu-id="24a00-105">Unlike group instant messaging (IM) that is saved in a user’s mailbox if conversation history is configured, a Persistent Chat Server session stays open longer, and the content is saved on a server, along with the messages, files, URLs, and other data that are part of an ongoing conversation.</span></span>

<span data-ttu-id="24a00-106">La pianificazione della capacità è una parte importante della preparazione alla distribuzione del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="24a00-106">Capacity planning is an important part of preparing to deploy Persistent Chat Server.</span></span> <span data-ttu-id="24a00-107">Questo argomento fornisce informazioni dettagliate sulle topologie del server di chat persistente supportate e sulle tabelle di pianificazione della capacità che è possibile usare per determinare la configurazione migliore per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="24a00-107">This topic provides details about supported Persistent Chat Server topologies and capacity planning tables that you can use to determine the best configuration for your deployment.</span></span> <span data-ttu-id="24a00-108">Descrive anche come gestire al meglio le distribuzioni del server della chat persistente che richiedono maggiore capacità nelle ore di punta.</span><span class="sxs-lookup"><span data-stu-id="24a00-108">It also describes how to best manage Persistent Chat Server deployments that require greater capacity at peak times.</span></span>

<span data-ttu-id="24a00-109">Per scaricare il server di chat persistente, vedere "Microsoft Lync Server 13 Persistent [http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539)Chat Server" at.</span><span class="sxs-lookup"><span data-stu-id="24a00-109">To download Persistent Chat Server, see "Microsoft Lync Server 13 Persistent Chat Server" at [http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539).</span></span>

<span data-ttu-id="24a00-110">Per informazioni dettagliate sull'installazione del server di chat persistente, vedere [installazione del server di chat persistente in Lync server 2013](lync-server-2013-installing-persistent-chat-server.md) e [configurazione del server di chat persistente in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="24a00-110">For details about installing Persistent Chat Server, see [Installing Persistent Chat Server in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) and [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="24a00-111">Gli strumenti di supporto, ad esempio lo strumento di pianificazione di Lync Server, possono aiutare ulteriormente la pianificazione della capacità.</span><span class="sxs-lookup"><span data-stu-id="24a00-111">Support tools, such as Lync Server Planning Tool, can further assist you with capacity planning.</span></span> <span data-ttu-id="24a00-112">Per informazioni dettagliate sullo strumento di pianificazione, vedere [inizio del processo di pianificazione per Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="24a00-112">For details about the Planning Tool, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<div>

## <a name="persistent-chat-server-supported-topologies"></a><span data-ttu-id="24a00-113">Topologie supportate dal server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="24a00-113">Persistent Chat Server Supported Topologies</span></span>

<span data-ttu-id="24a00-114">È possibile distribuire il server di chat persistente in pool a server singolo o a più server e con una topologia a pool singolo o multiplo.</span><span class="sxs-lookup"><span data-stu-id="24a00-114">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span>

<span data-ttu-id="24a00-115">Ora è anche supportato il server di chat persistente sul server Standard Edition per le nuove distribuzioni di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="24a00-115">We now also support Persistent Chat Server on Standard Edition server for new Lync Server 2013 deployments.</span></span> <span data-ttu-id="24a00-116">Tuttavia, le prestazioni e la scala saranno interessate e, poiché non esiste un'opzione di disponibilità elevata per questa nuova distribuzione, ci aspettiamo che tu usi questo aspetto principalmente ai fini della prova del concetto, della valutazione e così via.</span><span class="sxs-lookup"><span data-stu-id="24a00-116">However, performance and scale will be affected, and because there is no high availability option for this new deployment, we expect you to use this primarily for the purposes of proof of concept, evaluation, and so on.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="24a00-117">Per informazioni dettagliate su entrambe le topologie, vedere <A href="lync-server-2013-planning-for-persistent-chat-server.md">pianificazione del server di chat persistente in Lync server 2013</A> in questa documentazione e <A href="lync-server-2013-deploying-persistent-chat-server.md">distribuzione del server di chat persistente in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="24a00-117">For additional details about both topologies, see <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for Persistent Chat Server in Lync Server 2013</A> in this documentation set and <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="24a00-118">Topologia a server singolo</span><span class="sxs-lookup"><span data-stu-id="24a00-118">Single-Server Topology</span></span>

<span data-ttu-id="24a00-119">La configurazione minima e la distribuzione più semplice per il server di chat persistente è una singola topologia del server front end del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="24a00-119">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="24a00-120">Questa distribuzione richiede un singolo server che esegue il server di chat persistente (che facoltativamente esegue il servizio di conformità, se è abilitata la conformità), un server che ospita sia il database di SQL Server che se è necessaria la conformità, il database di SQL Server per archiviare il dati sulla conformità.</span><span class="sxs-lookup"><span data-stu-id="24a00-120">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="24a00-121">Non è possibile aggiungere altri server a un pool di server di chat persistente avviato come distribuzione a server singolo in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="24a00-121">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="24a00-122">È consigliabile usare la topologia di pool a più server, anche se si usa un singolo server.</span><span class="sxs-lookup"><span data-stu-id="24a00-122">We recommend using the multiple-server pool topology, even if you’re using a single server.</span></span> <span data-ttu-id="24a00-123">In questo modo potrai aggiungere più server in un secondo momento, se necessario.</span><span class="sxs-lookup"><span data-stu-id="24a00-123">This is so that you’ll be able to add more servers later, if it's necessary.</span></span> 


</div>

<span data-ttu-id="24a00-124">La figura seguente mostra tutti i componenti obbligatori e facoltativi di una topologia per un singolo server front-end del server di chat persistente con conformità.</span><span class="sxs-lookup"><span data-stu-id="24a00-124">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="24a00-125">**Singolo server di chat persistente**</span><span class="sxs-lookup"><span data-stu-id="24a00-125">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="24a00-126">![Topologia a server singolo con](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "topologia del servizio conformità Single Server con servizio conformità")</span><span class="sxs-lookup"><span data-stu-id="24a00-126">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="24a00-127">Topologia a più server</span><span class="sxs-lookup"><span data-stu-id="24a00-127">Multiple-Server Topology</span></span>

<span data-ttu-id="24a00-128">Per avere maggiore capacità e affidabilità, è possibile distribuire una topologia a più server, come descritto in [pianificazione per il server di chat persistente in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="24a00-128">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="24a00-129">La topologia a più server può includere fino a quattro computer attivi che eseguono il server di chat persistente (le configurazioni ad alta disponibilità e ripristino di emergenza consentiranno fino a otto, ma solo quattro possono essere attive e le rimanenti quattro in standby).</span><span class="sxs-lookup"><span data-stu-id="24a00-129">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="24a00-130">Ogni server può supportare tutti gli utenti simultanei di 20.000, per un totale di 80.000 utenti simultanei connessi a un pool di server di chat persistente con 4 server.</span><span class="sxs-lookup"><span data-stu-id="24a00-130">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="24a00-131">Una topologia a più server è uguale alla topologia a server singolo, ad eccezione del fatto che più server ospitano il server di chat persistente e possono essere ridimensionati in modo più elevato.</span><span class="sxs-lookup"><span data-stu-id="24a00-131">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="24a00-132">Più computer che eseguono il server di chat persistente devono risiedere nello stesso dominio di servizi di dominio Active Directory di Lync Server e nel servizio conformità.</span><span class="sxs-lookup"><span data-stu-id="24a00-132">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="24a00-133">La figura seguente mostra tutti i componenti di una topologia a più server con più computer che eseguono il server di chat persistente, il servizio di conformità facoltativo e un database di conformità separato.</span><span class="sxs-lookup"><span data-stu-id="24a00-133">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="24a00-134">**Più server di chat persistenti**</span><span class="sxs-lookup"><span data-stu-id="24a00-134">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="24a00-135">Topologia multiple server(images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "multiple") ![topologia]server</span><span class="sxs-lookup"><span data-stu-id="24a00-135">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="24a00-136">In una distribuzione di server di chat persistente con quattro server, in cui gli utenti di 80.000 possono essere connessi simultaneamente e usando la chat persistente, il carico viene distribuito uniformemente in 20.000 utenti per server.</span><span class="sxs-lookup"><span data-stu-id="24a00-136">In a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to and using Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="24a00-137">Se un server non è disponibile, gli utenti connessi al server perderanno l'accesso al server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="24a00-137">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="24a00-138">Gli utenti disconnessi verranno trasferiti automaticamente ai server rimanenti finché non viene ripristinato il server non disponibile.</span><span class="sxs-lookup"><span data-stu-id="24a00-138">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> <span data-ttu-id="24a00-139">A seconda della quantità di traffico di chat persistente nella rete, questo trasferimento può richiedere qualche minuto o più.</span><span class="sxs-lookup"><span data-stu-id="24a00-139">Depending on the amount of Persistent Chat traffic on the network, this transfer can take a few minutes or longer.</span></span> <span data-ttu-id="24a00-140">Poiché ognuno dei server rimanenti può ospitare fino a 30.000 utenti, è consigliabile ripristinare il server non disponibile il più rapidamente possibile per evitare problemi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="24a00-140">Because each of the remaining servers might be hosting as many as 30,000 users, we recommend that you restore the unavailable server as quickly as possible to avoid performance issues.</span></span> <span data-ttu-id="24a00-141">In caso contrario, è possibile rendere disponibile un altro server di chat persistente usando il generatore di topologia o il cmdlet di Windows PowerShell, **Set-CsPersistentChatActiveServer**.</span><span class="sxs-lookup"><span data-stu-id="24a00-141">Otherwise, you can make another Persistent Chat Server available by using the Topology Builder or the Windows PowerShell cmdlet, **set-CsPersistentChatActiveServer**.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a><span data-ttu-id="24a00-142">Pianificazione della capacità del server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="24a00-142">Persistent Chat Server Capacity Planning</span></span>

<span data-ttu-id="24a00-143">Le tabelle seguenti possono essere utili per la pianificazione della capacità per il server della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="24a00-143">The following tables can help you with capacity planning for Persistent Chat Server.</span></span> <span data-ttu-id="24a00-144">Modellano la modalità di modifica delle varie impostazioni del server di chat persistente sulle capacità.</span><span class="sxs-lookup"><span data-stu-id="24a00-144">They model how changing various Persistent Chat Server settings affect capacity capabilities.</span></span>

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a><span data-ttu-id="24a00-145">Pianificazione della capacità massima per il server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="24a00-145">Planning Your Maximum Capacity for Persistent Chat Server</span></span>

<span data-ttu-id="24a00-146">Usare la tabella di esempio seguente per determinare il numero di utenti che sarà in grado di supportare.</span><span class="sxs-lookup"><span data-stu-id="24a00-146">Use the following sample table to determine the number of users you will be able to support.</span></span>

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a><span data-ttu-id="24a00-147">Esempio di capacità massima del pool di server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="24a00-147">Persistent Chat Server pool Maximum Capacity Sample</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24a00-148">Istanze del servizio chat persistenti attive</span><span class="sxs-lookup"><span data-stu-id="24a00-148">Active Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="24a00-149"><em>4</em></span><span class="sxs-lookup"><span data-stu-id="24a00-149"><em>4</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-150">Istanze del servizio chat persistente</span><span class="sxs-lookup"><span data-stu-id="24a00-150">Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="24a00-151"><em>8 (4 deve essere inattivo; solo un massimo di 4 può essere attivo)</em></span><span class="sxs-lookup"><span data-stu-id="24a00-151"><em>8 (4 must be inactive; only a maximum of 4 can be active)</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-152">Utenti attivi connessi</span><span class="sxs-lookup"><span data-stu-id="24a00-152">Active users connected</span></span></p></td>
<td><p><span data-ttu-id="24a00-153"><em>80.000</em></span><span class="sxs-lookup"><span data-stu-id="24a00-153"><em>80,000</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-154">Totale utenti con provisioning</span><span class="sxs-lookup"><span data-stu-id="24a00-154">Total provisioned users</span></span></p></td>
<td><p><span data-ttu-id="24a00-155">150.000</span><span class="sxs-lookup"><span data-stu-id="24a00-155">150,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-156">Numero di endpoint</span><span class="sxs-lookup"><span data-stu-id="24a00-156">Number of endpoints</span></span></p></td>
<td><p><span data-ttu-id="24a00-157">120.000</span><span class="sxs-lookup"><span data-stu-id="24a00-157">120,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="24a00-158">Nell'esempio precedente il piano consiste nel supportare il numero massimo di utenti che il server di chat persistente consente: quattro server/istanze del servizio di chat persistente (può avere quattro server più passivi che gestiscono il server di chat persistente per l'elevata disponibilità e il ripristino di emergenza) e gli utenti di 20.000 per server, per un totale di 80.000 utenti attivi.</span><span class="sxs-lookup"><span data-stu-id="24a00-158">In the preceding sample, the plan is to support the maximum number of users that Persistent Chat Server allows: four servers/instances of the Persistent Chat service (can have four more passive servers running Persistent Chat Server for high availability and disaster recovery) and 20,000 users per server, for a total of 80,000 active users.</span></span>

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a><span data-ttu-id="24a00-159">Pianificazione della capacità per la gestione dell'accesso alla chat room persistente</span><span class="sxs-lookup"><span data-stu-id="24a00-159">Capacity Planning for Managing Persistent Chat Room Access</span></span>

<span data-ttu-id="24a00-160">La tabella di esempio seguente può essere utile per pianificare la gestione dell'accesso delle chat room permanenti in un pool di server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="24a00-160">The following sample table can help you plan for managing Persistent Chat room access in a Persistent Chat Server pool.</span></span>

### <a name="managing-chat-room-access-sample"></a><span data-ttu-id="24a00-161">Esempio di accesso alla chat room</span><span class="sxs-lookup"><span data-stu-id="24a00-161">Managing Chat Room Access Sample</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="24a00-162">Piccole chat room</span><span class="sxs-lookup"><span data-stu-id="24a00-162">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="24a00-163">Chat room di medie dimensioni</span><span class="sxs-lookup"><span data-stu-id="24a00-163">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="24a00-164">Chat room di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="24a00-164">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="24a00-165">Totale</span><span class="sxs-lookup"><span data-stu-id="24a00-165">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24a00-166">Dimensioni delle chat room (numero di utenti connessi)</span><span class="sxs-lookup"><span data-stu-id="24a00-166">Size of chat rooms (number of users connected)</span></span></p></td>
<td><p><span data-ttu-id="24a00-167">30 per camera</span><span class="sxs-lookup"><span data-stu-id="24a00-167">30 per room</span></span></p></td>
<td><p><span data-ttu-id="24a00-168">150 per camera</span><span class="sxs-lookup"><span data-stu-id="24a00-168">150 per room</span></span></p></td>
<td><p><span data-ttu-id="24a00-169">16.000 per camera</span><span class="sxs-lookup"><span data-stu-id="24a00-169">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-170">Chat room</span><span class="sxs-lookup"><span data-stu-id="24a00-170">Chat rooms</span></span></p></td>
<td><p><span data-ttu-id="24a00-171">32.000</span><span class="sxs-lookup"><span data-stu-id="24a00-171">32,000</span></span></p></td>
<td><p><span data-ttu-id="24a00-172">1.067</span><span class="sxs-lookup"><span data-stu-id="24a00-172">1,067</span></span></p></td>
<td><p><span data-ttu-id="24a00-173">10</span><span class="sxs-lookup"><span data-stu-id="24a00-173">10</span></span></p></td>
<td><p><span data-ttu-id="24a00-174">33.077</span><span class="sxs-lookup"><span data-stu-id="24a00-174">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-175">% delle sale che sono Auditorium</span><span class="sxs-lookup"><span data-stu-id="24a00-175">% of rooms that are auditorium</span></span></p></td>
<td><p><span data-ttu-id="24a00-176">1</span><span class="sxs-lookup"><span data-stu-id="24a00-176">1%</span></span></p></td>
<td><p><span data-ttu-id="24a00-177">1</span><span class="sxs-lookup"><span data-stu-id="24a00-177">1%</span></span></p></td>
<td><p><span data-ttu-id="24a00-178">50%</span><span class="sxs-lookup"><span data-stu-id="24a00-178">50%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-179">% delle camere aperte</span><span class="sxs-lookup"><span data-stu-id="24a00-179">% of rooms that are open</span></span></p></td>
<td><p><span data-ttu-id="24a00-180">3</span><span class="sxs-lookup"><span data-stu-id="24a00-180">3%</span></span></p></td>
<td><p><span data-ttu-id="24a00-181">3</span><span class="sxs-lookup"><span data-stu-id="24a00-181">3%</span></span></p></td>
<td><p><span data-ttu-id="24a00-182">50%</span><span class="sxs-lookup"><span data-stu-id="24a00-182">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-183">Aprire le sale (nessuna appartenenza esplicita)</span><span class="sxs-lookup"><span data-stu-id="24a00-183">Open rooms (no explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="24a00-184">960</span><span class="sxs-lookup"><span data-stu-id="24a00-184">960</span></span></p></td>
<td><p><span data-ttu-id="24a00-185">32</span><span class="sxs-lookup"><span data-stu-id="24a00-185">32</span></span></p></td>
<td><p><span data-ttu-id="24a00-186">5</span><span class="sxs-lookup"><span data-stu-id="24a00-186">5</span></span></p></td>
<td><p><span data-ttu-id="24a00-187">997</span><span class="sxs-lookup"><span data-stu-id="24a00-187">997</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-188">Camere non aperte (camere normali con appartenenza esplicita)</span><span class="sxs-lookup"><span data-stu-id="24a00-188">Non-open rooms (regular rooms with explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="24a00-189">31.040</span><span class="sxs-lookup"><span data-stu-id="24a00-189">31,040</span></span></p></td>
<td><p><span data-ttu-id="24a00-190">1,035</span><span class="sxs-lookup"><span data-stu-id="24a00-190">1.035</span></span></p></td>
<td><p><span data-ttu-id="24a00-191">5</span><span class="sxs-lookup"><span data-stu-id="24a00-191">5</span></span></p></td>
<td><p><span data-ttu-id="24a00-192">32.080</span><span class="sxs-lookup"><span data-stu-id="24a00-192">32,080</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-193">Sale Auditorium (voce relatori aggiunti)</span><span class="sxs-lookup"><span data-stu-id="24a00-193">Auditorium rooms (additional presenters entry)</span></span></p></td>
<td><p><span data-ttu-id="24a00-194">0</span><span class="sxs-lookup"><span data-stu-id="24a00-194">0</span></span></p></td>
<td><p><span data-ttu-id="24a00-195">32</span><span class="sxs-lookup"><span data-stu-id="24a00-195">32</span></span></p></td>
<td><p><span data-ttu-id="24a00-196">5</span><span class="sxs-lookup"><span data-stu-id="24a00-196">5</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-197">Sale gestite da un abbonamento diretto</span><span class="sxs-lookup"><span data-stu-id="24a00-197">Rooms managed by direct membership</span></span></p></td>
<td><p><span data-ttu-id="24a00-198">50%</span><span class="sxs-lookup"><span data-stu-id="24a00-198">50%</span></span></p></td>
<td><p><span data-ttu-id="24a00-199">10</span><span class="sxs-lookup"><span data-stu-id="24a00-199">10%</span></span></p></td>
<td><p><span data-ttu-id="24a00-200">0</span><span class="sxs-lookup"><span data-stu-id="24a00-200">0%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-201">Sale gestite da gruppi di utenti</span><span class="sxs-lookup"><span data-stu-id="24a00-201">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="24a00-202">50%</span><span class="sxs-lookup"><span data-stu-id="24a00-202">50%</span></span></p></td>
<td><p><span data-ttu-id="24a00-203">90%</span><span class="sxs-lookup"><span data-stu-id="24a00-203">90%</span></span></p></td>
<td><p><span data-ttu-id="24a00-204">100%</span><span class="sxs-lookup"><span data-stu-id="24a00-204">100%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-205">Gruppi di utenti nell'elenco di appartenenza di ogni chat room per le camere aperte (non specificato in modo esplicito)</span><span class="sxs-lookup"><span data-stu-id="24a00-205">User groups in each chat room's membership list for open rooms (not specified explicitly)</span></span></p></td>
<td><p><span data-ttu-id="24a00-206">0</span><span class="sxs-lookup"><span data-stu-id="24a00-206">0</span></span></p></td>
<td><p><span data-ttu-id="24a00-207">0</span><span class="sxs-lookup"><span data-stu-id="24a00-207">0</span></span></p></td>
<td><p><span data-ttu-id="24a00-208">0</span><span class="sxs-lookup"><span data-stu-id="24a00-208">0</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-209">Utenti nell'elenco di appartenenza di ogni chat room per le camere non aperte</span><span class="sxs-lookup"><span data-stu-id="24a00-209">Users in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="24a00-210">30</span><span class="sxs-lookup"><span data-stu-id="24a00-210">30</span></span></p></td>
<td><p><span data-ttu-id="24a00-211">150</span><span class="sxs-lookup"><span data-stu-id="24a00-211">150</span></span></p></td>
<td><p><span data-ttu-id="24a00-212">16.000</span><span class="sxs-lookup"><span data-stu-id="24a00-212">16,000</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-213">Gruppi di utenti nell'elenco di appartenenza di ogni chat room per le camere non aperte</span><span class="sxs-lookup"><span data-stu-id="24a00-213">User groups in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="24a00-214">3</span><span class="sxs-lookup"><span data-stu-id="24a00-214">3</span></span></p></td>
<td><p><span data-ttu-id="24a00-215">5</span><span class="sxs-lookup"><span data-stu-id="24a00-215">5</span></span></p></td>
<td><p><span data-ttu-id="24a00-216">10</span><span class="sxs-lookup"><span data-stu-id="24a00-216">10</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-217">Utenti e gruppi utenti nell'elenco Manager di ogni chat room (per le sale aperte e non aperte)</span><span class="sxs-lookup"><span data-stu-id="24a00-217">Users and user groups in each chat room's manager list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="24a00-218">6</span><span class="sxs-lookup"><span data-stu-id="24a00-218">6</span></span></p></td>
<td><p><span data-ttu-id="24a00-219">6</span><span class="sxs-lookup"><span data-stu-id="24a00-219">6</span></span></p></td>
<td><p><span data-ttu-id="24a00-220">6</span><span class="sxs-lookup"><span data-stu-id="24a00-220">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-221">Utenti e gruppi utenti nell'elenco relatori di ogni chat room dell'Auditorium (per le sale aperte e non aperte)</span><span class="sxs-lookup"><span data-stu-id="24a00-221">Users and user groups in each auditorium chat room's presenters list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="24a00-222">6</span><span class="sxs-lookup"><span data-stu-id="24a00-222">6</span></span></p></td>
<td><p><span data-ttu-id="24a00-223">6</span><span class="sxs-lookup"><span data-stu-id="24a00-223">6</span></span></p></td>
<td><p><span data-ttu-id="24a00-224">6</span><span class="sxs-lookup"><span data-stu-id="24a00-224">6</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-225">Entità di appartenenza basate sull'utente in tutte le camere non aperte</span><span class="sxs-lookup"><span data-stu-id="24a00-225">User-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="24a00-226">465.600</span><span class="sxs-lookup"><span data-stu-id="24a00-226">465,600</span></span></p></td>
<td><p><span data-ttu-id="24a00-227">15.520</span><span class="sxs-lookup"><span data-stu-id="24a00-227">15,520</span></span></p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-228">Entità di appartenenza basate su gruppi di utenti in tutte le camere non aperte</span><span class="sxs-lookup"><span data-stu-id="24a00-228">User-group-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="24a00-229">46.560</span><span class="sxs-lookup"><span data-stu-id="24a00-229">46,560</span></span></p></td>
<td><p><span data-ttu-id="24a00-230">4656</span><span class="sxs-lookup"><span data-stu-id="24a00-230">4656</span></span></p></td>
<td><p><span data-ttu-id="24a00-231">50</span><span class="sxs-lookup"><span data-stu-id="24a00-231">50</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-232">Utenti e gruppi utente basati su entità in tutte le chat room di Auditorium</span><span class="sxs-lookup"><span data-stu-id="24a00-232">Users and user groups based entities across all auditorium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="24a00-233">0</span><span class="sxs-lookup"><span data-stu-id="24a00-233">0</span></span></p></td>
<td><p><span data-ttu-id="24a00-234">192</span><span class="sxs-lookup"><span data-stu-id="24a00-234">192</span></span></p></td>
<td><p><span data-ttu-id="24a00-235">50</span><span class="sxs-lookup"><span data-stu-id="24a00-235">50</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-236">Gli utenti e le entità di gestione basate su gruppi utente in tutti gli elenchi di Manager di chat room</span><span class="sxs-lookup"><span data-stu-id="24a00-236">Users and user groups based manager entities across all chat rooms manager lists</span></span></p></td>
<td><p><span data-ttu-id="24a00-237">192.000</span><span class="sxs-lookup"><span data-stu-id="24a00-237">192,000</span></span></p></td>
<td><p><span data-ttu-id="24a00-238">6.400</span><span class="sxs-lookup"><span data-stu-id="24a00-238">6,400</span></span></p></td>
<td><p><span data-ttu-id="24a00-239">60</span><span class="sxs-lookup"><span data-stu-id="24a00-239">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-240">Utenti attivi per chat room</span><span class="sxs-lookup"><span data-stu-id="24a00-240">Active users per chat room</span></span></p></td>
<td><p><span data-ttu-id="24a00-241"><em>30</em></span><span class="sxs-lookup"><span data-stu-id="24a00-241"><em>30</em></span></span></p></td>
<td><p><span data-ttu-id="24a00-242"><em>150</em></span><span class="sxs-lookup"><span data-stu-id="24a00-242"><em>150</em></span></span></p></td>
<td><p><span data-ttu-id="24a00-243"><em>16.000</em></span><span class="sxs-lookup"><span data-stu-id="24a00-243"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-244">Chat room per utente</span><span class="sxs-lookup"><span data-stu-id="24a00-244">Chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="24a00-245"><em>12</em></span><span class="sxs-lookup"><span data-stu-id="24a00-245"><em>12</em></span></span></p></td>
<td><p><span data-ttu-id="24a00-246"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="24a00-246"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="24a00-247"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="24a00-247"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="24a00-248"><em>16</em></span><span class="sxs-lookup"><span data-stu-id="24a00-248"><em>16</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-249">Gruppi di utenti nell'elenco di appartenenza di ogni chat room</span><span class="sxs-lookup"><span data-stu-id="24a00-249">User groups in each chat room’s membership list</span></span></p></td>
<td><p><span data-ttu-id="24a00-250"><em>10</em></span><span class="sxs-lookup"><span data-stu-id="24a00-250"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="24a00-251"><em>10</em></span><span class="sxs-lookup"><span data-stu-id="24a00-251"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="24a00-252"><em>15</em></span><span class="sxs-lookup"><span data-stu-id="24a00-252"><em>15</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-253">Sale gestite da gruppi di utenti</span><span class="sxs-lookup"><span data-stu-id="24a00-253">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="24a00-254"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="24a00-254"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="24a00-255"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="24a00-255"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="24a00-256"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="24a00-256"><em>50%</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-257">Entità di appartenenza basate su gruppi di utenti in tutte le chat room</span><span class="sxs-lookup"><span data-stu-id="24a00-257">User-group-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="24a00-258">155.200</span><span class="sxs-lookup"><span data-stu-id="24a00-258">155,200</span></span></p></td>
<td><p><span data-ttu-id="24a00-259">5173</span><span class="sxs-lookup"><span data-stu-id="24a00-259">5173</span></span></p></td>
<td><p><span data-ttu-id="24a00-260">68</span><span class="sxs-lookup"><span data-stu-id="24a00-260">68</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-261">Entità di appartenenza basate sull'utente in tutte le chat room</span><span class="sxs-lookup"><span data-stu-id="24a00-261">User-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="24a00-262">465.600</span><span class="sxs-lookup"><span data-stu-id="24a00-262">465,600</span></span></p></td>
<td><p><span data-ttu-id="24a00-263">77.600</span><span class="sxs-lookup"><span data-stu-id="24a00-263">77,600</span></span></p></td>
<td><p><span data-ttu-id="24a00-264">72.000</span><span class="sxs-lookup"><span data-stu-id="24a00-264">72,000</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-265">Utenti e gruppi utenti negli elenchi Manager, relatore e ambito di ogni chat room</span><span class="sxs-lookup"><span data-stu-id="24a00-265">Users and user groups in each chat room's manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="24a00-266">6</span><span class="sxs-lookup"><span data-stu-id="24a00-266">6</span></span></p></td>
<td><p><span data-ttu-id="24a00-267">6</span><span class="sxs-lookup"><span data-stu-id="24a00-267">6</span></span></p></td>
<td><p><span data-ttu-id="24a00-268">6</span><span class="sxs-lookup"><span data-stu-id="24a00-268">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-269">Utenti e gruppi utenti in tutte le chat room Manager, relatore e elenchi di ambiti</span><span class="sxs-lookup"><span data-stu-id="24a00-269">Users and user groups across all chat rooms' manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="24a00-270">192.000</span><span class="sxs-lookup"><span data-stu-id="24a00-270">192,000</span></span></p></td>
<td><p><span data-ttu-id="24a00-271">6400</span><span class="sxs-lookup"><span data-stu-id="24a00-271">6400</span></span></p></td>
<td><p><span data-ttu-id="24a00-272">60</span><span class="sxs-lookup"><span data-stu-id="24a00-272">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-273">Voci di controllo di Access</span><span class="sxs-lookup"><span data-stu-id="24a00-273">Access control entries</span></span></p></td>
<td><p><span data-ttu-id="24a00-274">704.160</span><span class="sxs-lookup"><span data-stu-id="24a00-274">704,160</span></span></p></td>
<td><p><span data-ttu-id="24a00-275">26.768</span><span class="sxs-lookup"><span data-stu-id="24a00-275">26,768</span></span></p></td>
<td><p><span data-ttu-id="24a00-276">160</span><span class="sxs-lookup"><span data-stu-id="24a00-276">160</span></span></p></td>
<td><p><span data-ttu-id="24a00-277">731.088</span><span class="sxs-lookup"><span data-stu-id="24a00-277">731,088</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-278">Voci di controllo di accesso massimo</span><span class="sxs-lookup"><span data-stu-id="24a00-278">Maximum access control entries</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="24a00-279">2 milioni</span><span class="sxs-lookup"><span data-stu-id="24a00-279">2,000,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="24a00-280">Nell'esempio precedente, quando si distribuiscono i server di chat persistenti in base alle linee guida consigliate, è possibile gestire fino a 80.000 utenti attivi in un pool di quattro server con conformità abilitata.</span><span class="sxs-lookup"><span data-stu-id="24a00-280">In the preceding sample, when you deploy the Persistent Chat Servers according to the recommended guidelines, they can handle up to 80,000 active users across a four-server pool with compliance enabled.</span></span>

<span data-ttu-id="24a00-281">Questo esempio mostra le chat room categorizzate come piccole (30 utenti attivi in qualsiasi momento), medie (utenti attivi di 150) e grandi (16.000 utenti attivi).</span><span class="sxs-lookup"><span data-stu-id="24a00-281">This sample shows chat rooms categorized as small (30 active users at any given time), medium (150 active users), and large (16,000 active users).</span></span> <span data-ttu-id="24a00-282">Il numero di chat room di una determinata dimensione viene calcolato in base al numero totale di:</span><span class="sxs-lookup"><span data-stu-id="24a00-282">The number of chat rooms of a certain size is computed based on the total number of:</span></span>

  - <span data-ttu-id="24a00-283">Utenti attivi nel sistema</span><span class="sxs-lookup"><span data-stu-id="24a00-283">Active users in the system</span></span>

  - <span data-ttu-id="24a00-284">Utenti attivi nelle chat room delle dimensioni specificate</span><span class="sxs-lookup"><span data-stu-id="24a00-284">Active users in chat rooms of the given size</span></span>

  - <span data-ttu-id="24a00-285">Chat room con le dimensioni specificate a cui è associato un singolo utente</span><span class="sxs-lookup"><span data-stu-id="24a00-285">Chat rooms of the given size that a single user joins</span></span>

<span data-ttu-id="24a00-286">Per ogni chat room, la tabella di pianificazione della capacità precedente specifica il numero di voci di controllo di accesso associate alla chat room, incluse le voci assegnate direttamente alla chat room.</span><span class="sxs-lookup"><span data-stu-id="24a00-286">For each chat room, the preceding capacity planning table specifies the number of access control entries that are associated with the chat room, including entries that are assigned directly to the chat room.</span></span> <span data-ttu-id="24a00-287">È possibile controllare l'accesso alle singole chat room usando gli elenchi di controllo di accesso (ACL).</span><span class="sxs-lookup"><span data-stu-id="24a00-287">You can control access to individual chat rooms by using access control lists (ACLs).</span></span> <span data-ttu-id="24a00-288">È anche possibile controllare l'accesso a livello di categoria.</span><span class="sxs-lookup"><span data-stu-id="24a00-288">You can also control access at the category level.</span></span> <span data-ttu-id="24a00-289">In un ACL una singola voce di controllo di accesso può essere un gruppo di utenti, ad esempio un gruppo di sicurezza, una lista di distribuzione o un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="24a00-289">In an ACL, an individual access control entry can be either a user group—for example, a security group, a distribution list, or a single user.</span></span> <span data-ttu-id="24a00-290">Puoi definire le voci di controllo di accesso per i responsabili delle chat room, i relatori e i membri.</span><span class="sxs-lookup"><span data-stu-id="24a00-290">You can define access control entries for chat room managers, presenters, and members.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="24a00-291">Nella pianificazione della strategia per la gestione delle chat room, tieni presente che il numero totale di voci di controllo di accesso consentite è 2 milioni.</span><span class="sxs-lookup"><span data-stu-id="24a00-291">In planning your strategy for managing chat rooms, keep in mind that the total number of allowed access control entries is 2 million.</span></span> <span data-ttu-id="24a00-292">Se le voci di controllo di accesso calcolate superano 2 milioni, le prestazioni del server potrebbero peggiorare in modo significativo.</span><span class="sxs-lookup"><span data-stu-id="24a00-292">If the calculated access control entries exceed 2 million, server performance could degrade significantly.</span></span> <span data-ttu-id="24a00-293">Per evitare questo problema, se possibile, verificare che le voci di controllo di accesso siano gruppi di utenti anziché singoli.</span><span class="sxs-lookup"><span data-stu-id="24a00-293">To avoid this issue, whenever possible, be sure that your access control entries are user groups instead of individual users.</span></span>



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a><span data-ttu-id="24a00-294">Pianificazione della capacità per la gestione dell'accesso alle chat room tramite invito</span><span class="sxs-lookup"><span data-stu-id="24a00-294">Capacity Planning for Managing Chat Room Access by Invitation</span></span>

<span data-ttu-id="24a00-295">È possibile usare la tabella di pianificazione della capacità seguente per comprendere il numero di inviti che il server di chat persistente crea e archivia nel database della chat persistente quando è configurato per l'invio di inviti.</span><span class="sxs-lookup"><span data-stu-id="24a00-295">You can use the following capacity planning table to understand the number of invitations that Persistent Chat Server creates and stores in the Persistent Chat database when it is configured to send invitations.</span></span> <span data-ttu-id="24a00-296">Puoi gestire gli inviti per la categoria usando la pagina **Impostazioni categoria chat room** nel pannello di controllo di Lync Server oppure usando il cmdlet di Windows PowerShell, **set-csPersistentChatCategory**.</span><span class="sxs-lookup"><span data-stu-id="24a00-296">You manage invitations on the Category by using the **Chat Room Category settings** page in the Lync Server Control Panel, or by using the Windows PowerShell cmdlet, **set-csPersistentChatCategory**.</span></span> <span data-ttu-id="24a00-297">È possibile gestire gli inviti in una chat room (in linea con ciò che la categoria consente) usando la pagina **gestione sala** avviata dal client Lync o usando un cmdlet di Windows PowerShell, **set-csPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="24a00-297">You can manage invitations on a chat room (in line with what the category allows) by using the **Room Management** page launched from the Lync client, or by using a Windows PowerShell cmdlet, **set-csPersistentChatRoom**.</span></span>

<span data-ttu-id="24a00-298">I dati di esempio nella tabella seguente presuppongono che, nella pagina **delle impostazioni della chat room** per 50% di tutte le chat room, l'opzione **inviti** sia impostata su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="24a00-298">The sample data in the following table assumes that, on the **Chat room settings** page for 50 percent of all chat rooms, the **Invitations** option is set to **Yes**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="24a00-299">Se il valore calcolato per il numero di inviti generati dal server supera 1 milione, le prestazioni del server potrebbero peggiorare in modo significativo.</span><span class="sxs-lookup"><span data-stu-id="24a00-299">If the calculated value for the number of invitations that is generated by the server exceeds 1 million, server performance could degrade significantly.</span></span> <span data-ttu-id="24a00-300">Per evitare questo problema, assicurati di ridurre al minimo il numero di chat room configurate per l'invio di inviti o per limitare il numero di utenti che possono partecipare alle chat room configurate per l'invio di inviti.</span><span class="sxs-lookup"><span data-stu-id="24a00-300">To avoid this issue, be sure that you minimize the number of chat rooms that are configured to send invitations or restrict the number of users who can join chat rooms that have been configured to send invitations.</span></span>



</div>

### <a name="chat-room-access-by-invitation-sample"></a><span data-ttu-id="24a00-301">Accesso alla chat room tramite l'esempio di invito</span><span class="sxs-lookup"><span data-stu-id="24a00-301">Chat Room Access by Invitation Sample</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="24a00-302">Piccole chat room</span><span class="sxs-lookup"><span data-stu-id="24a00-302">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="24a00-303">Chat room di medie dimensioni</span><span class="sxs-lookup"><span data-stu-id="24a00-303">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="24a00-304">Chat room di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="24a00-304">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="24a00-305">Totale</span><span class="sxs-lookup"><span data-stu-id="24a00-305">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24a00-306">Utenti che possono accedere alla chat room</span><span class="sxs-lookup"><span data-stu-id="24a00-306">Users who can access chat room</span></span></p></td>
<td><p><span data-ttu-id="24a00-307">30 per camera</span><span class="sxs-lookup"><span data-stu-id="24a00-307">30 per room</span></span></p></td>
<td><p><span data-ttu-id="24a00-308">150 per camera</span><span class="sxs-lookup"><span data-stu-id="24a00-308">150 per room</span></span></p></td>
<td><p><span data-ttu-id="24a00-309">16.000 per camera</span><span class="sxs-lookup"><span data-stu-id="24a00-309">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-310">Percentuale di camere con inviti</span><span class="sxs-lookup"><span data-stu-id="24a00-310">Percentage of rooms that have invitations</span></span></p></td>
<td><p><span data-ttu-id="24a00-311">50%</span><span class="sxs-lookup"><span data-stu-id="24a00-311">50%</span></span></p></td>
<td><p><span data-ttu-id="24a00-312">50%</span><span class="sxs-lookup"><span data-stu-id="24a00-312">50%</span></span></p></td>
<td><p><span data-ttu-id="24a00-313">50%</span><span class="sxs-lookup"><span data-stu-id="24a00-313">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-314">Chat room configurate per l'invio di inviti</span><span class="sxs-lookup"><span data-stu-id="24a00-314">Chat rooms configured to send invitations</span></span></p></td>
<td><p><span data-ttu-id="24a00-315"><em>16.000</em></span><span class="sxs-lookup"><span data-stu-id="24a00-315"><em>16,000</em></span></span></p></td>
<td><p><span data-ttu-id="24a00-316"><em>533</em></span><span class="sxs-lookup"><span data-stu-id="24a00-316"><em>533</em></span></span></p></td>
<td><p><span data-ttu-id="24a00-317"><em>5</em></span><span class="sxs-lookup"><span data-stu-id="24a00-317"><em>5</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-318">Utenti che possono accedere alla chat room</span><span class="sxs-lookup"><span data-stu-id="24a00-318">Users who can access the chat room</span></span></p></td>
<td><p><span data-ttu-id="24a00-319"><em>60</em></span><span class="sxs-lookup"><span data-stu-id="24a00-319"><em>60</em></span></span></p></td>
<td><p><span data-ttu-id="24a00-320"><em>225</em></span><span class="sxs-lookup"><span data-stu-id="24a00-320"><em>225</em></span></span></p></td>
<td><p><span data-ttu-id="24a00-321"><em>16.000</em></span><span class="sxs-lookup"><span data-stu-id="24a00-321"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-322">Inviti generati dal server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="24a00-322">Invitations generated by Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="24a00-323">960.000</span><span class="sxs-lookup"><span data-stu-id="24a00-323">960,000</span></span></p></td>
<td><p><span data-ttu-id="24a00-324">120.000</span><span class="sxs-lookup"><span data-stu-id="24a00-324">120,000</span></span></p></td>
<td><p><span data-ttu-id="24a00-325">80.000</span><span class="sxs-lookup"><span data-stu-id="24a00-325">80,000</span></span></p></td>
<td><p><span data-ttu-id="24a00-326">1.160.000</span><span class="sxs-lookup"><span data-stu-id="24a00-326">1,160,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-327">Numero massimo di inviti consentiti</span><span class="sxs-lookup"><span data-stu-id="24a00-327">Maximum allowable number of invitations</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="24a00-328">2 milioni</span><span class="sxs-lookup"><span data-stu-id="24a00-328">2,000,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-329">Modello 1-iniziare con il numero di messaggi previsto per ogni camera al giorno</span><span class="sxs-lookup"><span data-stu-id="24a00-329">Model 1 - Start with expected number of messages per room per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-330">Tasso di chat per camera (per giorno)</span><span class="sxs-lookup"><span data-stu-id="24a00-330">Chat Rate Per Room (per day)</span></span></p></td>
<td><p><span data-ttu-id="24a00-331">50</span><span class="sxs-lookup"><span data-stu-id="24a00-331">50</span></span></p></td>
<td><p><span data-ttu-id="24a00-332">500</span><span class="sxs-lookup"><span data-stu-id="24a00-332">500</span></span></p></td>
<td><p><span data-ttu-id="24a00-333">100</span><span class="sxs-lookup"><span data-stu-id="24a00-333">100</span></span></p></td>
<td><p><span data-ttu-id="24a00-334">650</span><span class="sxs-lookup"><span data-stu-id="24a00-334">650</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-335">Velocità di chat (al secondo) in tutte le sale</span><span class="sxs-lookup"><span data-stu-id="24a00-335">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="24a00-336">55,56</span><span class="sxs-lookup"><span data-stu-id="24a00-336">55.56</span></span></p></td>
<td><p><span data-ttu-id="24a00-337">18,52</span><span class="sxs-lookup"><span data-stu-id="24a00-337">18.52</span></span></p></td>
<td><p><span data-ttu-id="24a00-338">0,03</span><span class="sxs-lookup"><span data-stu-id="24a00-338">0.03</span></span></p></td>
<td><p><span data-ttu-id="24a00-339">74</span><span class="sxs-lookup"><span data-stu-id="24a00-339">74</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-340">Modello 2-inizio con il numero di messaggi pubblicati per utente per giorno</span><span class="sxs-lookup"><span data-stu-id="24a00-340">Model 2 - Start with number of messages posted per user per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-341">Tasso di chat per utente per giorno</span><span class="sxs-lookup"><span data-stu-id="24a00-341">Chat rate per user per day</span></span></p></td>
<td><p><span data-ttu-id="24a00-342">15</span><span class="sxs-lookup"><span data-stu-id="24a00-342">15</span></span></p></td>
<td><p><span data-ttu-id="24a00-343">5</span><span class="sxs-lookup"><span data-stu-id="24a00-343">5</span></span></p></td>
<td><p><span data-ttu-id="24a00-344">0,1</span><span class="sxs-lookup"><span data-stu-id="24a00-344">0.1</span></span></p></td>
<td><p><span data-ttu-id="24a00-345">20</span><span class="sxs-lookup"><span data-stu-id="24a00-345">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-346">Tasso di chat per camera (per giorno)</span><span class="sxs-lookup"><span data-stu-id="24a00-346">Chat rate per room (per day)</span></span></p></td>
<td><p><span data-ttu-id="24a00-347">38</span><span class="sxs-lookup"><span data-stu-id="24a00-347">38</span></span></p></td>
<td><p><span data-ttu-id="24a00-348">375</span><span class="sxs-lookup"><span data-stu-id="24a00-348">375</span></span></p></td>
<td><p><span data-ttu-id="24a00-349">800</span><span class="sxs-lookup"><span data-stu-id="24a00-349">800</span></span></p></td>
<td><p><span data-ttu-id="24a00-350">1.213</span><span class="sxs-lookup"><span data-stu-id="24a00-350">1,213</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-351">Velocità di chat (al secondo) in tutte le sale</span><span class="sxs-lookup"><span data-stu-id="24a00-351">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="24a00-352">41,67</span><span class="sxs-lookup"><span data-stu-id="24a00-352">41.67</span></span></p></td>
<td><p><span data-ttu-id="24a00-353">13,89</span><span class="sxs-lookup"><span data-stu-id="24a00-353">13.89</span></span></p></td>
<td><p><span data-ttu-id="24a00-354">0,28</span><span class="sxs-lookup"><span data-stu-id="24a00-354">0.28</span></span></p></td>
<td><p><span data-ttu-id="24a00-355">56</span><span class="sxs-lookup"><span data-stu-id="24a00-355">56</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="24a00-356">Modello utente delle prestazioni del server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="24a00-356">Persistent Chat Server Performance User Model</span></span>

<span data-ttu-id="24a00-357">La tabella seguente descrive il modello di utente per il server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="24a00-357">The following table describes the user model for Persistent Chat Server.</span></span> <span data-ttu-id="24a00-358">Fornisce la base per i requisiti di pianificazione della capacità e rappresenta un'organizzazione tipica con utenti simultanei di 80.000 su quattro server.</span><span class="sxs-lookup"><span data-stu-id="24a00-358">It provides the basis for the capacity planning requirements and represents a typical organization with 80,000 concurrent users on four servers.</span></span>

### <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="24a00-359">Modello utente delle prestazioni del server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="24a00-359">Persistent Chat Server Performance User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24a00-360">Numero di utenti attivi connessi</span><span class="sxs-lookup"><span data-stu-id="24a00-360">Number of active users connected</span></span></p></td>
<td><p><span data-ttu-id="24a00-361">80.000</span><span class="sxs-lookup"><span data-stu-id="24a00-361">80,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-362">Numero di istanze del servizio server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="24a00-362">Number of Persistent Chat Server service instances</span></span></p></td>
<td><p><span data-ttu-id="24a00-363">4</span><span class="sxs-lookup"><span data-stu-id="24a00-363">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-364">Dimensioni delle piccole chat room</span><span class="sxs-lookup"><span data-stu-id="24a00-364">Size of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="24a00-365">30 utenti</span><span class="sxs-lookup"><span data-stu-id="24a00-365">30 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-366">Dimensioni delle chat room medie</span><span class="sxs-lookup"><span data-stu-id="24a00-366">Size of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="24a00-367">utenti di 150</span><span class="sxs-lookup"><span data-stu-id="24a00-367">150 users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-368">Dimensioni delle chat room di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="24a00-368">Size of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="24a00-369">utenti di 16.000</span><span class="sxs-lookup"><span data-stu-id="24a00-369">16,000 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-370">Numero totale di chat room</span><span class="sxs-lookup"><span data-stu-id="24a00-370">Total number of chat rooms</span></span></p></td>
<td><p><span data-ttu-id="24a00-371">33.077</span><span class="sxs-lookup"><span data-stu-id="24a00-371">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-372">Numero di chat room di piccole dimensioni</span><span class="sxs-lookup"><span data-stu-id="24a00-372">Number of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="24a00-373">32.000</span><span class="sxs-lookup"><span data-stu-id="24a00-373">32,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-374">Numero di chat room di medie dimensioni</span><span class="sxs-lookup"><span data-stu-id="24a00-374">Number of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="24a00-375">1.067</span><span class="sxs-lookup"><span data-stu-id="24a00-375">1,067</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-376">Numero di chat room di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="24a00-376">Number of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="24a00-377">10</span><span class="sxs-lookup"><span data-stu-id="24a00-377">10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-378">Numero totale di chat room per utente</span><span class="sxs-lookup"><span data-stu-id="24a00-378">Total number of chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="24a00-379">16</span><span class="sxs-lookup"><span data-stu-id="24a00-379">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-380">Numero di piccole chat room per utente</span><span class="sxs-lookup"><span data-stu-id="24a00-380">Number of small chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="24a00-381">12</span><span class="sxs-lookup"><span data-stu-id="24a00-381">12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-382">Numero di chat room medie per utente</span><span class="sxs-lookup"><span data-stu-id="24a00-382">Number of medium chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="24a00-383">2</span><span class="sxs-lookup"><span data-stu-id="24a00-383">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-384">Numero di chat room di grandi dimensioni per utente</span><span class="sxs-lookup"><span data-stu-id="24a00-384">Number of large chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="24a00-385">2</span><span class="sxs-lookup"><span data-stu-id="24a00-385">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-386">Numero di sale Unite per utente</span><span class="sxs-lookup"><span data-stu-id="24a00-386">Number of rooms joined per user</span></span></p></td>
<td><p><span data-ttu-id="24a00-387">24</span><span class="sxs-lookup"><span data-stu-id="24a00-387">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-388">Tasso di partecipazione di picco</span><span class="sxs-lookup"><span data-stu-id="24a00-388">Peak join rate</span></span></p></td>
<td><p><span data-ttu-id="24a00-389">10/secondo</span><span class="sxs-lookup"><span data-stu-id="24a00-389">10/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-390">Tasso di chat totale</span><span class="sxs-lookup"><span data-stu-id="24a00-390">Total chat rate</span></span></p></td>
<td><p><span data-ttu-id="24a00-391">24/secondo</span><span class="sxs-lookup"><span data-stu-id="24a00-391">24/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-392">Tariffa chat per piccole chat room</span><span class="sxs-lookup"><span data-stu-id="24a00-392">Chat rate for small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="24a00-393">22.22/second</span><span class="sxs-lookup"><span data-stu-id="24a00-393">22.22/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-394">Tasso di chat per le chat room di medie dimensioni</span><span class="sxs-lookup"><span data-stu-id="24a00-394">Chat rate for medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="24a00-395">1.67/Second</span><span class="sxs-lookup"><span data-stu-id="24a00-395">1.67/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-396">Tasso di chat per le chat room di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="24a00-396">Chat rate for large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="24a00-397">~ 0.15/secondo</span><span class="sxs-lookup"><span data-stu-id="24a00-397">~0.15/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-398">Percentuale di chat room configurate per gli inviti</span><span class="sxs-lookup"><span data-stu-id="24a00-398">Percentage of chat rooms configured for invitations</span></span></p></td>
<td><p><span data-ttu-id="24a00-399">50%</span><span class="sxs-lookup"><span data-stu-id="24a00-399">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-400">Percentuale di appartenenze dirette</span><span class="sxs-lookup"><span data-stu-id="24a00-400">Percentage of direct memberships</span></span></p></td>
<td><p><span data-ttu-id="24a00-401">50%</span><span class="sxs-lookup"><span data-stu-id="24a00-401">50%</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-402">Percentuale di appartenenze ai gruppi</span><span class="sxs-lookup"><span data-stu-id="24a00-402">Percentage of group memberships</span></span></p></td>
<td><p><span data-ttu-id="24a00-403">50%</span><span class="sxs-lookup"><span data-stu-id="24a00-403">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-404">Numero medio di affiliazioni predecessore in servizi di dominio Active Directory</span><span class="sxs-lookup"><span data-stu-id="24a00-404">Average number of ancestor affiliations in Active Directory Domain Services</span></span></p></td>
<td><p><span data-ttu-id="24a00-405">100-200</span><span class="sxs-lookup"><span data-stu-id="24a00-405">100 - 200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-406">Numero di contatti sottoscritti per utente</span><span class="sxs-lookup"><span data-stu-id="24a00-406">Number of subscribed contacts per user</span></span></p></td>
<td><p><span data-ttu-id="24a00-407">80</span><span class="sxs-lookup"><span data-stu-id="24a00-407">80</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-408">Numero medio di endpoint per utente</span><span class="sxs-lookup"><span data-stu-id="24a00-408">Average number of endpoints per user</span></span></p></td>
<td><p><span data-ttu-id="24a00-409">1,5</span><span class="sxs-lookup"><span data-stu-id="24a00-409">1.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-410">Numero medio di chat room visibili per endpoint</span><span class="sxs-lookup"><span data-stu-id="24a00-410">Average number of visible chat rooms per endpoint</span></span></p></td>
<td><p><span data-ttu-id="24a00-411">1,5</span><span class="sxs-lookup"><span data-stu-id="24a00-411">1.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-412">Numero medio di chat room visibili per utente</span><span class="sxs-lookup"><span data-stu-id="24a00-412">Average number of visible chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="24a00-413">2,25 (50% per 1 sala e 50% per 2 sale); Fino a 6 camere aperte, una per ogni monitor</span><span class="sxs-lookup"><span data-stu-id="24a00-413">2.25 (50% for 1 room and 50% for 2 rooms); Up to 6 rooms open, one per monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-414">Numero di partecipanti interrogati per intervallo</span><span class="sxs-lookup"><span data-stu-id="24a00-414">Number of participants polled per interval</span></span></p></td>
<td><p><span data-ttu-id="24a00-415">25 per la chat room visibile</span><span class="sxs-lookup"><span data-stu-id="24a00-415">25 per visible chat room</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-416">Lunghezza dell'intervallo di polling</span><span class="sxs-lookup"><span data-stu-id="24a00-416">Length of polling interval</span></span></p></td>
<td><p><span data-ttu-id="24a00-417">5 minuti</span><span class="sxs-lookup"><span data-stu-id="24a00-417">5 minutes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-418">Numero di partecipanti a polling al secondo</span><span class="sxs-lookup"><span data-stu-id="24a00-418">Number of participants polled per second</span></span></p></td>
<td><p><span data-ttu-id="24a00-419">15.000</span><span class="sxs-lookup"><span data-stu-id="24a00-419">15,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a00-420">Numero di modifiche alla presenza per ora per utente</span><span class="sxs-lookup"><span data-stu-id="24a00-420">Number of presence changes per hour per user</span></span></p></td>
<td><p><span data-ttu-id="24a00-421">6</span><span class="sxs-lookup"><span data-stu-id="24a00-421">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a00-422">Numero di modifiche alla presenza al secondo</span><span class="sxs-lookup"><span data-stu-id="24a00-422">Number of presence changes per second</span></span></p></td>
<td><p><span data-ttu-id="24a00-423">133,33</span><span class="sxs-lookup"><span data-stu-id="24a00-423">133.33</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

