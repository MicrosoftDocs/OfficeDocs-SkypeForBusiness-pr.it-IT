---
title: 'Lync Server 2013: porte e protocolli per i server interni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Ports and protocols for internal servers
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398833(v=OCS.15)
ms:contentKeyID: 48185402
ms.date: 04/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 026843216e433ebea120384209ed90f38be3437b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979692"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="d86a1-102">Porte e protocolli per i server interni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d86a1-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d86a1-103">_**Argomento Ultima modifica:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="d86a1-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="d86a1-104">Questa sezione riepiloga le porte e i protocolli usati dai server, i bilanciatori di carico e i client in una distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d86a1-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d86a1-105">I client di Lync e Communicator quando sono coinvolti in una comunicazione uno-a-uno, vengono spesso definiti peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="d86a1-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="d86a1-106">Tecnicamente, i due client comunicano in una conversazione uno-a-uno, con l'unità di controllo multipunto di messaggistica istantanea (IMMCU) al centro.</span><span class="sxs-lookup"><span data-stu-id="d86a1-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="d86a1-107">IMMCU è un componente del server front-end.</span><span class="sxs-lookup"><span data-stu-id="d86a1-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="d86a1-108">L'immissione di IMMCU nel flusso di lavoro di comunicazione richiesto consente la registrazione dei dettagli delle chiamate e altre caratteristiche abilitate dal server front-end.</span><span class="sxs-lookup"><span data-stu-id="d86a1-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="d86a1-109">La comunicazione è da una porta di origine dinamica nel client alla porta del server front-end TLS/TCP/5061 (presupponendo l'uso della sicurezza del livello di trasporto consigliato).</span><span class="sxs-lookup"><span data-stu-id="d86a1-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="d86a1-110">In base alla progettazione, la comunicazione peer-to-peer (così come la messaggistica istantanea a più parti) è possibile solo quando Lync Server e IMMCU è attivo e disponibile.</span><span class="sxs-lookup"><span data-stu-id="d86a1-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="d86a1-111">Dettagli sulla porta e sul protocollo</span><span class="sxs-lookup"><span data-stu-id="d86a1-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d86a1-112">Windows Firewall deve essere in corso prima di avviare i servizi Lync Server in un server, perché in questo caso Lync Server apre le porte necessarie nel firewall.</span><span class="sxs-lookup"><span data-stu-id="d86a1-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="d86a1-113">Per informazioni dettagliate sulla configurazione del firewall per i componenti perimetrali, vedere [determinare i requisiti per il firewall e la porta a/V esterni per Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d86a1-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="d86a1-114">La tabella seguente elenca le porte che devono essere aperte in ogni ruolo del server interno.</span><span class="sxs-lookup"><span data-stu-id="d86a1-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="d86a1-115">Porte del server obbligatorie (per ruolo del server)</span><span class="sxs-lookup"><span data-stu-id="d86a1-115">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="d86a1-116">Ruolo del server</span><span class="sxs-lookup"><span data-stu-id="d86a1-116">Server role</span></span></th>
<th><span data-ttu-id="d86a1-117">Nome servizio</span><span class="sxs-lookup"><span data-stu-id="d86a1-117">Service name</span></span></th>
<th><span data-ttu-id="d86a1-118">Porta</span><span class="sxs-lookup"><span data-stu-id="d86a1-118">Port</span></span></th>
<th><span data-ttu-id="d86a1-119">Protocollo</span><span class="sxs-lookup"><span data-stu-id="d86a1-119">Protocol</span></span></th>
<th><span data-ttu-id="d86a1-120">Note</span><span class="sxs-lookup"><span data-stu-id="d86a1-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-121">Tutti i server</span><span class="sxs-lookup"><span data-stu-id="d86a1-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-122">Browser SQL</span><span class="sxs-lookup"><span data-stu-id="d86a1-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="d86a1-123">1434</span><span class="sxs-lookup"><span data-stu-id="d86a1-123">1434</span></span></p></td>
<td><p><span data-ttu-id="d86a1-124">UDP</span><span class="sxs-lookup"><span data-stu-id="d86a1-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-125">Browser SQL per la copia replicata locale del database di Central Management store.</span><span class="sxs-lookup"><span data-stu-id="d86a1-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-126">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-127">Servizio front-end di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-128">5060</span><span class="sxs-lookup"><span data-stu-id="d86a1-128">5060</span></span></p></td>
<td><p><span data-ttu-id="d86a1-129">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-130">È possibile usare facoltativamente i server standard e i server front-end per le route statiche a servizi attendibili, ad esempio i server di controllo delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="d86a1-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-131">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-132">Servizio front-end di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-133">5061</span><span class="sxs-lookup"><span data-stu-id="d86a1-133">5061</span></span></p></td>
<td><p><span data-ttu-id="d86a1-134">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="d86a1-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="d86a1-135">Usato dai server standard e dai pool Front-end per tutte le comunicazioni SIP interne tra server (MTLS), per le comunicazioni SIP tra server e client (TLS) e per le comunicazioni SIP tra server front-end e Mediation Server (MTLS).</span><span class="sxs-lookup"><span data-stu-id="d86a1-135">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS).</span></span> <span data-ttu-id="d86a1-136">Usato anche per le comunicazioni con il server di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="d86a1-136">Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-137">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-138">Servizio front-end di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-139">444</span><span class="sxs-lookup"><span data-stu-id="d86a1-139">444</span></span></p></td>
<td><p><span data-ttu-id="d86a1-140">HTTPS</span><span class="sxs-lookup"><span data-stu-id="d86a1-140">HTTPS</span></span></p>
<p><span data-ttu-id="d86a1-141">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-142">Usato per la comunicazione HTTPS tra lo stato attiva (il componente Lync Server che gestisce lo stato conferenza) e i singoli server.</span><span class="sxs-lookup"><span data-stu-id="d86a1-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="d86a1-143">Questa porta viene usata anche per la comunicazione TCP tra gli elettrodomestici Survivable Branch e i server front-end.</span><span class="sxs-lookup"><span data-stu-id="d86a1-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-144">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-145">Servizio front-end di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-146">135</span><span class="sxs-lookup"><span data-stu-id="d86a1-146">135</span></span></p></td>
<td><p><span data-ttu-id="d86a1-147">DCOM e chiamata di procedura remota (RPC)</span><span class="sxs-lookup"><span data-stu-id="d86a1-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="d86a1-148">Usato per operazioni basate su DCOM come lo spostamento di utenti, la sincronizzazione di User Replicator e la sincronizzazione della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="d86a1-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-149">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-150">Servizio di conferenza telefonica di messaggistica istantanea di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-151">5062</span><span class="sxs-lookup"><span data-stu-id="d86a1-151">5062</span></span></p></td>
<td><p><span data-ttu-id="d86a1-152">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-153">Usato per le richieste SIP in arrivo per le conferenze di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="d86a1-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-154">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-155">Servizio di conferenza Web di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-156">8057</span><span class="sxs-lookup"><span data-stu-id="d86a1-156">8057</span></span></p></td>
<td><p><span data-ttu-id="d86a1-157">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="d86a1-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="d86a1-158">Usato per ascoltare le connessioni PSOM (Persistent Shared Object Model) dal client.</span><span class="sxs-lookup"><span data-stu-id="d86a1-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-159">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-160">Servizio compatibilità con Lync Server Web Conferencing</span><span class="sxs-lookup"><span data-stu-id="d86a1-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-161">8058</span><span class="sxs-lookup"><span data-stu-id="d86a1-161">8058</span></span></p></td>
<td><p><span data-ttu-id="d86a1-162">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="d86a1-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="d86a1-163">Consente di ascoltare le connessioni PSOM (Persistent Shared Object Model) dal client Live Meeting e dalle versioni precedenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d86a1-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-164">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-165">Servizio di conferenza audio/video di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-166">5063</span><span class="sxs-lookup"><span data-stu-id="d86a1-166">5063</span></span></p></td>
<td><p><span data-ttu-id="d86a1-167">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-168">Usato per le richieste SIP in arrivo per le conferenze audio/video (A/V).</span><span class="sxs-lookup"><span data-stu-id="d86a1-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-169">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-170">Servizio di conferenza audio/video di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="d86a1-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="d86a1-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="d86a1-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-173">Intervallo di porte multimediali usato per i servizi di conferenza video.</span><span class="sxs-lookup"><span data-stu-id="d86a1-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-174">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-175">Servizio compatibilità Web di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-176">80</span><span class="sxs-lookup"><span data-stu-id="d86a1-176">80</span></span></p></td>
<td><p><span data-ttu-id="d86a1-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="d86a1-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-178">Usato per la comunicazione dai server front-end agli FQDN della Web farm (gli URL usati da IIS Web Components) quando non viene usato HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d86a1-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-179">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-180">Servizio compatibilità Web di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-181">443</span><span class="sxs-lookup"><span data-stu-id="d86a1-181">443</span></span></p></td>
<td><p><span data-ttu-id="d86a1-182">HTTPS</span><span class="sxs-lookup"><span data-stu-id="d86a1-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="d86a1-183">Usato per la comunicazione dai server front-end agli FQDN della Web farm (gli URL usati da IIS Web Components).</span><span class="sxs-lookup"><span data-stu-id="d86a1-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-184">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-185">Servizio compatibilità Web di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-186">8080</span><span class="sxs-lookup"><span data-stu-id="d86a1-186">8080</span></span></p></td>
<td><p><span data-ttu-id="d86a1-187">TCP e HTTP</span><span class="sxs-lookup"><span data-stu-id="d86a1-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-188">Usato dai componenti Web per l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="d86a1-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-189">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-190">Componente server Web</span><span class="sxs-lookup"><span data-stu-id="d86a1-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="d86a1-191">4443</span><span class="sxs-lookup"><span data-stu-id="d86a1-191">4443</span></span></p></td>
<td><p><span data-ttu-id="d86a1-192">HTTPS</span><span class="sxs-lookup"><span data-stu-id="d86a1-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="d86a1-193">HTTPS (da proxy inverso) e le comunicazioni inter-pool HTTPS front-end per l'accesso all'individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="d86a1-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-194">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-195">Componente server Web</span><span class="sxs-lookup"><span data-stu-id="d86a1-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="d86a1-196">8060</span><span class="sxs-lookup"><span data-stu-id="d86a1-196">8060</span></span></p></td>
<td><p><span data-ttu-id="d86a1-197">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="d86a1-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-198">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-199">Componente server Web</span><span class="sxs-lookup"><span data-stu-id="d86a1-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="d86a1-200">8061</span><span class="sxs-lookup"><span data-stu-id="d86a1-200">8061</span></span></p></td>
<td><p><span data-ttu-id="d86a1-201">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="d86a1-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-202">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-203">Componente servizi mobili</span><span class="sxs-lookup"><span data-stu-id="d86a1-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="d86a1-204">5086</span><span class="sxs-lookup"><span data-stu-id="d86a1-204">5086</span></span></p></td>
<td><p><span data-ttu-id="d86a1-205">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="d86a1-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="d86a1-206">Porta SIP usata dai processi interni dei servizi mobili</span><span class="sxs-lookup"><span data-stu-id="d86a1-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-207">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-208">Componente servizi mobili</span><span class="sxs-lookup"><span data-stu-id="d86a1-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="d86a1-209">5087</span><span class="sxs-lookup"><span data-stu-id="d86a1-209">5087</span></span></p></td>
<td><p><span data-ttu-id="d86a1-210">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="d86a1-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="d86a1-211">Porta SIP usata dai processi interni dei servizi mobili</span><span class="sxs-lookup"><span data-stu-id="d86a1-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-212">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-213">Componente servizi mobili</span><span class="sxs-lookup"><span data-stu-id="d86a1-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="d86a1-214">443</span><span class="sxs-lookup"><span data-stu-id="d86a1-214">443</span></span></p></td>
<td><p><span data-ttu-id="d86a1-215">HTTPS</span><span class="sxs-lookup"><span data-stu-id="d86a1-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-216">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-217">Servizio Assistente conferenza di Lync Server (servizi di conferenza telefonica con accesso esterno)</span><span class="sxs-lookup"><span data-stu-id="d86a1-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="d86a1-218">5064</span><span class="sxs-lookup"><span data-stu-id="d86a1-218">5064</span></span></p></td>
<td><p><span data-ttu-id="d86a1-219">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-220">Usato per le richieste SIP in arrivo per i servizi di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="d86a1-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-221">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-222">Servizio Assistente conferenza di Lync Server (servizi di conferenza telefonica con accesso esterno)</span><span class="sxs-lookup"><span data-stu-id="d86a1-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="d86a1-223">5072</span><span class="sxs-lookup"><span data-stu-id="d86a1-223">5072</span></span></p></td>
<td><p><span data-ttu-id="d86a1-224">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-225">Usato per le richieste SIP in arrivo per l'operatore (servizi di conferenza telefonica con accesso esterno).</span><span class="sxs-lookup"><span data-stu-id="d86a1-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-226">Server front-end che eseguono anche un Mediation Server collocato</span><span class="sxs-lookup"><span data-stu-id="d86a1-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="d86a1-227">Servizio di mediazione Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-228">5070</span><span class="sxs-lookup"><span data-stu-id="d86a1-228">5070</span></span></p></td>
<td><p><span data-ttu-id="d86a1-229">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-230">Usato dal Mediation Server per le richieste in arrivo dal server front-end al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="d86a1-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-231">Server front-end che eseguono anche un Mediation Server collocato</span><span class="sxs-lookup"><span data-stu-id="d86a1-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="d86a1-232">Servizio di mediazione Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-233">5067</span><span class="sxs-lookup"><span data-stu-id="d86a1-233">5067</span></span></p></td>
<td><p><span data-ttu-id="d86a1-234">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="d86a1-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="d86a1-235">Usato per le richieste SIP in arrivo dal gateway PSTN al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="d86a1-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-236">Server front-end che eseguono anche un Mediation Server collocato</span><span class="sxs-lookup"><span data-stu-id="d86a1-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="d86a1-237">Servizio di mediazione Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-238">5068</span><span class="sxs-lookup"><span data-stu-id="d86a1-238">5068</span></span></p></td>
<td><p><span data-ttu-id="d86a1-239">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-240">Usato per le richieste SIP in arrivo dal gateway PSTN al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="d86a1-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-241">Server front-end che eseguono anche un Mediation Server collocato</span><span class="sxs-lookup"><span data-stu-id="d86a1-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="d86a1-242">Servizio di mediazione Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-243">5081</span><span class="sxs-lookup"><span data-stu-id="d86a1-243">5081</span></span></p></td>
<td><p><span data-ttu-id="d86a1-244">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-245">Usato per le richieste SIP in uscita dal server Mediation al gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="d86a1-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-246">Server front-end che eseguono anche un Mediation Server collocato</span><span class="sxs-lookup"><span data-stu-id="d86a1-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="d86a1-247">Servizio di mediazione Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-248">5082</span><span class="sxs-lookup"><span data-stu-id="d86a1-248">5082</span></span></p></td>
<td><p><span data-ttu-id="d86a1-249">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="d86a1-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="d86a1-250">Usato per le richieste SIP in uscita dal server Mediation al gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="d86a1-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-251">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-252">Servizio di condivisione applicazioni di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-253">5065</span><span class="sxs-lookup"><span data-stu-id="d86a1-253">5065</span></span></p></td>
<td><p><span data-ttu-id="d86a1-254">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-255">Usato per le richieste di ascolto SIP in arrivo per la condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="d86a1-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-256">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-257">Servizio di condivisione applicazioni di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="d86a1-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="d86a1-259">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-260">Intervallo di porte multimediali usato per la condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="d86a1-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-261">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-262">Servizio di annuncio di servizi di conferenza di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-263">5073</span><span class="sxs-lookup"><span data-stu-id="d86a1-263">5073</span></span></p></td>
<td><p><span data-ttu-id="d86a1-264">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-265">Usato per le richieste SIP in arrivo per il servizio di annuncio di conferenza di Lync Server (ovvero per i servizi di conferenza telefonica con accesso esterno).</span><span class="sxs-lookup"><span data-stu-id="d86a1-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-266">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-267">Servizio di parcheggio delle chiamate di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-268">5075</span><span class="sxs-lookup"><span data-stu-id="d86a1-268">5075</span></span></p></td>
<td><p><span data-ttu-id="d86a1-269">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-270">Usato per le richieste SIP in arrivo per l'applicazione Call Park.</span><span class="sxs-lookup"><span data-stu-id="d86a1-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-271">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-272">Servizio test audio di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-273">5076</span><span class="sxs-lookup"><span data-stu-id="d86a1-273">5076</span></span></p></td>
<td><p><span data-ttu-id="d86a1-274">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-275">Usato per le richieste SIP in arrivo per il servizio di test audio.</span><span class="sxs-lookup"><span data-stu-id="d86a1-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-276">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-277">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="d86a1-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="d86a1-278">5066</span><span class="sxs-lookup"><span data-stu-id="d86a1-278">5066</span></span></p></td>
<td><p><span data-ttu-id="d86a1-279">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-280">Usato per il gateway avanzato 9-1-1 (E9-1-1) in uscita.</span><span class="sxs-lookup"><span data-stu-id="d86a1-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-281">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-282">Servizio Response Group di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-283">5071</span><span class="sxs-lookup"><span data-stu-id="d86a1-283">5071</span></span></p></td>
<td><p><span data-ttu-id="d86a1-284">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-285">Usato per le richieste SIP in arrivo per l'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="d86a1-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-286">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-287">Servizio Response Group di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-288">8404</span><span class="sxs-lookup"><span data-stu-id="d86a1-288">8404</span></span></p></td>
<td><p><span data-ttu-id="d86a1-289">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="d86a1-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="d86a1-290">Usato per le richieste SIP in arrivo per l'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="d86a1-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-291">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-292">Servizio criteri di larghezza di banda di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-293">5080</span><span class="sxs-lookup"><span data-stu-id="d86a1-293">5080</span></span></p></td>
<td><p><span data-ttu-id="d86a1-294">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-295">Usato per il controllo dell'ammissione tramite chiamata tramite il servizio criteri di larghezza di banda per il traffico a/V Edge TURN.</span><span class="sxs-lookup"><span data-stu-id="d86a1-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-296">Server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-297">Servizio criteri di larghezza di banda di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-298">448</span><span class="sxs-lookup"><span data-stu-id="d86a1-298">448</span></span></p></td>
<td><p><span data-ttu-id="d86a1-299">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-300">Usato per il controllo dell'ammissione tramite chiamata dal servizio criteri di larghezza di banda di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d86a1-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-301">Server front-end in cui risiede l'Central Management store</span><span class="sxs-lookup"><span data-stu-id="d86a1-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="d86a1-302">Servizio agente Master Replicator di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-303">445</span><span class="sxs-lookup"><span data-stu-id="d86a1-303">445</span></span></p></td>
<td><p><span data-ttu-id="d86a1-304">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-305">Usato per spingere i dati di configurazione dall'Central Management store ai server che usano Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d86a1-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-306">Tutti i server</span><span class="sxs-lookup"><span data-stu-id="d86a1-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-307">Browser SQL</span><span class="sxs-lookup"><span data-stu-id="d86a1-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="d86a1-308">1434</span><span class="sxs-lookup"><span data-stu-id="d86a1-308">1434</span></span></p></td>
<td><p><span data-ttu-id="d86a1-309">UDP</span><span class="sxs-lookup"><span data-stu-id="d86a1-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-310">Browser SQL per la copia replicata locale dei dati di Central Management store nell'istanza di SQL Server locale</span><span class="sxs-lookup"><span data-stu-id="d86a1-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-311">Tutti i server interni</span><span class="sxs-lookup"><span data-stu-id="d86a1-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-312">Vari</span><span class="sxs-lookup"><span data-stu-id="d86a1-312">Various</span></span></p></td>
<td><p><span data-ttu-id="d86a1-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="d86a1-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="d86a1-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="d86a1-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-315">Intervallo di porte multimediali usato per i servizi di audioconferenza in tutti i server interni.</span><span class="sxs-lookup"><span data-stu-id="d86a1-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="d86a1-316">Usato da tutti i server che interrompono l'audio: Front End Server (per il servizio di conferenza telefonica di Lync Server, servizio di annuncio di Lync Server e servizi di conferenza audio/video di Lync Server) e Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="d86a1-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-317">Server di Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="d86a1-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d86a1-318">443</span><span class="sxs-lookup"><span data-stu-id="d86a1-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d86a1-319">Usato da Lync Server 2013 per connettersi al server di Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="d86a1-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-320">Consiglio</span><span class="sxs-lookup"><span data-stu-id="d86a1-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="d86a1-321">Servizio front-end di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-322">5060</span><span class="sxs-lookup"><span data-stu-id="d86a1-322">5060</span></span></p></td>
<td><p><span data-ttu-id="d86a1-323">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-324">Facoltativamente usato per le route statiche a servizi attendibili, ad esempio i server di controllo delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="d86a1-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-325">Consiglio</span><span class="sxs-lookup"><span data-stu-id="d86a1-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="d86a1-326">Servizio front-end di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-327">444</span><span class="sxs-lookup"><span data-stu-id="d86a1-327">444</span></span></p></td>
<td><p><span data-ttu-id="d86a1-328">HTTPS</span><span class="sxs-lookup"><span data-stu-id="d86a1-328">HTTPS</span></span></p>
<p><span data-ttu-id="d86a1-329">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-330">Comunicazioni tra server tra front-end e Director.</span><span class="sxs-lookup"><span data-stu-id="d86a1-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="d86a1-331">Inoltre, la pubblicazione del certificato client (per i server front-end) o la convalida se il certificato client è già stato pubblicato.</span><span class="sxs-lookup"><span data-stu-id="d86a1-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-332">Consiglio</span><span class="sxs-lookup"><span data-stu-id="d86a1-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="d86a1-333">Servizio compatibilità Web di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-334">80</span><span class="sxs-lookup"><span data-stu-id="d86a1-334">80</span></span></p></td>
<td><p><span data-ttu-id="d86a1-335">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-336">Usato per la comunicazione iniziale da Directors agli FQDN della Web farm (gli URL usati da IIS Web Components).</span><span class="sxs-lookup"><span data-stu-id="d86a1-336">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span> <span data-ttu-id="d86a1-337">In funzionamento normale si passa al traffico HTTPS usando la porta 443 e il protocollo TCP.</span><span class="sxs-lookup"><span data-stu-id="d86a1-337">In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-338">Consiglio</span><span class="sxs-lookup"><span data-stu-id="d86a1-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="d86a1-339">Servizio compatibilità Web di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-340">443</span><span class="sxs-lookup"><span data-stu-id="d86a1-340">443</span></span></p></td>
<td><p><span data-ttu-id="d86a1-341">HTTPS</span><span class="sxs-lookup"><span data-stu-id="d86a1-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="d86a1-342">Usato per la comunicazione da Directors agli FQDN della Web farm (gli URL usati da IIS Web Components).</span><span class="sxs-lookup"><span data-stu-id="d86a1-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-343">Consiglio</span><span class="sxs-lookup"><span data-stu-id="d86a1-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="d86a1-344">Servizio front-end di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-345">5061</span><span class="sxs-lookup"><span data-stu-id="d86a1-345">5061</span></span></p></td>
<td><p><span data-ttu-id="d86a1-346">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-347">Usato per le comunicazioni interne tra i server e per le connessioni client.</span><span class="sxs-lookup"><span data-stu-id="d86a1-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-348">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-349">Servizio di mediazione Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-350">5070</span><span class="sxs-lookup"><span data-stu-id="d86a1-350">5070</span></span></p></td>
<td><p><span data-ttu-id="d86a1-351">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-352">Usato dal Mediation Server per le richieste in arrivo dal server front-end.</span><span class="sxs-lookup"><span data-stu-id="d86a1-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-353">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-354">Servizio di mediazione Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-355">5067</span><span class="sxs-lookup"><span data-stu-id="d86a1-355">5067</span></span></p></td>
<td><p><span data-ttu-id="d86a1-356">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="d86a1-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="d86a1-357">Usato per le richieste SIP in arrivo dal gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="d86a1-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-358">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-359">Servizio di mediazione Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-360">5068</span><span class="sxs-lookup"><span data-stu-id="d86a1-360">5068</span></span></p></td>
<td><p><span data-ttu-id="d86a1-361">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-362">Usato per le richieste SIP in arrivo dal gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="d86a1-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-363">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="d86a1-364">Servizio di mediazione Lync Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-365">5070</span><span class="sxs-lookup"><span data-stu-id="d86a1-365">5070</span></span></p></td>
<td><p><span data-ttu-id="d86a1-366">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="d86a1-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="d86a1-367">Usato per le richieste SIP provenienti dai server front-end.</span><span class="sxs-lookup"><span data-stu-id="d86a1-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-368">Server front end di chat persistente</span><span class="sxs-lookup"><span data-stu-id="d86a1-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="d86a1-369">SIP chat persistente</span><span class="sxs-lookup"><span data-stu-id="d86a1-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-370">5041</span><span class="sxs-lookup"><span data-stu-id="d86a1-370">5041</span></span></p></td>
<td><p><span data-ttu-id="d86a1-371">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="d86a1-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-372">Server front end di chat persistente</span><span class="sxs-lookup"><span data-stu-id="d86a1-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="d86a1-373">Chat persistente Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="d86a1-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="d86a1-374">881</span><span class="sxs-lookup"><span data-stu-id="d86a1-374">881</span></span></p></td>
<td><p><span data-ttu-id="d86a1-375">TCP (TLS) e TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="d86a1-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-376">Server front end di chat persistente</span><span class="sxs-lookup"><span data-stu-id="d86a1-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="d86a1-377">Servizio di trasferimento file Chat persistente</span><span class="sxs-lookup"><span data-stu-id="d86a1-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="d86a1-378">443</span><span class="sxs-lookup"><span data-stu-id="d86a1-378">443</span></span></p></td>
<td><p><span data-ttu-id="d86a1-379">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="d86a1-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="d86a1-380">Alcuni scenari di controllo delle chiamate remote richiedono una connessione TCP tra il server front-end o il Director e il PBX.</span><span class="sxs-lookup"><span data-stu-id="d86a1-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="d86a1-381">Anche se Lync Server non usa più la porta TCP 5060, durante la distribuzione del controllo delle chiamate remote si crea una configurazione del server attendibile, che associa il nome di dominio completo del server RCC line alla porta TCP che il server front end o il direttore utilizzerà per la connessione al sistema PBX.</span><span class="sxs-lookup"><span data-stu-id="d86a1-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="d86a1-382">Per informazioni dettagliate, vedere il cmdlet <STRONG>CsTrustedApplicationComputer</STRONG> nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d86a1-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="d86a1-383">Per i pool che usano solo il bilanciamento del carico hardware (non il bilanciamento del carico DNS), la tabella seguente mostra le porte che devono aprire i dispositivi di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="d86a1-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="d86a1-384">Porte di bilanciamento del carico hardware se si usa solo il bilanciamento del carico hardware</span><span class="sxs-lookup"><span data-stu-id="d86a1-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d86a1-385">Bilanciamento del carico</span><span class="sxs-lookup"><span data-stu-id="d86a1-385">Load Balancer</span></span></th>
<th><span data-ttu-id="d86a1-386">Porta</span><span class="sxs-lookup"><span data-stu-id="d86a1-386">Port</span></span></th>
<th><span data-ttu-id="d86a1-387">Protocollo</span><span class="sxs-lookup"><span data-stu-id="d86a1-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-388">Bilanciamento del carico del server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="d86a1-389">5061</span><span class="sxs-lookup"><span data-stu-id="d86a1-389">5061</span></span></p></td>
<td><p><span data-ttu-id="d86a1-390">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="d86a1-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-391">Bilanciamento del carico del server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="d86a1-392">444</span><span class="sxs-lookup"><span data-stu-id="d86a1-392">444</span></span></p></td>
<td><p><span data-ttu-id="d86a1-393">HTTPS</span><span class="sxs-lookup"><span data-stu-id="d86a1-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-394">Bilanciamento del carico del server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="d86a1-395">135</span><span class="sxs-lookup"><span data-stu-id="d86a1-395">135</span></span></p></td>
<td><p><span data-ttu-id="d86a1-396">DCOM e chiamata di procedura remota (RPC)</span><span class="sxs-lookup"><span data-stu-id="d86a1-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-397">Bilanciamento del carico del server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="d86a1-398">80</span><span class="sxs-lookup"><span data-stu-id="d86a1-398">80</span></span></p></td>
<td><p><span data-ttu-id="d86a1-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="d86a1-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-400">Bilanciamento del carico del server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="d86a1-401">8080</span><span class="sxs-lookup"><span data-stu-id="d86a1-401">8080</span></span></p></td>
<td><p><span data-ttu-id="d86a1-402">TCP-client e recupero di dispositivi del certificato radice dal server front-end-client e dispositivi autenticati da NTLM</span><span class="sxs-lookup"><span data-stu-id="d86a1-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-403">Bilanciamento del carico del server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="d86a1-404">443</span><span class="sxs-lookup"><span data-stu-id="d86a1-404">443</span></span></p></td>
<td><p><span data-ttu-id="d86a1-405">HTTPS</span><span class="sxs-lookup"><span data-stu-id="d86a1-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-406">Bilanciamento del carico del server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="d86a1-407">4443</span><span class="sxs-lookup"><span data-stu-id="d86a1-407">4443</span></span></p></td>
<td><p><span data-ttu-id="d86a1-408">HTTPS (da proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="d86a1-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-409">Bilanciamento del carico del server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="d86a1-410">5072</span><span class="sxs-lookup"><span data-stu-id="d86a1-410">5072</span></span></p></td>
<td><p><span data-ttu-id="d86a1-411">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-412">Bilanciamento del carico del server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="d86a1-413">5073</span><span class="sxs-lookup"><span data-stu-id="d86a1-413">5073</span></span></p></td>
<td><p><span data-ttu-id="d86a1-414">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-415">Bilanciamento del carico del server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="d86a1-416">5075</span><span class="sxs-lookup"><span data-stu-id="d86a1-416">5075</span></span></p></td>
<td><p><span data-ttu-id="d86a1-417">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-418">Bilanciamento del carico del server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="d86a1-419">5076</span><span class="sxs-lookup"><span data-stu-id="d86a1-419">5076</span></span></p></td>
<td><p><span data-ttu-id="d86a1-420">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-421">Bilanciamento del carico del server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="d86a1-422">5071</span><span class="sxs-lookup"><span data-stu-id="d86a1-422">5071</span></span></p></td>
<td><p><span data-ttu-id="d86a1-423">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-424">Bilanciamento del carico del server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="d86a1-425">5080</span><span class="sxs-lookup"><span data-stu-id="d86a1-425">5080</span></span></p></td>
<td><p><span data-ttu-id="d86a1-426">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-427">Bilanciamento del carico del server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="d86a1-428">448</span><span class="sxs-lookup"><span data-stu-id="d86a1-428">448</span></span></p></td>
<td><p><span data-ttu-id="d86a1-429">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-430">Bilanciamento del carico di Mediation Server</span><span class="sxs-lookup"><span data-stu-id="d86a1-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="d86a1-431">5070</span><span class="sxs-lookup"><span data-stu-id="d86a1-431">5070</span></span></p></td>
<td><p><span data-ttu-id="d86a1-432">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-433">Bilanciamento del carico del server front-end (se il pool esegue anche Mediation Server)</span><span class="sxs-lookup"><span data-stu-id="d86a1-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="d86a1-434">5070</span><span class="sxs-lookup"><span data-stu-id="d86a1-434">5070</span></span></p></td>
<td><p><span data-ttu-id="d86a1-435">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-436">Direttore di bilanciamento del carico</span><span class="sxs-lookup"><span data-stu-id="d86a1-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="d86a1-437">443</span><span class="sxs-lookup"><span data-stu-id="d86a1-437">443</span></span></p></td>
<td><p><span data-ttu-id="d86a1-438">HTTPS</span><span class="sxs-lookup"><span data-stu-id="d86a1-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-439">Direttore di bilanciamento del carico</span><span class="sxs-lookup"><span data-stu-id="d86a1-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="d86a1-440">444</span><span class="sxs-lookup"><span data-stu-id="d86a1-440">444</span></span></p></td>
<td><p><span data-ttu-id="d86a1-441">HTTPS</span><span class="sxs-lookup"><span data-stu-id="d86a1-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-442">Direttore di bilanciamento del carico</span><span class="sxs-lookup"><span data-stu-id="d86a1-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="d86a1-443">5061</span><span class="sxs-lookup"><span data-stu-id="d86a1-443">5061</span></span></p></td>
<td><p><span data-ttu-id="d86a1-444">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-445">Direttore di bilanciamento del carico</span><span class="sxs-lookup"><span data-stu-id="d86a1-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="d86a1-446">4443</span><span class="sxs-lookup"><span data-stu-id="d86a1-446">4443</span></span></p></td>
<td><p><span data-ttu-id="d86a1-447">HTTPS (da proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="d86a1-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d86a1-448">I pool di front end e i pool di direttori che usano il bilanciamento del carico DNS devono essere distribuiti anche da un dispositivo di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="d86a1-448">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed.</span></span> <span data-ttu-id="d86a1-449">La tabella seguente mostra le porte che devono essere aperte in questi dispositivi di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="d86a1-449">The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="d86a1-450">Porte di bilanciamento del carico hardware se si usa il bilanciamento del carico DNS</span><span class="sxs-lookup"><span data-stu-id="d86a1-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d86a1-451">Bilanciamento del carico</span><span class="sxs-lookup"><span data-stu-id="d86a1-451">Load Balancer</span></span></th>
<th><span data-ttu-id="d86a1-452">Porta</span><span class="sxs-lookup"><span data-stu-id="d86a1-452">Port</span></span></th>
<th><span data-ttu-id="d86a1-453">Protocollo</span><span class="sxs-lookup"><span data-stu-id="d86a1-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-454">Bilanciamento del carico del server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="d86a1-455">80</span><span class="sxs-lookup"><span data-stu-id="d86a1-455">80</span></span></p></td>
<td><p><span data-ttu-id="d86a1-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="d86a1-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-457">Bilanciamento del carico del server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="d86a1-458">443</span><span class="sxs-lookup"><span data-stu-id="d86a1-458">443</span></span></p></td>
<td><p><span data-ttu-id="d86a1-459">HTTPS</span><span class="sxs-lookup"><span data-stu-id="d86a1-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-460">Bilanciamento del carico del server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="d86a1-461">8080</span><span class="sxs-lookup"><span data-stu-id="d86a1-461">8080</span></span></p></td>
<td><p><span data-ttu-id="d86a1-462">TCP-client e recupero di dispositivi del certificato radice dal server front-end-client e dispositivi autenticati da NTLM</span><span class="sxs-lookup"><span data-stu-id="d86a1-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-463">Bilanciamento del carico del server front-end</span><span class="sxs-lookup"><span data-stu-id="d86a1-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="d86a1-464">4443</span><span class="sxs-lookup"><span data-stu-id="d86a1-464">4443</span></span></p></td>
<td><p><span data-ttu-id="d86a1-465">HTTPS (da proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="d86a1-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-466">Direttore di bilanciamento del carico</span><span class="sxs-lookup"><span data-stu-id="d86a1-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="d86a1-467">443</span><span class="sxs-lookup"><span data-stu-id="d86a1-467">443</span></span></p></td>
<td><p><span data-ttu-id="d86a1-468">HTTPS</span><span class="sxs-lookup"><span data-stu-id="d86a1-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-469">Direttore di bilanciamento del carico</span><span class="sxs-lookup"><span data-stu-id="d86a1-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="d86a1-470">4443</span><span class="sxs-lookup"><span data-stu-id="d86a1-470">4443</span></span></p></td>
<td><p><span data-ttu-id="d86a1-471">HTTPS (da proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="d86a1-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="d86a1-472">Porte client richieste</span><span class="sxs-lookup"><span data-stu-id="d86a1-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d86a1-473">Componente</span><span class="sxs-lookup"><span data-stu-id="d86a1-473">Component</span></span></th>
<th><span data-ttu-id="d86a1-474">Porta</span><span class="sxs-lookup"><span data-stu-id="d86a1-474">Port</span></span></th>
<th><span data-ttu-id="d86a1-475">Protocollo</span><span class="sxs-lookup"><span data-stu-id="d86a1-475">Protocol</span></span></th>
<th><span data-ttu-id="d86a1-476">Note</span><span class="sxs-lookup"><span data-stu-id="d86a1-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-477">Client</span><span class="sxs-lookup"><span data-stu-id="d86a1-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="d86a1-478">67/68</span><span class="sxs-lookup"><span data-stu-id="d86a1-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="d86a1-479">DHCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-480">Usato da Lync Server per trovare il nome di dominio completo del registrar, ovvero se DNS SRV non riesce e le impostazioni manuali non sono configurate.</span><span class="sxs-lookup"><span data-stu-id="d86a1-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-481">Client</span><span class="sxs-lookup"><span data-stu-id="d86a1-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="d86a1-482">443</span><span class="sxs-lookup"><span data-stu-id="d86a1-482">443</span></span></p></td>
<td><p><span data-ttu-id="d86a1-483">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="d86a1-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="d86a1-484">Usato per il traffico SIP da client a server per l'accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="d86a1-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-485">Client</span><span class="sxs-lookup"><span data-stu-id="d86a1-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="d86a1-486">443</span><span class="sxs-lookup"><span data-stu-id="d86a1-486">443</span></span></p></td>
<td><p><span data-ttu-id="d86a1-487">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="d86a1-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="d86a1-488">Usato per l'accesso degli utenti esterni alle sessioni di conferenza Web.</span><span class="sxs-lookup"><span data-stu-id="d86a1-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-489">Client</span><span class="sxs-lookup"><span data-stu-id="d86a1-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="d86a1-490">443</span><span class="sxs-lookup"><span data-stu-id="d86a1-490">443</span></span></p></td>
<td><p><span data-ttu-id="d86a1-491">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="d86a1-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="d86a1-492">Usato per l'accesso degli utenti esterni alle sessioni A/V e agli elementi multimediali (TCP)</span><span class="sxs-lookup"><span data-stu-id="d86a1-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-493">Client</span><span class="sxs-lookup"><span data-stu-id="d86a1-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="d86a1-494">3478</span><span class="sxs-lookup"><span data-stu-id="d86a1-494">3478</span></span></p></td>
<td><p><span data-ttu-id="d86a1-495">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="d86a1-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="d86a1-496">Usato per l'accesso degli utenti esterni alle sessioni A/V e agli elementi multimediali (UDP)</span><span class="sxs-lookup"><span data-stu-id="d86a1-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-497">Client</span><span class="sxs-lookup"><span data-stu-id="d86a1-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="d86a1-498">5061</span><span class="sxs-lookup"><span data-stu-id="d86a1-498">5061</span></span></p></td>
<td><p><span data-ttu-id="d86a1-499">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="d86a1-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="d86a1-500">Usato per il traffico SIP da client a server per l'accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="d86a1-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-501">Client</span><span class="sxs-lookup"><span data-stu-id="d86a1-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="d86a1-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="d86a1-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="d86a1-503">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-504">Usato per il trasferimento di file tra client Lync e client precedenti (client di Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 e Live Communications Server 2005).</span><span class="sxs-lookup"><span data-stu-id="d86a1-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-505">Client</span><span class="sxs-lookup"><span data-stu-id="d86a1-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="d86a1-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="d86a1-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="d86a1-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="d86a1-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-508">Intervallo di porte audio (minimo 20 porte necessarie)</span><span class="sxs-lookup"><span data-stu-id="d86a1-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-509">Client</span><span class="sxs-lookup"><span data-stu-id="d86a1-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="d86a1-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="d86a1-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="d86a1-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="d86a1-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-512">Intervallo di porte video (è necessario un minimo di 20 porte).</span><span class="sxs-lookup"><span data-stu-id="d86a1-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-513">Client</span><span class="sxs-lookup"><span data-stu-id="d86a1-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="d86a1-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="d86a1-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="d86a1-515">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-516">Trasferimento di file peer-to-peer (per il trasferimento di file di conferenza, i client usano PSOM).</span><span class="sxs-lookup"><span data-stu-id="d86a1-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d86a1-517">Client</span><span class="sxs-lookup"><span data-stu-id="d86a1-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="d86a1-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="d86a1-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="d86a1-519">TCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-520">Condivisione applicazioni.</span><span class="sxs-lookup"><span data-stu-id="d86a1-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d86a1-521">Telefono per area comune Aastra 6721ip</span><span class="sxs-lookup"><span data-stu-id="d86a1-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="d86a1-522">Telefono da tavolo Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="d86a1-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="d86a1-523">Telefono IP HP 4110 (telefono area comune)</span><span class="sxs-lookup"><span data-stu-id="d86a1-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="d86a1-524">Telefono IP HP 4120 (telefono da tavolo)</span><span class="sxs-lookup"><span data-stu-id="d86a1-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="d86a1-525">Telefono per area comune IP di Polycom CX500</span><span class="sxs-lookup"><span data-stu-id="d86a1-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="d86a1-526">Telefono da tavolo IP Polycom CX600</span><span class="sxs-lookup"><span data-stu-id="d86a1-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="d86a1-527">Telefono da tavolo IP Polycom CX700</span><span class="sxs-lookup"><span data-stu-id="d86a1-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="d86a1-528">Telefono per conferenze IP di Polycom CX3000</span><span class="sxs-lookup"><span data-stu-id="d86a1-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="d86a1-529">67/68</span><span class="sxs-lookup"><span data-stu-id="d86a1-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="d86a1-530">DHCP</span><span class="sxs-lookup"><span data-stu-id="d86a1-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="d86a1-531">Usato dai dispositivi elencati per trovare il certificato di Lync Server, il nome di dominio completo e il nome di dominio completo del registrar.</span><span class="sxs-lookup"><span data-stu-id="d86a1-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d86a1-532">**\*** Per configurare porte specifiche per questi tipi di elementi multimediali, usare il cmdlet CsConferencingConfiguration (ClientMediaPortRangeEnabled, ClientMediaPort e ClientMediaPortRange Parameters).</span><span class="sxs-lookup"><span data-stu-id="d86a1-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d86a1-533">I programmi set per i client Lync creano automaticamente le eccezioni del firewall di sistema operativo necessarie nel computer client.</span><span class="sxs-lookup"><span data-stu-id="d86a1-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="d86a1-534">Le porte usate per l'accesso degli utenti esterni sono necessarie per qualsiasi scenario in cui il client deve attraversare il firewall dell'organizzazione, ad esempio le comunicazioni esterne o le riunioni ospitate da altre organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="d86a1-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

