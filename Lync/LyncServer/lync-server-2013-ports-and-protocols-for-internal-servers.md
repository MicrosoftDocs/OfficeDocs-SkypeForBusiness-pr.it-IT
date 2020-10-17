---
title: 'Lync Server 2013: porte e protocolli per i server interni'
description: 'Lync Server 2013: porte e protocolli per i server interni.'
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
ms.openlocfilehash: d7d8f12c78c5dec5caacaeb1156f4d228b7cd591
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566357"
---
# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="f24eb-103">Porte e protocolli per i server interni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f24eb-103">Ports and protocols for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f24eb-104">_**Ultimo argomento modificato:** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="f24eb-104">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="f24eb-105">In questa sezione vengono riepilogate le porte e i protocolli utilizzati dai server, dai bilanciamento del carico e dai client in una distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f24eb-105">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f24eb-106">I client Lync e Communicator quando sono coinvolti in una comunicazione One to One, vengono spesso definiti peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="f24eb-106">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="f24eb-107">Tecnicamente, i due client stanno comunicando in una conversazione One to One, con la Central Messaging Multipoint Control Unit (IMMCU) al centro.</span><span class="sxs-lookup"><span data-stu-id="f24eb-107">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="f24eb-108">IMMCU è un componente di front end server.</span><span class="sxs-lookup"><span data-stu-id="f24eb-108">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="f24eb-109">L'inserimento di IMMCU nel flusso di lavoro di comunicazione necessario consente di abilitare la registrazione dettagli chiamata e altre caratteristiche abilitate dal front end server.</span><span class="sxs-lookup"><span data-stu-id="f24eb-109">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="f24eb-110">La comunicazione è da una porta di origine dinamica sul client alla porta del server front-end TLS/TCP/5061 (presupponendo l'utilizzo della sicurezza del layer di trasporto consigliato).</span><span class="sxs-lookup"><span data-stu-id="f24eb-110">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="f24eb-111">In base alla progettazione, la comunicazione peer-to-peer (così come la messaggistica istantanea a più parti) è possibile solo quando Lync Server e IMMCU sono attivi e disponibili.</span><span class="sxs-lookup"><span data-stu-id="f24eb-111">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="f24eb-112">Informazioni dettagliate sulle porte e sui protocolli</span><span class="sxs-lookup"><span data-stu-id="f24eb-112">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f24eb-113">È necessario che Windows Firewall sia in esecuzione prima di avviare i servizi di Lync Server in un server, perché in questo caso Lync Server apre le porte necessarie nel firewall.</span><span class="sxs-lookup"><span data-stu-id="f24eb-113">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="f24eb-114">Per informazioni dettagliate sulla configurazione del firewall per i componenti perimetrali, vedere [Determine External A/V firewall and Port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f24eb-114">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="f24eb-115">Nella tabella seguente sono elencate le porte che è necessario aprire per ogni ruolo server interno.</span><span class="sxs-lookup"><span data-stu-id="f24eb-115">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="f24eb-116">Porte server richieste (per ruolo server)</span><span class="sxs-lookup"><span data-stu-id="f24eb-116">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="f24eb-117">Ruolo server</span><span class="sxs-lookup"><span data-stu-id="f24eb-117">Server role</span></span></th>
<th><span data-ttu-id="f24eb-118">Nome servizio</span><span class="sxs-lookup"><span data-stu-id="f24eb-118">Service name</span></span></th>
<th><span data-ttu-id="f24eb-119">Porta</span><span class="sxs-lookup"><span data-stu-id="f24eb-119">Port</span></span></th>
<th><span data-ttu-id="f24eb-120">Protocollo</span><span class="sxs-lookup"><span data-stu-id="f24eb-120">Protocol</span></span></th>
<th><span data-ttu-id="f24eb-121">Note</span><span class="sxs-lookup"><span data-stu-id="f24eb-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-122">Tutti i server</span><span class="sxs-lookup"><span data-stu-id="f24eb-122">All Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-123">SQL Browser</span><span class="sxs-lookup"><span data-stu-id="f24eb-123">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="f24eb-124">1434</span><span class="sxs-lookup"><span data-stu-id="f24eb-124">1434</span></span></p></td>
<td><p><span data-ttu-id="f24eb-125">UDP</span><span class="sxs-lookup"><span data-stu-id="f24eb-125">UDP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-126">Browser SQL per la copia locale replicata del database dell'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="f24eb-126">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-127">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-127">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-128">Servizio Front-End di Lync Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-128">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-129">5060</span><span class="sxs-lookup"><span data-stu-id="f24eb-129">5060</span></span></p></td>
<td><p><span data-ttu-id="f24eb-130">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-130">TCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-131">Utilizzata facoltativamente dai server Standard Edition e dai Front End Server per le route statiche ai servizi trusted, ad esempio i server di controllo delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="f24eb-131">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-132">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-132">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-133">Servizio Front-End di Lync Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-133">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-134">5061</span><span class="sxs-lookup"><span data-stu-id="f24eb-134">5061</span></span></p></td>
<td><p><span data-ttu-id="f24eb-135">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f24eb-135">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="f24eb-p102">Utilizzata dai server Standard Edition e dai pool Front End per tutte le comunicazioni SIP interne tra i server (MTLS), per le comunicazioni SIP tra Server e Client (TLS), per le comunicazioni SIP tra Front End Server e Mediation Server (MTLS), nonché per le comunicazioni con Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="f24eb-p102">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS). Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-138">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-138">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-139">Servizio Front-End di Lync Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-139">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-140">444</span><span class="sxs-lookup"><span data-stu-id="f24eb-140">444</span></span></p></td>
<td><p><span data-ttu-id="f24eb-141">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f24eb-141">HTTPS</span></span></p>
<p><span data-ttu-id="f24eb-142">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-142">TCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-143">Utilizzato per la comunicazione HTTPS tra lo stato attivo (il componente Lync Server che gestisce lo stato delle conferenze) e i singoli server.</span><span class="sxs-lookup"><span data-stu-id="f24eb-143">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="f24eb-144">Questa porta viene utilizzata anche per le comunicazioni TCP tra Survivable Branch Appliances e front end server.</span><span class="sxs-lookup"><span data-stu-id="f24eb-144">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-145">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-145">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-146">Servizio Front-End di Lync Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-146">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-147">135</span><span class="sxs-lookup"><span data-stu-id="f24eb-147">135</span></span></p></td>
<td><p><span data-ttu-id="f24eb-148">DCOM e RPC (Remote Procedure Call)</span><span class="sxs-lookup"><span data-stu-id="f24eb-148">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="f24eb-149">Utilizzata per le operazioni basate su DCOM quali spostamento utenti, sincronizzazione User Replicator e sincronizzazione rubrica.</span><span class="sxs-lookup"><span data-stu-id="f24eb-149">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-150">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-150">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-151">Lync Server IM Service Conferencing</span><span class="sxs-lookup"><span data-stu-id="f24eb-151">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-152">5062</span><span class="sxs-lookup"><span data-stu-id="f24eb-152">5062</span></span></p></td>
<td><p><span data-ttu-id="f24eb-153">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-153">TCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-154">Utilizzata per le richieste SIP in arrivo per le conferenze di messaggistica istantanea (IM).</span><span class="sxs-lookup"><span data-stu-id="f24eb-154">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-155">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-155">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-156">Servizio Web Conferencing di Lync Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-156">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-157">8057</span><span class="sxs-lookup"><span data-stu-id="f24eb-157">8057</span></span></p></td>
<td><p><span data-ttu-id="f24eb-158">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f24eb-158">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="f24eb-159">Utilizzata per attendere le connessioni PSOM (Persistent Shared Object Model) dal client.</span><span class="sxs-lookup"><span data-stu-id="f24eb-159">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-160">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-160">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-161">Lync Server Web Conferencing Compatibility Service</span><span class="sxs-lookup"><span data-stu-id="f24eb-161">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-162">8058</span><span class="sxs-lookup"><span data-stu-id="f24eb-162">8058</span></span></p></td>
<td><p><span data-ttu-id="f24eb-163">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f24eb-163">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="f24eb-164">Utilizzato per l'attesa per le connessioni PSOM (Persistent Shared Object Model) dal client Live Meeting e le versioni precedenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f24eb-164">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-165">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-165">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-166">Lync Server audio/video Conferencing Service</span><span class="sxs-lookup"><span data-stu-id="f24eb-166">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-167">5063</span><span class="sxs-lookup"><span data-stu-id="f24eb-167">5063</span></span></p></td>
<td><p><span data-ttu-id="f24eb-168">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-168">TCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-169">Utilizzata per le richieste SIP in arrivo per Audio/Video (A/V) Conferencing.</span><span class="sxs-lookup"><span data-stu-id="f24eb-169">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-170">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-170">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-171">Lync Server audio/video Conferencing Service</span><span class="sxs-lookup"><span data-stu-id="f24eb-171">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-172">57501-65535</span><span class="sxs-lookup"><span data-stu-id="f24eb-172">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="f24eb-173">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="f24eb-173">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-174">Intervallo di porte di attesa multimediali utilizzato per le conferenze video.</span><span class="sxs-lookup"><span data-stu-id="f24eb-174">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-175">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-176">Lync Server Web Compatibility Service</span><span class="sxs-lookup"><span data-stu-id="f24eb-176">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-177">80</span><span class="sxs-lookup"><span data-stu-id="f24eb-177">80</span></span></p></td>
<td><p><span data-ttu-id="f24eb-178">HTTP</span><span class="sxs-lookup"><span data-stu-id="f24eb-178">HTTP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-179">Utilizzata per le comunicazioni dai Front End Server ai nomi di dominio completi della Web farm (gli URL utilizzati dai componenti Web IIS) quando non si utilizzano protocolli HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f24eb-179">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-180">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-180">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-181">Lync Server Web Compatibility Service</span><span class="sxs-lookup"><span data-stu-id="f24eb-181">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-182">443</span><span class="sxs-lookup"><span data-stu-id="f24eb-182">443</span></span></p></td>
<td><p><span data-ttu-id="f24eb-183">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f24eb-183">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="f24eb-184">Utilizzata per le comunicazioni dai Front End Server ai nomi di dominio completi della Web farm (gli URL utilizzati dai componenti Web IIS).</span><span class="sxs-lookup"><span data-stu-id="f24eb-184">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-185">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-185">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-186">Lync Server Web Compatibility Service</span><span class="sxs-lookup"><span data-stu-id="f24eb-186">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-187">8080</span><span class="sxs-lookup"><span data-stu-id="f24eb-187">8080</span></span></p></td>
<td><p><span data-ttu-id="f24eb-188">TCP e HTTP</span><span class="sxs-lookup"><span data-stu-id="f24eb-188">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-189">Utilizzato dai componenti Web per l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="f24eb-189">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-190">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-190">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-191">Componente del server Web</span><span class="sxs-lookup"><span data-stu-id="f24eb-191">Web server component</span></span></p></td>
<td><p><span data-ttu-id="f24eb-192">4443</span><span class="sxs-lookup"><span data-stu-id="f24eb-192">4443</span></span></p></td>
<td><p><span data-ttu-id="f24eb-193">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f24eb-193">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="f24eb-194">HTTPS (da proxy inverso) e comunicazioni inter-pool HTTPS front-end per l'accesso all'individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="f24eb-194">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-195">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-195">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-196">Componente del server Web</span><span class="sxs-lookup"><span data-stu-id="f24eb-196">Web server component</span></span></p></td>
<td><p><span data-ttu-id="f24eb-197">8060</span><span class="sxs-lookup"><span data-stu-id="f24eb-197">8060</span></span></p></td>
<td><p><span data-ttu-id="f24eb-198">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f24eb-198">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-199">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-199">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-200">Componente del server Web</span><span class="sxs-lookup"><span data-stu-id="f24eb-200">Web server component</span></span></p></td>
<td><p><span data-ttu-id="f24eb-201">8061</span><span class="sxs-lookup"><span data-stu-id="f24eb-201">8061</span></span></p></td>
<td><p><span data-ttu-id="f24eb-202">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f24eb-202">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-203">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-203">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-204">Componente dei servizi per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="f24eb-204">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="f24eb-205">5086</span><span class="sxs-lookup"><span data-stu-id="f24eb-205">5086</span></span></p></td>
<td><p><span data-ttu-id="f24eb-206">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f24eb-206">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="f24eb-207">Porta SIP utilizzata dai processi interni dei servizi per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="f24eb-207">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-208">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-208">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-209">Componente dei servizi per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="f24eb-209">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="f24eb-210">5087</span><span class="sxs-lookup"><span data-stu-id="f24eb-210">5087</span></span></p></td>
<td><p><span data-ttu-id="f24eb-211">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f24eb-211">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="f24eb-212">Porta SIP utilizzata dai processi interni dei servizi per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="f24eb-212">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-213">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-213">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-214">Componente dei servizi per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="f24eb-214">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="f24eb-215">443</span><span class="sxs-lookup"><span data-stu-id="f24eb-215">443</span></span></p></td>
<td><p><span data-ttu-id="f24eb-216">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f24eb-216">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-217">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-217">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-218">Servizio Operatore Conferenza di Lync Server (servizi di conferenza telefonica con accesso esterno)</span><span class="sxs-lookup"><span data-stu-id="f24eb-218">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="f24eb-219">5064</span><span class="sxs-lookup"><span data-stu-id="f24eb-219">5064</span></span></p></td>
<td><p><span data-ttu-id="f24eb-220">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-220">TCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-221">Utilizzata per le richieste SIP in arrivo per le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="f24eb-221">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-222">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-222">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-223">Servizio Operatore Conferenza di Lync Server (servizi di conferenza telefonica con accesso esterno)</span><span class="sxs-lookup"><span data-stu-id="f24eb-223">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="f24eb-224">5072</span><span class="sxs-lookup"><span data-stu-id="f24eb-224">5072</span></span></p></td>
<td><p><span data-ttu-id="f24eb-225">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-225">TCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-226">Utilizzato per le richieste SIP in arrivo per Attendant (servizi di conferenza telefonica con accesso esterno).</span><span class="sxs-lookup"><span data-stu-id="f24eb-226">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-227">Front End Server che eseguono anche un Mediation Server collocato</span><span class="sxs-lookup"><span data-stu-id="f24eb-227">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="f24eb-228">Lync Server Mediation Service</span><span class="sxs-lookup"><span data-stu-id="f24eb-228">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-229">5070</span><span class="sxs-lookup"><span data-stu-id="f24eb-229">5070</span></span></p></td>
<td><p><span data-ttu-id="f24eb-230">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-230">TCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-231">Utilizzata dal Mediation Server per le richieste in arrivo dal Front End Server al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="f24eb-231">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-232">Front End Server che eseguono anche un Mediation Server collocato</span><span class="sxs-lookup"><span data-stu-id="f24eb-232">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="f24eb-233">Lync Server Mediation Service</span><span class="sxs-lookup"><span data-stu-id="f24eb-233">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-234">5067</span><span class="sxs-lookup"><span data-stu-id="f24eb-234">5067</span></span></p></td>
<td><p><span data-ttu-id="f24eb-235">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f24eb-235">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="f24eb-236">Utilizzata per le richieste SIP in arrivo dal gateway PSTN al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="f24eb-236">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-237">Front End Server che eseguono anche un Mediation Server collocato</span><span class="sxs-lookup"><span data-stu-id="f24eb-237">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="f24eb-238">Lync Server Mediation Service</span><span class="sxs-lookup"><span data-stu-id="f24eb-238">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-239">5068</span><span class="sxs-lookup"><span data-stu-id="f24eb-239">5068</span></span></p></td>
<td><p><span data-ttu-id="f24eb-240">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-240">TCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-241">Utilizzata per le richieste SIP in arrivo dal gateway PSTN al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="f24eb-241">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-242">Front End Server che eseguono anche un Mediation Server collocato</span><span class="sxs-lookup"><span data-stu-id="f24eb-242">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="f24eb-243">Lync Server Mediation Service</span><span class="sxs-lookup"><span data-stu-id="f24eb-243">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-244">5081</span><span class="sxs-lookup"><span data-stu-id="f24eb-244">5081</span></span></p></td>
<td><p><span data-ttu-id="f24eb-245">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-245">TCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-246">Utilizzata per le richieste SIP in uscita dal Mediation Server al gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="f24eb-246">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-247">Front End Server che eseguono anche un Mediation Server collocato</span><span class="sxs-lookup"><span data-stu-id="f24eb-247">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="f24eb-248">Lync Server Mediation Service</span><span class="sxs-lookup"><span data-stu-id="f24eb-248">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-249">5082</span><span class="sxs-lookup"><span data-stu-id="f24eb-249">5082</span></span></p></td>
<td><p><span data-ttu-id="f24eb-250">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f24eb-250">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="f24eb-251">Utilizzata per le richieste SIP in uscita dal Mediation Server al gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="f24eb-251">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-252">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-252">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-253">Servizio di condivisione applicazioni di Lync Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-253">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-254">5065</span><span class="sxs-lookup"><span data-stu-id="f24eb-254">5065</span></span></p></td>
<td><p><span data-ttu-id="f24eb-255">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-255">TCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-256">Utilizzata per le richieste di attesa SIP in arrivo per la condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="f24eb-256">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-257">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-257">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-258">Servizio di condivisione applicazioni di Lync Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-258">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-259">49152-65535</span><span class="sxs-lookup"><span data-stu-id="f24eb-259">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="f24eb-260">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-260">TCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-261">Intervallo di porte di attesa multimediali per la condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="f24eb-261">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-262">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-262">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-263">Servizio annuncio di Lync Server Conferencing</span><span class="sxs-lookup"><span data-stu-id="f24eb-263">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-264">5073</span><span class="sxs-lookup"><span data-stu-id="f24eb-264">5073</span></span></p></td>
<td><p><span data-ttu-id="f24eb-265">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-265">TCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-266">Utilizzato per le richieste SIP in arrivo per il servizio annuncio di Lync Server Conferencing, ovvero per le conferenze telefoniche con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="f24eb-266">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-267">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-267">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-268">Servizio Parcheggio di chiamata Lync Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-268">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-269">5075</span><span class="sxs-lookup"><span data-stu-id="f24eb-269">5075</span></span></p></td>
<td><p><span data-ttu-id="f24eb-270">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-270">TCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-271">Utilizzata per le richieste SIP in arrivo per l'applicazione Parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="f24eb-271">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-272">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-272">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-273">Servizio di test audio di Lync Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-273">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-274">5076</span><span class="sxs-lookup"><span data-stu-id="f24eb-274">5076</span></span></p></td>
<td><p><span data-ttu-id="f24eb-275">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-275">TCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-276">Utilizzata per le richieste SIP in arrivo per il servizio Test audio.</span><span class="sxs-lookup"><span data-stu-id="f24eb-276">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-277">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-277">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-278">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="f24eb-278">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="f24eb-279">5066</span><span class="sxs-lookup"><span data-stu-id="f24eb-279">5066</span></span></p></td>
<td><p><span data-ttu-id="f24eb-280">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-280">TCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-281">Utilizzata per il gateway Enhanced 9-1-1 (E9-1-1) in uscita.</span><span class="sxs-lookup"><span data-stu-id="f24eb-281">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-282">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-282">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-283">Servizio Response Group Lync Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-283">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-284">5071</span><span class="sxs-lookup"><span data-stu-id="f24eb-284">5071</span></span></p></td>
<td><p><span data-ttu-id="f24eb-285">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-285">TCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-286">Utilizzata per le richieste SIP in arrivo per l'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="f24eb-286">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-287">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-287">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-288">Servizio Response Group Lync Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-288">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-289">8404</span><span class="sxs-lookup"><span data-stu-id="f24eb-289">8404</span></span></p></td>
<td><p><span data-ttu-id="f24eb-290">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f24eb-290">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="f24eb-291">Utilizzata per le richieste SIP in arrivo per l'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="f24eb-291">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-292">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-292">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-293">Servizio criteri larghezza di banda di Lync Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-293">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-294">5080</span><span class="sxs-lookup"><span data-stu-id="f24eb-294">5080</span></span></p></td>
<td><p><span data-ttu-id="f24eb-295">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-295">TCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-296">Utilizzata per il controllo di ammissione di chiamata eseguito dal servizio criteri larghezza di banda per il traffico A/V Edge TURN.</span><span class="sxs-lookup"><span data-stu-id="f24eb-296">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-297">Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-297">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-298">Servizio criteri larghezza di banda di Lync Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-298">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-299">448</span><span class="sxs-lookup"><span data-stu-id="f24eb-299">448</span></span></p></td>
<td><p><span data-ttu-id="f24eb-300">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-300">TCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-301">Utilizzato per il controllo di ammissione di chiamata dal servizio criteri larghezza di banda di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f24eb-301">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-302">Server front end in cui si trova l'archivio di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="f24eb-302">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="f24eb-303">Servizio Agente di replica master di Lync Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-303">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-304">445</span><span class="sxs-lookup"><span data-stu-id="f24eb-304">445</span></span></p></td>
<td><p><span data-ttu-id="f24eb-305">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-305">TCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-306">Utilizzato per inviare i dati di configurazione dall'archivio di gestione centrale ai server che eseguono Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f24eb-306">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-307">Tutti i server</span><span class="sxs-lookup"><span data-stu-id="f24eb-307">All Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-308">SQL Browser</span><span class="sxs-lookup"><span data-stu-id="f24eb-308">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="f24eb-309">1434</span><span class="sxs-lookup"><span data-stu-id="f24eb-309">1434</span></span></p></td>
<td><p><span data-ttu-id="f24eb-310">UDP</span><span class="sxs-lookup"><span data-stu-id="f24eb-310">UDP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-311">SQL browser per la copia locale replicata dei dati dell'archivio di gestione centrale nell'istanza locale di SQL Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-311">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-312">Tutti i server interni</span><span class="sxs-lookup"><span data-stu-id="f24eb-312">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-313">Vari</span><span class="sxs-lookup"><span data-stu-id="f24eb-313">Various</span></span></p></td>
<td><p><span data-ttu-id="f24eb-314">49152-57500</span><span class="sxs-lookup"><span data-stu-id="f24eb-314">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="f24eb-315">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="f24eb-315">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-316">Intervallo di porte multimediali utilizzato per le conferenze audio su tutti i server interni.</span><span class="sxs-lookup"><span data-stu-id="f24eb-316">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="f24eb-317">Utilizzato da tutti i server che terminano audio: Front End Server (per il servizio Operatore Conferenza di Lync Server, Lync Server Conferencing Service annuncio e Lync Server audio/video Conferencing Server) e Mediation.</span><span class="sxs-lookup"><span data-stu-id="f24eb-317">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-318">Server Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="f24eb-318">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f24eb-319">443</span><span class="sxs-lookup"><span data-stu-id="f24eb-319">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f24eb-320">Utilizzato da Lync Server 2013 per la connessione al server Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="f24eb-320">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-321">Amministrazione</span><span class="sxs-lookup"><span data-stu-id="f24eb-321">Directors</span></span></p></td>
<td><p><span data-ttu-id="f24eb-322">Servizio Front-End di Lync Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-322">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-323">5060</span><span class="sxs-lookup"><span data-stu-id="f24eb-323">5060</span></span></p></td>
<td><p><span data-ttu-id="f24eb-324">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-324">TCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-325">Utilizzata facoltativamente per le route statiche ai servizi trusted, come i server di controllo delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="f24eb-325">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-326">Amministrazione</span><span class="sxs-lookup"><span data-stu-id="f24eb-326">Directors</span></span></p></td>
<td><p><span data-ttu-id="f24eb-327">Servizio Front-End di Lync Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-327">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-328">444</span><span class="sxs-lookup"><span data-stu-id="f24eb-328">444</span></span></p></td>
<td><p><span data-ttu-id="f24eb-329">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f24eb-329">HTTPS</span></span></p>
<p><span data-ttu-id="f24eb-330">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-330">TCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-331">Comunicazioni interne ai server tra Front End e Director.</span><span class="sxs-lookup"><span data-stu-id="f24eb-331">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="f24eb-332">È inoltre possibile pubblicare il certificato client (nei Front End Server) o convalidare se il certificato client è già stato pubblicato.</span><span class="sxs-lookup"><span data-stu-id="f24eb-332">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-333">Amministrazione</span><span class="sxs-lookup"><span data-stu-id="f24eb-333">Directors</span></span></p></td>
<td><p><span data-ttu-id="f24eb-334">Lync Server Web Compatibility Service</span><span class="sxs-lookup"><span data-stu-id="f24eb-334">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-335">80</span><span class="sxs-lookup"><span data-stu-id="f24eb-335">80</span></span></p></td>
<td><p><span data-ttu-id="f24eb-336">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-336">TCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-p105">Utilizzata per le comunicazioni iniziali dai Director ai nomi di dominio completo (FQDN) della Web farm (gli URL utilizzati dai componenti Web IIS). Durante il normale funzionamento, viene effettuato il passaggio al traffico HTTPS mediante la porta 443 e il tipo di protocollo TCP.</span><span class="sxs-lookup"><span data-stu-id="f24eb-p105">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components). In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-339">Amministrazione</span><span class="sxs-lookup"><span data-stu-id="f24eb-339">Directors</span></span></p></td>
<td><p><span data-ttu-id="f24eb-340">Lync Server Web Compatibility Service</span><span class="sxs-lookup"><span data-stu-id="f24eb-340">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-341">443</span><span class="sxs-lookup"><span data-stu-id="f24eb-341">443</span></span></p></td>
<td><p><span data-ttu-id="f24eb-342">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f24eb-342">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="f24eb-343">Utilizzata per le comunicazioni dai Director ai nomi di dominio completi (FQDN) della Web farm (gli URL utilizzati dai componenti Web IIS).</span><span class="sxs-lookup"><span data-stu-id="f24eb-343">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-344">Amministrazione</span><span class="sxs-lookup"><span data-stu-id="f24eb-344">Directors</span></span></p></td>
<td><p><span data-ttu-id="f24eb-345">Servizio Front-End di Lync Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-345">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-346">5061</span><span class="sxs-lookup"><span data-stu-id="f24eb-346">5061</span></span></p></td>
<td><p><span data-ttu-id="f24eb-347">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-347">TCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-348">Utilizzata per le comunicazioni interne tra i server e per le connessioni client.</span><span class="sxs-lookup"><span data-stu-id="f24eb-348">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-349">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-349">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-350">Lync Server Mediation Service</span><span class="sxs-lookup"><span data-stu-id="f24eb-350">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-351">5070</span><span class="sxs-lookup"><span data-stu-id="f24eb-351">5070</span></span></p></td>
<td><p><span data-ttu-id="f24eb-352">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-352">TCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-353">Utilizzata dal Mediation Server per le richieste in arrivo dal Front End Server.</span><span class="sxs-lookup"><span data-stu-id="f24eb-353">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-354">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-354">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-355">Lync Server Mediation Service</span><span class="sxs-lookup"><span data-stu-id="f24eb-355">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-356">5067</span><span class="sxs-lookup"><span data-stu-id="f24eb-356">5067</span></span></p></td>
<td><p><span data-ttu-id="f24eb-357">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f24eb-357">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="f24eb-358">Utilizzata per le richieste SIP in arrivo dal gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="f24eb-358">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-359">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-359">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-360">Lync Server Mediation Service</span><span class="sxs-lookup"><span data-stu-id="f24eb-360">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-361">5068</span><span class="sxs-lookup"><span data-stu-id="f24eb-361">5068</span></span></p></td>
<td><p><span data-ttu-id="f24eb-362">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-362">TCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-363">Utilizzata per le richieste SIP in arrivo dal gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="f24eb-363">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-364">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-364">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="f24eb-365">Lync Server Mediation Service</span><span class="sxs-lookup"><span data-stu-id="f24eb-365">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-366">5070</span><span class="sxs-lookup"><span data-stu-id="f24eb-366">5070</span></span></p></td>
<td><p><span data-ttu-id="f24eb-367">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f24eb-367">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="f24eb-368">Utilizzata per le richieste SIP dai Front End Server.</span><span class="sxs-lookup"><span data-stu-id="f24eb-368">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-369">Front End Server della chat persistente</span><span class="sxs-lookup"><span data-stu-id="f24eb-369">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="f24eb-370">SIP chat persistente</span><span class="sxs-lookup"><span data-stu-id="f24eb-370">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-371">5041</span><span class="sxs-lookup"><span data-stu-id="f24eb-371">5041</span></span></p></td>
<td><p><span data-ttu-id="f24eb-372">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f24eb-372">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-373">Front End Server della chat persistente</span><span class="sxs-lookup"><span data-stu-id="f24eb-373">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="f24eb-374">Chat persistente Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="f24eb-374">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="f24eb-375">881</span><span class="sxs-lookup"><span data-stu-id="f24eb-375">881</span></span></p></td>
<td><p><span data-ttu-id="f24eb-376">TCP (TLS) e TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f24eb-376">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-377">Front End Server della chat persistente</span><span class="sxs-lookup"><span data-stu-id="f24eb-377">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="f24eb-378">Servizio di trasferimento file di chat persistente</span><span class="sxs-lookup"><span data-stu-id="f24eb-378">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="f24eb-379">443</span><span class="sxs-lookup"><span data-stu-id="f24eb-379">443</span></span></p></td>
<td><p><span data-ttu-id="f24eb-380">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f24eb-380">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="f24eb-381">Alcuni scenari di controllo delle chiamate remote richiedono una connessione TCP tra il Front End Server o Director e il sistema PBX.</span><span class="sxs-lookup"><span data-stu-id="f24eb-381">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="f24eb-382">Anche se Lync Server non utilizza più la porta TCP 5060, durante la distribuzione del controllo delle chiamate remote viene creata una configurazione del server attendibile, che associa il nome di dominio completo del server RCC line alla porta TCP che verrà utilizzata dal front end server o dal Director per la connessione al sistema PBX.</span><span class="sxs-lookup"><span data-stu-id="f24eb-382">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="f24eb-383">Per informazioni dettagliate, vedere il cmdlet <STRONG>CsTrustedApplicationComputer</STRONG> nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f24eb-383">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="f24eb-384">Per i pool che utilizzano solo il servizio di bilanciamento del carico hardware (non il servizio di bilanciamento del carico DNS), la tabella che segue mostra le porte che devono aprire i servizi di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="f24eb-384">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="f24eb-385">Porte del servizio di bilanciamento del carico hardware se si utilizza solo questo servizio di bilanciamento</span><span class="sxs-lookup"><span data-stu-id="f24eb-385">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f24eb-386">Servizio di bilanciamento del carico</span><span class="sxs-lookup"><span data-stu-id="f24eb-386">Load Balancer</span></span></th>
<th><span data-ttu-id="f24eb-387">Porta</span><span class="sxs-lookup"><span data-stu-id="f24eb-387">Port</span></span></th>
<th><span data-ttu-id="f24eb-388">Protocollo</span><span class="sxs-lookup"><span data-stu-id="f24eb-388">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-389">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-389">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f24eb-390">5061</span><span class="sxs-lookup"><span data-stu-id="f24eb-390">5061</span></span></p></td>
<td><p><span data-ttu-id="f24eb-391">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f24eb-391">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-392">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-392">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f24eb-393">444</span><span class="sxs-lookup"><span data-stu-id="f24eb-393">444</span></span></p></td>
<td><p><span data-ttu-id="f24eb-394">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f24eb-394">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-395">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-395">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f24eb-396">135</span><span class="sxs-lookup"><span data-stu-id="f24eb-396">135</span></span></p></td>
<td><p><span data-ttu-id="f24eb-397">DCOM ed RPC (Remote Procedure Call)</span><span class="sxs-lookup"><span data-stu-id="f24eb-397">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-398">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-398">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f24eb-399">80</span><span class="sxs-lookup"><span data-stu-id="f24eb-399">80</span></span></p></td>
<td><p><span data-ttu-id="f24eb-400">HTTP</span><span class="sxs-lookup"><span data-stu-id="f24eb-400">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-401">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-401">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f24eb-402">8080</span><span class="sxs-lookup"><span data-stu-id="f24eb-402">8080</span></span></p></td>
<td><p><span data-ttu-id="f24eb-403">TCP - Recupero tramite client e dispositivi del certificato radice da Front End Server; client e dispositivi autenticati mediante NTLM</span><span class="sxs-lookup"><span data-stu-id="f24eb-403">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-404">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-404">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f24eb-405">443</span><span class="sxs-lookup"><span data-stu-id="f24eb-405">443</span></span></p></td>
<td><p><span data-ttu-id="f24eb-406">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f24eb-406">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-407">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-407">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f24eb-408">4443</span><span class="sxs-lookup"><span data-stu-id="f24eb-408">4443</span></span></p></td>
<td><p><span data-ttu-id="f24eb-409">HTTPS (da proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="f24eb-409">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-410">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-410">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f24eb-411">5072</span><span class="sxs-lookup"><span data-stu-id="f24eb-411">5072</span></span></p></td>
<td><p><span data-ttu-id="f24eb-412">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-412">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-413">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-413">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f24eb-414">5073</span><span class="sxs-lookup"><span data-stu-id="f24eb-414">5073</span></span></p></td>
<td><p><span data-ttu-id="f24eb-415">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-415">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-416">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-416">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f24eb-417">5075</span><span class="sxs-lookup"><span data-stu-id="f24eb-417">5075</span></span></p></td>
<td><p><span data-ttu-id="f24eb-418">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-418">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-419">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-419">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f24eb-420">5076</span><span class="sxs-lookup"><span data-stu-id="f24eb-420">5076</span></span></p></td>
<td><p><span data-ttu-id="f24eb-421">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-421">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-422">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-422">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f24eb-423">5071</span><span class="sxs-lookup"><span data-stu-id="f24eb-423">5071</span></span></p></td>
<td><p><span data-ttu-id="f24eb-424">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-424">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-425">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-425">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f24eb-426">5080</span><span class="sxs-lookup"><span data-stu-id="f24eb-426">5080</span></span></p></td>
<td><p><span data-ttu-id="f24eb-427">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-427">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-428">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-428">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f24eb-429">448</span><span class="sxs-lookup"><span data-stu-id="f24eb-429">448</span></span></p></td>
<td><p><span data-ttu-id="f24eb-430">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-430">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-431">Bilanciamento del carico di Mediation Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-431">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f24eb-432">5070</span><span class="sxs-lookup"><span data-stu-id="f24eb-432">5070</span></span></p></td>
<td><p><span data-ttu-id="f24eb-433">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-433">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-434">Bilanciamento del carico del server front-end (se il pool esegue anche Mediation Server)</span><span class="sxs-lookup"><span data-stu-id="f24eb-434">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="f24eb-435">5070</span><span class="sxs-lookup"><span data-stu-id="f24eb-435">5070</span></span></p></td>
<td><p><span data-ttu-id="f24eb-436">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-436">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-437">Servizio di bilanciamento del carico Director</span><span class="sxs-lookup"><span data-stu-id="f24eb-437">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="f24eb-438">443</span><span class="sxs-lookup"><span data-stu-id="f24eb-438">443</span></span></p></td>
<td><p><span data-ttu-id="f24eb-439">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f24eb-439">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-440">Servizio di bilanciamento del carico Director</span><span class="sxs-lookup"><span data-stu-id="f24eb-440">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="f24eb-441">444</span><span class="sxs-lookup"><span data-stu-id="f24eb-441">444</span></span></p></td>
<td><p><span data-ttu-id="f24eb-442">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f24eb-442">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-443">Servizio di bilanciamento del carico Director</span><span class="sxs-lookup"><span data-stu-id="f24eb-443">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="f24eb-444">5061</span><span class="sxs-lookup"><span data-stu-id="f24eb-444">5061</span></span></p></td>
<td><p><span data-ttu-id="f24eb-445">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-445">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-446">Servizio di bilanciamento del carico Director</span><span class="sxs-lookup"><span data-stu-id="f24eb-446">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="f24eb-447">4443</span><span class="sxs-lookup"><span data-stu-id="f24eb-447">4443</span></span></p></td>
<td><p><span data-ttu-id="f24eb-448">HTTPS (da proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="f24eb-448">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f24eb-p107">È necessario che anche nei pool Front End e server Director che utilizzano il servizio di bilanciamento del carico DNS sia distribuito un servizio di bilanciamento del carico hardware. Nella tabella che segue sono indicate le porte che è necessario aprire in questi servizi di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="f24eb-p107">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed. The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="f24eb-451">Porte del servizio di bilanciamento del carico hardware se si utilizza il servizio di bilanciamento del carico DNS</span><span class="sxs-lookup"><span data-stu-id="f24eb-451">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f24eb-452">Servizio di bilanciamento del carico</span><span class="sxs-lookup"><span data-stu-id="f24eb-452">Load Balancer</span></span></th>
<th><span data-ttu-id="f24eb-453">Porta</span><span class="sxs-lookup"><span data-stu-id="f24eb-453">Port</span></span></th>
<th><span data-ttu-id="f24eb-454">Protocollo</span><span class="sxs-lookup"><span data-stu-id="f24eb-454">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-455">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-455">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f24eb-456">80</span><span class="sxs-lookup"><span data-stu-id="f24eb-456">80</span></span></p></td>
<td><p><span data-ttu-id="f24eb-457">HTTP</span><span class="sxs-lookup"><span data-stu-id="f24eb-457">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-458">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-458">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f24eb-459">443</span><span class="sxs-lookup"><span data-stu-id="f24eb-459">443</span></span></p></td>
<td><p><span data-ttu-id="f24eb-460">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f24eb-460">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-461">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-461">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f24eb-462">8080</span><span class="sxs-lookup"><span data-stu-id="f24eb-462">8080</span></span></p></td>
<td><p><span data-ttu-id="f24eb-463">TCP - Recupero tramite client e dispositivi del certificato radice da Front End Server; client e dispositivi autenticati mediante NTLM</span><span class="sxs-lookup"><span data-stu-id="f24eb-463">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-464">Servizio di bilanciamento del carico Front End Server</span><span class="sxs-lookup"><span data-stu-id="f24eb-464">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="f24eb-465">4443</span><span class="sxs-lookup"><span data-stu-id="f24eb-465">4443</span></span></p></td>
<td><p><span data-ttu-id="f24eb-466">HTTPS (da proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="f24eb-466">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-467">Servizio di bilanciamento del carico Director</span><span class="sxs-lookup"><span data-stu-id="f24eb-467">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="f24eb-468">443</span><span class="sxs-lookup"><span data-stu-id="f24eb-468">443</span></span></p></td>
<td><p><span data-ttu-id="f24eb-469">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f24eb-469">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-470">Servizio di bilanciamento del carico Director</span><span class="sxs-lookup"><span data-stu-id="f24eb-470">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="f24eb-471">4443</span><span class="sxs-lookup"><span data-stu-id="f24eb-471">4443</span></span></p></td>
<td><p><span data-ttu-id="f24eb-472">HTTPS (da proxy inverso)</span><span class="sxs-lookup"><span data-stu-id="f24eb-472">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="f24eb-473">Porte client richieste</span><span class="sxs-lookup"><span data-stu-id="f24eb-473">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f24eb-474">Componente</span><span class="sxs-lookup"><span data-stu-id="f24eb-474">Component</span></span></th>
<th><span data-ttu-id="f24eb-475">Porta</span><span class="sxs-lookup"><span data-stu-id="f24eb-475">Port</span></span></th>
<th><span data-ttu-id="f24eb-476">Protocollo</span><span class="sxs-lookup"><span data-stu-id="f24eb-476">Protocol</span></span></th>
<th><span data-ttu-id="f24eb-477">Note</span><span class="sxs-lookup"><span data-stu-id="f24eb-477">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-478">Client</span><span class="sxs-lookup"><span data-stu-id="f24eb-478">Clients</span></span></p></td>
<td><p><span data-ttu-id="f24eb-479">67/68</span><span class="sxs-lookup"><span data-stu-id="f24eb-479">67/68</span></span></p></td>
<td><p><span data-ttu-id="f24eb-480">DHCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-480">DHCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-481">Utilizzato da Lync Server per individuare il nome di dominio completo del registrar, ovvero se DNS SRV ha esito negativo e le impostazioni manuali non sono configurate.</span><span class="sxs-lookup"><span data-stu-id="f24eb-481">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-482">Client</span><span class="sxs-lookup"><span data-stu-id="f24eb-482">Clients</span></span></p></td>
<td><p><span data-ttu-id="f24eb-483">443</span><span class="sxs-lookup"><span data-stu-id="f24eb-483">443</span></span></p></td>
<td><p><span data-ttu-id="f24eb-484">TCP (TLS)</span><span class="sxs-lookup"><span data-stu-id="f24eb-484">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="f24eb-485">Utilizzata per il traffico SIP da client a server per l'accesso utente esterno.</span><span class="sxs-lookup"><span data-stu-id="f24eb-485">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-486">Client</span><span class="sxs-lookup"><span data-stu-id="f24eb-486">Clients</span></span></p></td>
<td><p><span data-ttu-id="f24eb-487">443</span><span class="sxs-lookup"><span data-stu-id="f24eb-487">443</span></span></p></td>
<td><p><span data-ttu-id="f24eb-488">TCP (PSOM/TLS)</span><span class="sxs-lookup"><span data-stu-id="f24eb-488">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="f24eb-489">Utilizzata per l'accesso utente esterno alle sessioni di Web Conferencing.</span><span class="sxs-lookup"><span data-stu-id="f24eb-489">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-490">Client</span><span class="sxs-lookup"><span data-stu-id="f24eb-490">Clients</span></span></p></td>
<td><p><span data-ttu-id="f24eb-491">443</span><span class="sxs-lookup"><span data-stu-id="f24eb-491">443</span></span></p></td>
<td><p><span data-ttu-id="f24eb-492">TCP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="f24eb-492">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="f24eb-493">Utilizzata per l'accesso utente esterno alle sessioni A/V e ai supporti multimediali (TCP)</span><span class="sxs-lookup"><span data-stu-id="f24eb-493">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-494">Client</span><span class="sxs-lookup"><span data-stu-id="f24eb-494">Clients</span></span></p></td>
<td><p><span data-ttu-id="f24eb-495">3478</span><span class="sxs-lookup"><span data-stu-id="f24eb-495">3478</span></span></p></td>
<td><p><span data-ttu-id="f24eb-496">UDP (STUN/MSTURN)</span><span class="sxs-lookup"><span data-stu-id="f24eb-496">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="f24eb-497">Utilizzato per l'accesso degli utenti esterni alle sessioni A/V e ai supporti (UDP)</span><span class="sxs-lookup"><span data-stu-id="f24eb-497">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-498">Client</span><span class="sxs-lookup"><span data-stu-id="f24eb-498">Clients</span></span></p></td>
<td><p><span data-ttu-id="f24eb-499">5061</span><span class="sxs-lookup"><span data-stu-id="f24eb-499">5061</span></span></p></td>
<td><p><span data-ttu-id="f24eb-500">TCP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="f24eb-500">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="f24eb-501">Utilizzata per il traffico SIP da client a server per l'accesso utente esterno.</span><span class="sxs-lookup"><span data-stu-id="f24eb-501">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-502">Client</span><span class="sxs-lookup"><span data-stu-id="f24eb-502">Clients</span></span></p></td>
<td><p><span data-ttu-id="f24eb-503">6891-6901</span><span class="sxs-lookup"><span data-stu-id="f24eb-503">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="f24eb-504">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-504">TCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-505">Utilizzato per il trasferimento di file tra client Lync e client precedenti (client di Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 e Live Communications Server 2005).</span><span class="sxs-lookup"><span data-stu-id="f24eb-505">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-506">Client</span><span class="sxs-lookup"><span data-stu-id="f24eb-506">Clients</span></span></p></td>
<td><p><span data-ttu-id="f24eb-507">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="f24eb-507">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="f24eb-508">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="f24eb-508">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-509">Intervallo di porte audio (almeno 20 porte richieste)</span><span class="sxs-lookup"><span data-stu-id="f24eb-509">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-510">Client</span><span class="sxs-lookup"><span data-stu-id="f24eb-510">Clients</span></span></p></td>
<td><p><span data-ttu-id="f24eb-511">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="f24eb-511">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="f24eb-512">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="f24eb-512">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-513">Intervallo di porte video (almeno 20 porte richieste).</span><span class="sxs-lookup"><span data-stu-id="f24eb-513">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-514">Client</span><span class="sxs-lookup"><span data-stu-id="f24eb-514">Clients</span></span></p></td>
<td><p><span data-ttu-id="f24eb-515">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="f24eb-515">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="f24eb-516">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-516">TCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-517">Trasferimento file peer-to-peer (per il trasferimento dei file del servizio di conferenza, i client utilizzano PSOM).</span><span class="sxs-lookup"><span data-stu-id="f24eb-517">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f24eb-518">Client</span><span class="sxs-lookup"><span data-stu-id="f24eb-518">Clients</span></span></p></td>
<td><p><span data-ttu-id="f24eb-519">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="f24eb-519">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="f24eb-520">TCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-520">TCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-521">Condivisione applicazioni.</span><span class="sxs-lookup"><span data-stu-id="f24eb-521">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f24eb-522">Telefono di area comune Aastra 6721ip</span><span class="sxs-lookup"><span data-stu-id="f24eb-522">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="f24eb-523">Telefono da tavolo Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="f24eb-523">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="f24eb-524">Telefono IP HP 4110 (telefono di area comune)</span><span class="sxs-lookup"><span data-stu-id="f24eb-524">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="f24eb-525">Telefono IP HP 4120 (telefono da tavolo)</span><span class="sxs-lookup"><span data-stu-id="f24eb-525">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="f24eb-526">Telefono di area comune IP Polycom CX500</span><span class="sxs-lookup"><span data-stu-id="f24eb-526">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="f24eb-527">Telefono da tavolo IP Polycom CX600</span><span class="sxs-lookup"><span data-stu-id="f24eb-527">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="f24eb-528">Telefono da tavolo IP Polycom CX700</span><span class="sxs-lookup"><span data-stu-id="f24eb-528">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="f24eb-529">Telefono IP per conferenze Polycom CX3000</span><span class="sxs-lookup"><span data-stu-id="f24eb-529">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="f24eb-530">67/68</span><span class="sxs-lookup"><span data-stu-id="f24eb-530">67/68</span></span></p></td>
<td><p><span data-ttu-id="f24eb-531">DHCP</span><span class="sxs-lookup"><span data-stu-id="f24eb-531">DHCP</span></span></p></td>
<td><p><span data-ttu-id="f24eb-532">Utilizzato dai dispositivi elencati per individuare il certificato di Lync Server, il nome di dominio completo e il nome di dominio completo del servizio di registrazione.</span><span class="sxs-lookup"><span data-stu-id="f24eb-532">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f24eb-533">**\*** Per configurare porte specifiche per questi tipi di supporti, utilizzare il cmdlet CsConferencingConfiguration (parametri ClientMediaPortRangeEnabled, ClientMediaPort e ClientMediaPortRange).</span><span class="sxs-lookup"><span data-stu-id="f24eb-533">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f24eb-534">I programmi set per i client di Lync creano automaticamente le eccezioni del firewall del sistema operativo necessarie sul computer client.</span><span class="sxs-lookup"><span data-stu-id="f24eb-534">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="f24eb-535">Le porte utilizzate per l'accesso utente esterno sono richieste per tutti gli scenari in cui il client deve attraversare il firewall dell'organizzazione, ad esempio per qualsiasi comunicazione o riunione esterna ospitata da altre organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="f24eb-535">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

