---
title: 'Lync Server 2013: pianificazione della capacità per il server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Persistent Chat Server
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615006(v=OCS.15)
ms:contentKeyID: 48184580
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0cd27f961d3b4857cf13d5786897bd29a657851
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="7e7d1-102">Pianificazione della capacità per il server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e7d1-102">Capacity planning for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e7d1-103">_**Ultimo argomento modificato:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="7e7d1-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="7e7d1-104">Il server Chat persistente può eseguire chat in tempo reale multiutente che può persistere per il recupero e la ricerca futuri.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-104">Persistent Chat Server can perform multi-user real-time chat that can persist for future retrieval and search.</span></span> <span data-ttu-id="7e7d1-105">A differenza della messaggistica istantanea di gruppo che viene salvata nella cassetta postale dell'utente se la cronologia delle conversazioni è configurata, una sessione del server Chat persistente resta aperta più a lungo e il contenuto viene salvato in un server, insieme ai messaggi, ai file, agli URL e ad altri dati che fanno parte di un conversazione continua.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-105">Unlike group instant messaging (IM) that is saved in a user’s mailbox if conversation history is configured, a Persistent Chat Server session stays open longer, and the content is saved on a server, along with the messages, files, URLs, and other data that are part of an ongoing conversation.</span></span>

<span data-ttu-id="7e7d1-106">La pianificazione della capacità è una parte importante della preparazione per la distribuzione del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-106">Capacity planning is an important part of preparing to deploy Persistent Chat Server.</span></span> <span data-ttu-id="7e7d1-107">In questo argomento vengono fornite informazioni dettagliate sulle tabelle di topologie del server Chat persistente supportate e sulla pianificazione della capacità che è possibile utilizzare per determinare la configurazione ottimale per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-107">This topic provides details about supported Persistent Chat Server topologies and capacity planning tables that you can use to determine the best configuration for your deployment.</span></span> <span data-ttu-id="7e7d1-108">Viene inoltre descritto come gestire al meglio le distribuzioni di server Chat persistente che richiedono una maggiore capacità negli orari di punta.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-108">It also describes how to best manage Persistent Chat Server deployments that require greater capacity at peak times.</span></span>

<span data-ttu-id="7e7d1-109">Per scaricare il server Chat persistente, vedere "Microsoft Lync Server 13 Persistent Chat [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539)server" all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-109">To download Persistent Chat Server, see "Microsoft Lync Server 13 Persistent Chat Server" at [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539).</span></span>

<span data-ttu-id="7e7d1-110">Per informazioni dettagliate sull'installazione del server Chat persistente, vedere [Installing Persistent Chat Server in Lync server 2013](lync-server-2013-installing-persistent-chat-server.md) e [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-110">For details about installing Persistent Chat Server, see [Installing Persistent Chat Server in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) and [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="7e7d1-111">Gli strumenti di supporto, ad esempio lo strumento di pianificazione di Lync Server, sono in grado di facilitare la pianificazione della capacità.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-111">Support tools, such as Lync Server Planning Tool, can further assist you with capacity planning.</span></span> <span data-ttu-id="7e7d1-112">Per informazioni dettagliate sullo strumento di pianificazione, vedere [beginning the Planning Process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-112">For details about the Planning Tool, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<div>

## <a name="persistent-chat-server-supported-topologies"></a><span data-ttu-id="7e7d1-113">Topologie supportate dal server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="7e7d1-113">Persistent Chat Server Supported Topologies</span></span>

<span data-ttu-id="7e7d1-114">È possibile distribuire il server Chat persistente in pool a server singolo o a più server e con topologia a pool singolo o a più pool.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-114">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span>

<span data-ttu-id="7e7d1-115">Ora è supportato anche il server Chat persistente sul server Standard Edition per le nuove distribuzioni di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-115">We now also support Persistent Chat Server on Standard Edition server for new Lync Server 2013 deployments.</span></span> <span data-ttu-id="7e7d1-116">Tuttavia, le prestazioni e la scala saranno intaccate e poiché non esiste un'opzione di disponibilità elevata per la nuova distribuzione, si prevede di utilizzarla principalmente ai fini della prova del concetto, della valutazione e così via.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-116">However, performance and scale will be affected, and because there is no high availability option for this new deployment, we expect you to use this primarily for the purposes of proof of concept, evaluation, and so on.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7e7d1-117">Per ulteriori informazioni su entrambe le topologie, vedere <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for Persistent Chat Server in Lync server 2013</A> in questa documentazione impostare e <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-117">For additional details about both topologies, see <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for Persistent Chat Server in Lync Server 2013</A> in this documentation set and <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="7e7d1-118">Topologia a server singolo</span><span class="sxs-lookup"><span data-stu-id="7e7d1-118">Single-Server Topology</span></span>

<span data-ttu-id="7e7d1-119">La configurazione minima e la distribuzione più semplice per il server Chat persistente è una singola topologia del server front-end del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-119">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="7e7d1-120">Questa distribuzione richiede un singolo server che esegue il server Chat persistente (che facoltativamente esegue il servizio di conformità, se la conformità è abilitata), un server che ospita il database di SQL Server e, se è necessaria la conformità, il database di SQL Server per archiviare la dati di conformità.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-120">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7e7d1-121">Non è possibile aggiungere altri server a un pool di server Chat persistente avviato come distribuzione a server singolo in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-121">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="7e7d1-122">È consigliabile utilizzare la topologia del pool a più server, anche se si utilizza un server singolo.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-122">We recommend using the multiple-server pool topology, even if you’re using a single server.</span></span> <span data-ttu-id="7e7d1-123">In questo modo sarà possibile aggiungere altri server in un secondo momento, se necessario.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-123">This is so that you’ll be able to add more servers later, if it's necessary.</span></span> 


</div>

<span data-ttu-id="7e7d1-124">Nella figura seguente vengono illustrati tutti i componenti obbligatori e facoltativi di una topologia per un singolo server front-end di Persistent Chat Server con conformità.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-124">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="7e7d1-125">**Singolo server Persistent Chat**</span><span class="sxs-lookup"><span data-stu-id="7e7d1-125">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="7e7d1-126">![Topologia a server singolo con servizio di conformità](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologia a server singolo con servizio di conformità")</span><span class="sxs-lookup"><span data-stu-id="7e7d1-126">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="7e7d1-127">Topologia a più server</span><span class="sxs-lookup"><span data-stu-id="7e7d1-127">Multiple-Server Topology</span></span>

<span data-ttu-id="7e7d1-128">Per garantire maggiore capacità e affidabilità, è possibile distribuire una topologia a più server, come descritto in [Planning for Persistent Chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="7e7d1-128">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="7e7d1-129">La topologia a più server può includere ben quattro computer attivi che eseguono il server Chat persistente (le configurazioni a disponibilità elevata e ripristino di emergenza consentiranno fino a otto, ma solo quattro possono essere attive e le restanti quattro in standby).</span><span class="sxs-lookup"><span data-stu-id="7e7d1-129">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="7e7d1-130">Ogni server è in grado di supportare fino a 20.000 utenti simultanei, per un totale di 80.000 utenti simultanei connessi a un pool di server Chat persistente con 4 server.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-130">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="7e7d1-131">Una topologia a più server è identica alla topologia a server singolo, tranne per il fatto che più server ospitano il server Chat persistente e che possono aumentare la scalabilità verticale.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-131">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="7e7d1-132">Più computer che eseguono il server Chat persistente devono risiedere nello stesso dominio di servizi di dominio Active Directory come Lync Server e il servizio di conformità.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-132">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="7e7d1-133">Nella figura seguente vengono illustrati tutti i componenti di una topologia a più server con più computer che eseguono il server Chat persistente, il servizio di conformità facoltativo e un database di conformità distinto.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-133">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="7e7d1-134">**Più server Persistent Chat**</span><span class="sxs-lookup"><span data-stu-id="7e7d1-134">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="7e7d1-135">![Topologia a più server](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologia a più server")</span><span class="sxs-lookup"><span data-stu-id="7e7d1-135">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="7e7d1-136">In una distribuzione di server Chat persistente con quattro server, in cui 80.000 gli utenti possono essere contemporaneamente connessi a e utilizzando la chat persistente, il carico viene distribuito uniformemente a 20.000 utenti per server.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-136">In a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to and using Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="7e7d1-137">Se un server non è disponibile, gli utenti che sono connessi a quel server perderanno l'accesso al server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-137">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="7e7d1-138">Gli utenti disconnessi vengono automaticamente trasferiti ai server rimanenti fino a quando il server non disponibile non viene ripristinato.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-138">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> <span data-ttu-id="7e7d1-139">In base alla quantità di traffico di chat persistente sulla rete, il trasferimento può richiedere alcuni minuti o più.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-139">Depending on the amount of Persistent Chat traffic on the network, this transfer can take a few minutes or longer.</span></span> <span data-ttu-id="7e7d1-140">Poiché ognuno dei server rimanenti può ospitare fino a 30.000 utenti, è consigliabile ripristinare il server non disponibile il più velocemente possibile per evitare problemi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-140">Because each of the remaining servers might be hosting as many as 30,000 users, we recommend that you restore the unavailable server as quickly as possible to avoid performance issues.</span></span> <span data-ttu-id="7e7d1-141">In caso contrario, è possibile rendere disponibile un altro server Chat persistente mediante il generatore di topologie o il cmdlet di Windows PowerShell, **Set-CsPersistentChatActiveServer**.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-141">Otherwise, you can make another Persistent Chat Server available by using the Topology Builder or the Windows PowerShell cmdlet, **set-CsPersistentChatActiveServer**.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a><span data-ttu-id="7e7d1-142">Pianificazione della capacità del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="7e7d1-142">Persistent Chat Server Capacity Planning</span></span>

<span data-ttu-id="7e7d1-143">Nelle tabelle seguenti è possibile ottenere informazioni sulla pianificazione della capacità per il server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-143">The following tables can help you with capacity planning for Persistent Chat Server.</span></span> <span data-ttu-id="7e7d1-144">Modellano la modalità di modifica delle varie impostazioni del server Chat persistente sulle funzionalità di capacità.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-144">They model how changing various Persistent Chat Server settings affect capacity capabilities.</span></span>

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a><span data-ttu-id="7e7d1-145">Pianificazione della capacità massima per il server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="7e7d1-145">Planning Your Maximum Capacity for Persistent Chat Server</span></span>

<span data-ttu-id="7e7d1-146">Utilizzare la tabella di esempio seguente per determinare il numero di utenti che sarà possibile supportare.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-146">Use the following sample table to determine the number of users you will be able to support.</span></span>

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a><span data-ttu-id="7e7d1-147">Esempio di capacità massima del pool di server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="7e7d1-147">Persistent Chat Server pool Maximum Capacity Sample</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-148">Istanze del servizio Persistent Chat attiva</span><span class="sxs-lookup"><span data-stu-id="7e7d1-148">Active Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-149"><em>4</em></span><span class="sxs-lookup"><span data-stu-id="7e7d1-149"><em>4</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-150">Istanze del servizio chat persistente</span><span class="sxs-lookup"><span data-stu-id="7e7d1-150">Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-151"><em>8 (4 deve essere inattivo, solo un massimo di 4 può essere attivo)</em></span><span class="sxs-lookup"><span data-stu-id="7e7d1-151"><em>8 (4 must be inactive; only a maximum of 4 can be active)</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-152">Utenti attivi connessi</span><span class="sxs-lookup"><span data-stu-id="7e7d1-152">Active users connected</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-153"><em>80,000</em></span><span class="sxs-lookup"><span data-stu-id="7e7d1-153"><em>80,000</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-154">Totale utenti di cui è stato effettuato il provisioning</span><span class="sxs-lookup"><span data-stu-id="7e7d1-154">Total provisioned users</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-155">150.000</span><span class="sxs-lookup"><span data-stu-id="7e7d1-155">150,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-156">Numero di endpoint</span><span class="sxs-lookup"><span data-stu-id="7e7d1-156">Number of endpoints</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-157">120.000</span><span class="sxs-lookup"><span data-stu-id="7e7d1-157">120,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7e7d1-158">Nell'esempio precedente, il piano consiste nel supportare il numero massimo di utenti consentiti dal server Chat persistente: quattro server/istanze del servizio chat persistente (possono avere quattro server più passivi che eseguono il server Chat persistente per la disponibilità elevata e il ripristino di emergenza) e 20.000 utenti per server, per un totale di 80.000 utenti attivi.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-158">In the preceding sample, the plan is to support the maximum number of users that Persistent Chat Server allows: four servers/instances of the Persistent Chat service (can have four more passive servers running Persistent Chat Server for high availability and disaster recovery) and 20,000 users per server, for a total of 80,000 active users.</span></span>

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a><span data-ttu-id="7e7d1-159">Pianificazione della capacità per la gestione dell'accesso alle chat room persistente</span><span class="sxs-lookup"><span data-stu-id="7e7d1-159">Capacity Planning for Managing Persistent Chat Room Access</span></span>

<span data-ttu-id="7e7d1-160">La tabella di esempio seguente può essere utile per pianificare la gestione dell'accesso alle chat permanenti in un pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-160">The following sample table can help you plan for managing Persistent Chat room access in a Persistent Chat Server pool.</span></span>

### <a name="managing-chat-room-access-sample"></a><span data-ttu-id="7e7d1-161">Esempio di gestione dell'accesso alle chat</span><span class="sxs-lookup"><span data-stu-id="7e7d1-161">Managing Chat Room Access Sample</span></span>

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
<th><span data-ttu-id="7e7d1-162">Chat di piccole dimensioni</span><span class="sxs-lookup"><span data-stu-id="7e7d1-162">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="7e7d1-163">Chat room di medie dimensioni</span><span class="sxs-lookup"><span data-stu-id="7e7d1-163">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="7e7d1-164">Chat di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="7e7d1-164">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="7e7d1-165">Totale</span><span class="sxs-lookup"><span data-stu-id="7e7d1-165">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-166">Dimensioni delle chat room (numero di utenti connessi)</span><span class="sxs-lookup"><span data-stu-id="7e7d1-166">Size of chat rooms (number of users connected)</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-167">30 per stanza</span><span class="sxs-lookup"><span data-stu-id="7e7d1-167">30 per room</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-168">150 per camera</span><span class="sxs-lookup"><span data-stu-id="7e7d1-168">150 per room</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-169">16.000 per camera</span><span class="sxs-lookup"><span data-stu-id="7e7d1-169">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-170">Chat</span><span class="sxs-lookup"><span data-stu-id="7e7d1-170">Chat rooms</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-171">32.000</span><span class="sxs-lookup"><span data-stu-id="7e7d1-171">32,000</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-172">1.067</span><span class="sxs-lookup"><span data-stu-id="7e7d1-172">1,067</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-173">10 </span><span class="sxs-lookup"><span data-stu-id="7e7d1-173">10</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-174">33.077</span><span class="sxs-lookup"><span data-stu-id="7e7d1-174">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-175">% delle sale che sono Auditorium</span><span class="sxs-lookup"><span data-stu-id="7e7d1-175">% of rooms that are auditorium</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-176">1%</span><span class="sxs-lookup"><span data-stu-id="7e7d1-176">1%</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-177">1%</span><span class="sxs-lookup"><span data-stu-id="7e7d1-177">1%</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-178">50%</span><span class="sxs-lookup"><span data-stu-id="7e7d1-178">50%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-179">% di sale aperte</span><span class="sxs-lookup"><span data-stu-id="7e7d1-179">% of rooms that are open</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-180">3%</span><span class="sxs-lookup"><span data-stu-id="7e7d1-180">3%</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-181">3%</span><span class="sxs-lookup"><span data-stu-id="7e7d1-181">3%</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-182">50%</span><span class="sxs-lookup"><span data-stu-id="7e7d1-182">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-183">Aprire le sale (nessuna appartenenza esplicita)</span><span class="sxs-lookup"><span data-stu-id="7e7d1-183">Open rooms (no explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-184">960</span><span class="sxs-lookup"><span data-stu-id="7e7d1-184">960</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-185">32</span><span class="sxs-lookup"><span data-stu-id="7e7d1-185">32</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-186">5</span><span class="sxs-lookup"><span data-stu-id="7e7d1-186">5</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-187">997</span><span class="sxs-lookup"><span data-stu-id="7e7d1-187">997</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-188">Sale non aperte (sale normali con appartenenza esplicita)</span><span class="sxs-lookup"><span data-stu-id="7e7d1-188">Non-open rooms (regular rooms with explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-189">31.040</span><span class="sxs-lookup"><span data-stu-id="7e7d1-189">31,040</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-190">1,035</span><span class="sxs-lookup"><span data-stu-id="7e7d1-190">1.035</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-191">5</span><span class="sxs-lookup"><span data-stu-id="7e7d1-191">5</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-192">32.080</span><span class="sxs-lookup"><span data-stu-id="7e7d1-192">32,080</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-193">Sale Auditorium (ingresso altri relatori)</span><span class="sxs-lookup"><span data-stu-id="7e7d1-193">Auditorium rooms (additional presenters entry)</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-194">0</span><span class="sxs-lookup"><span data-stu-id="7e7d1-194">0</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-195">32</span><span class="sxs-lookup"><span data-stu-id="7e7d1-195">32</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-196">5</span><span class="sxs-lookup"><span data-stu-id="7e7d1-196">5</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-197">Sale gestite dall'appartenenza diretta</span><span class="sxs-lookup"><span data-stu-id="7e7d1-197">Rooms managed by direct membership</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-198">50%</span><span class="sxs-lookup"><span data-stu-id="7e7d1-198">50%</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-199">10%</span><span class="sxs-lookup"><span data-stu-id="7e7d1-199">10%</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-200">0</span><span class="sxs-lookup"><span data-stu-id="7e7d1-200">0%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-201">Chat gestite per gruppi di utenti</span><span class="sxs-lookup"><span data-stu-id="7e7d1-201">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-202">50%</span><span class="sxs-lookup"><span data-stu-id="7e7d1-202">50%</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-203">90%</span><span class="sxs-lookup"><span data-stu-id="7e7d1-203">90%</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-204">100%</span><span class="sxs-lookup"><span data-stu-id="7e7d1-204">100%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-205">Gruppi di utenti nell'elenco di appartenenza di ogni chat room per le sale aperte (non specificato in modo esplicito)</span><span class="sxs-lookup"><span data-stu-id="7e7d1-205">User groups in each chat room's membership list for open rooms (not specified explicitly)</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-206">0</span><span class="sxs-lookup"><span data-stu-id="7e7d1-206">0</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-207">0</span><span class="sxs-lookup"><span data-stu-id="7e7d1-207">0</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-208">0</span><span class="sxs-lookup"><span data-stu-id="7e7d1-208">0</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-209">Utenti nell'elenco di appartenenza di ogni chat room per le stanze non aperte</span><span class="sxs-lookup"><span data-stu-id="7e7d1-209">Users in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-210">30</span><span class="sxs-lookup"><span data-stu-id="7e7d1-210">30</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-211">150</span><span class="sxs-lookup"><span data-stu-id="7e7d1-211">150</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-212">16.000</span><span class="sxs-lookup"><span data-stu-id="7e7d1-212">16,000</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-213">Gruppi di utenti nell'elenco di appartenenza di ogni chat room per le stanze non aperte</span><span class="sxs-lookup"><span data-stu-id="7e7d1-213">User groups in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-214">3</span><span class="sxs-lookup"><span data-stu-id="7e7d1-214">3</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-215">5</span><span class="sxs-lookup"><span data-stu-id="7e7d1-215">5</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-216">10 </span><span class="sxs-lookup"><span data-stu-id="7e7d1-216">10</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-217">Users and User Groups nell'elenco Manager di ogni chat room (per le sale aperte e non aperte)</span><span class="sxs-lookup"><span data-stu-id="7e7d1-217">Users and user groups in each chat room's manager list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-218">6 </span><span class="sxs-lookup"><span data-stu-id="7e7d1-218">6</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-219">6 </span><span class="sxs-lookup"><span data-stu-id="7e7d1-219">6</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-220">6 </span><span class="sxs-lookup"><span data-stu-id="7e7d1-220">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-221">Gli utenti e i gruppi di utenti nell'elenco dei relatori di ogni sala chat dell'Auditorium (per le sale aperte e non aperte)</span><span class="sxs-lookup"><span data-stu-id="7e7d1-221">Users and user groups in each auditorium chat room's presenters list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-222">6 </span><span class="sxs-lookup"><span data-stu-id="7e7d1-222">6</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-223">6 </span><span class="sxs-lookup"><span data-stu-id="7e7d1-223">6</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-224">6 </span><span class="sxs-lookup"><span data-stu-id="7e7d1-224">6</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-225">Entità di appartenenza basate sull'utente in tutte le sale non aperte</span><span class="sxs-lookup"><span data-stu-id="7e7d1-225">User-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-226">465.600</span><span class="sxs-lookup"><span data-stu-id="7e7d1-226">465,600</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-227">15.520</span><span class="sxs-lookup"><span data-stu-id="7e7d1-227">15,520</span></span></p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-228">Entità di appartenenza basate sui gruppi di utenti in tutte le sale non aperte</span><span class="sxs-lookup"><span data-stu-id="7e7d1-228">User-group-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-229">46.560</span><span class="sxs-lookup"><span data-stu-id="7e7d1-229">46,560</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-230">4656</span><span class="sxs-lookup"><span data-stu-id="7e7d1-230">4656</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-231">50</span><span class="sxs-lookup"><span data-stu-id="7e7d1-231">50</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-232">Utenti e gruppi utenti basati su entità in tutte le chat room di Auditorium</span><span class="sxs-lookup"><span data-stu-id="7e7d1-232">Users and user groups based entities across all auditorium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-233">0</span><span class="sxs-lookup"><span data-stu-id="7e7d1-233">0</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-234">192</span><span class="sxs-lookup"><span data-stu-id="7e7d1-234">192</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-235">50</span><span class="sxs-lookup"><span data-stu-id="7e7d1-235">50</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-236">Gli utenti e i gruppi di utenti basati su entità Manager in tutti gli elenchi di gestione delle chat room</span><span class="sxs-lookup"><span data-stu-id="7e7d1-236">Users and user groups based manager entities across all chat rooms manager lists</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-237">192.000</span><span class="sxs-lookup"><span data-stu-id="7e7d1-237">192,000</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-238">6.400</span><span class="sxs-lookup"><span data-stu-id="7e7d1-238">6,400</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-239">60</span><span class="sxs-lookup"><span data-stu-id="7e7d1-239">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-240">Utenti attivi per chat</span><span class="sxs-lookup"><span data-stu-id="7e7d1-240">Active users per chat room</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-241"><em>30</em></span><span class="sxs-lookup"><span data-stu-id="7e7d1-241"><em>30</em></span></span></p></td>
<td><p><span data-ttu-id="7e7d1-242"><em>150</em></span><span class="sxs-lookup"><span data-stu-id="7e7d1-242"><em>150</em></span></span></p></td>
<td><p><span data-ttu-id="7e7d1-243"><em>16.000</em></span><span class="sxs-lookup"><span data-stu-id="7e7d1-243"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-244">Chat per utente</span><span class="sxs-lookup"><span data-stu-id="7e7d1-244">Chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-245"><em>12</em></span><span class="sxs-lookup"><span data-stu-id="7e7d1-245"><em>12</em></span></span></p></td>
<td><p><span data-ttu-id="7e7d1-246"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="7e7d1-246"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="7e7d1-247"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="7e7d1-247"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="7e7d1-248"><em>16</em></span><span class="sxs-lookup"><span data-stu-id="7e7d1-248"><em>16</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-249">Gruppi di utenti in ogni elenco di membri di una chat</span><span class="sxs-lookup"><span data-stu-id="7e7d1-249">User groups in each chat room’s membership list</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-250"><em>10</em></span><span class="sxs-lookup"><span data-stu-id="7e7d1-250"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="7e7d1-251"><em>10</em></span><span class="sxs-lookup"><span data-stu-id="7e7d1-251"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="7e7d1-252"><em>15</em></span><span class="sxs-lookup"><span data-stu-id="7e7d1-252"><em>15</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-253">Chat gestite per gruppi di utenti</span><span class="sxs-lookup"><span data-stu-id="7e7d1-253">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-254"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="7e7d1-254"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="7e7d1-255"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="7e7d1-255"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="7e7d1-256"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="7e7d1-256"><em>50%</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-257">Entità di appartenenza basata sui gruppi di utenti in tutte le chat</span><span class="sxs-lookup"><span data-stu-id="7e7d1-257">User-group-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-258">155.200</span><span class="sxs-lookup"><span data-stu-id="7e7d1-258">155,200</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-259">5173</span><span class="sxs-lookup"><span data-stu-id="7e7d1-259">5173</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-260">68</span><span class="sxs-lookup"><span data-stu-id="7e7d1-260">68</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-261">Entità di appartenenza basata sugli utenti in tutte le chat</span><span class="sxs-lookup"><span data-stu-id="7e7d1-261">User-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-262">465.600</span><span class="sxs-lookup"><span data-stu-id="7e7d1-262">465,600</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-263">77.600</span><span class="sxs-lookup"><span data-stu-id="7e7d1-263">77,600</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-264">72.000</span><span class="sxs-lookup"><span data-stu-id="7e7d1-264">72,000</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-265">Utenti e gruppi di utenti in ogni elenco dei gestori delle chat, dei relatori delle chat e degli ambiti</span><span class="sxs-lookup"><span data-stu-id="7e7d1-265">Users and user groups in each chat room's manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-266">6 </span><span class="sxs-lookup"><span data-stu-id="7e7d1-266">6</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-267">6 </span><span class="sxs-lookup"><span data-stu-id="7e7d1-267">6</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-268">6 </span><span class="sxs-lookup"><span data-stu-id="7e7d1-268">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-269">Gli utenti e i gruppi di utenti di tutte le chat room ' Manager, relatore e gli elenchi di ambiti</span><span class="sxs-lookup"><span data-stu-id="7e7d1-269">Users and user groups across all chat rooms' manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-270">192.000</span><span class="sxs-lookup"><span data-stu-id="7e7d1-270">192,000</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-271">6400</span><span class="sxs-lookup"><span data-stu-id="7e7d1-271">6400</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-272">60</span><span class="sxs-lookup"><span data-stu-id="7e7d1-272">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-273">Voci di controllo di accesso</span><span class="sxs-lookup"><span data-stu-id="7e7d1-273">Access control entries</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-274">704.160</span><span class="sxs-lookup"><span data-stu-id="7e7d1-274">704,160</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-275">26.768</span><span class="sxs-lookup"><span data-stu-id="7e7d1-275">26,768</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-276">160</span><span class="sxs-lookup"><span data-stu-id="7e7d1-276">160</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-277">731.088</span><span class="sxs-lookup"><span data-stu-id="7e7d1-277">731,088</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-278">Voci di controllo di accesso massime</span><span class="sxs-lookup"><span data-stu-id="7e7d1-278">Maximum access control entries</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="7e7d1-279">2 milioni</span><span class="sxs-lookup"><span data-stu-id="7e7d1-279">2,000,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7e7d1-280">Nell'esempio precedente, quando si distribuiscono i server Chat persistente in base alle linee guida consigliate, è possibile gestire fino a 80.000 utenti attivi in un pool di quattro server con conformità abilitata.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-280">In the preceding sample, when you deploy the Persistent Chat Servers according to the recommended guidelines, they can handle up to 80,000 active users across a four-server pool with compliance enabled.</span></span>

<span data-ttu-id="7e7d1-281">In questo esempio vengono illustrate le chat room categorizzate come piccole (30 utenti attivi in un determinato momento), medie (150 utenti attivi) e grandi (16.000 utenti attivi).</span><span class="sxs-lookup"><span data-stu-id="7e7d1-281">This sample shows chat rooms categorized as small (30 active users at any given time), medium (150 active users), and large (16,000 active users).</span></span> <span data-ttu-id="7e7d1-282">Il numero di chat di una determinata dimensione viene calcolato in base al numero totale di:</span><span class="sxs-lookup"><span data-stu-id="7e7d1-282">The number of chat rooms of a certain size is computed based on the total number of:</span></span>

  - <span data-ttu-id="7e7d1-283">Utenti attivi nel sistema</span><span class="sxs-lookup"><span data-stu-id="7e7d1-283">Active users in the system</span></span>

  - <span data-ttu-id="7e7d1-284">Utenti attivi nelle chat delle dimensioni specificate</span><span class="sxs-lookup"><span data-stu-id="7e7d1-284">Active users in chat rooms of the given size</span></span>

  - <span data-ttu-id="7e7d1-285">Chat delle dimensioni specificate cui partecipa ogni singole utente</span><span class="sxs-lookup"><span data-stu-id="7e7d1-285">Chat rooms of the given size that a single user joins</span></span>

<span data-ttu-id="7e7d1-286">Per ogni chat room, la tabella di pianificazione della capacità precedente specifica il numero di voci di controllo di accesso associate alla chat room, incluse le voci che vengono assegnate direttamente alla chat room.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-286">For each chat room, the preceding capacity planning table specifies the number of access control entries that are associated with the chat room, including entries that are assigned directly to the chat room.</span></span> <span data-ttu-id="7e7d1-287">È possibile controllare l'accesso a singole chat tramite elenchi di controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-287">You can control access to individual chat rooms by using access control lists (ACLs).</span></span> <span data-ttu-id="7e7d1-288">È inoltre possibile controllare l'accesso a livello di categoria.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-288">You can also control access at the category level.</span></span> <span data-ttu-id="7e7d1-289">In un ACL, una singola voce di controllo di accesso può essere un gruppo di utenti, ad esempio un gruppo di sicurezza, una lista di distribuzione o un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-289">In an ACL, an individual access control entry can be either a user group—for example, a security group, a distribution list, or a single user.</span></span> <span data-ttu-id="7e7d1-290">È possibile definire voci di controllo di accesso per gestori, relatori e membri delle chat.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-290">You can define access control entries for chat room managers, presenters, and members.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7e7d1-291">Nella pianificazione della strategia per la gestione delle chat room, tenere presente che il numero totale di voci di controllo di accesso consentito è 2 milioni.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-291">In planning your strategy for managing chat rooms, keep in mind that the total number of allowed access control entries is 2 million.</span></span> <span data-ttu-id="7e7d1-292">Se le voci di controllo di accesso calcolate superano 2 milioni, le prestazioni del server potrebbero peggiorare significativamente.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-292">If the calculated access control entries exceed 2 million, server performance could degrade significantly.</span></span> <span data-ttu-id="7e7d1-293">Per evitare questo problema, quando possibile, assicurarsi che le voci di controllo di accesso siano gruppi di utenti anziché singoli.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-293">To avoid this issue, whenever possible, be sure that your access control entries are user groups instead of individual users.</span></span>



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a><span data-ttu-id="7e7d1-294">Pianificazione della capacità per la gestione dell'accesso alle chat in base a invito</span><span class="sxs-lookup"><span data-stu-id="7e7d1-294">Capacity Planning for Managing Chat Room Access by Invitation</span></span>

<span data-ttu-id="7e7d1-295">È possibile utilizzare la seguente tabella di pianificazione della capacità per comprendere il numero di inviti che il server Chat persistente crea e archivia nel database di Persistent Chat quando è configurato per l'invio di inviti.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-295">You can use the following capacity planning table to understand the number of invitations that Persistent Chat Server creates and stores in the Persistent Chat database when it is configured to send invitations.</span></span> <span data-ttu-id="7e7d1-296">È possibile gestire gli inviti per la categoria utilizzando la pagina **Impostazioni categoria chat room** nel pannello di controllo di Lync Server o utilizzando il cmdlet di Windows PowerShell, **set-csPersistentChatCategory**.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-296">You manage invitations on the Category by using the **Chat Room Category settings** page in the Lync Server Control Panel, or by using the Windows PowerShell cmdlet, **set-csPersistentChatCategory**.</span></span> <span data-ttu-id="7e7d1-297">È possibile gestire gli inviti in una chat room (in linea con la categoria consentita) utilizzando la pagina **gestione sala** avviata dal client Lync o utilizzando un cmdlet di Windows PowerShell, **set-csPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-297">You can manage invitations on a chat room (in line with what the category allows) by using the **Room Management** page launched from the Lync client, or by using a Windows PowerShell cmdlet, **set-csPersistentChatRoom**.</span></span>

<span data-ttu-id="7e7d1-298">I dati di esempio riportati nella tabella seguente presuppongono che, nella pagina **Impostazioni chat room** per il 50% di tutte le chat room, l'opzione **inviti** è impostata su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-298">The sample data in the following table assumes that, on the **Chat room settings** page for 50 percent of all chat rooms, the **Invitations** option is set to **Yes**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7e7d1-299">Se il valore calcolato per il numero di inviti generati dal server supera 1 milione, le prestazioni del server potrebbero peggiorare significativamente.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-299">If the calculated value for the number of invitations that is generated by the server exceeds 1 million, server performance could degrade significantly.</span></span> <span data-ttu-id="7e7d1-300">Per evitare questo problema, accertarsi di ridurre al minimo il numero di chat configurate per l'invio di inviti o limitare il numero di utenti che possono partecipare alle chat room configurate per l'invio di inviti.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-300">To avoid this issue, be sure that you minimize the number of chat rooms that are configured to send invitations or restrict the number of users who can join chat rooms that have been configured to send invitations.</span></span>



</div>

### <a name="chat-room-access-by-invitation-sample"></a><span data-ttu-id="7e7d1-301">Esempio di accesso alle chat in base a invito</span><span class="sxs-lookup"><span data-stu-id="7e7d1-301">Chat Room Access by Invitation Sample</span></span>

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
<th><span data-ttu-id="7e7d1-302">Chat di piccole dimensioni</span><span class="sxs-lookup"><span data-stu-id="7e7d1-302">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="7e7d1-303">Chat room di medie dimensioni</span><span class="sxs-lookup"><span data-stu-id="7e7d1-303">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="7e7d1-304">Chat di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="7e7d1-304">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="7e7d1-305">Totale</span><span class="sxs-lookup"><span data-stu-id="7e7d1-305">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-306">Utenti che possono accedere a chat room</span><span class="sxs-lookup"><span data-stu-id="7e7d1-306">Users who can access chat room</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-307">30 per stanza</span><span class="sxs-lookup"><span data-stu-id="7e7d1-307">30 per room</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-308">150 per camera</span><span class="sxs-lookup"><span data-stu-id="7e7d1-308">150 per room</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-309">16.000 per camera</span><span class="sxs-lookup"><span data-stu-id="7e7d1-309">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-310">Percentuale di stanze con inviti</span><span class="sxs-lookup"><span data-stu-id="7e7d1-310">Percentage of rooms that have invitations</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-311">50%</span><span class="sxs-lookup"><span data-stu-id="7e7d1-311">50%</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-312">50%</span><span class="sxs-lookup"><span data-stu-id="7e7d1-312">50%</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-313">50%</span><span class="sxs-lookup"><span data-stu-id="7e7d1-313">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-314">Chat configurate per l'invio di inviti</span><span class="sxs-lookup"><span data-stu-id="7e7d1-314">Chat rooms configured to send invitations</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-315"><em>16.000</em></span><span class="sxs-lookup"><span data-stu-id="7e7d1-315"><em>16,000</em></span></span></p></td>
<td><p><span data-ttu-id="7e7d1-316"><em>533</em></span><span class="sxs-lookup"><span data-stu-id="7e7d1-316"><em>533</em></span></span></p></td>
<td><p><span data-ttu-id="7e7d1-317"><em>5</em></span><span class="sxs-lookup"><span data-stu-id="7e7d1-317"><em>5</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-318">Utenti che possono accedere alla chat</span><span class="sxs-lookup"><span data-stu-id="7e7d1-318">Users who can access the chat room</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-319"><em>60</em></span><span class="sxs-lookup"><span data-stu-id="7e7d1-319"><em>60</em></span></span></p></td>
<td><p><span data-ttu-id="7e7d1-320"><em>225</em></span><span class="sxs-lookup"><span data-stu-id="7e7d1-320"><em>225</em></span></span></p></td>
<td><p><span data-ttu-id="7e7d1-321"><em>16.000</em></span><span class="sxs-lookup"><span data-stu-id="7e7d1-321"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-322">Inviti generati dal server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="7e7d1-322">Invitations generated by Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-323">960.000</span><span class="sxs-lookup"><span data-stu-id="7e7d1-323">960,000</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-324">120.000</span><span class="sxs-lookup"><span data-stu-id="7e7d1-324">120,000</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-325">80,000</span><span class="sxs-lookup"><span data-stu-id="7e7d1-325">80,000</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-326">1.160.000</span><span class="sxs-lookup"><span data-stu-id="7e7d1-326">1,160,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-327">Numero massimo consentito di inviti</span><span class="sxs-lookup"><span data-stu-id="7e7d1-327">Maximum allowable number of invitations</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="7e7d1-328">2 milioni</span><span class="sxs-lookup"><span data-stu-id="7e7d1-328">2,000,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-329">Modello 1-iniziare con il numero previsto di messaggi per stanza al giorno</span><span class="sxs-lookup"><span data-stu-id="7e7d1-329">Model 1 - Start with expected number of messages per room per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-330">Frequenza chat per camera (al giorno)</span><span class="sxs-lookup"><span data-stu-id="7e7d1-330">Chat Rate Per Room (per day)</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-331">50</span><span class="sxs-lookup"><span data-stu-id="7e7d1-331">50</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-332">500</span><span class="sxs-lookup"><span data-stu-id="7e7d1-332">500</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-333">100</span><span class="sxs-lookup"><span data-stu-id="7e7d1-333">100</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-334">650</span><span class="sxs-lookup"><span data-stu-id="7e7d1-334">650</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-335">Velocità di chat (al secondo) in tutte le sale</span><span class="sxs-lookup"><span data-stu-id="7e7d1-335">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-336">55,56</span><span class="sxs-lookup"><span data-stu-id="7e7d1-336">55.56</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-337">18,52</span><span class="sxs-lookup"><span data-stu-id="7e7d1-337">18.52</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-338">0,03</span><span class="sxs-lookup"><span data-stu-id="7e7d1-338">0.03</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-339">74</span><span class="sxs-lookup"><span data-stu-id="7e7d1-339">74</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-340">Modello 2-iniziare con il numero di messaggi inviati per utente al giorno</span><span class="sxs-lookup"><span data-stu-id="7e7d1-340">Model 2 - Start with number of messages posted per user per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-341">Frequenza di chat per utente al giorno</span><span class="sxs-lookup"><span data-stu-id="7e7d1-341">Chat rate per user per day</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-342">15 </span><span class="sxs-lookup"><span data-stu-id="7e7d1-342">15</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-343">5</span><span class="sxs-lookup"><span data-stu-id="7e7d1-343">5</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-344">0,1</span><span class="sxs-lookup"><span data-stu-id="7e7d1-344">0.1</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-345">20</span><span class="sxs-lookup"><span data-stu-id="7e7d1-345">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-346">Frequenza chat per camera (al giorno)</span><span class="sxs-lookup"><span data-stu-id="7e7d1-346">Chat rate per room (per day)</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-347">38</span><span class="sxs-lookup"><span data-stu-id="7e7d1-347">38</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-348">375</span><span class="sxs-lookup"><span data-stu-id="7e7d1-348">375</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-349">800</span><span class="sxs-lookup"><span data-stu-id="7e7d1-349">800</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-350">1.213</span><span class="sxs-lookup"><span data-stu-id="7e7d1-350">1,213</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-351">Velocità di chat (al secondo) in tutte le sale</span><span class="sxs-lookup"><span data-stu-id="7e7d1-351">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-352">41,67</span><span class="sxs-lookup"><span data-stu-id="7e7d1-352">41.67</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-353">13,89</span><span class="sxs-lookup"><span data-stu-id="7e7d1-353">13.89</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-354">0,28</span><span class="sxs-lookup"><span data-stu-id="7e7d1-354">0.28</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-355">56</span><span class="sxs-lookup"><span data-stu-id="7e7d1-355">56</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="7e7d1-356">Modello utente per le prestazioni del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="7e7d1-356">Persistent Chat Server Performance User Model</span></span>

<span data-ttu-id="7e7d1-357">Nella tabella seguente viene descritto il modello utente per il server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-357">The following table describes the user model for Persistent Chat Server.</span></span> <span data-ttu-id="7e7d1-358">Fornisce la base per i requisiti di pianificazione della capacità e rappresenta un'organizzazione tipica con 80.000 utenti simultanei su quattro server.</span><span class="sxs-lookup"><span data-stu-id="7e7d1-358">It provides the basis for the capacity planning requirements and represents a typical organization with 80,000 concurrent users on four servers.</span></span>

### <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="7e7d1-359">Modello utente per le prestazioni del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="7e7d1-359">Persistent Chat Server Performance User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-360">Numero di utenti attivi connessi</span><span class="sxs-lookup"><span data-stu-id="7e7d1-360">Number of active users connected</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-361">80,000</span><span class="sxs-lookup"><span data-stu-id="7e7d1-361">80,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-362">Numero di istanze del servizio del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="7e7d1-362">Number of Persistent Chat Server service instances</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-363">4</span><span class="sxs-lookup"><span data-stu-id="7e7d1-363">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-364">Numero di utenti di chat di piccole dimensioni</span><span class="sxs-lookup"><span data-stu-id="7e7d1-364">Size of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-365">30 utenti</span><span class="sxs-lookup"><span data-stu-id="7e7d1-365">30 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-366">Numero di utenti di chat di medie dimensioni</span><span class="sxs-lookup"><span data-stu-id="7e7d1-366">Size of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-367">150 utenti</span><span class="sxs-lookup"><span data-stu-id="7e7d1-367">150 users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-368">Numero di utenti di chat di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="7e7d1-368">Size of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-369">16.000 utenti</span><span class="sxs-lookup"><span data-stu-id="7e7d1-369">16,000 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-370">Numero totale di chat</span><span class="sxs-lookup"><span data-stu-id="7e7d1-370">Total number of chat rooms</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-371">33.077</span><span class="sxs-lookup"><span data-stu-id="7e7d1-371">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-372">Numero di chat di piccole dimensioni</span><span class="sxs-lookup"><span data-stu-id="7e7d1-372">Number of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-373">32.000</span><span class="sxs-lookup"><span data-stu-id="7e7d1-373">32,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-374">Numero di chat di medie dimensioni</span><span class="sxs-lookup"><span data-stu-id="7e7d1-374">Number of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-375">1.067</span><span class="sxs-lookup"><span data-stu-id="7e7d1-375">1,067</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-376">Numero di chat di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="7e7d1-376">Number of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-377">10 </span><span class="sxs-lookup"><span data-stu-id="7e7d1-377">10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-378">Numero totale di chat per utente</span><span class="sxs-lookup"><span data-stu-id="7e7d1-378">Total number of chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-379">16 </span><span class="sxs-lookup"><span data-stu-id="7e7d1-379">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-380">Numero di chat di piccole dimensioni per utente</span><span class="sxs-lookup"><span data-stu-id="7e7d1-380">Number of small chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-381">12</span><span class="sxs-lookup"><span data-stu-id="7e7d1-381">12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-382">Numero di chat di medie dimensioni per utente</span><span class="sxs-lookup"><span data-stu-id="7e7d1-382">Number of medium chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-383">2</span><span class="sxs-lookup"><span data-stu-id="7e7d1-383">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-384">Numero di chat di grandi dimensioni per utente</span><span class="sxs-lookup"><span data-stu-id="7e7d1-384">Number of large chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-385">2</span><span class="sxs-lookup"><span data-stu-id="7e7d1-385">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-386">Numero di sale Unite per utente</span><span class="sxs-lookup"><span data-stu-id="7e7d1-386">Number of rooms joined per user</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-387">24</span><span class="sxs-lookup"><span data-stu-id="7e7d1-387">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-388">Frequenza di partecipazione di punta</span><span class="sxs-lookup"><span data-stu-id="7e7d1-388">Peak join rate</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-389">10/secondo</span><span class="sxs-lookup"><span data-stu-id="7e7d1-389">10/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-390">Frequenza di chat totale</span><span class="sxs-lookup"><span data-stu-id="7e7d1-390">Total chat rate</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-391">24/secondo</span><span class="sxs-lookup"><span data-stu-id="7e7d1-391">24/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-392">Frequenza di chat per chat di piccole dimensioni</span><span class="sxs-lookup"><span data-stu-id="7e7d1-392">Chat rate for small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-393">22.22/secondo</span><span class="sxs-lookup"><span data-stu-id="7e7d1-393">22.22/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-394">Frequenza di chat per chat di medie dimensioni</span><span class="sxs-lookup"><span data-stu-id="7e7d1-394">Chat rate for medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-395">1.67/secondo</span><span class="sxs-lookup"><span data-stu-id="7e7d1-395">1.67/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-396">Frequenza di chat per chat di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="7e7d1-396">Chat rate for large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-397">~ 0.15/Second</span><span class="sxs-lookup"><span data-stu-id="7e7d1-397">~0.15/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-398">Percentuale di chat configurate per l'invio di inviti</span><span class="sxs-lookup"><span data-stu-id="7e7d1-398">Percentage of chat rooms configured for invitations</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-399">50%</span><span class="sxs-lookup"><span data-stu-id="7e7d1-399">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-400">Percentuale di appartenenza diretta</span><span class="sxs-lookup"><span data-stu-id="7e7d1-400">Percentage of direct memberships</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-401">50%</span><span class="sxs-lookup"><span data-stu-id="7e7d1-401">50%</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-402">Percentuale di appartenenza a gruppi</span><span class="sxs-lookup"><span data-stu-id="7e7d1-402">Percentage of group memberships</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-403">50%</span><span class="sxs-lookup"><span data-stu-id="7e7d1-403">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-404">Numero medio di affiliazioni degli antenati in servizi di dominio Active Directory</span><span class="sxs-lookup"><span data-stu-id="7e7d1-404">Average number of ancestor affiliations in Active Directory Domain Services</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-405">100 - 200</span><span class="sxs-lookup"><span data-stu-id="7e7d1-405">100 - 200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-406">Numero di contatti sottoscritti per utente</span><span class="sxs-lookup"><span data-stu-id="7e7d1-406">Number of subscribed contacts per user</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-407">80</span><span class="sxs-lookup"><span data-stu-id="7e7d1-407">80</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-408">Numero medio di endpoint per utente</span><span class="sxs-lookup"><span data-stu-id="7e7d1-408">Average number of endpoints per user</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-409">1,5</span><span class="sxs-lookup"><span data-stu-id="7e7d1-409">1.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-410">Numero medio di chat room visibili per endpoint</span><span class="sxs-lookup"><span data-stu-id="7e7d1-410">Average number of visible chat rooms per endpoint</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-411">1,5</span><span class="sxs-lookup"><span data-stu-id="7e7d1-411">1.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-412">Numero medio di chat room visibili per utente</span><span class="sxs-lookup"><span data-stu-id="7e7d1-412">Average number of visible chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-413">2,25 (50% per 1 sala e 50% per 2 sale); Fino a 6 sale aperte, una per ogni monitor</span><span class="sxs-lookup"><span data-stu-id="7e7d1-413">2.25 (50% for 1 room and 50% for 2 rooms); Up to 6 rooms open, one per monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-414">Numero di partecipanti sottoposti a polling per intervallo</span><span class="sxs-lookup"><span data-stu-id="7e7d1-414">Number of participants polled per interval</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-415">25 per chat room visibile</span><span class="sxs-lookup"><span data-stu-id="7e7d1-415">25 per visible chat room</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-416">Durata dell'intervallo di polling</span><span class="sxs-lookup"><span data-stu-id="7e7d1-416">Length of polling interval</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-417">5 minuti</span><span class="sxs-lookup"><span data-stu-id="7e7d1-417">5 minutes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-418">Numero di partecipanti sottoposti a polling al secondo</span><span class="sxs-lookup"><span data-stu-id="7e7d1-418">Number of participants polled per second</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-419">15.000</span><span class="sxs-lookup"><span data-stu-id="7e7d1-419">15,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e7d1-420">Numero di modifiche delle informazioni sulla presenza all'ora per utente</span><span class="sxs-lookup"><span data-stu-id="7e7d1-420">Number of presence changes per hour per user</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-421">6 </span><span class="sxs-lookup"><span data-stu-id="7e7d1-421">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e7d1-422">Numero di modifiche delle informazioni sulla presenza al secondo</span><span class="sxs-lookup"><span data-stu-id="7e7d1-422">Number of presence changes per second</span></span></p></td>
<td><p><span data-ttu-id="7e7d1-423">133,33</span><span class="sxs-lookup"><span data-stu-id="7e7d1-423">133.33</span></span></p></td>
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

