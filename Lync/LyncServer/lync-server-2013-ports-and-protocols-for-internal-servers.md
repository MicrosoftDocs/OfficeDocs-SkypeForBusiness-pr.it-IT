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
ms.openlocfilehash: 8f730a0af21abfbff8058aa51c1163c1dae1ff3a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="3e604-102">Porte e protocolli per i server interni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e604-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e604-103">_**Ultimo argomento modificato:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="3e604-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="3e604-104">In questa sezione vengono riepilogate le porte e i protocolli utilizzati dai server, dai bilanciamento del carico e dai client in una distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e604-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3e604-105">I client Lync e Communicator quando sono coinvolti in una comunicazione One to One, vengono spesso definiti peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="3e604-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="3e604-106">Tecnicamente, i due client stanno comunicando in una conversazione One to One, con la Central Messaging Multipoint Control Unit (IMMCU) al centro.</span><span class="sxs-lookup"><span data-stu-id="3e604-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="3e604-107">IMMCU è un componente di front end server.</span><span class="sxs-lookup"><span data-stu-id="3e604-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="3e604-108">L'inserimento di IMMCU nel flusso di lavoro di comunicazione necessario consente di abilitare la registrazione dettagli chiamata e altre caratteristiche abilitate dal front end server.</span><span class="sxs-lookup"><span data-stu-id="3e604-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="3e604-109">La comunicazione è da una porta di origine dinamica sul client alla porta del server front-end TLS/TCP/5061 (presupponendo l'utilizzo della sicurezza del layer di trasporto consigliato).</span><span class="sxs-lookup"><span data-stu-id="3e604-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="3e604-110">In base alla progettazione, la comunicazione peer-to-peer (così come la messaggistica istantanea a più parti) è possibile solo quando Lync Server e IMMCU sono attivi e disponibili.</span><span class="sxs-lookup"><span data-stu-id="3e604-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="3e604-111">Informazioni dettagliate sulle porte e sui protocolli</span><span class="sxs-lookup"><span data-stu-id="3e604-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3e604-112">È necessario che Windows Firewall sia in esecuzione prima di avviare i servizi di Lync Server in un server, perché in questo caso Lync Server apre le porte necessarie nel firewall.</span><span class="sxs-lookup"><span data-stu-id="3e604-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="3e604-113">Per informazioni dettagliate sulla configurazione del firewall per i componenti perimetrali, vedere [Determine External A/V firewall and Port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e604-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="3e604-114">Nella tabella seguente sono elencate le porte che è necessario aprire per ogni ruolo server interno.</span><span class="sxs-lookup"><span data-stu-id="3e604-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="3e604-115">Porte server richieste (per ruolo server)</span><span class="sxs-lookup"><span data-stu-id="3e604-115">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="3e604-116">Ruolo server</span><span class="sxs-lookup"><span data-stu-id="3e604-116">Server role</span></span></th>
<th><span data-ttu-id="3e604-117">Nome servizio</span><span class="sxs-lookup"><span data-stu-id="3e604-117">Service name</span></span></th>
<th><span data-ttu-id="3e604-118">Porta</span><span class="sxs-lookup"><span data-stu-id="3e604-118">Port</span></span></th>
<th><span data-ttu-id="3e604-119">Protocol</span><span class="sxs-lookup"><span data-stu-id="3e604-119">Protocol</span></span></th>
<th><span data-ttu-id="3e604-120">Notes</span><span class="sxs-lookup"><span data-stu-id="3e604-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e604-121">Tutti i server</span><span class="sxs-lookup"><span data-stu-id="3e604-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-122">SQL Browser</span><span class="sxs-lookup"><span data-stu-id="3e604-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="3e604-123">1434</span><span class="sxs-lookup"><span data-stu-id="3e604-123">1434</span></span></p></td>
<td><p><span data-ttu-id="3e604-124">UDP</span><span class="sxs-lookup"><span data-stu-id="3e604-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="3e604-125">Browser SQL per la copia locale replicata del database dell'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="3e604-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-126">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-127">Servizio front-end di Lync Server</span><span class="sxs-lookup"><span data-stu-id="3e604-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="3e604-128">5060</span><span class="sxs-lookup"><span data-stu-id="3e604-128">5060</span></span></p></td>
<td><p><span data-ttu-id="3e604-129">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-130">Utilizzata facoltativamente dai server Standard Edition e dai Front End Server per le route statiche ai servizi trusted, ad esempio i server di controllo delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="3e604-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-131">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-132">Servizio front-end di Lync Server</span><span class="sxs-lookup"><span data-stu-id="3e604-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="3e604-133">5061</span><span class="sxs-lookup"><span data-stu-id="3e604-133">5061</span></span></p></td>
<td><p><span data-ttu-id="3e604-134">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="3e604-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="3e604-p102">Utilizzata dai server Standard Edition e dai pool Front End per tutte le comunicazioni SIP interne tra i server (MTLS), per le comunicazioni SIP tra Server e Client (TLS), per le comunicazioni SIP tra Front End Server e Mediation Server (MTLS), nonché per le comunicazioni con Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="3e604-p102">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS). Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-137">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-138">Servizio front-end di Lync Server</span><span class="sxs-lookup"><span data-stu-id="3e604-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="3e604-139">444</span><span class="sxs-lookup"><span data-stu-id="3e604-139">444</span></span></p></td>
<td><p><span data-ttu-id="3e604-140">HTTPS</span><span class="sxs-lookup"><span data-stu-id="3e604-140">HTTPS</span></span></p>
<p><span data-ttu-id="3e604-141">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-142">Utilizzato per la comunicazione HTTPS tra lo stato attivo (il componente Lync Server che gestisce lo stato delle conferenze) e i singoli server.</span><span class="sxs-lookup"><span data-stu-id="3e604-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="3e604-143">Questa porta viene utilizzata anche per le comunicazioni TCP tra Survivable Branch Appliances e front end server.</span><span class="sxs-lookup"><span data-stu-id="3e604-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-144">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-145">Servizio front-end di Lync Server</span><span class="sxs-lookup"><span data-stu-id="3e604-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="3e604-146">135</span><span class="sxs-lookup"><span data-stu-id="3e604-146">135</span></span></p></td>
<td><p><span data-ttu-id="3e604-147">DCOM e RPC (Remote Procedure Call)</span><span class="sxs-lookup"><span data-stu-id="3e604-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="3e604-148">Utilizzata per le operazioni basate su DCOM quali spostamento utenti, sincronizzazione User Replicator e sincronizzazione rubrica.</span><span class="sxs-lookup"><span data-stu-id="3e604-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-149">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-150">Lync Server IM Service Conferencing</span><span class="sxs-lookup"><span data-stu-id="3e604-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="3e604-151">5062</span><span class="sxs-lookup"><span data-stu-id="3e604-151">5062</span></span></p></td>
<td><p><span data-ttu-id="3e604-152">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-153">Utilizzata per le richieste SIP in arrivo per le conferenze di messaggistica istantanea (IM).</span><span class="sxs-lookup"><span data-stu-id="3e604-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-154">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-155">Servizio Web Conferencing di Lync Server</span><span class="sxs-lookup"><span data-stu-id="3e604-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="3e604-156">8057</span><span class="sxs-lookup"><span data-stu-id="3e604-156">8057</span></span></p></td>
<td><p><span data-ttu-id="3e604-157">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="3e604-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="3e604-158">Utilizzata per attendere le connessioni PSOM (Persistent Shared Object Model) dal client.</span><span class="sxs-lookup"><span data-stu-id="3e604-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-159">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-160">Lync Server Web Conferencing Compatibility Service</span><span class="sxs-lookup"><span data-stu-id="3e604-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="3e604-161">8058</span><span class="sxs-lookup"><span data-stu-id="3e604-161">8058</span></span></p></td>
<td><p><span data-ttu-id="3e604-162">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="3e604-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="3e604-163">Utilizzato per l'attesa per le connessioni PSOM (Persistent Shared Object Model) dal client Live Meeting e le versioni precedenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e604-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-164">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-165">Lync Server audio/video Conferencing Service</span><span class="sxs-lookup"><span data-stu-id="3e604-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="3e604-166">5063</span><span class="sxs-lookup"><span data-stu-id="3e604-166">5063</span></span></p></td>
<td><p><span data-ttu-id="3e604-167">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-168">Utilizzata per le richieste SIP in arrivo per Audio/Video (A/V) Conferencing.</span><span class="sxs-lookup"><span data-stu-id="3e604-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-169">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-170">Lync Server audio/video Conferencing Service</span><span class="sxs-lookup"><span data-stu-id="3e604-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="3e604-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="3e604-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="3e604-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="3e604-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="3e604-173">Intervallo di porte di attesa multimediali utilizzato per le conferenze video.</span><span class="sxs-lookup"><span data-stu-id="3e604-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-174">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-175">Lync Server Web Compatibility Service</span><span class="sxs-lookup"><span data-stu-id="3e604-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="3e604-176">80</span><span class="sxs-lookup"><span data-stu-id="3e604-176">80</span></span></p></td>
<td><p><span data-ttu-id="3e604-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="3e604-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="3e604-178">Utilizzata per le comunicazioni dai Front End Server ai nomi di dominio completi della Web farm (gli URL utilizzati dai componenti Web IIS) quando non si utilizzano protocolli HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3e604-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-179">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-180">Lync Server Web Compatibility Service</span><span class="sxs-lookup"><span data-stu-id="3e604-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="3e604-181">443</span><span class="sxs-lookup"><span data-stu-id="3e604-181">443</span></span></p></td>
<td><p><span data-ttu-id="3e604-182">HTTPS</span><span class="sxs-lookup"><span data-stu-id="3e604-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="3e604-183">Utilizzata per le comunicazioni dai Front End Server ai nomi di dominio completi della Web farm (gli URL utilizzati dai componenti Web IIS).</span><span class="sxs-lookup"><span data-stu-id="3e604-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-184">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-185">Lync Server Web Compatibility Service</span><span class="sxs-lookup"><span data-stu-id="3e604-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="3e604-186">8080</span><span class="sxs-lookup"><span data-stu-id="3e604-186">8080</span></span></p></td>
<td><p><span data-ttu-id="3e604-187">TCP e HTTP</span><span class="sxs-lookup"><span data-stu-id="3e604-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="3e604-188">Utilizzato dai componenti Web per l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="3e604-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-189">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-190">Componente del server Web</span><span class="sxs-lookup"><span data-stu-id="3e604-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="3e604-191">4443</span><span class="sxs-lookup"><span data-stu-id="3e604-191">4443</span></span></p></td>
<td><p><span data-ttu-id="3e604-192">HTTPS</span><span class="sxs-lookup"><span data-stu-id="3e604-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="3e604-193">HTTPS (da proxy inverso) e comunicazioni inter-pool HTTPS front-end per l'accesso all'individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="3e604-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-194">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-195">Componente del server Web</span><span class="sxs-lookup"><span data-stu-id="3e604-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="3e604-196">8060</span><span class="sxs-lookup"><span data-stu-id="3e604-196">8060</span></span></p></td>
<td><p><span data-ttu-id="3e604-197">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="3e604-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-198">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-199">Componente del server Web</span><span class="sxs-lookup"><span data-stu-id="3e604-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="3e604-200">8061</span><span class="sxs-lookup"><span data-stu-id="3e604-200">8061</span></span></p></td>
<td><p><span data-ttu-id="3e604-201">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="3e604-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-202">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-203">Componente dei servizi per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="3e604-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="3e604-204">5086</span><span class="sxs-lookup"><span data-stu-id="3e604-204">5086</span></span></p></td>
<td><p><span data-ttu-id="3e604-205">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="3e604-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="3e604-206">Porta SIP utilizzata dai processi interni dei servizi per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="3e604-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-207">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-208">Componente dei servizi per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="3e604-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="3e604-209">5087</span><span class="sxs-lookup"><span data-stu-id="3e604-209">5087</span></span></p></td>
<td><p><span data-ttu-id="3e604-210">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="3e604-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="3e604-211">Porta SIP utilizzata dai processi interni dei servizi per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="3e604-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-212">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-213">Componente dei servizi per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="3e604-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="3e604-214">443</span><span class="sxs-lookup"><span data-stu-id="3e604-214">443</span></span></p></td>
<td><p><span data-ttu-id="3e604-215">HTTPS</span><span class="sxs-lookup"><span data-stu-id="3e604-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-216">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-217">Servizio Operatore Conferenza di Lync Server (servizi di conferenza telefonica con accesso esterno)</span><span class="sxs-lookup"><span data-stu-id="3e604-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="3e604-218">5064</span><span class="sxs-lookup"><span data-stu-id="3e604-218">5064</span></span></p></td>
<td><p><span data-ttu-id="3e604-219">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-220">Utilizzata per le richieste SIP in arrivo per le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="3e604-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-221">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-222">Servizio Operatore Conferenza di Lync Server (servizi di conferenza telefonica con accesso esterno)</span><span class="sxs-lookup"><span data-stu-id="3e604-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="3e604-223">5072</span><span class="sxs-lookup"><span data-stu-id="3e604-223">5072</span></span></p></td>
<td><p><span data-ttu-id="3e604-224">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-225">Utilizzato per le richieste SIP in arrivo per Attendant (servizi di conferenza telefonica con accesso esterno).</span><span class="sxs-lookup"><span data-stu-id="3e604-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-226">Front End Server che eseguono anche un Mediation Server collocato</span><span class="sxs-lookup"><span data-stu-id="3e604-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="3e604-227">Lync Server Mediation Service</span><span class="sxs-lookup"><span data-stu-id="3e604-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="3e604-228">5070</span><span class="sxs-lookup"><span data-stu-id="3e604-228">5070</span></span></p></td>
<td><p><span data-ttu-id="3e604-229">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-230">Utilizzata dal Mediation Server per le richieste in arrivo dal Front End Server al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="3e604-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-231">Front End Server che eseguono anche un Mediation Server collocato</span><span class="sxs-lookup"><span data-stu-id="3e604-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="3e604-232">Lync Server Mediation Service</span><span class="sxs-lookup"><span data-stu-id="3e604-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="3e604-233">5067</span><span class="sxs-lookup"><span data-stu-id="3e604-233">5067</span></span></p></td>
<td><p><span data-ttu-id="3e604-234">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="3e604-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="3e604-235">Utilizzata per le richieste SIP in arrivo dal gateway PSTN al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="3e604-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-236">Front End Server che eseguono anche un Mediation Server collocato</span><span class="sxs-lookup"><span data-stu-id="3e604-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="3e604-237">Lync Server Mediation Service</span><span class="sxs-lookup"><span data-stu-id="3e604-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="3e604-238">5068</span><span class="sxs-lookup"><span data-stu-id="3e604-238">5068</span></span></p></td>
<td><p><span data-ttu-id="3e604-239">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-240">Utilizzata per le richieste SIP in arrivo dal gateway PSTN al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="3e604-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-241">Front End Server che eseguono anche un Mediation Server collocato</span><span class="sxs-lookup"><span data-stu-id="3e604-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="3e604-242">Lync Server Mediation Service</span><span class="sxs-lookup"><span data-stu-id="3e604-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="3e604-243">5081</span><span class="sxs-lookup"><span data-stu-id="3e604-243">5081</span></span></p></td>
<td><p><span data-ttu-id="3e604-244">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-245">Utilizzata per le richieste SIP in uscita dal Mediation Server al gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="3e604-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-246">Front End Server che eseguono anche un Mediation Server collocato</span><span class="sxs-lookup"><span data-stu-id="3e604-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="3e604-247">Lync Server Mediation Service</span><span class="sxs-lookup"><span data-stu-id="3e604-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="3e604-248">5082</span><span class="sxs-lookup"><span data-stu-id="3e604-248">5082</span></span></p></td>
<td><p><span data-ttu-id="3e604-249">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="3e604-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="3e604-250">Utilizzata per le richieste SIP in uscita dal Mediation Server al gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="3e604-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-251">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-252">Servizio di condivisione applicazioni di Lync Server</span><span class="sxs-lookup"><span data-stu-id="3e604-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="3e604-253">5065</span><span class="sxs-lookup"><span data-stu-id="3e604-253">5065</span></span></p></td>
<td><p><span data-ttu-id="3e604-254">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-255">Utilizzata per le richieste di attesa SIP in arrivo per la condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="3e604-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-256">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-257">Servizio di condivisione applicazioni di Lync Server</span><span class="sxs-lookup"><span data-stu-id="3e604-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="3e604-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="3e604-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="3e604-259">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-260">Intervallo di porte di attesa multimediali per la condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="3e604-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-261">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-262">Servizio annuncio di Lync Server Conferencing</span><span class="sxs-lookup"><span data-stu-id="3e604-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="3e604-263">5073</span><span class="sxs-lookup"><span data-stu-id="3e604-263">5073</span></span></p></td>
<td><p><span data-ttu-id="3e604-264">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-265">Utilizzato per le richieste SIP in arrivo per il servizio annuncio di Lync Server Conferencing, ovvero per le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="3e604-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-266">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-267">Servizio Parcheggio di chiamata Lync Server</span><span class="sxs-lookup"><span data-stu-id="3e604-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="3e604-268">5075</span><span class="sxs-lookup"><span data-stu-id="3e604-268">5075</span></span></p></td>
<td><p><span data-ttu-id="3e604-269">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-270">Utilizzata per le richieste SIP in arrivo per l'applicazione Parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="3e604-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-271">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-272">Servizio di test audio di Lync Server</span><span class="sxs-lookup"><span data-stu-id="3e604-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="3e604-273">5076</span><span class="sxs-lookup"><span data-stu-id="3e604-273">5076</span></span></p></td>
<td><p><span data-ttu-id="3e604-274">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-275">Utilizzata per le richieste SIP in arrivo per il servizio Test audio.</span><span class="sxs-lookup"><span data-stu-id="3e604-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-276">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-277">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="3e604-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="3e604-278">5066</span><span class="sxs-lookup"><span data-stu-id="3e604-278">5066</span></span></p></td>
<td><p><span data-ttu-id="3e604-279">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-280">Utilizzata per il gateway Enhanced 9-1-1 (E9-1-1) in uscita.</span><span class="sxs-lookup"><span data-stu-id="3e604-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-281">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-282">Servizio Response Group Lync Server</span><span class="sxs-lookup"><span data-stu-id="3e604-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="3e604-283">5071</span><span class="sxs-lookup"><span data-stu-id="3e604-283">5071</span></span></p></td>
<td><p><span data-ttu-id="3e604-284">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-285">Utilizzata per le richieste SIP in arrivo per l'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="3e604-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-286">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-287">Servizio Response Group Lync Server</span><span class="sxs-lookup"><span data-stu-id="3e604-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="3e604-288">8404</span><span class="sxs-lookup"><span data-stu-id="3e604-288">8404</span></span></p></td>
<td><p><span data-ttu-id="3e604-289">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="3e604-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="3e604-290">Utilizzata per le richieste SIP in arrivo per l'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="3e604-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-291">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-292">Servizio criteri larghezza di banda di Lync Server</span><span class="sxs-lookup"><span data-stu-id="3e604-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="3e604-293">5080</span><span class="sxs-lookup"><span data-stu-id="3e604-293">5080</span></span></p></td>
<td><p><span data-ttu-id="3e604-294">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-295">Utilizzata per il controllo di ammissione di chiamata eseguito dal servizio criteri larghezza di banda per il traffico A/V Edge TURN.</span><span class="sxs-lookup"><span data-stu-id="3e604-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-296">Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-297">Servizio criteri larghezza di banda di Lync Server</span><span class="sxs-lookup"><span data-stu-id="3e604-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="3e604-298">448</span><span class="sxs-lookup"><span data-stu-id="3e604-298">448</span></span></p></td>
<td><p><span data-ttu-id="3e604-299">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-300">Utilizzato per il controllo di ammissione di chiamata dal servizio criteri larghezza di banda di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e604-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-301">Server front end in cui si trova l'archivio di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="3e604-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="3e604-302">Servizio Agente di replica master di Lync Server</span><span class="sxs-lookup"><span data-stu-id="3e604-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="3e604-303">445</span><span class="sxs-lookup"><span data-stu-id="3e604-303">445</span></span></p></td>
<td><p><span data-ttu-id="3e604-304">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-305">Utilizzato per inviare i dati di configurazione dall'archivio di gestione centrale ai server che eseguono Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e604-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-306">Tutti i server</span><span class="sxs-lookup"><span data-stu-id="3e604-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-307">SQL Browser</span><span class="sxs-lookup"><span data-stu-id="3e604-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="3e604-308">1434</span><span class="sxs-lookup"><span data-stu-id="3e604-308">1434</span></span></p></td>
<td><p><span data-ttu-id="3e604-309">UDP</span><span class="sxs-lookup"><span data-stu-id="3e604-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="3e604-310">SQL browser per la copia locale replicata dei dati dell'archivio di gestione centrale nell'istanza locale di SQL Server</span><span class="sxs-lookup"><span data-stu-id="3e604-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-311">Tutti i server interni</span><span class="sxs-lookup"><span data-stu-id="3e604-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-312">Vari</span><span class="sxs-lookup"><span data-stu-id="3e604-312">Various</span></span></p></td>
<td><p><span data-ttu-id="3e604-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="3e604-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="3e604-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="3e604-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="3e604-315">Intervallo di porte multimediali utilizzato per le conferenze audio su tutti i server interni.</span><span class="sxs-lookup"><span data-stu-id="3e604-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="3e604-316">Utilizzato da tutti i server che terminano audio: Front End Server (per il servizio Operatore Conferenza di Lync Server, Lync Server Conferencing Service annuncio e Lync Server audio/video Conferencing Server) e Mediation.</span><span class="sxs-lookup"><span data-stu-id="3e604-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-317">Server Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="3e604-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e604-318">443</span><span class="sxs-lookup"><span data-stu-id="3e604-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e604-319">Utilizzato da Lync Server 2013 per la connessione al server Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="3e604-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-320">Amministrazione</span><span class="sxs-lookup"><span data-stu-id="3e604-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="3e604-321">Servizio front-end di Lync Server</span><span class="sxs-lookup"><span data-stu-id="3e604-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="3e604-322">5060</span><span class="sxs-lookup"><span data-stu-id="3e604-322">5060</span></span></p></td>
<td><p><span data-ttu-id="3e604-323">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-324">Utilizzata facoltativamente per le route statiche ai servizi trusted, come i server di controllo delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="3e604-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-325">Amministrazione</span><span class="sxs-lookup"><span data-stu-id="3e604-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="3e604-326">Servizio front-end di Lync Server</span><span class="sxs-lookup"><span data-stu-id="3e604-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="3e604-327">444</span><span class="sxs-lookup"><span data-stu-id="3e604-327">444</span></span></p></td>
<td><p><span data-ttu-id="3e604-328">HTTPS</span><span class="sxs-lookup"><span data-stu-id="3e604-328">HTTPS</span></span></p>
<p><span data-ttu-id="3e604-329">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-330">Comunicazioni interne ai server tra Front End e Director.</span><span class="sxs-lookup"><span data-stu-id="3e604-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="3e604-331">È inoltre possibile pubblicare il certificato client (nei Front End Server) o convalidare se il certificato client è già stato pubblicato.</span><span class="sxs-lookup"><span data-stu-id="3e604-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-332">Amministrazione</span><span class="sxs-lookup"><span data-stu-id="3e604-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="3e604-333">Lync Server Web Compatibility Service</span><span class="sxs-lookup"><span data-stu-id="3e604-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="3e604-334">80</span><span class="sxs-lookup"><span data-stu-id="3e604-334">80</span></span></p></td>
<td><p><span data-ttu-id="3e604-335">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-p105">Utilizzata per le comunicazioni iniziali dai Director ai nomi di dominio completo (FQDN) della Web farm (gli URL utilizzati dai componenti Web IIS). Durante il normale funzionamento, viene effettuato il passaggio al traffico HTTPS mediante la porta 443 e il tipo di protocollo TCP.</span><span class="sxs-lookup"><span data-stu-id="3e604-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-338">Amministrazione</span><span class="sxs-lookup"><span data-stu-id="3e604-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="3e604-339">Lync Server Web Compatibility Service</span><span class="sxs-lookup"><span data-stu-id="3e604-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="3e604-340">443</span><span class="sxs-lookup"><span data-stu-id="3e604-340">443</span></span></p></td>
<td><p><span data-ttu-id="3e604-341">HTTPS</span><span class="sxs-lookup"><span data-stu-id="3e604-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="3e604-342">Utilizzata per le comunicazioni dai Director ai nomi di dominio completi (FQDN) della Web farm (gli URL utilizzati dai componenti Web IIS).</span><span class="sxs-lookup"><span data-stu-id="3e604-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-343">Amministrazione</span><span class="sxs-lookup"><span data-stu-id="3e604-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="3e604-344">Servizio front-end di Lync Server</span><span class="sxs-lookup"><span data-stu-id="3e604-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="3e604-345">5061</span><span class="sxs-lookup"><span data-stu-id="3e604-345">5061</span></span></p></td>
<td><p><span data-ttu-id="3e604-346">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-347">Utilizzata per le comunicazioni interne tra i server e per le connessioni client.</span><span class="sxs-lookup"><span data-stu-id="3e604-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-348">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="3e604-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-349">Lync Server Mediation Service</span><span class="sxs-lookup"><span data-stu-id="3e604-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="3e604-350">5070</span><span class="sxs-lookup"><span data-stu-id="3e604-350">5070</span></span></p></td>
<td><p><span data-ttu-id="3e604-351">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-352">Utilizzata dal Mediation Server per le richieste in arrivo dal Front End Server.</span><span class="sxs-lookup"><span data-stu-id="3e604-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-353">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="3e604-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-354">Lync Server Mediation Service</span><span class="sxs-lookup"><span data-stu-id="3e604-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="3e604-355">5067</span><span class="sxs-lookup"><span data-stu-id="3e604-355">5067</span></span></p></td>
<td><p><span data-ttu-id="3e604-356">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="3e604-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="3e604-357">Utilizzata per le richieste SIP in arrivo dal gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="3e604-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-358">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="3e604-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-359">Lync Server Mediation Service</span><span class="sxs-lookup"><span data-stu-id="3e604-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="3e604-360">5068</span><span class="sxs-lookup"><span data-stu-id="3e604-360">5068</span></span></p></td>
<td><p><span data-ttu-id="3e604-361">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-362">Utilizzata per le richieste SIP in arrivo dal gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="3e604-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-363">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="3e604-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="3e604-364">Lync Server Mediation Service</span><span class="sxs-lookup"><span data-stu-id="3e604-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="3e604-365">5070</span><span class="sxs-lookup"><span data-stu-id="3e604-365">5070</span></span></p></td>
<td><p><span data-ttu-id="3e604-366">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="3e604-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="3e604-367">Utilizzata per le richieste SIP dai Front End Server.</span><span class="sxs-lookup"><span data-stu-id="3e604-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-368">Front End Server della chat persistente</span><span class="sxs-lookup"><span data-stu-id="3e604-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="3e604-369">SIP chat persistente</span><span class="sxs-lookup"><span data-stu-id="3e604-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="3e604-370">5041</span><span class="sxs-lookup"><span data-stu-id="3e604-370">5041</span></span></p></td>
<td><p><span data-ttu-id="3e604-371">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="3e604-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-372">Front End Server della chat persistente</span><span class="sxs-lookup"><span data-stu-id="3e604-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="3e604-373">Chat persistente Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="3e604-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="3e604-374">881</span><span class="sxs-lookup"><span data-stu-id="3e604-374">881</span></span></p></td>
<td><p><span data-ttu-id="3e604-375">TCP (TLS) e TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="3e604-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-376">Front End Server della chat persistente</span><span class="sxs-lookup"><span data-stu-id="3e604-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="3e604-377">Servizio di trasferimento file di chat persistente</span><span class="sxs-lookup"><span data-stu-id="3e604-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="3e604-378">443</span><span class="sxs-lookup"><span data-stu-id="3e604-378">443</span></span></p></td>
<td><p><span data-ttu-id="3e604-379">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="3e604-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="3e604-380">Alcuni scenari di controllo delle chiamate remote richiedono una connessione TCP tra il Front End Server o Director e il sistema PBX.</span><span class="sxs-lookup"><span data-stu-id="3e604-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="3e604-381">Anche se Lync Server non utilizza più la porta TCP 5060, durante la distribuzione del controllo delle chiamate remote viene creata una configurazione del server attendibile, che associa il nome di dominio completo del server RCC line alla porta TCP che verrà utilizzata dal front end server o dal Director per la connessione al sistema PBX.</span><span class="sxs-lookup"><span data-stu-id="3e604-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="3e604-382">Per informazioni dettagliate, vedere il cmdlet <STRONG>CsTrustedApplicationComputer</STRONG> nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3e604-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="3e604-383">Per i pool che utilizzano solo il servizio di bilanciamento del carico hardware (non il servizio di bilanciamento del carico DNS), la tabella che segue mostra le porte che devono aprire i servizi di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="3e604-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="3e604-384">Porte del servizio di bilanciamento del carico hardware se si utilizza solo questo servizio di bilanciamento</span><span class="sxs-lookup"><span data-stu-id="3e604-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e604-385">Servizio di bilanciamento del carico</span><span class="sxs-lookup"><span data-stu-id="3e604-385">Load Balancer</span></span></th>
<th><span data-ttu-id="3e604-386">Porta</span><span class="sxs-lookup"><span data-stu-id="3e604-386">Port</span></span></th>
<th><span data-ttu-id="3e604-387">Protocol</span><span class="sxs-lookup"><span data-stu-id="3e604-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e604-388">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="3e604-389">5061</span><span class="sxs-lookup"><span data-stu-id="3e604-389">5061</span></span></p></td>
<td><p><span data-ttu-id="3e604-390">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="3e604-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-391">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="3e604-392">444</span><span class="sxs-lookup"><span data-stu-id="3e604-392">444</span></span></p></td>
<td><p><span data-ttu-id="3e604-393">HTTPS</span><span class="sxs-lookup"><span data-stu-id="3e604-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-394">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="3e604-395">135</span><span class="sxs-lookup"><span data-stu-id="3e604-395">135</span></span></p></td>
<td><p><span data-ttu-id="3e604-396">DCOM ed RPC (Remote Procedure Call)</span><span class="sxs-lookup"><span data-stu-id="3e604-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-397">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="3e604-398">80</span><span class="sxs-lookup"><span data-stu-id="3e604-398">80</span></span></p></td>
<td><p><span data-ttu-id="3e604-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="3e604-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-400">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="3e604-401">8080</span><span class="sxs-lookup"><span data-stu-id="3e604-401">8080</span></span></p></td>
<td><p><span data-ttu-id="3e604-402">TCP - Recupero tramite client e dispositivi del certificato radice da Front End Server; client e dispositivi autenticati mediante NTLM</span><span class="sxs-lookup"><span data-stu-id="3e604-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-403">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="3e604-404">443</span><span class="sxs-lookup"><span data-stu-id="3e604-404">443</span></span></p></td>
<td><p><span data-ttu-id="3e604-405">HTTPS</span><span class="sxs-lookup"><span data-stu-id="3e604-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-406">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="3e604-407">4443</span><span class="sxs-lookup"><span data-stu-id="3e604-407">4443</span></span></p></td>
<td><p><span data-ttu-id="3e604-408">HTTPS (da proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="3e604-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-409">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="3e604-410">5072</span><span class="sxs-lookup"><span data-stu-id="3e604-410">5072</span></span></p></td>
<td><p><span data-ttu-id="3e604-411">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-412">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="3e604-413">5073</span><span class="sxs-lookup"><span data-stu-id="3e604-413">5073</span></span></p></td>
<td><p><span data-ttu-id="3e604-414">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-415">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="3e604-416">5075</span><span class="sxs-lookup"><span data-stu-id="3e604-416">5075</span></span></p></td>
<td><p><span data-ttu-id="3e604-417">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-418">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="3e604-419">5076</span><span class="sxs-lookup"><span data-stu-id="3e604-419">5076</span></span></p></td>
<td><p><span data-ttu-id="3e604-420">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-421">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="3e604-422">5071</span><span class="sxs-lookup"><span data-stu-id="3e604-422">5071</span></span></p></td>
<td><p><span data-ttu-id="3e604-423">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-424">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="3e604-425">5080</span><span class="sxs-lookup"><span data-stu-id="3e604-425">5080</span></span></p></td>
<td><p><span data-ttu-id="3e604-426">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-427">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="3e604-428">448</span><span class="sxs-lookup"><span data-stu-id="3e604-428">448</span></span></p></td>
<td><p><span data-ttu-id="3e604-429">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-430">Bilanciamento del carico di Mediation Server</span><span class="sxs-lookup"><span data-stu-id="3e604-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="3e604-431">5070</span><span class="sxs-lookup"><span data-stu-id="3e604-431">5070</span></span></p></td>
<td><p><span data-ttu-id="3e604-432">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-433">Bilanciamento del carico del server front-end (se il pool esegue anche Mediation Server)</span><span class="sxs-lookup"><span data-stu-id="3e604-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="3e604-434">5070</span><span class="sxs-lookup"><span data-stu-id="3e604-434">5070</span></span></p></td>
<td><p><span data-ttu-id="3e604-435">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-436">Servizio di bilanciamento del carico Director</span><span class="sxs-lookup"><span data-stu-id="3e604-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="3e604-437">443</span><span class="sxs-lookup"><span data-stu-id="3e604-437">443</span></span></p></td>
<td><p><span data-ttu-id="3e604-438">HTTPS</span><span class="sxs-lookup"><span data-stu-id="3e604-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-439">Servizio di bilanciamento del carico Director</span><span class="sxs-lookup"><span data-stu-id="3e604-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="3e604-440">444</span><span class="sxs-lookup"><span data-stu-id="3e604-440">444</span></span></p></td>
<td><p><span data-ttu-id="3e604-441">HTTPS</span><span class="sxs-lookup"><span data-stu-id="3e604-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-442">Servizio di bilanciamento del carico Director</span><span class="sxs-lookup"><span data-stu-id="3e604-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="3e604-443">5061</span><span class="sxs-lookup"><span data-stu-id="3e604-443">5061</span></span></p></td>
<td><p><span data-ttu-id="3e604-444">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-445">Servizio di bilanciamento del carico Director</span><span class="sxs-lookup"><span data-stu-id="3e604-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="3e604-446">4443</span><span class="sxs-lookup"><span data-stu-id="3e604-446">4443</span></span></p></td>
<td><p><span data-ttu-id="3e604-447">HTTPS (da proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="3e604-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3e604-p107">È necessario che anche nei pool Front End e server Director che utilizzano il servizio di bilanciamento del carico DNS sia distribuito un servizio di bilanciamento del carico hardware. Nella tabella che segue sono indicate le porte che è necessario aprire in questi servizi di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="3e604-p107">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed. The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="3e604-450">Porte del servizio di bilanciamento del carico hardware se si utilizza il servizio di bilanciamento del carico DNS</span><span class="sxs-lookup"><span data-stu-id="3e604-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e604-451">Servizio di bilanciamento del carico</span><span class="sxs-lookup"><span data-stu-id="3e604-451">Load Balancer</span></span></th>
<th><span data-ttu-id="3e604-452">Porta</span><span class="sxs-lookup"><span data-stu-id="3e604-452">Port</span></span></th>
<th><span data-ttu-id="3e604-453">Protocol</span><span class="sxs-lookup"><span data-stu-id="3e604-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e604-454">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="3e604-455">80</span><span class="sxs-lookup"><span data-stu-id="3e604-455">80</span></span></p></td>
<td><p><span data-ttu-id="3e604-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="3e604-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-457">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="3e604-458">443</span><span class="sxs-lookup"><span data-stu-id="3e604-458">443</span></span></p></td>
<td><p><span data-ttu-id="3e604-459">HTTPS</span><span class="sxs-lookup"><span data-stu-id="3e604-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-460">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="3e604-461">8080</span><span class="sxs-lookup"><span data-stu-id="3e604-461">8080</span></span></p></td>
<td><p><span data-ttu-id="3e604-462">TCP - Recupero tramite client e dispositivi del certificato radice da Front End Server; client e dispositivi autenticati mediante NTLM</span><span class="sxs-lookup"><span data-stu-id="3e604-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-463">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="3e604-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="3e604-464">4443</span><span class="sxs-lookup"><span data-stu-id="3e604-464">4443</span></span></p></td>
<td><p><span data-ttu-id="3e604-465">HTTPS (da proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="3e604-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-466">Servizio di bilanciamento del carico Director</span><span class="sxs-lookup"><span data-stu-id="3e604-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="3e604-467">443</span><span class="sxs-lookup"><span data-stu-id="3e604-467">443</span></span></p></td>
<td><p><span data-ttu-id="3e604-468">HTTPS</span><span class="sxs-lookup"><span data-stu-id="3e604-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-469">Servizio di bilanciamento del carico Director</span><span class="sxs-lookup"><span data-stu-id="3e604-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="3e604-470">4443</span><span class="sxs-lookup"><span data-stu-id="3e604-470">4443</span></span></p></td>
<td><p><span data-ttu-id="3e604-471">HTTPS (da proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="3e604-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="3e604-472">Porte client richieste</span><span class="sxs-lookup"><span data-stu-id="3e604-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e604-473">Componente</span><span class="sxs-lookup"><span data-stu-id="3e604-473">Component</span></span></th>
<th><span data-ttu-id="3e604-474">Porta</span><span class="sxs-lookup"><span data-stu-id="3e604-474">Port</span></span></th>
<th><span data-ttu-id="3e604-475">Protocol</span><span class="sxs-lookup"><span data-stu-id="3e604-475">Protocol</span></span></th>
<th><span data-ttu-id="3e604-476">Notes</span><span class="sxs-lookup"><span data-stu-id="3e604-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e604-477">Client</span><span class="sxs-lookup"><span data-stu-id="3e604-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="3e604-478">67/68</span><span class="sxs-lookup"><span data-stu-id="3e604-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="3e604-479">DHCP</span><span class="sxs-lookup"><span data-stu-id="3e604-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-480">Utilizzato da Lync Server per individuare il nome di dominio completo del registrar, ovvero se DNS SRV ha esito negativo e le impostazioni manuali non sono configurate.</span><span class="sxs-lookup"><span data-stu-id="3e604-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-481">Client</span><span class="sxs-lookup"><span data-stu-id="3e604-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="3e604-482">443</span><span class="sxs-lookup"><span data-stu-id="3e604-482">443</span></span></p></td>
<td><p><span data-ttu-id="3e604-483">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="3e604-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="3e604-484">Utilizzata per il traffico SIP da client a server per l'accesso utente esterno.</span><span class="sxs-lookup"><span data-stu-id="3e604-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-485">Client</span><span class="sxs-lookup"><span data-stu-id="3e604-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="3e604-486">443</span><span class="sxs-lookup"><span data-stu-id="3e604-486">443</span></span></p></td>
<td><p><span data-ttu-id="3e604-487">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="3e604-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="3e604-488">Utilizzata per l'accesso utente esterno alle sessioni di Web Conferencing.</span><span class="sxs-lookup"><span data-stu-id="3e604-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-489">Client</span><span class="sxs-lookup"><span data-stu-id="3e604-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="3e604-490">443</span><span class="sxs-lookup"><span data-stu-id="3e604-490">443</span></span></p></td>
<td><p><span data-ttu-id="3e604-491">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="3e604-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="3e604-492">Utilizzata per l'accesso utente esterno alle sessioni A/V e ai supporti multimediali (TCP)</span><span class="sxs-lookup"><span data-stu-id="3e604-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-493">Client</span><span class="sxs-lookup"><span data-stu-id="3e604-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="3e604-494">3478</span><span class="sxs-lookup"><span data-stu-id="3e604-494">3478</span></span></p></td>
<td><p><span data-ttu-id="3e604-495">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="3e604-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="3e604-496">Utilizzato per l'accesso degli utenti esterni alle sessioni A/V e ai supporti (UDP)</span><span class="sxs-lookup"><span data-stu-id="3e604-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-497">Client</span><span class="sxs-lookup"><span data-stu-id="3e604-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="3e604-498">5061</span><span class="sxs-lookup"><span data-stu-id="3e604-498">5061</span></span></p></td>
<td><p><span data-ttu-id="3e604-499">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="3e604-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="3e604-500">Utilizzata per il traffico SIP da client a server per l'accesso utente esterno.</span><span class="sxs-lookup"><span data-stu-id="3e604-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-501">Client</span><span class="sxs-lookup"><span data-stu-id="3e604-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="3e604-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="3e604-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="3e604-503">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-504">Utilizzato per il trasferimento di file tra client Lync e client precedenti (client di Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 e Live Communications Server 2005).</span><span class="sxs-lookup"><span data-stu-id="3e604-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-505">Client</span><span class="sxs-lookup"><span data-stu-id="3e604-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="3e604-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="3e604-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="3e604-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="3e604-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="3e604-508">Intervallo di porte audio (almeno 20 porte richieste)</span><span class="sxs-lookup"><span data-stu-id="3e604-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-509">Client</span><span class="sxs-lookup"><span data-stu-id="3e604-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="3e604-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="3e604-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="3e604-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="3e604-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="3e604-512">Intervallo di porte video (almeno 20 porte richieste).</span><span class="sxs-lookup"><span data-stu-id="3e604-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-513">Client</span><span class="sxs-lookup"><span data-stu-id="3e604-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="3e604-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="3e604-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="3e604-515">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-516">Trasferimento file peer-to-peer (per il trasferimento dei file del servizio di conferenza, i client utilizzano PSOM).</span><span class="sxs-lookup"><span data-stu-id="3e604-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e604-517">Client</span><span class="sxs-lookup"><span data-stu-id="3e604-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="3e604-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="3e604-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="3e604-519">TCP</span><span class="sxs-lookup"><span data-stu-id="3e604-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-520">Condivisione applicazioni.</span><span class="sxs-lookup"><span data-stu-id="3e604-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e604-521">Telefono di area comune Aastra 6721ip</span><span class="sxs-lookup"><span data-stu-id="3e604-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="3e604-522">Telefono da tavolo Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="3e604-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="3e604-523">Telefono IP HP 4110 (telefono di area comune)</span><span class="sxs-lookup"><span data-stu-id="3e604-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="3e604-524">Telefono IP HP 4120 (telefono da tavolo)</span><span class="sxs-lookup"><span data-stu-id="3e604-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="3e604-525">Telefono di area comune IP Polycom CX500</span><span class="sxs-lookup"><span data-stu-id="3e604-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="3e604-526">Telefono da tavolo IP Polycom CX600</span><span class="sxs-lookup"><span data-stu-id="3e604-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="3e604-527">Telefono da tavolo IP Polycom CX700</span><span class="sxs-lookup"><span data-stu-id="3e604-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="3e604-528">Telefono IP per conferenze Polycom CX3000</span><span class="sxs-lookup"><span data-stu-id="3e604-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="3e604-529">67/68</span><span class="sxs-lookup"><span data-stu-id="3e604-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="3e604-530">DHCP</span><span class="sxs-lookup"><span data-stu-id="3e604-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="3e604-531">Utilizzato dai dispositivi elencati per individuare il certificato di Lync Server, il nome di dominio completo e il nome di dominio completo del servizio di registrazione.</span><span class="sxs-lookup"><span data-stu-id="3e604-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3e604-532">**\*** Per configurare porte specifiche per questi tipi di supporti, utilizzare il cmdlet CsConferencingConfiguration (parametri ClientMediaPortRangeEnabled, ClientMediaPort e ClientMediaPortRange).</span><span class="sxs-lookup"><span data-stu-id="3e604-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3e604-533">I programmi set per i client di Lync creano automaticamente le eccezioni del firewall del sistema operativo necessarie sul computer client.</span><span class="sxs-lookup"><span data-stu-id="3e604-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="3e604-534">Le porte utilizzate per l'accesso utente esterno sono richieste per tutti gli scenari in cui il client deve attraversare il firewall dell'organizzazione, ad esempio per qualsiasi comunicazione o riunione esterna ospitata da altre organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="3e604-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

