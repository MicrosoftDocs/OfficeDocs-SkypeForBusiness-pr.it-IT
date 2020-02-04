---
title: "Lync Server 2013: Componenti necessari per l'accesso degli utenti esterni"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for external user access
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425779(v=OCS.15)
ms:contentKeyID: 48183711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 550eb864ff7cc26eb0bfeace37759bb15b9816f6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="e4683-102">Componenti necessari per l'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4683-102">Components required for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4683-103">_**Argomento Ultima modifica:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="e4683-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="e4683-104">La maggior parte dei componenti Edge viene distribuita in una rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="e4683-104">Most Edge components are deployed in a perimeter network.</span></span> <span data-ttu-id="e4683-105">I componenti seguenti costituiscono la topologia di Edge della rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="e4683-105">The following components make up the edge topology of the perimeter network.</span></span> <span data-ttu-id="e4683-106">Eccetto dove indicato, i componenti fanno parte degli [scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) e si trovano nella rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="e4683-106">Except where noted, the components are part of the [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and are in the perimeter network.</span></span> <span data-ttu-id="e4683-107">I componenti Edge includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4683-107">Edge components include the following:</span></span>

  - <span data-ttu-id="e4683-108">Edge Server</span><span class="sxs-lookup"><span data-stu-id="e4683-108">Edge Servers</span></span>

  - <span data-ttu-id="e4683-109">Reverse proxy</span><span class="sxs-lookup"><span data-stu-id="e4683-109">Reverse proxies</span></span>

  - <span data-ttu-id="e4683-110">Firewall</span><span class="sxs-lookup"><span data-stu-id="e4683-110">Firewalls</span></span>

  - <span data-ttu-id="e4683-111">Amministratori (facoltativi e logicamente presenti nella rete interna)</span><span class="sxs-lookup"><span data-stu-id="e4683-111">Directors (optional, and logically located on the internal network)</span></span>

  - <span data-ttu-id="e4683-112">Bilanciamento del carico per le topologie di Edge in scala (bilanciamento del carico DNS o un servizio di bilanciamento del carico hardware)</span><span class="sxs-lookup"><span data-stu-id="e4683-112">Load balancing for Scaled Edge Topologies (either DNS load balancing or a hardware load balancer)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e4683-113">L'uso del bilanciamento del carico DNS su un'interfaccia e il bilanciamento del carico hardware dall'altro non è supportato.</span><span class="sxs-lookup"><span data-stu-id="e4683-113">Using DNS load balancing on one interface and hardware load balancing on the other is not supported.</span></span> <span data-ttu-id="e4683-114">È necessario usare il bilanciamento del carico hardware per entrambe le interfacce o il bilanciamento del carico DNS per entrambi.</span><span class="sxs-lookup"><span data-stu-id="e4683-114">You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>

    
    </div>

<div>

## <a name="edge-servers"></a><span data-ttu-id="e4683-115">Edge Server</span><span class="sxs-lookup"><span data-stu-id="e4683-115">Edge Servers</span></span>

<span data-ttu-id="e4683-116">Gli Edge Server inviano e ricevono il traffico di rete per i servizi offerti dalla distribuzione interna da parte di utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="e4683-116">The Edge Servers send and receive network traffic for the services offered by internal deployment by external users.</span></span> <span data-ttu-id="e4683-117">Il server perimetrale esegue i servizi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4683-117">The Edge Server runs the following services:</span></span>

  - <span data-ttu-id="e4683-118">**Access Edge Services**   il servizio Access Edge offre un unico punto di connessione attendibile per il traffico SIP (Session Initiation Protocol) in uscita e in ingresso.</span><span class="sxs-lookup"><span data-stu-id="e4683-118">**Access Edge service**   The Access Edge service provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>

  - <span data-ttu-id="e4683-119">**Web Conferencing Edge service**   il Web Conferencing Edge service consente agli utenti esterni di partecipare a riunioni ospitate nella distribuzione interna di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e4683-119">**Web Conferencing Edge service**   The Web Conferencing Edge service enables external users to join meetings that are hosted on your internal Lync Server 2013 deployment.</span></span>

  - <span data-ttu-id="e4683-120">**A/v Edge service**   l'a/v Edge Services rende disponibili audio, video, condivisione applicazioni e trasferimento di file per gli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="e4683-120">**A/V Edge service**   The A/V Edge service makes audio, video, application sharing, and file transfer available to external users.</span></span> <span data-ttu-id="e4683-121">Gli utenti possono aggiungere audio e video alle riunioni che includono partecipanti esterni e possono comunicare usando audio e/o video direttamente con un utente esterno nelle sessioni Point-to-Point.</span><span class="sxs-lookup"><span data-stu-id="e4683-121">Your users can add audio and video to meetings that include external participants, and they can communicate using audio and/or video directly with an external user in point-to-point sessions.</span></span> <span data-ttu-id="e4683-122">Il servizio A/V Edge offre anche il supporto per la condivisione desktop e il trasferimento di file.</span><span class="sxs-lookup"><span data-stu-id="e4683-122">The A/V Edge service also provides support for desktop sharing and file transfer.</span></span>

  - <span data-ttu-id="e4683-123">**Servizio proxy XMPP**   il servizio proxy XMPP accetta e invia i messaggi XMPP (Extensible Messaging and Presence Protocol) a e da partner federativi XMPP configurati.</span><span class="sxs-lookup"><span data-stu-id="e4683-123">**XMPP Proxy service**   The XMPP Proxy service accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>

<span data-ttu-id="e4683-124">Gli utenti esterni autorizzati possono accedere agli Edge Server per connettersi alla distribuzione interna di Lync Server 2013, ma gli Edge Server non consentono di accedere alla rete interna.</span><span class="sxs-lookup"><span data-stu-id="e4683-124">Authorized external users can access the Edge Servers in order to connect to your internal Lync Server 2013 deployment, but the Edge Servers do not provide a means for any other access to the internal network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e4683-125">I server perimetrali vengono distribuiti per consentire connessioni per i client Lync abilitati e altri server Microsoft Edge (come in scenari federativi).</span><span class="sxs-lookup"><span data-stu-id="e4683-125">Edge servers are deployed to provide connections for enabled Lync clients and other Microsoft Edge servers (as in federation scenarios).</span></span> <span data-ttu-id="e4683-126">Non sono progettate per consentire connessioni da altri tipi di client o server di fine Point.</span><span class="sxs-lookup"><span data-stu-id="e4683-126">They are not designed to allow connections from other end point client or server types.</span></span> <span data-ttu-id="e4683-127">Il server gateway XMPP può essere distribuito per consentire connessioni con partner XMPP configurati.</span><span class="sxs-lookup"><span data-stu-id="e4683-127">The XMPP Gateway server can be deployed to allow connections with configured XMPP partners.</span></span> <span data-ttu-id="e4683-128">Il gateway Edge Server e XMPP può supportare solo le connessioni di fine punto da questi tipi di client e federazioni.</span><span class="sxs-lookup"><span data-stu-id="e4683-128">The Edge server and XMPP Gateway can only support end point connections from these client and federation types.</span></span>



</div>

</div>

<div>

## <a name="reverse-proxy"></a><span data-ttu-id="e4683-129">Proxy inverso</span><span class="sxs-lookup"><span data-stu-id="e4683-129">Reverse Proxy</span></span>

<span data-ttu-id="e4683-130">Il proxy inverso è necessario per gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4683-130">The reverse proxy is required for the following:</span></span>

  - <span data-ttu-id="e4683-131">Per consentire agli utenti di connettersi a riunioni o conferenze telefoniche con accesso esterno usando URL semplici</span><span class="sxs-lookup"><span data-stu-id="e4683-131">To allow users to connect to meetings or dial-in conferences using simple URLs</span></span>

  - <span data-ttu-id="e4683-132">Per consentire agli utenti esterni di scaricare il contenuto della riunione</span><span class="sxs-lookup"><span data-stu-id="e4683-132">To enable external users to download meeting content</span></span>

  - <span data-ttu-id="e4683-133">Per consentire agli utenti esterni di espandere i gruppi di distribuzione</span><span class="sxs-lookup"><span data-stu-id="e4683-133">To enable external users to expand distribution groups</span></span>

  - <span data-ttu-id="e4683-134">Per consentire all'utente di ottenere un certificato basato sull'utente per l'autenticazione basata su certificato client</span><span class="sxs-lookup"><span data-stu-id="e4683-134">To allow the user to obtain a user-based certificate for client certificate based authentication</span></span>

  - <span data-ttu-id="e4683-135">Per consentire agli utenti remoti di scaricare i file dal server della Rubrica o di inviare query al servizio query Web Rubrica</span><span class="sxs-lookup"><span data-stu-id="e4683-135">To enable remote users to download files from the Address Book Server or to submit queries to the Address Book Web Query service</span></span>

  - <span data-ttu-id="e4683-136">Per consentire agli utenti remoti di ottenere gli aggiornamenti al software client e dispositivi</span><span class="sxs-lookup"><span data-stu-id="e4683-136">To enable remote users to obtain updates to client and device software</span></span>

  - <span data-ttu-id="e4683-137">Per consentire ai dispositivi mobili di individuare automaticamente i server front-end che offrono servizi di mobilità</span><span class="sxs-lookup"><span data-stu-id="e4683-137">To enable mobile devices to automatically discover Front End Servers offering mobility services</span></span>

  - <span data-ttu-id="e4683-138">Per abilitare le notifiche push ai dispositivi mobili da Office 365 o Apple Push Notification Services</span><span class="sxs-lookup"><span data-stu-id="e4683-138">To enable push notifications to mobile devices from the Office 365 or Apple push notification services</span></span>

<span data-ttu-id="e4683-139">Per altre informazioni relative ai proxy inversi e ai requisiti che devono essere conformi ai proxy inversi, vedere i dettagli dei [requisiti di configurazione per il proxy inverso in Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="e4683-139">For additional information related to reverse proxies and the requirements that reverse proxies must meet, see the details in [Configuration requirements for reverse proxy in Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e4683-140">Gli utenti esterni non hanno bisogno di una connessione VPN (Virtual Private Network) alla propria organizzazione per partecipare alle comunicazioni tramite Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e4683-140">External users do not need a virtual private network (VPN) connection to your organization in order to participate in communications using Lync Server 2013.</span></span> <span data-ttu-id="e4683-141">Se è stata implementata la tecnologia VPN nell'organizzazione e gli utenti usano la VPN per Lync, il traffico multimediale (ad esempio videoconferenza) può essere influenzato negativamente.</span><span class="sxs-lookup"><span data-stu-id="e4683-141">If you have implemented VPN technology in your organization and your users use the VPN for Lync, media traffic (such as video conferencing) can be adversely affected.</span></span> <span data-ttu-id="e4683-142">È consigliabile fornire un mezzo per il traffico multimediale per connettersi direttamente al servizio Edge AV e ignorare la VPN.</span><span class="sxs-lookup"><span data-stu-id="e4683-142">You should consider providing a means for media traffic to connect to the AV Edge service directly and bypass the VPN.</span></span> <span data-ttu-id="e4683-143">Per informazioni dettagliate, vedere l'articolo su Blog di NextHop "Abilitazione di Lync media per ignorare un tunnel <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>VPN".</span><span class="sxs-lookup"><span data-stu-id="e4683-143">For details, see the NextHop Blog article, “Enabling Lync Media to Bypass a VPN Tunnel,” at <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>.</span></span>



</div>

</div>

<div>

## <a name="firewall"></a><span data-ttu-id="e4683-144">Firewall</span><span class="sxs-lookup"><span data-stu-id="e4683-144">Firewall</span></span>

<span data-ttu-id="e4683-145">È possibile distribuire la topologia di Edge con solo un firewall esterno o sia firewall esterni che interni.</span><span class="sxs-lookup"><span data-stu-id="e4683-145">You can deploy your edge topology with only an external firewall or both external and internal firewalls.</span></span> <span data-ttu-id="e4683-146">Le architetture di scenario includono due firewall.</span><span class="sxs-lookup"><span data-stu-id="e4683-146">The scenario architectures include two firewalls.</span></span> <span data-ttu-id="e4683-147">L'uso di due firewall è l'approccio consigliato perché garantisce un routing rigoroso da un bordo di rete all'altro e protegge la distribuzione interna dietro due livelli di firewall.</span><span class="sxs-lookup"><span data-stu-id="e4683-147">Using two firewalls is the recommended approach because it ensures strict routing from one network edge to the other, and it protects your internal deployment behind two levels of firewall.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="e4683-148">Director</span><span class="sxs-lookup"><span data-stu-id="e4683-148">Director</span></span>

<span data-ttu-id="e4683-149">Un amministratore è un ruolo del server facoltativo separato in Lync Server 2013 che non ospita gli account utente o offre servizi di conferenza o presenza.</span><span class="sxs-lookup"><span data-stu-id="e4683-149">A Director is a separate, optional server role in Lync Server 2013 that does not home user accounts, or provide presence or conferencing services.</span></span> <span data-ttu-id="e4683-150">Funge da server hop interno successivo a cui un Edge Server instrada il traffico SIP in ingresso destinato ai server interni.</span><span class="sxs-lookup"><span data-stu-id="e4683-150">It serves as an internal next hop server to which an Edge Server routes inbound SIP traffic destined for internal servers.</span></span> <span data-ttu-id="e4683-151">Il Director effettua la preautenticazione delle richieste in ingresso e le reindirizza al server o al pool di utenti.</span><span class="sxs-lookup"><span data-stu-id="e4683-151">The Director preauthenticates inbound requests and redirects them to the user’s home pool or server.</span></span> <span data-ttu-id="e4683-152">Eseguendo la preautenticazione presso il Director, è possibile eliminare le richieste da un account utente sconosciuto alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e4683-152">By preauthenticating at the Director, you can drop requests from user accounts that are unknown to the deployment.</span></span>

<span data-ttu-id="e4683-153">Un amministratore consente di isolare i server standard e i server front-end nei pool Front End di Enterprise Edition da traffico illecito, ad esempio attacchi DoS (Denial of Service).</span><span class="sxs-lookup"><span data-stu-id="e4683-153">A Director helps insulate Standard Edition servers and Front End Servers in Enterprise Edition Front End pools from malicious traffic such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="e4683-154">Se la rete viene allagata con traffico esterno non valido in un attacco di questo tipo, il traffico termina con il direttore.</span><span class="sxs-lookup"><span data-stu-id="e4683-154">If the network is flooded with invalid external traffic in such an attack, the traffic ends at the Director.</span></span> <span data-ttu-id="e4683-155">Per informazioni dettagliate sull'uso dei direttori, vedere [scenari per il Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="e4683-155">For details about the use of Directors, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e4683-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4683-156">See Also</span></span>


[<span data-ttu-id="e4683-157">Requisiti relativi al servizio di bilanciamento del carico hardware per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4683-157">Hardware load balancer requirements for Lync Server 2013</span></span>](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

