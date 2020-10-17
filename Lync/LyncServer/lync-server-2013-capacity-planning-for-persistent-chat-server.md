---
title: 'Lync Server 2013: pianificazione della capacità per il server Chat persistente'
description: 'Lync Server 2013: pianificazione della capacità per il server Chat persistente.'
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
ms.openlocfilehash: f78f9f3666fb272b808ef36da2d3010f451d0079
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544492"
---
# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="b536e-103">Pianificazione della capacità per il server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b536e-103">Capacity planning for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b536e-104">_**Ultimo argomento modificato:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="b536e-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="b536e-105">Il server Chat persistente può eseguire chat in tempo reale multiutente che può persistere per il recupero e la ricerca futuri.</span><span class="sxs-lookup"><span data-stu-id="b536e-105">Persistent Chat Server can perform multi-user real-time chat that can persist for future retrieval and search.</span></span> <span data-ttu-id="b536e-106">A differenza della messaggistica istantanea di gruppo che viene salvata nella cassetta postale di un utente se la cronologia delle conversazioni è configurata, una sessione del server Chat persistente resta aperta più a lungo e il contenuto viene salvato in un server, insieme ai messaggi, ai file, agli URL e ad altri dati che fanno parte di una conversazione in corso.</span><span class="sxs-lookup"><span data-stu-id="b536e-106">Unlike group instant messaging (IM) that is saved in a user’s mailbox if conversation history is configured, a Persistent Chat Server session stays open longer, and the content is saved on a server, along with the messages, files, URLs, and other data that are part of an ongoing conversation.</span></span>

<span data-ttu-id="b536e-107">La pianificazione della capacità è una parte importante della preparazione per la distribuzione del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="b536e-107">Capacity planning is an important part of preparing to deploy Persistent Chat Server.</span></span> <span data-ttu-id="b536e-108">In questo argomento vengono fornite informazioni dettagliate sulle tabelle di topologie del server Chat persistente supportate e sulla pianificazione della capacità che è possibile utilizzare per determinare la configurazione ottimale per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b536e-108">This topic provides details about supported Persistent Chat Server topologies and capacity planning tables that you can use to determine the best configuration for your deployment.</span></span> <span data-ttu-id="b536e-109">Viene inoltre descritto come gestire al meglio le distribuzioni di server Chat persistente che richiedono una maggiore capacità negli orari di punta.</span><span class="sxs-lookup"><span data-stu-id="b536e-109">It also describes how to best manage Persistent Chat Server deployments that require greater capacity at peak times.</span></span>

<span data-ttu-id="b536e-110">Per scaricare il server Chat persistente, vedere "Microsoft Lync Server 13 Persistent Chat Server" all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539) .</span><span class="sxs-lookup"><span data-stu-id="b536e-110">To download Persistent Chat Server, see "Microsoft Lync Server 13 Persistent Chat Server" at [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539).</span></span>

<span data-ttu-id="b536e-111">Per informazioni dettagliate sull'installazione del server Chat persistente, vedere [Installing Persistent Chat Server in Lync server 2013](lync-server-2013-installing-persistent-chat-server.md) e [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b536e-111">For details about installing Persistent Chat Server, see [Installing Persistent Chat Server in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) and [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="b536e-112">Gli strumenti di supporto, ad esempio lo strumento di pianificazione di Lync Server, sono in grado di facilitare la pianificazione della capacità.</span><span class="sxs-lookup"><span data-stu-id="b536e-112">Support tools, such as Lync Server Planning Tool, can further assist you with capacity planning.</span></span> <span data-ttu-id="b536e-113">Per informazioni dettagliate sullo strumento di pianificazione, vedere [beginning the Planning Process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="b536e-113">For details about the Planning Tool, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<div>

## <a name="persistent-chat-server-supported-topologies"></a><span data-ttu-id="b536e-114">Topologie supportate dal server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="b536e-114">Persistent Chat Server Supported Topologies</span></span>

<span data-ttu-id="b536e-115">È possibile distribuire il server Chat persistente in pool a server singolo o a più server e con topologia a pool singolo o a più pool.</span><span class="sxs-lookup"><span data-stu-id="b536e-115">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span>

<span data-ttu-id="b536e-116">Ora è supportato anche il server Chat persistente sul server Standard Edition per le nuove distribuzioni di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b536e-116">We now also support Persistent Chat Server on Standard Edition server for new Lync Server 2013 deployments.</span></span> <span data-ttu-id="b536e-117">Tuttavia, le prestazioni e la scala saranno intaccate e poiché non esiste un'opzione di disponibilità elevata per la nuova distribuzione, si prevede di utilizzarla principalmente ai fini della prova del concetto, della valutazione e così via.</span><span class="sxs-lookup"><span data-stu-id="b536e-117">However, performance and scale will be affected, and because there is no high availability option for this new deployment, we expect you to use this primarily for the purposes of proof of concept, evaluation, and so on.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b536e-118">Per ulteriori informazioni su entrambe le topologie, vedere <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for Persistent Chat Server in Lync server 2013</A> in questa documentazione impostare e <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b536e-118">For additional details about both topologies, see <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for Persistent Chat Server in Lync Server 2013</A> in this documentation set and <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="b536e-119">Topologia a server singolo</span><span class="sxs-lookup"><span data-stu-id="b536e-119">Single-Server Topology</span></span>

<span data-ttu-id="b536e-120">La configurazione minima e la distribuzione più semplice per il server Chat persistente è una singola topologia del server front-end del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="b536e-120">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="b536e-121">Questa distribuzione richiede un singolo server che esegue il server Chat persistente (che, facoltativamente, esegue il servizio di conformità, se la conformità è abilitata), un server che ospita il database di SQL Server e, se necessario, il database di SQL Server per archiviare i dati di conformità.</span><span class="sxs-lookup"><span data-stu-id="b536e-121">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b536e-122">Non è possibile aggiungere altri server a un pool di server Chat persistente avviato come distribuzione a server singolo in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="b536e-122">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="b536e-123">È consigliabile utilizzare la topologia del pool a più server, anche se si utilizza un server singolo.</span><span class="sxs-lookup"><span data-stu-id="b536e-123">We recommend using the multiple-server pool topology, even if you’re using a single server.</span></span> <span data-ttu-id="b536e-124">In questo modo sarà possibile aggiungere altri server in un secondo momento, se necessario.</span><span class="sxs-lookup"><span data-stu-id="b536e-124">This is so that you’ll be able to add more servers later, if it's necessary.</span></span> 


</div>

<span data-ttu-id="b536e-125">Nella figura seguente vengono illustrati tutti i componenti obbligatori e facoltativi di una topologia per un singolo server front-end di Persistent Chat Server con conformità.</span><span class="sxs-lookup"><span data-stu-id="b536e-125">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="b536e-126">**Singolo server Persistent Chat**</span><span class="sxs-lookup"><span data-stu-id="b536e-126">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="b536e-127">![Topologia a server singolo con servizio di conformità](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologia a server singolo con servizio di conformità")</span><span class="sxs-lookup"><span data-stu-id="b536e-127">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="b536e-128">Topologia a più server</span><span class="sxs-lookup"><span data-stu-id="b536e-128">Multiple-Server Topology</span></span>

<span data-ttu-id="b536e-129">Per garantire maggiore capacità e affidabilità, è possibile distribuire una topologia a più server, come descritto in [Planning for Persistent Chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="b536e-129">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="b536e-130">La topologia a più server può includere ben quattro computer attivi che eseguono il server Chat persistente (le configurazioni a disponibilità elevata e ripristino di emergenza consentiranno fino a otto, ma solo quattro possono essere attive e le restanti quattro in standby).</span><span class="sxs-lookup"><span data-stu-id="b536e-130">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="b536e-131">Ogni server è in grado di supportare fino a 20.000 utenti simultanei, per un totale di 80.000 utenti simultanei connessi a un pool di server Chat persistente con 4 server.</span><span class="sxs-lookup"><span data-stu-id="b536e-131">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="b536e-132">Una topologia a più server è identica alla topologia a server singolo, tranne per il fatto che più server ospitano il server Chat persistente e che possono aumentare la scalabilità verticale.</span><span class="sxs-lookup"><span data-stu-id="b536e-132">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="b536e-133">Più computer che eseguono il server Chat persistente devono risiedere nello stesso dominio di servizi di dominio Active Directory come Lync Server e il servizio di conformità.</span><span class="sxs-lookup"><span data-stu-id="b536e-133">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="b536e-134">Nella figura seguente vengono illustrati tutti i componenti di una topologia a più server con più computer che eseguono il server Chat persistente, il servizio di conformità facoltativo e un database di conformità distinto.</span><span class="sxs-lookup"><span data-stu-id="b536e-134">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="b536e-135">**Più server Persistent Chat**</span><span class="sxs-lookup"><span data-stu-id="b536e-135">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="b536e-136">![Topologia a più server](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologia a più server")</span><span class="sxs-lookup"><span data-stu-id="b536e-136">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="b536e-137">In una distribuzione di server Chat persistente con quattro server, in cui 80.000 gli utenti possono essere contemporaneamente connessi a e utilizzando la chat persistente, il carico viene distribuito uniformemente a 20.000 utenti per server.</span><span class="sxs-lookup"><span data-stu-id="b536e-137">In a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to and using Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="b536e-138">Se un server non è disponibile, gli utenti che sono connessi a quel server perderanno l'accesso al server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="b536e-138">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="b536e-139">Gli utenti disconnessi vengono automaticamente trasferiti ai server rimanenti fino a quando il server non disponibile non viene ripristinato.</span><span class="sxs-lookup"><span data-stu-id="b536e-139">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> <span data-ttu-id="b536e-140">In base alla quantità di traffico di chat persistente sulla rete, il trasferimento può richiedere alcuni minuti o più.</span><span class="sxs-lookup"><span data-stu-id="b536e-140">Depending on the amount of Persistent Chat traffic on the network, this transfer can take a few minutes or longer.</span></span> <span data-ttu-id="b536e-141">Poiché ognuno dei server rimanenti può ospitare fino a 30.000 utenti, è consigliabile ripristinare il server non disponibile il più velocemente possibile per evitare problemi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="b536e-141">Because each of the remaining servers might be hosting as many as 30,000 users, we recommend that you restore the unavailable server as quickly as possible to avoid performance issues.</span></span> <span data-ttu-id="b536e-142">In caso contrario, è possibile rendere disponibile un altro server Chat persistente mediante il generatore di topologie o il cmdlet di Windows PowerShell, **Set-CsPersistentChatActiveServer**.</span><span class="sxs-lookup"><span data-stu-id="b536e-142">Otherwise, you can make another Persistent Chat Server available by using the Topology Builder or the Windows PowerShell cmdlet, **set-CsPersistentChatActiveServer**.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a><span data-ttu-id="b536e-143">Pianificazione della capacità del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="b536e-143">Persistent Chat Server Capacity Planning</span></span>

<span data-ttu-id="b536e-144">Nelle tabelle seguenti è possibile ottenere informazioni sulla pianificazione della capacità per il server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="b536e-144">The following tables can help you with capacity planning for Persistent Chat Server.</span></span> <span data-ttu-id="b536e-145">Modellano la modalità di modifica delle varie impostazioni del server Chat persistente sulle funzionalità di capacità.</span><span class="sxs-lookup"><span data-stu-id="b536e-145">They model how changing various Persistent Chat Server settings affect capacity capabilities.</span></span>

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a><span data-ttu-id="b536e-146">Pianificazione della capacità massima per il server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="b536e-146">Planning Your Maximum Capacity for Persistent Chat Server</span></span>

<span data-ttu-id="b536e-147">Utilizzare la tabella di esempio seguente per determinare il numero di utenti che sarà possibile supportare.</span><span class="sxs-lookup"><span data-stu-id="b536e-147">Use the following sample table to determine the number of users you will be able to support.</span></span>

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a><span data-ttu-id="b536e-148">Esempio di capacità massima del pool di server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="b536e-148">Persistent Chat Server pool Maximum Capacity Sample</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b536e-149">Istanze del servizio Persistent Chat attiva</span><span class="sxs-lookup"><span data-stu-id="b536e-149">Active Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="b536e-150"><em>4</em></span><span class="sxs-lookup"><span data-stu-id="b536e-150"><em>4</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-151">Istanze del servizio chat persistente</span><span class="sxs-lookup"><span data-stu-id="b536e-151">Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="b536e-152"><em>8 (4 deve essere inattivo, solo un massimo di 4 può essere attivo)</em></span><span class="sxs-lookup"><span data-stu-id="b536e-152"><em>8 (4 must be inactive; only a maximum of 4 can be active)</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-153">Utenti attivi connessi</span><span class="sxs-lookup"><span data-stu-id="b536e-153">Active users connected</span></span></p></td>
<td><p><span data-ttu-id="b536e-154"><em>80,000</em></span><span class="sxs-lookup"><span data-stu-id="b536e-154"><em>80,000</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-155">Totale utenti di cui è stato effettuato il provisioning</span><span class="sxs-lookup"><span data-stu-id="b536e-155">Total provisioned users</span></span></p></td>
<td><p><span data-ttu-id="b536e-156">150.000</span><span class="sxs-lookup"><span data-stu-id="b536e-156">150,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-157">Numero di endpoint</span><span class="sxs-lookup"><span data-stu-id="b536e-157">Number of endpoints</span></span></p></td>
<td><p><span data-ttu-id="b536e-158">120.000</span><span class="sxs-lookup"><span data-stu-id="b536e-158">120,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b536e-159">Nell'esempio precedente, il piano consiste nel supportare il numero massimo di utenti consentiti dal server Chat persistente: quattro server/istanze del servizio chat persistente (possono avere quattro server più passivi che eseguono il server Chat persistente per la disponibilità elevata e il ripristino di emergenza) e 20.000 utenti per server, per un totale di 80.000 utenti attivi.</span><span class="sxs-lookup"><span data-stu-id="b536e-159">In the preceding sample, the plan is to support the maximum number of users that Persistent Chat Server allows: four servers/instances of the Persistent Chat service (can have four more passive servers running Persistent Chat Server for high availability and disaster recovery) and 20,000 users per server, for a total of 80,000 active users.</span></span>

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a><span data-ttu-id="b536e-160">Pianificazione della capacità per la gestione dell'accesso alle chat room persistente</span><span class="sxs-lookup"><span data-stu-id="b536e-160">Capacity Planning for Managing Persistent Chat Room Access</span></span>

<span data-ttu-id="b536e-161">La tabella di esempio seguente può essere utile per pianificare la gestione dell'accesso alle chat permanenti in un pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="b536e-161">The following sample table can help you plan for managing Persistent Chat room access in a Persistent Chat Server pool.</span></span>

### <a name="managing-chat-room-access-sample"></a><span data-ttu-id="b536e-162">Esempio di gestione dell'accesso alle chat</span><span class="sxs-lookup"><span data-stu-id="b536e-162">Managing Chat Room Access Sample</span></span>

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
<th><span data-ttu-id="b536e-163">Chat di piccole dimensioni</span><span class="sxs-lookup"><span data-stu-id="b536e-163">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="b536e-164">Chat room di medie dimensioni</span><span class="sxs-lookup"><span data-stu-id="b536e-164">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="b536e-165">Chat di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="b536e-165">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="b536e-166">Totale</span><span class="sxs-lookup"><span data-stu-id="b536e-166">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b536e-167">Dimensioni delle chat room (numero di utenti connessi)</span><span class="sxs-lookup"><span data-stu-id="b536e-167">Size of chat rooms (number of users connected)</span></span></p></td>
<td><p><span data-ttu-id="b536e-168">30 per stanza</span><span class="sxs-lookup"><span data-stu-id="b536e-168">30 per room</span></span></p></td>
<td><p><span data-ttu-id="b536e-169">150 per camera</span><span class="sxs-lookup"><span data-stu-id="b536e-169">150 per room</span></span></p></td>
<td><p><span data-ttu-id="b536e-170">16.000 per camera</span><span class="sxs-lookup"><span data-stu-id="b536e-170">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-171">Chat</span><span class="sxs-lookup"><span data-stu-id="b536e-171">Chat rooms</span></span></p></td>
<td><p><span data-ttu-id="b536e-172">32.000</span><span class="sxs-lookup"><span data-stu-id="b536e-172">32,000</span></span></p></td>
<td><p><span data-ttu-id="b536e-173">1.067</span><span class="sxs-lookup"><span data-stu-id="b536e-173">1,067</span></span></p></td>
<td><p><span data-ttu-id="b536e-174">10  </span><span class="sxs-lookup"><span data-stu-id="b536e-174">10</span></span></p></td>
<td><p><span data-ttu-id="b536e-175">33.077</span><span class="sxs-lookup"><span data-stu-id="b536e-175">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-176">% delle sale che sono Auditorium</span><span class="sxs-lookup"><span data-stu-id="b536e-176">% of rooms that are auditorium</span></span></p></td>
<td><p><span data-ttu-id="b536e-177">1%</span><span class="sxs-lookup"><span data-stu-id="b536e-177">1%</span></span></p></td>
<td><p><span data-ttu-id="b536e-178">1%</span><span class="sxs-lookup"><span data-stu-id="b536e-178">1%</span></span></p></td>
<td><p><span data-ttu-id="b536e-179">50%</span><span class="sxs-lookup"><span data-stu-id="b536e-179">50%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-180">% di sale aperte</span><span class="sxs-lookup"><span data-stu-id="b536e-180">% of rooms that are open</span></span></p></td>
<td><p><span data-ttu-id="b536e-181">3%</span><span class="sxs-lookup"><span data-stu-id="b536e-181">3%</span></span></p></td>
<td><p><span data-ttu-id="b536e-182">3%</span><span class="sxs-lookup"><span data-stu-id="b536e-182">3%</span></span></p></td>
<td><p><span data-ttu-id="b536e-183">50%</span><span class="sxs-lookup"><span data-stu-id="b536e-183">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-184">Aprire le sale (nessuna appartenenza esplicita)</span><span class="sxs-lookup"><span data-stu-id="b536e-184">Open rooms (no explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="b536e-185">960</span><span class="sxs-lookup"><span data-stu-id="b536e-185">960</span></span></p></td>
<td><p><span data-ttu-id="b536e-186">32</span><span class="sxs-lookup"><span data-stu-id="b536e-186">32</span></span></p></td>
<td><p><span data-ttu-id="b536e-187">5 </span><span class="sxs-lookup"><span data-stu-id="b536e-187">5</span></span></p></td>
<td><p><span data-ttu-id="b536e-188">997</span><span class="sxs-lookup"><span data-stu-id="b536e-188">997</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-189">Sale non aperte (sale normali con appartenenza esplicita)</span><span class="sxs-lookup"><span data-stu-id="b536e-189">Non-open rooms (regular rooms with explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="b536e-190">31.040</span><span class="sxs-lookup"><span data-stu-id="b536e-190">31,040</span></span></p></td>
<td><p><span data-ttu-id="b536e-191">1,035</span><span class="sxs-lookup"><span data-stu-id="b536e-191">1.035</span></span></p></td>
<td><p><span data-ttu-id="b536e-192">5 </span><span class="sxs-lookup"><span data-stu-id="b536e-192">5</span></span></p></td>
<td><p><span data-ttu-id="b536e-193">32.080</span><span class="sxs-lookup"><span data-stu-id="b536e-193">32,080</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-194">Sale Auditorium (ingresso altri relatori)</span><span class="sxs-lookup"><span data-stu-id="b536e-194">Auditorium rooms (additional presenters entry)</span></span></p></td>
<td><p><span data-ttu-id="b536e-195">0</span><span class="sxs-lookup"><span data-stu-id="b536e-195">0</span></span></p></td>
<td><p><span data-ttu-id="b536e-196">32</span><span class="sxs-lookup"><span data-stu-id="b536e-196">32</span></span></p></td>
<td><p><span data-ttu-id="b536e-197">5 </span><span class="sxs-lookup"><span data-stu-id="b536e-197">5</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-198">Sale gestite dall'appartenenza diretta</span><span class="sxs-lookup"><span data-stu-id="b536e-198">Rooms managed by direct membership</span></span></p></td>
<td><p><span data-ttu-id="b536e-199">50%</span><span class="sxs-lookup"><span data-stu-id="b536e-199">50%</span></span></p></td>
<td><p><span data-ttu-id="b536e-200">10%</span><span class="sxs-lookup"><span data-stu-id="b536e-200">10%</span></span></p></td>
<td><p><span data-ttu-id="b536e-201">0</span><span class="sxs-lookup"><span data-stu-id="b536e-201">0%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-202">Chat gestite per gruppi di utenti</span><span class="sxs-lookup"><span data-stu-id="b536e-202">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="b536e-203">50%</span><span class="sxs-lookup"><span data-stu-id="b536e-203">50%</span></span></p></td>
<td><p><span data-ttu-id="b536e-204">90%</span><span class="sxs-lookup"><span data-stu-id="b536e-204">90%</span></span></p></td>
<td><p><span data-ttu-id="b536e-205">100%</span><span class="sxs-lookup"><span data-stu-id="b536e-205">100%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-206">Gruppi di utenti nell'elenco di appartenenza di ogni chat room per le sale aperte (non specificato in modo esplicito)</span><span class="sxs-lookup"><span data-stu-id="b536e-206">User groups in each chat room's membership list for open rooms (not specified explicitly)</span></span></p></td>
<td><p><span data-ttu-id="b536e-207">0</span><span class="sxs-lookup"><span data-stu-id="b536e-207">0</span></span></p></td>
<td><p><span data-ttu-id="b536e-208">0</span><span class="sxs-lookup"><span data-stu-id="b536e-208">0</span></span></p></td>
<td><p><span data-ttu-id="b536e-209">0</span><span class="sxs-lookup"><span data-stu-id="b536e-209">0</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-210">Utenti nell'elenco di appartenenza di ogni chat room per le stanze non aperte</span><span class="sxs-lookup"><span data-stu-id="b536e-210">Users in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="b536e-211">30</span><span class="sxs-lookup"><span data-stu-id="b536e-211">30</span></span></p></td>
<td><p><span data-ttu-id="b536e-212">150</span><span class="sxs-lookup"><span data-stu-id="b536e-212">150</span></span></p></td>
<td><p><span data-ttu-id="b536e-213">16.000</span><span class="sxs-lookup"><span data-stu-id="b536e-213">16,000</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-214">Gruppi di utenti nell'elenco di appartenenza di ogni chat room per le stanze non aperte</span><span class="sxs-lookup"><span data-stu-id="b536e-214">User groups in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="b536e-215">3</span><span class="sxs-lookup"><span data-stu-id="b536e-215">3</span></span></p></td>
<td><p><span data-ttu-id="b536e-216">5 </span><span class="sxs-lookup"><span data-stu-id="b536e-216">5</span></span></p></td>
<td><p><span data-ttu-id="b536e-217">10  </span><span class="sxs-lookup"><span data-stu-id="b536e-217">10</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-218">Users and User Groups nell'elenco Manager di ogni chat room (per le sale aperte e non aperte)</span><span class="sxs-lookup"><span data-stu-id="b536e-218">Users and user groups in each chat room's manager list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="b536e-219">6 </span><span class="sxs-lookup"><span data-stu-id="b536e-219">6</span></span></p></td>
<td><p><span data-ttu-id="b536e-220">6 </span><span class="sxs-lookup"><span data-stu-id="b536e-220">6</span></span></p></td>
<td><p><span data-ttu-id="b536e-221">6 </span><span class="sxs-lookup"><span data-stu-id="b536e-221">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-222">Gli utenti e i gruppi di utenti nell'elenco dei relatori di ogni sala chat dell'Auditorium (per le sale aperte e non aperte)</span><span class="sxs-lookup"><span data-stu-id="b536e-222">Users and user groups in each auditorium chat room's presenters list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="b536e-223">6 </span><span class="sxs-lookup"><span data-stu-id="b536e-223">6</span></span></p></td>
<td><p><span data-ttu-id="b536e-224">6 </span><span class="sxs-lookup"><span data-stu-id="b536e-224">6</span></span></p></td>
<td><p><span data-ttu-id="b536e-225">6 </span><span class="sxs-lookup"><span data-stu-id="b536e-225">6</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-226">Entità di appartenenza basate sull'utente in tutte le sale non aperte</span><span class="sxs-lookup"><span data-stu-id="b536e-226">User-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="b536e-227">465.600</span><span class="sxs-lookup"><span data-stu-id="b536e-227">465,600</span></span></p></td>
<td><p><span data-ttu-id="b536e-228">15.520</span><span class="sxs-lookup"><span data-stu-id="b536e-228">15,520</span></span></p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-229">Entità di appartenenza basate sui gruppi di utenti in tutte le sale non aperte</span><span class="sxs-lookup"><span data-stu-id="b536e-229">User-group-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="b536e-230">46.560</span><span class="sxs-lookup"><span data-stu-id="b536e-230">46,560</span></span></p></td>
<td><p><span data-ttu-id="b536e-231">4656</span><span class="sxs-lookup"><span data-stu-id="b536e-231">4656</span></span></p></td>
<td><p><span data-ttu-id="b536e-232">50</span><span class="sxs-lookup"><span data-stu-id="b536e-232">50</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-233">Utenti e gruppi utenti basati su entità in tutte le chat room di Auditorium</span><span class="sxs-lookup"><span data-stu-id="b536e-233">Users and user groups based entities across all auditorium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="b536e-234">0</span><span class="sxs-lookup"><span data-stu-id="b536e-234">0</span></span></p></td>
<td><p><span data-ttu-id="b536e-235">192</span><span class="sxs-lookup"><span data-stu-id="b536e-235">192</span></span></p></td>
<td><p><span data-ttu-id="b536e-236">50</span><span class="sxs-lookup"><span data-stu-id="b536e-236">50</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-237">Gli utenti e i gruppi di utenti basati su entità Manager in tutti gli elenchi di gestione delle chat room</span><span class="sxs-lookup"><span data-stu-id="b536e-237">Users and user groups based manager entities across all chat rooms manager lists</span></span></p></td>
<td><p><span data-ttu-id="b536e-238">192.000</span><span class="sxs-lookup"><span data-stu-id="b536e-238">192,000</span></span></p></td>
<td><p><span data-ttu-id="b536e-239">6.400</span><span class="sxs-lookup"><span data-stu-id="b536e-239">6,400</span></span></p></td>
<td><p><span data-ttu-id="b536e-240">60</span><span class="sxs-lookup"><span data-stu-id="b536e-240">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-241">Utenti attivi per chat</span><span class="sxs-lookup"><span data-stu-id="b536e-241">Active users per chat room</span></span></p></td>
<td><p><span data-ttu-id="b536e-242"><em>30</em></span><span class="sxs-lookup"><span data-stu-id="b536e-242"><em>30</em></span></span></p></td>
<td><p><span data-ttu-id="b536e-243"><em>150</em></span><span class="sxs-lookup"><span data-stu-id="b536e-243"><em>150</em></span></span></p></td>
<td><p><span data-ttu-id="b536e-244"><em>16.000</em></span><span class="sxs-lookup"><span data-stu-id="b536e-244"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-245">Chat per utente</span><span class="sxs-lookup"><span data-stu-id="b536e-245">Chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="b536e-246"><em>12</em></span><span class="sxs-lookup"><span data-stu-id="b536e-246"><em>12</em></span></span></p></td>
<td><p><span data-ttu-id="b536e-247"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="b536e-247"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="b536e-248"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="b536e-248"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="b536e-249"><em>16</em></span><span class="sxs-lookup"><span data-stu-id="b536e-249"><em>16</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-250">Gruppi di utenti in ogni elenco di membri di una chat</span><span class="sxs-lookup"><span data-stu-id="b536e-250">User groups in each chat room’s membership list</span></span></p></td>
<td><p><span data-ttu-id="b536e-251"><em>10</em></span><span class="sxs-lookup"><span data-stu-id="b536e-251"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="b536e-252"><em>10</em></span><span class="sxs-lookup"><span data-stu-id="b536e-252"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="b536e-253"><em>15</em></span><span class="sxs-lookup"><span data-stu-id="b536e-253"><em>15</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-254">Chat gestite per gruppi di utenti</span><span class="sxs-lookup"><span data-stu-id="b536e-254">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="b536e-255"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="b536e-255"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="b536e-256"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="b536e-256"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="b536e-257"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="b536e-257"><em>50%</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-258">Entità di appartenenza basata sui gruppi di utenti in tutte le chat</span><span class="sxs-lookup"><span data-stu-id="b536e-258">User-group-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="b536e-259">155.200</span><span class="sxs-lookup"><span data-stu-id="b536e-259">155,200</span></span></p></td>
<td><p><span data-ttu-id="b536e-260">5173</span><span class="sxs-lookup"><span data-stu-id="b536e-260">5173</span></span></p></td>
<td><p><span data-ttu-id="b536e-261">68</span><span class="sxs-lookup"><span data-stu-id="b536e-261">68</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-262">Entità di appartenenza basata sugli utenti in tutte le chat</span><span class="sxs-lookup"><span data-stu-id="b536e-262">User-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="b536e-263">465.600</span><span class="sxs-lookup"><span data-stu-id="b536e-263">465,600</span></span></p></td>
<td><p><span data-ttu-id="b536e-264">77.600</span><span class="sxs-lookup"><span data-stu-id="b536e-264">77,600</span></span></p></td>
<td><p><span data-ttu-id="b536e-265">72.000</span><span class="sxs-lookup"><span data-stu-id="b536e-265">72,000</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-266">Utenti e gruppi di utenti in ogni elenco dei gestori delle chat, dei relatori delle chat e degli ambiti</span><span class="sxs-lookup"><span data-stu-id="b536e-266">Users and user groups in each chat room's manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="b536e-267">6 </span><span class="sxs-lookup"><span data-stu-id="b536e-267">6</span></span></p></td>
<td><p><span data-ttu-id="b536e-268">6 </span><span class="sxs-lookup"><span data-stu-id="b536e-268">6</span></span></p></td>
<td><p><span data-ttu-id="b536e-269">6 </span><span class="sxs-lookup"><span data-stu-id="b536e-269">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-270">Gli utenti e i gruppi di utenti di tutte le chat room ' Manager, relatore e gli elenchi di ambiti</span><span class="sxs-lookup"><span data-stu-id="b536e-270">Users and user groups across all chat rooms' manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="b536e-271">192.000</span><span class="sxs-lookup"><span data-stu-id="b536e-271">192,000</span></span></p></td>
<td><p><span data-ttu-id="b536e-272">6400</span><span class="sxs-lookup"><span data-stu-id="b536e-272">6400</span></span></p></td>
<td><p><span data-ttu-id="b536e-273">60</span><span class="sxs-lookup"><span data-stu-id="b536e-273">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-274">Voci di controllo di accesso</span><span class="sxs-lookup"><span data-stu-id="b536e-274">Access control entries</span></span></p></td>
<td><p><span data-ttu-id="b536e-275">704.160</span><span class="sxs-lookup"><span data-stu-id="b536e-275">704,160</span></span></p></td>
<td><p><span data-ttu-id="b536e-276">26.768</span><span class="sxs-lookup"><span data-stu-id="b536e-276">26,768</span></span></p></td>
<td><p><span data-ttu-id="b536e-277">160</span><span class="sxs-lookup"><span data-stu-id="b536e-277">160</span></span></p></td>
<td><p><span data-ttu-id="b536e-278">731.088</span><span class="sxs-lookup"><span data-stu-id="b536e-278">731,088</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-279">Voci di controllo di accesso massime</span><span class="sxs-lookup"><span data-stu-id="b536e-279">Maximum access control entries</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="b536e-280">2 milioni</span><span class="sxs-lookup"><span data-stu-id="b536e-280">2,000,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b536e-281">Nell'esempio precedente, quando si distribuiscono i server Chat persistente in base alle linee guida consigliate, è possibile gestire fino a 80.000 utenti attivi in un pool di quattro server con conformità abilitata.</span><span class="sxs-lookup"><span data-stu-id="b536e-281">In the preceding sample, when you deploy the Persistent Chat Servers according to the recommended guidelines, they can handle up to 80,000 active users across a four-server pool with compliance enabled.</span></span>

<span data-ttu-id="b536e-282">In questo esempio vengono illustrate le chat room categorizzate come piccole (30 utenti attivi in un determinato momento), medie (150 utenti attivi) e grandi (16.000 utenti attivi).</span><span class="sxs-lookup"><span data-stu-id="b536e-282">This sample shows chat rooms categorized as small (30 active users at any given time), medium (150 active users), and large (16,000 active users).</span></span> <span data-ttu-id="b536e-283">Il numero di chat di una determinata dimensione viene calcolato in base al numero totale di:</span><span class="sxs-lookup"><span data-stu-id="b536e-283">The number of chat rooms of a certain size is computed based on the total number of:</span></span>

  - <span data-ttu-id="b536e-284">Utenti attivi nel sistema</span><span class="sxs-lookup"><span data-stu-id="b536e-284">Active users in the system</span></span>

  - <span data-ttu-id="b536e-285">Utenti attivi nelle chat delle dimensioni specificate</span><span class="sxs-lookup"><span data-stu-id="b536e-285">Active users in chat rooms of the given size</span></span>

  - <span data-ttu-id="b536e-286">Chat delle dimensioni specificate cui partecipa ogni singole utente</span><span class="sxs-lookup"><span data-stu-id="b536e-286">Chat rooms of the given size that a single user joins</span></span>

<span data-ttu-id="b536e-287">Per ogni chat room, la tabella di pianificazione della capacità precedente specifica il numero di voci di controllo di accesso associate alla chat room, incluse le voci che vengono assegnate direttamente alla chat room.</span><span class="sxs-lookup"><span data-stu-id="b536e-287">For each chat room, the preceding capacity planning table specifies the number of access control entries that are associated with the chat room, including entries that are assigned directly to the chat room.</span></span> <span data-ttu-id="b536e-288">È possibile controllare l'accesso a singole chat tramite elenchi di controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="b536e-288">You can control access to individual chat rooms by using access control lists (ACLs).</span></span> <span data-ttu-id="b536e-289">È inoltre possibile controllare l'accesso a livello di categoria.</span><span class="sxs-lookup"><span data-stu-id="b536e-289">You can also control access at the category level.</span></span> <span data-ttu-id="b536e-290">In un ACL, una singola voce di controllo di accesso può essere un gruppo di utenti, ad esempio un gruppo di sicurezza, una lista di distribuzione o un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="b536e-290">In an ACL, an individual access control entry can be either a user group—for example, a security group, a distribution list, or a single user.</span></span> <span data-ttu-id="b536e-291">È possibile definire voci di controllo di accesso per gestori, relatori e membri delle chat.</span><span class="sxs-lookup"><span data-stu-id="b536e-291">You can define access control entries for chat room managers, presenters, and members.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b536e-292">Nella pianificazione della strategia per la gestione delle chat room, tenere presente che il numero totale di voci di controllo di accesso consentito è 2 milioni.</span><span class="sxs-lookup"><span data-stu-id="b536e-292">In planning your strategy for managing chat rooms, keep in mind that the total number of allowed access control entries is 2 million.</span></span> <span data-ttu-id="b536e-293">Se le voci di controllo di accesso calcolate superano 2 milioni, le prestazioni del server potrebbero peggiorare significativamente.</span><span class="sxs-lookup"><span data-stu-id="b536e-293">If the calculated access control entries exceed 2 million, server performance could degrade significantly.</span></span> <span data-ttu-id="b536e-294">Per evitare questo problema, quando possibile, assicurarsi che le voci di controllo di accesso siano gruppi di utenti anziché singoli.</span><span class="sxs-lookup"><span data-stu-id="b536e-294">To avoid this issue, whenever possible, be sure that your access control entries are user groups instead of individual users.</span></span>



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a><span data-ttu-id="b536e-295">Pianificazione della capacità per la gestione dell'accesso alle chat in base a invito</span><span class="sxs-lookup"><span data-stu-id="b536e-295">Capacity Planning for Managing Chat Room Access by Invitation</span></span>

<span data-ttu-id="b536e-296">È possibile utilizzare la seguente tabella di pianificazione della capacità per comprendere il numero di inviti che il server Chat persistente crea e archivia nel database di Persistent Chat quando è configurato per l'invio di inviti.</span><span class="sxs-lookup"><span data-stu-id="b536e-296">You can use the following capacity planning table to understand the number of invitations that Persistent Chat Server creates and stores in the Persistent Chat database when it is configured to send invitations.</span></span> <span data-ttu-id="b536e-297">È possibile gestire gli inviti per la categoria utilizzando la pagina **Impostazioni categoria chat room** nel pannello di controllo di Lync Server o utilizzando il cmdlet di Windows PowerShell, **set-csPersistentChatCategory**.</span><span class="sxs-lookup"><span data-stu-id="b536e-297">You manage invitations on the Category by using the **Chat Room Category settings** page in the Lync Server Control Panel, or by using the Windows PowerShell cmdlet, **set-csPersistentChatCategory**.</span></span> <span data-ttu-id="b536e-298">È possibile gestire gli inviti in una chat room (in linea con la categoria consentita) utilizzando la pagina **gestione sala** avviata dal client Lync o utilizzando un cmdlet di Windows PowerShell, **set-csPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="b536e-298">You can manage invitations on a chat room (in line with what the category allows) by using the **Room Management** page launched from the Lync client, or by using a Windows PowerShell cmdlet, **set-csPersistentChatRoom**.</span></span>

<span data-ttu-id="b536e-299">I dati di esempio riportati nella tabella seguente presuppongono che, nella pagina **Impostazioni chat room** per il 50% di tutte le chat room, l'opzione **inviti** è impostata su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="b536e-299">The sample data in the following table assumes that, on the **Chat room settings** page for 50 percent of all chat rooms, the **Invitations** option is set to **Yes**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b536e-300">Se il valore calcolato per il numero di inviti generati dal server supera 1 milione, le prestazioni del server potrebbero peggiorare significativamente.</span><span class="sxs-lookup"><span data-stu-id="b536e-300">If the calculated value for the number of invitations that is generated by the server exceeds 1 million, server performance could degrade significantly.</span></span> <span data-ttu-id="b536e-301">Per evitare questo problema, accertarsi di ridurre al minimo il numero di chat configurate per l'invio di inviti o limitare il numero di utenti che possono partecipare alle chat room configurate per l'invio di inviti.</span><span class="sxs-lookup"><span data-stu-id="b536e-301">To avoid this issue, be sure that you minimize the number of chat rooms that are configured to send invitations or restrict the number of users who can join chat rooms that have been configured to send invitations.</span></span>



</div>

### <a name="chat-room-access-by-invitation-sample"></a><span data-ttu-id="b536e-302">Esempio di accesso alle chat in base a invito</span><span class="sxs-lookup"><span data-stu-id="b536e-302">Chat Room Access by Invitation Sample</span></span>

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
<th><span data-ttu-id="b536e-303">Chat di piccole dimensioni</span><span class="sxs-lookup"><span data-stu-id="b536e-303">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="b536e-304">Chat room di medie dimensioni</span><span class="sxs-lookup"><span data-stu-id="b536e-304">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="b536e-305">Chat di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="b536e-305">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="b536e-306">Totale</span><span class="sxs-lookup"><span data-stu-id="b536e-306">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b536e-307">Utenti che possono accedere a chat room</span><span class="sxs-lookup"><span data-stu-id="b536e-307">Users who can access chat room</span></span></p></td>
<td><p><span data-ttu-id="b536e-308">30 per stanza</span><span class="sxs-lookup"><span data-stu-id="b536e-308">30 per room</span></span></p></td>
<td><p><span data-ttu-id="b536e-309">150 per camera</span><span class="sxs-lookup"><span data-stu-id="b536e-309">150 per room</span></span></p></td>
<td><p><span data-ttu-id="b536e-310">16.000 per camera</span><span class="sxs-lookup"><span data-stu-id="b536e-310">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-311">Percentuale di stanze con inviti</span><span class="sxs-lookup"><span data-stu-id="b536e-311">Percentage of rooms that have invitations</span></span></p></td>
<td><p><span data-ttu-id="b536e-312">50%</span><span class="sxs-lookup"><span data-stu-id="b536e-312">50%</span></span></p></td>
<td><p><span data-ttu-id="b536e-313">50%</span><span class="sxs-lookup"><span data-stu-id="b536e-313">50%</span></span></p></td>
<td><p><span data-ttu-id="b536e-314">50%</span><span class="sxs-lookup"><span data-stu-id="b536e-314">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-315">Chat configurate per l'invio di inviti</span><span class="sxs-lookup"><span data-stu-id="b536e-315">Chat rooms configured to send invitations</span></span></p></td>
<td><p><span data-ttu-id="b536e-316"><em>16.000</em></span><span class="sxs-lookup"><span data-stu-id="b536e-316"><em>16,000</em></span></span></p></td>
<td><p><span data-ttu-id="b536e-317"><em>533</em></span><span class="sxs-lookup"><span data-stu-id="b536e-317"><em>533</em></span></span></p></td>
<td><p><span data-ttu-id="b536e-318"><em>5</em></span><span class="sxs-lookup"><span data-stu-id="b536e-318"><em>5</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-319">Utenti che possono accedere alla chat</span><span class="sxs-lookup"><span data-stu-id="b536e-319">Users who can access the chat room</span></span></p></td>
<td><p><span data-ttu-id="b536e-320"><em>60</em></span><span class="sxs-lookup"><span data-stu-id="b536e-320"><em>60</em></span></span></p></td>
<td><p><span data-ttu-id="b536e-321"><em>225</em></span><span class="sxs-lookup"><span data-stu-id="b536e-321"><em>225</em></span></span></p></td>
<td><p><span data-ttu-id="b536e-322"><em>16.000</em></span><span class="sxs-lookup"><span data-stu-id="b536e-322"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-323">Inviti generati dal server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="b536e-323">Invitations generated by Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="b536e-324">960.000</span><span class="sxs-lookup"><span data-stu-id="b536e-324">960,000</span></span></p></td>
<td><p><span data-ttu-id="b536e-325">120.000</span><span class="sxs-lookup"><span data-stu-id="b536e-325">120,000</span></span></p></td>
<td><p><span data-ttu-id="b536e-326">80,000</span><span class="sxs-lookup"><span data-stu-id="b536e-326">80,000</span></span></p></td>
<td><p><span data-ttu-id="b536e-327">1.160.000</span><span class="sxs-lookup"><span data-stu-id="b536e-327">1,160,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-328">Numero massimo consentito di inviti</span><span class="sxs-lookup"><span data-stu-id="b536e-328">Maximum allowable number of invitations</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="b536e-329">2 milioni</span><span class="sxs-lookup"><span data-stu-id="b536e-329">2,000,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-330">Modello 1-iniziare con il numero previsto di messaggi per stanza al giorno</span><span class="sxs-lookup"><span data-stu-id="b536e-330">Model 1 - Start with expected number of messages per room per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-331">Frequenza chat per camera (al giorno)</span><span class="sxs-lookup"><span data-stu-id="b536e-331">Chat Rate Per Room (per day)</span></span></p></td>
<td><p><span data-ttu-id="b536e-332">50</span><span class="sxs-lookup"><span data-stu-id="b536e-332">50</span></span></p></td>
<td><p><span data-ttu-id="b536e-333">500</span><span class="sxs-lookup"><span data-stu-id="b536e-333">500</span></span></p></td>
<td><p><span data-ttu-id="b536e-334">100</span><span class="sxs-lookup"><span data-stu-id="b536e-334">100</span></span></p></td>
<td><p><span data-ttu-id="b536e-335">650</span><span class="sxs-lookup"><span data-stu-id="b536e-335">650</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-336">Velocità di chat (al secondo) in tutte le sale</span><span class="sxs-lookup"><span data-stu-id="b536e-336">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="b536e-337">55,56</span><span class="sxs-lookup"><span data-stu-id="b536e-337">55.56</span></span></p></td>
<td><p><span data-ttu-id="b536e-338">18,52</span><span class="sxs-lookup"><span data-stu-id="b536e-338">18.52</span></span></p></td>
<td><p><span data-ttu-id="b536e-339">0,03</span><span class="sxs-lookup"><span data-stu-id="b536e-339">0.03</span></span></p></td>
<td><p><span data-ttu-id="b536e-340">74</span><span class="sxs-lookup"><span data-stu-id="b536e-340">74</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-341">Modello 2-iniziare con il numero di messaggi inviati per utente al giorno</span><span class="sxs-lookup"><span data-stu-id="b536e-341">Model 2 - Start with number of messages posted per user per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-342">Frequenza di chat per utente al giorno</span><span class="sxs-lookup"><span data-stu-id="b536e-342">Chat rate per user per day</span></span></p></td>
<td><p><span data-ttu-id="b536e-343">15 </span><span class="sxs-lookup"><span data-stu-id="b536e-343">15</span></span></p></td>
<td><p><span data-ttu-id="b536e-344">5 </span><span class="sxs-lookup"><span data-stu-id="b536e-344">5</span></span></p></td>
<td><p><span data-ttu-id="b536e-345">0,1</span><span class="sxs-lookup"><span data-stu-id="b536e-345">0.1</span></span></p></td>
<td><p><span data-ttu-id="b536e-346">20</span><span class="sxs-lookup"><span data-stu-id="b536e-346">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-347">Frequenza chat per camera (al giorno)</span><span class="sxs-lookup"><span data-stu-id="b536e-347">Chat rate per room (per day)</span></span></p></td>
<td><p><span data-ttu-id="b536e-348">38</span><span class="sxs-lookup"><span data-stu-id="b536e-348">38</span></span></p></td>
<td><p><span data-ttu-id="b536e-349">375</span><span class="sxs-lookup"><span data-stu-id="b536e-349">375</span></span></p></td>
<td><p><span data-ttu-id="b536e-350">800</span><span class="sxs-lookup"><span data-stu-id="b536e-350">800</span></span></p></td>
<td><p><span data-ttu-id="b536e-351">1.213</span><span class="sxs-lookup"><span data-stu-id="b536e-351">1,213</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-352">Velocità di chat (al secondo) in tutte le sale</span><span class="sxs-lookup"><span data-stu-id="b536e-352">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="b536e-353">41,67</span><span class="sxs-lookup"><span data-stu-id="b536e-353">41.67</span></span></p></td>
<td><p><span data-ttu-id="b536e-354">13,89</span><span class="sxs-lookup"><span data-stu-id="b536e-354">13.89</span></span></p></td>
<td><p><span data-ttu-id="b536e-355">0,28</span><span class="sxs-lookup"><span data-stu-id="b536e-355">0.28</span></span></p></td>
<td><p><span data-ttu-id="b536e-356">56</span><span class="sxs-lookup"><span data-stu-id="b536e-356">56</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="b536e-357">Modello utente per le prestazioni del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="b536e-357">Persistent Chat Server Performance User Model</span></span>

<span data-ttu-id="b536e-358">Nella tabella seguente viene descritto il modello utente per il server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="b536e-358">The following table describes the user model for Persistent Chat Server.</span></span> <span data-ttu-id="b536e-359">Fornisce la base per i requisiti di pianificazione della capacità e rappresenta un'organizzazione tipica con 80.000 utenti simultanei su quattro server.</span><span class="sxs-lookup"><span data-stu-id="b536e-359">It provides the basis for the capacity planning requirements and represents a typical organization with 80,000 concurrent users on four servers.</span></span>

### <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="b536e-360">Modello utente per le prestazioni del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="b536e-360">Persistent Chat Server Performance User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b536e-361">Numero di utenti attivi connessi</span><span class="sxs-lookup"><span data-stu-id="b536e-361">Number of active users connected</span></span></p></td>
<td><p><span data-ttu-id="b536e-362">80,000</span><span class="sxs-lookup"><span data-stu-id="b536e-362">80,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-363">Numero di istanze del servizio del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="b536e-363">Number of Persistent Chat Server service instances</span></span></p></td>
<td><p><span data-ttu-id="b536e-364">4 </span><span class="sxs-lookup"><span data-stu-id="b536e-364">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-365">Numero di utenti di chat di piccole dimensioni</span><span class="sxs-lookup"><span data-stu-id="b536e-365">Size of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="b536e-366">30 utenti</span><span class="sxs-lookup"><span data-stu-id="b536e-366">30 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-367">Numero di utenti di chat di medie dimensioni</span><span class="sxs-lookup"><span data-stu-id="b536e-367">Size of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="b536e-368">150 utenti</span><span class="sxs-lookup"><span data-stu-id="b536e-368">150 users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-369">Numero di utenti di chat di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="b536e-369">Size of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="b536e-370">16.000 utenti</span><span class="sxs-lookup"><span data-stu-id="b536e-370">16,000 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-371">Numero totale di chat</span><span class="sxs-lookup"><span data-stu-id="b536e-371">Total number of chat rooms</span></span></p></td>
<td><p><span data-ttu-id="b536e-372">33.077</span><span class="sxs-lookup"><span data-stu-id="b536e-372">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-373">Numero di chat di piccole dimensioni</span><span class="sxs-lookup"><span data-stu-id="b536e-373">Number of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="b536e-374">32.000</span><span class="sxs-lookup"><span data-stu-id="b536e-374">32,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-375">Numero di chat di medie dimensioni</span><span class="sxs-lookup"><span data-stu-id="b536e-375">Number of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="b536e-376">1.067</span><span class="sxs-lookup"><span data-stu-id="b536e-376">1,067</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-377">Numero di chat di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="b536e-377">Number of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="b536e-378">10  </span><span class="sxs-lookup"><span data-stu-id="b536e-378">10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-379">Numero totale di chat per utente</span><span class="sxs-lookup"><span data-stu-id="b536e-379">Total number of chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="b536e-380">16 </span><span class="sxs-lookup"><span data-stu-id="b536e-380">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-381">Numero di chat di piccole dimensioni per utente</span><span class="sxs-lookup"><span data-stu-id="b536e-381">Number of small chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="b536e-382">12 </span><span class="sxs-lookup"><span data-stu-id="b536e-382">12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-383">Numero di chat di medie dimensioni per utente</span><span class="sxs-lookup"><span data-stu-id="b536e-383">Number of medium chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="b536e-384">2</span><span class="sxs-lookup"><span data-stu-id="b536e-384">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-385">Numero di chat di grandi dimensioni per utente</span><span class="sxs-lookup"><span data-stu-id="b536e-385">Number of large chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="b536e-386">2</span><span class="sxs-lookup"><span data-stu-id="b536e-386">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-387">Numero di sale Unite per utente</span><span class="sxs-lookup"><span data-stu-id="b536e-387">Number of rooms joined per user</span></span></p></td>
<td><p><span data-ttu-id="b536e-388">24</span><span class="sxs-lookup"><span data-stu-id="b536e-388">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-389">Frequenza di partecipazione di punta</span><span class="sxs-lookup"><span data-stu-id="b536e-389">Peak join rate</span></span></p></td>
<td><p><span data-ttu-id="b536e-390">10/secondo</span><span class="sxs-lookup"><span data-stu-id="b536e-390">10/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-391">Frequenza di chat totale</span><span class="sxs-lookup"><span data-stu-id="b536e-391">Total chat rate</span></span></p></td>
<td><p><span data-ttu-id="b536e-392">24/secondo</span><span class="sxs-lookup"><span data-stu-id="b536e-392">24/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-393">Frequenza di chat per chat di piccole dimensioni</span><span class="sxs-lookup"><span data-stu-id="b536e-393">Chat rate for small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="b536e-394">22.22/secondo</span><span class="sxs-lookup"><span data-stu-id="b536e-394">22.22/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-395">Frequenza di chat per chat di medie dimensioni</span><span class="sxs-lookup"><span data-stu-id="b536e-395">Chat rate for medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="b536e-396">1.67/secondo</span><span class="sxs-lookup"><span data-stu-id="b536e-396">1.67/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-397">Frequenza di chat per chat di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="b536e-397">Chat rate for large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="b536e-398">~ 0.15/Second</span><span class="sxs-lookup"><span data-stu-id="b536e-398">~0.15/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-399">Percentuale di chat configurate per l'invio di inviti</span><span class="sxs-lookup"><span data-stu-id="b536e-399">Percentage of chat rooms configured for invitations</span></span></p></td>
<td><p><span data-ttu-id="b536e-400">50%</span><span class="sxs-lookup"><span data-stu-id="b536e-400">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-401">Percentuale di appartenenza diretta</span><span class="sxs-lookup"><span data-stu-id="b536e-401">Percentage of direct memberships</span></span></p></td>
<td><p><span data-ttu-id="b536e-402">50%</span><span class="sxs-lookup"><span data-stu-id="b536e-402">50%</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-403">Percentuale di appartenenza a gruppi</span><span class="sxs-lookup"><span data-stu-id="b536e-403">Percentage of group memberships</span></span></p></td>
<td><p><span data-ttu-id="b536e-404">50%</span><span class="sxs-lookup"><span data-stu-id="b536e-404">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-405">Numero medio di affiliazioni degli antenati in servizi di dominio Active Directory</span><span class="sxs-lookup"><span data-stu-id="b536e-405">Average number of ancestor affiliations in Active Directory Domain Services</span></span></p></td>
<td><p><span data-ttu-id="b536e-406">100 - 200</span><span class="sxs-lookup"><span data-stu-id="b536e-406">100 - 200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-407">Numero di contatti sottoscritti per utente</span><span class="sxs-lookup"><span data-stu-id="b536e-407">Number of subscribed contacts per user</span></span></p></td>
<td><p><span data-ttu-id="b536e-408">80</span><span class="sxs-lookup"><span data-stu-id="b536e-408">80</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-409">Numero medio di endpoint per utente</span><span class="sxs-lookup"><span data-stu-id="b536e-409">Average number of endpoints per user</span></span></p></td>
<td><p><span data-ttu-id="b536e-410">1,5</span><span class="sxs-lookup"><span data-stu-id="b536e-410">1.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-411">Numero medio di chat room visibili per endpoint</span><span class="sxs-lookup"><span data-stu-id="b536e-411">Average number of visible chat rooms per endpoint</span></span></p></td>
<td><p><span data-ttu-id="b536e-412">1,5</span><span class="sxs-lookup"><span data-stu-id="b536e-412">1.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-413">Numero medio di chat room visibili per utente</span><span class="sxs-lookup"><span data-stu-id="b536e-413">Average number of visible chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="b536e-414">2,25 (50% per 1 sala e 50% per 2 sale); Fino a 6 sale aperte, una per ogni monitor</span><span class="sxs-lookup"><span data-stu-id="b536e-414">2.25 (50% for 1 room and 50% for 2 rooms); Up to 6 rooms open, one per monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-415">Numero di partecipanti sottoposti a polling per intervallo</span><span class="sxs-lookup"><span data-stu-id="b536e-415">Number of participants polled per interval</span></span></p></td>
<td><p><span data-ttu-id="b536e-416">25 per chat room visibile</span><span class="sxs-lookup"><span data-stu-id="b536e-416">25 per visible chat room</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-417">Durata dell'intervallo di polling</span><span class="sxs-lookup"><span data-stu-id="b536e-417">Length of polling interval</span></span></p></td>
<td><p><span data-ttu-id="b536e-418">5 minuti</span><span class="sxs-lookup"><span data-stu-id="b536e-418">5 minutes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-419">Numero di partecipanti sottoposti a polling al secondo</span><span class="sxs-lookup"><span data-stu-id="b536e-419">Number of participants polled per second</span></span></p></td>
<td><p><span data-ttu-id="b536e-420">15.000</span><span class="sxs-lookup"><span data-stu-id="b536e-420">15,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b536e-421">Numero di modifiche delle informazioni sulla presenza all'ora per utente</span><span class="sxs-lookup"><span data-stu-id="b536e-421">Number of presence changes per hour per user</span></span></p></td>
<td><p><span data-ttu-id="b536e-422">6 </span><span class="sxs-lookup"><span data-stu-id="b536e-422">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b536e-423">Numero di modifiche delle informazioni sulla presenza al secondo</span><span class="sxs-lookup"><span data-stu-id="b536e-423">Number of presence changes per second</span></span></p></td>
<td><p><span data-ttu-id="b536e-424">133,33</span><span class="sxs-lookup"><span data-stu-id="b536e-424">133.33</span></span></p></td>
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

