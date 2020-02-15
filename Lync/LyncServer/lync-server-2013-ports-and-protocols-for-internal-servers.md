---
title: 'Lync Server 2013: porte e protocolli per i server interni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Ports and protocols for internal servers
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398833(v=OCS.15)
ms:contentKeyID: 48185402
ms.date: 04/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c748a79fe118c9b1d233a7a276bd8298a0e1c3e4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="8b1fd-102">Porte e protocolli per i server interni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b1fd-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b1fd-103">_**Ultimo argomento modificato:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="8b1fd-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="8b1fd-104">In questa sezione vengono riepilogate le porte e i protocolli utilizzati dai server, dai bilanciamento del carico e dai client in una distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8b1fd-105">I client Lync e Communicator quando sono coinvolti in una comunicazione One to One, vengono spesso definiti peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="8b1fd-106">Tecnicamente, i due client stanno comunicando in una conversazione One to One, con la Central Messaging Multipoint Control Unit (IMMCU) al centro.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="8b1fd-107">IMMCU è un componente di front end server.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="8b1fd-108">L'inserimento di IMMCU nel flusso di lavoro di comunicazione necessario consente di abilitare la registrazione dettagli chiamata e altre caratteristiche abilitate dal front end server.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="8b1fd-109">La comunicazione è da una porta di origine dinamica sul client alla porta del server front-end TLS/TCP/5061 (presupponendo l'utilizzo della sicurezza del layer di trasporto consigliato).</span><span class="sxs-lookup"><span data-stu-id="8b1fd-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="8b1fd-110">In base alla progettazione, la comunicazione peer-to-peer (così come la messaggistica istantanea a più parti) è possibile solo quando Lync Server e IMMCU sono attivi e disponibili.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="8b1fd-111">Informazioni dettagliate sulle porte e sui protocolli</span><span class="sxs-lookup"><span data-stu-id="8b1fd-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8b1fd-112">È necessario che Windows Firewall sia in esecuzione prima di avviare i servizi di Lync Server in un server, perché in questo caso Lync Server apre le porte necessarie nel firewall.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="8b1fd-113">Per informazioni dettagliate sulla configurazione del firewall per i componenti perimetrali, vedere [Determine External A/V firewall and Port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b1fd-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="8b1fd-114">Nella tabella seguente sono elencate le porte che è necessario aprire per ogni ruolo server interno.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="8b1fd-115">Porte server richieste (per ruolo server)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-115">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="8b1fd-116">Ruolo server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-116">Server role</span></span></th>
<th><span data-ttu-id="8b1fd-117">Nome servizio</span><span class="sxs-lookup"><span data-stu-id="8b1fd-117">Service name</span></span></th>
<th><span data-ttu-id="8b1fd-118">Porta</span><span class="sxs-lookup"><span data-stu-id="8b1fd-118">Port</span></span></th>
<th><span data-ttu-id="8b1fd-119">Protocol</span><span class="sxs-lookup"><span data-stu-id="8b1fd-119">Protocol</span></span></th>
<th><span data-ttu-id="8b1fd-120">Notes</span><span class="sxs-lookup"><span data-stu-id="8b1fd-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-121">Tutti i server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-122">SQL Browser</span><span class="sxs-lookup"><span data-stu-id="8b1fd-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-123">1434</span><span class="sxs-lookup"><span data-stu-id="8b1fd-123">1434</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-124">UDP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-125">Browser SQL per la copia locale replicata del database dell'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-126">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-127">Servizio front-end di Lync Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-128">5060</span><span class="sxs-lookup"><span data-stu-id="8b1fd-128">5060</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-129">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-130">Utilizzata facoltativamente dai server Standard Edition e dai Front End Server per le route statiche ai servizi trusted, ad esempio i server di controllo delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-131">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-132">Servizio front-end di Lync Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-133">5061</span><span class="sxs-lookup"><span data-stu-id="8b1fd-133">5061</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-134">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-p102">Utilizzata dai server Standard Edition e dai pool Front End per tutte le comunicazioni SIP interne tra i server (MTLS), per le comunicazioni SIP tra Server e Client (TLS), per le comunicazioni SIP tra Front End Server e Mediation Server (MTLS), nonché per le comunicazioni con Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-p102">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS). Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-137">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-138">Servizio front-end di Lync Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-139">444</span><span class="sxs-lookup"><span data-stu-id="8b1fd-139">444</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-140">HTTPS</span><span class="sxs-lookup"><span data-stu-id="8b1fd-140">HTTPS</span></span></p>
<p><span data-ttu-id="8b1fd-141">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-142">Utilizzato per la comunicazione HTTPS tra lo stato attivo (il componente Lync Server che gestisce lo stato delle conferenze) e i singoli server.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="8b1fd-143">Questa porta viene utilizzata anche per le comunicazioni TCP tra Survivable Branch Appliances e front end server.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-144">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-145">Servizio front-end di Lync Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-146">135</span><span class="sxs-lookup"><span data-stu-id="8b1fd-146">135</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-147">DCOM e RPC (Remote Procedure Call)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-148">Utilizzata per le operazioni basate su DCOM quali spostamento utenti, sincronizzazione User Replicator e sincronizzazione rubrica.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-149">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-150">Lync Server IM Service Conferencing</span><span class="sxs-lookup"><span data-stu-id="8b1fd-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-151">5062</span><span class="sxs-lookup"><span data-stu-id="8b1fd-151">5062</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-152">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-153">Utilizzata per le richieste SIP in arrivo per le conferenze di messaggistica istantanea (IM).</span><span class="sxs-lookup"><span data-stu-id="8b1fd-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-154">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-155">Servizio Web Conferencing di Lync Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-156">8057</span><span class="sxs-lookup"><span data-stu-id="8b1fd-156">8057</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-157">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-158">Utilizzata per attendere le connessioni PSOM (Persistent Shared Object Model) dal client.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-159">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-160">Lync Server Web Conferencing Compatibility Service</span><span class="sxs-lookup"><span data-stu-id="8b1fd-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-161">8058</span><span class="sxs-lookup"><span data-stu-id="8b1fd-161">8058</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-162">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-163">Utilizzato per l'attesa per le connessioni PSOM (Persistent Shared Object Model) dal client Live Meeting e le versioni precedenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-164">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-165">Lync Server audio/video Conferencing Service</span><span class="sxs-lookup"><span data-stu-id="8b1fd-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-166">5063</span><span class="sxs-lookup"><span data-stu-id="8b1fd-166">5063</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-167">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-168">Utilizzata per le richieste SIP in arrivo per Audio/Video (A/V) Conferencing.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-169">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-170">Lync Server audio/video Conferencing Service</span><span class="sxs-lookup"><span data-stu-id="8b1fd-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="8b1fd-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-173">Intervallo di porte di attesa multimediali utilizzato per le conferenze video.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-174">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-175">Lync Server Web Compatibility Service</span><span class="sxs-lookup"><span data-stu-id="8b1fd-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-176">80</span><span class="sxs-lookup"><span data-stu-id="8b1fd-176">80</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-178">Utilizzata per le comunicazioni dai Front End Server ai nomi di dominio completi della Web farm (gli URL utilizzati dai componenti Web IIS) quando non si utilizzano protocolli HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-179">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-180">Lync Server Web Compatibility Service</span><span class="sxs-lookup"><span data-stu-id="8b1fd-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-181">443</span><span class="sxs-lookup"><span data-stu-id="8b1fd-181">443</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-182">HTTPS</span><span class="sxs-lookup"><span data-stu-id="8b1fd-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-183">Utilizzata per le comunicazioni dai Front End Server ai nomi di dominio completi della Web farm (gli URL utilizzati dai componenti Web IIS).</span><span class="sxs-lookup"><span data-stu-id="8b1fd-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-184">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-185">Lync Server Web Compatibility Service</span><span class="sxs-lookup"><span data-stu-id="8b1fd-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-186">8080</span><span class="sxs-lookup"><span data-stu-id="8b1fd-186">8080</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-187">TCP e HTTP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-188">Utilizzato dai componenti Web per l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-189">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-190">Componente del server Web</span><span class="sxs-lookup"><span data-stu-id="8b1fd-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-191">4443</span><span class="sxs-lookup"><span data-stu-id="8b1fd-191">4443</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-192">HTTPS</span><span class="sxs-lookup"><span data-stu-id="8b1fd-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-193">HTTPS (da proxy inverso) e comunicazioni inter-pool HTTPS front-end per l'accesso all'individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-194">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-195">Componente del server Web</span><span class="sxs-lookup"><span data-stu-id="8b1fd-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-196">8060</span><span class="sxs-lookup"><span data-stu-id="8b1fd-196">8060</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-197">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-198">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-199">Componente del server Web</span><span class="sxs-lookup"><span data-stu-id="8b1fd-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-200">8061</span><span class="sxs-lookup"><span data-stu-id="8b1fd-200">8061</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-201">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-202">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-203">Componente dei servizi per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="8b1fd-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-204">5086</span><span class="sxs-lookup"><span data-stu-id="8b1fd-204">5086</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-205">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-206">Porta SIP utilizzata dai processi interni dei servizi per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="8b1fd-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-207">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-208">Componente dei servizi per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="8b1fd-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-209">5087</span><span class="sxs-lookup"><span data-stu-id="8b1fd-209">5087</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-210">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-211">Porta SIP utilizzata dai processi interni dei servizi per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="8b1fd-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-212">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-213">Componente dei servizi per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="8b1fd-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-214">443</span><span class="sxs-lookup"><span data-stu-id="8b1fd-214">443</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-215">HTTPS</span><span class="sxs-lookup"><span data-stu-id="8b1fd-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-216">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-217">Servizio Operatore Conferenza di Lync Server (servizi di conferenza telefonica con accesso esterno)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-218">5064</span><span class="sxs-lookup"><span data-stu-id="8b1fd-218">5064</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-219">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-220">Utilizzata per le richieste SIP in arrivo per le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-221">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-222">Servizio Operatore Conferenza di Lync Server (servizi di conferenza telefonica con accesso esterno)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-223">5072</span><span class="sxs-lookup"><span data-stu-id="8b1fd-223">5072</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-224">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-225">Utilizzato per le richieste SIP in arrivo per Attendant (servizi di conferenza telefonica con accesso esterno).</span><span class="sxs-lookup"><span data-stu-id="8b1fd-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-226">Front End Server che eseguono anche un Mediation Server collocato</span><span class="sxs-lookup"><span data-stu-id="8b1fd-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-227">Lync Server Mediation Service</span><span class="sxs-lookup"><span data-stu-id="8b1fd-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-228">5070</span><span class="sxs-lookup"><span data-stu-id="8b1fd-228">5070</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-229">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-230">Utilizzata dal Mediation Server per le richieste in arrivo dal Front End Server al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-231">Front End Server che eseguono anche un Mediation Server collocato</span><span class="sxs-lookup"><span data-stu-id="8b1fd-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-232">Lync Server Mediation Service</span><span class="sxs-lookup"><span data-stu-id="8b1fd-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-233">5067</span><span class="sxs-lookup"><span data-stu-id="8b1fd-233">5067</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-234">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-235">Utilizzata per le richieste SIP in arrivo dal gateway PSTN al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-236">Front End Server che eseguono anche un Mediation Server collocato</span><span class="sxs-lookup"><span data-stu-id="8b1fd-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-237">Lync Server Mediation Service</span><span class="sxs-lookup"><span data-stu-id="8b1fd-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-238">5068</span><span class="sxs-lookup"><span data-stu-id="8b1fd-238">5068</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-239">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-240">Utilizzata per le richieste SIP in arrivo dal gateway PSTN al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-241">Front End Server che eseguono anche un Mediation Server collocato</span><span class="sxs-lookup"><span data-stu-id="8b1fd-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-242">Lync Server Mediation Service</span><span class="sxs-lookup"><span data-stu-id="8b1fd-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-243">5081</span><span class="sxs-lookup"><span data-stu-id="8b1fd-243">5081</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-244">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-245">Utilizzata per le richieste SIP in uscita dal Mediation Server al gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-246">Front End Server che eseguono anche un Mediation Server collocato</span><span class="sxs-lookup"><span data-stu-id="8b1fd-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-247">Lync Server Mediation Service</span><span class="sxs-lookup"><span data-stu-id="8b1fd-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-248">5082</span><span class="sxs-lookup"><span data-stu-id="8b1fd-248">5082</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-249">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-250">Utilizzata per le richieste SIP in uscita dal Mediation Server al gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-251">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-252">Servizio di condivisione applicazioni di Lync Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-253">5065</span><span class="sxs-lookup"><span data-stu-id="8b1fd-253">5065</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-254">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-255">Utilizzata per le richieste di attesa SIP in arrivo per la condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-256">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-257">Servizio di condivisione applicazioni di Lync Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="8b1fd-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-259">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-260">Intervallo di porte di attesa multimediali per la condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-261">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-262">Servizio annuncio di Lync Server Conferencing</span><span class="sxs-lookup"><span data-stu-id="8b1fd-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-263">5073</span><span class="sxs-lookup"><span data-stu-id="8b1fd-263">5073</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-264">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-265">Utilizzato per le richieste SIP in arrivo per il servizio annuncio di Lync Server Conferencing, ovvero per le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-266">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-267">Servizio Parcheggio di chiamata Lync Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-268">5075</span><span class="sxs-lookup"><span data-stu-id="8b1fd-268">5075</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-269">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-270">Utilizzata per le richieste SIP in arrivo per l'applicazione Parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-271">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-272">Servizio di test audio di Lync Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-273">5076</span><span class="sxs-lookup"><span data-stu-id="8b1fd-273">5076</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-274">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-275">Utilizzata per le richieste SIP in arrivo per il servizio Test audio.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-276">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-277">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="8b1fd-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-278">5066</span><span class="sxs-lookup"><span data-stu-id="8b1fd-278">5066</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-279">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-280">Utilizzata per il gateway Enhanced 9-1-1 (E9-1-1) in uscita.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-281">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-282">Servizio Response Group Lync Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-283">5071</span><span class="sxs-lookup"><span data-stu-id="8b1fd-283">5071</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-284">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-285">Utilizzata per le richieste SIP in arrivo per l'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-286">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-287">Servizio Response Group Lync Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-288">8404</span><span class="sxs-lookup"><span data-stu-id="8b1fd-288">8404</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-289">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-290">Utilizzata per le richieste SIP in arrivo per l'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-291">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-292">Servizio criteri larghezza di banda di Lync Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-293">5080</span><span class="sxs-lookup"><span data-stu-id="8b1fd-293">5080</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-294">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-295">Utilizzata per il controllo di ammissione di chiamata eseguito dal servizio criteri larghezza di banda per il traffico A/V Edge TURN.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-296">Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-297">Servizio criteri larghezza di banda di Lync Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-298">448</span><span class="sxs-lookup"><span data-stu-id="8b1fd-298">448</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-299">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-300">Utilizzato per il controllo di ammissione di chiamata dal servizio criteri larghezza di banda di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-301">Server front end in cui si trova l'archivio di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="8b1fd-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-302">Servizio Agente di replica master di Lync Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-303">445</span><span class="sxs-lookup"><span data-stu-id="8b1fd-303">445</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-304">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-305">Utilizzato per inviare i dati di configurazione dall'archivio di gestione centrale ai server che eseguono Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-306">Tutti i server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-307">SQL Browser</span><span class="sxs-lookup"><span data-stu-id="8b1fd-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-308">1434</span><span class="sxs-lookup"><span data-stu-id="8b1fd-308">1434</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-309">UDP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-310">SQL browser per la copia locale replicata dei dati dell'archivio di gestione centrale nell'istanza locale di SQL Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-311">Tutti i server interni</span><span class="sxs-lookup"><span data-stu-id="8b1fd-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-312">Vari</span><span class="sxs-lookup"><span data-stu-id="8b1fd-312">Various</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="8b1fd-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-315">Intervallo di porte multimediali utilizzato per le conferenze audio su tutti i server interni.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="8b1fd-316">Utilizzato da tutti i server che terminano audio: Front End Server (per il servizio Operatore Conferenza di Lync Server, Lync Server Conferencing Service annuncio e Lync Server audio/video Conferencing Server) e Mediation.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-317">Server Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="8b1fd-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8b1fd-318">443</span><span class="sxs-lookup"><span data-stu-id="8b1fd-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8b1fd-319">Utilizzato da Lync Server 2013 per la connessione al server Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-320">Amministrazione</span><span class="sxs-lookup"><span data-stu-id="8b1fd-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-321">Servizio front-end di Lync Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-322">5060</span><span class="sxs-lookup"><span data-stu-id="8b1fd-322">5060</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-323">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-324">Utilizzata facoltativamente per le route statiche ai servizi trusted, come i server di controllo delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-325">Amministrazione</span><span class="sxs-lookup"><span data-stu-id="8b1fd-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-326">Servizio front-end di Lync Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-327">444</span><span class="sxs-lookup"><span data-stu-id="8b1fd-327">444</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-328">HTTPS</span><span class="sxs-lookup"><span data-stu-id="8b1fd-328">HTTPS</span></span></p>
<p><span data-ttu-id="8b1fd-329">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-330">Comunicazioni interne ai server tra Front End e Director.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="8b1fd-331">È inoltre possibile pubblicare il certificato client (nei Front End Server) o convalidare se il certificato client è già stato pubblicato.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-332">Amministrazione</span><span class="sxs-lookup"><span data-stu-id="8b1fd-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-333">Lync Server Web Compatibility Service</span><span class="sxs-lookup"><span data-stu-id="8b1fd-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-334">80</span><span class="sxs-lookup"><span data-stu-id="8b1fd-334">80</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-335">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-p105">Utilizzata per le comunicazioni iniziali dai Director ai nomi di dominio completo (FQDN) della Web farm (gli URL utilizzati dai componenti Web IIS). Durante il normale funzionamento, viene effettuato il passaggio al traffico HTTPS mediante la porta 443 e il tipo di protocollo TCP.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-338">Amministrazione</span><span class="sxs-lookup"><span data-stu-id="8b1fd-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-339">Lync Server Web Compatibility Service</span><span class="sxs-lookup"><span data-stu-id="8b1fd-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-340">443</span><span class="sxs-lookup"><span data-stu-id="8b1fd-340">443</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-341">HTTPS</span><span class="sxs-lookup"><span data-stu-id="8b1fd-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-342">Utilizzata per le comunicazioni dai Director ai nomi di dominio completi (FQDN) della Web farm (gli URL utilizzati dai componenti Web IIS).</span><span class="sxs-lookup"><span data-stu-id="8b1fd-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-343">Amministrazione</span><span class="sxs-lookup"><span data-stu-id="8b1fd-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-344">Servizio front-end di Lync Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-345">5061</span><span class="sxs-lookup"><span data-stu-id="8b1fd-345">5061</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-346">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-347">Utilizzata per le comunicazioni interne tra i server e per le connessioni client.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-348">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-349">Lync Server Mediation Service</span><span class="sxs-lookup"><span data-stu-id="8b1fd-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-350">5070</span><span class="sxs-lookup"><span data-stu-id="8b1fd-350">5070</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-351">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-352">Utilizzata dal Mediation Server per le richieste in arrivo dal Front End Server.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-353">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-354">Lync Server Mediation Service</span><span class="sxs-lookup"><span data-stu-id="8b1fd-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-355">5067</span><span class="sxs-lookup"><span data-stu-id="8b1fd-355">5067</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-356">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-357">Utilizzata per le richieste SIP in arrivo dal gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-358">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-359">Lync Server Mediation Service</span><span class="sxs-lookup"><span data-stu-id="8b1fd-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-360">5068</span><span class="sxs-lookup"><span data-stu-id="8b1fd-360">5068</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-361">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-362">Utilizzata per le richieste SIP in arrivo dal gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-363">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-364">Lync Server Mediation Service</span><span class="sxs-lookup"><span data-stu-id="8b1fd-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-365">5070</span><span class="sxs-lookup"><span data-stu-id="8b1fd-365">5070</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-366">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-367">Utilizzata per le richieste SIP dai Front End Server.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-368">Front End Server della chat persistente</span><span class="sxs-lookup"><span data-stu-id="8b1fd-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-369">SIP chat persistente</span><span class="sxs-lookup"><span data-stu-id="8b1fd-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-370">5041</span><span class="sxs-lookup"><span data-stu-id="8b1fd-370">5041</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-371">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-372">Front End Server della chat persistente</span><span class="sxs-lookup"><span data-stu-id="8b1fd-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-373">Chat persistente Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-374">881</span><span class="sxs-lookup"><span data-stu-id="8b1fd-374">881</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-375">TCP (TLS) e TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-376">Front End Server della chat persistente</span><span class="sxs-lookup"><span data-stu-id="8b1fd-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-377">Servizio di trasferimento file di chat persistente</span><span class="sxs-lookup"><span data-stu-id="8b1fd-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-378">443</span><span class="sxs-lookup"><span data-stu-id="8b1fd-378">443</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-379">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="8b1fd-380">Alcuni scenari di controllo delle chiamate remote richiedono una connessione TCP tra il Front End Server o Director e il sistema PBX.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="8b1fd-381">Anche se Lync Server non utilizza più la porta TCP 5060, durante la distribuzione del controllo delle chiamate remote viene creata una configurazione del server attendibile, che associa il nome di dominio completo del server RCC line alla porta TCP che verrà utilizzata dal front end server o dal Director per la connessione al sistema PBX.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="8b1fd-382">Per informazioni dettagliate, vedere il cmdlet <STRONG>CsTrustedApplicationComputer</STRONG> nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="8b1fd-383">Per i pool che utilizzano solo il servizio di bilanciamento del carico hardware (non il servizio di bilanciamento del carico DNS), la tabella che segue mostra le porte che devono aprire i servizi di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="8b1fd-384">Porte del servizio di bilanciamento del carico hardware se si utilizza solo questo servizio di bilanciamento</span><span class="sxs-lookup"><span data-stu-id="8b1fd-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b1fd-385">Servizio di bilanciamento del carico</span><span class="sxs-lookup"><span data-stu-id="8b1fd-385">Load Balancer</span></span></th>
<th><span data-ttu-id="8b1fd-386">Porta</span><span class="sxs-lookup"><span data-stu-id="8b1fd-386">Port</span></span></th>
<th><span data-ttu-id="8b1fd-387">Protocol</span><span class="sxs-lookup"><span data-stu-id="8b1fd-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-388">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-389">5061</span><span class="sxs-lookup"><span data-stu-id="8b1fd-389">5061</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-390">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-391">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-392">444</span><span class="sxs-lookup"><span data-stu-id="8b1fd-392">444</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-393">HTTPS</span><span class="sxs-lookup"><span data-stu-id="8b1fd-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-394">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-395">135</span><span class="sxs-lookup"><span data-stu-id="8b1fd-395">135</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-396">DCOM ed RPC (Remote Procedure Call)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-397">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-398">80</span><span class="sxs-lookup"><span data-stu-id="8b1fd-398">80</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-400">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-401">8080</span><span class="sxs-lookup"><span data-stu-id="8b1fd-401">8080</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-402">TCP - Recupero tramite client e dispositivi del certificato radice da Front End Server; client e dispositivi autenticati mediante NTLM</span><span class="sxs-lookup"><span data-stu-id="8b1fd-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-403">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-404">443</span><span class="sxs-lookup"><span data-stu-id="8b1fd-404">443</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-405">HTTPS</span><span class="sxs-lookup"><span data-stu-id="8b1fd-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-406">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-407">4443</span><span class="sxs-lookup"><span data-stu-id="8b1fd-407">4443</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-408">HTTPS (da proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-409">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-410">5072</span><span class="sxs-lookup"><span data-stu-id="8b1fd-410">5072</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-411">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-412">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-413">5073</span><span class="sxs-lookup"><span data-stu-id="8b1fd-413">5073</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-414">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-415">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-416">5075</span><span class="sxs-lookup"><span data-stu-id="8b1fd-416">5075</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-417">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-418">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-419">5076</span><span class="sxs-lookup"><span data-stu-id="8b1fd-419">5076</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-420">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-421">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-422">5071</span><span class="sxs-lookup"><span data-stu-id="8b1fd-422">5071</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-423">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-424">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-425">5080</span><span class="sxs-lookup"><span data-stu-id="8b1fd-425">5080</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-426">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-427">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-428">448</span><span class="sxs-lookup"><span data-stu-id="8b1fd-428">448</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-429">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-430">Bilanciamento del carico di Mediation Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-431">5070</span><span class="sxs-lookup"><span data-stu-id="8b1fd-431">5070</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-432">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-433">Bilanciamento del carico del server front-end (se il pool esegue anche Mediation Server)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-434">5070</span><span class="sxs-lookup"><span data-stu-id="8b1fd-434">5070</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-435">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-436">Servizio di bilanciamento del carico Director</span><span class="sxs-lookup"><span data-stu-id="8b1fd-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-437">443</span><span class="sxs-lookup"><span data-stu-id="8b1fd-437">443</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-438">HTTPS</span><span class="sxs-lookup"><span data-stu-id="8b1fd-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-439">Servizio di bilanciamento del carico Director</span><span class="sxs-lookup"><span data-stu-id="8b1fd-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-440">444</span><span class="sxs-lookup"><span data-stu-id="8b1fd-440">444</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-441">HTTPS</span><span class="sxs-lookup"><span data-stu-id="8b1fd-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-442">Servizio di bilanciamento del carico Director</span><span class="sxs-lookup"><span data-stu-id="8b1fd-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-443">5061</span><span class="sxs-lookup"><span data-stu-id="8b1fd-443">5061</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-444">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-445">Servizio di bilanciamento del carico Director</span><span class="sxs-lookup"><span data-stu-id="8b1fd-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-446">4443</span><span class="sxs-lookup"><span data-stu-id="8b1fd-446">4443</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-447">HTTPS (da proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8b1fd-p107">È necessario che anche nei pool Front End e server Director che utilizzano il servizio di bilanciamento del carico DNS sia distribuito un servizio di bilanciamento del carico hardware. Nella tabella che segue sono indicate le porte che è necessario aprire in questi servizi di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-p107">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed. The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="8b1fd-450">Porte del servizio di bilanciamento del carico hardware se si utilizza il servizio di bilanciamento del carico DNS</span><span class="sxs-lookup"><span data-stu-id="8b1fd-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b1fd-451">Servizio di bilanciamento del carico</span><span class="sxs-lookup"><span data-stu-id="8b1fd-451">Load Balancer</span></span></th>
<th><span data-ttu-id="8b1fd-452">Porta</span><span class="sxs-lookup"><span data-stu-id="8b1fd-452">Port</span></span></th>
<th><span data-ttu-id="8b1fd-453">Protocol</span><span class="sxs-lookup"><span data-stu-id="8b1fd-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-454">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-455">80</span><span class="sxs-lookup"><span data-stu-id="8b1fd-455">80</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-457">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-458">443</span><span class="sxs-lookup"><span data-stu-id="8b1fd-458">443</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-459">HTTPS</span><span class="sxs-lookup"><span data-stu-id="8b1fd-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-460">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-461">8080</span><span class="sxs-lookup"><span data-stu-id="8b1fd-461">8080</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-462">TCP - Recupero tramite client e dispositivi del certificato radice da Front End Server; client e dispositivi autenticati mediante NTLM</span><span class="sxs-lookup"><span data-stu-id="8b1fd-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-463">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="8b1fd-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-464">4443</span><span class="sxs-lookup"><span data-stu-id="8b1fd-464">4443</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-465">HTTPS (da proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-466">Servizio di bilanciamento del carico Director</span><span class="sxs-lookup"><span data-stu-id="8b1fd-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-467">443</span><span class="sxs-lookup"><span data-stu-id="8b1fd-467">443</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-468">HTTPS</span><span class="sxs-lookup"><span data-stu-id="8b1fd-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-469">Servizio di bilanciamento del carico Director</span><span class="sxs-lookup"><span data-stu-id="8b1fd-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-470">4443</span><span class="sxs-lookup"><span data-stu-id="8b1fd-470">4443</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-471">HTTPS (da proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="8b1fd-472">Porte client richieste</span><span class="sxs-lookup"><span data-stu-id="8b1fd-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b1fd-473">Componente</span><span class="sxs-lookup"><span data-stu-id="8b1fd-473">Component</span></span></th>
<th><span data-ttu-id="8b1fd-474">Porta</span><span class="sxs-lookup"><span data-stu-id="8b1fd-474">Port</span></span></th>
<th><span data-ttu-id="8b1fd-475">Protocol</span><span class="sxs-lookup"><span data-stu-id="8b1fd-475">Protocol</span></span></th>
<th><span data-ttu-id="8b1fd-476">Notes</span><span class="sxs-lookup"><span data-stu-id="8b1fd-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-477">Client</span><span class="sxs-lookup"><span data-stu-id="8b1fd-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-478">67/68</span><span class="sxs-lookup"><span data-stu-id="8b1fd-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-479">DHCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-480">Utilizzato da Lync Server per individuare il nome di dominio completo del registrar, ovvero se DNS SRV ha esito negativo e le impostazioni manuali non sono configurate.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-481">Client</span><span class="sxs-lookup"><span data-stu-id="8b1fd-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-482">443</span><span class="sxs-lookup"><span data-stu-id="8b1fd-482">443</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-483">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-484">Utilizzata per il traffico SIP da client a server per l'accesso utente esterno.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-485">Client</span><span class="sxs-lookup"><span data-stu-id="8b1fd-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-486">443</span><span class="sxs-lookup"><span data-stu-id="8b1fd-486">443</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-487">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-488">Utilizzata per l'accesso utente esterno alle sessioni di Web Conferencing.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-489">Client</span><span class="sxs-lookup"><span data-stu-id="8b1fd-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-490">443</span><span class="sxs-lookup"><span data-stu-id="8b1fd-490">443</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-491">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-492">Utilizzata per l'accesso utente esterno alle sessioni A/V e ai supporti multimediali (TCP)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-493">Client</span><span class="sxs-lookup"><span data-stu-id="8b1fd-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-494">3478</span><span class="sxs-lookup"><span data-stu-id="8b1fd-494">3478</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-495">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-496">Utilizzato per l'accesso degli utenti esterni alle sessioni A/V e ai supporti (UDP)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-497">Client</span><span class="sxs-lookup"><span data-stu-id="8b1fd-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-498">5061</span><span class="sxs-lookup"><span data-stu-id="8b1fd-498">5061</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-499">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-500">Utilizzata per il traffico SIP da client a server per l'accesso utente esterno.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-501">Client</span><span class="sxs-lookup"><span data-stu-id="8b1fd-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="8b1fd-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-503">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-504">Utilizzato per il trasferimento di file tra client Lync e client precedenti (client di Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 e Live Communications Server 2005).</span><span class="sxs-lookup"><span data-stu-id="8b1fd-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-505">Client</span><span class="sxs-lookup"><span data-stu-id="8b1fd-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="8b1fd-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-508">Intervallo di porte audio (almeno 20 porte richieste)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-509">Client</span><span class="sxs-lookup"><span data-stu-id="8b1fd-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="8b1fd-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-512">Intervallo di porte video (almeno 20 porte richieste).</span><span class="sxs-lookup"><span data-stu-id="8b1fd-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-513">Client</span><span class="sxs-lookup"><span data-stu-id="8b1fd-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="8b1fd-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-515">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-516">Trasferimento file peer-to-peer (per il trasferimento dei file del servizio di conferenza, i client utilizzano PSOM).</span><span class="sxs-lookup"><span data-stu-id="8b1fd-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b1fd-517">Client</span><span class="sxs-lookup"><span data-stu-id="8b1fd-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="8b1fd-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-519">TCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-520">Condivisione applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b1fd-521">Telefono di area comune Aastra 6721ip</span><span class="sxs-lookup"><span data-stu-id="8b1fd-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="8b1fd-522">Telefono da tavolo Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="8b1fd-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="8b1fd-523">Telefono IP HP 4110 (telefono di area comune)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="8b1fd-524">Telefono IP HP 4120 (telefono da tavolo)</span><span class="sxs-lookup"><span data-stu-id="8b1fd-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="8b1fd-525">Telefono di area comune IP Polycom CX500</span><span class="sxs-lookup"><span data-stu-id="8b1fd-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="8b1fd-526">Telefono da tavolo IP Polycom CX600</span><span class="sxs-lookup"><span data-stu-id="8b1fd-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="8b1fd-527">Telefono da tavolo IP Polycom CX700</span><span class="sxs-lookup"><span data-stu-id="8b1fd-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="8b1fd-528">Telefono IP per conferenze Polycom CX3000</span><span class="sxs-lookup"><span data-stu-id="8b1fd-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-529">67/68</span><span class="sxs-lookup"><span data-stu-id="8b1fd-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-530">DHCP</span><span class="sxs-lookup"><span data-stu-id="8b1fd-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="8b1fd-531">Utilizzato dai dispositivi elencati per individuare il certificato di Lync Server, il nome di dominio completo e il nome di dominio completo del servizio di registrazione.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8b1fd-532">**\*** Per configurare porte specifiche per questi tipi di supporti, utilizzare il cmdlet CsConferencingConfiguration (parametri ClientMediaPortRangeEnabled, ClientMediaPort e ClientMediaPortRange).</span><span class="sxs-lookup"><span data-stu-id="8b1fd-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8b1fd-533">I programmi set per i client di Lync creano automaticamente le eccezioni del firewall del sistema operativo necessarie sul computer client.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="8b1fd-534">Le porte utilizzate per l'accesso utente esterno sono richieste per tutti gli scenari in cui il client deve attraversare il firewall dell'organizzazione, ad esempio per qualsiasi comunicazione o riunione esterna ospitata da altre organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="8b1fd-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

